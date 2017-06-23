---

title: Apparatus and method for remote control in a short-range network, and system supporting the same
abstract: An apparatus and method for remote control in a short-range network system, and a system supporting the same are provided, in which from a remote device that remotely controls the application execution device using a predetermined Control User Interface (CUI), information about capability of the remote device is collected, a CUI request requesting a CUI to be used for remotely controlling a currently executed application and the information about the capability of the remote device are sent to an application server, a CUI matching the capability of the remote device is received from the application server in response to the CUI request, and the received CUI is sent to the remote device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09607504&OS=09607504&RS=09607504
owner: Samsung Electronics Co., Ltd
number: 09607504
owner_city: 
owner_country: KR
publication_date: 20100901
---
This application claims priority under 35 U.S.C. 119 a to applications filed with the Korean Intellectual Property Office on Sep. 1 2009 and Oct. 12 2009 and assigned Serial No. 10 2009 0082237 and 10 2009 0096927 respectively the contents of both of which are incorporated herein by reference.

The present invention generally relates to an apparatus and method for matching a User Interface UI for remote control in a short range network. More particularly the present invention relates to an apparatus and method for enabling operation of a Control UI CUI matching the capability of a device in a short range network.

Many industrial standardization organizations have been conducting extensive research to increase the performance of home networking based on a short range network such as Digital Living Network Alliance DLNA a Home Audio Video Interoperability HAVi and Universal Plug and Play UPnP .

In a home network one device can control another device by Remote User Interface RUI technology. According to the RUI technology based on client server architecture an RUI Client RUIC fetches a UI from an RUI Server RUIS and allows a user to control the RUIS through the UI in the RUIC.

Accordingly there exists a need for developing a method for receiving a UI from an RUIS in order to control the RUIS in an RUIC.

An aspect of exemplary embodiments of the present invention is to address at least the problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of exemplary embodiments of the present invention is to provide an apparatus and method for providing an RUI so that a remote device can control an RUIS or an RUIC through the RUI.

Another aspect of exemplary embodiments of the present invention provides an apparatus and method for enabling an RUIS to provide an RUI matching the capability of a remote device.

A further aspect of exemplary embodiments of the present invention provides an apparatus and method for enabling a remote third device to receive a CUI matching the capability of the remote third device from an RUIS so that the remote third device can control a remote UI device through the CUI.

In accordance with an aspect of exemplary embodiments of the present invention there is provided a remote control method of an application execution device in a short range network system in which from a remote device that remotely controls the application execution device using a predetermined CUI information about capability of the remote device is collected a CUI request requesting a CUI to be used for remotely controlling a currently executed application and the information about the capability of the remote device are sent to an application server a CUI matching the capability of the remote device is received from the application server in response to the CUI request and the received CUI is sent to the remote device.

In accordance with another aspect of exemplary embodiments of the present invention there is provided an application execution device for performing remote control in a short range network system in which a first entity collects from a remote device that remotely controls the application execution device using a predetermined CUI information about capability of the remote device and a second entity sends a CUI request requesting a CUI to be used for remotely controlling a currently executed application and the information about the capability of the remote device to an application server and receives a CUI matching the capability of the remote device from the application server in response to the CUI request. The first entity sends the CUI received from the second entity to the remote device.

In accordance with another aspect of exemplary embodiments of the present invention there is provided a method for remotely controlling an application execution device using a predetermined CUI in a remote device in a short range network system in which information about capability of the remote device is sent to the application execution device a CUI matching the capability of the remote device is received from the application execution device and an application being executed in the application device is remotely controlled using the received CUI.

In accordance with a further aspect of exemplary embodiments of the present invention there is provided a system for providing a DAE application through remote control in which an application server provides a DAE application and a CUI a remote device sends information about capability of the remote device after the remote device is connected to an application execution device and receives a CUI matching the capability of the remote device from the application execution device and the application device collects the information about the capability of the remote device from the remote device sends a CUI request requesting a CUI to be used for remotely controlling a currently executed application and the information about the capability of the remote device to the application server and receives the CUI matching the capability of the remote device from the application server in response to the CUI request.

Throughout the drawings the same drawing reference numerals will be understood to refer to the same elements features and structures.

The matters defined in the description such as a detailed construction and elements are provided to assist in a comprehensive understanding of exemplary embodiments of the invention. Accordingly those of ordinary skill in the art will recognize that various changes and modifications of the embodiments described herein can be made without departing from the scope and spirit of the invention. Also descriptions of well known functions and constructions are omitted for clarity and conciseness.

In accordance with embodiments of the present invention as set forth below a Remote User Interface Client RUIC refers to a device that sends a Remote User Interface RUI and control information to a client in a client server architecture system. The RUIC may be a set top box that controls an Internet Protocol TV IPTV etc.

The RUIC receives UIs that can be rendered in the RUIC and Control UIs CUIs that can control the rendered UIs from a Remote User Interface Server RUIS . The RUIC and or the RUIs rendered in the RUIC are controlled through the CUIs.

In an embodiment of the present invention a third device which is a remote control RUIC device controls an RUIC through a CUI. The CUI may be received from the RUIC or the RUIS. The third device may be any of a mobile device e.g. a portable phone a portable device e.g. a small size display equipped with a communication function etc. The following description is made with the appreciation that the term remote control RUIC device is used interchangeably with the terms third device third RUIC or third RUIC device .

Referring to an RUIC communicates with an RUIS according to a preset protocol via a first interface I F . The RUIC receives an RUI and control information from the RUIS based on a protocol configured for I F . The control information may include a CUI as well as control information needed for controlling an RUI rendered in the RUIC .

An embedded server of the RUIC extracts the CUI from the control information received from the RUIS and sends the CUI to a third RUIC for controlling the RUIC . The CUI is rendered in the third RUIC so that a user of the third RUIC may control the RUIC through the CUI.

In the illustrated cases of the embedded server is configured outside an RUIC . Especially the embedded server may be an embedded server functional entity that resides within a Consumer Electronics Association CEA 2014 RUIS a DLNA RUIS or an Open IPTV Forum Terminal Function OITF of the Open IPTV Forum for communication with a mobile portable device. In addition the embedded server may even incorporate the function of a remote control plug in into it.

The RUIC or an RUI rendered in the RUIC may be controlled via a second interface I F between the RUIC and the third RUIC according to UPnP or HyperText Transfer Protocol HTTP using a CUI rendered in the third RUIC .

Referring to the third RUIC may fetch a CUI matching its capability from the RUIC through capability exchange with the embedded server of the RUIC . This is possible because a protocol was defined for I F between the third RUIC and the RUIC .

However there is no specified method for enabling the third RUIC to send information about its capability to the RUIS . As a consequence the third RUIC cannot fetch a CUI matching its capability from the RUIS .

Therefore protocols will be defined for I F and a third interface I F such that the RUIS may provide the third RUIC with a CUI matching the capability of the third RUIC in accordance with embodiments of the present invention.

A detailed description will be given of an apparatus and method for allowing a third RUIC to receive a CUI matching its capability from an RUIS for controlling an RUI rendered in an RUIC according to an embodiment of the present invention.

Referring to the third RUIC sends information about its capability to an embedded server of the RUIC via I F . The embedded server in turn sends the received capability information to a remote control plug in via a fourth interface I F .

The remote control plug in stores the capability information. A first browser Browser instructs the remote control plug in to download a CUI through communication with an RUI rendered by Browser by sending a CUI download command to the remote control plug in via a fifth interface I F .

Upon receipt of the CUI download command from Browser the remote control plug in converts the stored capability information into a format transmittable through a sixth interface I F . When needed the format of the stored capability information may not be converted. I F is defined between the RUIC and the RUIS .

The remote control plug in sends an HTTP message requesting CUI download to the RUIS via I F . A header of the HTTP message includes the capability information converted to a user agent value. As stated before the capability information may not be converted when needed.

Upon receipt of the capability information expressed as a User Agent value illustrated in Table 1 the RUIC provides the received capability information to the remote control plug in . The remote control plug in converts the capability information into a format transmittable to the RUIS e.g. User Agent A .

For example if the capability information is sent in a format defined by the OIPF a header structure defined by the OIPF may be modified to include the converted capability information in the HTTP Header as illustrated in Table 2.

The capability information illustrated in Table 1 is included in the capability information having the configuration illustrated in Table 2. For example the capability information may be included in a field illustrated in Table 2.

If capability information taking the form of User Agent A sent from the third RUIC to the RUIC is configured in the same format as capability information taking the form of User Agent A sent from the RUIC to the RUIS the capability information may be sent from the RUIC to the RUIS without being changed in format and contents.

Specifically is a flowchart illustrating a CUI providing operation in the case where a third RUIC is currently connected to an RUIC and is a flowchart illustrating a CUI providing operation in the case where a third RUIC is not currently connected to an RUIC and requests a CUI when the third RUIC is connected to the RUIC later.

Referring to an RUIC requests an RUI to an RUIS in step . The RUIS sends the requested RUI to the RUIC. In step the RUIC renders the RUI.

The RUI monitors the existence of a third RUIC currently connected to the RUIC in step . In the absence of a currently connected third RUIC no further CUI request process associated with the RUI is proceeded in step . When the third RUIC is connected to the RUIC later and requests a CUI the operation illustrated in is performed.

On the other hand in the presence of a third RUIC currently connected to the RUIC in step the RUIC requests capability information to the third RUIC and receives the capability information from the third RUIC in step .

In step the RUIC requests a CUI matching the capability of the third RUIC to the RUIS. Then the RUIS sends the CUI to the RUIC.

Referring to if the third RUIC is not currently connected to the RUIC at the moment the RUI is rendered in the operation of but later it is connected to the RUIC and requests a CUI to the RUIC the RUIC receives the CUI request from the third RUIC while the RUI is being rendered in step . In step the third RUIC sends its capability information to the RUIC.

In step the RUIC sends a CUI request along with the capability information to the RUIS. Then the RUIS extracts a CUI matching a capability indicated by the capability information and sends the CUI to the RUIC. The RUIC sends the CUI to the third RUIC in step .

Referring to upon receipt of an RUI rendering command from a third terminal or a traditional remote control an RUIC requests an RUI to an RUIS .

Then the RUIC receives the RUI from the RUIS and renders the received RUI in its browser . While being rendered the RUI asks a remote control plug in whether there is a third RUIC currently connected to the RUIC through a isRCExist method.

The remote control plug in in turn asks an embedded server whether there is a currently connected third RUIC. Then the embedded server checks the presence or absence of a connected third RUIC.

In the presence of a connected third RUIC the embedded server sends a message requesting capability information to the third RUIC . The third RUIC sends its capability information along with a CUI request message to the embedded server .

If the third RUIC has a history of accessing the embedded server and sending an HTTP message to the embedded server the embedded server internally stores a User Agent value set in the HTTP header of the HTTP message at the time. When the third RUIC is disconnected from the embedded server the stored User Agent value is deleted.

Until the connection between the third RUIC and the embedded server is released the third RUIC is in a state where it can receive a notification from the embedded server .

In this state upon receipt of a command to monitor the presence of the connected third RUIC from the remote control plug in the embedded server determines whether it has the User Agent value. When detecting the User Agent value the embedded server sends the User Agent value to the remote control plug in .

The remote control plug in stores the received User Agent value internally and sends a value true indicating the presence of the currently connected third RUIC to the RUI . The order of the value true transmission and the capability information storing may be changed.

Upon receipt of the value true the RUI sends a getCUI command to the remote control plug in requesting a CUI for use in controlling the RUI .

The remote control plug in converts the format of the capability information suitably for the RUIS and sends the converted capability information along with a CUI request to the RUIS . Then a CUI is downloaded at an appropriate position in the embedded server for transmission to the third RUIC .

To simplify the implementation of the embodiment of the present invention the process from calling an isRCExist method to returning the value true to the RUI may not be performed. Instead if the third RUIC has a history of accessing the RUIC and sending an HTTP message to the RUIC at least once the User Agent value is kept in the RUIC . When the RUI calls a getCUI method from the remote control plug in the remote control plug in requests a CUI associated with the RUI to the RUIS by simply using the User Agent value or converting the format of the User Agent value.

Upon completion of the CUI download the remote control plug in sends an onCompleteReceiveCUI event to the RUI indicating that the CUI download has been completed. Then the RUI sends a sendCUI command to the remote control plug in instructing the remote control plug in to send the CUI to the third RUIC .

Upon receipt of the command the remote control plug in sends a CUI send command to the embedded server . The embedded server then sends the CUI or a URL of the CUI to the third RUIC .

In case of receiving the URL of the CUI the third RUIC receives the CUI matching its capability at the URL and renders the received CUI.

Referring to as an RUI is rendered in the browser of the RUIC it is determined whether there is a currently connected third RUIC . In the absence of the currently connected third RUIC no further CUI associated process is proceeded.

Upon receipt of a CUI request message including capability information about the third RUIC from the third RUIC later the embedded server sends the capability information to the remote control plug in .

The remote control plug in stores the received capability information and then sends an onCUIRequest event indicating the reception of the CUI request to the RUI currently being rendered in the browser . The RUI then sends a getCUI command requesting a CUI for controlling the RUI to the remote control plug in .

The remote control plug in converts the format of the capability information about the third RUIC into a format transmittable to the RUIS and sends the converted capability information along with a CUI download request to the RUIS . Thereafter the remote control plug in downloads a CUI from the RUIS and stores the CUI at an appropriate location. The subsequent operation is performed in the same manner as illustrated in .

In accordance with the embodiment of the present invention illustrated in the RUIC sends a CUI to the third RUIC in a forwarding scheme not in a download scheme.

Referring to the RUI requests the remote control plug in to receive a CUI from the RUIS . The remote control plug in then requests the CUI to the RUIS . The RUIS encapsulates the contents of the requested CUI in a body of an HTTP message and sends the HTTP message to the remote control plug in .

The remote control plug in extracts the contents of the CUI from the received HTTP message and sends the extracted contents of the CUI to the RUI . The RUI commands the remote control plug in to send the contents of the CUI to the third RUIC through an embedded Web server . The contents of the CUI may be modified by the RUI the remote control plug in or the embedded Web server when needed.

Signaling of onCompleteReceivingCUI and sendCUI may not be performed according to situations. For example in the case where the remote control plug in requests a CUI to the RUIS and receives a response from the RUIS if it is not necessary to notify the RUI of what the response is about the signaling is not performed. In this case the remote control plug in sends the contents of the CUI extracted from the HTTP message received from the RUIS to the embedded Web server . Then the embedded Web server sends the received contents of the CUI to the third RUIC .

In accordance with the embodiment of the present invention illustrated in the RUIC sends a CUI to the third RUIC in a forwarding scheme not in a download scheme.

Referring to as an RUI is rendered in the browser of the RUIC it is determined whether there is a currently connected third RUIC . In the absence of the currently connected third RUIC no further CUI associated process is proceeded.

Upon receipt of a CUI request message including capability information about the third RUIC from the third RUIC later the embedded server sends the capability information to the remote control plug in .

The remote control plug in stores the received capability information and then sends an onCUIRequest event indicating the reception of the CUI request to the RUI currently being rendered in the browser . The RUI then sends a getCUI command requesting a CUI for controlling the RUI to the remote control plug in .

Then the remote control plug in requests a CUI to the RUIS . The RUIS encapsulates the contents of the requested CUI in a body of an HTTP message and sends the HTTP message to the remote control plug in .

The remote control plug in extracts the contents of the CUI from the received HTTP message and sends the extracted contents of the CUI to the RUI . The RUI commands the remote control plug in to send the contents of the CUI to the third RUIC through the embedded Web server . The contents of the CUI may be modified by the RUI the remote control plug in or the embedded Web server when needed.

The signaling of onCompleteReceivingCUI and sendCUI may not be performed according to situations. For example in the case where the remote control plug in requests a CUI to the RUIS and receives a response from the RUIS if it is not necessary to notify the RUI of what the response is about the signaling is not performed. In this case the remote control plug in sends the contents of the CUI extracted from the HTTP message received from the RUIS to the embedded Web server . Then the embedded Web server sends the received contents of the CUI to the third RUIC .

Referring to a DLNA device RUIPL requests an IPTV service to an OITF through a predefined Universal Resource Identifier URI . The DLNA device RUIPL also sends its capability information along with a service request message when requesting the IPTV service.

DLNA functions RUISRC store the capability information and command a Declarative Application Environment DAE browser to receive a DAE application matching the IPTV service from an IPTV applications server and execute the DAE application.

When a DAE application matching the IPTV service is executed in the DAE browser in response to the command the DAE application provides a getCUI method along with a URI of a CUI to a remote control plug in . Then the remote control plug in retrieves the stored capability information from the DLNA functions RUISRC and processes the capability information such that it can be sent to the IPTV applications server . When needed the capability information may not be processed.

Meanwhile the remote control plug in sends the processed or non processed capability information to the IPTV applications server using the URI parameter set in the getCUI method and receives a CUI from the IPTV applications server . The CUI may be received in two schemes.

In the case where a CUI is received in a download scheme the remote control plug in downloads a compressed file including CUIs from the IPTV applications server to the DLNA functions and decompresses the downloaded compressed file and indicates an accessible location to the DAE application in the form of a URL corresponding to the decompressed directory using an onCompleteReceivingCUI event function.

The DAE application generates a new URI by attaching the received prefix URI to the name of a CUI included in an internally stored CUI list. The DLNA device may access the CUI of the OITF using the new URI.

The new URI is sent to the DLNA device through a sendCUI method. The DLNA device calls the URI and receives the CUI from the DLNA functions in the OITF .

On the other hand in the case where a CUI is received from the IPTV applications server in a forwarding scheme the DAE application receives the HTML contents of a CUI from the IPTV applications server through a getCUI method. The DAE application modifies the HTML contents when needed and then sends the modified HTML contents to the DLNA device through a sendCUI method. If the HTML contents do not need to be modified the DAE application may simply send the HTML contents to the DLNA device through the sendCUI method.

As described above HTML contents are included in sendCUI in the forwarding scheme whereas a URI value is included in sendCUI in the download scheme.

Referring to it is assumed herein that an IPTV service is going on by the DAE application in the OITF . In this state a user requests a CUI to the OITF through a predefined URI using an ITF Remote Control Function IRCF of the DLNA device in order to control the on going IPTV service. Herein the DLNA device sends its capability information along with a CUI request message to the DLNA functions . The capability information is stored in the DLNA functions .

The DLNA functions notify the remote control plug in of the reception of the CUI request from the DLNA device . The remote control plug in in turn notifies the DAE application of the reception of the CUI request through an onCUIRequest event function. The DAE application commands the remote control plug in to receive the CUI from the IPTV applications server through a getCUI method. The DLNA functions use the stored capability information to receive the CUI from the IPTV applications server . The subsequent process is performed in the same manner as illustrated in and will not be described herein in detail.

As to Property Event when a third RUIC requests a CUI for a DAE application being executed in an OITF a remote control plug in generates an onCUIRequest callback event function to the DAE application. A device handle value for the currently connected third RUIC is also sent as a parameter to the DAE application. Before the onCUIRequest callback event function is generated to the DAE application the OITF stores capability information about the third RUIC received along with a CUI request from the third RUIC. The capability information is used when a getCUI method is called later to receive an appropriate CUI that can be rendered in the third RUIC from an IPTV applications server.

An onCompleteReceivingCUI callback event function is generated to the remote control plug in by the DAE application. The onCompleteReceivingCUI callback event function requests a CUI download by a getCUI method. When a CUI is completely downloaded from the IPTV application server to the OITF and ready to be sent to the third RUIC the remote control plug in sends a prefix of a URI through which the downloaded CUI is accessible to the DAE application.

A parameter cuiPrefixURI sent along with the onCompleteReceivingCUI callback event function is expressed as a URI e.g. cui playercontroller 001 through which the third RUIC can access a directory having the downloaded CUI.

If the name of a CUI that the DAE application has is friends cod controller.html a combination of cuiPrefixURI and the name of the CUI may be sent to the third RUIC e.g. cui playercontroller 001 friends cod controller.html .

Regarding Method there is a Boolean isRCExist method for in the presence of the capability information about the third RUIC sending the capability information to the remote control plug in. If a value true is returned this means that the third RUIC is currently connected to the OITF and the capability information is successfully stored in the remote control plug in of the OITF.

In case of a getConnectedRemoteDeviceHandle method similar in function to the isRCExist method when the DAE application calls it it delivers an integer device handle value by which to adjust the connected third RUIC to the DAE application. In the absence of a connected third RUIC an undefined value or a null value is returned.

The DAE application commands the remote control plug in to download a CUI from the IPTV applications server through the getCUI method. The DAE application also sends a URL for downloading as a parameter to the remote control plug in. Then the remote control plug in sends to the IPTV applications server a download request message along with the capability information about the third RUIC stored in the OITF.

The getCUImethod is asynchronous. When the DAE application calls the getCUI method a value true or false indicating success or failure of the getCUI method execution is directly returned to the DAE application. That is although the download is being performed between the remote control plug in and the IPTV applications server the DAE application can perform a process shortly after calling the getCUI method. Upon completion of the download between the remote control plug in and the IPTV applications server the afore described onCompleteReceivingCUI event is sent to the DAE application.

When the DAE application sends to the remote control plug in the device handle value specific to the third RUIC currently connected to the OITF along with the URI information by which a CUI is accessible by calling a sendCUI method the remote control plug in sends the URI information as a second parameter to the third RUIC identified by the device handle value as a first parameter. Thus the third RUIC can fetch the CUI from the OITF using the URI information.

HTTP uses an interface defined in the OITF DAE SPEC as an interface between the remote control plug in and an RUIS and writes the capability information about the third RUIC at a location designated for writing capability information. Basically other information about the third RUIC is also written together such as vendorName modelName softwareVersion hardwareVersion applicationName and applicationVersion.

If such information i.e. vendorName modelName softwareVersion hardwareVersion applicationName and applicationVersion of the third RUIC cannot be sent together with the capability information about the third RUIC for example when the third RUIC has not sent the information about vendorName modelName softwareVersion hardwareVersion applicationName and applicationVersion this information may be replaced with information about the OITF. Because the information about vendorName modelName softwareVersion hardwareVersion applicationName and applicationVersion of the third RUIC is optional a field designed for the capability information and the other information about the third RUIC may carry only the capability information. Meanwhile the other information about the third RUIC is marked with in the description of the interface between the remote control plug in and the IPTV applications server in . means optional.

The protocol is required to send an RUI an IPTV service from an IPTV applications server to an OITF and to render the RUI in the OITF through a third RUIC in the flowcharts of .

As is apparent from the above description of the present invention since a remote third device can receive a CUI matching the capability of the third device from an RUIS the performance of a short range network can be maximized.

Exemplary embodiments of the present invention can also be embodied as computer readable codes on a computer readable recording medium. The computer readable recording medium is any data storage device that can store data which can thereafter be read by a computer system. Examples of the computer readable recording medium include but are not limited to read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks optical data storage devices and carrier waves such as data transmission through the Internet via wired or wireless transmission paths . The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. Also function programs codes and code segments for accomplishing the present invention can be easily construed as within the scope of the invention by programmers skilled in the art to which the present invention pertains.

While the invention has been shown and described with reference to certain exemplary embodiments of the present invention thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the appended claims and their equivalents.

