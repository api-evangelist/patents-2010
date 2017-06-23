---

title: Image processing apparatus, remote management system, license update method, and computer program product
abstract: An image processing apparatus includes an HDD that stores therein a license file containing an expiration date of a license of an application and a class of the license, a detecting unit that acquires the expiration date from the license file and detects whether the expiration date has passed, a class identifying unit that identifies a class of the license whose expiration date is detected as having passed, based on the license file, an update-process determining unit that determines a method of performing an update process based on the class, a license-file acquiring unit that acquires a license file from the license file management server based on the method of performing the update process, and a replacing unit that replaces the license file stored in the HDD with the license file acquired by the license-file acquiring unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08713161&OS=08713161&RS=08713161
owner: Ricoh Company, Limited
number: 08713161
owner_city: Tokyo
owner_country: JP
publication_date: 20100903
---
The present application claims priority to and incorporates by reference the entire contents of Japanese Patent Application No. 2009 213836 filed in Japan on Sep. 15 2009.

The present invention relates to an image processing apparatus a remote management system a license update method and a computer program product for managing and updating a license.

Conventionally a method has been developed for automatically performing a process of updating a license of an application installed in an image processing apparatus. For example a method has been proposed in which a timing to update a license is determined based on an expiration date to automatically update the license see for example Japanese Patent Application Laid open No. 2006 235963 .

In the technology disclosed in Japanese Patent Application Laid open No. 2006 235963 a method is proposed in which information is input to an input box to set how many days before a license expiration date a license is automatically updated and whether to automatically update the license before the number of printed sheets exceeds the upper limit so that a timing to update the license can be determined based on setting information and license information e.g. the expiration date and the upper limit number of printed sheets that are managed separately and a license update request can automatically be performed at the timing.

However in the method disclosed in Japanese Patent Application Laid open No. 2006 235963 it is difficult to change a type of a license at the timing of the automatic update. Therefore when an agreement type is to be changed it is necessary to perform operation of cancelling an agreement and then perform works to newly install a newly purchased program on an apparatus side. Furthermore it is impossible to change only the agreement type for an identical program. Thus in the method disclosed in Japanese Patent Application Laid open No. 2006 235963 the type of a license cannot be changed at the time of update leading to cumbersome and complicated operation.

The present invention has been made in view of the above and it is an object of the present invention to provide an image processing apparatus a remote management system a license update method and a computer program product capable of enhancing convenience.

It is an object of the present invention to at least partially solve the problems in the conventional technology.

According to an aspect of the present invention there is provided an image processing apparatus connected to a license management server that manages a license of an application the image processing apparatus including a storage unit that stores therein a license file containing an expiration date of the license of the application and a class of the license a detecting unit that acquires the expiration date from the license file and detects whether the expiration date has passed a class identifying unit that identifies a class of the license whose expiration date is detected as having passed based on the license file an update process determining unit that determines a method of performing an update process based on the identified class a license file acquiring unit that acquires a license file from the license file management server based on the determined method of performing the update process and a replacing unit that replaces the license file stored in the storage unit with the license file acquired by the license file acquiring unit.

According to another aspect of the present invention there is provided a remote management system that includes an image processing apparatus and a license management server that manages a license of an application wherein the image processing apparatus includes a storage unit that stores therein a license file containing an expiration date of the license of the application and a class of the license a detecting unit that acquires the expiration date from the license file and detects whether the expiration date has passed a class identifying unit that identifies a class of the license whose expiration date is detected as having passed based on the license file an update process determining unit that determines a method of performing an update process based on the identified class a license file acquiring unit that acquires a license file from the license file management server based on the determined method of performing the update process and a replacing unit that replaces the license file stored in the storage unit with the license file acquired by the license file acquiring unit and the license management server includes a receiving unit that receives a request to update a license from the image processing apparatus and a transmitting unit that transmits a license file according to the request.

According to sill another aspect of the present invention there is provided a computer program product comprising a computer usable medium having computer readable program codes embodied in the medium to be executed by a computer that includes a storage unit that stores therein a license file containing an expiration date of a license of an application and a class of the license the program codes when executed causing the computer to execute acquiring the expiration date from the license file determining whether the expiration date acquired at the acquiring has passed identifying a class of the license whose expiration date is detected as having passed at the determining based on the license file determining a method of performing an update process based on the class identified at the identifying acquiring a license file from the license management server based on the method of performing the update process determines at the determining and replacing the license file stored in the storage unit with the license file acquired at the acquiring the license file.

The above and other objects features advantages and technical and industrial significance of this invention will be better understood by reading the following detailed description of presently preferred embodiments of the invention when considered in connection with the accompanying drawings.

Exemplary embodiments of the present invention will be explained in detail below with reference to the accompanying drawings. In the following embodiments an example is described in which an image processing apparatus according to the present invention is applied to an MFP Multi Function Peripheral that has a plurality of functions of a copier a facsimile machine a printer and the like in one casing. However the present invention is not limited to the embodiments and may be applied to any application installable image processing apparatuses such as MFPs facsimile machines and scanner devices.

The firewall monitors data that passes through a boundary with the outside and detects and blocks unauthorized access to prevent fraud by a third party who has intruded into the remote management system via an external network such as a public line or the Internet.

Each MFP is an apparatus that has a plurality of functions of a copier a facsimile machine a printer and the like and is connected to one another via a local network such as a LAN Local Area Network . Each MFP is able to extend functions as needed by adding or updating a software component hereinafter simply referred to as a component . Although the three MFPs are connected in the remote management system of the embodiment the present invention is not limited to this configuration. It is possible to connect one two or more than four MFPs in the remote management system.

The application download server is an apparatus that manages the substance of the component. More specifically the application download server is a server that provides the MFP with a component for which a user makes an offer to purchase and of which license is authenticated by the license management server .

The license management server is an apparatus that manages a license right of use of a component which is provided by the application download server and installed in the MFP .

The sales server is an apparatus used for performing a procedure for purchasing a component to be added to the MFP or the like. The sales server is installed for each sales territory for the MFP .

The sales server receives an offer to purchase a component via a user PC Personal Computer or the like. The sales server is a server device installed in a service center of a manufacturer or a service provider of the MFP for example and has a management database for storing various types of management data.

The management database stores therein a network equipment configuration related to an MFP which is a managing object at a customer site and management information such as customer information and technical information for each customer. The network equipment configuration management information is information that contains a network configuration at each customer site a configuration of an MFP connected to the network various types of information about the MFP such as a machine type a machine number a date of delivery or installation location information or the like and that allows for identification of the MFP being the managing object and identification of the network configuration. The customer information is information that contains a customer name an address a phone number a facsimile number an apparatus administrator a network administrator or the like and that allows for identification of a customer and his her contact information or more particularly contact information to reach an apparatus administrator or a network administrator. The technical information contains a machine type a machine number a count value of the number of printed sheets or the number of scanned sheets a failure code an assumed cause or the like and that allows for identification of a cause and measures to some extent for a failure phenomenon that occurs in the MFP being the managing object.

In the remote management system of the embodiment in order to realize the remote management each apparatus is equipped with a function of transmitting and receiving a request and a response related to a process on methods for a mutually implemented application by using RPC Remote Procedure Call and is allowed to use a protocol such as SOAP Simple Object Access Protocol HTTP Hypertext Transfer Protocol and FTP File Transfer Protocol to implement the RPC.

Described below are details of the component. The component according to the embodiment is distributed in units of so called sales packages. A set of aggregated sales packages may be used as a unit of distribution.

A single sales package is constructed as an archive file e.g. JAR Java registered trademark Archive containing a single sales package information file and more than one functional package. The sales package information file is a file in which attribute information of a sales package sales package information is recorded. The sales package information contains a product ID a version a name a description a vender name a distribution type and the like.

The product ID is an identifier product identifier uniquely assigned to each sales package and each functional package. The version is a version number of the sales package. The description is a description related to the sales package. The vender name is a name of a vender developer of the sales package. The name is a name of the sales package. The distribution type is information indicating necessity or unnecessity of activation license authentication . A sales package for which the activation is not necessary is available free of charge. In the embodiment however a sales package for which the activation is necessary is explained below as an example.

The functional package is a software package that is packaged in functional units. A single functional package is constructed as an archive file containing a single functional package information file and the substance of a single component.

The functional package information file is a file in which attribute information of a functional package functional package information is recorded. The functional package information contains a product ID a version a name a description a vender name a distribution type and the like.

The product ID is a product ID assigned to the functional package. The version is a number of the functional package. The name is a name of the functional package. The description is a description related to the functional package. The vender name is a name of a vender developer of the functional package. The distribution type is information indicating necessity or unnecessity of activation of the functional package.

The MFP that has received the product key from the sales server requests a license file from the activation server unit of the license management server . The license file is a file containing license information about a sales package that is allowed to be installed in the MFP and a license expiration date and a license class are contained as the license information. The activation server unit of the license management server transmits a license file generated by a component server unit to the MFP .

The MFP that has received the license file specifies the product ID to request downloading from the component server unit of the license management server and also transmits the license file to the component server unit of the license management server . The component server unit of the license management server authenticates the received license file and downloads a sales package identified by the product ID onto the MFP .

The sales managing unit receives from a user PC an offer to purchase a product whose product information is registered in the product management DB . The sales managing unit causes the license management server to issue a product key for the product ID for which the offer to purchase is made and transmits the product key to the MFP via the user PC or the like as a response to the offer to purchase.

The product registering unit downloads list information of sales packages that are centrally managed by the license management server and registers in the product management DB product configuration information or the like which is input based on the list information.

In the embodiment a product is a concept composed of a sales package or a group which is identified by a product ID and license information which indicates the contents of a license. The license information is information such as a license type a license period the number of licenses or the like.

The license type is explained below. is a diagram illustrating examples of license types. As illustrated in five license types are provided and also classes are provided such as an official license as represented by No. to No. and a trial version license as represented by No. . The official license is a license that allows a user to buy and exercise a license right of use of an application. The trial version license is a license to be used by a user free of charge on a trial basis.

Furthermore as illustrated in the official license is further divided into No. to No. . No. is a flat monthly rate agreement that is an agreement to lend a right to use a function to a customer at a flat rate. No. is a variable rate agreement that is an agreement to lend a right to use a function to a customer at a rate depending on usage of the function. No. is a limited period use agreement that is an agreement to lend a right to use a function to a customer for a predetermined period defined in the agreement. No. is a sellout agreement that is an agreement to sell a right to use a function to a customer. On the other hand the trial version license is an agreement to lend a right to use a function to a customer free of charge for a predetermined period which is listed in No. .

Moreover as illustrated in a list on an operation display screen is divided by each agreement type. In the list on the operation display screen an official license auto renewal is displayed for No. flat monthly rate agreement and No. variable rate agreement an official license subscription period is displayed for No. limited period use agreement an official license no period limit is displayed for No. sellout agreement and a trial version license trial is displayed for No. trial agreement .

The product key is an identifier that is uniquely issued or assigned every time a product is purchased. Therefore the product key is used as information for identifying a license of a sales package contained in the product license identifier or information for certifying a legitimate purchaser of the product.

The license management server mainly includes the activation server unit and the component server unit . The activation server unit mainly includes an issuance application receiving unit a product key generating unit an activating unit a license managing unit and the license management DB .

The license management DB stores therein a license of a sales package. More specifically the license management DB stores therein a product ID for identifying a sales package and a license corresponding to a product key of the sales package in association with the product key.

The issuance application receiving unit receives from the sales server an application for issuance of a product key for a product ID of a predetermined sales package.

When receiving the application for issuance of the product key from the issuance application receiving unit the product key generating unit generates the product key for the product ID of the specified sales package. Upon generating the product key the product key generating unit registers the generated product key in the license management DB and transmits the product key to the sales server .

Upon receiving an activation request from the MFP the activating unit checks a license in the license management DB and activates a sales package related to the activation request. The activation request is a request for authenticating a license of an application and contains a product ID a product key and an apparatus ID.

When the activating unit confirms that more than one license is not registered as a result of checking the license management DB the activating unit transmits an error indicating that the activation is not available to the MFP that has transmitted the activation request.

Furthermore when receiving a deactivation request from the MFP the activating unit deactivates a sales package related to the deactivation request. The deactivation request is a request for deactivating use of an application and contains a product ID a product key and an apparatus ID.

More specifically the activating unit receives the product ID and the product key together with the deactivation request from the MFP . Then the activating unit deactivates the sales package for the MFP that has transmitted the deactivation request.

When the MFP is activated by the activating unit the license managing unit registers the apparatus ID of the activated MFP in a lock code that is registered in the license management DB .

When the MFP is deactivated by the activating unit the license managing unit deletes the apparatus ID of the deactivated MFP from the lock code that is registered in the license management DB .

When receiving a change in the license type i.e. an update of the license from the MFP the license managing unit rewrites the license file in the license management DB with an updated license.

The component server unit mainly includes a product key receiving unit a download performing unit a license file generating unit a license file transmitting unit and a component management DB .

The download performing unit downloads a sales package which is received from the application download server and registered in the component management DB onto the MFP .

The license file generating unit receives a product key from the MFP via a user PC or the like refers to the license management DB to check the validity of the product key and generates a license file when the product key is valid. More specifically the license file generating unit compares the received product key with an issued product key which is registered in the license management DB to check whether the product keys are identical or not and determines that the received product key is valid when the product keys are identical.

The component management DB stores therein a sales package received from the application download server .

The application download server mainly includes a download processing unit and a sales package management DE .

The download processing unit transfers to the component server unit of the license management server a sales package identified by the product ID that is specified in the download request sent by the MFP so that the sales package is transmitted to the MFP via the component server unit of the license management server .

The sales package management DB stores therein sale packages in association with product IDs for identifying the respective sales packages.

Described below is a hardware configuration of the MFP . is a block diagram illustrating the hardware configuration of the MFP according to the embodiment. As illustrated in the figure the MFP includes a controller and an engine unit Engine that are connected to each other with a PCI Peripheral Component Interface bus. The controller is a controller that controls the whole MFP picture processing communications input from an operating unit not illustrated. The engine unit is a printer engine or the like that is connectable to the PCI bus. Examples of the engine unit include a monochrome plotter a one drum color plotter a four drum color plotter a scanner and a facsimile unit. The engine unit includes an image processing section that performs error diffusion gamma conversion and the like in addition to what is called an engine section such as the plotter.

The controller includes a CPU a north bridge NB a system memory MEM P a south bridge SB a local memory MEM C an ASIC Application Specific Integrated Circuit and a hard disk drive HDD . The NB and the ASIC are connected to each other with an AGP Accelerated Graphics Port bus . The MEM P includes a ROM Read Only Memory and a RAM Random Access Memory 

The CPU controls the whole MFP includes a chipset constructed of the NB the MEM P and the SB and is connected to other devices via the chipset.

The NB is a bridge for connecting the CPU to the MEM P the SB and the AGP bus and includes a memory controller a PCI master and an AGP target for controlling read and write from and to the MEM P .

The MEM P is a system memory used as a memory for storing computer programs and data a memory for loading computer programs and data and a memory for use in picture processing performed by a printer or the like and includes the ROM and the RAM . The ROM is a read only memory used as a memory for storing computer programs and data. The RAM is a writable and readable memory used as a memory for loading computer programs and data a memory used in picture processing performed by the printer and the like.

The SB is a bridge for connecting the NB to PCI devices and peripheral devices. The SB is connected to the NB via the PCI bus to which a network interface I F unit and the like are also connected.

The ASIC which is an integrated circuit IC for use in image processing includes a hardware component for the image processing and functions as a bridge that connects the AGP bus the PCI bus the HDD and the MEM C to one another. The ASIC includes a PCI target and an AGP master an arbiter ARB serving as the core for the ASIC a memory controller that controls the MEM C a plurality of DMACs Direct Memory Access Controllers that control rotation of image data and the like by hardware logic or the like and a PCI unit that performs data transfer to and from the engine unit via the PCI bus. An FCU Facsimile Control Unit a USB Universal Serial Bus and an IEEE 1394 the Institute of Electrical and Electronics Engineers 1394 interface are connected to the ASIC via the PCI bus. An operation display unit is directly connected to the ASIC .

The HDD is a storage for storing image data computer programs font data and forms. The HDD also stores therein a license file of an application to be executed by the MFP .

The AGP bus is a bus interface for a graphics accelerator card introduced to speed up graphics operation and allows direct access to the MEM P with a high throughput thereby speeding up operation related to the graphic accelerator card.

Described below is a software configuration of the MFP . is a block diagram illustrating a software configuration diagram of the MFP according to the embodiment. As illustrated in the figure the MFP includes a black and white laser printer B and W LP a color laser printer color LP the HDD a hardware resource such as a scanner a facsimile machine or a memory a communication I F interface and a software group constructed of a platform and an application .

In the MFP of the embodiment the HDD stores therein an application a license file of the application and an apparatus ID as identification information unique to the MFP .

The platform includes a control service that interprets a process request from the application and issues an acquisition request for a hardware resource a system resource manager SRM that manages a single or a plurality of hardware resources and arbitrates the acquisition request from the control service and a universal OS .

The control service is formed of a plurality of service modules and includes an SCS system control service an ECS engine control service an MCS memory control service an OCS operation panel control service an FCS facsimile control service an NCS network control service an NRS new remote service and an application installation control service . The platform also includes an application programming interface API that allows for reception of a process request from the application by using a predetermined function.

The universal OS is a universal operating system for UNIX registered trademark or the like and executes each software of the platform and the application in parallel as a process.

A process of the SRM performs system control and resource management in cooperation with the SCS . The process of the SRM performs arbitration and controls execution according to a request from a higher layer that uses a hardware resource such as an engine for a scanner unit or a printer unit a memory an HDD file and a host I O e.g. a centronics I F a network I F an IEEE 1394 I F or an RS232C I F .

More specifically the SRM determines whether a requested hardware resource is available i.e. whether the hardware resource is not used by other requests and when the hardware resource is available notifies the higher layer of the fact that the requested hardware is available. Furthermore the SRM performs scheduling of use of hardware resources by a request from the higher layer and directly executes the contents of the request e.g. paper conveyance and image formation by a printer engine memory allocation file generation or the like .

A process of the SCS runs for application management control of an operating unit displaying of a system screen displaying by an LED resource management interruption application control or the like.

A process of the ECS runs for control of engines of the B and W LP the color LP or the hardware resource formed of the scanner a facsimile and the like.

A process of the MCS runs for acquisition and release of an image memory use of a hard disk drive HDD compression and extension of image data or the like.

A process of the FCS provides an API for performing facsimile transmission and reception from each application layer of a system controller by using a PSTN ISDN network registration and extraction of various types of facsimile data managed by a BKM backup SRAM read of facsimiles reception and printing of facsimiles or integrated transmission and reception.

A process of the NCS is a process for providing a service which is available for all applications that need an network I O and performs sorting of data received from a network side through each protocol into each application or arbitration for transmitting data from an application to the network side.

A process of the OCS runs for control of an operation panel that functions as an information conveying means between an operator user and a main body control side. The OCS is constructed of an OCS process section which receives a key pressing operation or a touch operation as a key event from the operation panel and transmits a key event function corresponding to the received key to the SCS and an OCS library section in which a drawing function for drawing and outputting various screens on the operation panel according to a request from the application or the control service or a function for performing other control on the operation panel is registered in advance. The OCS library is implemented with link with the modules of the application and the control service. The OCS may be configured so that the whole thereof is operated as a process or the whole thereof functions as the library.

The application installation control service performs control to install an application in the MFP . Details are explained below.

The application includes a printer application which is an application for a printer and has a page description language PDL a PCL and a post script PS a copy application as an application for copying a fax application as an application for handling facsimiles a scanner application as an application for scanning a network file application as an application for handling a network file a process check application as an application for checking a process and an WEB section application which operates as an WEB server http server for a client terminal such as a PC connected to the Internet and displays various screens on a WEB browser that runs on the client terminal.

Each process of the application and each process of the control service realize a user service related to an image forming process performed by a copier a printer a scanner a facsimile machine or the like while performing inter process communications by function call transmission of return values and transmission and reception of messages.

In this manner the MFP according to the first embodiment includes a plurality of the applications and a plurality of the control services and each of the applications and the control services is run as a process. Furthermore in each process a single or a plurality of threads is generated and parallel execution is performed in units of threads. Moreover the control services provide a common service to the applications . Therefore while a large number of the processes are executed in parallel and the threads are also executed in parallel so as to perform inter process communications with each other in a cooperative manner a user service related to the image forming process performed by a copier a printer a scanner a facsimile machine or the like is provided.

Furthermore the MFP is configured to allow external applications A B . . . hereinafter simply referred to as external applications when they need not be identified to be developed and mounted on an application layer above a control service layer by a third party such as a customer of the MFP or a third vender. The external applications can be installed via a network.

In the MFP according to the first embodiment the processes of the plurality of applications and the processes of the plurality of control services are run. However it is possible to construct each process of the applications and the control services to have a unitary structure. Furthermore each application allows addition and deletion of each application. In other words as described above it is possible to install or uninstall the external applications .

Described in detail below is the application installation control service . is a diagram for explaining functions of the application installation control service . As illustrated in the application installation control service mainly includes an installing unit a detecting unit a class identifying unit an update process determining unit an update requesting unit a license file acquiring unit a replacing unit a display control unit and a communication control unit .

The installing unit installs an application contained in a sales package downloaded from the application download server or the component server unit of the license management server .

The detecting unit acquires an expiration date of a license from a license file stored in the HDD and checks whether a current license is expired or not based on the expiration date to detect expiration. More specifically the detecting unit detects the expiration by acquiring current time and comparing the current time with the acquired expiration date.

The class identifying unit identifies a class of a license based on the license file stored in the HDD . More specifically the class identifying unit identifies a type of the license from among the license types No. to No. illustrated in and then determines whether the identified type corresponds to the official license class or the trial version license class.

The update process determining unit determines a method of updating a license which is detected as being expired by the detecting unit based on the class identified by the class identifying unit . More specifically when the license is detected as being expired and is identified to be the trial version license the update process determining unit determines to employ a method of updating the trial version license stored in the HDD to the official license. Furthermore when the license is detected as being expired and is identified to be the official license the update process determining unit determines to employ the method of updating the license with normal input of a product key.

The update requesting unit transmits an update request to the component server unit of the license management server via the communication control unit . More specifically the update requesting unit transmits a request file to the component server unit of the license management server .

The request file contains an apparatus ID and a product key. is a diagram illustrating an example of the request file. As illustrated in details of a license issuance request a product key a machine type of the MFP a serial number of the MFP the apparatus ID and the like are written in the request file.

The license file acquiring unit receives a license file from the activation server unit of the license management server . An update start process performed by the MFP and the license management server is explained below. is a sequence diagram of the update start process performed by the MFP and the license management server . As illustrated in the MFP transmits the request file to thereby transmit a license update request to the license management server Step S . The license management server transmits a license file to the MFP to thereby accept the update of the license Step S .

The replacing unit replaces the license file stored in the HDD with the license file acquired by the license file acquiring unit .

The display control unit displays a screen of a list of licenses an operation screen for allowing a user to preform operation or input an execution screen for indicating a progress of the update process or the like on the operation display unit . Furthermore the display control unit displays a screen of the updated list of licenses after the update process is completed.

The communication control unit controls communication between the MFP and the license management server . For example the communication control unit transmits a request file for the update request to the license management server or receives a license file from the license management server .

Described below is a procedure of a process of updating a trial version license to an official license. is a flowchart of the procedure of the process of updating the trial version license to the official license.

The detecting unit acquires an expiration date contained in the license file stored in the HDD and checks whether time is left until the expiration date of the license or not to detect expiration Step S . When the expiration is detected NO at Step S the class identifying unit refers to the HDD to identify a class contained in the stored license file Step S .

The update process determining unit checks whether the identified class of the license corresponds to a trial version license or not Step S . When the class corresponds to the trial version license YES at Step S the update process determining unit determines to employ a process of updating the trial version license to the official license and the update requesting unit makes a connection to a server via the communication control unit Step S . At this time the display control unit displays a screen for indicating a server connecting state on the operation display unit . is a diagram illustrating an example of the screen for indicating the server connecting state. As illustrated in the display control unit displays a screen for notifying that a connection to the server is currently being performed.

The update requesting unit transmits a license update request to the license management server Step S . At this time the update requesting unit transmits a request file to the license management server . In this case the display control unit displays a screen for indicating a license acquiring and updating state on the operation display unit . is a diagram illustrating an example of the screen for indicating the license acquiring and updating state. As illustrated in the display control unit displays a screen for notifying that the license is currently being acquired and updated.

The replacing unit checks whether a license file is acquired from the license management server by the license file acquiring unit Step S . When confirming that the license file is acquired YES at Step S the replacing unit analyzes the contents of the response Step S . More specifically an expiration date or a class of the license is acquired from the acquired license file based on the response by the license management server .

After the check it is further checked whether a class contained in the acquired license file corresponds to an official license or not Step S . When the class corresponds to the official license YES at Step S the replacing unit replaces the license file stored in the HDD with the acquired license file of the official license Step S . illustrates a screen for indicating a license update executing state. As illustrated in the display control unit displays a screen for notifying that the update of the license is being executed on the operation screen.

At Step S when the class of the license does not correspond to the trial version license as a result of the check by the update process determining unit NO at Step S the display control unit displays a screen for inputting a product key and waits for input of a product key Step S . At this time the display control unit displays a screen for inputting a product key on the operation display unit . is a diagram illustrating an example of the product key input screen. As illustrated in the display control unit displays the product key input screen for receiving input of a product key from a user.

When confirming that a product key is input YES at Step S the update requesting unit transmits an update request to the license management server Step S . At this time the update requesting unit transmits a request file to the license management server . In this case similarly to the process at Step S the display control unit displays the license acquiring and updating screen as illustrated in on the operation display unit . Consequently the update process is performed in a conventionally known manner.

At Step S when the input of the product key is not confirmed NO at Step S the display control unit displays an error on the operation display unit Step S . The installing unit invalidates the license and disables functions of an application of the invalidated license Step S . Similarly also in the case in which the class of the license of the acquired license file does not correspond to the official license at Step S NO at Step S the installing unit invalidates the license and disables functions of the application of the invalidated license Step S .

At. Step S the display control unit displays a screen for indicating a result of the update or the invalidation process on the operation display unit Step S . is a diagram illustrating an example of a list screen displayed after the update or the invalidation process. When the license file is replaced at Step S or when the license invalidation process is performed at Step S the display control unit displays a screen of a list obtained after the update or the invalidation process on the operation display unit as illustrated in . More specifically as illustrated in a vender name a license type an expiration date and a status are displayed in association with a name of a version of the application package. Furthermore a check box for checking a processed item is associated with each record. In an example is illustrated in which a package a package and a package are processed this time.

At this time the display control unit displays the license type in the list screen so as to enable to distinguish whether the license is changed to the trial version license or the license is initially the trial version license.

As described above according to the embodiment it is possible to change the type of a license at the time of automatic update. Therefore it is possible to enhance convenience.

In the first embodiment when the trial version license is expired the trial version license is updated to the official license. In contrast in a second embodiment of the present invention when the official license is expired and is not yet updated the official license is updated to the trial version license.

An application installation control service performs control to install an application in the MFP . Details are explained below.

The application installation control service included in the MFP according to the embodiment is explained below. is a functional configuration diagram of the application installation control service . As illustrated in the application installation control service mainly includes the installing unit the detecting unit the class identifying unit an update process determining unit the update requesting unit the license file acquiring unit the replacing unit the display control unit and the communication control unit .

Functions and a configuration of the update process determining unit are explained below. The functions and the configurations of the components other than the update process determining unit are the same as the components denoted by the same reference symbols in the functional configuration of the application installation control service of the first embodiment as illustrated in and therefore explanation thereof is not repeated.

The update process determining unit includes a checking unit and determines a method of updating a license which is detected as being expired by the detecting unit based on a class identified by the class identifying unit and a result of the check performed by the checking unit .

The checking unit checks with the license management server whether a license update procedure has been completed by a user or not when the class identified by the class identifying unit corresponds to the official license.

More specifically when the checking unit confirms that a user has completed the update procedure for the official license which is detected as being expired the update process determining unit determines to employ a conventionally known update process by the update procedure.

On the other hand when it is not confirmed that the user has completed the update procedure the update process determining unit determines to employ a process of updating the official license to the trial version license. In this update process the license file of the official license stored in the HDD is replaced with a license file of the trial version license.

Described below is a procedure of a process of updating the expired official license to the trial version license. is a flowchart of the procedure of the process of updating the expired official license to the trial version license.

The detecting unit checks whether a setting unit not shown has set automatic update of a license Step S . When confirming that the automatic update is set YES at Step S the detecting unit checks whether current time coincides with the timing of the automatic update or not Step S . More specifically the detecting unit acquires the expiration date contained in the license file stored in the HDD and the current time and checks whether the current time coincides with the expiration date.

When it is confirmed that the current time coincides with the timing of the automatic update YES at Step S the class identifying unit identifies a class of the license based on the license file stored in the HDD Step S . The update process determining unit checks whether the identified class of the license corresponds to a trial version license or not Step S .

When the update process determining unit determines that the class corresponds to the official license NO at Step S the checking unit checks with the license management server whether the user has completed the update procedure or not Step S .

When it is not confirmed that the user has completed the update procedure NO at Step S the update process determining unit determines to employ the update process of updating the official license to the trial version license and the update requesting unit makes a server connection via the communication control unit Step S . At this time the display control unit displays a screen for indicating a server connecting state as illustrated in on the operation display unit . The processes from Step S to Step S are the same as those at Step S to Step S of the flowchart of the update process according to the first embodiment and therefore explanation thereof is not repeated.

On the other hand when it is confirmed that the user has completed the update procedure YES at Step S the update process determining unit determines to employ a conventionally known update process Step S . The processes at Step S to Step S are the same as those at Step S to Step S of the flowchart of the update process according to the first embodiment and therefore explanation thereof is not repeated.

At Step S when it is determined that the class corresponds to the trial version license YES at Step S the update process determining unit determines to employ the update process by the processes at Step to Step and at Step to Step in of the first embodiment.

The processes at Step S to Step S are the same as those at Step S to Step S of the flowchart of the update process according to the first embodiment and therefore explanation thereof is not repeated.

At Step S the license file acquiring unit checks whether the type of the license is successfully updated or not Step S . More specifically the license file acquiring unit checks whether a trial version license is acquired from the license management server or not.

When the license file acquiring unit acquires the license file of the trial version license YES at Step S the replacing unit replaces the license file stored in the HDD with the license file of the trial version license acquired by the license file acquiring unit Step S .

When replacing the license file with the license file of the trial version license the replacing unit notifies the license management server of success in replacing the license via the communication control unit Step S . At this time the display control unit displays a screen of a list obtained after the update on the operation display unit .

As another example even when the class contained in the license file stored in the HDD corresponds to the trial version license it is possible to update the license to a new trial version license.

In this case at Step S the checking unit checks with the license management server whether the update to the official license has been requested and the update procedure has been completed or not Step S . More specifically the checking unit confirms that the license management server has received the update request with an offer to purchase the official license from a user of the trial version license but the update procedure such as fee payment or the like has not been completed.

Furthermore at Step S the license file acquiring unit acquires a license file of a trial version license for which the expiration date is set to another three months. Therefore it is possible to automatically extend the trial period of the trial version license for three months.

Consequently even when the trial version license is originally to be expired after issuance of the update request with purchase of the official license by a user and before completion of the update procedure it is possible to allow continuous use of the trial version license.

As described above according to the embodiment it is possible to change the type of a license at the time of automatic update. Therefore it is possible to reduce the operation procedure of the license update process and enhance the convenience.

Furthermore according to the embodiment even when a user of an official license leaves the update procedure unprocessed while the user requests continuous use of the license it is possible to allow for continuous use of the license by automatically changing the license to the trial version license as tentative measures.

In the first and the second embodiments the update process is started upon automatically detecting expiration of a license. In contrast according to a third embodiment of the present invention the update process is started upon receiving an update request that is issued for an official license which has manually been deactivated by a user and that is manually input by the user. In the embodiment an example is explained in which the update process is performed for a license which is once deactivated and then reactivated by a user while the license remains unexpired.

The configuration of a remote management system and the hardware configuration of an MFP according to the embodiment are the same as those of the first embodiment and therefore explanation thereof is not repeated.

An application installation control service performs control to install an application in the MFP . Details are explained below.

The application installation control service included in the MFP of the embodiment is explained below. is a functional configuration diagram of the application installation control service . As illustrated in the application installation control service mainly includes the installing unit an update request receiving unit the detecting unit the class identifying unit the update process determining unit the update requesting unit the license file acquiring unit the replacing unit the display control unit and the communication control unit .

Functions and a configuration of the update request receiving unit are explained below. The functions and the configurations of the above components other than the update request receiving unit are the same as the components denoted by the same reference symbol in the functional configuration diagram of the application installation control service and of the first and second embodiments as illustrated in and and therefore explanation thereof is not repeated.

The update request receiving unit receives input of a request for update to a trial version license from a user via the operation display unit .

Described below is a procedure of a process of updating an official license to a trial version license. is a flowchart of the procedure of the process of updating the official license to the trial version license.

The update request receiving unit checks whether a request for update to the trial version license is received from a user or not Step S . When the update request receiving unit receives input of the request for update to the trial version license YES at Step S the class identifying unit checks a type of a license of the license file stored in the HDD Step S .

The processes from Step S to Step S are the same as those at Step S to Step S of the flowchart of the update process according to the first embodiment and therefore explanation thereof is not repeated.

At Step S the license file acquiring unit checks whether a license file is acquired from the license management server or not Step S . At this time the detecting unit detects whether the expiration date in the license file stored in the HDD has passed or not. When the expiration is detected the license file acquiring unit acquires a license file of a trial version license from the license management server . On the other hand when the expiration is not detected the license file acquiring unit acquires a license file in which an expiration date of a trial version license is added to the expiration date contained in the license file stored in the HDD .

Processes at Step S to Step S are the same as those at Step S to Step S of the flowchart of the update process according to the second embodiment and therefore explanation thereof is not repeated.

As another example at Step S the expiration date contained in the license file that the license file acquiring unit is to acquire from the license management server may be set by adding time to the expiration date of the trial version license to remaining time to the expiration date of the deactivated license.

Furthermore as still another example at Step S the expiration date contained in the license file that the license file acquiring unit is to acquire from the license management server may be set by adding time to the expiration date of the trial version license to unused time in which the application is not used within the time to the expiration date of the deactivated license.

Moreover as still another example at Step S when it is not detected that the expiration date contained in the license file stored in the HDD has passed the license file acquiring unit may acquire the trial version license after the expiration date contained in the license file passes.

As described above according to the embodiment when a user manually deactivates a license and then manually inputs an update request a procedure of the update operation need not be started from the initial state. Therefore it is possible to enhance the convenience of the update process.

Furthermore as described above according to the embodiment the expiration date of the trial version license is added to the remained time or the suspended time within the time to the expiration date of the license which deactivated by a user. Therefore it is possible to save the time in which the license is not used.

The license update program to be executed by the image processing apparatus according to the embodiment can be configured so as to be provided as being recorded in a computer readable recording medium such as a CD ROM a flexible disk FD or a CD R a DVD Digital Versatile Disk in an installable and executable format.

Moreover the license update program to be executed by the image processing apparatus of the embodiment can be configured so as to be stored in a computer connected to a network such as the Internet so that the computer programs are provided by downloading via the network. The license update programs to be executed by the image processing apparatus of the embodiment can be configured so as to be provided or distributed via a network such as the Internet.

Furthermore the license update program of the embodiment can be configured so as to be provided as being built in a ROM or the like.

The license update program to be executed by the image processing apparatus of the embodiment have a module structure made up of the above mentioned units the installing unit the detecting unit the class identifying unit the update process determining unit the update requesting unit the license file acquiring unit the replacing unit the display control unit and the communication control unit . As actual hardware the CPU processor reads the license update programs from the ROM and executes them to load the units on the main memory thereby generating the installing unit the detecting unit the class identifying unit the update process determining unit the update requesting unit the license file acquiring unit the replacing unit the display control unit and the communication control unit on the main memory.

The computer program to be executed by the image processing apparatus of the embodiment to implement the installing unit the detecting unit the class identifying unit the update process determining unit the update requesting unit the license file acquiring unit the replacing unit the display control unit and the communication control unit are provided as being built in a ROM or the like.

In the embodiments described above the examples have been explained in which the image processing apparatus of the present invention is applied to the MFP having at least two functions from among a copy function a printer function a scanner function and a facsimile function. However the present invention can be applied to any image processing apparatuses such as a copier a printer a scanner a facsimile machine and the like.

Although the invention has been described with respect to specific embodiments for a complete and clear disclosure the appended claims are not to be thus limited but are to be construed as embodying all modifications and alternative constructions that may occur to one skilled in the art that fairly fall within the basic teaching herein set forth.

