---

title: Image forming apparatus, method of controlling image forming apparatus, and memory medium for storing computer program for executing method, with function program providing API
abstract: An image forming apparatus in which a control program can be loaded, the control program providing a service for image forming processing, said apparatus comprising: a memory unit configured to store (i) an operating system, (ii) an interpreter which provides an execution environment to execute the control program, runs on the operating system, and interprets the control program, (iii) a driver program for controlling image forming processing, and (iv) a function program, wherein the driver program operates a hardware resource unit which includes at least one of a printing unit and an image pickup unit, and wherein the function program (a) serves as an API (Application Programming Interface), (b) is defined between the control program and the driver program, and (c) is used by the control program.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07973963&OS=07973963&RS=07973963
owner: Canon Kabushiki Kaisha
number: 07973963
owner_city: Tokyo
owner_country: JP
publication_date: 20100816
---
This application is a division of application Ser. No. 12 546 736 filed Aug. 25 2009 which is a division of application Ser. No. 11 768 389 filed Jun. 26 2007 U.S. Pat. No. 7 633 643 B2 which is a division of application Ser. No. 10 727 621 filed Dec. 5 2003 U.S. Pat. No. 7 259 883 B2 which is a division of application Ser. No. 09 274 334 filed Mar. 23 1999 U.S. Pat. No. 6 747 753 B1.

The invention relates to an image processing apparatus having an image processing unit to perform image processes and to a control method of such an image processing apparatus. The invention also relates to a storage medium in which a control program for such an image processing apparatus has been stored.

Hitherto OA Office Automation apparatuses such as a copying machine facsimile printer image scanner image file system telephone with an advanced function and the like have widely been used.

Hitherto most of those OA apparatuses are not connected to a network but have provided functions while being limited in sole equipment. In recent years however those OA apparatuses used so far in a stand alone manner are connected to a network such as an Ethernet or the like and are started to be commonly used by a plurality of computers or the like as clients.

For example a technique such that a plurality of clients commonly use image processing apparatuses such as a copying machine facsimile printer image scanner and the like via a network has been put into practical use relatively from early on.

In the conventional technique however when the clients use such OA apparatuses via the network the OA apparatuses need to be always communicated with the clients via the network for a period of time of processes.

For example when a client program which is executed on a client such a workstation personal computer portable information terminal or the like uses services which are provided by the OA apparatus a processing request and data necessary for processes are transmitted to a server program that is executed on the OA apparatus in accordance with a predetermined protocol for example a network protocol such as LPR PAP or the like. Thus the client controls the operation of a target OA apparatus.

Further the client program receives a response and necessary data from the server program in accordance with the necessity. The client discriminates the contents of the response from the OA apparatus and transmits a new instruction request to the OA apparatus in accordance with them.

Such a server client system is installed in various network protocols such as TCP IP and the like and is used. However it is necessary to continue an interactive communication between the server and the client while a service is being provided.

On the other hand in the field of a distributive calculation purely comprising computers in recent years its technique has been developed from the technique such as a remote procedure call in which the distributive calculation is performed by repeating the interactive communication by a protocol to the technique called a mobile agent in which the executable program object itself moves on a network and executes the distributive calculation. Various techniques have been proposed.

As examples of realizing the distributive calculation system by the mobile agent various systems such as Telescript of General Magic Co. Ltd. of U.S. Pat. No. 5 603 031 and Aglets of IBM Tokyo Basic Laboratory have been well known.

The mobile agent comprises a command train and data necessary to execute them and is not limited to one certain execution environment but moves from a certain execution environment to another execution environment and is executed on a dedicated interpreter.

First in the client server system for the server process a client process frequently performs the request of a service and the transmission of the data necessary for processes of the service. While controlling a physical mechanism of the OA apparatus corresponding to the request the server process frequently performs a response to the client process and the return transmission of a processing result in accordance with the necessity. Moreover as the service to be requested becomes finer the interactive communication between the client process and the server process has to be repeated many times in accordance with it.

Importance has recently been made to a request such that the service which is provided by the OA apparatus is finely controlled from the client. However if it is intended to meet this request by the interactive communication of information by the conventional control protocol traffic of the network increases due to it. Therefore the user has to use an expensive network infrastructure of higher performance and it is economically disadvantageous.

Second if the interactive communication by the control protocol is continuously maintained between the client process and the server process the OA apparatus has to execute in parallel both of the control of the physical mechanism to provide the service and the interactive communication by the network communication. A burden on the OA apparatus due to it is large. In the case where the OA apparatus is a multiclient type apparatus which provides services to a plurality of clients particularly such a burden is large.

That is to maintain the connection of the communication via the network while controlling the physical mechanism which the apparatus has in order to provide the service a processor of higher performance is necessary as a processor of the apparatus. A memory of a larger capacity is also needed. This becomes a cause of an increase in costs of the apparatus main body.

Third according to the method of using the communication protocol in order to perform a series of interactive processes for controlling the OA apparatus a command system to control the apparatus has to be previously designed and installed as a command protocol. Therefore in the future when a new using method of the apparatus is expanded in order to realize such a new using method the command protocol also has to be expanded.

Thus both of the client process and the server process have to be changed version up of the program so as to correspond to the expanded command protocol. This results in a troublesomeness for the user and particularly since the program of the server process built in the conventional OA apparatus is generally called firmware and is stored in a non volatile memory or the like much costs are required to update the program or in many cases the updating of the program is exactly impossible. Therefore expandability of the service that is provided by the OA apparatus decreases.

Fourth the mobile agent proposed recently in the field of the distributive calculation is a method of a distributive programming on the computer. Therefore in the mere mobile agent proposed in the field of the distributive calculation it is impossible to perfectly satisfy the foregoing recent various requirements requested for the conventional OA apparatuses. Particularly the mobile agent in such a field intends to distributively perform the calculation to solve a certain problem and does not aim to control another computer from a remote location.

Although the above requirements can be satisfied to a certain extent by installing the mobile agent to the server computer to exclusively perform the control of the OA apparatus such as represented by the print server under an execution environment a network or a communication infrastructure in place of it is still necessary between the server computer and the OA apparatus.

Therefore there is still a problem of a traffic on the communication medium and a burden of an interface process on the OA apparatus side is also not reduced. Further if the communication between the OA apparatus and the server computer to exclusively perform the control of the OA apparatus is executed in accordance with the conventional interactive protocol expandability of the service that is provided by the OA apparatus itself also decreases in a manner similar to the third problem. Since the user has to newly prepare the dedicated server computer for the apparatus it is disadvantageous from an economical viewpoint and in consideration of the installing area.

To solve the above problems according to the invention the client can provide a desired image processing service while minimizing a connection time that is required to connect to the client and an interactive communication with the client. According to the invention excellent expandability of an image process can be obtained without being limited to firmware of an image processing apparatus.

To solve the above problems therefore according to the invention there is provided an image processing apparatus for receiving an agent including an operation train through a network and allowing an image processing unit to perform image processes comprising control means for controlling the image processing unit interpreting means for interpreting the operation train of the agent and message output means for outputting a message to the control means in response to the operation interpreted by the interpreting means.

Preferred embodiments of the present invention will be described in detail in accordance with the accompanying drawings.

Reference numeral denotes a local area network hereinafter referred to as an LAN constructed by the Ethernet or the like. The LAN enables a mutual communication between the apparatuses or between the client and the apparatus. Reference numeral denotes client information processing apparatuses such as a personal computer workstation word processor and the like. Generally the client information processing apparatus has input devices such as a keyboard mouse and the like which are used when the user inputs and output apparatuses such as a display and the like to output information to the user and is connected to the LAN .

Reference numeral denotes a router for connecting the LAN to another network and enabling a communication to be performed between apparatuses connected to those networks. In case of TCP IP the router usually provides a function to mutually transfer a data frame between the networks having different network addresses.

Reference numeral denotes a wide area network WAN such as an Internet or Intranet. The WAN mutually connects various LANs by an enterprise dedicated network to mutually connect a number of networks an Internet a virtual private network on the internet or the like.

Reference numeral denotes a second LAN that is mutually connected to the first LAN via the WAN a second router to connect the LAN and WAN and a remote client connected to the LAN . The remote client can be connected to the apparatus from a remote location via the WAN .

Reference numeral denotes a non volatile memory constructed by any one of an ROM a flash ROM an NVRAM an HDD and the like not shown or some of them to store the program which is executed by the processor initial values of the data regarding the execution of the program data necessary to be also saved even after the turn off of a power source and the like.

Reference numeral denotes an engine controller to control an image processing engine in the diagram a printer and an image scanner to perform image processes by hardware an image memory to store image data the printer to form an image corresponding to the image data onto a transfer paper the image scanner to read an image from an original and form image data and a processor bus to mutually connect the network I F processor work memory non volatile memory engine controller and image memory and execute the transmission and reception of data control information status of the engine and the like. Reference numeral denotes an image bus to mutually connect the engine controller image memory printer and image scanner and performs the transmission and reception of the image data.

In reference numeral denotes a document feeder to sequentially convey originals stacked on a copyboard original supporting base plate one by one onto the surface of a copyboard glass . When the original is conveyed a lamp of an image scanner unit is lit on and a scanner unit is moved and irradiates the original. Reflection light of the original passes through mirrors and and a lens and after that enters a CCD image sensor .

A signal inputted to a printer unit is converted to a photosignal by an exposure controller . The photosignal irradiates a photosensitive drum in accordance with an image signal. A latent image formed on the photosensitive drum by the irradiation light is developed to a toner image by a developer . The transfer paper is conveyed from a paper tray or in accordance with the development timing. In a transfer unit the developed image is transferred onto the transfer paper. After the transferred image was fixed onto the transfer paper by a fixing unit the transfer paper is ejected to the outside of the apparatus from a paper ejector . The transfer paper ejected from the paper ejector is conveyed to each bin in the case where a sorting function by a sorter operates and is conveyed to a top non sort bin of the sorter when the sorting function does not operate. The engine controller in is mounted onto a control section .

In each layer can use services which are provided by the lower layers. The lowest layer is an operating system and is a layer to perform a management of an execution context of the program a memory management and the like. Three device drivers of a network interface driver a printer control driver and an image scanner control driver are built in the operating system and mutually function in an interlocking relation manner.

The network interface driver controls the network I F . The printer control driver controls the printer via the engine controller and image memory . The image scanner control driver controls the image scanner via the engine controller and image memory .

The second lowest layer corresponds to various libraries. The various libraries are statistically or dynamically linked to an interpreter which will be explained hereinlater and the other application programs and mediate between the operating system and the application program. Among them a thread library provides a thread function to the programs of the upper layers. A terminology thread denotes a unit of parallel processes in the program. Although a plurality of threads in a single process program under execution have different execution contexts program counter stack register value etc. they commonly use a memory space or the like. The switching of the contexts of the threads is also called a light weight thread because an amount of processes to be executed is smaller than that in case of switching the contexts of the process.

A network interface library is a library to provide a transmitting and receiving function of data in the network by using the network interface driver . A printer control library is a library to provide a printer control API application programming interface by using the printer control driver. An image scanner control library is a library to provide an image scanner control API by using the image scanner control driver.

The third lowest layer is the interpreter . The interpreter provides an object execution environment for allowing the object such as a mobile agent to operate. The object in the embodiment is a subset of an object in a well known object oriented paradigm. That is the object is a program structure in which a command train and data regarding the execution of the command train are combined.

Each object autonomically exists and the objects operate in parallel while communicating message passing with the other objects. Thus a series of processes is accomplished as a whole. Specifically speaking the interpreter interprets a command train of a certain object A and generates a message command to the other object B in response to the command. When the message command is generated to the object B the interpreter interprets and executes a command train of the object B corresponding to the message command . The interpreter generates messages commands to various lower libraries in accordance with the interpretation of the command train of the object.

The interpreter can actually generate the message command as mentioned above or can merely interpret and execute the command train of the other object B corresponding to the command of the object A without actually generating the message. In the invention in any case an expression the operation which is provided by the other object B is accessed or message command is generated to the other operation B is used.

There is an object scheduler in the interpreter and it intermittently allocates a processing time of the processor to each object which operates on the interpreter . The object scheduler controls so that the processes of the objects are executed virtually in parallel by using the thread library .

An object decoder encoder exists in the interpreter . The command train scripts of the object stored in the memory in an executable form and the data are encoded by the object encoder in a form such that they can be substantially reconstructed to a bit train that can be transferred through the network.

The decoder decodes the bit train which can be transferred through the network and develops the object into the memory in an executable form. In the encoding and decoding steps data compressing and decompressing processes can be also included to reduce the traffic on the network. By including the data compressing and decompressing processes an amount of data which is transferred between the client and the image recording apparatus can be further reduced and it is useful to reduce the traffic on the network. Even when a band of the network is narrow as in the dial up connection by the modem or TA a sufficiently practical throughput can be obtained.

The interpreter described here is provided in not only the image processing apparatus but also the clients and . Structures and operations of those interpreters are substantially the same while also including the following description.

In the top layer corresponds to a plurality of objects which are executed on the interpreter. A printer control object provides an operation to control the printer via the printer control library and functions as an alternate object of the printer .

For instance when the operation which is provided by the printer control object in the command train of the object is accessed the printer control object performs a control corresponding to the relevant operation to the printer .

Specifically speaking the interpreter interprets a command train of a certain object and generates a message to the printer control object if the interpreted operation is an operation that is provided by the printer control object . In accordance with the message the interpreter interprets the command train of the printer control object and controls the printer via the printer control library or the like in response to the interpretation.

Similarly when the object accesses the operation which is provided by the printer control object and is used to obtain the information of the printer actual status information or the like of the printer can be obtained.

An image scanner control object provides an operation to control the image scanner via the image scanner control library and functions as an alternate object of the image scanner .

For example in the command train of the object when the operation of the image scanner control object is accessed the image scanner control object performs a control of the image scanner corresponding to the relevant operation. Similarly when the object accesses the operation which is provided by the image scanner control object and is used to obtain the information of the image scanner the actual status information or the like of the image scanner can be obtained.

The printer control object and image scanner object are called resident agents here. That is after the image processing apparatus was activated the interpreter first automatically forms initializes and activates the resident agents. The resident agents exist during the operation of the image processing apparatus there is an infinite loop in a live operation which will be explained hereinlater . The resident agents provide various operations to control the printer to the other objects thereby enabling the other objects to perform various image processes by combining those operations.

In reference numerals and denote objects to play roles as agents of a certain image process and are called OA mobile agents here. The OA mobile agent is an object having a nature such that it is moved between the client and OA apparatus connected to the network. In the command train the OA mobile agent accesses the operation hereinafter referred to as a go operation which denotes movement .

When the go operation is detected during the execution of the interpretation of the command train of the OA mobile agent the interpreters in the image processing apparatus and clients and in encode the data of the relevant object and the command train by using the object encoder. In this instance the interpreter transfers the network packet formed by encoding to an apparatus designated by an argument of the go operation for example to the interpreter of the image processing apparatus .

The interpreter of the image processing apparatus receives the transferred packet and decodes the packet by using the object decoder. Thus the command train of the object and the data are developed into the memory space that is managed by the interpreter and further the object becomes a target of scheduling of the object scheduler.

Data showing the location of a command to be executed subsequently to the relevant object is also included in the data of the object. Therefore in the object the command that is first executed by the interpreter on the transfer destination side is the command next to the command which was finally executed by the interpreter on the transfer source side.

The mobile agents and consequently execute the processes described by the command train while moving among the image processing apparatus having the execution environment interpreter of the object and the clients and or the like.

In the command train of the object which can be executed by the interpreter an operation defining processes necessary to initialize itself hereinafter such an operation is called an initialize operation exists. When the object is formed the interpreter first executes the initialize operation .

In the command trains of the mobile agents and or resident agents and there is an operation defining a series of processes which are executed while itself exists hereinafter such an operation is called a live operation . After the object was initialized the interpreter executes the live operation . When the execution of the command train defined in the live operation of the object is finished the interpreter extinguishes the object and releases a whole memory area used for the object.

To enable the OA mobile agent to dialogue with another agent the mobile agent has to get a reference to a partner agent prior to it. In this operation in the command train of the object a dialogue request operation hereinafter referred to as a meet operation that is provided by the interpreter is accessed. Identification information ID information to designate the object of the partner to enter an interactive operation is included in an argument of the meet operation .

The ID information to designate the object is information showing conditions to specify the object and includes for example a unique object identifier an identifier of a class to which the object belongs or the like.

When the meet operation is successfully completed the mobile agent can obtain the reference to the partner agent. By using it the operation of the partner agent can be executed. That is an interactive operation of the message can be performed.

For example in when the mobile agent or mobile agent moved from the other apparatus meets the printer control object or image scanner object as a resident agent the public operation can be accessed by accessing to the open data of the partner agent.

Therefore the mobile agent or formed in the client in moves to the image processing apparatus and can directly make a dialogue with the printer control object or image scanner control object of the image processing apparatus without using the network. Thus the OA mobile agent can execute a desired process namely an image reading by the scanner or an image recording by the image processing apparatus . The user can allow the image processing apparatus to execute various image processes by freely forming an OA mobile agent in the client . Particularly although the image processing function installed in the image processing apparatus is relatively fixed in the conventional technique according to the embodiment the image processing function installed in the image processing apparatus is expanded by forming the OA mobile agent.

The operation of the invention will now be described hereinbelow with reference to flowcharts of and subsequent diagrams. The image recording will be described as an example hereinbelow. However it will be obviously understood that the processes such as an image reading by the scanner and the like can be also executed by a similar control.

First is a flowchart showing a processing procedure of the OA mobile agent in the case where the image recording is performed by using the OA mobile agent according to the embodiment when a use frequency is low.

First in step S the OA mobile agent formed by the client opens a file which should be printed and was designated by the user from the local file system of the client and stores it as own data.

In subsequent step S the image processing apparatus is set to a destination and the OA mobile agent moves to the interpreter on the image processing apparatus by the go operation . In this instance the command train of the OA mobile agent and the data to be printed are encoded as shown in and transferred to the image processing apparatus. When the movement of the OA mobile agent is completed the interpreter on the client deletes the OA mobile agent object from an internal table and releases resources such as a memory space and the like used by the object.

In step S the OA mobile agent moved to the image processing apparatus is decoded by the interpreter of the image processing apparatus and the processes are started. The OA mobile agent requests the interpreter to make a dialogue with the printer control object which is resident in the image processing apparatus .

In step S an average use frequency getting operation that is provided by the printer control object is accessed thereby obtaining the latest average use frequency of the printer engine.

In step S a result of the latest average use frequency is compared with a predetermined use frequency thereby discriminating whether the latest use frequency is sufficiently low or not. For example if the obtained average use frequency of latest one hour is equal to a few times hour and a constant of a threshold value embedded in the command train is equal to 0.5 time hour this discrimination result is false and step S follows.

In step S the execution is paused for a waiting time for example 30 minutes embedded in the command train by sleep as a built in operation. After the elapse of the execution pause time the execution of the command train is restarted and the processing routine is returned to step S. The getting and discrimination of the latest average use frequency are re executed.

In the discrimination in step S for example if the average use frequency of latest one hour is equal to zero time and the constant of the threshold value embedded in the command train is equal to 0.5 time hour this discrimination result is true and step S follows.

In step S a print request operation of the printer control object is accessed by using the print data stored by the client stored as data of the mobile agent in step S as an argument. Thus the process by the print request operation of the printer control object is executed by the printer and the print data is printed. Although the print data has an arbitrary format for instance a PDL such as PostScript or LIPS is considered.

When the process in step S is completed the live operation is finished the interpreter deletes the mobile agent object from the internal table and releases the resources such as a memory space and the like used by the object.

As mentioned above by transmitting the print data and the OA mobile agent which substitutes its printing process to the image processing apparatus the client can print after that without directly performing an interactive operation to the image processing apparatus . Moreover according to the processes shown in a fine process which needs the discrimination based on the status of the image processing apparatus such that the print data of a low priority is automatically printed for a period of time during which the image processing apparatus is free is easily realized and the communication between the client and image processing apparatus is never necessary during this process.

Subsequently is a flowchart showing a processing procedure of the OA mobile agent in the case where the image recording is performed by using the OA mobile agent according to the embodiment when there are an enough amount of papers.

First in step S the OA mobile agent formed by the client opens a file which should be printed and was designated by the user from the local file system of the client and stores it as own data.

Subsequently in step S the image processing apparatus is set to a destination and the OA mobile agent moves to the interpreter on the image processing apparatus by the go operation . In this instance the command train of the OA mobile agent and the data to be printed are encoded as shown in and transferred to the image processing apparatus. When the movement of the OA mobile agent is completed the interpreter on the client deletes the OA mobile agent object from the internal table and releases the resources such as a memory space and the like used by the object.

In step S the OA mobile agent moved to the image processing apparatus is decoded by the interpreter of the image processing apparatus and the processes are started. The OA mobile agent requests the interpreter to perform an interactive operation to the printer control object which is resident in the image processing apparatus .

In step S a remaining amount of the print papers is calculated by using the operation that is provided by the printer control object. In step S a check is made to see if an amount of papers is sufficient to print. If there is an enough paper amount YES in step S a printing process is performed in step S.

If the amount of papers is insufficient to print NO in step S in step S the execution is paused for the waiting time for example 30 minutes embedded in the command train by sleep as a built in operation. After the elapse of the execution pause time the execution of the command train is restarted and the processing routine is returned to step S.

As shown in the processes of the client transmits the print data and the OA mobile agent which substitutes its process to the image processing apparatus so that the print data can be automatically printed after that without an interactive operation between the client and image processing apparatus by waiting until an enough amount of papers are supplemented to the printer.

In step S the current time is obtained from a timer circuit not shown in the image processing apparatus . In step S the OA mobile agent discriminates whether the print time designated by the command train has elapsed or not. If it elapses YES in step S the printing process is performed in step S. The print time is designated by the user by the printing operation from the client .

As shown in processes in the client transmits the print data and the mobile agent which substitutes its process to the image processing apparatus so that a large amount of print data for example can be automatically printed at midnight after that without an interactive operation between the client and image processing apparatus .

In step S a current temperature of the fixing unit is obtained. In step S whether the temperature of the fixing unit exceeds a temperature designated by the command train or not is discriminated. If the fixing temperature is sufficiently high YES in step S the printing process is performed.

If the fixing temperature is insufficient NO in step S in step S the execution is paused for the waiting time for example 30 minutes embedded in the command train by sleep as a built in operation. After the elapse of the execution pause time the processing routine is returned to step S to restart the execution of the command train.

As shown in the processes of the client transmits the print data and the OA mobile agent which substitutes its process to the image processing apparatus so that the print data can be automatically printed after that without an interactive operation between the client and image processing apparatus for example by waiting until a preparation of the apparatus is completed upon activation of the apparatus.

The invention can be applied to a system constructed by a plurality of equipment for example a host computer interface equipment a reader a printer etc. or can be also applied to an apparatus comprising one equipment for instance a copying machine a facsimile apparatus or the like .

As shown in it will be obviously understood that the object of the invention is accomplished by a method whereby a storage medium in which program codes of software to realize the functions of the embodiments mentioned above have been recorded is supplied to an OA apparatus and a computer or a CPU or an MPU of the OA apparatus reads out and executes the program codes stored in the storage medium.

As shown in the object of the invention can be also accomplished by a method whereby the program codes of the software to realize the functions of the embodiments mentioned above are supplied from a server computer to the OA apparatus via a network a public telephone line or a cable and the computer or a CPU or an MPU of the OA apparatus executes the supplied program codes.

In this case the program codes themselves read out from the storage medium realize the functions of the embodiments mentioned above and the storage medium in which the program codes have been stored and a server apparatus which transmitted the program codes construct the invention.

Although the embodiments have been shown with respect to an example in which the present program and associated data are directly loaded from the storage medium into the RAM and are executed it is also possible to use another method whereby the present program and associated data are once stored installed from an external storage medium such as an FD or the like to a hard disk as a non volatile storage medium in an external memory and when a control program for the data forming and transmitting processes is made operative they are loaded from the hard disk to the RAM.

As a storage medium to supply the program codes for instance any one of a floppy disk a hard disk an optical disk a magnetooptical disk a CD ROM a CD R a magnetic tape a non volatile memory card an ROM and the like can be used. It will be also obviously understood that the invention includes not only a case where the functions of the embodiments mentioned above are realized by executing the read out program codes by the computer but also a case where the OS operating system or the like which operates on the computer executes a part or all of the actual processes on the basis of instructions of the program codes and the functions of the embodiments mentioned above are realized by those processes.

Further the invention also incorporates a case where the program codes read out from the storage medium are written into a memory provided in a function expanding board inserted in a computer or a function expanding unit connected to the computer and after that a CPU or the like provided for the function expanding board or function expanding unit executes a part or all of the actual processes on the basis of instructions of the program codes and the functions of the embodiments mentioned above are realized by those processes.

As described above according to the embodiments the client transmits the print data and the mobile agent which substitutes its process to the image processing apparatus so that the fine processes which need the discrimination based on the status of the image processing apparatus can be easily performed after that without an interactive operation between the client and image processing apparatus .

As processes by the discrimination based on the status of the image processing apparatus the processes are performed when the use frequency of the image processing apparatus is low the processes are performed when an amount of papers is sufficient and the processes are performed when the designated print time comes and the processes are performed when the temperature of the fixing unit is higher than the designated temperature have been shown. However the control that can be executed by the OA mobile agent in the OA apparatus on the movement destination side is not limited to the foregoing control.

For example as another method upon execution of the OA mobile agent it is possible to take a dynamic countermeasure such that by referring to version information or the like of the interpreter of the image recording apparatus or the printer control object the printer engine is controlled by a different method in accordance with each version. That is desired various controls can be performed by the OA mobile agent and it shows high expandability of the printer function.

Although the image recording has been described above as an example the process such as an image reading by the scanner or the like can be also obviously executed by a similar control. In this case the OA mobile agent moved from the client allows the scanner control object to perform the image reading operation by the scanner by the meet operation and also enables the read out image data to be transmitted to the client by the go operation .

It is also obviously possible to allow the OA mobile agent to perform various converting processes for the image data for example arbitrary converting processes such as a zoom of an image halftone process conversion of an image file format and the like besides the recording and reading operations of the image.

Further in the embodiments while the OA mobile agent is performing the printing process by the image recording apparatus there is no need to continue the connection between the client and the image recording apparatus so that the traffic on the network can be reduced.

The interpreter can execute the recording process without depending on the operating system of the client and the image recording apparatus so long as there is a compatibility between the client and the image recording apparatus.

Moreover in the conventional technique although expandability is low because the command train itself to perform the printer control has fixedly been stored in the image recording apparatus an arbitrary command train can be executed by the OA mobile agent by using the operation or the like which is provided by the interpreter of the image recording apparatus and the resident object.

By referring to the version information or the like of the interpreter of the image recording apparatus and the printer control object it is possible to take a dynamic countermeasure such that the printer engine is controlled by the method corresponding to each version or the like.

According to the embodiments the remote client or the like in can also control the image processing apparatus through the network such as a wide area network or Internet.

Further even if the client and the image recording apparatus are intermittently connected the printing process can be sufficiently performed. Therefore even if the remote client is connected to the image recording apparatus by the dial up type network connection the control of the image processing apparatus can be sufficiently and easily performed.

According to the invention as described above a desired image processing service can be sufficiently and easily executed while minimizing the connection time between the client and the OA apparatus and the interactive communication between the client and the OA apparatus. Further by transmitting the command train to control the OA apparatus from the client there are effects such that a flexible control more than that in the conventional system can be performed and the expandability of the OA apparatus increases.

The present invention is not limited to the above embodiments and various changes and modifications can be made within the spirit and scope of the present invention. Therefore to appraise the public of the scope of the present invention the following claims are made.

