---

title: Method and apparatus for transmitting and receiving service in a wireless communication system
abstract: A method and apparatus transmits and receives a service in a wireless communication system by acquiring Quality of Service (QoS) information. A packet is received through a direct communication with a terminal equipment providing a service. When the received packet includes a new destination Internet Protocol (IP) address different from a previously received packet, one or more service quality identifiers corresponding to the received packet are identified. The identified service quality identifiers are transmitted to the terminal equipment, and a service quality identifier corresponding to a service category selected by a user from the identified service categories is received from the terminal equipment. QoS information corresponding to the received service quality identifier is determined and used to generate a radio link between the mobile equipment and a mobile communication network. And the service is received through the radio link.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08792471&OS=08792471&RS=08792471
owner: Samsung Electronics Co., Ltd.
number: 08792471
owner_city: Suwon-Si
owner_country: KR
publication_date: 20100803
---
The present application is related to and claims the priority under 35 U.S.C. 119 a of an application entitled Method And Apparatus For Transmitting And Receiving Service In A Wireless Communication System filed in the Korean Industrial Property Office on Aug. 4 2009 and assigned Serial No. 10 2009 0071723 the contents of which are hereby incorporated by reference.

The present invention relates to a wireless communication system and more particularly to a method and an apparatus for transmitting and receiving a service in a wireless communication system.

With development in the high speed wireless data communication technology such as Long Term Evolution LTE High Speed Packet Access HSPA and High Rate Packet Data eHRPD users of a terminal equipment such as a Personal Computer PC can receive a real time service through a mobile communication network such as a Voice over Internet Protocol VoIP phone Internet phone service or an image communication service by using a corresponding application.

The terminal equipment can use a mobile equipment in order to access a mobile communication network. At this time the mobile equipment is required to secure a guaranteed Quality of Service QoS corresponding to a service that enables the user to achieve an optimal use of the service. Therefore the mobile equipment generates a wireless link for transmitting and receiving a service according to QoS information of an application being executed in the terminal equipment i.e. an application for providing the service.

It is impossible for a conventional mobile equipment to take QoS information from an application of a terminal equipment. Accordingly the application of the terminal equipment should transmit the QoS information to a corresponding mobile equipment by using an Application Programming Interface API provided by a modem.

For this reason a particular interface for transmitting and receiving QoS information is constructed between a mobile equipment and an application of a terminal equipment. When the mobile equipment has received QoS information through the interface the mobile equipment generates a wireless link in response to the received QoS information. Further the mobile equipment receives a service from a corresponding application by using the generated wireless link.

A process of information transmission and reception between a terminal equipment and a mobile equipment in a conventional wireless communication system will be described in detail with reference to .

Referring to the conventional wireless communication system includes a terminal equipment for providing a service to a user and a mobile equipment for accessing a mobile communication network and transmitting a service to the terminal equipment .

First the terminal equipment includes three applications and for providing an e mail service an internet phone VoIP service and an image conference Net meeting service respectively.

Each of the applications and includes an interface or for transmitting QoS information to the mobile equipment . Each of the applications and notifies the mobile equipment by using the interface or of the execution of the service and requests the mobile equipment to generate a wireless link for the service according to the transmission of the QoS information.

The applications and are configured in accordance with the type and version of the software installed in the mobile equipment . Therefore the applications and can provide a corresponding service only through a mobile equipment using particular software. Further the applications and should be updated whenever the type and version of the software are changed.

Meanwhile the mobile equipment includes a communication module for performing a communication with the applications and of the mobile equipment . The communication module receives QoS information transmitted from an application selected by the user from among the applications and and generates a wireless link by using the received QoS information. Further the communication module receives a service from a corresponding application by using the generated wireless link.

As described above an application of a terminal equipment is not universal for multiple mobile equipments and is dependent on a specific mobile equipment. That is the application of the terminal equipment depends on the software used by a corresponding mobile equipment.

Therefore the user can only receive a service from a particular terminal equipment according to the software employed by the mobile equipment used by the user. Moreover when the software of the mobile equipment is changed the terminal equipment should update corresponding software or employ another application or an additional interface in order to continuously provide the service.

To address the above discussed deficiencies of the prior art it is a primary object to provide a method and an apparatus for transmitting and receiving a service in a wireless communication system.

Also the present invention provides a method and an apparatus for service transmission and reception which enable a terminal equipment to provide an application service through a mobile communication network to a user by using a mobile equipment in a wireless communication system.

Moreover the present invention provides a method and an apparatus for service transmission and reception which enable a mobile equipment to acquire QoS information regardless of the application of a terminal equipment in a wireless communication system.

In addition the present invention provides a method and an apparatus for service transmission and reception by which a mobile equipment connected to a terminal equipment can acquire exact QoS information according to a corresponding service in a wireless communication system such that a user of the terminal equipment can use an optimum service according to the acquired QoS information.

In accordance with an aspect of the present invention there is provided a method of receiving a service by a mobile equipment in a wireless communication system the method including receiving a packet through a direct communication with a terminal equipment providing a service. When the received packet includes a new destination Internet Protocol IP address different from an IP address of a previously received packet one or more service quality identifiers corresponding to the received packet are identified. The identified service quality identifiers are transmitted to the terminal equipment and a service quality identifier corresponding to a service category selected by a user from among the identified one or more service categories is received from the terminal equipment. Quality of Service QoS information corresponding to the received service quality identifier is determined. A radio link between the mobile equipment and a mobile communication network is generated according to the acquired QoS information and the service from the mobile communication network is received through the radio link.

In accordance with another aspect of the present invention there is provided a method of transmitting a service by a terminal equipment in a wireless communication system. The method includes transmitting a packet through a direct communication to a mobile equipment connected to a mobile communication network and receiving a service quality identifiers corresponding to one or more service categories according to the transmitted packet from the mobile communication network. One among the one or more service categories corresponding to the received one or more service quality identifiers is selected by a user. The selected service quality identifier corresponding to the service category selected by the user is transmitted to the mobile equipment and when a radio link is generated between the mobile equipment and the mobile communication network the service transmitted through the radio link is provided to the user.

In accordance with another aspect of the present invention there is provided an apparatus for receiving a service within a mobile equipment in a wireless communication system. The apparatus includes a direct communication unit receives a packet through a direct communication with a terminal equipment providing a service transmits one or more service quality identifiers identified based on the received packet to the terminal equipment and receives a selected service quality identifier selected by a user from among the one or more service quality identifiers corresponding to the received. A packet processing unit when the received packet includes a new destination Internet Protocol IP address different from an IP address of a previously received packet identifies the one or more service quality identifiers corresponding to the received packet. A Quality of Service QoS information processing unit acquires QoS information corresponding to the received service quality identifier. A wireless communication unit generates a radio link between the mobile equipment and a mobile communication network according to the acquired QoS information and receives the service from the mobile communication network through the radio link.

In accordance with yet another aspect of the present invention there is provided an apparatus for transmitting a service in a wireless communication system. The apparatus includes a transmission reception unit for transmitting a packet through a direct communication to a mobile equipment connected to a mobile communication network receiving service quality identifiers corresponding to one or more service categories according to the transmitted packet from the mobile communication network and transmitting a service quality identifier corresponding to a service category selected by the user to the mobile equipment. An input unit receives a selection of one service category from the one or more service categories corresponding to the received service quality identifier. An application unit when a radio link is generated between the mobile equipment and the mobile communication network provides the service transmitted through the radio link to the user.

Before undertaking the DETAILED DESCRIPTION OF THE INVENTION below it may be advantageous to set forth definitions of certain words and phrases used throughout this patent document the terms include and comprise as well as derivatives thereof mean inclusion without limitation the term or is inclusive meaning and or the phrases associated with and associated therewith as well as derivatives thereof may mean to include be included within interconnect with contain be contained within connect to or with couple to or with be communicable with cooperate with interleave juxtapose be proximate to be bound to or with have have a property of or the like and the term controller means any device system or part thereof that controls at least one operation such a device may be implemented in hardware firmware or software or some combination of at least two of the same. It should be noted that the functionality associated with any particular controller may be centralized or distributed whether locally or remotely. Definitions for certain words and phrases are provided throughout this patent document those of ordinary skill in the art should understand that in many if not most instances such definitions apply to prior as well as future uses of such defined words and phrases.

The present invention proposes a method and an apparatus for transmitting and receiving a service in a high speed wireless communication system such as a Long Term Evolution LTE system a High Speed Packet Access HSPA system and a High Rate Packet Data eHRPD system. Specifically the present invention proposes a method and an apparatus for transmitting and receiving a service in a wireless data communication system by which a terminal equipment can provide an application service through a mobile communication network to a user by using a mobile equipment. Further the present invention proposes a method and an apparatus for transmitting and receiving a service in a wireless data communication system by which a mobile equipment can acquire QoS information regardless of an application of a terminal equipment.

For convenience of description the following description of the present invention employs a Personal Computer PC as an example of the terminal equipment. However the terminal equipment may be other devices such as a Personal Digital Assistant PDA and a mobile communication terminal providing a service as well as the PC.

Hereinafter a wireless communication system for service transmission reception between a terminal equipment and a mobile equipment according to an embodiment of the present invention will be described with reference to .

Referring to a wireless communication system for service transmission reception according to an embodiment of the present invention includes a terminal equipment for providing a service to a user and a mobile equipment for accessing a mobile communication network and transmitting a service to the terminal equipment . The terminal equipment and the mobile equipment are interconnected through a Universal Serial Bus USB or Personal Computer Memory Card International Association PCMCIA slot and such. That is the terminal equipment and the mobile equipment can perform a direct communication with each other.

First the terminal equipment includes three applications and for providing an e mail service an internet phone VoIP service and an image conference Net meeting service respectively. Although shows only three applications and the terminal equipment may further include at least one application for providing a game image communication or Video On Demand VOD service in addition to the three applications and or may include less than three applications.

The terminal equipment includes a communication module for performing a communication with the mobile equipment in order to access a mobile communication network. The applications and provide a service through the mobile communication network by using the communication module .

The communication module is not dependent on the software installed in the mobile equipment . That is although each application within a terminal equipment should be updated according to version information and type of software installed in the mobile equipment the mobile equipment and the terminal equipment can be interconnected through the communication module even without update of the applications and in the present embodiment.

As a result the terminal equipment can provide a service to users by using various mobile communication apparatuses regardless of whether it is a terminal equipment provided with particular software.

Meanwhile the mobile equipment includes a communication module for performing a communication with the applications and of the terminal equipment .

The mobile equipment acquires QoS information of an application selected by a user from among the applications and of the terminal equipment by communicating with the terminal equipment through the communication module . The mobile equipment generates a wireless link corresponding to the acquired QoS information and receives a service from the selected application by using the generated wireless link. The operation of acquiring the QoS information and generating a wireless link by the mobile equipment will be described later in more detail.

Hereinafter a construction of the terminal equipment and the mobile equipment in the wireless communication system as described above will be discussed in more detail. The following discussion mainly deals with the communication module of the terminal equipment and the communication module of the mobile equipment .

As described above the mobile equipment includes a communication module for receiving a service from the applications and of the terminal equipment . The communication module includes a control unit a transmitting receiving unit a packet processing unit a Domain Name System DNS unit a control packet processing unit a QoS information processing unit and a wireless communication unit .

First the control unit controls the general operation of the transmitting receiving unit the packet processing unit the DNS unit the control packet processing unit the QoS information processing unit and the wireless communication unit .

The transmitting receiving unit enables the mobile equipment to transmit and receive packets or messages through a direct communication with the terminal equipment . Specifically the transmitting receiving unit receives packets transmitted through a USB or PCMCIA slot from the terminal equipment wherein the received packets refer to service packets provided by an application of the terminal equipment . The transmitting receiving unit can receive the service packets when the user newly executes an application which is not being executed or accesses another Uniform Resource Locator URL different from a currently connected URL.

The transmitting receiving unit transmits or receives a control message to or from the terminal equipment through the USB or PCMCIA slot. The control message is a message for acquiring QoS of the mobile equipment and will be described later in more detail.

Meanwhile according to an embodiment of the present invention the transmitting receiving unit may include a transmission unit and a reception unit separated from each other. The transmitting receiving unit may be a host interface for communication with an external device.

The packet processing unit includes a packet monitoring unit a packet filtering unit and a packet analysis unit for processing the packets received through the transmitting receiving unit .

The packet monitoring unit monitors all packets received through the transmitting receiving unit . The packet filtering unit checks a target Internet Protocol IP address of a packet monitored by the packet monitoring unit and determines whether the checked IP address is different from a destination IP address of a previously received packet.

Further when the checked IP address is different from a destination IP address of a previously received packet the packet filtering unit recognizes the packet as a new packet and the checked destination IP address of the packet to the DNS unit .

The packet analysis unit analyzes the service to which the packet is related based on the destination IP address of the packet the protocol and the port number. The packet analysis unit acquires the information including the protocol the port number and such from URL information output from the DNS unit i.e. the URL information corresponding to the destination IP address of the packet. Further the packet analysis unit identifies a QoS Class Identifier QCI that corresponds to the packet based on a QoS index mapping table stored in advance. For example the QoS index mapping table may be configured as shown in Table 1 below.

It is noted from that the QCI is determined by the destination IP address protocol and port number of a packet for each application. For example when the protocol of a packet is User Datagram Protocol UDP and the port number of the packet is 5060 the packet analysis unit determines that the packet is a Session Initiated Protocol SIP packet which provides an Internet Phone service or image communication service. Further the packet analysis unit identifies QCIs 1 2 and 6 which correspond to the Internet phone service and the image communication service as selectable QCIs and outputs information of the identified selectable QCIs together with corresponding URL information to the control packet processing unit under the control of control unit .

The DNS unit converts the destination IP address of the packet to Uniform Resource Locator URL information and then stores the URL information. Further under the control of the control unit the DNS unit transmits the URL information to the packet analysis unit .

The control packet processing unit receives a packet analysis result output from the packet analysis unit . The packet analysis result includes URL information and the selectable CQI information indicating categories which can be provided by the packet. For example the selectable CQI information may include QCI 1 indicating the Internet phone service and QCIs 2 and 6 indicating the image communication service.

The control packet processing unit generates a control message for QoS acquisition by using the URL information and the selectable CQI information. The control message is generated in the form as shown in according to an embodiment of the present invention.

Referring to the control message includes an Ethernet header part that includes identification information of a corresponding control message and a control message part that includes information to be actually transmitted.

The Ethernet header part includes a destination address DA field a source address SA field and a type field . The DA field and the SA field include Media Access Control MAC addresses of the receiver and the transmitter i.e. MAC addresses of the terminal equipment and the mobile equipment . Further the type field defines a protocol of a network layer.

The control message part includes an operation OP code field and a data field . The OP code field includes a particular operation to be executed and the data field includes information to be actually transmitted that is the URL information and the selectable QCI information.

When a control message such as one described above is generated in the control packet processing unit the control unit transmits the generated control message to the terminal equipment through the transmitting receiving unit .

Upon receiving a control message including QCI information selected by the user that is QCI information indicating the service category selected by the user from among the selectable QCI information from the terminal equipment as a response to the transmission of the control message including the selectable QCI information the QoS information processing unit acquires the QCI information from the received control message. Further the QoS information processing unit acquires QoS information corresponding to the acquired QCI information such as QoS parameter information.

In the meantime when the selectable QCI information output from the packet analysis unit includes a single QCI information item the QoS information processing unit can acquire QoS information corresponding to the single QCI information item. For example when the selectable QCI information includes QCI 3 only the VOD service corresponding to QCI 3 can be acquired. Therefore the control packet processing unit does not need to generate a control message in this situation.

Upon acquiring the QoS information the wireless communication unit transmits a Packet Data Protocol PDP context request message including the QoS information to a management node of a mobile communication network in order to generate a wireless link with the mobile communication network. The management node may be for example a Serving General Packet Radio Service GPRS Support Node SGSN .

The PDP context request message is a message through which the mobile equipment requests a connection for transmission reception of a packet with the management node. After transmitting the PDP context request message the wireless communication unit can establish a connection with the management node i.e. a wireless link. The wireless communication unit generates a new session with the management node and receives the corresponding service packet and allocated radio resources from the management node. Thereafter the wireless communication unit sets a radio access bearer. At this time the wireless communication unit sets a packet filter for receiving the corresponding service packet.

The packet filter receives service packets which have been transmitted from the management node according to preset filter values. That is the packet filter enables packets according to an application providing a service selected by a user to be received through the set radio access bearer from the management node. Therefore the mobile equipment can continuously transmit the packets according to the application to the terminal equipment .

The mobile equipment that includes the construction as described above can acquire accurate QoS information for use of a service from various terminal equipments regardless of the installation of particular software. Furthermore the mobile equipment acquires QoS information according to the QCI information so as to enable a user of the terminal equipment to use a service with an optimum quality.

Next the terminal equipment according to an embodiment of the present invention will be described with reference to .

Referring to the terminal equipment includes a control unit a transmission reception unit an application unit a packet processing unit a display unit and an input unit . The transmission reception unit and packet processing unit may perform the same function as the communication module for providing a service to the mobile equipment as described above with reference to .

The control unit controls the general operation of the transmission reception unit the application unit the packet processing unit the display unit and the input unit .

The transmission reception unit transmits a packet to the mobile equipment through a USB or PCMCIA slot. When the user newly executes an application or accesses another Uniform Resource Locator URL different from a currently connected URL the transmitting receiving unit transmits a service packet which is provided through the application or the URL to the mobile equipment . After transmitting the packet the transmission reception unit performs transmission reception of a control message with the mobile equipment .

Although the transmission reception unit is a single unit in the transmission reception unit may be separated to a transmission unit and a reception unit according to another embodiment of the present invention. Furthermore according to the present embodiment based on an example in which the terminal equipment is a personal computer the transmission reception unit may be a device driver functioning as an interface between hardware and the application unit and an operating system.

The application unit includes applications that provide services related to Internet phone image communication e mail image conference game and so forth. Furthermore the application unit executes at least one of the applications according to the user s selection.

Upon receiving a control message including URL information and selectable QCI information from the mobile equipment the packet processing unit parses the received control message according to the control of the control unit . Further the packet processing unit acquires the URL information and the selectable QCI information from the parsed control message. Further the packet processing unit transmits the acquired URL information and selectable QCI information to the control unit .

Thereafter the packet processing unit receives an input regarding a service category selected by the user from among service categories corresponding to the selectable QCI information through the control unit . Further the packet processing unit identifies QCI information corresponding to the input service category information. At this time the packet processing unit can identify the QCI information by using a service category based QCI mapping table stored in advance. For example the pre stored service category based QCI mapping table may be configured as shown in Table 2 below.

As shown Table 2 includes a QCI field a resource type field indicating a corresponding bit rate when a Guaranteed Bit Rate GBR is used a priority field a packet delay budget field a packet error loss rate field a service category field an eHRPD flow profile ID field and an eHRPD flow description field.

According to an embodiment of the present invention the QCI field and the service category field are used from among the fields of the service category based QCI mapping table. However other fields as well as the two fields can be used according to another embodiment of the present invention.

Referring to the QCI field and the service category field it is noted that a corresponding QCI is determined according to the service category. That is the Internet phone service conventional voice service corresponds to QCI 1 the image communication service conventional video live streaming service corresponds to QCIs 2 and 6 the VOD service Non conventional video buffered streaming service corresponds to QCI 3 the game service real time gaming service corresponds to QCI 5 and a Transmission Control Protocol TCP based service such as services associated with e mail Hypertext Transport Protocol HTTP File Transfer Protocol FTP and chatting corresponds to QCIs 7 8 and 9 .

For example when the selectable QCI information includes QCIs 1 2 and 6 the user can select one service category from among the Internet phone service corresponding to QCI 1 and the image communication service corresponding to QCIs 2 and 6 . The packet processing unit then identifies QCI information corresponding to the selected service category and generates a control message including the identified QCI information. The control message has the same format as that of the control message generated by the mobile equipment as shown in .

Under the control of the control unit the display unit provides a screen as shown in to the user by using the acquired URL information and selectable QCI information.

Referring to the display unit displays the URL information and a service category list that includes the selectable QCI information. The control unit uses the service category based QCI mapping table in controlling the display of service categories corresponding to the selectable QCI information on the display unit .

For example when the selectable QCI information includes QCIs 1 2 and 6 the display unit displays service categories of the Internet phone service corresponding to QCI 1 and the image communication service corresponding to QCIs 2 and 6 . Further the display unit displays a screen on which a user can select a desired service category from among the displayed service categories.

The input unit receives an input of one service category by the user from among the service categories displayed on the display unit and then transmits information on the input service category to the control unit . Then the control unit identifies QCI information corresponding to the input service category and outputs the identified QCI information to the packet processing unit .

As described above the terminal equipment receives the URL information and the selectable QCI information from the mobile equipment and receives an input of one service category by the user from among the service categories corresponding to the selectable QCI information. Further the terminal equipment identifies QCI information corresponding to the input service category and transmits a control message including the identified QCI information to the mobile equipment . The mobile equipment can then acquire QoS information according to the corresponding service by using the control message.

In the wireless communication system as described above the process of service transmission reception between the terminal equipment and the mobile equipment includes five stages including a first stage in which the mobile equipment identifies a new packet and transmits a control message including QCI information a second stage in which the terminal equipment identifies service category information selected by a user from among service categories corresponding to QCI information received from the mobile equipment a third stage in which the mobile equipment identifies QoS information by using the QCI information corresponding to the service category selected by the user a fourth stage in which the mobile equipment receives an allocated radio resource and sets a packet filter and a fifth stage in which the communication module receives packets which have been transmitted according to a corresponding application from a mobile communication network through the packet filter. The five stages are sequentially performed.

The first stage in which the mobile equipment identifies a new packet and transmits a control message including QCI information will be described with reference to .

Referring to in block the packet monitoring unit monitors all packets received through the transmitting receiving unit from the terminal equipment while determining whether a packet has been received. The packet reception through the transmitting receiving unit may be achieved when the user newly executes an application which is not currently being executed or accesses another URL different from a currently connected URL.

In block the packet filtering unit determines whether the checked destination IP address is a new destination IP address. That is the packet filtering unit determines whether the checked destination IP address is a new destination IP address different from a destination IP address of a previously received packet.

As a result of the determination when the checked destination IP address is not a new destination IP address the packet filtering unit terminates the entire process. In contrast as a result of the determination when the checked destination IP address is a new destination IP address the packet filtering unit recognizes the received packet as a new packet and transmits the checked destination IP address to the DNS unit .

In block the DNS unit converts the destination IP address of the corresponding packet to URL information through DNS processing and stores the URL information.

In block the packet analysis unit analyzes the corresponding packet by using the URL information. The packet analysis unit then analyzes the protocol the port number and such acquired from the URL information so as to determine the service to which the packet is related.

In block the packet analysis unit identifies selectable QCI information according to a result of the packet analysis. Specifically the packet analysis unit identifies the QCI corresponding to the packet based on the QoS index mapping table as shown in Table 1 described above.

The selectable QCI information output from the packet analysis unit is output together with the corresponding URL information to the control packet processing unit . In block the control packet processing unit generates a control message for QoS acquisition by using the URL information and selectable QCI information. In an embodiment the control message has a configuration as shown in .

In block the transmitting receiving unit transmits the generated control message to the terminal equipment .

As described above in the first stage the mobile equipment recognizes a packet that includes a new destination IP address analyzes the packet to determine the service provided by the packet and transmits a control message including selectable QCI information based on a result of the analysis to the terminal equipment .

The second stage in which the terminal equipment identifies service category information selected by a user from among service categories corresponding to QCI information received from the mobile equipment will be described with reference to .

Referring to in block the transmission reception unit receives the control message transmitted from the mobile equipment . The received control message includes the URL information and the selectable QCI information.

In block the packet processing unit parses the received control message and acquires the URL information and the selectable QCI information from the parsed control message. The packet processing unit outputs the URL information and the selectable QCI information to the display unit .

In block the display unit displays a service category list corresponding to the URL information and the selectable QCI information on a screen. The service category list corresponding to the selectable QCI information displayed on the display unit may be generated by using the service category based QCI mapping table as shown in Table 2.

In block the control unit determines whether the user has selected a service category. That is the control unit determines whether the user has input one of the service categories displayed on the display unit through the input unit .

When the user has selected a service category the control unit proceeds to block in which the control unit identifies QCI information corresponding to the selected service category. The identified QCI information is output to the packet processing unit . In block the packet processing unit generates a control message by using the identified QCI information. The control message has the configuration as shown in and includes the identified QCI information.

When the generation of the control message is completed the transmission reception unit transmits the generated control message to the mobile equipment in block .

In the second stage as described above the terminal equipment receives a control message including QCI information from the mobile equipment receives an input of one service category from the user from among the service categories corresponding to the QCI information and transmits a control message including QCI information corresponding to the input service category to the mobile equipment .

The third stage in which the mobile equipment identifies QoS information by using the QCI information corresponding to the service category selected by the user will be described with reference to .

Referring to in block the transmitting receiving unit receives a control message transmitted from the terminal equipment . The received control message includes QCI information indicating the service category selected by the user.

In block the QoS information processing unit acquires the QCI information from the control message. Because the QCI information corresponds to an identifier indicating a particular QoS the QoS information processing unit can acquire QoS information corresponding to the acquired QCI information in block .

As noted from the third stage the terminal equipment does not unilaterally transmit the QoS information to the mobile equipment but rather enables the mobile equipment to determine the QoS information through the QCI information. Therefore the mobile equipment can connect with the terminal equipment regardless of software information and the user of the terminal equipment can conveniently use the service of the mobile communication network through the mobile equipment .

Hereinafter the fourth stage in which the mobile equipment receives an allocated radio resource and sets a packet filter will be described with reference to .

Referring to in block the wireless communication unit generates a PDP context request message including QoS information.

In block the wireless communication unit transmits the generated PDP context request message to a management node of the mobile communication network. For example the management node may be a Serving General Packet Radio Service GPRS Support Node SGSN .

When a radio link with the terminal equipment is established according to transmission of the PDP context request message the wireless communication unit generates a new session with the management node in block . The generated session is used in order to receive a service from a particular application of the terminal equipment .

In block the wireless communication unit receives allocation of a radio resource from the management node. When it is determined in block that the allocation of a radio resource has been completed the wireless communication unit proceeds to block in which the wireless communication unit sets a radio access bearer.

In block the wireless communication unit sets a packet filter for receiving a packet according to a corresponding application. The wireless communication unit may then receive a packet according to an application providing the service selected by the user through the set radio bearer.

In the fourth stage as described above the mobile equipment generates a PDP context request message by using the acquired QoS information receives allocation of a radio resource in response to the transmission of the PDP context request message sets a radio access bearer and sets a packet filter corresponding to a packet to be received. That is even without receiving the QoS information the mobile equipment can acquire the QoS information and transmit a service according to a corresponding application to the terminal equipment .

The fifth stage corresponds to a process in which a mobile equipment receives packets which are transmitted according to a corresponding application from a mobile communication network through a packet filter according to QoS information.

The fifth stage will now be described with reference to which illustrates a process in which a mobile equipment receives packets that are transmitted according to a corresponding application from a mobile communication network through a packet filter according to QoS information according to an embodiment of the present invention.

Referring to in block the wireless communication unit determines whether a packet based on an application of the terminal equipment has been received. The wireless communication unit monitors all packets received through the mobile communication network.

As a result of the determination when a packet has been received the wireless communication unit checks an existence of a packet filter corresponding to the received packet in block . When it is determined in block that the packet filter exists the wireless communication unit proceeds to block in which the wireless communication unit receives packets according to an application of the packet by using a preset radio access bearer. Accordingly a user of the mobile equipment can achieve an optimum use of a desired service according to the acquired QoS information.

Meanwhile when it is determined in block that the packet filter does not exist the wireless communication unit terminates the process of . In this situation the first stage as shown in can be performed again.

In the fifth stage as described above the mobile equipment receives packets according to the corresponding application by using the packet filter set in . In addition the mobile equipment transmits the received packet to the terminal equipment . Therefore the user can continuously use the service from the desired application by using the mobile equipment .

Through the five stages or processes described above the mobile equipment can determine QoS information even without separately receiving the QoS information from the terminal equipment. Furthermore the mobile equipment can acquire accurate QoS information so as to enable the user to use a service with an optimum performance.

According to the present invention without updating an application of a terminal equipment or using an additional interface a mobile equipment can acquire QoS information of the application. Additionally a mobile equipment can determine accurate QoS information corresponding to a service generate a radio link according to the acquired QoS and transmit an optimum service to a user of the terminal equipment.

Although the present disclosure has been described with an exemplary embodiment various changes and modifications may be suggested to one skilled in the art. It is intended that the present disclosure encompass such changes and modifications as fall within the scope of the appended claims.

