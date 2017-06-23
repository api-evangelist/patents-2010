---

title: Automatic WSDL download of client emulation for a testing tool
abstract: A method is disclosed which may include analyzing communication requests in a business process between a client and a server offering a service application to be tested. The method may further include identifying a call to a web service in the analyzed communication. The method may also include determining a location of a Web Service Description Language (WSDL) file relating to the web service on a remote server and downloading the WSDL file from the determined location. A computer readable medium having stored thereon instructions for performing the method and a computer system are also disclosed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09043440&OS=09043440&RS=09043440
owner: Hewlett-Packard Development Company, L.P.
number: 09043440
owner_city: Houston
owner_country: US
publication_date: 20101216
---
Web Services are widely used in modern applications. The term web service usually refers to an application programming interface API which is accessed and executed on a remote server which hosts the requested service.

A load testing tool is software designed to examine an application behavior under various load conditions. The testing tool can emulate numerous concurrent users to simulate real life loads on the tested application. When doing so the testing tool collects information from various infrastructure components e.g. system servers which is analyzed. HP s LoadRunner typically may include several different tools Virtual User Generator VuGen Controller load generators Analysis and Launches.

When automatically recording any business process in a load testing tool such as for example LoadRunner a popular load testing application available from Hewlett Packard Inc HP various Web Service calls may be found in that process.

Currently when using LoadRunner and finding a Web Service call the appropriate Web Service Description Language WSDL is downloaded manually. WSDL may be an Extensible Markup Language XML format for describing network services as a set of endpoints operating on messages containing either document oriented information or procedure oriented information. The automation user also has to manually configure the request settings such as security. In the protocols heavy domain of web services for example WS Security WS Addressing this is a major overhead.

In accordance with an embodiment of the invention when using a testing tool such as for example HP s LoadRunner for business processes monitored in a transport level script it is suggested to analyze communication requests in a business process between a client and a server offering a service application to be tested. A call to a web service may be identified in the analyzed communication and a location of a Web Service Description Language WSDL file relating to the web service on a remote server may be determined from the analyzed communication requests. A WSDL file may be then automatically downloaded from the determined location.

Furthermore it is further suggested to perform automatic configuration of a client emulation to properly work with the application under test AUT e.g. configuration settings such as encoding and security settings.

Previously a user would download WSDL files manually and then configure the client emulation so as to facilitate proper use of the WSDL files. Manual downloading and configuring of WSDL requires considerable understanding of Web Services. According to an embodiment of the invention WSDL files may be automatically downloaded.

When a testing tool monitors a business process in transport level it may capture communication messages passing between the client and the server. These messages may be expressed in a script or a similar entity which may later be used for simulating the business process by the testing tool using a client emulation.

Commonly users of the testing tool may manually modify the recorded script for various reasons such as for example correlation and parameterization but also inserting client side logic to the script maintaining existing script to support changes of the application etc.

Therefore offering the users the ability to modify the script and the readability of the script may be desired.

Web Service calls may be expressed in the script in HTTP level i.e. by API for handling HTTP messages or in Web Services level. Working in Web Service level may require the WSDL file of the service.

Web Service level is typically a higher and more usable level. Configuration may be made in service level instead of message level. There is usually no need to modify each message just the service configuration. Web Service attributes may be expressed as entities and not as a set of Simple Object Access Protocol SOAP headers. Also some security mechanisms like message level security may not be able to simulate in HTTP level because the relevant SOAP headers are generated dynamically. In addition working in service level may have the code efficiency advantage that a service proxy may be used for generating the service calls. One of the main proclaimed objects of automatic testing tools is the record and replay ability e.g. simulating the business process after recording it with minimum intervention of the user.

The configuration of the client is complicated and requires wide understanding of Web Services technology. For example in LoadRunner there are tens of options that the user would have to configure manually. Manual work takes time and is more prone to mistakes. It requires a wide understanding of Web Services technology that application testers do not usually possess.

An HTTP message to a web service WS server may be captured. The message may be analyzed and heuristics may be employed to find the location of the web service. For example the location of the web service may be determined from a destination indication of the message or from other parts of the message allowing the determination of the WS location.

The following exemplary scripts relate to Silverlight Web Services embodiments of the invention may be applicable to other platforms as well 

B. the string wsdl may be appended after the service name in the end point. For example http may be amended to http wsdl .

For example the service MEX Metadata Exchange endpoint http msdn.microsoft.com enus library ms730243.aspx may be used running SvcUtil.exe one to obtain service endpoints locations. In addition the user may be offered the possibility of manually specifying the WSDL. A local cache may be kept at machine level of previously downloaded WSDL files. When the endpoint is identified from the recorded envelope one may choose the best source for the WSDL for example by applying heuristics.

Once the WSDL files are successfully downloaded one may analyze the HTTP message and determine the attributes used by the client in order to properly configure the client.

For example in Web Services created in Silverlight platform it may be possible to identify which port is used in each request by matching the HTTP message endpoint to the endpoints of the ports which are specified in the WSDL. It may also be possible to encode binary XML or plain text identified by its HTTP content type.

Additional examples for attributes that may be detected by the corresponding SOAP headers e.g. duplex binding Web Service addressing version authentication mode UserNameOverTransport authentication mechanism such as used in Silverlight .

According to embodiments of the present invention Soap messages which may be captured on the wire may be analyzed. This may allow presenting a standards free request and automatically configure the replay.

For example consider a client e.g. Silverlight client who wants to send a plain XNL message containing the number 42 to a server logical message . Such message may be in the following form binary encoding is omitted for clearness this envelope is very simplified and does not necessarily reflect how any of the standards appear in a SOAP 

The message may be subjected to WS standards. The process of applying these standards may involve applying an algorithm on the logical message. The result of applying the algorithm on the logical message is an opaque message which is communicated to the WS server the above example message .

Using deep domain knowledge and heuristics the logical message may be extracted and the algorithm which the real client applied may be reconstructed.

According to embodiments of the present invention a tester may now independently edit the logical message or the algorithm using an editor.

During replay the algorithm may be applied on the logical message ensuring that server policies are satisfied. This may also refresh any stale or dynamic data e.g. timestamps IDs .

There may be no generic way of identifying each algorithm step applied on a message nor reverting the message to its state prior to applying the algorithm on it. Each protocol may have its own set of structures and formats. For example identifying WS addressing headers may require querying the message with an XPath expression. In contrast pinpointing an exact WS Security configuration may require a correlation between different parts of a message between a request and its response and sometimes even between multiple correspondences. For example when WS SecureConversation is applied multiple messages may be exchanged and only after the last request response pair may one fully identify the use of derived encryption keys or signatures.

The client may send a message on the wire to the web service server. This message may be a standalone message that does not have any metadata inside it or linked to it.

During code generation heuristics may be used to find the metadata WSDL which corresponds to this message. These heuristics may be based for example on keeping a machine wide cache for WSDLs guessing the metadata address based on the destination URL trying to download it and or parsing HTML error messages which the server renders after a false guess.

Now the logical message may be linked to its metadata. This may give the tester a rich set of capabilities such as data driving schema aware data editing and refreshing the metadata on demand.

Once the attributes of the intercepted message are determined the client may be configured accordingly.

The automation offered by embodiments of the present invention may save work time of downloading and configuring the services. Also it may reduce the number of errors that may occur in a manual process. Manual configuration requires wider understanding of Web Services technology including security and authentication aspects standards encoding and so on which automated configuration may eliminate or greatly reduce.

AUT server is designed to service remote clients with an application which is mostly or fully executed on that server.

In the process a remote Web Service may be required which is hosted on remote WS server . Clients may download the appropriate WSDL files from remote WS server so as to allow them to properly cooperate with the AUT server .

A testing tool which may be executed on another server may monitor a business process of client and may emulate a plurality of clients so as to simulate real life load scenarios.

Reference is now made to illustrating a method for automated download and configuration of web services in a testing tool in accordance with an embodiment of the present invention.

Such method may include analyzing communication requests between a client and an AUT server which is part of a business process monitored by a testing tool. The method may also include identifying a call to a web service in the analyzed communication requests. The method may further include determining from the web service call the location of a WSDL file relating to the web service on a remote server may be determined . Once the location of the WSDL file is determined it may be automatically downloaded .

The method may also include automatically configuring the client to work with the WS based on analyzing the web service call.

For example such method may include capturing a HTTP message in the communication between a client and a WS server. The location of the WS may be then identified based on message information for example by applying heuristics .

Once the location of the WS is determined the appropriate WSDL files may be downloaded to the client.

The method may include analyzing the communication between a client and an AUT server for example a HTTP message and determining attribute of that HTTP message. Based on information related to the determined attribute it may be possible to configure the client emulation .

The HTTP headers soap headers and soap body may be analyzed and the presence of WS standards public or vendor proprietary such as WS Addressing Windows Communication Foundation WCF binary encoding WCF is a Microsoft web service technology WS Security may be determined. Based on domain knowledge and heuristics it may be possible to determine how these standards were applied on the captured message and extract these standards. This way the user may be presented with a standards free message so he can edit it. These standards may also be applied when performing the testing of the AUT.

The system may include for example a computing device which may include a storage device for storing a computer program for testing an AUT server which may include automated download and configuration of web services. The system may also include a processor for executing the computer program Input output I O interface for input and out put and communication interface for communication with other devices using direct communication or over a network .

Aspects of the present invention may be embodied as a computer program product saved on one or more computer readable mediums in the form of computer readable program code embodied thereon. For example the computer readable medium may be a non transitory storage medium. A computer readable storage medium may be for example an electronic optical magnetic electromagnetic infrared or semiconductor system apparatus or device or any combination thereof.

Computer program code of the above described embodiments of the invention may be written in any suitable programming language. The program code may execute on a single computer or on a plurality of computers.

The foregoing description of the embodiments of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. It should be appreciated by persons skilled in the art that many modifications variations substitutions changes and equivalents are possible in light of the above teaching. It is therefore to be understood that the appended claims are intended to cover all such modifications and changes as fall within the true spirit of the invention.

