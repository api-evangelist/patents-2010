---

title: Data duplication resynchronization with reduced time and processing requirements
abstract: There is provided a method of resynchronising a previous duplication, started at a first time, of a source logical drive on a destination logical drive. The method comprises tracking changes to the data on said source logical drive since said first time and starting a resynchronisation operation at a second time later than said first time. The resynchronisation operation comprises copying data from said source logical drive to said destination logical drive by copying only data which has changed since said first time. By providing such a method, the need to copy data which has not changed since the previous duplication operation is alleviated. This reduces the time and processing required to perform the resynchronisation operation by eliminating unnecessary transfer of data which has not changed since the earlier duplication.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08745343&OS=08745343&RS=08745343
owner: Xyratex Technology Limited
number: 08745343
owner_city: Havant
owner_country: GB
publication_date: 20100420
---
The present invention relates to a method of and apparatus for re synchronising a duplication of a logical drive.

There are a number of possible architectures for storage systems such as data stores in networked computer systems. These systems often feature a large number of storage devices such as hard disks which are networked together. One arrangement of disk drives is known as a redundant array of inexpensive disk RAID . RAID arrays are the primary storage architecture for large networked computer storage systems. The RAID architecture was first disclosed in A Case for Redundant Arrays of Inexpensive Disks RAID Patterson Gibson and Katz University of California Berkeley . RAID architecture combines multiple small inexpensive disk drives into an array of disk drives that yields performance exceeding that of a single large drive.

There are a number of different RAID architectures designated as RAID 1 through RAID 6. RAID architecture provides data redundancy in two basic forms mirroring RAID 1 and parity RAID 3 4 5 and 6 . The implementation of mirroring in RAID 1 architectures involves creating an identical image of the data on a primary disk on a secondary disk. Mirroring enables a system to maintain automatically one or more copies of data so that in the event of a disk hardware failure a system can quickly recover lost data. Mirroring may be performed locally or remotely as part of a disaster recovery process or both.

RAID 3 4 5 or 6 architectures generally utilise three or more disks of identical capacity. In these architectures two or more of the disks are utilised for reading writing of data and one of the disks stores parity data. Data interleaving across the disks is usually in the form of data striping in which the data to be stored is broken down into blocks called stripe units . The stripe units are then distributed across the disks. Therefore should one of the disks in a RAID group fail or become corrupted the missing data can be recreated from the data on the other disks.

A RAID array is usually presented to the host user as one or more logical drives. A logical drive is a usable region of storage capacity located on one or more physical disk drive components in a computer system. The drive is referred to as logical or sometimes virtual because it does not actually form a physical entity in its own right and may comprise for example a partition on one or more disks in a RAID array.

In most modern storage networks a number of storage devices are connected to many host server devices in a storage network. A single RAID array may provide to capacity to one or more servers. In this case logical drives are used to partition the available capacity and provide the amount of storage needed by each host from a common pool of logical drives.

Many modern disk controllers implement a feature known as logical drive duplication. This enables a user to generate an identical copy of a logical drive for backup or reference purposes. The copy of the logical drive resides on another physical storage area of the disk array or on an entirely different disk array.

The time taken to perform a logical drive duplication operation will depend upon the size of the logical drive to be duplicated. In the case of a large logical drive the time taken may be significant. The performance and availability of a system can be greatly hindered when a logical drive must be taken offline to perform a duplication operation.

Instead of taking a logical drive offline an alternative is to disable temporarily write access to data during the duplication either by stopping the accessing applications or by using a locking application provided by the operating system to enforce exclusive read access.

The above arrangements may be acceptable for low demand systems or non time critical environments such as for example desktop computers or small workgroup servers. However high demand systems or critical access systems such as storage area networks cannot afford to be inoperative for such time periods.

A known solution is to use a snapshot engine. A snapshot is a copy of a data set of the source logical drive which is frozen at a point in time. This data is stored on a snapshot logical drive. When a snapshot is first created only meta data relating to the configuration in which the source data is stored on the source logical drive is obtained and stored on the snapshot logical drive. Since there is no actual copying of data from the source logical drive to the snapshot logical drive the creation of the snapshot image is extremely fast and almost instantaneous.

The snapshot image then monitors and tracks any writes to logical blocks on the source logical drive. If a write is requested to a particular logical block of data the original data is copied onto the snapshot logical drive before the write is allowed to the logical block. This is known as a copy on write . This maintains on the snapshot logical drive a consistent image of the source logical drive at the exact time the snapshot was taken.

For a read request to a logical block on the source logical drive it is first determined whether the logical block of data has been modified by having been written to. If the logical block of data has not been written to then the read request is directed to the source logical drive. However if the read request is directed to a logical block of data which has been written to since the snapshot was taken then the read request is directed to the copied logical block stored on the snapshot logical drive.

Therefore snapshots enable source data protection during duplications and allows for continued normal host access of the source logical drive being duplicated. This therefore preserves a self consistent past image of the logical drive. The snapshot image contains the meta data describing the logical blocks of data that have changed since the snapshot was first created together with a copy of the original data of those logical blocks when the first write request to the logical blocks are received. The duplication engine uses the snapshot data as a source logical drive for copying data which has changed onto the destination logical drive.

An alternative method of using a snapshot engine during duplications is to use the data directly from the source logical drive bypassing the snapshot logical drive. This may result in the destination logical drive comprising temporary corruptions due to writes occurring on the source logical drive during the duplication process. However this temporary corruption is corrected by performing a snapback .

A snapback describes the process whereby the newly duplicated destination logical drive is updated with data sourced from the snapshot logical drive. This will update only the data blocks which were modified e.g. written to during the duplication process because the snapshot contains only this data. Once the snapback process is complete the duplicated logical drive is freed from temporary corruption and contains an identical copy of the data on the source logical drive.

Once a duplication operation has completed then writes are once again allowed to the source logical drive and normal usage of the source logical drive continues. At some time later which may be anything from a few hours to a period of weeks or months it will become necessary to perform another duplication operation to duplicate the data stored on the source logical drive. This is to ensure that the data written to the source logical drive since the duplication operation is backed up to provide redundancy should the source logical drive become corrupted or the data thereon lost.

A known approach to this is to perform a further complete duplication operation as described above. This will resynchronise the data on the destination logical drive so that the data on the destination logical drive is an exact copy of the data on the source logical drive at the time the further duplication operation is initiated.

However a disadvantage of this approach is that all of the data on the destination logical drive is overwritten. Depending upon the amount of data that has changed in the time interval between the earlier duplication and the later one not all of the data may have been changed. Therefore in many cases the further duplication operation is overwriting data with the same unchanged data.

Therefore known destination logical drive resynchronisation methods and arrangements suffer from a technical problem that the resynchronisation process requires a further complete duplication operation to copy all of the data on the source logical drive irrespective of whether the data has been changed since the last duplication operation. By copying all of the data from the source logical drive to the destination logical drive data on the destination logical chive may potentially be overwritten by identical data. This is wasteful of system resources and unnecessarily increases the time required to resynchronise the destination logical drive to the source logical drive.

According to a first aspect of the present invention there is provided a method of resynchronising a previous duplication started at a first time of a source logical drive on a destination logical drive the method comprising tracking changes to the data on said source logical drive since said first time and starting a resynchronisation operation at a second time later than said first time said resynchronisation operation comprising copying data from said source logical drive to said destination logical drive wherein said copying comprises copying only data which has changed since said first time.

By providing such a method the need to copy data which has not changed since the previous duplication operation is alleviated. This reduces the time and processing required performing the resynchronisation operation by eliminating unnecessary transfer of data which has not changed since the earlier duplication.

In one embodiment the step of tracking changes comprises storing in a data storage area metadata relating to said changed data.

In one embodiment said step of tracking changes comprises utilising a first snapshot created at said first time said first snapshot comprising said metadata relating to said changed data. In a variation said data storage area comprises a snapshot logical drive.

Conventionally snapshots are used to track data which has changed during a duplication operation. However the inventors of the present application have realised that this approach can be used to monitor all of the changes on the source logical drive since the start of the previous duplication operation.

In a variation said first snapshot comprises only metadata. To store all of the data which has changed as copy on write data would be prohibitive in terms of the storage space required. By storing only metadata relating to the data which has changed since the first time the storage capacity required for the snapshot will be relatively small.

In an alternative variation wherein said first snapshot comprises only metadata relating to changes subsequent to said previous duplication operation.

In one embodiment the method further comprises prior to said step of tracking converting said first snapshot image such that said first snapshot image records only metadata relating to any writes to said source logical drive subsequent to completion of said previous duplication. This approach enables a conventional snapshot to be used during a duplication operation. Then after the duplication operation has completed the snapshot can be used to track the changes occurring on the source logical drive by recording metadata relating to data which has changed since said first time.

In another embodiment said resynchronisation operation further comprises prior to said copying creating a second snapshot of said source logical drive at said second time. The resynchronisation operation is configured to resynchronise the destination logical drive back to an identical copy of the source logical drive at the second time. Therefore a second snapshot can be employed to enable write requests to the source logical drive to continue i.e. copy on write during the resynchronisation process.

In one variation said copying utilises said second snapshot such that only data which has changed in between said first and second times is copied to said destination logical drive. The second snapshot can be used to provide a picture of the source logical drive at the second time irrespective of any writes which may have occurred on the source logical drive after the second time.

In another variation the method further comprises subsequent to said resynchronisation operation tracking data on said source logical drive which has changed since said second time. This process enables changes after the second time to be tracked so that a later resynchronisation operation can be carried out.

In one example the method further comprises prior to said tracking of data since said second time converting said second snapshot such that said second snapshot records only metadata relating to any writes to said source logical drive subsequent to completion of said resynchronisation operation.

According to a second aspect of the present invention there is provided a method of resynchronising a previous duplication started at a first time of a source logical drive on a destination logical drive the method comprising providing a first snapshot taken at said first time subsequent to said previous duplication converting said first snapshot such that said first snapshot records only metadata relating to any writes to said source logical drive subsequent to completion of said previous duplication tracking changes made to the data on said source logical drive since said first time using said converted first snapshot starting a resynchronisation duplication operation at a second time later than said first time creating a second snapshot at said second time and utilising said first and second snapshots copying only data which has changed in between said first and second times from said source logical drive to said destination logical drive.

According to a third aspect of the present invention there is provided a method of resynchronising a previous duplication started at a first time of a source logical drive on a destination logical drive the method comprising providing first and second snapshots taken at said first time said first snapshot comprising data and metadata relating to data which has changed since said first time and said second snapshot comprising only metadata relating to data which has changed since said first time subsequent to said previous duplication deleting said first snapshot tracking using said second snapshot changes made to the data on said source logical drive since said first time starting a resynchronisation operation at a second time later than said first time creating a third snapshot at said second time said third snapshot being arranged to comprise data and metadata relating to data which has changed since said second time utilising said second and third snapshots copying only data which has changed in between said first and second times from said source logical drive to said destination logical drive.

In one example the method further comprises creating a fourth snapshot at said second time said fourth snapshot being arranged to comprise only metadata relating to data which has changed since said second time.

According to a fourth aspect of the present invention there is provided apparatus for resynchronising a previous duplication started at a first time of a source logical drive on a destination logical drive the apparatus comprising a controller operable to track changes to the data on said source logical drive since said first time and to start a resynchronisation operation at a second time later than said first time the controller being further operable to perform said resynchronisation operation by copying data from said source logical drive to said destination logical drive said controller being operable to copy only data which has changed since said first time.

In one example the apparatus is further operable to store in a data storage area metadata relating to said changed data.

In one example the apparatus is further operable to utilise a first snapshot created at said first time said first snapshot comprising said metadata relating to said changed data. In a variation said data storage area comprises a snapshot logical drive.

In another variation said first snapshot comprises only metadata relating to changes subsequent to said previous duplication operation.

In one embodiment the apparatus is further operable prior to said step of tracking to convert said first snapshot image such that said first snapshot image records only metadata relating to any writes to said source logical drive subsequent to completion of said previous duplication.

In an example the apparatus is further operable prior to said copying to create a second snapshot of said source logical drive at said second time.

In another example the apparatus is further operable to utilise said second snapshot such that only data which has changed in between said first and second times is copied to said destination logical drive.

In a variation the apparatus is further operable subsequent to said resynchronisation operation to track data on said source logical drive which has changed since said second time.

In one example the apparatus is further operable to utilises said second snapshot to track data on said source logical drive which has changed since said second time.

In another example the apparatus is further operable prior to said tracking of data since said second time to convert said second snapshot such that said second snapshot records only metadata relating to any writes to said source logical drive subsequent to completion of said resynchronisation operation.

According to a fifth aspect of the invention there is provided apparatus for resynchronising a previous duplication started at a first time of a source logical drive on a destination logical drive the apparatus comprising a controller operable to provide a first snapshot taken at said first time to convert subsequent to said previous duplication said first snapshot such that said first snapshot records only metadata relating to any writes to said source logical drive subsequent to completion of said previous duplication to track changes made to the data on said source logical drive since said first time using said converted first snapshot to start a resynchronisation duplication operation at a second time later than said first time to create a second snapshot at said second time and to copy utilising said first and second snapshots only data which has changed in between said first and second times from said source logical drive to said destination logical drive.

According to a sixth aspect of the invention there is provided apparatus for resynchronising a previous duplication started at a first time of a source logical drive on a destination logical drive the apparatus comprising a controller operable to provide first and second snapshots taken at said first time said first snapshot comprising data and metadata relating to data which has changed since said first time and said second snapshot comprising only metadata relating to data which has changed since said first time to delete subsequent to said previous duplication said first snapshot to track using said second snapshot changes made to the data on said source logical drive since said first time to start a resynchronisation operation at a second time later than said first time to create a third snapshot at said second time said third snapshot being arranged to comprise data and metadata relating to data which has changed since said second time to utilise said second and third snapshots in order to copy from said source logical drive to said destination logical drive only data which has changed in between said first and second times.

By providing such an arrangement the need to overwrite copied data during the resynchronisation of the duplication process is removed. This reduces the time and processing required to perform the duplication operation by eliminating unnecessary data transfers.

In one arrangement the apparatus is further operable to create a fourth snapshot at said second time said fourth snapshot being arranged to comprise only metadata relating to data which has changed since said second time.

The inventors have identified an advantage in skipping the transfer of data from the source logical drive to the destination logical drive which has not been changed since the initial duplication operation was carried out.

In an alternative variation the RAID controller comprises firmware software or a combination of both in an off host controller.

According to a seventh aspect of the present invention there is provided a networked data resource comprising at least one physical disk and the RAID controller of the second aspect of the invention.

According to an eighth aspect of the present invention there is provided a computer program product executable by a programmable processing apparatus comprising one or more software portions for performing the steps of the first aspect of the present invention.

According to a ninth aspect of the present invention there is provided a computer usable storage medium having a computer program product according to the fourth aspect of the present invention thereon.

The hosts are connected to a first communication network which couples the hosts to a plurality of RAID controllers . The communication network may take any suitable form and may comprise any form of electronic network that uses a communication protocol for example a local network such as a LAN or Ethernet or any other suitable network such as a mobile network or the internet.

The RAID controllers are connected through device ports not shown to a second communication network which is also connected to a plurality of storage devices . The RAID controllers may comprise any storage controller devices that process commands from the hosts and based on those commands control the storage devices . RAID architecture combines a multiplicity of small inexpensive disk drives into an array of disk drives that yields performance that can exceed that of a single large drive. This arrangement enables high speed access because different parts of a file can be read from different devices simultaneously improving access speed and bandwidth. Additionally each storage device comprising a RAID array of devices appears to the hosts as a single logical storage unit LSU or drive.

The operation of the RAID controllers may be set at the Application Programming Interface API level. Typically Original Equipment Manufactures OEMs provide RAID networks to end users for network storage. OEMs generally customise a RAID network and tune the network performance through an API.

Any number of RAID controllers may be provided and N RAID controllers where N is an integer are shown in . Any number of storage devices may be provided in N storage devices are shown where N is any integer value.

The second communication network may comprise any suitable type of storage controller network which is able to connect the RAID controllers to the storage devices . The second communication network may take the form of for example a SCSI network an iSCSI network or fibre channel.

The storage devices may take any suitable form for example tape drives disk drives non volatile memory or solid state devices. Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device. More than one drive may form a storage device for example a RAID array of drives may form a single storage device . The skilled person will be readily aware that the above features of the present embodiment could be implemented in a variety of suitable configurations and arrangements.

The RAID controllers and storage devices also provide data redundancy. The RAID controllers provide data integrity through a built in redundancy which includes data mirroring. The RAID controllers are arranged such that should one of the drives in a group forming a RAID array fail or become corrupted the missing data can be recreated from the data on the other drives. The data may be reconstructed through the use of data mirroring. In the case of a disk rebuild operation this data is written to a new replacement drive that is designated by the respective RAID controller .

The host comprises a general purpose computer PC which is operated by a user and which has access to the storage area network . Any number of hosts may be provided. However for clarity only one host is shown in . A graphical user interface GUI is run on the host . The GUI is a software application used to input attributes for the RAID controller and acts as a user interface for a user of the host .

The RAID controller comprises a software application layer an operating system and RAID controller hardware . The software application layer comprises software applications including the algorithms and logic necessary for the initialisation and run time operation of the RAID controller . The software application layer includes software functional blocks such as a system manager for fault management task scheduling and power management. The software application layer also receives commands from the host e.g. assigning new volumes read write commands and executes those commands. Commands that cannot be processed because of lack of space available for example are returned as error messages to the user of the host .

The operating system utilises an industry standard software platform such as for example Linux upon which the software applications forming part of the software application layer can run. The operating system comprises a file system which enables RAID controller to store and transfer files.

The RAID controller hardware is the physical processor platform of the RAID controller that executes the software applications in the software application layer . The RAID controller hardware comprises a microprocessor memory and all other electronic devices necessary for RAID control of storage device .

The storage device comprises a plurality of physical drives see . The physical drives may be any form of storage device such as for example tape drives disk drives non volatile memory or solid state devices. Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device.

The RAID array of physical drives is via the RAID controller presented as a logical drive upon which one or more volumes may be defined and which can be read write accessed by the host . The logical drive may be considered to be a usable region of storage capacity located on one or more physical disk drive components forming the logical drive . The RAID array of physical drives may comprise any number of logical drives . However for clarity only one is shown and described herein.

The logical drive can be accessed by the host and RAID controller to read write data. Input output processing can also be carried out on the logical drive in the manner of an actual physical drive for example defragmentation rebuilding or backup operations.

In order to provide data security and redundancy it is important to backup the data stored on a logical drive at regular intervals. This is known as logical drive duplication. This enables a user on the host to generate an identical copy of the logical drive for backup or reference purposes. The copy of the logical drive may reside on an entirely different logical drive or on a dedicated backup storage facility such as a tape drive. The copied logical drive is known as the source logical drive and the copied data is written to what is known as a destination logical drive.

In the logical drive forms the source logical drive. also shows a configuration of a suitable destination logical drive. A plurality of physical drives form a RAID array similar to the physical drives . The physical drives are controlled by a further RAID controller not shown different from the RAID controller . The further RAID controller not shown presents the physical drives as a single logical drive . The RAID array of physical drives may through the further RAID controller comprise any number of logical drives . However for clarity only one is shown and described herein.

In many cases the time taken to duplicate a large logical drive may be considerable. If a logical drive has to be taken offline or cannot be accessed for read write operations for a considerable period then time and efficiency losses to the users of the storage area network may be significant. High demand systems or critical access systems cannot afford to be inoperative for such time periods. The arrangement for duplicating a logical drive will now be described with reference to .

There is also provided a snapshot logical drive . The snapshot logical drive comprises an additional storage area into which certain types of data will be stored during the duplication operation. The snapshot logical drive may be a separate logical drive from the source logical drive . Alternatively the snapshot logical drive may form a part of the source logical drive .

The snapshot logical drive comprises a snapshot . The snapshot is created at the same time that the duplication operation is started and comprises metadata relating to where the original data on the source logical drive is stored. The snapshot does not contain a physical copy of the data on the source logical drive . Therefore the snapshot is created almost instantaneously when the duplication operation is started.

The duplication method will now be described with reference to . shows a flow diagram of the method for duplicating the source logical drive on the destination logical drive .

At step the duplication is initialised at a time T. In other words the duplication is started. When the duplication is complete the destination logical drive will comprise a copy of the source logical drive at time Twhen the duplication process was started.

This step may simply be a reference point identifying when the duplication was started and need not require any actions to be carried out. Alternatively additional steps may be carried out as appropriate prior to copying of data from the source logical drive for example logging the time at which the duplication was started or initialising required programs. The skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

At this point the snapshot logical drive may also be created. This temporary drive may be created on spare space on the source logical drive or the data area for the snapshot may be located elsewhere. Once the destination logical drive and snapshot logical drive are created the duplication process can be initialised.

At step a snapshot of the source logical drive is created by a snapshot engine. The snapshot is a point in time representation of the source logical drive at the moment the duplication process is initialised i.e. at time T. This enables any changes to the original data on the source logical drive to be monitored and logged so that the destination logical drive can hold an exact duplication of the source logical drive when the duplication operation has completed. When the snapshot is created accesses to the source logical drive may have to be temporarily frozen however the creation of the snapshot is extremely fast and so any accessing applications will not be frozen for a significant period of time. The duplication method then proceeds to step .

At step data is read from the source logical drive . This is the first part of the copy process the read data is then written to the destination logical drive in step to complete the copy process. The data is read from data areas specified in units of logical blocks see from the source logical drive . In the described example the copy process starts with the first logical block in sequence on the source logical drive i.e. the data is read from the first logical block 0 in a sequence of logical blocks from 0 to N. However any sequence may be used for example the read operation may start at logical block N or at any other suitable point. The method then proceeds to step .

Alternatively the step of reading may be performed in terms of multiple blocks. The skilled person would be readily aware of possible variations in the step reading of the blocks and the combinations of blocks which could be read in a single step.

At step the data from the logical block read in step is copied to the destination logical drive to create a duplicate of the logical block on the destination logical drive . This is shown in . The method then proceeds to step .

Throughout the copy process it is determined whether all of the logical blocks on the source logical drive have been copied to the destination logical drive . If the determination is positive then the method proceeds to step . If however it is determined that there are still logical blocks to be copied on the source logical drive then the method proceeds to step .

Whilst step has been referred to herein as occurring after the first read and write steps it will be appreciated that this step may be carried out at any point during the duplication process or may be continuously checked for. The example shown and described herein is organised stepwise for clarity. However the skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

At step it is determined whether the host has issued a write request to a logical block on the source logical drive since the duplication process was initiated at step . This applies to any logical block on the source logical drive and not just to logical blocks which are currently being copied.

If it determined that a write request to a logical block on the source logical drive is detected then the method proceeds to step . If no write request to the source logical drive is detected then the method proceeds to step .

The step of determining whether the host has issued a write request to a logical block on the source logical drive since the duplication process was initiated has been referred to herein as occurring after the first read and write steps and after the determination of whether all logical blocks have been copied. However it will be appreciated that this step may be carried out at any point during the duplication process or may be continuously checked for throughout the duplication process. The example shown and described herein is organised stepwise for clarity. However the skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

If at step a write request to a logical block is detected then the original data on that particular logical block is copied in a copy operation to the snapshot logical drive prior to the write request being allowed. This is known as copy on write . This preserves the original data in the snapshot data area. The method then proceeds to step .

Once the original data in the write requested logical block has been copied to the snapshot logical drive then that particular logical block of data is now recorded safely and the write request to that particular logical block can be allowed.

At step the sequential copy process proceeds. In this example after a copy process of the first logical block of data from the source logical drive to the destination logical drive in steps and then at step the process moves to the next available logical block in the sequence of logical blocks. In other words the sequential copy process moves to data stored in another data area. In this example this will usually be the next block in the sequence of 0 to N.

Alternative sequence patterns may be used. The data may be read in any suitable sequence format for example in terms of logical blocks data addresses or data areas hard drive sectors or particular regions of the physical drive. Further any suitable sequence of data area copying may be used for example random a count down from logical block N to logical block 0 or a different sequential copy pattern arranged in terms of rows columns or any other pre determined order.

The method then proceeds back to step wherein the selected logical block is read and then at step written to the destination logical drive to complete the copy process for that particular block of data.

This process continues in the sequential copy process until it is determined at step that all logical blocks have been copied from the source logical drive to the destination logical drive .

Step occurs once the sequential copy process in steps and has been completed. At this point the process determines whether any data has been copied from write requested logical blocks to the snapshot logical drive during the duplication process.

If such data exists then a snapback process is carried out. This involves copying the logical blocks of data stored on the snapshot logical drive to the destination logical drive . This is so that the destination logical drive contains an exact copy of the data on the source logical drive at the time Twhen the duplication process was initialised.

At step the destination logical drive now contains an exact copy of the data on the source logical drive at time T i.e. the moment the duplication process was initialised at step .

Variations to the above method may be carried out. For example the sequential copy process may copy from the snapshot logical drive and not directly from the source logical drive . This means that step is not required because there is no need to perform a snapback operation to remove temporary corruption from the destination logical drive .

In this case if data in a data area has not changed since time T then the snapshot logical drive will refer the copy engine back to data on the source logical drive. However if data in a data area has changed since time T then copy on write process will have occurred and the snapshot logical drive will store an original copy of the data in the data area. in this case the data is copied directly from the snapshot logical drive.

After the duplication process has been completed the destination logical drive will contain an identical copy of the source logical drive at time T. The duplicate of the data from source logical drive on the destination logical drive can now be used as required for example as the basis for a tape back up copy or otherwise.

Once the duplication process has been completed no more data is shared between the source logical drive and the destination logical drive . Normal Operating System OS read and write requests are now allowed to happen to the source logical drive and this will cause the data on the source logical drive to change and to diverge over time from the duplicate of the data on the destination logical drive taken at time T.

Once the copy of the data on the destination logical drive has been utilised it may be required to perform another duplication operation to once again bring the data on the destination logical drive back into synchronisation with the data on the source logical drive . In other words it may be required to perform another duplication operation to make the destination logical drive an identical copy of the source logical drive at a time later than time T.

As previously described the snapshot logical drive comprises an additional storage area into which certain types of data will be stored during the duplication operation. The snapshot logical drive may be a separate logical drive from the source logical drive . Alternatively the snapshot logical drive may form a part of the source logical drive .

The snapshot logical drive comprises the snapshot taken at time T. The snapshot immediately after the duplication operation is completed at step comprises metadata relating to where the original data on the source logical drive is stored and copy on write data where writes were requested to the source logical drive during the copy process.

The snapshot is kept running after the duplication operation has completed and is modified so that the snapshot no longer stores any copy on write data in response to write requests addressed to data areas on the source logical drive .

Therefore whilst the snapshot will contain both metadata and copy on write data from the earlier duplication process initiated at time T the snapshot will only store metadata relating to changes occurring to the data on the source logical drive after the earlier duplication operation has been completed at step .

Therefore the snapshot will be relatively small in size because the snapshot will only comprise metadata relating to the changed data on the source logical drive after the duplication operation has completed.

The above data areas are followed by the actual data representing the changed data areas on the source logical drive . These data areas comprise a Stripe Header SH and a data packet . The SH comprises an address tag identifying a data area e.g. a logical block or a sector on the physical disk on the source logical drive which has changed since the snapshot was started. The data packet comprises the original data from a data area on the source logical drive which has been copied to the snapshot logical drive in a copy on write operation. This copy on write operation has been carried out to preserve the original data on the source logical drive prior to allowing a write request to that particular data area.

The snapshot also comprises stripe headers SHs which each comprise an address tag identifying a data area e.g. a logical block or a sector on the physical disk on the source logical drive which has changed since the snapshot was started.

However in contrast to the known snapshot data format the snapshot does not comprise any data packets or copy on write data. Therefore the snapshot merely contains a record of the data which has changed without storing a record of the original data which has been overwritten or deleted.

When a further duplication operation is required at a time T a further resynchronisation snapshot is created on the snapshot logical drive . The resynchronisation snapshot is used in the same manner as the snapshot was during the previous copy process. However in this case the copy engine is configured to refer to the snapshot in a referral process in order to determine which data areas to copy from the resynchronisation snapshot to the destination logical drive to resynchronise the two logical drives .

In the snapshot only snapshot metadata is being generated and stored on the snapshot overwrite data area. This metadata is generated the same way as for a known snapshot but without the pointers to the copy on write data since no data is actually copied.

A method to enable the destination logical drive to be re synchronised with the source logical drive according to a first embodiment of the invention is shown in . shows for consistency steps and of . However the remainder of the steps of are not shown for reasons of clarity and conciseness.

Normally when the duplication operation previously described with reference to is completed the snapshot is no longer needed and is deleted. However in the method according to an embodiment of the present invention the snapshot is maintained.

The snapshot comprises metadata relating to the configuration of the data on the source logical drive at time Twhen the earlier duplication operation was initialised at step . The snapshot also contains a copy of any original data on the source logical drive at time Tin a data area to which a write request was issued during the copy process. This is the copy on write data which was used to update the destination logical drive .

Instead of deleting the snapshot when the earlier duplication operation is completed the snapshot is maintained and the snapshot is kept running.

At step the snapshot from the previous duplication is maintained i.e. not deleted. In step the snapshot is modified so that the snapshot no longer stores any copy on write data in response to write requests addressed to data areas on the source logical drive . Therefore whilst the snapshot will contain both metadata and copy on write data from the earlier duplication process initiated at time T the snapshot will only store metadata relating to changes occurring to the data on the source logical drive after the earlier duplication operation has been completed at step to . Therefore the snapshot will be relatively small in size because the snapshot will only comprise metadata relating to the changed data on the source logical drive after the duplication operation has completed.

By keeping the snapshot running after the duplication operation has finished a record can be kept of any changes made to the data on the source logical drive since time T i.e. the time at which the earlier duplication operation was started . The changes to the data may comprise write requests which overwrite data previously stored at a particular data area deletions or newly added data. For each incoming write request addressed to a data area on the source logical drive metadata relating to the changed data at that particular data area will be stored in the snapshot .

Since the snapshot only records metadata relating to the data which has changed then the snapshot will neither take up excessive storage space nor be resource intensive to update. In contrast if the snapshot continued to store copy on write data for every write request to the source logical drive after the duplication operation had finished the storage space required to store the snapshot would be large. Further the speed at which the system could operate would be seriously compromised because for every write request to the source logical drive the copy on write data would have to be saved to the snapshot before the write could be executed to the source logical drive .

At step it is determined whether a request for a further duplication has been received. This may be specified by a user or may be predetermined to occur automatically a set interval.

If no duplication is required then the method proceeds back to step and continues to track the changes made to the source logical drive .

If a further duplication is required to bring the destination logical drive back into synchronisation with the source logical drive then the method proceeds to step .

In step a further duplication is initialised at a time Twhich is later than time T. In other words the further duplication is started at time T. When the further duplication is complete the destination logical drive will comprise a copy of the source logical drive at time Twhen the further duplication process was started.

This step may simply be a reference point identifying when the duplication was started and need not require any actions to be carried out. Alternatively additional steps may be carried out as appropriate prior to copying of data from the source logical drive for example logging the time at which the duplication was started or initialising required programs. The skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

A further snapshot is taken at time Twhen the duplication is initialised. The further or resynchronisation snapshot ensures that any writes issued to the source logical drive during the duplication process do not affect the copy of the data copied to the destination logical drive and that the destination logical drive comprises at the end of the copy process an identical copy of the source logical drive at time T.

At step the data from the resynchronisation snapshot is read. This is the first part of the copy process the read data is then written to the destination logical drive in step to complete the copy process.

However there is no need to copy data from the source logical drive or snapshot which has not changed since the earlier duplication process occurred at time T. Therefore the copy engine refers to the snapshot which has been running since time T to indicate which data areas or blocks have been changed since the previous duplication at time T.

In other words the snapshot contains metadata referring to only the data areas on the source logical drive which have been modified changed written to deleted or added to between times Tand T. The resynchronisation snapshot enables the data configuration on the source logical drive to be effectively frozen at time T. Therefore the resynchronisation snapshot does not comprise any physical data corresponding to activity occurring on the source logical drive after time T. Any incoming writes to the source logical drive will be subject to a copy on write operation i.e. the original data at the write requested data area will be copied to the resynchronisation snapshot data area prior to the write being allowed.

At step the data read in step is copied to the destination logical drive . The data written to the destination logical drive is data which has changed in between times Tand T. The written data area on the destination logical drive now corresponds to that on the source logical drive at time T. The method then proceeds to step .

Throughout the resynchronisation process it is determined whether all of the data on the source logical drive which has changed between times Tand Thas been copied to the destination logical drive . If the determination is positive then the method proceeds to step . If however it is determined that with reference to the snapshot there is still data to be copied from the source logical drive to the destination logical drive then the method proceeds to step .

Whilst this has been referred to herein as occurring after the first read and write steps it will be appreciated that this step may be carried out at any point during the duplication process or may be continuously checked for. The example shown and described herein is organised stepwise for clarity. However the skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

At step similarly to step described previously it is determined whether the host has issued a write request to a data on the source logical drive since the resynchronisation process was initiated at time T step .

If it determined that a write request to a data area e.g. a logical block on the source logical drive is detected then the method proceeds to step . If no write request to the source logical drive is detected then the method proceeds to step .

The step of determining whether the host has issued a write request to a logical block on the source logical drive since the resynchronisation process was initiated has been referred to herein as occurring after the first read and write steps and after the determination of whether all logical blocks have been copied. However it will be appreciated that this step may be carried out at any point during the duplication process or may be continuously checked for throughout the duplication process. The example shown and described herein is organised stepwise for clarity. However the skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

If at step a write request to a data area is detected then the original data on that particular data area on the source logical drive is copied in a copy operation to the snapshot logical drive prior to the write request being allowed. This is known as copy on write . This preserves the original data in the snapshot data area so that the resynchronisation snapshot is representative of the data on the source logical drive at time Twhen the resynchronisation operation is initiated. The method then proceeds to step .

Once the original data in the write requested data area e.g. logical block has been copied to the snapshot logical drive then that particular data area is now recorded safely and the write request to that particular data area can be allowed.

At step the resynchronisation process proceeds. In this example at step the resynchronisation process moves to the next data area to be copied as specified by the snapshot which comprises a record of which data areas have been changed or modified between times Tand T.

Alternative sequence patterns may be used provided that the data read is only data which has changed in between times Tand T. The data may be read in any suitable sequence format for example in terms of logical blocks data addresses or data areas hard drive sectors or particular regions of the physical drive. Further any suitable sequence of data area copying may be used for example random a count down from logical block N to logical block or a different sequential copy pattern arranged in terms of rows columns or any other pre determined order.

The method then proceeds back to step wherein the identified data is read and then at step written to the destination logical drive to complete the copy process for that particular data area.

This process continues until it is determined at step that all data areas which have been changed between times Tand Thave been copied from the source logical drive to the destination logical drive .

At step the destination logical drive now contains an exact copy of the data on the source logical drive at time T i.e. the moment the resynchronisation process was initialised at step . The method then proceeds to step .

At step the resynchronisation snapshot is converted into a dataless snapshot in the same manner as set out in step for the snapshot . In other words the resynchronisation snapshot is modified so that the resynchronisation snapshot no longer stores any copy on write data in response to write requests addressed to data areas on the source logical drive . Therefore whilst the resynchronisation snapshot will contain both metadata and copy on write data from the time period between time Tand the time the duplication operation terminates at step the resynchronisation snapshot will only contain metadata relating to changes occurring to the data on the source logical drive after step has been completed.

Therefore the resynchronisation snapshot will be relatively small in size because the resynchronisation snapshot will only comprise metadata relating to the changed data on the source logical drive after the resynchronisation operation has completed at step .

Once the resynchronisation snapshot has been converted to a snapshot format similar to the snapshot shown in there is no longer any need to keep the snapshot which specifies changes made between times Tand T and so the snapshot can be deleted. This is because the snapshot can provide a complete record of changes made to the data on the source logical drive after time T.

Should a further resynchronisation of the destination logical drive to the source logical drive be required at a later time i.e. later than time T then a further resynchronisation snapshot can be taken at a time Tand the earlier resynchronisation snapshot taken at time T can be used to direct the copy process to the data areas which have changed in between times Tand T.

As previously described the snapshot logical drive comprises an additional storage area into which certain types of data will be stored during the duplication operation. The snapshot logical drive may be a separate logical drive from the source logical drive . Alternatively the snapshot logical drive may form a part of the source logical drive .

The snapshot logical drive comprises a snapshot taken at time Tand a snapshot taken at time T. The snapshots have the same format as the snapshot i.e. the snapshots comprise both metadata and data.

The snapshot logical drive also comprises snapshots . Snapshot is also taken at time T. Snapshot is taken at time T. The snapshots both have the same format as snapshot shown in . Therefore snapshot comprises only metadata relating to changes occurring on the source logical drive since time T. Snapshot only comprises metadata relating to changes occurring on the source logical drive since time T.

A method to enable the destination logical drive to be re synchronised with the source logical drive according to a second embodiment of the invention is shown in .

At step the duplication is initialised at a time T. In other words the duplication is started. When the duplication is complete the destination logical drive will comprise a copy of the source logical drive at time Twhen the duplication process was started. This step is in essence identical to step described previously and for reasons of conciseness will not be described further here.

At step a snapshot of the source logical drive is created by a snapshot engine. The snapshot is a point in time representation of the source logical drive at the moment the duplication process is initialised i.e. at time T. As discussed previously this enables any changes to the original data on the source logical drive to be monitored and logged so that the destination logical drive can hold an exact duplication of the source logical drive when the duplication operation has completed. When the snapshot is created accesses to the source logical drive may have to be temporarily frozen however the creation of the snapshot is extremely fast and so any accessing applications will not be frozen for a significant period of time. The snapshot stores both metadata and data relating to the original copy data which has changed since time T.

Additionally a further snapshot is taken at time T. As described above the snapshot comprises only metadata and does not store any copy on write data as is the case for snapshot .

The duplication method then proceeds in the manner shown in along steps equivalent to steps to . These steps of the duplication procedure have already been described and for conciseness will not be described again here. However the method of the second embodiment can be considered to comprise steps equivalent to steps .

After steps equivalent to steps to have been carried out the destination logical drive will be an exact copy of the source logical drive at time T. In contrast to the first embodiment at this point the snapshot comprising both metadata and data having updated the destination logical drive with its contents is no longer required and can be deleted. The snapshot taken at time Tcomprising only metadata remains. The method now proceeds to step .

By keeping the snapshot running after the duplication operation has finished a record can be kept of any changes made to the data on the source logical drive since time T i.e. the time at which the earlier duplication operation was started . The changes to the data may comprise write requests which overwrite data previously stored at a particular data area deletions or newly added data. For each incoming write request addressed to a data area on the source logical drive metadata see relating to the changed data at that particular data area will be stored in the snapshot .

Since the snapshot only records metadata relating to the data which has changed then the snapshot will neither take up excessive storage space nor be resource intensive to update.

At step it is determined whether a request for a further duplication has been received. This may be specified by a user or may be predetermined to occur automatically a set interval.

If no duplication is required then the method proceeds back to step and continues to track the changes made to the source logical drive .

If a further duplication is required to bring the destination logical drive back into synchronisation with the source logical drive then the method proceeds to step .

In step a further duplication is initialised at a time Twhich is later than time T. In other words the further duplication or resynchronisation is started at time T. When the further duplication is complete the destination logical drive will comprise a copy of the source logical drive at time Twhen the further duplication process was started.

This step may simply be a reference point identifying when the duplication was started and need not require any actions to be carried out. Alternatively additional steps may be carried out as appropriate prior to copying of data from the source logical drive for example logging the time at which the duplication was started or initialising required programs. The skilled person will be readily aware that this step could be implemented in a variety of suitable approaches and arrangements.

Two further snapshot are taken at time Twhen the further duplication or resynchronisation is initialised. A snapshot is created which stores both metadata and copy on write data. The snapshot ensures that any writes issued to the source logical drive during the duplication process do not affect the copy of the data copied to the destination logical drive and that the destination logical drive comprises at the end of the copy process an identical copy of the source logical drive at time T.

Another snapshot is created which stores only metadata relating to data which has changed since time T.

At step the data from the snapshot is read. This is the first part of the copy process the read data is then written to the destination logical drive in step to complete the copy process.

However there is no need to copy data from the source logical drive which has not changed since the earlier duplication process occurred at time T. Therefore the copy engine refers to the snapshot which has been running since time T to indicate which data areas or blocks have been changed since the previous duplication at time T.

In other words the snapshot contains metadata referring to only the data areas on the source logical drive which have been modified changed written to deleted or added to between times Tand T.

The snapshot enables the data configuration on the source logical drive to be effectively frozen at time T. Therefore the snapshot does not comprise any data corresponding to activity occurring on the source logical drive after time T. Any incoming writes to the source logical drive will be subject to a copy on write operation i.e. the original data at the write requested data area will be copied to the resynchronisation snapshot data area prior to the write being allowed.

At step the data read in step is copied to the destination logical drive . The data written to the destination logical drive is data which has changed in between times Tand T. The written data area on the destination logical drive now corresponds to that on the source logical drive at time T. The method then proceeds to step .

Throughout the resynchronisation process it is determined whether all of the data on the source logical drive which has changed between times Tand Thas been copied to the destination logical drive . If the determination is positive then the method proceeds to step . If however it is determined that with reference to the snapshot there is still data to be copied from the source logical drive to the destination logical drive then the method proceeds to step .

At step similarly to steps and described previously it is determined whether the host has issued a write request to a data on the source logical drive since the resynchronisation process was initiated at time T step .

If it determined that a write request to a data area e.g. a logical block on the source logical drive is detected then the method proceeds to step . If no write request to the source logical drive is detected then the method proceeds to step .

If at step a write request to a data area is detected then the original data on that particular data area on the source logical drive is copied in a copy operation to the snapshot on the snapshot logical drive prior to the write request being allowed. This is known as copy on write . This preserves the original data in the snapshot data area so that the resynchronisation snapshot is representative of the data on the source logical drive at time Twhen the resynchronisation operation is initiated. The method then proceeds to step .

Once the original data in the write requested data area e.g. a particular logical block has been copied to the snapshot logical drive then that particular data area is now recorded safely and the write request to that particular data area can be allowed.

At step the resynchronisation process proceeds. In this example at step the resynchronisation process moves to the next data area to be copied as specified by the snapshot which comprises a record of which data areas have been changed or modified between times Tand T.

The method then proceeds back to step wherein the identified data is read and then at step written to the destination logical drive to complete the copy process for that particular data area.

This process continues until it is determined at step that all data areas which have been changed between times Tand Thave been copied from the source logical drive to the destination logical drive .

At step the destination logical drive now contains an exact copy of the data on the source logical drive at time T i.e. the moment the resynchronisation process was initialised at step . The method then proceeds to step .

Once the duplication has completed there is no longer any need to keep the snapshot which specifies changes made between times Tand T and so the snapshot can be deleted. This is because the snapshot can provide a complete record of changes made to the data on the source logical drive after time T. At this time the snapshot is no longer required and this can be deleted also.

Should a further resynchronisation of the destination logical drive to the source logical drive be required at a later time i.e. later than time T then a further resynchronisation snapshot can be taken at a time Tand the earlier snapshot taken at time T can be used to direct the copy process to the data areas which have changed in between times Tand T.

Variations of the above embodiments will be apparent to the skilled person. The precise configuration of hardware and software components may differ and still fall within the scope of the present invention.

For example whilst the above examples have been shown and described with reference to a RAID arrangement this need not be so. Any suitable arrangement of physical drives or logical drive managers could be used. For example a single physical drive could be represented by a single logical drive.

Embodiments of the present invention have been described with particular reference to the examples illustrated. While specific examples are shown in the drawings and are herein described in detail it should be understood however that the drawings and detailed description are not intended to limit the invention to the particular form disclosed. It will be appreciated that variations and modifications may be made to the examples described within the scope of the present invention.

