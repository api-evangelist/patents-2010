---

title: Method and apparatus for reprogramming applications in embedded devices
abstract: A method for uploading and storing application code in a re-writable, non-volatile memory of an electronic device is carried out by means of a bootloader. The bootloader receives the application code transmitted by a master unit through a communication channel, writes at least one portion of the application code to a portion of the non-volatile memory, and validates the at least one portion of the application code by means of the bootloader.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08612734&OS=08612734&RS=08612734
owner: Power-One Italy S.p.A.
number: 08612734
owner_city: Terranuova Bracciolini
owner_country: IT
publication_date: 20100405
---
A portion of the disclosure of this patent document contains material that is subject to copyright protection. The copyright owner has no objection to the reproduction of the patent document or the patent disclosure as it appears in the U.S. Patent and Trademark Office patent file or records but otherwise reserves all copyright rights whatsoever.

This application claims benefit of the following patent application which is hereby incorporated by reference PCT IT2007 000692 filed Oct. 3 2007.

The present invention relates to electronic devices in particular electronic embedded devices which may include a microcontroller and a nonvolatile memory storing software or application code i.e. firmware. More particularly the present invention relates to methods for programming or re programming firmware in electronic embedded devices such as power supply systems controllers sensors and other devices.

In the field of producing programming and installing embedded electronic devices it is well known that even after a test or production period a need can arise to re program the devices to update them to new functionalities or because of the presence of faults or failures not previously detected in the code.

The conventional re programming solution is to physically remove the board and to update the firmware by means of a conventional external programming device.

A bootloader is a software layer which manages the basic functions of the device to update the application code without using a programmer and without touching the device itself. Typically this operation is performed by using a communication channel e.g. RS232 RS485 12CBus SPI or USB. This procedure is carried out remotely. Furthermore it is necessary to consider that an embedded environment is typically an environment with few resources and that the bootloader must necessarily ha code.

In an embedded environment e.g. power supply systems controllers and sensors this software layer is used for reprogramming the firmware with no need to shut down the machine to remove the board from its support or to disconnect it from one or more parts of the device. In this manner savings can be obtained in a variety of ways including the following 

2. The customer himself can update the firmware received through any means even through the same management program for managing the device i.e. friendly interface produced and tested ad hoc by the manufacturing company.

3. The customer does not incur service interruptions due to the traditional management of reprogramming.

4. The manufacturing company can provide stronger support to the customer without logistics and management costs of reprogramming by making the new firmware available for the customer through whatever means e.g. via electronic mail .

European Patent Publication EP A 1 701 262 describes a method for re programming a device in which a memory is present comprising a sector storing a bootloader and one or more sectors storing the application programs. This publication relates in particular to a method that allows optimal exploitation of the available memory without leaving unused spaces but rather guaranteeing the integrity of the bootloader during the reprogramming phase.

U.S. Pat. No. 6 925 365 describes a system for updating applications by means of a flashloader in a vehicle control unit for controlling electronic devices. The described system provides for the automatic update from an existing version of application code to a new version by using the flashloader.

One of the problems that can occur in conventional updating or re programming procedures is management of the critical operations which can result in a malfunction of the device. These critical operations can include management of the communication channel receipt of the new firmware fragmented into a plurality of messages power outage during the procedure corruption of the new firmware during transmission during saving or corruption of a memory cell because of external factors due to damage to the device minimal management of the device in the case of absence of the application code so as to avoid device damage and certainty that the application code to be executed is the code desired by the person who updated the device.

Data corruption or loss during the reprogramming phase controlled by the bootloader can result in a non functioning device. Errors in data transmission reading or writing an accidental power outage or other external factors may lead to the corruption of the application code and therefore to a failure in the device.

In particular the present invention relates to re programming methods for re programming application code stored in a memory for example a memory of an embedded device by means of a bootloader which allows avoiding or limiting errors or critical situations of the type described above.

According to one aspect the invention provides a method for uploading and storing application code in a rewritable non volatile memory of an electronic device by means of a bootloader. The method may include receiving the application code transmitted by a master unit through a communication channel writing the application code in a portion of the non volatile memory and validating at least a portion of the application code by means of the bootloader.

In general the code or a portion thereof is validated by computing through the bootloader a checksum for instance CRC or other validation algorithm which is then transmitted back to the master which in turn verifies whether the checksum matches with a checksum previously calculated on the application code or on the corresponding portion thereof before the transmission from the master to the bootloader. If the two checksums match the master enables the bootloader to execute a subsequent operation. If the two checksums do not match the master can repeat the transmission of the same portion of application code or of the whole application code or in case it can abort the procedure and signal the anomaly.

Further advantageous characteristics and embodiments of the method according to the invention are set forth in the appended claims and will be further described hereunder with reference to non limiting practical embodiments of the invention shown in the accompanying drawings.

Referring to in principle a system on which the invention can be implemented can be represented schematically as a hardware block which interacts with bootloader and application code which constitute as a whole the firmware installed on the device.

According to a first approach both the bootloader and the application code can be provided as two separate firmware installations each forming a unit by itself. Each firmware exists as an alternative to the other. Therefore to operate both the bootloader and the application code should have at least the basic functionalities for managing the available hardware including for example 

2. Management of the communication channels so that the bootloader can receive new application code to allow remote control and

3. Generic functions not depending from the program per se such as by way of example CRC routines memory management routines etc.

The bootloader is firmware with reduced dimensions 512 1024 048 . . . bytes code and 128 256 512 . . . bytes RAM depending upon the device located in a typically protected memory portion of the microcontroller that is in a portion of memory which can not be written without the aid of an application external device called a programmer . This means that the bootloader cannot be accidentally overwritten because of an error in the firmware. The application can instead occupy the remaining part of the device and is located in a portion of memory of the microcontroller which is not typically protected that is in a portion of memory which can be written without the aid of a programmer. This is the real project and contains all the functionalities necessary for managing the device. Both the bootloader and the application code must be compiled in the programming environment dedicated to the microcontroller used.

After any reset of the device due to either a shutdown an external hardware management or a forced reset via software the bootloader is the first firmware which takes the control of the device. The bootloader performs the following functions 

4. Controls whether it was commanded to stay in boot mode and wait for new application code or if it can jump to the execution of the application code already present after having validated it.

Typically when a reset of the device occurs once the bootloader has performed the controls defined above and verified that it can jump to the application code already present in the non volatile memory the device changes from the boot mode to the execution of the application code under the control of the latter. At startup the application code once again initializes all the peripheral devices and starts normal functioning.

When a user decides to externally update the application code of the device it is sufficient to communicate it so that the application code itself stores somewhere for example external EPROM the need for boot mode and executes a software reset.

The operations carried out by the bootloader at a new startup of the device are substantially known to a person of skill in the art per se and they will not be described in particular detail. Possible methods for re programming the application code resident in the non volatile memory by means of the bootloader will be described hereunder.

Generally the resources of a microcontroller are extremely limited. Therefore according to some embodiments of the invention the new firmware is not downloaded all at once and validated before being accepted. Instead it will be received fragmented and each fragment is stored in the zone dedicated to the application code. According to some embodiments the application code can be subdivided into a plurality of so called portions called pages each of which is stored in a portion of memory. Each page is transmitted as a whole stored by the bootloader in the non volatile memory and validated. In other embodiments each page must be subdivided into parts or portions which are stored one at a time in a buffer or temporary register to complete a single page. The single page is then stored in the non volatile memory and validated or validated before being copied by the buffer into the non volatile memory or validated both before and after being written to the non volatile memory .

A process of this type in which each page is subdivided in code parts or fragments is necessary for example in the case of a microprocessor with pages of 64 or 128 bytes and an exchanged packet of 32 bytes. In this case the writing command for writing the pages to the non volatile memory or flash memory can be subdivided into two or four commands of 32 bytes each for example due to the limited memory available for implementing transmission receipt of data.

This process will be described in greater detail hereunder with reference to the schematic sequence shown in .

In a first phase the bootloader receives from the master through the channel a first part of a generic page N of the application software which must be written to the non volatile memory . In this phase the integrity of the message containing the first part of the Npage is verified by the bootloader in a known manner for example by means of a CRC cyclic redundancy check contained in the message itself. The validity of the message i.e. the integrity of data received is verified by the bootloader on the basis of the transmission protocol used. Data is stored in a support buffer constituted for example by a portion of the RAM of the device .

The procedure is repeated C until the support buffer will contain all the parts which form the Npage. At this point it is possible to validate the received page otherwise validation can be performed after writing to the non volatile memory . In the example shown in validation of the page is carried out after writing to the non volatile memory in such a way as also to detect any error which may occur in transferring data from the volatile memory of the support buffer to the flash memory . It is also possible to perform both the validations before and after writing to the non volatile memory .

With reference to the example represented in after the whole Npage has been written to the support buffer the bootloader writes it to a partition of non volatile memory .

Validation of the whole page is necessary for the following reason. The integrity of the individual messages or page parts which has been validated by the bootloader through the CRC stored in each message received during the preceding phases does not guarantee that the Npage is correctly written to the flash memory . Furthermore the correct receipt of the single messages containing single parts of a page does not allow confirmation of whether all the parts of the page have been effectively received.

Therefore the following phase provides that the bootloader performs the verification or validation of the Npage. For this purpose according to one possible embodiment the bootloader can read the page from the memory and transmit it again to the master which then performs the comparison between what was transmitted and what was received for example by calculating a checksum of the two versions of the application code. This process is however long and not efficient.

According to other more efficient embodiments validation of the page is performed by making the bootloader calculate the checksum of the whole page just written. For this purpose the content of the page can be transferred by the bootloader to a volatile memory buffer and the checksum is calculated on this data. The checksum can be advisably stored in a further buffer or volatile memory register associated with the page number N to which it refers if desired.

In the following phase the bootloader transfers the checksum to the master and the latter verifies that this checksum corresponds to the checksum stored by the master before the transmission of the Npage.

Validation of all single pages received is not sufficient to guarantee the integrity and completeness of the application code received and loaded by the bootloader in the non volatile memory . In fact the checks and validations performed up to now are not able to detect for example a missing page. It is therefore necessary to perform a validation operation i.e. a control operation on the integrity and completeness of the whole application code in its entirety. For this purpose according to some embodiments the bootloader can calculate the whole checksum on the whole application code stored in the flash memory . The calculated checksum is stored in a register and transmitted to the master . However this process is not particularly efficient.

In a preferred embodiment validation of the entire application code is performed by using the partial checksums as they are calculated on the single pages written in the flash memory . For this purpose the checksum of an Npage stored in the volatile register as described with reference to is used as a seed to generate the checksum of the following page. Therefore the value of the checksum calculated on the last page represents the checksum of the whole application code in its entirety. This data is transmitted to the master for validation. The master has calculated in a similar manner the checksum of the application code before transmitting it and now it can therefore compare these two values. If the transmission was successful and complete and the data has not been corrupted during the transmission writing and reading phases the two checksums must be equal. If this condition does not occur the master can repeat the operation again.

If the validation is successful the master communicates one or more additional parameters to the bootloader to allow it to validate the whole application code during subsequent startups of the system for example following a shutdown of the device . These parameters can include addresses of the zones of the non volatile memory in which the firmware or application code is stored address of the first instruction of the new firmware or application code or complete checksum CRC of the whole application code.

At startup the bootloader reads this information and calculates the checksum of the firmware in order to verify whether the application is correct or whether it is corrupted or incomplete and therefore damaged. In the first case the bootloader is authorized to jump to the application code. In the second case it waits for example in error mode for a new application.

In this way it is possible to avoid errors due for example to a power outage during the programming phase. In fact after having received and stored the first portion page of application code the old application code resident in the memory cannot be used as it is no longer complete and coherent. At this point if for any reason a reset occurs the device would have available an incorrect and potentially dangerous application. The bootloader can detect this error situation as at startup it performs a validation phase for validating the stored application code by calculating its checksum and comparing it with the checksum previously stored. In an anomalous situation of the type described above the checksum is calculated on a series of instructions that are partly of the old application code and partly of the new application code. Therefore this checksum does not match with the stored checksum.

The described validation criteria can be applied also in the presence of a different organization of the hardware firmware bootloader application code system for example of the type shown in .

In this new organization the management functions of the bootloader for managing the hardware are not replicated in the application code. The application code utilizes the management functions API application programming interface already present in the bootloader and that the bootloader is made available to the application code itself.

APIs are a series of basic functions to which the application can have access in order to perform its operations and which in this way do not have to be duplicated. By way of example one can consider I O initializing interrupt functionalities communication routines transmitting and receiving CRC and timing routines.

In this case the application code cannot exist alone but rather only with the support of the bootloader. This approach allows the application code to be reduced eliminating all the generic and redundant parts generally duplicated and provides a more efficient and safe application code. It is not necessary to test the basic routines every single time new application code is made available. It will only be necessary to test the advanced functionalities.

Obviously in the case of a request for update the device will not be reset and the bootloader which is as already stated always active will suspend the execution of the application until further orders and until a correct and validated application will be present again.

The previous detailed description has been provided for the purposes of illustration and description. Thus although there have been described particular embodiments of the present invention of a new and useful Method And Apparatus For Reprogramming Applications In Embedded Devices it is not intended that such references be construed as limitations upon the scope of this invention except as set forth in the following claims.

