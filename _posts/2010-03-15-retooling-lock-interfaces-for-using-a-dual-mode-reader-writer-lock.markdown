---

title: Retooling lock interfaces for using a dual mode reader writer lock
abstract: A method, system, and computer usable program product for retooling lock interfaces for using a dual mode reader writer lock. An invocation of a method is received using an interface. The method is configured to operate on a lock associated with a resource in a data processing system. A determination is made whether the lock is an upgraded lock. The upgraded lock is the DML operating in an upgraded mode. An operation corresponding to the method is executed on the DML, if the lock is the upgraded lock.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08943502&OS=08943502&RS=08943502
owner: International Business Machines Corporation
number: 08943502
owner_city: Armonk
owner_country: US
publication_date: 20100315
---
The present invention is related to similar subject matter of co pending and commonly assigned U.S. patent application Ser. No. 12 723 717 entitled DUAL MODE READER WRITER LOCK filed on Mar. 15 2010 and U.S. patent application Ser. No. 12 723 714 entitled USING A DUAL MODE READER WRITER LOCK filed on Mar. 15 2010 which are hereby incorporated by reference.

The present invention relates generally to an improved data processing system and in particular to a computer implemented method for improving the reading and writing of data. Still more particularly the present invention relates to a computer implemented method system and computer usable program code for using a dual mode reader writer lock DML .

Processes executing in a data processing system read and write data associated with a variety of resources. A data file a memory location and an address on a disk are some examples of such a resource.

When a process executing in a data processing system has to read or write data from or to a resource the operating system has to sequence and control the read write requests. This control is important in ensuring that read and write requests for the same resource by multiple processes do not compromise the integrity of the data of that resource. For example a process should not be allowed to read data while another process is writing that data. Multiple processes may be allowed to read the same data simultaneously but not in conjunction with one or more processes attempting to write that data.

To implement these and other rules for reading and writing data operating systems implement locks. A read write lock is a data structure whose data has to be set or reset or incremented or decremented before a process can read or write the data of an associated resource. Such a lock is also known as a reader writer lock RWL or a complex lock.

Setting or incrementing a RWL is called acquiring or getting a lock. Resetting or decrementing a RWL is called releasing or freeing a lock. A reader lock or a read lock is a state of a RWL that permits a process or thread to read the resource associated with the RWL. Multiple processes or threads can concurrently acquire a read lock on a common resource. A writer lock or a write lock is a state of a RWL that permits a thread to write data to the resource associated with the RWL. Only a single thread can acquire a single write lock on the resource at any given time and no thread can hold or acquire a read lock while another thread holds a write lock on the resource.

Typically a RWL is implemented using a single data word. A data word is a specific number of bits that are handled together in the architecture of an operating system. In one case the size of a data word may be the number of bits that can be held in a single register in a particular processor of the data processing system. In another case the data word size may be the minimum number of bits can be transferred from a given memory to a given processor. Commonly available operating systems have implemented data word sizes of sixteen thirty two sixty four and one hundred and twenty eight bits. A data word may be of any size suitable for a particular implementation.

When an operating system manipulates a RWL that manipulation must not be interrupted for the integrity of the lock. In other words all the instructions for setting or resetting or incrementing or decrementing a RWL must be executed from start to finish without being interrupted or preempted by another process. An operation whose set of instructions must be executed in this manner is called an atomic operation. Manipulation of a RWL is an atomic operation. Acquiring a lock and releasing a lock are examples of lock manipulations performed as atomic operations.

At any given time during the operation of a data processing system several processes or threads may wish to acquire a lock for a common resource in close temporal proximity of one another. Several other processes or threads that have already acquired the lock may wish to release the lock at or near the same time. Some processes or threads wishing to acquire or release the lock may deal with read locks on the resource while others may deal with write locks.

The illustrative embodiments provide a method system and computer usable program product for retooling lock interfaces for using a dual mode reader writer lock DML . An embodiment receives an invocation of a method using an interface. The method is configured to operate on a lock associated with a resource in a data processing system. The embodiment determines whether the lock is an upgraded lock. The upgraded lock is the DML operating in an upgraded mode. The embodiment executes an operation on the DML corresponding to the method if the lock is the upgraded lock.

Under certain circumstances several atomic operations for each request to acquire or release a lock from several processes or threads may be pending in a data processing system. The invention recognizes that inundating the data processing system with several atomic operations for a RWL can adversely affect the performance of the data processing system.

For the clarity of the description process is used to mean a process or a thread of a process. An operation with respect to a process is similarly applicable to a thread and an operation with respect to a thread is similarly applicable to a process within the scope of the invention.

The invention further recognizes that under certain other circumstances the data structure of the lock may be saturated and may not be able to accommodate any more lock requests. For example a data word of hypothetical size of two bits will be saturated if four threads are already holding read locks on the associated resource because two bits can be used to count only from 0 to 4. A fifth thread requesting a read lock cannot be accommodated until one of the other four processes holding a read lock releases its read lock. The invention recognizes that a backlog of atomic operations waiting to execute on a RWL in a data processing system can also adversely affect the performance of the data processing system.

These circumstances are example scenarios where contention for RWLs arises in a data processing system. The invention recognizes that a contention for RWL is likely in a data processing system when the number of processes or threads contending for a RWL increase beyond a threshold number. The invention further recognizes that as the number of processors in a data processing system increase such as in a multiprocessor data processing system or logical partition the number of processes and threads also rises leading to the RWL contentions.

The illustrative embodiments used to describe the invention generally address and solve the above described problems and other problems related to RWLs. The illustrative embodiments provide a method computer usable program product and data processing system for retooling lock interfaces for using a dual mode reader writer lock.

An embodiment of the invention may enable the data processing system to process atomic operations for a RWL with a reduced affect on the system performance as compared to the presently configured data processing system when the number of atomic operations reaches a threshold number. For example for the same number of atomic operations performed for a single RWL a data processing system implementing an embodiment of the invention may demonstrate better system performance as compared to a data processing system without the embodiment.

An embodiment of the invention may also allow more processes and threads to acquire and release locks concurrently with a diminished adverse affect on the system performance as compared to a presently configured data processing system. For example for the same system performance a data processing system employing an embodiment of the invention may allow more processes to acquire read locks on a resource as compared to a data processing system without the embodiment.

The illustrative embodiments are described with respect to data data structures indicators and identifiers only as examples. Such descriptions are not intended to be limiting on the invention. For example an illustrative embodiment described with respect to 64 bit data word may be implemented using a 128 bit data word in a similar manner within the scope of the invention.

Furthermore the illustrative embodiments may be implemented with respect to any type of data processing system. For example an illustrative embodiment described with respect to a multiprocessor standalone data processing system may be implemented in a multiprocessor logical partition system within the scope of the invention.

The illustrative embodiments are further described with respect to certain parameters attributes and configurations only as examples. Such descriptions are not intended to be limiting on the invention. An embodiment of the invention may be implemented with respect to any type of data processing system such as for example any type of client system server system platform or a combination thereof.

An application implementing an embodiment may take the form of data objects code objects encapsulated instructions application fragments services and other types of software implementations available in a data processing environment. For example Java Virtual Machine JVM Java object an Enterprise Java Bean EJB a servlet or an applet may be manifestations of an application with respect to which within which or using which the invention may be implemented. Java JVM EJB and other Java related terminologies are registered trademarks of Sun Microsystems Inc. in the United States and other countries. 

An illustrative embodiment may be implemented in hardware software or a combination thereof. The examples in this disclosure are used only for the clarity of the description and are not limiting on the illustrative embodiments. Additional or different information data operations actions tasks activities and manipulations will be conceivable from this disclosure for similar purpose and the same are contemplated within the scope of the illustrative embodiments.

The illustrative embodiments are described using specific code data structures file systems designs architectures layouts schematics and tools only as examples and are not limiting on the illustrative embodiments. Furthermore the illustrative embodiments are described in some instances using particular data processing environments only as an example for the clarity of the description. The illustrative embodiments may be used in conjunction with other comparable or similarly purposed structures systems applications or architectures.

Any advantages listed herein are only examples and are not intended to be limiting on the illustrative embodiments. Additional or different advantages may be realized by specific illustrative embodiments. Furthermore a particular illustrative embodiment may have some all or none of the advantages listed above.

With reference to the figures and in particular with reference to these figures are example diagrams of data processing environments in which illustrative embodiments may be implemented. are only examples and are not intended to assert or imply any limitation with regard to the environments in which different embodiments may be implemented. A particular implementation may make many modifications to the depicted environments based on the following description.

In addition clients and couple to network . A data processing system such as server or or client or may contain data and may have software applications or software tools executing thereon.

Server may include multiple processors . Other depicted data processing systems may also include more than one processor in a similar manner not shown . Server may further include DML . DML may be a DML according to an embodiment of the invention. DML may be implemented in server in conjunction with other RWLs without limitation. Furthermore DML may be configured in a data processing system other than server such as in server and may be accessible to server over network .

Servers and storage unit and clients and may couple to network using wired connections wireless communication protocols or other suitable data connectivity. Clients and may be for example personal computers or network computers.

In the depicted example server may provide data such as boot files operating system images and applications to clients and . Clients and may be clients to server in this example. Clients or some combination thereof may include their own data boot files operating system images and applications. Data processing environment may include additional servers clients and other devices that are not shown.

In the depicted example data processing environment may be the Internet. Network may represent a collection of networks and gateways that use the Transmission Control Protocol Internet Protocol TCP IP and other protocols to communicate with one another. At the heart of the Internet is a backbone of data communication links between major nodes or host computers including thousands of commercial governmental educational and other computer systems that route data and messages. Of course data processing environment also may be implemented as a number of different types of networks such as for example an intranet a local area network LAN or a wide area network WAN . is intended as an example and not as an architectural limitation for the different illustrative embodiments.

Among other uses data processing environment may be used for implementing a client server environment in which the illustrative embodiments may be implemented. A client server environment enables software applications and data to be distributed across a network such that an application functions by using the interactivity between a client data processing system and a server data processing system. Data processing environment may also employ a service oriented architecture where interoperable software components distributed across a network may be packaged together as coherent business applications.

With reference to this figure depicts a block diagram of a data processing system in which illustrative embodiments may be implemented. Data processing system is an example of a computer such as server or client in in which computer usable program code or instructions implementing the processes may be located for the illustrative embodiments.

In the depicted example data processing system employs a hub architecture including North Bridge and memory controller hub NB MCH and south bridge and input output I O controller hub SB ICH . Processing unit main memory and graphics processor are coupled to north bridge and memory controller hub NB MCH . Processing unit may contain one or more processors and may be implemented using one or more heterogeneous processor systems. Graphics processor may be coupled to the NB MCH through an accelerated graphics port AGP in certain implementations.

In the depicted example local area network LAN adapter is coupled to south bridge and I O controller hub SB ICH . Audio adapter keyboard and mouse adapter modem read only memory ROM universal serial bus USB and other ports and PCI PCIe devices are coupled to south bridge and I O controller hub through bus . Hard disk drive HDD and CD ROM are coupled to south bridge and I O controller hub through bus . PCI PCIe devices may include for example Ethernet adapters add in cards and PC cards for notebook computers. PCI uses a card bus controller while PCIe does not. ROM may be for example a flash binary input output system BIOS . Hard disk drive and CD ROM may use for example an integrated drive electronics IDE or serial advanced technology attachment SATA interface. A super I O SIO device may be coupled to south bridge and I O controller hub SB ICH .

An operating system runs on processing unit . The operating system coordinates and provides control of various components within data processing system in . The operating system may be a commercially available operating system such as Microsoft Windows Microsoft and Windows are trademarks of Microsoft Corporation in the United States and other countries or Linux Linux is a trademark of Linus Torvalds in the United States and other countries . An object oriented programming system such as the Java programming system may run in conjunction with the operating system and provides calls to the operating system from Java programs or applications executing on data processing system Java is a trademark of Sun Microsystems Inc. in the United States and other countries .

Instructions for the operating system the object oriented programming system and applications or programs are located on storage devices such as hard disk drive and may be loaded into main memory for execution by processing unit . The processes of the illustrative embodiments may be performed by processing unit using computer implemented instructions which may be located in a memory such as for example main memory read only memory or in one or more peripheral devices.

The hardware in may vary depending on the implementation. Other internal hardware or peripheral devices such as flash memory equivalent non volatile memory or optical disk drives and the like may be used in addition to or in place of the hardware depicted in . In addition the processes of the illustrative embodiments may be applied to a multiprocessor data processing system.

In some illustrative examples data processing system may be a personal digital assistant PDA which is generally configured with flash memory to provide non volatile memory for storing operating system files and or user generated data. A bus system may comprise one or more buses such as a system bus an I O bus and a PCI bus. Of course the bus system may be implemented using any type of communications fabric or architecture that provides for a transfer of data between different components or devices attached to the fabric or architecture.

A communications unit may include one or more devices used to transmit and receive data such as a modem or a network adapter. A memory may be for example main memory or a cache such as the cache found in north bridge and memory controller hub . A processing unit may include one or more processors or CPUs.

The depicted examples in and above described examples are not meant to imply architectural limitations. For example data processing system also may be a tablet computer laptop computer or telephone device in addition to taking the form of a PDA.

Presently software code exists that can be utilized for manipulating a RWL. Such software code is exposed to applications that wish to use the RWL via well defined application programming interface API . The software code behind each API performs a manipulation function with respect to the presently used RWL. Applications that wish to use a RWL call one or more of these API to perform one or more of the associated functions on a RWL.

In accordance with an illustrative embodiment a DML may take the place of a RWL in a given data processing system configuration. Accordingly applications utilizing the RWL have to perform similar functions using the DML upon substitution.

In order to avoid having to modify the code of hundreds or thousands of applications that use locks DML APIs should be similar to the APIs that are used for manipulating RWLs. The DML APIs should however implement the functions and operations behind those APIs with respect to a DML.

Configured in this manner DML interfaces appear no different from the existing RWL interfaces to an application but the application can transparently use a DML where the application was previously using a RWL. From an operating system s point of view the operating system can continue to expose familiar APIs to existing and new applications without having to address issues such as backward compatibility support for multiple sets of lock types or support for multiple sets of APIs.

With reference to this figure depicts a block diagram of an example operation of an initializing API in accordance with an illustrative embodiment. Lock may be a RWL or an original lock element of a DML as described elsewhere in this disclosure.

To expand a DML or an original lock element thereof the DML has to be expandable. The initialization of the expandable indicator in the lock word occurs by default for all locks initialized via the API lock init or another similar API. Upon initialization in this manner the expandable indicator of lock is set for example as shown in lock . Lock is an example expandable original lock element showing the expandable indicator as having been set to a value 1.

The particular API depicted in this figure is only an example and is not intended to be limiting on the invention. Any existing API for initializing a RWL can be modified in a similar manner to set the expandable indicator in a corresponding DML structure within the scope of the invention.

With reference to this figure depicts a block diagram of an example operation of another retooled API in accordance with an illustrative embodiment. Lock may be similar to lock in .

In some cases it may be desirable to not use an expanded lock structure such as a DML with the expanded elements. In one embodiment if the expandable indicator is reset or set to a particular value such as 0 the lock structure cannot be expanded as shown in lock . API lock ctl or another similar API can be used to turn off or reset the expandable indicator so that a lock cannot be expanded. Lock is an example of a non expandable original lock element showing the expandable indicator as having been reset to a value 0.

With reference to this figure depicts a block diagram of an example operation of another API in accordance with an illustrative embodiment. Lock may be a presently used RWL.

In an embodiment locks may be initialized differently for being an expandable lock or a non expandable lock. For example locks that are not initialized via lock init as shown in may not be expandable. As shown in this figure RWL may be initialized using an API different from lock init to form non expandable RWL . Thus if desired RWLs non expandable DMLs and expandable DMLs can coexist in a data processing system and may be initialized differently from one another.

With reference to this figure depicts a block diagram of a lock cache in accordance with an illustrative embodiment. Memory may be a lock cache and may be implemented using main memory in or any other suitable data storage device or location in a data processing system without limitation.

A number of lock structures such as storage for DML elements may be pre allocated at system initialization time so that those structures are available for lock transition. In one embodiment a memory segment such as memory may be allocated for the DML elements to be used later as needed during transitions. The initial address of the segment may be kept in a global pointer.

In one embodiment space for lock structures may include several pages of one or more desirable page sizes. Space may be pre allocated and pinned in memory at system initialization.

A number of pages in space may depend on the volume of lock contentions encountered during the operation of a data processing system. In a system where lock contention is below a threshold volume the number of pages in space may be small such as below a specified number of pages. In a system where lock contention is between two threshold volumes the number of pages in space may be a number in a specified range.

Memory may be re populated or space may be added to memory if the pre allocated cache is drained during the data processing system operation. For example in one data processing environment suitable code may be added to the xmgc kproc APIs to re populate or extend the cache.

With reference to this figure depicts a block diagram of the operation of another retooled interface in accordance with an illustrative embodiment. Lock may be similar to expandable original lock in .

Lock may be configured as expandable but may not yet be expanded. For example lock may have the expandable indicator set and the expanded indicator reset in such a configuration.

In one example embodiment during the transition of lock from expandable mode to expanded mode the interlock indicator is set and an expanded lock element is allocated. For example a get from list API may be modified to allocate expanded lock element from pre allocated pinned page . Pre allocated pinned page may be a page in space in . Index of the expanded lock element is maintained in expanded original lock element . Expanded original lock element is the expanded configuration of lock and has both the expandable indicator and the expanded indicator set.

With reference to this figure depicts a block diagram of the operation of another retooled interface in accordance with an illustrative embodiment. Expanded original lock element may be similar to expanded original lock element in . Expanded lock element in pre allocated pinned page may be similar to expanded lock element in pre allocated pinned page in . Expanded original lock element may have the expandable indicator and the expanded indicator set to specific values to indicate the expanded configuration of the DML.

API lock free can be modified to free expanded lock element . Freeing expanded lock element in pre allocated pinned page causes pre allocated pinned page to transform to pre allocated pinned page .

Once expanded lock element is freed expanded original lock element transforms to original lock element which may or may not be expanded depending on whether additional expanded lock elements remain indexed within original lock element . If no more expanded lock elements are indexed within original lock element the expandable indicator may remain set for allowing future expansion and the expanded indicator may be reset. If one or more expanded lock elements are still indexed within original lock element the expandable indicator and the expanded indicator may each remain set to indicate the expanded configuration.

API lock free may be modified such that the space freed in pre allocated pinned page by freeing expanded lock element can be used again by same or different expanding DML in the future. In one embodiment expanded lock element structures may preferably be allocated within the context of a modified lock read operation for maintaining the integrity of the lock.

With reference to this figure depicts a flowchart of an example process of using a retooled interface with a DML in accordance with an illustrative embodiment. Process may be implemented in an application for administrating locks in a data processing system such as in an operating system or a component thereof of server in .

Process begins by receiving an invocation of an interface to perform an operation on a lock step . The interface invoked may be the interface of a retooled existing method designed to work with a RWL or of a new method designed to work with a DML. Process determines whether the lock that is the subject of the operation is an upgraded lock step .

If the lock is not an upgraded lock No path of step the lock may be a RWL or a downgraded DML as described elsewhere in this disclosure. Accordingly process determines whether to upgrade the lock step . If process upgrades the lock Yes path of step process may perform the upgrade of the lock step . For performing step process may invoke an upgrading process not shown as described elsewhere in this disclosure. Following an upgrade of the lock in step process returns to step .

If process decides not to upgrade the lock No path of step process performs the operation of the invocation using a RWL or a downgraded DML step .

If the lock is an upgraded lock Yes path of step process performs the desired operation of the invocation in the backing high level language mode step . Backing high level language mode is simply the execution of a part of the logic of process that is coded in a high level language assuming that another part of process is coded in assembler or another low level language.

Process maintains the expandable and expanded indicators and the index of expanded lock elements as needed for the upgraded lock step . Process ends thereafter.

A high level programming language is a programming language that uses abstracted concepts of data processing system and provides a user a user friendly human understandable programming lexicon. C C and Java are some examples of high level programming languages.

A low level programming language is a programming language that employs a lower level of abstraction or no abstraction of the concepts of a data processing system. Machine language or binary code is regarded as the lowest level language. Assembly language or assembler code is regarded as another low level programming language.

Process may be particularly useful for modifying the low level programming language code generally assembler code that implement lock read lock write lock done and any other APIs or routines that include any low level language front end . The assembler routines are generally very short and highly optimized paths to handle the most frequent cases which do not involve upgrade or contention. These routines are generally the logical front end to a high level programming language code that each of these short routines calls to compute the more complicated paths.

In one embodiment the logic to handle upgraded DMLs may be implemented in a high level language such as in c language. An implementation of process may include a check in a low level programming language such as in assembler code to determine if the lock is upgraded as in step . If the lock is upgraded the implementation may branch to the c code or another high level language code which is more convenient for programming the logic code than the assembler language. Such a switch is a part of the backing higher level language mode operation of process . The assembler code and the higher level language code may together implement portions of process in some combination.

Many commonly implemented interfaces for using locks can be modified or retooled to operate using DML of an embodiment. Pseudo code for implementing some example retooled interfaces is provided here to illustrate the mechanism of using these APIs routines functions methods or services with a DML. The pseudo code described here can be easily converted into functioning code in any higher or lower level programming language of choice or a combination thereof without limitation. Furthermore the pseudo code is not intended to be comprehensive but only intended to illustrate certain considerations in implementing these interfaces for operations with a DML. Additional or different features or modifications can be integrated into existing interfaces for accomplishing similar purpose and the same are contemplated within the scope of the invention.

In the example pseudo code described herein when an operation is set to execute atomically a possibility exists that the atomic operation will fail. For the purposes of these examples a failed atomic operation simply means that when the attempt is made the data at the location does not contain the value that is expected or a race condition exists. Failure may mean that there is a race and the logic might need to retry or re read. In some cases the atomic operation can be performed again without retrying all the surrounding logic depending on the circumstances. Some sections of the example pseudo code briefly describe example consequences of failure.

References to complex lock in the pseudo code refer to a DML according to an embodiment. An interface with the words complex lock or other similar phrase may be an implementation with respect to an existing RWL that may continue to exist in that form of the API but operate with respect to a DML.

Other nomenclature abbreviations and shortened words for example reader writer waiter tid id sleep wakeup and many others as used in the pseudo code refer to their logically corresponding names and nomenclatures in this disclosure or as commonly used in software programming for lock manipulation. One of ordinary skill in the art will be able to identify the correspondence using this disclosure.

As one example wakeup c lock interface can be retooled to operate in conjunction with a DML in the following example way 

As another example complex lock sleep interface can be retooled to operate in conjunction with a DML in the following example way 

As another example lock write interface can be retooled to operate in conjunction with a DML in the following example way 

As another example lock read interface can be retooled to operate in conjunction with a DML in the following example way 

As another example expand and upgrade lock interface can be implemented to operate in conjunction with a DML in the following example way 

As another example lock done interface can be retooled to operate in conjunction with a DML in the following example way 

As another example lock read to write interface can be retooled to operate in conjunction with a DML in the following example way 

As another example lock write to read interface can be retooled to operate in conjunction with a DML in the following example way 

As another example lock try write interface can be retooled to operate in conjunction with a DML in the following example way 

As another example lock try read interface can be retooled to operate in conjunction with a DML in the following example way 

As another example lock try read to write interface can be retooled to operate in conjunction with a DML in the following example way 

As another example upgrade complex lock or clk upgrade interface can be implemented to operate in conjunction with a DML in the following example way 

The components in the block diagrams and the steps in the flowcharts described above are described only as examples. The components and the steps have been selected for the clarity of the description and are not limiting on the illustrative embodiments of the invention. For example a particular implementation may combine omit further subdivide modify augment reduce or implement alternatively any of the components or steps without departing from the scope of the illustrative embodiments. Furthermore the steps of the processes described above may be performed in a different order within the scope of the invention.

Any code or pseudo code described above is described only as an example. The nomenclature identifiers references functions operations and data structures have been selected for the clarity of the description and are not limiting on the illustrative embodiments of the invention. Furthermore any logic conditions or processing have also been selected for the clarity of the description and are not limiting on the illustrative embodiments of the invention. Any notes or comments embedded in the code or pseudo code are not intended to be limiting on the invention and are included merely as additional clarifying information. The nomenclature identifiers references functions operations data structures logic conditions or processing can be combined modified or replaced or alternatively implemented for similar purpose within the scope of the invention.

Thus a computer implemented method apparatus and computer program product are provided in the illustrative embodiments for retooling lock interfaces for using a dual mode reader writer lock. Using the embodiments of the invention a data processing system can operate with improved efficiency under lock contention conditions. Using the embodiment a data processing system can operate with improved efficiency also when a RWL is saturated and can hold no more locks.

A DML according to an embodiment can operate as a presently used RWL using only the original lock element of the expanded or unexpanded DML when demand for the lock is below a threshold. When the demand for the lock reaches or exceeds the threshold to wit when a contention condition exists for the lock the DML can transform to operate using expanded locks. In other words a DML according to an embodiment can be upgraded to operate in the expanded mode or downgraded to operate in the original mode depending on the demand for the lock.

The structure of a lock whether a RWL or a DML is a data structure in any suitable data storage location. In one embodiment an existing RWL may occupy less than 1 data word of space. In such an embodiment the original lock and one or more expanded locks can be accommodated within 1 data word within the scope of the illustrative embodiments. Expanded locks have been described as holding reader locks only as some example embodiments of the invention. Upon suitable modifications expanded locks can be used for holding a combination of types of locks including write locks.

An embodiment of the invention may facilitate maintaining the integrity of the DML while operating the DML. As one example method for maintaining the integrity of the DML the interlock indicator may be set to cause one operation to wait while another completes with respect to one or more elements of the DML. Other indicators different indicators than those described or a combination thereof may be used in a similar manner to implement a DML that can be operated while maintaining the lock s integrity. An indicator may be relocated to other elements of the DML than the element the indicator has been described in within the scope of the invention.

The rules described in particular embodiments are only examples and are not intended to limit the scope of the invention. Any rule may be implemented in a manner similar to the rules described in this disclosure within the scope of the invention.

The embodiments of the invention can collaborate with existing lock management applications. The embodiments can also allow existing applications and processes to transparently use DML where they were only configured to use presently used RWLs. Furthermore during use DML mode can change while the applications and processes using the DML remain unaware of such transitions.

The invention can take the form of an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software or program code which includes but is not limited to firmware resident software and microcode.

Furthermore the invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any tangible apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

Further a computer storage medium may contain or store a computer readable program code such that when the computer readable program code is executed on a computer the execution of this computer readable program code causes the computer to transmit another computer readable program code over a communications link. This communications link may use a medium that is for example without limitation physical or wireless.

A data processing system suitable for storing and or executing program code will include at least one processor coupled directly or indirectly to memory elements through a system bus. The memory elements can include local memory employed during actual execution of the program code bulk storage media and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage media during execution.

A data processing system may act as a server data processing system or a client data processing system. Server and client data processing systems may include data storage media that are computer usable such as being computer readable. A data storage medium associated with a server data processing system may contain computer usable code. A client data processing system may download that computer usable code such as for storing on a data storage medium associated with the client data processing system or for using in the client data processing system. The server data processing system may similarly upload computer usable code from the client data processing system. The computer usable code resulting from a computer usable program product embodiment of the illustrative embodiments may be uploaded or downloaded using server and client data processing systems in this manner.

Input output or I O devices including but not limited to keyboards displays pointing devices etc. can be coupled to the system either directly or through intervening I O controllers.

Network adapters may also be coupled to the system to enable the data processing system to become coupled to other data processing systems or remote printers or storage devices through intervening private or public networks. Modems cable modem and Ethernet cards are just a few of the currently available types of network adapters.

The description of the present invention has been presented for purposes of illustration and description and is not intended to be exhaustive or limited to the invention in the form disclosed. Many modifications and variations will be apparent to those of ordinary skill in the art. The embodiment was chosen and described in order to explain the principles of the invention the practical application and to enable others of ordinary skill in the art to understand the invention for various embodiments with various modifications as are suited to the particular use contemplated.

