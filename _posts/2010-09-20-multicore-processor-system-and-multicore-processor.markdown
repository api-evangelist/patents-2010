---

title: Multi-core processor system and multi-core processor
abstract: According to one embodiment, a state manager classifies an area allocated to the multi-core processor in a first memory area into one of a first state in which allocation to processor cores is not performed, a second state in which allocation to one of the processor cores is performed and read and write are performed, and a third state in which allocation to one or more of the processor cores is performed and read and write are prohibited, and further performs a transition from one of the first state, the second state, and the third state to another. A cache/memory manager writes back a corresponding cache when the state manager performs the transition from the second state to the third state.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08380936&OS=08380936&RS=08380936
owner: Kabushiki Kaisha Toshiba
number: 08380936
owner_city: Tokyo
owner_country: JP
publication_date: 20100920
---
This application is based upon and claims the benefit of priority from the prior Japanese Patent Application No. 2010 180156 filed on Aug. 11 2010 the entire contents of which are incorporated herein by reference.

Embodiments described herein relate generally to a multi core processor system and a multi core processor.

Conventionally there has been a demand for development of a technology for implementing a function of maintaining cache coherency by software rather than a hardware mechanism for suppressing increase in chip area and power consumption.

In general according to one embodiment a multi core processor system includes a multi core processor that includes a plurality of processor cores each including a cache and a first memory area in which an access using the cache is possible and an access without using the cache is impossible. The multi core processor further includes a state managing unit and a cache memory management unit. The state managing unit classifies an area allocated to the multi core processor in the first memory area into one of a first state in which allocation to the processor cores is not performed a second state in which allocation to one of the processor cores is performed and read and write are performed and a third state in which allocation to one or more of the processor cores is performed and read and write are prohibited and further performs a transition from one of the first state the second state and the third state to another. When the state managing unit performs the transition from the second state to the third state the cache memory management unit invalidates and writes back a corresponding cache line on the core where the transition is performed.

Exemplary embodiments of a multi core processor system and a multi core processor will be explained below in detail with reference to the accompanying drawings. The present invention is not limited to the following embodiments.

A multi core processor system includes a multi core processor and a memory . The multi core processor and the memory are connected to each other via a bus. The configuration can be such that these components are connected to each other in other network topologies such as mesh instead of the bus.

The multi core processor includes a plurality of cores processor cores for executing a user task and each core includes a cache .

The memory for example includes a Random Access Memory RAM . In the memory a kernel program for managing hardware resources of the multi core processor is loaded. Furthermore a kernel management area that the multi core processor can use as a main memory is reserved. The multi core processor allocates a memory area in the kernel management area to each core while maintaining coherency of the cache by executing the kernel program .

In the following explanation the operations expressed with the multi core processor as a main component are realized by the multi core processor more precisely the cores executing the kernel program or a user task a user task described later . The operations based on the kernel program are expressed with the kernel program as a main component in some cases. Furthermore the kernel program is abbreviated as the kernel in some cases. Moreover the operations based on the user task are expressed with the user task as a main component in some cases.

The load source of the kernel program can be a nonvolatile memory area that for example includes a Read Only Memory ROM an external storage or the like in which the program is stored in advance.

In the memory map shown in the shadow area with the size identical to the size of the area mapped as the main memory area is needed so that an address space is reduced. Furthermore it is needed to mount hardware for accessing the physical memory directly without using the cache so that development costs for a chip increases. Therefore in the first embodiment a Memory Access Protocol MAP is defined as described below so that the cache coherency can be maintained with respect to a memory with no shadow area i.e. a memory in which only an access using a cache is permitted. is a diagram explaining the MAP according to the first embodiment.

A state in which the memory area is out of the kernel management area is defined as the UNMANAGED state. The kernel does not manage the cache coherency in a memory area in this state.

A state in which allocation to a user task the core executing the user task is not performed by the kernel and the allocation is possible is defined as the INVALID state. Specifically the state before memory allocation and after memory freeing belongs to this state. No read write access from any user tasks is permitted.

A state in which the read write access using the cache is performed is defined as the PRIVATE state. Only one user task transitioned to this state is permitted to perform the read write access.

A state in which the memory area is shared by all of user tasks and in which no read write access from any user tasks is permitted is defined as the PUBLIC state. When transmitting data to other user tasks each user task must transition the data i.e. a memory area in which the data is stored to this state and the user task on the receiving side must transition the data in this state to the PRIVATE state or a PROTECTED state described below to read the data.

A state in which the access using the cache is possible only in the read access is defined as the PROTECTED state. The write access to an area in this state is impossible. Only one or more of the user tasks transitioned to this state is permitted to perform the read access using the cache .

The memory area contained in the kernel management area is in any one of the INVALID state the PRIVATE state the PUBLIC state and the PROTECTED state. Transition is possible between the INVALID state and the PUBLIC state and between the INVALID state and the PRIVATE state. The PUBLIC state can also be transitioned to the PRIVATE state and the PROTECTED state in addition to the INVALID state. In the kernel management area the cache coherency is maintained by following the memory access based on the definition of each of the INVALID state the PRIVATE state the PUBLIC state and the PROTECTED state and the relationship of the state transition.

The UNMANAGED state and the PROTECTED state are not the essential constituents of the structure for maintaining the cache coherency. However by providing the PROTECTED state simultaneous read out from the plurality of cores can be made possible. Furthermore by setting an area that is not under the management of the kernel to the UNMANAGED state and making the transition between the UNMANAGED state and the INVALID state possible the multi core processor system can dynamically change the size of the kernel management area placed under the management of the kernel .

The state transition function is an API Application Programming Interface for performing the transition between the states defined in the MAP described above. The state transition function includes the following ten functions.

The allocate private memory function is a function for allocating the memory area with a size specified by the argument size in the PRIVATE state from the memory area in the INVALID state.

The free private memory function is a function for freeing the memory area specified by the beginning address addr and the size size from the PRIVATE state to the INVALID state.

The allocate public memory function is a function for allocating the memory area with a size specified by the argument size in the PUBLIC state from the memory area in the INVALID state.

The free public memory function is a function for freeing the memory area specified by the beginning address addr and the size size from the PUBLIC state to the INVALID state.

The open private memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the PUBLIC state to the PRIVATE state.

The close private memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the PRIVATE state to the PUBLIC state.

The open protected memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the PUBLIC state to the PROTECTED state.

The close protected memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the PROTECTED state to the PUBLIC state.

The enter memory access protocol function is a function for transitioning the memory area specified by the beginning address addr and the size size from the UNMANAGED state to the INVALID state.

The leave memory access protocol function is a function for transitioning the memory area specified by the beginning address addr and the size size from the INVALID state to the UNMANAGED state.

In the first embodiment 1 the allocate private memory and 3 the allocate public memory are collectively referred to as the allocate function in some cases. Furthermore 2 the free private memory and 4 the free public memory are collectively referred to as the free function in some cases. Moreover 5 the open private memory and 7 the open protected memory are collectively referred to as the open function in some cases. Furthermore 6 the close private memory and 8 the close protected memory are collectively referred to as the close function in some cases.

The allocate function the free function the open function and the close function are called by the user task and an enter function the enter memory access protocol and a leave function the leave memory access protocol are called by the kernel itself.

The memory allocation managing unit and the MAP managing unit cooperatively classify the kernel management area into one of the states defined in the MAP and function as a state managing unit that performs the transition between the states.

The memory allocation managing unit manages increase and decrease of the kernel management area and allocation and freeing of a memory area in the kernel management area with respect to the user task . Specifically the memory allocation managing unit defines a binary variable isAllocated indicating whether or not a memory area in the kernel management area is allocated to the user task and updates and manages memory allocation management information indicating the state of the variable isAllocated of the memory area in the kernel management area . The isAllocated variable is mainly used for searching for an area that is not allocated to a task in the kernel management area .

When the enter function is called the memory allocation managing unit adds a corresponding entry to the memory allocation management information and when the leave function is called the memory allocation managing unit deletes a corresponding entry from the memory allocation management information . Furthermore when the allocate free function is called the memory allocation managing unit operates the value of the isAllocated variable of a corresponding entry.

The MAP managing unit manages the state of the MAP of the memory area to maintain the cache coherency in the kernel management area . Specifically the MAP managing unit classifies the state of the memory area into one of the four states of the INVALID state the PUBLIC state the PRIVATE state and the PROTECTED state registers the state in MAP management information and updates and manages the MAP management information in response to a call of the allocate free function and the open close function.

When the enter function is called the MAP managing unit adds a corresponding entry to the MAP management information and when the leave function is called the MAP managing unit deletes a corresponding function from the MAP management information .

In this example the area other than the kernel management area is implicitly set to the UNMANAGED state and is not managed explicitly in both the memory allocation management information and the MAP management information .

Furthermore although the example is explained in which the memory allocation management information has the table structure as an example of the data structure the data structure of the memory allocation management information is not limited to the table structure. For example information in a list format or information in a bitmap format is also applicable. Similarly the data structure of the MAP management information is not limited to the table structure.

When the close private memory is called the cache memory management unit writes the contents of a corresponding cache line in the cache back to a corresponding memory area. Furthermore when the close function is called the cache memory management unit invalidates a corresponding cache line.

Next the operation of the multi core processor system of the first embodiment is explained. First as a summary of the operation an example of the state transition is explained. is a flowchart explaining an example of the state transition of a memory area.

The memory area is in the UNMANAGED state that is not managed by the kernel S . In other words this memory area is not included in the kernel management area . Next the memory area is placed under the management of the kernel program and the state of the MAP of the memory area is transitioned to the INVALID state S . In other words this memory area is added to the kernel management area . Next when the user task calls the allocate public memory the state of this memory area is transitioned to the PUBLIC state by the operation of the MAP managing unit and this memory area is allocated to the user task that has called the function S . Thereafter when the user task calls the open private memory this memory area is transitioned to the PRIVATE state and the user task performs a read write access using the cache to this memory area S . During this access an access from other user tasks is not permitted so that the coherency of the corresponding cache line is maintained properly. When the user task calls the close private memory this memory area is transitioned back to the PUBLIC state S . At this time a corresponding cache line on the core where the transition is performed is properly written back to the physical memory by the cache memory management unit .

Thereafter when other user task specifies this memory area and calls the open protected memory this memory area is transitioned to the PROTECTED state by the MAP managing unit and the user task that has called the open protected memory performs a read access using the cache to this memory area S . The call of the open protected memory can be performed simultaneously by the plurality of user tasks . That is although the memory area in the PUBLIC state is registered in the MAP management information such that the memory area is allocated to one of the user tasks the memory area is virtually allocated to one or more of the user tasks . When the call is simultaneously performed by the plurality of user tasks the memory area is allocated to the plurality of user tasks that has performed the call.

When the user task that has completed the read access calls the close protected memory this memory area is transitioned back to the PUBLIC state S . Lastly when any of the user tasks calls the free public memory this memory area is transitioned to the INVALID state S . Then the leave memory access protocol is called so that the memory area is removed from under the management of the kernel and transitioned to the UNMANAGED state S and the series of the operations ends.

In this manner according to the first embodiment it is possible to maintain the coherency of the cache by a software mechanism using the memory in which only an access using the cache is permitted and it is also possible to share data between the plurality of cores .

Next the operation performed by the multi core processor system when each of the ten functions included in the state transition function is called is explained.

When the memory area with the specified size is normally allocated YES at S the MAP managing unit registers an entry containing the task ID of the user task as the allocation destination the state PRIVATE and the beginning address and the size of the allocated memory area in the MAP management information so that the allocated memory area is transitioned from the INVALID state to the PRIVATE state S . Then the memory allocation managing unit returns the beginning address of the allocated memory area S and the operation ends.

When the memory area with the specified size is normally allocated YES at S the MAP managing unit registers an entry containing the task ID of the user task as the allocation destination the state PUBLIC and the beginning address and the size of the allocated memory area in the MAP management information so that the allocated memory area is transitioned from the INVALID state to the PUBLIC state S . Then the memory allocation managing unit returns the beginning address of the allocated memory area S and the operation ends.

The kernel preferably calls the enter memory access protocol when the memory area in the INVALID state decreases and calls the leave memory access protocol when the memory area in the INVALID state excessively increases. When the kernel fails to allocate the memory area in the INVALID state with the size specified at Sll i.e. in the case of NO at S it is possible for the kernel to call the enter memory access protocol to reserve the memory area in the INVALID state.

As described above according to the first embodiment the memory allocation managing unit and the MAP managing unit cooperatively classify the kernel management area into one of the INVALID state the first state in which allocation to the cores is not performed the PRIVATE state the second state in which allocation to one of the cores is performed and read and write using the cache is performed and the PUBLIC state the third state in which allocation to one or more of the processor cores is performed and read and write are prohibited and further perform the transition between the states. Furthermore the cache memory management unit is configured to write back a corresponding cache line when the MAP managing unit performs the transition from the PRIVATE state to the PUBLIC state. Therefore the cache coherency in the memory in which only an access using the cache is permitted can be maintained by software. That is even in the multi core processor system that includes a memory with no shadow area it is possible to maintain the cache coherency by software. As for the transition between the PUBLIC state and the PRIVATE state and between the PUBLIC state and the PROTECTED state it is sufficient if at least one of them is possible.

Furthermore the MAP managing unit is configured to perform the transition between the PROTECTED state the fourth state in which allocation to one or more of the cores is performed and the read access is performed and the PUBLIC state. Therefore it is possible to simultaneously perform read out from the plurality of cores by performing the transition to the PROTECTED state.

Moreover the memory allocation managing unit is configured to allocate free the memory area in the INVALID state from to the UNMANAGED area in which allocation to the multi core processor is not performed. Therefore it is possible to dynamically increase and decrease the kernel management area .

In the above explanation it is explained that the multi core processor generates the state transition function the memory allocation managing unit the MAP managing unit and the cache memory management unit by executing the kernel program however it is possible to realize any of the above units by a program other than the kernel program . For example it is possible to realize the state transition function and the MAP managing unit by middleware.

When the memory shown in is employed the memory area that can be used as the kernel management area is limited to the memory area with the shadow area. In view of this according to a second embodiment it is enabled to reserve the kernel management area both in a memory area with the shadow area second memory area and a memory area with no shadow area first memory area .

The configuration of the multi core processor system according to the second embodiment is the same as the first embodiment except for the kernel program loaded on the memory. Detailed explanation of the same components is not repeated.

A state in which allocation to a user task is not performed by a kernel and the allocation is possible is defined as the EXT INVALID state.

A state in which the read write access using the cache is performed is defined as the EXT PRIVATE state. Only one user task transitioned to this state is permitted to perform the read write access.

A state in which the read write access without using the cache is performed is defined as the EXT PUBLIC state. A user task transitioned to this state can share data with other user tasks. A difference from c the PUBLIC state lies in that the read write access without using the cache can be performed.

A state in which the read access using the cache is performed is defined as the EXT PROTECTED state. The write access to an area in this state is impossible. Only one or more user tasks transitioned to this state is permitted to perform the read access using the cache .

The function configuration of the multi core processor system according to the second embodiment is the same as the multi core processor system of the first embodiment shown in . The multi core processor generates the state transition function the memory allocation managing unit the MAP managing unit and the cache memory management unit by executing the kernel program . Furthermore the multi core processor executes the user task .

The state transition function includes the following ten functions in addition to the functions 1 to 10 explained in the first embodiment.

The allocate ext private memory function is a function for allocating the memory area with a size specified by the argument size in the EXT PRIVATE state from the memory area in the EXT INVALID state.

The free ext private memory function is a function for freeing the memory area specified by the beginning address addr and the size size from the EXT PRIVATE state to the EXT INVALID state.

The allocate ext public memory function is a function for allocating the memory area with a size specified by the argument size in the EXT PUBLIC state from the memory area in the EXT INVALID state.

The free ext public memory function is a function for freeing the memory area specified by the beginning address addr and the size size from the EXT PUBLIC state to the EXT INVALID state.

The open ext private memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the EXT PUBLIC state to the EXT PRIVATE state.

The close ext private memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the EXT PRIVATE state to the EXT PUBLIC state.

The open ext protected memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the EXT PUBLIC state to the EXT PROTECTED state.

The close ext protected memory function is a function for transitioning the memory area specified by the beginning address addr and the size size from the EXT PROTECTED state to the EXT PUBLIC state.

The enter ext memory access protocol function is a function for transitioning the memory area specified by the beginning address addr and the size size from the UNMANAGED state to the EXT INVALID state.

The leave ext memory access protocol function is a function for transitioning the memory area specified by the beginning address addr and the size size from the EXT INVALID state to the UNMANAGED state.

In the second embodiment 1 the allocate private memory 3 the allocate public memory 11 the allocate ext private memory and 13 the allocate ext public memory are collectively referred to as the allocate function in some cases. Furthermore 2 the free private memory 4 the free public memory 12 the free ext private memory and 14 the free ext public memory are collectively referred to as the free function in some cases. Moreover 5 the open private memory 7 the open protected memory 15 the open ext private memory and 17 the open ext protected memory are collectively referred to as the open function in some cases. Furthermore 6 the close private memory 8 the close protected memory 16 the close ext private memory and 18 the close ext protected memory are collectively referred to as the close function in some cases.

The allocate function the free function the open function and the close function are called by the user task and an enter function the enter memory access protocol and the enter ext memory access protocol and a leave function the leave memory access protocol and the leave ext memory access protocol are called by the kernel itself.

The memory allocation managing unit updates and manages the memory allocation management information having the same data structure as that of the first embodiment. The memory allocation managing unit recognizes a range of the memory area with the shadow area within the memory and when the enter memory access protocol is called the memory allocation managing unit transitions the memory area in the UNMANAGED state and with no shadow area to the INVALID state. On the other hand when the enter ext memory access protocol is called the memory allocation managing unit transitions the memory area in the UNMANAGED state and with the shadow area to the EXT INVALID state.

The MAP managing unit manages the state of the memory area in the kernel management area based on the MAP shown in . Specifically the MAP managing unit classifies the state of the memory area into one of the six states of the PUBLIC state the PRIVATE state the PROTECTED state the EXT PUBLIC state the EXT PRIVATE state and the EXT PROTECTED state for each memory area allocated to the user task i.e. for each memory area of which isAllocated variable is true and registers the state in the MAP management information . Furthermore the MAP managing unit updates and manages the MAP management information in response to the call of the allocate free function and the open close function. The data structure of the MAP management information is the same as the data structure of the MAP management information shown in .

In both the memory allocation management information and the MAP management information the INVALID state and the EXT INVALID state are not managed distinctly from each other. However it is possible to manage these two states distinctly from each other based on information on either one of the states. For example it is possible to include an information bit indicating presence and absence of the shadow area in each entry of the memory allocation management information to make it possible to distinguish whether the memory area of which isAllocated is false is in the EXT INVALID state or the INVALID state. Furthermore it is possible to manage the memory area in the INVALID state or the EXT INVALID state by the MAP management information .

When the close private memory or the close ext private memory is called the cache memory management unit writes the contents of a corresponding cache line in the cache back to a corresponding memory area. Furthermore when the close function is called the cache memory management unit invalidates a corresponding cache line.

Moreover when the allocate public memory the close private memory or the close protected memory is called the cache memory management unit translates the beginning address of the memory area specified by the argument addr into the address of a corresponding shadow area. Furthermore when the free public memory the open private memory or the open protected memory is called the cache memory management unit translates the address of the shadow area specified by the argument addr into the address of a corresponding memory area.

Next the operation of the multi core processor system of the second embodiment is explained. is a flowchart explaining an operation performed when the allocate ext private memory is called. When the user task calls the allocate ext private memory the memory allocation managing unit sets true to the isAllocated variable of a continuous memory area which has the size specified by the argument size in the memory area with the shadow area and of which isAllocated variable is false i.e. the memory area in the EXT INVALID state and allocates this memory area to the user task S . When the memory area with the specified size is not normally allocated because of the reason that the continuous area in the EXT INVALID state is absence or the like NO at S the memory allocation managing unit returns NULL S and the operation ends.

When the memory area with the specified size is normally allocated YES at S the MAP managing unit registers an entry containing the task ID of the user task as the allocation destination the state EXT PRIVATE and the beginning address and the size of the allocated memory area in the MAP management information so that the allocated memory area is transitioned from the EXT INVALID state to the EXT PRIVATE state S . Then the memory allocation managing unit returns the beginning address of the allocated memory area S and the operation ends.

Subsequently the MAP managing unit registers an entry containing the task ID of the user task as the allocation destination the state EXT PUBLIC and the beginning address and the size of the allocated memory area the beginning address before translation in the MAP management information so that the allocated memory area is transitioned from the EXT INVALID state to the EXT PUBLIC state S . Then the memory allocation managing unit returns the beginning address of the allocated memory area S and the operation ends.

As described above according to the second embodiment the memory allocation managing unit and the MAP managing unit cooperatively classify the kernel management area reserved in the memory area with the shadow area into one of the EXT INVALID state the fifth state in which allocation to the cores is not performed the EXT PRIVATE state the sixth state in which allocation to one of the cores is performed and read and write using the cache are performed and the EXT PUBLIC state the seventh state in which allocation to one or more of the cores is performed and read and write without using the cache are performed and further perform the transition from one of the EXT INVALID state the EXT PRIVATE state and the EXT PUBLIC state to another. Furthermore the cache memory management unit is configured to write back a corresponding cache line when the MAP managing unit performs the transition from the EXT PRIVATE state to the EXT PUBLIC state. Therefore it is possible to place the kernel management area in both the memory area with the shadow area and the memory area with no shadow area. Consequently it is possible to increase the memory area to be used as the main memory compared with the system in which only a memory with the shadow area is used as the main memory or the system in which only a memory area with no shadow area is used as the main memory.

Furthermore the memory allocation managing unit is configured to allocate free the memory area in the EXT INVALID state from to the memory area in the UNMANAGED state in which allocation to the multi core processor is not performed. Therefore it is possible to dynamically increase and decrease the kernel management area reserved in the memory area with the shadow area.

While certain embodiments have been described these embodiments have been presented by way of example only and are not intended to limit the scope of the inventions. Indeed the novel embodiments described herein may be embodied in a variety of other forms furthermore various omissions substitutions and changes in the form of the embodiments described herein may be made without departing from the spirit of the inventions. The accompanying claims and their equivalents are intended to cover such forms or modifications as would fall within the scope and spirit of the inventions.

