---

title: Generic smart USSD client module embarked in a telecommunication terminal
abstract: A digital telecommunications system communicates with an unstructured supplementary service data protocol by a digital application located on a mobile terminal. The digital application includes a navigation module, a presentation module, an interpreter module and an encryption module. The digital application interprets data received from an unstructured supplementary service data protocol that communicates with a telecommunications network and displays interpreted data on a screen of said mobile terminal from data received from the unstructured supplementary service data protocol. The digital application interprets a request of a user entered into the mobile terminal in response to the interpreted data displayed on the screen of the mobile terminal, and sends from the mobile terminal data interpreted from the request of the user to the telecommunications network by the unstructured supplementary service data protocol.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08938494&OS=08938494&RS=08938494
owner: 
number: 08938494
owner_city: 
owner_country: 
publication_date: 20100615
---
Applicant claims priority of Application PCT IB2010 052686 filed Jun. 15 2010 which claimed priority from French application Ser. No. 09 02933 filed Jun. 17 2009 and from which Applicant also claims priority.

This invention relates to a generic smart USSD Unstructured Supplementary Service Data client module embedded in a telecommunication terminal.

The present invention relates to conversational client server applications and more particularly relates to the field of dynamic dialogues between a mobile telecommunication terminal and a network or a server for applications and services using interactive interfaces. The invention provides to the terminal to reach a server or other terminals dialogue navigate exchange information download applications and data text video audio images and other and use different applications and services.

The present invention relates to mobile telephony expanding new features and interactive services and a convergence of dialogue between heterogeneous devices such as mobile phones mobile devices digital applications and services platforms Internet servers third parties services and equipments and others. Moreover the invention provides the additional requirement of highly useful ergonomics for terminal users such as real time services requirements which are in accordance with the resource constraints of mobile infrastructures servers networks bandwidths real time constraints and mobile terminals limited processing storage and display capacities .

A technical problem to be solved is thus to provide generic client server systems to implement and use protocols with dynamic interactive intuitive features that are easy to use and also allow fact integration and with low resources consumption. To this need is added the requirements of inter operability customization and deployment.

Consequently a technical problem to be solved is to provide a client server system for applications and services allowing the set up of multiple and reusable applications and services with the lowest possible costs targeting a large number of users. An objective is also to satisfy the requirement to have interactive services compliant with existing and emergent technologies without costly implementations and preferably with few modifications of the equipment managed by network operators. Another objective is the requirements of providing such applications and services with few modifications to the user terminals while providing a dynamic interactive user friendly interface and satisfying real time constraints.

An important objective is to have means to reach a variety of information with only short delays. Also this objective relates to obtaining information via the telecommunication network from a mobile terminal in local mode or in roaming or nomad mode.

Thus the significant capacity constraints of the terminals must be taken into account as well as network performance and inherent ergonomics problems.

Furthermore in client server systems the problem exists of distributing the intelligence of different portions of 25 services between the network and the terminal.

The term intelligence includes the capability to decide the management or the execution of an action a process or data processing. For example intelligence is used with the aim of providing complementary functional possibilities flexibility and independence versus constraints and or users needs.

In order to address this problem various documents of the prior art relate to embedded clients on mobile terminals either compliant with the networks and mobiles terminals constraints at the expense of ergonomics or providing functional and user friendly user interface at the expense of the quality of service response time number of proposed services .

These documents provide technical solutions to the client server model for which a client connects to a server with special means to reach information navigate download save or transfer applications and data.

The prior art provides different approaches which however address only limited and punctual aspects of this problem without solving the global technical problem i.e. to find and optimal point between the equipments constraints networks and terminals real time aspects ergonomics and number of features and services.

Concrete applications and services are possible based on navigation using standard protocols that are WEB like World Wide W6eb or Internet such as HTTP protocols Hypertext Transfer Protocol XML Extended Markup Language and extended markup language for describing and analyzing date IP Internet Protocol or others in combination with standard transport protocols TCP Transmission Control Protocol one of the basic protocols for IP data transmission UDP User Datagram Protocol protocol for data transmission being part of the TCP IP protocol and others which do not guarantee the desired response time for the queries therefore failing with regard to the real time services constraint.

Another approach known from the prior art is to limit the scope of the access to some services and applications based on simplified protocols taking into account the limited capabilities of mobile phones for example the WAP protocol Wireless Application Protocol especially designed for mobile phones. However this approach is at the expense of ergonomics aspects and multi services without ensuring compliance with real time services.

Finally a major effort is focused on clients applications embedded in mobile phones that satisfy the characteristics of ergonomics and aesthetics. However they unfortunately require installing dedicated software on the terminal which is demanding in terms of mobile terminal resources but does not guarantee real time services.

U.S. Pat. No. 7 103 018 relates to a communication terminal initiating a WAP session Wireless Session Protocol by sending a query to the server. The query includes an identification of the required data as an identification number provided from the server. According to this identification number of the terminal i.e. of the user the server identifies the terminal versus identification data in a database associated with this user. Information regarding user s profile indicates the data format that can be managed by the terminal. When the server responds to the request it sends data corresponding to the format defined by the user profile.

However this document is limited to a data type predetermined by the profile of each user by the data format to be sent and by the capacity of transport channels and does not offer the flexibility of a WEB browser type. Based on WAP technologies this solution provides neither a guaranteed response time nor a high level of ergonomics.

WO 03030026 concerns the redirection of content from a content server by applying a special definition for this content. The content and the accompanying definitions are then sent to the device over the cellular network. The browser installed on the device is programmed to recognize the definition and to put an appropriate indicator on the content the indicator defines how the device uses the contents especially by defining that the content will not remove this content from the memory even emptying the cache to free up disk space.

Nevertheless this document proposes data and content recognition according to the mobile terminal capabilities and is limited to a restricted number of features services uses and data access.

EP 1874018 relates to markup language specifications that are defined to provide pseudo rich media during phone calls and implements two end times that support these specifications. Each implemented end items functions as mid phone and mid navigator where the telephone call is partly a traditional duplex audio stream between the callers completed by pseudo rich media transmitted from one to the other. However data and voice applications are distinct and the data are transmitted through separate channels i.e. a splitting is applied in steps to request content from a given channel and steps to receive data from several other separate channels.

Also many documents of the prior art relate to navigation clients embedded in mobile devices having aesthetic and ergonomic user interfaces which are allowed to reach standard WEB pages to display the WEB pages and to navigate them. However this high level of ergonomics and diversity are provided to the detriment of the quality of service in terms of guaranteed channel and response time and are of high complexity in terms of implementation resources.

In summary the prior art does not proposed entire complete services such as navigation in real time nor does the prior art satisfy the requirements and objectives of the above mentioned client server systems for mobile telecommunications.

A digital telecommunications system communicates with an unstructured supplementary service data protocol by a digital application located on a mobile terminal. The digital application includes a navigation module a presentation module an interpreter module and an encryption module. The digital application interprets data received from an unstructured supplementary service data protocol that communicates with a telecommunications network and displays interpreted data on a screen of said mobile terminal from data received from the unstructured supplementary service data protocol. The digital application interprets a request of a user entered into the mobile terminal in response to the interpreted data displayed on the screen of the mobile terminal and sends from the mobile terminal data interpreted from the request of the user to the telecommunications network by the unstructured supplementary service data protocol.

The present invention is based on standards and existing protocols including USSD Unstructured Supplementary Service Data open and already implemented in a native way in the devices and fully or partially available. It is based on native networks and terminal features by offering a generic client server system which provides multiple applications and multiple services. The present invention relates to a generic smart USSD client module embedded in a telecommunication terminal.

In the present invention the term client is understood to mean an application having its own embedded navigator or using a third embedded navigator the application itself being embedded in the terminal and not in the telecommunication network. This network is for example a GSM Global System for Mobile GPRS General Packet Services communications system with access using packets services UMTS Universal Mobile Telecommunications System 3G 3G and or any other network such as Next Generation Network .

The present invention addresses the weakness of the prior art via a client server system based on standard network protocols such as USSD where the server for applications and services is located in a core telecommunications network a computer network or another network. This server for applications and services is based on an interpreter of a structured by conversational objects language such as XML Extensible Markup Language VXML Voice Extensible Markup Language language voice extended tagging which means an application programming interface for communication using peripheral devices related to the telephony or another.

The user equipment such as a terminal is for example a mobile phone such as a cell phone a PDA Personal 30 Digital Assistant handheld computer combining many functions a multi functions board computer or similar for a vehicle a home or business multi platform including for example a monitoring or safety function or any other fixed or mobile device being able to communicate with at least one network.

In the present invention the term user is understood to mean an individual subscriber fixed nomadic or Roamer itinerant subscriber in the sense of roaming between networks to at least one network or a third party for example a provider of applications of services of content or of any equipment for example alarm or signaling equipment .

The purpose of the present invention is a client application embedded in a mobile telecommunications terminal that is able to communicate and to share data with a server and or a network based on real time telecommunications protocols such as USSD. The client satisfies requirements for real time low resources consumption multi functions and integration with its own ergonomics or with third party ergonomics used in the terminal.

In its most general meaning the present invention relates to a digital telecommunications client system based on at least one USSD protocol with the USSD client being located in at least one mobile terminal and including means for 

Advantageously the USSD client includes at least one transport module including at least one encryption module at least one decoder interpreter module and at least one presentation module.

In one implementation the USSD client is based on at least one interpreter of structured languages such as HTML or XML or VXML or CCXML or other suitable language.

In another implementation the presentation module is a transformation module to any presentation language and includes means for modifying the processed contents modification filtering suppression content addition and other .

In a preferred embodiment the USSD client includes means for operating as an USSD server versus at least one other terminal and or at least one network.

The present invention also relates to a processing method implemented by the USSD client system which is composed of at least 

Advantageously the step of choice and validation of at least one choice is performed with at least one simple pressing on specific text and or graphic areas by using at least one key of a keyboard of the terminal.

In a first embodiment the method includes a step of support and management of at least one feature ringing by the user and or by the network service.

In a second embodiment the method includes a step of support and management of at least one feature advertisements and or customized information during at least one user session the advertisements and or customized information being dynamic or static.

In a third embodiment the method includes a step of support and management of the proprieties of the terminal and of the network to which the terminal is attached.

In a fourth embodiment the method includes a step of support and management of at least one additional feature relative to at least one application available on the terminal.

In a fifth embodiment the method includes a step of support and management of at least one feature USSD bookmark. 

In an embodiment the method includes a step of externalization of at least one content of at least one current page and or of at least one session or portion of a session the step of externalization being a backup or archive or transfer from the USSD client to any external application.

In another embodiment the method includes a step to restore at least one session on the mobile terminal.

In a preferred embodiment the method includes a step of visual management of at least one session including the duration of the session as well as the duration of the user s interactivity during the session and a verification of continuity of the session.

In another preferred embodiment the method includes a step of management of one or many USSD messages as at least one USSD message the virtual USSD message.

In one implementation the method includes a step of simulation and or management of at least two USSD sessions activated in parallel for the same terminal.

In another implementation the method includes a step of customization of at least one service for at least one user by the USSD client and or remotely by the network.

In a preferred embodiment the method includes a step of encryption with or without visual indication of the data and or of services with at least one custom security key or with at least one security automatically managed by the client and by the server.

The present invention will be better understood when considering the non limiting embodiment described below.

In the classical case an USSD message is sent by typing on the terminal keyboard a sequence for example 123 1 2 followed by pressing an Enter key.

When an USSD message is emitted from the mobile it is always directed to a home network in which there is an USSD equipment such as an USSD server with a browser in the present invention USSD Center. This network USSD Center interprets the USSD query and then sends back a requested information and or menu.

For instance a menu with list of choices is displayed on the terminal screen where every choice is for example a number 1 2 or 3. In order to make a choice the user has to press the right number on the keyboard and then validate by using another key.

This manual USSD navigation mode doesn t need any modification in the user terminal and the network services are directly usable. However this solution for USSD navigation is not satisfactory from ergonomics and usability point of view.

The user wastes a lot of time in manual interaction. Also with increasing complexity of mobile terminals in term of features a complementary technical problem occurs the user phone is more complicated for example having extended keyboard special and complementary keys touch screen smart phone evolution evolved cell phone offering personal assistant features and other devices. lit therefore becomes more difficult for the user to navigate by pressing different keys.

The embedded mobile USSD client purpose of the present invention contributes for an enriched user experience via advantages such as ergonomics especially improving and multiplying networks services in regards to various topics such as security facility to connect and maintain the connection response time and information access time new features services and data customization and other advantages.

In the present invention the term data is understood to mean at least one information and or at least one instruction and or at least one structured or unstructured content the data being textual graphic audiovisual or any other type.

The availability in the terminal of an embedded USSD client that is equipped with a browser having a user navigation interface overcomes the aforementioned drawbacks of the prior art. The client is installed as a standard application in the mobile phone. The browser included in the client is based on at least one structured language interpreter for example HTML Hypertext Markup Language descriptor XML VXML CCXML Call Control XML XML for the call control feature or other.

In another embodiment the client does not include a navigator and cooperates with at least one navigator or with an application specific to the terminal.

The module is a cell phone with screen and keyboard including keys for example corresponding to number 1 corresponding to number 2 and corresponding to number 3 . A navigation key allows navigation via keystrokes left right up down and selection via a central keystroke.

When user decides to connect to the USSD Center he she types on keyboard an USSD code for example 123 1 2 . This code is then sent to the USSD Center a session is opened and the USSD Center returns back the required menu displaying on screen for example 

The item My bank is an example of service with encrypted USSD session the item My city is an example of service for Internet information retrieval via USSD and the item My house is an example of service for house automation management via two USSD terminals.

When the user wishes to come back for example in the previous menu he she presses on the keyboard the displayed number as per screen and then confirms the validation key for example.

When the user requests for a service he she connects directly through the user interface of the mobile terminal for example presented as icons and so on proposed on screen of mobile terminal . The USSD Client is available and accessible directly or not via the interface. By using navigation key the user selects and activates the USSD client or a cooperating application .

A list of predefined and customizable USSD favorites Bookmarks also known as signets in French is then displayed. When the user makes a choice the corresponding USSD query is sent to the network and its returns back a menu of request services for example the following menu 

Advantageously navigation and choice selection are done for instance by using validation key or by using navigation key or by using an predefined key of the digital keyboard or by using a softkey virtual dynamic key .

In another implementation the bookmark is hierarchical end to end data and services encryption. In the current 2G 3G mobile networks the information conveyed by the USSD channel is not secure. Following requests from operators users and third parties this information is encrypted end to end by the USSD client at content and or at service level. For example for at least one USSD service the user can install a custom security key or choose a security key automatically managed by the client and the server .

During navigation or when out of navigation mode the USSD client has the capability to save one or many pages in the terminal and to send at least one selected page or at least one part of at least one selected page to the network for example as SMS Short Message Service short text message that can be transmitted and received from a mobile phone as MMS Multimedia Message Service multimedia message that can be transmitted and received from a mobile phone as email and other message forms. Also the USSD client has the capability to do complete or partial archives of the session.

Indication and management of a navigation skin application downloadable on mobile networks and allowing operators to customize in the terminal the subscriber s navigation and or services.

Additional applications available from navigation for example are applications that can be launched with a simple touch on specific text and or graphic areas. There may be a feature for session restore form the USSD client.

This session restore option is active if a session is interrupted. The USSD client manages then an automatic restore by reconnecting to a network service via any communication channel transparently to the navigation feature.

Feature for management and verification of the duration and the continuity of an USSD session. It is well known for persons skilled in the art that the duration on an USSD session is unknown from the user and that an USSD session in which the user remains passive for some time for example during one minute is interrupted without any indication. To improve the ergonomics of the USSD user interaction the USSD client provides visual management of the session and of the session duration as well as verification of the duration of the user inactivity and session continuity.

In one embodiment the session is interrupted after a specified period of inactivity and a warning message is displayed on the screen of the terminal . In another embodiment the session is automatically extended in a transparent for the user manner i.e. without displaying a warning message on the screen of the terminal .

In another embodiment the session is automatically extended in a transparent for the user manner i.e. without displaying a warning message on the screen of the terminal .

In yet another embodiment the client has means to customize this management of virtual USSD messages i.e. the management of one or many USSD messages as at least one USSD message or the virtual USSD message or the management of one or many USSD messages grouped in an USSD message a long USSD message. By using USSD client the dedicated to this long USSD message channel is for example used as a channel for downloading data such as text images graphics or audiovisual contents.

An embodiment of the client server system architecture particularly of the USSD client module architecture. A purpose of the present invention is presented in .

The mobile terminal includes an USSD client module software integrated with the native telecommunications platform of the mobile terminal .

The USSD client includes a transport module with services encryption module which receives USSD data from any network for example from a network with an USSD Center and transmits the USSD data via a link to the module which is the decoder interpreter.

The module has for example a function to decode the USSD messages and to convert them into a structured language.

The module transmits the decoded data via a link to a presentation module for example a transformation module using HTML language or using any other presentation language. The function of the module is to format the data for display.

Advantageously the presentation module includes means to modify the processed content modification filtering suppression content addition and other functions .

The module then sends formatted for presentation data via a link to a module such as standard WEB navigator or Browser . Moreover the USSD client has the capability to communicate and to automatically adapt itself to at least one third client server system such as any USSD server On Device Portal embedded portal and others and thus in a transparent or declared manner for the server. The data provided from the navigator module is sent via a link to the display of the terminal .

The presented USSD client architecture on allows integration with at least one navigator such as WEB or any other mobile terminal application or user application. In addition this USSD architecture allows the USSD client to be embedded into at least one navigator such as WEB or any other mobile terminal or user application.

When a query is sent by the user to the network via a link a session is opened between the network and the USSD client which successively share data via the transport module the decoder interpreter module the presentation module and the navigation module . The navigation module transmits the data for display at the required format via a link and data is displayed on the screen of the terminal .

The described features and characteristics of the USSD client are illustrative and not limiting embodiments. Many other features are implemented on demand or during a user customization of the USSD client.

Based on a native USSD standard the USSD client purpose of the present invention is operational with any type of USSD network services.

The USSD client includes a graphic presentation enhancement module supporting different user interface graphic presentations. These presentations are based on descriptors of structured languages and format such as the standard formats CSS Cascading Style Sheet style sheet format for Internet Browsers DOM Document Object Model document template independent of all programming languages and of all platforms SMIL Synchronized Multimedia Integration Language language allowing the synchronization of different multimedia elements on a WEB page SVG Scalable Vector Graphics description language for vectors graphic sets based on XML LASER Lightweight Application Scene Representation SAF Simple Aggregation Format binary format for integration in the same stream LASER contents and audio video contents or such as proprietary formats as Macromedia Flash or a kind of Rich Media format formats using advanced techniques to transfer and display of multimedia data audio video still images graphics text and for interactive user interface .

Preferably the USSD client has the capability to manage advanced value added features as for example 

Furthermore in another embodiment the client server system intelligence is located in the USSD service and in the USSD client .

In a preferred embodiment the digital telecommunications client system for using of digital applications and services is based on at least one USSD protocol the USSD client and located in at least one mobile terminal . This USSD client includes means for receiving and interpreting at least one data and or at least one instruction from at least one telecommunications network means for displaying in text and or in graphic on a screen and for presenting on the mobile terminal at least one data and or at least one instruction from the network means for interpreting and for sending back to the network at least one request and or at least one message of at least one user in function of at least one data and or at least one presented service and means for communicating with at least one server of at least one third party such as any USSD server on device portal server or other. The USSD client includes at least one transport module including at least one encryption module at least one decoder interpreter module and at least one presentation module . It includes also at least one navigation module .

