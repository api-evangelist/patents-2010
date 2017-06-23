---

title: Information processing apparatus, interrupt control device and interrupt control method
abstract: An information processing device in which interrupts are generated when some events are occurred. The information processing device includes: an interrupt generating unit to generate an interrupt; an interrupt control unit to receive the generated interrupt, count an interrupt reception count per unit time, notify of the interrupt and delay, if the counted interrupt reception count per unit time exceeds a predetermined value, the interrupt notification; and an interrupt processing unit to process the notified interrupt.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08386683&OS=08386683&RS=08386683
owner: Fujitsu Limited
number: 08386683
owner_city: Kawasaki
owner_country: JP
publication_date: 20100930
---
This is a continuation of Application PCT JP2008 056377 filed on Mar. 31 2008 now pending the entire contents of which are herein wholly incorporated by reference.

The embodiments discussed herein are related to an information processing apparatus an interrupt control device and an interrupt control method.

As broadly known over the recent years a variety of communication standards having higher communication speeds such as Ethernet trademark of Xerox Corp. in U.S.A. or Fibre Channel have been developed and there have been an increased number of computers each mounted with a communication adaptor an expansion card functioning as a communication interface pursuant to these types of communication standards.

The normal communication adaptor is contrived to interrupt a CPU Central Processing Unit via a PCI Peripheral Components Interconnect bus and a host bridge each time a process transmission or reception related to one piece of data is completed. Therefore an interrupt count per unit time when the communication adaptor interrupts the CPU rises as the communication speed increases. Then if a plurality of communication adaptors operating fast is mounted in the computer such a problem arises that a considerable load is applied to the CPU.

According to an aspect of the embodiment an information processing device includes an interrupt generating unit to generate an interrupt an interrupt control unit to receive the generated interrupt count an interrupt reception count per unit time notify of the interrupt and delay if the counted interrupt reception count per unit time exceeds a predetermined value the interrupt notification and an interrupt processing unit to process the notified interrupt.

According to another aspect of the embodiment an information processing device includes an interrupt generating unit to generate an interrupt an interrupt control unit to receive the generated interrupt delay the received interrupt notification and notify of when receiving a first new interrupt from the interrupt generating unit while delaying the interrupt notification the interrupt with its notification delayed and the received first new interrupt and an interrupt processing unit to process the notified interrupt.

Note that the operation related to the information processing device disclosed above can be realized by an interrupt control method or an interrupt control program stored on a computer readable medium.

The object and advantages of the embodiments will be realized and attained by means of the elements and combinations particularly pointed out in the claims.

It is to be understood that both the foregoing general description and the following detailed description are exemplary and explanatory and are not restrictive of the invention as claimed.

Three examples of a computer will hereinafter be discussed by way of embodiments of an information processing device disclosed herein with reference to the drawings.

As illustrated in the computer in the first embodiment includes a display device such as a liquid crystal display etc. an operation device such as a keyboard a mouse etc. and a main body connected to these devices and . The main body is connected to a network N.

As depicted in the main body incorporates a communication adaptor a super I O Input Output controller a boot memory a hard disk drive a CPU Central Processing Unit a main memory a graphics controller a south bridge performing a role of an integrated I O controller and a north bridge performing a role of a memory controller.

The communication adaptor is a device which transfers and receives data to and from other computers on the network N. The communication adaptor is exemplified such as an Ethernet expansion card and a fibre channel expansion card.

The super I O controller is a device which transfers and receives the data to and from a device connected via an I O port such as a PS 2 Personal System 2 port. The operation device in is connected to this super I O controller .

The boot memory is a flash memory recorded with a BIOS Basic Input Output System program that is executed immediately after starting the computer .

The hard disk drive is a device which executes writing and reading to and from the hard disk defined as a disk medium. The hard disk is as will be described later on recorded with various categories of software such as operating system OS software network driver software and application software.

The CPU is a device which executes the processes according to the programs in the boot memory and the hard disk drive .

The main memory is a unit used for the CPU to cache the programs and the data and to deploy a working area.

The graphics controller is a device which generates and outputs a video signal based on rendering data transferred from the CPU . The display device in is connected to this graphics controller .

The south bridge is an LSI Large Scale Integration mounted with controllers for controlling a PCI Peripheral Components Interconnect device an LPC Low Pin Count device and an ATA Advanced Technology Attachment device respectively. The super I O controller is connected via the LPC bus to the south bridge and the hard disk drive is connected via an ATA bus to the south bridge . Further in the first embodiment the first through Nth communication adaptors are connected via the PCI bus to the south bridge .

Furthermore the south bridge performing the role of the integrated I O controller is mounted with a controller for controlling access to the boot memory and with a DMA Direct Memory Access controller serving as an access controller. The DMA controller is a controller for transmitting the data within the hard disk drive to the main memory without via the CPU .

Moreover the south bridge is mounted with an interrupt controller . The interrupt controller is a controller for monitoring occurrence of the interrupt at the PCI device the communication adaptor in the first embodiment and notifying the CPU of the occurred interrupt as a hardware interrupt.

The north bridge performing the role of the memory controller is an LSI on which controllers are mounted which respectively control the CPU the main memory and the graphics controller . To the north bridge the CPU is connected via a system bus the main memory is connected to via a memory bus and the graphics controller is connected via an AGP Accelerated Graphics Port bus.

Further the north bridge implements a bus bus bridge function of controlling the data transfer between the CPU and the south bridge and is connected via a dedicated bus to the south bridge . The dedicated bus is exemplified by A Link trademark of Ali Corp. in Taiwan Hyper Transport trademark of Advanced Micro Devices Inc. AMD in U.S.A. MuTIOL trademark of Silicon Integrated Systems Corp. in Taiwan and V Link trademark of VIA Technology Corp. in Taiwan 

As illustrated in the communication adaptor includes an interface module a ROM Read Only Memory and a controller . The interface module is a module for transferring and receiving the data to and from the devices on the network N. The ROM is a device recorded with information on the communication adaptor . The controller is a device for controlling the communication adaptor .

The controller includes a communication protocol control unit a PCI interface control unit and an interrupt control unit .

The communication protocol control unit is a unit which controls the communications based on a communication protocol. The communication protocol control unit is contrived to generate an interrupt upon detecting a predetermined event. Note that the event as a factor of the interrupt generation is exemplified such as normal completion of I O an abnormal end of I O receiving a frame and detecting an error of the hardware.

It should be noted that the communication protocol control unit corresponds to the interrupt occurrence unit described above.

The PCI interface control unit is a unit for transferring and receiving via data lines within the PCI bus the data to and from the PCI device connected to the PCI bus and for notifying of the interrupt via an interrupt line within the PCI bus. The PCI interface control unit includes a register recorded with as an interrupt factor the event becoming the factor for the interrupt generation.

The interrupt control unit is a unit for controlling the interrupt. To be specific the interrupt control unit notifies the interrupt controller in of the interrupt generated by the communication protocol control unit and records the interrupt factor in the register of the PCI interface control unit . Further the interrupt control unit includes a register recorded with an upper limit value count sec of an interrupt notification count per unit time. The interrupt control unit controls the interrupt notification so that the interrupt notification count per unit time does not exceed the upper limit value recorded in the register . For example if the upper limit value of the interrupt notification count per unit time is set to 10 000 count per sec the interrupt control unit stops the interrupt notification at a point of time when the interrupt notification count per sec reaches 10 000 count then stands by till next 1 sec starts and is enabled to make the interrupt notification upon the start of next 1 sec.

Note that the interrupt control unit if only one interrupt factor occurs for a period till the next notification is done since the interrupt notification was executed as illustrated in a sequence diagram in notifies a communication adaptor driver which will be explained later on of one interrupt factor e.g. one factor which triggers a process A in in the interrupt notification given once. On the other hand two or more events each becoming the interrupt factor occur for the period till the next notification is done since the interrupt notification was executed the interrupt control unit notifies as illustrated in a sequence diagram in the communication adaptor driver which will be explained later on of plural interrupt factors e.g. three factors which trigger the processes A through C in in the interrupt notification given once.

In the computer the hard disk drive is stored with a user application a statistic information generation demon the communication adaptor driver and operating system software

The user application is software for realizing services such as a document edit service a spreadsheet service a rendering service and a Web page browsing service on the computer . This user application is a Web browser or a mailer in which case the user application performs the communications with a Web server or a mail server via the communication adaptor driver

The statistic information generation demon is a program for setting in the communication adaptor the upper limit value count sec of the interrupt notification count per unit time on the basis of an interrupt notification count per unit time from the communication adaptor and a system load defined as a ratio usage ratio at which the time for the CPU to execute the process related to this communication adaptor occupies the unit time. The same number of the statistic information generation demons as the number of the communication adaptor drivers are prepared in the computer . Note that a content of the process executed by the CPU according to the statistic information generation demon will be described later on with reference to .

The communication adaptor driver is software for controlling the communication adaptor . The same number of the communication adaptor drivers as the number of communication adaptors are prepared in the computer . The communication adaptor driver includes a basic control module a hardware control module and a setting control module .

The basic control module is a module which transmits a command to the communication adaptor transfers and receives the data between the user application and the communication adaptor transmits the command to the communication adaptor and executes a process corresponding to the interrupt factor related to the interrupt generated by the communication protocol control unit of the communication adaptor .

The hardware control module is a module which converts formats of data and commands between the basic control module and the communication adaptor .

The setting control module is a module for controlling the information set in the communication adaptor . A content of the process executed by the CPU according to this setting control module will be described later on with reference to .

The operating system software is software for providing an API Application Programming Interface and an ABI Application Binary Interface to the variety of applications managing the storage areas of the hard disk drive and the main memory managing a process and a task providing utilities such as file management the variety of setting tools and editors to the applications and allocating windows to a plurality of tasks for multiplexing the screen outputs.

The operating system software includes a function of monitoring the interrupt notification given from the communication adaptor . Further this operating system software includes a function of executing upon detecting the interrupt notification a process a process X in and of acquiring the interrupt factor from the register of the PCI interface control unit of the communication adaptor and transferring this interrupt factor to the communication adaptor driver

More specifically the operating system software executes upon detecting the interrupt notification given from the communication adaptor the process related to the interrupt on the basis of a predetermined interrupt priority level. Note that the main interrupts are sequenced in the order from the highest priority level such as a PIO Programmed I O serial interrupt a clock interrupt an interrupt from the communication adaptor an interrupt related to the access to the disk device and a software interrupt. The operating system software determines when detecting the interrupt notification whether the priority level of the process related to an in execution interrupt at that point of time is higher or lower than the priority level of the interrupt of which the notification is detected. Then if the priority level of the interrupt of which the notification is detected is higher the operating system software prioritizes the process related to the interrupt of which the notification is detected in a way that suspends the in execution process at that point of time and gets the process related to this interrupt to stand by if the priority level of the interrupt of which the notification is detected is lower. Further the operating system software acquires if an interrupt notifying destination is the communication adaptor one or more interrupt factors from the register of the PCI interface control unit of the communication adaptor and invokes an interrupt handler within the basic control module in the communication adaptor driver the process X in . It is to be noted that this interrupt handler carries out processes the processes A through C in corresponding to one or more interrupt factors and clears the register of the PCI interface control unit of the communication adaptor . The operating system software when the interrupt handler finishes the processes executes a process of getting the suspended process to resume a process Y in .

Note that the CPU executing the operating system software and the CPU executing the basic control module and the hardware control module of the communication adaptor driver correspond to the interrupt processing unit described above.

After switching on the main power source of the computer the CPU reads the statistic information generation demon thereby starting a statistic information generation process.

After starting the statistic information generation process in first step S the CPU reads an upper limit value of the system load. This upper limit value of the system load is previously included in the communication adaptor driver corresponding thereto and implies an upper limit value of the system load which is a ratio at which the time for the CPU to execute the process related to this communication adaptor occupies the unit time i.e. the usage ratio accompanying the operation of the communication adaptor controlled by the communication adaptor driver . Upon reading the upper limit value of the system load the CPU advances the processing to step S.

In step S the CPU acquires the notification count per unit time of the corresponding communication adaptor from the hardware control module via the setting control module .

In next step S the CPU calculates the upper limit value count sec of the interrupt notification count per unit time. To be specific the CPU to begin with divides the upper limit value of the system load read in step S over the system load acquired in step S and subsequently multiplies the value obtained from this division by the interrupt notification count count sec per unit time that is acquired in step S. The CPU calculates the upper limit value count sec of the interrupt notification count per unit time by this arithmetic formula .

In subsequent step S the CPU sets the upper limit value calculated in step S in the communication adaptor driver

In next step S the CPU stands by for a fixed period of time and thereafter loops the processing back to step S.

According to the statistic information generation process described above it follows that the upper limit value per unit time is periodically set in the communication adaptor driver

After switching on the main power source of the computer the CPU reads the setting control module thereby starting the setting control process.

After starting the setting control process in first step S the CPU reads the upper limit value of the interrupt notification count per unit time that is set in the communication adaptor driver

In next step S the CPU acquires the interrupt notification count I count sec per unit time of the corresponding communication adaptor from the hardware control module .

In next step S the CPU determines whether or not the interrupt notification count I per unit time that is acquired in step S exceeds the upper limit value read in step S. Then if the interrupt notification count I per unit time exceeds the upper limit value the CPU advances the processing to step S.

In step S the CPU sets the upper limit value count sec of the interrupt notification count per unit time that is read in step S in the communication adaptor via the hardware control module . Note that the controller of the communication adaptor records the upper limit value of the interrupt notification count per unit time in the register within the interrupt control unit . Thereafter the CPU advances the processing to step S.

While on the other hand in step S if the interrupt notification count I count sec per unit time acquired in step S is equal to or lower than the upper limit value count sec read in step S the CPU diverts the processing to step S from step S.

In step S the CPU changes the upper limit value set in the communication adaptor to the infinity. Thereafter the CPU advances the processing to step S.

In step S the CPU stands by for a fixed period of time and thereafter loops the processing back to step S.

According to the setting control process described above if the interrupt notification count I per unit time of the corresponding communication adaptor exceeds the upper limit value set in the statistic information generation process it follows that the interrupt notification by the communication adaptor is restricted.

It should be noted that the CPU executing the statistic information generation process and the setting control process and the interrupt control unit within the controller of the communication adaptor correspond to the interrupt control unit described above.

As discussed above in the first embodiment the statistic information generation demon periodically sets the upper limit value of the interrupt notification count per unit time in the corresponding communication adaptor driver on the basis of the upper limit value of the system load of the corresponding communication adaptor the actually measured system load and the interrupt notification count per unit time steps S S .

Further the setting control module executed in parallel with this statistic information generation demon periodically determines whether or not the interrupt notification count I per unit time actually measured with respect to the corresponding communication adaptor exceeds the upper limit value steps S S and if the interrupt notification count I per unit time exceeds the upper limit value restricts the interrupt of the communication adaptor step S Yes S .

The operating system software called e.g. Solaris trademark of Sun Microsystems in U.S.A. when receiving a command named mpstat gives a reply of the system load usage ratio per CPU .

As given in an intr field in the example of the reply in the CPU having the number 1 receives the interrupt notifications counted 20000 per sec 20000 . Further as given in a sys field in the example of the reply in the CPU having the number 1 is 60 in its system load usage ratio 60 .

Then with respect to one of the communication adaptor drivers within the computer in the first embodiment if 30 is set in the upper limit value 30 of the system load of the CPU having the number 1 which accompanies the operation of the communication adaptor corresponding to the one communication adaptor driver the interrupt notification count per unit time has substantially a proportional relation with the system load and hence the upper limit value of the interrupt notification count per unit time of the communication adaptor is estimated such as 30 60 20000 10000 count sec step S .

Herein an assumption is that the time required for the operating system software to execute the process the process X in of acquiring the interrupt factor is on the order of 2 sec the average time required for the basic control module of the communication adaptor driver to execute the process for one interrupt factor is on the order of 10 sec and the time taken for the operating system software to execute a subsequent stage process a process Y in after the communication adaptor driver has executed the process corresponding to the interrupt factor is on the order of 2 sec.

Then supposing that one interrupt factor is transferred to the communication adaptor driver through the one interrupt notification the CPU having the number 1 illustrated in receives the interrupt notifications counted 20000 per second and hence the time taken for the interrupt process per second is given such as 20000 2 10 2 280000 sec. Note that the processing time of the CPU per interrupt notification is given by 280000 20000 14 sec.

On the other hand in the first embodiment if the upper limit value of the interrupt notification count per unit time of the communication adaptor is restricted to 10000 count sec the processes are executed for 20000 pieces of interrupt factors with respect to the interrupt notifications counted 10000 per second and therefore the time taken for the CPU having the number 1 illustrated in to execute the interrupt process is given by 20000 10 10000 2 2 240000 sec. Note that the processing time of the CPU per interrupt notification is given by 240000 10000 24 sec.

Accordingly in the first embodiment the time taken for the CPU having the number 1 illustrated in to execute the interrupt process is reduced by about 15 240000 280000 0.857 . are sequence diagrams illustrating a state where the time taken for the CPU to execute the interrupt process is reduced by approximately 15 .

It should be noted that in the first embodiment discussed above the upper limit value of the interrupt notification count per unit time is dynamically set in the communication adaptor driver through the statistic information generation process in however this upper limit value may also be statically set in a setting file of the communication adaptor driver

A second embodiment is different from the first embodiment in terms of such a point that not the upper limit value count sec of the interrupt notification count per unit time but the lower limit value 1 sec count of the interrupt notification interval is set in the communication adaptor . The hardware configuration and the software configuration other than this different point in the second embodiment are the same as in the first embodiment.

The interrupt control unit of the communication adaptor in the second embodiment includes a register recorded with the lower limit value 1 sec count of the interrupt notification interval. The interrupt control unit controls the interrupt notification so that the interrupt notification interval does not exceed the lower limit value 1 recorded in the register . For example if 1 10000 sec per count is the lower limit value 1 of the interrupt notification interval the interrupt control unit after making the one interrupt notification stops the interrupt notification till an elapse of 1 10000 sec and stops the interrupt notification at a point of time when the interrupt notification reaches 10000 count after 1 sec and after the elapse of 1 10000 sec the next interrupt notification can be made.

Note that the interrupt control unit if only one event becoming the interrupt factor occurs till the next notification is made after the interrupt notification has been made as illustrated in the sequence diagram of notifies the communication adaptor driver of one interrupt factor e.g. one factor which triggers the process A in in the interrupt notification made once. On the other hand if two or more events each becoming the interrupt factor occurs for the period till the next notification is done since the interrupt notification was executed the interrupt control unit notifies as illustrated in the sequence diagram in the communication adaptor driver which will be explained later on of plural interrupt factors e.g. three factors which trigger the processes A through C in in the interrupt notification given once.

The communication adaptor driver in the second embodiment includes a setting control module . The setting control module executes a process slightly different from the process by the setting control module in the first embodiment.

After switching on the main power source of the computer the CPU reads the setting control module thereby starting a setting control process.

After starting the setting control process in first step S the CPU reads the upper limit value count sec of the interrupt notification count per unit time that is set in the communication adaptor driver

In next step S the CPU acquires the interrupt notification count I count sec per unit time of the corresponding communication adaptor from the hardware control module .

In next step S the CPU determines whether or not the interrupt notification count I per unit time that is acquired in step S exceeds the upper limit value read in step S. Then if the interrupt notification count I per unit time exceeds the upper limit value the CPU advances the processing to step S.

In step S the CPU sets in the communication adaptor the lower limit value 1 sec count of the interrupt notification interval per unit time which is an inverse number of the upper limit value count sec of the interrupt notification count per unit time that is read in step S via the hardware control module . Note that the controller of the communication adaptor records the lower limit value 1 of the interrupt notification interval in the register within the interrupt control unit . Thereafter the CPU advances the processing to step S.

While on the other hand in step S if the interrupt notification count I count sec per unit time acquired in step S is equal to or lower than the upper limit value count sec read in step S the CPU diverts the processing to step S from step S.

In step S the CPU changes the lower limit value 1 set in the communication adaptor to zero. Thereafter the CPU advances the processing to step S.

In step S the CPU stands by for a fixed period of time and thereafter loops the processing back to step S.

According to the setting control process described above if the interrupt notification count I per unit time of the corresponding communication adaptor exceeds the upper limit value set in the statistic information generation process it follows that the interrupt notification by the communication adaptor is restricted.

In the second embodiment also similarly to the first embodiment the statistic information generation demon periodically sets the upper limit value of the interrupt notification count per unit time in the corresponding communication adaptor driver on the basis of the upper limit value of the system load of the corresponding communication adaptor the actually measured system load and the interrupt notification count per unit time steps S S in .

Further the setting control module executed in parallel with this statistic information generation demon periodically determines whether or not the interrupt notification count I per unit time actually measured with respect to the corresponding communication adaptor exceeds the upper limit value steps S S and if the interrupt notification count I per unit time exceeds the upper limit value restricts the interrupt of the communication adaptor step S Yes S .

For example as stated above the CPU having the number 1 illustrated in receives the interrupt notifications counted 20000 per unit time 20000 and is 60 in its system load usage ratio 60 in which case the upper limit value of the system load of the CPU is set to 30 30 and the upper limit value of the interrupt notification count per unit time is estimated 10000 count sec step S. Then I 20000 with the result that 1 1 10000 is set in the communication adaptor step S .

Then it is assumed that the time required for the operating system software to execute the process the process X in of acquiring the interrupt factor is on the order of 2 sec the average time required for the basic control module of the communication adaptor driver to execute the process for one interrupt factor is on the order of 10 sec and the time taken for the operating system software to execute the subsequent stage process the process Y in after the communication adaptor driver has executed the process corresponding to the interrupt factor is on the order of 2 sec.

Then supposing that one interrupt factor is transferred to the communication adaptor driver through the one interrupt notification the CPU having the number 1 illustrated in receives the interrupt notifications counted 20000 per unit time and hence the time taken for the interrupt process is given such as 20000 2 10 2 280000 sec. Note that the processing time of the CPU per interrupt notification is given by 280000 20000 14 sec.

On the other hand in the second embodiment if the lower limit value of the interrupt notification interval of the communication adaptor is restricted to 1 10000 sec the lower limit value of the interrupt notification interval increases twice and therefore the two interrupt factors on the average are transferred to the communication adaptor driver through the one interrupt notification. Accordingly the time taken for the CPU having the number 1 illustrated in to execute the interrupt process is given by 20000 10 10000 2 2 240000 sec. Note that the processing time of the CPU per interrupt notification is given by 240000 10000 24 sec.

Accordingly in the second embodiment also the time taken for the CPU having the number 1 illustrated in to execute the interrupt process is reduced by about 15 240000 280000 0.857 . are sequence diagrams illustrating a state where the time taken for the CPU to execute the interrupt process is reduced by approximately 15 .

A third embodiment is different from the first and second embodiments in terms of taking not the scheme of setting some threshold values in the communication adaptor but a scheme that the software controls interrupt permission and interrupt inhibition with respect to the communication adaptor . The hardware configuration and the software configuration other than this different point in the third embodiment are the same as in the first and second embodiments.

The third embodiment does not involve using the register of the interrupt control unit of the communication adaptor . Further in the third embodiment the PCI interface control unit of the communication adaptor includes a register recorded with the interrupt factor and a register recorded with an interrupt permitting or inhibiting instruction. The interrupt control unit if the interrupt inhibiting instruction is recorded in the register does not notify the CPU of the interrupt.

Note that the interrupt control unit if only one event becoming the interrupt factor occurs till the next notification is made after the interrupt notification has been made as illustrated in the sequence diagram of notifies the communication adaptor driver of one interrupt factor e.g. one factor which triggers the process A in in the interrupt notification made once. On the other hand if two or more events each becoming the interrupt factor occurs for the period till the next notification is done since the interrupt notification was executed the interrupt control unit notifies as illustrated in the sequence diagram in the communication adaptor driver which will be explained later on of plural interrupt factors e.g. three factors which trigger the processes A through C in in the interrupt notification given once.

The communication adaptor driver in the third embodiment includes a setting control module . The setting control module executes a process slightly different from the processes by the setting control modules in the first and second embodiments.

After switching on the main power source of the computer the CPU reads the setting control module thereby starting the setting control process.

After starting the setting control process in first step S the CPU reads the upper limit value count sec of the interrupt notification count per unit time that is set in the communication adaptor driver

In next step S the CPU acquires the interrupt notification count I count sec per unit time of the corresponding communication adaptor from the hardware control module . Note that the communication adaptor is inhibited from interrupting in a processing step which will be described later on in which case the interrupt notification count I count sec per unit time is calculated based on the number of the interrupt factors acquired per unit time in step S that will be described later on.

In next step S the CPU determines whether or not the interrupt notification count I per unit time that is acquired in step S exceeds the upper limit value read in step S. Then if the interrupt notification count I per unit time exceeds the upper limit value the CPU advances the processing to step S.

In step S the CPU sets the interrupt inhibiting instruction in the communication adaptor . Note that the controller of the communication adaptor records the interrupt inhibiting instruction in the register within the PCI interface control unit .

In next step S the CPU executes a process of calculating 1 that is an inverse number of the upper limit value count sec of the interrupt notification count per unit time that is read in step S and checking whether or not the interrupt factor is recorded in the register within the PCI interface control unit of the communication adaptor at an interval of 1 sec. Further the CPU as a result of checking if the interrupt factor is recorded in the register executes also a process of invoking an interrupt handler within the basic control module in the communication adaptor driver . The CPU after executing the process of monitoring how the interrupt factor described above is generated for the fixed period of time loops the processing back to step S.

While on the other hand in step S if the interrupt notification count I count sec per unit time acquired in step S is equal to or lower than the upper limit value count sec read in step S the CPU diverts the processing to step S from step S.

In step S the CPU sets the interrupt permitting instruction in the communication adaptor . Note that the controller of the communication adaptor records the interrupt permitting instruction in the register within the PCI interface control unit .

In step S the CPU stands by for the fixed period of time and thereafter loops the processing back to step S.

According to the setting control process described above if the interrupt notification count I per unit time of the corresponding communication adaptor exceeds the upper limit value set in the statistic information generation process it follows that the interrupt notification by the communication adaptor is restricted.

In the third embodiment also similarly to the first and second embodiments the statistic information generation demon periodically sets the upper limit value of the interrupt notification count per unit time in the corresponding communication adaptor driver on the basis of the upper limit value of the system load of the corresponding communication adaptor the actually measured system load and the interrupt notification count per unit time steps S S in .

Further the setting control module executed in parallel with this statistic information generation demon periodically determines whether or not the interrupt notification count I per unit time actually measured with respect to the corresponding communication adaptor exceeds the upper limit value steps S S and if the interrupt notification count I per unit time exceeds the upper limit value restricts the interrupt of the communication adaptor step S Yes S .

For example as stated above the CPU having the number 1 illustrated in receives the interrupt notifications counted 20000 per unit time 20000 and is 60 in its system load usage ratio 60 in which case the upper limit value of the system load of the CPU is set to 30 30 and the upper limit value of the interrupt notification count per unit time is estimated 10000 count sec step S. Then I 20000 so that the interrupt inhibiting instruction is set in the communication adaptor step S and the generation of the interrupt factor is checked at an interval of 1 sec step S .

Then as illustrated in it is assumed that the time required for the setting control module of the communication adaptor driver to execute the process the process X in of acquiring the interrupt factor is on the order of 2 sec the average time required for the basic control module of the communication adaptor driver to execute the process for one interrupt factor is on the order of 10 sec and the time taken for executing the subsequent stage process the process Yin after the communication adaptor driver has executed the process corresponding to the interrupt factor is on the order of 2 sec.

Then supposing that one interrupt factor is transferred to the communication adaptor driver through the one interrupt notification the CPU having the number 1 illustrated in receives the interrupt notifications counted 20000 per unit time and hence the time taken for the interrupt process is given such as 20000 2 10 2 280000 sec. Note that the processing time of the CPU per interrupt notification is given by 280000 20000 14 sec.

On the other hand in the third embodiment if the communication adaptor is inhibited from interrupting and if an interrupt factor acquiring interval of the communication adaptor driver is set such as 1 1 10000 sec the interrupt notification interval substantially increases twice and it therefore follows that the two interrupt factors on the average are transferred to the communication adaptor driver through the one interrupt notification. Accordingly the time taken for the CPU having the number 1 illustrated in to execute the interrupt process is given by 20000 10 10000 2 2 240000 sec. Note that the processing time of the CPU per interrupt notification is given by 240000 10000 24 sec.

Accordingly in the third embodiment also the time taken for the CPU having the number 1 illustrated in to execute the interrupt process is reduced by about 15 240000 280000 0.857 . are sequence diagrams illustrating a state where the time taken for the CPU to execute the interrupt process is reduced by approximately 15 .

In the first through third embodiments discussed above the respective units in the controller may each be constructed of a software component and a hardware component and may also be constructed of only the hardware component.

The software component can be exemplified by an interface program a driver program a table and data and by a combination of some of these components. These components may be stored on a computer readable medium that will be explained later on and may also be firmware that is fixedly incorporated into a storage device such as a ROM Read Only Memory and an LSI Large Scale Integration .

Moreover the hardware component can be exemplified by an FPGA Field Programmable Gate Array an ASIC Application Specific Integrated Circuit a gate array a combination of logic gates a signal processing circuit an analog circuit and other types of circuits. Among these components the logic gate may include an AND an OR a NOT a NAND a flip flop a counter circuit and so on. Moreover the signal processing circuit may include circuit elements which execute addition multiplication subtraction inversion a sum of products operation differentiation and integration of signal values. Further the analog circuit may include circuit elements which execute amplification addition multiplication differentiation integration etc.

Note that the components building up the units in the controller are not limited to those exemplified above but may be other components equivalent thereto.

In the first through third embodiments discussed above the pieces of software in the main body of the computer and the software components described above may each include elements such as a software component a procedure oriented language based component an object oriented software component class software a component managed as a task a component managed as a process as a function an attribute a procedure a subroutine software routine a fragment or segment of a program code a driver firmware a microcode a code a code segment an extra segment a stack segment a program area a data area data a database a data structure a field a record a table a matrix table an array a variable and a parameter.

Further the pieces of software in the main body of the computer and the software components described above may each be described in a C language C Java trademark of Sun Microsystems in U.S.A. Visualbasic trademark of Microsoft Corp. in U.S.A. Perl Ruby and other programming languages.

Moreover the instruction the code and the data contained in the pieces of software in the main body of the computer and the software components described above may be transmitted to or loaded into a computer or a computer embedded into a machine or a system via a wired network card and a wired network or via a wireless card and a wireless network.

In the transmission or loading described above the data signals flow via the wired network or the wireless network in the way of their being carried on e.g. carrier waves subcarriers . The data signals may also be however transferred intact as so called baseband signals without depending on the carrier waves described above. These carrier waves are transmitted in an electric magnetic or electromagnetic mode an optical mode an acoustic mode or other modes.

Herein the wired network or the wireless network is a network built up by e.g. a telephone line a network line a cable including an optical cable and a metallic cable a wireless link a mobile phone access line a PHS Personal Handyphone System network a wireless LAN Local Area Network Bluetooth trademark of the Bluetooth Special Interest Group on vehicle wireless type communications including DSRC Dedicated Short Range Communication and a network constructed of any one of those given above. Then the data signals are used for transmitting the information including the instruction the code and the data to a node or the component on the network.

Note that the components configuring the pieces of software in the main body of the computer and the software components described above are not limited those exemplified above and may also be other components equivalent thereto.

Any one of the functions in the first through third embodiments discussed above may be coded and thus stored in a storage area on the computer readable medium. In this case the program for utilizing the function can be provided to the computer or the computer embedded into the machine or the system via the computer readable medium. The computer or the computer embedded into the machine or the system reads the program from the storage area on the computer readable medium and executes the program thereby enabling the function thereof to be utilized.

Herein the computer readable medium connotes a recording medium capable of accumulating information such as the program and the data by electrical magnetic optical chemical physical or mechanical action and retaining the information in a readable by computer status.

The electrical or magnetic action can be exemplified by writing the data to the element on the ROM Read Only Memory constructed by use of a fuse. The magnetic or physical action can be exemplified by a phenomenon of toners to form a latent image on a paper medium. Note that the information recorded on the paper medium can be read e.g. optically. The optical and chemical action can be exemplified by forming a thin film or a rugged portion on a substrate. Incidentally the information recorded in the ruggedness utilized mode can be read e.g. optically. The chemical action can be exemplified by oxidation reduction reaction on the substrate forming an oxide film or a nitride film on a semiconductor substrate or a photo resist phenomenon. The physical or mechanical action can be exemplified by forming a rugged portion on an emboss card or forming a punch hole in the paper medium.

Moreover in the computer readable mediums some mediums can be detachably attached to the computer or the computer embedded into the machine or the system. The attachable detachable computer readable medium can be exemplified by a DVD including DVD R DVD RW DVD ROM DVD RAM a R RW a BD including BD R BD RE BD ROM a CD Compact Disk including CD R CD RW CD ROM an MO Magneto Optical disk other optical disk mediums a flexible disk including a floppy disk Floppy is a trademark of Hitachi Ltd. other magnetic disk mediums a memory card CompactFlash trademark of SanDisk Corp. in U.S.A. SmartMedia trademark of Toshiba Co. Ltd. SD card trademark of SanDisk Corp. in U.S.A. Matsushita Electric Industrial Co. Ltd. and Toshiba Co. Ltd. Memory Stick trademark of Sony Corp. MMC trademark of Siemens in U.S.A. and SanDisk Corp. in U.S.A. etc a magnetic tape and other tape mediums and a storage device including as a built in component any one of those mediums. Some of the storage devices have a built in DRAM Dynamic Random Access Memory or SRAM Dynamic Random Access Memory .

Furthermore some of the computer readable mediums are fixedly installed in the computer or the computer embedded into the machine or the system. This type of computer readable medium can be exemplified by a hard disk a DRAM an SRAM a ROM an EEPROM Electronically Erasable and Programmable Read Only Memory and a flash memory.

All examples and conditional languages recited herein are intended for pedagogical purposes to aid the reader in understanding the invention and the concepts contributed by the inventor to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions nor does the organization of such examples in the specification relates to a showing of the superiority and inferiority of the invention. Although the embodiments of the present inventions have been described in detail it should be understood that the various changes substitutions and alterations could be made hereto without departing from the spirit and scope of the invention.

