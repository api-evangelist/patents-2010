---

title: System and method for managing the interleaved execution of threads
abstract: The computer system further includes means for classifying threads to be executed according to several predetermined types, and the handler for distributing the execution of threads directs each thread to be executed to a virtual processor according to the type thereof.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09436510&OS=09436510&RS=09436510
owner: BULL SAS
number: 09436510
owner_city: Les Clayes-Sous-Bois
owner_country: FR
publication_date: 20100915
---
The present invention relates to a computer system for managing the execution of threads comprising at least one central processing unit having interleaved execution of a plurality of threads throughout a plurality of virtual processors from said same central processing unit and a handler for distributing the execution of the threads throughout the virtual processors. It also relates to a corresponding method to an application of this method to a cluster of servers and to a computer program comprising instructions for the execution of this method.

In the following description computer system is understood as being any system capable of executing the instructions of a computer program and for this purpose having at least one processor including at least one central processing unit said central processing unit being further called calculation core of the processor or CPU. It will be noted that a processor may have only one calculation core or a plurality of calculation cores. In an increasing order of complexity a computer system according to the invention can be composed of a microprocessor with one or more calculation cores a single microcomputer having one or more microprocessors or a more complex arrangement in which a plurality of microcomputers are interconnected via a data transmission network. The complexity of a computer system in which the invention can be implemented depends primarily on the application to be carried out.

 Computer process more generally referred to as process is understood as a set of instructions to be executed by a central processing unit i.e. a calculation core of a processor in a specifically allocated memory space with the possible aid of other resources. Because a computer program itself is composed of a structured set of instructions a computer process can then be considered as an instance of a computer program to be executed or as a portion of said computer program. Since the same program can be executed multiple times in parallel successively on the same processor or on different processors it can therefore generate a plurality of computer processes.

A computer process is not necessarily composed of a single linear sequence of instructions but can call several of them asynchronously. Thread is then understood as such a linear sequence of instructions participating in the execution of a computer process. From the point of view of the execution of instructions a computer process can therefore always be considered as being a thread or a set of threads.

 Central processing unit having interleaved execution of a plurality of threads throughout a plurality of virtual processors from said same central processing unit is understood as being a central processing unit having a mechanism for increasing the parallel execution of threads by sharing some of its internal resources particularly its execution pipeline its registers and its cache memories. Such a central processing unit therefore has as many virtual processors as threads that can simultaneously share its resources. From the user s point of view everything takes place as though instead of only one central processing unit there were several more specifically as many as its number of virtual processors.

This mechanism is generally referred to as hyper threading or simultaneous multi threading. One objective of central processing units implementing this mechanism is to take advantage of periods of inactivity created by waiting for data from the shared memory space of a thread. Specifically when a thread is in a waiting situation the central processing unit that executes it goes automatically to executing another thread thus giving the impression of having several different virtual processors.

The Linux registered trademark operating system currently supports such a mechanism and therefore presents the user when it is executed on a microprocessor having a hyper threading mechanism with the N virtual processors from this microprocessor when this mechanism is activated. It also advantageously implements a load balancing algorithm during the execution of threads which must therefore take into account the specificities of the virtual processors in particular a virtual processor should not be unloaded by switching the threads to another virtual processor of a same central processing unit. This limitation particularly burdens the load balancing algorithm.

Specifically this limitation is particularly problematic in applications of real time calculation or embedded processing for example for microprocessors involved in mobile telephone applications.

According to a second specific example in a supercomputer environment of the HPC type High Performance Computing involving a plurality of processing nodes organized in clusters of servers the user wishes to have even finer control of the placement of his applications on the central processing units for example in order to take advantage of shared caches that favor one communication mechanism or another.

There are thus possibilities of fine placement of the threads via system calls of application programming interface for managing these threads allowing a user i.e. the programmer to specify the behavior of a task scheduler of the operating system with respect to a thread but for the application concerned this involves having the knowledge of the topology of the computer system and carrying out a placement that can sometimes conflict with other software layers.

Indeed taking into account the specificities of the virtual processors appears to be complex and becomes truly problematic and even automatically unmanageable in an HPC supercomputer application.

It is therefore desirable to provide a system for managing the interleaved execution of threads that makes it possible to overcome at least partially the above mentioned problems and limitations.

An object of the invention is therefore a computer system for managing the execution of threads comprising at least one central processing unit having interleaved execution of a plurality of threads throughout a plurality of virtual processors from said same central processing unit and a handler for distributing the execution of the threads throughout the virtual processors characterized in that it comprises means for classifying the threads to be executed according to a plurality of predetermined types and in that the handler for distributing the execution of the threads is designed for directing each thread to be executed to a virtual processor according to the type thereof.

Thus by classifying the threads by types and systematically directing them to one virtual processor or another in accordance with their type by means of the handler for distributing the execution of the threads the computing resources are preserved. The result is a better utilization of the central processing unit and an acceleration of the execution of the application concerned. Moreover the risks of errors that could be caused by a user the programmer due to the hyper threading mechanism are limited.

Optionally a computer system according to the invention can further comprise means for associating each virtual processor from said same central processing unit with one of said predetermined types and the handler for distributing the execution of the threads can be designed to direct each thread to be executed to a virtual processor whose type is identical to the type thereof.

Thus the handler for distributing threads is only concerned with selecting if applicable a central processing unit for a thread the specific choice of a virtual processor then being automatically guided by the type of thread. The result is that the hyper threading mechanism can be hidden to the user. There is therefore no longer any risk that the user could cause errors due to inadequate understanding of this mechanism. Furthermore performance is increased because the threads are automatically directed to the proper virtual processors.

Also optionally the central processing unit comprises two virtual processors one associated with a first type of threads the other associated with a second type of threads and each computer process to be executed is either of the first type or of the second type.

the first type of threads referred to as calculation relates for a program intended to be executed by the computer system so as to provide a result to threads participating to the execution of this program for the direct production of the result and

the second type of process referred to as service relates to threads participating to the execution of this program to provide annex services to threads of the calculation type.

Also optionally a computer system according to the invention can comprise at least two central processing units each for the interleaved execution of a plurality of threads throughout a plurality of virtual processors from said same central processing unit and the handler for distributing the execution of threads can be designed to select one central processing unit for each thread to be executed regardless of the virtual processors it has.

An object of the invention is also a method for managing the interleaved execution of a plurality of threads throughout a plurality of virtual processors from a same central processing unit of a computer system comprising a step of distributing the execution of the threads throughout the virtual processors characterized in that it comprises a preliminary step of classifying the threads to be executed according to a plurality of predetermined types and in that during the step of distributing the execution of the threads each thread to be executed is directed to a virtual processor according to the type thereof.

Optionally during the classification step each thread is classified into a type based on a parameter identifying this type in a function of an application programming interface for managing the thread.

Also optionally during the classification step each thread is classified into a type based on a parameter identifying this type in a command for executing a program involving the execution of said thread.

An object of the invention is also the application of a method as defined above to the management of the execution of a plurality of threads over a plurality of processing nodes of a cluster of servers of the supercomputer type wherein each processing node comprises at least one central processing unit having interleaved execution of a plurality of threads throughout a plurality of virtual processors from said same central processing unit.

Finally an object of the invention is a computer program that can be downloaded from a communication network and or recorded on a medium readable by computer and or executable by a processor particularly the operating system of a computer characterized in that it comprises program code instructions for the execution of the steps of a method for managing the interleaved execution of a plurality of threads as defined above when said program is executed on a computer.

Irrespective of any application the invention one embodiment of which will now be explained in detail can be implemented in any computer system having at least one central processing unit for the interleaved execution of a plurality of threads throughout a plurality of virtual processors from said same central processing unit and a handler for distributing the execution of the threads throughout the virtual processors.

In the simplest case the invention can thus be implemented with a microprocessor integrating a hyper threading mechanism. Real time calculation and or embedded applications can thus benefit from it.

In more complex applications of networked computer devices or HPC supercomputers each device comprising at least one microprocessor can advantageously implement the invention.

In the embodiment represented in this is an HPC computer application which will be explained in detail to show an embodiment of the invention. It is an industrial application particularly important for the invention. But it is clear from the foregoing that the invention is not limited to such an HPC computer arrangement.

The arrangement of computing devices shown in is for example a very simplified and incomplete representation of an HPC computer organized as a cluster of servers interconnected by means of at least one very wide band data transmission network . This arrangement comprises for example computing devices forming calculation nodes identified by references and and computing devices forming nodes for service administration or storage not shown . The general structure of the calculation nodes and can be the same but only the structure of the computing device will be detailed below.

a communication bus to which are connected a first central processing unit and a second central processing unit for the execution of computer processes from computer programs and more particularly threads 

a read only memory ROM and a random access memory RAM for storing processing data and or startup programs an application of the BIOS type for example and programs for management of peripherals and

Said computing device possibly further comprises in a conventional way not shown in this figure one or more of the following items a screen a keyboard a mouse a communication interface with the network and a device for reading recording data on a removable medium for example a CD ROM or DVD read write device.

The hard disk stores in the form of files an operating system such as the Linux system loaded by the BIOS application when the computing device is started. A mechanism for the interleaved execution of threads throughout a plurality of virtual processors of a same central processing unit is activated by this operating system. For example this mechanism is such that the central processing units and each have two virtual processors the virtual processors C and S for the first central processing unit and the virtual processors C and S for the second central processing unit .

Alternatively the operating system can be stored on external storage means on an external medium such as a hard disk on the network etc. . In this alternative the reader recorder and the communication interface of the computing device are capable of transferring data from an external medium to the hard disk to allow the loading of the operating system .

In every case the operating system is a computer program that can be downloaded from a communication network and or recorded on a medium readable by computer and or executable by a processor comprising program code instructions for the execution of the steps of a process for managing the interleaved execution of a plurality of threads that will be described with reference to .

More generally the above mentioned structure is suitable for any type of network of computing devices not necessarily of the HPC type in which the operating system of each computing device uses a mechanism for the interleaved execution of threads on virtual processors.

Finally it will be noted that the computer as it has just been structurally described is only one non limiting example of a device capable of implementing the invention. There is a great diversity of architectures in computer design and any device having at least one central processing unit for the interleaved execution of a plurality of threads throughout a plurality of virtual processors from said same central processing unit is suitable.

According to one embodiment of the invention the computing device comprises means for classifying threads to be executed according to a plurality of predetermined types and in particular according to two types of threads 

a first type of threads referred to as calculation for a program intended to be executed by the computing device so as to produce a result relates to threads participating in the execution of this program for the direct production of the result and a second type of threads referred to as service relates to threads participating in the execution of said program to offer annex services to the calculation type threads.

The service threads concern for example the saving of results memory management input output management data communication monitoring access to files etc.

In a first application a program to be executed requests the execution of several threads some of which participate in calculation and others in the annex services. In this case this program is designed to call an application programming interface function for managing threads for example the sched setscheduler function of the POSIX application programming interface based on a parameter identifying the calculation type HT CALCUL or the service type HT SERVICE . The means for classifying threads implemented by the operating system therefore consists of automatically recognizing this parameter in order to identify the type of a thread to be directed to a virtual processor.

In a second application several programs are to be executed some of them being calculation programs and others service programs. In this case the user provides for launching the execution of a program by means of a command in which the type calculation or service is identified by parameter for example the command can take the form of ht sched CALCUL or SERVICE . The means for classifying threads implemented by the operating system then consist of automatically recognizing this parameter in order to identify the type of a thread requested by a program.

In a third application an MPI message passing interface library currently used in parallel calculation programs creates a thread intended for services within the framework of a main program launched in calculation mode see second application . In this case it can call the setscheduler function based on a parameter identifying the service type HT SERVICE . The means for classifying threads implemented by the operating system then consist of automatically recognizing this parameter in order to identify the type of the thread created by this MPI library.

In a fourth application where the type of threads is not first specified as indicated previously the classification means of the operating system can be designed to determine it automatically even in summary form particularly by automatic recognition of applications producing these threads.

Moreover the computing device comprises means for associating each virtual processor of a same central processing unit with one of the two above mentioned types as shown in these association means are for example parameters C and S respectively identifying the calculation type or the service type. They are for example managed by the concerned central processing unit or alternatively by the operating system either explicitly or implicitly. Thus in the example shown schematically in the virtual processor C of the first central processing unit is of the calculation type the virtual processor S of the first central processing unit is of the service type the virtual processor C of the second central processing unit is of the calculation type and the virtual processor S of the second central processing unit is of the service type.

The operating system includes a handler for distributing the execution of threads throughout the virtual processors C S C and S. More specifically said distribution handler is designed to direct each thread to be executed to one of the virtual processors in accordance with its type and still more specifically to a virtual processor whose type is identical to the thread s type. Therefore a thread of the calculation type can only be directed to the virtual processor C or C and a thread of the service type can only be directed to the virtual processor S or S.

first software means for selecting a central processing unit or for each thread to be executed regardless of the virtual processors C S or C S it has and

second software means for automatically assigning from among the virtual processors of the selected central processing unit the one that is of the same type as the thread to be executed.

A method for managing the interleaved execution of a plurality of computer processes implemented by the computer of will now be explained in detail with reference to .

During a first classification step threads T T and T awaiting execution are classified according to whether they are of the calculation type right hatching or of the service type left hatching . This type can be defined a priori in control parameters or application programming interface functions and automatically recognized by the software means of the operating system as was explained in detail previously. The type can also be defined directly and automatically by the software means of the operating system .

During the next step the distribution handler of the operating system selects by software means a central processing unit or for each thread and places this thread in a queue of the selected central processing unit.

Next during a step of assigning each thread to a virtual processor performed by software means each thread placed in the queue of a central processing unit or is automatically placed in a queue of the virtual processor of said central processing unit or which is of the same type as said thread.

Finally during an execution step each thread is executed by the virtual processor that was assigned to it in the preceding step.

It is clear that a computing device like the one described above makes it possible to facilitate the management of execution of threads through a plurality of virtual processors.

In the prior art the operating system loaded onto a computer capable of implementing a mechanism of interleaved execution of threads on virtual processors has all of the virtual processors as generic calculation media and makes the distribution of the threads more complex.

According to the invention the distribution of threads by the operating system is simplified and more benefit is derived from the mechanism of interleaved execution of threads particularly in an environment of heavy calculation demands such as a HPC supercomputer or a processor implementing a calculation application in real time. More specifically in the embodiment described above two virtual processors of the same central processing unit are presented not as two interchangeable calculation media but as one main execution medium for the calculations and a secondary execution medium for the annex services. Thus a generalized computing device with N central processing units even if it implements the mechanism of interleaved execution of threads actually only presents to the user and to the operating system N central processing units as if it were not implementing this mechanism. Consequently benefit is derived from this mechanism without having to undergo management constraints thereof in the distribution of the threads.

The automatic assignment of threads to the virtual processor of the selected central processing unit makes it possible to distribute them throughout virtual processors based on their role and their constraints and the user or operating system does not have to be involved in this distribution.

Once the threads are distributed it is clear that the advantage of implementing the parallel execution mechanism on two virtual processors of the same central processing unit is based on the following points 

The central processing unit manages two different queues and therefore has no need to manage the changeover of one thread to another this simultaneous execution being managed by the hardware 

In particular when there is only one thread left to execute per virtual processor the central processing unit can allow the virtual processors to execute the code without interrupting them 

This very fine granularity can prove beneficial especially in the case of daemons that can cause disturbances. Indeed the calculation virtual processor of a same central processing unit will be slowed down but not blocked during a constant time by the service virtual processor. The effect of disturbances daemons and interruptions is then greatly reduced in favor of the calculation virtual processor.

In an HPC environment the calculation code can therefore be positioned on the calculation virtual processor and the annex services on the service virtual processor and this can be done in a transparent manner for operating tools such as batch managers. In a real time environment this makes it possible to isolate automatically a critical thread from all other service threads guaranteeing it at least 50 of the available execution time on the selected central processing unit and with no interruption due to scheduling.

Finally for compatibility of the computing device with programs that do not accommodate this functionality of assigning a priori a type to each thread it seems clear that by default the threads must be directed to a service virtual processor. Indeed all of the daemons launched by the operating system must be executed on a service virtual processor in order not to disturb the calculation. Only the calculation code must therefore be specifically adapted to direct its threads to a calculation virtual processor. This adaptation is not necessarily done from the program itself but can be performed in external tools such as the above mentioned MPI libraries for example.

Furthermore it will be noted that the invention is not limited to the embodiment described above. In particular if each central processing unit is capable of implementing a mechanism allowing it to present more than two virtual processors it can be of advantage to define more than two types of threads.

It will also be noted as was suggested several times previously that the HPC supercomputer arrangement shown in is not the only one in which the invention can be implemented. In a much simpler configuration for example real time and or embedded processing the invention can be implemented as soon as there is a single processor or a computer having such a processor comprising at least one central processing unit for the interleaved execution of a plurality of threads throughout a plurality of virtual processors.

More generally it will be clear to a person skilled in the art that various modifications can be made to the embodiment described above in the light of the teaching that has just been disclosed. In the following claims the terms used must not be interpreted as limiting the claims to the embodiment set forth in the present description but must be interpreted to include all of the equivalents that the claims seek to cover by their formulation the provision of which enables the person skilled in the art by applying his general knowledge to implement the teaching that has just been disclosed.

