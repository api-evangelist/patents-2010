---

title: Communication apparatus provided with network interfaces, control method therefor, and storage medium storing control program therefor
abstract: A communication apparatus is provided with network interfaces. A control unit provides an application programming interface for an application that runs on the communication apparatus. A transmission unit transmits a search packet via the respective network interfaces in response to a request from the application. A reception unit receives a response packet in response to the search packet that the transmission unit transmits. A first determination unit determines whether the information showing a transmitting source of the response packet that the reception unit received is stored in a storage unit. The control unit stores the information showing the transmitting source of the response packet received into the storage unit and transfers the response packet received to the application, when the first determination unit determines that the information showing the transmitting source of the response packet received is not stored in the storage unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08984087&OS=08984087&RS=08984087
owner: Canon Kabushiki Kaisha
number: 08984087
owner_city: 
owner_country: JP
publication_date: 20101001
---
The present invention relates to a communication apparatus provided with a plurality of network interfaces a control method therefor and a storage medium storing a control program therefor.

In recent years a communication apparatus that can search for other devices on a network is developed in order to provide a service while devices such as image forming apparatuses cooperate mutually. The communication apparatus generally uses a method using a multicast packet or a broadcast packet for example see Japanese Laid Open Patent Publication Kokai No. 2000 181849 JP 2000 181849A .

The multicast packet is an IP Internet Protocol packet used when transmitting the same data to specific devices that stand on a network. One of the features of the multicast packet is that a TTL TimeToLive value is included in a packet. The TTL value expresses life time of the IP packet and the value decreases one by one when passing through a router. That is when the TTL value is set to 1 or more at a transmitting source of the multicast packet it becomes possible to transmit the same multicast packet to networks subnets in a wide area beyond a router.

On the other hand the broadcast packet is an IP packet used when transmitting the same data to many and unspecified devices that stand on a network. The broadcast packet cannot exceed a router but can be transmitted only to devices on the network subnet that is formed by the router. As compared with this a packet that specifies a single device that stands on a network and is transmitted to an IP address of the device is called a unicast packet.

Conventionally a multi home device that has a plurality of network interfaces I F sends out a multicast packet or a broadcast packet from the network interfaces when searching for other devices on a network. In this case the multi home device of which the network interfaces belong to the same subnet has a problem in that device search responses are received in duplication from devices that stand on the subnet.

Since the multi home device of which the network interfaces connect with different subnets becomes possible to search beyond a subnet when searching with the multicast packet of which the TTL value is set to 1 or more the same problem occurs.

The present invention provides a communication apparatus a control method therefor and a storage medium storing a control program therefor that are capable of searching a necessary device when the communication apparatus provided with a plurality of network interfaces searches a device without correcting an application running on the apparatus concerned.

Accordingly a first aspect of the present invention provides a communication apparatus provided with network interfaces comprising a control unit configured to provide an application programming interface for an application that runs on the communication apparatus a transmission unit configured to transmit a search packet via the respective network interfaces in response to a request from the application a reception unit configured to receive a response packet in response to the search packet that the transmission unit transmits and a first determination unit configured to determine whether the information showing a transmitting source of the response packet that the reception unit received is stored in a storage unit wherein the control unit stores the information showing the transmitting source of the response packet received into the storage unit and transfers the response packet received to the application when the first determination unit determines that the information showing the transmitting source of the response packet received is not stored in the storage unit.

Accordingly a second aspect of the present invention provides a control method for a communication apparatus provided with network interfaces and a control unit that provides an application programming interface for an application that runs on the apparatus itself the control method comprising a transmission step of transmitting a search packet via the respective network interfaces in response to a request from the application a reception step of receiving a response packet in response to the search packet that is transmitted in the transmission step a first determination step of determining whether the information showing a transmitting source of the response packet that is received in the reception step is stored in a storage unit and a control step of storing the information showing the transmitting source of the response packet received into the storage unit and of transferring the response packet received to the application when it is determined that the information showing the transmitting source of the response packet received is not stored in the storage unit in the first determination step.

Accordingly a third aspect of the present invention provides a computer readable storage medium storing a program causing a computer to execute the above mentioned control method for the communication apparatus.

According to the present invention the problem in that unnecessary devices are retrieved when the communication apparatus that is provided with a plurality of network interfaces searches a device can be solved without correcting the application running on the communication apparatus concerned.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Hereafter embodiments according to the present invention will be described in detail with reference to the drawings.

The first multifunctional peripheral device is an image forming apparatus provided with a print function a scanner function etc. is provided with two network interfaces network I Fs and is connected to mutually different networks subnets and . The subnet and the subnet are mutually connected via a router .

The first multifunctional peripheral device has a function to transmit a multicast packet and a broadcast packet to at least one of the subnet and the subnet and to search apparatuses on the networks. The first multifunctional peripheral device has a function to receive the multicast packet and the broadcast packet from the subnet or the subnet and to respond to an apparatus search by another apparatus on the networks.

A second multifunctional peripheral device is an image forming apparatus provided with a print function a scanner function etc. is provided with one network I F and is connected to the subnet . The second multifunctional peripheral device has a function to receive the multicast packet and the broadcast packet from the subnet and to respond to an apparatus search by another apparatus on the network.

It should be noted that this embodiment employs an SLP Service Location Protocol as an apparatus search protocol that uses the multicast packet. A TTL value in an SLP apparatus search packet is set as 1 .

Next the hardware and software configurations of the first and second multifunctional peripheral devices and in will be described.

The first multifunctional peripheral device is provided with the hardware described below. A scanner I F control unit connects to a scanner unit that reads an image of an original and controls input output of image data etc. with the scanner unit . A CPU executes software programs stored in the first multifunctional peripheral device and controls the whole of apparatus.

A ROM is a read only memory that stores a boot program for the apparatus and data such as fixed parameters. A RAM is a random access memory that temporarily stores data required when the CPU controls the apparatus etc. An HDD is a hard disk drive that stores various kinds of data such as print data.

A printer I F control unit connects to a printer unit that prints data and controls input output of the print data etc. with the printer unit . An NVRAM is a nonvolatile memory that saves various setting values of the printer unit . A panel control unit controls an operation panel as a display device that consists of an LCD Liquid Crystal Display a touch panel etc. displays pieces of information and receives instructions inputted by a user.

A first network I F control unit consists of a network interface card etc. connects to the subnet and controls transmission and reception of data with the subnet . Like the first network I F control unit a second network I F control unit consists of a network interface card etc. connects to the subnet and controls transmission and reception of data with the subnet .

A bus is a system bus that mutually connects the scanner I F control unit the CPU the ROM etc. as shown in the figure and transmits control signals from the CPU and the data signal among the units.

The second multifunctional peripheral device is provided with the hardware described below. A scanner I F control unit connects to a scanner unit that reads an image of an original and controls input output of data with the scanner unit . A CPU executes software programs stored in the second multifunctional peripheral device and controls the whole of apparatus.

A ROM is a read only memory that stores a boot program for the apparatus and data such as fixed parameters. A RAM is a random access memory that temporarily stores data required when the CPU controls the apparatus etc. An HDD is a hard disk drive that stores various kinds of data such as print data.

A printer I F control unit connects to a printer unit that prints data and controls input output of the print data etc. with the printer unit . An NVRAM is a nonvolatile memory that saves various setting values of the printer unit . A panel control unit controls an operation panel as a display device that consists of an LCD Liquid Crystal Display a touch panel etc. displays pieces of information and receives instructions inputted by a user.

A network I F control unit consists of a network interface card etc. connects to the subnet and controls transmission and reception of data with the subnet . A bus is a system bus that mutually connects the scanner I F control unit the CPU the ROM etc. as shown in the figure and transmits control signals from the CPU and the data signal among the units.

A protocol stack controls a TCP Transmission Control Protocol IP protocol and a UDP User Datagram Protocol IP protocol. The TCP and the UDP belong to the fourth layer transport layer in the OSI reference model and act as a bridge between the protocol belonging to the IP layer and the protocol belonging to the fifth layer session layer . A TCP header and a UDP header include port numbers that are used to identify higher level protocols. For example the port number 427 of the TCP header is used to identify the SLP.

The protocol stack is used from another software module application . An interface part between the protocol stack and an application is called a socket and an identifier socket identifier that uniquely identifies a socket is assigned to each socket.

A socket API is an API Application Programming Interface provided in order that a higher level protocol uses the protocol stack . In recent years the API is uniformly standardized by a POSIX Portable Operating System Interface for UNIX registered trademark etc. and has a common format in various systems. The socket API has a socket identifier as an argument that the protocol stack uses to identify an application that uses the protocol stack .

A socket API wrapper is a wrapper for using the socket API and is used from an apparatus search control unit . Since the socket API wrapper is provided in the same format as the socket API an application is able to use the socket API wrapper without changing the format used when calling the socket API directly.

A first network I F driver transfers data between the first network I F control unit connected to the subnet and the protocol stack . A second network I F driver transfers data between the second network I F control unit connected to the subnet and the protocol stack .

The apparatus search control unit is a module that controls an apparatus search. The apparatus search control unit receives a trigger of the apparatus search and processes an apparatus search result. For example the apparatus search control unit receives the apparatus search instruction from a user via the operation panel and the panel control unit and executes an apparatus search when receiving the instruction as a trigger. The apparatus search control unit displays an apparatus search result on the operation panel via the panel control unit to notify a user.

When receiving the trigger of the apparatus search the apparatus search control unit forms an SLP apparatus search packet for performing an apparatus search and transmits the packet using the socket API wrapper . Then the apparatus search control unit receives a SLP search response packet using the socket API wrapper and obtains an apparatus search result see RFC2165 for the details of the SLP apparatus search packet .

An apparatus search response unit receives an SLP apparatus search packet from another apparatus on the network using the socket API . When receiving an SLP apparatus search packet the apparatus search response unit forms an SLP search response packet and transmits the packet using the socket API .

When receiving an apparatus search request from another apparatus on the network an apparatus search response unit generates response data. A protocol stack controls the protocols of TCP IP and UDP IP. A socket API is an API provided in order to use the protocol stack . A network I F driver transfer data between the network I F control unit connected to the subnet and the protocol stack .

In the SLP apparatus search packet formed by the apparatus search control unit is sent out to the subnet and the subnet via the first network I F driver and the second network I F driver . The SLP apparatus search packet sent out to the subnet reaches the second multifunctional peripheral device linked to the subnet . On the other hand since the TTL value of an SLP apparatus search packet is 1 via the router the SLP apparatus search packet sent out to the subnet is transmitted to the subnet and reaches the second multifunctional peripheral device connected to the subnet .

In the SLP apparatus search packet sent out to the subnet is sent out to the subnet via the router and also reaches to the second network I F control unit in the first multifunctional peripheral device linked to the subnet .

In the second multifunctional peripheral device transmits the SLP search response packet that is a response to the SLP apparatus search packet that is directly received from the first multifunctional peripheral device . The second multifunctional peripheral device transmits the SLP search response packet that is a response to the received SLP apparatus search packet via the router . As a result the first multifunctional peripheral device receives the SLP search response packets twice from the second multifunctional peripheral device .

In the SLP apparatus search packet that reaches the second network I F control unit in the first multifunctional peripheral device is received by the apparatus search response unit via the second network I F driver the protocol stack and the socket API . The apparatus search response unit transmits an SLP search response packet that is a response to the SLP apparatus search packet . As a result the first multifunctional peripheral device receives the SLP search response packet from the device itself and the apparatus search result includes the device itself.

In the apparatus search management table comprises elements described below. A socket identifier is set up to identify an application that uses the protocol stack . A destination port number is set up to mean the destination port number of TCP and UDP connections that the socket identifier manages and to identify the using protocol. The socket identifier and the destination port number serve as identification information about search data for example.

The IP address of the destination that receives the response when performing the apparatus search to the socket identifier and the destination port number is set to a search response received address .

The relationship among the socket identifier the destination port number and the search response received address is 1 1 n n is an integer larger than 1 . In the illustrated example 172.24.24.244 and 172.24.24.245 are set up to the search response received address that uses the socket identifier 6 and the destination port number 427 SLP .

In the socket API wrapper refers to the port number of the data passed from the apparatus search control unit and determines whether the protocol deduced from the port number is the apparatus search protocol step S . For example since the port number is 427 when the SLP apparatus search packet is passed from the apparatus search control unit the socket API wrapper determines that the protocol is the apparatus search protocol.

When it is determined that the protocol according to the port number is not the apparatus search protocol as a result of the determination in the step S the socket API wrapper passes the data to the socket API as is step S and finishes this process. On the other hand when it is determined that the protocol according to the port number is the apparatus search protocol in the step S the process proceeds to step S.

In step S the socket API wrapper refers to the apparatus search management table and determines whether the applicable socket identifier and destination port number are registered. When it is determined that the applicable information is registered the socket API wrapper deletes clears all the search response received addresses corresponding to the socket identifier and the destination port number from the apparatus search management table step S . For example in the apparatus search management table shown in all the addresses such as 172.24.24.244 and 172.24.24.245 corresponding to the socket identifier 6 and the destination port number 427 are deleted. The reason why the set up information is deleted in the step S is to avoid being treated as an already responded address when the apparatus search is continuously executed from the same application.

On the other hand when it is determined that the applicable information is not registered in the step S the socket API wrapper newly registers a socket identifier and a destination port number into the apparatus search management table step S and proceeds with the process to step S.

In the socket API wrapper passes a socket identifier to the protocol stack via the socket API and acquires the data corresponding to the socket identifier step S .

As shown by the reference numeral in the second network I F control unit of the first multifunctional peripheral device receives the SLP apparatus search packet of which the source address matches the address held by the first network I F control unit . On the other hand as shown by the reference numeral in the first network I F control unit of the first multifunctional peripheral device receives the SLP apparatus search packet of which the source address matches the address held by the second network I F control unit . In order to cancel such data the socket API wrapper determines whether the source address of the received data matches an address an address of the device itself held by the first and second network I F control units and of the device itself step S . When it is determined that the source address of the received data matches the address of the network I F of the device itself as a result of the determination in the step S the socket API wrapper cancels the corresponding data step S and finishes this process. On the other hand when it is determined that the source address does not match the address of the network I F of the device itself in the step S the process proceeds to step S.

In the step S the socket API wrapper refers to the apparatus search management table and determines whether the socket identifier and destination port number of the data obtained in the step S are registered. When it is determined that the applicable information is not registered the socket API wrapper determines that the received data is not a response to the apparatus search packet passes the data concerned to the application step S and finishes this process.

On the other hand when it is determined that the applicable information is registered in the step S the socket API wrapper determines whether the source address of the data is registered in the apparatus search management table step S . Here it is determined whether the source address is registered to the search response received address in the apparatus search management table .

When it is determined that the source address is registered as a result of the determination in the step S since the SLP search response is transmitted from the apparatus that has already received the SLP apparatus search packet the socket API wrapper cancels the received data step S and finishes this process. On the other hand when it is determined that the source address is not registered in the step S the process proceeds to step S.

In the step S the socket API wrapper registers the source address of data to the search response received address in the apparatus search management table and proceeds with the process to step S. In the step S the socket API wrapper passes only the SLP search response packet to the application not shown and finishes this process.

Next the search results displayed on the operation panel of the first multifunctional peripheral device will be described.

On the other hand shows the apparatus search result obtained when the apparatus search control unit searches an apparatus while using the socket API wrapper . As a result the information about the second multifunctional peripheral device is obtained without duplication .

For example when searching the image forming apparatus managed in a unified manner a setting of an apparatus search policy that a device itself is included in an apparatus search result is forecast. In such a case this embodiment enables to apply the unified policy by correcting the process flow of the socket API wrapper without correcting each application that searches an apparatus.

When searching a connectable apparatus by a certain interface among a plurality of network I Fs a setting of a search interface policy is forecast. Also in such a case this embodiment enables to apply the unified policy by correcting the process flow of the socket API wrapper without correcting each application that searches an apparatus.

On the operation screen shown in ETH corresponds to the first network I F control unit and ETH corresponds to the second network I F control unit . For example when the ETH is set to OFF and the ETH is set to ON as shown in the search data is sent out from the second network I F control unit . When both of the ETH and ETH are ON the search data is sent out from the first and a second network I F control units.

According to the above mentioned embodiment the socket identifier and the destination port number about the search data sent out to the network and the search response received address of the response data received in response to the sent out search data are registered into the apparatus search management table . When it is determined that the transmitting source of the data is the device itself according to the transmission source information about the data received from the network the data concerned is canceled. Further when it is determined that the transmission source information about the data is registered in the apparatus search management table the data concerned is canceled. When it is determined that the transmission source information about the data is not registered in the apparatus search management table the source address of the data is registered into the apparatus search management table and the data is passed to the application. Accordingly an apparatus that is necessary when the device search is performed by the communication apparatus having a plurality of network interfaces can be searched without correcting the application running on the communication apparatus concerned.

Alternatively the process in and may be executed only when the first and second network I F control units send out the search data in the above mentioned embodiment.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiment s and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiment s . For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium .

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2009 230595 filed on Oct. 2 2009 which is hereby incorporated by reference herein in its entirety.

