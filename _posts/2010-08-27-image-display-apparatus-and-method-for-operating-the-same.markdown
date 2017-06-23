---

title: Image display apparatus and method for operating the same
abstract: An image display apparatus and a method for operating the same are disclosed. The image display apparatus includes a display, a user input interface for receiving a control signal from a remote controller and processing the received control signal, a network interface for transmitting or receiving data over a network, a controller for controlling a pointer on the display according to the control signal received from the remote controller, and a platform for controlling data transmission or reception over the network according to the control signal received from the remote controller. The platform includes an Operating System (OS) kernel and an application layer that runs on the OS kernel, and the application layer including an installable or deletable application downloaded over the network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08552975&OS=08552975&RS=08552975
owner: LG Electronics Inc.
number: 08552975
owner_city: Seoul
owner_country: KR
publication_date: 20100827
---
This application claims the benefit of Korean Application No. 10 2009 0081421 filed on Aug. 31 2009 in the Korean Intellectual Property Office and U.S. Provisional Application No. 61 322 614 filed on Apr. 9 2010 in the USPTO the disclosure of which is incorporated herein by reference.

The present invention relates to an image display apparatus and a method for operating the same and more particularly to an image display apparatus for increasing user convenience and a method for operating the same.

An image display apparatus has a function of displaying images viewable to a user. The image display apparatus can display a broadcast program selected by the user on a display from among broadcast programs transmitted from broadcasting stations. The recent trend in broadcasting is a worldwide shift from analog broadcasting to digital broadcasting.

As it transmits digital audio and video signals digital broadcasting offers many advantages over analog broadcasting such as robustness against noise less data loss ease of error correction and the ability to provide high definition clear images. Digital broadcasting also allows interactive services for viewers.

Therefore the present invention has been made in view of the above problems and it is an object of the present invention to provide an image display apparatus for increasing user convenience and a method for operating the same.

It is another object of the present invention to provide an image display apparatus for enabling a user to easily select an intended application from an application list and a method for operating the same.

It is another object of the present invention to provide an image display apparatus for enabling a user to easily receive an intended application list and a method for operating the same.

It is a further object of the present invention to provide an image display apparatus for providing various user interfaces and a method for operating the same.

In accordance with an aspect of the present invention the above and other objects can be accomplished by the provision of an image display apparatus including a display a user input interface for receiving a control signal from a remote controller and processing the received control signal a network interface for transmitting or receiving data over a network a controller for controlling a pointer on the display according to the control signal received from the remote controller and a platform for controlling data transmission or reception over the network according to the control signal received from the remote controller. The platform includes an Operating System OS kernel and an application layer that runs on the OS kernel and the application layer including an installable or deletable application downloaded over the network.

In accordance with another aspect of the present invention there is provided a method for operating an image display apparatus including transmitting an application selection command to a content server or a network server over a network according to a control signal received from a remote controller downloading an application corresponding to the application selection command from the content server or the network server over the network and installing the downloaded application.

Exemplary embodiments of the present invention will be described below with reference to the attached drawings.

The terms module and portion attached to describe the names of components are used herein to help the understanding of the components and thus they should not be considered as having specific meanings or roles. Accordingly the terms module and portion may be interchangeable in their use.

An image display apparatus as set forth herein is an intelligent image display apparatus equipped with a computer support function in addition to a broadcasting reception function. As the image display apparatus is capable of browsing the Internet as well as receiving broadcast programs it may have user friendly interfaces such as a handwriting input device a touch screen or a pointing device. Further because the image display apparatus supports wired or wireless Internet a user can enjoy e mail transmission reception Web browsing banking gaming etc. by connecting the image display apparatus to the Internet or a computer. For implementing these functions the image display apparatus may operate based on a standard general purpose Operating System OS .

Various applications can be freely added to or deleted from the image display apparatus according to the present invention. Therefore the image display apparatus may perform a number of user friendly functions. The image display apparatus may be a smart TV for example.

Referring to from the perspective of providing content services from broadcasters the image display system may include a Content Provider CP a Service Provider SP a Network Provider NP and a customer .

The CP creates and provides contents. The CP may be for example a terrestrial broadcaster a cable System Operator SO or Multiple System Operator MSO a satellite broadcaster or an Internet broadcaster.

Besides broadcasting contents the CP may provide various applications which will be described later with reference to .

The SP may provide contents received from the CP in a service package. For instance the SP packages first terrestrial broadcasting second terrestrial broadcasting cable broadcasting satellite broadcasting Internet broadcasting and applications and provides the package to users.

The SP may unicast or multicast a service to the customer . Unicast is a type of transmission in which information is sent from only one transmitter to only one receiver. In another words Unicast transmission is between one to one nodes involving two nodes only. In an example of unicast transmission upon receipt of a request for data from a receiver a server transmits the data to only one receiver. Multicast is a type of transmission or communication in which transmitter transmits data to a group of receivers. For example a server may transmit data to plurality of pre registered receivers at one time. For this multicast registration an Internet Group Management Protocol IGMP may be used.

The NP may provide a network over which a service is provided to the customer . The customer i.e. Home Network End User HNED may configure a home network and receive a service over the home network.

Contents transmitted in the above image display system may be protected by conditional access or content protection. CableCard and Downloadable Conditional Access System DCAS are examples of conditional access or content protection.

The customer may also transmit contents over a network. In this case the customer serves as a CP and the CP may receive contents from the customer . Therefore a bi directional content service or data service may be provided.

Referring to an image display apparatus according to an exemplary embodiment of the present invention includes a broadcast receiver an external device interface a memory a user input interface a controller a display an audio output unit and a power supply . The broadcast receiver may include a tuner a demodulator and a network interface . It is possible to selectively provide the broadcast receiver with the tuner and the demodulator or the network interface .

The tuner selects a Radio Frequency RF broadcast signal corresponding to a channel selected by a user from among a plurality of RF broadcast signals received through an antenna or an RF broadcast signal corresponding to each of pre memorized channels and downconverts the RF broadcast signal to a digital Intermediate Frequency IF signal or an analog baseband Audio Video A V signal.

More specifically if the RF broadcast signal is a digital broadcast signal the tuner downconverts the RF broadcast signal to a digital IF signal DIF. On the other hand if the RF broadcast signal is an analog broadcast signal the tuner downconverts the RF broadcast signal to an analog baseband Audio Video A V signal CVBS SIF. That is the tuner may be a hybrid tuner capable of processing not only digital broadcast signals but also analog broadcast signals. The analog baseband A V signal CVBS SIF may be directly input to the controller .

The tuner may be able to receive RF broadcast signals from an Advanced Television Systems Committee ATSC single carrier system or from a Digital Video Broadcasting DVB multi carrier system.

The tuner may sequentially select a number of RF broadcast signals corresponding to all broadcast channels previously memorized in the image display apparatus by a channel add function from a plurality of RF signals received through the antenna and may downconvert the selected RF broadcast signals to IF signals or baseband A V signals.

The demodulator receives the digital IF signal DIF from the tuner and demodulates the digital IF signal DIF.

For example if the digital IF signal DIF is an ATSC signal the demodulator may perform 8 Vestigal SideBand VSB demodulation on the digital IF signal DIF. The demodulator may also perform channel decoding. For the channel decoding the demodulator may include a Trellis decoder not shown a deinterleaver not shown and a Reed Solomon decoder not shown and thus perform Trellis decoding deinterleaving and Reed Solomon decoding.

For example if the digital IF signal DIF is a DVB signal the demodulator performs Coded Orthogonal Frequency Division Multiple Access COFDMA demodulation on the digital IF signal DIF. The demodulator may also perform channel decoding. For the channel decoding the demodulator may include a convolution decoder not shown a deinterleaver not shown and a Reed Solomon decoder not shown and thus perform convolutional decoding deinterleaving and Reed Solomon decoding.

The demodulator may perform demodulation and channel decoding on the digital IF signal DIF received from the tuner thereby obtaining a stream signal TS. The stream signal TS may be a signal in which a video signal an audio signal and a data signal are multiplexed. For example the stream signal TS may be a Moving Picture Experts Group 2 MPEG 2 Transport Stream TS signal obtained by multiplexing an MPEG 2 video signal and a Dolby AC 3 audio signal. The MPEG 2 TS signal may include a 4 byte header and a 184 byte payload.

In order to properly handle not only ATSC signals but also DVB signals the demodulator may include an ATSC demodulator and a DVB demodulator.

The stream signal TS may be input to the controller and thus subjected to demultiplexing and A V signal processing. The processed video and audio signals are output to the display and the audio output unit respectively.

The external device interface may interface between an external device and the image display apparatus . For the interfacing the external device interface may include an A V Input Output I O portion not shown or a wireless communication module not shown .

The external device interface may be connected wirelessly or wiredly to an external device such as a Digital Versatile Disc DVD a Blu ray disc a gaming device a camera a camcorder or a computer e.g. a laptop computer . Then the external device interface receives video audio and or data signals from the external device and transmits the received external input signals to the controller . In addition the external device interface may output video audio and data signals processed by the controller to the external device. In order to receive or transmit audio and video signals from or to the external device the external device interface may include the A V I O portion not shown or the wireless communication module not shown .

To provide the video and audio signals received from the external device to the image display apparatus the A V I O portion may include a Universal Serial Bus USB port a Composite Video Banking Sync CVBS port a component port a Super video S video analog port a Digital Visual Interface DVI port a High Definition Multimedia Interface HDMI port a Red Green Blue RGB port and a D sub port.

The wireless communication module may perform short range wireless communication with other electronic devices. For the short range wireless communication over a network the wireless communication module may operate in compliance with communication standards such as Bluetooth Radio Frequency IDentification RFID Infrared Data Association IrDA Ultra WideBand UWB and ZigBee.

The external device interface may be connected to various set top boxes through at least one of the USB port the CVBS port the component port the S video port the DVI port the HDMI port the RGB port and the D sub port and may thus receive data from or transmit data to the various set top boxes.

The external device interface may receive applications or an application list from an adjacent external device and provide the applications or the application list to the controller or the memory .

The network interface interfaces between the image display apparatus and a wired wireless network. The network interface may include an Ethernet port for connection to a wired network. For connection to wireless networks the network interface may use Wireless Local Area Network WLAN i.e. Wi Fi Wireless Broadband Wibro World Interoperability for Microwave Access WiMax and High Speed Downlink Packet Access HSDPA .

The network interface may access a specific Web page over a network. That is the network interface may access a specific Web page over a network and transmit or receive data to or from a server. Besides the network interface may receive contents or data from a CP or an NP. Specifically the network interface may receive contents including movies advertisements games Video on Demand VoD files and broadcast signals and information related to the contents from a CP or an NP. Also the network interface may receive update information about firmware and update files of the firmware from the NP. The network interface may transmit data to the Internet the CP or the NP.

The network interface may selectively receive a desired application among open applications over a network.

The memory may store various programs for processing and controlling signals by the controller and may also store processed video audio and data signals.

The memory may temporarily store a video audio and or data signal received from the external device interface or the network interface . The memory may memorize broadcast channels by the channel add function.

The memory may store the applications or the application list received from the external device interface or the network interface .

The memory may include for example at least one of a flash memory type memory medium a hard disc type memory medium a multimedia card micro type memory medium a card type memory e.g. a Secure Digital SD or eXtreme Digital XD memory a Random Access Memory RAM and a Read Only Memory ROM such as Electrical Erasable and Programmable ROM EEPROM . The image display apparatus may play content files stored in the memory e.g. video files still image files music files text files and application files for the user.

While the memory is shown in as configured separately from the controller to which the present invention is not limited the memory may be incorporated into the controller for example.

The user input interface transmits a signal received from the user to the controller or transmits a signal received from the controller to the user.

For example the user input interface may receive various user input signals such as a power on off signal a channel selection signal and a screen setting signal from a remote controller or may transmit a signal received from the controller to the remote controller according to various communication schemes for example RF communication and IR communication.

For example the user input interface may provide the controller with user input signals or control signals received from local keys not shown such as inputs of a power key a channel key and a volume key and setting values.

Also the user input interface may transmit a user input signal or control signal received from a sensor unit not shown for sensing a user s gesture to the controller or transmit a signal received from the controller to the sensor unit. The sensor unit may include a touch sensor a voice sensor a position sensor a motion sensor etc.

The controller may demultiplex the stream signal TS received from the tuner the demodulator or the external device interface into a number of signals and process the demultiplexed signals so that the processed signals can be output as audio and video data.

The video signal processed by the controller may be displayed as an image on the display . The video signal processed by the controller may also be transmitted to an external output device through the external device interface .

The audio signal processed by the controller may be output to the audio output unit . Also the audio signal processed by the controller may be transmitted to the external output through the external device interface .

While not shown in the controller may include a demultiplexer and a video processor which will be described later with reference to .

Besides the controller may provide overall control to the image display apparatus . For example the controller may control the tuner to select an RF broadcast signal corresponding to a user selected channel or a pre memorized channel.

The controller may control the image display apparatus according to a user command received through the user input interface or according to an internal program. Especially the controller may access a network and download a user desired application or an application list to the image display apparatus over the network.

For example the controller controls the tuner to receive a channel selected according to a specific channel selection command received through the user input interface and processes a video audio and or data signal of the selected channel. The controller outputs the processed video or audio signal along with information about the user selected channel to the display or the audio output unit .

In another example the controller outputs a video or audio signal received from an external device such as a camera or a camcorder through the external device interface to the display or the audio output unit according to an external device video play command received through the external device interface .

The controller may control the display to display images. For instance the controller may control the display to display a broadcast image received from the tuner an external input image received through the external device interface an image received through the network interface or an image stored in the memory . The image displayed on the display may be a Two Dimensional 2D or Three Dimensional 3D moving picture or still image.

When an application view menu item is selected the controller may control the display to display applications or an application list available in the image display apparatus or downloadable from an external network.

The controller may control installation and execution of applications downloaded from the external network by use of various user interfaces. In addition the controller may control the display to display an image related to a user selected application that is executed.

The image display apparatus may further include a channel browsing processor not shown for generating thumbnail images corresponding to channel signals or external input signals. The channel browsing processor may extract some of the video frames of each of stream signals TS received from the demodulator or stream signals received from the external device interface and display the extracted video frames on the display as thumbnail images. The thumbnail images may be output to the controller after they are encoded or as they are. Also it is possible to encode the thumbnail images into a stream and output the stream to the controller . The controller may display a thumbnail list including a plurality of received thumbnail images on the display . The thumbnail images may be updated sequentially or simultaneously in the thumbnail list. Therefore the user may intuitively identify the contents of broadcast programs received through a plurality of channels.

The display may convert a processed video signal a processed data signal and an On Screen Display OSD signal received from the controller or a video signal and a data signal received from the external device interface to RGB signals thereby generating driving signals.

The display may be implemented into various types of displays such as a Plasma Display Panel PDP a Liquid Crystal Display LCD an Organic Light Emitting Diode OLED a flexible display and a 3D display.

The display may also be implemented as a touch screen so that it is used not only as an output device but also as an input device.

The audio output unit may receive a processed audio signal e.g. a stereo signal a 3.1 channel signal or a 5.1 channel signal from the controller and output the received audio signal as voice. The audio output unit may be implemented into various types of speakers.

The image display apparatus may further include a camera portion not shown for capturing the user. The camera portion may be implemented with one camera to which the present invention is not limited. Hence the camera portion may include a plurality of cameras. Image information captured by the camera portion is transmitted to the controller .

To sense a user s gesture the image display apparatus may further include the sensor unit not shown that has at least one of a touch sensor a voice sensor a position sensor and a motion sensor as stated before. A signal sensed by the sensor unit may be output to the controller through the user input interface .

The controller may sense a user s gesture from an image captured by the camera portion or a signal sensed by the sensor unit or by combining the captured image and the sensed signal.

The power supply supplies power to the image display apparatus . Particularly the power supply may supply power to the controller that can be implemented as a System On Chip SOC the display for displaying images and the audio output unit for audio output.

For supplying power the power supply may include a converter not shown for converting alternate current to Direct Current DC . If the display is configured with for example a liquid crystal panel having a plurality of backlight lamps the power supply may further include an inverter not shown capable of performing a Pulse Width Modulation PWM operation for luminance change or dimming driving.

The remote controller transmits a user input to the user input interface . For the transmission of a user input the remote controller may use various communication techniques such as Bluetooth RF IR Ultra WideBand UWB and ZigBee.

In addition the remote controller may receive a video signal an audio signal or a data signal from the user input interface and output the received signals visually audibly or as vibrations.

The above described image display apparatus may be a fixed digital broadcast receiver capable of receiving at least one of ATSC 8 VSB broadcast programs DVB T COFDM broadcast programs and ISDB T BST OFDM broadcast programs.

Alternatively the image display apparatus may be a wireless type without the display and the audio output unit illustrated in which transmits and receives data to and from the display and the audio output unit by radio communication.

The block diagram of the image display apparatus illustrated in is an exemplary embodiment of the present invention. Depending on the specification of the image display apparatus in real implementation the components of the image display apparatus may be incorporated added or omitted. That is two or more components are incorporated into one component or one component may be configured as separate components when needed. In addition the function of each block is described for the purpose of describing the exemplary embodiment of the present invention and thus specific operations or devices should not be construed as limiting the scope and spirit of the present invention.

Unlike the image display apparatus may not have the tuner and the demodulator illustrated in and thus may receive and play video contents through the network interface or the external device interface .

The image display apparatus is an example of an image signal processing apparatus that processes a video signal corresponding to an input or stored image. Another example of the image signal processing apparatus may be a set top box that does not include the display illustrated in a DVD player a Blu ray player a game player or a computer. Now a description will be made of the set top box with reference to .

Referring to a set top box and a display device may transmit data to or receive data from each other wirelessly or wiredly. The following description will focus on the difference between the set top box and the display device illustrated in and the image display apparatus illustrated in .

The set top box may include a network interface a memory a signal processor a user input interface and an external device interface .

The network interface provides interfacing with a wired wireless network including the Internet. The network interface may also transmit data to or receive data from other users or other electronic devices over a connected network or another network linked to the connected network.

The memory may store programs for signal processing and control operations of the signal processor and temporarily store video audio and or data signals received from the external device interface or the network interface . The memory may further store platforms illustrated in which will be described later.

The signal processor processes an input signal. For example the signal processor demultiplexes or decodes an input video signal or audio signal. For the demultiplexing or decoding the signal processor may include a video decoder or an audio decoder. The processed video signal or audio signal may be transmitted to the display device through the external device interface .

The user input interface transmits a user input signal to the signal processor or transmits a signal received from the signal processor to a user. For example the user input interface may transmit various control signals received through a local key not shown or the remote controller such as a power on off signal an operation input signal and a setting input signal to the signal processor .

The external device interface provides interfacing with a wiredly or wirelessly connected external device particularly the display device for data transmission or reception. Besides the external device interface may provide interfacing with an external device such as a game player a camcorder and a laptop computer for data transmission or reception.

The set top box may further include a media input unit not shown to play media. The media input unit may be a Blu ray input unit not shown . That is the set top box may include a Blu ray player. Media played from a Blue ray disc may be demultiplexed or decoded in the signal processor and then transmitted to the display device through the external device interface so that the media is displayed.

The display device may include a tuner an external device interface a demodulator a memory a controller a user input interface a display and an audio output unit .

Since the tuner the demodulator the memory the controller the user input interface the display and the audio output unit are identical respectively to the tuner the demodulator the memory the controller the user input interface the display and the audio output unit a description of them will not be provided herein.

The external device interface interfaces with a wiredly or wirelessly connected external device particularly the set top box for data transmission or reception.

Therefore a video signal or audio signal received from the set top box is output to the display or the audio output unit through the controller .

Referring to the set top box and the display device are essentially the same as the set top box and the display device illustrated in except that the tuner and the demodulator reside in the set top box not in the display device . The following description will be made of the difference between .

The signal processor may process a broadcast signal received through the tuner and the demodulator . The user input interface may receive an input such as a channel selection input a channel store input etc.

Referring to the image display apparatus may communicate with a broadcasting station a network server or an external device .

The image display apparatus may receive a broadcast signal including a video signal from the broadcasting station . The image display apparatus may process the audio and video signals of the broadcast signal or the data signal of the broadcast signal to be suitable for being output from the image display apparatus . The image display apparatus may output images or sound based on the processed video or audio signal.

Meanwhile the image display apparatus may communicate with the network server . The network server is a device that transmits and receives signals to and from the image display apparatus over a network. For example the network server may be a portable terminal that can be connected to the image display apparatus through a wired or wireless base station. In addition the network server may provide contents to the image display apparatus over the Internet. A CP may provide contents to the image display apparatus through the network server .

The image display apparatus may communicate with the external device . The external device can transmit and receive signals directly to and from the image display apparatus wirelessly or by cable. For instance the external device may be a media memory or a player. That is the external device may be any of a camera a DVD a Blu ray player a PC etc.

The broadcasting station the network server or the external device may transmit a signal including a video signal to the image display apparatus . The image display apparatus may display an image based on the video signal included in the received signal. Also the image display apparatus may transmit a signal received from the broadcasting station or the network server to the external device and a signal received from the external device to the broadcasting station or the network server . That is the image display apparatus may transmit contents included in signals received from the broadcasting station the network server and the external device as well as reproduce them directly.

Referring to the controller may include a Demultiplexer DEMUX a video processor an OSD generator a mixer a Frame Rate Converter FRC and a formatter according to an exemplary embodiment of the present invention. The controller may further include an audio processor not shown and a data processor not shown .

The DEMUX demultiplexes an input stream. For example the DEMUX may demultiplex an MPEG 2 TS into a video signal an audio signal and a data signal. The input stream signal may be received from the tuner the demodulator or the external device interface .

The video processor may process the demultiplexed video signal. For the video signal processing the video processor may include a video decoder and a scaler .

The video decoder decodes the demultiplexed video signal and the scaler scales the resolution of the decoded video signal so that the video signal can be displayed on the display .

If the demultiplexed video signal is for example an MPEC 2 coded video signal the video signal may be decoded by an MPEC 2 decoder.

On the other hand if the video signal is an H.264 encoded DMB or DVB handheld DVB H signal the video signal may be decoded by an H.264 decoder.

The OSD generator generates an OSD signal on its own or according to a user input. For example the OSD generator may generate signals by which a variety of information is displayed as graphic images or text on the display according to user input signals or control signals. The OSD signal may include various data such as a User Interface UI screen a variety of menu screens widgets icons etc.

For example the OSD generator may generate a signal by which a caption of a broadcast image or Electronic Program Guide EPG based broadcasting information is displayed.

The mixer may mix the decoded video signal with the OSD signal and output the mixed signal to the formatter . As the decoded broadcast video signal or the external input signal is mixed with the OSD signal an OSD may be displayed overlaid on the broadcast image or the external input image.

The FRC may change the frame rate of an input image. For example a frame rate of 60 Hz is converted to a frame rate of 120 or 240 Hz. When the frame rate is changed from 60 Hz to 120 Hz the same first frame is inserted between a first frame and a second frame or a predicted third frame is inserted between the first and second frames. If the frame rate is changed from 60 Hz to 480 Hz three identical frames or three predicted frames are inserted between the first and second frames. It is also possible to maintain the frame rate of the input image without frame rate conversion.

The formatter changes the format of the signal received from the FRC to be suitable for the display . For example the formatter may convert a received signal to an RGB data signal. The RGB signal may be output in the form of a Low Voltage Differential Signal LVDS or mini LVDS.

The audio processor not shown of the controller may process the demultiplexed audio signal. For the audio signal processing the audio processor may have a plurality of decoders.

If the demultiplexed audio signal is a coded audio signal the audio processor of the controller may decode the audio signal. For example the demultiplexed audio signal may be decoded by an MPEG 2 decoder an MPEG 4 decoder an Advanced Audio Coding AAC decoder or an AC 3 decoder.

The audio processor of the controller may also adjust the base treble and volume of the audio signal.

The data processor not shown of the controller may process the data signal obtained by demultiplexing the input stream signal. For example if the data signal is an encoded signal such as an EPG which includes broadcast information specifying the start time end time etc. of scheduled broadcast TV or radio programs the controller may decode the data signal. Examples of an EPG include ATSC Program and System Information Protocol PSIP information and DVB Service Information SI . ATSC PSIP information or DVB SI information may be included in the header of a TS i.e. a 4 byte header of an MPEG 2 TS.

The block diagram of the controller illustrated in is an exemplary embodiment of the present invention. Depending on the specification of the controller in real implementation the components of the controller may be incorporated added or omitted.

A platform for the image display apparatus may have OS based software to implement the above described various operations according to an exemplary embodiment of the present invention.

Referring to a platform for the image display apparatus is a separate type according to an exemplary embodiment of the present invention. The platform may be designed separately as a legacy system platform and a smart system platform . An OS kernel may be shared between the legacy system platform and the smart system platform .

The legacy system platform may include a stack of a driver middleware and an application layer on the OS kernel .

On the other hand the smart system platform may include a stack of a library a framework and an application layer on the OS kernel .

The OS kernel is a core of an operating system. When the image display apparatus is driven the OS kernel may be responsible for at least one of hardware driver driving security protection for hardware and processors in the image display apparatus efficient management of system resources memory management hardware interfacing by hardware abstraction multi processing and scheduling associated with the multi processing. Meanwhile the OS kernel may further perform power management.

The hardware drivers of the OS kernel may include for example at least one of a display driver a Wi Fi driver a Bluetooth driver a USB driver an audio driver a power manager a binder driver and a memory driver.

Alternatively or additionally the hardware drivers of the OS kernel may be drivers for hardware devices within the OS kernel . The hardware drivers may include a character device driver a block device driver and a network device driver. The block device driver may need a buffer for buffering data on a block basis because data is transmitted on a block basis. The character device driver may not need a buffer since data is transmitted on a basic data unit basis that is on a character basis.

The OS kernel may be implemented based on any of various OSs such as Unix Linux Windows etc. The OS kernel may be a general purpose open OS kernel which can be implemented in other electronic devices.

The driver lies between the OS kernel and the middleware . Along with the middleware the driver drives devices for operations of the application layer . For example the driver may include a driver s for a microcomputer a display module a Graphic Processing Unit GPU the FRC a General Purpose Input Output GPIO pin a High Definition Multimedia Interface HDMI a System Decoder SDEC or DEMUX a Video Decoder VDEC an Audio Decoder ADEC a Personal Video Recorder PVR and or an Inter Integrated Circuit I2C . These drivers operate in interaction with the hardware drivers of the OS kernel .

In addition the driver may further include a driver for the remote controller especially a later described pointing device. The remote controller driver may reside in the OS kernel or the middleware instead of the driver .

The middleware sits between the OS kernel and the application layer . The middleware may mediate between different hardware devices or different software programs for data transmission and reception between the hard devices or software programs. Therefore the middleware can provide standard interfaces support various environments and enable interaction between tasks conforming to heterogeneous communication protocols.

Examples of the middleware in the legacy system platform may include Multimedia and Hypermedia information coding Experts Group MHEG and Advanced Common Application Platform ACAP as data broadcasting related middleware PSIP or SI middleware as broadcast information related middleware and Digital Living Network Alliance DLNA middleware as peripheral device communication related middleware.

The application layer that resides on the middleware in the legacy system platform may include for example UI applications associated with various menus in the image display apparatus . The application layer may allow editing and updating over a network by user selection. With use of the application layer the user may enter a desired menu among various UIs by manipulating the remote controller during viewing a broadcast program.

The application layer may further include at least one of a TV guide application a Bluetooth application a reservation application a Digital Video Recorder DVR application and a hotkey application.

In the smart system platform the library lies between the OS kernel and the framework forming the basis of the framework . For example the library may include Secure Socket Layer SSL being a security related library WebKit being a Web engine related library c library libc and Media Framework being a media related library such as specifying a video format and an audio format. The library may be written in C or C . Also the library may be exposed to a developer through the framework .

The library may include a runtime with a core Java library and a Virtual Machine VM . The runtime and the library form the basis of the framework .

The VM may be a virtual machine that enables concurrent execution of a plurality of instances that is multi tasking. For each application of the application layer a VM may be allocated and executed. For scheduling or interconnection between instances the binder driver not shown of the OS kernel may operate.

In the smart system platform the framework includes programs on which applications of the application layer are based. The framework is compatible with any application and may allow component reuse movement or exchange. The framework may include support programs and programs for interconnecting between different software components. For example the framework may include an activity manager related to activities of applications a notification manager and a CP for abstracting common information between applications. This framework may be written in Java.

The application layer on top of the framework includes a variety of programs that are executed and displayed in the image display apparatus . The application layer may include for example a core application that has at least one of e mail Short Message Service SMS a calendar a map and a browser. The application layer may be written in Java.

In the application layer applications may be categorized into user undeletable applications stored in the image display apparatus and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus .

With the applications of the application layer a variety of functions may be performed by network access including Internet telephony VoD Web album Social Networking Service SNS Location Based Service LBS map service Web browsing and application search. In addition the user may enjoy games and manage his schedule using applications.

Referring to a platform for the image display apparatus according to another exemplary embodiment of the present invention is an integrated type. The integrated platform may include an OS kernel a driver middleware a framework and an application layer .

Compared to the separate type platform illustrated in the integrated type platform is characterized by the absence of the library and the application layer being an integrated layer. The driver and the framework correspond to the driver and the framework of respectively.

The library of may be incorporated into the middleware . That is the middleware may include both the legacy system middleware and the image display system middleware. As described before the legacy system middleware includes MHEG or ACAP as data broadcasting related middleware PSIP or SI middleware as broadcast information related middleware and DLNA middleware as peripheral device communication related middleware whereas the image display system middleware includes SSL as a security related library WebKit as a Web engine related library WebKit libc and Media Framework as a media related library. The middleware may further include the afore described runtime.

The application layer may include menu related applications a TV guide application a reservation application etc. as legacy system applications and e mail SMS a calendar a map and a browser as image display system applications.

In the application layer applications may be categorized into user undeletable applications that are stored in the image display apparatus and user installable or user deletable applications that are downloaded from an external device or a network and stored in the image display apparatus .

The platforms illustrated in may be general purpose ones that can be implemented in many other electronic devices as well as in image display apparatuses. The platforms may be loaded on the memory the controller or any other processor not shown .

Referring to B and C the remote controller may transmit and receive signals to and from the image display apparatus according to an RF or IR communication standard.

The user may move the remote controller up and down side to side and back and forth . The pointer moves in accordance with the movement of the remote controller as illustrated in B and C. In this context the remote controller may be referred to as a pointing device.

Referring to if the user moves the remote controller to the left the pointer moves to the left accordingly. A sensor of the remote controller detects the movement of the remote controller and transmits motion information corresponding to the result of the detection to the image display apparatus . Then the image display apparatus determines the movement of the remote controller based on the motion information received from the remote controller and calculates the coordinates of a target point to which the pointer should be shifted in accordance with the movement of the remote controller based on the result of the determination. The image display apparatus then displays the pointer at the calculated coordinates.

Referring to while pressing a predetermined button of the remote controller the user moves the remote controller farther from the display . Then a selected area corresponding to the pointer may be zoomed in and enlarged on the display . On the contrary if the user moves the remote controller toward the display the selection area corresponding to the pointer is zoomed out and thus contracted on the display . The opposite case is possible. That is when the remote controller recedes from the display the selection area may be zoomed out and when the remote controller approaches the display the selection area may be zoomed in.

With the predetermined button pressed in the remote controller the up down left and right movements of the remote controller may not be sensed as meaningful. That is when the remote controller recedes from or approaches the display only the back and forth movements of the remote controller are sensed while the up down left and right movements of the remote controller are neglected. Unless the predetermined button is kept pressed in the remote controller the pointer moves in accordance with the up down left or right movement of the remote controller .

The moving speed and direction of the pointer may correspond to the moving speed and direction of the remote controller .

The pointer is an object displayed on the display in correspondence with the movement of the remote controller . Therefore objects of various shapes other than an arrow illustrated in B and C are available for the pointer . For example the pointer may be shaped into a dot a cursor a prompt a thick outline etc. The pointer may be displayed across a plurality of points such as a line and a surface as well as at a single point on horizontal and vertical axes.

Referring to the remote controller may be a pointing device. The pointing device may include a wireless communication module a user input portion a sensor unit an output portion a power supply a memory and a controller .

The wireless communication module transmits signals to and or receives signals from the image display apparatus . The wireless communication module may include an RF module for transmitting RF signals to and or receiving RF signals from the image display apparatus according to an RF communication standard. The wireless communication module may also include an IR module for transmitting IR signals to and or receiving IR signals from the image display apparatus according to an IR communication standard.

The pointing device transmits motion information representing the movement of the pointing device to the image display apparatus through the RF module in this exemplary embodiment. The pointing device may also receive signals from the image display apparatus through the RF module . When needed the pointing device may transmit commands to the image display apparatus through the IR module such as a power on off command a channel switching command or a sound volume change command.

The user input portion may include a keypad a plurality of buttons a touchpad and or a touch screen. The user may enter commands to the image display apparatus by manipulating the user input portion . If the user input portion includes a plurality of hard key buttons the user may input various commands to the image display apparatus by pressing the hard key buttons. Alternatively or additionally if the user input portion includes a touch screen displaying a plurality of soft keys the user may input various commands to the image display apparatus by touching the soft keys. The user input portion may also include various input tools other than those set forth herein such as a scroll key and or a jog key which should not be construed as limiting the present invention.

The sensor unit may include a gyro sensor and or an acceleration sensor . The gyro sensor may sense the movement of the pointing device for example in X Y and Z axis directions and the acceleration sensor may sense the moving speed of the pointing device .

The output portion may output a video and or audio signal corresponding to a manipulation of the user input portion or corresponding to a signal received from the image display apparatus . The user may easily identify whether the user input portion has been manipulated or whether the image display apparatus has been controlled based on the video and or audio signal output by the output portion .

The output portion may include a Light Emitting Diode LED module which is turned on or off whenever the user input portion is manipulated or whenever a signal is received from or transmitted to the image display apparatus through the wireless communication module a vibration module which generates vibrations an audio output module which outputs audio data and or a display module which outputs video data.

The power supply supplies power to the pointing device . If the pointing device is kept stationary for a predetermined time or longer the power supply may for example reduce or cut off supply of power to the pointing device in order to save power. The power supply may resume the power supply if a predetermined key on the pointing device is manipulated.

The memory may store various application data required for controlling or driving the pointing device . The pointing device may wirelessly transmit signals to and or receive signals from the image display apparatus in a predetermined frequency band with the aid of the RF module . The controller of the pointing device may store information regarding the frequency band used for the pointing device to wirelessly transmit signals to and or wirelessly receive signals from the paired image display apparatus in the memory and may then refer to this information for a later use.

The controller provides overall control to the pointing device . For example the controller may transmit a signal corresponding to a key manipulation detected from the user input portion or a signal corresponding to a motion of the pointing device as sensed by the sensor unit to the image display apparatus .

Referring to the image display apparatus may include an application manager and an application host for implementing applications. The application manager and the application host may reside in the afore described controller for example in a processor not shown of the controller .

The application manager is responsible for overall management of applications such as installation execution management and deletion. The overall management may cover installation of an add on application by a third party.

The application manager may include an application browser for executing applications an application controller for managing and providing overall control to applications a security checker for ensuring security for application installation execution management and deletion and an application downloader for installing applications.

The application host is added to the image display apparatus in order to support running of the application manager . The application host may include a host agent and an open Application Programming Interface API host .

The host agent transmits and receives status information about host software of the image display apparatus and key events of the remote controller .

The open API host calls an open API of an application and receives a response. The application transmits the open API in response to the call from the open API host . The open API may be provided in the form of an open API library . The application may register to the application manager through the open API library and thus use functions provided by the host software.

The download and installation operation is for the case where the image display apparatus accesses a content server via the application manager and downloads contents particularly applications from the content server .

Referring to the application host in the image display apparatus transmits a download instruction to the application downloader of the application manager in step S.

As described before the application host may be added to the host software of the image display apparatus to control reception and execution of applications. For example the application host may be added to the host software of the image display apparatus and control application reception and execution independently of broadcast signal output.

The download instruction may be transmitted when the user selects the application downloader on a UI using the remote controller or when the application downloader automatically runs.

Upon receipt of the download instruction the application downloader transmits an application list request to the content server or a network server and downloads the application list from the content server or the network server in step S. The application list request may be an application list update request.

A network address of the content server or the network server may be preset received from the user or acquired by predetermined signaling or through a predetermined channel.

The downloaded application list is displayed on the display . With the application list displayed on the display a user input signal or a control signal corresponding to selection of an application from the application list is received from the remote controller in step S.

The application downloader downloads the selected application from the content server or the network server in step S. When downloading the selected application the application downloader may use metadata included in the application list.

The security checker authenticates the downloaded application using authentication data that is carried in a header of the application or certain metadata for the application in step S.

If the downloaded application turns out valid in the authentication the application downloader installs the downloaded application using the header of the application or the metadata in step S.

If an installation path is signaled by the header of the application or the metadata the application downloader may install the application according to the installation path.

The application browser may output a list of downloaded applications to the display . Upon receipt of a user input signal or control signal requesting execution of one or more downloaded applications from the remote controller the application controller executes the selected applications according to a control command received from the application host .

Because the application manager operates independently of other functions of the image display apparatus as stated before it may execute all of selected applications even though a plurality of applications are selected for execution.

Referring to a list of various applications available within the connected server is displayed on the display . The application list may include icons representing the applications and brief descriptions of the applications. As the image display apparatus allows full browsing the icons or descriptions may be displayed enlarged so that the user can easily identify the applications.

Referring to the user selects an application from the application list using the pointer corresponding to the remote controller . Therefore the selected application may be downloaded easily.

Referring to if the user selects an application list view menu by manipulating the remote controller a list of applications stored in the image display apparatus is displayed on the display . While only icons representing the applications are shown in to which the present invention is not limited a brief description may be provided for each application as in . Accordingly the user can easily identify the applications.

Referring to the user selects an application from the application list using the pointer corresponding to the remote controller . Thus the selected application can be executed easily.

While it has been described that a specific item is selected by moving the pointer which moves according to a user s motion with the remote controller illustrated in this is merely an exemplary application. Therefore the present invention is not limited to it and many other examples may be contemplated.

For example a specific item may be selected using a cursor displayed on a screen by manipulating both a directional key and an OK key provided in the remote controller or provided as local keys.

In another example if the remote controller includes a touchpad a specific item may be selected by touching the touchpad and thus moving the pointer on the display .

The image display apparatus is capable of full browsing when displaying a mail service page in accordance with the exemplary embodiment of the present invention. Therefore the user can enjoy the mail service conveniently.

The image display apparatus may divide the screen of the display into at least two areas for displaying images according to an exemplary embodiment of the present invention.

A first display area in a lower part of the display may display icon objects. Icon objects may include objects representing applications. The user selects one of the icon objects of the applications using the pointer corresponding to the remote controller in by way of example. Hence the selected application may be executed.

A second display area lies on the first display area for displaying a variety of images or information.

The first area may display contents such as broadcast images. The contents may be displayed on the first area in a detail view mode. Specifically the entire contents of a received broadcast image or an image corresponding to a running application may be displayed up to details. Notably the resolution of the input image may be changed taking into account the display area of the display .

The second area may display real time or up to date information received over a network. This information may be updated periodically. Depending on the amount of the information the information may be displayed in summary that is in a summary view mode.

The third area may display information that can be acquired from an application. The information may be displayed in summary that is in the summary view mode according to the amount of the information.

The first display area may further include a enlarging reducing command object . The enlarging reducing command object may be regarded as an extension of the first display area . When the user drags the enlarging reducing command object a command for enlarging or reducing the first display area may be input to the image display apparatus and thus the size of the first display area may be changed. In addition the size of the second display area may be changed along with a change in the size of the first display area which will be described later with reference to .

Similarly the user may change the size of at least one of the first second and third areas and in the second display area using the pointer corresponding to the remote controller .

While not shown a enlarging reducing command object may be provided in each of the first second and third areas and . Using the enlarging reducing command objects the first second and third areas and may be enlarged or reduced to a user desired size. It is also possible to enlarge or reduce each area by dragging an edge or vortex of the area using the pointer .

Referring to compared to the screen composition illustrated in the screen composition is characterized in that as the first display area is enlarged the second display area may be reduced.

For example if the user drags upward the zoom in zoom out command object using the pointer as illustrated in the first display area is displayed enlarged while the second display area is displayed reduced accordingly.

Icon objects are displayed in the first display area . As the first display area gets enlarged more icon objects may be displayed in the first display area .

Referring to the application downloader requests information about the version of an application list to the content server or the network server in step S.

The application list version request may be transmitted to the content server or the network server when the user selects an application download menu using the remote controller or when an application list update message is received from the content server or the network server.

The content server or the network server transmits the information about the version of an application list to be transmitted to the application downloader in step S.

Upon receipt of the application list version information the application downloader determines whether to update a currently stored application list by comparing the received version information with information about the version of the currently stored application list in step S.

If the received version information is different from the stored version information or if the current application list is of a lower version and thus needs updating the application downloader requests an application list update to the content server or the network server by an update message in step S. The update message may be transmitted by HyperText Transfer Protocol HTTP GET POST or Simple Object Access Protocol SOAP .

The content server or the network server compresses the application list in step S and transmits the compressed application list to the application downloader in step S.

Along with the update request the application downloader may transmit system information about the image display apparatus or the application host to the content server or the network server. Then the content server or the network server may make the application list by extracting applications that can be executed according to a control command from the application host .

The application downloader receives the compressed application list in step S and decompresses and stores the application list in step S. The compression and decompression of the application list may be carried out in various manners according to exemplary embodiments of the present invention. The application list may be stored in eXtensible Markup Language XML .

Upon completion of downloading the application list the application downloader may transmit information about a device Identifier ID of the image display apparatus and the version of the downloaded application list to the content server or the network server. The content server or the network server may preserve the received information and determine the version of the current application list that the image display apparatus has at the next time when the image display apparatus downloads an application list.

Referring to when the user selects an application download item using the pointer of the remote controller from the display on which an application list provided by the application browser is displayed an application list may be downloaded in the procedure illustrated in .

When the application list needs to be updated a screen indicating an application list is being downloaded may be displayed as illustrated in .

When the application list is completely downloaded and decompressed a screen indicating the application list is being decompressed may be displayed as illustrated in .

In this manner the application list may be received efficiently especially as the application list can be downloaded only when it has been changed.

As is apparent from the above description of the exemplary embodiments of the present invention since a user installable or user deletable application or application list is downloaded over a network according to a user input signal received from a remote controller a user can easily use his desired application with increased use convenience.

Especially as the user selects an intended application using the remote controller from an application list available in a network displayed on a display the user can easily download the application from the network.

Also the user selects an intended application using the remote controller from an application list available in an image display apparatus displayed on the display the user can easily execute the selected application.

The version of an application is checked and updated when needed. Thus the application list can be received efficiently.

The image display apparatus and the method for operating the same according to the foregoing exemplary embodiments are not restricted to the exemplary embodiments set forth herein. Therefore variations and combinations of the exemplary embodiments set forth herein may fall within the scope of the present invention.

The method for operating an image display apparatus according to the foregoing exemplary embodiments may be implemented as code that can be written on a computer readable recording medium and can thus be read by a processor. The computer readable recording medium may be any type of recording device in which data is stored in a computer readable manner. Examples of the computer readable recording medium include a ROM a RAM a CD ROM a magnetic tape a floppy disc an optical data memory and a carrier wave e.g. data transmission through the internet . The computer readable recording medium can be distributed over a plurality of computer systems connected to a network so that computer readable code is written thereto and executed therefrom in a decentralized manner. Functional programs code and code segments needed for realizing the embodiments herein can be construed by one of ordinary skill in the art.

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims.

