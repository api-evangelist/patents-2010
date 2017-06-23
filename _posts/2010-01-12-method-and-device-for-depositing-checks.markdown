---

title: Method and device for depositing checks
abstract: A system and method for depositing and processing checks using an ATM is provided. The method includes capturing the image data of the check with a reading unit, transmitting the image data to a web service based on an open API (Application Programming Interface) without resorting to standard protocols of ATMs. The method also includes processing the image data with the web service so that the text data on the check is recognized. When calling the API, version information is transmitted to ensure that the web service is a correct web service. When a version indicated by the version information is not supported, an error is reported to the ATM and transmission is reattempted for a predetermined number of times. The method also includes booking the recognized data on the basis of account information determined from a credit card by a magnetic card reader.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08630950&OS=08630950&RS=08630950
owner: Wincor Nixdorf International GmbH
number: 08630950
owner_city: 
owner_country: DE
publication_date: 20100112
---
This application is a National Stage of International Application No. PCT EP2009 050258 filed Jan. 12 2010. This application claims the benefit and priority of European application 09150566.9 filed Jan. 14 2009. The entire disclosures of the above applications are incorporated herein by reference.

This section provides background information related to the present disclosure which is not necessarily prior art.

The invention relates to a method and device for depositing checks. The invention relates specifically to an interface of an ATM to transmit check data information that allows the check to be posted immediately.

Today customer checks can be deposited in check deposit terminals known as self service machines or ATMs . The checks are processed without validation and the customer receives a receipt to the effect that he has deposited the check s . Until the amount is posted or there is some activity in the account the checks from the terminals have to be sent to what are known as clearing centers. This is handled over normal mail routes. The consequence is that the amount of the check is not validated and finally posted for several days or weeks.

Publication WO 99 11021 and the entries under Check 21 Act in Wikipedia describe handling of the checks as scanned data. Precise implementation with respect to an ATM is however not disclosed.

There exists a plurality of communication protocols in the area of ATMs such as NDC DDC IFX etc. All these standard protocols do not contain the necessary definitions for an integrated complete image inspection and processing. Expanding the standard protocols is very challenging and difficult because of the interests of the large number of members. Thus there is a need for an alternative solution to enable the expansion of the ATMs so that inspecting the image data that normally represent checks is made possible.

The object An aspect of the present invention is to provide a method and a device specifically an ATM that provides an expansion of ATMs in addition to the existing protocols so that in one potential embodiment inspection of image data and their analysis is allowed.

In order to provide inspection of a check in an ATM the invention is based on the following elements. These elements are

One possible inventive idea behind it is that ATMs and other inspection devices can integrate the inspection and reading functionality of different CPSs check processing systems through a single web service interface. In this way the host and the client are independent of each other. Implementation of the web service connects the client to the specific CPS system in the individual customer environment. Client and host software do not need to be modified and they continue to be independent of each other.

There are probably as many definitions for web services as there are companies that already provide them but the numerous definitions have one thing in common 

1. Web services make a useable functionality available to the user over a standard web protocol. In most cases SOAP Simple Object Access Protocol is used as the protocol. It is a network protocol in which data can be exchanged between network systems over RPC Remote Procedure Calls .

2. Web services provide a path that describes the interface in a sufficient degree of detail so that the user is able to develop a client application that communicates with the web service. This description is normally detailed in an XML document using for example Web Services Description Language WSDL .

3. Web services are registered so that potential user can find them easily. This is usually accomplished using Universal Discovery Description and Integration UDDI .

One of the primary advantages of the web architecture is that it allows programs to be programmed in different languages and on different platforms but which communicate with each other in a standardized way and exchange information. So they operate with standard web protocols such as XML HTTP and TCP IP. A significant number of firms already have a web infrastructure and consequently knowledge and experience in this area already exists. As a result the costs for entry into the area of web services are significantly lower than in previous technologies.

This approach allows the customer to drive a multi vendor strategy in both directions. Web services are a fundamental technology and represent an important evolutionary step in the direction of distributed computing. Open standards and the focus on communication and cooperation between man and applications have created an environment in which web services are becoming the platform for application integration. Applications are developed using several web services from different sources that cooperate regardless of where they are located or how they are implemented.

With this invention a standardized interface is created in the form of a WEB service containing methods that define the electronic dispatch of checks or transfer records from an ATM to a remote check validation server. At the same time this interface makes possible online real time validation from a check validation server. Batch inspections using this technology are also conceivable .

An important aspect is the definition of functions and parameters that make a check transaction possible with simultaneous online real time posting. This means that the checks deposited by the customer are sent as image data BMP JPG or TIF to a remote validation server and validated immediately while the customer transaction is active. The customer has the immediate opportunity to initiate confirmation of the amount when the amounts can be posted immediately to the respective accounts. As a result there is a generally valid interface based on web server technology that allows server and client providers to use this interface to develop a communications logic for online check processing. The advantage is the preselection of functions and data fields that need only to be filled with predefined values. Preselecting functions and data fields allows the client and server application to be developed totally independently.

The result is a number of advantages. One of the advantages some of which have already been mentioned is the high degree of independence. As soon as the customers have integrated a clear web service API they are independent of the host system. On the other hand it requires no specific device integration effort. As was already mentioned previously the customer now has the opportunity to select a multi vendor strategy for clients and a CPS system.

Furthermore the possibility exists for simple integration into an open standardized environment. In addition to the unique integration of a web service proxy on the client the primary integration must be seen in implementing the web service itself. Web service implementation realizes the connection between the unique client API and the individual CPS host system. The advantage lies in the fact that web service development can take place in a completely open environment using standard technologies.

Furthermore no ATM protocol or an expansion of said protocol is required. The expansion of existing protocols has shown that it is often a protracted and difficult process. In addition the expense would be very great in order to carry out specific CPS solutions for each ATM protocol .NDC DDC IFX etc. .

Furthermore no installation of check inspection and reading software on the client ATM is necessary. This would normally involve high administration costs since the software would have to be installed on each device and has to be continuously updated and synchronized. Moreover integration into an ATM software is very specific.

Conversely maintenance is very simple the major components run on a central server web service server or the CPS system or another host system. Scalability and flexibility represent a further advantage the web service solution makes it possible for the web service to run either on the client which is not advisable or on a separate server or on the same server as the CPS system.

HTTPS can be used as the software for secure data transmission which is well known. Using this approach it is possible that other image recognition software can also use the interface since it concerns an open standard.

Corresponding reference numerals indicate corresponding parts throughout the several views of the drawings.

Parts of the following description of the API web service are described in WSDL notation reference is made to the fact that a plurality of programming languages can be used the one employed serves only for an understanding of the example .

When a message is sent between the devices and the service it is possible that the content is duplicated during the transmission in the network. The result can be that the same message arrives twice at the service. The same phenomenon is possible when the service sends a message to the terminal. For this reason a MessageID is used that ensures that the same message is not processed twice. Each time that a method is carried out on the service said method is given a message identifier ID . This message identification must be unique within the service for all messages so that the device has to construct a unique identifier for each message. The service must receive the message identifiers to ensure that they are unique. In the event that the same message identifier is received by the service for the same method the service has to must transmit its original response again. In the event that the same message identifier is received in different methods the service must confirm that there is a problem and must return an appropriate error code InvalidMessageId. This implies that the service must retain copies of all messages that it receives and sends so that it can validate the incoming messages and reproduce the outgoing messages. The terminal must correspondingly monitor all messages that it sends so that it does not receive duplicate responses. Duplicate responses can be ignored.

A further approach for the present invention is that each time a method is called up it can be ensured the correct type of service can be used by transmitting information about the version. The terminal should normally integrate the same version values into each call so that the server is able to recognize which version of the method is being used. The version of the method is generally the same as the version of the API itself. The server can thus support different versions of APIs. It has to check the version value in each method call to ensure that the version of the method is supported. In the event that the version is not supported the service must report an UnsupportedVersion error to the device SSM ATM . The maker of the terminal SSM ATM must take into consideration that this error can be applied to each method call so that the terminal must process these errors accordingly. For example it is possible to provide two different check deposit services on different servers that respond to method inquiries in a load distribution scenario. If two methods are routed to different servers by the same device the version may be acceptable for one server but not for the other. The terminal cannot assume that all methods for one version are always acceptable if only one method call was successful on one occasion. An individual method may have a version value that is different from that of other method calls in the version of API even if this is an unusual circumstance it should be taken into consideration but also avoided if at all possible. The version number is determined from primary and sub extension elements. Based on these tightly structured version numbers rules can be established that determine whether greater or smaller changes in the versions are involved.

Based on these considerations several attempts can be made in the event of an error message to carry out the method again or cancelation ensues after a specific number of attempts. In an alternative embodiment the service can also immediately give up sending further attempts.

By means of the GetCapabilities method the service can be asked which languages are supported which image data are supported what type of transactions how many checks can be transmitted and so on. The client or the self service system can thus scan the capabilities of the service to control the following method calls correctly. Details about the precise type of scan are omitted here for reasons of arbitrariness and brevity. Someone versed in the art can derive the type of calls from the examples that follow. For example the StartTransaction method allows the transmission of the following parameters 

The terminal or ATM transmits the parameters listed above to the service when the method is opened with StartTransaction. The terminal takes the user s language into account and transmits the identifications listed above to a service. In addition the account number is transmitted which was normally determined from a card. Additional information that is transmitted is often established in a dialog with the user.

The service in turn evaluates the data transmitted in this manner and when necessary sends back error messages if it cannot meet the requirements such as version and language. If all data can be taken into consideration it sends back StartTransaction as a response the details of which will not be pursued further at this time since it is constructed quite simply.

The method ProcessItem through which the check data are transmitted from the self service device to the service is examined below.

The description in the table is comprehensible enough that further details are superfluous. What must be taken into account is that both the front side and the back side are transmitted as image data and some additional data such as the time the check was transmitted.

This information is also very detailed and allows one skilled in the art to draw a clear conclusion about the sequence.

The service can provide the SOAP RPC communications model. The API can be described in its entirety in a WSDL file from which the skeleton or the framework of the service can be generated automatically that then has to be filled with life through appropriate programming.

The foregoing description of the embodiments has been provided for purposes of illustration and description. It is not intended to be exhaustive or to limit the invention. Individual elements or features of a particular embodiment are generally not limited to that particular embodiment but where applicable are interchangeable and can be used in a selected embodiment even if not specifically shown or described. The same may also be varied in many ways. Such variations are not to be regarded as a departure from the invention and all such modifications are intended to be included within the scope of the invention.

