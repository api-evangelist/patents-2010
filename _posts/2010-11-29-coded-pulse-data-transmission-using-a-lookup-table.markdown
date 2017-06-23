---

title: Coded pulse data transmission using a look-up table
abstract: Input data is encoded using a look-up table and then transmitted over a transmission medium as a series of pulses. The look-up table includes data elements. The length of each pulse is calibrated to correspond to one of the data elements in the look-up table. Upon receipt at another end of the transmission medium, the data is decoded using a look-up table. This decoding includes measuring the length of each received pulse to match the measured length to a corresponding one of data elements in the look-up table.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09049093&OS=09049093&RS=09049093
owner: Seagate Technology LLC
number: 09049093
owner_city: Cupertino
owner_country: US
publication_date: 20101129
---
This patent document is a continuation under 35 U.S.C. 120 of U.S. patent application Ser. No. 12 273 933 filed on Nov. 19 2008 now abandoned which is fully incorporated herein by reference.

At least some embodiments disclosed herein relate to communication systems in general and more particularly but not limited to transmission of encoded data.

Light is a standard messenger in communications technology. Currently the bits in data audio or video traffic are sent through fiber optic cables as brief pulses of light. A pulse is a value of one and the absence of a pulse equals zero. Each pulse may be millionths of a second or less and standard fiber optic lines now typically run 2.5 billion to 10 billion bits 2.5 gigabits to 10 gigabits per second.

The fiber optic cable itself consists of a bundle of single optical fiber strands each barely the size of a human hair. At the center of each of these strands is the core made of glass silica. A laser which encodes data as pulses of light sends the pulses through the fiber optic cable s core. Surrounding the core is a mirror like optical material called the cladding which reflects the light back into the core. Because the cladding doesn t absorb light the light pulses are able to travel long distances.

Both transmission lasers and light emitting diodes LEDs can be used as the light source but lasers which are more powerful are more commonly employed. The laser can be roughly analogized to an extremely powerful flashlight that blinks billions of time each second. When the laser is turned on the equivalent of a digital 1 is transmitted and when it s off a digital 0 is represented. The high level of internal reflectivity of the cladding in a fiber optic cable allows the light to be transmitted down the length of the cable even through the many twists and turns of its run.

Light is sent into the fiber and it bounces back and forth inside the fiber all the way to the other end which is sometimes hundreds of miles away. Pulses of light in a fiber optic material can carry the same kind of information that is transmitted as electrical pulses in a copper wire. This information can be telephone conversations or data from computers and fax machines. A conventional copper wire can carry a few million electrical pulses each second. In contrast an optical fiber can carry as many as 20 billion light pulses per second. Telephone companies are switching to fiber optic cables because they can handle huge numbers of conversations at one time many more than conventional copper wire can carry.

The following description and drawings are illustrative and are not to be construed as limiting. Numerous specific details are described to provide a thorough understanding. However in certain instances well known or conventional details are not described in order to avoid obscuring the description. References to one or an embodiment in the present disclosure are not necessarily references to the same embodiment and such references mean at least one.

Reference in this specification to one embodiment or an embodiment means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the disclosure. The appearances of the phrase in one embodiment in various places in the specification are not necessarily all referring to the same embodiment nor are separate or alternative embodiments mutually exclusive of other embodiments. Moreover various features are described which may be exhibited by some embodiments and not by others. Similarly various requirements are described which may be requirements for some embodiments but not other embodiments.

As used herein a look up table includes any reference table library or stored information that provides a set of data elements for reference during the encoding or decoding of transmitted data. The data elements in a look up table may include for example numbers text binary code and other data or data strings that correspond to values or characteristics associated with information being transmitted. Data elements contained in the look up tables of other embodiments may include for example computer program elements e.g. portions of code commonly used in a given program language corresponding to an encoded data transmission . In yet other embodiments data elements may include pointers or references to other look up tables.

The look up table is often identical for both the encoding and decoding ends. In other embodiments differences between look up tables at the encoding and decoding ends may exist.

As used herein a series of pulses includes the use of a series of light or dark pulses in the case of light transmission or a series of positive or negative pulses in the case of electric or other forms of transmission as may vary depending on the particular embodiment implemented. The systems and methods described herein are generally applicable to use of either a light or dark or positive or negative pulse. For purposes of explanation the disclosure will generally describe the use of a light or a positive pulse.

Systems and methods for the transmission of data are described herein. Generally input data to be transmitted is encoded using a look up table to provide encoded data. The look up table includes a plurality of data elements. The length of each pulse is calibrated to correspond to one of the data elements in the look up table. The encoded data is transmitted as a series of pulses over a transmission medium such as for example a fiber optic cable.

Upon receipt at another end of the transmission medium the data is decoded using a look up table. The look up table at least to the extent of the data elements used to encode the data is identical at the decoder. This decoding includes measuring the length of each received pulse to match the measured length to a corresponding one of the data elements in the look up table.

Data is received at another end of transmission medium by a decoder . The data is decoded using look up table . In one embodiment look up table is identical to look up table .

Transmission medium may be for example a fiber optic line a conventional copper wire line e.g. for telephone communication or a coaxial cable distribution system.

A data processing system may be the source of the input data . Data processing system may be for example a system that generates streaming video.

A data processing system may receive the decoded output data at the receiving end. Data processing system may be for example a user client device executing a streaming video or audio player for the user.

Input data received by encoder is encoded using data elements in look up table . These data elements typically correspond to the type of data e.g. video audio or program that is to be encoded. For example for encoding a text document exemplary data elements and may include respectively the words the apple and and . The types of data that may be encoded are numerous and include for example any type of images such as medical x ray images and digital photography images and many types of audio files.

Each pulse length corresponds to a data element in the table . For example pulse has length L that is associated with data element . Input data is encoded so that the length of each transmitted pulse is determined by the corresponding entry in table .

In one embodiment the data elements of table are selected so that the more commonly occurring input data corresponds to shorter pulse lengths. This typically will increase the efficiency of transmission. For example the word the is a common text string that would have a shorter pulse length L. The word apple is less common than the and has a longer pulse length L.

In one embodiment the input data is for example video data e.g. high definition HD television data . A number of look up tables may be used to encode such data with the data elements in a first table being unique pixel locations in a video image and data elements in a second table being colors for the video image.

In one embodiment one or more of the pulse lengths are less than one thousandth of a second and may even be defined or calibrated in lengths of time as short as trillionths or billionths of a second e.g. less than 10 billionths of a second and for some of the pulses as long as many seconds e.g. greater than 2 seconds . In an alternative embodiment some pulses may be measured by a distance of the pulse instead of a time duration of the pulse. Look up tables corresponding to pulse distance would be used for encoding and decoding such pulses.

Delineations between sets of pulses to be encoded or decoded may be provided as coded elements to maintain pulse order and boundaries. For example pre defined breaks a set pulse of a specific time or a multiple set of pulses of light and dark may be used as delineating elements.

The size of the look up tables may be for example about 1 10 million data elements or even billions of data elements or larger depending on the embodiment.

Timing reference may be for example an atomic clock. An atomic clock may for example permit using differences in pulse length of about 2 3 billionths of a second.

One or more transmission lasers or one or more light emitting diodes LEDs may be used for example as the source for generating the series of pulses sent over transmission medium . Encoder may use existing conventional hardware as used for existing light or electrical communications over various known transmission mediums but modified to operate as described herein.

A large number of different look up tables may be stored in memory e.g. as used for encoding video data streams and several tables may be used to encode different portions of transmitted data streams. A command may be transmitted over transmission medium in order to identify the particular look up table from the many accessible by encoder in order to identify for later decoding those tables that were used to encode the data.

Received pulses from transmission medium are received by receiver . A timing reference is used as a standard against which to measure the lengths of the received pulses. Receiver may be for example an optical sensor. Timing reference may be for example an atomic clock.

One exemplary approach for the timing of laser pulses received by a sensor may be implemented in a system using one or more photodiode detectors e.g. an array of photodiode detectors . The use of such photodiode detectors and the timing of received pulses is described further in an article by D. A. Cohen Y. Chang A. F. J. Levi H. Fetterman and I. Newberg titled Optically Controlled Serially Fed Phased Array Sensor IEEE Photonics Technol. Lett. 8 1683 1685 1996 which is incorporated by reference in its entirety.

Similarly as was discussed above for encoding numerous look up tables may be stored in memory e.g. for decoding video data streams . A command may be received from transmission medium so that decoder can select the appropriate look up table from many tables accessible by decoder .

More specifically receiver receives or senses each pulse e.g. using an optical sensor as pulses are received from transmission medium by decoder . Under control of processor each pulse is compared to timing reference to measure the length of the pulse. The measured pulse lengths may be stored in memory awaiting further processing.

Processor controls a comparison of the measured pulse lengths against look up table . Processor retrieves data elements from the appropriate look up table which can be selected using the command or other pointer received e.g. a header information as part of the transmission from transmission medium .

Each pulse length is associated with a data element in look up table . As data elements are retrieved from one or more look up tables processor controls the assembly and output of the retrieved data to provide output data .

In one embodiment the pulses can be set for a unique program situation. For example a set of words each having a unique pulse length for a first type of data i.e. word data to be transmitted do not need to be included in the same look up table as a set of colors which could use some of the same pulse lengths as used in the word look up table. As another example a look up table can be associated with various portions of a computer program once the application programming interface API is known. This association can be handled by an intermediary service company and the look up table does not need to be prepared by the original programmer of the computer program.

In one embodiment at the start of every transmission the type of transmission may be defined e.g. using a command as described above . For example a video transmission may be defined by command data transmitted prior to or even following in other embodiments a series of pulses e.g. as a header corresponding to video data. This video command will be used to identify an appropriate unique look up table. Similarly a command may identify data for a word document and be used to identify an appropriate unique look up table for decoding a series of pulses for word data. A given length of pulse can be re used for different types of data transmissions.

In one embodiment each of the commands for defining the type of transmission can be a string of ones and zeroes e.g. 1110001101010110 or can be a unique pulse length that has been predefined as corresponding to a command which itself defines the type of data transmission and is used to select yet another look up table for decoding. Also computer programs may be predefined in this manner to make the transmission and look up table usage more efficient.

In one embodiment a portion of the encoded data sent over transmission medium includes test data to adjust for line loss and other variations in transmission. This test data is decoded by decoder . The results from this decoding is communicated to encoder as feedback and based this feedback the calibration of transmitted pulse lengths by encoder is adjusted in order to compensate for variations in transmission medium .

The parameters of the existing line in the transmission medium typically affect the possible range of variations in pulse lengths. For example the longer pulses could be thousands of times longer than the shortest pulses e.g. one pulse could be one billionth of a second and another pulse could be five thousand billionths of a second .

As mentioned above the shorter pulses may be used for the most commonly transmitted data. In other embodiments processes may be established to use more commonly used elements of a computer program or a data transmission system for the shorter pulse lengths.

In one non limiting example a high definition HD television data stream e.g. in a 1920 1080 format at 60 frames second is transmitted as the encoded data. It should be noted that in this example audio data is omitted from the calculations for purposes of simplified explanation. Download times would be slightly longer when accounting for audio data with audio data in 5.1 or better format requiring an even greater download time.

The quantity of HD data to be transmitted may be estimated as follows HD pixel specifications 1920 1080 pixels multiplied by 60 frames per second 1920 1080 60 124 416 000 pixel data points second of HD production. Pixel color data points plus described colors for each pixel per second 2 124 416 000 248 832 000 points second of HD production.

Thus the total number of pixels plus the ascribed colors for each pixel is 248 832 000 data elements per second of HD production viewing. This does not include transition pulse codes codes which define the end of a screen frame an order to match pixels to color an order to define pulses as colors pixels etc. which typically will only be a nominal portion of the total data to be transmitted. At a laser pulse rate of 20 billion pulses per second with necessary gapping and variation spacing for individual characters and coding elements an HD video download speed can be calculated as follows 20 000 000 000 pulses per second divided by 248 832 000 data elements per second of HD production 80 seconds of an HD production transmitted per second. This corresponds for example to a total transmission time of about 90 seconds for a 2 hour HD movie.

While illustrates various components of a computer system it is not intended to represent any particular architecture or manner of interconnecting the components. Other systems that have fewer or more components may also be used.

In data processing system includes an inter connect e.g. bus and system core logic which interconnects a microprocessor s and memory . The microprocessor is coupled to cache memory in the example of .

The inter connect interconnects the microprocessor s and the memory together and also interconnects them to a display controller and display device and to peripheral devices such as input output I O devices through an input output controller s . Typical I O devices include mice keyboards modems network interfaces printers scanners video cameras and other devices which are well known in the art.

The inter connect may include one or more buses connected to one another through various bridges controllers and or adapters. In one embodiment the I O controller includes a USB Universal Serial Bus adapter for controlling USB peripherals and or an IEEE 1394 bus adapter for controlling IEEE 1394 peripherals.

The memory may include ROM Read Only Memory and volatile RAM Random Access Memory and non volatile memory such as hard drive flash memory etc.

Volatile RAM is typically implemented as dynamic RAM DRAM which requires power continually in order to refresh or maintain the data in the memory. Non volatile memory is typically a magnetic hard drive a magnetic optical drive or an optical drive e.g. a DVD RAM or other type of memory system which maintains data even after power is removed from the system. The non volatile memory may also be a random access memory.

The non volatile memory can be a local device coupled directly to the rest of the components in the data processing system. A non volatile memory that is remote from the system such as a network storage device coupled to the data processing system through a network interface such as a modem or Ethernet interface can also be used.

In one embodiment a data processing system as illustrated in is used to implement a user terminal which may receive streaming video or audio data. A user terminal may be in the form of a personal digital assistant PDA a cellular phone a notebook computer or a personal desktop computer.

In some embodiments one or more servers of the system can be replaced with the service of a peer to peer network of a plurality of data processing systems or a network of distributed computing systems. The peer to peer network or a distributed computing system can be collectively viewed as a server data processing system.

Embodiments of the disclosure can be implemented via the microprocessor s and or the memory . For example the functionalities described can be partially implemented via hardware logic in the microprocessor s and partially using the instructions stored in the memory . Some embodiments are implemented using the microprocessor s without additional instructions stored in the memory . Some embodiments are implemented using the instructions stored in the memory for execution by one or more general purpose microprocessor s . Thus the disclosure is not limited to a specific configuration of hardware and or software.

In this description various functions and operations may be described as being performed by or caused by software code to simplify description. However those skilled in the art will recognize what is meant by such expressions is that the functions result from execution of the code by a processor such as a microprocessor. Alternatively or in combination the functions and operations can be implemented using special purpose circuitry with or without software instructions such as using Application Specific Integrated Circuit ASIC or Field Programmable Gate Array FPGA . Embodiments can be implemented using hardwired circuitry without software instructions or in combination with software instructions. Thus the techniques are limited neither to any specific combination of hardware circuitry and software nor to any particular source for the instructions executed by the data processing system.

While some embodiments can be implemented in fully functioning computers and computer systems various embodiments are capable of being distributed as a computing product in a variety of forms and are capable of being applied regardless of the particular type of machine or computer readable media used to actually effect the distribution.

At least some aspects disclosed can be embodied at least in part in software. That is the techniques may be carried out in a computer system or other data processing system in response to its processor such as a microprocessor executing sequences of instructions contained in a memory such as ROM volatile RAM non volatile memory cache or a remote storage device.

Routines executed to implement the embodiments may be implemented as part of an operating system middleware service delivery platform SDK Software Development Kit component web services or other specific application component program object module or sequence of instructions referred to as computer programs. Invocation interfaces to these routines can be exposed to a software development community as an API Application Programming Interface . The computer programs typically comprise one or more instructions set at various times in various memory and storage devices in a computer and that when read and executed by one or more processors in a computer cause the computer to perform operations necessary to execute elements involving the various aspects.

A machine readable medium can be used to store software and data which when executed by a data processing system causes the system to perform various methods. The executable software and data may be stored in various places including for example ROM volatile RAM non volatile memory and or cache. Portions of this software and or data may be stored in any one of these storage devices. Further the data and instructions can be obtained from centralized servers or peer to peer networks. Different portions of the data and instructions can be obtained from different centralized servers and or peer to peer networks at different times and in different communication sessions or in a same communication session. The data and instructions can be obtained in entirety prior to the execution of the applications. Alternatively portions of the data and instructions can be obtained dynamically just in time when needed for execution. Thus it is not required that the data and instructions be on a machine readable medium in entirety at a particular instance of time.

Examples of computer readable media include but are not limited to recordable and non recordable type media such as volatile and non volatile memory devices read only memory ROM random access memory RAM flash memory devices floppy and other removable disks magnetic disk storage media optical storage media e.g. Compact Disk Read Only Memory CD ROMS Digital Versatile Disks DVDs etc. among others. The instructions may be embodied in digital and analog communication links for electrical optical acoustical or other forms of propagated signals such as carrier waves infrared signals digital signals etc.

In general a machine readable medium includes any mechanism that provides i.e. stores and or transmits information in a form accessible by a machine e.g. a computer network device personal digital assistant manufacturing tool any device with a set of one or more processors etc. .

In various embodiments hardwired circuitry may be used in combination with software instructions to implement the techniques. Thus the techniques are neither limited to any specific combination of hardware circuitry and software nor to any particular source for the instructions executed by the data processing system.

Although some of the drawings illustrate a number of operations in a particular order operations which are not order dependent may be reordered and other operations may be combined or broken out. While some reordering or other groupings are specifically mentioned others will be apparent to those of ordinary skill in the art and so do not present an exhaustive list of alternatives. Moreover it should be recognized that the stages could be implemented in hardware firmware software or any combination thereof.

In the foregoing specification the disclosure has been described with reference to specific exemplary embodiments thereof. It will be evident that various modifications may be made thereto without departing from the broader spirit and scope as set forth in the following claims. The specification and drawings are accordingly to be regarded in an illustrative sense rather than a restrictive sense.

