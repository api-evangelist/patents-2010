---

title: System and method for providing a service
abstract: According to one example of the present invention, there is provided a system for providing a service. The service is accessible from a client application and is provided through a service application using a set of service provider resources. The system comprises a mapping module for generating mapping data, the mapping data being generated in part from an enterprise architecture definition, in part from a vocabulary definition; and in part from a client context definition. The system additionally comprises a communication module for receiving a communication request, transforming the communication request using the generated mapping data, and processing the transformed communication request.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09276999&OS=09276999&RS=09276999
owner: Hewlett Packard Enterprise Development LP
number: 09276999
owner_city: Houston
owner_country: US
publication_date: 20101015
---
The use of electronic IT services has been growing rapidly over recent years as specialized IT service providers offer services to their clients. Clients may typically access the services through use of a client application running on client computing hardware.

For example a service provider may provide a complex powerful and resource intensive IT service that clients may access via a client application running on standard personal or business computers. This is particularly advantageous for the client who can access such services without having to provide and maintain the computing hardware and software required to provide the service.

In order to optimize their service offerings service providers may offer their services to multiple clients. However due to differences in client infrastructure architectures and functional requirements the service provider typically needs to either provide separate customized instances of the service for each client or needs to provide a single service which is customized to cater for multiple clients.

However due to the relatively short shelf life of computing devices and software applications it is common for the IT systems of the clients the service providers or both to undergo upgrades and modernization on a regular basis. Such modifications may however be problematic for those providing and or for those consuming IT services.

Referring now to there is shown a block diagram showing a simplified overview of an information technology system according to the prior art. The system enables an IT service provider to provide IT services to one or more clients and . Typically each client has a service contract with the service provider for the provision and delivery of the appropriate service.

The service provider has a set of service provider resources which may include for example software applications . storage not shown data bases and the like. The service provider resources may run or be hosted on suitable computing hardware not shown . The service provider resources provide the underpinnings enabling the service provider to provide one or more IT services to one or more clients. Accordingly the service provider resources may also be referred to as service underpinnings.

The service provider provides a service application executing on suitable computing hardware. The service application may provide any suitable IT service such as a human resources management service a travel planning and booking service and the like.

The service application is accessible over a network by one or more clients. Each client accesses the service applications application using respective client applications and . The client applications may be said to consume the service provided by the service application and as such may be referred to as consumer applications. Each client application and executes on suitable client computing hardware not shown and may utilize respective client computing resources and

The business and or IT requirements of the IT service being provided dictate which service resources or service underpinnings are to be used by the service application . The service provider resources could be authoritative enterprise resources data elements or other service building blocks. Service building blocks may include for example existing services or service applications application programming interfaces APIs software components and the like.

As the business and or IT requirements change so the service provider may make changes to the service provider resources or underpinnings . For example the service provider may change from one database product to another. In order for the service application to continue functioning in the intended manner it may be necessary for the service provider to make corresponding changes to the service application to take into account any changes in the service provider resources or underpinnings . Such changes may be made for example by way of one or more service underpinning customization modules etc.

Different clients may have different IT infrastructures. For example a client may use a Windows operating system whereas client may use a Linux operating system. Additionally one client may use an Oracle database whereas another client may use a Microsoft database.

These differences in client IT architecture lead to different clients being required to interact with the servicer application in different manners. Accordingly this makes it difficult for the service provider to provide a single generic service application suitable for use by any client.

To cope with the differences in client IT architectures the service application includes client customization modules and for each different client. The client customization modules and ensure that interaction with the service application is done in the correct manner for each client application.

As IT equipment and computer software typically has a relatively short shelf life enterprises frequently undergo IT infrastructure modernization. Through IT modernization programs new computing technology is used to replace aging computing systems enabling enterprises to operate with improved efficiency and reduced costs.

Similarly a client may modify or change at least some of their computing resources after a service provider has customized a service application such as service application . Such changes may include for example a change from one database provider to another changes to underlying computing hardware changes in data format and the like. However such changes in a client IT architecture may require corresponding changes to be made in associated client customization module in the service application . Not surprisingly such changes are disruptive complex and costly to implement.

Referring now to there is shown a simplified block diagram illustrating an information technology system according to an example of the present invention. Operation of the system according to an example of the present invention is described below with additional reference to the flow diagram of . The system enables an IT service provider to provide IT services to one or more clients in a flexible manner that is more resilient to changes in either the service provider or the client resources.

The system enables an IT service provider to provide IT services to one or more clients and . For clarity only two clients are shown although it will be appreciated that examples of the present invention are not limited to only two clients.

The IT service provider has a set of service provider resources or service underpinnings which may include for example computing hardware software applications storage data bases and the like. A service application is provided which enables the clients and to access the IT service provided by the service application . Each client and has a respective client service application and which are used to consume the service. Each client and additionally has respective uses respective client resources and

However unlike in the system shown in the service application is arranged as a generic service application. In other words it is not tied or hard coded to any set of client resources or to any set of service provider resources. Advantageously by decoupling the service application from the service provider resources and the client resources enables the service provider resources and or the client resources and to be modified without affecting the provision of the service by the service provider . Accordingly this enables both the client and the service provider to undergo IT modernization without affecting the provision of the IT service.

To enable the effective decoupling of both client and service provider resources from the service application the service application additionally includes a communication module for brokering processing for the service application. Additionally the system includes a mapping module . The mapping module includes an application programmer interface API through which the communication module of service application obtains definitive service input and output fields and resources when providing the service as described in greater detail below. In a further example the interface of the mapping module may be provided in the form of a web services interface.

The mapping module generates a dynamic resource mapping database that is used by the API . The mapping module updates the mapping database whenever a change in either the service provider resources or underpinnings or a change in the client resources or are determined.

In order to generate the mapping database the mapping module makes use of an enterprise architecture EA definition that provides a detailed description of different aspects of the service provider architecture and environment. For example an EA definition may include details of both business and technical aspects of the service provider. For example the business aspects may include details of the business structure of the service provider business goals and other business information. Technical aspects may include for example details of the service provider computing systems service provider software applications service provider IT system architecture and data definitions.

An enterprise architecture definition may define business processes and their relationships with service provider resources. For example an EA definition may define among other things that 

In addition to the EA definition there is also provided a service provider vocabulary definition . The vocabulary definition defines the nomenclature used by the service provider for providing the service. For example the vocabulary definition may define a standard nomenclature of the data sources or data definitions as defined by the service provider. Each entry in the vocabulary definition includes one or more equivalent definitions as used or defined by one or more clients using the service. The data vocabulary definition does not define relationships between the data but just shows equivalent nomenclature.

In addition to the EA definition and the service provider data vocabulary definition there is provided a client context definition for each client who is entitled to access the service provided through the service application .

Each client context definition defines information about each client application or applications as well as the service agreements between each client application and the service provider for each service provided through the service application. The information may include for example a unique client identifier its role operations provided by each service input and output parameters message type and message definition the client application identifier data source identifiers Universal Resource Indicators URIs identifying resources and how those resources are to be accessed interface types binding protocol and so on.

Turning now to there is shown a simplified flow diagram outlining an example method of operating the mapping module according to one example of the present invention.

The mapping module processes the data in the enterprise architecture definition the service provider vocabulary definition and the client context or contexts and generates mapping data to populate the mapping database . Once the mapping data has been generated the mapping module determines whether any changes have been made to any of the available definitions and . Changes may be detected in any suitable manner for example by checking a file modification date of a definition stored as a file. If any changes are detected the mapping module updates the mapping database with updated mapping data taking into account the determined changes.

The mapping database populated by the mapping module is used by the communication module to decouple the client resources and as well as the service provider resources . In this way the service application does not need to maintain references to service provider resources nor client resources and but instead uses the communication module and mapping module to resolve service application inputs and outputs and to convert or translate them to appropriate service provider or client resources.

Accordingly this decoupling enables changes to be made to service provider resources and or client resources and without requiring any changes to be made to the service application . Advantageously this reduces downtime of the service application due to recompilation or modification and reduces the maintenance and customization on the service application .

A more detailed explanation of the operation of the mapping module will now be described with additional reference to .

As previously mentioned the EA definition provides a detailed description of many aspects of an enterprise. However for the purposes of generating the mapping data for the mapping data base only a subset of the information contained in the EA definition is required. Some examples of the type of information to be included in the subset of information are illustrated in Table 1 above. At the mapping module extracts a subset of the EA definition .

At the mapping module obtains a subset of the data comprised in the vocabulary definition . A subset of the vocabulary definition is obtained since not all of the data stored therein may be relevant for the purposes of generating the mapping data for the mapping database . Some examples of typical data that may be included in the subset of obtained data are illustrated in Table 2 above.

At the mapping module obtains a subset of the data comprised in each of the client context definitions and . Again this is because not all of the data in the client context definitions may be relevant for the purposes of generating the mapping data for the mapping database . Some examples of typical data that may be included in the subset of obtained data are illustrated in Table 3 above.

In other examples subsets of the different definitions and are not obtained. However in examples in which the subsets are obtained the processing of the different definitions may be considerably more efficient. In a further example the definitions and are pre optimized definitions containing only relevant subsets of the full definitions.

At the Nentry in the obtain subset of the EA definition is processed. An example of the Nentry is shown below in Table 4.

The mapping module identifies the name of the data element defined which in this case is called L Name . The mapping module then obtains from the obtained subset of the vocabulary definition the standard nomenclature to which the data element L Name maps. From Table 2 above it can be seen that the standard nomenclature associated with the data element L name is Lastname . The mapping module may obtain the standard nomenclature corresponding to the data element in the current entry using any appropriate technique such as using suitable search techniques.

At the mapping module uses the standards based interfaces connectors and APIs as defined by the enterprise architecture definition and the client context definitions to retrieve information such as data source name schema name table name column name universal resource indicator URI API name API type protocol port and so on. The mapping module parses analyzes correlates and fuses this information as required to derive a set of redirection or mapping data. At the mapping module stores the mapping transformation or redirection information in a suitable form in the mapping database

At the counter N is incremented and the above described process is repeated for each entry in the obtained subset of the enterprise architecture definition.

As each entry is processed the mapping database is populated with the derived mapping data. An example extract of the generated mapping data is shown below in Table 5.

In one example the mapping database may be generated using semantic web technology where a web ontology language OWL or resource description framework RDF ontology may be used to describe the mapping data in the mapping data base using subject predicate and object. In this example subject may relate to Service and objects may relate to context attribute data source data element and standardized name.

In further examples additional data may be included in the mapping database during the above described process. Such additional data may include for example details of a universal resource indicator URI which contains the information about where and how to reach the resource or return destination.

Once the mapping database has been populated it may be used by the service provider in providing the service provided through the service application .

Operation of the communication manager will now be described below with additional reference to the flow diagrams of .

The service application may provide the service to the client in a number of different manners. In one example the service application is invoked using a request response type protocol. In another example the service application may be invoked using an API remote procedure calls asynchronous messaging or the like. In the present example however it is assumed that the service application is invoked using a request response type protocol.

At the communication manager receives a service invocation request. The service invocation request may for example be in the form of a message containing the name of a service function to invoke the name of a data element a value for which is to be returned to the client or in any other suitable form.

At the communication manager uses the mapping module to translate or transform the request message into a service invocation request in a suitable form for use with the service application .

For example if the received service invocation message request includes a service function GetLName LName the mapping module may transform this to the service application service function GetPersonalDetails LastName .

At the communication manager uses the mapping module to determine a service provider resource redirection as illustrated in Table 5. For example when a client 1 accesses a service 2 the service 2 may retrieve the data element LastName from Table1.column1. When a client 3 accesses a service 2 the service 2 may retrieve the data element LastName though use of an API call ClassA.Method1 .

At the communication manager of the service provider application processes the transformed request to for example access the resolved resource or resources to obtain the required data. This may be achieved for example by sending the transformed service invocation request to one of the service provider resources to

When the service application responds to a service invocation request message the communication module receives an output response request.

At the communication module uses the mapping module to translate or transform the output response request into a suitable form for the client who sent the initial corresponding original service invocation message.

At the communication module again using the mapping module determines a client resource redirection as illustrated in Table 5 above. For example when using service 2 client 1 expects the output data structure Out data to be returned using the URI1 which may point to a service provider message queue. When a client 2 uses the same service service 2 client 2 may need the service 2 to return the same output data structure via a web service pointed to by the URI2.

At the communication module processes the transformed request for example to cause the transformed output request to be sent to the appropriate client in the appropriate format.

For example if client application of client invokes the service application with the invocation service1.getAddress the communication module transforms the invocation through use of API of the mapping module to a service provider invocation suitable to obtain the data in the service provider resource dataSrc2.permanentAddress. However if the client application of client invokes the service application with the same service invocation service1.getAddress the communication module transforms the invocations through use of the API of the mapping module to a service provider invocation suitable to obtain the data in the service provider resource dataSrc2.mailingAddress.

By way of further example depending on the particular service contracts between a client and the service provider as detailed in the client contexts a service invocation received at the communication module from one client may be transformed to differently service provider invocation compared to the same service invocation received from a different client. For example a service invocation received from one client may be transformed to use an API of a service provider resource whereas the same service invocation received from a different client may be transformed to use a web services interface of the same or a different service provider resource.

In other words the communication module transforms an incoming service invocation to a service provider invocation with the nature of the transformation being dependent on the mapping data in the mapping database which is generated based on the enterprise architecture definition the service provider vocabulary definition and the client context definition s .

The communication module may additionally transform outputs from the service provider application into outputs suitable for the client application to which the output is intended in the same manner.

In the above examples the enterprise architecture definition the service provider vocabulary definition and the client context definitions and have been shown in table form. It will be appreciated however that the definitions are not so limited thereto. For example it will be appreciated that at least some of the definitions may be defined using semantic web technology based ontologies. As will be appreciated use of ontologies may give greater freedom of definition.

Turning now to there is shown a block diagram of computer system on which the mapping module may be implemented in one example. For example the mapping module may be implemented by way of programming instructions stored on a non transitory computer readable storage medium or . The memory and storage are coupled to a processor such as a microprocessor through a communication bus . The instructions when executed by the processor provide the functionality of a mapping module as described above by executing the above described method steps.

It will be appreciated that examples and embodiments of the present invention can be realized in the form of hardware software or a combination of hardware and software. Any such software may be stored in the form of volatile or non volatile storage such as for example a storage device like a ROM whether erasable or rewritable or not or in the form of memory such as for example RAM memory chips device or integrated circuits or on an optically or magnetically readable medium such as for example a CD DVD magnetic disk or magnetic tape. It will be appreciated that the storage devices and storage media are examples of machine readable storage that are suitable for storing a program or programs that when executed implement embodiments of the present invention. Accordingly examples provide a program comprising code for implementing a system or method as claimed in any preceding claim and a machine readable storage storing such a program. Still further examples of the present invention may be conveyed electronically via any medium such as a communication signal carried over a wired or wireless connection and examples suitably encompass the same.

All of the features disclosed in this specification including any accompanying claims abstract and drawings and or all of the steps of any method or process so disclosed may be combined in any combination except combinations where at least some of such features and or steps are mutually exclusive.

Each feature disclosed in this specification including any accompanying claims abstract and drawings may be replaced by alternative features serving the same equivalent or similar purpose unless expressly stated otherwise. Thus unless expressly stated otherwise each feature disclosed is one example only of a generic series of equivalent or similar features.

