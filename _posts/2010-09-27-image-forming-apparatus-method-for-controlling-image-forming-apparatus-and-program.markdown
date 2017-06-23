---

title: Image forming apparatus, method for controlling image forming apparatus, and program
abstract: The purpose of the present invention is to add a user restriction function with use of a card by a simple structure even with an inexpensive image forming apparatus. A CPU of an image forming apparatus determines a port of a signal acquired from a card R/W at the time of initialization of the connected IC card R/W. Then, the CPU of the image forming apparatus controls an execution or a stop of an application for performing authentication service processing corresponding to the port of the signal received from the card R/W.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08832826&OS=08832826&RS=08832826
owner: Canon Kabushiki Kaisha
number: 08832826
owner_city: Tokyo
owner_country: JP
publication_date: 20100927
---
The present invention relates to an image forming apparatus capable of executing a plurality of applications to perform service processing.

There is a system in which an integrated circuit IC card unit provided with the short range wireless communication function can be connected to an image forming apparatus such as a copying machine. The authentication function service has been commercialized to be used with such an image forming apparatus for enabling an image forming apparatus to identify a user and the department of the user and determine whether or not the user is allowed to use the image forming apparatus when the user holds an IC card storing user identification information over an IC card unit before operating the image forming apparatus.

With the increase in the number of copying machines designed as an open platform the above described function service has been widely developed and commercialized by not only copying machine manufactures but also third party software vendors refer to Japanese Patent Application Laid Open No. 2007 251279 .

Generally for use in the authorization function with use of an IC card as mentioned above the required specification varies depending on a market and a customer s environment. Especially in consideration of the improvement of the customer satisfaction it is desirable to offer the service by realizing the specification and device configuration an IC card unit and an authentication server according to customer s requests.

On the other hand there has been proposed an expensive image forming apparatus supporting an application based on the application programming interface API specification for an open platform. Such an image forming apparatus can be flexibly and conveniently arranged according to implementation of an application.

However in a low price image forming apparatus that is not designed as an open platform a controller of the apparatus has to appropriately perform a control according to a device to be connected thereto and a service to be provided thereby. As a result a problem arises in that it is difficult to develop for example a system employing a system with use of an IC card as mentioned above.

According to an aspect of the present invention an apparatus to which a card unit configured to communicate with a card storing user information is connectable includes a storage unit configured to store an application for executing an authentication service a determination unit configured to determine a port from information acquired from the card unit and a control unit configured to control an execution or a stop of the authentication service according to the determined port.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

The image forming apparatus employing the present invention is an example of a system for offering a user restriction processing service with use of an IC card as a card. Therefore an IC card reader writer R W communicable with an IC card is connected to the image forming apparatus .

Here the IC card is constituted by a non contact type IC card. The IC card R W transmits a carrier to the IC card whereby power is supplied to the IC card due to electromagnetic induction and the IC card and the reader communicate with each other through carrier modulation.

On the other hand the image forming apparatus is provided with the function of determining through which port communication has been performed from among a plurality of ports each associated with an IC card reader and performs user restriction function processing which will be described later according to the port information of the determined port.

Further the image forming apparatus has an authentication table and is configured to perform authentication processing within the apparatus. In the present exemplary embodiment the IC card R W is referred to as IC card unit and the image forming apparatus includes a universal serial bus USB host as an interface means for enabling a connection to the IC card unit.

On the other hand illustrates an example of a system including external authentication servers and connected to the network. In this example the external authentication server provides an authentication service A by communicating with the image forming apparatus through a port A when an IC card is held over an IC card R W of the image forming apparatus .

Information processing apparatuses personal computer PC A and B are connected in the network and a printer driver is installed therein for transmitting a print job to the image forming apparatus . Further the printer driver in the information processing apparatuses PC A and B can recognize the status of the image forming apparatus by communicating with the image forming apparatus .

Referring to a user is given in advance an IC card storing user authentication information for himself herself from a system administrator and holds the IC card over the IC card R W when the user starts to operate the image forming apparatus . This action causes the image forming apparatus to perform authentication processing and allow the user to use the image forming apparatus upon a success in the authentication.

Further the present system may be modified to be capable of using a common IC card R W and a common IC card to both the authentication service A and the authentication service B. Generally two types of cards contact type card and non contact type card are available as an IC card and the IC card may be embodied by either card.

Further the image forming apparatus includes a plotter for an image formation a scanner for scanning of a document and other hardware resources .

Here the plotter is so called a printer engine and performs image forming processing according to the electrophotographic method or the inkjet printing method. In the following description the term IC card is used to collectively refer to IC cards while the terms IC card and IC card are used to respectively refer to IC cards. Identifiable device IDs are stored in advance in the IC cards and respectively. Further in the IC card R W is indicated as IC Card R W .

Referring to the controller includes a central processing unit CPU which performs an overall control of the image forming apparatus and an application specific integrated circuit ASIC for the controller which includes an operation unit interface I F a CPU I F a peripheral component interconnect PCI I F a memory controller and others.

Further the controller includes a hard disk drive HDD storing image data a serial bus and a network interface card hereinafter referred to as NIC equipped with the function for a connection to the network. An application associated with authentication service processing executed by the image forming apparatus is installed in the HDD .

The HDD is configured to be able to store a plurality of applications associated with authentication service processing although the present exemplary embodiment can be applied if an HDD stores at least one application.

In the present exemplary embodiment the image forming apparatus is configured to be able to identify a port by reading an initialization result signal corresponding to a unique device ID assigned to an IC card R W. The HDD stores a correspondence table in which device IDs are associated with respective ports. The correspondence table is referred to according to a device ID acquired by the ASIC from an IC card R W whereby the port is identified.

Further the controller includes a USB for a connection to a device such as a keyboard a mouse and a printer an IEEE for a wireless local area network LAN and an IEEE for a connection of a computer to a peripheral device.

Further the controller includes a north bridge NB connected to a USB host for a connection to the IC card R W through a USB cable and a memory card I F through the PCI bus .

The USB host is configured to be able to acquire a device ID from an IC card R W connected through the USB cable. A device ID is information for identifying a connected IC card R W and is stored in a non volatile memory of an IC card R W in advance as unique information.

Such a device ID is read out when an IC card R W is initialized and is notified to the CPU of the image forming apparatus . Further the USB host is configured to be able to be connected to IC card R Ws having different device IDs.

The controller further includes a random access memory RAM a read only memory ROM and others. The ASIC is connected to the facsimile control unit the plotter the scanner and the other hardware resources through the PCI bus . Here ASIC is an abbreviation for Application Specific Integrated Circuit.

The CPU is connected to the IC card R W by a USB cable via the NB the PCI bus and the USB host and performs control by transmitting a command to the IC card R W . An access to the IC card is realized by wireless communication of the IC card R W with the IC card .

In the present exemplary embodiment an IC card R W is connected through the USB host but may be connected through another interface other than a USB. The IC card R W stores a device ID in the internal memory thereof and is configured so that it is possible to perform the processing of identifying a port through identification of the device ID.

Referring to a supervisor issues an initialization request to a card reader controller before starting the polling processing. The card reader controller issues a similar initialization request to a class driver . The class driver controls communication between the IC card R W and an IC card.

The supervisor upon receiving the result of the initialization from the card reader controller determines the reception port. At this time if the supervisor determines that the port that has received the result is a port A the supervisor determines that the authentication service is the authentication service A and starts polling processing.

First after the supervisor issues an initialization request in step S the supervisor receives an initialization completion signal of the IC card R W from the card reader controller . Then the operation proceeds to step S. In step S the supervisor determines whether or not the port that has received the initialization completion signal is the port A. At this time if the supervisor determines that the port that has received the initialization completion signal is the port A YES in step S the operation proceeds to step S. If the supervisor determines that the port that has received the initialization completion signal is not the port A but for example a port B NO in step S then the operation proceeds to step S.

Then in step S the supervisor performs the processing for the service B including a user restriction function corresponding to the port B and then ends the current polling start processing. Here the processing for the service B is processing realized by an application stored in the HDD of the image forming apparatus . More specifically the service B includes service processing which does not read an IC card when a user logs off the service B after using for example a document management function.

While the supervisor is performing the processing for the service B the supervisor stops the polling processing to the card reader A. Therefore the service B ignores information from the card reader even when an IC card is placed on the card reader.

In the present exemplary embodiment an application associated with a user restriction function is exemplified by the processing of a document management application having the login and logoff function with use of an IC card but may be embodied by another functional processing.

On the other hand in step S the supervisor performs the processing for the service A associated with a user restriction function corresponding to the port A. Here the processing for the service A includes for example the processing which reads an IC card of a user at both times of logging in and logging off the service A.

As will be described later during an execution of the processing of the service A the supervisor repeats the polling processing to the card reader A. Therefore when an IC card is placed on the card reader information is read through the card reader. Subsequently in the service A the processing requiring authentication is performed.

When the operation proceeds to step S NO in step S it is possible to stop the service A that is not an execution target. When the processing proceeds to step S YES in step S it is possible to stop the service B that is not an execution target. These processes are controlled by an instruction from the supervisor .

Further turning on off of an interrupt login mode can be specified through for example the operation unit of the image forming apparatus . This interrupt login mode will now be described. Even if it is determined based on the identified port that the authentication service by the application should be stopped communication through the port B is detected it is possible to instruct the service B not to stop the authentication service related to the service B.

In other words the interrupt login mode can be tuned on. More specifically for example it is assumed that the application is started up under authentication of a user after the IC card is authenticated.

In this state this user may leave and another user may hold his her ID card over the IC card unit to be authenticated for logging in the service B interrupt login mode . In this case if it is detected that the another user holds his her IC card over the IC card unit the polling processing to the IC card reader is not stopped.

Next in step S the supervisor requests a start of polling to the card reader A and ends the current polling start processing. According to this processing it is possible to build a system capable of switching between the service processing based on the user restriction function A and the service processing based on the user restriction function B by identifying a port of an initialization result signal received from an IC card R W.

Now as an example of the service processing if the IC card A can be handled by the IC card R W A the image forming apparatus executes the authorization service which performs the IC card reading processing at the times of user s logging in and logging off.

On the other hand if the IC card B can be handled by the IC card R W B the image forming apparatus executes the authentication service which performs the IC card reading processing only when a user logs in the image forming apparatus .

In other words even if the image forming apparatus is an inexpensive apparatus the information forming apparatus controls an execution or a stop of an installed application by identifying a port of an initialization result signal notified at the time of initialization processing of a connected IC card R W. As a result it is possible to control an execution or a stop of an application corresponding to a service carrying out a user restriction function according to a user restriction specification for each country or a usage environment.

In the first exemplary embodiment an application to be executed is determined by receiving an initialization result signal through the port corresponding to the device ID of an IC card reader connected to the image forming apparatus . Instead of this configuration the image forming apparatus may be configured to identify a port used for communication to an authentication server connected in the network and then execute an application corresponding to the identified port. In the following such an exemplary embodiment will be described.

The system configuration in the present exemplary embodiment corresponds to the system illustrated in and is a system including the authentication servers and connected in the network. Here the authentication servers and perform difference authentication services.

In particular illustrates an example identifying which port has been used to receive an authentication result signal notified from the authentication server or executing any of registered applications and performing the service processing associated with the application.

The image forming apparatus includes the modules corresponding to the following units to . A display controller communicates with a user interface UI main unit . The UI main unit communicates with the supervisor and an authentication controller . The card reader controller communicates with the class driver or . Here the class driver is associated with the IC card R W and the class driver is associated with the IC card R W

In the present exemplary embodiment if the supervisor receives an initialization result signal of the IC card R W acquired via the card reader controller through the reception port A the supervisor determines that the required service is the service A and then requests a polling start. Similarly if a signal indicating falling out of an IC card is acquired through the supervisor the image forming apparatus determines that the required service is the service A and performs a control such that an error is not displayed.

On the other hand if the information of the authentication result acquired from the authentication controller is acquired through the port B in this state it is determined that the required service is the service A and the UI main unit requests a stop to the authentication server .

In the system illustrated in the authentication controller communicates with the authentication server or and obtains card information a set of an ID and a password read from an IC card that a user holds over the IC card R W. Then the authentication controller requests authentication of the card information to the authentication server or and receives the authentication result from the authentication server or .

At this time since the communication is performed through the port specific to the authentication server or the UI main unit of the image forming apparatus can determine which port has received the authentication result. Then the UI main unit executes an application corresponding to the determined port and performs the processing for the specific service.

If it is determined that the port specified by the UI main unit is the port B the UI main unit notifies the supervisor of a stop of the polling similarly to the first exemplary embodiment. In response to this notification the supervisor notifies the card reader controller of the stop of the polling. Then the card reader controller controls the class driver to stop the polling.

Now the communication processing according to the present exemplary embodiment will be described with reference to the flowcharts illustrated in . The CPU illustrated in loads a control program stored in the ROM or HDD onto the RAM and executes it thereby realizing steps S to S. In the following description the control entity is the supervisor and the main unit executed by the CPU .

Further steps S and S are steps performed by the authentication server or in particular are steps performed by the CPU of the authentication server or .

First in step S the image forming apparatus causes information of an IC card to be read through a connected IC card R W and receives the read IC card information. Then in step S the UI main unit requests authentication of the received card information to the authentication server or through the authentication controller .

Upon the issue of this request the operation proceeds to step S. If for example the authentication server receives the card information YES in step S the operation proceeds to step S where the CPU of the authentication server refers to a user information table registered in advance authenticates the card information and then notifies the image forming apparatus of the authentication result through the network.

Next in step S the UI main unit of the image forming apparatus determines whether or not the authentication result from the authentication server has been received through the port A. At this time if the UI main unit determines that the authentication result from the authentication server has been received through the port A YES in step S the operation goes to step S and performs the subsequent steps.

On the other hand in step S if the UI main unit determines that the authentication result from the authentication server has been received through the port B NO in step S then the operation goes to step S and performs the subsequent steps.

As illustrated in the image forming apparatus may perform a control in such a manner that the function used by the image forming apparatus is determined and the CPU of the image forming apparatus executes an application corresponding to the determined function.

Further in the present exemplary embodiment an application performed according to an identified port is exemplified by the application related to the user restriction function but may be embodied by an application corresponding to a service related to another functional processing.

Further in the above described exemplary embodiment the authentication server externally connected to the image forming apparatus is in charge of authentication processing but instead the image forming apparatus may store an authentication table and perform authentication processing within the image forming apparatus . Further in the present exemplary embodiment the IC card R W is connected through a USB but may be connected through another interface other than a USB.

According to the above described exemplary embodiments in an image forming apparatus such as a copying machine offering a plurality of IC card authorization functions services it is possible to provide an appropriate apparatus control according to the respective functions services.

More specifically even with an apparatus that is not designed as an open platform it is possible to provide a high value added apparatus that can flexibly satisfy customer s needs.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium . In such a case the system or apparatus and the recording medium where the program is stored are included as being within the scope of the present invention.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2009 228315 filed Sep. 30 2009 which is hereby incorporated by reference herein in its entirety.

