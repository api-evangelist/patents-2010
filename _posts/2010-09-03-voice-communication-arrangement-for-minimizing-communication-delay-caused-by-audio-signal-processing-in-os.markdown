---

title: Voice communication arrangement for minimizing communication delay caused by audio signal processing in OS
abstract: A voice communication arrangement having a voice communication program installed in a computer loaded with a versatile OS thereon includes a voice data input/output function for passing through the OS voice data produced from voice sound captured by a microphone of the arrangement or received from another voice communication device, when connected to the arrangement, without being processed by the OS as audio data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09098235&OS=09098235&RS=09098235
owner: Oki Electric Industry Co., Ltd.
number: 09098235
owner_city: Tokyo
owner_country: JP
publication_date: 20100903
---
The present invention relates to a voice communication arrangement for causing a computer such as a personal computer commercially available to function as a telephone terminal or a softphone.

In recent years personal computers having an application for softphone loaded thereon have been used as telephone terminals. For example a personal computer having a connector such as a USB Universal Serial Bus interface connectable to an external device is connected through the connector to an external voice input output device such as a headset or a handset comprising a microphone and a loudspeaker by means of which an operator or user may be on the phone. Further for example an audio device dedicated to audio signals may be used as the above described external voice input output device to enjoy voice communication of high sound quality.

Forwarding and receiving of voice signals between a personal computer and an external voice input output device have conventionally been taken place by means of a general of standard audio interface mounted on an OS Operating System of the personal computer due to the following two factors.

First since most of personal computers available on the market have a built in sound device mounted thereon which is adapted to analog input output and have a preinstalled driver dedicated to the OS installed in the computers they have been used by many of users. Some of users giving weight to sound quality have separately used an external voice input output device such as a USB headset. However they have still used the standard mechanism of the OS including drivers and PnP Plug and Play functions as they are with the result that voice signals are input and output on the same audio route as the built in device.

Second in order to accomplish sound volume control sound file playback for generating audible sound and a mixing function as well as to cooperate with other applications API Application Programming Interface has been used.

In U.S. Pat. No. 7 567 549 to Adan et al. there is proposed a computer telephony interface adaptor which can be connected between a telephone network and a personal computer having a headset or the like connected thereto to process voice signals thereby reducing processing work on the personal computer and delay in the processing.

However use of the voice input output interface and drivers generally included in the OS is based on the premises of compatibility with other applications such as reproduction of music thus causing thanks to the versatility expanding the processing to be dealt with many of those software applications which possibly cause excessive overhead thus ultimately resulting in delay. In order to overcome the problem described above there has been an interface designed with delay partially taken into account for example ASIO Audio Streaming Input Output . Such an interface is specialized for reproduction and play of music and not effectively applicable to both way real time communications.

Generally the newer version of an OS remarkably tends to exhibit more excessive overhead so as to cause more serious delay than before notwithstanding the performance of hardware including personal computers being substantially improved.

The delay may be raised by a variety of causes. For example when an application starts up with plural applications simultaneously active so as to render the delay suddenly increase due to the processing on the background the delay often has a negative effect for example on the operation of an echo canceller and the like.

Such a variety of problems described above has become a significant bottleneck to developing voice communication services thus rendering the range of applications of softphones limited.

Adan et al. intends to achieve reduced delay whereas requiring an adaptor dedicated therefor and thus it can hardly be said that it is a solution applicable to a variety of users.

It is therefore an object of the present invention to provide a voice communication arrangement capable of reducing delay in processing voice signals regardless of intermediation of an OS.

In accordance with the invention a voice communication arrangement having a voice communication program installed in a computer loaded with an operating system including a voice data processing feature comprises a first audio device detachably connectable to the computer and including a microphone for catching a voice of a near end talker to produce corresponding voice data and a loudspeaker for producing as an audible sound a voice of a far end talker from voice data transmitted from a voice communication device when connected to the computer and the voice communication program comprises a first voice data input output function operative in response to the first audio device being connected to the computer for causing the voice data received from or to be transmitted to the voice communication device to pass the operating system without intermediation of the voice data processing feature to forward or receive the voice data to or from the first audio device.

In accordance with the invention a voice communication program for functioning when installed in a computer a voice communication arrangement in which the computer has an operating system loaded thereon and including a voice data processing feature the computer having a first audio device detachably connectable to the computer the first audio device comprising a microphone for catching a voice of a near end talker to produce corresponding voice data and a loudspeaker for producing as an audible sound a voice of a far end talker from voice data transmitted from a voice communication device when connected to the computer causes the computer to serve as a first voice data input output function operative in response to the first audio device being connected to the computer for causing the voice data received from the voice communication device to pass the operating system without intermediation of the voice data processing feature to forward or receive the voice data to or from the first audio device.

In accordance with a voice communication arrangement of the present invention delay in processing voice signals can be minimized even when an OS is intervened in forwarding and receiving voice data to and from an external audio device detachably connected thus attaining high sound quality.

The inventive concept disclosed in the application may also be defined in ways other than in the claims presented below. The inventive concept may consist of several separate inventions particularly if the invention is considered in light of explicit or implicit subtasks or from the point of view of advantages achieved. In such a case some of the attributes included in the claims may be superfluous from the point of view of separate inventive concepts. Within the framework of the basic inventive concept features of different embodiments are applicable in connection with other embodiments.

With reference to the accompanying drawings preferred embodiments of a voice communication arrangement according to the invention will be described in detail when applied to a personal computer commercially available to implement a telephone terminal such as a softphone.

The dedicated USB audio device in this embodiment includes a USB interface having a voice and audio signal input output function and may comprise a loudspeaker and a microphone which may be built therein or detachably i.e. externally connected thereto.

The dedicated USB audio device is adapted to send and receive voice data and to and from the personal computer . Particularly with the embodiment the data are not processed as audio data by the OS Operating System installed in the personal computer . In other words the OS is blind to the sort of data being audio or voice.

Therefore the dedicated USB audio device as compared to a common audio device currently available on the market such as an audio device employing AC97CODEC HD Audio or the like may be different in function in that forwarding and receiving of voice data and to and from the personal computer are performed by the OS in a mode of being unconscious of the fact that the data and are voice data. Namely the dedicated USB audio device may forward and receive voice data to and from the personal computer in the same mode as data that are digitally processed by the personal computer and transferred to and from a USB memory when connected to the computer .

The dedicated USB audio device comprises a USB controller or USB interface I F device for controlling and executing data transfer to and reception from the personal computer an analog to digital and digital to analog converter ADC DAC for converting analog voice signals caught by the microphone to corresponding digital voice data as well as converting digital voice data given from the personal computer to corresponding analog voice signals and an interface I F for establishing connection to the loudspeaker and the microphone .

The USB controller may be adapted to transfer voice data in such a form that the OS is unconscious of the fact that the data are audio data.

As will be described later as the dedicated USB audio device a common USB audio device such as an audio device employing AC97CODEC HD Audio or the like as stated above may be employed. Such a common USB audio device may be recognized as the dedicated USB audio device by means of recognition procedure of the OS so that the voice data and transferred from and to the audio device will not be processed by the OS as audio data.

Returning to the personal computer may comprise a VoIP Voice over Internet Protocol engine the OS a USB controller or USB I F device a built in loudspeaker a built in microphone and a built in ADC DAC or built in audio device as components related to telephone communication. In the description the VoIP engine and the OS of which the substance is constituted of software will be referred to as a VoIP engine and an OS respectively which cover the possibility of hardware such as a CPU Central Processor Unit for executing the software.

The VoIP engine mainly comprises an assembler disassembler a call controller a coder decoder or codec an audio controller a voice data input output I O function and an audible sound data output function .

The assembler disassembler is adapted to disassemble a packet received by a communication section not shown from a telephone network. Thus signals or data are designated with reference numerals of connections on which they are conveyed. When the received packet is a call control packet the assembler disassembler disassembles the packet to obtain control data and provides them to the call controller . When the received packet is a voice packet the packet assembler disassembler disassembles the packet to obtain coded voice data and provides them to the coder decoder .

Further the assembler disassembler is adapted to assemble a packet including call control data from the call controller and or a coded voice data from the coder decoder to transmit the packet to the telephone network from the communication section.

The call controller is adapted to execute call control such as establishment of a speech path when a call is originated or terminated and disconnection of a speech path when a call is released. In addition the call controller is arranged to be given through the OS a key touch signal or the like generated by a keyboard not shown when manipulated by the user.

The call controller when necessary to generate a tonal output of a predetermined audible tone or sound such as ring tone and ringing signal in some predominant stages of the call control takes out the audible sound data stored therein and provides them to the audible sound data output function or section . In the context the term section may be referred to part of software and sometimes to hardware implementing the function defined by the software.

The coder decoder is adapted to receive and decode the coded voice data to produce and send decoded voice data to the voice data input output function or section via the voice controller . Further the coder decoder is adapted to receive and encode voice data from the voice data input output function via the voice controller to produce and transfer the coded voice data to the assembler disassembler .

The voice controller is provided inside the VoIP engine since this illustrative embodiment is structured to allow voice data from the coder decoder and voice data from the audio device to bypass an audio controller in the OS . The audio controller is adapted to process voice data for volume control sound file playback or media play audio recording mixing and the like. The voice controller in this embodiment processes the received voice data from the coder decoder to produce output voice data and produces the transmitting voice data from voice data fed from the voice data input output function .

The voice data input output function is adapted to transfer the voice data to and receive the voice data from the dedicated USB audio device via the OS . In this embodiment as described above transfer and reception of the voice data and to and from the dedicated USB audio device are performed in a mode of the USB audio device being unconscious of the fact that the data are audio data and thus the voice data input output function processes the voice data and so that the input output function can forward and receive the data and in a fashion similar to the case of general digital data such as alphanumeric data.

For example between the voice data input output function and the USB controller of the dedicated USB audio device voice data are forwarded and received to and from each other in a form of USB packet having voice data such as PCM Pulse Code Modulation voice data contained therein so as to make the OS unaware of the fact that the voice data are audio data.

The audible sound data output function is adapted to receive the audible sound data from the call controller and produce from the data audible sound data in a form compatible with the standard or general interface of the OS to provide the data to the OS .

The USB controller is adapted to transfer when interconnected to the mating USB controller of the dedicated USB audio device data and on the USB.

The built in loudspeaker and microphone are mounted on the personal computer . In this embodiment when the personal computer acts as a telephone terminal the loudspeaker and microphone may simply play a function of certain level such as production of audible tone or signal from the audible sound data .

The built in ADC DAC is adapted to convert analog voice signals captured by the built in microphone to corresponding digital voice data as well as convert digital voice data given from the OS to corresponding analog voice signals to transfer and receive signals to the built in loudspeaker and from and the built in microphone .

The OS may be for example an existing general purpose or versatile OS such as Windows Linux Mac OS Trademarks etc. So far as the function of telephone terminal such as softphone the OS may comprise a dedicated device driver a USB driver an audio controller and a built in audio device driver or built in ADC DAC driver .

The dedicated device driver and the USB driver may be involved in forwarding and receiving of voice data and while the audio controller and the built in device driver may be involved in operation of emanating audible sound produced from the audible sound data .

The dedicated device driver is dedicated to rendering the dedicated USB audio device when connected function as a dedicated audio interface of the dedicated USB audio device performing transmission and reception of data and rather than a standard or general audio interface like the audio controller .

Specifically the dedicated device driver executes together with the USB driver transparent transfer of the voice data and between the VoIP engine and the dedicated USB audio device . In other words the dedicated device driver allows the transfer data and e.g. in the form of USB packets having voice data included therein in this embodiment to be transferred between the VoIP engine and the dedicated USB audio device without being processed as audio data.

The dedicated device driver may implement a function equivalent to that of a driver for a USB audio device such as usbaudio.sys in case of Windows trade name whereas it does not execute any processes other than such data transfer i.e. audio processes such as volume control sound file playback audio recording mixing and the like are not dealt with. In other words the dedicated device driver in this embodiment may be adapted to execute only data transmission process.

The USB driver is adapted to drive data transfer i.e. USB transfer in this embodiment between the USB controller and the USB controller of the dedicated USB audio device . Further the USB driver is adapted to recognize that the dedicated USB audio device is inserted in a USB connector not specifically shown of the personal computer .

In order to allow a commercially available USB audio device to be recognized as the dedicated USB audio device rather than a general audio device it may be preferable to rewrite beforehand its manufacturer supplied device information necessary for the commercially available USB driver to activate its PnP Plug and Play function such as inf file in case of Windows trade name with the information e.g. ID IDentification such as vender or product ID of the dedicated USB audio device .

In such a case the dedicated driver may be enabled when the device is connected to the personal computer via its USB connector and the USB driver receives ID information from the dedicated USB audio device to recognize the ID of the interconnected device being ID of the dedicated USB audio device .

Applying the above described solution makes it possible for a versatile USB audio device to be recognized and started up without being subject to special modification remodeling or the like.

The audio controller which may be a general or standard audio controller the OS has is adapted to process the audible sound data such as volume control sound file playback recording mixing and the like to produce processed sound data .

In operation when the voice communication arrangement establishes a call connection upon a call being originated therefrom or terminated thereon the call controller executes a sequence of establishing the call.

At either of stages of the call control when it becomes necessary to produce a tonal output of audible sound the call controller sends appropriate audible sound data to the audible sound data output function . In response the audible sound data output function sends the audible sound data to the OS together with information representing that the audible sound data is audio data.

In the OS in turn the audible sound data are processed by the audio controller and the built in device driver which are general interfaces for audio and voice data and thereafter the processed audible sound data are passed to the built in ADC DAC in which they are converted to corresponding analog signals which are reproduced by the built in loudspeaker in the form of audible sound.

As described above at the call connection control stage audible sound or tone that is scarcely problematic in terms of delay is thus dealt with the general interface of the OS .

When a call connection is established to a called or calling party under the call control of the call controller the users on both devices i.e. far end and near end users will start telephone conversation. Of course the near end user may be of the voice communication arrangement .

A voice packet conveying voice information of a far end talker from a call connected telephone device not shown is received by the assembler disassembler where it is disassembled and the coded voice data are taken out. The coded voice data are then decoded by the coder decoder into the voice data . The voice data after being subject to processing such as volume control and the like by the voice controller are converted by the voice data input output function to transfer data in a form capable of passing through or blind to the OS as they are and will then be sent to the OS . Such a form may be for example a USB packet.

In the OS the dedicated device driver and the USB driver permit the transfer data thus provided to pass therethrough as they are and in turn sent from the USB controller to the USB controller of the dedicated USB audio device .

The USB controller disassembles the transfer form e.g. a USB packet or packets in this embodiment of the voice data and restores voice data therefrom. The voice data are converted by the ADC DAC to corresponding analog voice signals which are then sent via the interface to the loudspeaker where they will be reproduced in the form of audible sound.

When the near end user talks on the microphone the voice is caught by the microphone to be transduced into a voice signal which is sent through the interface to the ADC DAC where the voice signal is converted to corresponding digital signals . In the USB controller the voice data are converted into transfer data namely assembled in a form of USB packet or packets capable of passing through the OS as they are. The USB packets are then sent to the personal computer together with ID information of the device .

In the personal computer the transfer data are received by the USB controller . However since the transfer data are recognized by the USB driver as data from the dedicated USB audio device by means of its ID information the transfer data will be given to the USB driver under the control of the dedicated device driver and the USB driver without disassembling the transfer form thereof i.e. USB packets with the instant illustrative embodiment. The transfer data are passed through the USB driver and the dedicated device driver as they are and given to the voice data input output function .

In the voice data input output function the transfer form of the transfer data is released i.e. the USB packet or packets are disassembled to thereby restore the voice data which will then be transferred to the voice controller . In the voice controller the voice data are subjected to necessary voice processing to be output as the voice data which are then sent to the coder decoder even when the voice data have not been substantially processed. The processed voice data are encoded by the coder decoder into the coded data which are assembled by the assembler disassembler into a packet or packets which will be transmitted to the telephone network.

In summary according to the instant embodiment a dedicated transmitter receiver interface particularly logics is prepared to provide a dedicated route for passing only voice data requiring stricter real time transmission while a general purpose interface is used for media processing such as processing of audible tone with the use of an audio device provided as standard for an OS. As the result delay of voice data otherwise caused by audio processing by an OS can be minimized because the data are not passed through a voice processing route or feature of the OS.

Further since voice data can pass IP networks it is possible for the illustrative embodiment to transmit and receive broadband voice data. If the OS is not compatible in voice data processing with a broadband application then high sound quality could not be accomplished. According to the instant embodiment however since voice data are simply passed through the OS as they are and also the external or detachable dedicated USB audio device is applied it is possible to accomplish high sound quality.

Specifically according to the present embodiment it is possible to achieve both way transmission and reception of media streams upon which the VoIP system relies with high sound quality almost in real time.

Next an alternative preferred embodiment will be described in detail with reference further to in which a voice communication arrangement A in accordance with the invention are also applied to a commercially available personal computer A so as to serve as a softphone terminal. is a schematic block diagram showing the functional configuration of the personal computer A applied to the voice communication arrangement A. Like components are designated with the same reference numerals.

In the personal computer A applied to the voice communication arrangement A comprises a plurality of e.g. two USB connectors to which the dedicated USB audio device and a general or standard USB audio device can be connected. In the following from the viewpoint of emphasizing the characteristic features of the dedicated USB audio device when applied to the voice communication arrangement A of the alternative embodiment the dedicated USB audio device will hereinafter be referred to as a reduced delay USB audio device but its substance may be the same. shows the personal computer A having the reduced delay USB audio device and the general USB audio device connected.

The general USB audio device may be an existing common USB audio device. The reduced delay USB audio device and the general USB audio device are different from each other in constituent elements of the OS A which will process the data transferred to and from the devices and . As shown in the general USB audio device has a loudspeaker and a microphone interconnected thereto as well as comprises a USB controller or USB I F device an ADC DAC and an I F which are interconnected as depicted.

The USB audio device in this alternative embodiment is adapted to receive from the personal computer A a voice signal representing voice information of a far end talker in addition to an audio signal representing the audible sound data . The USB audio device is further adapted to receive an analog voice signal of a near end talker and produce a digital voice signal to supply the latter to the personal computer A.

In use the USB controller of the reduced delay USB audio device is connected to the USB controller of the personal computer A while the USB controller of the general USB audio device is connected to a USB controller or a USB I F device of the personal computer A.

Note that the personal computer A may include the built in loudspeaker the built in microphone and the built in ADC DAC which are however omitted from merely for avoiding complexity.

In the personal computer A shown in the OS A may comprise in addition to the dedicated device driver and the USB driver shown in an audio controller a device driver or USB audio driver and a USB driver that may be rendered active when transferring voice and audio data from and to the general USB audio device . The audio controller is may be same as the audio controller shown in .

The OS A further comprises a connected device manager . The connected device manager in this embodiment is adapted for receiving connecting information and from the USB controllers and respectively to manage what type of USE device is connected to which one of the USE connectors. Of course the manager may receive connecting information and from other components such as the drivers and .

The personal computer A may include a VoIP engine A as shown in . The VoIP engine A comprises a general voice input output function A and a device determiner in addition to the assembler disassembler the call controller the coder decoder the voice controller the voice data input output function .

The general voice data input output function A is provided in place of the audible sound data output function included in the embodiment shown in and is adapted to transmit and receive voice data including audible sound data to and from a processing system constituted of the audio controller the device driver and the USB driver in the OS A. In other words the general voice data input output function A may be enabled when the general USB audio device is connected to the personal computer A.

The device determiner is adapted to determine which audio device or to be used based on management information provided from the connected device manager in the OS A. In the instant alternative embodiment the determiner sends resultant information to the call controller so as to control data flow in the personal computer A.

Specifically when audible tonal sound has to be produced in the call control stage of establishing or disconnecting a call connection the device determiner decides to select the general USB audio device to be used if the general USB audio device is connected while the determiner selects the built in loudspeaker to be used if the general USB audio device is not connected.

During a telephone call connection established the device determiner selects the reduced delay USB audio device to be used as a voice input output device if the reduced delay USB audio device is connected regardless of whether or not the general USB audio device is connected.

Otherwise during a telephone call connection established the device determiner selects the general USB audio device to be used as a voice input output device if the reduced delay USB audio device is not connected but the general USB audio device is connected.

During a telephone call connection established when neither the reduced delay USB audio device nor the general USB audio device is connected the device determiner selects the built in loudspeaker and the built in microphone to be used as a voice input output device for the call connection.

When the reduced delay USB audio device is used as a speech sound input output device the device determiner causes the processing system constituted of the assembler disassembler the coder decoder the voice controller and the voice data input output function to be active. When the general USB audio device is used as a voice input output device the determiner causes the processing system constituted of the assembler disassembler the coder decoder and the general voice data input output function A to actively function.

Now when the general USB audio device is connected if an audio application such as software for playing background music other than the VoIP engine A is in operation then the general USB audio device is used for audio data from the application . In such a case when the general USB audio device is not used as a speech sound input output device the audio data from the audio application are delivered from the general USB audio device to be generated as audible sound. When the general USB audio device is used as a speech sound input output device the audio controller synthesizes the data from the audio application with the voice data from the general voice data input output function A to deliver the resultant data to the general USB audio device to produce corresponding audible sound.

To execute these processes when the device determiner transmits or receives voice data to or from the OS A the determiner selects an appropriate API Application Program Interface or system call in case of Linux trade name of the OS A in conformity to specific devices currently opened. Specifically when controlling the general USB audio device the determiner may select an API for transmitting and receiving PCM Pulse Code Modulation signals to use the general voice data input output function A while selecting a USB control AIP to use the voice data input output function when controlling the USB device .

Thus the alternative embodiment shown in when using the reduced delay USB audio device as a speech sound input output device can accomplish the advantages similar to those of the embodiment shown in .

Further in accordance with the alternative embodiment speech sound signals can be transmitted and received in the most appropriate form in dependence upon how and which external devices are connected. Still further in accordance with the alternative embodiment it is possible to use the VoIP engine in combination with another audio application such as .

The alternative embodiment shown in is thus adapted to determine a device for use in inputting and outputting speech sound signals in dependence upon whether or not the reduced delay USB audio device and or the general USB audio device are connected. The system may be adapted to determine a device for use in inputting and outputting speech sound signals in response to a command from an application such as an application higher in layer than the VoIP engine A other than the VoIP engine A in addition to how the reduced delay USB audio device and or the general USB audio device are connected.

A further alternative embodiment may be provided in which the VoIP engine or A has a list of USB audio devices usable for the VoIP engine A prepared beforehand. In the instant embodiment when an audio device which is not included in the list is connected to the personal computer or A the computer may process audio data as if the unlisted audio device were not connected thereto.

The respective preferred embodiments described above are adapted to use no audio controller that the OS has but a voice controller included in the VoIP engine for compensating for such an audio controller. Such compensation may be taken place with another solution. For example when the dedicated or reduced delay USB audio device comprises a sound volume control function a command for controlling sound volume may be issued from the VoIP engine to the dedicated or reduced delay USB audio device so as to control sound volume.

Further in the respective preferred embodiments described above the dedicated or reduced delay USE audio device cannot be used as a general USB audio device such as . Use may be made of a USB audio device which is usable as both the dedicated or reduced delay USB audio device and the general USB audio device . For example a single USB audio device may be provided with plural e.g. two pieces of ID information so as to enable the user to manipulate its setting switch to selectively set the single USE audio device to function as either of the dedicated or reduced delay USB audio device and the general USB audio device .

Still further in the respective preferred embodiments described above the dedicated device driver transparently transmits and receives transfer data. Use may be made of the dedicated or reduced delay USB audio device adapted to render its optional function effective at the time of being connected to the USB connector of a personal computer. For example user information may be stored beforehand in the dedicated or reduced delay USB audio device under the control of the VoIP engine and the stored user information will be read out for user authentication when the dedicated or reduced delay USB audio device is connected.

The respective preferred embodiments described above use USB interfaces the most popular general purpose PC Personal Computer interface. Other general purpose interfaces may be applied such as FireWire IEEE Institute of Electrical and Electronic Engineers 1394 Bluetooth trade name PC card interfaces PCMCIA Personal Computer Memory Card International Association and CardBus and PCI Peripheral Components Interconnect bus interface.

Further the respective preferred embodiments described above are directed to a personal computer as a computer or information processor having an OS installed. However the invention is applicable to any forms of processor device as far as a versatile operating system or system control program can be installed. For example the invention is applicable to not only general or popular personal computers but also so called netbooks or mini notebooks and mobile personal computers. Also for example the invention is applicable to multimedia internet devices MIDs and ultra mobile PCs UMPCs .

The entire disclosure of Japanese patent application No. 2009 222664 filed on Sep. 28 2009 including the specification claims accompanying drawings and abstract of the disclosure is incorporated herein by reference in its entirety.

While the present invention has been described with reference to the particular illustrative embodiments it is not to be restricted by the embodiments. It is to be appreciated that those skilled in the art can change or modify the embodiments without departing from the scope and spirit of the present invention.

