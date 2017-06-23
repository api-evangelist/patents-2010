---

title: Media mediator system and method for managing contents of various formats
abstract: Provided is a system and method that may encode various formats of contents to a single format and thereby manage the contents, and may transform the contents to a format corresponding to a request of a third party or an end user to distribute the content. A media mediator system of managing various formats of contents may include: a service manager to receive a content and metadata of the content from a content provider; a metadata manager to register the content using the metadata, and to store the metadata of the registered content; a database manager to store and manage information associated with the content; and an encoding manager to schedule an encoding sequence of the content, and to sequentially encode the content based on a scheduling result.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08346741&OS=08346741&RS=08346741
owner: Electronics and Telecommunications Research Institute
number: 08346741
owner_city: Deajeon
owner_country: KR
publication_date: 20100127
---
This application claims the benefit of Korean Patent Application No. 10 2009 0082472 filed on Sep. 2 2009 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference.

The present invention relates to a system and method that may encode various formats of contents to a single format and thereby manage the contents and may transform the contents to a format corresponding to a request of a third party or an end user to distribute the contents.

In a conventional content providing service using a network when various content providers provide contents to a service provider using a different platform the service provider may provide the contents to an end user using the same platform as the platform of the service provider.

However when a content desired by the end user is provided by only another service provider using a platform not owned by the end user the end user may need to purchase a device or a system using the corresponding platform or abandon efforts to receive the content.

The service provider or the content provider may be limited to providing contents to only a number of end users using the corresponding platform and thus may have limited revenues or limited advertising effect with respect to providing of contents.

Accordingly there is a need for a system and method that may provide contents to all end users without restrictions on a type of a platform used by a service provider or a type of platform used by a content provider for a content creation.

An aspect of the present invention provides a system and method that may upload contents from a plurality of service providers and content providers using different platforms and transform the uploaded contents to a single platform to thereby provide all end users with the contents transformed to the single platform and thus enable all the end users to receive a content provided by a service provider using a different platform.

Another aspect of the present invention also provides a system and method that may transform an uploaded content to a platform desired by another service provider and then provide the other service provider with the content transformed to the desired platform and thereby may easily increase a number of target users to receive the content.

Another aspect of the present invention also provides a system and method that may enable a system side to periodically verify and upload a content of a content provider and thereby may enable the content provider to provide the content without a separate uploading process.

According to an aspect of the present invention there is provided a media mediator system of managing various formats of contents including a service manager to receive a content and metadata of the content from a content provider a metadata manager to register the content using the metadata and to store the metadata of the registered content a database manager to store and manage information associated with the content and an encoding manager to schedule an encoding sequence of the content and to sequentially encode the content based on a scheduling result.

According to another aspect of the present invention there is provided a method of managing various formats of contents the method including setting by an end user a format of the content desired by the end user receiving by a service manager a content and metadata of the content from a content provider registering by a metadata manager the content and the metadata of the content to a database manager encoding by an encoding manager the content and providing by the service manager the encoded content to the end user.

According to embodiments of the present invention it is possible to provide all end users with contents uploaded from a plurality of service providers and content providers using different platforms and transformed to a single platform and thus to enable all the end users to receive a content provided by a service provider using a different platform by uploading the contents and transforming the uploaded contents to the single platform.

According to embodiments of the present invention it is possible to easily increase a number of target users to receive a content by transforming an uploaded content to a platform desired by another service provider and then providing the other service provider with the content transformed to the desired platform.

According to embodiments of the present invention it is possible to enable a content provider to provide a content without a separate uploading process by enabling a system side to periodically verify and upload the content of the content provider.

Reference will now be made in detail to exemplary embodiments of the present invention examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. Exemplary embodiments are described below to explain the present invention by referring to the figures.

According to embodiments of the present invention in a system of providing contents to end users over a network such as an Internet Protocol Television IPTV it is possible to provide the end users with contents created by content providers by automatically uploading the contents at predetermined intervals and by transforming various formats of the uploaded contents to a single format.

In addition when a third party desires to provide a content using a different format an uploaded content may be transformed to the different format and be provided to the third party. Accordingly it is possible to easily increase a content target scope.

The service release information platform for the IPTV may be commonly used by a content provider to provide a content broadcasted by the IPTV a service provider to manage the content and to provide the content to an end user and a network provider . The network provider may provide a network to transmit the content provided by the service provider to the IPTV owned by the end user .

As shown in in the contents managing system a broker service provider may collectively manage contents of content providers maintained by service providers and may provide contents to an end user over a network provided by a network provider .

As shown in in the conventional service providing system when various content providers provide contents to service providers and using different platforms each of the service providers and may provide contents to an end user using the same platform as a platform of a corresponding service provider.

For example an end user using an Application Configuration Access Protocol ACAP platform may not receive a content provided using only an Association of Radio Industries and Businesses ARIB platform.

In the contents managing system according to an embodiment of the present invention a broker service provider may upload contents from content providers and service providers and using different platforms transform the contents to a single platform and then provide the contents to an end user . Accordingly the end user may receive a content provided from a service provider using a platform different from a platform of the end user .

In the broker service provider transforms a content to a web platform that is a most easily accessible environment and then provides the content to the end user .

Also it is possible to transform an uploaded content to a platform desired by another service provider and to thereby provide the uploaded content to the other service provider.

As shown in in the contents managing system a broker service provider may include an aggregator a media mediator a syndication portal and a media farm .

The aggregator may periodically verify whether an added content exists in a feed of a content provider and upload the added content when the added content exists.

Here the feed may denote a share set folder for uploading in a content provider terminal or may denote an address accessible to a site based on address information provided from the syndication portal or to a content provided from the content provider.

The aggregator may verify whether the added content exists only with respect to a published content of the content provider.

The media mediator may register the uploaded content encode the content and provide the encoded content to an end user or a third party.

The media mediator may exclusively access the content provider terminal to receive the content and metadata of the content from the content provider register the received content encode the content and provide the encoded content to the end user.

The syndication portal may register a content provider desiring to provide a content in the contents managing system and may transmit to the content provider a Universal Resource Locator URL for a feed and a content metadata format to be used for a content creation.

The syndication portal may provide a content transformed to a format used by a third party to the third party that receives the content registered in the contents managing system to provide the received content to an end user using a platform different from a platform of the contents managing system. In this instance a terminal of the third party receiving the content transformed to the format used by the third party may be referred to as a third party terminal .

The media farm may store the uploaded content and may provide the stored content to the end user according to a control of the media mediator .

The media farm may include a web application server to provide an access site of the end user a file transfer server to transfer a content to the end user a window media server to execute the content on a website and a content storage unit to store the content.

As shown in the aggregator may include a feed listener a feed transmission unit an uploader a temporary content storage unit a content collector and a content transmission unit .

The feed listener may interpret a published format of a content from an original source of the content provider terminal in order to receive the content from the content provider terminal .

The feed transmission unit may transmit metadata of the content to the media mediator to be assigned with a unique identifier ID with respect to the content may schedule uploading of the content and may execute the uploader to upload the content.

The uploader may upload the content from a feed of the content provider terminal and store the uploaded content in the temporary content storage unit . The uploader may use for example a direct upload Application Programming Interface API .

The temporary content storage unit may temporarily store the content until the content is transmitted to the media mediator .

When contents are temporarily stored in the temporary content storage unit by an operation of the aggregator the content collector may collect at least one content stored in the temporary content storage unit .

The content transmission unit may transmit the collected at least one content to the media mediator .

Describing an operation of the aggregator in detail when the feed listener receives metadata of the content from the feed of the content provider terminal the feed transmission unit may analyze the metadata to register an uploader ID for identifying the content provider providing the content and may request the media mediator for a content unique ID for identifying the content.

The feed transmission unit may transmit the metadata to the media mediator and upload the content from the feed of the content provider terminal to the uploader and may store the uploaded content in the temporary content storage unit .

When the feed transmission unit receives the content unique ID from the media mediator the content collector may collect a corresponding content stored in the temporary content storage unit and the content transmission unit may transmit the collected content to the media mediator .

As shown in the media mediator may include a service manager a metadata manager a database manager and an encoding manager .

The serving manager may receive a content from the aggregator and request another constituent component such as the metadata manager the database manager and the encoding manager for operations associated with the content.

The metadata manager may generate a unique ID from metadata of the content register the unique ID to the syndication portal transmit the unique ID to the aggregator and transform the metadata to a schema suitable for a contents managing system and store the transformed metadata.

The encoding manager may schedule an encoding sequence of the content and sequentially encode the content into a format corresponding to the contents managing system.

As shown in the service manager may include a register service unit a select service unit and an update service unit .

The register service unit may sequentially control configurations required during a process of registering a content uploaded from a feed. Also the register service unit may control a process of registering the content received from the content provider.

The select service unit may sequentially control configurations required during a process of transforming metadata of the content to a format employed by the contents managing system and using the transformed metadata in a service.

When a request for modifying the metadata of the content is received from the syndication portal the update service unit may modify the metadata of the content stored in the database manager .

As shown in the metadata manager may include an orchestrator a rule storage unit a rule manager a rule loader an editor a reverse rule manager and a reverse orchestrator .

The orchestrator may orchestrate metadata of a content based on a rule stored in the rule storage unit .

The rule storage unit may store a rule set by a content provider or a third party. The rule may include information associated with a particular standard and a format or a platform of the content used by the content provider or the third party and a metadata format of the content.

The rule manager may transmit a particular condition to the rule loader according to a request of the syndication portion so that the rule loader may retrieve an edition target rule satisfying the particular condition and may transmit the edition target rule to the editor .

The rule loader may retrieve from the rule storage unit a rule satisfying the particular condition and may transmit the retrieved rule to the rule manager .

The editor may execute a jamper to edit the edition target rule according to a request of the third party connected to the syndication portal or to the media mediator .

The reverse rule manager may receive the edited rule from the editor and transmit the edited rule to the rule storage unit and syndication portal to store the edited rule.

As shown in the database manager may include an inserter a metadata storage unit a formatter an encoding rule loader an updater a selector and a reverse formatter .

The inserter may receive orchestrated metadata of a content from the service manager store the orchestrated metadata of the content in the metadata storage unit and request the syndication portal to register the content containing the orchestrated metadata.

The metadata storage unit may store metadata of the content and information associated with the content.

Information associated with the content may include at least one of a Uniform Resource Identifier URI string for identifying the content basic content information including a content title or a content creator information associated with a marker indicated at a play point when the content corresponds to a media content information regarding a content credit and a plurality of media link addresses. The metadata of the content may include an encoding rule to encode the content.

The formatter may transform the orchestrated metadata to a method schema used in the metadata storage unit . The method schema may include for example a Structured Query Language SQL query string.

The encoding rule loader may extract the encoding rule from the stored metadata to provide the extracted encoding rule to the encoding manager .

The updater may update to the metadata storage unit an access path to the encoded content and an access path to a thumbnail extracted from the content.

The selector may retrieve metadata of the content from the metadata storage unit according to a request of the service manager transmit the retrieved metadata to the reverse formatter to transform the metadata and may request the metadata manager for reverse orchestrating of the metadata.

The reverse formatter may transform the metadata of the content to an Extensible Markup Language XML format managed by the syndication portal .

The receiver may periodically receive from the syndication portal a content list uploaded by the aggregator and change content status information included in the received content list to received .

The content status information included in the content list may be stored in the syndication portal .

When the media mediator is exclusively used the content status information may be stored in the database manager . Accordingly when the media mediator is exclusively used and the content status information needs to be changed the content status information stored in the database manager may be changed instead of changing the content status information stored in the syndication portal .

In this instance the receiver may periodically verify a content list received from the content provider stored in the database manager and may change to received content status information included in the verified content list.

The scheduler may periodically receive from the syndication portal a list of contents that are in a received status and receive from the metadata manager a rule to encode the contents being in the received status and transmit the encoded contents and the rule to the encoder to request the encoder for encoding of the content being in the received status.

The scheduler may transmit to the thumbnailer the contents being in the received status to extract a thumbnail.

The scheduler may also transmit to the updater an access path to the encoded contents and an access path to the extracted thumbnail.

The encoder may receive from the scheduler the contents being in the received status and the rule to encode the contents and encode the contents based on the received rule. When encoding is completed the encoder may change the content status information to encoding complete .

The thumbnailer may receive from the scheduler the contents being in the received status and extract the thumbnail from the contents.

As shown in the syndication portal may include a system database a service operator interface a content provider interface and a third party interface .

The system database may store content status information feed information content provider information third party information end user information receiving the content and content use status information.

The content status information may include at least one of a URI string for identifying the content basic content information including a content title and a content creator information associated with a marker indicated at a play point when the content corresponds to a media content information regarding a content credit a plurality of media link addresses of the link and a right to the content and information associated with a content price or a contract.

The content provider information the third party information and the end user information may include at least one of an ID a password a name a height a language and a subscribed date with respect to a target user and ID information indicating which one the target user belongs among the content provider the third party and the end user.

The feed information may include at least one of an ID of a content provider owning a corresponding feed ID information of the feed initial address information of a metadata list of a content created by the content provider and status information of the feed.

The system database may further store information associated with events having a possibility of occurring in the syndication portal information associated with an event solution scheme and information associated with a type of the content provided for the end user and a provided time.

The service operator interface may manage content status information and content provider information and may register the content provider the third party and the end user.

The service operator interface may identify an end user connected to the contents managing system based on an ID of the end user and may recommend a content suitable for the end user based on types of contents provided for the user and provided times.

The service operator interface may include a feed upload managing function of the content provider and may utilize a block function by referring to the contents.

The service operator interface may manage information alarms and events occurring in a constituent component different from the syndication portal .

The content provider interface may provide the content provider with an upload status an issue status and a use status with respect to a content desired by the content provider.

The third party interface may provide information associated with the content registered to the third party holding the third party terminal and may transform and provide a format of the registered content according to a request of the third party.

In operation S the syndication portal may register a content provider desiring to provide a content according to a request of the content provider.

In this instance the syndication portal may transmit to the content provider a URL for a feed and a metadata format to be used for content creation.

In operation S the aggregator may periodically inspect a feed of each of registered content providers.

In operation S the aggregator may verify whether an added content exists in the inspected feed. When the added content does not exist in operation S the aggregator may repeat operation S.

Conversely when the added content exists in operation S the aggregator may upload the added content from the feed and request the media mediator to register the added content in operation S.

The content verifying and uploading process corresponding to operations S through S will be further described with reference to .

In operation S the media mediator may encode the registered added content to a format suitable for the contents managing system.

In this instance the media mediator may transform the encoded content to a format set by the end user or the third party and thereby provide the transformed content.

The format setting process will be further described with reference to and the encoded content changing and providing process will be further described with reference to .

When the syndication portal receives a subscription request signal from the content provider terminal in operation the syndication portal may generate an ID and a password of the content provider based on the subscription request signal and may store the ID and the password in the media farm in operation . In this instance the syndication portion may generate subscription information including the ID and the password of the content provider and information associated with the content provider.

The syndication portal may receive the subscription request signal from the content provider terminal via a webpage provided from the service operator interface . The syndication portal may generate the subscription information using a service layer containing the system database and the service operator interface .

In operation the syndication portal may generate a key corresponding to the ID and the password of the content provider. In operation the syndication portal may transmit the ID and the password of the content provider and the key to request an execution of a log in process.

In this instance the syndication portal may generate a corresponding key based on the ID of the content provider and a current time and may store the generated key in the system database . When a particular situation occurs while generating the key the syndication portal may process the particular situation by transmitting and receiving information to and from the system database .

When the content provider attempts to log in the content in operation the syndication portal may compare an ID and a password received from the content provider terminal with the ID and the password stored in the system database and verify the information in operation and may provide the content provider with a main page to utilize the service operator interface or the content provider interface in operation .

In this instance the syndication portal may verify information changed in the system database and update the information in operation and then may provide the content provider with the main page.

In operation a content may be prepared in a feed of the content provider terminal . In this state when the aggregator attempts content polling with respect to address information of the feed the aggregator may detect the content in operation .

In operation the aggregator may upload metadata of the content from the feed of the content provider terminal . The aggregator may analyze the uploaded metadata to obtain address information of the content and content information in operation .

In operation the aggregator may register to the media mediator an uploader ID for identifying the content provider providing the content and may request the media mediator for a content unique ID for identifying the content.

In operation the media mediator may transmit to the aggregator the content unique ID generated during a content registration process.

In operation the aggregator receiving the content unique ID may transmit the content to the media mediator periodically perform polling with respect to the feed of the content provider terminal and transmit collected contents to the media mediator .

When the aggregator transmits the content uploaded in operation S to the service manager of the media mediator the register service unit of the service manager may request the orchestrator of the metadata manager to transform metadata of the content . In this instance the orchestrator may transform a format of the metadata to a format used in the contents managing system for example to a cans rss format.

The orchestrator may retrieve from the rule storage unit according to a request of the register service unit a rule to transform metadata of the content provider providing the content . The orchestrator may orchestrate the metadata of the content based on the retrieved rule .

Specifically the orchestrator may orchestrate an XML of the metadata to an XML format used in a web base IPTV middleware and may transmit the orchestrated metadata to the register service unit .

The register service unit may transmit the orchestrated metadata to the inserter of the database manager to request a content registration .

The inserter may transmit the orchestrated metadata to the formatter to transform the orchestrated metadata to a method schema used in the metadata storage unit .

The inserter may transmit the content containing the orchestrated metadata to the syndication portal to register the content . The inserter may store the orchestrated metadata in the metadata storage unit .

When the inserter transmits to the register service unit a content list managing registered contents the register service unit may return the received content list to the aggregator .

The encoding manager may share contents with the media farm using a network file system. The encoder and the thumbnailer may access contents stored in the media farm without restrictions.

The receiver may periodically receive from the syndication portal a list of contents uploaded by the aggregator and may change content status information included in the content list to received .

The scheduler may periodically receive from the syndication portal a list of contents being in a received status to determine an encoding sequence and change content status information of a content to be encoded to encoding .

The scheduler may request the encoding rule loader for an encoding rule and the encoding rule loader may extract from content metadata an encoding rule corresponding to the content being in the received status and may provide the extracted encoding rule to the scheduler .

The scheduler may transmit the content being in the received status and the encoding rule to the encoder to request an encoding .

In this instance the encoder may encode the received content being in the received status based on the encoding rule. When encoding is completed the encoder may transmit the encoded content to the scheduler . Also the encoder may provide an encoding progress rate to the syndication portal periodically during the encoding process .

The scheduler may transmit the content being in the received status to the thumbnailer to request the thumbnailer for extracting a thumbnail .

In this instance the thumbnailer may extract the thumbnail from the content being in the received status using FFMpeg and transmit the extracted thumbnail to the scheduler .

The scheduler may transmit to the updater an access path to the encoded content and an access path to the extracted thumbnail .

The updater may update to the metadata storage unit the access path to the encoded content and the access path to the extracted thumbnail .

When the syndication portal approaches the rule manager of the media mediator to request a format setting according to a request of a content provider the rule manager may transmit a particular condition to the rule loader according to a request of the syndication portal so that the rule loader may retrieve a rule to be edited satisfying the particular condition .

The rule loader may retrieve from the rule storage unit a rule satisfying the particular condition and may transmit the retrieved rule to the rule manager .

The editor may edit the rule according to the request of the end user or the third party connected to the syndication portal . When the edition is completed the editor may transmit the edited rule to the reverse rule manager .

The reverse rule manager may store the edited rule in the rule storage unit and transmit the edited rule to the syndication portal for a registration . Through this it is possible to terminate a setting process of a corresponding tool.

When the syndication portal receives from an end user or a third party a request for a content satisfying a particular condition the syndication portal may request the select service unit of the service manager for information associated with the content .

The select service unit may request the selector of the database manager for content information . The selector may retrieve the content information from the metadata storage unit .

The selector may transmit the content information to the reverse formatter to transform the content information to an XML format managed by the syndication portal and may request the reserve rule manager of the metadata manager for a reverse transformation .

In this instance the metadata transformed to the XML format by the reverse formatter may be transmitted as metadata of the content to the third party terminal according to a request of the third party.

For example the reverse formatter may transform the content information to an XML format used over an IPTV middleware.

The reverse rule manager may retrieve from the rule storage unit according to a reverse transformation request the rule edited by the end user or the third party and may transmit the edited rule to the select service unit via the selector .

The select service unit may transmit the edited rule to the syndication rule . The syndication portal may request the encoding manager to encode the content using the edited rule and to transform the content to a format suitable for the end user or the third party. When the content transformed to the suitable format is transmitted from the encoding manager the syndication portal may provide the transformed content to the end user or the third party.

When the syndication portal receives a feed list request signal from the content provider terminal in operation the syndication portal may load feeds stored in the system database according to the feed list request signal to obtain a feed list in operation . In operation the syndication portal may provide a content provider with the feed list and a main page so that the content provider may utilize the service operator interface or the content provider interface .

When the syndication portal receives a feed update request signal from the content provider terminal in operation the syndication portal may generate a feed based on the feed update request signal to add the feed to the system database in operation or may delete the feed from the system database in operation .

In operation the syndication portal may provide the content provider with a feed update result and the main page so that the content provider may utilize the service operator interface or the content provider interface .

When the syndication portal receives from the content provider terminal a rule generation signal to generate a rule or a rule modification signal to modify a rule stored in the rule storage unit in operation the syndication portal may verify user information stored in the system database according to the rule generation signal or the rule modification signal in operation .

In this instance the rule generation signal may denote a signal indicating generation of a rule with respect to a metadata format of the content provider. The rule modification signal may denote a signal indicating modifying of a rule with respect to the metadata format of the content provider. The user information may correspond to subscription information of the content provider.

When the content provider is authenticated using user information stored in the system database in operation the syndication portal may request the orchestrator for an access address to modify the rule in operation .

The syndication portal may receive the access address from the orchestrator in operation and transfer the received access address to the content provider terminal in operation .

When the orchestrator receives from the content provider terminal information associated with a rule to be generated or a portion of the rule to be modified in operation data may be exchanged between the content provider terminal and the rule storage unit according to to thereby set a format in operation and .

The orchestrator may transmit to the content provider terminal a rule generation complete signal or a rule modification complete signal in operation to indicate the format is set according to . The rule generation complete signal or the rule modification complete signal may be differently transmitted depending on which one the syndication portal receives between the rule generation signal and the rule modification signal.

When a third party desires to modify a rule of the third party using the third party terminal the syndication portal may replace the orchestrator with the reverse orchestrator to thereby perform operations shown in and thereby modify the rule of the third party.

As described above according to embodiments of the present invention it is possible to provide all end users with contents uploaded from a plurality of service providers and content providers using different platforms and transformed to a single platform and thus to enable all the end users to receive a content provided by a service provider using a different platform by uploading the contents and transforming the uploaded contents to the single platform.

Also according to embodiments of the present invention it is possible to easily increase a number of target users to receive a content by transforming an uploaded content to a platform desired by another service provider and then providing the other service provider with the content transformed to the desired platform.

Also according to embodiments of the present invention it is possible to enable a content provider to provide a content without a separate uploading process by enabling a system side to periodically verify and upload the content of the content provider.

The contents managing method according to the above described exemplary embodiments of the present invention may be recorded in computer readable media including program instructions to implement various operations embodied by a computer. The media may also include alone or in combination with the program instructions data files data structures and the like. Examples of computer readable media include magnetic media such as hard disks floppy disks and magnetic tape optical media such as CD ROM disks and DVDs magneto optical media such as floptical disks and hardware devices that are specially configured to store and perform program instructions such as read only memory ROM random access memory RAM flash memory and the like. Examples of program instructions include both machine code such as produced by a compiler and files containing higher level code that may be executed by the computer using an interpreter. The described hardware devices may be configured to act as one or more software modules in order to perform the operations of the above described exemplary embodiments of the present invention or vice versa.

Although a few exemplary embodiments of the present invention have been shown and described the present invention is not limited to the described exemplary embodiments. Instead it would be appreciated by those skilled in the art that changes may be made to these exemplary embodiments without departing from the principles and spirit of the invention the scope of which is defined by the claims and their equivalents.

