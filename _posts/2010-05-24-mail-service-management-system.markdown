---

title: Mail service management system
abstract: An electronic mail management system may have a standardized interface to which different mail providers may provide an adapter. The standardized interface may have a predefined set of functions that each mail provider may provide, and the mail management system may have a user interface through which the functions may be managed. In some cases, a mail provider may have additional or customized functions that may be added to the user interface and made available to an administrator. Through the user interface, an administrator may be able to add, delete, configure, and move mailboxes, as well as other functions.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09225552&OS=09225552&RS=09225552
owner: Microsoft Technology Licensing, LLC
number: 09225552
owner_city: Redmond
owner_country: US
publication_date: 20100524
---
Electronic mail email is very prevalent for business and private communication. Many businesses rely on email for a vast majority of the communication inside a company and with suppliers and customers.

Many different providers are available for email. For example on premise email systems may have a messaging or mail server that stores email and provides mail boxes for clients to connect and access email. In addition remotely hosted services may use the same server software but provide services from a server computer located in an offsite datacenter. Several cloud email services may also exist where the email service comes from one of many datacenters. Each type of mail provider may have different advantages and disadvantages and may be appropriate for different situations or different types of users.

An electronic mail management system may have a standardized interface to which different mail providers may provide a plugin application. The standardized interface may have a predefined set of functions that each mail provider may provide and the mail management system may have a user interface through which the functions may be managed. In some cases a mail provider may have additional or customized functions that may be added to the user interface and made available to an administrator. Through the user interface an administrator may be able to add delete configure and move mailboxes as well as other functions.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

A mail management system may be used by an administrator to manage several mail services for a business or other enterprise. The mail management system may use a standardized interface where each mail provider implements a standard set of operations. The interface may define a set of invokable operations that each mail service may have and may be extended for additional operations.

An administrator may set up accounts or other relationships with different mail providers and may create authenticated communications sessions with a mail provider when performing one of the various operations.

A user interface may display multiple mail service providers from which an administrator may select. The administrator may perform various mailbox management operations with the mail service provider such as adding a new mailbox reconfiguring an existing mailbox and deleting a mailbox.

Each mail service provider may implement a mail provider interface which may be a definition of invokable operations. The mail provider interface may include type definitions classes or other definitions that may be used by a management system to communicate with the various mail service providers.

The mail provider interface may represent a common set of operations and data types that any mail provider may implement. In some cases a mail provider may create a mail provider interface as an extension to or an application programming interface API to an existing mail service.

The mail provider interface may include both a set of standard operations and a set of custom operations. The standard operations may be common to all mail providers and may represent a minimum set of operations which all mail providers implement. The custom operations may be extensions to the standard operations and may represent specific operations that may not be implemented by all mail providers.

Throughout this specification like reference numbers signify the same elements throughout the description of the figures.

When elements are referred to as being connected or coupled the elements can be directly connected or coupled together or one or more intervening elements may also be present. In contrast when elements are referred to as being directly connected or directly coupled there are no intervening elements present.

The subject matter may be embodied as devices systems methods and or computer program products. Accordingly some or all of the subject matter may be embodied in hardware and or in software including firmware resident software micro code state machines gate arrays etc. Furthermore the subject matter may take the form of a computer program product on a computer usable or computer readable storage medium having computer usable or computer readable program code embodied in the medium for use by or in connection with an instruction execution system. In the context of this document a computer usable or computer readable medium may be any medium that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The computer usable or computer readable medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or propagation medium. By way of example and not limitation computer readable media may comprise computer storage media and communication media.

Computer storage media includes volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and may be accessed by an instruction execution system. Note that the computer usable or computer readable medium can be paper or other suitable medium upon which the program is printed as the program can be electronically captured via for instance optical scanning of the paper or other suitable medium then compiled interpreted of otherwise processed in a suitable manner if necessary and then stored in a computer memory.

Communication media typically embodies computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media. The term modulated data signal can be defined as a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above mentioned should also be included within the scope of computer readable media.

When the subject matter is embodied in the general context of computer executable instructions the embodiment may comprise program modules executed by one or more systems computers or other devices. Generally program modules include routines programs objects components data structures and the like that perform particular tasks or implement particular abstract data types. Typically the functionality of the program modules may be combined or distributed as desired in various embodiments.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be operating system level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the described functions.

Embodiment is a simplified example of a network environment in which a mail management system may be used to manage several different types of mail providers. A user interface may present multiple mail providers each of which having implemented a mail provider interface. The mail provider interface may define a set of operations common to all mail providers and the user interface may allow an administrator to interact with any mail provider using the same user interface and management systems.

The mail providers may be made available to the administrator through several different mechanisms. For example a centralized service provider registry may identify many different mail providers each of which may implement the mail provider interface. An automated system may communicate with the service provider registry to download the mail providers and present them on a user interface for an administrator. In another example an administrator may manually add mail providers to a list of mail providers.

The mail provider interface may define a set of named operations that may be invoked. These invokable operations may be common across all mail service providers and each mail service provider may implement every one of the operations defined in the mail provider interface. In some implementations the mail provider interface may include data type definitions for data objects passed to and from the mail service. The mail provider interface may be an application programming interface API or other predefined set of operations callable from an administrative system.

The mail provider interface may define a set of operations that relate to the administration of mail services. Examples of such operations may be to add a new mailbox reconfigure an existing mailbox and delete a mailbox. Some embodiments may have operations for moving a mailbox establishing or resetting user authentication credentials for a mailbox setting access permissions to a mailbox and other functions.

The mail provider interface may have two sets of operations a set of standard operations and a set of custom operations. The standard set of operations may be the minimum set of operations which all mail service providers may implement and the custom operations may be additional operations that may be available to specific mail service providers and may or may not be implemented by other mail service providers.

Because the mail provider interface may have a set of predefined and universally implemented operations user interfaces and management systems may be created that may operate with many different types of mail server providers. From a management system design perspective a single management system may be used to manage many different types of mail providers such as on premise mail systems cloud based mail systems remotely hosted mail systems and others.

From an administrator perspective the mail provider interface may allow an administrator flexibility to choose an appropriate type of mail service provider to meet a business need and may further reduce training as each mail service provider may be accessed and managed using the same familiar user interface.

For example an administrator may have a group of users who work primarily in an office environment and a second group of users who may travel frequently. The users in an office environment may be assigned mailboxes on an on premise mail system while the travelling users may be assigned mailboxes on a cloud based mail service.

In another use scenario an administrator may have user mailboxes operating with a first vendor who has remotely hosted mail services. However a second vendor may offer increased capacity or better reliability at a lower cost. The administrator may move or migrate the mailboxes to the new vendor to achieve a cost or performance gain while at the same time having the same user interface and management console.

In many embodiments the mail provider interface may contain all of the information that may be used by a mail management system to access a mail provider. For example the mail provider interface may include network connectivity information such as web addresses for the mail provider Internet Protocol IP addresses communication protocols or other connectivity information. The mail provider interface may also include information and metadata about the various available operations.

In some embodiments the mail provider interface may include descriptors data types and other information from which a user interface may be constructed or populated. The metadata may be used to create input tools such as drop down lists checkboxes or other input mechanisms and display descriptors prompts help explanations or other information that may be used to display standard operations or custom operations for a user to select and use.

The mail provider interface may be implemented in two different manners. In one architecture each mail provider may supply a plugin application that implements the mail provider interface. The plugin application may perform all communications to the mail provider and may have operations that are callable from the mail management system. In a second architecture each mail provider may implement the mail provider interface but the mail management system may perform the communications to the mail provider. The mail management system may implement the mail provider interface as an application programming interface for example.

A device may be a device on which an administrator may manage one or more mail services. The device may represent a typical computer device such as a desktop computer or server having hardware components and software components . In some embodiments the device may be a laptop computer netbook computer tablet computer mobile telephone handheld personal digital assistant game console network appliance or any other computing device.

The architecture illustrated for device may represent a typical architecture with hardware and software components however other architectures may be used to implement some or all of the distributed database system.

The hardware components may include a processor random access memory and nonvolatile storage . The hardware components may also include a network interface and a user interface .

The software components may include an operating system on which a mail management system and administrative system may operate. The mail management system may be a specialized application that manages mail services while the administrative system may be an application from which an administrator may perform many network administrative tasks including managing mail services.

The mail management system may be an application that performs many functions relating to configuring electronic mail and other messaging systems for users. The mail management system may have a user interface that allows an administrator to interact with different mail services and perform many if not all administrative functions. The administrative system may also perform some or all of the same functions as the mail management system .

In many embodiments the administrative system may perform a subset of the operations of the mail management system . In some embodiments the mail management system may be a subset of the administrative system and may perform all of the mail related operations for the administrative system .

The mail management system may establish a relationship with a mail service provider prior to being able to perform actions such as adding a mailbox. In an example of a mail service provided by a third party a billing account may be set up along with administrative credentials with which the administrator may access the mail service and perform the various administrative tasks. Once such an account is set up and operational the mail management system may be able to access the mail service.

In some embodiments the mail management system may facilitate the establishment of an administrative account with a mail service provider. For example the mail management system may have a user interface in which all available mail service providers are displayed. An administrator may be able to select one of the mail service providers and be directed to a website or other user interface through which the administrator may be able to create an administrative account. In a typical use the administrator may enter a company name establish a method of payment identify one or more administrators able to access the account and may receive administrative credentials.

The mail management system may store the administrative credentials and other connection information in a mail provider database . The mail management system may use the administrative credentials to establish connections for performing administrative functions with the mail service provider so that the administrator may not have to type in a password or present other information each time an operation is executed with the mail service provider.

For each mail service provider the mail management system may interact with applications that implement a mail provider interface that may include a set of standard operations and custom operations . The applications may be downloaded prior to or after establishing an administrative relationship with the mail service provider. In some embodiments the applications may be downloaded directly from the mail provider while in other embodiments the applications may be downloaded from a service provider registry or other intermediate location.

Embodiment illustrates plugin applications that may operate on the device and provide a translation between the mail provider interface and an interface for a particular mail service provider. For each mail service provider a different plugin application may be used. The applications may be routines plugins or other executable code that may interact with the mail management system and administrative system . In such embodiments the applications may handle all communications between the device and a mail provider.

In some embodiments the mail provider interface may be implemented by the mail service provider. In such an embodiment the mail management system or administrative system may transmit the various operations and data to a mail service provider in a manner that complies with the mail provider interface. In such an embodiment the mail management system may handle all communications between the device and a mail provider.

The device is illustrated as connected to a local area network to which an on premise mail system may be located. The on premise mail system may be a server or system that has mailboxes and other messaging services. The on premise mail system may be part of a domain to which the device and an administrator may have access. In many such local area networks a domain manager may have a local user database in which device accounts and user accounts may be stored.

In some embodiments a local authentication system may authenticate users and devices to the network such as the client devices and users of the client devices . The local authentication system is illustrated as being a separate component from the domain manager but in other embodiments the local authentication system may be a component of the domain manager .

The local authentication system may provide credentials to an administrator to access the on premise mail system . In one use scenario an administrator may login to the device and present administrative credentials that may be authenticated by the local authentication system . The administrative credentials may give the administrator access to the mail management system or administrative system each of which may store access credentials to the on premise mail system or other off premise mail systems. In some cases the administrator s user credentials may be presented to the on premise mail system which may verify the credentials with the local authentication system .

In some embodiments a local database may store approved service providers . The approved service providers may be those mail service providers with which an administrative account may have been established. In such an embodiment a mail management system and administrative system may access the approved service providers to populate a list of mail service providers. The list may reflect those service providers with which operations may be performed.

The local area network may be connected to a gateway and may connect to a wide area network . The wide area network may be the Internet or other wide area network and may have various servers and devices that are outside of a domain defined by the local area network .

In some embodiments a service provider registry may be a central location where different mail service providers may identify themselves. In some embodiments the mail service providers may download their plugin applications . A mail management system such as the mail management system may connect to the service provider registry to identify any mail service providers.

In some embodiments a web interface or other software interface may allow an administrator to search the service provider registry to find mail services that meet certain criteria such as location price feature set or other criteria. Once a selection is made an administrator may establish an administrative account and add the plugin application to the set of plugin applications on the device . In some embodiments the newly added mail provider may be added to the approved service providers .

In other embodiments the mail management system may connect to the service provider registry and download a list of available service providers. From the mail management system an administrator may be able to browse a list of mail providers to which an administrative account has already been established as well as those mail providers for which no prior relationship has been formed.

An example of a mail provider may be a remotely located mail server . The remotely located mail server may be a server that may be located in a datacenter or network operations center and may be located offsite from a company s premises. Such a configuration may be useful to provide physical security to the email server as well as improved Internet connectivity for example. The remotely located mail server may have a downloadable plugin application .

Another example of a mail provider may be a remotely hosted mail server which may also have a downloadable plugin application . A remotely hosted mail server may be a virtual machine that may or may not be shared with other users.

In still another example of a mail provider may be a cloud mail service which may also have a downloadable plugin application . The cloud mail service may or may not have a notion of a server and may present an application programming interface API or other connection mechanism.

For each of the various types of mail services an application or plugin may implement the mail provider interface for the mail management system . The application or plugin may present the operations defined by the mail provider interface so that the mail management system may transmit and receive commands and data across the interface. Once the commands and data are received the application may translate the commands and data into commands and data that may be received by the various mail providers.

In some embodiments a mail service provider may have its own authentication service such as the authentication service provided by the cloud mail service . Other embodiments may use a remote authentication service . In a domain environment a domain controller may provide a local authentication system to which each user may authenticate. Typically a mail service provided by a third party may or may not be able to connect to the local authentication system to authenticate a user and therefore may use a second authentication system.

When a second authentication system is used a new mailbox may be created on the mail service and the user s login credentials may be transmitted to the remote mail service. The remote mail service may receive the user s credentials and establish the user access using the credentials. In some embodiments a synchronization mechanism may update any changes to a user s credentials on a local authentication system with that stored on a second authentication system.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be operating system level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the described functions.

Embodiment illustrates an architecture of a mail management system that may use a mail provider interface. An object model may implement a mail provider interface . An on premise object may also implement the mail provider interface and may also have custom operations . The on premise object may be bound to the object model through the mail provider interfaces.

The on premise object may be a set of executable operations that are contained in a plugin application. The plugin application may be installed and linked to the object model .

Similarly a remotely hosted mail object may be bound to the object model and may implement the mail provider interface. The remotely hosted mail object may include some custom operations . Likewise a cloud mail system object may be bound to the object model and may implement the mail provider interface . The cloud mail system object may include custom operations .

An administrative console add new user wizard or other wizards may be bound to the object model . The various bindings may cause the objects to be linked together so that an operation in the administrative console for example may be performed by the respective mail provider.

The various objects may be stored in a central configuration store which may include all of the various objects and information for the various mail services that may be available active or installed.

A service provider registry may contain a list of available mail service providers. In some cases the service provider registry may contain object models for many different mail service providers including those mail service providers that are not installed into the system.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment is an example of a method for managing mail service providers where the service providers are first selected and configured for use. After configuration the service providers can be selected and have an operation performed such as adding a new mailbox. Embodiment illustrates the management operation in two major steps selecting and configuring service providers then operating with the configured service providers.

Embodiment presented later in this specification illustrates a different method where similar steps are performed but in a different sequence. In embodiment service providers that are both configured and not configured may be presented to an administrator. When the administrator selects one of the service providers to perform an operation that service provider may be configured if it is not already.

In block a mail management system may be started up and may contact a service provider registry in block . From the service provider registry the mail management system may download available service providers in block .

In some embodiments locally available mail service providers may be searched. In an example with a mail server in a local domain the mail management system may search for any mail providers within the domain and retrieve metadata about the local mail providers in addition to the information downloaded from the service provider registry.

The downloaded information in block may be merely metadata that describes the available service providers. In other embodiments the downloaded information may include plugin applications for each of the available service providers.

The available service providers may be displayed in block and an administrator may select one or more of the service providers in block . Each service provider may be processed in block .

For every selected service provider in block if the mail service provider is within a local domain in block access credentials for the mail service may be determined in block . In many embodiments the access credentials may be included in the information downloaded from the mail service. In other embodiments the access credentials may be determined by performing a query against the mail service.

If the mail service provider is not local in block a connection may be established to the mail service provider in block . An administrator may establish an account in block by providing payment information contact information and any other information that may be asked by a service provider.

In some embodiments the operations of block may be performed outside of a mail management system. For example a web browser may be used to display an interactive website for the administrator to establish an account.

Once the account is established administrative credentials may be generated in block . The administrative credentials may be defined by the mail service provider in some cases or by the mail management system in other cases.

The credentials from either the remote or local mail service may be stored locally in block . A plugin application may be downloaded in block . In some embodiments the plugin application may be downloaded from the mail service provider while in other cases the plugin application may be downloaded from a service provider registry or other intermediate location.

The service provider may be registered with the mail management system in block . The process may return to block to process additional service providers.

At this point in the process of embodiment one or more mail service providers may have accounts established and registered with the mail management system. The operations of blocks through may be performed once during the initial configuration of the mail management system and the remaining blocks of embodiment may be performed as a normal operation of the mail management system.

In block a user interface may be generated with registered service providers and the user interface may be presented in block . A user may select a service provider in block and the mail management system may present the available operations for the mail service provider in block . In cases where the mail service provider has one or more optional or custom operations the custom operations may be displayed for an administrator to select.

In some embodiments the user interface in block may be created or supplemented by metadata contained in a plugin application or other metadata. The user interface may contain descriptors defined in the metadata as well as data types that may be used to select user interface mechanisms such as text input boxes radio buttons drop down lists or other mechanisms.

An administrator may select an operation to perform in block . The mail management system may gather parameters related to the operation in block . The parameters may be gathered from different sources including databases domain management systems authentication systems and user input.

A communication session may be established with the service provider in block and administrator authentication credentials may be transmitted in block . Once an authenticated session is established in blocks and the requests operation may be called in block .

The operations of blocks through may represent an embodiment where a communication session may be established by the device containing the mail management system. In some embodiments the operations of blocks through may be performed by a plugin application.

In many cases the requested operation may transmit user credentials such as a user name and password. For example an operation of creating a new mailbox for a user may involve transmitting the user credentials to a remote mail service. The user credentials may be retrieved from a local authentication system and transmitted to the remote mail service. In some embodiments a synchronization mechanism may be used to synchronize the remote authentication mechanism with a local authentication mechanism so that a user may not have to manage passwords in two different locations.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates another method for managing mail services that performs many of the same steps as embodiment but in a different sequence.

The mail management system may be started in block and may contact a service provider registry in block to download available service providers in block .

The available service providers may be displayed in block and a user may select a service provider in block . For the selected service provider a set of operations may be displayed in block and an administrator may select one of the operations in block . Parameters related to the operation may be gathered in block .

If the selected service is a registered service in block a communication session may be established with the service provider in block and the administrative authentication credentials may be transmitted in block to create an authenticated connection. Once the session is established the requested operation may be called in block .

If the selected service is not a registered service in block embodiment may attempt to register the service beginning with connecting to the remote service in block and downloading a mail provider plugin in block .

The administrator may establish an account with the selected service provider in block and administrator credentials may be generated in block . The credentials may be stored locally in block .

The administrator credentials may take different forms in different embodiments. In some cases the administrator credentials may be a user name and password. In other cases the administrator credentials may include a certificate or other type of credentials.

In block the service provider may be registered with the mail management service. The process may return to block to establish a communication session and transmit the operation to the mail service.

The foregoing description of the subject matter has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the subject matter to the precise form disclosed and other modifications and variations may be possible in light of the above teachings. The embodiment was chosen and described in order to best explain the principles of the invention and its practical application to thereby enable others skilled in the art to best utilize the invention in various embodiments and various modifications as are suited to the particular use contemplated. It is intended that the appended claims be construed to include other alternative embodiments except insofar as limited by the prior art.

