---

title: Generic boxed components for multi-client systems
abstract: In one embodiment, a method includes defining a parent structure including an extension. A polymorphic structure is defined for the extension. The polymorphic structure is associated with a plurality of client specialization structures, each client specialization being associated with a client in a plurality of clients. During runtime by a computing device, the parent structure is generated with an extension to a client specialization structure associated with one of the plurality of clients where client specialization structures associated with other clients are not visible to the parent structure.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09378468&OS=09378468&RS=09378468
owner: SAP SE
number: 09378468
owner_city: Walldorf
owner_country: DE
publication_date: 20101227
---
An application platform may implement business objects to support different business solutions. A business object for example is a software model representing real world items used during the transaction of business. A business object may comprise a SalesOrder object model or an Organization object model. Instances of these object models in turn represent specific data e.g. SalesOrder SO435539 ACME corporation .

A business object may specify business logic and or data having any suitable structure. The structure may be determined based on the requirements of a business scenario in which the instance is to be deployed. A business application for a particular business scenario may require many business object instances where the structure of each has been determined based on the requirements of the particular business scenario.

A customer deploying a business solution may desire changes to a business object included in the business solution. For example a customer may require a field e.g. SerialNumber that does not exist within the Product business object of a business solution. In addition another customer may require an additional node or query within the Product business object of the same business solution.

Some conventional application platforms support the addition of extension fields to nodes of existing business objects. Consequently these application platforms are able to store data associated with instances of these extension fields in a primary persistency e.g. a relational database flat files . This data can then be consumed by user interfaces queries and other entities supported by the application platforms. However when the field is added recompilation may be needed. When multiple clients are using the system and structures are extended other programs being run by the clients are affected by the recompilation being performed and may have their programs aborted.

In one embodiment a method includes defining a parent structure including an extension. A polymorphic structure is defined for the extension. The polymorphic structure is associated with a plurality of client specialization structures each client specialization being associated with a client in a plurality of clients. During runtime by a computing device the parent structure is generated with an extension to a client specialization structure associated with one of the plurality of clients where client specialization structures associated with other clients are not visible to the parent structure.

In one embodiment the method includes adding information for a client specialization structure associated with a client in the plurality of clients and creating a component in the client specialization structure for the client.

In one embodiment the method includes creating a set of switches for a set of components in the client specialization structure associated with the one of the plurality of clients and using the set of switches to determine which components to include in the client specialization structure at runtime.

In one embodiment the contents of the polymorphic structure are not known at compile time and the polymorphic structure includes the client specialization structure associated with one of the plurality of clients at runtime.

In one embodiment a non transitory computer readable storage medium containing instructions for controlling a computer system is provided. The instructions control a computer system to be operable to define a parent structure including an extension define a polymorphic structure for the extension the polymorphic structure being associated with a plurality of client specialization structures each client specialization being associated with a client in a plurality of clients and generate during runtime the parent structure with an extension to a client specialization structure associated with one of the plurality of clients wherein client specialization structures associated with other clients are not visible to the parent structure.

In one embodiment an apparatus includes one or more computer processors and a computer readable storage medium comprising instructions for controlling the one or more computer processors. The instructions control a computer system to be operable to define a parent structure including an extension define a polymorphic structure for the extension the polymorphic structure being associated with a plurality of client specialization structures each client specialization being associated with a client in a plurality of clients and generate during runtime the parent structure with an extension to a client specialization structure associated with one of the plurality of clients wherein client specialization structures associated with other clients are not visible to the parent structure.

The following detailed description and accompanying drawings provide a better understanding of the nature and advantages of the present invention.

Described herein are techniques for a framework for generic boxed components. In the following description for purposes of explanation numerous examples and specific details are set forth in order to provide a thorough understanding of embodiments of the present invention. Particular embodiments as defined by the claims may include some or all of the features in these examples alone or in combination with other features described below and may further include modifications and equivalents of the features and concepts described herein.

Several clients which may be referred to as tenants may run on one system . Each client is only supposed to have access to the client s own independent data. Particular embodiments allow clients to extend structures without causing recompilation of other clients structures.

User might comprise a Personal Computer PC or mobile device executing a Web client. Examples of a Web client include but are not limited to a Web browser an execution engine e.g. JAVA Flash Silverlight to execute associated code in a Web browser and or a proprietary standalone application.

User may execute a Web browser to access services via HyperText Transport Protocol HTTP communication. For example a user may submit via a user interface an instruction e.g. show me a sales report . User in response may transmit a corresponding HTTP service request to business service provider . Services may conduct any processing required by the request e.g. generating views and user interfaces and after completing the processing provide a response to user .

Business service provider might receive requests from user and provide responses to user via a service oriented architecture. The use of remotely hosted business service provider may help client avoid the costs and problems associated with maintaining a local in house Enterprise Resource Planning ERP system.

Business service provider might store client information into and retrieve client information from physical tables of data store . Data store may be a relational database. Alternatively data store could be a multi dimensional database an eXtendable Markup Language XML document or any other structured data storage system. The physical tables may be distributed among several relational databases dimensional databases and or other data sources. To provide economies of scale data store may include data of more than one client. This may be considered a multi tenancy system. Business service provider includes mechanisms to ensure that a client user accesses only the data that the client user is authorized to access.

The structures of and relationships between the physical database tables may be complex and business objects may be used to shield developers and end users from these complexities. A business object may comprise for example a software model including nodes to encapsulate related data and methods. As described above a business object may be associated with a business entity such as a client partner sales order product store time etc. represented in the data of a data source. Each instance of a business object may represent a particular instance of the entity represented by the business object. An instance of a SalesOrder business object may for example provide a mapping to the underlying tables storing data associated with a particular sales order.

Metadata includes metadata defining metadata models and object models. The object models or objects are instances of the metadata models. The metadata models may include generic models of a BI view a floorplan a business object a user interface text a process component a data type and a message type but embodiments are not limited thereto. The metadata models and object models may be embodied in any type of data structure including but not limited to eXtensible Markup Language files. As in the conventional storage of object instance data the metadata defining the specific metadata models and object models may be stored in database tables and or any other suitable format.

Each metadata model may comprise an instance of a same meta metadata model. The meta metadata model may consist of nodes composite associations associations elements structure and attribute properties. Development of specific business objects specific floorplans etc. may therefore proceed using the same development technologies. Moreover access and lifecycle issues of the various object models may be managed using similar or identical mechanisms.

Metadata provides information regarding the structure and attributes of the data of underlying business object instances i.e. the data stored in data store . Metadata may include design time and or runtime proxy objects generated based on other metadata e.g. an eXtensible Markup Language XML representation of a business object stored therein. For example metadata may include Advanced Business Application Programming ABAP proxy objects which are consumed by ABAP code of applications services residing in business service provider .

Services include any business services that are or become known. Services may provide user with user interfaces print forms search capabilities message interfaces e.g. A2X B2B etc. based on data stored in data store and defined by metadata .

Services may use metadata to access data of data store . In accordance with this paradigm an extension field that is modeled within the metadata as a generic boxed component of a business object and allows services to store and retrieve data associated with the extension field. Generic boxed components allow different clients to use client specific specializations for a parent structure. Changes can be made to client specific specializations without having impact on other clients . For example recompilation of the parent structure or other clients specializations may not be performed. The generic box may be a substructure whose components are not known at compile time. The generic box may refer to a polymorphic structure that is a virtual structure that will differ per client. A client specialization may be a client specific view on the polymorphic structure in a client.

As will be described in more detail below metadata may be used to define the parent structure and generic boxed components. In one embodiment a data dictionary is used to instantiate a generic boxed component. The data dictionary is a centralized repository of information that includes relationships between parent structures and generic boxed components. The data dictionary is stored in database .

As described above with respect to a change to a user interface extension fields may be added to these entities in order to retrieve data and provide services including extension field data. For purposes of the present description entities to which extension fields may be added in order to consume corresponding business object data will be referred to as consuming business entities.

Client may customize consuming business entities which are provided by business service provider . In particular client may add components to a generic boxed component to a user interface and to its corresponding business object . Embodiments may facilitate addition of the component of a client specialization to other consuming business entities. This addition may be performed without affecting other clients .

In one embodiment a developer of a business service provider may define extension fields for various consuming business entities. An extension field definition may point to a specific portion of a consuming business entity e.g. a location on a user interface into a field in the data model of the user interface i.e. as representing the path down to a corresponding persistent business object node .

Extension field may be classified as a generic boxed component. A generic box is a substructure the components of which are not known at compile time. At design time extension field points to polymorphic structure . The polymorphic structure may be a virtual structure that looks different for multiple clients at runtime. For example at design time polymorphic structure may be associated with client specializations for a client a client and a client . Each client specialization of polymorphic structure may be a client specific structure. For example client specialization may be a client specific section for client client specialization may be a client specific section for client and client specialization may be a client specific section for client . Each of these client specializations may be an extension of field of parent structure at runtime.

Each client specialization may assign a set of components to the generic box. Each client specialization may also include components which may be associated with fields of a user interface. For example a SerialNumber may be added as component of client specialization .

During runtime one client is selected. In this case client may be using the services . In this case client specialization is visible through extension field . However components for client specializations and are not visible. Thus when a component in polymorphic structure is accessed through extension field the component for client specialization is accessed for client .

Particular embodiments derive polymorphic structure at runtime. For example during compile time the contents of polymorphic structure that will apply at runtime are not known. The compiled program code does not contain client specific information. At runtime when a client specialization is selected the contents of polymorphic structure are generated with the selected client specialization .

Particular embodiments allow for changes to one client specialization but these changes do not impact other client specializations . That is neither recompilation of the other client specializations nor recompilation of the parent structure is necessary. In this case only recompilation of the affected client specialization may be performed.

In one embodiment a definition of the generic boxed component is performed in the data dictionary found in metadata . In one example the definition is performed via an application programming interface API . Via this API a structure component may be designated to be a generic boxed component corresponding to the extension field .

At different dictionary appends are created for clients . For example appends may be created. Each append may add one or more components to polymorphic structure for the client.

As shown at client specializations have been generated for clients . Each client specialization may be a data structure that includes components appended for that client.

When a request for an append is received at a dictionary append is created. At dictionary append is assigned to a switch. A switch may be regarded as a Boolean function that may depend upon a combination of SwitchID Client . SwitchID may be the identifier for the switch and Client is the identifier for the client . The switch may be used to indicate whether the components of the append are to be used or not. If the switch is on the components may be included in client specialization .

At the states of the switches of the relevant appends may be analyzed to determine the set of client specializations to be created. At client specializations are created resulting in dictionary runtime objects.

In conventional application platforms with type safe access to structure components a change in the structure definition requires a recheck and recompilation of all programs using the structure. Additionally for optimized component access address information e.g. offset and length may be included in compiled code. In particular embodiments using generic boxed components this address information is transferred to dictionary runtime objects for the client specializations and not reflected in the compiled programs. Hence any change to appends does not cause a recompilation of programs accessing parent structure . However access to non generic boxed components of the parent structure remains optimized.

As a consequence of the generic boxed components value semantics adding extension fields to already existing structure types preserves among others the semantics of copy and compare operations on parent structure . Thus the impact on the functional behavior of existing programs is minimized.

Also it may be possible to define aggregate types on base of types containing generic boxed components e.g. classes collections and complex structures.

To allow generic boxed components to operate in system certain restrictions may be imposed. Although ABAP is discussed the restrictions may be applied to similar concepts in other programming languages. In one embodiment static access to a generic box or its components is not allowed. Static access may be usage checked evaluated and optimized by a compiler. In another embodiment static access may be allowed syntactically but internally it is converted by the compiler to a dynamic access using the dictionary runtime object at runtime.

Examples for static access in the programming language such as ABAP may be a reset of all values stored in extension field of some structure variable struc to their initial values or an assignment of a value val to some component comp of the generic box ext . For example the following ABAP statements may result in syntax errors 

Also static reference to the type of a generic box or its components is not allowed. One example for static type access in ABAP is the declaration of some variable var referring to a component comp of a generic box ext of type ty 

Another example would be sorting an Internal Table itab by some component located in a generic box. Internal Tables are ABAP s built in collections with fixed element type 

One example for a valid static specification of a generic box in ABAP is the statement MOVE CORRESPONDING. It assigns all components of the extension field ext of a structure struc to corresponding components of the extension field ext of a structure struc having identical names 

Another example for a valid static specification may occur in the definition of a simple transformation. Simple transformations are a programming language to convert data between an XML representation and ABAP. Simple transformations may access components of a generic box statically.

At runtime generic boxes behave like substructures. For example a copy of a structure variable struc containing some generic boxed component to a structure variable struc may result in a deep copy of the structure itself and its client specialization for the current client 

In general single components of a generic box may be accessed dynamically at runtime. Dynamic access means that the mapping of the name of a component to the technical addressing information is deferred to runtime. For example in ABAP the statement ASSIGN may be used to provide access to a component via its name 

In ABAP dynamic component access may be allowed for Internal Table statements. The actual names of the components to be used for sorting the Internal Table are given by the content of the variables name name name 

In one embodiment a generic box may contain no components at all i.e. the polymorphic structure contains no components for a specific client. In this case the box is called empty and the length of the generic box would be zero.

In one embodiment up to the first write access to the contents of a generic box no memory is allocated for the box instance. In this case the generic boxed component is called initial.

There are restrictions for cross client access because the specializations may be different in different clients. For export to database shared memory shared buffer instructions the data can only be stored in client dependent clusters. For example in ABAP Shared Objects generic boxes can only be stored in client dependent areas.

Computer system may be coupled via bus to a display such as a cathode ray tube CRT or liquid crystal display LCD for displaying information to a computer user. An input device such as a keyboard and or mouse is coupled to bus for communicating information and command selections from the user to processor . The combination of these components allows the user to communicate with the system. In some systems bus may be divided into multiple specialized buses.

Computer system also includes a network interface coupled with bus . Network interface may provide two way data communication between computer system and the local network . The network interface may be a digital subscriber line DSL or a modem to provide data communication connection over a telephone line for example. Another example of the network interface is a local area network LAN card to provide a data communication connection to a compatible LAN. Wireless links are another example. In any such implementation network interface sends and receives electrical electromagnetic or optical signals that carry digital data streams representing various types of information.

Computer system can send and receive information through the network interface across a local network an Intranet or the Internet . In the Internet example software components or services may reside on multiple different computer systems or servers across the network. The processes described above may be implemented on one or more servers for example. A server may transmit actions or messages from one component through Internet local network and network interface to a component on computer system . The software components and processes described above may be implemented on any computer system and send and or receive information across a network for example.

Particular embodiments may be implemented in a non transitory computer readable storage medium for use by or in connection with the instruction execution system apparatus system or machine. The computer readable storage medium contains instructions for controlling a computer system to perform a method described by particular embodiments. The instructions when executed by one or more computer processors may be operable to perform that which is described in particular embodiments.

As used in the description herein and throughout the claims that follow a an and the includes plural references unless the context clearly dictates otherwise. Also as used in the description herein and throughout the claims that follow the meaning of in includes in and on unless the context clearly dictates otherwise.

The above description illustrates various embodiments of the present invention along with examples of how aspects of the present invention may be implemented. The above examples and embodiments should not be deemed to be the only embodiments and are presented to illustrate the flexibility and advantages of the present invention as defined by the following claims. Based on the above disclosure and the following claims other arrangements embodiments implementations and equivalents may be employed without departing from the scope of the invention as defined by the claims.

