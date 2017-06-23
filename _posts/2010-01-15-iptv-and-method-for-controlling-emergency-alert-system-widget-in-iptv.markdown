---

title: IPTV and method for controlling emergency alert system widget in IPTV
abstract: A digital broadcast receiver and a method of controlling data for an emergency alert system (EAS) in a digital broadcast receiver are provided. The method includes receiving a digital broadcast signal including an emergency alert table including a uniform resource identifier (URI) descriptor, detecting a URI address included in the URI descriptor, accessing the URI address, receiving additional emergency alert information from the URI address, and performing control to display the additional emergency alert information on a screen of the digital broadcast receiver.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08572645&OS=08572645&RS=08572645
owner: LG Electronics Inc.
number: 08572645
owner_city: Seoul
owner_country: KR
publication_date: 20100115
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 145 571 filed on Jan. 18 2009 which is hereby incorporated by reference as if fully set forth herein.

The present invention relates to an Internet Protocol Television IPTV and more particularly to an IPTV that controls an Emergency Alert System EAS widget.

A Emergency Alert System EAS provides notification messages to the public in cases such as when a national emergency has occurred or when a natural disaster is expected. Detailed protocols for implementing the EAS have not been defined for an Internet Protocol Television IPTV having bidirectionality an interactive or bidirectional TV and the like.

An object of the present invention devised to solve the problem lies on providing a method for executing an EAS widget application.

Another object of the present invention devised to solve the problem lies on defining a more detailed protocol for driving an EAS widget application on an IPTV or an interactive cable TV.

A further object of the present invention devised to solve the problem lies on providing a more efficient method for preventing delay of an EAS message.

In one embodiment of the present invention to achieve the above objects provided herein is a method of controlling data for an emergency alert system EAS in a digital broadcast receiver the method including receiving a digital broadcast signal including an emergency alert table including a uniform resource identifier URI descriptor detecting a URI address included in the URI descriptor accessing the URI address receiving additional emergency alert information from the URI address and performing control to display the additional emergency alert information on a screen of the digital broadcast receiver.

In another embodiment of the present invention provided herein is a method of controlling an emergency alert system EAS widget application in an IPTV the method including executing the EAS widget application directly receiving additional emergency alert information from an EAS server connected to an Internet protocol IP network and performing control to display the additional emergency alert information on the EAS widget application.

In a further another embodiment of the present invention provided herein is a digital broadcast receiver for controlling multiple events the digital broadcast receiver including a browser configured to render and control a user interface delivered by a server a first handler configured to forward a first event to the browser for processing a second handler configured to send and receive a second event during active interaction via server supplied scripts a third handler configured to process a third event and invoke the browser to fetch and render UI content using a URL contained within the third event and a prioritized event scheduler configured to connect the first handler the second handler the third handler and the browser wherein the prioritized event scheduler further reorders sequences based on priorities which the first event second event and third event is to be transmitted to the browser.

Although embodiments of the present invention will now be described with reference to the accompanying drawings and illustrations or descriptions in the drawings the present invention is not limited to the embodiments.

Although most terms of elements in the present invention have been selected from general ones widely used in the art taking into consideration their functions in the invention the terms may be changed depending on the intention or convention of those skilled in the art or the introduction of new technology. Some terms have been arbitrarily selected by the applicant and their meanings are explained in detail in the following description as needed. Thus the definitions of the terms used in the invention should be determined based on the whole content of this specification together with the intended meanings of the terms rather than their simple names or meanings.

A home server shown in functions to store or transmit web pages and A V files. A client TV is connected to a home network. When the client TV detects a device for example through UPnP using the home server the client TV can transmit for example an XHTML web page to the device. The client TV may also be connected to an Internet gateway to communicate with an Internet server .

The Internet server provides web pages. When a user selects specific A V content on a web page the client TV performs operations for reproduction storage or the like of the A V content. The client TV may execute or displays a plurality of web pages and may reduce the number of web pages that can be executed or displayed simultaneously according to the user s need.

Another function of the client TV is to support 3rd party notification using a scheme such as a HTTP text notification b Polling based notification for Internet or c Home multicast.

In scheme a a specific notification is provided to the TV using for example an HTTP protocol text message. In scheme b the TV requests a specific web site at regular intervals to receive data. In scheme c a managed network transmits data using a multicast channel to provide the specific notification to the TV.

As shown in the client includes for example a connector handler a 3party notification handler an event notification handler a UI shell a user input handler bookmarks profiles an XHTML browser a save restore handler an A V control point and an A V media renderer .

The XHTML browser is also connected to the 3rd party notification handler and the event notification handler . To allow an EAS message to be output through the XHTML browser it is necessary to transfer an event associated with the EAS message to the 3rd party notification handler or the event notification handler .

As shown in the client includes for example a 3rd party notification handler an event notification handler an XHTML browser and a user input handler and the server includes for example a 3rd party notification handler an event notification handler and a web server .

Particularly the event notification handler processes or handles a notification transmitted through a script controlled by the server . The 3rd party notification handler is designed to allow external events to be provided to the XHTML browser even when the XHTML browser is not running.

It is necessary to install a proper framework before executing a widget application since widget service providers provide different widget operating frameworks according to their service characteristics. For example it is not possible to execute a widget provided by one provider if a widget of another provider is running. However there is a need to use a standardized framework and widget application in an IPTV environment unlike that described above.

The structure of is designed to enable the widget application to perform TV related functions. The widget application performs a specific function using a predefined object and performs TV middleware or hardware functions through an OEM implementation. The TV interface API allows the widget to perform a TV function enabling control of lower APIs.

As shown in an extensible TV widget framework may have a structure for accessing special hardware whose manufacturer is not defined. This structure can easily extend objects that can be used by a downloaded widget application.

On the other hand widget applications need to use specific APIs provided by manufacturers. For example in order to support the emergency alert function a conventional receiver needs to include a receiving unit for receiving an emergency alert message a converter for converting the message into text and a display unit for displaying the text on a screen. However the IPTV according to an embodiment of the present invention does not need such non flexible hardware and software since upon receiving a distributed widget application for the EAS the IPTV only needs to execute the widget application.

First in an embodiment of the present invention an EAS widget application is designed using EAS objects which include OEM extension APIs and plug in APIs. Operations of an EAS widget application performed when an EAS message is received over the Internet are defined in another embodiment of the present invention. In a further another embodiment of the present invention the EAS widget application displays additional information when an EAS message is received through an Out Of Band OOB or an emergency alert table of an MPEG 2 TS. Another embodiment of the present invention suggests a more efficient method for allowing a specific event to be preferentially processed among a variety of events.

The following is a more detailed description of the embodiments of the present invention described above.

As shown in the Emergency Alert System EAS is independently connected to the Internet to notify the general public of a national emergency a natural disaster or a regional emergency. In this case the EAS is controlled by a national organization. On the other hand an access network service provider may include functionality of the EAS.

A widget service provider may include the EAS or may process and transmit another EAS information. In this case the widget service provider transmits appropriate data together with the widget service application.

The user may view a broadcast of a specific channel on the IPTV. An EAS widget application is running while being displayed at a specific position on the screen as shown in . The EAS widget application may be designed such that a specific EAS message is transmitted according to the current position of the IPTV or the viewer.

In a broadcast in which a person is cleaning snow in a severe snowstorm is shown and a moving image received from a specific web site is displayed on the screen at a lower portion thereof. Weather information of another region may also be received and displayed on the screen at another lower portion thereof. Since the EAS related information is very important and relates to the public interest for example a national organization a meteorological office or an authorized broadcast system need to provide the EAS related information.

The EAS widget application according to an embodiment of the present invention may receive EAS related information using two methods. In the first method the EAS widget application receives additional emergency alert information directly from the network. In the second method the EAS widget application accesses the additional emergency alert information using a table included in a broadcast signal.

The first method will be described below with reference to and the second method will be described later with reference to . The first method may be used by an IPTV and the second method may be used by an interactive or bidirectional cable TV. In the second method additional information relating to the EAS is extracted from an MPEG 2 TS or Out Of Band OOB .

As shown in a power source is connected to an interactive TV for example an IPTV according to an embodiment of the present invention S . The interactive TV boots up S . The interactive TV requests IP address and network setting S and performs a corresponding IP address and network setting procedure S . A widget manager of the interactive TV executes the EAS widget application S .

The EAS widget application determines whether or not an IP address has been allocated to the interactive TV S . When it is determined that an IP address has been allocated the EAS widget application determines the position of the user of the interactive TV S .

The EAS widget application accesses a specified EAS service address S . The EAS widget application collects EAS data from a server that provides the specified EAS service S . The EAS widget application processes and stores the collected EAS data S .

The EAS widget application determines whether or not new data or scheduled EAS data is present in the EAS data S . If it is determined that new data or scheduled EAS data is present the EAS widget application notifies the user of the EAS data using an EAS message S .

As shown in a power source is connected to an interactive TV for example the IPTV according to an embodiment of the present invention S . The interactive TV boots up S . The interactive TV requests IP address and network setting S and performs an IP address and network setting procedure S . A widget manager of the interactive TV executes the EAS widget application S and an event handler of the EAS widget application is registered in the interactive TV S . Step S may further include for example the step of previously registering the interactive TV in an EAS related server.

The EAS widget application determines whether or not an IP address has been allocated to the interactive TV S . When it is determined that an IP address has been allocated the EAS widget application determines the position of the user of the interactive TV S .

The EAS widget application receives EAS data from the EAS related server S . The EAS widget application collects EAS data from a server that provides a specified EAS service S . The EAS widget application processes and stores the collected EAS data S .

The EAS widget application determines whether or not an event has been received through a 3rd party notification handler S . If it is determined that an event has been received the EAS widget application notifies the user of the event using an EAS message S .

The following is a summary of the embodiment of the present invention described above with reference to .

The method of controlling an emergency alert system EAS widget application in an IPTV includes executing the EAS widget application directly receiving additional emergency alert information from an EAS server connected to an Internet Protocol IP network and performing control to display the additional emergency alert information on the EAS widget application.

Here the receiving step includes identifying a region in which the IPTV is located and accessing an EAS server corresponding to the identified region.

The receiving step includes receiving the additional emergency alert information from an EAS server in which information identifying the region in which the IPTV is located has been previously registered.

The EAS widget application calls at least one EAS extension Application Programming Interface API . The EAS extension API will be described in more detail with reference to .

According to another embodiment of the present invention the EAS widget application is executed using a method of acquiring an address of an EAS related server from an MPEG 2 TS. The server address acquisition method may be manually set or may be set through a remote control procedure and may also be set using a Dynamic Host Configuration Protocol DHCP method.

The descriptor can be used to store URL addresses since a descriptor length is 1024 bytes as shown in . However the structure of descriptor  is changed as shown in in order to notify the TV of presence of a URL in the descriptor that is inserted in an entry A in the emergency alert table shown in .

As shown in descriptor tags are used to discriminate between descriptors. For example when a descriptor tag has a value of 0x03 the descriptor tag identifies a URI descriptor. Detailed examples of the URI descriptor that is included in the emergency alert table of are illustrated in .

That is illustrates a detailed example of the URI Descriptor that is added to the emergency alert table of .

When the descriptor tag has a value of 0x03 the descriptor tag of is also set to 0x03 as shown in . When the descriptor length is set to 8 bits URI information of up to 256 bytes can be included in the descriptor.

The emergency alert table may also be designed such that a URI Descriptor is located in entry B in . In this case the URI Descriptor is changed as shown in according to an embodiment of the present invention.

When the structure of URI Descriptor is designed as shown in a plurality of URI descriptors may be included in the URI Descriptor structure. In the case where URI Descriptors are added individually in this manner the size of each URI Descriptor can be adjusted variably and thus it is possible to transmit a URI address containing an unlimited amount of additional information. For example when a URI Descriptor length shown in is set to 15 bits the URI Descriptor can be extended to 32 Kbytes. However if a URI Descriptor is located in an extensible descriptor there is an advantage in that it is possible to extend the URI Descriptor while minimizing modification of the existing transmitter and receiver.

The following is a summary of an embodiment of the present invention described above with reference to .

An embodiment of the present invention defines a method of controlling data for an emergency alert system EAS in a digital broadcast receiver able to receive cable broadcast data.

The method includes steps of receiving a digital broadcast signal including an emergency alert table including a uniform resource identifier URI descriptor detecting a URI address included in the URI descriptor accessing the URI address receiving additional emergency alert information from the URI address and performing control to display the additional emergency alert information on a screen of the digital broadcast receiver.

The method further includes executing an EAS widget application. Moreover the controlling step includes performing control to display the additional emergency alert information on the EAS widget application using the URI address.

The EAS extension API includes at least one of a first API used to determine a region in which the IPTV is located using an IP address of the IPTV a second API used to allow the EAS widget application to be displayed in a layer above other widget applications a third API used to most preferentially perform access to an EAS server a fourth API used to forcibly tune to an EAS channel and a fifth API used to limit partial functionality of the IPTV during execution of the EAS widget application.

The EAS widget application calls at least one EAS extension Application Programming Interface API . The EAS extension API will be described in more detail with reference to .

As shown in an interactive TV includes for example a connector handler a 3rd party notification handler an event notification handler a UI shell a user input handler a bookmarks profiles an XHTML browser a save restore handler an A V control point an A V media renderer and a prioritized event scheduler . This embodiment may also be complementarily construed with reference to if needed.

A browser is used to render and control a user interface delivered by a server. For example the browser corresponds to the XHTML browser .

A first handler is used to forward a first event to the browser for processing. For example the first handler corresponds to the user input handler .

A second handler is used to send and receive a second event during active interaction via server supplied scripts. For example the second handler corresponds to the event notification handler .

A third handler is used to process a third event and invoke the browser to fetch and render UI content using a URL contained within the third event. For example the third handler corresponds to the 3rd party notification handler .

The prioritized event scheduler connects the event notification handler the user input handler the third party notification handler and the browser wherein the prioritized event scheduler further reorders sequences based on priorities which the first event second event and third event is to be transmitted to the browser.

The prioritized event scheduler cancels or discards or delays or postpones some events according to the priorities. The prioritized event scheduler assigns highest priority to an event associated with emergency alert information.

The prioritized event scheduler newly suggested in the present invention is connected to all of the user input handler the event notification handler and the 3rd party notification handler . The prioritized event scheduler is designed to be responsible for and process all notifications or events received through a remote UI client or the interactive TV .

In the case where the prioritized event scheduler is added to the client TV as shown in notifications or events received from a number of handlers may be reordered according to priorities and may be canceled or delayed as needed thereby overcoming the problem that delivery of the most important message such as an EAS message is delayed or the most important message is not received.

In the case where the prioritized event scheduler is added to the client TV as shown in there is an advantage in that it is possible to reduce the number of event handlers to be managed by the XHTML browser from a plurality of event handlers for example and to one event handler for example . Accordingly it is possible to control all handlers using a unified function.

To normally run the EAS widget application described above there is a need to define object APIs to be used by the EAS widget application. These object APIs may be named EAS extension APIs .

A plurality of EAS extension APIs may be defined as shown in . For example a first API used to determine a region in which the IPTV is located using an IP address of the IPTV is named for example GetHostIpAddress .

In addition a second API used to allow the EAS widget application to be displayed in a layer above other widget applications is named for example DisplayEASWidgetOnTop .

Further a third API used to most preferentially perform access to an EAS server is named for example ConnectEASServer .

Furthermore a fourth API used to forcibly tune to an EAS channel is named for example ChangeEASChannel . In addition a fifth API used to limit partial functionality of the IPTV during execution of the EAS widget application is named for example SetHostControlPolicy .

A network interface is responsible for functions associated with receiving sending IPTV packets and physical data link layers.

A TCP IP manager is responsible for functions associated with end to end source to destination packet delivery and classifying packets into appropriate protocol managers.

A service delivery manager is responsible for functions associated with handling real time streaming data and downloading content and also responsible for functions associated with retrieving content from a content DB for later consuming.

A demultiplexer is responsible for functions associated with de multiplexing audio video and PSI tables from input transport packets and controlling the de multiplexing for PSI tables by a PSI Decoder and making the sections of PSI tables and sending the same to the PSI Decoder and controlling the de multiplexing for A V transport packets.

A PSI PSIP and or DVB SI decoder is responsible for functions associated with setting PIDs for PSI tables and PSIP DVB SI tables to the demultiplexer and decoding the private sections of PSI and PSIP and or DVB SI sent by the demultiplexer. The decoding result is used to de multiplex input transport packets e.g. set Audio and Video PID to the demultiplexer . The decoder also functions as an audio and video decoder for decoding audio and video elementary stream packets.

An A V and OSD displayer is responsible for functions associated with receiving audio and video data from A V Decoder controlling video and audio data displaying the video data on a screen outputting the audio data through a speaker and controlling On Screen Display OSD Graphic data.

An audio and video decoder is responsible for functions associated with decoding audio and video elementary stream packets.

A video filter processor is responsible for functions associated with processing the video filter in all areas of user selections or an entire video screen. The video filter processor may access the video frame buffer memory to manipulate or adjust video or still pictures.

A User Interface UI manager is responsible for functions associated with supporting the Graphical User Interface on a TV Screen and receiving a user key through a remote control or front panel and managing the states of the entire TV system.

A Service manager is responsible for functions associated with controlling all other managers relating to the services such as service control manager service delivery manager IG OITF client service discovery manager and metadata manager services and is also responsible for supporting or providing IPTV services.

An SI metadata DB is a database of service discovery information and metadata relating to the services.

A service discovery SD manager is responsible for functions associated with enabling the discovery of IPTV services over a bi directional IP network and providing all information for selecting services.

A service control manager is responsible for functions associated with selecting and controlling services and managing sessions selecting live broadcasting services using an IGMP or RTSP protocol and selecting VOD content using an RTSP protocol. If IMS is used the service control manager may use an SIP protocol for initiating and managing sessions through an IMS Gateway. The service control manager may also use the RTSP protocol to control delivery of TV broadcasts audio and on demand data. The RTSP protocol uses persistent TCP connection and allows trick mode control of real time media streaming.

A Content DB is a database of content which may be delivered by a content download system or may be recorded by a live media TV.

A PVR manager is responsible for functions associated with recording and playing back live streaming content and gathering all necessary metadata of the recorded content and generating additional information for better user experience e.g. thumbnail image index etc .

A metadata manager is responsible for functions associated with handling metadata such as TV Anytime BCG and ECG related to a service.

A video display processor processes video display information and a graphic processor processes graphic information.

The system may maintain user information all information associated with widgets installed widgets and active inactive widgets preferences and the ITF receiver s hardware compatibility and standard profile. User Profile data stored in a user profile preferences storage may be read from a widget launcher a widget manager and a web browser when the user logs into the system or deletes downloaded widget applications.

A widget launcher executes an installed widget when the user logs into the system and executes the activated widget when the user changes the downloaded widget application.

A widget manager displays all widget applications which can be installed and executed in the ITF requests downloading of a widget application that the user has selected from servers activates inactivates the downloaded widget deletes the downloaded or running widget and controls the running widget and changes the location of the widget on the screen.

The Widget application calls a predefined module or control interface in the ITF. The EAS Extension is one of a number of manufacturer extensions. The EAS Extension operates with Widget Runtime middleware . The EAS Widget application calls the predefined EAS Extension APIs.

A web browser Declarative Application Environment may render HTML pages on the screen and parse documents according to the W3C specification.

The Real Time Transport Protocol RTP Control Protocol RTP RTCP may be used with MPEG 2 TSs. MPEG 2 packets are encapsulated in an RTP. RTP packets may be parsed and the parsed transport packets may be sent to the demultiplexer. Moreover feedback on the network reception quality is sent using the RTCP. MPEG 2 transport packets may be carried directly in a UDP without an RTP. For content downloading the HTTP or FLUTE protocol may be used for delivery.

Although the embodiments of the present invention have been individually described with reference to the features of the embodiments shown in may be combined as needed to implement other embodiments.

The embodiments of the present invention described above suggest architectures required to implement emergency alert in an interactive TV or IPTV so that smooth transmission of emergency messages is achieved using a unified notification method. The embodiments of the present invention also suggest a method for managing event handlers and a method for receiving a variety of emergency alert messages which are required when an emergency alert widget application is implemented using a widget thereby enabling efficient receiver operations. The embodiments of the present invention also suggest how a widget application provides additional service information regarding an emergency to the user when an emergency alert message is received through an OOB or in band so that the widget application can operate not only in an interactive TV but also in a one way cable DTV receiver even when the widget application is embedded in the TV receiver. Of course the widget application is designed to be free from compatibility problems since the bidirectional cable DTV receiver supports bidirectionality.

Each of the methods according to the present invention may be implemented in the form of program commands that are executable by a variety of computer means and may then be recorded on a computer readable medium. The computer readable medium may include program commands data files data structures and the like individually or in combination. The program commands recorded on the medium may be specially designed and configured for the present invention or may be known and available to those skilled in computer software. Examples of the computer readable recording medium include magnetic media such as a hard disk a floppy disk and a magnetic tape optical media such as a CD ROM and a DVD magneto optical media such as a floptical disk and hardware devices specially configured to store and execute program commands such as a ROM a RAM and a flash memory. Examples of the program commands include not only machine language code such as that produced by a compiler but also high level language code that may be executed by a computer using an interpreter or the like. The hardware devices described above may be configured to operate as one or more software modules to perform the operations of the present invention and vice versa. Although the present invention has been described in conjunction with the limited embodiments and drawings the present invention is not limited to the embodiments. Those skilled in the art will appreciate that various modifications additions and substitutions are possible from this description. Therefore the scope of the present invention should not be limited to the description of the exemplary embodiments and should be determined by the appended claims and their equivalents.

