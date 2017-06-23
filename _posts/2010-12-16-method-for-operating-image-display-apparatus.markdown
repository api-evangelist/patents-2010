---

title: Method for operating image display apparatus
abstract: A multifunctional display device displays a first area containing a program received through a channel, a second area containing card objects, and a third area containing additional information of a downloadable applications selected in association with one of the card objects.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08863191&OS=08863191&RS=08863191
owner: LG Electronics Inc.
number: 08863191
owner_city: Seoul
owner_country: KR
publication_date: 20101216
---
This application claims the benefit of and priority to Korean Patent Application No. 10 2010 0071969 filed on Jul. 26 2010 in the Korean Intellectual Property Office and to U.S. Provisional Application No. 61 367 621 filed on Jul. 26 2010 the contents of which are incorporated herein by reference.

Televisions have traditionally displayed content based on received broadcast signals. Recently consumer demand has prompted an effort to expand the functionality of televisions computer monitors mobile terminals and other display devices. This in turn requires the development of a user interface that can both display and allow for adjustments in multimedia content for viewing by users.

The CP creates and provides content. The CP may be for example a terrestrial broadcaster a cable System Operator SO or Multiple System Operator MSO a satellite broadcaster or an Internet broadcaster as illustrated in .

The SP may provide content received from the CP in a service package. For instance the SP may package first terrestrial broadcasting second terrestrial broadcasting cable broadcasting satellite broadcasting Internet broadcasting and applications and provide the package to users.

The SP may unicast or multicast a service to the client . Unicast is a form of transmission in which information is sent from only one transmitter to only one receiver. In other words unicast transmission is point to point involving two nodes only. In an example of unicast transmission upon receipt of a request for data from a receiver a server transmits the data to only one receiver. Multicast is a type of transmission or communication in which a transmitter transmits data to a group of receivers. For example a server may transmit data to a plurality of pre registered receivers at one time. For multicast registration the Internet Group Management Protocol IGMP may be used.

The NP may provide a network over which a service is provided to the client . The client may construct a home network and receive a service over the home network. Content transmitted in the above described broadcasting system may be protected through conditional access or content protection. CableCard and Downloadable Conditional Access System DCAS are examples of conditional access or content protection.

The client may also transmit content over a network. In this case the client serves as a CP and thus the CP may receive content from the client . Therefore an interactive content service or data service can be provided.

The image display apparatus includes for example a broadcast interface a section filter an Application Information Table AIT filter an application data processor a broadcast data processor a media player an IP processor an Internet interface and a runtime module .

The image display apparatus receives AIT data real time broadcast content application data and stream events through the broadcast interface . The real time broadcast content may be referred to as linear Audio Video A V content.

The section filter performs section filtering on the four types of data received through the broadcast interface and outputs the AIT data to the AIT filter the linear A V content to the broadcast data processor and the stream events and application data to the application data processor .

Meanwhile the image display apparatus receives non linear A V content and application data through the Internet interface . The non linear A V content may be for example a Content On Demand CoD application.

The non linear A V content and the application data are transmitted to the media player and the runtime module respectively.

The runtime module includes for example an application manager and a browser as illustrated in . The application manager controls the life cycle of an interactive application using the AIT data for example. The browser displays and processes the interactive application.

More specifically SP Discovery is a process by which SPs that provide IPTV services search for Service Discovery SD servers having information about the offerings of the SPs.

In order to receive information about the SD servers an SD server address list can be detected for example using three methods specifically use of an address preset in the image display apparatus or an address manually set by a user Dynamic Host Configuration Protocol DHCP based SP Discovery and Domain Name System Service DNS SRV based SP Discovery. The image display apparatus accesses a specific SD server using the SD server address list obtained through one of the above three methods and receives a SP Discovery record from the specific SD server. The Service Provider Discovery record includes information needed to perform Service Discovery on an SP basis. The image display apparatus then starts a Service Discovery operation using the SP Discovery record. These operations can be performed in a push mode or a pull mode.

The image display apparatus accesses an SP attachment server specified by an SP attachment locator included in the SP Discovery record and performs a registration procedure or a service attachment procedure .

Further after accessing an authentication service server of an SP specified by an SP authentication locator and performing an authentication procedure the image display apparatus may perform a service authentication procedure.

After service attachment is successfully performed a server may transmit data in the form of a provision information table to the image display apparatus.

During service attachment the image display apparatus may include an Identifier ID and location information thereof in data and transmit the data to the service attachment server. Thus the service attachment server may specify a service that the image display apparatus has subscribed to based on the ID and location information. In addition the service attachment server provides in the form of a provisioning information table address information from which the image display apparatus can obtain Service Information SI . The address information corresponds to access information about a Master SI Table. This method facilitates provision of a customized service to each subscriber.

The SI is divided into a Master SI Table record for managing access information and version information about a Virtual Channel Map a Virtual Channel Map Table for providing a list of services in the form of a package a Virtual Channel Description Table that contains details of each channel and a Source Table that contains access information about actual services.

Each Virtual Channel MAP is identified by its Virtual Channel MAP identifier. VirtualChannelMAPVersion specifies the version number of the Virtual Channel MAP. If any of the tables connected to the Master SI Table in the arrowed direction is modified the versions of the modified table and overlying tables thereof up to the Master SI Table are incremented. Accordingly a change in any of the SI tables can be readily identified by monitoring the Master SI Table.

For example when the Source Table is changed the version of the Source Table is incremented and the version of the Virtual Channel Description Table that references the Source Table is also incremented. In conclusion a change in any lower table leads to a change in its higher tables and eventually a change in the Master SI Table.

One Master SI Table may exist for each SP. However in the case where service configurations differ for regions or subscribers or subscriber groups an SP may have a plurality of Master SI Tables in order to provide a customized service on a region subscriber or subscriber group basis. Thus it is possible to provide a customized service to a subscriber according to a region in which the subscriber is located and subscriber information regarding the subscriber.

A Virtual Channel Map Table may contain a list of one or more virtual channels. A Virtual Channel Map includes not details of the channels but information about the locations of the details of the channels. In the Virtual Channel Map Table VirtualChannelDescriptionLocation specifies the location of a Virtual Channel Description Table that provides virtual channel descriptions.

The Virtual Channel Description Table contains the details of the virtual channels. The Virtual Channel Description Table can be accessed using VirtualChannelDescriptionLocation of the Virtual Channel Map Table.

A Source Table provides information necessary to access actual services e.g. IP addresses ports AV Codecs transmission protocols etc. on a service basis.

The above described Master SI Table the Virtual Channel Map Table the Virtual Channel Description Table and the Source Table are delivered in four logically separate flows in a push mode or a pull mode. For version management the Master SI Table may be multicast and thus a version change can be monitored by receiving a multicast stream of the Master SI Table.

The network interface transmits packets to and receives packets from a network. Specifically the network interface receives services and content from an SP over the network.

The TCP IP manager is involved in packet reception and transmission of the image display apparatus that is packet delivery from a source to a destination. The TCP IP manager classifies received packets according to appropriate protocols and outputs the classified packets to the service delivery manager the service discovery manager the service control manager and the metadata manager .

The service delivery manager controls received service data. For example when controlling real time streaming data the service delivery manager may use the Real time Transport Protocol Real time Transport Control Protocol RIP RTCP . If real time streaming data is transmitted over RTP RTCP the service delivery manager parses the received real time streaming data using RTP and outputs the parsed real time streaming data to the DEMUX or stores the parsed real time streaming data in the SI metadata DB under the control of the service manager . In addition the service delivery manager feeds back network reception information to a server that provides the real time streaming data service using RTCP.

The DEMUX demultiplexes a received packet into audio data video data and PSI data and outputs the audio data video data and PSI data to the audio decoder the video decoder and the PSI PSIP and or SI decoder respectively.

The PSI PSIP and or SI decoder decodes SI such as PSI. More specifically the PSI PSIP and or SI decoder decodes PSI sections PSIP sections or SI sections received from the DEMUX .

The PSI PSIP and or SI decoder constructs an SI DB by decoding the received sections and stores the SI DB in the SI metadata DB .

The audio decoder and the video decoder decode the audio data and the video data received from the DEMUX and output the decoded audio and video data to a user through the display A V and OSD module .

The UI manager and the service manager manage the overall state of the image display apparatus provide UIs and manage other managers.

The UI manager provides a Graphical User Interface GUI in the form of an OSD and performs a reception operation corresponding to a key input received from the user. For example upon receipt of a key input signal regarding channel selection from the user the UI manager transmits the key input signal to service manager .

The service manager controls managers associated with services such as the service delivery manager the service discovery manager the service control manager and the metadata manager .

The service manager also makes a channel map and selects a channel using the channel map according to the key input signal received from the UI manager . The service manager sets the audio video Packet ID PID of the selected channel based on SI about the channel received from the PSI PSIP and or SI decoder .

The service discovery manager provides information necessary to select an SP that provides a service. Upon receipt of a channel selection signal from the service manager the service discovery manager detects a service based on the channel selection signal.

The service control manager takes charge of selecting and control services. For example if a user selects live broadcasting like a conventional broadcasting service the service control manager selects and controls the service using Internet Group Management Protocol IGMP or Real Time Streaming Protocol RTSP . If the user selects Video on Demand VoD the service control manager selects and controls the service. RTSP supports trick mode for real time streaming. Further the service control manager may initialize and manage a session through an IP Multimedia Control IMC gateway using IP Multimedia Subsystem IMS and Session Initiation Protocol SIP . The protocols are given by way of example and thus other protocols are also applicable according to other embodiments.

The metadata manager manages metadata related to services and stores the metadata in the SI metadata DB .

The SI metadata DB stores the SI decoded by the PSI PSIP and or SI decoder the metadata managed by the metadata manager and the information required to select an SP received from the service discovery manager . The SI metadata DB may store setup data for the system.

The tuner selects a Radio Frequency RF broadcast signal corresponding to a channel selected by a user from among a plurality of RF broadcast signals received through an antenna and downconverts the selected RF broadcast signal into a digital Intermediate Frequency IF signal or an analog baseband A V signal.

More specifically if the selected RF broadcast signal is a digital broadcast signal the tuner downconverts the selected RF broadcast signal into a digital IF signal DIF. On the other hand if the selected RF broadcast signal is an analog broadcast signal the tuner downconverts the selected RF broadcast signal into an analog baseband A V signal CVBS SIF. That is the tuner may be a hybrid tuner capable of processing not only digital broadcast signals but also analog broadcast signals. The analog baseband A V signal CVBS SIF may be directly input to the controller .

The tuner may be capable of receiving RF broadcast signals from an Advanced Television Systems Committee ATSC single carrier system or from a Digital Video Broadcasting DVB multi carrier system.

The tuner may sequentially select a number of RF broadcast signals corresponding to all broadcast channels previously stored in the image display apparatus by a channel add function from a plurality of RF signals received through the antenna and may downconvert the selected RF broadcast signals into IF signals or baseband A V signals.

The demodulator receives the digital IF signal DIF from the tuner and demodulates the digital IF signal DIF. For example if the digital IF signal DIF is an ATSC signal the demodulator may perform 8 Vestigal SideBand VSB demodulation on the digital IF signal DIF. The demodulator may also perform channel decoding. For channel decoding the demodulator may include a Trellis decoder not shown a de interleaver not shown and a Reed Solomon decoder not shown so as to perform Trellis decoding de interleaving and Reed Solomon decoding.

For example if the digital IF signal DIF is a DVB signal the demodulator performs Coded Orthogonal Frequency Division Multiple Access COFDMA demodulation upon the digital IF signal DIF. The demodulator may also perform channel decoding For channel decoding the demodulator may include a convolution decoder not shown a de interleaver not shown and a Reed Solomon decoder not shown so as to perform convolution decoding de interleaving and Reed Solomon decoding.

The demodulator may perform demodulation and channel decoding on the digital IF signal DIF thereby obtaining a stream signal TS. The stream signal TS may be a signal in which a video signal an audio signal and a data signal are multiplexed. For example the stream signal TS may be an MPEG 2 TS in which an MPEG 2 video signal and a Dolby AC 3 audio signal are multiplexed. An MPEG 2 TS may include a 4 byte header and a 184 byte payload.

In order to properly handle not only ATSC signals but also DVB signals the demodulator may include an ATSC demodulator and a DVB demodulator.

The stream signal TS may be input to the controller and thus subjected to demultiplexing and A V signal processing. The processed video and audio signals are output to the display and the audio output unit respectively.

The external device interface may serve as an interface between an external device and the image display apparatus . For interfacing the external device interface may include an A V Input Output I O unit not shown and or a wireless communication module not shown .

The external device interface may be connected to an external device such as a Digital Versatile Disk DVD player a Blu ray player a game console a camera a camcorder or a computer e.g. a laptop computer wirelessly or by wire. Then the external device interface externally receives video audio and or data signals from the external device and transmits the received input signals to the controller . In addition the external device interface may output video audio and data signals processed by the controller to the external device. In order to receive or transmit audio video and data signals from or to the external device the external device interface includes the A V I O unit not shown and or the wireless communication module not shown .

The A V I O unit of the external device interface may include a Universal Serial Bus USB port a Composite Video Banking Sync CVBS port a Component port a Super video S video analog port a Digital Visual Interface DVI port a High Definition Multimedia Interface HDMI port a Red Green Blue RGB port and a D sub port.

The wireless communication module of the external device interface may perform short range wireless communication with other electronic devices. For short range wireless communication the wireless communication module may use Bluetooth Radio Frequency IDentification RFID Infrared Data Association IrDA Ultra WideBand UWB ZigBee and Digital Living NetworkAlliance DLNA .

The external device interface may be connected to various set top boxes through at least one of the above described ports and may thus receive data from or transmit data to the various set top boxes. The external device interface may receive applications or an application list from an adjacent external device and provide the applications or the application list to the controller or the memory .

The network interface serves as an interface between the image display apparatus and a wired wireless network such as the Internet. The network interface may include an Ethernet port for connection to a wired network. The wireless communication module of the external signal I O unit may wirelessly access the Internet. For connection to wireless networks the network interface may use Wireless Local Area Network WLAN i.e. Wi Fi Wireless Broadband WiBro World Interoperability for Microwave Access WiMax and High Speed Downlink Packet Access HSDPA .

The network interface may transmit data to or receive data from another user or electronic device over a connected network or another network linked to the connected network. Especially the network interface may transmit data stored in the image display apparatus to a user or electronic device selected from among users or electronic devices pre registered with the image display apparatus .

The network interface may access a specific Web page over a connected network or another network linked to the connected network. That is the network interface may access a specific Web page over a network and transmit or receive data to or from a server. Additionally the network interface may receive content or data from a CP or an NP. Specifically the network interface may receive content such as movies advertisements games VoD files and broadcast signals and information related to the content from a CP or an NP. Also the network interface may receive update information about firmware and update files of the firmware from the NP. The network interface may transmit data over the Internet or to the CP or the NP.

The network interface may selectively receive a desired application among open applications over a network.

In one embodiment when a game application is executed in the image display apparatus the network interface may transmit data to or receive data from a user terminal connected to the image display apparatus through a network. In addition the network interface may transmit specific data to or receive specific data from a server that records game scores.

The memory may store various programs necessary for the controller to process and control signals and may also store processed video audio and data signals.

The memory may temporarily store a video audio and or data signal received from the external device interface or the network interface . The memory may store information about broadcast channels by the channel add function.

The memory may store applications or a list of applications received from the external device interface or the network interface . The memory may store a variety of platforms which will be described later.

In one embodiment when the image display apparatus executes a game application the memory may store user specific information and game play information about a user terminal used as a game controller.

The memory may include for example at least one of a flash memory type storage medium a hard disk type storage medium a multimedia card micro type storage medium a card type memory e.g. a Secure Digital SD or eXtreme Digital XD memory a Random Access Memory RAM or a Read Only Memory ROM such as an Electrically Erasable and Programmable Read Only Memory. The image display apparatus may reproduce content stored in the memory e.g. video files still image files music files text files and application files to the user.

While the memory is shown in as configured separately from the controller and the memory may be incorporated into the controller for example.

The user input interface transmits a signal received from the user to the controller or transmits a signal received from the controller to the user. For example the user input interface may receive various user input signals such as a power on off signal a channel selection signal and a screen setting signal from a remote controller or may transmit a signal received from the controller to the remote controller according to various communication schemes for example RF communication and IR communication.

For example the user input interface may provide the controller with user input signals or control signals received from local keys not shown such as inputs of a power key a channel key and a volume key and setting values.

Also the user input interface may transmit a control signal received from a sensor unit not shown for sensing a user gesture to the controller or transmit a signal received from the controller to the sensor unit. The sensor unit may include a touch sensor a voice sensor a position sensor a motion sensor etc.

The controller may demultiplex the stream signal TS received from the tuner the demodulator or the external device interface into a number of signals and process the demultiplexed signals into audio and video data.

The video signal processed by the controller may be displayed as an image on the display . The video signal processed by the controller may also be transmitted to an external output device through the external device interface .

The audio signal processed by the controller may be output to the audio output unit . Also the audio signal processed by the controller may be transmitted to the external output device through the external device interface .

While not shown in the controller may include a DEMUX and a video processor which will be described later with reference to .

In addition the controller may provide overall control to the image display apparatus . For example the controller may control the tuner to select an RF broadcast signal corresponding to a user selected channel or a pre stored channel.

The controller may control the image display apparatus according to a user command received through the user input interface or according to an internal program. Especially the controller may access a network and download an application or application list selected by the user to the image display apparatus over the network.

For example the controller controls the tuner to receive a channel selected according to a specific channel selection command received through the user input interface and processes a video audio and or data signal of the selected channel. The controller outputs the processed video or audio signal along with information about the user selected channel to the display or the audio output unit .

In another example the controller outputs a video or audio signal received from an external device such as a camera or a camcorder through the external device interface to the display or the audio output unit according to an external device video playback command received through the external device interface .

The controller may control the display to display images. For instance the controller may control the display to display a broadcast image received from the tuner an external input image received through the external device interface an image received through the network interface or an image stored in the memory . The image displayed on the display may be a Two Dimensional 2D or Three Dimensional 3D still image or moving picture.

The controller may control content playback. The content may include any content stored in the image display apparatus received broadcast content and external input content. The content includes at least one of a broadcast image an external input image an audio file a still image a Web page or a text file.

Upon receipt of a go to home screen input the controller may control display of the home screen on the display . The home screen may include a plurality of card objects classified according to content sources. The card objects may include at least one of a card object representing a thumbnail list of broadcast channels a card object representing a broadcast program guide a card object representing a program reservation list or a program recording list or a card object representing a media list of a device connected to the image display apparatus . The card objects may further include at least one of a card object representing a list of connected external devices or a card object representing a call associated list.

The home screen may further include an application menu with at least one application that can be executed. Upon receipt of a card object move input the controller may control movement of a card object corresponding to the card object move input on the display or if the card object is not displayed on the display the controller may control display of the card object on the display .

When a card object is selected from among the card objects on the home screen the controller may control display of an image corresponding to the selected card object on the display .

The controller may control display of an input broadcast image and an object representing information about the broadcast image in a card object representing broadcast images. The broadcast image may be fixed in size through lock setting.

The controller may control display of a set up object for at least one of image setting audio setting screen setting reservation setting setting of a pointer of the remote controller or network setting on the home screen.

The controller may control display of a log in object a help object or an exit object on a part of the home screen.

The controller may control display of an object representing the total number of available card objects or the number of card objects displayed on the display among all card objects on a part of the home screen.

If one of the card objects displayed on the display is selected the controller may fullscreen the selected card object to cover the entirety of display .

Upon receipt of an incoming call at a connected external device or the image display apparatus the controller may control focusing on or shift of a call related card object among the plurality of card objects.

If an application view menu item is selected the controller may control display of applications or a list of applications that are available in the image display apparatus or downloadable from an external network.

The controller may control installation and execution of an application downloaded from the external network along with various UIs. Also the controller may control display of an image related to the executed application on the display upon user selection.

In one embodiment when the image display apparatus provides a game application the controller may control assignment of player IDs to specific user terminals creation of game play information by executing the game application transmission of the game play information to the user terminals through the network interface and reception of the game play information at the user terminals.

The controller may control detection of user terminals connected to the image display apparatus over a network through the network interface display of a list of the detected user terminals on the display and reception of a selection signal indicating a user terminal selected for use as a user controller from among the listed user terminals through the user input interface .

The controller may control output of a game play screen of the game application inclusive of player information about each user terminal and game play information through the display .

The controller may determine the specific signal received from a user terminal through the network interface as game play information and thus control the game play information to be reflected in the game application in progress.

The controller may control transmission of the game play information about the game application to a specific server connected to the image display apparatus over a network through the network interface .

In another embodiment upon receipt of information about a change in the game play information from the server through the network interface the controller may control output of a notification message in a predetermined area of the display .

The image display apparatus may further include a channel browsing processor not shown for generating thumbnail images corresponding to channel signals or external input signals.

The channel browsing processor may extract some of the video frames of each of stream signals TS received from the demodulator or stream signals received from the external device interface and display the extracted video frames on the display as thumbnail images. The thumbnail images may be directly output to the controller or may be output after being encoded. Also it is possible to encode the thumbnail images into a stream and output the stream to the controller . The controller may display a thumbnail list including a plurality of received thumbnail images on the display . The thumbnail images may be updated sequentially or simultaneously in the thumbnail list. Therefore the user can readily identify the content of broadcast programs received through a plurality of channels.

The display may convert a processed video signal a processed data signal and an OSD signal received from the controller or a video signal and a data signal received from the external device interface into RGB signals thereby generating driving signals.

The display may be various types of displays such as a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED display a flexible display and a 3D display. The display may also be a touch screen that can be used not only as an output device but also as an input device.

The audio output unit may receive a processed audio signal e.g. a stereo signal a 3.1 channel signal or a 5.1 channel signal from the controller and output the received audio signal as sound. The audio output unit may employ various speaker configurations.

To sense a user gesture the image display apparatus may further include the sensor unit not shown that has at least one of a touch sensor a voice sensor a position sensor and a motion sensor as stated before. A signal sensed by the sensor unit may be output to the controller through the user input interface .

The image display apparatus may further include the camera unit not shown for capturing images of a user. Image information captured by the camera unit may be input to the controller . The controller may sense a user gesture from an image captured by the camera unit or a signal sensed by the sensor unit or by combining the captured image and the sensed signal.

The power supply supplies power to the image display apparatus . Particularly the power supply may supply power to the controller the display and the audio output unit which may be implemented as a System On Chip SOC .

For supplying power the power supply may include a converter not shown for converting Alternating Current AC into Direct Current DC . If the display is configured with for example a liquid crystal panel having a plurality of backlight lamps the power supply may further include an inverter not shown capable of performing Pulse Width Modulation PWM for luminance change or dimming driving.

The remote controller transmits a user input to the user input interface . For transmission of user input the remote controller may use various communication techniques such as Bluetooth RF communication IR communication UWB and ZigBee.

In addition the remote controller may receive a video signal an audio signal or a data signal from the user input interface and output the received signals visually audibly or as vibrations.

The above described image display apparatus may be a fixed digital broadcast receiver capable of receiving at least one of ATSC 8 VSB broadcast programs DVB T COFDM broadcast programs and ISDB T BST OFDM broadcast programs.

The block diagram of the image display apparatus illustrated in is purely exemplary. Depending upon the specifications of the image display apparatus in actual implementation the components of the image display apparatus may be combined or omitted or new components may be added. That is two or more components are incorporated into one component or one component may be configured as separate components as needed.

Unlike the configuration illustrated in the image display apparatus may be configured so as to receive and playback video content through the network interface or the external device interface without the tuner and the demodulator .

The image display apparatus is an example of image signal processing apparatus that processes a stored image or an input image. Other examples of the image signal processing apparatus include a set top box without the display and the audio output unit a DVD player a Blu ray player a game console and a computer. The set top box will be described later with reference to .

The network interface serves as an interface between the set top box and a wired wireless network such as the Internet. The network interface may transmit data to or receive data from another user or another electronic device over a connected network or over another network linked to the connected network.

The memory may store programs necessary for the signal processor to process and control signals and temporarily store a video audio and or data signal received from the external device interface or the network interface . The memory may also store platforms illustrated in as described later.

The signal processor processes an input signal. For example the signal processor may demultiplex or decode an input video or audio signal. For signal processing the signal processor may include a video decoder or an audio decoder. The processed video or audio signal may be transmitted to the display device through the external device interface .

The user input interface transmits a signal received from the user to the signal processor or a signal received from the signal processor to the user. For example the user input interface may receive various control signals such as a power on off signal an operation input signal and a setting input signal through a local key not shown or the remote controller and output the control signals to the signal processor .

The external device interface serves as an interface between the set top box and an external device that is connected wirelessly or by wire particularly the display device for signal transmission or reception. The external device interface may also interface with an external device such as a game console a camera a camcorder and a computer e.g. a laptop computer for data transmission or reception.

The set top box may further include a media input unit for media playback. The media input unit may be a Blu ray input unit for example. That is the set top box may include a Blu ray player. After signal processing such as demultiplexing or decoding in the signal processor a media signal from a Blu ray disk may be transmitted to the display device through the external device interface so as to be displayed on the display device .

The display device may include a tuner an external device interface a demodulator a memory a controller a user input interface a display and an audio output unit .

The tuner the demodulator the memory the controller the user input interface the display and the audio output unit are identical respectively to the tuner the demodulator the memory the controller the user input interface the display and the audio output unit illustrated in and thus a description thereof is not provided herein.

The external device interface serves as an interface between the display device and a wireless or wired external device particularly the set top box for data transmission or reception. Hence a video signal or an audio signal received through the set top box is output through the display or the audio output unit through the controller .

Referring to the configuration of the set top box and the display device illustrated in is similar to that of the set top box and the display device illustrated in except that the tuner and the demodulator reside in the set top box not in the display device . Thus the following description is given focusing on such difference.

The signal processor may process a broadcast signal received through the tuner and the demodulator . The user input interface may receive a channel selection input a channel store input etc.

The image display apparatus may receive a broadcast signal including a video signal from the broadcasting station . The image display apparatus may process the audio and video signals of the broadcast signal or the data signal of the broadcast signal suitably for transmission from image display apparatus . The image display apparatus may output images or sound based on the processed video or audio signal.

Meanwhile the image display apparatus may communicate with the network server . The network server is capable of transmitting signals to and receiving signals from the image display apparatus over a network. For example the network server may be a portable terminal that can be connected to the image display apparatus through a wired or wireless base station. In addition the network server may provide content to the image display apparatus over the Internet. A CP may provide content to the image display apparatus through the network server .

The image display apparatus may communicate with the external device . The external device can transmit and receive signals directly to and from the image display apparatus wirelessly or by wire. For instance the external device may be a media memory device or a player. That is the external device may be any of a camera a DVD player a Blu ray player a PC etc.

The broadcasting station the network server or the external device may transmit a signal including a video signal to the image display apparatus . The image display apparatus may display an image based on the video signal included in the received signal. Also the image display apparatus may transmit a signal received from the broadcasting station or the network server to the external device and may transmit a signal received from the external device to the broadcasting station or the network server . That is the image display apparatus may transmit content included in signals received from the broadcasting station the network server and the external device as well as playback the content immediately.

The DEMUX demultiplexes an input stream. For example the DEMUX may demultiplex an MPEG 2 TS into a video signal an audio signal and a data signal. The input stream signal may be received from the tuner the demodulator or the external device interface .

The video processor may process the demultiplexed video signal. For video signal processing the video processor may include a video decoder and a scaler .

The video decoder decodes the demultiplexed video signal and the scaler scales the resolution of the decoded video signal so that the video signal can be displayed on the display .

The video decoder may be provided with decoders that operate based on various standards. If the demultiplexed video signal is for example an MPEC 2 encoded video signal the video signal may be decoded by an MPEC 2 decoder.

On the other hand if the video signal is an H.264 encoded DMB or DVB handheld DVB H signal the video signal may be decoded by an H.264 decoder. The video signal decoded by the video processor is provided to the mixer .

The OSD generator generates an OSD signal autonomously or according to user input. For example the OSD generator may generate signals by which a variety of information is displayed as images or text on the display according to control signals received from the user input interface . The OSD signal may include various data such as a UI a variety of menu screens widgets icons etc. For example the OSD generator may generate a signal by which subtitles are displayed for a broadcast image or Electronic Program Guide EPG based broadcasting information.

The mixer may mix the decoded video signal with the OSD signal and output the mixed signal to the formatter . As the decoded broadcast video signal or the external input signal is mixed with the OSD signal an OSD may be overlaid on the broadcast image or the external input image.

The FRC may change the frame rate of an input image. For example a frame rate of 60 Hz is converted into a frame rate of 120 or 240 Hz. When the frame rate is to be changed from 60 Hz to 120 Hz a first frame is inserted between the first frame and a second frame or a predicted third frame is inserted between the first and second frames. If the frame rate is to be changed from 60 Hz to 240 Hz three identical frames or three predicted frames are inserted between the first and second frames. It is also possible to maintain the frame rate of the input image without frame rate conversion.

The formatter changes the format of the signal received from the FRC to be suitable for the display . For example the formatter may convert a received signal into an RGB data signal. The RGB signal may be output in the form of a Low Voltage Differential Signal LVDS or mini LVDS.

The audio processor not shown of the controller may process the demultiplexed audio signal. For audio signal processing the audio processor may have a plurality of decoders.

If the demultiplexed audio signal is a coded audio signal the audio processor of the controller may decode the audio signal. For example the demultiplexed audio signal may be decoded by an MPEG 2 decoder an MPEG 4 decoder an Advanced Audio Coding AAC decoder or an AC 3 decoder.

The data processor not shown of the controller may process the data signal obtained by demultiplexing the input stream signal. For example if the data signal is an encoded signal such as an EPG which includes broadcasting information specifying the start time end time etc. of scheduled broadcast TV or radio programs the controller may decode the data signal. Examples of an EPG include ATSC Program and System Information Protocol PSIP information and DVB Service Information SI .

ATSC PSIP information or DVB SI may be included in the header of a TS i.e. a 4 byte header of an MPEG 2 TS.

The block diagram of the controller illustrated in is but one possible embodiment. Depending upon the specifications of controller the components of the controller may be combined or omitted. Or new components are added to the controller .

Referring to a platform for either of the image display apparatuses is a separate type. The platform may be designed separately as a legacy system platform and a smart system platform . An OS kernel may be shared between the legacy system platform and the smart system platform .

The legacy system platform may include a stack of a driver middleware and an application layer on the OS kernel . On the other hand the smart system platform may include a stack of a library a framework and an application layer on the OS kernel .

The OS kernel is the core of an operating system. When the image display apparatus is driven the OS kernel may be responsible for operation of at least one of hardware drivers security protection for hardware and processors in the image display apparatus efficient management of system resources memory management hardware interfacing by hardware abstraction multi processing or scheduling associated with the multi processing. Meanwhile the OS kernel may further perform power management.

The hardware drivers of the OS kernel may include for example at least one of a display driver a Wi Fi driver a Bluetooth driver a USB driver an audio driver a power manager a binder driver or a memory driver.

Alternatively or additionally the hardware drivers of the OS kernel may be drivers for hardware devices within the OS kernel . The hardware drivers may include a character device driver a block device driver and a network device driver. The block device driver may need a buffer for buffering data on a block basis because data is transmitted on a block basis. The character device driver may not need a buffer since data is transmitted on a basic data unit basis that is on a character basis.

The OS kernel may be implemented based on any of various OSs such as Unix Linux Windows etc. The OS kernel may be a general purpose open OS kernel which can be implemented in other electronic devices.

The driver is interposed between the OS kernel and the middleware . Along with the middleware the driver drives devices for operations of the application layer . For example the driver may include a driver s for a microcomputer a display module a Graphic Processing Unit GPU the FRC a General Purpose Input Output GPIO pin a High Definition Multimedia Interface HDMI a System Decoder SDEC or DEMUX a Video Decoder VDEC an Audio Decoder ADEC a Personal Video Recorder PVR and or an Inter Integrated Circuit C . These drivers operate in conjunction with the hardware drivers of the OS kernel .

In addition the driver may further include a driver for the remote controller especially a pointing device to be described below. The remote controller driver may reside in the OS kernel or the middleware instead of the driver .

The middleware resides between the OS kernel and the application layer . The middleware may mediate between different hardware devices or different software programs for data transmission and reception between the hardware devices or the software programs. Therefore the middleware can provide standard interfaces support various environments and enable interaction between tasks conforming to heterogeneous communication protocols.

Examples of the middleware in the legacy system platform may include Multimedia and Hypermedia information coding Experts Group MHEG and Advanced Common Application Platform ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware.

The application layer that runs atop the middleware in the legacy system platform may include for example UI applications associated with various menus in the image display apparatus. The application layer may allow editing and updating over a network by user selection. With use of the application layer the user may enter a desired menu among various UIs by manipulating the remote controller while viewing a broadcast program.

The application layer may further include at least one of a TV guide application a Bluetooth application a reservation application a Digital Video Recorder DVR application and a hotkey application.

In the smart system platform the library is positioned between the OS kernel and the framework forming the basis of the framework . For example the library may include Secure Socket Layer SSL being a security related library WebKit being a Web engine related library c library libc and Media Framework being a media related library specifying for example a video format and an audio format. The library may be written in C or C . Also the library may be exposed to a developer through the framework .

The library may include a runtime with a core Java library and a Virtual Machine VM . The runtime and the library form the basis of the framework .

The VM may be a virtual machine that enables concurrent execution of a plurality of instances that is multi tasking. For each application of the application layer a VM may be allocated and executed. For scheduling or interconnection between instances the binder driver not shown of the OS kernel may operate.

The binder driver and the runtime may connect Java applications to C based libraries. The library and the runtime may correspond to the middleware of the legacy system platform .

In the smart system platform the framework includes programs on which applications of the application layer are based. The framework is compatible with any application and may allow component reuse movement or exchange. The framework may include supporting programs and programs for interconnecting different software components. For example the framework may include an activity manager related to activities of applications a notification manager and a CP for abstracting common information between applications. This framework may be written in Java.

The application layer on top of the framework includes a variety of programs that are executed and displayed in the image display apparatus. The application layer may include for example a core application that is a suit having at least one solution of e mail Short Message Service SMS calendar map or browser. The application layer may be written in Java.

In the application layer applications may be categorized into user undeletable applications stored in the image display apparatus that cannot be modified and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus.

With the applications of the application layer a variety of functions such as Internet telephony VoD Web album Social Networking Service SNS Location Based Service LBS map service Web browsing and application search may be performed through network access. In addition other functions such as gaming and schedule management may be performed by the applications.

Referring to a platform for the image display apparatus according to another embodiment is an integrated type. The integrated platform may include an OS kernel a driver middleware a framework and an application layer .

Compared to the separate type platform illustrated in the integrated type platform is characterized by the absence of the library and the application layer being an integrated layer. The driver and the framework correspond to the driver and the framework of respectively.

The library of may be incorporated into the middleware . That is the middleware may include both the legacy system middleware and the image display system middleware. As described before the legacy system middleware includes MHEG or ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware whereas the image display system middleware includes SSL as a security related library WebKit as a Web engine related library libc and Media Framework as a media related library. The middleware may further include the afore described runtime.

The application layer may include a menu related application a TV guide application a reservation application etc. as legacy system applications and e mail SMS a calendar a map and a browser as image display system applications.

In the application layer applications may be categorized into user undeletable applications that are stored in the image display apparatus and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus.

Based on the afore described platforms illustrated in a variety of Application Programming Interfaces APIs and Software Development Kits SDKs necessary to develop applications may be opened. APIs may be implemented functions that provide connectivity to specific sub routines for execution of the functions within a program. Or APIs may be implemented programs.

For example sources related to hardware drivers of the OS kernel such as a display driver a WiFi driver a Bluetooth driver a USB driver or an audio driver may be opened. Related sources within the driver such as a driver for a microcomputer a display module a GPU an FRC an SDEC a VDEC an ADEC or a pointing device may be opened. In addition sources related to PSIP or SI middleware as broadcasting information related middleware or sources related to DLNA middleware may be opened.

Such various open APIs allow developers to create applications executable in the image display apparatus or applications required to control operations of the image display apparatus based on the platforms illustrated in .

The platforms illustrated in may be general purpose ones that can be implemented in many other electronic devices as well as in image display apparatuses. The platforms may be stored or loaded in the memory the controller or any other processor not shown . To execute applications an additional application processor not shown may be further provided.

The user may move or rotate the remote controller up and down side to side and back and forth . Since the pointer moves in accordance with the movement of the remote controller the remote controller may be referred to as a pointing device.

Referring to if the user moves the remote controller to the left the pointer moves to the left on the display . A sensor of the remote controller detects the movement of the remote controller and transmits motion information corresponding to the result of the detection to the image display apparatus Then the image display apparatus determines the movement of the remote controller based on the motion information received from the remote controller and calculates the coordinates of a target point to which the pointer should be shifted in accordance with the movement of the remote controller based on the result of the determination. The image display apparatus then displays the pointer at the calculated coordinates.

Referring to while pressing a predetermined button of the remote controller the user moves the remote controller away from the display . Then a selected area corresponding to the pointer may be zoomed in on and enlarged on the display . On the contrary if the user moves the remote controller toward the display the selection area corresponding to the pointer is zoomed out and thus contracted on the display . The opposite case is possible. That is when the remote controller moves away from the display the selection area may be zoomed out and when the remote controller approaches the display the selection area may be zoomed in.

With the predetermined button pressed in the remote controller the up down left and right movements of the remote controller may be ignored. That is when the remote controller moves away from or approaches the display only the back and forth movements of the remote controller are sensed while the up down left and right movements of the remote controller are ignored. Unless the predetermined button is pressed in the remote controller the pointer moves in accordance with the up down left or right movement of the remote controller .

The speed and direction of the pointer may correspond to the speed and direction of the remote controller . The pointer is an object displayed on the display in correspondence with the movement of the remote controller . Therefore the pointer may have various shapes other than the arrow illustrated in . For example the pointer may be a dot a cursor a prompt a thick outline etc. The pointer may be displayed across a plurality of points such as a line and a surface as well as at a single point on horizontal and vertical axes.

The wireless communication module transmits signals to and or receives signals from either of the afore described image display apparatuses herein the image display apparatus .

The wireless communication module may include an RF module for transmitting RF signals to and or receiving RF signals from the image display apparatus according to an RF communication standard. The wireless communication module may also include an IR module for transmitting IR signals to and or receiving IR signals from the image display apparatus according to an IR communication standard.

The remote controller transmits motion information representing the movement of the remote controller to the image display apparatus through the RF module in this embodiment. The remote controller may also receive signals from the image display apparatus through the RF module . As needed the remote controller may transmit commands such as a power on off command a channel switch command or a volume change command to the image display apparatus through IR module .

The user input unit may include a keypad a plurality of buttons a touchpad and or a touch screen. The user may enter commands to the image display apparatus by manipulating the user input unit . If the user input unit includes a plurality of hard buttons the user may input various commands to the image display apparatus by pressing the hard buttons. Alternatively or additionally if the user input unit includes a touch screen displaying a plurality of soft keys the user may input various commands to the image display apparatus by touching the soft keys. The user input unit may also include various input tools other than those set forth herein such as a scroll key and or a jog wheel.

The sensor unit may include a gyro sensor and or an acceleration sensor . The gyro sensor may sense the movement of the remote controller for example in X Y and Z axis directions and the acceleration sensor may sense the speed of the remote controller . The sensor unit may further include a distance sensor for sensing the distance between the remote controller and the display .

The output unit may output a video and or audio signal corresponding to manipulation of the user input unit or corresponding to a signal received from the image display apparatus . The user may easily identify whether the user input unit has been manipulated or whether the image display apparatus has been controlled based on the video and or audio signal output by the output unit .

The output unit may include a Light Emitting Diode LED module which is turned on or off whenever the user input unit is manipulated or whenever a signal is received from or transmitted to the image display apparatus through the wireless communication module a vibration module which generates vibrations an audio output module which outputs audio data and or a display module which outputs video data.

The power supply supplies power to the remote controller . If the remote controller is kept stationary for a predetermined time or longer the power supply may for example reduce or shut off supply of power to the spatial remote controller in order to save power. The power supply may resume power supply if a predetermined key on the spatial remote controller is manipulated.

The memory may store various types of programs and application data necessary to control or drive the remote controller . The spatial remote controller may wirelessly transmit signals to and or receive signals from the image display apparatus over a predetermined frequency band with the aid of the RF module . The controller of the remote controller may store information regarding the frequency band used for the remote controller to wirelessly transmit signals to and or wirelessly receive signals from the paired image display apparatus in the memory for later use.

The controller provides overall control to the remote controller . The controller may transmit a signal corresponding to a key manipulation detected from the user input unit or a signal corresponding to motion of the spatial remote controller as sensed by the sensor unit to the image display apparatus .

Specifically illustrates an application list available in a connected server displayed on the display . The application list may include an icon representing each application and a brief description of the application. Because each of the image display apparatuses is capable of full browsing it may enlarge the icons or descriptions of applications received from the connected server on the display . Accordingly the user can readily identify applications which will be described later.

While it is shown in that the user selects a desired application by moving the pointer using the remote controller the application may be selected in many other ways. For example the user may select a specific application using a cursor displayed on the display by a combined input of a local key and an OK key in the remote controller .

In another example if the remote controller has a touch pad the pointer moves on the display according to touch input of the touch pad. Thus the user may select a specific menu using the touch based pointer .

The image display apparatuses are capable of full browsing when displaying a mail service page. Therefore the user can use the mail service conveniently.

Referring to a card object area may be defined in a home screen . The card object area may include a plurality of card objects and classified according to content sources.

In the illustrated case of the card object is named BROADCAST and displays a broadcast image. The card object is named NETCAST and provides a CP list. The card object which is named APP STORE provides a list of applications.

Other card objects may be arranged in a hidden area and thus hidden from the display . These card objects may be shifted to show up on the display substituting for card objects displayed on the display . The hidden card objects are a CHANNEL BROWSER card object for providing a thumbnail list of broadcast channels a TV GUIDE card object for providing a program list a RESERVATION REC card object for providing a reserved or recorded program list a MY MEDIA card object for providing a media list available in the image display apparatus or in a device connected to the image display apparatus an EXTERNAL DEVICE card object for providing a list of connected external devices and a PHONE card object for providing a call related list.

The BROADCAST card object may contain a broadcast image received through the tuner or the network interface an object for providing information about the broadcast image an object representing an external device and a setup object .

The broadcast image is displayed as a card object. Since the broadcast image may be fixed in size by a lock function the user may continue viewing the broadcast image conveniently.

It is also possible to scale the broadcast image according to user manipulation. For instance the broadcast image may be enlarged or contracted by dragging the broadcast image with the pointer of the remote controller . As the broadcast image is scaled up or down four or two card objects may be displayed on the display instead of the current three card objects.

When the broadcast image is selected in the card object the broadcast image may be full screened on the display .

The object representing information about the broadcast image may include a channel number DTV7 1 a channel name YBC HD the title of a broadcast program Oh Lady and airing time 8 00 8 50 PM of the broadcast program. Therefore the user can be readily aware of information about the displayed broadcast image .

An object for notifying a date 03.24 a day THU and a current time 8 13 PM may be positioned above the card object that displays a broadcast image. Thus the user can identify time information readily through the object .

The object may represent an external device connected to the image display apparatus . For example if the object is selected a list of external devices connected to the image display apparatus may be displayed.

The setup object may be used to set various settings of the image display apparatus such as video settings audio settings screen settings reservation settings setting of the pointer of the remote controller and network settings.

The card object representing a CP list may contain a card object name NETCAST and a CP list . While Yakoo Metflix weather.com Pcason and My tube are shown as CPs in the CP list in it is obvious that many other settings are available.

Upon selection of the card object name the card object may be displayed fullscreen on the display . The same may apply to other card objects.

If a specific CP is selected from the CP list a screen with a list of content provided by the selected CP may be displayed on the display .

The card object representing an application list may include a card object name APP STORE and an application list . Applications may be sorted into predetermined categories in the application list . In the illustrated case of applications are sorted by popularity HOT and by time NEW .

Upon selection of an application from the application list a screen that provides information about the selected application may be displayed on the display .

A Log in menu item a Help menu item and an Exit menu item may be displayed above the card objects and .

The user may log in to the APP STORE or a network connected to the image display apparatus using the Log in menu item . The Help menu item provides guidance on operation of the image display apparatus . The Exit menu item is used to exit the home screen. When the Exit menu item is selected a received broadcast image may be fullscreened on the display .

An object may be displayed under the card objects and to indicate the total number of available card objects. Alternatively or additionally the object may indicate the number of card objects being displayed on the display as well.

The card object representing a thumbnail list of broadcast channels may include a card object name CHANNEL BROWSER and a thumbnail list of broadcast channels . Sequentially received broadcast channels are represented as thumbnail images in . The thumbnail images may be still images or moving pictures. The thumbnail list may include information about the channels along with the thumbnail images of the channels so that the user can readily identify broadcast programs of the channels. The thumbnail images may be thumbnail images of pre stored user favorite channels or thumbnail images of channels following or previous to the channel of the broadcast image displayed in the card object . Although eight thumbnail images are displayed in many other configurations are possible. Thumbnail images may be updated in the thumbnail list .

Upon selection of a thumbnail image from the thumbnail list a broadcast image corresponding to the channel of the selected thumbnail image may be displayed on the display .

The card object providing a program list may contain a card object name TV GUIDE and a program list . The program list may list broadcast programs that air after the broadcast program of the broadcast image or broadcast programs of other channels.

If a program is selected from the program list a broadcast image of the selected program or broadcasting information about the selected program may be displayed on the display .

The card object representing a reserved or recorded program list may include a card object name RESERVATION REC and a reserved or recorded program list . The reserved or recorded program list may include user reserved programs or programs recorded by reservation. While a thumbnail image is displayed for each program this is merely an exemplary application and thus various examples can be considered.

Upon selection of a reserved program or a recorded program from the reserved or recorded program list broadcast information about the reserved or recorded broadcast program or broadcast images of the recorded broadcast program may be displayed on the display .

The card object representing a media list may include a card object name MY OBJECT and a media list . The media list may list media available in the image display apparatus or a device connected to the image display apparatus . While the media are shown as moving pictures still images and audio in many other media such as text e books etc. may be added to the media.

Upon selection of a file from the media list the selected file may be opened and a screen corresponding to the selected file may be displayed on the display .

The card object representing a list of connected external devices may contain a card object name EXTERNAL DEVICE and a list of external devices connected to the image display apparatus . The external device list includes a gaming box a DVD player and a computer in by way of example.

Upon selection of a specific external device from the external device list a menu related to the selected external device may be executed. For example content may be played back from the external device and a screen corresponding to the reproduced content may be displayed on the display .

The card object representing a call related list may include a card object name PHONE and a call related list . The call related list may be a listing related to calls conducted in a portable phone not shown a computer not shown or the image display apparatus capable of placing calls. For instance the call related list may include a message item a phone book item or a setting item. Upon receipt of an incoming call at the portable phone the computer or the image display apparatus the call related card object may automatically show up in the card object area of the display . If the card object has already been displayed on the display it may be focused on highlighted .

Therefore the user can readily identify incoming calls of a nearby portable phone not shown a computer not shown or the image display apparatus . This is interactive function among the portable phone the computer and the image display apparatus called a 3 screen function.

Upon selection of a specific item from the call related list a screen corresponding to the selected item may be displayed on the display .

In the card objects and are displayed in the card object area and the card objects to are placed in the hidden area by way of example.

The card objects and displayed on the display may be exchanged with the hidden card objects to according to a card object shift input. Specifically at least one of the card objects and being displayed on the display may move to the hidden area and in turn at least one of the hidden objects to may show up on the display .

An application menu includes a plurality of application menu items particularly predetermined menu items to selected from among all available application menu items on the display . Thus the application menu may be referred to as an application compact view menu.

The application menu items to may be divided into mandatory application menu items and Search App Store and and optional application menu items Music Book MAZON and SNS set by the user.

The mandatory application menu items and may be fixed such that the user is not allowed to edit the same. The Search application menu item provides a search function based on an input search keyword. The App Store application menu item enables the user to access an AppStore directly. The View More application menu item may provide a fullscreen function.

In an exemplary embodiment an Internet application menu item and a mail application menu item may be added as mandatory application menu items in the application menu .

The user set application menu items may be edited to represent applications that the user often uses.

The method for operating an image display apparatus depicted in is an exemplary case in which a plurality of card objects are classified and arranged under tab menus according to classification.

Referring to a broadcast image is displayed in a first area S and tab menus corresponding to categories into which a plurality of applications are classified are displayed in a second area S . Upon selection of a tab menu applications that fall into a category corresponding to the selected tab menu are re classified and the icons of the applications are displayed in a plurality of card objects according to the re classified applications S . When one of the icons is focused on S information about an application corresponding to the focused icon is displayed in a third area S .

Instead of the tab menus any other type of menus may be displayed in step S. Alternatively step S may be omitted. That is card objects including a plurality of icons may be displayed in a part of the display .

As new applications are continuously emerging on the market users cannot easily identify applications displayed on a screen due to insufficient knowledge of the new applications. However if applications are classified into categories such as Games News Sports etc. as illustrated in a user may identify the applications more easily.

In addition the user can access the application market while viewing the broadcast image . Hence the user may search for an application to install without missing a desired content.

Upon selection of one of the tab menus a plurality of card objects and are displayed at least in a partial area of the display . Icons representing applications included in the selected tab menu are classified into the card objects and .

That is applications that fall into a category corresponding to the selected tab menu are re classified according to a predetermined criterion on a card object basis so that the user can identify the applications more readily.

In the illustrated case of a tab menu corresponding to a category All containing all applications is selected. The selected category may be displayed differently from the other categories in color size etc.

For instance with the category All set as a default category when the user accesses the application market card objects under the category All may be automatically displayed on the display as illustrated in .

The card objects may include the card object representing popular applications during a preset time period a card object representing top ranking paid applications the card object representing top ranking free applications and the card object representing new applications.

The preset time period may be for example one day one week one month one quarter a half year or one year. A different statistical time period may be set for each card object. For example the popularity ranking card object representing the download or installation rankings of applications may be based on weekly statistics and thus displayed on a weekly basis. For the top ranking free card object and the top ranking paid card object a statistical time period may be set to be infinite and thus these objects may display applications ranked in terms of total number of downloads or total number of installs.

The new application card object indicates new applications introduced during a preset time period. The new application card object may be based on a different statistical time period from other card objects.

At least one of the plurality of card objects may further include a menu object that allows the user to view more applications. The menu object may be represented as one of various graphic objects. For instance the menu object may take the form of an arrow. Upon receipt of an input corresponding to the menu object icons representing applications positioned in the arrowed direction may be displayed. The menu object may also take the form of a screen switch icon that upon selection switches from a current screen with displayed icons to another screen with only hidden icons or a view more icon that upon selection makes at least one hidden icon to show up in a card object corresponding to the view more icon and thus displays the hidden icon along with already displayed icons.

The menu object may be selected using a directional key input of the image display apparatus or a pointer corresponding to movement of the remote controller . Then icons representing applications included in a card object having the menu object are displayed. Other menu items such as Search My App and Exit may be displayed in a partial area of the display .

Referring to the user may move the pointer using the remote controller . When the pointer moves to the icon of an application the icon is focused on.

While an icon is focused on when the pointer moves to and is placed over the icon in the icon may be focused in other manners. For example a cursor is designed to move from one icon to another. Upon receipt of a right directional key input from the remote controller the cursor moves to the right icon. Upon receipt of a left directional key input from the remote controller the cursor moves to the left icon. In this case the cursor may take the form of a figure or symbol that flickers around an icon.

Thereafter information and about an application corresponding to the focused icon is displayed in a third area S .

The application information may include the focused icon brief information expressed as text or graphics and screen shots that are exemplary screens generated when the application is executed. The brief information may specify the name price category most recent update date user rating and user reviews of the application.

Because applications are classified into categories corresponding to tab menus re classified in each category and arranged in a plurality of card objects according to the re classifications of the applications the user can readily identify displayed applications. Further when an icon is focused on information about an application corresponding to the icon is displayed. Thus the user can easily acquire details of the application.

When an icon is focused on the icon is enlarged highlighted or outlined in the same color as the background of the third area . The focused icon is marked with slash lines in . For convenience it is assumed herein that slash lines drawn in the same direction represent the same color. Thus the focused icon is shown as surrounded by the same color as the background of third area in .

As the focused icon is enlarged or highlighted relative to other icons and the user is aware that the icon is focused on.

Further because the focused icon is surrounded by the same color as the background of the third area as illustrated in the focused icon is more conspicuous to the user.

However the background of the third area may be colored differently from the backgrounds of the card objects and . In consideration of the assumption that a color is represented as slash lines drawn in a specific direction in it is noted that the backgrounds of the card objects and are not colored at all or have a default color.

Unlike the card objects and may take the form of card type graphic objects having a predetermined background color in order to distinguish them from the other card objects and the other areas of the display and increase the visibility of icons displayed in the card objects and . In this case the background of the third area in which application information is displayed is colored differently from the card objects and to help the user notice the focused icon and the associated information.

In other words a new image and application information in the third area may be more easily noticed by coloring the background of the third area differently from the other areas.

Meanwhile at least one of the size or position of the first area in which the broadcast image is displayed may be changed. That is the first area may be moved from the position illustrated in and thus the broadcast image may be displayed in the moved first area . Also the first area may be enlarged so that the user can view the broadcast image more easily or contracted so that the user can concentrate on applications.

In the absence of any focused icon a predetermined image such as an advertisement may be displayed in the third area . Compared to in which the third area is empty the third area may be utilized to display an advertisement other information or a specific image in the case where application information need not be displayed.

In another embodiment of the method for operating an image display apparatus a broadcast image is displayed in a first area tab menus corresponding to categories into which a plurality of applications are classified are displayed in a second area. Upon selection of one of the tab menus icons representing applications that fall into a category corresponding to the selected tab menu are displayed in a plurality of card objects. Upon receipt of an object shift command for one of the card objects the card object for which the object shift command has been issued is exchanged with a card object positioned in a direction indicated by the object shift command.

In an exemplary embodiment upon receipt of an object shift command for one of the card objects the card object may be exchanged with a card object positioned at the direction indicated by the object shift command on the display .

Referring to if the object shift command indicates leftward movement of the card object the card object may be exchanged with the next card object positioned to the left of the card object on the display .

In another exemplary embodiment upon receipt of an object shift command for one of the card objects at least two card objects may be moved according to a direction indicated by the object shift command.

Referring to if the object shift command instructs leftward movement of the card object both the card object and the card object on the right side of the card object may be shifted to the left.

In this case a card object hidden on the right side of the display appears and the leftmost card object is hidden from the display .

Referring to first and second hidden areas and linked to displayed areas are illustrated. More specifically the hidden areas and may contain card objects that are not being displayed on the display . The image display apparatus may display a hidden card object on the display according to an object shift command received through the remote controller .

The shift command may be generated in various ways. For example the shift command may be generated as a result of a user rapidly flicking the remote controller while a cursor is displayed on the screen. Alternatively the shift command may be generated in response to a user pressing a button similar to a page up or page down button on the remote controller. The shift signal may also be generated as a result of a user rapidly flicking the remote controller while holding down a button to display a cursor on the screen.

For example upon receipt of a left shift command for at least one card object the image display apparatus displays the card object included in the second hidden area on the display . Accordingly to the user it appears that the card object shows up from the right of the displayed card object .

The leftmost card object may move to the first hidden area . That is the leftmost card object is placed in a hidden state.

The user may input a left or right shift command for at least one card object to the image display apparatus . The image display apparatus may display a card object included in the first or second hidden area or on the display according to the received shift command. Hence it appears to the user that card objects included in the first hidden area the display and the second hidden area are moving to the left or right.

While once an application is focused on information about the latest focused application continues to be displayed in the third area in the image display apparatus may return to the screen of or display a predetermined image such as an advertisement in the third area upon completion of the focusing.

In the illustrated cases of three card objects are displayed on the AppStore screen by way of example. The number of card objects displayed on a screen may be changed. For instance the card objects and are displayed on a screen in . In addition a plurality of card objects may be arranged in a different order.

While the above description has been given by way of an example in which a broadcast image is displayed on a part of the display the AppStore screen may be configured to be free of a broadcast image as illustrated in .

The method for operating an image display apparatus may further include displaying upon selection of an icon an application purchase menu window or displaying upon selection of an icon an application purchase menu window and displaying an application installation menu window.

Referring to the application purchase menu window may include at least one of a selected icon details of an application corresponding to the icon a screen shot that is an example of what might be created by executing the application Buy and Cancel menu items or an application review item.

The visibility of the application purchase menu window may be improved by reducing the brightness of the other areas.

In an exemplary embodiment upon selection of an icon an application installation menu window may be displayed for installation of an application corresponding to the selected icon. The application installation menu window may indicate the progress of download and installation of an application using a progress bar.

The visibility of the application installation menu window may be improved by reducing the brightness of the other areas.

The application purchase menu window and the application installation menu window may be displayed separately or incorporated into a single menu window. In the latter case when the user selects an application menus necessary to purchase and install an application may be displayed in one window. Accordingly the method for operating an image display apparatus may further include when an icon is selected displaying a menu window including menus for purchasing and installing an application corresponding to the selected icon.

In an exemplary embodiment when the application is installed the current screen is switched to a screen that displays the installed application fullscreen. An icon representing an application being installed an icon representing an application installed within a predetermined time period or an icon representing the most recently installed application may be distinguished from icons representing the other applications by changing the display state of the icon.

Referring to upon receipt of an application installation command the image display apparatus may display an application list screen listing installed applications instead of displaying menu windows or a notification of application installation progress on the AppStore screen. An application may flicker during installation compared to already installed applications on the application list screen .

Referring to a specific image for example an advertisement is displayed in a part of the display that is in the third area . The advertisement image may be received over a network or through a connected external device. If no signal of an advertisement is received any image may be displayed. For example the image may be a stored advertisement of the manufacturer of the image display apparatus .

Thus both a screen related to applications and a live broadcast image may be displayed on the display . Unless the user selects or focuses on a specific application a predetermined image such as an advertisement may be displayed in a part of the display .

When the user selects or focuses on an application a screen related to the application may be displayed. When the user focuses on one of the icons the image displayed in the third area may be replaced with information about an application corresponding to the focused icon.

While in the broadcast image is displayed in a part of the display an AppStore screen may be displayed free of any broadcast image as illustrated in .

All or part of the embodiments illustrated in may be selectively combined with the method for operating an image display apparatus as described with reference to and .

As is apparent from the above description a variety of applications are displayed along with a broadcast image. Therefore user convenience is increased. Further applications are classified according to predetermined criteria when they are displayed thereby enabling the user to more readily identify the applications.

The image display apparatus and the method for operating the same according to the foregoing exemplary embodiments are not restricted to the exemplary embodiments set forth herein.

The method for operating an image display apparatus according to the foregoing exemplary embodiments may be implemented as code that can be written on a computer readable recording medium and thus read by a processor. The computer readable recording medium may be any type of recording device in which data is stored in a computer readable manner.

Examples of the computer readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disc an optical data memory and a carrier wave e.g. data transmission over the Internet . The computer readable recording medium can be distributed over a plurality of computer systems connected to a network so that computer readable code is written thereto and executed therefrom in a decentralized manner. Programs code and code segments to realize the embodiments herein can be construed by one of ordinary skill in the art.

One or more embodiments described herein provide an image display apparatus and a method for operating the same which can increase user convenience and provide various user interfaces.

One or more embodiments described herein also provide an image display apparatus and a method for operating the same which enable downloading and execution of various applications.

In accordance one embodiment a method for operating an image display apparatus includes displaying a broadcast image displaying icons representing a plurality of applications in a plurality of card objects and displaying when one of the icons is focused on information about an application corresponding to the focused icon.

In accordance with another embodiment a method for operating an image display apparatus includes displaying a broadcast image in a first area displaying tab menus representing categories into which a plurality of applications are classified in a second area displaying upon selection of one of the tab menus icons representing applications that fall into a category corresponding to the selected tab menu in a plurality of card objects and displaying a predetermined image in a third area.

In accordance with another embodiment a multifunctional display device comprises a tuner configured to tune to a channel of a broadcast signal a network interface configured to receive data packets a display module a wireless input interface to receive signals from a remote controller a storage device to store data a processor to control the display module based on at least one of broadcast signal data packets or signals from the remote controller.

A first area of the display module displays a program received through a channel of the broadcast signal tuned by the tuner and a second area of the display module displays a plurality of card objects. Each card object has a plurality of downloadable applications which fall within at least one prescribed category. Based on a cursor location over a prescribed downloadable application among the plurality of downloadable application the prescribed downloadable application is highlighted in a prescribed color.

A third area of the display module displays additional information of the prescribed downloadable application. In addition the third area may be highlighted in with the same color as the prescribed color.

In addition an indicator is displayed to indicate that additional card objects not shown in the second area are available for display. The additional card objects are displayed based on a flicking signal to move the displayed card objects in a predetermined direction. The flicking signal is generated by the remote controller.

In addition the second area includes a plurality of regions corresponding to respective ones of the card objects each region including one or more icons corresponding to a plurality of downloadable applications and at least one indicator displayed to indicate that at least one of the regions includes additional icons not currently displayed. The additional icons are displayed when a signal is received to move additional icons into the region associated with the indicator and the signal is generated by the remote controller.

In addition a fourth area is displayed to include tabs identifying a respective number of categories a plurality of card objects corresponding to each category. Also a search area is displayed to allow a search to be conducted for content relating to the card objects and the additional information displayed in the third area includes a price for allowing a user to buy the downloadable application.

In addition an option is displayed to allow a user to buy the downloadable application. The first card object corresponds to a plurality of channels a second card object corresponds to network content a third card object corresponds to external device connections a fourth card object corresponds to phone features and a fifth card object corresponds to games.

In addition one or more screen shots are displayed corresponding to the highlighted downloadable application. The one or more screen shots are displayed in the third area with the additional information. Also a swipe signal is received from the remote controller the swipe signal causes a cursor on a screen to move and positions of the card objects displayed in the second area move based on movement of the cursor.

In accordance with another embodiment a multifunctional display device comprises a display module a storage device to store information a network interface to receive data packets a tuner to tune to a channel of a broadcast signal a wireless interface to receive signals from a remote controller a processor to control the display module based on at least one of the broadcast signal data packets or signals from the remote controller.

The first area displays content based on the broadcast signal or data packets a second area displays a plurality of card objects and one or more downloadable applications for each card object the downloadable applications displayed with respective ones of the card objects and a third area displays additional information corresponding to a selected one of the downloadable applications. Positions of the card objects are changed when a signal is received indicating that additional card objects are to be displayed in the second area the signal is received as a position signal from the remote controller and an indicator is displayed indicating that the additional card objects are available for display.

In addition displayed information corresponding to the selected downloadable application is changed based on the selection and the displayed information corresponding to the selected downloadable application is highlighted in a predetermined color and wherein at least the additional information in the third area is highlighted. The additional information in the third area is highlighted with the predetermined color when the selection is made.

In any of the aforementioned embodiments additional card objects may be displayed in response to a shift command received from the remote controller. The shift command may move the displayed card objects in a predetermined direction and one or more hidden card objects are displayed in response to movement of the displayed card objects in the predetermined direction.

The terms module and unit used to signify components are used herein to help the understanding of the components and thus they should not be considered as having specific meanings or roles. Accordingly the terms module and unit may be used interchangeably.

In accordance with one or more embodiments the image display apparatus is an intelligent image display apparatus equipped with a computer support function in addition to a broadcast reception function for example. Thus the image display apparatus may have user friendly interfaces such as a handwriting input device a touch screen or a pointing device. Further because the image display apparatus supports wired or wireless Internet it is capable of e mail transmission reception Web browsing banking gaming etc. by connecting to the Internet or a computer. To implement these functions the image display apparatus may operate based on a standard general purpose Operating System OS . Various applications can be freely added to or deleted from for example a general purpose OS kernel in the image display apparatus according to the present invention. Therefore the image display apparatus may perform a number of user friendly functions. The image display apparatus may be a network TV a Hybrid broadcast broadband TV HbbTV a smart TV etc. for example. The image display apparatus is applicable to a smart phone as needed.

Any reference in this specification to one embodiment an embodiment example embodiment etc. means that a particular feature structure or characteristic described in connection with the embodiment is included in at least one embodiment of the invention. The appearances of such phrases in various places in the specification are not necessarily all referring to the same embodiment. Further when a particular feature structure or characteristic is described in connection with any embodiment it is submitted that it is within the purview of one skilled in the art to effect such feature structure or characteristic in connection with other ones of the embodiments. The features of one embodiment may be combined with the features of any other embodiment.

Although embodiments have been described with reference to a number of illustrative embodiments thereof it should be understood that numerous other modifications and embodiments can be devised by those skilled in the art that will fall within the spirit and scope of the principles of this disclosure. More particularly various variations and modifications are possible in the component parts and or arrangements of the subject combination arrangement within the scope of the disclosure the drawings and the appended claims. In addition to variations and modifications in the component parts and or arrangements alternative uses will also be apparent to those skilled in the art.

