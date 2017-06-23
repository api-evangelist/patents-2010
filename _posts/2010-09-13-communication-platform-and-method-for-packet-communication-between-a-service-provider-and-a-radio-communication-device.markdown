---

title: Communication platform and method for packet communication between a service provider and a radio communication device
abstract: The present invention relates to a communication platform for packet communication between at least one service provider in a first network and a radio communication device in a second network, the second network comprises a first network node provided to, at least partly, handle communication between the radio communication device and a gateway located in the second network. The gateway is provided to handle communication between the second network and the communication platform, and the communication platform comprises an application programming interface provided to handle two-way communication between the service provider and the radio communication device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08477664&OS=08477664&RS=08477664
owner: Yahoo! Inc.
number: 08477664
owner_city: Sunnyvale
owner_country: US
publication_date: 20100913
---
This utility patent application is a divisional application of allowed U.S. patent application No. 11 571 391 filed on Dec. 28 2006 the benefit of which is claimed under 35 U.S.C. 120 and which further claims benefit as a U.S. National Phase Application to PCT SE2005 000921 filed on Jun. 15 2005 which further claims benefit to Sweden Patent Application No. 0401683 8 filed on Jun. 30 2004 the benefit to each are claimed herein and further each are incorporated by reference in their entirety herein.

The present invention relates to a communication platform for supporting communication between a service provider and a radio communication device using packet communication and a method therefore. More specifically the present invention relates to a communication platform for enabling two way communication between a service provider and a radio communication device and a method therefore.

In present day radio communication systems new radio devices become more and more intelligent and are introduced side by side with older radio devices still serving a large community.

The communication capabilities of these radio communication devices are ever increasing and data packet communication is today commonplace using for instance GPRS General Packet Radio System . Data communication protocols used by radio communication devices more specifically cellular radio communication devices are among others WAP 1.0 Wireless Application Protocol WAP 1.1 WAP 2.0 HTTP HyperText Transfer Protocol HTTPS TCP Transport Control Protocol IP Internet Protocol etc. where many cellular devices give access only to one or a few of these protocols.

Parallel with the development of more intelligent radio devices are the development of more and more intelligent and demanding services for these radio devices. Since so many different devices are out on the market a service provider oftentimes need to develop a specific service only towards a specific subset of the available radio devices. Not always because the other devices axe not capable of handling the service although this will of course also be the case in many situations but also since the development cost would soar when the service need to be adapted to the capabilities of the different radio devices.

It would thus be beneficial If a solution could be provided that would reduce development cost for service providers and increase the consumer base.

Another problem in modern radio packet communication networks is the incapability for a service provider to initiate communication towards a radio communication device. Although this has sound reasons in terms of security many valuable services such as instant messaging and pushing of live content such as sport results stock quotes etc can not be developed without this capability. An additional problem in this respect is that telecommunication operators commonly provides the gateways between intranet and extranet with NAT Network Address Translation to increase security. This scheme hides any address information of the radio devices from the service providers thus increasing the difficulty in establish connections from the service providers to the radio communication devices.

Consequently it would be beneficial if a solution could be provided that gave a radio communication device the capability to receive connections initiated from a service provider.

It is a main object of the present invention to provide such apparatus and method that at least alleviate the above problems.

These objects among others are according to a first aspect of the present invention attained by a communication platform for packet communication between at least one service provider in a first network and a radio communication device in a second network the second network comprises a first network node provided to at least partly handle communication between the radio communication device and a gateway located in the second network. The gateway is provided to handle communication between the second network and the communication platform and the communication platform comprises an application programming interface provided to handle two way communication between the service provider and the radio communication device.

By providing a platform for service providers to develop service provider applications providing a uniform and consistent application programming interface independent of the capabilities of the individual radio device development time and thus money can be saved. Since the communication platform furthermore provides two way communication that is that it is possible for the service provider application to establish connections to the radio device more elaborate services can be developed.

These objects among others are according to a second aspect of the present invention attained by a method for packet communication between a service provider located in a first network and a radio communication device located in a second network the second network comprises a first network node for communication between the radio communication device and a gateway and the gateway is provided for communication between the first network node and the first network. The method comprises the steps of 

According to the above method the radio device registers at the communication platform and receives an identification key. Since the platform stores the particulars relating to the radio device it is possible for a service provider application to look up the identity the first data information of the radio device or its user and request a data channel from the communication platform. Thus it is possible to communicate between the service provider platform and radio device.

According to one variant of the invention the communication platform is provided to set up a control channel between the communication platform and the radio communication device.

The general control channel provides the means for requesting a set up of a transparent data channel between a service provider application and the radio device. The control channel is constantly present and is re established if the connection to the radio device is temporarily lost. Thereby the communication platform can always request a connection to the radio device for a service provider application.

According to one variant of the invention the radio communication device comprises a radio device platform providing means for a radio device application to communicate with a service provider application or a radio communication device using the radio device platform and the communication platform.

The radio device platform is a small application in the radio device supporting the functionality of the communication platform. Among other things the radio device platform supports different proprietary protocols and for instance re sends the unique key when the radio connection has been lost to re establish and communication channels including the control channel. The radio device platform is used by for instance a service provider radio device application part for communication with the service provider application part which resides centrally.

According to one variant of the invention a service provider application is provided to communicate with the radio communication device through the communication platform using an application protocol supported by the communication platform and a radio communication device application.

The communication platform supports communication between service provider applications and radio devices by providing an API and communication protocol stacks for all existent radio devices e.g. using C java Symbian Windows Linux etc.

According to one variant of the invention the radio communication device is provided to connect to the communication platform and receive and store first data information generated at the communication platform and the communication platform is provided to store the first data information in relation to second data information identifying the radio communication device and a session context in the communication platform.

The first data information can for instance be a unique key identifying the radio device to the communication platform. The key is stored in a look up register such as for instance a RMI Remote method Invocation registry Corba registry or proprietary registry object together with information relating to the radio device such as ID phone number IMSI IMEI etc. and session connection socket context.

According to one variant of the invention the communication platform is provided to generate a unique key upon reception of a connection from the radio communication device uniquely identifying the radio communication device and to send the key to the radio communication device.

According to one variant of the invention the radio communication device is provided to send the received key to the communication platform whenever connection is resumed after a temporary loss of connection.

The radio device platform is provided to send the key to the communication platform if the communication channel is lost. The key identifies the session in the communication platform and the session connection can be re established. Thus the platform provides means for establishing a persistent connection with the radio device and the individual service provider applications need not to care about this complication relating to the radio interface.

According to one variant of the invention the service provider is provided to use the second data information in the communication platform to initiate communication to the radio communication device.

The second data information may for instance be a SIP address which may be used by a service provider application for establishing a connection to a radio device. The SIP address is looked up in the look up register and a session context is identified. This session context can then be used to establish a data channel to the radio device.

According to one variant of the invention the communication platform is provided to establish a data channel with the radio communication device using the control channel.

The control channel is used to set up a data channel between the radio communication device and a session in the communication platform. This session is then related to another session connected to a service provider application or another radio device and a communication channel is thereby established.

According to one variant of the invention the system comprises at least a second radio communication device having a control channel established to the communication platform and wherein the first radio communication device is provided to establish a data channel through the communication platform to the second radio communication device using the control channel.

As is mentioned elsewhere in this text the communication platform provides possibilities to connect two radio communication devices.

According to one variant of the invention the radio communication device is provided to connect to the communication platform using the HTTP protocol and the communication platform is provided to delay a HTTP response to any HTTP request from the radio communication device and the radio communication device is provided to send a new HTTP request upon reception of a HTTP response to thereby establish a communication channel.

Some radio device do not support native TCP IP but only HTTP. To establish a persistent control channel between such a radio device and the communication platform a HTTP request needs to be continuously active. Therefore the radio device platform is provided to send a new HTTP request to the communication platform whenever a HTTP response is received from the communication platform. To reduce the number of signalling over the HTTP protocol the communication platform is provided to delay the HTTP response to HTTP requests received from the radio device. The HTTP response can then be used by the communication platform to send control signals or data signals to the radio device.

According to one variant of the invention the communication platform receives and stores information about the state of the radio communication device and any application of the service provider.

The communication platform can store the state of the radio device and service provider applications and thereby provide possibilities for the service provider application to be state less. That is the service provider applications need not to monitor state changes of the radio device.

According to one variant of the invention the service provider application is an application in a second radio communication device.

The service provider application can also be an application in a radio communication device such as a cellular telephone or a PDA Personal Digital Assistant which is connected to a radio network. Thus it is possible for two radio communication devices to communicate using packet data communication.

According to one variant of the invention the second radio communication device is located in said second network.

According to one variant of the second aspect of the invention a control channel is established between the radio communication device and the communication platform using the method steps a to e .

According to one variant of the invention according the second aspect a data channel request is sent from a service provider to the communication platform requesting a data channel from the service provider to the radio communication device the control channel for the radio communication device is identified a data channel is established between the radio communication device and the platform using the control channel and data is sent between the service provider and the radio communication device using the data channel.

According to one variant of the second aspect of the invention a data packet is received from the service provider to the communication platform the data packet is stored at the communication platform the data packet is sent to the radio communication device an acknowledgement packet from the radio communication device indicating the successful reception of the data packet is received and the data packet is re sent to the radio communication device if the acknowledgement packet is not received within a specified time period or if the acknowledgment packet indicates a failure in the reception of the data packet at the radio communication device.

According to one variant of the second aspect of the invention the communication platform comprises a plurality of communication platform units and where a first communication platform unit of the communication platform units comprises a database relating the key with the identity of the communication platform unit handling the session. The method comprises the further steps of receiving a key at a second of the communication platform units sending a identity request comprising the key to the first communication platform unit receiving a communication platform unit identity from the first communication platform unit at the second platform unit identifying a handling communication platform unit sending the key to the handling platform unit and responding to the radio communication device from the handling platform unit.

Further characteristics of the invention and advantages thereof will be evident from the following detailed description of embodiments of the invention.

In the following description for purposes of explanation and not limitation specific details are set forth such as particular techniques and applications in order to provide a thorough understanding of the present invention. However it will be apparent to one skilled in the art that the present invention may be practiced in other embodiments that depart from these specific details. In other instances detailed descriptions of well known methods and apparatuses are omitted so as not to obscure the description of the present invention with unnecessary details.

The radio communication device is in radio communication with a BTS BSC which in turn is connected to a SGSN Serving Gprs Support Node for providing GPRS support to the radio communication device . The SGSN is connected to a GGSN Gateway Gprs Support Node . The GGSN acts as a gateway between the second network and other foreign networks such as the first network . Thus the GGSN acts as a connection point for the communication platform to the second network . A NAT Network Address Translation and firewall functionality is also provided between the first and second network according to common techniques to increase the security in the second network .

Session objects to be further described below provides an interface for the first service provider application towards the radio communication device for two way communication them between. As is shown in the communication platform hides the specifics regarding the radio communication device and provides extra services to the service provider application such as QoS Quality of Service flow control transaction security abstraction of device specific communication capabilities scaling load balancing billing etc all to be further described below. This means that the service provider when designing the service provider application need not consider complications such as lost connections support of different protocols flow control etc.

The radio communication device denoted MTin sends a connection request to a first communication platform unit CPU in . The communication platform also comprises a second communication platform unit . The communication platform units may for instance be common computers.

The CPU receiving the connection request from the radio communication device MTcreates with a signal a super session object denoted SSA for the MT. In the signal is specific connection details included enabling the CPU to send messages to the radio communication device MT. The SSA generates a unique key representing the MTand stores this key together with a reference to a Session Control object SCA. The SSA register its process identity in a look up register such as a RMI registry Corba registry or proprietary registry object together with the generated unique key and address information identifying the radio communication device and or its user for instance a SIP address Session Initiation Protocol . The key is finally sent to the MTin an accept message .

Thus a control channel has been established between the communication platform and the radio communication device .

When the radio device discovers that a channel has been lost for instance the control channel described in connection with it sends a request comprising the previously received key to the communication platform. This request may be received by any CPU in the communication platform for instance CPU . The CPU will then send a question to the look up register including the received key. The look up register looks up the key and finds the process identity of the super session related to this key and thereby to the radio device sending the request. The CPU sends the request to the CPU which sends an accept message to the radio device whereby the control channel is re established. If data channels described below were established they would be re established in a similar way if disconnected.

Firstly the radio device needs to establish a server connection. That is a connection which other may connect to. This is performed by sending from the radio device a Create Server Socket message to the communication platform. The message comprises the key identifying the SSA and thus a Server Connection or a server socket can be registered in the SSA with the message Register . The registration is acknowledge in message . The physical connection or the session is however not yet created. Now the radio device is ready to receive connections on the server socket and applications may thus connect to the radio device .

To connect to the radio device the SPA service provider application sends a connect message to the communication platform using the control channel and the communication platform answers with a message comprising a selected CPU to use for the channel to be established in this case the CPU . The SPA sends a connect message which comprises an address to the radio device or its user preferably but not necessarily an SIP address to the CPU . The CPU creates a session object SB denoted and registers the session SB in the SSB using the supplied key.

The session object SB now sends a query to the look up register LUR supplying the address of the radio device MT. The look up register answers with the process identification and the CPU ID handling the super session for the specified address that is the radio device . The session SB then sends a connect message to the so identified super session SSA . The SSA then stores the process reference to the session SB .

The super session SSA sends a connection request message to the radio device including a specific CPU IP address using the established control channel. The radio device assumingly accepts the connection in a message and a dedicated socket session to the specific CPU in the platform is created for this connection. A session object SA is then created and registered in the SSA . The SSA finally sends an accept message to the session SB identifying the newly created session SA and thus is a data channel between the service provider application and the radio device established using the two sessions SA and SB .

Data is sent from the service provider application to the radio device by transferring data from the SPA to the session SB from the session SB to the session SA and finally from the session SA to the radio device . Since the communication platform has control over the data flow it is possible to introduce for instance flow control.

Even tough the present invention has been described in relation to a server connecting to a radio device the opposite may also occur that is the present invention may of course be used by a radio device connecting to a service provider application. Moreover the present invention may also be used for connection two radio communication devices. In general terms and in using the present invention there are no difference between a radio communication device and a service provider application when it comes to creating connections between such units.

It will be obvious that the invention may be varied in a plurality of ways. Such variations are not to be regarded as a departure from the scope of the invention. All such modifications as would be obvious to one skilled in the art are intended to be included within the scope of the appended claims.

