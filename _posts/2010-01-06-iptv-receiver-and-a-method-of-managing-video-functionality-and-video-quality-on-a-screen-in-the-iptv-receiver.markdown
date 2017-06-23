---

title: IPTV receiver and a method of managing video functionality and video quality on a screen in the IPTV receiver
abstract: An IPTV receiver and a method for managing video functionality and video quality on a screen in the IPTV receiver are disclosed. Herein, a method includes downloading a widget application from a server, executing the downloaded widget application at a browser, requesting a video test stream through the executed widget application to the server and managing the video functionality and the video quality on the screen using the video test stream.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08239906&OS=08239906&RS=08239906
owner: LG Electronics Inc.
number: 08239906
owner_city: Seoul
owner_country: KR
publication_date: 20100106
---
This application further claims the benefit of U.S. Provisional Application No. 61 142 639 filed on Jan. 6 2009 which is hereby incorporated by reference.

The present invention relates to an Internet Protocol Television IPTV service and more particularly to a method for managing video functionality and video quality on a screen in an IPTV receiver and the IPTV receiver.

Conventional broadcast receivers received broadcast signals from a broadcasting medium such as terrestrial satellite and cable thereby providing the broadcast signals to users. Recently however Internet Protocol Television IPTV services enabling the reception and transmission of broadcast signals in Internet Protocol IP packets via IP are being actively provided. Unlike other broadcasting media such IPTV services are free from all geographical limitations. More specifically once a user is connected to an IP the user may be provided with the requested IPTV services.

There are two types of IPTV receivers an IPTV set with an IPTV and a display in combination and an IPTV set top box having an IPTV reception part only. Many types of displays are available. In case of the IPTV set top box especially a test for determining whether video configuration and video functionality are normal and a video quality test are required. Conventionally a test environment that enables fine video adjustment according to users tastes has not been built thus causing user inconvenience. Moreover a conventional test environment has limitations in applying to both a stand alone IPTV receiver and an IPTV set including an IPTV receiver and a display in combination.

Accordingly the present invention is directed to a method for controlling a video management widget application and an Internet Television IPTV receiver that substantially obviates one or more problems due to limitations and disadvantages of the related art.

An object of the present invention is to provide a method for helping a user to optimize video quality by a periodical test of a video output device in a display device. For example since a video configuration changes in some cases when the user views a movie the user may not enjoy the movie normally.

Another object of the present invention is to provide a method for enabling fine video adjustment when a user needs.

A further object of the present invention is to provide a method for providing a video test stream for checking video functionality from a remote controller to an IPTV receiver by a manufacturer so that a user may adjust video quality or check video connectivity and configuration on his own using the video test stream.

Additional advantages objects and features of the invention will be set forth in part in the description which follows and in part will become apparent to those having ordinary skill in the art upon examination of the following or may be learned from practice of the invention. The objectives and other advantages of the invention may be realized and attained by the structure particularly pointed out in the written description and claims hereof as well as the appended drawings.

To achieve these objects and other advantages and in accordance with the purpose of the invention as embodied and broadly described herein a method includes downloading a widget application from a server executing the downloaded widget application at a browser requesting a video test stream through the executed widget application to the server and managing the video functionality and the video quality on the screen using the video test stream.

At this time the video test stream may be received through a connected Internet Protocol in real time.

Also the method may further comprise receiving a user s input associated with managing video functionality and video quality on the screen.

And the method may further comprise storing the received video test stream and reproducing the stored video test stream.

Also the method may further comprise transmitting a result of managing the video functionality and the video quality on the screen to the server.

And the video test stream may be used to test a plurality of pattern types the plurality of patter types including a vertical resolution pattern a vertical resolution pattern with motion a vertical resolution with motion and 3 2 pulldown pattern a colorbar pattern an overscan and a pixel crop pattern.

Also the method may further comprise performing an operation corresponding to the called Application Programming Interface API when the executed widget application calls a specific API.

And the video test stream includes a Moving Picture Experts Group 2 MPEG 2 Transport Stream TS or an MPEG 4 TS in order to test video quality.

In another aspect of the present invention an IPTV receiver includes a receiving unit for downloading a widget application from a server a widget processor for executing the downloaded widget application at a browser and requesting a video test stream through the executed widget application to the server and a controller for controlling the video functionality and the video quality on the screen to be managed using the video test stream according to a user s input.

At this time the widget processor may receive the video test stream through a connected Internet Protocol in real time.

And the receiving unit may receive a request for selecting an area on the screen to test video quality from the user.

Also the IPTV receiver may further comprise a storage unit for storing the received video test stream.

Also the controller may control a result of managing the video functionality and the video quality on the screen to transmit to the server.

And the received video test stream may be used to test a plurality of pattern types the plurality of patter types including a vertical resolution pattern a vertical resolution pattern with motion a vertical resolution with motion and 3 2 pulldown pattern a colorbar pattern an overscan and a pixel crop pattern.

Also when the executed widget application calls a specific Application Programming Interfaces APIs the widget processor may request the controller to perform an operation corresponding to the called API.

And the video test stream may include a Moving Picture Experts Group 2 MPEG 2 Transport Stream TS or an MPEG 4 TS in order to test video quality.

It is to be understood that both the foregoing general description and the following detailed description of the present invention are exemplary and explanatory and are intended to provide further explanation of the invention as claimed.

Reference will now be made in detail to the preferred embodiments of the present invention examples of which are illustrated in the accompanying drawings. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts. In addition although the terms used in the present invention are selected from generally known and used terms some of the terms mentioned in the description of the present invention have been selected by the applicant at his or her discretion the detailed meanings of which are described in relevant parts of the description herein. Furthermore it is required that the present invention is understood not simply by the actual terms used but by the meaning of each term lying within.

Hereinafter preferred embodiments of the IPTV receiver and method for controlling an application in the IPTV receiver according to the present invention will now be described in detail with reference to the following drawings. Hereinafter in the description of the present invention the term video management widget application will refer to an application which corresponds to one of the applications used in an IPTV environment and more particularly to a widget application for managing video functionality and video quality on a screen in the IPTV receiver.

Also in the description of the present invention a method for managing video functionality and video quality on the screen through a video management widget application in an IPTV environment will hereinafter be described in detail. Also the description of the present invention provides a standardized framework enabling a widget application such as the video management widget application of the present invention to be executed in all IPTV receivers i.e. in an IPTV terminal function ITF . This is because in an IPTV environment the ITF has different hardware and operation system OS environment or condition .

Accordingly a user can solve a problem easily by optimizing the video output of an IPTV receiver or testing the video functionality of the IPTV receiver on his own. Also the user can adjust video quality by receiving a video test stream or an image using or through a widget application in the present invention. When the user wants a video quality suitable for a broadcast program provided by a content provider or a service provider he may download a video management widget application and adjust the video configuration setting of the IPTV receiver. Once the user installs the video management widget application in the IPTV receiver he can simply test video functionality and video quality at an expert level without expensive video test equipment.

Therefore according to the present invention the user may download a proper video management widget application and execute the downloaded video management widget application at a browser thereby being able to manage video functionality and video quality on the screen in the IPTV receiver. Also for the convenience in searching and selecting the above described video management filter the present invention may provide a widget application. Also in the present invention a list of video management filters applicable to corresponding to the IPTV receiver or a receiver profile is managed. And detailed information may be transmitted to the service provider or the contents provider so as to be used in the searching of video management filters. Furthermore according to the present invention when an optimal user designated video management filter is set up the widget application uses Broadband Content Guide BCG information or category information of a Content on Demand CoD Extensible Markup Language XML schema so as to be automatically set up. Thereafter configuration information on the widget application for each user i.e. user profile is stored so as to be managed by the IPTV service provider thereby enabling the user to use his or her own unique widget application at any location provided with IP connection.

Referring to in an IPTV environment a widget service is serviced from a server to a receiver through a network . The server may include a contents provider a receiver manufacturer or consumer manufacturer server and service providers such as Widget service providers and . Herein the contents provider manufactures contents included in an IPTV service. The receiver may include an IPTV receiver a display device and a delivery network gateway DNG . The display device outputs the IPTV service received through the IPTV receiver . The delivery network gateway DNG helps the IPTV receiver to access the Internet. Herein the network may correspond to an open Internet or unmanaged network.

Referring to as an example the widget service is described to be provided to widget service providers and which correspond to a type of service provider. Therefore the widget service may also be provided through a content provider or a receiver manufacturer or consumer manufacturer server . Hereinafter according to the present invention a video management widget application will be given as an example of the widget service. However this is merely exemplary and therefore a widget application performing other functions may also be included herein.

Referring to the widget service is transmitted from a server to an accessible ITF through a gateway . The server may include a CoD server a widget server and a manufacturer server . The CoD server corresponds to a server that provides CoD services. Herein the CoD server includes a database having video pattern and test stream or test images stored therein. The manufacturer server corresponds for example to a server for manufacturers manufacturing the ITF and the manufacturer server includes a database having video pattern and test stream adequate for the ITF manufactured by the manufacturers. The widget server corresponds to a service provider providing a video management widget application. Herein the widget server may directly manufacture and provide a video management widget application or may receive a manufactured video management widget application thereby servicing the corresponding video management widget application. Furthermore the widget server may share information with databases and in other servers via application pairing so as to manufacture and service a widget application.

The ITF may include one or more modules for executing the widget application a widget storage unit for storing the widget application and a user profile storage unit . In as the modules for executing the widget application the ITF may include a widget manager a widget launcher and a widget runtime framework . The ITF also includes a widget storage unit for storing the widget application and a user profile storage unit both being subordinate to the hardware abstraction layer . However the structure of the ITF shown in is merely an example showing a minimum structure associated with the widget application operation. Therefore the present invention will not be limited only to the example shown in .

The widget manager may install and manage a widget application received via the gateway . The widget launcher may launch the installed widget application in accordance with the User profile .

In the above description the manufacturer server may create device specific information such as a widget application or a video parameter which can control detailed operations of the hardware respective to the ITF and may distribute the created device specific information so as to be linked with a 3 party widget application.

The widget application may be easily downloaded from the ITF and installed. Also the widget application may use a hardware profile of the IPTV i.e. a receiver profile and a user profile so as to identify the widget application that can be installed in accordance with each ITF.

Herein in an IPTV environment a widget service provider an IPTV service provider a gateway and an ITF may be involved in the widget servicing process or the process of providing the widget service . However the present invention will not be limited only to the example shown in . Therefore a separate structure associated with the provision of a widget service may be further included in the IPTV environment or conversely part of the structure may be omitted or a specific structure may be replaced with a different structure. For example in the widget service provider and the IPTV service provider may correspond to the same entity.

If the power of an ITF is turned on by the user STEP the ITF sends a request for a web browser initial page to the IPTV service provider STEP . Thereafter the ITF receives the requested service provider page from the IPTV service provider STEP .

The ITF provides the requested service provider page received from the IPTV service provider to the user through a display screen STEP . Also the IPTV service provider may correspond to the same entity as an IPTV service profile Functional Entity FE . Moreover the IPTV service provider may correspond to the IPTV service provider determined by default setting by the ITF .

When the user selects or clicks on an IPTV widget service or a provider from the initial page provided through the display screen STEP the ITF accesses the widget service provider and requests for an IPTV service provider initial page STEP . According to the request the widget service provider transmits the IPTV service provider initial page to the ITF and the ITF provides the received IPTV service provider initial page to the user through the display screen STEP . Herein the widget service provider may correspond to the same entity as an IPTV application FE. Also as described above when the user selects or clicks on an IPTV widget service or a provider and when the corresponding initial page is requested the ITF may transmit the profile of the ITF i.e. receiver profile to the widget service provider in accordance with the related protocol along with the request.

When the user selects a specific widget service STEP the ITF sends a request for downloading the corresponding widget application to the widget service provider which provides the selected widget service STEP . Based upon the download request received from the ITF the widget service provider transmits the selected IPTV widget application in a package file format STEP . During this process the user may search a widget application fro the IPTV widget service page displayed on the display screen of the ITF . More specifically the user may search for a widget application suitable for a user equipment class UE capacity.

In relation to the IPTV widget application within the package received from the widget service provider the TIF may verify whether or not the user wishes to proceed with the installation through an on screen display OSD STEP . Based upon the verified result if the user wishes to install the application the ITF authorizes the installation of the IPTV widget application within the received package STEP .

If the authorization is transmitted by the user the ITF installs the IPTV widget application included in the received package STEP . Subsequently the ITF initializes the installed IPTV widget application STEP and provides the installed and initialized IPTV widget application to the user. Thereafter the ITF receives the IPTV widget application settings from the user STEP .

The ITF stores a user profile including widget configuration information set up by the user in relation with the installed IPTV widget application STEP . Then the ITF requests the stored user profile to pass through the gateway and stored in the IPTV service provider STEP . Accordingly the IPTV service provider stores the received user profile STEP . During this process the ITF may operate the widget application in which the user settings have been applied STEP . In the example given in the user profile is stored in the IPTV service provider . However this is merely exemplary. Accordingly in another example the user profile may be alternatively stored in the widget service provider . The user profile may be differentiated according to each user by the server and or thereby being stored in the respective database. Therefore the user may access the server at any time and any place and call his or her own user profile information thereby being able to use his or her own unique widget application from an ITF different from his or her own ITF.

Hereinafter the receiver profile and the user profile of will be described in more detail with reference to and .

By searching browsing a widget application and by transmitting information associated to execution conditions or environment of the widget application such as ITF functions available resource amount or size and so on to the server in order to download the searched widget application the ITF may be capable of optionally downloading the adequate widget application.

Hereinafter the above described receiver profile transmitted from the ITF will be specified as follows.

Referring to the user profile includes a UserEquipmentID element a UserEquipmentClass element a Resolution element a SupportedEncodings element an IPEncapsulations element and an Extension element.

The UserEquipmentID element includes a model Unique Identifier UID of the corresponding ITF. The Resolution element includes video resolution information of the corresponding ITF. And the SupportedEncodings element includes information on the video frequency of the corresponding ITF.

The receiver profile of further includes a Graphic Resolution element a Graphic colors element an Available Resources element and a Supported Filters element in addition to the receiver profile shown in .

Referring to and the Graphic colors element is defined as a tGraphicColor Type and includes information indicating the processing ability of the ITF on the graphic color. Herein the graphic color refers to a bit depth of each pixel when graphic data are rendered to the OSD. The tGraphicColor Type can be defined based on a color depth attribute. Any one value of 32 bpp 24 bpp 16 bpp and 8 bpp may be given as an enumeration value of the color depth attribute.

The Graphic Resolution element is defined as a tGraphicResolution Type and includes information indicating the processing ability of the ITF on the graphic resolution. Herein the graphic resolution refers to a resolution of OSD graphic that can be used by the widget application. The tGraphicResolution Type can be defined based on a horizontal size attribute a vertical size attribute and a rotation attribute.

The Available Resources element is defined as a tAvailableResolution Type and includes information indicating the available resource amount for the widget application. Herein the resource amount refers to a non volatile memory and a volatile memory.

The Supported Filters element is defined as a tSupportedFilters Type and includes information indicating a function among many video functions that can be executed by the user equipment. Therefore among the video functions described in the present invention the user equipment may transmit executable video functions to the server thereby being able to download and use only the video management widget application that can be used by the user equipment.

The receiver profile according to the third embodiment of the present invention includes information related to receiver capabilities. Such information related to receiver capabilities or performance is largely divided into a DeviceInfo element which is defined as a DeviceInfo Type and a STBService element which is defined as an STBService Type.

The DeviceInfo element may include a Manufacturer element a Manufacturer OUI element a Model Name element a description element a productclass element a serial number element a hardware version element a software version element an enabled options element an additional hardware version element an additional software version element a provisioning element a device status element an Uptime element a first use data element and a device log element.

The STBService element may include a FrontEnd element a Personal Video Recorder PVR element an AudioDecoder element a VideoDecoder element an AudioOutput element a VideoOutput element a Conditional Access CA element a Digital Rights Management DRM element a ServiceMonitoring element and an AudienceStatus element. Also attributes of the STBService element may be a MaxActiveAVStreams attribute and a MaxActiveAVPlayers attribute.

In the DeviceInfo element of further includes an AvailableResources element on available resource information for executing the widget application. The AvailableResouces element may include a nonVolatileMemory element and a VolatileMemory element.

The DeviceInfo element is defined as a type of an object wherein the object contains general device information. The Manufacturer element is defined as a type of string 64 and descriptive of a manufacturer of the CPE human readable string . The Manufacturer OUI element is defined as a type of string 6 and descriptive of structurally unique identifier of the device manufacturer. The Model Name element is defined as a type of string 64 and descriptive of a model name of the CPE human readable string . The description element is defined as a type of string 256 and descriptive of a full description of the CPE device human readable string . The productclass element is defined as a type of string 64 and descriptive of an identifier of the class of product to which the serial number applies. In other words for a given manufacturer this parameter is used to identify the product or class of for product for which the SerialNumber parameter is unique. The serial number element is defined as a type of string 64 and descriptive of a serial number of the CPE.

The hardware version element is defined as a type of string 64 and descriptive of a string identifying the particular CPE model and version. The software version element is defined as a type of string 64 and descriptive of a string identifying the software version currently installed in the CPE. The enabled options element is defined as a type of string 1024 and descriptive of a comma separated list maximum length 1024 of strings. The Comma separated list corresponds to a list of the OptionName for each Option that is currently enabled in the CPE. The OptionName for each option is identical to the OptionName element of the OptionStruct. Only these options are listed wherein the respective State indicates that the corresponding option is enabled. The additional hardware version element is defined as a type of string 64 and descriptive of a comma separated list maximum length 64 of strings. The comma separated list of any additional version represents any additional hardware version information a vendor may wish to supply. The additional software version element is defined as a type of string 64 and descriptive of a comma separated list maximum length 64 of strings. The comma separated list of any additional version represents any additional software version information the vendor may wish to supply.

The provisioning element is defined as a type of string 64 and descriptive of an identifier of the primary service provider and other provisioning information so as to determine service provider specific customization and provisioning parameters. The device status element is defined as a type of string 64 and descriptive of a current operational status of the device. The current operational status corresponds to any one of up initializing error and disabled . The Uptime element is defined as a type of unsignedInt and descriptive of the time in seconds since the CPE was last restarted. The first use data element is defined as a type of dateTime and descriptive of a date and time in Universal Time Coordinated UTC that the CPE first successfully established an IP layer network connection and acquired an absolute time reference using NTP or equivalent over the network connection. The CPE may reset this date after a factory reset. If NTP or equivalent is not available this parameter if present should be set to an Unknown Time value. The device log element is defined as a type of string 32768 and descriptive of a vendor specific log s .

The nonVolatileMemory element is defined as a type of unsignedInt and descriptive of the amount or size of an available non volatile memory. The VolatileMemory element is defined as a type of unsignedInt and descriptive of the amount or size of an available volatile memory.

In the STBService element of further includes a Graphic element for describing or specifying OSD graphic functions of a set top and a SupportedFilters element for specifying a supportable video filter function. The Graphic element may include a GraphiResolution element and a GraphicColor element.

The FrontEnd element is descriptive of a function of the front end which acts as an interface between the network and the inner functional blocks of the STB. The PVR element is descriptive of a function of the PVR which stores programs coming or delivered from any Front End and sends stored programs to audio and or video decoders or to the output IP front end. The AudioDecoder element is descriptive of a function of the audio decoder which receives an elementary audio stream decodes the audio and outputs an uncompressed native audio stream to an audio output object. The VideoDecoder element is descriptive of a function of the video decoder which receives an elementary video stream decodes the video and outputs an uncompressed native video stream to a video output object. The AudioOutput element is descriptive of a function of the audio output which receives uncompressed audio streams from one or more audio decoders and performs format adaptations. The VideoOutput element is descriptive of a function of the video output which receives uncompressed video streams from one or more video decoders and performs format adaptations. The CA element is descriptive of a function of the CA component which contains details of one of the CA mechanisms that may be supported by the STB. The DRM element is descriptive of a function of the DRM component which contains details of one of the DRM mechanisms that may be supported by the STB. The ServiceMonitoring element is descriptive of a service monitoring statistics which are collected based upon service types. The main reason for defining service types is that the service types correspond to different protocol stacks and configurations and statistics collected across multiple service types would be meaningless. Finally the AudienceStatus element is descriptive of a statistics which contains audience viewing statistics organized by channels.

Furthermore since the Graphic element and the Supported Filters element further included in and are identical to those shown in detailed description of the same will be omitted for simplicity.

The above description consists of details on the receiver profile of the ITF. Hereinafter the user profile will now be described in detail. In the following description when the user uses a video management widget application according to the present invention for managing video functionality and video quality on a screen in the IPTV receiver the user profile may include all content modified according to the user settings made during this process e.g. settings that change values of particular functions .

Hereinafter among the elements included in the user profile detailed description of the elements that are identical to those included in the receiver profile will be omitted for simplicity. Accordingly only the elements that are newly introduced will be described in detail. Referring to and unlike the receiver profile the user profile includes an ApplicationSettings element. The ApplicationSettings element may include an ApplicationID element a RevisionNumber element and a Settings element. The ApplicationID element corresponds to an element respective to an identifier that can uniquely identify each widget application. The RevisionNumber element corresponds to an element that indicates the version of each widget application. Therefore the ApplicationID and version information for each widget application are stored in the user profile thereby being able to call upon a specific widget application. Furthermore the Settings element corresponds to an element that stores user specific set up information for each widget application. Herein the Settings element includes a Position element an Extension element and other elements. More specifically the Position element indicates position information of each widget application within the overall list of widget applications. And the Extension element and other elements indicate information on environment settings for each widget application. Accordingly by storing the widget application installed in each ITF and the information on the environment settings for each widget application in the server through the user profile information the user may be able to easily use the same environment even when using a related service through any random ITF.

Hereinafter the processes of downloading and installing upgrading and deleting video management widget applications in an ITF will be described in detail with reference to to .

Now a description will be made of methods for enabling a user to test video streams available to an IPTV receiver with regard to compatibility to change configurations such as a video configuration per resolution e.g. overscan and the like available to the IPTV receiver and a configuration of a Coder Decoder Codec for reproducing Moving Picture Experts Group 2 MPEG 2 and MPEG 4 Transport Streams TSs or to optimize the configurations.

To this end a method for installing and upgrading a video management widget application in an IPTV receiver the types of video tests that may be performed by the video management widget application a method for performing a test by the video management widget application the types of functions for changing a video decoder configuration provided by the video management widget application and method for setting the functions by the video management widget application will be described herein for the convenience sake of description. The following description will be made with the appreciation that the description of are referred to for a configuration or an operation whose description is regarded as redundant or whose description is not provided herein.

A user may want a quick and simple video test before viewing a high quality content or he may want a video quality adjustment by a video test if the video quality is not satisfactory during viewing a content. The high quality may be defined any one of a high definition HD and a standard definition SD .

A description will first be made of a method for installing a video management widget application in an IPTV receiver.

The user selects a widget service provider from the widget service page displayed on the screen in step S.

The ITF receives a list of installable or compatible video management widget applications that the widget service provides has transmitted according to the receiver profile in step S.

The ITF displays a list of the received video management widget applications on the screen in step S.

Upon user selection of a video management widget application from the list the ITF downloads the selected video management widget application in step S.

The ITF stores the downloaded video management widget application and launches the video management widget application in step S. For instance the video management widget application may be launched through a browser.

The ITF adds information about the video management widget application e.g. configuration to a user profile in step S.

In this manner for example a video management widget application is installed according to the present invention.

The user performs a video setting and a video test in step S. Under the circumstances this step may be directly performed by inputting a video control key by the user.

The ITF receives an installable widget list that the manufacturer widget server has transmitted based on the receiver profile in step S.

When the user selects a specific widget application from the displayed widget list the ITF downloads the selected widget application in step S.

The ITF adds information about the widget application e.g. specific settings to a user profile in step S.

Now a description will be made of a method for performing a video test and adjusting a video quality on a screen using or through the installed video management widget application.

Referring to the ITF executes the already installed video management widget application upon user request in step S. In the presence of a plurality of video management widget applications the ITF may provide a User Interface UI that allows the user to select one of the video management widget applications.

When the video management widget application is executed the ITF outputs a menu for video functionality quality test and video quality management on the screen in step S.

The ITF receives a user input indicating a user selection of a video functionality quality test from the user in step S.

The ITF requests a video functionality quality test stream s or images required for the selected video functionality quality test to a server in step S.

The ITF reproduces the video functionality quality test stream s received from the server in step S. Herein the video functionality quality test stream can be stored at a storage unit in the ITF.

Upon user selection of a play stream test item for the reproduced video functionality quality test stream the ITF performs an operation or a test corresponding to the selected test item in step S.

The ITF receives a feedback concerning the test item execution from the user and checks the video functionality quality test according to the feedback in step S.

The ITF outputs the result of the video functionality quality test on the screen in step S. Herein the ITF may give a solution to a possibly generated problem on the screen.

The ITF transmits the video functionality quality test result to the server in step S. The server may build a database with the video functionality quality test result of each ITF.

During reproducing the video test stream the user may enter a video quality satisfaction degree regarding the current video test stream. To receive the user s satisfaction degree by the video management widget application the ITF may display various quality criteria. Or a repair and maintenance personnel in charge of IPTV service or interactive service enabled TV receivers on the manufacturer s side may receive a user input and change settings remotely based on the user input.

The manufacturer may change the current video settings based on the user satisfaction degree provide the changed video screen to the user and receive a user satisfaction degree about the video quality of the video screen again.

The manufacturer collects various video test patterns or video quality information remotely in the above manner and optimizes IPTV receivers according to users.

In reference numeral denotes a user selected area having a low sharpness. Thus the video management widget application guides the user to perform additional settings or displays adjustable menus on the screen so that the user can change settings on his own.

Reference numeral denotes an exemplary video test stream received from the manufacturer or the content provider in order to perform a video test in the video management widget application. The video test stream may be reproduced for example in two methods. One of the methods is to reproduce the video test stream like a live stream using a Real time Transport Protocol RTP packet such as a Content on Demand CoD packet and the other is to reproduce the video test stream after it is downloaded.

Reference numeral denotes the video management widget application downloaded by the user. By the video management widget application the user may perform a video test and adjust video quality in an order set by a test procedure. The video management widget application may request a necessary video test stream s or image s to the server during the test in progress and may store and reproduce the video test stream s by interfacing with a native TV application manager. Referring to this is possible by a widget runtime framework module and a widget manager module .

With reference to Table 1 the types of video quality tests that can be performed by the video management widget application will be described below. That is Table 1 presents an exemplary video play test by the video management widget application.

As illustrated in Table 1 the ITF may perform an MPEG 2 TS play test to check the functionality of the IPTV receiver. The ITF may perform a test for video adjustment as well as the MPEG 2 TS play test by downloading information from the manufacturer server or the widget application server. During playing a content errors generated in a video decoder or a video display processor may be stored in the memory thus affecting a test result.

A video quality test as well as the play functionality test is also possible with the video management widget application. Video management widget applications such as a vertical resolution pattern a vertical resolution pattern with motion a vertical resolution with motion and 3 2 pulldown pattern a color bar pattern and an overscan and pixel crop pattern and the like can control the video quality of the IPTV receiver to adjust in various manners including video quality adjustment and tests illustrated in the above table.

Although APIs called by the video management widget application are not illustrated in a table or a drawing herein the names of exemplary APIs and an exemplary operation order are shown in .

Referring to a high layer operation of the video management widget application is described as functions.

The video management widget application may visually notify the user of a current test in progress and what is a normal video screen.

The user may change a video quality according to a video quality improvement algorithm in the video management widget application by notifying the position of an abnormal video part on a displayed screen according to an indication of the video management widget application. The video management widget application may provide menus that enable the user to adjust video quality directly. The video management widget application may perform a video functionality test and a video quality test upon user request collect user feedbacks and store them during the tests. When the tests are finished the video management widget application may output test results on the screen.

Referring to a manufacturer a main application a video management widget application and many other objects are involved in the high level sequence of the video management widget application. The objects may include CVideoStreamObject ProtocolObject VideoDecoderObject PlaybackObject and UserFeedbackObject. Hereinbelow an operation for testing video quality and adjusting the video quality will be described using functions.

When the user requests a video quality test and a video quality adjustment the main application initializes the video management widget application to test and adjust video quality in step S. Herein this step S can be called Initialize API by the video management widget application.

The video management widget application connects to the ProtocolObject to access necessary one or more objects in step S GetConnection API .

According to a connection request from the video management widget application the ProtocolObject transmits a connection request to an object for example the CVideoStreamObject in step S RequestConnection API .

When the video management widget application is connected to the CVideoStreamObject via the ProtocolObject the main application commands the video management widget application to start a video test in step S StartVideoTest API .

Upon receipt of the video test start command from the main application the video management widget application accesses the ProtocolObject to get a video test stream in step S GetVideoTestStream API .

The ProtocolObject requests the video test stream to the CVideoStreamObject in step S RequestVideoStream API .

Then the video management widget application commands playback to the PlaybackObject in step S Play API .

The PlaybackObject sets the VideoDecoderObject to playback according to the playback command received from the video management widget application in step S SetPlayback API .

The CVideoStreamObject transmits the requested video test stream to the ProtocolObject in step S Send API .

The ProtocolObject notifies the video management widget application of the reception of the requested video test stream in step S NotifyEvent API .

The video management widget application notifies the main application of displaying of the video test stream for a video quality test and adjustment in step S DisplayMessage API .

The main application feeds back for example a content selected or set by the user via the main application to the video management widget application in response to the video display notification in step SetFeedback API .

The video management widget application writes the feedback in the UserFeedbackObject in step S WriteFeedback API .

The video management widget application adjusts video parameters according to the feedback at the VideoDecoderObject in step S AdjustVideoParameters API . The VideoDecoderObject continues the video parameter adjustment until receiving an OK command from the video management widget application.

The video management widget application notifies the main application that an adjusted video stream is displayed in step S DisplayMessage API .

The main application transmits a feedback in response to the video display notification to the video management widget application in step S SetFeedbck API .

In step S the main application sets video coordination concerning the video display notification and transmits a feedback to the video management widget application in step S SetVideoCoordination API .

Then the video management widget application writes the feedback in the UserFeedbackObject in step S WriteFeedback API .

The video management widget application receives adjusted video settings from the user and reports them to the manufacturer server in step S Report API .

The manufacturer server responds to the video management widget application according to the report in step S ResponseReport API .

After receiving the response from the manufacturer server the video management widget application writes requested video parameters in the UserFeedbackObject in step S WriteRecommendationParameters API .

The video management widget application adjusts the video parameters again in step S AdjustVideoParameters API .

The video management widget application notifies the main application that the re adjusted video stream is displayed in step S DisplayMessage API .

When the video quality is completely adjusted as he wants the user commands the video management widget application to finish the procedure through the main application in step S Finalize API .

The video management widget application accesses the PlaybackObject and commands the PlaybackObject to discontinue the playback according to a finish command from the main application in step S Stop API .

The PlaybackObject accesses the VideoDecoderObject and sets a playback related command for the VideoDecoderObject in step S SetPlayback int .

The video management widget application commands the ProtocolObject to disconnect in step S Disconnect API .

The ProtocolObject commands the CVideoStreamObject to discontinue packet transmission in step S StopPacket API .

Upon receipt of an ACKnowledgement ACK message from the CVideoStreamObject the ProtocolObject notifies the video management widget application of generation of an event in step S NotifyEvent API .

The UserFeedbackObject accesses the video management widget application and reads feedback information from the video management widget application in step S ReadFeedback API .

The video management widget application notifies the main application that the video quality test and adjustment has been completed and a content is displayed in step S DisplayMessage API .

Hereinafter an exemplary ITF operating the video management widget application will be described in detail.

Referring to the ITF comprises a network interface a TCP IP Manager a service delivery manager a Demultiplexer DEMUX a signaling information decoder an A V processor a display unit a service control manager a service discovery manager a metadata manager an SI metadata DB an application manager a Widget processor and a user profile preferences storage .

The network interface receives and sends IPTV packets. The network interface connects a network via physical and data link layers.

The TCP IP manager or Internet protocol manager is responsible for an end to end source to destination packet delivery. The TCP IP manager classifies each packet into an appropriate protocol manager.

The service delivery manager is responsible for handling real time streaming data and downloading contents. Also the service delivery manager is responsible for retrieving contents from a content DB for later consuming or usage . In this case a Real Time Transport Protocol RTP Control Protocol RTP RTCP may be used with an MPEG 2 TS. MPEG 2 packets are encapsulated in the RTP. The service delivery manager parses the RTP packets and sends the parsed transport packets to the DEMUX . The service delivery manager sends a feedback on the network reception quality using the RTCP. The MPEG 2 transport packets may be carried directly in the UDP without the RTP. For content downloading an HTTP or FLUTE protocol may be used as the delivery protocol.

The DEMUX demultiplexes audio video and Program Specific Information Program and System Information Protocol PSI PSIP tables from inputted transport packets. In this case the demultiplexing of the DEMUX is controlled for PSI PSIP tables by the signaling information decoder . At this time the DEMUX creates the sections of PSI PSIP tables and sends them to the signaling information decoder . Also the demultiplexing of the DEMUX is controlled for A V transport packets by the A V processor .

The signaling information decoder sets Packet Identifier PID s for the signaling information e.g. PSI PSIP and Digital Video Broadcasting System Information DVB SI tables to the DEMUX . The signaling information decoder decodes the private sections of the PSI PSIP and or DVB SI sent by the DEMUX . The decoding result is used to demultiplex inputted transport packets e.g. set Audio and Video PID to the DEMUX .

The A V processor may include an A V decoder a video filter processor a video display processor and a graphic processor . The A V decoder decodes audio and video A V elementary stream packets The video filter processor will process the video filter in all user selected areas or a whole or entire video screen. The video filter processor may access the video frame buffer memory not shown to manipulate or adjust the video or still picture. The video display processor controls the picture in picture PIP video and or the picture on picture POP video on the display screen. The video display processor also includes a video scale in the end of MPEG 2 decoder system. The graphic processor controls the OSD plane on the screen to display a UI menu and notification dialogue messages.

The display unit receives audio and video data from the A V Decoder . The display unit controls video and audio data and displays the data on the screen and through the speaker. The display unit also controls OSD graphic data.

The Application Manager may support the graphic user interface GUI on the TV screen. The application manager may receive a user key by a remote controller or a front panel. And the application manager may manage the states of the entire TV system.

The service manager may control all of the other managers related to the services such as the service control manager the service delivery manager an IG OITF client not shown the service discovery manager and the metadata manager . The service manager may be responsible for serving IPTV services.

The SI metadata DB is a database for service discovery information and metadata related to the services.

The service discovery SD manager may enable the discovery of IPTV services over a bi directional IP network and may provide all information for selecting the corresponding service.

The service control manager may be responsible for selecting and controlling services and managing sessions. The service control manager may select a live broadcasting service using the Internet Group Management Protocol IGMP or Real Time Streaming Protocol RTSP protocol. Also the service control manager may select VOD contents using the RTSP protocol. When using the International Measurement System IMS a Session Initiation Protocol SIP protocol may be used for initiating and managing sessions through the IMS gateway. The RTSP protocol may be used in the controlling of the delivery of broadcast TV and audio as well as for an on demand delivery. The RTSP protocol may use a persistent TCP connection and allow a trick mode control on real time media streaming.

The user profile preferences storage may keep the user information all information associated to the widget installed widget application and active inactive widget applications preferences and the ITF receiver s hardware compatibility and standard profile. The user profile data may be read from a widget launcher a widget manager and a web browser when the user logs into the system or deletes downloaded widget applications.

The widget processor may include the web browser the widget launcher the widget manager and the widget runtime . The widget launcher may execute an installed widget application when the user logs in. And the widget launcher may execute an activated widget application when the user changes the downloaded widget application. The widget manager may display all widget applications that can be installed and executed in the ITF. And the Widget manager may request downloading of a widget application that the user selected from the servers. Also the widget manager may activate inactivate the downloaded widget application. The widget manager may delete the downloaded or running widget application or widget application being played . The widget manager may control the running widget application and change the location of the widget application within the display screen. The widget runtime framework may be used for a widget application that calls the predefined module or controls the interface in the ITF. The web browser declarative application environment DAE may render HyperText Markup Language HTML pages on the screen and parse documents according to a W3C specification.

Referring to major interfaces are given as follows. An interface interfaces between a widget runtime framework and the application manager . The interface controls mainly functions related to video adjustment and optimization and operates the IPTV receiver in conjunction with functions related to video streams and playback. An interface controls transmission of a setting or a video stream obtained from interfacing with the widget runtime framework to the A V decoder . An interface outputs a video test stream on the screen. There are many interfaces for the IPTV set top box. Therefore setting information about the interfaces e.g. HDMI connection IEEEE1394 connection Component connection Composite connection etc. may be stored and managed in a user profile preferences.

As is apparent from the above description fine video adjustment customized to a user s taste can be performed by use of the video management widget application in both a stand alone IPTV receiver and an IPTV set including an IPTV receiver and a display device in combination. Also the user can enjoy moving pictures or images over the Internet Protocol with a desired video quality by use of the video management widget application.

It will be apparent to those skilled in the art that various modifications and variations can be made in the present invention without departing from the spirit or scope of the inventions. Thus it is intended that the present invention covers the modifications and variations of this invention provided they come within the scope of the appended claims and their equivalents.

