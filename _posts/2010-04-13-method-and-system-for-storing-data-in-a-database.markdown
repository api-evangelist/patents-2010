---

title: Method and system for storing data in a database
abstract: A method allows one to store in a parallel way branches and nodes of a hierarchy into a database by creating queues. Each queue has a status and a unlock item indicating if a superior node has already been stored. A process looks up these indicators and performs according to commands received from a first process control of the queues.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08862628&OS=08862628&RS=08862628
owner: Siemens Aktiengesellschaft
number: 08862628
owner_city: Munich
owner_country: DE
publication_date: 20100413
---
This application claims the priority under 35 U.S.C. 119 of European application EP 09157843 filed Apr. 14 2009 the prior application is herewith incorporated by reference in its entirety.

The present invention relates to a method and a system for storing a hierarchy in a relational database management system RDBMS used within a manufacturing execution system MES . The hierarchy has a root element and is structured into branches with nodes. The method is carried out by a first process knowing the hierarchy and a second process storing branches in the database and the second process receives commands from the first process.

In the world of process automation and process monitoring standard automation systems for controlling the widest conceivable variety of machines and plants are known in the prior art. Such technology covers in particular a broad range of products which are offered by the Siemens Corporation under its SIMATIC product family within the field of manufacturing execution systems MES . An extensive line of products for solving the technical tasks in question such as counting measuring positioning motion control closed loop control and cam control enhance the performance capabilities of appropriate process controllers. A variety of configurations enable the implementation of flexible machine concepts.

Software programs can deal with and represent data in various ways. Nowadays the most popular of them are Object Oriented programming and relational databases. Many programs representing data as objects maintain objects live in memory or in their process allocation space mainly for performance reasons in this way in fact objects are immediately available to processes without the need of accessing a data storage component as a relational database management system RDBMS . On the contrary RDBMS give a powerful way to make data persistent and allow other software components to access them in a standard way. The set of objects living in the process allocation space i.e. directly available on physical memory is usually referred as the process image.

In manufacturing execution systems MES software applications relational databases are broadly used not only to store data stemming from the production process but also and even more attributed to store configuration data application data and system data.

The process image of complex programs can be very complex as well and objects there contained can be related to each other forming a hierarchy which can be of different types. In an MES environment a common hierarchy is the topological one where a plant can be described by a set of objects which can in turn contain other objects of a lower level.

In many cases in MES applications we have to handle the persistence in a RDBMS of entities objects hierarchies that are living in a process image managed using an Object Oriented Approach. One of these topological hierarchies is the plant model with all equipment defined for a plant according to the s95 standard levels see ANSI ISA 95.00.01 2000 Enterprise Control System Integration Part 1 Models and Terminology. Each equipment instance is an entity with a standard attribute a list of other equipment methods and default values. Such equipment is inserted in a topological hierarchy and thus it may contain other equipment which in turn contains other and so on.

Storing an actual plant can require a lot of time because any equipment has to be sent to the database with a correct sequence in order to create an effective and a correct hierarchy into the database tables. There in fact each item of equipment must be saved only when a superior one i.e. the one which contains it has already been saved. Note that in order to correctly store a plant it is necessary to store the relation with the parent node for any child equipment. It has to be noted that this problem relies also on the wide field of object relational mapping ORM which is one of the tougher things to accomplish in modern object oriented programming languages.

Usually this operation is made in an asynchronous way sending the object data in a queue. A dedicated process takes data from the queue and stores it in the database. The data have to be inserted in the queue in the correct order first is the root entity then the first children level and so on. On the other side the process that stores data in a RDBMS has to proceed storing the root equipment and then the first children level of equipments storing also for each child the relation with the parent node. The correct ordering is guaranteed by the fact that 

The module where the hierarchy is defined is the one which inserts the equipment in queue and thus can insert them in the correct order.

Elements in the queue are stored one by one the subsequent element is stored only when the previous has been correctly stored thus not altering the order.

i Since storing the equipment in RDBMS is an operation longer than inserting it in a queue to avoid that it may grow indefinitely speed of saving is ultimately determined by RDBMS.

ii Additionally to preserving ordering the queue is unique and it is not possible to take advantage of multiprocessor hardware HW which is available now.

Due to the above problems this operation can be very time consuming and ultimately unaffordable in case of a hierarchy with large structures to save. In such a case downloading a plant model of medium complexity can require hours of work on the RDBMS side.

It is accordingly an object of the invention to provide a method and a system for storing a hierarchy in a RDBMS which overcome the drawbacks of the known solutions for storing a hierarchy in a RDBMS of the prior art methods and devices of this general type.

With the foregoing and other objects in view there is provided in accordance with the invention a method for storing a hierarchy in a database being part of a relational database management system. The hierarchy has a root element and is structured into branches with nodes. The method is carried out by a first process knowing the hierarchy and a second process storing the branches in the database. The second process receives commands from the first process. The method includes structuring the second process in queues where a queue is created via a command from the first process except a first queue which is always present with a status RUNNING. The other queues are created with a status WAIT. Each of the queues has access to the database independently from another one of the queues. The root element is inserted in the first queue and the root element is stored in the database. Further nodes of the hierarchy are inserted in the other queues where in each of the queues an unlock item is held indicating if a superior node already has been stored in the database if not the queue is held in the status WAIT until the unlock item contains an id of the superior node. A threading of the queues is performed via the second process by extracting a first node storing the first node in the database and looking in the other queues if one of them has the unlocked item equal to the superior node just stored and changing the status of the queue to RUNNING.

To speed up the overall operation objects must be stored in parallel while maintaining a correct ordering. The basic idea comes noting that the order must be maintained inside a branch of the global tree but parallel branches can be stored independently. Exploiting this idea makes it possible for the storing process to able to work in parallel each branch of the tree will in fact be processed by a different thread running in parallel. The number of threads can be configured taking in account PC resource usage versus speed of saving and spread of hierarchy. Since the number of threads does not affect the saving process behavior but only its speed the process is easily scalable according to user needs.

The advantages of the present invention are related to the possibility to save in a parallel way a branch of a hierarchy leaving to the owner of the tree the configuration and the optimization of the algorithm to avoid queue to stop start many time.

With this approach saving complex hierarchy of objects in databases is feasible in reasonable time. Moreover the time can be further reduced by adjusting the number of queues leveraging multiprocessor architectures more and more common nowadays. With this approach we can make complex hierarchies of objects saved on RDBMS in a time which is compatible with real time operations. In this way the publication of such structures living in process images of single programs can be done on standard ROBMS opening a wide set of possibilities.

The proposed algorithm can be in advance widely used in every case where a object oriented structure must be saved on RDBMS like in the more recent object oriented programming methodologies see Microsoft s OEM for an example .

Other features which are considered as characteristic for the invention are set forth in the appended claims.

Although the invention is illustrated and described herein as embodied in a method and a system for storing a hierarchy in a RDBMS it is nevertheless not intended to be limited to the details shown since various modifications and structural changes may be made therein without departing from the spirit of the invention and within the scope and range of equivalents of the claims.

The construction and method of operation of the invention however together with additional objects and advantages thereof will be best understood from the following description of specific embodiments when read in connection with the accompanying drawings.

Referring now to the figures of the drawing in detail and first particularly to thereof there is shown as an example of a hierarchy a plant hierarchy. The hierarchy is structured into several branches. It can be easily noticed that each branch can be saved independently from others. One may assume to have more than one queue saving objects. This is not yet sufficient however because it is not wanted that each queue will be statically assigned to a branch of the tree. In other words it is not wanted that in the previous example CELL PO O branch will be managed by queue Q and CELL PO branch by queue Q.

i Saving time in the different branches can vary in unpredictable ways it depends from a single object s complexity which should not be considered in advance to speed up the algorithm .

ii The number of elements in the branches and the sub branches can be very different so having a queue working and another empty and thus not exploiting parallel computing.

iii It may not be inserted a predictive algorithm to decide which queue must be used instead the algorithm must work even if the queue is chosen randomly.

So the algorithm must deal with the fact that in the same queue objects belonging to different trees must be inserted while still maintaining the correct order between them.

1. Process P manages the object hierarchy and is shown in . This is an object oriented process which holds the process image and deals with living objects particularly it knows the hierarchy. The main tasks of process P are now described 

2. The Storing Server creates and manages queues and stores objects in a RDBMS being part of a database system having a database as shown in . A direct link library DLL that expose the set of an application programming interface API has to be used by the process P in order to communicate with the server. The main tasks of the Storing Server are 

3. A queue is an item living in the process P respectively in the storing server created by a command from the process P which has the following attributes 

3.2 Unlock Item Is an identification of the item that has to be already saved into RDBMS before proceeding to extract a new item from the queue.

3.3 Item list Contains items representing the entities to be stored on the database each item is a node of hierarchy.

3.4 The number of items in the queue zero means an empty queue . It has to be considered that the queue has a maximum dimension in term of bytes.

The status of a queue determines its behavior when a queue is in status WAIT no elements will be saved.

4.2 The status is set to RUNNING at the creation by default. All remaining queues are created with the status set to WAIT.

4.3 The unlock element for all queues except the main queue contains the name of the Root of the plant hierarchy.

5. Item is a file of type XML that contains data to be stored in this file of type XML the following information are mandatory.

a Process P looking at a hierarchy to save and a user configuration asks Process P to create n queues.

b Process P looks if the requested number of queues has already been created if not it will be created.

c Process P inserts the hierarchy root element in the main queue all other queues are waiting for the root to be saved .

d Process P recursively looks at sub nodes of the tree and inserts them in available queues. The choice of the queue must not be important it can be a simple round robin algorithm. What is important is that each item is inserted with the knowledge of its superior i.e. the object containing it in hierarchy . e Process P threads managing queues by the steps 

b V.3 Once saved it looks on other waiting queues if some of them has the unlock item equal to the one just saved it changes its status to RUNNING 

 1 A superior object SO is inserted in a queue Q different from that containing a child node CN in Queue Q 

 3 The queue Q status is checked due to the save of the superior object SO from queue Q before being set to fail due to failure in saving the child Node CN .

In this case when the superior object SO is saved queue Q is not awakened because is still running and shortly after queue Q is put in wait by failure in saving the CN without being awakened later by queue Q because the SO has already been saved .

This is true also in case where we have more than two queues. To avoid this dead lock a simple retry mechanism can be added at the last point of the previous algorithm when the saving on RDBMS fails because the superior object has not been saved another retry is issued. The retry for sure comes after the saving of the superior object and thus the saving can proceed. To cover each possible time combination this retry is issued when both of the following conditions occur 

An embodiment of the present invention will be explained with the following example let s suppose that the below depicted hierarchy has to be saved on a RDBMS 

A user configured process P is to have 3 queues available inserting an element in a queue from process P to the storing server is faster than storing an element from the queue to the RDBMS. At a certain point a connection between the RDBMS and the storing server might break. Let s now follow a step by step discussion of what can happen with the proposed algorithm 

2. At time tprocess P starts to insert Site O in the database and process P inserts new elements in queues.

5. At time tQ of Process P tries to save item cell 011 but fails because Area 01 is not yet committed in the database.

Process P saves cell 011 in the database if operation succeeds it is possible to process a new item in queue. If the insert in the database fails because the parent equipment is missing step 6 see above is repeated.

