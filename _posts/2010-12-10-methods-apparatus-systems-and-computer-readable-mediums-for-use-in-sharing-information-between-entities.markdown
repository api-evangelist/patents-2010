---

title: Methods, apparatus, systems and computer readable mediums for use in sharing information between entities
abstract: In one aspect, a method comprises: receiving, by a first processing system, information indicating that a second processing system has content that is to be provided to the first processing system; receiving, by the first processing system, content and at least one identifier from the second processing system; determining, by the first processing system and based at least in part on the at least one identifier, whether the content is another version of content previously received by the first processing system; receiving, by the first processing system, information indicating that a third processing system is to receive content from the first processing system; and transmitting, by the first processing system, the content, at least one identifier and version information to the third processing system, wherein the version information indicates whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08918447&OS=08918447&RS=08918447
owner: SAP SE
number: 08918447
owner_city: Walldorf
owner_country: DE
publication_date: 20101210
---
Businesses software systems are often built using a collection of software components sometimes referred to as content. The content is sometimes viewed as falling into two categories i.e. data e.g. metadata master data catalogues modeled processes and configurations and code e.g. applications tools built in processes and user interfaces . Content in the form of data e.g. master data and configuration is often useful to configure the collection of software components to perform as desired.

Business software systems often change over time. Such change sometimes referred to as the evolution of the business software systems is often in the form of changes in content e.g. changes in data and or code.

It is generally desirable to allow changes to the content of a system while minimizing or at least limiting the impact of such change on the remaining content of the system.

From time to time it is desirable to transfer content from one system e.g. a system of a supplier to one or more other systems e.g. a system of customers of the supplier .

It would be desirable to provide a system that further assists in the above so as to improve the life cycle management process for one or more of systems.

It has been determined that the life cycle management process may be improved by providing the ability to determine whether content received by a processing system is another version e.g. a same version or a different e.g. newer version of content previously received by such processing system.

In one aspect a method comprises receiving by a first processing system information indicating that a second processing system has content that is to be provided to the first processing system receiving by the first processing system content and at least one identifier from the second processing system determining by the first processing system and based at least in part on the at least one identifier whether the content is another version of content previously received by the first processing system receiving by the first processing system information indicating that a third processing system is to receive content from the first processing system and transmitting by the first processing system the content at least one identifier and version information to the third processing system wherein the version information indicates whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system.

In some embodiments the received content comprises a plurality of content records and wherein the at least one identifier comprises a plurality of identifiers each one of the plurality of identifiers being associated with and identifying a respective one of the plurality of content records.

In some embodiments the method further comprises determining at least one global identifier based at least in part on the at least one identifier from the second processing system and a one to one mapping from the at least one identifier from the second processing system to the at least one global identifier.

In some embodiments the method further comprises determining the at least one identifier transmitted to the third processing system based at least in part on the at least one global identifier and a one to one mapping between the at least one global identifier and the at least one identifier transmitted to the third processing system.

In some embodiments the receiving content and at least one identifier comprises extracting the content and the at least one identifier from the second processing system after receiving the information indicating that the second processing system has content to be provided to the first processing system.

In some embodiments the transmitting the content to the third processing system comprises deploying the content to the third processing system.

In some embodiments the information indicating that a second processing system is to provide content to the first processing system is supplied by a graphical user interface in response to input from a user and the information indicating that the third processing system is to receive content from the first processing system is supplied by a graphical user interface in response to input from a user.

In some embodiments the at least one global identifier comprises a global identifier and the determining whether the content is another version of content previously received by the first processing system comprises determining based at least in part on the global identifier that a version of the content has been previously received by the first processing system and determining based at least in part on the content that the content is a same version or a different version of content previously received by the first processing system.

In some embodiments the version of the content previously received comprises a plurality of records the method further comprising comparing the content to the version of the content previously received to identify one or more of the following changes to the content compared to the version of the content previously received a first one of the plurality of records in the content is a same version as a first one of the plurality of records in the version of the content previously received a second one of the plurality of records in the content is a different version from a second one of the plurality of records in the version of the content previously received a third one of the plurality of records in the content is not another version of any of the plurality of records in the version of the content previously received or one of the plurality of records in the version of the content previously received is omitted from the plurality of records in the content.

In some embodiments the method of further comprises providing a user interface to allow a user to reject one or more of the identified changes.

In some embodiments the method further comprises transmitting content from the first processing system to the third processing system based at least in part on the users choices.

In some embodiments the method further comprises determining whether the at least one identifier received from the second processing system includes a global identifier having an originating vendor identifier an authoring source identifier and an application namespace field.

In some embodiments the at least one global identifier includes an identifier having an originating vendor identifier an authoring source identifier and an application namespace field.

In some embodiments the content is only a portion of a content group that has a plurality of content records and is received from the second processing system.

In some embodiments the method further comprises transmitting by the first processing system the content to a fourth processing system.

In another aspect a computer readable storage medium has instructions stored thereon the instructions being executable by a machine to result in a method comprising receiving by a first processing system information indicating that a second processing system has content that is to be provided to the first processing system receiving by the first processing system content and at least one identifier from the second processing system determining by the first processing system and based at least in part on the at least one identifier whether the content is another version of content previously received by the first processing system receiving by the first processing system information indicating that a third processing system is to receive content from the first processing system and transmitting by the first processing system the content at least one identifier and version information to the third processing system wherein the version information indicates whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system.

In some embodiments the received content comprises a plurality of content records and wherein the at least one identifier comprises a plurality of identifiers each one of the plurality of identifiers being associated with and identifying a respective one of the plurality of content records.

In some embodiments the method further comprises determining at least one global identifier based at least in part on the at least one identifier from the second processing system and a one to one mapping from the at least one identifier from the second processing system to the at least one global identifier.

In some embodiments the method further comprises determining the at least one identifier transmitted to the third processing system based at least in part on the at least one global identifier and a one to one mapping between the at least one global identifier and the at least one identifier transmitted to the third processing system.

In some embodiments the receiving content and at least one identifier comprises extracting the content and the at least one identifier from the second processing system after receiving the information indicating that the second processing system has content to be provided to the first processing system.

In some embodiments the transmitting the content to the third processing system comprises deploying the content to the third processing system.

In another aspect apparatus comprises a processing system comprising a processor the processing system to i receive information indicating that a second processing system has content that is to be provided to the first processing system receive content and at least one identifier from the second processing system determine based at least in part on the at least one identifier whether the content is another version of content previously received by the first processing system receive information indicating that a third processing system is to receive content from the first processing system and transmit the content at least one identifier and version information to the third processing system wherein the version information indicates whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system.

In some embodiments the received content comprises a plurality of content records and wherein the at least one identifier comprises a plurality of identifiers each one of the plurality of identifiers being associated with and identifying a respective one of the plurality of content records.

In some embodiments the processing further to determine at least one global identifier based at least in part on the at least one identifier from the second processing system and a one to one mapping from the at least one identifier from the second processing system to the at least one global identifier.

In some embodiments the processing system further to determine the at least one identifier transmitted to the third processing system based at least in part on the at least one global identifier and a one to one mapping between the at least one global identifier and the at least one identifier transmitted to the third processing system.

In some embodiments the processing system to receive the content comprises a processing system to extract the content and the at least one identifier from the second processing system after receiving the information indicating that the second processing system has content to be provided to the first processing system.

In some embodiments the processing system to transmit the content comprises a processing system to deploy the content to the third processing system.

This summary is not intended to be exhaustive and or limiting. For example while some aspects are described in this summary other aspects may not be described in this summary but rather may be apparent from the description drawings and or claims which follow. In addition for example nor are the various portions of the aspects described in this summary and or any possible advantages described in this summary required in every aspect.

Referring to in accordance with some embodiments the system or landscape includes a plurality of processing systems . A first one of the processing systems i.e. processing system comprises a content lifecycle management CLM system and is sometimes referred to herein as the CLM system or CLM repository . A plurality of communication links couple the other processing systems to the CLM system .

For example is a block diagram of a portion of one of the processing systems e.g. processing system in accordance with some embodiments. The processing system may include a plurality of applications e.g. application A application B application C and application D which may be hosted and or otherwise executed by the processing system . In some embodiments one or more of the applications e.g. application A application B application C and or application D comprises a program written in ABAP language. In some embodiments one or more of the applications overlaps with one or more others of the applications.

One or more of the applications e.g. application A application B application C and application D may include and or otherwise provide access to content. Content may be received by the CLM system. Content received together from an application is sometimes referred to herein as a content group. For example application A may include and or otherwise provide access to a content group . A content group may include one or more records sometimes referred to herein as content records. For example the content group may include two content records e.g. content record A and content record B.

In some embodiments one or more of the content records may include a reference to and or may otherwise refer to one or more of the other content records. For example and as represented by a dashed line the content record B may include a reference to and or may otherwise refer to the content record A . If a content group includes a content record that refers to a content record not included in the content the content group may be considered and or treat as bad e.g. lacking in referential integrity . Consequently if the content group did not include content record A the content group may be considered and or treated as bad lacking in referential integrity .

The one or more applications may further include and or otherwise provide access to one or more identifiers that are associated with and or identify the content. For example application A may further include and or provide access to identifiers that are associated and or identify the content . In some embodiments each identifier is associated with and or identifies a respective one of a plurality of the content records in a content group. For example one of the identifiers e.g. the identifier for content record A may be associated with and or identify content record A. The other of the identifiers e.g. the identifier for content record B may be associated with and or identify content record B. The one or more identifiers e.g. identifiers may be part of the content group or separate therefrom.

In some embodiments the one or more identifiers are unique e.g. selected so as to be unique within the processing system in which it resides e.g. the processing system that includes the content with which they are associated but not necessarily unique within the system or landscape . For example the identifiers may be unique within the processing system but not necessarily unique within the system or landscape . This may be because the processing system may not be aware of and or concerned with identifiers used within the other processing systems of system or landscape . Identifiers that are not necessarily unique within the system or landscape are sometimes referred to herein as local identifiers.

In some other embodiments the one or more identifiers are unique e.g. selected so as to be unique within the system or landscape . In some of such embodiments the one or more identifiers may comply with an identifier scheme that is used by the CLM system and further described herein sometimes referred to herein as a CLM or global identifier scheme. Identifiers that comply with the CLM identifier scheme are sometimes referred to herein as CLM or global identifiers.

The application may further include and or otherwise provide access to metadata regarding a content group. For example application A may further include and or otherwise provide access to metadata regarding the content group .

In some embodiments content may be shared between two or more of the applications. For example application B may also include and or otherwise provide access to the content group .

In some embodiments each of the processing systems may or may not be the same as one another. In some embodiments each of the processing systems are independent from one another. Although the processing systems are represented as separate blocks in some embodiments there is no requirement that each processing system is on a separate machine. In some embodiments two or more of the processing systems may be on the same machine. In some embodiments the CLM system is on the same machine as another one of the processing systems .

In some embodiments there may be only one CLM system e.g. CLM system in the system or landscape . In some embodiments the system may include a plurality of copies of an application and each of the plurality of copies of the application may be associated with and executed on a respective one of the plurality of processing systems .

In some embodiments one or more of the processing systems comprises an advanced business application programming ABAP processing system such as for example an SAP application server that execute one or more programs written in ABAP language.

It would be desirable to provide a system that assists in a life cycle management process for one or more of the processing systems.

For example from time to time it may be desirable to transfer content from one or more of the processing systems e.g. a processing system for a supplier to one or more of the other processing systems e.g. a processing system for a customer .

It would also be desirable to provide the ability to determine whether content received by a processing system is another version e.g. a same version or a different e.g. newer version of content previously received by such processing system.

In some embodiments the CLM system may receive information indicating that one of the processing systems e.g. processing system has content e.g. content group that is to be provided to the CLM system and made available to one or more processing systems. As further described herein in some embodiments the information may be supplied by a graphical user interface in response to input from a user e.g. an administrator .

Thereafter the CLM system may receive the content e.g. content group and at least one identifier e.g. identifiers from the processing system e.g. processing system . The content may be received all at once or in parts. The at least one identifier may identify the content and may be received together with or separate from the content.

In some embodiments the content comprises a plurality of content records e.g. content records and or the at least one identifier comprises a plurality of identifiers e.g. identifiers . In some embodiments each of a plurality of identifiers may be associated with and identify a respective one of a plurality of content records e.g. identifiers may be associated with and identify content records respectively . In some embodiments the receiving of content and the at least one identifier may be performed by extracting the content and at least one identifier from the processing system e.g. processing system as further described herein.

The CLM system may determine based at least in part on the at least one identifier whether the content is another version of content previously received by the CLM system . In some embodiments the CLM system may not have previously received a version of the content. In some embodiments the content may be a same version or a different e.g. newer version of content previously received by the CLM system.

If the CLM system determines based at least in part on the at least one identifier that the content is another version of content previously received by the CLM system the CLM system may compare the content to the content previously received by the CLM system in order to determine whether the content is a same version of content previously received by the CLM system or whether the content is a different e.g. newer version of content previously received by the CLM system. If the content is a same version of content previously received by the CLM system the CLM system may not save the content that is a same version of content previously received by the CLM system. If the content is a different version of content previously received by the CLM system the CLM system may save the content that is a different version of content previously received by the CLM system. The CLM system may also provide one or more version indicator indicating that the content is a different version of content previously received by the CLM system.

In some embodiments the CLM system determines whether the content received by the CLM system includes a content record that refers to another content record not included in the content received by the CLM system. If the CLM system determines that the content includes a content record that refers to another content record not included in the content the CLM system may consider and or treat the content as bad or inconsistent e.g. lacking in referential integrity . In some embodiments the CLM system may provide a status indicator indicating that the content and or content record is bad or inconsistent e.g. lacking in referential integrity .

If the at least one identifier includes a local identifier the CLM system may determine whether the local identifier has already been mapped to a CLM or global identifier. In some embodiments if the local identifier has already been mapped to a CLM or global identifier the CLM system determines a CLM or global identifier based at least in part on the mapping. In some embodiments if the local identifier has not already been mapped to a CLM or global identifier the CLM system generates a one to one mapping from the local identifier to a CLM identifier. In some embodiments the one to one mapping from local identifier to CLM identifier is one to one in the context of one CLM system and the second processing system. In some embodiments if the local identifier has not already been mapped to a CLM or global identifier the CLM system assumes the content entity in question has not previously been checked in to the CLM system it then generates a global identifier for that entity stores it in its repository and creates a mapping entry relating the received local identifier to the newly generated global identifier.

In some embodiments if the at least one identifier is a local identifier the CLM system determines that the content is another version another copy of same version or a different e.g. newer version of content previously received by the CLM system only if the CLM system has a global identifier to which the at least one identifier has been mapped.

The CLM system may receive information indicating that a processing system e.g. one of processing systems is to receive the content. As further described herein in some embodiments the information may be supplied by a graphical user interface in response to input from a user e.g. an administrator .

Thereafter the CLM system may transmit the content at least one identifier and version information to the processing system. The content may be transmitted all at once or in parts. The at least one identifier transmitted by the CLM system may be based at least in part on the at least one identifier received by the CLM system and may be transmitted with or separate from the content.

In some embodiments the CLM system determines whether any of at least one CLM identifiers associated with the content are mapped to a local identifier for the processing system to which the content is to be transmitted. If so each CLM identifier that is so mapped may be replaced by the local identifier to which it is mapped.

In some embodiments the version information indicates whether the transmitted content is another version of content that has been previously transmitted by the CLM system to the processing system. In some embodiments the content is a same or different e.g. newer version as previously received by the processing system.

In some embodiments the version information may be anything that could be used to indicate whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system. In some embodiments it could be a flag that indicates whether or not the content is new or a revision update or a deletion. In some embodiments it could be a version number or anything else that indicates whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system. Thus in some embodiments it may indicate an actual version. In some other embodiments it may not.

In some embodiments the content may comprise an entire content group received from the second processing system. In some other embodiments the content may comprise only a portion of a content group that is received from the second processing system.

In some embodiments the transmitting of content and at least one identifier may be performed by deploying the content and at least one identifier from the CLM system to the processing system as further described herein.

Referring to in accordance with some embodiments and as stated above the CLM system may receive the content the one or more identifiers and the metadata . The CLM system may generate the version indicator and version indicator which may be indicative of the version of content record A and the version of content record B respectively. The CLM system may also generate the status indicator and the status indicator which may be indicative of the status e.g. good bad of content record A and the status of content record B respectively.

As stated above in some embodiments the one or more identifiers received from the processing system may be local identifiers rather than CLM or global identifiers.

If either of the identifiers is a local identifier the CLM system may determine whether the local identifier has already been mapped to a CLM or global identifier. If the local identifier has already been mapped to a CLM or global identifier the CLM system may determine a CLM or global identifier based at least in part on the mapping. If the local identifier has not already been mapped to a CLM or global identifier the CLM system generates a one to one mapping from the local identifier to a CLM identifier. The mapping is necessarily one to one only in the context of the CLM system and the local identifier s system it may optionally also be one to one in wider contexts for example across an entire landscape.

Mapping represented in by a table is an example of a one to one mapping between local identifiers received from a processing system e.g. processing system and CLM or global identifiers generated by the CLM system in association with the processing system e.g. processing system . That is a mapping that associates each local identifier that has been received from a particular processing system with the CLM or global identifier that has been generated and is associated with and or identifies the same content as the local identifier. In some embodiments the CLM system maintains a similar mapping for each processing system in the system or landscape .

In some embodiments the CLM system stores information for a plurality of content groups. In some embodiments the information stored for some or all of the content groups is the same and or similar to the information shown in for the content group .

Referring to in accordance with some embodiments a CLM or global identifier that is mapped to a local identifier may comprise a plurality of fields .

A first field may comprise an originating vendor identifier. In some embodiments the originating vendor identifier comprises a unique identifier assigned to the vendor of the content. In some embodiments the unique identifier is set at the CLM repository level. An example of an originating vendor identifier is SAP .

A second field may comprise a repository identifier. In some embodiments the repository identifier is an identifier of a CLM repository. An example of a repository ID is Repo24 . In some embodiments the repository identifier defaults to a null string.

A third field may comprise an authoring source identifier. In some embodiments each adapter which may be unique to each system client configuration from which checkpoints may originate may have a CLM name maintained as a CLM configuration. In some embodiments the authoring source identifier field comprises the CLM name maintained as a CLM configuration. In some embodiments the authoring source identifier field defaults to a null string. An example of an authoring source identifier is OG e.g. representing oil and gas .

A fourth field may comprise an application namespace field. In some embodiments the application namespace field may comprise the XML namespace of application metadata. In some embodiments the fourth field comprises a two part entity type. A first part may comprise the schema of the application under which the entity type is defined. The second part may comprise the name of the type. An example is Grc rm 1 .

A fifth field may comprise a content record type field. In some embodiments the content record type field comprises an entity type corresponding to the content record type described in the application metadata. An example is CRisk .

A sixth field may comprise a content record instance field sometimes referred to herein as a local ID. In some embodiments the content record instance field comprises a number that distinguished the entity instance making it unique with the content group. In some embodiments the sixth field comprises an alphanumeric or other type of ID string. An example is 1011 .

Thus an example of a complete CLM identifier in accordance with some embodiments is sap repo24 og grc rm 1 crisk 1011 .

In some embodiments the namespace content record and content record instance number all each derived from the content extracted from the application instance. In some embodiments the remaining fields may be derived from data obtained from the application registration and the CLM repository.

The method and of the other methods described herein may be performed by hardware software including low level language code or any combination of these approaches. Moreover a storage medium may store thereon instructions that when executed by a machine result in performance according to any of the embodiments described herein.

The method is not limited to the order shown in the flow chart. Rather embodiments of the method and any method disclosed herein may be performed in any order that is practicable. Moreover some embodiments may employ one or more portions of a method without one or more other portions of a method.

At the method may include receiving by a first processing system e.g. CLM system information indicating that a second processing system e.g. one of processing systems has content that is to be provided to the first processing system. The information may be supplied by a graphical user interface in response to input from a user e.g. an administrator .

At the method may further include receiving by the first processing system e.g. the CLM system content and at least one identifier from the second processing system e.g. one of processing systems . The content may be received all at once or in parts. The at least one identifier may identify the content and may be received together with or separate from the content.

In some embodiments the content comprises a plurality of content records and the at least one identifier comprises a plurality of identifiers each one of the plurality of identifiers being associated with and identifying a respective one of the plurality of content records. If the at least one identifier includes a local identifier a determination may be made as to whether the local identifier has already been mapped to a CLM or global identifier. If the local identifier has not already been mapped to a CLM or global identifier a CLM or global identifier may be determined based at least in part on the mapping. If the local identifier has not already been mapped to a CLM or global identifier a mapping from the local identifier to a CLM or global identifier may be generated.

In some embodiments a determination may be made as to whether the received content includes a content record that refers to a content record not included in the received content received by the CLM system. If so the content may be considered and or treated as bad e.g. lacking in referential integrity . In some embodiments one or more status indicators may be generated to indicate whether the content and or a content record is bad e.g. lacking in referential integrity .

In some embodiments the receiving is accomplished by extracting the content and at least one identifier from the second processing system after receiving the information indicating that the second processing system has content to be provided to the first processing system e.g. the CLM system using a method further described herein. In some embodiments the receiving of content and the at least one identifier is performed using an extraction portion of a method described with respect to . In some embodiments one or more other portions of the method of may be performed before after and or in association with the extraction.

At the method may further include determining by the first processing system e.g. the CLM system and based at least in part on the at least one identifier whether the content is another version of content previously received by the first processing system e.g. the CLM system .

In some embodiments the first processing system e.g. the CLM system may not have previously received a version of the content. In some other embodiments the content may be a same version or a different e.g. newer version of content previously received by the system. In some embodiments the method may determine that the content is another version of content previously received by the first processing system e.g. the CLM system only if the CLM system has received the at least one identifier from the processing system more than once. If the content is another version of content previously received by the first processing system e.g. the CLM system the method may further include comparing the content to the content previously received in order to determine whether the content is a same version of the content previously received or whether the content is a different e.g. newer version of the content previously received. One or more version indicators may be provided to indicate whether the content is a different version of content previously received.

At the method may include receiving by the first processing system e.g. the CLM system information indicating that a third processing system is to receive content from the first processing system e.g. the CLM system . The information may be supplied by a graphical user interface in response to input from a user e.g. an administrator .

At the method may further include transmitting by the first processing system e.g. the CLM system the content at least one identifier and version information to the third processing system. The content may be transmitted all at once or in parts. The at least one identifier transmitted by the first processing system e.g. the CLM system may be based at least in part on the at least one identifier received by the first processing system e.g. the CLM system and may be transmitted with or separate from the content.

In some embodiments the version information indicates whether the content is another version of content that has been previously transmitted by the first processing system e.g. the CLM system to the third processing system. In some embodiments the content is a same or different e.g. newer version as previously received by the processing system.

As stated above in some embodiments the version information may be anything that could be used to indicate whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system. In some embodiments it could be a flag that indicates whether or not the content is new or a revision update or a deletion. In some embodiments it could be a version number or anything else that indicates whether the transmitted content is another version of content that has been previously transmitted by the first processing system to the third processing system. Thus in some embodiments the version information may indicate an actual version. In some other embodiments it may not.

In some embodiments the at least one global identifier comprises a global identifier and the determining whether the content is another version of content previously received by the first processing system comprises determining based at least in part on the global identifier that a version of the content has been previously received by the first processing system and determining based at least in part on the content that the content is a same version or a different version of content previously received by the first processing system.

In some embodiments the version of the content previously received comprises a plurality of records and the method further comprises comparing the content to the version of the content previously received to identify one or more of the following changes to the content compared to the version of the content previously received a first one of the plurality of records in the content is a same version as a first one of the plurality of records in the version of the content previously received a second one of the plurality of records in the content is a different version from a second one of the plurality of records in the version of the content previously received a third one of the plurality of records in the content is not another version of any of the plurality of records in the version of the content previously received or one of the plurality of records in the version of the content previously received is omitted from the plurality of records in the content. In some embodiments the method further comprises providing a user interface to allow a user to reject one or more of the identified changes. In some embodiments the method further comprises transmitting content from the first processing system to the third processing system based at least in part on the users choices.

In some embodiments the transmitting is accomplished by deploying the content and the at least one identifier to the processing system after receiving the information indicating that the processing system is to receive content from the CLM system using a method further described herein. In some embodiments the transmitting is performed using a deploying portion of a method described with respect to . In some embodiments one or more other portions of the method of may be performed before after and or in association with the deploying.

As stated above in some embodiments the information e.g. indicating that a processing system has content that is to be provided and or indicating that a processing system is to receive content received by the CLM system may be supplied by a graphical user interface in response to input from a user e.g. an administrator . In some embodiments the information received by the CLM system may be supplied by a graphical user interface in response to input from a user e.g. an administrator as described hereinafter with respect to .

Referring to in accordance with some embodiments the view may include a plurality of graphical tools e.g. a tool to select a type of view that is desired for the view and tools labeled Extract View Edit View Differences Deploy Delete View History Deployment Log and Mass Edit . Activation of one of the tools e.g. the tool labeled Extract may request a view that may be used to request and or otherwise indicate content to be transferred to the CLM system from one of the processing systems .

Referring to in some embodiments the view may include a window that may be used to request and or otherwise indicate content to be transferred to the CLM system from one of the processing systems .

The window may include a graphical tool that may be used to select a particular processing system that includes the content that is to be provided to the CLM system . In some embodiments the graphical tool comprises a drop down menu that lists names of processing systems that have been registered with the CLM system . The graphical tool may allow selection of a name of one of the listed processing systems. The second processing system in the list is shown selected.

The window and or another window not shown may include a graphical tool not show that may used to select a particular application that is on the selected processing system and includes and or otherwise has access to the content that is to be provided to the CLM system . In some embodiments such graphical tool comprises a drop down menu that lists names of applications that are on the selected processing system and that have been registered with the CLM system . The graphical tool may allow selection of a name of one of the listed applications.

The window may further include a plurality of graphical tools that allow a user to select a view e.g. a text box labeled View provide a description of the content to be transferred to the CLM system e.g. a text box labeled Description provide a comment associated with the content e.g. a text box labeled Description request transfer of the content the CLM system e.g. a graphical tool labeled Save and or cancel the request for the view e.g. a graphical tool labeled Cancel .

If the user requests that the content be transferred to the CLM system e.g. a graphical tool labeled Save the CLM system may then extract the specified content from the selected application. As further described herein in some embodiments a subset of content exposed by the application may be controlled by the application and returned or otherwise transferred to the CLM system via XML.

Referring again to activation of another one of the tools e.g. the tool labeled Deploy may request a view that may be used to request and or otherwise indicate a processing system to which content is to be transferred to from the CLM system .

In some embodiments prior to activating such graphical tool e.g. the tool labeled Deploy one or more graphical tools may be used by a user to select and or otherwise indicate the content to be transferred to the processing system from the CLM system .

In that regard the view may include a plurality of graphical tools to specify a search criteria e.g. a tool to specify a search string a tool to specify a from date e.g. an earliest date of creation or last change a tool to specify a to date e.g. a latest date of creation or last change and a tool e.g. a tool labeled go that may be activated to initiate performance of the search .

The view may further include a table showing some or all results of the search. In some embodiments the search may be performed on the content groups e.g. received from processing systems within the system and or on packages e.g. received from other landscapes . In some embodiments the table may show results of the search on content groups if a graphical tool e.g. shown as a tab labeled content groups has been activated and may show results of the search on packages if a graphical tool e.g. shown as a tab labeled packages has been activated.

In some embodiments the table may include a plurality of rows and a plurality of columns. The first row may define a header that includes a plurality of titles e.g. ID Status Name Description Application Type Created On Created By Last Change Date Last Change Time Changed By and Source System each of which may be associated with a respective one of the plurality of columns and may indicate the type of information that is listed in the respective one of the plurality of columns.

Each of the other rows may define a line item sometimes referred to herein as an entry that includes an ID a Status a Name a Description an Application a Type a Created On a Created By a Last Change Date a Last Change Time a Changed By and a Source System associated with particular content e.g. a particular content group or package . The ID may indicate an ID assigned to and or otherwise associated with the particular content the Status may indicate a status for the particular content e.g. where good is indicated by a green or clear indicator and bad is indicated by a red or dark indicator the Name may indicate a name assigned to and or otherwise associated with the particular content the Description may indicate a description for the content the Application may identify an application e.g. run and or executed by one of a processing systems from which the particular content was received the Type may indicate a type of classification for the particular content the Created On and Created at may indicate a date and a time respectively that a first version of the particular content was stored in the CLM system the Last Change Date and a Last Change Time may indicate a date and a time respectively that a last version of the particular content was stored in the CLM system the Changed By may indicate a name of a person that made and or otherwise requested the last change to the particular content and a Source System may indicate a name of a processing system that runs and or otherwise executes the application from which the particular content is received.

In some embodiments a user may select an entry in the table to select and or otherwise indicate the content to be transferred to the processing system from the CLM system . described below shows the third line item of the table as being selected.

Thereafter one of the graphical tools e.g. the tool labeled Deploy may be activated to request the view that may be used to request and or otherwise indicate a processing system to which the selected content is to be transferred.

Referring to in some embodiments the view may include a window that may be used to request and or otherwise indicate the processing system to which the selected content is to be transferred.

The window may include a graphical tool that may be used to select the particular processing. In some embodiments the graphical tool comprises a drop down menu that lists names of processing systems that have been registered with the CLM system . The graphical tool may allow selection of a name of one of the listed processing systems. The third processing system in the list is shown selected.

The window may further include a plurality of graphical tools that allow a user to request that the content be transferred to the selected processing system e.g. a graphical tool labeled Deploy to request a deployment log e.g. a graphical tool labeled Deployment Log and or to close the window without transferring the content e.g. a graphical tool labeled close .

If the user requests that the content be transferred to the selected processing system e.g. a graphical tool labeled Deploy the content may then be transferred to the selected processing system for deployment.

As stated above in some embodiments the content received by the CLM system may be another version i.e. a same version or a different version of content previously received by the CLM system . If the content is a different version of content previously received the content may be viewed as having one or more changes compared to the content previously received. In some embodiments the CLM system may provide a user with the ability to indicate that the content is to be transferred to another processing system without one or more of the changes. In some embodiments the CLM system may provide the ability to accept or reject the changes on a content record by content record basis.

Referring to in some embodiments the view includes a first area that identifies a name of a first content group e.g. exported process control 10.0 ml and a name of a second content group e.g. Process Control . The area may further include a graphical tool e.g. a button labeled compare activation of which may initiate a comparison between the content records in the first content group e.g. exported process control 10.0 ml and the content records in the second content group e.g. Process Control .

In some embodiments the comparison may determine for each content record in the first content group whether the content record is a same version as a content record in the second content group a different version from a content record in the second content group and or not another version of any content records in the second content group. In some embodiments the comparison may also determine all of the content records in the second content group that are omitted from the first content group.

In some embodiments each content record in the first content group will be compared to a content record that is in the second content group and has the same global identifier as that of the content record in the first content group if such a content record in the second content group exists. Thus in some embodiments the comparison compares content records having matching global identifiers.

A content record in the first content group that is a same version as a content record in the second content group is sometimes referred to herein as an unchanged content record. A content record in the first content group that is a different version from a content record in the second content group is sometimes referred to herein as an updated or modified content record. A content record in the first content group that is not another version of any content record in the second content group is sometimes referred to herein as a new or added content record. A content record in the second content group that is omitted from the first content group is sometimes referred to herein as a deleted content record.

The view may further include a table that indicates one or more results of the comparison. In some embodiments the table may include a plurality of rows and a plurality of columns. The first row may define a header that includes a plurality of titles Type of Change Schema Content Record Vendor Name Repository ID Authorizing Do . . . Local ID Name Description Time Stamp Changed By Created By and Decision each of which may be associated with a respective one of the plurality of columns and may indicate the type of information that is listed in the respective one of the plurality of columns. Each of the other rows may define a line item sometimes referred to herein as an entry that is associated with a content record in the first content group and or second content group and indicates whether the content record is changed and if so the type of change. Each line item or entry may include a graphical tool e.g. a graphical tool disposes in a column e.g. the Decision column to indicate a user s choice as to whether to accept or reject the change associated with the content record.

Although the illustrated embodiment of table happens to include only changes that are updates modified for some comparisons of some content the table may include updates additions and or deletions all in the same table.

In some embodiments the comparison and or results are limited to content records that satisfy a search criteria e.g. as indicated by a graphical tool labeled CRGROUP 

In some embodiments the view may further include a second area that provide further details regarding changes. In some embodiments the content record in the first content group and the content record in the second content group each have a field and a value associated with the field. If a change is an update the value associated with a field in the first content group may be different than the value associated with the field in the second content group.

In some embodiments content is transmitted from the CLM system to another processing system based at least in part on the users choice s . In some embodiments if a user chooses to reject a change that is an update the updated content record is not included in the content transmitted from the CLM system to the other processing system. In some embodiments if a user chooses to reject a change that is an addition the new or added content record is not included in the content transmitted from the CLM system to the other processing system. In some embodiments if a user chooses to reject a change that is a deletion the deleted content record is not omitted from the content transmitted from the CLM system to the other processing system.

In some embodiments the CLM system interacts with applications that are executed by a processing system.

To that effect in some embodiments the CLM system defines an application programming interface API for exchange of information and or for configuring interaction between the CLM system and an application or applications executed by a processing system.

In some embodiments one or more applications of one or more of the processing systems implement at least some of the API s defined by the CLM system in order to exchange information with and or configure an interaction between the CLM system and the one or more applications of the one or more processing systems.

Table 1 shows an API that may be defined by the CLM system for exchange of information and or for configuring interaction between the CLM system and an application of a processing system in accordance with some embodiments is set forth below in Table 1.

As will be further described below in some embodiments an adapter is used to implement one or more of the API s defined by the CLM system.

As stated above in some embodiments an adapter is used to implement one or more of the API s defined by the CLM system.

Referring to in accordance with some embodiments an adapter sometimes referred to as a CLM adapter may be provided between an application e.g. the application of processing system and the CLM system. The adapter may implement one or more portions of an API defined by the CLM system as may be required in order to allow for exchange of information between the application and the CLM system. In some embodiments the adapter is only a thin layer adapting the CLM API to the needs of the application.

The CLM system may consider the adapter to be part of the application and may otherwise be independent of the applications and unaware of how the applications are implemented. As further described herein in some embodiments the adapter may need to support a particular configuration and or it may need to return information to indicate the CLM behaviors it supports. For example as further described herein if chunking of content is supported the size of the chunks may be negotiated based on a minimum amount that the adapter can handle and a minimum amount that the CLM system can itself handle.

An adapter is not limited to an adapter between the application and the CLM system. In some embodiments an adapter e.g. which may be similar to the adapter in one or more respects may be provided between the CLM system and any other application that is to exchange of information with the CLM system. Such adapter may implement one or more portions of an API defined by the CLM system as may be required in order to allow for exchange of information between the CLM system and such any application.

Referring to in accordance with some embodiments at the method may include registering one or more applications with the CLM system .

In some embodiments such registering may comprise storing information in a registry in the CLM system which may include e.g. store information identifying applications that are registered with the CLM system . The registry may further include information identifying functions that implement the CLM API s for each of such applications. Thus the registry may be used in determining how to access a logical unit with which the CLM system can exchange information.

In some embodiments the registry comprises a table having a plurality of rows or line entries e.g. where each of such rows or line entries is associated with an application registered with the CLM system system and with which the CLM system can interact.

Table 2 shows a portion of a registry that includes information for registration of various applications in accordance with some embodiments.

Based on the information in Table 2 it can be seen that in some embodiments an application named GRC RM runs on System A System B and System D. An application named GRC PC runs on System C. A machine which may be one of the processing systems at location 192.168.0.21 runs two of the versions of the application named GRC RM which are separated somehow by the machine. The machine at location 192.168.0.21 also runs the application named GRC PC. A machine at location 10.10.0.126 runs the other version of the application named GRC RM.

In some embodiments the information that is included in the registry is supplied via an administrative user interface not shown which may be provided by the CLM system to allow an administrator to supply such information.

In some embodiments a provider of CLM systems may test a CLM system with various applications and may store information in the registry prior to shipping the CLM regarding the configuration of the applications that have been tested with the CLM system.

At the method may further include configuring information about the applications that are registered with the CLM system and with which the CLM system can interact . This information sometimes referred to herein as configuration information may include information about the functions that implement one or more portions of the CLM API for such applications and in turn provide metadata associated with such applications. In some embodiments the configuration information is stored in a table sometimes referred to herein as a configuration table.

Based on the information in Table 3 it can be seen that an application named GRC RM implements the CLM setup API using a method named grrm clm setup.

In some embodiments neither the metadata nor the set of functions associated with an application is intended to vary over the life of the CLM system. Therefore whenever content is identified as belonging to a particular application the content can be extracted and deployed using the same set of functions and with the same structure as described by the various metadata and schema .

At the method may further include performing a setup which may include obtaining application metadata that describes some or all content that is exposed by an application via the CLM API. In some embodiments the metadata may be in an XSD format.

At the method may further include metadata processing e.g. by parsing metadata in an XSD format to determine some or all of the following a namespace for the content types of content records available relationships and dependencies between content records a cardinality of content records and an order of content records.

In some embodiments the metadata must be consistent across Landscapes and processing systems within a Landscape. In such embodiments the CLM system may store the metadata by the namespace reported by the metadata itself. If an application returns inconsistent metadata for this namespace it is considered an error. A revised version of the metadata requires a new namespace which might only differ by an embedded version number . In some embodiments all content is qualified by and associated with the namespace after it has been received by the CLM system. Some embodiments for doing so are further described below.

Table 4 shows a listing for a portion of a content group in accordance with some embodiments. In accordance with some embodiments the portion of the content group includes two content records content record A and content record B. Each content record provides information regarding the animal kingdom. More particularly content record A describes two types of body coverings i.e. short fur and short hair. Content record B describes 3 types of animals i.e. cats dogs and wolf. The reference field in content record B links to the body coverings in content record type A in order to link each type of animal to its type of body covering.

In some embodiments the metadata identifies relationships between entities e.g. content records as XSD Keys and KeyRefs or by using some other convention . Consequently following the parse of the metadata the CLM system knows the fields within an entity that are reference fields.

Referring to in accordance with some embodiments the representation defines two content records i.e. content record A and content record B . Each of the content records has an attribute ID that holds the content record ID either a local ID or a CLM ID . For example in the representation the content record A has an attribute ID that holds the content record ID for content record A. The content record B has an attribute ID that holds the content record ID for content record B. In some embodiments local IDs for content records must be unique within the XML document and must be returned consistently for each and every extract of the content from a given application instance.

Each content record may also have a Key by which the content record can be referenced. The Keys refer to a content record s position within the document its path and its ID. Content record A thus has a Key i.e. Key A that refers to content record A s position within the document its path i.e. A and its ID i.e. ID. In the representation content record B has a Key i.e. Key B that refers to content record B s position within the document its path i.e. B and its ID i.e. ID.

The representation also shows a relation between content record A and content record B. A KeyRef i.e. REFERENCE A FROM B holds a value of a Key A from any of the KEY As contained in the document. The KeyRef also refers to the position of a reference within the document its path i.e. B and its name i.e. F REF TO A.

Referring to in accordance with some embodiments the sequence of calls may include a call to a setup method a call to a get adapter info method a call to a get metadata method one or more calls to extract upload and or deploy methods and a call to a release job method .

The call to the setup method the call to a get adapter info method and the call to the get metadata method may be made in performing the setup and metadata processing functions and in response the application or the adapter of the application may return information exposed by the setup method the get adapter info method and the get metadata method respectively.

Thereafter call to the release job method may be made to release the job and any resource associated with the job as further described below. Following invocation of this function the application or adapter of the application may not be expected to track the job status anymore.

Referring again to at the method may further include a content query. For example in some embodiments an application supports querying or selective retrieval of content and a content query function returns information needed to form such queries as XML. The process of forming a query may be application specific and may involve passing query information to an application specific component or user interface that is used to form a query. As a result the CLM system may not interpret or process the query information directly. In some embodiments no XSD is provided by the CLM system for the EV CONTENT parameter by CLM. In some embodiments the CLM system may optionally embed an application specific component to render the query information allow the user to make a selection of that information and format a query string that can then be returned to the application during the content extraction and deployment processes.

Referring to in accordance with some embodiments the call may include a call to a get query info method .

Referring again to at the method may further include extracting content. In some embodiments this may be performed by calling a function defined by the CLM API e.g. extract content to extract the content. After the content is extracted the extracted content may be serialized as XML complying to an XML format described by the metadata of the application from which the content is extracted.

The volume of content to be extracted may vary according to the application and the processing system. In some cases a single CLM function call e.g. extract content may be used to extract all of the content. However in some other cases the volume of content to be extracted may exceed what can be returned to the CLM system by a CLM function call. To accommodate such cases the CLM system may support chunking of content such that the content may be extracted in blocks i.e. portions sometimes referred to herein as chunks. If chunking is supported one block of the content may be returned in response to each function call e.g. extract content . The size of the block may be in accordance with parameters exchanged during a setup of the adapter e.g. min and max chunk sizes . The extract portion may repeatedly call the function defined by the CLM API e.g. extract content until all of the content has been extracted. An application may indicate that it has sent all content to be extracted by setting a flag e.g. a has more flag to false. The chunks may not be considered valid in and of themselves. Thus content that is received as chunks may not be processed until all chunks have been received and the chunks have been reassembled.

As described above in some embodiments a user begins the extract process by clicking an Extract button in a user interface. On Extract the CLM system may then allow the user to select one of the target system and application combinations that they have registered. The CLM system may then extract the content from the specific application. The subset of content exposed by the application may be controlled by the application and returned to the CLM system via XML. The application may also return metadata that describes the content.

As further described below the CLM system may then parse the XML and store the content in its database. In some embodiments the content is read only and the CLM system does not allow editing of the content within an individual content group. The extracted content group may tagged by user date time system application and status.

Referring to in accordance with some embodiments the sequence of calls may include a call to a start extract method one or more calls to an extract content method a call to end extract method .

Referring again to at the method may further include parsing the extracted content. In some embodiments parsing splits the content group into content records.

Information about success and or failure of the parse may be logged and the state of the content group may be updated based on such results.

If a parse is not able to successfully parse 100 of the content group the content group may be treated as bad. In some embodiments if a content group is bad it cannot be deployed or packaged for export by CLM.

In some embodiments the CLM system may parse in a top to bottom order in the XML document depth first.

In some embodiments all references or relations must be backward references that is no reference may be to a content record that has not yet been parsed by the CLM system.

At and after parsing each of the content records may be checked against the metadata provided by the application and or for structural integrity i.e. that the required fields are present and in the correct numbers. If a content record fails the check the content record may be deemed bad. If a content record is deemed bad the entire content group may also be deemed bad although in some embodiments processing may continue.

Each of the content records may be stored in a database sometimes referred to herein as a CLM database or CLM repository. In some embodiments storing is performed prior to checking the content records. In some other embodiments the storing is performed after checking the content records.

At the method may further include identification. Initially each content record may be stored in association with the associated ID provided in the extracted XML. However as described above if the ID provided is not a CLM managed ID the CLM system may generate a CLM Managed ID for the content record.

Each field that is a reference or relation to another content record thereby containing a content record ID may also be updated with the CLM ID instead of the Local ID.

As described above the CLM system may maintain a map e.g. a mapping table of Local IDs to CLM IDs for each system registered with CLM. Thus prior to generating a CLM ID the CLM system determines whether a CLM identifier has already been generated for the local ID. If the Local ID is found in the mapping for the source system i.e. a CLM ID has already been generated for the local ID in the source system then the CLM ID already generated for the local ID will be used i.e. the local ID in the extracted content will be replaced by the CLM ID associated with the local ID . If the local ID is not found in the mapping i.e. a CLM ID has not already been generated for the local ID in the source system then a new CLM ID is generated and a mapping between the local ID and the CLM ID is added to the mapping of Local IDs to CLM IDs for that system.

At the method may further include versioning. If it is determined that a CLM ID has already been generated for the local ID then a version of the content record and its local ID have appeared in a previous extraction and may still be stored in the CLM system and the version of the content record in the current extraction may be treated as an update to the content in the previous extraction.

In some embodiments the version of the content record in the current extraction is compared to the version of the content record in the previous extraction.

In some embodiments this comparison is performed by determining a cryptographic hash e.g. an MD5 hash for the content record in the current extraction. The hash of the content record may then be compared to a similar type of hash determined for the corresponding content record i.e. the content with the same ID in the previous extraction. If there are multiple previous versions of the content record i.e. from multiple extractions the hash of the content record in the current extraction may be compared to multiple hashes each being associated with a respective one of the multiple previous versions of the content record. In some embodiments the comparison is performed after all local ID s in the content group have been replaced by the CLM ID s mapped thereto.

If a match is found then the matching previous version is referenced and or otherwise indicated as being part of the content group in the current extraction.

If a match is not found then the new version of the content record is stored versioned and persisted to the CLM database. In some embodiments the new version of the content record is versioned by based at least in part on a timestamp and or a monotonically increasing counter.

At the method may further include reference checking. In some embodiments after the content group has been parsed the content records are checked to ensure that the relations are all resolved that is that the content group contains all the content records that are referenced within the content group.

In some embodiments all the references between content records must be resolved within a single content group. Without this constraint the CLM system would have to maintain dependencies between content groups in order to ensure referential integrity.

If a reference is not resolved the content record that includes that reference is treated as a bad. In some embodiments the rest of the content group i.e. the content group that includes the bad content record may also be treated as bad.

In some embodiments if a content group is bad then it cannot be deployed or packaged for export by CLM the system.

At the method may further include comparing content groups with compatible content groups i.e. content groups that have the XML namespace.

In some embodiments the CLM system may compare content groups by iterating over the content records and comparing content records one by one. If an existing content record is different than a recently extracted content record it is marked as an Update. If the source i.e. the previously extracted content group for a comparison does not include a content record that appears in the target of the comparison i.e. the most recently extracted content group then the content record is marked as an Addition. If the target for the comparison does not include a content record that is included in the source then the content record is marked as a Deletion.

The results of a comparison of content groups can be saved as a content group. A comparison content group is a union of the source and target content groups plus the comparison status for each content record.

In some embodiments the CLM system provides a user interface that indicates for a user any differences that were identified through the comparison process. The user interface allows the user accept or reject the changes. Rejection of a change means that a content record newly marked as an addition will not be added to the deployment target a content record newly marked as a deletion will not be deleted on the deployment target or that a particular change will not occur on the deployment target.

For purposes of referential integrity even rejected changes are included in a comparison content group.

In some embodiments the user interface of the CLM system includes a facility e.g. a view or set of views in the user interface to see the relations between content records as a where used list.

In some embodiments the CLM system includes sufficient information to traverse relationships and prevent changes that might compromise referential integrity. Therefore during deployment of a change the CLM system can modify the comparison status so that an application is given a valid content group. In some embodiments a comparison that indicates that an entity is a new content record will be sent as a changed content record if that content record already exists on a deployment target. Similarly if an addition has been rejected and some other content record references the rejected content record then the rejected content record can still be sent to the deployment target as a new content record.

At the method may further include receiving a request to deploy content to a selected processing system. In some embodiments the deployment process can begin after the CLM user has selected the target system to which content is to be deployed.

In some embodiments a user can select a content group for deployment by choosing it from a list and selecting the Deploy option in a user interface. The user may then choose the target or destination system for the content. In some embodiments the CLM system provides a user interface that offers a list of compatible system application registrations from which a user can choose a target system. After a user chooses a target system the CLM system may send the content to the target system for deployment.

As further described below in some embodiments there are several steps involved in deploying content. In some embodiments the first step is to serialize content to XML. The next step may be to upload the content to the target system. The third step may be to deploy the content. After the content is deployed the CLM system may check for errors.

At the method may further include ID mapping. In some embodiments as content records are serialized the CLM system checks its ID mapping for the processing system to which the content is to be deployed to determine if there is a Local ID for either the content records or any of their relations.

In some embodiments if a mapping is found then the Local ID is used in place of the CLM ID and it is assumed that the deployment target already has a copy of the content record. If a content record had been deleted from the target system then it would have shown up as a deletion when the content group was compared.

In some embodiments the CLM system also checks that the basis of the comparison still corresponds to the basis on which the comparison content group was calculated. Such a check can be carried out by comparing content groups or by comparing the extraction dates for the content groups.

At the method may further include serializing content to XML. In some embodiments in order to deploy a content group the content group must first be serialized to XML in order to prepare it for upload to the deployment target. In some embodiments this comprises a serialization process that combines the content with the comparison information for content groups that underwent comparison.

At the method may further include uploading of content. As with extraction in some embodiments the upload process may split the content into blocks or chunks. Again the chunks are not intended to be consumed and instead they are assembled on the target system to reproduce the complete XML document for the content group being deployed.

In some embodiments a content group need not be deployed immediately. Several attempts might also be made to deploy a content group and therefore an application Adapter may choose to hold on to an uploaded content group for an extended period.

Depending on the configuration information exchanged between the application and the CLM system upon handshaking the CLM system either uploads the content in one chunk or in multiple chunks. If more content is being sent in a chunking scenario then the more content flag is true and the application should expect more data.

Referring to in accordance with some embodiments the sequence of calls may include a call to a start upload method one or more calls to an upload content method a call to end upload method .

Referring again to at the method may further include initiating deployment. In some embodiments the deployment is initiated after the content has been completely uploaded. In such embodiments the deployment may be initiated by calling the deploy content API and the deploy content function is a signal to deploy content.

The deployment may be asynchronous or synchronous. In some embodiments if the deployment is asynchronous the function the deploy content function returns immediately and the CLM system then polls for completion of the deployment.

At the method may further include checking the deployment status. In some embodiments following deployment initiation the CLM system calls the adapter s get status method to check the deployment job status.

At the method may further include fetching results. If the job completes successfully the CLM system may then call the adapter s get results method which returns the following deployment job status results the ID mapping for NEW content records and any error or warning messages.

The deployment job status results may indicate that the deployment failed the deployment job may have completed successfully without successfully deploying the content. For example in some embodiments the content can be progressively uploaded by sending it in pieces or fragments. An application needs a flag to indicate that the last piece is being sent to know that the upload is complete. Otherwise it would have to remain open waiting for further pieces. For example even if all steps and processes in the deployment job are executed successfully the content may not be deployed if the third processing system detects any problems or conflicts with the new content such as a value being out of range .

At the method may further include parsing results. In some embodiments the XML is parsed and results are prepared for further processing. Any Content Record Identifiers are resolved to CLM IDs.

At the method may further include mapping of new entities. In some embodiments the ID mapping for NEW content records is a mapping that indicates the new Local ID for any new content records that were deployed. The new content records were sent with a CLM ID and the results therefore indicates the Local ID that corresponds to the CLM ID that had been sent in the uploaded content. The error or warning messages may use CLM or Local IDs for new Entities or Local IDs for existing content records that are being modified by the deployment.

At the method may further include releasing the adapter. In some embodiments the release job method tells the Adapter that the CLM system will no longer request operations on the uploaded content and it can then be deleted.

Some embodiments may allow content to be moved from one landscape e.g. landscape to another landscape.

Referring to in accordance with some embodiments the second system or landscape may include a second plurality of processing systems and a second plurality of communication links . A first one of the second plurality of processing systems i.e. processing system may comprise a second CLM system and is sometimes referred to herein as CLM system . The second plurality of communication links may couple the second plurality of processing systems to the second CLM system .

In some embodiments the CLM system and the plurality of processing systems are similar to the CLM system and the plurality of processing systems respectively. A communication link which may comprise a mechanism external to the system and system may enable content to be passed between the CLM system and the second CLM system .

The CLM system and the CLM system may allow content to be moved from the system or landscape to the second system or landscape and or from the second landscape to the landscape .

Referring to in some embodiments the CLM system packages content that is to be moved from the system or landscape to the system or landscape . The packaged content may be exported from the CLM system in the landscape and imported into the CLM system in the second landscape .

In some embodiments a CLM package may comprise a ZIP file containing one or more content groups serialized as XML plus some metadata that describes the content of the package. The packaged content may further include one or more attachments i.e. files that are added to the package for example PDF documentation. In some embodiments the attachments may not be linked in any way to other content in the package by any CLM enforced mechanism.

In some embodiments a content record cannot appear in more than one version within a Package. Therefore if more than one content group refers or includes a content record then all content groups that refer or include the content record must refer or include the same version of that content record.

Referring to in accordance with some embodiments the architecture includes a processor coupled to a communication device an input device an output device and a storage device .

In some embodiments the processor may execute processor executable program code to provide or otherwise result in one or more portions of one or more functions and or one or more portions of one or more methods disclosed herein. In some embodiments the processor may comprise one or more INTEL Pentium processors.

The communication device may be used to facilitate communication with other devices and or systems. In some embodiments communication device may comprise an Ethernet and or other type of connection to a network and or resource and through which architecture may receive and or transmit information.

The input device may be used to input information. In some embodiments the input device may comprise a keyboard a keypad a track ball a touchpad a mouse or other pointing device a microphone a knob or a switch an infra red IR port and or a computer media reader.

The output device may be used to output information. In some embodiments the output device may comprise an IR port a docking station a display a speaker and or a printer.

The storage device may store one or more programs and or other information for operation of the architecture . In some embodiments the one or more programs and or other information may include one or more operating systems one or more database management systems and or other applications for operation of the architecture . In some embodiments the one or more programs may include one or more instructions to be executed by the processor to provide one or more portions of one or more functions and or one or more portions of one or more methods disclosed herein. In some embodiments the one or more programs and or other information may include one or more databases .

In some embodiments the storage device may comprise one or more storage devices such as for example magnetic storage devices e.g. magnetic tape and or hard disk drives optical storage devices and or semiconductor memory devices such as Random Access Memory RAM devices and Read Only Memory ROM devices.

In some embodiments one or more portions of one or more embodiments disclosed herein may be embodied in a system a method an apparatus and or a computer readable storage medium. Some embodiments may employ one or more portions of any a system a method an apparatus and or a computer readable storage medium disclosed herein without one or more other portions of such a system a method an apparatus and or a computer readable storage medium.

In some embodiments one or more i.e. some or all portions of any embodiment disclosed herein may be performed by a processor.

In some embodiments one or more portions of any embodiment disclosed herein may result from a processor executing instructions.

In some embodiments a computer readable storage medium may store thereon instructions that when executed by a processor result in performance of one or more portions of one or more embodiments disclosed herein.

A computer readable storage medium may store thereon instructions that when executed by a processor or multiple processors result in performance of a process according to any of the embodiments described herein.

In some embodiments some or all portions of the information described in herein may be stored in one or more storage devices.

In some embodiments a processing system comprises an individual computer system consisting of one or more logical processing units.

In some embodiments an application comprises a logical software component that is accessible on its own and not as part of some other software component .

In some embodiment a content record comprises the lowest level of content that CLM can deploy manipulate.

In some embodiments chunking comprises passing of a content group s XML serialization in successive blocks or subsection that when reassembled in the order in which they were sent match the complete original XML document.

In some embodiments a local identifier ID comprises the ID used by an application instance to identify a content record.

In some embodiments a CLM ID comprises an ID used by a CLM system to identify a content record. The ID is globally unique.

Unless stated otherwise a mapping may have any form for example but not limited to a look up table a rule base hardwired logic fuzzy logic neural networks and or any combination thereof and may be embodied in software hardware firmware or any combination thereof. In some embodiments the mapping is generated manually automatically or by a combination thereof.

Unless stated otherwise terms such as for example comprises has includes and all forms thereof are considered open ended so as not to preclude additional elements and or features. In addition unless stated otherwise terms such as for example a one first are considered open ended and do not mean only a only one and only a first respectively. Moreover unless stated otherwise the term first does not by itself require that there also be a second .

In addition unless stated otherwise terms such as for example in response to and based on mean in response at least to and based at least on respectively so as not to preclude being responsive to and or based on more than one thing.

In addition unless stated otherwise a user device may comprise any type of device that may be used by a user. Thus a user device may have any form factor and may not be owned by and or assigned to a user.

In addition unless stated otherwise a database may comprise one or more related or unrelated databases.

In addition unless stated otherwise data may comprise any type of information and may have and or be stored in any form. In some embodiments data may be stored in raw excerpted summarized and or analyzed form.

Unless stated otherwise a processing system may comprise any type of processing system. For example a processing system may be programmable or non programmable general purpose or special purpose dedicated or non dedicated distributed or non distributed shared or not shared and or any combination thereof. A processing system may include but is not limited to hardware software firmware and or any combination thereof. Hardware may include but is not limited to off the shelf integrated circuits custom integrated circuits and or any combination thereof. In some embodiments a processing system will include at least one processor. Software may include but is not limited to instructions that are storable and or stored on a computer readable medium such as for example magnetic or optical disk magnetic or optical tape CD ROM DVD RAM EPROM ROM or other semiconductor memory. In some embodiments a processing system will include at least one processor that executes instructions stored on the computer readable medium. A processing system may employ continuous signals periodically sampled signals and or any combination thereof. If a processor is distributed two or more portions of the processor may communicate with one another through a communication link.

Unless stated otherwise a processor may comprise any type of processor. For example a processor may be programmable or non programmable general purpose or special purpose dedicated or non dedicated distributed or non distributed shared or not shared and or any combination thereof. A processor may include but is not limited to hardware software firmware and or any combination thereof. Hardware may include but is not limited to off the shelf integrated circuits custom integrated circuits and or any combination thereof. In some embodiments a processor comprises a microprocessor. Software may include but is not limited to instructions that are storable and or stored on a computer readable medium such as for example magnetic or optical disk magnetic or optical tape CD ROM DVD RAM EPROM ROM or other semiconductor memory. In some embodiments a processing may execute instructions stored on the computer readable medium. A processor may employ continuous signals periodically sampled signals and or any combination thereof. If a processor is distributed two or more portions of the processor may communicate with one another through a communication link.

In addition unless stated otherwise a communication link may be any type of communication link for example but not limited to wired e.g. conductors fiber optic cables or wireless e.g. acoustic links electromagnetic links or any combination thereof including for example but not limited to microwave links satellite links infrared links and or combinations thereof each of which may be public or private dedicated and or shared e.g. a network . A communication link may or may not be a permanent communication link. A communication link may support any type of information in any form for example but not limited to analog and or digital e.g. a sequence of binary values i.e. a bit string signal s in serial and or in parallel form. The information may or may not be divided into blocks. If divided into blocks the amount of information in a block may be predetermined or determined dynamically and or may be fixed e.g. uniform or variable. A communication link may employ a protocol or combination of protocols.

While various embodiments have been described such description should not be interpreted in a limiting sense. It is to be understood that other embodiments may be practiced without departing from the spirit and scope of the invention as recited in the claims appended hereto.

