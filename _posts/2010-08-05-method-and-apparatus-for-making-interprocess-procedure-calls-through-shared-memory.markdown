---

title: Method and apparatus for making inter-process procedure calls through shared memory
abstract: One embodiment of the present invention provides a system that facilitates making an inter-process procedure call through a shared memory that is shared between a client process and a server process, wherein the client makes the inter-process procedure call as if the client is making a local procedure call, but the procedure call actually executes on the server. The system operates by an Application Programming Interface (API) to allow the client to make an inter-process procedure call. The system then allocates a section of the shared memory for the data structure parameters of the inter-process procedure call.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08191076&OS=08191076&RS=08191076
owner: Oracle International Corporation
number: 08191076
owner_city: Redwood Shores
owner_country: US
publication_date: 20100805
---
This application is a continuation application of application Ser. No. 11 259 240 now U.S. Pat. No. 7 779 417 entitled METHOD AND APPARATUS FOR MAKING INTER PROCESS PROCEDURE CALLS THROUGH SHARED MEMORY by inventors Mohammad Shoaib Lari and Srinath Krishnaswamy filed 25 Oct. 2005.

The present invention relates to enterprise computer applications. More specifically the present invention relates to a method and an apparatus for making inter process procedure calls through shared memory.

Organizations typically arrange enterprise applications into multiple tiers to facilitate scalability increased performance and security. Traditionally each tier is physically located on a different server or cluster of servers. For example it is common to host the web server user interface tier on one server the business logic on a second server and the database server on a third server. In the example illustrated in browsers are coupled to application via network . Application runs on a server and is coupled to database server which runs on a different server than application . As illustrated in when application wants to execute a procedure call on database server it does so by making a remote procedure call via Oracle Call Interface OCI .

However the multiple tier architecture gives rise to new problems. Network bandwidth is relatively expensive and increased usage of the enterprise application results in increased network bandwidth consumption. Performance can also suffer because it takes time for the tiers to communicate with each other.

In some instances to increase performance the various tiers can be placed on the same server. However for security reasons the different tiers still run in separate processes on the server. In order for one process to communicate with another process elaborate protocols are needed because no generalized mechanism exists for inter process procedure calls.

Hence what is needed is a method and an apparatus for making inter process procedure calls without the limitations listed above.

One embodiment of the present invention provides a system that facilitates making an inter process procedure call through a shared memory that is shared between a client process and a server process wherein the client makes the inter process procedure call as if the client is making a local procedure call but the procedure call actually executes on the server. The system operates by receiving a request from the client through an Application Programming Interface API to make an inter process procedure call. The system then allocates a section of the shared memory for the data structure parameters of the inter process procedure call. Additionally the client process acquires a lock on a commonly known section of shared memory called a Parameter Control Block. Once the lock is acquired the client process stores parameters for the inter process procedure call in the Parameter Control Block. Finally the client process clears a Call Done flag and releases the lock.

In a variation on this embodiment the server process acquires the lock. Once the lock is acquired the server process processes the inter process procedure call using the parameters from the Parameter Control Block and data structure parameters in the shared memory. The server process then stores results of the inter process procedure call in the shared memory. In addition the server process sets a Call Done flag to indicate that the server process has completed processing the inter process procedure call. Finally the server process releases the lock.

In a variation on this embodiment the client process acquires the lock. Upon acquiring the lock the client process determines if the Call Done flag is set. If so the client process processes the results of the inter process procedure call from the section of shared memory at the client.

In a further variation the request to make an inter process procedure call is made by a thread executing on the client wherein the client is operating in a multi threaded environment.

In another variation the results of the inter process procedure call are consumed by a different client thread than the one that issued the call.

In a further variation the server process can service calls from multiple client processes by waiting on locks on more than one parameter control blocks.

In another variation the server process can have multiple threads each serving one or more client processes.

In a variation on this embodiment the client is an enterprise application running on a middle tier in a multi tier application environment.

In a further variation the inter process procedure call is triggered by a request from a browser coupled to the enterprise application.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not intended to be limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs and DVDs digital versatile discs or digital video discs and computer instruction signals embodied in a transmission medium with or without a carrier wave upon which the signals are modulated . For example the transmission medium may include a communications network such as the Internet.

In the embodiment illustrated in application and database server are separate operating system processes running on the same server. Application and database server both have access to shared memory . Application includes Oracle Call Interface OCI client stub . Likewise database server includes OCI server stub . In the embodiment of the present invention illustrated in OCI client stub and OCI server stub allow application to make inter process procedure calls on database server via shared memory as if application was making a local procedure call. These inter process procedure calls are accomplished by OCI client stub and OCI server stub via an Application Programming Interface API . This is described in more detail below in .

Parameter control block is a data structure in shared memory for keeping track of an inter process procedure call. Parameter control block comprises a lock a Call Done flag to indicate the processing status of the inter process procedure call a count of the number of arguments for the inter process procedure call an array of Parameter Descriptors and an array of arguments for the inter process procedure call. Note that in the parameter control block illustrated in the lock is a semaphore. The present invention is not meant to be limited to the use of semaphores and any type of locking mechanism may be used.

In one embodiment of the present invention the operation to be performed by the inter process call is indicated by an Operation Code OPCODE in the parameter control block. This is a mutually agreed operation code for the procedure call to be performed. In this embodiment the number parameter n is still passed in the parameter control block. Corresponding to the number of parameters there are n parameter descriptors and parameters. A parameter descriptor describes the data type of the argument parameter of the call such as integer floating point text string or pointer to a data structure parameter allocated in the shared memory. The parameters to the call are either arguments for the call or they are pointers to data structures in the shared memory.

In one embodiment of the invention the process of setting up of parameter control block can be automated by a translator that will generate parameter control blocks based on the prototype function declaration of the local procedure calls.

Note that the checking of the Call Done flag by the server process step after acquiring the lock is to prevent the race condition where the server process re acquires the lock before the client process had the time to process the results of the inter process procedure call. That is after acquiring the lock step if the server process finds that the Call Done flag is still set step then the server process releases the lock step and tries to re acquire the lock again step . An optional delay can be introduced between the time the server releases the lock step and re acquires the lock step to give the client process time to acquire the lock step .

Once the client process acquires the lock at OCI client stub with the Call Done flag set the system then processes the results of the inter process procedure call from shared memory step .

The client process normally holds on to the lock as the client process is either preparing parameters for the call or processing the results of the call. Only during the time the server process is executing the inter process procedure call the server process has the possession of the lock. Therefore the client process does not release the lock after the completion of the call. Arguments for a new inter process procedure call can be set by the client process in the parameter call and lock is only released when the client process is ready to issue the next call as described in .

The foregoing descriptions of embodiments of the present invention have been presented for purposes of illustration and description only. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

