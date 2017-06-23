---

title: Detection and correction of silent data corruption
abstract: There is provided a method of writing data to a sector of a storage device, the sector comprising a data field and a protection information field and having identifying information identifying the location of said sector. The method comprises providing data to be written to an intended sector, generating, for said intended sector, a message comprising the data and the identifying information of said intended sector and performing, on said message, error correcting encoding to generate a codeword. The codeword comprises the message and parity information generated from said error correcting coding. The data can then be written to the data field of the sector, and the parity information can be written to said protection information field of the sector.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09009569&OS=09009569&RS=09009569
owner: Xyratex Technology Limited
number: 09009569
owner_city: Havant, Hampshire
owner_country: GB
publication_date: 20101018
---
The present invention relates to a method of and apparatus for detection and correction of silent data corruption.

Data integrity is a core requirement for a reliable storage system. The ability to prevent and if necessary identify and correct data errors and corruptions is essential for operation of storage systems ranging from a simple hard disk drive up to large mainframe storage arrays.

A typical hard disk drive comprises a number of addressable units known as sectors. A sector is the smallest externally addressable portion of a hard disk drive. Each sector typically comprises 512 bytes of usable data. However recent developments under the general term advanced format sectors enable support of sector sizes up to 4 k bytes. When data is written to a hard disk drive it is usually written as a block of data which comprises a plurality of contiguous sectors.

A hard disk drive is an electro mechanical device which may be prone to errors and or damage. Therefore it is important to detect and correct errors which occur on the hard disk drive during use. Commonly hard disk drives set aside a portion of the available storage in each sector for the storage of error correcting codes ECCs . This data is also known as protection information. The ECC can be used to detect corrupted or damaged data and in many cases such errors are recoverable through use of the ECC. However for many cases such as enterprise storage architectures the risks of such errors occurring are required to be reduced further.

One approach to improve the reliability of a hard disk drive storage system is to employ redundant arrays of inexpensive disk RAID . Indeed RAID arrays are the primary storage architecture for large networked computer storage systems.

The RAID architecture was first disclosed in A Case for Redundant Arrays of Inexpensive Disks RAID Patterson Gibson and Katz University of California Berkeley . RAID architecture combines multiple small inexpensive disk drives into an array of disk drives that yields performance exceeding that of a single large drive.

There are a number of different RAID architectures designated as RAID 1 through RAID 6. Each architecture offers disk fault tolerance and offers different trade offs in terms of features and performance. In addition to the different architectures a non redundant array of disk drives is referred to as a RAID 0 array. RAID controllers provide data integrity through redundant data mechanisms high speed through streamlined algorithms and accessibility to stored data for users and administrators.

RAID architecture provides data redundancy in two basic forms mirroring RAID 1 and parity RAID 3 4 5 and 6 . The implementation of mirroring in RAID 1 architectures involves creating an identical image of the data on a primary disk on a secondary disk. The contents of the primary and secondary disks in the array are identical. RAID 1 architecture requires at least two drives and has increased reliability when compared to a single disk. Since each disk contains a complete copy of the data and can be independently addressed reliability is increased by a factor equal to the power of the number of independent mirrored disks i.e. in a two disk arrangement reliability is increased by a factor of four.

RAID 3 4 5 or 6 architectures generally utilise three or more disks of identical capacity. In these architectures two or more of the disks are utilised for reading writing of data and one or more of the disks store parity information. Data interleaving across the disks is usually in the form of data striping in which the data to be stored is broken down into blocks called stripe units . The stripe units are then distributed across the disks.

Therefore should one of the disks in a RAID group fail or become corrupted the missing data can be recreated from the data on the other disks. The data may be reconstructed through the use of the redundant stripe units stored on the remaining disks. However RAID architectures utilising parity configurations need to generate and write parity information during a write operation. This may reduce the performance of the system.

However even in a multiple redundant system such as a RAID array certain types of errors and corruptions cannot be detected or reported by the RAID hardware and associated controllers. This class of errors is known as silent data corruption.

A number of errors and corruptions fall into the category of silent data corruption. One such error is a misdirected write. This is a situation where a block of data which is supposed to be written to a first location is actually written to a second incorrect location. In this case the system will not return a disk error because there has not technically been any corruption or hard drive error. However on a data integrity level the data at the second location has been overwritten and lost and old data is still present at the first location. These errors remain undetected by the RAID system.

A misdirected read can also cause corruptions. A misdirected read is where data intended to be read from a first location is actually read from a second location. In this situation parity corruption can occur due to read modify write RMW operations. Consequently missing drive data may be rebuilt incorrectly.

A further silent data corruption which can occur is a torn write. This situation occurs where only a part of a block of data intended to be written to a particular location is actually written. Therefore the data location comprises part of the new data and part of the old data. Such a corruption is again not detected by the RAID system.

Additionally data is not always protected by ECC or CRC cyclic redundancy check systems. Therefore such data can become corrupted when being passed from hardware such as the memory and central processing unit CPU via hardware adapters and RAID controllers. Again such an error will not be flagged by the RAID system.

When silent data corruption has occurred in a RAID system a further problem of parity pollution may occur. This is when parity information is calculated from unknowingly corrupt data. In this case the parity cannot be used to correct the corruption and restore the original non corrupt data.

Certain RAID systems for example RAID 6 systems can be configured to detect and correct such errors. However in order to do this a full stripe read is required for each sub stripe access. This requires significant system resources and time.

Therefore known storage systems suffer from a technical problem that silent data corruptions cannot be detected reliably and without placing excessive demands on system resources. There also exists a need to provide a method and system which is able to correct user data that is not protected by ECC for all RAID levels with requiring a full stripe read and which enables misdirected write to be detected and corrected.

According to a first aspect of the present invention there is provided a method of writing data to a sector of a storage device the sector comprising a data field and a protection information field and having identifying information identifying the location of said sector the method comprising providing data to be written to an intended sector generating for said intended sector a message comprising the data and the identifying information of said intended sector performing on said message error correcting encoding to generate a codeword said codeword comprising said message and parity information generated from said error correcting coding writing said data to the data field of the sector and writing said parity information to said protection information field of the sector.

By providing such a method parity information can be generated from a message comprising both actual user data and the intended destination address of that data. Consequently should the data then subsequently be sent to the wrong address when the data is read the parity information will show that the data is in the incorrect location.

In one arrangement said identifying information comprises a device identifier address and a sector logical address.

In a variation the codeword comprises a plurality of symbols relating to user data a plurality of symbols relating to identifying information of said intended sector and a plurality of symbols relating to parity information.

In a variation said codeword comprises N bit symbols where N is greater than 8. In a further variation said codeword comprises 9 bit symbols.

According to a second aspect of the present invention there is provided a method of reading data from a sector of a storage device the sector comprising a data field and a protection information field and having identifying information identifying the location of said sector the method comprising executing a read request for reading of data from a sector having specified identifying information reading data from the data field of said sector generating a message comprising said data and the identifying information of said read sector reading parity information from the protection information field of said sector generating a codeword comprising said message and parity information performing on said codeword error correcting decoding such that said codeword is checked for errors.

In one embodiment said identifying information comprises a device identifier address and a sector logical address.

In one embodiment wherein the codeword comprises a plurality of symbols relating to user data a plurality of symbols relating to identifying information of said intended sector and a plurality of symbols relating to parity information.

In a variation said codeword comprises N bit symbols where N is greater than 8. In a further variation said codeword comprises 9 bit symbols.

In one embodiment if at said step of decoding one or more errors in the data field of said message is detected the method further comprises correcting said data in said data field of said sector.

In one embodiment if at said step of decoding one or more errors in the identifying information of said message is detected the method further comprises correcting said identifying information and writing said data in said data field of said sector having said correct identifying information.

According to a third aspect of the invention there is provided a controller operable to writing data to a sector of a storage device the sector comprising a data field and a protection information field and having identifying information identifying the location of said sector the controller being further operable to provide data to be written to an intended sector generate for said intended sector a message comprising the data and the identifying information of said intended sector perform on said message error correcting encoding to generate a codeword said codeword comprising said message and parity information generated from said error correcting coding write said data to the data field of the sector and write said parity information to said protection information field of the sector.

In one embodiment said identifying information comprises a device identifier address and a sector logical address.

In one embodiment the codeword comprises a plurality of symbols relating to user data a plurality of symbols relating to identifying information of said intended sector and a plurality of symbols relating to parity information.

In a variation said codeword comprises N bit symbols where N is greater than 8. In a further variation said codeword comprises 9 bit symbols.

According to a fourth aspect of the present invention there is provided a controller operable to read data from a sector of a storage device the sector comprising a data field and a protection information field and having identifying information identifying the location of said sector the controller being further operable to execute a read request for reading of data from a sector having specified identifying information read data from the data field of said sector generate a message comprising said data and the identifying information of said read sector read parity information from the protection information field of said sector generate a codeword comprising said message and parity information perform on said codeword error correcting decoding and check said codeword for errors.

In one embodiment said identifying information comprises a device identifier address and a sector logical address.

In one embodiment the codeword comprises a plurality of symbols relating to user data a plurality of symbols relating to identifying information of said intended sector and a plurality of symbols relating to parity information.

In a variation said codeword comprises N bit symbols where N is greater than 8. In a further variation said codeword comprises 9 bit symbols.

In one embodiment the controller is further operable to correct said data in said data field of said sector if one or more errors in the data field of said message is detected.

In one embodiment the controller is further operable to correct said identifying information and write said data in said data field of said sector having said correct identifying information if one or more errors in the identifying information of said message is detected.

According to a fifth aspect of the invention there is provided a data storage apparatus comprising at least one storage device and the controller of the third or fourth aspects.

According to a sixth aspect of the present invention there is provided a computer program product executable by a programmable processing apparatus comprising one or more software portions for performing the steps of the first and or second aspects.

According to a seventh aspect of the present invention there is provided a computer usable storage medium having a computer program product according to the sixth aspect stored thereon.

The hosts are connected to a first communication network which couples the hosts to a plurality of RAID controllers . The communication network may take any suitable form and may comprise any form of electronic network that uses a communication protocol for example a local network such as a LAN or Ethernet or any other suitable network such as a mobile network or the interne.

The RAID controllers are connected through device ports not shown to a second communication network which is also connected to a plurality of storage devices . The RAID controllers may comprise any storage controller devices that process commands from the hosts and based on those commands control the storage devices . RAID architecture combines a multiplicity of small inexpensive disk drives into an array of disk drives that yields performance that can exceed that of a single large drive. This arrangement enables high speed access because different parts of a file can be read from different devices simultaneously improving access speed and bandwidth. Additionally each storage device comprising a RAID array of devices appears to the hosts as a single logical storage unit LSU or drive.

The operation of the RAID controllers may be set at the Application Programming Interface API level. Typically Original Equipment Manufactures OEMs provide RAID networks to end users for network storage. OEMs generally customise a RAID network and tune the network performance through an API.

Any number of RAID controllers may be provided and N RAID controllers where N is an integer are shown in . Any number of storage devices may be provided in N storage devices are shown where N is any integer value.

The second communication network may comprise any suitable type of storage controller network which is able to connect the RAID controllers to the storage devices . The second communication network may take the form of for example a SCSI network an iSCSI network or fibre channel.

The storage devices may take any suitable form for example tape drives disk drives non volatile memory or solid state devices. Although most RAID architectures use hard disk drives as the main storage devices it will be clear to the person skilled in the art that the embodiments described herein apply to any type of suitable storage device. More than one drive may form a storage device for example a RAID array of drives may form a single storage device . The skilled person will be readily aware that the above features of the present embodiment could be implemented in a variety of suitable configurations and arrangements.

The RAID controllers and storage devices also provide data redundancy. The RAID controllers provide data integrity through a built in redundancy which includes data mirroring. The RAID controllers are arranged such that should one of the drives in a group forming a RAID array fail or become corrupted the missing data can be recreated from the data on the other drives. The data may be reconstructed through the use of data mirroring. In the case of a disk rebuild operation this data is written to a new replacement drive that is designated by the respective RAID controller .

The host is connected to the RAID controller through a communication network such as an Ethernet and the RAID controller is in turn connected to the storage devices via a storage network such as an iSCSI network.

The host comprises a general purpose computer PC which is operated by a user and which has access to the storage resource . A graphical user interface GUI is run on the host . The GUI is a software application which acts as a user interface for a user of the host .

The RAID controller comprises a software application layer an operating system and RAID controller hardware . The software application layer comprises software applications including the algorithms and logic necessary for the initialisation and run time operation of the RAID controller . The software application layer includes software functional blocks such as a system manager for fault management task scheduling and power management. The software application layer also receives commands from the host e.g. assigning new volumes read write commands and executes those commands. Commands that cannot be processed because of lack of space available for example are returned as error messages to the user of the host .

The operating system utilises an industry standard software platform such as for example Linux upon which the software applications forming part of the software application layer can run. The operating system comprises a file system which enables the RAID controller to store and transfer files and interprets the data stored on the primary and secondary drives into for example files and directories for use by the operating system .

The RAID controller hardware is the physical processor platform of the RAID controller that executes the software applications in the software application layer . The RAID controller hardware comprises a microprocessor memory and all other electronic devices necessary for RAID control of the storage devices 

The storage devices forming the RAID 6 array are shown in more detail in . Each storage device comprises a hard disk drive generally of high capacity for example 1 TB. Each device can be accessed by the host through the RAID controller to read write data.

As shown in data is stored on the RAID 6 array in the form of stripe units. Each data stripe A B comprises five separate stripe units stripe A comprises stripes A A A Aand A. Stripe B comprises stripe units B B B Band B. Therefore the stripe units comprising each stripe A A or B B respectively are distributed across a plurality of disk drives together with parity information Aand Aand Band Brespectively. This provides data redundancy.

The following embodiment of the invention may be utilised with the above RAID arrangement. In the following description for brevity a single storage device will be referred to. However the embodiment of the invention is equally applicable to other arrangements for example the storage device may be a logical drive or may be a single hard disk drive.

As set out above the term storage device in the context of the following description may refer to a logical drive which is formed on the RAID array . In this case a sector refers to a portion of the logical drive created on the RAID array . The following embodiment of the present invention is applicable to any of the above described arrangements.

In this embodiment the storage device is formatted such that each sector comprises 520 bytes 4160 bits . The data field in this embodiment is 512 bytes 4096 bits long and the protection information field is 8 bytes 64 bits long.

The term sector used herein whilst described in an embodiment with particular reference to 520 byte sector sizes is generally applicable to any sector sizes. Therefore the term sector is merely intended to indicate a portion of the storage availability on a storage device and is not intended to be limited to any of the disclosed examples. Additionally sector may be used to refer to a portion of a logical drive i.e. a virtual drive created from a plurality of physical hard drives linked together in a RAID configuration.

The data field comprises user data to be stored on the storage device . This data may take any suitable form and as described with reference to may be divided into a plurality of stripe units spread across a plurality of storage devices . However for clarity the following description will focus on the data stored on a single storage device .

In a conventional storage device the protection information field may comprise ECC CRC or parity bits. However in the present invention the protection information to be stored in the protection information field relates to the actual data stored in the data field together with location information specifying the correct location of that data i.e. which sector and on which storage device the data is or should be stored.

The protection information in the protection information field is generated in the following way. The following discussion will focus on a single storage device . However the skilled person would readily appreciate that the system method and apparatus described below could be applied to a RAID array comprising data stripes or any other type of distributed storage system.

A write request from the host specifies both the data to be written to the data field of one or more sectors plus routing or identifying information specifying the location of the one or more sectors . Each storage device in the storage resource is assigned a device target identifier T. This identifier may comprise any suitable form and identifies the hard disk drive in question.

For instance non exhaustive examples of suitable device target identifiers may be a hash of the SAS address WWN serial number a combination of the array identifier and member index or an enumerated value assigned to the disk by software. In the present embodiment the device target identifier Tcomprises an 18 bit device identifier.

Each sector is also assigned a logical address identifier T. This identifier may comprise any suitable form. For instance non exhaustive examples of suitable formats may be the S least significant bits the S most significant bits of the logical address of sector to partition all the LBAs into 2regions and assign the logical address identifier be the LBA region number. In the present embodiment the logical address identifier Tcomprises an 18 bit address identifier.

Together the device target identifier Tand logical address identifier Tcomprise target identifying information T which identifies the sector to which data is to be written.

To generate parity information for the protection information field the RAID controller is configured to generate a message from the data and the identifying information T directed to sector . The format of the message is shown in .

As shown in the message comprises the user data intended to be written to a particular sector having identifying information T comprising device target identifier Tand logical address identifier T . Therefore message comprises M bits where M is equal to the number of bits D of user data and the number of bits T of identifying information T or M D T. Since T 36 bits and D 4096 bits M 4132 bits in this embodiment.

For each sector the RAID controller is arranged to generate a codeword from the respective message . The codeword is shown in and comprises user data identifying information T and parity information .

In other words the codeword comprises the message including the user data and identifying information T comprising device target identifier Tand logical address identifier T plus parity information generated from the message .

The parity information is generated by use of an error correcting code ECC . Any suitable error correcting code may be used provided that it meets certain criteria. Firstly the ECC scheme must be systematic i.e. it must not modify the message . Secondly the scheme must produce p bits of parity information also known as redundant information or checksum data where p must not be greater than the number of bits available in the protection information field of a sector .

The codeword is generated through use of Reed Solomon coding applied to the message . Reed Solomon codes are non binary cyclic codes with symbols made up of m bit symbols where m is any positive integer having a value greater than 2 . Reed Solomon code on m bit symbols exist for all n and k for which 022 1 

where k is the number of data symbols being encoded and n is the total number of code symbols in the codeword i.e. k p i.e. the message plus parity information . The codeword is the combination of message and parity symbols together.

As a further parameter t is the symbol error correcting capability of the code and for a conventional Reed Solomon code 

As an example RAID 6 provides an instance of Reed Solomon coding where the symbol size m 8 bits. This value is chosen because a byte is 8 bits. In the RAID 6 arrangement k corresponds to the number of data drives and the number of parity symbols p 2. All of the bytes at the same offset within each drive of an array is equivalent to the codeword.

Since bytes are 8 bits long it is naturally desirable to set the symbol size to 8 bits so that each byte is one symbol. However a codeword so generated is limited in size to 255 symbols. However the data to be written to the data area of a sector already contains 512 bytes of user data so there is insufficient room to include the 36 bits of identifying information T.

Consequently in this embodiment a larger symbol size is used and the user data is organised into groups of 9 bit symbols i.e. m 9 . Given a 9 bit symbol the codeword size can be as large as 2 1. Therefore the codeword may comprise 511 symbols.

As discussed the user data has a size of 512 bytes 4096 bits . In order to make this data fit the 9 bit symbol scheme the user data is padded with 8 bits of zero data to provide a total user data volume of 4104 bits. This number of bits is evenly divisible by 9.

Consequently the number of symbols of user data is 456 i.e. 4104 bits 9. Since this is less than the maximum available 511 symbols the use of 9 bit symbols enables all the user data intended to be written to a sector together with the identifying information T comprising 36 bits and generated parity information to be provided in a single codeword .

A codeword thus generated is shown schematically in . Each symbol 0 464 comprises 9 bits of data. Symbols 0 to 454 comprise sequential blocks of 9 bits of the data to be written to the data area of a sector . Symbol 455 comprises the final bit bit 4096 of the data together with the 8 zero bits provided to pad the data . Therefore symbols 0 to 455 comprise the entirety of the bits of the data to be written to a single sector.

Symbols 456 and 457 contain the target drive identifier Tforming part of the identifying information T. Symbols 458 and 459 comprise the address identifier Tof the sector forming the other part of the identifying information T.

Finally symbols 460 to 464 comprise the generated parity information generated through the use of the Reed Solomon code.

Once the codeword has been generated the RAID controller is configured to write data held in symbols 0 to 455 to the data field of the respective sector . Further the parity information generated by Reed Solomon encoding is written into the protection information field of the sector . This is shown in .

Since the parity information is in the form of five 9 bit symbols 45 bits in total this can easily be saved into 6 bytes 48 bits of the available 8 bytes of the protection information field . This is particularly advantageous since this approach enables the T10 data integrity field DIF format to be supported on the side of the host of the RAID controller .

The American National Standards Institute s ANSI T10 DIF specification calls for data to be written in blocks of 520 bytes. As part of this protocol it is necessary to save two bytes of the protection information field in order to store the T10 DIF application tag which is required to be written to each sector . The remaining six bytes are used to store parity generated by Reed Solomon encoding of the user data and routing information.

The identifying information T is not required because the routing information is known to the RAID controller firmware and does not need to be copied to the sector data area.

The operation of a method according to the present invention will now be described with reference to .

At step the host generates a write request for a specific volume e.g. storage device to which it has been assigned access rights. The request is sent via communication network to the host ports not shown of the RAID controller . The write command is then stored in a local cache not shown forming part of the RAID controller hardware of the RAID controller .

The RAID controller is programmed to respond to any commands that request write access to the storage device . The RAID controller processes the write request from the host and determines the target identifying address T of the sector to which it is intended to write that data to. The target identifying address T comprises the device target identifier T which in this embodiment is 18 bytes in length and the sector logical address identifier T which is also 18 bytes in length in this embodiment .

In summary the device target identifier Tidentifies the particular storage device amongst all the storage devices and the sector logical address identifier Tidentifies the pertinent sector amongst all of the sectors forming the usable capacity of the storage device . The method then proceeds to step .

A message is then generated. The format of the message is shown in and comprises the user data intended to be written to a particular sector having identifying information T comprising device target identifier Tand logical address identifier T .

Therefore message comprises M bits where M is equal to the number of bits D of user data and the number of bits T of identifying information T or M D T. Since T 36 bits and D 4096 bits M 4132 bits in this embodiment.

For each sector the RAID controller utilises the message to generate a codeword . The codeword is shown in and comprises user data identifying information T and parity information .

In other words the codeword comprises the message including the user data and identifying information T comprising device target identifier Tand logical address identifier T plus parity information generated from the message .

The RAID controller utilises a Reed Solomon code is used to generate the parity information . The user data is organised into groups of 9 bit symbols. Since the user data has a size of 512 bytes 4096 bits the user data is padded with 8 bits of zero data to provide a total user data volume of 4104 bits which is split into 456 symbols. Another four symbols are used to store the target drive identifier Tand the address identifier Tforming the identifying information T.

From the user data and identifying information T the RAID controller generates parity information through the use of the Reed Solomon code. Once the codeword has been generated the method proceeds to step .

The data area comprises 512 bytes or 4096 bits. The bits of data comprising part of the codeword in 9 bit format symbol format are written to the data area of the sector . The eight zero values entered as padding are ignored and not written to the data area since these values do not comprise part of the original data .

The parity information generated in step is then written to the protection information field of the sector .

The protection information field comprises 8 bytes 64 bits of available space for the parity information . The parity information generated in step comprises 5 symbols of 9 bits each a total of 45 bits. Consequently the parity information can be written to the protection information field comfortably within 6 bytes. The remaining two bytes may optionally be reserved for a T10 DIF application tag assigned to each sector .

At step the writing of the data together with parity information is complete. The method may then proceed back to step for further sectors or may terminate.

At step the host generates a read request for the primary storage device to which it has been assigned access rights. The request is sent via the communication network to the host ports not shown of the RAID controller . The read command is then stored in a local cache not shown forming part of the RAID controller hardware of the RAID controller .

The RAID controller is programmed to respond to any commands that request read access to the storage device . The RAID controller processes the read request from the host and determines the sector s of the storage device in which the data is stored. The method then proceeds to step .

At step a message is generated. The message is shown in . The message is similar in composition to the message described previously. However the message is constructed from the existing stored data retrieved from the data area of the sector in question together with identifying information i.e. target device identifier Tconcatenated with the logical address identifier T supplied by the RAID controller in response to the read direction determined in step . Once the message is constructed the method proceeds to step .

For each sector to be read the RAID controller utilises the message to generate a codeword . The codeword is shown in and is similar in format to the codeword described previously.

The codeword comprises the message generated in step together with the parity information retrieved from the protection information field of the sector . Therefore the codeword comprises the user data read from the data area of the sector together with identifying information T comprising device target identifier Tand logical address identifier T forming part of the read request and the parity information written to the sector in step .

In step the RAID controller decodes the codeword using the ECC scheme in this embodiment Reed Solomon coding . The codeword is checked for consistency.

If no decode error is detected following the decoding at step the user data is assumed to be correct and in the correct location.

Alternatively if an error is detected the sector is first read again to ensure the error is not transient. If the error is not transient the method proceeds to step .

If at the error checking step a correctable error in the data or the parity information portions of the codeword is detected the data stored in the sector in question can be updated with the correct information.

However if the error checking step detects a correctable error in the identification information portion T of the message a mis direction has occurred. In this instance the error correction coding in this embodiment Reed Solomon coding can correct the codeword .

From the corrected codeword the RAID controller software or firmware can determine where the previously misdirected write was intended to go. The RAID controller firmware or software then re submits the previously misdirected write to the correct location.

As an example based on the described embodiment the Reed Solomon decoding will correct the message and identify where the original write was intended to go. For example take the situation the write request was targeted at a physical drive having ID 0x1234 but instead was misdirected to target physical drive having ID 0x5555.

When the sector on physical drive ID 0x5555 is read the codeword will be decoded and determined to be corrupt. Consequently the identifying information T will be corrected to refer to the correct physical drive having ID 0x1234. The user data is then written to the correct drive whose ID is 0x1234 and the drive whose ID is 0x5555 can be rebuilt.

Additional corrective actions may also be taken. For example the chunk where data corruption occurred due to misdirection can be rebuilt. Alternatively in the case of a RAID array data can be synchronised with parity for all stripe units affected by the identified misdirection. As a further step all stripe units in the target address region of the affected drive affected by the misdirection can be verified.

Variations of the above embodiments will be apparent to the skilled person. The precise configuration of hardware and software components may differ and still fall within the scope of the present invention.

For example the present invention has been described with reference to controllers in hardware. However the controllers and or the invention may be implemented in software. This can be done with a dedicated core in a multi core system. Given a proper software algorithm it should be feasible to calculate protection information in parallel with array parity so that each piece of user data is read only once.

Additionally whilst the present embodiment relates to arrangements operating predominantly in off host firmware or software e.g. on the RAID controller an on host arrangement could be used.

Further alternative ECC methods could be used. The skilled person would be readily aware of variations which fall within the scope of the appended claims.

Alternatively if Reed Solomon coding is used symbols other than 9 bit symbols could be used. The skilled person would be readily aware of the different symbol sizes that could be used with the present invention. For example symbols having greater than 8 bits would be suitable for use with the present invention.

Embodiments of the present invention have been described with particular reference to the examples illustrated. While specific examples are shown in the drawings and are herein described in detail it should be understood however that the drawings and detailed description are not intended to limit the invention to the particular form disclosed. It will be appreciated that variations and modifications may be made to the examples described within the scope of the present invention.

