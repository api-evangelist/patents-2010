---

title: Method and apparatus for byte-access in block-based flash memory
abstract: Techniques are described herein for managing data in a block-based flash memory device which avoid the need to perform sector erase operations each time data stored in the flash memory device is updated. As a result, a large number of write operations can be performed before a sector erase operation is needed. In addition, the block-based flash memory can emulate both programming and erasing on a byte-by-byte basis, like that provided by an EEPROM.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08769189&OS=08769189&RS=08769189
owner: Macronix International Co., Ltd.
number: 08769189
owner_city: Hsinchu
owner_country: TW
publication_date: 20100427
---
This application claims the benefit of U.S. Provisional Application No. 61 178 813 titled Intelligent and Reliable Algorithm to Perform Byte Access in Block Based Flash Memory filed 15 May 2009 which is incorporated by reference herein.

The present invention relates to flash memory technology and more particularly to techniques for managing data in block based flash memory devices.

Electrically Erasable Programmable Read Only Memory EEPROM and flash memory include memory cells that store charge between the channel and gate of a field effect transistor. The charge stored affects the threshold voltage of the transistor and the changes in threshold voltage due to the stored charge can be sensed to indicate data stored in the memory cell. One type of charge storage cell is known as a floating gate memory cell which stores charge on an electrically conductive layer between the channel and gate. Another type of charge storage cell is referred to as a charge trapping memory cell which uses a dielectric layer in place of the floating gate.

The term program as used herein refers to an operation which increases the threshold voltage of the transistor. The term erase as used herein refers to an operation which decreases the threshold voltage of the transistor. Further the term write as used herein describes an operation which changes the threshold voltage of the transistor and is intended to encompass the operations for increasing and for decreasing the threshold voltage of the transistor.

In an EEPROM device the memory cells can be both programmed and erased on a byte by byte basis independent of the other data bytes. However to enable the programming and erasing on a byte by byte basis the memory density of EEPROM is relatively low.

Flash memory typically provides higher memory density than EEPROM. In a flash memory device the memory cells can be programmed on a byte by byte basis. However because of the configuration of the flash memory cells erasing is performed on a much larger sector by sector basis where each sector includes a relatively large number of bytes. Therefore in order to erase a memory cell in a sector all the memory cells in that sector must also be erased. In other words flash memory offers programming on a byte by byte basis but does not offer erasing on a byte by byte basis as is provided by EEPROM.

EEPROM and flash memory devices are often used for different applications. Generally because of its higher density flash memory is more economical than EEPROM in mass data storage applications. EEPROM is commonly used in applications where programming and erasing small amounts of data on a byte by byte basis is desired.

A variety of electronic devices also include both EEPROM and flash memory in order to fulfill the different memory performance requirements for the various functions of the device. However using both of these types of memory increases the cost and complexity of the device.

Because flash memory does not offer erase on a byte by byte basis writing updated data to a sector can be done by performing a sector erase operation to erase all the memory cells in that sector and then writing the updated data into that sector. A drawback to this process is that all the memory cells in that sector experience a cycle count even though data may only be changed in some of the memory cells in that sector. This process is also slow.

A specific issue arising in flash memory is limited endurance the number of erase and or program cycles over which the cells in the device remain operative and reliable. Thus repeated and frequent writes to a single sector or a small number of sectors will result in some of the sectors becoming defective in a relatively short time.

Various wear leveling techniques have been proposed for extending the lifetime of flash memory. One wear leveling approach involves the use of counters to track the number of times each sector is erased. The counters are then used to alter the mapping of data into the various sectors to even out their wear. See for example U.S. Pat. Nos. 6 000 006 5 485 595 and 5 341 339.

Although the use of counters can extend the lifetime of flash memory devices the problem of limited read write endurance continues to preclude the use of flash memory in applications requiring a large number of program and erase operations.

Another wear leveling approach is to write updated data to an unused physical location in the flash memory device rather than overwriting old data in the original location. This reduces the number of sector erase operations for a given number of write operations to the flash memory device. See for example U.S. Pat. Nos. 5 845 313 and 6 115 785.

In order to track the changes in the physical locations of the data a programmable mapping or address translation table can be used. The programmable mapping table stores mapping information between the logical addresses specified by an external system and the actual physical addresses of the flash device containing valid data. In order to accurately track the physical locations of valid data the programmable mapping table is updated during operation.

To ensure that valid data is preserved the mapping information must be preserved when power is no longer being supplied. However since the programmable address translation is continuously being updated storing the mapping information in the flash memory reduces the life of the device. This can also significantly impact the performance of a system utilizing flash memory due to the relatively slow erase cycle of the flash memory. The programmable mapping table may alternatively be stored in another non volatile memory circuit on the flash device. However this increases the cost and complexity of the flash device.

It is therefore desirable to provide flash memory devices which emulate programming and erasing on a byte by byte basis as provided by EEPROM while also addressing the issue of endurance with reduced complexity and cost.

Techniques are described herein for managing data in a flash memory device which avoid the need to perform sector erase operations each time data stored in the flash memory device are updated. Logical addresses mapped to the blocks in the flash memory device have a smaller number of addresses than the blocks. The sector erase operations are avoided by writing the updated data for the logical addresses to empty pre erased locations in the corresponding blocks rather than directly overwriting old data. As a result a large number of write operations can be performed before a sector erase operation is needed. In addition the block based flash memory can emulate both programming and erasing on a byte by byte basis as provided by an EEPROM.

A method is described herein for operating a flash memory device having a plurality of blocks where each block in the plurality of blocks comprises a plurality of sectors. The method includes mapping logical addresses to corresponding blocks in the plurality of blocks.

For a particular block in the plurality of blocks the method also includes marking a first sector of the particular block as an active sector having a core data area and a write log area. The core data area is used to store a data set for the corresponding logical addresses and the write log area is used to store updates of the data in the data set. A second sector of the particular block is marked as an inactive sector. The inactive sector serves as a transfer unit to store an updated data set for the corresponding group of logical addresses. The data set is then written to the core data area.

In response to a write command to write update data for a logical address mapped to the particular block write log data is written to a free location in the write log area. The write log data indicates the logical address and indicates the updated data.

The data from the core data area and the write log area is also used to compose an updated data set from time to time such as when the write log area is full so that the write log area does not overflow. The updated data set is written within a core data area of the second sector and marked as the active sector for the particular block. The first sector is erased and marked as the inactive sector for the particular block.

The first and second sectors can each include a status flag area where marking the second sector as the active sector comprises programming predetermined data in the status flag area of the second sector and marking the first sector as the inactive sector comprises erasing the status flag area of the first sector.

The marking of the sectors can be accomplished by changing data in the status flag area without the need to always erase the status flag area. For example when a sector is inactive the data in the status flag area can be all 1 s in binary notation or all F s in hexadecimal notation. Thereafter the data in the status flag area can be changed by programming predetermined data in the status flag area so that particular bits that are a logical state 1 erased are changed to a logical state 0 programmed while leaving the bits that are already at logical state 0 . For example if the data of the status flag area for an inactive sector is 0xFFFFFF successive programming to the status flag area during operation change the data value to 0xFFFF00 then to 0xFF0000 and then to 0x000000 . Since the status flag area is within the sector the status flag area is then erased back to 0xFFFFFF when the sector is erased. This technique eliminates the need to erase the status flag area each time the data of the status flag area needs to be changed.

Techniques described herein also efficiently manage the mapping between logical addresses and the physical addresses of the blocks which contain valid data without the need for frequent updates to the logical to physical address mapping information.

Mapping techniques described herein identify the block corresponding to a particular logical address and identify an offset indicating a relative physical address in the core data area. In the case where the write log area does not include updated data for the particular logical address the active sector offset when used in connection with the marking of the active sector indicates the corresponding entry in the core data area storing valid data for the logical address. The use of the mapping techniques status flags and the write log area obviates the need to update the mapping information each time data in the flash memory device is updated. Thus instead of having to read and update large mapping tables during operation the mapping information can remain static.

Also described is an apparatus including a data processor and memory coupled to the data processor. The memory stores instructions executable by the data processor including instructions for carrying out the various operations described herein on a flash memory array.

Other aspects and advantages of the present invention can be seen on review of the drawings the detailed description and the claims which follow.

User interface input devices may include a keyboard pointing devices such as a mouse trackball touchpad or graphics tablet a scanner a touchscreen incorporated into the display audio input devices such as voice recognition systems microphones and other types of input devices. In general use of the term input device is intended to accommodate all possible types of devices and ways to input information into computer system or onto communication network .

User interface output devices may include a display subsystem a printer a fax machine or non visual displays such as audio output devices. The display subsystem may include a cathode ray tube CRT a flat panel device such as a liquid crystal display LCD a projection device or some other mechanism for creating a visible image. The display subsystem may also provide non visual display such as via audio output devices. In general use of the term output device is intended to include all possible types of devices and ways to output information from computer system to the user or to another machine or computer system.

Flash memory device stores the basic programming and data constructs that provide the functionality of certain embodiments described herein including the instructions for logical to physical address mapping and translation and instructions used for organization of data within flash memory device discussed below . These software modules are generally executed by processor which may include random access memory RAM for storage of instructions and data during program execution.

In the illustrated embodiment the processor executing instructions to carry the various operations described herein is external to the flash memory device . Alternatively the flash memory device includes a processor or other type of controller to control the management of data and carry out the various operations described herein. For example the controller can be a state machine implemented using special purpose logic circuitry as known in the art. In alternative embodiments the controller comprises a general purpose processor which may be implemented on the same integrated circuit which executes a computer program to control the operations of the flash memory device . In yet other embodiments a combination of special purpose logic circuitry and a general purpose processor may be utilized for implementation of the controller.

Bus subsystem provides a mechanism for letting the various components and subsystems of computer system communicate with each other as intended. Although bus subsystem is shown schematically as a single bus alternative embodiments of the bus subsystem may use multiple buses. In some embodiments the data address and command signals between the flash memory device and the bus subsystem are applied on shared lines in a serial fashion such as can be implemented using serial peripheral interfaces as known in the art.

Computer system itself can be of varying types including a personal computer a portable computer a workstation a computer terminal a network computer a mainframe or any other data processing system or user device. Due to the ever changing nature of computers and networks the description of computer system depicted in is intended only as a specific example for purposes of illustrating the preferred embodiments. Many other configurations of computer system are possible having more or less components than the computer system depicted in .

As illustrated in the flash memory device includes a plurality of physical blocks including Block 0 through Block N N for storing data organized using the techniques described herein. As noted above the flash memory device also includes additional blocks for storing the instructions for logical to physical address mapping and translation and the organization of the data in the blocks Block 0 through Block N N.

The instructions include the mapping between the logical addresses specified by the computer system to the flash memory device and the physical addresses of the blocks Block 0 through Block N N of the flash memory device . As described in more detail below the logical addresses mapped to the blocks Block 0 through Block N N have a smaller number of addresses than the number of addresses in the corresponding blocks Block 0 through Block N N so that updated data can be stored in the blocks Block 0 through Block N N without the need to perform a sector erase operation.

The blocks Block 0 through Block N N each include a plurality of sectors which are separately erasable from the other sectors. The sectors of the blocks Block 0 through Block N N include a status flag area storing data which indicates whether a given sector is currently active working inactive erased dirty or temporary.

The active sector of a given block is used to store the data for the corresponding logical addresses. The active sector includes a core data area storing a data set for the corresponding group of logical addresses. To enable storage of the updates to the data in the data set the active sector also includes a write log area. In a write operation write log data including updated data is written into free empty locations in the write log area. The size of the write log area is a trade off between how often sector erase operations will be performed and the speed of the read operation discussed below and thus can vary from embodiment to embodiment.

As discussed in more detail below the write log data in the write log area is stored in an organized manner so that the valid data can be correctly determined.

Each block also includes a plurality of inactive sectors that serve as transfer units to store updated data sets for the corresponding logical addresses from time to time such as when the write log area is full so that the write log area does not overflow.

Block 1 is representative of the blocks Block 0 through Block N N in the flash memory device . Block 1 includes several sectors including and that are separately erasable. In this example sector is currently the active sector and sectors and are currently the inactive sectors.

The active sector also includes a pre erased write log area . In response to a write command to update data for a particular logical address mapped to Block 1 an entry of write log data is written to an empty pre erased location in the write log area .

The write log data includes a first field logical address field indicating the particular logical address for the updated data. The write log data also includes a second field updated data field indicating the updated data.

The first field of the write log data indicates that the entry in the core data area corresponding to the particular logical address is no longer valid and has been replaced by the updated data of the second field of the write log data .

The data in the first field may for example be the particular logical address the physical address in the core data area of the entry corresponding to the particular logical address the active sector offset discussed below or any other data that can be used to determine the particular logical address.

In a write operation an entry of the write log data is written to the first empty location in the write log area with remaining empty locations within the write log area following the most recent entry of write log data. In alternative embodiments an entry of the write log data is written to the last empty location in the write log area with remaining empty locations within the write log area preceding the most recent entry of write log data. Consequently the entries of the write log data are arranged sequentially in a temporal fashion.

By writing the updated data to the write log area rather than directly overwriting data in the core data area by sector erasing the sector only the memory cells storing the write log data have been written to. In addition the updated data was written without performing a sector erase operation. This results in a small number of sector erase operations compared to the number of write operations which effectively increases the endurance of the flash memory device .

Since the write log data is written to empty locations in the write log area eventually the write log area of the sector will become full. Thus from time to time an updated data set is composed using data from the core data area and the write log area and the sectors acting as the active and inactive sectors are switched so that the write log area does not overflow. The term from time to time as used herein is intended to be construed generally to mean occasionally and is therefore not restricted to uniform cyclic or otherwise equal time intervals.

In the composing process discussed below the updated data set containing the valid data for the corresponding logical addresses is composed using the data from the core data area and write log area of the current active sector . The updated data set is then written to the core data area of sector and the status flag in the status flag area of sector is changed to indicate that sector is now the active sector. Sector is then erased and set as an inactive sector for the Block 1 . In subsequent write operations to the Block 1 the write log data is written to the write log area of sector .

In addition to using the status flag areas to identify the active and inactive sectors of the sectors of the Block 1 the status flag areas are also used to ensure that the updated data is composed and properly stored in the new active sector. This is discussed in more detail below with respect to .

Thus group of logical addresses 0x0000 0x01FF is mapped to Block 0 groups of logical addresses 0x0200 0x03FF is mapped to Block 1 and so on.

In this example each of the 8 K byte blocks includes two 4 K byte sectors. The active sector of each block Block 0 through Block 7 includes a 512 byte core data area used to store the data set for the corresponding 512 byte logical address group through . The status flag area of each sector is 3 bytes. The remaining 35814 bytes of the active sector are used for the write log area. In this example 2 bytes are used for the first field logical address field of an entry of write log data to indicate the particular logical address of the updated data and 1 byte is used for the second field updated data field of the entry of write log data to indicate the updated data. Thus in this example the write log area can support 1193 single byte data write operations before the active sector becomes full.

As mentioned above the active sector of a given block will change during operation. Accordingly the physical addresses of valid data in the blocks depends upon which sector is currently active as well as any updated data in the write log area. As a result the translation between the logical addresses and the physical addresses which contain valid data is not fixed during operation.

The logical addresses are mapped to the corresponding blocks using an address translation table . For a particular logical address the address translation table provides the block which corresponds to the logical address. The address translation table also provides an active sector offset that identifies a relative address in the core data area associated with the particular logical address.

In the illustrated embodiment the active sector offset is a relative address from the beginning physical address of the core data area. In one such example in which a 512 byte core data area is used to store the data set for a corresponding 512 byte logical address group the active sector offset is a data value between 0x0000 to 0x01FF.

The active sector offset when used in connection with the status flags identifying the active sector indicates the corresponding entry in the core data area associated with the logical address. It should be noted that the corresponding entry in the core data area does not necessarily contain valid data for the logical address as updated data may be within the write log area. The read operation for determining the location of valid data is explained below with respect to .

The use of the status flags offset and the write log area obviates the need to update the address translation table each time data in the flash memory device is updated or when an active sector in a block is changed. Thus the address translation table can remain static while also enabling accurate tracking of the valid data.

Since the address translation table need not be continuously updated it may be stored in the flash memory device . During operating the address translation table may also be loaded into higher access speed memory such as DRAM or SRAM within the processor of .

At step the logical addresses are mapped to corresponding blocks in the flash memory device . The mapping can be carried out by creating and storing the address translation table discussed above with reference to .

At step a first sector of the particular block is marked as the active sector by programming the status flag area of the first sector to set its status flag to active. The active sector has a core data area and a write log area. A second sector in the particular block is marked as the inactive sector by setting its status flag to inactive. In this example a 0xFF0000 status flag indicates the active sector and a 0xFFFFFF status flag indicates the erased sector.

In response to a write command to store the updated data at step the block which corresponds to the particular logical address is determined using the address translation table discussed above.

At step the status flag areas of the sectors of the corresponding block are read to find the active sector.

At step the write log area of the active sector is searched to find a free location. Since empty locations in the write log area are in an erased state in this example the logical address fields are read from a beginning of the write log area to find the first instance of an erased location.

At step if a free location is not found in the write log area the write log area of the active sector is full and the operation continues to block where an updated data set is composed. The composing operation is discussed below with reference to .

If a free location is found in the write log area the process continues to step . At step a write log data entry indicating the logical address and the updated data is written to the free location in the write log area. The write operation then ends at step .

In response to a read command to read data from the particular logical address at step the block which corresponds to the particular logical address is determined using the address translation table discussed above.

At step the status flag areas of the sectors of the corresponding block are read to determine the active sector.

At step the write log area of the active sector is searched for an entry of the logical address the entry indicating that the write log area includes updated data for the logical address.

The write log data in the example above was written to the first free location in the write log area. As a result the write log data is arranged in a temporal sequence. Thus in the illustrated embodiment the data in the write log area is read beginning with the latest write log data because if the data for the logical address is updated a number of times the first entry of the logical address that is found is the most recent and thus indicates the valid data for the logical address. Thus upon finding an entry of the logical address the operation continues to step where the data for the logical address is read using the entry.

If an entry is not found in the write log area then the corresponding entry in the core data area contains the valid data for the particular logical address. At step the corresponding entry in the core data area associated with the particular logical address is determined using the active sector offset provided by the address translation table discussed above. The data stored in the corresponding entry is then read and output.

As was discussed above from time to time the sectors acting as the active and inactive sectors are switched.

For clarity purposes in the discussion below the sector that is active before the operation begins is referred to as Sector A while the inactive sector is referred to as Sector B .

At step the data stored in the write log area and the core data area of the active sector before the operation Sector A is read. The updated data set containing the valid data for the corresponding logical addresses is composed using the data read from the core data area and the write log area.

At step the updated data set is written to the core data area of Sector B and Sector B is marked as the active sector. In the illustrated embodiment the data of the status flag area of Sector B is changed to temporary 0xFFFF00 prior to the updated data set being written and following the writing of the updated data set the data in the status flag area of Sector B is then changed to active. Marking Sector B as active only after the updated data set is written ensures that Sector B includes the valid data. In addition by changing the status flag area of Sector B in this manner the data of the status flag area can be used to indicate whether an interruption such as power down occurred. This is discussed in more detail below with reference to .

At step Sector A is marked as inactive and is erased. In the illustrated embodiment the data of the status flag area of Sector A is changed to dirty 0x000000 prior to performing the erase operation on Sector A. The sector erase operation then changes the data of the status flag are of Sector A to erased inactive . By marking Sector A as dirty prior to erasing it the data of the status flag area can be used to indicate whether an interruption occurred prior to erasing Sector A.

As described above the marking of the sectors is accomplished by changing data in the status flag areas of the sectors without the need to always erase the status flag area.

As shown in when a sector is inactive the data in the status flag area is 0xFFFFFF . In the change from inactive to active the status flag is first changed to temporary. In the change to temporary status is done by programming the least significant byte so that the data of the status flag area is 0xFFFF00 . The change from temporary to active is done by programming the middle byte so that the data of the status flag area is 0xFF0000 .

In the change from active to inactive the data of the status flag area is first changed to dirty. In the change to dirty is done by programming the most significant byte in the status flag area so that the data is 0x000000 dirty . Since the status flag area is within the sector the status flag area is erased back to 0xFFFFFF when the sector is erased. This technique eliminates the need to erase the status flag area each time it needs to be changed. As a result the data of the status flag area can be stored within the sector rather than stored separately.

Alternatively the change in the status of the various sectors can be done by programming data in the status flag area different from those illustrated in .

At step the status flag of the sectors of a particular block are read. If the status flag of a sector is dirty then an interruption occurred during step of the operation . In such a case at step a sector erase is performed on the sector.

If the status flag of a sector indicates the sector is temporary then an interruption occurred during step of the operation . In such a case at step the operation is performed on the block.

If two sectors in the block have working sector status flags then an interruption occurred sometime between during steps and of the operation . In such a case at block the sectors are read to determine which sector is full and thus is actually the dirty sector and a sector erase is then performed on the dirty sector.

The operation then continues to check the next block in the flash memory device until all the blocks have been checked.

The Intelligent Flash Application Programming Interface API is a software module including logic to perform the logical to physical address mapping and translation and logic for the management of the data written to and read from the flash memory device to carry out the various operations described herein. The Intelligent Flash API translates the commands from the user code and provides instructions to the low level flash API . The Intelligent Flash API also uses the address translation table to translate the logical addresses from the user code to corresponding physical addresses which are then provided to the low level flash API software module.

The low level flash API is a software driver particularly adapted to function with the flash memory device . The low level flash API includes logic to perform the actual reading and writing of data in the flash memory device in response to the instructions and physical addresses provided by the Intelligent Flash API .

The flash memory device the low level flash API and the Intelligent Flash API together emulate the programming and erasing of the flash memory device on a byte by byte basis as described herein.

The flash memory device and the low level flash API can be implemented using a variety of commercially available off the shelf flash devices such as the MX25L512 CMOS serial flash by Macronix International Corporation Ltd. As a result the Intelligent Flash API provides the ability emulate the programming and erasing of the flash memory device on a byte by byte basis as described herein without necessitating the re writing of the low level drivers used by such devices.

In the Intelligent Flash API operates the byte write region of the flash memory device to emulate the programming and erasing on a byte by byte basis as described herein. In addition the low level flash API operates the page write region to program and erase data on a block by block basis in the flash memory device .

In such an embodiment the flash memory device can be used as both an EEPROM and a flash memory. As a result the flash memory device can be used to replace separate EEPROM and flash memory which reduces the system cost and complexity.

The techniques described herein enable the use of block based flash memory in a large number of information processing systems. As an example the techniques described herein emulate programming and erasing of single bytes of data. More generally the techniques described herein can be used to program and erase data of other sizes in block based flash memory where the size of the data to be programmed and erased is less than the size of the block.

Advantages of the techniques described herein include savings on system cost by allowing for the replacement of higher priced lower density EEPROM with block based flash memory. By implementing the techniques described herein the flash memory read write endurance can be increased by greater than 1000 over traditional block access algorithms.

While the present invention is disclosed by reference to the preferred embodiments and examples detailed above it is to be understood that these examples are intended in an illustrative rather than in a limiting sense. It is contemplated that modifications and combinations will readily occur to those skilled in the art which modifications and combinations will be within the spirit of the invention and the scope of the following claims.

