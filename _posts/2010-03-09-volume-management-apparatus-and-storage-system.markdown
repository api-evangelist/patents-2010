---

title: Volume management apparatus and storage system
abstract: The present invention allocates a suitable physical device to each volume page according to the state transition command relating to paired volumes. A plurality of logical devices forming a logical storage area of a plurality of physical devices of varying performance are tiered according to the performance of the physical devices to form a pool volume, and each of the areas of the primary logical volume, secondary logical volume and pool volume are managed by a controller, divided into a primary page, secondary page and pool page. Upon receiving a pair formation-related command from the host computer, the controller allocates pool pages belonging to the same tier to the primary page and secondary page, and upon subsequently receiving a pair-related state transition command, the controller allocates a pool page, in a different tier from the primary page, to the secondary page.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08458421&OS=08458421&RS=08458421
owner: Hitachi, Ltd.
number: 08458421
owner_city: Tokyo
owner_country: JP
publication_date: 20100309
---
The present invention relates to a volume management apparatus and a storage system for performing management to dynamically allocate pages to logical volumes which are access targets of a host computer.

Conventionally there exist computer systems which provide a host computer with large scale data storage services. Among such systems a system is known which comprises a host computer a storage server to which the host computer is connected and a management apparatus for the storage server.

The storage server manages a plurality of hard disks using a RAID Redundant Array of Independent Inexpensive Disks system. The storage server also virtualizes a physical storage area of a multiplicity of hard disks and provides this physical storage area as logical volumes to the host computer. The host computer accesses the logical volumes and requests data reads and data writes.

One example of this type of virtualization technology is known as Thin Provisioning. The storage server configures a virtual volume which has no physical storage area for the host computer. The storage server sequentially allocates storage area to the virtual volume in step with the host computer write accessing the virtual volume.

Therefore this technology is effective in enabling storage resources to be effectively utilized in comparison with systems in which a large capacity storage area is allocated to the logical volumes from the outset. This technology appears in Japanese Unexamined Patent Publication Nos. 2003 15915 and 2006 338341.

Means for providing storage area to the virtual volume comprises means obtained by placing a plurality of logical volumes each assigned real storage area into logical groups called pools. The plurality of logical volumes are called pool volumes. When the virtual volumes are write accessed by the host computer a corresponding storage area of the pool volume is assigned to the virtual volume access destination.

The storage server is capable of saving write data from the host computer by mapping an area of access by the host computer to the virtual volume to an area in which storage capacity has been allocated to the pool volume.

Meanwhile in order to improve efficiency of investment in the storage server a storage server is required in which used storage media physical devices of a plurality of types are prepared and which is capable of defining data values and storing data by associating the values of the data with the storage media. Therefore U.S. Patent Publication No. 2005 055603 discloses the dynamic re allocation of suitable storage media to pages which are the units in which capacity is allocated in response to input output access to the pages.

U.S. Patent Publication No. 2005 055603 discloses the automatic re arrangement of suitable storage media onto pages which are the units in which capacity is allocated in response to input output access to the pages. However U.S. Patent Publication No. 2005 055603 does not disclose that suitable physical devices are allocated to the logical volumes which configuring paired volumes in response to a state transition command for changing the pair state between the paired logical volumes.

The present invention was conceived in view of the problems with the conventional technology and an object of the present invention is to provide a volume management apparatus and storage system with which suitable physical devices can be allocated to pages in each volume in response to a state transition command relating to paired volumes.

In order to achieve the foregoing object the present invention is configured such that a plurality of logical devices forming a logical storage area of a plurality of physical devices of varying performance are tiered according to the performance of the physical devices and the tiered logical volumes are stored in a virtualization pool as pool volumes which correspond to each tier a plurality of primary pages are allocated to a primary logical volume and a plurality of secondary pages are allocated to a secondary logical volume the storage area of the pool volume in each tier belonging to the virtualization pool is divided into a plurality of pool pages and these pool pages are managed and upon receiving a command relating to pair formation to pair the primary logical volume with the secondary logical volume any of the pool pages is allocated to the primary page and a pool page belonging to the same tier as the pool page allocated to the primary page is allocated to the secondary page and upon receiving a state transition command relating to the pair from the device which issued the command the tier of the pool page allocated to at least one of the primary page and secondary page is selected according to the state transition command.

According to the present invention suitable physical devices can be allocated to the pages of each of the volumes in response to a state transition command relating to paired volumes.

This embodiment is configured such that a plurality of logical devices forming a logical storage area of a plurality of physical devices of varying performance are tiered according to the performance of the physical devices and the tiered logical volumes are stored in a virtualization pool as pool volumes which correspond to each tier a plurality of primary pages are allocated to a primary logical volume and a plurality of secondary pages are allocated to a secondary logical volume the storage area of the pool volume in each tier belonging to the virtualization pool is divided into a plurality of pool pages and these pool pages are managed and upon receiving a pair formation related command pool pages belonging to the same tier are allocated to the primary pages and secondary pages and upon subsequently receiving a pair related state transition command and when page migration is instructed by the state transition command the pool page allocated to the secondary page is migrated to a pool page in a different tier from the pool page allocated to the primary page.

An embodiment according to the present invention will be described hereinbelow with reference to the drawings. is a hardware block diagram of a computer system to which the present invention is applied. The computer system comprises a host computer a management apparatus and a storage system to which the host computer and management apparatus are connected. The storage system is known as a storage server or a storage subsystem.

The host computer accesses logical storage resources of the storage system . The management apparatus manages the configuration of the storage area of the storage system . The storage system stores data in the storage area configured in the physical device .

The host computer comprises input means output means a CPU Central Processing Unit a memory a disk adapter a network adapter and a disk drive . The input means is means for receiving inputs from the system administrator or the like operating the host computer . The input means comprises a keyboard for example. The output means is means for displaying the state and configuration items of the host computer . The output means comprises a display device for example. Note that the configuration includes one or two of the host computer .

The CPU reads programs stored in the disk drive to the memory and executes the processing that is prescribed by the program. The memory comprises a RAM or the like for example and stores programs and data and so forth.

The disk adapter is connected to the storage system via a storage network and sends and receives data to and from the storage system . The storage network comprises a protocol Fibre Channel for example which is suited to data transfers.

The network adapter sends and receives data to and from the storage system management apparatus or the storage system via the management network . The management network comprises an Ethernet registered trademark for example.

The management apparatus comprises input means output means a CPU a memory a network adapter and a disk drive .

The input means is means for receiving inputs from the system administrator or the like operating the management apparatus . The input means comprises a keyboard for example. The output means is means for displaying the state and configuration items of the management apparatus . The output means comprises a display device for example.

The CPU reads a management program management software which is stored on the disk drive to the memory and executes management processing with respect to the storage system based on this program. The memory comprises a RAM or the like for example and stores programs and data and so forth.

The network adapter sends and receives data to and from the host computer or the storage system via the management network .

The storage system comprises a controller a storage cache memory a shared memory a physical device PDEV a power source switch and a power source .

The storage cache memory temporarily stores data which is read written from to the physical device PDEV . The shared memory stores configuration information of the controller and the PDEV and so on. The physical device PDEV comprises a plurality of disk devices. The power source supplies electrical power to each of the parts of the storage system . The power source switch is a switch which turns ON OFF the power supply from the power source . The disk drive storage device comprises a hard disk drive for example and mainly stores user data. The storage device may be a drive comprising a semiconductor memory such as a flash memory.

The controller comprises a host adapter a network adapter an involatile memory a power controller a memory a processor a storage adapter and a shared memory adapter .

The host adapter sends and receives data to and from the host computer via the storage network . The network adapter sends and receives data to and from the host computer or the storage system management apparatus via the management network .

The involatile memory comprises a hard disk or flash memory and stores programs and configuration information and so forth operated by the controller . The power source controller controls the electrical power supplied from the power source .

The memory comprises a RAM Random Access Memory or the like for example and stores programs and data and so forth. The processor reads programs stored in the involatile memory to the memory and executes the processing that is prescribed by the programs.

The storage adapter sends and receives data between the physical device PDEV and the storage cache memory . The shared memory adapter sends and receives data to and from the shared memory .

In a plurality of physical devices PDEV comprise a parity group for example and a virtual device LDEV is formed by the physical devices PDEV which belong to the parity group . The virtual device comprises a first type VDEV and is divided by a plurality of logic devices LDEV which form a logical storage area of the physical devices belonging to the parity group .

The logic devices LDEV are each stored in the system pool as first type LDEV and managed in association with logical volumes or logical units LU which are the access targets of the host computer . In other words the host computer is able to access the logical units as target devices and the logical units are configured by defining a path to the logic devices for the host computer .

In addition if an external physical device is connected to the outside of the storage system a virtual device LDEV is created from the external physical device . The virtual device VDEV is divided by a plurality of logic devices LDEV which form the logical storage area of the external physical device . The logic devices LDEV are each stored in the system pool and associated with logical volumes or logical units LU in the same way as the logic devices .

Furthermore the logic devices LDEV are each associated with pool volumes which are stored in the hierarchical management type capacity virtualization pool . A virtual volume forms a target device which is an access target of the host computer and comprises a virtual device VDEV . The virtual device VDEV is as a second type VDEV divided into a plurality of logic devices LDEV and the logic devices LDEV are as second type LDEV each associated with the pool volumes .

Here the virtual storage area of the virtual volume the storage area of the pool volumes and the storage area of each of the logic devices and are each divided into a plurality of areas and pages which are the units in which capacity is allocated are allocated to each of the areas.

Furthermore when access relating to new writing to an unallocated area is made to the virtual volume which includes a plurality of logic devices LDEV A pages P of the virtual volume are allocated to the new write access A pages P of the pool volumes are allocated to the pages P of the virtual volume A and pages P of the logic volumes are allocated to the pages P of the pool volume A A . The physical devices PDEV which belong to the parity group are allocated to the pages P of the logic devices A . As a result write data comes to be written to the physical devices PDEV which correspond to the pages P of the logic devices .

Here the physical devices PDEV are storage devices of varying performance or costs which comprise for example SSD Solid State Drives SAS Serial Attached SCSI Disks also referred to hereinafter as SAS SATA Serial ATA Disks also referred to hereinbelow as SATA and FC Fibre Channel Disks also called FC hereinbelow and if these storage devices are divided into a plurality of groups according to their performance such as for example their response time to read access or write access the logic devices and are constructed in tiers in correspondence with the performance of each of the physical devices PDEV and the pool volumes are also constructed in tiers in correspondence with the performance of each of the physical devices PDEV .

For example if the physical devices PDEV comprise physical devices of three different types of varying performance namely SSD SAS and SATA these physical devices PDEV are tiered divided into three groups where SSD is Tier SAS is Tier and SATA is Tier. In this case the logical volumes are tiered divided into three tiers namely an SSD comprising logical volume which belongs to Tier an SAS comprising logical volume which belongs to Tier and a SATA comprising logical volume which belongs to Tier and the pool volumes are tiered in correspondence with the logical volumes tiered divided into three tiers and stored in the hierarchical management type capacity virtualization pool .

The command control program parses commands from the host computer or the storage system management apparatus and executes processing that is prescribed by these commands. The path control program configures a path to the host computer . The host adapter control program controls input output data of the host adapter . The configuration control program controls the configuration of the storage system . The disk I O program controls access to the physical devices PDEV .

The network control program controls data which is sent and received via the storage network or management network . The pool control program configures the capacity virtualization pool and the system pool . The power source control program controls the ON OFF of the electrical power supplied by the power source . The cache control program controls the area and data of the storage cache memory . The drive diagnosis program diagnoses the state of each disk device of the PDEV physical devices .

The configuration information stores configurations relating to the virtual devices VDEV and logic devices LDEV of the storage system . The pool information stores configurations relating to the capacity virtualization pool and the system pool and so on. The configuration information includes an address management table LDEV management information target device information and VDEV management information .

The address management table stores address mapping information for the target devices LDEV and VDEV and the physical devices. The address management table includes target device LDEV mapping information LDEV VDEV mapping information and VDEV PDEV mapping information . The LDEV management information stores information relating to LDEV logic devices . The target device information stores target device related information. The VDEV management information stores information relating to VDEV virtual devices .

The hierarchical management type capacity virtualization management information includes POOL management information POOL VOL management information capacity virtualization pool configuration management information V VOLDIR capacity virtualization area management information PSCB capacity virtualization pool area management information SYS area information and hierarchical management information .

The pool management information stores configurations of the capacity virtualization pool . The POOL VOL management information stores information on the pool volumes of the capacity virtualization pool . The V VOLDIR stores address allocation of the pool volumes of the capacity virtualization pool . The PSCB information capacity virtualization pool area management information stores address information of the pool volumes in the capacity virtualization pool . The SYS area information stores information of the LDEV storing the configuration information of the storage system . The hierarchical management information stores information relating to the tiers of the pool volumes in the capacity virtualization pool .

The VDEV is an identifier of the VDEV virtual device . The emulation type is a VDEV emulation type identifier. The total size is the total size configured for the VDEV. The remaining size is the size of the unused area of the VDEV.

The device attribute is an identifier for the attribute that is defined for the VDEV. If the VDEV is a first type VDEV a VDEV allocated to the logical unit an identifier indicating the first type VDEV is stored and if the VDEV is a second type VDEV and configured in the virtual volume an identifier indicating the second type VDEV is stored.

The device state is an identifier that indicates the VDEV state. The VDEV states are normal closed and closed due to a fault or the like. Closure indicates closure for reasons other than fault generation such as closure caused by a puncture. Closure due to a fault indicates closure due to the generation of some kind of fault with the device.

The number of configured LDEV is the total number of LDEV configured for the VDEV. For the LDEV number the number of the LDEV configured for the VDEV is stored. The first VDEV SLOT is an identifier of the first physical slot number of the configured LDEV.

The final VDEV SLOT is the final physical slot number of the configured LDEV. The LDEV number the first VDEV SLOT and the final VDEV SLOT are configured for each of the LDEV numbers in the same quantity as the number of LDEV.

The LDEV is an identifier of the LDEV logic device . The emulation type is an LDEV emulation type identifier. The size is the total size configured for the LDEV.

The first slot number is an identifier of the first slot number of the configured LDEV. The final slot number is the final slot number of the configured LDEV. The path definition information is an identifier of the path defined in the host computer .

The device attribute is an identifier of the LDEV attribute. If the LDEV is a first type LDEV an identifier indicating the first type LDEV is stored and if the LDEV is a second type LDEV an identifier indicating the second type LDEV is stored. Furthermore if the LDEV is configured in the capacity virtualization pool an identifier indicating the pool attribute is stored.

The device state is an identifier that indicates the state of the VDEV to which the LDEV belongs. The VDEV states are normal closed and closed due to a fault or the like. Closure indicates closure for reasons other than fault generation such as closure caused by a puncture. Closure due to a fault indicates closure due to the generation of some kind of fault with the device.

If the LDEV is being processed by some kind of program the program usage state stores the identifier of the program. If the LDEV is configured in the capacity virtualization pool the POOL ID stores an identifier for the LDEV.

The target device LDEV mapping information stores correspondence between the target device address and LDEV address. The LDEV VDEV mapping information stores LDEV first type LDEV second type LDEV addresses and VDEV first type VDEV second type VDEV addresses.

The VDEV PDEV mapping information stores VDEV addresses RAID group numbers or parity group and PDEV physical device addresses.

The storage system is able to recognize that a target device address corresponds to an address of any given LDEV by referring to the address management table . The storage system is also able to recognize that an LDEV address corresponds to an address of any given VDEV. The storage system is also able to recognize that a VDEV address belongs to any given RAID group and corresponds to an address of any given PDEV.

The POOL ID is an identifier of the POOL capacity virtualization pool . The attribute application is an identifier indicating the attribute and application of the capacity virtualization pool . The application can be an operating form application such as a snapshot or SYS area or the like for example.

The emulation type is an identifier for the emulation type of the capacity virtualization pool . The capacity is the total capacity of the capacity virtualization pool and the unused capacity is the size of the unused area of the capacity virtualization pool .

The threshold is the maximum data storage capacity allowed by the capacity virtualization pool . The state is the current state of the capacity virtualization pool . The state is being defined undergoing expansion valid and so on for example. The number of POOL VOL is the total number of LDEV configured as the capacity virtualization pool .

The POOL VOL device number list is a list of LDEV numbers configured as the capacity virtualization pool . The number of devices using the POOL is the number of second type LDEV with which the LDEV of the capacity virtualization pool are associated. The number of the devices using the POOL is a list of the numbers of the second type LDEV with which the LDEV of the capacity virtualization pool are associated.

The port is the port number of the host adapter . The target device number indicates the number of the target device and when the virtual volume is the target device for example indicates the number of the virtual volume . The number of LDEV indicates when the virtual volume is the target device the number of LDEV second type LDEV which the virtual volume comprises. The LDEV indicates when the virtual volume is the target device for example the numbers of the LDEV second type LDEV which the virtual volume comprises.

The attribute indicates when the virtual volume is the target device for example the attribute of the virtual volume . The state indicates when the virtual volume is the target device the state of the virtual volume such as a state where the virtual volume is an access target for example. The capacity indicates when the virtual volume is the target device the capacity of the LDEV second type LDEV which the virtual volume comprises. The allowed host information is information which indicates when the virtual volume is the target device whether or not access to the virtual volume is allowed.

The storage system forms a first type VDEV virtual device from the physical devices PDEV by means of a RAID configuration. The first type VDEV is divided into a first type LDEV logic device which is a storage area. The first type LDEV is configured in the system pool . A volume which comprises the first type LDEV configured in the system pool is taken as the pool volume POOL VOL .

Furthermore the storage system configures the virtual volume VVOL and comprises the second type VDEV virtual device . The second type VDEV is divided into second type LDEV logic devices which are storage areas.

The storage system allocates the second type LDEV of the virtual volume to the first type LDEV logic device of the pool volume . As a result a storage area of the virtual volume accessed by the host computer is configured in the first type LDEV logic device comprising the physical devices PDEV . The configuration of the virtual volume is stored in the VVOL DIR . The VVOL DIR comprises an LDEV number LDEV and an entry .

The LDEV number LDEV is an identifier of the second type LDEV logic device . The entry is configuration information of the second type LDEV. The entry comprises a second type LDEV address and a PSCB pointer .

The second type LDEV address stores the address of the second type LDEV logic device of the virtual volume .

The PSCB pointer stores if the second type LDEV logic device is allocated to the first type LDEV logic device of the pool volume the PSCB pointer stores the pointer of the area of the first type LDEV logic device . Note that in an initial state the second type LDEV is not allocated to the first type LDEV and hence the PSCB pointer stores NULL. 

The PSCB POOL SLOT Control Block is information of the first type LDEV logic device configured in the pool volume . PSCB are configured for each slot of the first type LDEV logic device configured in the pool volume .

The PSCB comprises a real page number real page an address of the pool volume a pointer A and a pointer B.

The real page number real page is the real page number of the first type LDEV logic device in the pool volume . The address of the pool volume is the address of the first type LDEV logic device in the pool volume .

The pointer A and the pointer B are identifiers of the slots before and after the first type LDEV logic device in the pool volume .

Moreover the header of an unused area within the pool volume area is indicated by the free PSCB queue . The free PSCB queue includes the pointer to the PSCB indicating the next slot.

The storage system refers to the pointer indicated by the free PSCB queue to obtain the next PSCB . The storage system also refers to the pointer B of the next PSCB in order to follow the PSCB stepwise. The storage system then obtains the PSCB which corresponds to the final slot of the unused area.

The pointer B of the final PSCB is a free PSCB queue . The storage system follows the free PSCB queue and is able to determine the unused area of the pool volumes of the capacity virtualization pool from the aggregate group which is linked by pointers of the PSCB .

The storage system configures the PSCB which correspond to the first type LDEV logic devices configured in the pool volume . More specifically the storage system configures the PSCB which correspond to each slot of the first type LDEV logic devices configured in the pool volumes and configures the free PSCB queue . In an initial state the pool volumes are completely unused and therefore the aggregate group linked by the free PSCB queue corresponds to all the areas of the first type LDEV logic devices configured in the pool volumes .

Furthermore if the area of a pool volume is used this area is made usable as a result of the storage system allocating a quantity of the PSCB which corresponds to the required slots to the VVOL DIR which is a second type LDEV. The aggregate of the plurality of slots is equivalent to a page. A page is specified from a plurality of PSCB. Access to the virtual volume from the host computer and allocation of storage area from the pool volume to the access area of the virtual volume are executed in page units.

More specifically the storage system refers to the free PSCB queue . The storage system then acquires a quantity of PSCB which corresponds to the required area pages allocated to the second type LDEV. The storage system then allocates the acquired PSCB to each of the entries of the VVOL DIR . In other words the PSCB pointer of each of the entries in the VVOL DIR stores a pointer indicating the corresponding PSCB . Note that the allocated PSCB are excluded from the free PSCB queue .

As a result each page slot of the second type LDEV is allocated to the PSCB indicated by the PSCB pointer of each entry in the VVOL DIR . The PSCB correspond to the slots of the first type LDEV logic devices and as a result the second type LDEV are allocated to the first type LDEV logic devices and the virtual volume which is the access target of the host computer can be used as the target device.

In the pool management table when a second type LDEV of the virtual volume has not been allocated to the pool volume FREE information is stored in correspondence with the second type LDEV and when a second type LDEV of the virtual volume has been allocated to the pool volume ALLOCATED information is stored in correspondence with the second type LDEV.

If tiered pool volumes are stored in the capacity virtualization pool free PSCB are queued and managed for every tier and area is allocated to one LDEV for each page in a plurality of tiers. Here the page unit method is managed as PSCB unit information. The PSCB pointer is information indicating which area in the pool volume page data is stored in. The tier number is a tier number indicating which tier in the pool volume page data is stored in.

Here with regard to pool volumes if a pool volume belonging to Tier is a pool volume and a pool volume belonging to Tier is a pool volume for example a certain page of LDEV in the VVOL DIR is allocated area of the pool volume belonging to Tier and when addresses are managed by a PSCB of the PSCB S and this page is migrated to Tier processing is executed by the controller to acquire a PSCB of the PSCB from the free PSCB queue and copy the content of the PSCB to the PSCB S .

Thereafter processing is executed by the controller to connect the PSCB to the free PSCB queue S in order to change the mapping of a certain page of the LDEV in the VVOL DIR to the PSCB from the PSCB and return the PSCB to the free queue.

Note that page unit information also includes information acquired from the monitor. In this case the frequency of access to the pages is monitored and managed at regular intervals. Furthermore data stored in the pool volumes may have information appended thereto for each pool page to enable a search to determine which data at which address of which virtual volume has been allocated.

If the tiered pool volumes are stored in the capacity virtualization pool for example when the pool volumes are stored in the capacity virtualization pool divided into five tiers PSCB F is used as the PSCB of Tier PSCB R is used as the PSCB of Tier PSCBA is used as the PSCB of Tier PSCBD is used as the PSCB of Tier and the PSCBU is used as the PSCB of Tier.

The pool creation processing will be explained next with reference to the flowchart in . The CPU of the storage system management apparatus runs the management program management software instructs that pool creation be executed by designating a pool ID IDentifier threshold application the number of pool volumes logic device numbers LDEV reserve reserve devices different from the target device ratios S and transmits a pool creation instruction to the storage system S .

When the network adapter of the storage system receives a pool creation instruction the processor of the controller runs the command control program to start the following processing.

First the processor receives the pool creation instruction S checks the content of the command appended to the pool creation instruction S judges whether there is invalid content S migrates to pool creation processing when the command has no invalid content S determines whether or not pool creation processing has been successful S and when pool creation processing has succeeded transmits a response to the effect that pool creation has succeeded to the storage system management apparatus S .

On the other hand upon judging in S that the command content includes invalid content and upon judging in step S that pool creation processing has failed the processor transmits the cause of pool creation failure and an error response to the instruction to the storage system management apparatus S and ends the processing of this routine.

Upon receiving a pool creation processing response from the storage system S the CPU of the storage system management apparatus judges whether or not pool creation processing has succeeded based on the content of the received response S and when pool creation processing has succeeded logs the fact that the instructed pool creation has succeeded provides information to an external I F InterFace or GUI Graphical User Interface S and ends the processing of this routine.

When it is judged in step S that pool creation processing has failed the CPU logs the fact that the designated pool creation has failed as well as the cause of failure provides information to the external I F or GUI S and ends the processing of this routine.

Pool management information creation processing will be explained next with reference to the flowchart in .

This processing is pool management information creation processing which is to be executed in the pool creation processing in step S and is started as a result of the processor running the pool control program .

The processor performs a pool ID check checking for example whether the pool ID is valid and unused S changes the state of the pool capacity virtualization pool from undefined to being defined S and checks the state of the designated logic device LDEV S and since the checked logic device is inoperable when it is being used is subject to a fault is closed or being formatted and so on the processor ends the processing given that pool creation would fail and executes the following processing on the other logic devices S .

The processor then configures pool volume information for the LDEV information S updates the capacity of the pool management information the free capacity the threshold and the number of pool volumes S then creates a pool free management queue S creates a reserve queue S changes the pool state to valid S and ends the processing of this routine.

The virtual volume VOL creation processing will be explained next with reference to the flowchart in . The CPU of the storage system management apparatus runs a management program management software and starts the processing. The CPU designates the connected host information port numbers LUN logic device numbers LDEV the emulation type the capacity the virtual device number VDEV the pool ID the threshold the application QoS Quality of Services LANE and so forth and instructs virtual volume creation S and transmits a virtual volume creation instruction to the storage system S .

Meanwhile when the network adapter of the storage system receives a virtual volume creation instruction the command control program is run by the processor and the following processing is started.

First the processor receives a virtual volume creation instruction S checks the content of the command assigned to the virtual volume creation instruction S judges whether or not the command content is invalid content S executes virtual volume creation processing when there is no invalid content S and judges whether or not virtual volume creation processing has been successful S .

When it is judged in step S that virtual volume creation has succeeded the processor performs path definition processing for example defining a virtual volume as a logic unit LU for the port configures a host group logical unit number LUN and security S and transmits a response to the effect that virtual volume creation has succeeded to the storage system management apparatus S .

On the other hand upon judging in step S that the command content includes invalid content and upon judging in step S that virtual volume creation has failed the processor transmits the cause of virtual volume creation failure and an error response to the instruction to the storage system management apparatus S and ends the processing of this routine.

Upon receiving a virtual volume creation response from the storage system S the CPU of the storage system management apparatus judges whether or not virtual volume creation has succeeded based on the content of the received response S and when virtual volume creation processing has succeeded logs the fact that the instructed virtual volume creation has succeeded provides information to an external I F or GUI S and ends the processing in the routine.

When it is judged that virtual volume creation processing has failed the CPU logs the fact that the instructed virtual volume creation has failed as well as the cause provides information to the external I F or GUI S and ends the processing of this routine.

Virtual volume management information creation processing will be explained next with reference to the flowchart in . This processing is processing which is to be executed in the virtual volume creation processing in step S of and which is started as a result of the processor of the controller running the pool control program .

The processor performs as a virtual volume check for example a check of whether or not the virtual volume is valid and unused and checks the threshold or the like of the virtual volume S checks whether or not the number of the virtual device VDEV which belongs to the virtual volume is correct S and when the number of the virtual device is correct creates as virtual device information creation processing for example the pool number the capacity the emulation type the RAID level the state normal and so on S and then judges whether or not the logic device LDEV number is correct S .

When the number of the logical device LDEV is judged to be correct in step S the processor then creates as logic device information creation processing information such as the pool number the capacity the attribute virtual volume attribute and the state normal for example S and then creates as map information creation processing map information by referring to a specified data page S executes processing to the effect that the virtual volume creation processing has ended normally S and ends the processing in this routine.

However when it is judged in step S that the number of the virtual device VDEV is incorrect or when it is judged in step S that the number of the logic device LDEV is incorrect the processor executes processing to the effect that the virtual volume creation processing has ended abnormally S and ends the processing in this routine.

Conversely if a SAS belonging to Tier is eliminated as shown in b the controller manages the SATA configured in Tier after moving this SATA up to Tier. In this case the pool volumes are tiered and managed in two tiers.

Here in the storage system the act of copying data within the storage system will be referred to hereinafter as a local copy and if the storage system is connected to another storage system the act of copying a copy of data of a logical volume in the storage system to another storage system is known as a remote copy. 

Furthermore in a local copy and remote copy a set of a copy source logical volume and a copy destination logical volume will be referred to as a pair and of the logical volumes which the pair comprises for example a logical volume which is an access target of the host computer is called a primary logical volume P VOL and a logical volume which is a target of a pair of primary logical volumes P VOL will be referred to as a secondary volume S VOL .

When a new pair is formed formation copy processing is executed. In this case a copy source primary logical volume and copy destination secondary volume of the newly formed pair are designated. At this point in time the secondary volume does not store the same data as the primary logical volume however by executing a formation copy in which the data of the copy source primary logical volume is subsequently copied sequentially to the copy destination secondary volume the same data as the primary logical volume P VOL is stored in the secondary volume S VOL . A state where formation copying is executed is a state formation copying in progress. 

A state where data is copied and the same data is stored in the primary logical volume P VOL and secondary volume S VOL that is a state where data is duplicated is known as a synchronized state. In a synchronized state when data of a primary logical volume P VOL is updated the updated data is copied to the secondary volume S VOL . This copy is called an update copy.

A state where a data copy is stopped is a suspend state. In a suspend state pair data which is different from the primary logical volume P VOL is sometimes also stored in the secondary volume S VOL . In a suspend state and a formation copy in progress state differential management using a differential bitmap is executed.

For example when the pair to which the primary logical volume P VOL belongs is in a synchronized state all the bits of the differential bitmap are OFF invalid or 0. When the pair to which the primary logical volume P VOL belongs is in the suspend state when data of the primary logical volume P VOL is updated as a result of access from the host computer the bit corresponding to the storage area to which the data is written is updated to ON valid or 1. 

Meanwhile when a SPRIT command is issued as a state transition command linked to a pair processing to change a synchronized state pair to a suspend state is executed. When SPRIT processing is executed data copying from the primary logical volume P VOL to the secondary volume S VOL is not executed.

Furthermore when a re sync command is issued as a state transition command processing to change a suspend state pair to a synchronized state is executed. When re sync processing is executed among the data stored in the primary logical volume P VOL data that differs at least from the data stored in the secondary volume S VOL is copied to the secondary volume S VOL . As a result data which is the same as that of the primary logical volume P VOL is stored in the secondary volume S VOL .

Furthermore when a RESTORE or REVERSE re sync command is issued as a state transition command processing to change a suspend state pair to a synchronized state is executed. When restore or reverse re sync processing is executed among the data stored in the secondary volume S VOL data that differs at least from the data stored in the primary logical volume P VOL is copied to the primary logical volume P VOL . As a result data which is the same as that of the secondary volume S VOL is stored in the primary logical volume S VOL .

Processing when a pair related command is issued to the storage system from the host computer will be explained next with reference to . First as shown in the controller manages volumes which the virtual volume comprises namely an operational volume which is an access target of the host computer as a primary logical volume PVOL a virtual volume which is to be paired with the primary logical volume as the secondary logical volume SVOL allocates a plurality of primary pages P P . . . to the virtual storage area of the primary logical volume and allocates and manages a plurality of secondary pages S S . . . to the virtual storage area of the secondary logical volume .

Furthermore the controller tiers and manages the pool volumes stored in the capacity virtualization pool in three tiers. For example the controller tiers and manages the pool volumes such that a pool volume corresponding to the SSD comprising logic device LDEV belonging to Tier is pool volume a pool volume corresponding to the SAS comprising logic device LDEV belonging to Tier is pool volume and a pool volume corresponding to the SATA comprising logic device LDEV belonging to Tier is a pool volume allocates a plurality of pool pages P and P to the pool volume allocates a plurality of pool pages P and P to the pool volume and allocates a plurality of pool pages P P . . . to the pool volume .

Here when the controller receives as a pair related command from the host computer a command relating to pair formation pair create which pairs the primary logical volume with the secondary logical volume the controller allocates pages designated by the command allocating for example the pool pages P P to the primary pages P P and the pool volumes P P to the secondary pages S S of the secondary logical volume .

In other words primary page P and secondary page S are paired pages and primary page P and secondary page S are paired pages and therefore pool pages which belong to the same tier as the pool pages allocated to the primary pages P P are allocated to the secondary pages S S paired with the primary pages P P.

Thereafter a state is assumed where read access or write access to the primary logical volume and secondary logical volume are prohibited and the data of the primary pages P and P are copied to the secondary pages S and S respectively as pre update data. As a result the content of the data of the primary pages P P and the secondary pages S S is identical.

Subsequently when after receiving a pair created related command a pair suspend command is received as a pair related state transition command the controller stops an update copy between the primary logical volume and the secondary logical volume as shown in . At this time the host computer is able to perform read access or write access on the primary logical volume or the secondary logical volume .

Upon receiving a pair suspend command because the data of the secondary pages S S need not be stored in the Tier SSD or Tier SAS when migration from the SSD or SAS to the lower cost SATA is instructed in the suspend command the controller migrates the pool page P in the pool volume to the pool volume and makes this page the pool page P migrates the pool page P of the pool volume to the pool volume and makes this page the pool page P and then associates the secondary page S with the pool page P and associates the secondary page S with the pool page P.

The pool page P which belongs to Tier and the pool page P which belongs to Tier can accordingly be migrated to the pool pages P P respectively which belong to Tier in response to a state transition command. In this case when the host computer write accesses the secondary pages S S of the secondary logical volume the write data is stored in the SATA.

Furthermore when after a pair create command has been issued to the storage system a pair suspend command is issued the host computer is able to read access or write access the primary logical volume and the secondary logical volume of the storage system .

At this time as shown in when a backup to an external device such as tape media for example is instructed by the pair suspend command the controller executes processing to backup data stored in the secondary pages S S to the tape media .

Thereafter when a pair suspend command is received as a state transition command and a page migration instruction is contained in the pair suspend command the controller executes page migration processing in accordance with the page migration instruction

For example the controller migrates the pool page P in the pool volume to the pool volume and makes this page the pool page P migrates the pool page P of the pool volume to the pool volume and makes this page the pool page P and then associates the secondary page S with the pool page P and associates the secondary page S with the pool page P.

The pool page P which belongs to Tier and the pool page P which belongs to Tier can accordingly be migrated to the pool pages P P respectively which belong to Tier in response to a state transition command.

When after receiving a pair suspend command as a state transition command a command to spin down a physical device which belongs to the external physical device is received as a command containing a spin down instruction the controller executes processing in accordance with the command instruction as shown in .

Thereupon the controller stores as a spin down instruction data older than the Nth generation such as the fifth generation for example in the external physical device and when an instruction to spin down the external physical device is received stores a pool volume corresponding to the external physical device as a pool volume in the capacity virtualization pool allocates pool pages P P to the pool volume and associates the pool pages P P with the pages P P configured in the logical device of the external physical device .

Thereafter when the secondary pages S and S are associated with the pool pages P P in Tier the controller executes processing to associate the secondary pages S S with the pool pages P P migrates data earlier than the fifth generation stored in the secondary pages S S to the pages P P of the external physical device via the pool pages P P and spins down the external physical device in which pre fifth generation data is stored to reduce power consumption.

Thereafter if a pair suspend command is received when a pair re sync re synchronization command is received as a state transition command the controller executes processing in accordance with the pair re sync command as shown in .

In this case when after a pair suspend command is received the data of the primary logical volume is updated and a primary page P is added as a page for storing differential data and the primary page P is associated with the pool page P the controller configures a secondary page S in the secondary logical volume as a secondary page which is paired with the primary page P allocates a pool page P which belongs to the same tier as the pool page P to the secondary volume S and copies data of the primary page P to the secondary page S. Note that it is assumed that the data of the secondary pages S S is stored in the pool pages P P.

The processing when the controller receives a pair re sync reverse restore command will be described next with reference to . When after a pair suspend command is received a pair re sync reverse restore command is received as a state transition command the controller performs restore processing to restore the data backed up to the secondary logical volume to the primary logical volume .

Here for example S S and S exist in the secondary logical volume as secondary pages and the secondary page S is associated with the pool page P the secondary page S is associated with the pool page P and the secondary page S is associated with the pool page P. When in this state data of the secondary pages S S and S is copied to the primary volume the data of secondary page P is copied to the primary page P data of the secondary page S is copied to the primary page P and data of the secondary page S is copied to the primary page P.

Here when the controller receives the pair create command if the primary page P belongs to the pool volume which corresponds to the Tier SSD processing to map the primary page P to the pool page P is executed by the controller . Furthermore when the controller receives the pair create command if the primary page P belongs to the pool volume which corresponds to the Tier SAS processing to map the secondary page P to the pool page P is executed by the controller .

In addition when after restoration a page on which differential data is stored still exists in the primary logical volume as the primary page P the differential data stored on the primary page P is returned to a temporally preceding state as a result of the restore processing and is therefore unnecessary. The controller therefore frees the pool page P allocated to the primary page P and deletes the allocation.

The processing when the controller executes a quick restore command as a state transition command will be described next with reference to .

When a quick restore command is received from the host computer the controller executes a configuration change in which the primary logical volume is made the secondary logical volume and the secondary logical volume is made the primary logical volume and then executes processing in response to the command from the host computer to make the volumes which have undergone a configuration change as the access destination.

Here as a result of the host computer accessing the primary logical volume or the secondary logical volume of the storage system after issuing the quick restore command the controller is able to obtain the same data as when executing restore processing without executing a pair copy due to the pair request thereby enabling faster access to the storage system .

In this case the pool pages P P and P are allocated to the new primary pages P P and P respectively and pool pages P P P and P are allocated to the new secondary pages S S S and S. In addition the pool page P is migrated to the pool volume and managed as the pool page and the pool page P is migrated to the pool volume and managed as the pool page P.

The processing when the controller receives a pair delete command as a state transition command will be described next with reference to .

Upon receiving a pair delete command as a state transition command the controller deletes the relationship whereby the primary logical volume and the secondary logical volume are paired and deletes the relationship whereby the primary pages P P and P are paired with the secondary pages S S and S respectively. Here the controller comes to execute processing in accordance with subsequent commands in a state of holding correspondence relationships between the primary pages P P P and P and the pool pages P P P and P and correspondence relationships between the secondary pages S S and S and the pool pages P P and P.

The processing when the controller receives a snapshot creation command as a state transition command will be described next with reference to . Upon receiving the snapshot creation command the controller creates a secondary logical volume in addition to the secondary logical volume and allocates the secondary volumes S S to the secondary logical volumes when the pool page P is allocated to the primary page P and secondary page S the controller allocates the pool page P to the secondary page S and when the pool page P is allocated to the primary page P and secondary page S the controller allocates the pool page P in the same tier to the secondary page S.

The controller then copies the data obtained in the snapshots on the primary pages P and P respectively to the secondary pages S S and S.

When subsequently a pair suspend command is received and the primary logical volume and secondary logical volume enter a pair suspend state the host computer is capable of write accessing the primary logical volume or secondary logical volumes .

More specifically as shown in when a pair suspend command is input after snapshot creation processing the controller receives a request to write to the primary logical volume or secondary logical volumes . Here if there is write access to the primary page P for example when pre write access data is stored on the secondary page S the controller copies data of the secondary page S to the pool page P which belongs to the same tier as the pool page P allocated to the primary page P and changes the mapping destination.

Note that when the pair suspend command includes an instruction to migrate pre write data to Tier or Tier pre write data can also be copied from the secondary page S to the pool page of the pool volume which belongs to Tier or to the pool page of the pool volume which belongs to Tier.

Primary logical volume and secondary logical volume write processing will be explained next with reference to the flowchart in .

This processing is started as a result of the processor of the controller running the command control program . First the processor receives a write command from the host computer S checks the parameters of the received write command S and transmits a response relating to whether transfer is possible based on the result of this check to the host computer as a host command response S .

Thereafter upon receiving write data from the host computer S the processor confirms the pair state of the primary logical volume and the secondary logical volume S locks the write destination address S performs judgment processing to determine whether or not write data exists in the storage cache memory that is performs cache hit H or cache miss M judgment processing S and judges whether or not there is a cache hit S .

When there is no cache hit the processor then secures a write area in the storage cache memory S and then shifts to the processing of step S and when it is judged in step S that there has been a cache hit the processor determines the slot state of the storage cache memory S transfers the write data to the storage cache memory S performs differential bitmap processing to manage the differential bitmap S unlocks the write destination address S executes a write processing completion report for the host computer S and ends the processing in this routine.

Write after processing will be explained next as write processing of the primary logical volume and secondary logical volume with reference to the flowchart in .

This processing is started as a result of the processor of the controller running the disk I O program . The processor first performs a host dirty queue search S judges whether or not a virtual volume such as the primary logical volume for example is cached S and when the primary logical volume is cached judges whether or not there is a default page S and when there is a default page judges whether there is a free page S .

When there is a free page the processor selects an allocation page from the free queue as new allocation processing S subtracts the free capacity counter S and judges whether or not the subtraction result is the threshold S when the subtraction result is the threshold the processor issues a warning that free capacity is scarce S and then advances to the processing of step S when the processor judges that the subtraction result is not the threshold links the unallocated area to the pool free area S and moves to the processing of step S.

However when it is judged in step S that there is no default page the processor calculates the allocated page S and then advances to the processing of step S.

Furthermore when it is judged in step S that there is no free page the processor issues a warning that the free capacity is exhausted S then issues a warning to prohibit pool writing S then judges whether or not reserves are configurable for use S when reserves are not configurable the processor moves to the processing of step S and when configurable the processor terminates the processing in this routine.

In step S the processor creates parity data and so on in accordance with RAID level performs processing to re link the created parity data and so on to the disk write queue S and terminates the write after processing.

Read command processing with respect to the primary logical volume and secondary logical volume will be explained next with reference to the flowchart in .

This processing is started as a result of the processor of the controller running the command control program and the disk I O program .

The processor first receives a read command S checks the parameters of the received read command S then confirms the pair state based on the result of checking the command parameters for example the pair state of the primary logical volume and the secondary logical volume S then locks the read destination S executes cache hit or cache miss processing to check whether read data exists in the storage cache memory S and judges whether or not there is a cache hit S .

When there is a cache hit the processor confirms whether there is area to be allocated in the storage cache memory S judges whether area in the storage cache memory has been allocated S and when area has been allocated performs virtualization pool address conversion S .

When area has not been allocated in the storage cache memory the processor judges whether or not page allocation is required S and upon judging that page allocation is required the processor dynamically allocates pages to the storage cache memory and advances to the processing of step S.

Upon judging in step S that there is no cache hit the processor determines the slot state in the storage cache memory S and upon judging in step S that page allocation is not required the processor reads the data area of the default page S and then transfers read data to the storage cache memory S .

The processor then transfers read data of the storage cache memory to the host computer S unlocks the read destination S issues a completion report to the effect that read command processing is complete to the host computer S and terminates the read command processing.

Initial copy processing will be explained next with reference to the flowchart in . This processing is started when the controller receives a pair request command for example as a state transition command from the host computer .

First when the controller receives a pair request command the processor performs processing for turning ON a bitmap for copying to the whole copy target range S configuring a processing start address of the primary logical volume for example as the copy source processing start address S checking the copy bitmap S and judging whether or not a copy is required S judges whether or not a copy is required S and when a copy is not required the processor advances to the processing of step S promotes one copy processing judgment target address first returns to the processing of step S and then repeats the processing of steps S to S.

Meanwhile when it is judged in step S that a copy is required the processor confirms the copy source address and copy destination address and when for example the primary logical volume is the copy source and the secondary logical volume is the copy destination confirms the addresses of the primary logical volume and secondary logical volume S locks the copy source address S performs copy source hit H or hit miss M processing for judging whether copy source data exists in the storage cache memory S and judges whether or not there is a cache hit S .

When there is a cache hit the processor performs processing to determine the copy source cache area S lock the copy destination address S and check for a copy destination related hit or miss S and judges whether or not there is a cache hit to the copy destination storage cache memory S .

When there is no cache hit the processor secures cache area at the copy destination S determines the cache area at the copy destination S copies the data in the copy source storage cache memory to the copy destination storage cache memory S and advances to the processing of step S.

However when it is judged in step S that there is no cache hit the processor performs processing to secure the copy source disk area S lock the copy destination address S and check for a hit or miss with respect to the copy destination S and then judges whether or not there is a cache hit S . When there is no cache hit the processor secures area in the copy destination storage cache memory S determines when there is a cache hit the cache area in the area of the copy destination storage cache memory S copies the data in the copy source disk to the copy destination storage cache memory S and advances to the processing of step S.

In step S the processor turns OFF the copy bitmap and then unlocks the copy destination address S then unlocks the copy source address S judges whether or not the copy processing target address is the end address S and when it is not the end address the processor returns to the processing of step S and after promoting one copy processing judgment target address returns to the processing of step S and repeats the processing of steps S to S upon judging that the copy processing target address is the end address the processor ends the initial copy.

Differential copy processing will be explained next with reference to the flowchart in . This processing is started when the controller receives a pair re sync command for example as a state transition command from the host computer .

Upon receiving a pair re sync command the processor of the controller first configures a processing start address of the primary logical volume for example as the copy source processing start address S and then checks a differential bitmap a differential bitmap processed in step S of S and then performs processing to judge whether or not a copy is necessary S and judges whether or not a copy is required S . Upon judging in step S that a copy is not required the processor advances to the processing of step S promotes one copy processing judgment target address returns to the processing of step S and repeats the processing of steps S to S.

Meanwhile when it is judged in step S that a copy is required the processor confirms the copy source address and copy destination address and when for example the primary logical volume is the copy source and the secondary logical volume is the copy destination confirms the addresses of the primary logical volume and secondary logical volume S locks the copy source address S performs copy source hit H or hit miss M processing for judging whether copy source data exists in the storage cache memory S and judges whether or not there is a cache hit S .

When there is a cache hit the processor performs processing to determine the copy source cache area S lock the copy destination address S and check for a copy destination related hit or miss S and judges whether or not there is a cache hit to the copy destination storage cache memory S .

When there is no cache hit the processor secures cache area at the copy destination S then determines the cache area at the copy destination S copies the data in the copy source storage cache memory to the copy destination storage cache memory S and advances to the processing of step S.

However when it is judged in step S that there is no cache hit the processor performs processing to secure the copy source disk area S lock the copy destination address S and check for a hit or miss with respect to the copy destination S and then judges whether or not there is a cache hit S . When there is no cache hit the processor secures area in the copy destination storage cache memory S determines when there is a cache hit the cache area in the area of the copy destination storage cache memory S copies the data in the copy source disk to the copy destination storage cache memory S and advances to the processing of step S.

In step S the processor turns OFF the copy bitmap and then unlocks the copy destination address S then unlocks the copy source address S judges whether or not the copy processing target address is the end address S and when it is not the end address the processor returns to the processing of step S and after promoting one copy processing judgment target address returns to the processing of step S and repeats the processing of steps S to S upon judging that the copy processing target address is the end address the processor ends the differential copy.

Copy after write CAW and copy on write COW processing will be explained next with reference to the flowchart in .

This processing is started by the controller when write access to the primary logical volume is executed by the host computer or when read access or write access to the secondary logical volume is executed thereby.

The processor first performs processing to confirm the primary logical volume for example as the copy source and processing to confirm the secondary logical volume for example as the copy destination S and starts processing to lock the copy source address S and check for a cache hit or cache miss with respect to the copy source S and performs judgment of whether or not data which is to be copied to the copy source storage cache memory exists S .

When there is a cache hit the processor performs processing to determine the copy source cache area S lock the copy destination address S and check for a copy destination related hit or miss S and judges whether or not there is a cache hit to the copy destination storage cache memory S .

When there is no cache hit the processor secures cache area at the copy destination S then determines the cache area at the copy destination S copies the data in the copy source storage cache memory to the copy destination storage cache memory S and advances to the processing of step S.

However when it is judged in step S that there is no cache hit the processor performs processing to secure the copy source disk area S lock the copy destination address S and check for a hit or miss with respect to the copy destination S and then judges whether or not there is a cache hit S .

When there is no cache hit the processor secures area in the copy destination storage cache memory S determines when there is a cache hit the cache area in the area of the copy destination storage cache memory S copies the data in the copy source disk to the copy destination storage cache memory S and advances to the processing of step S.

In step S the processor unlocks the copy destination address and then unlocks the copy source address S and terminates the copy after write CAW and copy on write COW processing.

Disaster recovery processing of the computer system will be described next with reference to . shows the configuration of a computer system when a storage system with the same configuration as the storage system is a local storage system A another storage system with the same configuration as the storage system is a remote storage system B and when the local storage system A and the remote storage system B are connected by a storage network .

Here upon starting the processing of the disaster recovery DR when a remote copy command is transmitted via the storage network S from the local storage system A to the local storage system B the data of the primary logical volume A is copied to a primary logical volume B of the remote storage system B and then the data of the primary logical volume B is copied to the secondary logical volume B of the remote storage system B.

At this time in the local storage system A when the pool pages P P are associated with the primary pages P P and the pool pages P P are allocated to the secondary pages S S the pool pages P P are also allocated to the primary pages P P and pool pages P P are allocated to the secondary pages S S respectively in the remote storage system B.

In other words when data is backed up from the local storage system A to the remote storage system B backup source pages and backup destination pages in the same tier are associated with one another.

Processing in which a pair suspend command is input to the remote storage system B after data of the local storage system A has been backed up to the remote storage system B will be described next with reference to .

When after the data of the local storage system A has been backed up to the remote storage system B a pair suspend command is transferred to the remote storage system B from the local storage system A the controller of the local storage system A and the remote storage system B individually execute I O processing from the host computer in accordance with remote copy stoppage.

For example when I O processing from the host computer is received in the remote storage system B in a pair create state for example the I O processing from the host computer is executed.

Recovery processing when the local storage system A has recovered from a disaster will be described next with reference to .

When after data has been backed up to the remote storage system B the local storage system A undergoes disaster recovery and the data in the remote storage system B is copied to the local storage system A a reverse processing command is transferred to the local storage system A from the remote storage system B and the data of the primary logical volume B in the remote storage system B is copied to the primary logical volume A in the local storage system A. Thereafter data of the primary logical volume A in the local storage system A is copied to the secondary logical volume A.

As shown in when a remote copy is complete information to the effect that remote copying due to recovery processing is complete is transferred to the remote storage system B from the local storage system A via the storage network S and recovery processing is complete.

Furthermore various processing is executed in the local storage system A and the remote storage system B respectively in accordance with commands from the host computer . For example when a state transition command is issued from the host computer the processing shown in is executed as processing conforming to the state transition command by the controller of the local storage system A and the controller of the remote storage system B.

According to this embodiment when a command relating to pair formation is received from the host computer a pool page which belongs to the same tier is allocated to the primary page and secondary page and then when a pair related state transition command is received and page migration is instructed by the state transition command the pool page allocated to the secondary page is migrated to the pool page of a different tier from the pool page allocated to the primary page and the migrated pool page is allocated to the secondary page it is therefore possible to allocate a suitable physical device to the secondary page of the secondary logical volume in accordance with the state transition command.

Moreover according to this embodiment a suitable physical device can be allocated to the secondary page of the secondary logical volume in accordance with the state transition command and hence performance and reliability can be improved according to the logical volume application.

In addition according to this embodiment a pool page which is allocated to the primary page of the primary logical volume can also be migrated to a pool page in a different tier according to the state transition command.

