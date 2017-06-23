---

title: Semiconductor memory device capable of accurate reading even when erasure level changes
abstract: According to one embodiment, a semiconductor memory device includes a memory cell array and a controller. The memory cell array includes first, second, and third memory cells each of which stores k-bit data (where k is a natural number not smaller than 1). The first and second memory cells are adjacent to each other, and the second and third memory cells are adjacent to each other. Data is stored into the memory cells in an order of the first, second, and third memory cells. When reading data from the second memory cells, the controller reads data from the first and third memory cells, and changes read conditions for the second memory cell in accordance with the read data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08379444&OS=08379444&RS=08379444
owner: Kabushiki Kaisha Toshiba
number: 08379444
owner_city: Tokyo
owner_country: JP
publication_date: 20100916
---
This application is based upon and claims the benefit of priority from Japanese Patent Application No. 2010 005261 filed Jan. 13 2010 the entire contents of which are incorporated herein by reference.

Embodiments described herein relate generally to a semiconductor memory device such as a NAND flash memory which is capable of storing 2 level data and multi level data.

In a NAND flash memory all or half of plural cells arranged in a row direction each are connected to write and read latch circuits through a bit line. A write or read operation is performed on all or half of the plural cells arranged in the row direction for example cells equivalent to 2 to 8 kB at one time.

Units of writing and reading are referred to as pages and one block is constituted by plural pages. Erasure of memory cells is performed in units of blocks. In an erase operation electrons are pulled out of memory cells thereby making threshold voltages negative. In a write operation electrons are injected into memory cells thereby setting threshold voltages to be positive.

Recently a multi level memory has been developed in which one of plural threshold voltages hereinafter also referred to as threshold levels is set to enable storage of data constituted by multiple bits. For example when four threshold levels are given 2 bit data can be stored in one cell. When eight threshold levels are given 3 bit data can be stored in one cell. Further when sixteen threshold levels are given 4 bit data can be stored in one cell.

Meanwhile there is a tendency that capacitive coupling between adjacent cells increases as elements are more micronized. Therefore there is a problem that a threshold level of a cell which is written first changes when an adjacent cell is written. Therefore there has been proposed that when data is read from a word line WLn data from a word line WLn 1 which is written after a word line WLn is read and a read voltage for the word line WLn is corrected depending on a level of the data for example see Jpn. Pat. Appln. KOKAI Publication No. 2004 326866 .

However an erasure level of cells connected to the word line WLn varies depending on a level of the word line WLn 1 written before the word line WLn. Therefore there is a problem that a read margin for cells connected to the word line WLn decreases. Therefore there is a demand for a semiconductor memory device which can suppress any influence of capacitive coupling with adjacent cells and accurately read even when an erasure level changes.

In general according to one embodiment a semiconductor memory device includes a memory cell array and a controller. The memory cell array includes first second and third memory cells each of which stores k bit data where k is a natural number not smaller than 1 . The first and second memory cells are adjacent to each other and the second and third memory cells are adjacent to each other. Data is stored into the memory cells in an order of the first second and third memory cells. When reading data from the second memory cell the controller reads data from the first and third memory cells and changes read conditions for the second memory cell in accordance with the read data.

The memory cell array includes plural bit lines plural word lines and common source lines. In the memory cell array memory cells constituted by for example EEPROM cells and capable of electrically rewriting data are arrayed in a matrix. The memory cell array is connected to a bit line control circuit for controlling the bit lines and to a word line control circuit .

The bit line control circuit reads data from memory cells in the memory cell array through the bit lines detects states of the memory cells in the memory cell array through the bit lines and applies a write control voltage to the memory cells in the memory cell array through the bit lines to execute writing. The bit line control circuit is connected to a column decoder and a data input output buffer . A data storage circuit in the bit line control circuit is selected by a column decoder . Data in the memory cells which has been read into the data storage circuit is externally output from the data input output terminal through the data input output buffer . The data input output terminal is connected to an unillustrated host outside the memory chip. This host is constituted by for example a microcomputer and receives data output from the data input output terminal . Further a host outputs various commands CMD for controlling operations of the NAND flash memory addresses ADD and data DT. Write data input from the host to the data input output terminal is supplied through the data input output buffer to a data storage circuit selected by the column decoder . Commands and addresses are supplied to a control signal control voltage generation circuit .

The word line control circuit is connected to the memory cell array . The word line control circuit selects word lines in the memory cell array and applies the word lines with a voltage required for reading writing or erasing.

The memory cell array bit line control circuit column decoder data input output buffer and word line control circuit are connected to and controlled by the control signal control voltage generation circuit . The control signal control voltage generation circuit is connected to a control signal input output terminal and is controlled by control signals ALE Address Latch Enable CLE Command Latch Enable input from the host through the control signal input output terminal WE Write Enable and RE Read Enable . The control signal control voltage generation circuit generates voltages for word lines and bit lines when writing data and a voltage supplied to wells when erasing data. The control signal control voltage generation circuit includes for example a boost circuit such as a charge pump circuit and can generate a program voltage a read voltage an erasure voltage and other voltages.

For example the bit line control circuit word line control circuit and control signal control voltage generation circuit constitute a controller which controls write and read operations.

The bit line control circuit includes plural data storage circuits . The data storage circuits are respectively connected to pairs of bit lines BL BL BL BL . . . BLie BLio BLne BLno .

The memory cell array includes plural blocks as denoted by broken lines. Each of the blocks is constituted by plural NAND units. For example data is erased in units of blocks. Further an erase operation is performed simultaneously on two bit lines connected to each of the data storage circuits .

Further one sector is constituted by plural memory cells which are arranged on every other bit line and are connected to one word line i.e. memory cells surrounded by a broken line . For each sector data is written and read. That is half of plural memory cells which are arranged in a row direction are connected to a corresponding bit line. Therefore the write operation and the read operation each are performed on half of the plural memory cells arranged in one row direction.

In the read operation program verify operation and program operation one of two bit lines BLie BLio connected to each of a data storage circuit is selected in accordance with an address signal YA YA YA . . . YAn . Further in accordance with the external address one word line is selected and two pages denoted by a broken line are selected. Switching between the two pages is performed by an address.

When two bits are stored in one cell two pages are selected. When one bit is stored in one cell one page is selected. When three bits are stored in one cell three pages are selected. When four bits are stored in one cell four pages are selected.

Descriptions made below are applicable to both of the configurations represented in and . However a case of applying will now be described below.

Furthermore Vpass is a voltage to be supplied to word lines of non selected cells when writing data and Vread is a voltage supplied to non selected cells when reading data.

In the sense amplifier unit is constituted by plural N channel MOS transistors hereinafter referred to as NMOS to plural P channel MOS transistors hereinafter referred to as PMOS and transfer gates and a latch circuit and a capacitor . The latch circuit is constituted by for example clocked inverter circuits and

An end of a current path of the NMOS is connected to a node supplied with a power supply voltage Vdd and another end of the current path is grounded through a transfer gate an NMOS and a transfer gate . A connection node between the NMOS and transfer gate is connected to an end of the current path of the NMOS . Another end of the NMOS is connected to a bit line BL provided on the memory cell array. A serial circuit of NMOS and NMOS is connected in parallel with the NMOS .

Further an end of the current path of a PMOS is connected to a node supplied with a power supply voltage Vdd and another end is connected to an input end of an inverter circuit which constitutes a latch circuit through the PMOS and is grounded through NMOS . An input end of a clocked inverter circuit which is cross connected the inverter circuit is connected to data control unit DCU through an NMOS . Further the gate of the PMOS is connected to a connection node between NMOS and NMOS . An end of a capacitor is connected to the connection node. Another end of the capacitor is supplied with a clock signal CLK.

The gate of the NMOS is supplied with a signal BLX. A gate of an NMOS constituting a transfer gate is supplied with a signal LAT at an output end of an inverter circuit which constitutes a latch circuit . A gate of the PMOS transistor is supplied with a signal INV at an input end of the inverter circuit . A gate of the NMOS is supplied with a signal BLC and a gate of the NMOS is supplied with a signal BLS. A gate of an NMOS constituting a transfer gate is supplied with a signal INV at an input end of an inverter circuit which constitutes the latch circuit . A gate of the PMOS transistor is supplied with a signal LAT at an output end of the inverter circuit

The gate of the NMOS is supplied with a signal HLL and the gate of the NMOS is supplied with a signal XXL.

The gate of a PMOS is supplied with a signal STB and the gate of the NMOS is supplied with a reset signal RST. The gate of the NMOS is supplied with a signal NCO.

When data is written into memory cells at first a signal STB is set to a high level hereinafter referred to as level H and a reset signal RST is temporarily set to the level H thereby to reset the latch circuit . The LAT is set to the level H and the signal INV is set to a low level hereinafter referred to as level L .

Thereafter the signal NCO is set to the level H and data is taken in from the data control unit . When this data is at the level L 0 which indicates write the signal LAT goes to the level L and the signal INV goes to the level H. Otherwise when the data is at the level H 1 which indicates non write the data in the latch circuit is not changed but the signal LAT and the signal INV are respectively maintained at the levels H and L.

Subsequently when the signal LAT is at the level L and the signal INV is at the level H write where signals BLX BLC and BLS are at the level H the transfer gate is turned off and the transfer gate is turned on to set the bit line BL to Vss. When the word line reaches the voltage Vpgm in this state data is written into the memory.

On the other side in the latch circuit when the signal LAT is at the level H and the signal INV is at the level L non write the transfer gate is on and the transfer gate is off. Therefore the bit line BL is charged to Vdd. Accordingly when the word line reaches Vpgm a channel of the cell is boosted up to a high potential and data is therefore not written into the memory cell.

When data is read from memory cells at first the reset signal RST is once set to the level H thereby resetting the latch circuit and the signals LAT and INV are set to the levels H and L. Thereafter signals BLS BLC BLX HLL and XXL are set to predetermined voltages and the bit line BL is charged. Accordingly a node of the capacitor is charged to Vdd. When a threshold voltage of a memory cell is higher than a read level read voltage the memory cell is in an off state and the bit line is maintained at the level H. That is Node is maintained at the level H. Otherwise when the threshold voltage of the memory cell is lower than the read level the memory cell is in an on state and electric charges of the bit line BL are discharged. Therefore the bit line BL goes to the level L. Therefore Node goes to the level L.

Subsequently when a signal STB is dropped to the level L the PMOS is turned on since the Node is at the level L if the memory cell is on. The signal INV of the latch circuit goes to the level H and the signal LAT goes to the level L. Otherwise if the memory cell is off the signal INV of the latch circuit is maintained at the level L and the signal LAT is maintained at the level H.

Thereafter when a signal NCO is stepped to the level H the NMOS is turned on and data in the latch circuit is transferred to the data control unit

The program verify operation to verify the threshold voltage of the memory cell after the write operation is the same as that for the read operation.

The data control unit is constituted by a calculation circuit and plural data latch circuits ADL BDL XDL and NMOS .

The calculation circuit is constituted by a bus hereinafter referred to as IBUS transfer gates and which are connected to two ends of the IBUS and operate complementarily to each other a latch circuit which latches data of the IBUS and a setting circuit which sets levels of data latch circuits ADL BDL and XDL.

The transfer gate is operated by complementary signals COND and CONS and connects the bus of the sense amplifier unit SAU referred to as SBUS to the IBUS. The transfer gate is operated by complementary signals CONS and COND and connects the IBUS to a bus connected to the data latch circuits ADL BDL and XDL hereinafter referred to as DBUS . When the transfer gate is on the transfer gate is off. When the transfer gate is off the transfer gate is on.

The latch circuit is constituted by plural PMOS to plural NMOS to and an inverter circuit . The gates of the PMOS and NMOS are supplied with a set signal SET and the gate of the PMOS is supplied with a reset signal REST. The gate of the NMOS is supplied with a signal IFH and the gate of the NMOS is supplied with a signal IFL. The gate of the NMOS is connected to the IBUS through the inverter circuit . The gate of the NMOS is connected to the IBUS.

The setting circuit is constituted by PMOS to and NMOS to . Gates of the PMOS and NMOS are supplied with a signal FAIL. The signal FAIL is a signal of a connection node between the PMOS and NMOS as an output end of the latch circuit . Gates of the PMOS and NMOS are supplied with a signal MTCH. The signal MTCH is a signal of a connection node between the PMOS and NMOS as an output end of the latch circuit . Further a gate of the PMOS is supplied with a signal MHB and a gate of the PMOS is supplied with a signal FHB. A gate of the NMOS is supplied with a signal FL and a gate of the NMOS is supplied with a signal ML.

The data latch circuits ADL BDL and XDL have the same configurations as each other and each are constituted by a latch circuit and a transfer gate which connects the latch circuit to the DBUS. Each of transfer gates is controlled by signals BLCA BLCB and BLCX. The data latch circuit XDL is connected through the NMOS to an external I O. A gate of the NMOS is supplied with a signal CSL.

The data control unit maintains write data as described above and maintains data read from memory cells when reading data.

2 bit write data supplied from the data input output buffer is latched by the data latch circuits ADL and BDL through the data latch circuit XDL for example in a manner that one bit is latched by one of the circuits.

A calculation circuit represented in can perform calculations such as AND OR and or exclusive NOR on data in the data latch circuits ADL and BDL. For example for AND data maintained in the data latch circuits ADL and BDL are output to the DBUS and IBUS. In this case only when data 1 is latched in both the data latch circuits ADL and BDL does IBUS go to the level H. Otherwise the IBUS is at the level L. That is only for non write the IBUS goes to 1 . For write the IBUS is 0 . Writing is performed by transferring the data through the SBUS to the sense amplifier unit represented in .

A calculation circuit represented in may be provided per plural sense amplifier units SAU represented in and per plural data control units DCU represented in . In this manner a circuit area can be reduced.

Operation of the calculation circuit can be variously modified. For example various control methods are applicable even to one logic calculation and can be changed upon necessity.

In the present embodiment there are three data latch circuits ADL BDL and XDL. If a write cache for inputting next data during writing is not required XDL may be omitted.

The present NAND flash memory is a multi level memory. Therefore 2 bit data can be stored in one cell. Switching to 2 bit is performed by addresses first and second pages . When storing 2 bit data into one cell 2 pages are used. However when storing 3 bit data into one cell bit numbers are switched by addresses first page second page and third page . When storing 4 bit data into one cell bit numbers are switched by addresses first page second page third page and fourth page .

Next an operation of writing or reading data into or from all cells arranged in one row direction at once will be described with reference to 2 level data.

Reading of 2 level data is performed by using a read level R which corresponds to intermediate threshold voltages between data 1 and data 0 . A verify level V in the write operation is set to be slightly higher than the read level R in order to provide a data retention margin.

As represented in and at first data for one page is externally supplied and is latched by the latch circuit XDL in each of the data storage circuits. Thereafter 2 level data is written into one selected word line. Plural word lines in one block are sequentially selected in an order from a word line WL and data is written into memory cells connected to each of the selected word lines.

Next when the cells MCn are written up to a verify level the threshold voltage of the cells MCn becomes as represented in .

Thereafter when data is written into cells MCn 1 connected to a word line WLn 1 the threshold distribution of the cells MCn becomes as represented in and in accordance with data in the cells MCn 1 and MCn 1.

A threshold voltage of cells MCn is as represented in and due to capacitive coupling between floating gates of the cells MCn connected to the word line WLn and those of the cells MCn 1 and MCn 1 connected respectively to adjacent word lines WLn 1 and WLn 1. Therefore for example as represented in a threshold voltage of memory cells connected to WLn 1 is read when data is read from the memory cells connected to the word line WLn. If data in the memory cells connected to the word line WLn 1 is 1 the read level is set to AR . Otherwise if data in the memory cells connected to the word line WLn 1 is 0 the read level can be read as BR .

However as represented in when simultaneously reading data from plural memory cells connected to one word line the read operation is performed by using both the read levels AR and BR . Thereafter in accordance with data of the word line WLn 1 correct read data between data read by using the read level AR and data read by using the read level BR is taken as read data from the word line WLn.

However as represented in and threshold levels of data 1 differ depending on data of word lines WLn 1 and WLn 1 in the memory cells connected to the word line WLn. Therefore the read operation in is not satisfactory.

Hence according to the first embodiment data in memory cells connected to WLn 1 and data in memory cells connected to WLn 1 are read when reading data from the word line WLn as represented in . Based on the read data a read level for the memory cells connected to WLn is determined. Specifically reading is performed based on the following conditions.

However as represented in data is read simultaneously from plural memory cells connected to one word line i.e. AR BR CR and DR are read. In accordance with data of WLn 1 and WLn 1 a correct data read result is taken as read data from WLn.

Otherwise if arbitrary ones of the levels AR BR CR and DR are close to each other reading may be limited to reading of one of the close levels.

Next a read level VCGRV is applied to the word line WLn 1 and a voltage Vread which turns on cells without fail is applied to the word lines WLn and WLn 1. Data is thereby read from the memory cells connected to the word line WLn 1.

Thereafter a voltage Vread which turns on cells without fail is applied to the word lines WLn 1 and WLn 1. The word line WLn is applied with the read levels AR BR CR and DR in this order and data is thereby read from the word line WLn. Thereafter in accordance with data read from memory cells connected to the word lines WLn 1 and WLn 1 read data from the word line WLn is selected from results of reading the read levels AR BR CR and DR . If a threshold voltage of memory cells in the word line WLn is higher than the read level data becomes 0 . Otherwise if the threshold voltage of memory cells in the word line WLn is lower than the read level data becomes 1 .

According to the first embodiment described above data is read from memory cells connected to the word line WLn 1 which is subjected to the write operation prior to the word line WLn and from memory cells connected to the word line WLn 1 which is subjected to the write operation next to the word line WLn. Based on the read data one of data read from the word line WLn by using read levels AR BR CR and DR is output as read data. Therefore even if a threshold voltage of erase cells connected to the word line WLn is increased due to write data in memory cells connected to adjacent word lines WLn 1 and WLn 1 data can be accurately read from memory cells connected to the word line WLn.

In contrast in the second embodiment represented in when reading a potential of the word line WLn the potential of the word line WLn is made constant and a voltage of an adjacent word line WLn 1 and or a voltage of an adjacent word line WLn 1 is set to a higher potential than Vread and Vread.

If data 0 is written into adjacent cells a threshold level of cells connected to the word line WLn is increased by capacitive coupling between floating gates. This is because electrons have been injected into floating gates of adjacent cells. Therefore if data 0 is written into adjacent cells a voltage Vread supplied to the word lines of the adjacent cells is set to a higher voltage Vread and reading is performed so as to cancel electric charges of electrons injected into the adjacent cells. Here may be a voltage which can cancel an increase of a threshold level caused by capacitive coupling due to electrons injected into the adjacent cells.

Alternatively if Vread is a high voltage and causes a problem of a read disturb Vread of adjacent word lines may be reduced at the time of verify reading during writing and Vread of adjacent word lines is set to a higher value than the voltage at the time of the verify reading. In particular during writing into the word line WLn the threshold voltage of cells in the word line WLn 1 is low and therefore Vread can be reduced. In this case for example Vread and Vread are as represented in where Vread and Vread are respectively Vread for the word lines WLn 1 and WLn 1 during verification. Vread and Vread each satisfy for example Vread

At first as represented in and the word line WLn 1 is applied with read levels VCGRV and the word lines WLn and WLn 1 are applied with a voltage Vread which turns cells on without fail and data is read from memory cells connected to the word line WLn 1.

Next a read level VCGRV is applied to the word line WLn 1 and a voltage Vread which turns cells on without fail is applied to the word lines WLn and WLn 1. Data is thereby read from the memory cells connected to the word line WLn 1.

Thereafter a read level VCGRV substantially equal to AR is applied to the word line WLn and a voltage Vread is applied to the word lines WLn 1 and WLn 1. This potential relationship corresponds to when the read level is set to AR where the word line WLn 1 is 1 and the word line WLn 1 is 1 in the first embodiment.

Next the word line WLn 1 is left at the voltage Vread and the voltage of the word line WLn 1 is set to the voltage Vread . This potential relationship corresponds to when the read level is set to BR where the word line WLn 1 is 1 and the word line WLn 1 is 0 .

Further the voltage of the word line WLn 1 is increased to Vread and the voltage of the word line WLn 1 is maintained at Vread . This potential relationship corresponds to when the read level is set to DR where the word line WLn 1 is 0 and the word line WLn 1 is 0 .

Next the voltage of the word line WLn 1 is maintained at Vread and the voltage of the word line WLn 1 is set to Vread. This potential relationship corresponds to when the read level is set to CR where the word line WLn 1 is 0 and the word line WLn 1 is 1 .

From data read on the potential relationships as described above one item of data is selected and taken as data from the word line WLn based on data concerning the word lines WLn 1 and WLn 1.

In the example in if voltages Vread and Vread are respectively applied to the word lines WLn 1 and WLn 1 and the voltage Vread is set to Vread when reading from memory cells connected to the word line WLn voltages increased from Vread and Vread are applied.

In the second embodiment an order of potentials supplied to the word lines WLn 1 and WLn 1 may be modified and a read order may be changed.

If the levels BR and CR are close to each other only one of BR and CR may be read. Alternatively if arbitrary ones of the levels AR BR CR and DR are close to each other reading may be limited to reading of one of the close levels.

According to the second embodiment as described above with a constant read level VCGRV substantially equal to AR applied to the word line WLn the read levels Vread and Vread are sequentially applied to the word lines WLn 1 and WLn 1. In this manner any influence of the threshold voltages of memory cells connected to the word lines WLn 1 and WLn 1 is suppressed and data can be accurately read from memory cells connected to the word line WLn.

In addition there is no need of generating plural read levels AR BR CR and DR . Therefore a simplified circuit configuration can be achieved. Further read operations using the plural read levels AR BR CR and DR are not required. Therefore high speed read operations can be achieved in some cases.

At first one bit of 2 bit data is written into one memory cell based on a write sequence for the first page lower page as represented in . That is data for the first page is loaded from outside into a data latch circuit in the data storage circuit S . Thereafter a write operation and a verify operation for the first page are performed based on data in the data latch circuit S S . An operation as described above is repeated until data for one page is all written S S .

Thereafter writing into adjacent cells is performed in the same write sequence as represented in . By writing into adjacent cells threshold voltages of memory cells which have been written early shift under the influence of coupling between cells .

Next the remaining one bit of 2 bit data is written based on a write sequence for the second page upper page represented in . That is data for the second page is loaded into the data latch circuit S . Thereafter data for the first page which has been written first is read by internal data reading S . This read operation is to read 2 level data. Therefore the read operation described in the publication No. 2004 326866 or the read operation described in the first or second embodiment is applicable. In particular it is desirable when data read by the internal data reading is not corrected by ECC but is taken as write data for the second page because highly accurate reading is required. By the read operation as described above read accuracy can be improved. Based on the read data and data loaded into the data latch circuit data for the data latch circuit is operated and write data for the second page is set S . Based on this set data a write operation for the second page is performed S . Thereafter a verify operation is performed by using three verify levels corresponding to write data S to S . This verify level is set to levels which are slightly lower than an original verify level. The operation as described above is repeated until all data is written S to S . In this manner 4 level data is roughly written .

Next data for the second page is written into adjacent cells in the same manner as described above. Accordingly a threshold voltage which has been written before shifts under the influence of coupling between cells .

Thereafter 2 bit data to be stored into one memory cell is written again by using an original verify level . Although the 2 bit data to be written may be supplied externally 2 bit write data may be recovered from a roughly written 4 level threshold distribution as represented in . For a read operation when recovering the 2 bit write data the read operation described in the foregoing publication No. 2004 326866 or the read operation described in the first or second embodiments can be used.

Subsequently as writing into adjacent cells is performed in the same manner as described above a slight shift takes place .

As described above in memory cells in which data 1 2 and 3 as represented in B C D E F and G are written threshold voltages corresponding to the data 1 2 and 3 suppress influence of coupling between cells and therefore sufficient margins are ensured. However a threshold voltage of an erased cell namely a cell into which data 0 is written increases in accordance with writing into adjacent cells.

Hence in the third embodiment read levels are set in accordance with a variability range of the threshold voltage of erase cells. That is a threshold voltage of erase cells connected to the word line WLn is 0V as denoted by an arrow of a broken line in and the read level is set to AR . If change of a threshold voltage is within a range of 0.15V to 0.3V the read level is set to BR . Alternatively if change of the threshold voltage is within a range of 0.35V to 0.5V the read level is set to CR . Still alternatively if change of the threshold voltage is 0.6V or more the read level is set to DR .

For example if data 0 is written into cells connected to the word line WLn 1 and if data 2 is written into cells connected to the word line WLn 1 the read level is set to BR . If data 3 is written into the word line WLn 1 and if data 1 is written into cells connected to the word line WLn 1 the read level is set to CR .

According to the third embodiment described above read levels of erased cells are changed on the basis of data written into adjacent cells selected by the word lines WLn 1 and WLn 1. Therefore even if a threshold voltage of erased cells is increased by writing into adjacent cells data can be steadily read.

In the present embodiment a read potential for the word line WLn is changed when reading the word line WLn. However levels of Vread for adjacent word lines WLn 1 and WLn 1 may be changed without changing the read potential for the word line WLn as in the second embodiment.

Further as represented in data is read simultaneously from plural cells connected to one word line. Therefore AR BR CR and DR are read and a result of accurately reading data may be taken as read data from the word line WLn in accordance with data from the word lines WLn 1 and WLn 1.

Each of the embodiments described above has been described where 2 level or 4 level data is read. However the embodiments are not limited to 2 level data and 4 level data but are applicable where 3 value 8 level or 16 level data is read.

In each of the embodiments when reading data from the memory cell connected to the word line WLn read conditions for the memory cell are changed in accordance with the word line WLn 1 which is adjacent to the word line WLn. The data is selected by using appropriate read conditions from two or more data read from the memory cell by using two or more read conditions. However it is not limited to this. When reading data from the memory cell it may be connected to the same word line as the memory cell and may read using the data of the memory cell and an adjoining memory cell and the data of the memory cell which exists in a slanting position to the memory cell and conditions may be changed.

While certain embodiments have been described these embodiments have been presented by way of example only and are not intended to limit the scope of the inventions. Indeed the novel embodiments described herein may be embodied in a variety of other forms furthermore various omissions substitutions and changes in the form of the embodiments described herein may be made without departing from the spirit of the inventions. The accompanying claims and their equivalents are intended to cover such forms or modifications as would fall within the scope and spirit of the inventions.

