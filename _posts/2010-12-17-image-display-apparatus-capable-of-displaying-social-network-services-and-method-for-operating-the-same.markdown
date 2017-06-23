---

title: Image display apparatus capable of displaying social network services and method for operating the same
abstract: A method for operating an image display apparatus is discussed. The method according to an embodiment includes storing a Web site list including a plurality of Web sites and login information for the Web sites, connecting to servers of at least two of the stored Web sites using the stored login information, and displaying a list of the connected Web sites or Web pages of the connected Web sites on at least a part of a display.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09363470&OS=09363470&RS=09363470
owner: LG ELECTRONICS INC.
number: 09363470
owner_city: Seoul
owner_country: KR
publication_date: 20101217
---
This application claims the benefit of Korean Patent Application No. 10 2010 0057640 filed on Jun. 17 2010 in the Korean Intellectual Property Office and the benefit of U.S. Provisional Application No. 61 355 962 filed on Jun. 17 2010 in the USPTO. The entire contents of all these applications are incorporated herein by reference.

The present invention relates to an image display apparatus and a method for operating the same and more particularly to an image display apparatus and a method for operating the same which increase user convenience.

An image display apparatus has a function of displaying images to a user. The image display apparatus can display a broadcast program selected by the user on a display from among broadcast programs transmitted from broadcasting stations. The recent trend in broadcasting is a worldwide shift from analog broadcasting to digital broadcasting.

As it transmits digital audio and video signals digital broadcasting offers many advantages over analog broadcasting such as robustness against noise less data loss ease of error correction and the ability to provide high definition clear images. Digital broadcasting also allows interactive viewer services compared to analog broadcasting.

Therefore the present invention has been made in view of the above problems and it is an object of the present invention to provide an image display apparatus and a method for operating the same which can increase user convenience.

It is another object of the present invention to provide an image display apparatus and a method for operating the same which can display a plurality of social network services.

It is another object of the present invention to provide an image display apparatus and a method for operating the same which can simply access a plurality of Web sites.

It is a further object of the present invention to provide an image display apparatus and a method for operating the same which can provide various user interfaces.

In accordance with an aspect of the present invention the above and other objects can be accomplished by the provision of a method for operating an image display apparatus including storing a Web site list including a plurality of Web sites and login information for the Web sites connecting to servers of at least two of the stored Web sites using the stored login information and displaying a list of the connected Web sites or Web pages of the connected Web sites on at least a part of a display.

In accordance with another aspect of the present invention there is provided a method for operating an image display apparatus including displaying upon receipt of an application menu display input an application menu on at least a part of a display selecting upon receipt of a Social Network Service SNS selection input an SNS application in the application menu connecting to servers of a plurality of SNSs using pre stored login information for the SNSs and displaying objects representing users or electronic devices subscribed to the plurality of SNSs on at least a part of the display.

In accordance with another aspect of the present invention there is provided a method for operating an image display apparatus including connecting to servers of a plurality of SNSs and displaying objects representing users or electronic devices subscribed to the plurality of SNSs on at least a part of the display. Each of the objects includes an icon representing an SNS subscribed to by a user or electronic device represented by the object.

In accordance with a further aspect of the present invention there is provided an image display apparatus including a display for displaying an application menu on at least a part of a display a memory for storing login information for a plurality of SNSs a network interface for transmitting or receiving data to or from a network and a controller for selecting upon receipt of an SNS application selection input an SNS application in the application menu controlling connection to servers of a plurality of SNSs through the network interface and controlling display of objects representing users or electronic devices subscribed to the plurality of SNSs on at least a part of the display.

In accordance with a further aspect of the present invention there is provided a method computer program product and apparatus for operating an image display apparatus. The method includes simultaneously displaying on a display of the image display apparatus a broadcast image and images corresponding to Web sites connected to the image display apparatus. The connected Web sites are at least a subset of a list of Web sites stored within the image display device. The connected Web sites are connected to the image display apparatus based on corresponding Web site login information stored within the image display device. The Web site login information includes a corresponding Web site user identification ID and Web site password.

Embodiments of the present invention will be described below with reference to the attached drawings.

The terms module and unit used to signify components are used herein to help the understanding of the components and thus they should not be considered as having specific meanings or roles. Accordingly the terms module and unit may be used interchangeably.

An image display apparatus as set forth herein is an intelligent image display apparatus equipped with a computer support function in addition to a broadcast reception function for example. Thus the image display apparatus may have user friendly interfaces such as a handwriting input device a touch screen or a pointing device. Further because the image display apparatus supports wired or wireless Internet it is capable of e mail transmission reception Web browsing banking gaming etc. by connecting to the Internet or a computer. To implement these functions the image display apparatus may operate based on a standard general purpose Operating System OS .

Various applications can be freely added to or deleted from for example a general purpose OS kernel in the image display apparatus according to the present invention. Therefore the image display apparatus may perform a number of user friendly functions. The image display apparatus may be a network TV a Hybrid broadcast broadband TV HbbTV a smart TV etc. for example. The image display apparatus is applicable to a smart phone as needed.

Embodiments of the present invention will be described in detail with reference to the attached drawings but it should be understood that they are merely illustrative of the present invention and should not be interpreted as limiting the scope of the present invention.

In addition although the terms used in the present invention are selected from generally known and used terms some of the terms mentioned in the description of the present invention the detailed meanings of which are described in relevant parts of the description herein have been selected by the applicant at his or her discretion. Furthermore the present invention must be understood not simply by the actual terms used but by the meanings of each term lying within.

Referring to the broadcasting system may include a Content Provider CP a Service Provider SP a Network Provider NP and a Home Network End Device HNED . The HNED corresponds to for example a client which is an image display apparatus according to an embodiment of the present invention. As stated before the image display apparatus may be a network TV a smart TV an Internet Protocol TV IPTV etc.

The CP creates and provides content. The CP may be for example a terrestrial broadcaster a cable System Operator SO or Multiple System Operator MSO a satellite broadcaster or an Internet broadcaster as illustrated in .

Besides broadcast content the CP may provide various applications which will be described later in detail.

The SP may provide content received from the CP in a service package. For instance the SP may package first terrestrial broadcasting second terrestrial broadcasting cable broadcasting satellite broadcasting Internet broadcasting and applications and provide the package to users.

The SP may unicast or multicast a service to the client . Unicast is a form of transmission in which information is sent from only one transmitter to only one receiver. In other words unicast transmission is point to point involving two nodes only. In an example of unicast transmission upon receipt of a request for data from a receiver a server transmits the data to only one receiver. Multicast is a type of transmission or communication in which a transmitter transmits data to a group of receivers. For example a server may transmit data to a plurality of pre registered receivers at one time. For multicast registration the Internet Group Management Protocol IGMP may be used.

The NP may provide a network over which a service is provided to the client . The client may construct a home network and receive a service over the home network.

Content transmitted in the above described broadcasting system may be protected through conditional access or content protection. CableCard and Downloadable Conditional Access System DCAS are examples of conditional access or content protection.

The client may also transmit content over a network. In this case the client serves as a CP and thus the CP may receive content from the client . Therefore an interactive content service or data service can be provided.

Referring to the image display apparatus according to another embodiment of the present invention is connected to a broadcast network and the Internet. The image display apparatus is for example a network TV a smart TV an HbbTV etc.

The image display apparatus includes for example a broadcast interface a section filter an Application Information Table AIT filter an application data processor a broadcast data processor a media player an IP processor an Internet interface and a runtime module .

The image display apparatus receives AIT data real time broadcast content application data and stream events through the broadcast interface . The real time broadcast content may be referred to as linear Audio Video A V content.

The section filter performs section filtering on the four types of data received through the broadcast interface and outputs the AIT data to the AIT filter the linear A V content to the broadcast data processor and the stream events and application data to the application data processor .

Meanwhile the image display apparatus receives non linear A V content and application data through the Internet interface . The non linear A V content may be for example a Content On Demand CoD application.

The non linear A V content and the application data are transmitted to the media player and the runtime module respectively.

The runtime module includes for example an application manager and a browser as illustrated in . The application manager controls the life cycle of an interactive application using the AIT data for example. The browser displays and processes the interactive application.

Referring to an SP performs an SP Discovery operation S and the image display apparatus transmits a Service Provider Attachment Request signal to the SP S . Upon completion of attachment to the SP the image display apparatus receives provisioning information from the SP S . Further the image display apparatus receives Master System Information SI Tables Virtual Channel Map Tables Virtual Channel Description Tables and Source Tables from the SP S to S .

More specifically SP Discovery is a process by which SPs that provide IPTV services search for Service Discovery SD servers having information about the offerings of the SPs.

In order to receive information about the SD servers an SD server address list can be detected for example using three methods specifically use of an address preset in the image display apparatus or an address manually set by a user Dynamic Host Configuration Protocol DHCP based SP Discovery and Domain Name System Service DNS SRV based SP Discovery. The image display apparatus accesses a specific SD server using the SD server address list obtained through one of the above three methods and receives a SP Discovery record from the specific SD server. The Service Provider Discovery record includes information needed to perform Service Discovery on an SP basis. The image display apparatus then starts a Service Discovery operation using the SP Discovery record. These operations can be performed in a push mode or a pull mode.

The image display apparatus accesses an SP attachment server specified by an SP attachment locator included in the SP Discovery record and performs a registration procedure or a service attachment procedure .

Further after accessing an authentication service server of an SP specified by an SP authentication locator and performing an authentication procedure the image display apparatus may perform a service authentication procedure.

After service attachment is successfully performed a server may transmit data in the form of a provision information table to the image display apparatus.

During service attachment the image display apparatus may include an Identifier ID and location information thereof in data and transmit the data to the service attachment server. Thus the service attachment server may specify a service that the image display apparatus has subscribed to based on the ID and location information. In addition the service attachment server provides in the form of a provisioning information table address information from which the image display apparatus can obtain Service Information SI . The address information corresponds to access information about a Master SI Table. This method facilitates provision of a customized service to each subscriber.

The SI is divided into a Master SI Table record for managing access information and version information about a Virtual Channel Map a Virtual Channel Map Table for providing a list of services in the form of a package a Virtual Channel Description Table that contains details of each channel and a Source Table that contains access information about actual services.

Referring to a Master SI Table contains information about the location and version of each Virtual Channel MAP.

Each Virtual Channel MAP is identified by its Virtual Channel MAP identifier. VirtualChannelMAPVersion specifies the version number of the Virtual Channel MAP. If any of the tables connected to the Master SI Table in the arrowed direction is modified the versions of the modified table and overlying tables thereof up to the Master SI Table are incremented. Accordingly a change in any of the SI tables can be readily identified by monitoring the Master SI Table.

For example when the Source Table is changed the version of the Source Table is incremented and the version of the Virtual Channel Description Table that references the Source Table is also incremented. In conclusion a change in any lower table leads to a change in its higher tables and eventually a change in the Master SI Table.

One Master SI Table may exist for each SP. However in the case where service configurations differ for regions or subscribers or subscriber groups an SP may have a plurality of Master SI Tables in order to provide a customized service on a region subscriber or subscriber group basis. Thus it is possible to provide a customized service to a subscriber according to a region in which the subscriber is located and subscriber information regarding the subscriber.

A Virtual Channel Map Table may contain a list of one or more virtual channels. A Virtual Channel Map includes not details of the channels but information about the locations of the details of the channels. In the Virtual Channel Map Table VirtualChannelDescriptionLocation specifies the location of a Virtual Channel Description Table that provides virtual channel descriptions.

The Virtual Channel Description Table contains the details of the virtual channels. The Virtual Channel Description Table can be accessed using VirtualChannelDescriptionLocation of the Virtual Channel Map Table.

A Source Table provides information necessary to access actual services e.g. IP addresses ports AV Codecs transmission protocols etc. on a service basis.

The above described Master SI Table the Virtual Channel Map Table the Virtual Channel Description Table and the Source Table are delivered in four logically separate flows in a push mode or a pull mode. For version management the Master SI Table may be multicast and thus a version change can be monitored by receiving a multicast stream of the Master SI Table.

Referring to an image display apparatus includes a network interface a Transmission Control Protocol Internet Protocol TCP IP manager a service delivery manager a Demultiplexer DEMUX a Program Specific Information PSI Program and System Information Protocol PSIP and or SI decoder a display A V and On Screen Display OSD module a service control manager a service discovery manager a metadata manager an SI metadata DataBase DB a User Interface UI manager and a service manager .

The network interface transmits packets to and receives packets from a network. Specifically the network interface receives services and content from an SP over the network.

The TCP IP manager is involved in packet reception and transmission of the image display apparatus that is packet delivery from a source to a destination. The TCP IP manager classifies received packets according to appropriate protocols and outputs the classified packets to the service delivery manager the service discovery manager the service control manager and the metadata manager .

The service delivery manager controls received service data. For example when controlling real time streaming data the service delivery manager may use the Real time Transport Protocol Real time Transport Control Protocol RTP RTCP . If real time streaming data is transmitted over RTP RTCP the service delivery manager parses the received real time streaming data using RTP and outputs the parsed real time streaming data to the DEMUX or stores the parsed real time streaming data in the SI metadata DB under the control of the service manager . In addition the service delivery manager feeds back network reception information to a server that provides the real time streaming data service using RTCP.

The DEMUX demultiplexes a received packet into audio data video data and PSI data and outputs the audio data video data and PSI data to the audio decoder the video decoder and the PSI PSIP and or SI decoder respectively.

The PSI PSIP and or SI decoder decodes SI such as PSI. More specifically the PSI PSIP and or SI decoder decodes PSI sections PSIP sections or SI sections received from the DEMUX .

The PSI PSIP and or SI decoder constructs an SI DB by decoding the received sections and stores the SI DB in the SI metadata DB .

The audio decoder and the video decoder decode the audio data and the video data received from the DEMUX and output the decoded audio and video data to a user through the display A V and OSD module .

The UI manager and the service manager manage the overall state of the image display apparatus provide UIs and manage other managers.

The UI manager provides a Graphical User Interface GUI in the form of an OSD and performs a reception operation corresponding to a key input received from the user. For example upon receipt of a key input signal regarding channel selection from the user the UI manager transmits the key input signal to the service manager .

The service manager controls managers associated with services such as the service delivery manager the service discovery manager the service control manager and the metadata manager .

The service manager also makes a channel map and selects a channel using the channel map according to the key input signal received from the UI manager . The service manager sets the audio video Packet ID PID of the selected channel based on SI about the channel received from the PSI PSIP and or SI decoder .

The service discovery manager provides information necessary to select an SP that provides a service. Upon receipt of a channel selection signal from the service manager the service discovery manager detects a service based on the channel selection signal.

The service control manager takes charge of selecting and control services. For example if a user selects live broadcasting like a conventional broadcasting service the service control manager selects and controls the service using Internet Group Management Protocol IGMP or Real Time Streaming Protocol RTSP . If the user selects Video on Demand VoD the service control manager selects and controls the service. RTSP supports trick mode for real time streaming. Further the service control manager may initialize and manage a session through an IP Multimedia Control IMC gateway using IP Multimedia Subsystem IMS and Session Initiation Protocol SIP . The protocols are given by way of example and thus other protocols are also applicable according to other embodiments.

The metadata manager manages metadata related to services and stores the metadata in the SI metadata DB .

The SI metadata DB stores the SI decoded by the PSI PSIP and or SI decoder the metadata managed by the metadata manager and the information required to select an SP received from the service discovery manager . The SI metadata DB may store setup data for the system.

Referring to an image display apparatus according to another embodiment of the present invention includes a broadcasting receiver an external device interface a memory a user input interface a controller a display an audio output unit a power supply and a camera module. The broadcasting receiver may include a tuner a demodulator and a network interface . As needed the broadcasting receiver may be configured so as to include only the tuner and the demodulator or only the network interface .

The tuner selects a Radio Frequency RF broadcast signal corresponding to a channel selected by a user from among a plurality of RF broadcast signals received through an antenna and downconverts the selected RF broadcast signal into a digital Intermediate Frequency IF signal or an analog baseband A V signal.

More specifically if the selected RF broadcast signal is a digital broadcast signal the tuner downconverts the selected RF broadcast signal into a digital IF signal DIF. On the other hand if the selected RF broadcast signal is an analog broadcast signal the tuner downconverts the selected RF broadcast signal into an analog baseband A V signal CVBS SIF. That is the tuner may be a hybrid tuner capable of processing not only digital broadcast signals but also analog broadcast signals. The analog baseband A V signal CVBS SIF may be directly input to the controller .

The tuner may be capable of receiving RF broadcast signals from an Advanced Television Systems Committee ATSC single carrier system or from a Digital Video Broadcasting DVB multi carrier system.

The tuner may sequentially select a number of RF broadcast signals corresponding to all broadcast channels previously stored in the image display apparatus by a channel add function from a plurality of RF signals received through the antenna and may downconvert the selected RF broadcast signals into IF signals or baseband A V signals.

The demodulator receives the digital IF signal DIF from the tuner and demodulates the digital IF signal DIF.

For example if the digital IF signal DIF is an ATSC signal the demodulator may perform 8 Vestigal SideBand VSB demodulation on the digital IF signal DIF. The demodulator may also perform channel decoding. For channel decoding the demodulator may include a Trellis decoder a de interleaver and a Reed Solomon decoder so as to perform Trellis decoding de interleaving and Reed Solomon decoding.

For example if the digital IF signal DIF is a DVB signal the demodulator performs Coded Orthogonal Frequency Division Multiple Access COFDMA demodulation upon the digital IF signal DIF. The demodulator may also perform channel decoding. For channel decoding the demodulator may include a convolution decoder a de interleaver and a Reed Solomon decoder so as to perform convolution decoding de interleaving and Reed Solomon decoding.

The demodulator may perform demodulation and channel decoding on the digital IF signal DIF thereby obtaining a stream signal TS. The stream signal TS may be a signal in which a video signal an audio signal and a data signal are multiplexed. For example the stream signal TS may be an MPEG 2 TS in which an MPEG 2 video signal and a Dolby AC 3 audio signal are multiplexed. An MPEG 2 TS may include a 4 byte header and a 184 byte payload.

In order to properly handle not only ATSC signals but also DVB signals the demodulator may include an ATSC demodulator and a DVB demodulator.

The stream signal TS may be input to the controller and thus subjected to demultiplexing and A V signal processing. The processed video and audio signals are output to the display and the audio output unit respectively.

The external device interface may serve as an interface between an external device and the image display apparatus . For interfacing the external device interface may include an A V Input Output I O unit and or a wireless communication module.

The external device interface may be connected to an external device such as a Digital Versatile Disk DVD player a Blu ray player a game console a camera a camcorder or a computer e.g. a laptop computer wirelessly or by wire. Then the external device interface externally receives video audio and or data signals from the external device and transmits the received input signals to the controller . In addition the external device interface may output video audio and data signals processed by the controller to the external device. In order to receive or transmit audio video and data signals from or to the external device the external device interface includes the A V I O unit and or the wireless communication module.

The A V I O unit of the external device interface may include a Universal Serial Bus USB port a Composite Video Banking Sync CVBS port a Component port a Super video S video analog port a Digital Visual Interface DVI port a High Definition Multimedia Interface HDMI port a Red Green Blue RGB port and a D sub port.

The wireless communication module of the external device interface may perform short range wireless communication with other electronic devices. For short range wireless communication the wireless communication module may use Bluetooth Radio Frequency IDentification RFID Infrared Data Association IrDA Ultra WideBand UWB ZigBee and Digital Living Network Alliance DLNA .

The external device interface may be connected to various set top boxes through at least one of the above described ports and may thus receive data from or transmit data to the various set top boxes.

The external device interface may receive applications or an application list from an adjacent external device and provide the applications or the application list to the controller or the memory .

The network interface serves as an interface between the image display apparatus and a wired wireless network such as the Internet. The network interface may include an Ethernet port for connection to a wired network. The wireless communication module of the external signal I O unit may wirelessly access the Internet. For connection to wireless networks the network interface may use Wireless Local Area Network WLAN i.e. Wi Fi Wireless Broadband WiBro World Interoperability for Microwave Access WiMax and High Speed Downlink Packet Access HSDPA .

The network interface may transmit data to or receive data from another user or electronic device over a connected network or another network linked to the connected network. Especially the network interface may transmit data stored in the image display apparatus to a user or electronic device selected from among users or electronic devices pre registered with the image display apparatus .

The network interface may access a specific Web page over a connected network or another network linked to the connected network. That is the network interface may access a specific Web page over a network and transmit or receive data to or from a server. Additionally the network interface may receive content or data from a CP or an NP. Specifically the network interface may receive content such as movies advertisements games VoD files and broadcast signals and information related to the content from a CP or an NP. Also the network interface may receive update information about firmware and update files of the firmware from the NP. The network interface may transmit data over the Internet or to the CP or the NP.

The network interface may selectively receive a desired application among open applications over a network.

In an embodiment of the present invention when a game application is executed in the image display apparatus the network interface may transmit data to or receive data from a user terminal connected to the image display apparatus through a network. In addition the network interface may transmit specific data to or receive specific data from a server that records game scores.

The memory may store various programs necessary for the controller to process and control signals and may also store processed video audio and data signals.

The memory may temporarily store a video audio and or data signal received from the external device interface or the network interface . The memory may store information about broadcast channels by the channel add function.

The memory may store applications or a list of applications received from the external device interface or the network interface .

In an embodiment of the present invention when the image display apparatus executes a game application the memory may store user specific information and game play information about a user terminal used as a game controller.

The memory may include for example at least one of a flash memory type storage medium a hard disk type storage medium a multimedia card micro type storage medium a card type memory e.g. a Secure Digital SD or eXtreme Digital XD memory a Random Access Memory RAM or a Read Only Memory ROM such as an Electrically Erasable and Programmable Read Only Memory. The image display apparatus may reproduce content stored in the memory e.g. video files still image files music files text files and application files to the user.

While the memory is shown in as configured separately from the controller to which the present invention is not limited the memory may be incorporated into the controller for example.

The user input interface transmits a signal received from the user to the controller or transmits a signal received from the controller to the user.

For example the user input interface may receive various user input signals such as a power on off signal a channel selection signal and a screen setting signal from a remote controller or may transmit a signal received from the controller to the remote controller according to various communication schemes for example RF communication and IR communication.

For example the user input interface may provide the controller with user input signals or control signals received from local keys such as inputs of a power key a channel key and a volume key and setting values.

Also the user input interface may transmit a control signal received from a sensor unit for sensing a user gesture to the controller or transmit a signal received from the controller to the sensor unit. The sensor unit may include a touch sensor a voice sensor a position sensor a motion sensor etc.

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

Upon receipt of a go to home input the controller may control display of the home screen on the display in an embodiment of the present invention.

The home screen may include a plurality of card objects classified according to content sources. The card objects may include at least one of a card object representing a thumbnail list of broadcast channels a card object representing a broadcast program guide a card object representing a program reservation list or a program recording list or a card object representing a media list of a device connected to the image display apparatus . The card objects may further include at least one of a card object representing a list of connected external devices or a card object representing a call associated list.

The home screen may further include an application menu with at least one application that can be executed.

Upon receipt of a card object move input the controller may control movement of a card object corresponding to the card object move input on the display or if the card object is not displayed on the display the controller may control display of the card object on the display .

When a card object is selected from among the card objects on the home screen the controller may control display of an image corresponding to the selected card object on the display .

The controller may control display of an input broadcast image and an object representing information about the broadcast image in a card object representing broadcast images. The broadcast image may be fixed in size through lock setting.

The controller may control display of a set up object for at least one of image setting audio setting screen setting reservation setting setting of a pointer of the remote controller or network setting on the home screen.

The controller may control display of a log in object a help object or an exit object on a part of the home screen.

The controller may control display of an object representing the total number of available card objects or the number of card objects displayed on the display among all card objects on a part of the home screen.

If one of the card objects displayed on the display is selected the controller may fullscreen the selected card object to cover the entirety of the display .

Upon receipt of an incoming call at a connected external device or the image display apparatus the controller may control focusing on or shift of a call related card object among the plurality of card objects.

If an application view menu item is selected the controller may control display of applications or a list of applications that are available in the image display apparatus or downloadable from an external network.

The controller may control installation and execution of an application downloaded from the external network along with various UIs. Also the controller may control display of an image related to the executed application on the display upon user selection.

In an embodiment of the present invention when the image display apparatus provides a game application the controller may control assignment of player IDs to specific user terminals creation of game play information by executing the game application transmission of the game play information to the user terminals through the network interface and reception of the game play information at the user terminals.

The controller may control detection of user terminals connected to the image display apparatus over a network through the network interface display of a list of the detected user terminals on the display and reception of a selection signal indicating a user terminal selected for use as a user controller from among the listed user terminals through the user input interface .

The controller may control output of a game play screen of the game application inclusive of player information about each user terminal and game play information through the display .

The controller may determine the specific signal received from a user terminal through the network interface as game play information and thus control the game play information to be reflected in the game application in progress.

The controller may control transmission of the game play information about the game application to a specific server connected to the image display apparatus over a network through the network interface .

As another embodiment upon receipt of information about a change in the game play information from the server through the network interface the controller may control output of a notification message in a predetermined area of the display .

The image display apparatus may further include a channel browsing processor for generating thumbnail images corresponding to channel signals or external input signals.

The channel browsing processor may extract some of the video frames of each of stream signals TS received from the demodulator or stream signals received from the external device interface and display the extracted video frames on the display as thumbnail images. The thumbnail images may be directly output to the controller or may be output after being encoded. Also it is possible to encode the thumbnail images into a stream and output the stream to the controller . The controller may display a thumbnail list including a plurality of received thumbnail images on the display . The thumbnail images may be updated sequentially or simultaneously in the thumbnail list. Therefore the user can readily identify the content of broadcast programs received through a plurality of channels.

The display may convert a processed video signal a processed data signal and an OSD signal received from the controller or a video signal and a data signal received from the external device interface into RGB signals thereby generating driving signals.

The display may be various types of displays such as a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED display a flexible display and a 3D display.

The display may also be a touch screen that can be used not only as an output device but also as an input device.

The audio output unit may receive a processed audio signal e.g. a stereo signal a 3.1 channel signal or a 5.1 channel signal from the controller and output the received audio signal as sound. The audio output unit may employ various speaker configurations.

To sense a user gesture the image display apparatus may further include the sensor unit that has at least one of a touch sensor a voice sensor a position sensor and a motion sensor as stated before. A signal sensed by the sensor unit may be output to the controller through the user input interface .

The image display apparatus may further include the camera unit for capturing images of a user. Image information captured by the camera unit may be input to the controller .

The controller may sense a user gesture from an image captured by the camera unit or a signal sensed by the sensor unit or by combining the captured image and the sensed signal.

The power supply supplies power to the image display apparatus . Particularly the power supply may supply power to the controller the display and the audio output unit which may be implemented as a System On Chip SOC .

For supplying power the power supply may include a converter for converting Alternating Current AC into Direct Current DC . If the display is configured with for example a liquid crystal panel having a plurality of backlight lamps the power supply may further include an inverter capable of performing Pulse Width Modulation PWM for luminance change or dimming driving.

The remote controller transmits a user input to the user input interface . For transmission of user input the remote controller may use various communication techniques such as Bluetooth RF communication IR communication UWB and ZigBee.

In addition the remote controller may receive a video signal an audio signal or a data signal from the user input interface and output the received signals visually audibly or as vibrations.

The above described image display apparatus may be a fixed digital broadcast receiver capable of receiving at least one of ATSC 8 VSB broadcast programs DVB T COFDM broadcast programs and ISDB T BST OFDM broadcast programs.

The block diagram of the image display apparatus illustrated in is purely exemplary. Depending upon the specifications of the image display apparatus in actual implementation the components of the image display apparatus may be combined or omitted or new components may be added. That is two or more components are incorporated into one component or one component may be configured as separate components as needed. In addition the function of each block is described for the purpose of describing the embodiment of the present invention and thus specific operations or devices should not be construed as limiting the scope and spirit of the present invention.

Unlike the configuration illustrated in the image display apparatus may be configured so as to receive and playback video content through the network interface or the external device interface without the tuner and the demodulator .

The image display apparatus is an example of image signal processing apparatus that processes a stored image or an input image. Other examples of the image signal processing apparatus include a set top box without the display and the audio output unit a DVD player a Blu ray player a game console and a computer. The set top box will be described later with reference to .

The set top box may include a network interface a memory a signal processor a user input interface and an external device interface .

The network interface serves as an interface between the set top box and a wired wireless network such as the Internet. The network interface may transmit data to or receive data from another user or another electronic device over a connected network or over another network linked to the connected network.

The memory may store programs necessary for the signal processor to process and control signals and temporarily store a video audio and or data signal received from the external device interface or the network interface . The memory may also store platforms illustrated in as described later.

The signal processor processes an input signal. For example the signal processor may demultiplex or decode an input video or audio signal. For signal processing the signal processor may include a video decoder or an audio decoder. The processed video or audio signal may be transmitted to the display device through the external device interface .

The user input interface transmits a signal received from the user to the signal processor or a signal received from the signal processor to the user. For example the user input interface may receive various control signals such as a power on off signal an operation input signal and a setting input signal through a local key or the remote controller and output the control signals to the signal processor .

The external device interface serves as an interface between the set top box and an external device that is connected wirelessly or by wire particularly the display device for signal transmission or reception. The external device interface may also interface with an external device such as a game console a camera a camcorder and a computer e.g. a laptop computer for data transmission or reception.

The set top box may further include a media input unit for media playback. The media input unit may be a Blu ray input unit for example. That is the set top box may include a Blu ray player. After signal processing such as demultiplexing or decoding in the signal processor a media signal from a Blu ray disk may be transmitted to the display device through the external device interface so as to be displayed on the display device .

The display device may include a tuner an external device interface a demodulator a memory a controller a user input interface a display and an audio output unit .

The tuner the demodulator the memory the controller the user input interface the display and the audio output unit are identical respectively to the tuner the demodulator the memory the controller the user input interface the display and the audio output unit illustrated in and thus a description thereof is not provided herein.

The external device interface serves as an interface between the display device and a wireless or wired external device particularly the set top box for data transmission or reception.

Hence a video signal or an audio signal received through the set top box is output through the display or the audio output unit through the controller .

Referring to the configuration of the set top box and the display device illustrated in is similar to that of the set top box and the display device illustrated in except that the tuner and the demodulator reside in the set top box not in the display device . Thus the following description is given focusing on such difference.

The signal processor may process a broadcast signal received through the tuner and the demodulator . The user input interface may receive a channel selection input a channel store input etc.

Referring to the image display apparatus may communicate with a broadcasting station a network server or an external device .

The image display apparatus may receive a broadcast signal including a video signal from the broadcasting station . The image display apparatus may process the audio and video signals of the broadcast signal or the data signal of the broadcast signal suitably for transmission from the image display apparatus . The image display apparatus may output images or sound based on the processed video or audio signal.

Meanwhile the image display apparatus may communicate with the network server . The network server is capable of transmitting signals to and receiving signals from the image display apparatus over a network. For example the network server may be a portable terminal that can be connected to the image display apparatus through a wired or wireless base station. In addition the network server may provide content to the image display apparatus over the Internet. A CP may provide content to the image display apparatus through the network server .

The image display apparatus may communicate with the external device . The external device can transmit and receive signals directly to and from the image display apparatus wirelessly or by wire. For instance the external device may be a media memory device or a player. That is the external device may be any of a camera a DVD player a Blu ray player a PC etc.

The broadcasting station the network server or the external device may transmit a signal including a video signal to the image display apparatus . The image display apparatus may display an image based on the video signal included in the received signal. Also the image display apparatus may transmit a signal received from the broadcasting station or the network server to the external device and may transmit a signal received from the external device to the broadcasting station or the network server . That is the image display apparatus may transmit content included in signals received from the broadcasting station the network server and the external device as well as playback the content immediately.

Referring to the controller may include a DEMUX a video processor an OSD generator a mixer a Frame Rate Converter FRC and a formatter according to an embodiment of the present invention. The controller may further include an audio processor and a data processor.

The DEMUX demultiplexes an input stream. For example the DEMUX may demultiplex an MPEG 2 TS into a video signal an audio signal and a data signal. The input stream signal may be received from the tuner the demodulator or the external device interface .

The video processor may process the demultiplexed video signal. For video signal processing the video processor may include a video decoder and a scaler .

The video decoder decodes the demultiplexed video signal and the scaler scales the resolution of the decoded video signal so that the video signal can be displayed on the display .

If the demultiplexed video signal is for example an MPEC 2 encoded video signal the video signal may be decoded by an MPEC 2 decoder.

On the other hand if the video signal is an H.264 encoded DMB or DVB handheld DVB H signal the video signal may be decoded by an H.264 decoder.

The OSD generator generates an OSD signal autonomously or according to user input. For example the OSD generator may generate signals by which a variety of information is displayed as images or text on the display according to control signals received from the user input interface . The OSD signal may include various data such as a UI a variety of menu screens widgets icons etc.

For example the OSD generator may generate a signal by which subtitles are displayed for a broadcast image or Electronic Program Guide EPG based broadcasting information.

The mixer may mix the decoded video signal with the OSD signal and output the mixed signal to the formatter . As the decoded broadcast video signal or the external input signal is mixed with the OSD signal an OSD may be overlaid on the broadcast image or the external input image.

The FRC may change the frame rate of an input image. For example a frame rate of 60 Hz is converted into a frame rate of 120 or 240 Hz. When the frame rate is to be changed from 60 Hz to 120 Hz a first frame is inserted between the first frame and a second frame or a predicted third frame is inserted between the first and second frames. If the frame rate is to be changed from 60 Hz to 240 Hz three identical frames or three predicted frames are inserted between the first and second frames. It is also possible to maintain the frame rate of the input image without frame rate conversion.

The formatter changes the format of the signal received from the FRC to be suitable for the display . For example the formatter may convert a received signal into an RGB data signal. The RGB signal may be output in the form of a Low Voltage Differential Signal LVDS or mini LVDS.

The audio processor of the controller may process the demultiplexed audio signal. For audio signal processing the audio processor may have a plurality of decoders.

If the demultiplexed audio signal is a coded audio signal the audio processor of the controller may decode the audio signal. For example the demultiplexed audio signal may be decoded by an MPEG 2 decoder an MPEG 4 decoder an Advanced Audio Coding AAC decoder or an AC 3 decoder.

The data processor of the controller may process the data signal obtained by demultiplexing the input stream signal. For example if the data signal is an encoded signal such as an EPG which includes broadcasting information specifying the start time end time etc. of scheduled broadcast TV or radio programs the controller may decode the data signal. Examples of an EPG include ATSC Program and System Information Protocol PSIP information and DVB Service Information SI .

ATSC PSIP information or DVB SI may be included in the header of a TS i.e. a 4 byte header of an MPEG 2 TS.

The block diagram of the controller illustrated in is an embodiment of the present invention. Depending upon the specifications of the controller the components of the controller may be combined or omitted. Or new components are added to the controller .

A platform for either of the image display apparatuses may have OS based software to implement the above described various operations according to an embodiment of the present invention.

Referring to a platform for either of the image display apparatuses is a separate type according to an embodiment of the present invention. The platform may be designed separately as a legacy system platform and a smart system platform . An OS kernel may be shared between the legacy system platform and the smart system platform .

The legacy system platform may include a stack of a driver middleware and an application layer on the OS kernel .

On the other hand the smart system platform may include a stack of a library a framework and an application layer on the OS kernel .

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

The VM may be a virtual machine that enables concurrent execution of a plurality of instances that is multi tasking. For each application of the application layer a VM may be allocated and executed. For scheduling or interconnection between instances the binder driver of the OS kernel may operate.

In the smart system platform the framework includes programs on which applications of the application layer are based. The framework is compatible with any application and may allow component reuse movement or exchange. The framework may include supporting programs and programs for interconnecting different software components. For example the framework may include an activity manager related to activities of applications a notification manager and a CP for abstracting common information between applications. This framework may be written in Java.

The application layer on top of the framework includes a variety of programs that are executed and displayed in the image display apparatus. The application layer may include for example a core application that is a suit having at least one solution of e mail Short Message Service SMS calendar map or browser. The application layer may be written in Java.

In the application layer applications may be categorized into user undeletable applications stored in the image display apparatus that cannot be modified and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus.

With the applications of the application layer a variety of functions such as Internet telephony VoD Web album Social Networking Service SNS Location Based Service LBS map service Web browsing and application search may be performed through network access. In addition other functions such as gaming and schedule management may be performed by the applications.

Referring to a platform for the image display apparatus according to another embodiment of the present invention is an integrated type. The integrated platform may include an OS kernel a driver middleware a framework and an application layer .

Compared to the separate type platform illustrated in the integrated type platform is characterized by the absence of the library and the application layer being an integrated layer. The driver and the framework correspond to the driver and the framework of respectively.

The library of may be incorporated into the middleware . That is the middleware may include both the legacy system middleware and the image display system middleware. As described before the legacy system middleware includes MHEG or ACAP as data broadcasting related middleware PSIP or SI middleware as broadcasting information related middleware and DLNA middleware as peripheral device communication related middleware whereas the image display system middleware includes SSL as a security related library WebKit as a Web engine related library libc and Media Framework as a media related library. The middleware may further include the afore described runtime.

The application layer may include a menu related application a TV guide application a reservation application etc. as legacy system applications and e mail SMS a calendar a map and a browser as image display system applications.

In the application layer applications may be categorized into user undeletable applications that are stored in the image display apparatus and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus.

Based on the afore described platforms illustrated in a variety of Application Programming Interfaces APIs and Software Development Kits SDKs necessary to develop applications may be opened. APIs may be implemented functions that provide connectivity to specific sub routines for execution of the functions within a program. Or APIs may be implemented programs.

For example sources related to hardware drivers of the OS kernel such as a display driver a WiFi driver a Bluetooth driver a USB driver or an audio driver may be opened. Related sources within the driver such as a driver for a microcomputer a display module a GPU an FRC an SDEC a VDEC an ADEC or a pointing device may be opened. In addition sources related to PSIP or SI middleware as broadcasting information related middleware or sources related to DLNA middleware may be opened.

Such various open APIs allow developers to create applications executable in the image display apparatus or applications required to control operations of the image display apparatus based on the platforms illustrated in .

The platforms illustrated in may be general purpose ones that can be implemented in many other electronic devices as well as in image display apparatuses. The platforms may be stored or loaded in the memory the controller or any other processor. To execute applications an additional application processor may be further provided.

The user may move or rotate the remote controller up and down side to side and back and forth . Since the pointer moves in accordance with the movement of the remote controller the remote controller may be referred to as a pointing device.

Referring to if the user moves the remote controller to the left the pointer moves to the left on the display . A sensor of the remote controller detects the movement of the remote controller and transmits motion information corresponding to the result of the detection to the image display apparatus. Then the image display apparatus determines the movement of the remote controller based on the motion information received from the remote controller and calculates the coordinates of a target point to which the pointer should be shifted in accordance with the movement of the remote controller based on the result of the determination. The image display apparatus then displays the pointer at the calculated coordinates.

Referring to while pressing a predetermined button of the remote controller the user moves the remote controller away from the display . Then a selected area corresponding to the pointer may be zoomed in on and enlarged on the display . On the contrary if the user moves the remote controller toward the display the selection area corresponding to the pointer is zoomed out and thus contracted on the display . The opposite case is possible. That is when the remote controller moves away from the display the selection area may be zoomed out and when the remote controller approaches the display the selection area may be zoomed in.

With the predetermined button pressed in the remote controller the up down left and right movements of the remote controller may be ignored. That is when the remote controller moves away from or approaches the display only the back and forth movements of the remote controller are sensed while the up down left and right movements of the remote controller are ignored. Unless the predetermined button is pressed in the remote controller the pointer moves in accordance with the up down left or right movement of the remote controller .

The speed and direction of the pointer may correspond to the speed and direction of the remote controller .

The pointer is an object displayed on the display in correspondence with the movement of the remote controller . Therefore the pointer may have various shapes other than the arrow illustrated in . For example the pointer may be a dot a cursor a prompt a thick outline etc. The pointer may be displayed across a plurality of points such as a line and a surface as well as at a single point on horizontal and vertical axes.

Referring to the remote controller may include a wireless communication module a user input unit a sensor unit an output unit a power supply a memory and a controller .

The wireless communication module transmits signals to and or receives signals from either of the afore described image display apparatuses according to the embodiments of the present invention herein the image display apparatus .

The wireless communication module may include an RF module for transmitting RF signals to and or receiving RF signals from the image display apparatus according to an RF communication standard. The wireless communication module may also include an IR module for transmitting IR signals to and or receiving IR signals from the image display apparatus according to an IR communication standard.

The remote controller transmits motion information representing the movement of the remote controller to the image display apparatus through the RF module in this embodiment. The remote controller may also receive signals from the image display apparatus through the RF module . As needed the remote controller may transmit commands such as a power on off command a channel switch command or a volume change command to the image display apparatus through the IR module .

The user input unit may include a keypad a plurality of buttons a touchpad and or a touch screen. The user may enter commands to the image display apparatus by manipulating the user input unit . If the user input unit includes a plurality of hard buttons the user may input various commands to the image display apparatus by pressing the hard buttons. Alternatively or additionally if the user input unit includes a touch screen displaying a plurality of soft keys the user may input various commands to the image display apparatus by touching the soft keys. The user input unit may also include various input tools other than those set forth herein such as a scroll key and or a jog wheel which should not be construed as limiting the present invention.

The sensor unit may include a gyro sensor and or an acceleration sensor . The gyro sensor may sense the movement of the remote controller for example in X Y and Z axis directions and the acceleration sensor may sense the speed of the remote controller . The sensor unit may further include a distance sensor for sensing the distance between the remote controller and the display .

The output unit may output a video and or audio signal corresponding to manipulation of the user input unit or corresponding to a signal received from the image display apparatus . The user may easily identify whether the user input unit has been manipulated or whether the image display apparatus has been controlled based on the video and or audio signal output by the output unit .

The output unit may include a Light Emitting Diode LED module which is turned on or off whenever the user input unit is manipulated or whenever a signal is received from or transmitted to the image display apparatus through the wireless communication module a vibration module which generates vibrations an audio output module which outputs audio data and or a display module which outputs video data.

The power supply supplies power to the remote controller . If the remote controller is kept stationary for a predetermined time or longer the power supply may for example reduce or shut off supply of power to the spatial remote controller in order to save power. The power supply may resume power supply if a predetermined key on the spatial remote controller is manipulated.

The memory may store various types of programs and application data necessary to control or drive the remote controller . The spatial remote controller may wirelessly transmit signals to and or receive signals from the image display apparatus over a predetermined frequency band with the aid of the RF module . The controller of the remote controller may store information regarding the frequency band used for the remote controller to wirelessly transmit signals to and or wirelessly receive signals from the paired image display apparatus in the memory for later use.

The controller provides overall control to the remote controller . The controller may transmit a signal corresponding to a key manipulation detected from the user input unit or a signal corresponding to motion of the spatial remote controller as sensed by the sensor unit to the image display apparatus .

Referring to an application list available from a network is displayed on the display . A user may access a CP or an NP directly search for various applications and download the applications from the CP or the NP.

Specifically illustrates an application list available in a connected server displayed on the display . The application list may include an icon representing each application and a brief description of the application. Because each of the image display apparatuses according to the embodiments of the present invention is capable of full browsing it may enlarge the icons or descriptions of applications received from the connected server on the display . Accordingly the user can readily identify applications which will be described later.

While it is shown in that the user selects a desired application by moving the pointer using the remote controller the application may be selected in many other ways. For example the user may select a specific application using a cursor displayed on the display by a combined input of a local key and an OK key in the remote controller .

In another example if the remote controller has a touch pad the pointer moves on the display according to touch input of the touch pad. Thus the user may select a specific menu using the touch based pointer .

The image display apparatuses according to the embodiments of the present invention are capable of full browsing when displaying a mail service page. Therefore the user can use the mail service conveniently.

Referring to the image display apparatus enters a setup menu S . Specifically the controller enters the setup menu according to a control signal received from a local key or the remote controller .

The screen configuration illustrated in may be a default screen configuration for a smart TV. The screen may be set as an initial screen that is displayed when the image display apparatus is powered on or as a default screen that is displayed when a local key or a Home key of the remote controller is manipulated. A card object area and an application menu area may be defined on the screen.

The card object area may include a plurality of card objects and classified according to content sources. In the card object is named BROADCAST and displays a broadcast image. The card object is named NETCAST and provides a CP list. The card object which is named APP STORE provides a list of applications. Other card objects may further be included in the card object area such as a card object for providing a thumbnail list of broadcast channels a card object for providing a program list a card object for providing a reserved program list and a card object for providing a media list available in a device.

The BROADCAST card object may contain a broadcast image an object representing an external device and the setup object . Upon selection of the setup object the setup menu appears so that the user can set login information an ID and a password for a plurality of Social Network Services SNSs as illustrated in .

The NETCAST card object may contain a CP list. While Yakoo Metflix weather.com Picason and My tube are shown as CPs in the CP list in others may be displayed.

The APP STORE card object may contain a list of applications available in an APP STORE. The applications may be sorted for example by popularity HOT and by time NEW as illustrated in which should not be interpreted as limiting the present invention.

While the three card objects and are shown in as displayed on the display this is purely exemplary. Thus the number of displayed card objects may be changed. For instance the card object may be displayed alone or along with another card object on the display .

Any of the card objects displayed on the display may be exchanged with another card object. Specifically the card object or may be exchanged with any other card object according to a control signal received from a local key or the remote controller thereby allowing the user to simply select an intended service. Herein the card object having the broadcast image may be kept displayed so that the user can continue viewing the broadcast image .

An application menu may be displayed in the application menu area defined on a lower part of the display . The application menu includes a plurality of application menu items particularly preferred application menu items Search and App Store and optional application menu items DVR Bluray MAZON and SNS set by the user. The SNS menu item may represent an application that can execute a plurality of SNSs.

With the setup object displayed on the display the user may enter the setup menu using the pointer of the controller which should not be interpreted as limiting the present invention. To enter the setup menu many other settings are possible. For instance the setup menu may be directly entered through input of a Setup key of the remote controller . With the setup object displayed on the display the setup menu may be directly entered through input of a local key or through input of a directional key and or an OK key of the remote controller .

Referring to the user sets login information for a plurality of SNSs such as Pacebook Witter TSN and Myhome in the setup menu by way of example. Other SNSs including blogs and messengers are also available. The login information may include an ID and a password.

The user may enter an ID and a password for each SNS using local keys letter keys of the remote controller or a letter key object displayed on the display .

Upon receipt of a save input for the login information after the login information is completely entered the controller controls saving of the login information in the memory .

If an SNS is not accessible using login information set for the SNS the controller may display an object notifying that the login information is not valid on the display .

Since login information is preliminarily stored for a plurality of SNSs as described above the user may directly access the SNSs using the stored login information without a login procedure.

After the login information is stored an image is displayed on the display S . Specifically once the setup menu is exited the controller controls display of an image on at least a part of the display . The image may be a broadcast image or an external input image.

Upon completion of saving the login information in the setup menu of triggered by selecting the setup object of the image display apparatus may return to the screen of in which the broadcast image is displayed on a part of the display .

It is determined whether an application menu display input has been received S . Upon receipt of the application menu display input an application menu is displayed on at least a part of the display S .

More specifically the controller monitors receipt of the application menu display input according to a control signal received from a local key or the remote controller . Upon receipt of the application menu display input the controller controls display of the application menu on at least a part of the display .

The application menu display input may be created using an additional menu displayed on the display using a local key set as a hot key or a hot key provided in the remote controller . The hot key functions to directly open an application menu.

Unlike the screen configuration illustrated in the screen illustrated in or is configured so as to include the application menu . Therefore when the image display apparatus is powered on or a local key or the Home key of the remote controller is manipulated the application menu may be displayed.

It is determined whether an SNS selection input has been received S . Upon receipt of the SNS selection input the SNS application menu item is selected in the application menu S . Subsequently a plurality of social network servers are accessed based on the stored login information S and objects representing other users or electronic devices subscribed to the plurality of SNSs are displayed on at least a part of the display S .

Specifically the controller determines whether an application menu item representing SNS has been selected in the application menu according to a control signal received from a local key or the remote controller . Upon selection of the SNS application menu item the controller controls execution of the SNSs. That is the controller controls access to a plurality of social network servers using the stored login information and controls display of objects representing other users or electronic devices subscribed to the plurality of SNSs on at least a part of the display .

The TOTAL SNS card object contains objects representing other users or electronic devices subscribed to the plurality of SNSs. Each of these objects may include an avatar an image an icon or text indicating a name which represents a user or electronic device. The objects may be sorted by SNS. The term used herein other electronic devices may refer to electronic devices registered with the plurality of SNSs such as mobile phones PCs TVs etc.

In the objects are sorted from a first SNS to a fourth SNS. Specifically objects represent other users or electronic devices subscribed to the first SNS objects represents other users or electronic devices subscribed to the second SNS objects represent other users or electronic devices subscribed to the third SNS and objects represent other users or electronic devices subscribed to the fourth SNS. Meanwhile the objects may be sorted such that logged in users are distinguished from logged out users in the card object . Also the objects may be sorted according to user set groups e.g. friend family company etc. 

In this manner a plurality of SNSs are displayed on at least a part of the display thereby allowing the user to easily identify other users or electronic devices subscribed to each SNS in the embodiment of the present invention. Accordingly user convenience is increased.

As stated before with reference to login information necessary to access the first to fourth SNSs may be stored in advance.

In objects and objects are arranged in different rows. The objects represent other users or electronic devices logged in to the first SNS and the objects represent other users or electronic devices logged in to the second SNS. Objects representing other users or electronic devices logged out from the first or second SNS are arranged in a row. To distinguish the objects and representing the logged in users from the object representing the logged out users the objects may be displayed differently from the objects and in terms of at least one of color brightness contrast or outline thickness. Therefore the user can readily distinguish the logged in users from the logged out users.

Because the object screen illustrated in is larger than the card object illustrated in the object screen may display more objects than the card object . Hence the user can more easily identify other users of the SNSs.

It is also possible to continue to display the application menu in the lower part of the display along with the objects and representing other users or electronic devices of the SNSs as illustrated in .

On the other hand illustrates an example of displaying an object screen alone without the application menu . Referring to in addition to objects and representing other users or electronic devices logged in to the first and second SNSs objects representing other users or electronic devices logged in to a third SNS are arranged in a row. Thus the objects and are distinguished from one another on a row basis. Objects representing other users or electronic devices logged out from the first second and third SNSs are arranged in a row. Therefore the user can readily tell the logged in users from the logged out users.

The screen configuration of is the same as the screen configuration of in that an object screen is displayed alone on the display without an application menu and different from the latter in that each object further includes an icon that identifies an SNS. Hence the same icon represents the same SNS and different icons represent different SNSs.

Referring to each of objects representing other users or electronic devices logged in to the first SNS may include an icon indicating Pacebook besides an avatar an image or text member . Thus the user can identify the SNSs of other users or electronic devices by such icons.

Similarly each of objects representing other users or electronic devices logged in to the second SNS may further include an icon indicating Witter each of objects representing other users or electronic devices logged in to the third SNS may further include an icon indicating TSN and each of objects representing other users or electronic devices logged in to the fourth SNS may further include an icon indicating Myhome.

Objects representing other users or electronic devices logged out from the first to fourth SNSs may be different from the objects to in color brightness etc.

While not shown in each object may further include an icon representing an electronic device connected to an SNS. For example if a mobile phone or a TV is connected to the first SNS an icon representing a mobile phone or a TV may further be displayed. Therefore if different electronic devices are connected to an SNS for the same user different icons may be displayed for the user. It is also possible to configure an object to be shaped into an electronic device connected to an SNS.

It is determined whether an object representing another user or electronic device has been focused on S . Upon focusing of an object representing another user or electronic device a menu including information about the user or electronic device or service menu items available for the user or electronic device is displayed S .

Specifically upon focusing on an object representing another user or electronic device according to a control signal received from a local key or the remote controller the controller may control display of a menu including information about the user or electronic device or service menu items available for the user or electronic device on the display .

In the menu the information about the user or electronic device may include an ID a nickname and a profile of the user or electronic device and the service menu items may include video call voice call SMS and file share.

Although it is preferable to provide a common menu for a plurality of SNSs it is also possible to provide different menus for the SNSs if different services are provided for the SNSs.

Different menus may be provided for an object representing a logged in user or electronic device and an object representing a logged out user or electronic device. For example the afore described video call and voice call menu items may not be provided for the logged out user or electronic device.

It is determined whether a menu item has been selected in the menu S . Upon selection of a menu item a service corresponding to the menu item is executed S .

More specifically upon selection of one of related information video call voice call SMS and file share in the menu according to a control signal received from a local key or the remote controller the controller may control execution of a service corresponding to the selected menu item.

The captured image of the other user may be utilized as an object representing the other user as a subscriber to an SNS. As described above an image object may be created based on the captured image of the other user.

Referring to with the broadcast image and the setup object displayed on the display the setup object is selected using the pointer of the remote controller as illustrated in . The selection of the setup object triggers opening of the setup menu as illustrated in .

Referring to the setup menu may contain a Web site list listing a plurality of Web sites along with login information for accessing the Web sites. The Web sites are shown to be Web Site to Web Site by way of example. The login information for each Web site may include an ID and a password.

The user may enter an ID and a password for each Web site using a local key a letter key of the remote controller or a letter key object displayed on the display .

Upon receipt of a save input after the login information is completely set for the plurality of Web sites the controller may control saving of the Web site list listing the plurality of Web sites along with the login information for the Web sites in the memory .

The user may select only a Web site that he or she wants to automatically access in the Web site list. In the illustrated case of the boxes beside Web Site to Web Site are all checked that is Web Site to Web Site are all selected by way of example.

As illustrated in in the case where selection of the setup object triggers the setup menu of the screen of or may be returned to upon completion of saving the login information.

Compared to the application menu illustrated in the application menu illustrated in further includes the Internet application menu item and a mail application menu item.

Referring to the APP STORE card object representing an application list has been replaced with the card object .

The card object represents Web sites that have been connected based on the Web site list containing a plurality of Web sites along with login information for the Web sites as illustrated in .

The card object contains a connected site list . The connected site list may include icons representing automatically logged in Web sites and text specifying the names of the Web sites.

With the card object displayed on the display as illustrated in upon selection of an icon representing Web Site using the pointer of the remote controller an automatically logged in Web page is displayed on the display as illustrated in .

Referring to the automatically logged in Web page may include a user account on the Web site and a logout menu item .

Since login information for accessing a plurality of Web sites has already been stored in advance the Web sites can be accessed directly based on the stored login information without a login procedure.

With the CONNECTED SITE card object displayed on the display as illustrated in upon selection of the name of the card object CONNECTED SITE using the pointer of the remote controller a screen including Web pages of automatically logged in Web sites may all be displayed on the display as illustrated in .

Upon selection of the Internet application menu item in the application menu using the pointer of the remote controller as illustrated in the screen may be displayed on the display without the card object of .

Referring to the screen includes Web pages to of the plurality of connected Web sites Web Site to Web Site . Web Site to Web Site are shown in as a search site an Internet banking site a Blog and a broadcasting station site respectively. Many other Web sites may be automatically logged in.

The Web pages to may include logout menu items and respectively. In addition the Web pages to may include user accounts on the Web sites.

As described above since the automatically logged in Web pages are displayed on the single screen the user can access desired Web sites at the same time and view Web pages of the Web sites in an organized manner.

The mechanism of automatic log in to a plurality of Web sites as described with reference to may be applicable to automatic log in to the Web sites of CPs Yakoo Metflix weather.com Picason and My tube listed in the card object illustrated in . The App Store of the card object illustrated in may also be automatically logged in. For instance in the presence of a plurality of App Stores the App Stores may be automatically logged in.

Web site lists each listing a plurality of Web sites along with login information for the Web sites as described before with reference to may be sorted on a user basis when they are stored. It is also possible to automatically log in to the stored plurality of Web sites on a user basis which will be described later with reference to .

Each user may be identified using the camera module or using information about a finger print of the users on the remote controller . Many other implementations are possible for identifying a user. In addition a user may be identified based on a character input.

Referring to the BROADCAST card object for displaying the broadcast image the NETCAST card object for providing a CP list the APP STORE card object for providing an application list and an application menu are displayed on the display like the screen configuration of . However a login menu item may be displayed above the card object or unlike .

The login menu item may be used to identify a user. For example the login menu item may be used when a user accesses a Web site receives content from a CP accesses an App Store logs in to a network connected to the image display apparatus or logs in to the image display apparatus .

The login menu or may be displayed as a pop up window to which the present invention is not limited. Thus the login menu or may be displayed as an independent login screen on the display .

Referring to the user may enter login information an ID and a password directly into the login menu for example using letter keys of the remote controller .

Referring to if login information is pre stored in the memory on a user basis a user may select his or her login information in the login menu . In login information of User is selected.

In after the user logs in to the image display apparatus the user selects the setup object using the pointer of the remote controller with the broadcast image and the setup object displayed on the display . Therefore the setup menu appears as illustrated in .

The setup menu of is the same as the setup menu of in that it may include a Web site list listing a plurality of Web sites along with login information for the Web sites except that a tab menu representing a logged in user is further displayed. In a Web site list lists a plurality of Web sites for User among User User and User along with login information for the Web sites.

Unlike illustrates an example in which the user selects the setup object using the pointer of the remote controller without logging in to the image display apparatus with the broadcast image and the setup object displayed on the display . Hence the setup menu is entered as illustrated in . Herein the login menu or may be displayed as a popup window on the setup menu .

Referring to the user may enter login information an ID and a password directly into a login menu for example using letter keys of the remote controller .

Referring to in the case where login information is pre stored for each user in the memory the user may select user login information herein login information for USER .

In this manner a plurality of Web sites may be set on a user basis. Accordingly upon selection of the Internet application menu item in the application menu a plurality of Web sites to which USER subscribed may be automatically logged in.

As is apparent from the above description of the present invention a plurality of social network services are displayed on at least a part of a display in such a manner that a user can identify other users subscribed to each social network service at one time. Therefore user convenience can be increased.

The plurality of social network services are distinguishably displayed to the user. Especially the social network services are represented as icons thereby allowing the user to readily identify them.

Objects representing other users or electronic devices logged into the plurality of social network services are displayed distinguishably from objects representing other users or electronic devices logged out from the plurality of social network services. Thus the user can easily tell the logged in users or electronic devices from the logged out users or electronic devices.

When one of a plurality of objects is focused on a menu including information about a user or electronic device represented by the focused object and available service menu items for the user or electronic device is displayed so that the user can easily get to know the user or electronic device.

A Web site list listing a plurality of Web sites along with login information for the Web sites is stored. Hence the user can automatically log in to the plurality of Web sites. Especially since the Web sites are accessed on a user basis user convenience can be increased.

The user convenience can be further increased because the image display apparatus provides the user with various user interfaces.

The image display apparatus and the method for operating the same according to the foregoing exemplary embodiments are not restricted to the embodiments set forth herein. Therefore variations and combinations of the embodiments set forth herein may fall within the scope of the present invention.

The method for operating an image display apparatus according to the foregoing exemplary embodiments may be implemented as code that can be written on a computer readable recording medium and thus read by a processor. The computer readable recording medium may be any type of recording device in which data is stored in a computer readable manner. Examples of the computer readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disc optical data storage and a carrier wave e.g. data transmission over the Internet . The computer readable recording medium can be distributed over a plurality of computer systems connected to a network so that computer readable code is written thereto and executed therefrom in a decentralized manner. Programs code and code segments to realize the embodiments herein can be construed by one of ordinary skill in the art.

While the present invention has been particularly shown and described with reference to embodiments thereof it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims.

