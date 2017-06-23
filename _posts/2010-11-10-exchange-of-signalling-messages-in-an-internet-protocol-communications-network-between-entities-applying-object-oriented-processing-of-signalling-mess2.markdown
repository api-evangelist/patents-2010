---

title: Exchange of signalling messages in an internet protocol communications network between entities applying object oriented processing of signalling messages
abstract: Signalling messages in an Internet Protocol, IP, communications network comprising a chain of at least two entities () applying object oriented processing () of signalling messages are exchanged between the at least two entities () of the IP communications network comprising object oriented based data items. Parsing and inverse parsing of text based signalling messages are effectively avoided, thereby reducing system resources and increasing processing speed of the system as a whole.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09648085&OS=09648085&RS=09648085
owner: Telefonaktiebolaget LM Ericsson (publ)
number: 09648085
owner_city: Stockholm
owner_country: SE
publication_date: 20101110
---
The present invention generally relates to signalling in an Internet Protocol IP communications network and more specifically to the exchange of signalling messages in an IP communications network comprising a chain of at least two entities applying object oriented processing of signalling messages.

Internet communications networks or Internet Protocol IP communications networks support a variety of telecommunications services including voice audio video and other data communications. Data are exchanged in packets using a set of communications protocols independent of underlaying transport technologies.

Examples of implementations of IP communications networks are amongst others Voice over IP VoIP networks and IP Multimedia Subsystem IMS communications networks.

Voice over Internet Protocol VoIP is a general term for voice or speech communications and multimedia communications sessions over packet switched IP networks. Other terms frequently encountered and synonymous with VoIP are IP telephony Internet telephony Voice over broadband VoBB broadband telephony and broadband phone.

Using packet switched IP networks allows for efficient allocation of network resources as packets are routed on paths with the least congestion. Packet header information comprises information about the packet s intended destination as well as information to reconstruct the data included in the packet at a receiving entity.

The IP Multimedia Subsystem IMS communications network is an architectural framework defined by the wireless standard setting body 3rd Generation Partnership Project 3GPP amongst others for delivering IP multimedia services to user terminals operating in a circuit switched or packet switched telecommunications network for example.

Fixed and wireless i.e. mobile communications such as called W CDMA CDMA2000 GSM GPRS WLAN WiMAX and others are supported by IMS through gateway servers. Dedicated IMS user equipment such as mobile phones Personal Digital Assistants PDAs and other communication equipment may directly register with an IMS communications network. The IMS also supports roaming in other networks or countries.

IP communications networks in general and IMS communications networks in particular typically comprise a separate content domain in IMS also called user plane and a separate signalling domain in IMS also called control plane. The content domain operates for the actual exchange of media for example audio video or data between a calling party and a called party during a communications session. The signalling domain amongst others operates to exchange signalling or control messages in relation to a communications session between a calling and called party not only to establish or terminate a session but also during a session to provide additional services for example. Besides the calling and called party other entities such as gateway servers media servers voice mail servers proxy servers such as called Proxy Call Session Control Function P CSCF servers and subscriber registrar Serving Call Session Control Function S CSCF servers associated with both the calling party and the called party may be involved in a communication session.

The signalling protocol used in IMS communications networks is called Session Initialisation Protocol SIP. SIP is a standardised application layer control protocol for the exchange of signalling messages between entities of an IMS communications network. Using SIP provides for many advantages for example its scalability its implementation and its support for both IP and conventional telephone communications.

The SIP protocol is text based and incorporates many elements of the HyperText Transfer Protocol HTTP and the Simple Mail Transfer Protocol SMTP. SIP call establishment poses large requirements on SIP entity processing capacity. The text based aspects of SIP imply that keywords and labels within a signalling message are recognized through byte by byte character comparison. Headers of a SIP message have a high degree of flexibility in terms of their position in the SIP message. This means that when decoding parsing a SIP message the decoder has to read the SIP message line by line until the required SIP header is found. Keywords and labels in SIP message are generally case insensitive. This has the effect that for recognizing keywords and labels a parser has to convert each and every character where case insensitivity applies to a normalized case such as upper case for example. Further the headers in SIP messages have a variable length. There is no length indicator per line of text. This implies that when reading a line a parser has to continue reading characters until a combination is encountered.

These aspects when using text based signalling messages in an IP communications network amongst others cause a relatively high processing load on the signalling processing entities in the network and consume a substantial amount of resources within such entities for encoding and decoding of the signalling messages. Further text based signalling messages are regarded as being vulnerable to eavesdropping.

Object oriented programming languages such as but not limited to JAVA C C dot NET Python Perl and Ruby are suitable for object oriented programming for executing operations in servers of for example an IP communications network. These object oriented programming languages utilize object oriented based data items such as object classes.

In present IMS communications networks for example JAVA is a commonly used object oriented programming language accommodated with a comprehensive SIP library for applying object oriented processing of signalling messages by the service logic of an entity operating in the communications network.

Entities of an IP communications network which process received text based signalling messages applying object oriented programming are arranged to convert parse received text based signalling messages into object oriented based data items for a JAVA Application Programming Interface API to operate. The entities are also arranged to reconstruct object oriented based data items back to text based signalling messages the inverse of the parsing process for exchanging same with a next entity of a chain of entities in an IP communications network.

The conversion of text based signalling messages to and from object oriented based data items causes a high load on the entities handling these signalling messages. In other words this is very resource intensive for these entities.

Future utilization and the number of IP communications networks are expected to grow gradually due to among others the increasing demand for IP services of users of communications devices such as mobile telephones and other user equipment. One of the challenges for operators of IP communications networks is to facilitate this increasing demand and at the same time maintain or improve the reliability efficiency and robustness of their network as a whole and the signalling domain in particular.

It is an object to provide an improved method of exchanging signalling messages in an IP communications network.

It is another object to provide for an entity for use in an IP communications network supporting the improved method of exchanging signalling messages.

It is a further object to provide for an IP communications system comprising at least two entities supporting the improved method of exchanging signalling messages.

In a first aspect there is provided a method of exchanging signalling messages in an Internet Protocol IP communications network the IP communications network comprising a chain of at least two entities applying object oriented processing of signalling messages. The method is characterised in that signalling messages exchanged between the at least two entities of the IP communications network comprise object oriented based data items.

The improved method is based on the insight that if communicating entities in a network are arranged for applying object oriented processing of signalling messages utilization of resources of these entities is reduced when signalling messages exchanged between these entities comprise object oriented based data items. The use of resources of entities in the communications network is mainly reduced since these entities do not need to convert text based signalling messages to object oriented based signalling messages and vice versa.

By removing both types of conversions a significant reduction in the processing time of signalling messages is achieved due the absence of the time consuming parsing process and the inverse of the parsing process as detailed in the background section above. In particular when an increasing amount of signalling entities applying processing of object oriented based data items are chained in an IP communications network due to the absence of multiple conversions of the signalling messages exchanged the improved method not only drastically improves the efficiency of the signalling process of the network but also enhances the reliability and robustness of the signalling domain and thereby the performance of the network as a whole. The decrease in resource utilization when applying the improved method leads to among others an increase in the capacity of the IP communications network.

In addition to the decrease in resource utilization the exchange of signalling messages in the IP communications network using the improved method becomes less vulnerable to eavesdropping of for example third parties. For third parties it is much more difficult to directly derive useful information from signalling messages exchanged between entities in the communications network comprising object oriented based data items as compared to text based signalling messages.

Another advantage of the improved method is that unnecessary overhead during the exchange of signalling messages is reduced thereby further improving the efficiency of the communications network.

The chain of at least two entities applying object oriented processing of signalling messages may exist between a calling party and a called party for example as well as between a calling party and several called parties or vice versa. In other words the chain does not need to solely comprise consecutively traversed or coupled entities between a calling party and a called party.

In general entities in modern IP communications networks are arranged to apply modern Object Oriented OO programming languages such as for example JAVA C C dot NET Python Perl Ruby and the like for handling signalling messages. The improved method is applicable for use by entities applying such object oriented languages for the processing of signalling messages.

In a further aspect of the improved method the object class based data items are one of an OO programming language.

JAVA is a commonly used object oriented programming language for entities in IMS communications networks processing SIP signalling messages. Accordingly in IMS communications networks the improved method is among others applicable to entities applying JAVA processing. Within an IMS communications network the improved method of exchanging signalling messages is not only applicable to SIP but may also be applied to Diameter signalling messages. Diameter signalling messages are used between servers in the IMS communications network such as an Interrogating CSCF I CSCF server and Home Subscriber Server HSS during call establishment and when the called party i.e. the destination subscriber is currently not registered between the S CSCF server and the HSS server.

It will be appreciated that the improved method may also be used for other signalling protocols that are based on similar principles such as Hypertext Transfer Protocol HTTP and the Real Time Streaming Protocol RTSP. Further the signalling messages may be compressed using any compressing technique for efficient transportation of the signalling messages.

In another aspect the object oriented based data items are serialised by an entity of the chain for exchanging serialised object oriented based data items between entities of the chain.

Serialising object oriented based data items comprises converting a data structure for example an object class into a sequence of bits so that the transport of object oriented based data items is simplified. This process of serialising a data structure is also often referred to as deflating or marshalling a data structure.

In the receiving entity according to another aspect the received bit sequence is de serialised for applying object oriented processing of the object oriented based data items.

In a further aspect an instance of the signalling messages exchanged between the at least two entities comprises a designation string indicating that the instance comprises serialised object oriented based data items. By interpreting the designation string a receiving entity determines that the object oriented based data items such as a set of JAVA object classes is encoded in binary serialised form such that a de serialising process may be started for processing of the signalling message. The designation string may be incorporated for example in the header of signalling message exchanged between entities of the IP communications network.

In another aspect with exchanging the signalling messages the entities exchange a parameter indicating whether an entity of the chain is arranged for exchanging object oriented based data items. The parameter may be exchanged in any of a request and response signalling message for example.

From this parameter entities gain knowledge whether the signalling message to a subsequent entity has to be exchanged as a regular text based message or as a message comprising object oriented based data items according to the improved method. Based on this indication an entity in the IP communications network may apply conversion of the text based message to object oriented based data items or vice versa.

In a further aspect prior to exchanging signalling messages the entities of the IP communications network exchange a parameter indicating whether an entity of the chain is arranged for exchanging object oriented based data items.

Here it is not necessary to include such a parameter in for example the header of every signalling message exchanged between entities in the IP communications network. By determining beforehand which entities are capable of receiving object oriented based data items signalling overhead is decreased.

Based on this parameter an entity of the chain may directly forward signalling messages according to the improved method knowing that the receiving entity is able to process same. In an IMS communications network applying SIP signalling for example the parameter or the designation string is exchanged in at least one of a SIP Register a SIP Invite and a SIP Response message.

In yet another aspect the parameter comprises at least one of a first port number for exchanging signalling messages comprising object class based items and a second port number for exchanging signalling messages not comprising object oriented based data items.

Dependent on the value of the parameter i.e. the applicable port number signalling messages may be routed for correctly processing same by a receiving entity.

In a further aspect the entities of the chain operate in an IP communications network supporting Voice over IP VoIP communications. Reference is made to the background section above concerning VoIP.

According to another object there is provided an entity comprising a signalling module arranged for applying object oriented processing of signalling messages in an Internet Protocol IP communications network. The entity is characterised in that the signalling module is arranged for exchanging in the IP communications network signalling messages comprising object oriented based data items in accordance with the improved method disclosed above.

In yet another aspect the entity comprises a transmission module arranged for serialising of object oriented based data items and for de serialising of received serialised object oriented based data items for exchanging serialised object oriented based data items in the IP communications network.

In a further aspect the entity comprises a version module arranged for exchanging in the IP communications network object oriented programming version information.

For example when processing software for signalling messages in one or more entities is updated within the chain of entities different versions of for example the set of JAVA Object classes may exist. By exchanging such version information processing errors due to different software versions are effectively avoided.

In a further object there is provided an IP communications system such as an IMS communications system comprising at least two entities arranged for applying object oriented processing of signalling messages. The IP communications network is characterized in that the at least two entities of the IP communications system each comprise a signalling module arranged for exchanging in the IP communications system signalling messages comprising object oriented based data items in accordance with the improved method disclosed above.

The improved method entity and IP communications system disclosed above benefit form a greatly reduced signalling transmission in the IP communications network. This may lead to cost saving in the network infrastructure. In addition the time and resource consuming parsing in entities of the IP communications network such as servers nodes gateways and the like is greatly alleviated which may lead to an increase in the communication capacity of the entity because the processing power and memory usage which is at present occupied by the parsing process may to a certain extent be used for communication purposes such as handling calls. Call establishment duration will be shortened which will be positively perceived by the users of the network.

The above mentioned and other features and advantages of the invention will be best understood from the following description referring to the attached drawings. In the drawings like reference numerals denote identical parts or parts performing an identical or comparable function or operation.

Although the examples presented relate to an IMS communications network and system using SIP signalling and JAVA object classes the above disclosed improved method entity and IP communications network and system are not to be construed as limited to IMS SIP or JAVA services. To the contrary the invention may be applied in any IP communications network applying text based signalling messages and object oriented processing of signalling messages applying object oriented data items such as C .Net Python Perl and Ruby based object oriented data items.

A SIP proxy entity receives text based SIP signalling messages at a SIP decompressor parser . The SIP proxy entity can be any entity operative in an IP communications network for example a Serving Call Session Control Function S CSCF a Proxy Call Session Control Function P CSCF an Application Server AS an Interrogating Call Session Control Function I CSCF a Home Subscriber Server HSS and others. Note that in the latter case instead of the SIP signalling messages signalling messages according to the Diameter protocol are received.

The incoming text based SIP messages may be raw text based messages or compressed using available compression techniques for example lossless or even lossy data compression technology. The incoming text based SIP messages are processed by the SIP decompressor parser . The SIP decompressor parser converts the text based SIP messages to JAVA object classes . The JAVA object classes are processed by the SIP proxy entity using a JAVA service .

SIP signalling messages to be transmitted by the SIP proxy are provided by the JAVA service and comprise JAVA object classes . The SIP proxy entity prepares text based SIP signalling messages using a SIP compressor inverse parser for converting the JAVA object classes back to text based messages . The text based SIP messages may comprise identical content compared to the incoming SIP messages or a non identical content modified by the JAVA service of the SIP proxy entity .

A SIP proxy entity receives text based SIP messages sent from the SIP proxy entity at a SIP decompressor parser . Again received text based SIP messages are decompressed parsed by the SIP decompressor parser for converting these signalling messages to JAVA object classes such that the SIP proxy entity is able to process the messages internally using a JAVA service . Again before the messages are sent or forwarded to a next entity in the IMS network JAVA object classes are converted to text based signalling messages using a SIP compressor inverse parser . As will be appreciated the SIP proxy entity may be any entity operative in an IP communications network as disclosed above with respect to SIP proxy entity .

Again the SIP proxy entity may be any entity operative in an IP communications network as disclosed above with respect to SIP proxy entity . In the particular example SIP proxy entity is a P CSCF server in the IMS communications network for supporting VoIP for example.

The decompressor parser converts SIP text based signalling messages or any other type of text based message to JAVA object classes . In this example the SIP proxy entity is arranged to apply object oriented processing of signalling messages using a JAVA service .

After the JAVA service has internally processed the JAVA object classes of a received signalling message and for example as result hereof has to transmit a signalling message to a next entity i.e. SIP proxy entity in the chain the SIP proxy entity is arranged to forward the processed JAVA object class directly to the SIP proxy entity . That is no inverse parsing and if applicable data compression are applied to the JAVA object classes provided by the JAVA service before transmission thereof to SIP proxy entity . Accordingly SIP signalling messages are exchanged between the SIP Proxy entity and the SIP Proxy entity comprising object oriented based data items.

The SIP proxy entity may be any entity operative in an IP communications network as disclosed above with respect to SIP proxy entity . In the particular example SIP proxy entity is an S CSCF server and or I CSCF server in the IMS communications network .

The next entity in the IMS network i.e. the SIP proxy entity is arranged to process received signalling messages using a JAVA service . In this case the exchanged JAVA object classes do not need to be decompressed parsed at the SIP proxy entity . Thus in accordance with the improved method signalling messages comprising object oriented based data items for example JAVA object classes are exchanged between entities of an IP communications network for example SIP proxy entity and SIP proxy entity .

In this particular example the JAVA object classes provided by the JAVA service are converted to serialised JAVA object classes using a transmission module S of the SIP proxy entity . Serialisation is the process of converting a data structure or object in this case an object oriented data item into a sequence of bits. This sequence of bits allows among others for conveniently transporting the data structure or object to another entity in a network for example SIP proxy entity . The receiving SIP proxy entity is arranged to deserialize the received JAVA object classes using a transmission module S for processing of JAVA object classes by the JAVA service .

The utilization of resources of the SIP proxy entity and the SIP proxy entity is considerably less for serialisation deserialization of JAVA object classes compared to compression decompression and parsing of text based signalling messages. Therefor the load on these entities and the processing times as a whole are considerably reduced. Another advantage of the improved method is that eavesdropping on signalling messages exchanged between the entities is more difficult since these message are no longer text based messages.

The SIP proxy entity processes de serialised JAVA object classes using the JAVA service . For sending JAVA object classes to a next entity in the chain of the IMS network that is SIP proxy entity the JAVA object classes are again serialised into serialised JAVA object classes using a transmission module S .

The SIP proxy entity receives the serialised JAVA object classes and processes same in a like manner as SIP proxy entity for example using a transmission module S and JAVA service .

The SIP proxy entity may be any entity operative in an IP communications network as disclosed above with respect to SIP proxy entity . In the particular example SIP proxy entity is a P CSCF server in the IMS communications network .

Calling party B or UE is not arranged to apply object oriented processing of received signalling messages . Therefore the SIP proxy entity is arranged to compress if applicable and inverse parse JAVA object classes for transmission to UE using a compressor inverse parser I . Text based SIP signalling messages are then sent to the calling party B as disclosed above with respect to .

It will be appreciated that in setting up communication sessions between the UE and during such sessions signalling messages have to be exchanged in both ways between the entities and the UE . To this end each entity comprises transmission modules S providing both serialising and de serialising of JAVA object classes back and forth. SIP proxy entity may likewise comprise a compressor inverse parser I disclosed with respect to SIP proxy entity for transmitting text based signalling messages to UE . SIP proxy entity may comprise a decompressor parser P disclosed with respect to SIP proxy entity for receiving text based signalling messages from UE . The decompressor parser and compressor inverse parser may be combined in a single unit or module.

These URI parameters may comprise a parameter indicating whether an entity for example the P CSCF is arranged for exchanging object oriented based data items. The parameter may also be utilized for version information for example version information of the object oriented programming version. Although this example is directed to SIP Invite messages other type of messages may be used utilizing the same principle.

Whenever the P CSCF forwards the SIP invite message to a S CSCF it uses a service route which the S CSCF had previously returned towards the P CSCF . Such a service route comprises the S CSCF address as well as URI parameters. Again these URI parameters may comprise a parameter indicating whether the S CSCF is arranged for exchanging object oriented based data items for example serialized object oriented based data items.

The SIP Invite message is then forwarded from the S CSCF to a SIP AS and back. Here the S CSCF may add a parameter to the SIP Invite message indicating that the S CSCF is arranged for exchanging object oriented based data items. The SIP Invite message sent from the SIP AS to the S CSCF may already comprise object oriented based data items that is if the SIP AS is also arranged for exchanging object oriented based data items. A SIP Response message sent from the SIP AS to the S CSCF may then comprise a designation string indicating that the SIP Response message comprises object oriented based data items.

The S CSCF then forwards the SIP Invite message to an I CSCF which acts as a main inbound proxy for a domain name of the called UE . The I CSCF queries a Home Subscriber Server HSS for the location of the called UE . The I CSCF then forwards the SIP Invite message to the S CSCF associated with the called UE .

When the I CSCF intends to forward a SIP Invite message to the S CSCF it either determines the S CSCF address from internal configuration or asks receives the S CSCF address at from the HSS . In case of internal configuration the internally configured S CSCF address may comprise a parameter indicating whether the S CSCF is arranged for exchanging object oriented based data items. In case of receiving the S CSCF address from the HSS the HSS provides the S CSCF address as well as the parameter.

The parameter may comprises at least one of a first port number for exchanging signalling messages comprising object oriented based data items and a second port number for exchanging signalling messages not comprising object oriented based data items.

A similar reasoning as explained above is applied for messages exchanged between the SIP AS P CSCF and the called UE . Basically the address of the next entity in the network to which a message is to be forward may be obtained in three ways. First the address of the next entity was already provided by the next entity in previous exchange of messages. Second the address of the next entity is internally configured and third the address of the next entity is received during registration of a user.

The method according to the invention may also be applicable for non SIP messaging for example Diameter messages. Diameter is used during a communication session establishment between the I CSCF and the HSS and if the called UE B is currently not registered in the S CSCF between the S CSCF and the HSS .

Whenever an entity in an IMS network receives a message it needs to determine whether the message is exchanged comprises a regular SIP text based message or an object oriented based data items. Hereto one of the following methods or a combination thereof may be applied.

First a designated application identifier may be used which identifier indicates to the receiving entity whether the message exchanges comprises a regular SIP text based message or an object oriented based data item. Second en entity in the IMS network may utilize two port numbers for exchanging messages one port number for messages comprising regular text based messages and the other port number for messages comprising object oriented based data items.

The entity comprises an input unit having an input port and an output unit having an output port for receiving and sending signalling messages in an IP communications network. The input and output units connect to a transmission module . The transmission module connects to a signalling module which is arranged exchanging signalling messages comprising object oriented based data items. The signalling module connects to a processing unit amongst others arranged for applying object oriented processing of signalling messages such as a JAVA service for processing SIP signalling messages applying JAVA object classes.

The transmission module is arranged for serialising and de serialising of signalling messages comprising object oriented based data items as explained above in connection with . If no serialising is applied the input and output units may connect directly to the signalling module .

A memory and version module connect to the processing unit such to ensure that signalling messages are processed in accordance with the appropriate version of JAVA software for example.

The signalling module may further be arranged for receiving an interpreting parameters indicating whether a neighbouring entity in a chain of entities is arranged for exchanging signalling messages comprising object oriented based data items. For exchanging text based signalling messages the entity may comprise a decompressor parser and a compressor and inverse parser disclosed above in connection with . Separate input and output ports may be provided for the exchange of text based signalling messages.

In such a case the parameter comprises at least one of a first port number for exchanging signalling messages comprising object oriented based data items and a second port number for exchanging signalling messages not comprising object oriented based data items such as text based signalling messages.

It will be appreciated by those skilled in the art that the functionality disclosed in relation to the improved method entity and IP communications system may be applied in special hardware software or a combination thereof.

The invention is not limited to the embodiments described but can be practice with modification and alteration within the spirit and scope of the appended claims.

