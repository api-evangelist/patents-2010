---

title: Method and system for improving performance of a manufacturing execution system
abstract: A manufacturing execution system contains a depicting device for depicting at least a part of a productive process to a hierarchically structured set of entities and an application programming interface for managing data in a data base and for inputting a tree into the application programming interface. The tree representing a hierarchical relationship between at least two entities of the hierarchically structured set of entities. A program device provides a method accessible by the application programming interface. The method is adapted to manipulate the hierarchically structured set of entities. A manipulating device is provided for manipulating the entities of the tree according to the method.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08452810&OS=08452810&RS=08452810
owner: Siemens Aktiengesellschaft
number: 08452810
owner_city: Munich
owner_country: DE
publication_date: 20100716
---
This application claims the priority under 35 U.S.C. 119 of European application EP 09171793 filed Sep. 30 2009 the prior application is herewith incorporated by reference in its entirety.

The present invention relates to a method and systems for improving the performance of a manufacturing execution system MES according to the independent claims.

ISA S95 is an international standard defining and describing enterprise activities and control activities. For example it provides standard models and terminology for defining the interfaces between an enterprise s business systems and its manufacturing execution systems MES .

Inside the ISA S95 it is possible to find a definition for the information flow between the enterprise and the manufacturing execution systems and a definition for the information exchanged between the enterprise and the manufacturing execution systems. Then practically the information exchanged between the enterprise and the MES is usually stored by the MES in a data base.

The information exchanged and their definitions are listed inside ISA S95. They are modeled inside the MES database with tables. They represent the different kind of resources exchanged and managed by the MES. The different kind of information represents the entities involved and managed by the MES. In this context the terms node and entity are often used synonymously. Examples of entities include a production request a segment requirement a material in input a material in output manpower requirements equipment material production parameters properties related to persons material and other needs or resources in order to perform the execution of a productive process to obtain the final product.

A segment requirement is defined by ISA S95 as a production step. It even identifies or references the capability to which the associated personnel equipment materials and production parameters correspond. Besides a production request is made up of one or more segment requirements.

ISA S95 defines the use of a hierarchically structured set of entities in order to represent a productive process. The term tree is often used synonymously in order to address such a hierarchically structured set of entities or a subset of such a hierarchically structured set of entities.

Usually a manufacturing execution system MES provides an application programming interface API on a user interface side in order to let the user access data of a data base DB of the MES. The API therefore usually contains measures to access a set of methods in one of the nowadays available technologies in order to manage the data in the DB. The main methods usually exposed to the user are Get in order to get data from the DB Add in order to add data to the DB Delete in order to delete data from the DB and Edit in order to edit data of the DB . In the classic approach a MES provides to the user the methods aforementioned for each entity of the S95 hierarchy resulting in a huge number of methods exposed. An API of a typical nowadays MES therefore usually contains hundreds of methods each method working at a specific level and without the chance to perform different action at different entity level inside the hierarchy.

Thus each method usually performs its operation only for a specific entity. For example an Edit method for the production request usually allows the user to edit data of the production request but does not allow to edit children entities of the production request for example Segment Requirement . In this case a user that should perform an operation considering the whole hierarchy of for example a Production Request should call one by one the methods to perform the desired operation. This is a time consuming operation because for each method call a round trip between the client application and the server application is required. This means that for each method call the data needed to perform the operation should be transported through the network from the client application to the server application.

In other words a large number of methods exposed by the API require significant time for a user when he wants to manipulate the MES since the methods need to be called up individually for a large number of entities. In addition due to the repetitive work there is an increased risk that the user makes an error in his manipulation.

An additional disadvantage of the state of the art solutions is that each method that is called up involves a roundtrip between the data base and the application server requiring resources and time.

Besides during merging of data between external sources the editing of the data in the DB becomes critical because thousands of operations may be required.

It is accordingly an object of the invention to provide a method and a system for improving performance of a manufacturing execution system which overcome the above mentioned disadvantages of the prior art methods and devices of this general type.

According to an aspect of the invention in order to improve the performance of a manufacturing execution system that depicts at least a part of a productive process to a hierarchically structured set of entities and that provides an application programming interface for managing data in a data base a method that is accessible by the API is provided. The method is adapted to manipulate the hierarchically structured set of entities. A tree that represents a hierarchical relationship between at least two entities of the hierarchically structured set of entities can be inputted into the API. At least two of the entities of the tree are manipulated according the method.

According to another aspect of the invention a manufacturing execution system contains a depicting device for depicting at least a part of a productive process to a hierarchically structured set of entities and an application programming interface for managing data in a data base and for inputting a tree into the application programming interface. The tree represents a hierarchical relationship between at least two entities of the hierarchically structured set of entities. A program device provides a method accessible by the application programming interface. The method is adapted to manipulate the hierarchically structured set of entities. A manipulating device is provided for manipulating the entities of the tree according the method.

According to a preferred embodiment the tree represents a hierarchical relationship between all entities of the hierarchically structured set of entities.

According to another preferred embodiment the tree is inputted into the API as a code written in Extensible Markup Language XML .

According to another preferred embodiment the method specifies a specific behavior for each entity of the tree.

According to a preferred embodiment of the invention a single method is applied in order to input an XML tree representing the hierarchical structure that the user wants to manage e.g. wants to insert in the DB . An XML code will thus provide a tree representation of the data and each node of this tree will be processed according to the specified behavior for the whole set of data in input e.g. inserting of the nodes . In addition a specific behavior can be specified for each node in order to be able to manage exception.

According to a preferred embodiment the MES contains means adapted to specify the set of method calls a user wants to perform and with means to call up the method with a single method call. In order to reach this goal a single method on the user interface COM object or C assembly is able to receive as an input an xml code representing the hierarchy S95. Each node of the XML input represents an entity of the S95 hierarchy. The user can specify at the global level but even at the node level the operation to perform for that specific entity EDIT ADD DELETE .

According to a preferred embodiment operations are performed in the same method call but managing different kinds of entities e.g. Material Produced Requirement and Equipment Requirement at the same time which is particularly useful when the MES system is importing data from external sources like SAP.

According to a preferred embodiment the tree analysis works processing each single node of the tree and performing the required operation. In this way with a single method call it is possible to manage different entities at the same time.

An advantage of the invention is that the number of calls between the user interface and DB in a MES system can be reduced improving the performance in terms of time. Besides the use of a hierarchical XML tree provides the user the possibility to mix different kind of entities at the same time.

An advantage is the reduction of the number of round trips and the reduction of the number of methods on the user interface allowed by hierarchical operation because a user can add a node and its sub tree in one shot reducing the amount of time to perform the required operation. If all data is put in one single method call roundtrips are saved.

Other features which are considered as characteristic for the invention are set forth in the appended claims.

Although the invention is illustrated and described herein as embodied in a method and a system for improving performance of a manufacturing execution system it is nevertheless not intended to be limited to the details shown since various modifications and structural changes may be made therein without departing from the spirit of the invention and within the scope and range of equivalents of the claims.

The construction and method of operation of the invention however together with additional objects and advantages thereof will be best understood from the following description of specific embodiments when read in connection with the accompanying drawings.

Referring now to the figures of the drawing in detail and first particularly to thereof there is shown an XML tree with hierarchically structured entities . One of the entities represents a production request which can be the same production request as represented by entity depicted in or which can also be a different production request. The production request shown in is a parent entity of three other entities which represent three segment requirements. The segment requirement 1 represented by entity does not have a local behavior while the segment requirement 2 and the segment requirement 3 represented by entities do have a local behavior.

The production request represented by entity provides a global behavior Add that will be applied to each entity that does not have a local behavior Segment Requirement 1 . Segment requirement 2 and segment requirement 3 represented by entities and instead will consider the local behavior Delete Update.

According to a preferred embodiment the tree represents a hierarchical relationship between all entities of the hierarchically structured set of entities.

According to another preferred embodiment the tree can be inputted into the application programming interface as a code written in Extensible Markup Language XML.

According to another preferred embodiment the calling up of the method involves a single round trip between a client application and a server application.

According to another preferred embodiment the method specifies a specific behavior for each entity of the tree.

