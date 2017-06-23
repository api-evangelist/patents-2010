---

title: Method and apparatus for providing remote user interface service
abstract: Provided is a method of providing a remote user interface (UI) service of a remote UI client device. The method includes: receiving optimized scalable vector graphics (OSVG) information encoded so as to represent graphics including contents and a UI from a remote UI server device; decoding the encoded OSVG information; and rendering the decoded OSVG information using an OSVG primitive application programming interface (API).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09160556&OS=09160556&RS=09160556
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09160556
owner_city: Suwon-si
owner_country: KR
publication_date: 20100216
---
This application claims the benefit of Korean Patent Application No. 10 2009 0134930 filed on Dec. 30 2009 in the Korean Intellectual Property Office and U.S. Provisional Application No. 61 152 321 filed on Feb. 13 2009 in the USPTO the disclosures of which are incorporated herein in their entirety by reference.

The present invention relates to a method and apparatus for providing a remote user interface UI service and more particularly to a method and apparatus for providing a remote UI service in which a remote UI client device that received encoded optimized scalable vector graphics OSVG information from a remote UI server device renders graphics represented by the OSVG information by using OSVG primitive application programming interfaces API .

A server executes various applications providing contents and requiring a user interface UI to a client device. The server represents graphics including contents and a UI as bitmap graphics or vector graphics.

As networks have recently advanced there are demands for various client devices such as a television TV a mobile device etc. connected to a server through a network to receive graphics including contents and a UI from the server and to control applications executed in the server through various input output interfaces of the client devices.

In this instance a client device has various specifications in terms of resolution memory capacity and network bandwidth etc. and thus it is necessary to consider the environments of the client device.

The present invention provides a method and apparatus for providing a remote UI service in which a remote UI client device that received encoded optimized scalable vector graphics OSVG information from a remote UI server device renders graphics represented by the OSVG information by using OSVG primitive application programming interfaces API .

The present invention also provides a computer readable recording medium having embodied thereon a computer program for executing the method.

According to an aspect of the present invention there is provided a method of providing a remote UI service of a remote user interface UI client device the method including receiving optimized scalable vector graphics OSVG information encoded so as to represent graphics including contents and a UI from a remote UI server device decoding the encoded OSVG information and rendering the decoded OSVG information using an OSVG primitive application programming interface API .

The encoded OSVG information is information that text based OSVG information is binary encoded and also is information that only semantic information representing a changed state is encoded when the remote UI server device renews graphics.

The decoding of the encoded OSVG information includes decoding the encoded OSVG information to the text based OSVG information and parsing each OSVG primitive API.

The OSVG primitive API includes at least one from among the group consisting of Define Viewport Define Transform Define Color Define Gradient Define Path Define Image Define Font Define Group Define Animation Push Transform Pop Transform Stroke Path Fill Path Draw Image Draw Glyphs Draw Text Draw Group and Animate.

The OSVG primitive API includes at least one from among from among the group consisting of Query Screen Query Viewport Query Font Metrics Query Glyph Metrics Query Memory Query Instrumentation Define Event Reserve Event Release Event Remove Definition and Capture Raster.

The method further includes generating an input event for controlling an application executed in the remote UI server device on the basis of an external input encoding the input event using a value defined in a predetermined protocol and transmitting the encoded input event to the remote UI server device.

According to another aspect of the present invention there is provided a method of providing a remote UI service of a remote UI server device the method including executing an application providing contents and requiring a UI encoding graphics including the contents and the UI to OSVG information and transmitting the encoded OSVG information to a remote UI client device.

The application is implemented using local APIs including JAVA abstract window toolkit AWT APIs and home audio video interoperability HAVI APIs and the encoding of the graphics is executed using APIs encoding to OSVG information.

The encoded OSVG information is information that text based OSVG information is binary encoded and also is information that only semantic information representing a changed state is encoded when the remote UI server device renews graphics.

The method further includes receiving from the remote UI client device an encoded input event for controlling the application decoding the input event to a value defined in the application and executing the application so as to control the application using the decoded input event.

According to another aspect of the present invention there is provided a computer readable recording medium having embodied thereon a computer program for executing the method.

According to another aspect of the present invention there is provided a remote UI client device including an OSVG information receiving unit for receiving OSVG information encoded so as to represent graphics including contents and a UI from a remote UI server device an OSVG information decoding unit for decoding the encoded OSVG information and a rendering unit for rendering the decoded OSVG information using an OSVG primitive API.

According to another aspect of the present invention there is provided a remote UI server device including an application executing unit executing an application for providing contents and requiring a UI an OSVG information encoding unit encoding graphics including the contents and the UI to OSVG information and an OSVG information transmitting unit transmitting the encoded OSVG information to a remote UI client device.

The present general inventive concept will now be described more fully with reference to the accompanying drawings in which exemplary embodiments of the present general inventive concept are shown. In the drawings like reference numerals denote like elements and the sizes and thicknesses of elements may be exaggerated for clarity.

A remote UI server device is a network based device executing various applications providing contents and requiring a UI. The remote UI server device includes various consumer electronics CE devices such as a set top box or the like. The applications executed in the remote UI server device may be implemented using local application programming interfaces APIs including JAVA abstract window toolkit AWT APIs and home audio video interoperability HAVI APIs. However one of ordinary skill in the art would understand that various other implementations are possible.

A remote UI client device is a network based device including various input output interfaces and includes a TV and mobile devices.

The remote UI server device encodes graphics including contents and a UI to optimized scalable vector graphics OSVG information and provides the encoded OSVG information to the remote UI client device remotely through a network.

The remote UI server device maps application local APIs to OSVG based graphic encoding APIs executes an OSVG encoding independently on the application local APIs and then transmits the encoded OSVG information to the remote UI client device .

A scalable vector graphics SVG which is a language based on extensible markup language XML to represent two dimensional graphics is an XML graphics standard proposed by the world wide web consortium W3C . The SVG allows three types of graphic objects including images text and vector graphic shapes.

The OSVG information is information represented by optimizing SVG information. The OSVG information optimizes the SVG information by binary encoding the SVG information and encoding only semantic information representing a changed state in order to represent renewed graphics.

The remote UI client device decodes the encoded OSVG information received from the remote UI server device and then renders the graphics represented by the OSVG information by using an OSVG primitive API.

The remote UI client device receives various control commands text etc. from a user encodes them and then transmits the encoded input event to the remote UI server device . The remote UI server device decodes the input event provides the input event to an application requiring the input event and then executes the application.

According to the current embodiment the remote UI server device represents graphics as OSVG information not as a bitmap graphic and provides the graphics to the remote UI client device so that a remote UI service which is extensible and may maintain the quality of the graphics may be provided to the remote UI client device having various specifications in terms of resolution memory capacity network bandwidth and the like.

Furthermore according to the current embodiment the remote UI server device binary encodes text based SVG information and transmits OSVG information that only semantic information representing a changed state to represent the renewed graphics is encoded to the remote UI client device so that the amount of the transmitted graphic information and a transmission time may be minimized and consequently a UI performance may be increased.

Furthermore according to the current embodiment even when the kinds of input output interfaces of the remote UI server device are limited user friendliness in that applications executed in the remote UI server device may be controlled through various input output interfaces of the remote UI client device is provided.

Furthermore according to the current embodiment the remote UI server device implements various applications providing contents and requiring a UI independently with standardized or non standardized remote UI service platform in a method of providing a subordinate remote UI service so that requirements of a standardized application implementation environment for example OpenCable Application Platform OCAP may be satisfied and a remote UI service may be provided to the remote UI client device as well.

In operation a remote UI server device executes an application providing contents and requiring a UI. The application may be implemented using local APIs including JAVA AWT APIs and HAVI APIs. However one of ordinary skill in the art would understand that other implementations are possible.

In operation the remote UI server device encodes graphics including contents and a UI to OSVG information. The remote UI server device encodes the graphics to the OSVG information using APIs encoding to OSVG information. The remote UI server device maps application local APIs to OSVG encoding APIs and then executes an OSVG encoding independently on the application local APIs.

The encoded OSVG information is information that text based OSVG information is binary encoded. The encoded OSVG information is also information that only semantic information representing a changed state is encoded when the remote UI server device renews graphics.

In operation the remote UI server device transmits the encoded OSVG information to a remote UI client device .

In operation the remote UI client device decodes the received encoded OSVG information. The remote UI client device decodes the encoded OSVG information to text based OSVG information and parses each OSVG primitive API.

In operation the remote UI client device renders the decoded OSVG information using an OSVG primitive API.

The OSVG primitive API includes at least one from among the group consisting of Define Viewport Define Transform Define Color Define Gradient Define Path Define Image Define Font Define Group Define Animation Push Transform Pop Transform Stroke Path Fill Path Draw Image Draw Glyphs Draw Text Draw Group and Animate .

The Define Viewport defines an area where graphics are to be rendered in a coordinate space. The Define Transform defines an affine transformation that converts a coordinate in a two dimensional coordinate space. The Define Color defines a color. The Define Gradient defines a gradient that exhibits a gradual color effect.

The Define Path defines an arbitrary shape representing an outline in successive dots. The Define Image defines a two dimensional raster image for example a joint photographic coding experts group JPEG image. The Define Font defines a font.

The Define Group defines a group consisting of a Path an Image and a Font. The Define Animation defines an animation in which contents of a vector graphic vary according to time.

The Push Transform executes a conversion requirement. The Pop Transform executes a conversion withdrawal. The Stroke Path draws an outline. The Fill Path fills an arbitrary shape represented in an outline. The Draw Image renders a two dimensional raster image. The Draw Glyphs renders a font of an outline. The Draw Text renders a series of glyphs consisting of at least one font. The Draw Group renders a group consisting of a Path an Image and a Font. The Animate renders contents of a vector graphic that varies according to time.

The OSVG primitive API further includes at least one from among the group consisting of Query Screen Query Viewport Query Font Metrics Query Glyph Metrics Query Memory Query Instrumentation Define Event Reserve Event Release Event Remove Definition and Capture Raster .

The Query Screen inquires about a screen that is a basic coordinate space where graphics are to be rendered. The Query Viewport inquires about an area where graphics are to be rendered in a coordinate space.

The Query Font Metrics inquires about properties of a font. The Query Glyph Metrics inquires about properties of an outline font. The Query Memory inquires about properties of a memory. The Query Instrumentation inquires about a graphic tool. The Define Event defines an event. The Reserve Event registers an event. The Release Event cancels the registration of the event. The Remove Definition cancels definitions about various graphic objects and graphic formats. The Capture Raster captures a two dimensional raster image.

In operation a remote UI client device generates an input event for controlling an application executed in a remote UI server device on the basis of an external input.

In operation the remote UI client device encodes the input event using a value defined in a predetermined protocol. The predetermined protocol includes a universal plug and play UPnP RemoteUI standard and a consumer electronics association CEA 2014 standard. However one of ordinary skill in the art would understand that other protocols for encoding the input event may be applied.

In operation the remote UI client device transmits the encoded input event to the remote UI server device .

In operation the remote UI server device decodes the received encoded input event to a value defined in the application.

In operation the remote UI server device executes the application to control the application using the decoded input event.

The remote UI server device includes an application executing unit an OSVG information encoding unit and an OSVG information transmitting unit .

The application executing unit executes an application providing contents and requiring a UI. The application is implemented using local APIs including JAVA AWT APIs and HAVI APIs.

The remote UI server device may further include an API mapping unit not shown that maps application local APIs to OSVG encoding APIs.

The OSVG information encoding unit encodes graphics including contents and a UI to OSVG information using APIs encoding to the OSVG information mapped by the API mapping unit.

The encoded OSVG information is information that text based OSVG information is binary encoded. The encoded OSVG information is also information that only semantic information representing a changed state is encoded when the remote UI server device renews graphics

The OSVG information transmitting unit transmits the encoded OSVG information to a remote UI client device .

The remote UI server device further includes an input event receiving unit not shown and an input event decoding unit not shown .

The input event receiving unit receives from the remote UI client device an encoded input event for controlling an application.

The application executing unit executes the application to control the application using the decoded input event.

The remote UI client device includes an OSVG information receiving unit an OSVG information decoding unit and a rendering unit .

The OSVG information receiving unit receives OSVG information encoded so as to represent graphics including contents and a UI from the remote UI server device .

The OSVG information decoding unit decodes the encoded OSVG information. The OSVG information decoding unit decodes the encoded OSVG information to text based OSVG information and parses each OSVG primitive API.

The OSVG primitive API includes at least one from among the group consisting of Define Viewport Define Transform Define Color Define Gradient Define Path Define Image Define Font Define Group Define Animation Push Transform Pop Transform Stroke Path Fill Path Draw Image Draw Glyphs Draw Text Draw Group and Animate .

The OSVG primitive API further includes at least one from among the group consisting of Query Screen Query Viewport Query Font Metrics Query Glyph Metrics Query Memory Query Instrumentation Define Event Reserve Event Release Event Remove Definition and Capture Raster .

The remote UI client device further includes an input event generating unit not shown an input event encoding unit not shown and an input event transmitting unit not shown .

The input event generating unit generates an input event for controlling the application executed in the remote UI server device on the basis of an external input.

The input event encoding unit encodes the input event using a value defined in a predetermined protocol. The predetermined protocol includes a UPnP Remote UI standard and a CEA 2014 standard. However one of ordinary skill in the art would understand that other protocols for encoding an input event may be applied.

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by one of ordinary skill in the art that various changes in form and details may be made therein without departing from the spirit and scope of the present invention as defined by the following claims.

For example the remote UI server device and the remote UI client device according to exemplary embodiments of the present invention may include a bus coupled to units of each device illustrated in at least one processor coupled to the bus and a memory that is coupled to the bus to store a command a received message or a generated message and is coupled to the at least one processor for executing the commands.

The invention can be also embodied as computer readable codes on a computer readable recording medium. The computer readable recording medium is any data storage device that can store data which can be thereafter read by a computer system. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs magnetic tapes floppy disks optical data storage devices etc. The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion.

