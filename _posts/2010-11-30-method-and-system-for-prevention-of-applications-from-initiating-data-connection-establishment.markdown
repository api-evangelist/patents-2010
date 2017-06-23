---

title: Method and system for prevention of applications from initiating data connection establishment
abstract: A method and apparatus for prevention of user-level applications from initiating data connection establishment using signaling from radio code, the method including receiving a request from an application on a mobile device at a tunnel management module on the mobile device, the request being to establish a data connection with a network; checking a state of a tunnel for the data connection at the tunnel management module; blocking the connection request if the tunnel for the data connection is in a stalled state; and allowing the connection request to proceed to a networking access interface module if the tunnel for the data connection is not in a stalled state.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08898302&OS=08898302&RS=08898302
owner: BlackBerry Limited
number: 08898302
owner_city: Waterloo
owner_country: US
publication_date: 20101130
---
The present disclosure claims priority from U.S. provisional application No. 61 349 968 filed May 31 2010 the entire contents of which are incorporated herein by reference.

The present disclosure relates to radio bearers for mobile device and in particular to the establishment of radio bearers.

A mobile device requires the establishment of a radio access bearer in order to communicate with the wireless network infrastructure. Furthermore some devices allow the establishment of multiple radio access bearers for communication. In one instance multiple radio access bearers can be dependent on the device requiring multiple PDP contexts. Thus for example a device may have a propriety PDP context for the manufacturer of the device a general wireless application protocol WAP context for browsing a multi media messaging service MMS PDP context for MMS applications a streaming media PDP context for streaming media applications among others. As will be appreciated a PDP context is a term that is generally referred to in the third generation partnership project 3GPP and more generally the term tunnel is used herein to refer to a data connection to a particular network.

The establishment of a connection may fail for a variety of reasons. For example the network may indicate that a particular data connection is not allowed in the current network area. However user level applications may not know how to interpret this information and have little knowledge of when a data connection can or cannot be established. An application or client may thus initiate a data connection process continually even on data connections which are known to fail.

The present disclosure provides a method comprising receiving a request from an application on a mobile device at a tunnel management module on the mobile device the request being to establish a data connection with a network checking a state of a tunnel for the data connection at the tunnel management module blocking the connection request if the tunnel for the data connection is in a stalled state and allowing the connection request to proceed to a networking access interface module if the tunnel for the data connection is not in a stalled state.

The present disclosure further provides a mobile device comprising a processor a communications subsystem and memory storing an application a tunnel management module and a networking access interface module wherein the processor and communications subsystem cooperate to receive a request from the application at the tunnel management module the request being to establish a data connection with a network check a state of a tunnel for the data connection at the tunnel management module block the connection request if the tunnel for the data connection is in a stalled state and allow the connection request to proceed to the networking access interface module if the tunnel for the data connection is not in a stalled state.

As indicated above user level applications have little or no knowledge of when a data connection can or cannot be established. This may make the data connection process inefficient as the user level application may continually try to establish data connections which are known to fail. For example a network may indicate that a particular data connection is not allowed in the current network area. However the user level application may not know how to interpret the information.

The present disclosure provides for a registry of data connections which associate particular connection states to each data connection registered. Further radio code associated with a particular radio communication method may interpret radio access technology specific causes received over a radio network and may signal to the registry a state for the radio connection.

For example a general packet radio service GPRS radio code would know better than a user application how to interpret a GPRS cause given by a network. Thus a received cause stating that a data connection is not allowed in the current area may be interpreted by the radio code and signaling generated to send to the registry indicating that the state for the connection is stalled .

Reference is now made to . shows an exemplary block diagram of various components within a mobile device that may be used to establish connections from the mobile device to a network. In particular a tunnel management module TMM is an intermediate module between a client and a wireless access family WAF .

Client may be any service or application that requires a data connection with a network. Examples of clients include but are not limited to email applications web browsers multimedia services streaming media among others.

Wireless access family WAF provides for the various wireless access options on the mobile device. Thus if a mobile device is able to connect over both code division multiple access CDMA and third generation partnership project 3GPP technologies such as global system for mobile communication GSM universal mobile telecommunications system UMTS long term evolution LTE or long term evolution advanced LTE A then the wireless access family may have a WAF CDMA and a WAF 3GPP option. In other embodiments the WAF may have access to wireless local area networks WLANs over technologies such as WiFi or WiMAX . Further the present disclosure is not meant to be limited to any particular wireless access family and those skilled in the art will appreciate that WAF may be customized for each particular mobile device. WAF is also referred to as a networking access interface. Further the networking access interface does not need to be wireless in some embodiments.

TMM provides a registry of data connections for clients . The tunnels for the data connection are each provided with a state as described in more detail below.

Requests to establish a data connection proceed from client to TMM . TMM then proceeds to forward the request to WAF in certain situations as described in more detail below.

In order to access the registry of data connections at TMM an interface is provided between the client and TMM . Client to TMM functions may be provided using TMM Client interface as shown by arrow . Further TMM Client interface may provide client to TMM messaging as shown by arrow .

TMM to client functions may be provided as shown by arrow between TMM and TMM Client interface . Also TMM Client interface may provided TMM to client messaging as shown by arrow .

Similarly an interface between TMM and WAF is provided as shown by TMM WAF interface . TMM to WAF functions may be provided to TMM WAF interface as shown by arrow . The TMM WAF interface may then provide TMM to WAF messaging as shown by arrow .

WAF to TMM functions may be provided to the TMM WAF interface as shown by arrow . Further TMM WAF interface may provide WAF to TMM messaging as shown by arrow .

The use of the TMM client interface allows various clients to communicate with TMM . Further the use of TMM WAF interface allows for various WAF to be able to communicate with TMM .

Reference is now made to which shows an exemplary state machine in which four internal states are defined. Namely the internal states may be null state closed state open state and stalled state . Each is described in more detail below.

Further the internal states shown by state machine of can be mapped to external states. The external states may be ready or not ready. A ready external state means that the tunnel could be used to send and receive data. A not ready state means that the tunnel cannot be used to send or receive data at the moment. The description below discusses internal states and may provide a link to an external state.

Initially before a tunnel is registered with TMM a tunnel may be in a null state . This indicates that the tunnel record is not allocated. Messages regarding activation and deactivation are flushed for a tunnel is null state .

Further tunnels in null state cannot be considered for activation by TMM . The null state may be considered to be not ready from an external state perspective.

During tunnel allocation in null state tunnels may be considered but only if clear. A clear pending flag is used for this purpose. In other words if there are pending messages for the tunnels the clear pending flag ensures that newly allocated tunnels do not receive stale activation or deactivation messages from the WAF when reallocated.

From null state a tunnel may be registered. Registration moves the state of the tunnel from null state to closed state .

Closed state indicates that the tunnel record is allocated but the tunnel is not activated. Tunnels in this state are considered for activation by TMM . As will be appreciated one purpose of TMM is to provide service to a maximal set of registered tunnels and thus closed state is in effect a continual retry state. Further the closed state maps to the not ready external state.

From closed state the tunnel may be activated by TMM in which case the state proceeds to open state . Further the tunnel may be deregistered which would cause the state to move back to null state . Finally the tunnel may be considered to be stalled in which case the state would change to stalled state .

Open state indicates that the tunnel record is allocated and the tunnel is activated. Tunnels in this state are used for communication of data. Open state maps to a ready external state.

The state may change from open state if the tunnel is deactivated in which case the state changes to closed state . This may for example be required if a prioritization algorithm changes the priority of the tunnels and the current tunnel does not have a high enough priority.

For example a network may have a watermark which indicates how many tunnels are allowed to be open. If two tunnels are allowed to be open and two other services have a higher priority than the current tunnel the prioritization algorithm may find that the present tunnel needs to be deactivated which would move the tunnel to closed state .

In other cases the tunnel may be finished with the exchange of data and may be deactivated causing the state of the tunnel to change to closed state .

Stalled state indicates that the tunnel record is allocated but the tunnel is not activated. Messages regarding activation and deactivation are flushed for a tunnel in stalled state .

One difference between stalled state and closed state is that tunnels that are in stalled state are not considered for activation by TMM . Entering stalled state effectively halts retries and the state is considered externally as not ready.

From stalled state the tunnel may be deregistered causing the state to change to null state . The tunnel may also be unstalled and change the state to closed state .

Based on the TMM keeps a state for each registered tunnel which may be one of the closed open or stalled states shown. Tunnels that are not registered with TMM are considered to be in a null state . However as will be appreciated since the tunnel in null state is not registered with the TMM no entry in the registry will exist for the tunnel in one embodiment.

A client uses a tunnel to obtain data from a network. To use the tunnel the tunnel must change to an open state by being activated through a tunnel establishment attempt. The result of the establishment attempt is that the tunnel may be successfully established or that the establishment may fail.

In the case of failure as indicated above WAF is in a better position to interpret radio codes than client . Having client interpret radio codes may cause the client to misinterpret the radio code or ignore the radio code. Therefore if the radio code indicates that a data connection cannot be established at this time the client may ignore the radio code or not be capable of interpreting the radio code and continue to try to establish a data connection. This uses unnecessary network resources since connection requests are continually being made. Further the continual attempt to establish a connection can drain battery resources on the mobile device.

Client in may for example be a browser application. The browser application may be brought up by a user of a mobile device and an attempt to connect to the internet may be made over a WAP tunnel. In the example of it is assumed that the WAP tunnel is previously registered with TMM and that tunnel has therefore been placed in a closed state by TMM .

Client requests a data connection over a WAP tunnel be established as shown by message . TMM checks the state of the tunnel for the service of client as shown by arrow and determines that the tunnel is currently in a closed state. Based on this the TMM sends a message to WAF requesting a data connection as shown by arrow . WAF then requests a data connection with network as shown by arrow .

Network may determine that the data connection is now allowed for the current public land mobile network PLMN based on agreements between the mobile device carrier and the current network for example. Therefore a fail message is returned to WAF indicating a cause code of roaming not allowed in PLMN .

In accordance with one embodiment of the present disclosure WAF then interprets the fail code received in message as shown by arrow and determines that the tunnel should be set to a stalled state . The WAF then sends a message to TMM indicating that the tunnel should be set to stalled state . TMM receives message and updates the state of the tunnel as shown by arrow .

Subsequently client may decide that it wants to again attempt to establish a data connection. A message may be sent to TMM . In this case TMM checks the state of the tunnel and determines that the tunnel is in a stalled state as shown by arrow . TMM therefore does not consider activation of the tunnel and no further messaging is sent to WAF or to network thereby saving battery resources on the mobile device as well as network resources.

At some later time an event may occur. For example the routing area or the location area of the network may change. In this case WAF interprets the event as shown by arrow and determines that the routing area has changed. In this case the interpretation at arrow decides that the tunnels may be unstalled and thus an unstall message is sent to TMM which may be then update the state of the tunnel as shown by arrow .

The example of utilizes a roaming is not allowed in the PLMN fail code at arrow . However other indications that a data connection cannot be established would be known to those in the art. Examples which are not limiting include a set of Session Management errors for the 3GPP WAF including 

The above therefore provides for the maintaining of a state registry at a TMM to prevent user level applications such as client from initiating a data connection establishment attempt in the case that an indication from radio code has been previously received indicating that the data connection cannot be established for the current network.

The tunnel management module may be a software module located on a mobile device and in particular located in memory on the device. Further client may be any user level application or other application on the device stored in the memory on the device or accessible by the device and using a processor of the device for running the application.

WAF may be comprised of both the communications subsystem and software associated with it to use various communication technologies supported by the mobile device and to interpret radio level cause codes received by the device from a network that the device connects to.

As will be appreciated the registering of tunnels with a tunnel registry maintaining states for tunnels at the tunnel registry and deciding whether to initiate a data connection establishment request may be done utilizing the processor on a mobile device in combination with a communications subsystem of the mobile device. One such exemplary mobile device is illustrated below with reference to . The mobile device of is however not meant to be limiting and other mobile devices could also be used.

Mobile device is typically a two way wireless communication device having voice and data communication capabilities. Mobile device generally has the capability to communicate with other computer systems on the Internet. Depending on the exact functionality provided the mobile device may be referred to as a data messaging device a two way pager a wireless e mail device a cellular telephone with data messaging capabilities a wireless Internet appliance a wireless device a user equipment or a data communication device as examples.

Where mobile device is enabled for two way communication it will incorporate a communication subsystem including both a receiver and a transmitter as well as associated components such as one or more antenna elements and local oscillators LOs and a processing module such as a digital signal processor DSP . As will be apparent to those skilled in the field of communications the particular design of the communication subsystem will be dependent upon the communication network in which the device is intended to operate.

Network access requirements will also vary depending upon the type of network . In some networks network access is associated with a subscriber or user of mobile device . A mobile device may require a removable user identity module RUIM or a subscriber identity module SIM card in order to operate on a network. The SIM RUIM interface is normally similar to a card slot into which a SIM RUIM card can be inserted and ejected like a diskette or PCMCIA card. The SIM RUIM card can have memory and hold many key configuration and other information such as identification and subscriber related information.

When required network registration or activation procedures have been completed mobile device may send and receive communication signals over the network . As illustrated in network can consist of multiple base stations communicating with the mobile device. For example in a hybrid CDMA 1 EVDO system a CDMA base station and an EVDO base station communicate with the mobile station and the mobile device is connected to both simultaneously. The EVDO and CDMA 1 base stations use different paging slots to communicate with the mobile device.

Signals received by antenna through communication network are input to receiver which may perform such common receiver functions as signal amplification frequency down conversion filtering channel selection and the like and in the example system shown in analog to digital A D conversion. A D conversion of a received signal allows more complex communication functions such as demodulation and decoding to be performed in the DSP . In a similar manner signals to be transmitted are processed including modulation and encoding for example by DSP and input to transmitter for digital to analog conversion frequency up conversion filtering amplification and transmission over the communication network via antenna . DSP not only processes communication signals but also provides for receiver and transmitter control. For example the gains applied to communication signals in receiver and transmitter may be adaptively controlled through automatic gain control algorithms implemented in DSP .

Mobile device generally includes a processor which controls the overall operation of the device. Communication functions including data and voice communications are performed through communication subsystem . Processor also interacts with further device subsystems such as the display flash memory random access memory RAM auxiliary input output I O subsystems serial port one or more keyboards or keypads speaker microphone other communication subsystem such as a short range communications subsystem and any other device subsystems generally designated as . Serial port could include a USB port or other port known to those in the art.

Some of the subsystems shown in perform communication related functions whereas other subsystems may provide resident or on device functions. Notably some subsystems such as keyboard and display for example may be used for both communication related functions such as entering a text message for transmission over a communication network and device resident functions such as a calculator or task list.

Operating system software used by the processor may be stored in a persistent store such as flash memory which may instead be a read only memory ROM or similar storage element not shown . Those skilled in the art will appreciate that the operating system specific device applications or parts thereof may be temporarily loaded into a volatile memory such as RAM . Received communication signals may also be stored in RAM .

As shown flash memory can be segregated into different areas for both computer programs and program data storage and . These different storage types indicate that each program can allocate a portion of flash memory for their own data storage requirements. Processor in addition to its operating system functions may enable execution of software applications on the mobile device. A predetermined set of applications that control basic operations including at least data and voice communication applications for example will normally be installed on mobile device during manufacturing. Other applications could be installed subsequently or dynamically.

Applications and software such as client TMM WAF among others may be stored on any computer readable storage medium. The computer readable storage medium may be a tangible or intransitory non transitory medium such as optical e.g. CD DVD etc. magnetic e.g. tape or other memory known in the art.

One software application may be a personal information manager PIM application having the ability to organize and manage data items relating to the user of the mobile device such as but not limited to e mail calendar events voice mails appointments and task items. Naturally one or more memory stores would be available on the mobile device to facilitate storage of PIM data items. Such PIM application may have the ability to send and receive data items via the wireless network . In one embodiment the PIM data items are seamlessly integrated synchronized and updated via the wireless network with the mobile device user s corresponding data items stored or associated with a host computer system. Further applications may also be loaded onto the mobile device through the network an auxiliary I O subsystem serial port short range communications subsystem or any other suitable subsystem and installed by a user in the RAM or a non volatile store not shown for execution by the processor . Such flexibility in application installation increases the functionality of the device and may provide enhanced on device functions communication related functions or both. For example secure communication applications may enable electronic commerce functions and other such financial transactions to be performed using the mobile device .

In a data communication mode a received signal such as a text message or web page download will be processed by the communication subsystem and input to the processor which may further process the received signal for output to the display or alternatively to an auxiliary I O device .

A user of mobile device may also compose data items such as email messages for example using the keyboard which may be a complete alphanumeric keyboard or telephone type keypad among others in conjunction with the display and possibly an auxiliary I O device . Such composed items may then be transmitted over a communication network through the communication subsystem .

For voice communications overall operation of mobile device is similar except that received signals would typically be output to a speaker and signals for transmission would be generated by a microphone . Alternative voice or audio I O subsystems such as a voice message recording subsystem may also be implemented on mobile device . Although voice or audio signal output is preferably accomplished primarily through the speaker display may also be used to provide an indication of the identity of a calling party the duration of a voice call or other voice call related information for example.

Serial port in would normally be implemented in a personal digital assistant PDA type mobile device for which synchronization with a user s desktop computer not shown may be desirable but is an optional device component. Such a port would enable a user to set preferences through an external device or software application and would extend the capabilities of mobile device by providing for information or software downloads to mobile device other than through a wireless communication network. The alternate download path may for example be used to load an encryption key onto the device through a direct and thus reliable and trusted connection to thereby enable secure device communication. As will be appreciated by those skilled in the art serial port can further be used to connect the mobile device to a computer to act as a modem.

Other communications subsystems such as a short range communications subsystem is a further optional component which may provide for communication between mobile device and different systems or devices which need not necessarily be similar devices. For example the subsystem may include an infrared device and associated circuits and components or a Bluetooth communication module to provide for communication with similarly enabled systems and devices.

While the above examples utilize PDP contexts in 3GPP networks such as HSDPA networks the solution is equally applicable to other networks which include but are not limited to Universal Mobile Telecommunications System UMTS networks Global System for Mobile telephony GSM networks Long Term Evolution LTE networks among others. For example in UMTS the channels are cumulative and the data must therefore be shared between the channels.

The embodiments described herein are examples of structures systems or methods having elements corresponding to elements of the techniques of this application. This written description may enable those skilled in the art to make and use embodiments having alternative elements that likewise correspond to the elements of the techniques of this application. The intended scope of the techniques of this application thus includes other structures systems or methods that do not differ from the techniques of this application as described herein and further includes other structures systems or methods with insubstantial differences from the techniques of this application as described herein.

