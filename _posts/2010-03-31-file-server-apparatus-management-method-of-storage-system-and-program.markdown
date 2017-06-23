---

title: File server apparatus, management method of storage system, and program
abstract: When a storage capacity of a file server is expanded using an online storage service, elimination of an upper-limit constraint of the file size as a constraint of the online storage service and reduction in the communication cost are realized. A kernel module including logical volumes on the online storage service divides a file into block files at a fixed length and stores and manages the block files to prevent the upper-limit constraint of the file size. When a READ/WRITE request is generated for a mounted file system, only necessary block files are downloaded and used from the online storage service based on an offset value and size information to optimize the communication and realize the communication cost reduction.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08595440&OS=08595440&RS=08595440
owner: Hitachi Solutions, Ltd.
number: 08595440
owner_city: Tokyo
owner_country: JP
publication_date: 20100331
---
The present invention relates to a file server apparatus a management method of a storage system and a program and for example relates to a technique for acquiring a file stored in an external storage service to provide the file to a user terminal.

A new IT application called cloud computing is drawing attention as a big flow of IT trend of recent years. STaaS Storage as a service as an example of the IT application which provides a storage service via the Internet is proliferating. The STaaS is a service of providing a logical storage capacity at a low price and the STaaS generally provides an external interface for using the storage service in a Web interface format such as REST and SOAP. Although problems such as security and compliance remain in the STaaS the cost reduction is prioritized and the use of the STaaS by individuals and companies is expected to increase in the future.

In general the online storage service features an enormous scalability but there is an upper limit to the file size that can be stored. For example in the case of Amazon registered trademark S3 although there is no limit to the number of file objects that can be stored in the bucket the maximum size of the file object is 5 GB and a single file in a size greater than 5 GB cannot be stored constraint condition 1 . As for file reading a partial reading process can be executed. However as for writing partial writing cannot be performed and only the replacement of the file stored in the bucket is possible constraint condition 2 . For example to rewrite a 1 MB block in a 5 GB file all the 5 GB file needs to be downloaded to rewrite the 1 MB block and the entire 5 GB file needs to be uploaded at the end. There is a problem that the communication cost increases. Therefore there is a problem that data communication of an unnecessary part is generated in a Random READ WRITE process and the communication cost increases. The data is accessed via a WAN and the communication speed is significantly slower than the data communication speed to a local disk or the like. There is a problem that the overhead of file listing or READ WRITE increases in a synchronous communication.

To use the online storage service as a backup external storage of a file server or an external storage for capacity expansion a mechanism is necessary in which the file server looks like a transparently single file server from the client and the online storage service is connected from the file server to copy or move data. For example Patent Literature 1 discloses an existing technique of transparently showing the file server as a single server to the client and concealing the data copy and movement. Patent Literature 2 discloses an existing technique related to the data copy and movement.

In Patent Literature 1 an intermediate apparatus is arranged between a first server including a primary storage a second server including a secondary storage and the client. When there is a file access to the primary storage from the client the access request is changed to a corresponding file on the secondary storage if the access target file is a stub file file for linking the destination . In this way it looks as if the stub file is an entity and the data movement from the primary storage to the secondary storage is concealed from the client.

In Patent Literature 2 updates of high speed disk volumes are monitored to create update bit maps OR of each update bit map is calculated to detect segments that are not updated for a predetermined time and the data is moved from the high speed disk volumes to low speed disk volumes movement between storage tires based on the detected segment information.

However in Patent Literatures 1 and 2 the online storage service cannot be used as a backup external storage of a file server or an external storage for capacity expansion while preventing the constraint conditions 1 and 2 of the online storage service. Patent Literatures 1 and 2 do not propose measures to prevent the constraints related to the file size on the online storage and do not propose measures to optimize the communication cost via the WAN.

The present invention has been made in view of the circumstances and the present invention provides a technique for optimizing the communication cost in using an online storage service and realizing a high speed access.

To solve the problems a block file group with divided file data and meta information are stored when a file is stored in an online storage service in the present invention and in response to a file read request from a user terminal a block file necessary in reading is downloaded from the online storage service and cached. In response to a write request from the user terminal a block file to be written is downloaded from the online storage service and cached and the cached write data is overwritten. The cached and changed block file and meta information are asynchronously reflected on the online storage service.

An online storage mount module refers to a meta information update flag a file update flag and a deletion flag recorded in the meta information and sequentially executes deletion of the original file in the online storage service file content and meta information in accordance with policy information not in synchronization with asynchronously the process of the file server

To process a write request from the user terminal the online storage mount module reflects identification information of the updated block file on bit map information recorded in the meta information and uses the bit map information to asynchronously update only block files that need to be uploaded to the online storage service in accordance with the policy information.

Further features of the present invention will become apparent from the embodiment for carrying out the present invention and the attached drawings.

According to the present invention the communication cost in using an online storage service can be optimized and a high speed access can be realized.

The present invention relates to for example a system of eliminating an upper limit constraint in the file size stored in an external storage service and reducing the communication cost. The present invention proposes a mechanism of dividing and managing individual files in an online storage service downloading and uploading only a necessary part in accordance with a READ WRITE operation of file eliminating the file size constraint of the online storage service and optimizing the communication cost. The present invention further provides a mechanism of locally caching the divided file blocks to speed up the file access storing meta information of the files on the online storage service in the file server changing file listing and the meta information such as file names and directory configurations and realizing high speed READ WRITE.

Hereinafter an embodiment of the present invention will be described with reference to the attached drawings. However the present embodiment is just an example for realizing the present invention and it should be noted that the present embodiment does not limit the technical scope of the present invention. Common configurations in the drawings are designated with the same reference numerals.

A file access occurs to the file server from the user terminal which is also connected. The intranet connects to the WAN via the gateway server and the online storage service operates beyond the WAN . The online storage service is a website that discloses and provides a storage service to the WAN through a Web interface and examples of the actual service include Amazon registered trademark S3 and Windows registered trademark Azure Storage.

The file server which is a file server such as NAS Network Attached Storage includes an NFS CIFS service module a management daemon a file system an online storage mount module and a secondary storage device including a local cache . The NFS CIFS service module the management daemon the file system and the online storage mount module may be realized as modules or may be constituted by programs and a process in the file server may realize the functions according to the programs. Although the local cache is arranged as an area for cache in the secondary storage device the mode is not limited to this and a memory for cache may be prepared separately from the secondary storage device .

The NFS CIFS service module is a basic module for receiving an access from the user terminal based on an NFS or CIFS protocol and for operation as a file server and Samba is an example of the NFS CIFS service module . When authentication of the user is required the NFS CIFS service module processes the authentication.

The online storage mount module is a module for providing a function of mounting a logical drive on the online storage service in the file server . The logical drive corresponds to a logical storage volume on the online storage service and is equivalent to for example a bucket in Amazon registered trademark S3. It is assumed in the following description that the service is Amazon registered trademark S3 the OS of the file server is Linux and the online storage mount module is a kernel module for example FUSE based file system module including the bucket. However the present invention is not limited by this.

The management daemon is a module for setting which bucket with whose account and where in the file server the online storage mount module will mount the bucket. The management daemon provides a setting GUI for example see . The manager can use the setting GUI displayed on a display screen of a manager terminal not shown to manage the online storage mount module .

The local cache is stored in the secondary storage device in the file server . The local cache is a file generated and managed by the online storage mount module and is a cache for speeding up the access to the file on the online storage service .

The following is a description of an operation summary of the file access. For example when the user terminal issues an I O request to a file the NFS CIFS service module provides the request to the file system . If the target file of the I O request is a file stored in the secondary storage device the file system acquires the target file from the secondary storage device and provides the file to the user terminal through the NFS CIFS service module . Meanwhile if the target file is in the local cache if the file is associated with Amazon registered trademark S3 and cached the file system acquires the target file through the online storage mount module and provides the file to the user terminal through the NFS CIFS service module . If the target file file associated with Amazon registered trademark S3 is not in the local cache either if the target file is in the online storage service the online storage mount module acquires mounts the target file from the online storage service stores the target file in the local cache and provides the target file to the file system . The file system then provides the file to the user terminal through the NFS CIFS service module .

The meta information is attribute information attached to each file and for example the meta information includes information such as file name and update date time see for details . The divided block file group is a set of block files that are formed by dividing the file main body at a fixed size.

Meanwhile the local cache in the file server includes cache file data equivalent to a set of cache files of a single file. The cache file data includes the meta information and a cache block file group . The cache block file group includes files downloaded from the divided block file group by the online storage mount module for a speed up process and is a subset of the divided block file group when a file update process is not generated. When the file update process is generated corresponding updated blocks are stored and the online storage mount module overwrites and updates corresponding files in the divided block file group in periodically executed update processes see .

In the actual cache data storage method in the file server one directory is prepared for each cache file data in the cache area of the file server and the meta information and the cache block file group are stored in the directory. The data is also stored in the same configuration one directory is prepared for one file on the online storage service .

The identification number is number information for uniquely identifying the file equivalent to the file data and is the only data that does not change even if the meta information such as the file name and the file path changes. The parent node identification number stores an identification number of a file corresponding to the parent directory of the file when a directory configuration is adopted.

The meta information update flag and the file update flag are flags set when the meta information and the file data of the files are updated and the flags are referenced in the periodical update processes. The flags indicate whether there is an update and for example 1 or 0 is stored. When a writing process is executed in the local cache there is a mismatch between the data on the local cache and the data on the online storage service . The flags are used to later reflect the mismatch caused by the update on the data in the online storage .

The deletion flag is a flag set when there is a deletion process of the file equivalent to the file data and the flag is also referenced in the update processes.

The bit map information is data for recording blocks in which update processes are generated among the locally cached block files and is used in a file update process.

The size on online storage is an attribute that stores the data size of the original file when the data is downloaded from the online storage and is used to delete an excess file in the update processes.

Lastly the Stat information stores file statistical information such as file size of the file block size and ACL.

The setting management screen includes a list control and buttons. The list control displays a list of set data including set buckets file paths on the file server that are mounted corresponding to the buckets and accounts .

The set data indicates a set of designated bucket names of Amazon registered trademark S3 file paths of mount destination folders in the file server and user account names of Amazon registered trademark S3 used for the mounting. When reading or writing of file is executed for a mounted folder a usage fee is generated for the user account of Amazon registered trademark S3 used for the mounting.

A new button an edit button and a delete button are arranged on the setting GUI and an entry can be newly generated edited and deleted. An OK button is pressed to confirm the setting content and a cancel button is pressed to cancel the setting content. As for the accounts a contract needs to be made and the accounts need to be created by Amazon registered trademark S3 in advance. Access ID Key and Secret Access Key that are issued for each account and that are necessary to access the Amazon registered trademark S3 service are encoded and stored in the file server.

First when the online storage mount module receives a file open request step the online storage mount module checks whether there is a cache block file group of files as the open request target in a cache area of the file server step .

If there is the cache area Yes in step the online storage mount module opens the folder that stores the cache block file group and returns the file identifier step .

On the other hand if the cache area does not exist No in step a folder that stores the meta information and the cache block file group is generated and the file identifier is returned.

When the online storage mount module receives a READ request step the online storage mount module calculates necessary divided blocks as destinations based on the offset information and the size information of the file designated in the READ request step .

The online storage mount module determines whether all divided block files necessary in providing the file are stored in the local cache step .

If all necessary divided block files are cached Yes in step the online storage mount module reads the data of necessary areas from the cached block files and generates a buffer memory device to be returned in the READ request step .

On the other hand if at least part of the necessary divided block files is not cached No in step the online storage mount module downloads the non cached divided block file from the online storage service to store the divided block file in the local cache step and forms a read buffer memory device to be returned in the READ request in the same way as when the files are cached step .

Lastly the online storage mount module returns the formed read buffer memory device to the higher control the file system to end the process step .

When the online storage mount module receives a WRITE request step the online storage mount module calculates necessary divided blocks from the offset information and the size information designated in the WRITE request step .

The online storage mount module then determines whether all necessary divided block files that cover write areas are stored in the local cache step .

If part of the block files is not cached No in step the online storage mount module downloads the file from the online storage service and stores the file in the local cache step .

If all necessary block files are cached Yes in step or after all necessary block files are cached by the process of step the online storage mount module overwrites a write buffer memory device in the WRITE request in necessary write areas for the cached block files step .

The online storage mount module sets corresponding bits in the bit map information to 1 in accordance with the updated block files to update the bit map information step .

When the online storage mount module receives a TRUNCATE request step the online storage mount module determines whether the request is an expansion request or reduction request of file based on the designated size information step .

If the request is an expansion request Yes in step the online storage mount module expands the bit map information data by the amount necessary for the size after the expansion of the file step and updates the file size information step .

On the other hand if the request is a reduction request No in step the online storage mount module reduces the bit map information data to a size equivalent to the size after the reduction of the file step and updates the file size information step .

Lastly the online storage mount module sets the meta information update flag and the file update flag to ON to end the process step .

When the file size is reduced there are divided block files not necessary in the reduction process and a process of deleting the files is not executed. This is to prevent the overhead of generating the divided block files again when an expansion process is generated after the reduction.

The online storage mount module first uses an asynchronous update thread to access the meta information of the files to check whether the deletion flag is ON step . If the deletion flag is ON Yes in step the online storage mount module deletes the target file on the online storage corresponding to the identifier step and ends the process.

When the deletion flag is OFF No in step the online storage mount module determines whether the file update flag is ON step .

When the file update flag is ON Yes in step the online storage mount module executes a file update process see for details step . If the file update flag is OFF the online storage mount module skips the file update process and moves the process to a determination process of the meta information update flag step .

If the meta information update flag is ON Yes in step the online storage mount module updates the meta information of the corresponding file on the online storage step . If the meta information update flag is OFF No in step the online storage mount module ends the process without executing anything.

The online storage mount module compares the current file size with the size of the original size on the online storage service that is stored in the meta information attribute of the file step .

The online storage mount module determines whether the file size is reduced at this time relative to the original file step . If the file size is not reduced No in step there are no excess files and the process moves to step .

If the file size is reduced Yes in step there are excess divided block files on the online storage service . Therefore the online storage mount module first deletes the files from the online storage service step .

If there are no updated block files No in step the online storage mount module ends the file update process. On the other hand if there are updated block files Yes in step the online storage mount module discriminates the updated block files based on the bit map information to upload the files to the online storage service step and ends the process.

In the present embodiment the online storage mount module directly performs the file deletion the information update and the like on the online storage in steps and the like. Alternatively the online storage mount module may instruct a processor not shown of the online storage service for the file update and the like through the Web interface and the processor of the online storage service may perform the actual file update and the like.

In the embodiment of the present invention the local cache of the file server stores K positive integer K

If all necessary divided blocks do not exist in the local cache the mount module accesses the online storage service to acquire insufficient divided blocks and stores the blocks in the local cache. In this way only necessary divided block files are downloaded and processed on demand in accordance with the request from the client and the communication cost can be reduced.

The local cache further stores the meta information of the original file along with the divided files. The meta information includes the file update flag indicating whether the original file is updated and the bit map information indicating the state of N divided files. If there is a write request from the user terminal and at least one of the K divided files stored in the local cache is updated the mount module sets the file update flag to ON and updates the bit map information corresponding to the updated divided file. The meta information further includes the meta information update flag indicating whether the meta information is updated and the file size information indicating the file size. If there is a file size change request TRUNCATE request and the target file is expanded or reduced by the file size change request the mount module applies an expansion process or a reduction process to the bit map information. The mount module updates the file size information and sets the meta information update flag to ON. In this way the original file on the online service and the meta information can be appropriately not in synchronous with the process in the file server updated. The meta information and the file are cached on the file server and the cache data is periodically and asynchronously uploaded to the online storage in the mechanism. As a result the meta information access of the file and the file access can be speeded up in the access to the online storage service via the WAN.

As described to speed up the file and meta information accesses the mechanism of caching the file and meta information on the online storage service in the file server is provided and the cached meta information and file in the file server are asynchronously uploaded to the online storage. Therefore a confirmation process of the update content to the online storage service is also realized in a format of a reduced load to the file server.

The present invention can also be realized by a program code of software for realizing the functions of the embodiment. In this case a storage medium recording the program code is provided to a system or an apparatus and a computer or CPU or MPU of the system or the apparatus reads out the program code stored in the storage medium. In this case the program code read out from the storage medium realizes the functions of the embodiment and the program code and the storage medium storing the program code constitute the present invention. Examples of the storage medium for supplying the program code include a flexible disk a CD ROM a DVD ROM a hard disk an optical disk a magneto optical disk a CD R a magnetic tape a nonvolatile memory card and a ROM.

An OS operating system and the like operating on a computer may execute part or all of the actual processes based on instructions of the program code and the processes may realize the functions of the embodiment. Furthermore after the program code read out from the storage medium is written in the memory on the computer a CPU or the like of the computer may execute part or all of the actual processes based on instructions of the program code and the processes may realize the functions of the embodiment.

The program code of the software for realizing the functions of the embodiment may be distributed via a network and the program code may be stored in a storage section such as a hard disk and a memory or a storage medium such as a CD RW and a CD R of the system or the apparatus. Upon the use the computer or CPU or MPU of the system or the apparatus may read out and execute the program code stored in the storage section or the storage medium.

