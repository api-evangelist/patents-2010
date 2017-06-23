---

title: Securing partner-enabled web service
abstract: The claimed subject matter provides a method for securing a partner-enabled web service. The method includes receiving a request to access the partner-enabled web service. The request is received from a browser client for a partner application. The browser client is associated with a user. Additionally, the method includes determining that the user is authorized to access the partner application. The method further includes generating a token that associates the user with the partner application. Also, the method includes sending the token to the browser client.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09071616&OS=09071616&RS=09071616
owner: MICROSOFT TECHNOLOGY LICENSING, LLC
number: 09071616
owner_city: Redmond
owner_country: US
publication_date: 20101118
---
Web services may provide users a secured environment for accessing everyday applications such as email and chat. Generally authenticated users may access the everyday applications using a web browser client.

In some cases web services may be partner enabled. A partner enabled web service may securely serve data for a partner application. Because of security concerns partner applications typically access a partner enabled web service through server to server communication.

Direct access to a partner enabled web service from a partner application s browser client is insecure. The insecurity arises from the challenge in verifying whether the direct access originates from a specific partner. Because of such insecurities the partner client applications are typically stand alone applications instead of web browser clients.

The following presents a simplified summary of the innovation in order to provide a basic understanding of some aspects described herein. This summary is not an extensive overview of the claimed subject matter. It is intended to neither identify key or critical elements of the claimed subject matter nor delineate the scope of the subject innovation. Its sole purpose is to present some concepts of the claimed subject matter in a simplified form as a prelude to the more detailed description that is presented later.

The subject innovation relates to a method and a system for securing a partner enabled web service. In an exemplary method a request to access the partner enabled web service is received. The request is received from a browser client for a partner application. The browser client is associated with a user. Additionally the method includes determining that the user is authorized to access the partner application. The method further includes generating a token that associates the user with the partner application. Also the method includes sending the token to the browser client.

An exemplary system according to the subject innovation may be used for securing a partner enabled web service. The exemplary system comprises a processing unit and a system memory that comprises code configured to direct the processing unit. In particular the code may be configured to direct the processor to receive a request to access the partner enabled web service. The request is received from a browser client for a partner application. The browser client is associated with a user. The code may also be configured to direct the processor to determine that the user is authorized to access the partner application. The processor may be further directed by the code to generate a token that associates the user with the partner application. Also the processor may be directed by the code to send the token to the browser client.

Another exemplary embodiment of the subject innovation provides one or more computer readable storage media that include code to direct the operation of a processing unit. The code may direct the processing unit to secure a partner enabled web service by receiving a request to access a partner enabled web service. The request may be received from a browser client for a partner application. The browser client may be associated with a user. The code may also direct the processor to determine the user is authorized to access partner application. The code may direct the processor to generate a token that associates the user with the partner application. In one exemplary embodiment the token comprises a shared secret of the partner application and the partner enabled web service the user id an identifier of the partner application and an issue time that the token is generated. The code may direct the processor to send the token to the browser client and to encode the token using a one way hashing algorithm.

The following description and the annexed drawings set forth in detail certain illustrative aspects of the claimed subject matter. These aspects are indicative however of a few of the various ways in which the principles of the innovation may be employed and the claimed subject matter is intended to include all such aspects and their equivalents. Other advantages and novel features of the claimed subject matter will become apparent from the following detailed description of the innovation when considered in conjunction with the drawings.

The claimed subject matter is described with reference to the drawings wherein like reference numerals are used to refer to like elements throughout. In the following description for purposes of explanation numerous specific details are set forth in order to provide a thorough understanding of the subject innovation. It may be evident however that the claimed subject matter may be practiced without these specific details. In other instances well known structures and devices are shown in block diagram form in order to facilitate describing the subject innovation.

As utilized herein terms component system browser web service client partner application and the like are intended to refer to a computer related entity either hardware software e.g. in execution and or firmware. For example a component can be a process running on a processor an object an executable a program a function a library a subroutine and or a computer or a combination of software and hardware. By way of illustration both an application running on a server and the server can be a component. One or more components can reside within a process and a component can be localized on one computer and or distributed between two or more computers. The term processor is generally understood to refer to a hardware component such as a processing unit of a computer system.

Furthermore the claimed subject matter may be implemented as a method apparatus or article of manufacture using standard programming and or engineering techniques to produce software firmware hardware or any combination thereof to control a computer to implement the disclosed subject matter. The term article of manufacture as used herein is intended to encompass a computer program accessible from any non transitory computer readable device or media.

Non transitory computer readable storage media can include but are not limited to magnetic storage devices e.g. hard disk floppy disk and magnetic strips among others optical disks e.g. compact disk CD and digital versatile disk DVD among others smart cards and flash memory devices e.g. card stick and key drive among others . Of course those skilled in the art will recognize many modifications may be made to this configuration without departing from the scope or spirit of the claimed subject matter. Moreover the word exemplary is used herein to mean serving as an example instance or illustration. Any aspect or design described herein as exemplary is not necessarily to be construed as preferred or advantageous over other aspects or designs.

Access to the partner enabled web service may be restricted to authenticated users and authenticated partner client applications. These partner client applications may run on web browser clients. However existing options to enable access for an authenticated user of a partner client application running on a browser are limited.

For example a partner authentication function may generate an application token to authenticate the partner client application running on the browser. Separate functionality may authenticate the user. However this scheme offers no association between the authenticated partner client application and the authenticated user. As such if the application token is compromised security to the partner server application may be jeopardized.

Further there is no strong hint to trace the compromised token back to the authenticated user responsible for the token. This could result in resetting the whole partner server application even for innocent users of such. Further because there is no mechanism for associating a user and a partner application a compromised user could claim an unverifiable association with any partner application. The result is that our partner enabled web service would not be able to trust the service requests from our partners.

A delegated authentication function may set up a session allowing the browser client to act on behalf of the authenticated user. While this scheme provides a strong association between the partner client application and the authenticated user this scheme prohibits the partner application from sharing the user s authenticated session. As such the partner application s authentication to the web service may be disjoint from other applications capable of sharing the same authentication system such as Windows Live enabled applications.

In one embodiment a partner client application running on a web browser may access a partner enabled web service. In such an embodiment the partner client application may be authenticated and associated with the authenticated user. In this manner the authenticated user may be enabled to access the partner enabled web service via a partner application running on a web browser.

The client may be a web browser that enables a user to create an authenticated session on the partner application . The partner enabled web service may be a secured web server application that provides access to common applications such as email chat and partner applications. Additionally the partner enabled web service may secure its data service by serving only users that are associated with the partner application .

The partner application and the partner enabled web service may have a trusted relationship that enables them to share a server side secret. In one embodiment the partner enabled web service may be accessed using a representational state transfer application program interface REST API .

Further both the partner application and the partner enabled web service share a set of proprietary authentication utilities. Using these utilities both the partner enabled web service and the partner application may be able to retrieve a user id from the authenticated session.

The partner application may also include a centralized authorization engine that holds a list of users who can use the client to access the partner application . Advantageously maintaining a centralized list of authorized users for a given application is easy to manage.

The authorization engine may issue a client application association token CAAT that is carried to the client . The client may then pass both the user authenticated session and the CAAT to the partner enabled web service . The authentication engine may then verify that the CAAT is generated by the partner application for the specified user. If any of the above steps fails the authentication may fail and the user may be denied access to the partner enabled web service .

In this manner an association may be maintained between an authenticated user and the authenticated partner application . Additionally the partner application may share a session with the partner enabled web service . The authenticated user may be any user that can authenticate using the set of proprietary authentication utilities.

The partner application may send a response to the client that includes a canary value. As understood by one skilled in the art the canary value may be used to guard against security issues like a replay attack and cross site request forgery.

The client may send an http request that includes the canary value. The http request may be for access to the partner application .

In response the partner application may determine whether the user is authorized to access the partner application .

If the user is authorized for both the partner application may generate a signature. The signature may include an application secret the user id and an application id for the partner application . The application secret may be a key shared by the partner application and the partner enabled web service and used for signing the signature.

The partner application may retrieve the user id from the authenticated session which may be represented as cookies. On the receiving end of the partner application the cookie may represent the logged in user. The cookies are transported to the partner application in a web service request to the partner application not shown .

In one embodiment the time within which the partner enabled web service is accessible to the partner application may be limited. In such an embodiment the signature may also include a time at which the signature is generated.

The signature may be included within the CAAT along with the application ID and time of issue. In one embodiment the signature may be encoded using a hashing algorithm such as a keyed hash message authentication code such as HMAC SHA1.

The application ID may enable the partner enabled web service to know which partner application has generated the CAAT. The partner enabled web service may use the application secret specific to the application ID to verify the CAAT. The time of issue may be used to guard against replay attacks so that the CAAT cannot be reused indefinitely.

The CAAT may be sent within the body of a response to the client . The client may store the CAAT in client memory. Advantageously by encoding the CAAT using a one way hashing algorithm no server side secrets may be readily exposed on the client .

The client may then compose a web service request for the partner enabled web service . In one embodiment the web service request may be a REST request. The REST request may include the CAAT in the request header. The client may then send an http request that includes the request header and cookies to the partner enabled web service .

The partner enabled web service may then regenerate the signature. The signature may be regenerated using the component parts the user id the application ID the time of issue and the application secret.

The partner enabled web service may retrieve the user id from the authenticated session. The application ID and the time of issue may be retrieved from the CAAT included in the request header.

Both the partner application and the partner enabled web service may own a copy of the application secret. As such the partner enabled web service may use the application ID to determine which application secret to use.

The partner enabled web service may then regenerate the signature and verify that the regenerated signature matches the signature included in the CAAT of the request header. If they match the partner enabled web service may process the request and send a response to the client . If not the partner enabled web service may send an error message.

As stated previously the time within which a signature may be used may be limited. In one embodiment the partner may calculate an expiration time that is eight hours passed the issue time. If the current time is past the expiration time the request may be rejected with an error message.

Advantageously using this method the CAAT passed to the client is associated with a user id. As such any breach of usage agreement with regard to a specific CAAT may be linked to a specific user. Because the CAAT is associating a user with the partner application the partner enabled web service may trust the origin of the request as a valid referral from a partner application .

One possible communication between a client and a server can be in the form of a data packet adapted to be transmitted between two or more computer processes. The environment includes a communication framework that can be employed to facilitate communications between the client s and the server s . The client s are operably connected to one or more client data store s that can be employed to store information local to the client s . The client data store s do not have to be in the client s but may be located remotely such as in a cloud server. Similarly the server s are operably connected to one or more server data store s that can be employed to store information local to the servers .

As an example the client s may be computers providing access to servers over a communication framework such as the Internet. The server s may be web service servers accessed by the client .

With reference to an exemplary operating environment for implementing various aspects of the claimed subject matter includes a computer . The computer includes a processing unit a system memory and a system bus .

The system bus couples system components including but not limited to the system memory to the processing unit . The processing unit can be any of various available processors. Dual microprocessors and other multiprocessor architectures also can be employed as the processing unit .

The system bus can be any of several types of bus structure s including the memory bus or memory controller a peripheral bus or external bus and or a local bus using any variety of available bus architectures known to those of ordinary skill in the art.

The system memory is non transitory computer readable media that includes volatile memory and nonvolatile memory . The basic input output system BIOS containing the basic routines to transfer information between elements within the computer such as during start up is stored in nonvolatile memory . By way of illustration and not limitation nonvolatile memory can include read only memory ROM programmable ROM PROM electrically programmable ROM EPROM electrically erasable programmable ROM EEPROM or flash memory.

Volatile memory includes random access memory RAM which acts as external cache memory. By way of illustration and not limitation RAM is available in many forms such as static RAM SRAM dynamic RAM DRAM synchronous DRAM SDRAM double data rate SDRAM DDR SDRAM enhanced SDRAM ESDRAM SynchLink DRAM SLDRAM Rambus direct RAM RDRAM direct Rambus dynamic RAM DRDRAM and Rambus dynamic RAM RDRAM .

The computer also includes other non transitory computer readable media such as removable non removable volatile non volatile computer storage media. shows for example a disk storage . Disk storage includes but is not limited to devices like a magnetic disk drive floppy disk drive tape drive Jaz drive Zip drive LS 100 drive flash memory card or memory stick.

In addition disk storage can include storage media separately or in combination with other storage media including but not limited to an optical disk drive such as a compact disk ROM device CD ROM CD recordable drive CD R Drive CD rewritable drive CD RW Drive or a digital versatile disk ROM drive DVD ROM . To facilitate connection of the disk storage devices to the system bus a removable or non removable interface is typically used such as interface .

It is to be appreciated that describes software that acts as an intermediary between users and the basic computer resources described in the suitable operating environment . Such software includes an operating system . Operating system which can be stored on disk storage acts to control and allocate resources of the computer system .

System applications take advantage of the management of resources by operating system through program modules and program data stored either in system memory or on disk storage . It is to be appreciated that the claimed subject matter can be implemented with various operating systems or combinations of operating systems.

A user enters commands or information into the computer through input device s . Input devices include but are not limited to a pointing device such as a mouse trackball stylus or the like a keyboard a microphone a joystick a satellite dish a scanner a TV tuner card a digital camera a digital video camera a web camera and or the like. The input devices connect to the processing unit through the system bus via interface port s . Interface port s include for example a serial port a parallel port a game port and a universal serial bus USB .

Output device s use some of the same type of ports as input device s . Thus for example a USB port may be used to provide input to the computer and to output information from computer to an output device .

Output adapter is provided to illustrate that there are some output devices like monitors speakers and printers among other output devices which are accessible via adapters. The output adapters include by way of illustration and not limitation video and sound cards that provide a means of connection between the output device and the system bus . It can be noted that other devices and or systems of devices provide both input and output capabilities such as remote computer s .

The computer can be a server hosting a partner enabled web service in a networked environment using logical connections to one or more remote computers such as remote computer s . The remote computer s may be client systems configured with web browsers PC applications mobile phone applications and the like to allow users to access the advertising network as discussed herein. The remote computer s can be a personal computer a server a router a network PC a workstation a microprocessor based appliance a mobile phone a peer device or other common network node and the like and typically includes many or all of the elements described relative to the computer .

For purposes of brevity only a memory storage device is illustrated with remote computer s . Remote computer s is logically connected to the computer through a network interface and then physically connected via a communication connection .

Network interface encompasses wire and or wireless communication networks such as local area networks LAN and wide area networks WAN . LAN technologies include Fiber Distributed Data Interface FDDI Copper Distributed Data Interface CDDI Ethernet Token Ring and the like. WAN technologies include but are not limited to point to point links circuit switching networks like Integrated Services Digital Networks ISDN and variations thereon packet switching networks and Digital Subscriber Lines DSL .

Communication connection s refers to the hardware software employed to connect the network interface to the bus . While communication connection is shown for illustrative clarity inside computer it can also be external to the computer . The hardware software for connection to the network interface may include for exemplary purposes only internal and external technologies such as mobile phone switches modems including regular telephone grade modems cable modems and DSL modems ISDN adapters and Ethernet cards.

An exemplary embodiment of the computer may comprise a server hosting a partner enabled web service. The server may be configured to secure access to partner applications as described herein. An exemplary processing unit for the server may be a computing cluster comprising Intel Xeon CPUs. The disk storage may comprise an enterprise data storage system for example holding thousands of impressions.

Exemplary embodiments of the subject innovation may associate an authenticated user with an authenticated application. The subject innovation may generate a token that includes a user id application id and an application secret that is encoded by a one way hashing algorithm.

What has been described above includes examples of the subject innovation. It is of course not possible to describe every conceivable combination of components or methodologies for purposes of describing the claimed subject matter but one of ordinary skill in the art may recognize that many further combinations and permutations of the subject innovation are possible. Accordingly the claimed subject matter is intended to embrace all such alterations modifications and variations that fall within the spirit and scope of the appended claims.

In particular and in regard to the various functions performed by the above described components devices circuits systems and the like the terms including a reference to a means used to describe such components are intended to correspond unless otherwise indicated to any component which performs the specified function of the described component e.g. a functional equivalent even though not structurally equivalent to the disclosed structure which performs the function in the herein illustrated exemplary aspects of the claimed subject matter. In this regard it will also be recognized that the innovation includes a system as well as a computer readable storage media having computer executable instructions for performing the acts and or events of the various methods of the claimed subject matter.

There are multiple ways of implementing the subject innovation e.g. an appropriate API tool kit driver code operating system control standalone or downloadable software object etc. which enables applications and services to use the techniques described herein. The claimed subject matter contemplates the use from the standpoint of an API or other software object as well as from a software or hardware object that operates according to the techniques set forth herein. Thus various implementations of the subject innovation described herein may have aspects that are wholly in hardware partly in hardware and partly in software as well as in software.

The aforementioned systems have been described with respect to interaction between several components. It can be appreciated that such systems and components can include those components or specified sub components some of the specified components or sub components and or additional components and according to various permutations and combinations of the foregoing. Sub components can also be implemented as components communicatively coupled to other components rather than included within parent components hierarchical .

Additionally it can be noted that one or more components may be combined into a single component providing aggregate functionality or divided into several separate sub components and any one or more middle layers such as a management layer may be provided to communicatively couple to such sub components in order to provide integrated functionality. Any components described herein may also interact with one or more other components not specifically described herein but generally known by those of skill in the art.

In addition while a particular feature of the subject innovation may have been disclosed with respect to only one of several implementations such feature may be combined with one or more other features of the other implementations as may be desired and advantageous for any given or particular application. Furthermore to the extent that the terms includes including has contains variants thereof and other similar words are used in either the detailed description or the claims these terms are intended to be inclusive in a manner similar to the term comprising as an open transition word without precluding any additional or other elements.

