---

title: System and method for capturing parameters and recording events in portable devices with digital television receiver
abstract: A system and method for capturing and recording parameters of events on portable devices with a digital television receiver, a method for remote configuration of service parameters for capturing and recording events on portable devices, as well as a portable device and server. More specifically, a system and method for capturing audience data, the method for remote configuration of audience data capture service, especially adapted for digital TV services on portable devices such as mobile phones, smartphones, and personal digital assistants, among others, that helps in remotely setting up the service. Another aspect of the present architecture is the fact that it is completely based on software, using only resources that are already present in portable devices with an embedded service.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08850463&OS=08850463&RS=08850463
owner: 
number: 08850463
owner_city: 
owner_country: 
publication_date: 20101230
---
The present invention relates to a system and method for capturing and recording parameters of events on portable devices with digital television receiver a method for remote configuration of service parameters for capturing and recording events on portable devices as well as portable device and server. More specifically a system and method for capturing audience data the method for remote configuration of audience data capture service especially adapted for digital TV services on portable devices such as mobile phones smartphones personal digital assistants PDA among others.

The present invention is necessary due to the absence of a simple and effective solution in the digital TV field on portable devices. The prior art presents some solutions to capture audience data on portable devices as shown below.

The patent document U.S. 60 749 443 published on Jun. 21 2007 assignee The Nielsen Company disclosures a system and method for wireless measuring of devices for audio visual A V . According to that document an exemplary method provides the steps of receiving media content from a A V source device embedding a video overlay in media content wirelessly received and wireless transmitting media content and video overlay to a unit A V wireless. The exemplary method receives via a wireless connection identification information for the hearing in response to the overlay video broadcast and receives information from the behavior of audience through a wireless connection.

The document published in Chinese CN 101370129 Feb. 18 2009 owner Zhongwei Shixum Satellite Tech CN presents a system for collecting statistical and analytical data as well as a method of implementing mobile TV audience data capture of mobile television and direct broadcast satellite television. The system and method include a data collection module a data encoding module a data transmission module a data service center and a module for statistical analysis of data. The data collection module is in a user terminal receiver that essentially encodes the data collected to form a text file. The data encoding module is respectively in the service center and the user data receiving terminal for the transmission of the text file with data from data service center. The data service center is on the front of the mobile television or direct broadcast television satellite. The module for analysis and statistical analysis of data implements statistical analysis of audience data for an audience ranking. The system and method provided by this invention are able to automatically collect data from the receiving terminal of the user terminal and transmit the collected audience to the data service center via a data communication module and processes and statistically analyze the data in service center for obtainment of accurate and comprehensive ranking data for television programs.

The Japanese document JP 2006352438 published on Dec. 28 2006 owner Casio Hitachi Mobile Comm Co aims to improve the accuracy of the survey audience rating of transmission for a mobile terminal and protect privacy. The document objects a receiving terminal that combines the information for the audience and transmits that information to a communication device on a network. This document increases the sample survey and thus the reliability of survey accuracy can be improved. Additionally the receiving terminal displays the transmission choices as the user s participation in the survey of audience rating receiving a transaction option that the user makes to choose from keeping the information received from the user and allows a means to gather the audience data collection and a transmission means to transmit the data only when the information indicates the operation of choice user participation in the audience survey classification. Still the privacy of the user who does not want to participate in the survey can be protected.

The document U.S. Ser. No. 11 075 711 published on Sep. 15 2005 owner NTT DoCoMo Inc. claims a mobile terminal comprising a receiving means 2 means for reproducing the signal 3 means for measuring the signal level 4 means for generating information to generate a information 5 means for transmitting information to transmit the information generated by the means for generating information.

The document U.S. Ser. No. 10 079 435 published on Nov. 28 2002 owner Minoru Hashimoto refers to a system and method for audience research. The method proposed by this document comprises the steps of acquiring the user identification through the communication network and determining the audience ranking based on the acquired identifications.

According to the above proposals the prior art solutions that use other modules in the architecture to help obtain audience data usually traveling information through the conventional mobile data networks such as 2G and 3G networks.

The approach that these proposals bring does not provide specific contributions in the area of application of the present invention. Although in some of the documents is implicitly mentioned the possibility of using the SMS channel to exchange messages between the data capture device and the server that processes the data it is not dealt with the merits of how such messages are built encapsulated sent or received nor to which class they belong.

The approach of the present invention employs an efficient method of using the SMS channel of communication beyond their conventional standard usage and defined in the standard conventional technique.

As previously mentioned the presented prior art solutions make a simple extrapolation of what is known in the area of audience data capture systems wired to the wireless environment. In the context of wireless systems known solutions focus on using the Internet which means in practice using the mobile data network. However this solution which is technically obvious is not within the scope of the present invention since it does not satisfy the requirement that the portable device may be captured at any time and in real time to logical reach of the server.

Another difference that is not explored in any document of the prior art is the possibility that the server can remotely configure the capture portable device. This feature is only technically feasible from the implementation presented in present invention.

The present invention shows a simple robust and functional. solution for audience data capture of mobile digital television A primary object of the present invention is to provide a system comprising a portable device connected to the mobile network which collects use events of the digital television and a server which processes information received from said portable device and can generate reports of audience data and that in turn can remotely configure the portable device.

A second object of the invention is to enable the exchange of information between the said portable device and said server in which sending information from mobile device to the server is done via SMS Class 2 and the receipt of information by the portable device originating from server is done via SMS Class 0 having a receiving port previously defined in the system.

A third object of the invention is to provide a method to capture parameters and record events on portable devices with digital television receiver comprising obtaining user information such as name and location as well as information about intensity of TV signal physical and logical channels at the time of the event collection and access information to electronic program guide EPG or search for channels for sending the events encapsulated in an SMS message class 2 to said server transparently to the user s portable device.

Another object of the invention is to provide a method for remote configuration of service parameters capture and registration of events on portable devices in which class 0 SMS with predefined port are sent to portable devices to enable the service of capturing audience data or change SMS address of the server for example.

Other solutions for the same purpose have been proposed. However the following features that distinguish the present invention clearly advance the existing state of the art 

Another important aspect of the present invention is that the architecture is completely based on software using only the resources that are already present in portable devices with embedded service.

The present invention shows some points that are important to the uniqueness of the solution. These points make the solution more robust simple and at the same time integrated with a variety of resources in terms of user and administrator. Here some advantages of the present invention are presented 

The objects and advantages of the present invention will become apparent from the following detailed description of an example implementation of the invention and attached drawings by way of non limiting example in which 

According to the present invention the SMS channel existing in GSM networks is used to facilitate the exchange of information between a portable device and a server and sending information from the portable device to the server made via SMS Class 2 and receiving the information by portable device coming from the server done through SMS Class 0 having a receiving port previously defined in the system.

A class 0 SMS is used to configure a server to demand the key parameters for capturing audience data on the portable device . This configuration occurs transparently to the user in real time.

As depicted in the main component of this system is the manager Mgr DTVAM . This DTVAM Mgr manager is the entity that manages and processes the logic of receiving transmitting and validating events generated and received by service as a whole within the portable device . The manager analyzes not only the arrival of TV events of the application but also calls for data to all other components to enable the assembly of the message for sending checking whether the event is valid for the validation algorithms and still starting or finishing all other components within the service.

The first component is a database implemented in file which includes a queue of events to be sent to the server. According to the preferred embodiment of the invention for security and integrity of the system each and every event is always validated by the service previously stored in a database. The sending of events occurs when the number of bytes in which event information is packaged are near but does not exceed 140 bytes or upon reaching a timeout which is originally set to 10 minutes according to preferred embodiment of the invention. Once events are sent to the server and the latter confirms that the data arrived intact such data is discarded from said database.

The second component is the interface where the configuration parameters of the service is in which all the preference parameters for both the end user and the service are configured. It is a fairly simple component that includes settings in nonvolatile memory for future launches due to battery loss or shutdown of the portable device .

The third component is the SIM card interface present in the application programming interfaces basic to portable device . Through said component it is possible to obtain the user information on the SIM card ICCID and insert it into the event to be sent to the server . With this information the server then compares the ICCID with a detailed user registration generally validated the purchase of portable device . Thus it is possible to determine in the server a huge variety of individual characteristics in order to generate multiple combinations of reports.

The component is the interface of the portable device in which it is obtained the location information of the user in the time of the event computed in the service. Said interface is used to get the country code of the cell MCC the code of the mobile network MNC and network identifier Cell ID in which the user was registered at collection event. Thus with reasonable accuracy it is possible to obtain the user s location and the region at the time of collection. This information may be required for reporting by region of interest to the mobile operator for example.

The component is the TV circuit interface of the portable device. With this interface it is possible to collect the signal of TV channels as well as the physical and logical channels at the time of collection event. Still it is possible to obtain information such as access to electronic program guide EPG or search for channels. Such TV circuit interface provides the following information 

The component is the SMS interface for the portable device known as TAPI Telephone API . By means of this interface the device can send and receive SMS messages. In the case of sending messages to the server the SMS messages are of type class 2. For receiving messages from the Server SMS messages are of the class 0 with a port previously defined in the system. It should be note that the port previously defined by the system cannot be any port defined by default for the GSM standard SMS channel.

The queuing means serves to store the events received in a queue ordered by event date in order to optimize the sending of SMS messages to the portable device . For performance reasons this component keeps the information active in the volatile memory of the portable device . Periodically the component sends to said component the current queue of events to be stored in file serving for redundancy in case of any failures.

The component is a means for formatting events so that they are passed to the queue and then are sent by the SMS channel. This component encapsulates the events so that they are consistent with the protocol DTVAM DS which will be detailed in .

The component is the means of implementation of SMS and MMS messages Multimedia Messaging Service embedded in the portable device . This application is modified to be able to receive and process commands from the server on a specific port. These commands are forwarded to said manager DTVAM Mgr that processes and executes the request. Said application is responsible for processing the SMS invitation coming from the server showing a special interface for the user when reading the invitation. Special menus are added to the reading panel so that the user can directly accept service for capturing audience data using the application without going into the TV application.

The component is the application of the TV itself. By means of this component the events are generated and passed on to that manager . Said manager processes and validates if the event is suitable for registration or for disposal. The TV application can also display periodically pop ups inviting users to participate in the service for capturing data audience. There is a specific menu so that the user can interact when he wants and enable or disable the service for data capture.

In we can represent the useful area of SMS data as the whole train of bytes represented. It will be specified each of the components from left to right where each small rectangle represents one byte 

The component is a sequence number added to the event so that the server can track whether a SMS message is being lost during transmission. It goes from 0 to 255 and is cyclical.

The component represents the event date collected with priority to the network time and if not available the time of the portable device. The mode of representation is 2 characters per byte.

The component represents respectively the physical and logical channels representing respectively the frequency of the channel and the channel number assigned at the time of collection.

The component represents the strength of TV signal at the time of collection of the event. The component represents channels obtained from a channel search and is optional. This information is only sent in case of searching channels. In the case of sending it as expanded in and the first byte is how many channels were obtained from the search being cut at . Thereafter the channels are represented by two bytes one byte for the physical channel and a channel to the logical channel.

Once an event ends another is attached to the end to maximize space in the SMS data. According to the preferred embodiment of the invention if an event does not fit at the end of the SMS message so that it has to be broken the whole event then moves to the next message. The current message is then sent with a small surplus in the data field.

In the case of network failure the events are stored on disk and as soon as the portable device is registered again on a network all events accumulated are sent to the server.

Starting with the reference number the field represents the number of configuration messages in the message SMS followed by sequence number to track the message if no text message was lost on the path represented by .

Thereafter all fields marked with standard cross represents the command code in question followed by the fields marked with standard in x representing the command data. The main commands according to the preferred embodiment of the invention are described below 

The server manager is the interface that receives information from the records and events captured by the portable device . This information is processed and consolidated by that manager to obtain the desired audience data. This manager also conducts management of the activity of remote configuration of service parameters and capture records of events on the portable device . In addition the item is able to cross all the events databases process requests for graphics and still refer to the Web Server that needs to provide this data in an organized way in the final reports. The manager can cross the ICCID user information and save in the events database the full range of user information saved in the database of previously registered users.

Item represents the physical interface of the radio channel through which the server exchanges SMS messages with the portable device .

Item is the interface of SMS that in case of receiving an SMS Class 2 from the portable device it validates the integrity of the data and forwards it to the server manager . In the case of sending an SMS class 0 message to the portable device item validates the information generated by the server manager and packages it according to the DTVAM SD protocol defined in .

Item is a relational database capable of managing all data event captured by the manager and saved in the same. This database was designed so to be able to mount various types of graphs later as demanded by the service administrator.

Item is a Web server capable of processing data from the database and display them then in the form of graphs.

According to the preferred embodiment of the present invention the sending of an SMS server to the portable device is outlined as follows the server sends a class 0SMS with port previously defined for the aforementioned portable device in which that interface receives the SMS text message and checks the class and port. If the SMS message is Class 0 and the port is that previously defined in the system then the information is passed to the mentioned manager so that the capture parameters of the audience data are configured. It is important to indicate that in the display screen of the portable device it will not be presented any information about this setting and the user will not have to take any additional action for this configuration is performed. Using this approach you can perform the following operations 

According to the method of the present invention these specific actions sent by the server manager are included in the group comprising 

Although a preferred embodiment of the present invention is shown and described those skilled in the technical will understand that various modifications can be made without departing from the spirit and scope of the present invention as defined in the appended claims.

It is also expressly stated that all combinations of elements that perform the same function in substantially the same way to achieve the same results are within the scope of the present invention.

