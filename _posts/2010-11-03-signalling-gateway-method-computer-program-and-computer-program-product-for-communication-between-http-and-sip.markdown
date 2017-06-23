---

title: Signalling gateway, method, computer program and computer program product for communication between HTTP and SIP
abstract: A signalling gateway is arranged to allow a first client using hypertext transfer protocol, HTTP, to initiate a real-time connection to a SIP, session initiation protocol, client using SIP. The signalling gateway is arranged to use a distributed shared memory to support communication between the first client and the signalling gateway regarding session information of the real-time connection. Corresponding methods, computer programs, and computer program products are also presented.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09432408&OS=09432408&RS=09432408
owner: Telefonaktiebolaget LM Ericsson (Publ)
number: 09432408
owner_city: Stockholm
owner_country: SE
publication_date: 20101103
---
This application is a 35 U.S.C. 371 national stage application of PCT International Application No. PCT SE2010 051196 filed on 3 Nov. 2010 the disclosure and content of which is incorporated by reference herein in its entirety. The above referenced PCT International Application was published in the English language as International Publication No. WO 2012 060747 A1 on 10 May 2012.

The invention relates to enabling communication between a client using HTTP HyperText Transfer Protocol and a client using SIP Session Initiation Protocol .

Streaming media over IP Internet Protocol networks have been used for many years now. However there are still problems with interconnecting clients of various networks.

For example it is beneficial if web clients can set up communication with SIP clients. So far there are a number of issues with such communication. One aspect of SIP is that is was designed to operate on in practice managed networks. In other words the design of SIP assumes that it is always possible to discover the routing information needed to route messages to their respective end receivers. The Internet today often does not allow this due to the presence of private networks which often implies the user of NATs Network Address Translators and firewalls.

In the prior art solutions have been developed to allow clients of the web domain and SIP domain to connect but these are complicated intricate and delicate.

An object of the invention is to provide a gateway method computer program and computer program product to allow a first client using HTTP to connect to a SIP client which is simpler and easier than what is known in the prior art.

A first aspect is a signalling gateway arranged to allow a first client using hypertext transfer protocol HTTP to initiate a real time connection to a SIP session initiation protocol client using SIP. The signalling gateway is arranged to use a distributed shared memory to support communication between the first client and the signalling gateway regarding session information of the real time connection.

By using the distributed shared memory complicated signalling protocols between the signalling gateway and the first client can be avoided. Session initialisation properties and status of the connection can simply be communicated by storing data in the distributed shared memory by the sending entity after which the receiving entity detects the changed added data and acts accordingly.

The signalling gateway may be arranged to use a player data structure of the distributed shared memory to send or receive data regarding active sessions and media players of the first client. In other words the shared memory can be used to make communication of properties of active sessions and players efficient.

The distributed shared memory may comprise a plurality of player data structures for respective plurality of first clients and wherein each player data structure has a unique key coupled to its respective first client. In other words the same distributed shared memory can be used for an entire system with many clients as long as each HTTP client is uniquely identifiable in the distributed shared memory.

The data regarding active sessions may comprise at least one of the following properties identifier of the SIP client conference identifier media encoding player state media gateway state and media gateway URL.

The distributed shared memory may comprise a users data structure for communicating available SIP clients to the first client. In other words also user data can be stored in the distributed shared memory to make communication more efficient and simple.

A second aspect is a method for enabling a real time connection between a first client using hypertext transfer protocol HTTP to a SIP session initiation protocol client using SIP.

The method comprises the steps performed in a signalling gateway of reading SIP client data from a distributed shared memory which SIP client data was stored in the distributed shared memory by the first client initialising communication with the SIP client and storing an indicator in the distributed shared memory the indicator indicating to the first client that the connection is initialised.

The indicator comprises a pointer to a media gateway for real time communication between the first client and the SIP client.

The steps of reading and storing may comprise reading and storing data respectively in a player data structure of the distributed shared memory the player data structure indicating active sessions and media players of the first client.

The data regarding active sessions may comprise at least one of the following properties identifier of the SIP client conference identifier media encoding player state media gateway state and media gateway URL.

The step may further comprise the step prior to the step of reading of storing in a users data structure of the distributed shared memory available SIP clients whereby the users data structure is available to the first client.

A third aspect is a computer program for a signalling gateway to enable a real time connection between a first client using hypertext transfer protocol HTTP to a SIP session initiation protocol client using SIP. The computer program comprises computer program code which when run on the signalling gateway causes the signalling gateway to perform the steps of reading SIP client data from a distributed shared memory which SIP client data was stored in the distributed shared memory by the first client initialise communication with the SIP client and storing an indicator in the distributed shared memory the indicator indicating to the first client that the connection is initialised.

A fourth aspect is a computer program product comprising a computer program according to the third aspect and a computer readable means on which the computer program is stored.

It is to be noted that any feature of the first second third and fourth aspects may where appropriate be applied to any other of these aspects.

It is to be noted what whenever the term call is used herein it can refer to a voice call a video call a call with both voice and video between two or more parties. A video call is to be construed as referring to any communication comprising images i.e. either streaming images or one or a succession of still images.

Generally all terms used in the application are to be interpreted according to their ordinary meaning in the technical field unless explicitly defined otherwise herein. All references to a an the element apparatus component means step etc. are to be interpreted openly as referring to at least one instance of the element apparatus component means step etc. unless explicitly stated otherwise. The steps of any method disclosed herein do not have to be performed in the exact order disclosed unless explicitly stated.

The invention will now be described more fully hereinafter with reference to the accompanying drawings in which certain embodiments of the invention are shown. This invention may however be embodied in many different forms and should not be construed as limited to the embodiments set forth herein rather these embodiments are provided by way of example so that this disclosure will be thorough and complete and will fully convey the scope of the invention to those skilled in the art. Like numbers refer to like elements throughout the description.

A client is user client comprising a web client and a media player . The user of the client would like to set up communication with one or more SIP Session Initiation Protocol clients . The SIP clients here also represent video or voice conferences. One or more other clients are arranged in the same way as the client and thus comprise a media player and a web client . A web server providing web pages to the web client which enables the web client to interact with a DSM distributed shared memory of DSM server as is explained in more detail below.

A DSM as used in the DSM server is a distributed global address space where every memory is assigned a unique address. By knowing this address it is possible to get a copy or replica of the memory. Any modification to the memory is synchronized so that every replica converges to the same state potentially after some time. This is known as eventual consistency as it may take time until the system becomes consistent. This consistency model is used in many NoSQL architectures to provide scalability in large scale databases running in data centres. While a DSM can be implemented in many different ways using a wide variety of algorithms embodiments herein benefit from some specific functionality in order to perform as expected.

In particular the DSM can be based on Operational Transformation OT . Operational Transformation is a theoretical framework for optimistic concurrency control allowing clients to work locally on a shared memory replica and then synchronize changes to a main memory instance in the background. Any operation on the local replica is applied immediately without being delayed due to a server request or response. This makes it possible to implement responsive user interfaces very suitable for web browsers without having to wait for lock on a central data base.

For example the Jupiter algorithm as presented in Nichols et al. High latency low bandwidth windowing in the Jupiter collaboration system Proceedings of the 8annual ACM symposium on User interface and software technology pp. 111 120 1995 can be used to implement OT.

Optimistic concurrency control allows the Media Player to write to the DSM without having to wait and block the browser s main thread or having to care about other network issues such as managing different event listeners for incoming data. It just writes to the DSM and wait for the changes to be propagated to all other replica instances and ultimately some other entity to update the memory. As the DSM takes care of all synchronization issues it significantly reduces the complexity of the client making it easy to implement.

The DSM server is in turn in contact with a signalling gateway which acts as a signalling interface between the web domain and the SIP domain . As such the signalling gateway is in contact with a Call Session Control Function CSCF which is used to process SIP signalling packets for call management.

The CSCF is in contact with an application server such as an IMS IP multimedia system application server which in turn is in contact with a Media Resource Function Processor MRFP . The MRFP is a media plane node used to mix source or process media streams. The MRFP can also manage access right to shared resources. The MRFP is in contact with one or more SIP clients such as IMS terminals or conferences.

The SIP clients can via the MRFP and a media gateway communicate with clients in the web domain e.g. using RTP real time protocol . The purpose of the media gateway is to exchange packets with payload data such as RTP packets between the web domain and the SIP domain . In this way two way real time communication is enabled between the http clients and the SIP clients .

The media player adapter connects a media player component e.g. in the browser to the DSM . The media player adapter can either be implemented using any suitable player implementation structure such as a HTML5 HyperText Markup Language 5 player DOM object a NPAPI Netscape Plugin Application Programming Interface browser plug in or an ActiveX browser plug in. The media player adapter can either run in the browser or in the external web server .

The AS adapter connects a SIP conference session to the DSM . As the AS adapter shares the same address space as the media player adapter in the DSM they can work together independently of each other in establishing a multimedia session. The AS adapter can be an IMS AS adapter or any other module implementing equivalent functionality.

Optionally a participation adapter not shown is used to keep track of tracks of active users in an SIP conference session.

The idea in short is to allow a set of independent adapters to operate on the DSM which represents the current state of a session. Rather than defining a new signalling protocol for communication between different components it is only necessary to define a common data format and an addressing schema to locate and discover the DSM .

As will be explained in more detail below to set up a session the web application of the client calls the media player adapter which stores an initial session state in the DSM . This will trigger an event to the AS adapter running on the signalling gateway which will do some processing and update the DSM to another state. Typically the AS sets up a SIP dialog and configures the Web Media GW which the media player running under control of the browser can then use to exchange RTP packets with one or more SIP clients .

It is to be noted that the communication between the client and the AS adapter is completely event driven. For example the media player adapter stores data in the DSM which will trigger an event that is received by another node accessing the DSM such as the AS adapter . All information exchange is thus done by manipulating a data base which is addressed by a global identifier specified by developers effectively bypassing complicated protocol structures for this part of the set up process.

The players data structure keeps track of active sessions and media players. In this context a media player can both accept incoming media as well as capture and transmit outgoing media.

The users data structure keeps track of users and conference sessions. It contains information about which conferences meetings a particular user has access to as well as participation information. Note that each node in both data structures is part of a globally addressable DSM which means that the data structures are completely distributed and can be accessed by any peer in the system that has access to the DSM system .

A key is used to identify an object. For example the key can comprise a unique client identifier x and a suffix video or audio to indicate the type of media associated with the object.

An IMS adapter property allows the use of various services when applied to IMS. For example MMTel denoted IMS Multimedia Telephony and PoC denotes Push to talk over Cellular. If only one service is used all the time this property can be omitted. Alternatively if IMS is not used the property would typically a different name but would still indicate the service to use if the property is used.

A second client id property indicates the address or identifier of the second client i.e. the IMS client such as sip john foo.com.

A conference id property indicates an identifier of a conference to connect to. For example the conference id property can contain the SIP address to the conference that the AS adapter should join.

A media encoding property indicates how the media is encoded. A player state property and a media gateway state property indicate the state of the player and media gateway respectively. These properties can assume any state from the group of connecting connected disconnected and failed.

Now follows a short description on how the properties are used in practice with reference to . When a client wants to set up a call or join a video conference session it calls the media player adapter which determines a new DSM address based on a unique key x in the web page provided by the web server e.g. embedded in generated javascript. To be able to handle multiple media e.g. both voice and video the client appends another identifier to the address for example video . The media player adapter then creates a new DSM object based on the calculated key.

The media player adapter then adds some properties to the DSM for setting up a session for example media encoding and SIP URIs to the SIP system. The media player adapter also specifies an IMS Adapter name for example mmtel and sets the property called player state to connecting indicating that it wants to connect the media player to a remote conference session or another peer . The media player adapter then adds a listener to the DSM that is automatically called when a property called media gateway URL is added or updated to the object in the DSM . When the media gateway URL property is determined the media player component can connect to the media gateway which enables real time communication.

The media player adapter then adds a reference i.e. the DSM object address of the created DSM object to the players data structure in the DSM . This is needed to let the application server adapter of the signalling gateway detect that a new media player adapter has been created.

The web client sends an HTTP HyperText Transfer Protocol GET command to the web server to receive links to SIP clients such as conferences or users to connect to. The web server responds with generated HTML optionally using CSS Cascading StyleSheets and JavaScript or equivalent for client side processing. Optionally the response from the web server embeds the unique key to be used to distinguish the session in the DSM later. The reason that the server generates the key is to ensure that the keys for different clients are unique. An alternative solution is to let the browser clients generate a hash value themselves without server interference for example using MD5 Message Digest algorithm 5 . However the DSM addresses would become larger and more bandwidth would be consumed when synchronizing different DSM replicas.

The user interacts with the web client to select a SIP client to connect to whereby the web client sends a command to the media player adapter to set up communication. The media player adapter creates an object in the DSM stores data in properties to allow call setup and commits the changes. The AS adapter has an event listener for new objects in the DSM whereby an event is triggered to notify the AS adapter of the new object.

The AS adapter reads the object from the DSM and sends an HTTP add local termination command to the media gateway . The media gateway processes the command from the AS adapter and responds with HTTP port information to the AS adapter .

The AS adapter sends an SIP INVITE command to the CSCF which sends an SIP INVITE command to the application server . The application server then sends a H.248 add termination command to the MRFP which responds with SDP Session Description Protocol data to the application server . The application server in turn sends a SIP OK command to the CSCF which sends a SIP OK command to the AS adapter . The AS adapter responds to the CSCF with a SIP ACK message after which the CSCF sends a SIP ACK message to the application server .

The AS adapter can then send an HTTP add remote termination command to the media gateway which responds with an HTTP gateway URL . This allows the AS adapter to store the gateway URL property in the previously read DSM object in the DSM and commit the change. Since the media player adapter listens to any changes to the gateway URL property an event will be triggered from the DSM to the media player adapter .

The media player adapter can then configure the media player for real time communication after which the media player can set up real time two way communication to the media gateway e.g. RTP over WebSocket or HTTP or alternatively using STUN Session Traversal Utilities for NAT or ICE Interactive Connectivity Establishment to allow real time communication over NATs Network Address Translators . The media gateway sets up real time two way communication with the MRFP e.g. using RTP over UDP User Datagram Protocol . The MRFP in turn sets up real time two way communication e.g. using RTP over UDP with the SIP client . In this way real time two way communication between the media player of the client and the SIP client has been set up.

Furthermore the web server sends an HTTP register SIP user name command to the AS adapter . The AS adapter then sends a SIP register command to the CSCF for the user of the web client after which the CSCF responds with a SIP OK when the user is registered. The AS adapter also sends a SIP subscribe command to the application server .

In this way when any relevant updates are made e.g. to participant lists of conferences subscribed to the application server sends a SIP notify command to the AS adapter whereby the AS adapter stores and commits the change in the users data structure of the DSM . The user adapter of the client is registered to listen to such changes in the DSM whereby an event is triggered to the user adapter . The user adapter then effects a change in the web client e.g. an updated participant list in the browser window.

In a first store available SIP clients step the steps of the AS adapter of are executed to store available SIP clients in the users data structure of the distributed shared memory . This allows the users data structure to be available to the client .

In a read SIP client data step the signalling gateway reads SIP client data from the DSM . This SIP client data was previously stored in the DSM by the client indicating the SIP client that the client wants to connect to as explained above.

In an initialise communication step the signalling gateway sets up communication using appropriate elements as explained with reference to above. This substantially corresponds to the HTTP add local termination command SIP INVITE command SIP ACK command and HTTP add remote termination command .

Once the communication is initialised the signalling gateway stores an initialisation indicator in the DSM such as a pointer to the media gateway e.g. the media gateway URL. In this way the client knows that the communication is initialised and any necessary properties can be read from the players data structure in the DSM .

While embodiments herein mainly deal with setting up communication other parts of session management can also be implemented using the DSM such as disconnection adding or removing parties etc.

The invention has mainly been described above with reference to a few embodiments. However as is readily appreciated by a person skilled in the art other embodiments than the ones disclosed above are equally possible within the scope of the invention as defined by the appended patent claims.

