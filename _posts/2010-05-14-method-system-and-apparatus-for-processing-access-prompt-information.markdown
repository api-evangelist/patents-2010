---

title: Method, system, and apparatus for processing access prompt information
abstract: A method, system, and apparatus for processing access prompt information in an IP session are disclosed. The method includes: managing the state of an IP session in an IP session process, and providing access prompt information of the IP session, where the access prompt information includes an IP session termination cause, or advertisement information or accounting information of the IP session, or any combination thereof; adding the access prompt information to an IP session control signaling message; and sending the IP session control signaling message that carries the access prompt information to a receiver so that the receiver can perform corresponding operations according to the access prompt information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08433807&OS=08433807&RS=08433807
owner: Huawei Technologies Co., Ltd.
number: 08433807
owner_city: Shenzhen
owner_country: CN
publication_date: 20100514
---
This application a continuation of International Application No. PCT CN2008 073082 filed on Nov. 17 2008 which claims priority to Chinese Patent Application No. 200710188318.7 filed on Nov. 16 2007 both of which are hereby incorporated by reference in their entireties.

The present invention relates to the Internet Protocol IP session field and in particular to a method system and apparatus for processing access prompt information in an IP session.

With the popularity of the broadband network management and control on broadband access become an important part of the broadband network management and control. A general mode of managing and controlling broadband access is to set up a session for controlling and managing a User Equipment UE that accesses including authentication authorization and accounting for the UE. At present the main mode of managing and controlling broadband access is to set up a Point to Point Protocol PPP session to control and manage the access thus providing a broadband access mode for the UE and enabling convenient control management and accounting for the access. However the PPP session based access mode has limitations for example lack of flexible support.

As a current trend the IP session based access mode is used in place of the PPP session based access mode to control and manage the broadband access.

The IP session represents an access session of the broadband network associated with an IP address. The IP session is equivalent to a PPP session. The IP session is generally terminated at an IP edge device. That is the IP session is a session connection set up between the UE and the IP edge device. The IP address of the IP session is designed to identify the key part of the parameters of the IP session. Generally the IP address of the IP session is allocated through a Dynamic Host Configuration Protocol DHCP server dynamically. The IP session is designed to manage and control the UE access on a broadband network for example authentication authorization and accounting. An IP session involves these processes setup and generation of the IP session keep alive or state detection of the IP session and termination of the IP session.

At present some technical solutions are provided for setting up detecting keeping alive and terminating an IP session. Because the IP session is designed to control and manage broadband access plenty of access prompt information occurs in the process of controlling and managing the broadband access for example an IP session disconnection cause and an IP session setup failure cause. Such access prompt information is very important for diagnosing the IP session prompting the UE in the IP session or backing up logs of other servers on the network side.

However the inventor of the present invention discovers that the prior art provides no method for processing the access prompt information in an IP session which hinders the operation administration and maintenance for the broadband access and makes the UE in the IP session or other servers on the network side unable to obtain the prompt information in time or take necessary measures to manage the IP session thus deteriorating the experience of the user who uses the UE and increasing the operator s cost for maintaining the IP session.

The embodiments of the present invention provide a method for processing access prompt information and this method enables processing of access prompt information in an IP session.

The embodiments of the present invention provide a system for processing access prompt information and this system enables processing of access prompt information in an IP session.

The embodiments of the present invention provide an apparatus for processing access prompt information and this apparatus enables processing of access prompt information in an IP session.

A computer program product provided in an embodiment of the present invention includes a program stored in a computer readable storage medium. When being executed the program performs the following steps 

In the technical solution under the present invention the obtained access prompt information is carried in an IP session control signaling message which is sent to the receiver. In this way the receiver can perform corresponding operations according to the access prompt information. Therefore the method system and apparatus provided herein enable processing of access prompt information in an IP session which facilitates the operation administration and maintenance for the broadband access through IP session based access and enables the UE in the IP session or the policy server on the network side to obtain the prompt information in time and take necessary measures to manage the IP session thus improving the experience of the user who uses the UE and decreasing the operator s cost for maintaining the IP session.

To make the technical solution objectives and merits of the present invention clearer the following describes the embodiments of the present invention in more detail with reference to accompanying drawings.

An IP session is independent of access line technologies and is set up between an IP edge device and a UE. The IP session is characterized by user oriented access management and control. In the negotiation process of setting up keeping alive and terminating an IP session the IP edge device and the policy server generate access prompt information for facilitating management control and use. In the embodiments of the present invention to process the access prompt information in an IP session the IP edge device manages the state of the IP session during the IP session process obtains the access prompt information from a locally created directory or from another server on the broadband network adds the access prompt information to an IP session control signaling message and sends the IP session control signaling message to the receiver such as a UE and or network side policy server. The receiver performs the corresponding management according to the access prompt information carried in the IP session control signaling message.

In the embodiments of the present invention the access prompt information includes but is not limited to prompt information about IP session setup success an IP session setup failure cause an IP session termination cause or advertisement information or user accounting information. The prompt information about IP session setup success may be prompt information about user login success. The IP session setup failure cause may be a user login failure cause. The IP session termination cause may be a user logout cause. The advertisement information may be an IP address of an advertisement portal on a broadband network or advertisement graph text information. The user accounting information may be the remaining duration or remaining sum of the subscription account of the user.

The UE A and the IP edge device B are two sides of the IP session. That is the UE A is an IP session client side and the IP edge device B is an IP session network side. The UE A is connected through the access network to the IP edge device B and the IP edge device B may be further connected to a policy server C.

The UE A includes a Client Info Prompt Unit CIPU A a Client Session Signaling Process Unit CSSPU A and a Client Info Adoption Unit CIAU A. In the embodiments of the present invention UEs include a Personal Computer PC a Residential Gateway RG and a wireless portable terminal such as a mobile phone or a Personal Digital Assistant PDA . The CSSPU A is configured to receive an IP session control signaling message that carries access prompt information and send the IP session control signaling message to the CIAU A where the IP session control signaling message may be a protocol message such as a DHCP message or a Bidirectional Forwarding Detection BFD protocol message. The CIAU A is configured to parse the IP session control signaling message obtained from the CSSPU A obtain the access prompt information and then perform operations according to the access prompt information for example restart the IP session according to the prompt information such as a session disconnection cause or send the access prompt information such as a session disconnection cause to the CIPU A or save the prompt information such as a session disconnection cause. The CIPU A is configured to perform operations according to the access prompt information received from the CIAU for example display the session disconnection cause or the advertisement information to the user through a man machine interface or screen .

The IP edge device B includes an AICU B a GSSPU B a GSSMU B and an IMU B. In the embodiments of the present invention examples of the IP

edge devices are Network Access Servers NASs such as a Broadband Remote Access Server BRAS and a Broadband Network Gateway BNG a service router and an access gateway. The GSSMU B is configured to manage the state of the IP session and obtain the access prompt information based on the IP session state management. The IP session state management includes IP session setup management IP session keep alive management and IP session termination management. For example the GSSMU B sends the IP session termination cause to the AICU B or the GSSMU B sends the information about IP session setup failure to the AICU B. The AICU B is configured to obtain the access prompt information including obtaining the access prompt information from the GSSMU B or from the network management control interface. After obtaining the access prompt information the AICU B instructs the IMU B to perform information mapping for the access prompt information. The IMU B is configured to perform information mapping for the access prompt information and send the mapped access prompt information to the GSSPU B. For example the IMU B converts the IP session termination cause into a termination cause code and then instructs the GSSPU B to add the termination cause code to the specified IP session control signaling message. The GSSPU B is configured to add the access prompt information to the specified IP session control signaling message and then send the IP session control signaling message that carries the access prompt information to the UE and or policy server.

The policy server C includes a Server Info Prompt Unit SIPU C a Server Session Signaling Process Unit SSSPU C and a Server Info Adoption Unit SIAU C. In the embodiments of the present invention a policy server may be an Authentication Authorization and Accounting AAA server or a DHCP server. The SSSPU C is configured to receive the IP session control signaling message that carries access prompt information and send the IP session control signaling message to the SIAU C where the IP session control signaling message may be a Remote Authentication Dial In User Service RADIUS protocol message. The SIAU C is configured to parse the IP session control signaling message obtained from the SSSPU C obtain the access prompt information and then perform operations according to the prompt information for example stop IP session accounting according to the prompt information such as a session disconnection cause or send the access prompt information such as a session disconnection cause to the SIPU or save the prompt information such as a session disconnection cause and perform session troubleshooting according to the prompt information such as a session disconnection cause. The SIPU C is configured to perform operations according to the access prompt information received from the SIAU for example display the session disconnection cause to the network administrator through a man machine interface or screen .

The method under the present invention is detailed below with respect to the units in the devices illustrated in .

In this step the AICU B of the IP edge device obtains the access prompt information of the specified IP session from the GSSMU B during the IP session process and instructs the IMU B to perform access information mapping. The access prompt information comes from a local directory or another policy server on the network such as a DHCP server or an AAA server. The AICU B may instruct the IMU B by sending an operation instruction to the IMU B. The operation instruction includes the identifier of the IP session and the access prompt information. The IP session identifier includes at least one of these items IP address UE MAC address and UE ID.

Step The IP edge device B adds the access prompt information to the IP session control signaling message and sends the message to the UE in the IP session and or the policy server that serves the IP session.

Specifically the IMU B of the IP edge device B maps the access prompt information to the IP session control signaling message and then instructs the GSSPU B to process the information. For example the GSSPU B adds the access information to the IP session control signaling message and then forwards the IP session control signaling message that carries the access prompt information to the UE A and or policy server C.

In this step the IMU B instructs the GSSPU B to insert or add the access prompt information or the codes corresponding to the access prompt information to the control signaling message specified by the IP session. The IMU B maps or converts the access prompt information into the prompt information codes. The GSSPU B inserts the access prompt information determines the destination of the IP session control signaling message namely the IP client that the IP session control signaling message is destined for and sends the IP session control signaling message. The step of determining the destination of the IP session control signaling message includes searching for the destination of the IP session control signaling message according to the IP session identifier.

Step The UE A in the IP session and or the policy controller C that serves the IP session performs the corresponding management according to the access prompt information carried in the received IP session control information.

Specifically the CIAU A of the UE A obtains the access prompt information carried in the IP session control signaling message from the CSSPUA and or the SIAU C of the policy controller C obtains the access prompt information carried in the IP session control signaling message from the SSSPU C and performs the corresponding management. In this step the access prompt information management performed by the UE may include the CIAU A displays the access prompt information to the user through the interface of the CIPU A namely prompts the user to take the corresponding measures or the CIAU A records or stores the received access prompt information. The access prompt information management performed by the policy controller C includes the SIAU C backs up the received access prompt information for subsequent maintenance diagnosis tracking and statistics.

The processing for the access prompt information in the IP session herein includes four parts which are detailed below with reference to .

The process of setting up the IP session comes in two parts setup success and setup failure. As shown in the part related to setup failure includes the following steps 

Specifically the CSSPU A of the UE A sends a session setup detection message to the IP edge device B.

In this step the UE is an IP session client the session setup detection message is an IP session control signaling message for example a DHCP discovery message a DHCP request message and a DHCP AUTH message.

Step After receiving the session setup detection message the GSSPU B of the IP edge device B instructs the GSSMU B to perform IP session setup processing such as authentication and authorization. If the attempt of setting up the IP session fails the GSSMU B indicates or notifies the IP session setup failure cause to the AICU B.

Step The AICU B of the IP edge device B notifies the session prompt information IP session setup failure cause to the IMU B. The IMU B converts the IP session setup failure cause into an error code and then instructs the GSSPU B to insert or add the IP session setup failure cause or the error code to the notification of the IP session setup failure cause. Afterward the GSSPU B sends the notification of the IP session setup failure cause to the UE.

The notification of the IP session setup failure cause is an IP session control signaling message which may be a DHCP message or an Extensible Authentication Protocol EAP message. The IP session setup failure cause may be carried in an existing field or extension field of a DHCP message or EAP message.

Step The UE A attempts to access the network namely set up an IP session. For example the UE A sends a message to the IP edge device B.

Step After receiving the session setup detection message the IP edge device B sets up an IP session. If the attempt of setting up the IP session succeeds the IP edge device B obtains the prompt information about IP session setup success and uses the information as access prompt information.

Step The IP edge device B notifies the prompt information about IP session setup success to the UE A for example sends a session setup success notification that carries the prompt information about IP session setup success.

The session setup success notification is an IP session control signaling message which may be a DHCP message or an EAP message. The prompt information about IP session setup success may be carried in an existing field or extension field of a DHCP message or EAP message. The prompt information about IP session setup success includes advertisement information and user accounting information.

During the process of the keeping the IP session alive the interaction between the UE A and the IP edge device B includes the following steps as shown in .

Step The IP edge device B obtains the access prompt information and sends a notification of session keep alive access prompt information to the UE A of the IP session where the notification carries the access prompt information. Specifically the AICU B obtains the access prompt information and notifies the session prompt information advertisement information and accounting information to the IMU B. The IMU B maps the session prompt information to the specified IP session control signaling message keep alive message and then instructs the GSSPU B to insert or add the prompt information to the keep alive message of the IP session. The GSSPU B sends the keep alive message to the UE A.

The notification of the session keep alive access prompt information is an IP session control signaling message. The access prompt information includes advertisement information and user accounting information. The notification of the session keep alive access prompt information may be a Bidirectional Forwarding Detection BFD protocol message or a DHCP message. Specifically an Option field may be added to the BFD control message or BFD echo message or DHCP echo message or DHCP lease active message and then the access prompt information is added to the Option field.

In the process of terminating the IP session the interaction between the UE A and the IP edge device B includes the following steps as shown in .

Step The IP edge device B detects termination of the IP session. Upon discovering termination of the IP session the GSSMU B performs termination processing for the IP session and then indicates or notifies the IP session termination cause to the AICU B namely the IP edge device B obtains the termination cause . The IP session termination cause is a type of access prompt information.

Step The IP edge device B sends a notification of the session termination cause to the UE A. The notification carries the IP session termination cause. Specifically the AICU B of the IP edge device notifies the IP session termination cause to the IMU B. The IMU B converts the IP session termination cause into a termination cause code and instructs the GSSPU B to insert or add the IP session termination cause or the code to the notification of the IP session termination cause. Afterward the GSSPU B sends the notification of the IP session termination cause to the UE A.

In this step the notification of the IP session termination cause is an IP session control signaling message and may be a DHCP message or a BFD protocol message.

Step The IP edge device B sends a session termination indication message to the policy server C. The session termination indication message carries the code of the IP session termination cause.

In this step the session termination indication message is an IP session control signaling message for example a RADIUS accounting message or a subscriber authentication and authorization accounting protocol Diameter protocol message.

In the process of terminating the IP session in the session termination indication message sent by the IP edge device B carries the code of the IP session termination cause. Specifically the code may be carried through a parameter field in a RADIUS message or Diameter message and the parameter field may be Field Attribute or Attribute Value Pair AVP . After receiving the session termination indication message the policy server C performs management according to the IP session termination cause carried in the session termination indication message. The detailed process is exemplified below 

The IP edge device B adds the IP session termination cause to an Acct Terminate Cause field of an Accounting Request message in a RADIUS protocol message or a Diameter protocol message where the field is Field or Attribute or AVP and then sends the Accounting Request message to the policy server C. In this case the policy server C may be an AAA server.

Alternatively the IP edge device B adds the IP session termination cause to a Disconnect Cause field this field is an AVP of a Disconnect Peer Request message in a Diameter protocol message or to a Termination Cause field of a Session Termination Request message or Accounting Request message and then sends the Diameter protocol message to the policy server C. In this case the policy server C may be an AAA server.

In the process shown in the IP edge device B adds the access prompt information to a BFD protocol message DHCP message or EAP message and sends the message to the UE A. The detailed process includes the following steps 

The IP edge device B sends a BFD protocol message that carries the access prompt information to the UE A. As shown in the BFD protocol message includes a BFD message header and a BFD message body. The BFD message header includes an IP header and a UDP header. The BFD message includes a Diagnostic field or an Information Option field. In the embodiment illustrated in the GSSPU B of the IP edge device B adds the prompt information to the Diagnostic field or Information Option field and then sends the message to the UE A. For example the IMU B of the IP edge device B converts the IP session termination cause into a termination cause code and then notifies the GSSPU B to add the code to the Diagnostic field A of the BFD protocol message. Afterward the IP edge device B sends the BFD control message to the UE A. The UE A obtains the IP session termination cause from the BFD control message sent by the IP edge device B and then performs management for example displays the IP session termination cause on the interface. In another example through an existing Option field or an extension Option field of the BFD protocol message an Information Option field is added to the BFD control message. The Information Option field includes Info Type Info Length and Info Data. The advertisement type information user accounting type information or IP session termination cause type is added to the Information Option field of the BFD protocol message. The IMU B of the IP edge device B performs type code mapping and the GSSPU B of the IP edge device B implements insertion of access prompt information mapping from the IP session to the signaling message and message sending. The mapping from the IP session to the signaling message may be the mapping to the IP session through the destination IP address of the IP header.

Alternatively the IP edge device B sends a DHCP message that carries the access prompt information to the UE A. As shown in the DHCP message includes a DHCP message header and a DHCP message body. The DHCP message header includes an IP header and a UDP header. The DHCP message includes a Transaction Identifier XID a DHCP message type and a DHCP Option. The GSSPU B of the IP edge device B adds the prompt information as a DHCP Option field to the DHCP message. Table 1 describes the access prompt information supported by the DHCP message 

For example the DHCP carries the prompt information in this way The AICU B of the IP edge device B obtains the prompt information and instructs the IMU B to perform information mapping map the access prompt information to the access prompt information code or map the access prompt information to the IP session control signaling message of the specified type . The IMU B instructs the GSSPU B to add the prompt information as a DHCP Option field to the DHCP message. The GSSPU B supports the DHCP relay or proxy to process the DHCP message and the GSSPU B also supports processing of the DHCP message in DHCP server mode.

Alternatively the IP edge device B supports the access prompt information to be carried in an existing field or an extension field of the EAP message. This field carries the access prompt information and includes the user login failure cause or the IP session setup success information. In this embodiment the EAP serves as a general authentication mechanism and can be carried in a DHCP message or a User Datagram Protocol UDP message.

Step The UE sends an access control message to set up an IP session. The access control message carries the access session information.

In this embodiment the access control message may be but is not limited to a DHCP discovery message or a DHCP request message or a DHCP AUTH message.

Step After receiving the access control message sent by the UE the IP edge device parses the access control message and obtains the access session information and then performs access authentication and authorization processing.

In this step the access session information includes but is not limited to user name and UE address. The access authentication and authorization processing may be sending a RADIUS Access Request message to the policy server to perform authentication and authorization.

Step After receiving the access authentication and authorization message sent by the IP edge device the policy server performs authorization processing if the authentication and authorization fail the policy server returns an access rejection message to the IP edge device. The access rejection message carries the access rejection prompt information.

In this step the access rejection message may be a RADIUS Access Reject message and the access rejection prompt information may include password error or a cause code 0x301 . For example the Reply Message of the RADIUS Access Reject message serves as access prompt information.

Step The IP edge device receives the access rejection message returned by the policy server obtains the access prompt information carried in the access rejection message constructs an IP session control signaling message that carries the access prompt information and sends it to the UE.

In this embodiment there are different causes for IP session setup failure. The cause may be mapped to a cause code as shown in Table 2. Table 2 gives the mapping relations between the common IP session setup failure causes and the cause codes.

In this step the IP session control signaling message may further carry the access session information.

In this step the IP session control signaling message that carries the access prompt information may be a DHCP Offer message a DHCP Advertise message a DHCP NAK message or a DHCP AUTH message. The IP session control signaling message may carry an Option field. This field includes the access rejection prompt information or the cause code. If the IP session control signaling message is an EAP DHCP AUTH message EAP is carried in the DHCP message for authentication and EAP DHCP may be regarded as a combination of EAP and DHCP the access rejection prompt information may be included in the EAP message.

In this step the IP edge device is responsible for mapping and association between the access rejection message sent by the policy server and the IP session control signaling message sent by the UE. Mapping refers to correspondence between the access rejection message and the sent IP session control signaling message. For example when the received access rejection message is a DHCP discovery message a DHCP Offer message is returned to the UE as a response if the received access rejection message is a DHCP request message a DHCP rejection message is returned to the UE as a response. Association refers to association of the information about the access session.

Step The UE performs the corresponding management after receiving the IP session control signaling message that carries the access prompt information.

In this step the management process is The UE obtains the access prompt information from the DHCP Offer message DHCP rejection message or DHCP AUTH message that carries the access prompt information for example obtains access rejection prompt information or the cause code and then converts the access prompt information into a string and displays it on the interface or records the access prompt information.

Step The UE sends an access control message to set up an IP session. The access control message carries the access session information.

Step After receiving the access control message sent by the UE the IP edge device parses the access control message and obtains the access session information and then performs access authentication and authorization processing.

Step After receiving the access authentication and authorization message sent by the IP edge device the policy server performs authorization processing if the authentication and authorization succeed the policy server returns an access acceptance message to the IP edge device. The access acceptance message carries the access prompt information.

In this step the access acceptance message may be a RADIUS Access Accept message and the access prompt information may be carried in a Reply Message of a RADIUS Access Accept message. The access prompt information may include user accounting information for example the remaining duration of the user or the remaining sum of the account and may also include advertisement information such as the IP address of the portal on a broadband network.

Step The IP edge device receives the access acceptance message returned by the policy server obtains the access prompt information carried in the access acceptance message constructs an IP session control signaling message that carries the access prompt information and sends it to the UE.

In this step the IP session control signaling message that carries the access prompt information is a DHCP Offer message a DHCP Advertise message a DHCP acknowledgement ACK or Reply message or a DHCP AUTH message. The IP session control signaling message includes an Option field which is designed to add the access prompt information obtained by the IP edge device from the access acceptance message and other access prompt information obtained by the IP edge device.

In this step the acceptance prompt information obtained by the IP edge device may include user accounting information and advertisement information. The access prompt information includes the access prompt information collected by the IP edge device from a local directory or from other servers on the network. For example the IP edge device obtains the access prompt information from other servers through the interface to such servers.

Step The UE performs the corresponding management after receiving the IP session control signaling message that carries the access prompt information.

In this step the detailed management process is The CIAU of the UE obtains the access prompt information from the DHCP Offer message DHCP acknowledgement message or DHCP AUTH message received from the CSSPU for example obtains the user accounting information or advertisement information and then displays the access prompt information.

In this step the CIAU starts a web browser according to the advertisement information for example an address of a portal in the access prompt information the browser here is a CIPU and advertisement information such as a web page pops up.

Step The IP edge device obtains an instruction or event of updating the IP session sends a DHCP Reconfigure message to the UE where the DHCP Reconfigure message is constructed locally or received from the DHCP server and carries access prompt information.

In this step the update of the IP session information may be modification of the IP address configuration of the IP session.

The DHCP Reconfigure message may be a DHCP Forcerenew message. The DHCP update message includes access prompt information. The access prompt information may be a cause for terminating the IP session for the purpose of modifying the IP session configuration and the access prompt information may be carried in a DHCP Option field.

Step After receiving the DHCP Reconfigure message the UE parses the DHCP Reconfigure message to obtain the access prompt information and know the IP session termination cause and then sends a configuration request message to the IP edge device.

Step After receiving the configuration request message the DHCP server updates the IP session information for example modifies the IP address of the IP session that is set up and sends a DHCP NAK message to the IP edge device.

Step . The IP edge device receives the DHCP NAK message from the DHCP server performs termination processing for the IP session and then forwards the DHCP NAK message to the UE. The IP edge device may add access prompt information such as an IP session termination cause to the DHCP NAK message to be forwarded.

Step The IP edge device sends an accounting stop message or a session termination message to the AAA server. The message carries the IP session termination cause and instructs the AAA server to back up the IP session termination cause. If the AAA server and the IP edge device are in the same physical entity the AAA server may interact with the IP edge device through an Application Programming Interface API . This step is optional depending on the actual deployment.

In this step the accounting stop message or the session termination message includes the Accounting Request message of the RADIUS protocol or the Diameter protocol or the Session Termination Request message of the Diameter protocol.

Specifically the IP edge device adds the IP session termination cause to the Termination Cause field of the Session Termination Request message of the Diameter protocol or to the Acct Terminate Cause field of the Accounting Request message of the RADIUS or Diameter protocol.

Step After receiving the DHCP NAK message the UE obtains the access prompt information and modifies the configuration for example records or displays the access prompt information or sets up an IP session again according to the access prompt information.

Step The IP edge device obtains the access prompt information which includes advertisement information and user accounting information.

In this step the IP edge device may obtain the access prompt information locally or obtain the access prompt information from another server on the network. For example the IP edge device obtains the user accounting information from the policy server through a RADIUS message and obtains the access prompt information as triggered periodically or as triggered by an external application such as a network management command.

In this step the access prompt information may be carried in a BFD protocol message. Specifically an Option field may be added to the BFD control message or BFD echo message and then the access prompt information is added to the Option field of the BFD control message or BFD echo message.

Step The UE performs the corresponding processing. Specifically the UE obtains the access prompt information from the received BFD protocol message for example obtains the user accounting information or advertisement information. The UE displays the user accounting information on the interface as a prompt to the user. The UE displays advertisement information according to the advertisement information such as an IP address of a portal.

Step The IP edge device detects the IP session termination instruction and sends an IP session termination message via a session Keep alive protocol to the UE. The IP session termination message carries an IP session termination cause.

In this embodiment there are different session termination causes. Each cause is mapped to a cause code as shown in Table 3. Table 3 gives common IP session termination causes.

In this step the IP session termination instruction is sent by the network management system or the policy server or sent locally at fixed time for example upon expiry of the IP session lifetime . The IP session termination instruction may be an instruction of active release of the session from the UE for example a DHCP release message from the UE.

In this step the IP session termination message may be sent to the UE through a BFD control message. The IP session termination cause may be carried in the Diagnosis Diag code field of the BFD control message namely the IP edge device adds the IP session termination cause to the Diag code field of the BFD control message and then sends a BFD control message of state change to the UE.

Step The IP edge device sends an IP session termination instruction for example an accounting stop message or an IP session termination message to the policy server and adds the IP session termination cause to the accounting stop message or IP session termination message. This step is optional depending on the actual deployment.

Step After receiving the IP session termination message the UE performs the corresponding processing for example records or displays the IP session termination cause or sets up an IP session again.

Supposing that the receiver includes a UE and or a policy controller the system and the apparatus provided in an embodiment of the present invention are detailed below.

The system may further include a server which is configured to send the access prompt information of the IP session to the IP edge device. In this case the access prompt information is obtained by the IP edge device from the server.

As shown in an apparatus for processing access prompt information in an IP session for example an IP edge device includes 

The mapped access prompt information sent by the IMU to the GSSPU may instruct the GSSPU to add the access prompt information to the specified IP session control signaling message.

Besides the embodiments of the present invention provide a method and apparatus for processing access prompt information from the perspective of the UE or policy server.

A method for processing access prompt information includes obtaining an IP session control signaling message that carries access prompt information of an IP session and performing corresponding operations according to the access prompt information carried in the IP session control signaling message.

An apparatus for processing access prompt information is provided. The apparatus may be a UE or a policy server. As shown in the apparatus includes 

Through the method the system and the apparatus provided herein the IP edge device obtains the access prompt information during the IP session process and adds the access prompt information obtained during the IP session process to an IP session control signaling message which is sent to the UE and or policy server in time thus improving the user experience in the IP session. After receiving the IP session control signaling message the UE and or policy server parses the message to obtain the access prompt information and performs log backup for the obtained access prompt information thus improving the efficiency of maintaining the IP session and reducing the operation cost. Besides the access prompt information may carry some information pushed by the policy server actively for example advertisement information thus increasing the operation cost of the broadband access.

It is understandable to those skilled in the art that all or part of the steps of the foregoing embodiments may be implemented by hardware instructed by a computer program. The program may be stored in a computer readable storage medium. When being executed the program performs the processes covered in the foregoing embodiments. The storage medium may be a magnetic disk a Compact Disk CD a Read Only Memory ROM or a Random Access Memory RAM .

Although the invention has been described through several exemplary embodiments the invention is not limited to such embodiments. It is apparent that those skilled in the art can make modifications and variations to the invention without departing from the spirit and scope of the invention. The invention is intended to cover the modifications and variations provided that they fall within the scope of protection defined by the following claims or their equivalents.

