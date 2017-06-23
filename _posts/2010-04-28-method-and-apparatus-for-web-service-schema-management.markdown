---

title: Method and apparatus for web service schema management
abstract: The invention relates to a method and an apparatus for web service schema management. The apparatus includes a processor; a memory including computer program code configured to, with the processor, cause the apparatus at least to perform: controlling the storing of schema information of a binary web service system, the schemas describing the encoding/decoding of binary XML messages; and providing an interface for maintaining the schema information up-to-date in each component of the binary web service system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09418052&OS=09418052&RS=09418052
owner: ARM FINLAND OY
number: 09418052
owner_city: Oulu
owner_country: FI
publication_date: 20100428
---
The invention relates to a method and an apparatus for web service schema management. In particular the invention relates to managing schemas utilized in binary web services between computer servers or nodes in computer networks.

The following description of background art may include insights discoveries understandings or disclosures or associations together with disclosures not known to the relevant art prior to the present invention but provided by the invention. Some of such contributions of the invention may be specifically pointed out below whereas other such contributions of the invention will be apparent from their context.

In modern communication and computer networks data exchange between programs and computers is a vital element. Different programs computers and processors exchange data without human intervention. Different networks and protocols are used in different environments. On the Internet the Transmission Control Protocol Internet Protocol TCP IP is the basic protocol used in communication. TCP IP takes care of assembling and disassembling the data to be transmitted in packets. IP handles the addressing so that packets are delivered to the correct destination. Above TCP IP the Hypertext Transfer Protocol HTTP is used as a client server protocol. A program may send an HTTP request to a server which responds with another HTTP message.

The exchanges of interoperable messages using APIs Application Program Interfaces provided by servers on the Internet are realized by using web services. A web service can be realized in many ways usually by using a REST Representational State Transfer design with the built in features of a web protocol like HTTP and payload encoding with Extensible Markup Language XML or realized as a remote procedure call via SOAP Simple Object Access Protocol .

SOAP is an Internet service messaging protocol which is widely used in the transmission of automated messages between computer servers on the Internet. SOAP provides an extensible format for providing message exchanges between computers to achieve any given task. At present the content of a SOAP message is encoded by using XML. XML can be used to represent any kind of information. The messages are made up of structured XML tags. When SOAP messages are transmitted over the Internet they use an application protocol such as HTTP over TCP IP or Session Initiation Protocol SIP over TCP IP.

Low power wireless networks such as IEEE 802.15.4 based embedded and sensor networks have extremely limited resources for transmitting packets. These networks are very energy efficient and the chip technology is cheap. For this reason the technology is making its way to embedded devices very quickly for automation measurement tracking and control for example.

In the low power wireless networks current web service technologies are far too complex headers content parsing and heavy large header and content overhead . Recently binary web service protocols have been developed for low power wireless networks. A binary web service solution includes the use of a suitable web service protocol such as simplified HTTP or a binary web service protocol such as Constrained Application Protocol CoAP and an efficient content encoding such as Efficient XML Interchange EXI Binary XML or Fast Infoset FI .

Typical web services use XML for content encoding making use of XML schemas having well known or easily available namespace information. Furthermore even in the absence of exact schema information an XML document can be parsed by an end point. However the same is not true in binary web services. In order to achieve the very small overhead requirements XML encoding technologies such as EXI make use of out of band Schema information so called Schema informed Mode in EXI . The deployment of binary web services requires a large range of components including embedded device clients proxies and servers. In order for this system to function most efficiently all components must have the correct schema information and be able to identify which schema to use for which binary web service payload.

Currently if a schema has been used in the encoding of a message a schema ID may be included in the header of the message. However the current state of the art only describes how schema information is used to encode or decode a payload but not how to identify manage and optimize schemas across an entire binary web service system called a domain .

An object of the invention is to provide an improved solution for web service schema management between computer servers or nodes in computer networks.

According to an aspect of the present invention there is provided an apparatus comprising a processor a memory including computer program code configured to with the processor cause the apparatus at least to perform controlling the storing of schema information of a binary web service system the schemas describing the encoding decoding of binary XML messages providing an interface for maintaining the schema information up to date in each component of the binary web service system.

According to another aspect of the present invention there is provided a method comprising controlling the storing of schema information of a binary web service system the schemas describing the encoding decoding of binary XML messages and providing an interface for maintaining the schema information up to date in each component of the binary web service system.

According to an aspect of the present invention there is provided an apparatus comprising means for controlling the storing of schema information of a binary web service system the schemas describing the encoding decoding of binary XML messages means for providing an interface for maintaining the schema information up to date in each component of the binary web service system.

According to an aspect of the present invention there is provided an apparatus comprising a processor a memory including computer program code configured to with the processor cause the apparatus at least to perform loading a schema describing the encoding decoding of binary XML messages analyzing the schema with one or more test payloads optimizing the schema on the basis of the analysis generating a code library on the basis of the schema.

The following embodiments are exemplary. Although the specification may refer to an one or some embodiment s in several locations this does not necessarily mean that each such reference is to the same embodiment s or that the feature only applies to a single embodiment. Single features of different embodiments may also be combined to provide other embodiments.

As already stated modern applications running in computing equipment connected to communication and computer networks communicate with each other. Web service methods such as SOAP or REST were designed to provide a suitable platform for communication between applications running in different environments operating systems and computers.

In general web services utilize XML for content encoding. The messages sent are XML documents which contain given elements some of which are required and some optional. Web services may utilize XML schemas which describe how data is encoded in the messages and which elements are required and optional. In practice a schema describes the grammar used in the encoding of a payload in the messages and usually includes links to other references such as namespaces. A schema is a description of the structure of an XML document. Other format information markups such as Abstract Syntax Notation One ASN.1 also make use of a Schema like description of the grammar and structure of the information.

In the Internet Intranet and the IP based network with a server messaging is implemented by using XML encoding and transmitted by using HTTP over TCP IP.

The low power wireless network may be a multihop network comprising a set of wireless low power nodes. In this simplified example one node is illustrated.

In an embodiment the wireless links in the wireless network may be realized by using IEEE 802.15.4 with Internet Protocol v6 6lowpan IEEE 802.15.4 with ZigBee Bluetooth or Bluetooth Ultra Low Power ULP Low Power Wireless Local Area Network proprietary low power radio cellular radio system or any other system suitable for low power transmission. IEEE stands for the Institute of Electrical and Electronics Engineers.

A binary web service system makes use of web service protocols either a binary protocol or full HTTP and a binary encoded payload content. These binary techniques are typically applied in a constrained network or with constrained devices which do not have the resources or capacity to realize full web services. In the low power wireless network is such a constrained domain consisting of a constrained node which makes use of a binary web service protocol and payload data . The intermediate node or proxy may be used to convert between binary web service protocols and payloads to full web services . Such a proxy may also be used as a cache or to provide extra security to a constrained domain without converting protocols or payload encodings. In case the payload remains encoded the server must also be aware of the payload encoding schema information.

In order for the system architecture in to operate efficiently out of band schema information is used to encode the payload content. This is typically XML Schema information used to encode decode between the XML content and EXI or Fast Infoset formats for example. Any entity that wants to parse encode or decode the payload must know the correct schema information.

In an embodiment the network of comprises a management apparatus and a schema configuration storage operationally connected to the management apparatus. One or more components of the network involved with the binary web service system make use of schema information managed by the management apparatus.

The management apparatus is configured to provide a schema management interface to used with all system components. The management apparatus also has an interface with the schema storage . The management apparatus may be realized and situated in many ways. Typically the apparatus is a stand alone application in a separate server. It may be integrated into one of the other system components such as the server or the intermediate node or proxy .

In order for the binary web service system to operate efficiently the same schema configuration must be available on all components. In an embodiment the management apparatus is configured to maintain schema related information and provide the web service system with the information via the schema management interface to . The schema information must be consistent within the same domain. A domain may be defined as a set of web service components nodes proxies and servers administered by a management entity sharing the same schema configuration. A management entity may maintain multiple domains and components may participate in multiple domains in this case Schema ID spaces between domains must not overlap .

The schemas of a domain are assigned a unique identification a SchemaID. The identification may be an integer but it may as well be an alphanumeric name or any other suitable identifier. In an embodiment the management apparatus is configured to assign each schema of the domain a unique identifier and maintain information on the identifiers and schemas defined in the domain. The management apparatus may store the information related to the identifiers and schemas in the storage .

In the case of an XML Schema schema related information may be a URI pointing to the actual schema on the Internet. URI refers to Uniform Resource Identifier. An example of a URI is a web address Uniform Resource Locator URL . An example of a URI pointing to a schema on the Internet is http www.example.com SensorData.xsd

In an embodiment the management apparatus is configured to keep track of a set of schema information for each domain under the apparatus. The information may be stored in the storage . The schema information may include the domain the SchemaID which is always unique within a domain and a URI to the schema which may be stored locally or remotely. The schema information may also comprise other configuration information. The following is an example of schema information for a domain called www.example.com 

In the above example the schema information comprises information on four different schemas with SchemaIDs 0 1 2 and 3.

When a component of the system a node a proxy or a server receives an encoded web service payload it must know the schema in order to decode it. In an embodiment the SchemaID is carried either in the header of the web service protocol such as in the content type header of HTTP or corresponding payload type of other protocols or in the header of the payload encoding itself. The EXI standard provides such a field for a Schema ID in its own payload header which can be decoded without yet knowing the payload s schema. Alternatively the Schema ID may be carried just after the protocol header but just before the encoded payload as a kind of magic byte . Once the SchemaID of the encoded payload is determined the schema information is retrieved verified and then used for decoding.

In an embodiment schema configuration information and the related schemas are stored locally on each component. The schema configuration interface to of the management apparatus is used to maintain the same schema configuration on all components in the same domain.

The information stored by the management apparatus may be updated in various ways. In an embodiment the schemas are installed in all components by a management tool. The addition of a new schema to the system is triggered manually through a user or a computer interface. This method may be called a static mode.

In an embodiment components of the system automatically discover and configure new schema information. The addition of a new schema to the system happens automatically through schema discovery as new schemas are detected. This method may be called a dynamic mode.

The procedure starts as a result of either a static schema assignment A through the user interface of a management tool or a dynamic schema discovery process B where it is detected that a particular schema should be added to the binary web service domain and supported by all components.

First in step a Schema URI it may point to a local storage or a remote web resource domain and possibly other configuration information is passed to the process. The information is passed to the process either from the management tool by a component of the system receiving payload encoded with a schema unknown to the system or by a component of the system starting to offer a service utilizing payload encoded with a schema unknown to the system.

If the verification fails in step then a failure code may be returned to the static or dynamic process.

In step a free SchemaID is requested for a valid schema. In an embodiment the free SchemaID may be determined by querying the schema configuration storage .

In step the new SchemaID is then stored along with the Schema URI and possibly the schema itself and other configuration information in the schema configuration storage .

Next the updated schema configuration is installed on all the components belonging to that domain. In this example it is assumed that a list of components is maintained in the storage . The management apparatus comprises a schema configuration interface A to C with each component of the system. In an embodiment the interface is used by applying a push method where the management apparatus updates the configuration on each component. In an embodiment the interface is used by applying a pull method where each component polls the management apparatus for new schema information. The polling may be done at given intervals.

In step the management apparatus receives a request for new schema information from a component of the system. The request comes via the configuration interface A to C.

In step the management apparatus determines whether new schemas have been received since the last update.

If so the new schema or schemas are sent to the component by using the configuration interface A to C in step . If not the component is informed in step that no update is available.

In an embodiment especially with embedded nodes a new firmware may have to be compiled or some executable code may have to be sent to a node so that it can handle a new schema. The mere sending of a new schema via the interface is sufficient for nodes having processing power. illustrates this embodiment. At an embodiment the procedure of may replace step of or step of .

The procedure begins at step . In the beginning of the procedure the new schema and the node to which the schema is to be sent are known.

In step the type of the node is determined. The type of the node indicates whether the code or firmware of the node needs an update or recompilation or whether the sending of schema information is sufficient.

Otherwise the code or firmware of the node is compiled in step to support the new schema information and the compiled code is sent to the node in step . Instead of compiling the code in the management apparatus a code supporting the schema may be loaded from the Internet or the storage .

The procedure ends in step . The same procedure may be repeated for all nodes to which the schema information must be sent.

Regarding the pull method of the management apparatus may compile the code or firmware dynamically when each node polls for changes in schema information. In an embodiment the management apparatus compiles the codes in advance and stores the new code or firmware. When a node polls for changes the management apparatus may send the compiled code in return.

In the static schema assignment method a new schema may be added to a binary web service domain by using a manual installation method realized through a user interface or any appropriate computer API for example.

In step a schema is loaded into a computer. The schema may be a predesigned schema or it may have been designed using a suitable tool. The tool may be a management tool software module.

In step the loaded schema is verified by using a suitable verification method known in the art. If the schema does not pass the verification it is reloaded.

In step a verified schema is stored temporarily in a memory . When applied to a user interface an interactive stage may be offered to the user in order to suggest optimizations and corrections to the schema and possible payloads being designed for the best encoding performance. First in step the schema itself is analyzed using knowledge of the encoding technique and schema features.

In step the results of the encoding are analyzed. This analysis may include for example the size of the encoded vs. original payload the identification of non optimal fields e.g. strings and suggestions for better payload design. In an embodiment this analysis of the test payload s includes checking the completeness of the Schema with regard to the test payload s ensuring that every element in the payloads is defined in the Schema. Incomplete Schemas are less efficient using binary XML techniques. Next the data of each element may be analyzed with respect to the data type of the Schema whereby unnecessary strings may be identified along with complex structures. Finally namespaces not defined in the schema can not be compressed in strict schema informed encodings thus these are identified as they incur large string overheads.

In step a decision is made whether to install the new schema in the system or to go back and improve the payload s or the schema itself for better performance. In an embodiment the described improvement cycle is a semi automated process. In an embodiment the analyzing and optimizing steps are performed a desired number of times. The desired number may be a predetermined number or it may be received as an input from the user interface. In an embodiment based on the analysis of inefficient features of the Schema and payload s incremental improvements may be made to the Schema and also to the payloads using the encoding efficiency results as a measure of success.

In step a firmware library is created from the optimized schema. In step the firmware library is stored to storage . This firmware may be later used in the procedure of . The process ends in step . The process may be realized as the management tool software module tool run in the management apparatus or other server or computer. The tool does not need an online connection to the components of a binary web service while running the process of .

In step the proxy parses the advertisement and determines the number of schemas in the advertisement.

In step the proxy checks whether the schema is known in the domain. In an embodiment the proxy queries the schema from the storage .

In step the URIs of the new schemas are sent to the management apparatus via the interface A to C . Steps to are performed for all schemas in the advertisement. The procedure continues according to .

In step the proxy or the server extracts the full Schema URI from the payload itself. A well formed XML payload includes the schema URI.

In step the schema URI is sent to the management apparatus via the interface A to C . The procedure continues according to .

If not the URI of the new schema is detected. The URI may point to the Internet or the node may store the schema. The schema URI is sent to the management apparatus via the interface A to C in step . The procedure continues according to .

If the schema exists it is checked in step whether the schema ID is unknown. If not the procedure ends in .

If the SchemaID is unknown a new SchemaID is requested from the management apparatus via the interface A to C in step .

In an embodiment the apparatus may be realized as software in a router or a computer connected to a binary web service domain or in a proxy or node between the low power wireless network and the Internet Intranet or an edge server located in the IP network.

An embodiment provides a computer program embodied on a distribution medium comprising program instructions which when loaded into an electronic apparatus execute a computer process the process comprising controlling the storing of schema information of a binary web service system the schemas describing the encoding decoding of binary XML messages and providing an interface for maintaining the schema information up to date in each component of the binary web service system.

The computer program may be in source code form object code form or in some intermediate form and it may be stored in some sort of carrier which may be any entity or device capable of carrying the program. Such carriers include a record medium computer memory read only memory and software distribution package for example. Depending on the processing power needed the computer program may be executed in a single electronic digital controller or it may be distributed amongst a number of controllers.

It will be obvious to a person skilled in the art that as technology advances the inventive concept can be implemented in various ways. The invention and its embodiments are not limited to the examples described above but may vary within the scope of the claims.

