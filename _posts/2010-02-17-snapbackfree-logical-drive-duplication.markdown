---

title: Snapback-free logical drive duplication
abstract: There is provided a method of duplicating a logical drive. The method includes sequentially copying data from a source logical drive to a destination logical drive and determining whether a write request is received to a data area on the source logical drive which has not yet been copied to the destination logical drive. If a write request is detected, the data at the write-requested data area is copied to the destination logical drive prior to executing the write request. By providing such a method, the destination logical drive can be used as the change-data store while in the process of the duplication operation, removing the need for a snapshot logical drive in the duplication process. This results in improvements in duplication speed and reduces drive wear due to the reduced number of data reads/writes.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08751761&OS=08751761&RS=08751761
owner: Xyratex Technology Limited
number: 08751761
owner_city: Havant
owner_country: GB
publication_date: 20100217
---
There are a number of possible architectures for storage systems such as data stores in networked computer systems. These systems often feature a large number of storage devices such as hard disks which are networked together. One arrangement of disk drives is known as a redundant array of inexpensive disk RAID arrays are the primary storage architecture for large networked computer storage systems. The RAID architecture was first disclosed in A Case for Redundant Arrays of Inexpensive Disks RAID Patterson Gibson and Katz University of California Berkeley . RAID architecture combines multiple small inexpensive disk drives into an array of disk drives that yields performance exceeding that of a single large drive.

There are a number of different RAID architectures designated as RAID 1 through RAID 6. Each RAID architecture offers different trade offs in terms of features and performance. In addition to the different architectures a non redundant array of disk drives is referred to as a RAID 0 array. RAID controllers provide data integrity through redundant data mechanisms high speed through streamlined algorithms and accessibility to stored data for users and administrators.

RAID architecture provides data redundancy in two basic forms mirroring RAID 1 and parity RAID 3 4 5 and 6 . The implementation of mirroring in RAID 1 architectures involves creating an identical image of the data on a primary disk on a secondary disk. The contents of the primary and secondary disks in the array are identical. Mirroring enables a system to maintain automatically one or more copies of data so that in the event of a disk hardware failure a system can quickly recover lost data. Mirroring may be performed locally or remotely as part of a disaster recovery process or both.

RAID 3 4 5 or 6 architectures generally utilise three or more disks of identical capacity. In these architectures two or more of the disks are utilised for reading writing of data and one of the disks stores parity data. Data interleaving across the disks is usually in the form of data striping in which the data to be stored is broken down into blocks called stripe units . The stripe units are then distributed across the disks. Therefore should one of the disks in a RAID group fail or become corrupted the missing data can be recreated from the data on the other disks. The data may be reconstructed through the use of the redundant stripe units stored on the remaining disks.

A RAID array is usually presented to the host user as one or more logical drives. A logical drive is a usable region of storage capacity located on one or more physical disk drive components in a computer system. The drive is referred to as logical or sometimes virtual because it does not actually form a physical entity in its own right and may comprise for example a partition on one or more disks in a RAID array.

In most modern storage networks a number of storage devices are connected to many host server devices in a storage network. A single RAID array may provide capacity to one or more servers. In this case logical drives are used to partition the available capacity and provide the amount of storage needed by each host from a common pool of logical drives.

Many modern disk controllers implement a feature known as logical drive duplication. This enables a user to generate an identical copy of a logical drive for backup or reference purposes. The copy of the logical drive resides on another physical storage area of the disk array or on an entirely different disk array.

The time taken to perform a logical drive duplication operation will depend upon the size of the logical drive to be duplicated. In the case of a large logical drive the time taken may be significant. The performance and availability of a system can be greatly hindered when a logical drive must be taken offline to perform a duplication operation.

Instead of taking a logical drive offline an alternative is to disable temporarily write access to data during the duplication either by stopping the accessing applications or by using a locking application provided by the operating system to enforce exclusive read access.

The above arrangements may be acceptable for low demand systems or non time critical environments such as for example desktop computers or small workgroup servers. However high demand systems or critical access systems such as storage area networks cannot afford to be inoperative for such time periods.

A known solution is to use a snapshot engine. A snapshot is a copy of a data set of the source logical drive which is frozen at a point in time. This data is stored on a snapshot logical drive. When a snapshot is first created only meta data relating to the configuration in which the source data is stored on the source logical drive is obtained and stored on the snapshot logical drive. Since there is no actual copying of data from the source logical drive to the snapshot logical drive the creation of the snapshot image is extremely fast and almost instantaneous.

The snapshot image then monitors and tracks any writes to logical blocks on the source logical drive. If a write is requested to a particular logical block of data the original data is copied onto the snapshot logical drive before the write is allowed to the logical block. This is known as a copy on write . This maintains on the snapshot logical drive a consistent image of the source logical drive at the exact time the snapshot was taken.

For a read request to a logical block on the source logical drive it is first determined whether the logical block of data has been modified by having been written to. If the logical block of data has not been written to then the read request is directed to the source logical drive. However if the read request is directed to a logical block of data which has been written to since the snapshot was taken then the read request is directed to the copied logical block stored on the snapshot logical drive.

Therefore snapshots enable source data protection during duplications and allows for continued normal host access of the source logical drive being duplicated. This therefore preserves a self consistent past image of the logical drive. The snapshot image contains the meta data describing the logical blocks of data that have changed since the snapshot was first created together with a copy of the original data of those logical blocks when the first write request to the logical blocks are received. The duplication engine then uses the snapshot data as a source logical drive for copying data which has changed onto the destination logical drive.

An alternative method of using a snapshot engine is to copy the data directly from the source logical drive and to allow writes to occur during this process. This may result in the destination logical drive comprising temporary corruptions due to writes occurring on the source logical drive during the duplication process. However this temporary corruption is corrected by performing a snapback from the snapshot logical drive.

A snapback describes the process whereby the newly duplicated destination logical drive is updated with data sourced from the snapshot logical drive. This will update only the data blocks which were modified e.g. written to during the duplication process because the snapshot contains only this data. Once the snapback process is complete the duplicated logical drive is freed from temporary corruption and contains an identical copy of the data on the source logical drive.

However a disadvantage of the above approaches is that storage space is required for a snapshot logical drive. The greater the number of writes that are issued to the source logical drive during the duplication process then a greater amount of data is required to be stored by the snapshot increasing the size of the storage area required.

Further the greater the amount of data that is stored by the snapshot the greater the amount of data that needs to be read from the snapshot logical drive and copied to the destination logical drive. This increases the time required to complete the duplication of the source logical drive. Further in cases where temporarily corrupted data on the destination logical drive is overwritten by data from the snapshot logical drive the particular block or blocks of data is written to the destination logical drive twice causing additional writes to be required.

Therefore known logical drive duplication methods and arrangements suffer from a technical problem that the duplication process requires a snapshot logical drive to be created and involves plural steps in order to duplicate the data on a source logical drive. This increases the number of writes that need to happen to copy a logical drive reducing the speed at which a duplication operation can be carried out.

According to a first aspect of the present invention there is provided a method of duplicating a logical drive comprising starting said duplication sequentially copying data from a source logical drive to a destination logical drive and determining whether subsequent to starting said duplication a write request is received to a data area on the source logical drive which has not yet been copied to said destination logical drive and if such a write request is received copying the data at said write requested data area to the destination logical drive prior to executing said write request.

By providing such a method the destination logical drive can be used as the change data store while in the process of the duplication operation removing the need for a snapshot logical drive in the duplication process. This improves duplication speed and reduces drive wear due to the reduced number of data reads writes.

In one approach if said write request is received the method further comprises the step of ignoring the data at said write requested data area during said sequential copying step. This approach means that data which has already been copied to the destination logical drive can be skipped during said sequential copying steps. This has benefits in terms of the number of copies required to be made and the increased speed of the duplication operation.

In another approach if said write request is received the method further comprises the step of storing information regarding said write requested data in a data file or memory. In a variation said data file is a bitmap.

By providing such a method write requested data which has already been copied to the destination logical drive can be tracked and monitored.

In one example said step of ignoring said data at said write requested data area involves determining from said data file the data area to be ignored during said sequential copying. The data file or bitmap provides a reference for a sequential copy engine to know which data to ignore during the sequential copy steps.

In one version said data is arranged in a plurality of logical blocks. In a variation the step of sequential copying starts with the first or last logical block in a group of logical blocks. In a further variation the step of sequential copying starts with the first or last logical block on the source drive.

In one variation the method further comprises prior to said sequential copying initialising said duplication process wherein said step of determining whether a write request is received comprises determining whether a write request is received after said initialisation.

According to a second aspect of the present invention there is provided an apparatus for duplicating a logical drive the apparatus comprising a controller operable to start said duplication and to copy sequentially data from a source logical drive to a destination logical drive and an access manager operable to determine whether subsequent to starting said duplication a write request is received to a data area on the source drive which has not yet been copied to said destination logical drive and if such a write request is received the controller is further operable to copy the data at said write requested data area to the destination logical drive prior to executing said write request.

By providing such an apparatus the destination logical drive can be used as the change data store while in the process of the duplication operation removing the need for a snapshot logical drive in the duplication process. This improves duplication speed and reduces drive wear due to the reduced number of data reads writes.

In a variation if said write request is received the apparatus is further operable to ignore the data at said write requested data area during said sequential copying step.

In a further variation if said write request is received the apparatus is further operable to store information regarding said write requested data area in a data file or memory. In one arrangement said data file is a bitmap.

In one example the apparatus is further operable to determine from said data file the data area to be ignored during said sequential copying.

In one example said data is arranged in a plurality of logical blocks. In a further example the apparatus is further operable to start said sequential copying with the first or last logical block in a group of logical blocks. In a yet further example the apparatus is further operable to start said sequential copying with the first or last logical block on the source drive.

In one variation the apparatus is further operable to prior to said sequential copying initialise said duplication process wherein said step of determining whether a write request is received comprises determining whether a write request is received after said initialisation.

In a variation the apparatus of the second aspect of the invention is in the form of a controller. In a further variation the controller is a RAID controller.

In an alternative variation the RAID controller comprises firmware software or a combination of both in an off host controller.

According to a third aspect of the present invention there is provided a data storage resource comprising at least one physical drive and a controller.

According to a fourth aspect of the present invention there is provided a computer program product executable by a programmable processing apparatus comprising one or more software portions for performing the steps of the first aspect of the present invention.

According to a fifth aspect of the present invention there is provided a computer usable storage medium having a computer program product according to the fourth aspect of the present invention stored thereon.

The hosts are connected to a first communication network which couples the hosts to a plurality of RAID controllers . The communication network may take any suitable form and may comprise any form of electronic network that uses a communication protocol for example a local network such as a LAN or Ethernet or any other suitable network such as a mobile network or the internet.

The RAID controllers are connected through device ports not shown to a second communication network which is also connected to a plurality of storage devices . The RAID controllers may comprise any storage controller devices that process commands from the hosts and based on those commands control the storage devices . RAID architecture combines a multiplicity of small inexpensive disk drives into an array of disk drives that yields performance that can exceed that of a single large drive. This arrangement enables high speed access because different parts of a file can be read from different devices simultaneously improving access speed and bandwidth. Additionally each storage device comprising a RAID array of devices appears to the hosts as a single logical storage unit LSU or drive.

The operation of the RAID controllers may be set at the Application Programming Interface API level. Typically Original Equipment Manufactures OEMs provide RAID networks to end users for network storage. OEMs generally customise a RAID network and tune the network performance through an API.

Any number of RAID controllers may be provided and N RAID controllers where N is an integer are shown in . Any number of storage devices may be provided in N storage devices are shown where N is any integer value.

The second communication network may comprise any suitable type of storage controller network which is able to connect the RAID controllers to the storage devices . The second communication network may take the form of for example a SCSI network an iSCSI network or fibre channel.

The storage devices may take any suitable form for example tape drives disk drives non volatile memory or solid state devices. Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device. More than one drive may form a storage device for example a RAID array of drives may form a single storage device . The skilled person will be readily aware that the above features of the present embodiment could be implemented in a variety of suitable configurations and arrangements.

The RAID controllers and storage devices also provide data redundancy. The RAID controllers provide data integrity through a built in redundancy which includes data mirroring. The RAID controllers are arranged such that should one of the drives in a group forming a RAID array fail or become corrupted the missing data can be recreated from the data on the other drives. The data may be reconstructed through the use of data mirroring. In the case of a disk rebuild operation this data is written to a new replacement drive that is designated by the respective RAID controller .

The host comprises a general purpose computer PC which is operated by a user and which has access to the storage area network . Any number of hosts may be provided. However for clarity only one host is shown in . A graphical user interface GM is run on the host . The GUI is a software application used to input attributes for the RAID controller and acts as a user interface for a user of the host .

The RAID controller comprises a software application layer an operating system and RAID controller hardware . The software application layer comprises software applications including the algorithms and logic necessary for the initialisation and run time operation of the RAID controller . The software application layer includes software functional blocks such as a system manager for fault management task scheduling and power management. The software application layer also receives commands from the host e.g. assigning new volumes read write commands and executes those commands. Commands that cannot be processed because of lack of space available for example are returned as error messages to the user of the host .

The operating system utilises an industry standard software platform such as for example Linux upon which the software applications forming part of the software application layer can run. The operating system comprises a file system which enables RAID controller to store and transfer files.

The RAID controller hardware is the physical processor platform of the RAID controller that executes the software applications in the software application layer . The RAID controller hardware comprises a microprocessor memory and all other electronic devices necessary for RAID control of storage device .

The storage device comprises a plurality of physical drives see . The physical drives may be any form of storage device such as for example tape drives disk drives non volatile memory or solid state devices. Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device.

The RAID array of physical drives is via the RAID controller presented as a logical drive upon which one or more volumes may be defined and which can be read write accessed by the host as a single volume. The logical drive may be considered to be a usable region of storage capacity located on one or more of the physical disk drive components forming the logical drive . The RAID array of physical drives may comprise any number of logical drives . However for clarity only one is shown and described herein.

The logical drive can be accessed by the host and RAID controller to read write data. Input output processing can also be carried out on the logical drive in the manner of an actual physical drive for example defragmentation rebuilding or backup operations.

In order to provide data security and redundancy it is important to backup the data stored on a logical drive at regular intervals. This is known as logical drive duplication. This enables a user on the host to generate an identical copy of a logical drive for backup or reference purposes. The copy of the logical drive may reside on an entirely different logical drive or on a dedicated backup storage facility such as a tape drive. The copied logical drive is known as the source logical drive and the copied data is written to what is known as a destination logical drive.

In the logical drive forms the source logical drive. also shows a configuration of a suitable destination logical drive. A plurality of physical drives form a RAID array similar to the physical drives . The physical drives are controlled by a further RAID controller not shown different from the RAID controller . The further RAID controller not shown presents the physical drives as a single logical drive . The logical drive is configured as a destination logical drive. The RAID array of physical drives may through the further RAID controller comprise any number of logical drives . However for clarity only one is shown and described herein.

In many cases the time taken to duplicate a large logical drive may be considerable. If a logical drive has to be taken offline or cannot be accessed for read write operations for a considerable period then time and efficiency losses to the users of the storage area network may be significant. High demand systems or critical access systems cannot afford to be inoperative for such time periods.

Consequently the embodiment of the present invention enables hosts to perform read write operations to the logical drive being duplicated during the duplication operation. The arrangement for duplicating a logical drive according to an embodiment of the present invention will now be described with reference to .

During the duplication operation a bitmap is created. The bitmap contains information relating to the duplication operation. This will be described later. The bitmap may be stored in a data area of the source logical drive temporary or otherwise. Alternatively the bitmap may be stored in the memory of the RAID controller or in any other suitable location. The bitmap may take the form of for example a look up table.

The duplication method will now be described with reference to . shows a flow diagram of the method for duplicating the source logical drive on the destination logical drive .

At step the duplication is initialised. In other words the duplication is started. When the duplication is complete the destination logical drive will comprise a copy of the source logical drive at the point in time that the duplication process was started. This step may simply be a reference point identifying when the duplication was started and need not require any actions to be carried out. Alternatively additional steps may be carried out as appropriate prior to copying of data from the source logical drive for example logging the time at which the duplication was started or initialising required programs. The skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

At step data is read from the source logical drive . This is the first part of the copy process the read data is then written to the destination logical drive in step to complete the copy process. The data is read in units of logical blocks see from the source logical drive . In the described example the copy process starts with the first logical block in sequence on the source logical drive i.e. the data is read from the first logical block 0 in a sequence of logical blocks from 0 to N. However any sequence may be used for example the read operation may start at logical block N or at any other suitable point.

As an alternative the step of reading may be performed in terms of multiple blocks. The skilled person would be readily aware of possible variations in the step of reading of the blocks and the combinations of blocks which could be read in a single step.

At step the data from the logical block read in step is copied to the destination logical drive to create a duplicate of the logical block on the destination logical drive . This is shown in . The method then proceeds to step .

Throughout the copy process it is determined whether all of the logical blocks on the source logical drive have been copied to the destination logical drive . If the determination is positive then the method proceeds to step and the duplication operation terminates. If however it is determined that there are still logical blocks to be copied on the source logical drive then the method proceeds to step .

Whilst step has been referred to herein as occurring after the first read and write steps it will be appreciated that this step may be carried out at any point during the duplication process or may be continuously checked for. The example shown and described herein is organised stepwise for clarity. However the skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

At step it is determined whether the host has issued a write request to a data area such as a logical block on the source logical drive which has not yet been copied to the destination drive since the duplication process was initiated at step .

If it determined that such a write request to a logical block on the source logical drive is detected then the method proceeds to step . If no write request to the source logical drive is detected then the method proceeds to step .

Alternatively if it is determined that the host has issued a write request to a data area or logical block which has already been copied in steps and there is no need to proceed to step because a copy of the original data in this data area is already present on the destination logical drive. Additionally if a write request is issued to a data area that has not yet been copied in steps and but to which a previous write request has been issued then there is no need to proceed to step because the data at this write requested area will already have been copied before the previous write request was allowed. In the above cases a write request to an already copied data area can be executed without any additional copying steps being required.

The step of determining whether the host has issued a write request to a logical block on the source logical drive since the duplication process was started has been referred to herein as occurring after the first read and write steps and after the determination of whether all logical blocks have been copied. However it will be appreciated that this step may be carried out at any point during the duplication process or may be continuously checked for throughout the duplication process. The example shown and described herein is organised stepwise for clarity. However the skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

If at step a write request to a particular data area or logical block is detected then the original data on that particular data area or logical block is copied in a copy operation to the destination logical drive prior to the write request being allowed. This process involves reading the original data on the source logical drive and writing a copy of this data to the destination logical drive . This operation preserves the original data by writing it to the destination logical drive before the data is overwritten by the execution of the write request at step . The method then proceeds to step .

At step the particular logical block copied to the destination logical drive in step is updated in a marking operation see on the bitmap by the RAID controller .

In this process the bitmap is updated to reflect the write requested logical blocks of data which have been copied in step . The bitmap can then be referred to in the sequential copy steps . Since the write requested logical blocks have already been copied to the destination logical drive there is then no need to copy these blocks again in the read and write steps of the sequential copy process. In other words at step it is specified by the bitmap that said write requested data in the particular logical block is ignored and not copied during said sequential copying in steps and .

As an alternative this step may occur at a different point in the process to that described herein e.g. the write requested logical block may be marked on the bitmap subsequent to the execution of the write request to the write requested logical block on the source logical drive .

The bitmap may also be used in the case where a second write request is received to the same data area. In this case the first write request will have triggered the copying at step and the updating of the bitmap at step . Therefore there is no need to copy any data from this data area and this second write request can simply be written straight to the source logical drive .

Once the original data in the write requested logical block has been copied to the destination logical drive then that particular logical block of data is now recorded safely and the write request to that particular logical block can be allowed.

At step the sequential copy process proceeds. In this example after a copy process of the first logical block of data from the source logical drive to the destination logical drive in steps and then at step the process moves to the next available logical block in the sequence of logical blocks. In other words the sequential copy process moves to data stored in another data area. In this example this will usually be the next block in the sequence of 0 to N.

However if at step the next logical block has been marked on the bitmap not to be copied then the process proceeds to the next available logical block i.e. the next logical block in sequence which has not been marked on the bitmap to be ignored during the copy process . In other words the process skips the data in the data area which has been marked on the bitmap to be ignored.

The method then proceeds back to step wherein the selected logical block is read and then at step written to the destination logical drive to complete the copy process for that particular block of data.

This process continues in a sequential copy process until it is determined at step that all logical blocks have been copied from the source logical drive to the destination logical drive .

Alternative sequence patterns may be used. The data may be read in any suitable sequence format for example in terms of logical blocks data addresses or data areas hard drive sectors or particular regions of the physical drive. Further any suitable sequence of data area copying may be used for example random a count down from logical block N to logical block 0 or a different sequential copy pattern arranged in terms of rows columns or any other pre determined order.

At step the destination logical drive now contains an exact copy of the data on the source logical drive at the moment the duplication process was initialised.

The above described embodiment of the present invention enables the destination logical drive removes the requirement for a snapshot process in a logical drive duplication operation. Therefore a separate snapshot data area is not required and this decreases the corresponding complexity of managing conventional snapshot related data resources.

Further the embodiment of the present invention described above enables the duplication process to be carried out more straightforwardly and at higher speed. This is because there is no requirement for an entire copy of snapshot data to be re applied to the destination logical drive after the sequential copy operation has completed. Consequently because the embodiment described above ensures that write requested data has already been copied to the destination logical drive before executing a write request no further data transfers are required once the sequential copy process has been completed.

Variations of the above embodiments will be apparent to the skilled person. The precise configuration of hardware and software components may differ and still fall within the scope of the present invention.

For example whilst the above examples have been shown and described with reference to a RAID arrangement this need not be so. Any suitable arrangement of physical drives or logical drive managers could be used. For example a single drive could be represented by a single logical drive.

Embodiments of the present invention have been described with particular reference to the examples illustrated. While specific examples are shown in the drawings and are herein described in detail it should be understood however that the drawings and detailed description are not intended to limit the invention to the particular form disclosed. It will be appreciated that variations and modifications may be made to the examples described within the scope of the present invention.

