---

title: Information processing apparatus to process a processing target, information method, and computer readable medium
abstract: An information processing apparatus includes: a reliability determination unit that determines reliability required for processing a processing target based on the processing target; a processing determination unit that makes a comparison between the reliability determined by the reliability determination unit and reliability of a processing main body and determines whether or not the processing main body can be caused to process the processing target; a processing target change unit that changes the processing target so as to change the reliability of the processing target if the processing determination unit determines that the processing main body cannot be caused to process the processing target; and a processing request unit that requests the processing main body to process the processing target changed by the processing target change unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08612979&OS=08612979&RS=08612979
owner: Fuji Xerox Co., Ltd.
number: 08612979
owner_city: Tokyo
owner_country: JP
publication_date: 20100916
---
This application is based on and claims priority under 35 USC 119 from Japanese Patent Application No. 2010 024249 filed on Feb. 5 2010.

This invention relates to an information processing apparatus an information processing method and a computer readable medium.

According to an aspect of the invention an information processing apparatus includes a reliability determination unit that determines reliability required for processing a processing target based on the processing target a processing determination unit that makes a comparison between the reliability determined by the reliability determination unit and reliability of a processing main body and determines whether or not the processing main body can be caused to process the processing target a processing target change unit that changes the processing target so as to change the reliability of the processing target if the processing determination unit determines that the processing main body cannot be caused to process the processing target and a processing request unit that requests the processing main body to process the processing target changed by the processing target change unit.

Exemplary embodiments for realizing the invention will be discussed below based on the accompanying drawings 

A module refers to a generally and logically detachable component of software computer program hardware etc. Therefore the module in the exemplary embodiments means not only a module in a computer program but also a module in the hardware configuration. Therefore the exemplary embodiments also serve as the description of a computer program a system and a method for functioning as the modules. For the convenience of the description store and its equivalent word are used however if the exemplary embodiment is a computer program the words are used to mean storing in storage or controlling so as to store in storage. Modules may be in a one to one correspondence with functions however in implementation one module may be one program or two or more modules may make up one program or two or more programs may make up one module. Two or more modules may be executed by one computer or one module may be executed in two or more computers in a distributed or parallel environment. One module may contain any other module. In the description to follow the term connection is used to mean not only physical connection but also logical connection data transfer command reference relationship between data pieces etc. . The term predetermined refers to determined before target processing and is used to mean not only determined before start of processing according to exemplary embodiment but also determined in response to the situation or the state at the time or the situation or the state so far if the time is before the target processing even if the time is after the processing according to exemplary embodiment is started.

The system or apparatus is not only provided by connecting a plurality of computers hardware devices units etc. by communication means such as a network containing peer to peer communication connection etc. but also implemented as one computer hardware device apparatus etc. The apparatus and the system are used as synonyms. The system does not contain a social mechanism of artificial arrangement of course.

Target information is read from storage for each processing by each module or for each processing if a plurality of types of processing are performed in a module and after the processing is performed the processing result is written to storage. Therefore description of read from storage before processing and write to storage after processing may be omitted. The storage may contain hard disk RAM Random Access Memory an external storage medium storage through a communication line a register in a CPU Central Processing Unit etc.

An information processing apparatus of the exemplary embodiment causes a Web service providing apparatus A etc. to execute processing target in response to operation of a user . As shown in an example in the information processing apparatus has a service providing apparatus the Web service providing apparatus A and a Web service providing apparatus B. The service providing apparatus and the Web service providing apparatus A and the Web service providing apparatus B are connected by a communication line. In the example in the two Web service providing apparatus are illustrated but the number of Web service providing apparatus may be three or more or may be one. In the exemplary embodiment the processing main body refers to a computer a program etc. for processing the processing target. In the example in Web service A etc. applies. A plurality of processing main bodies may perform processing in cooperation hereinafter also called cooperation processing . The cooperation mode may be sequential processing for example mode in which the processing result of one processing body is used as the processing target of any other processing and processing is performed in sequence or may be parallel processing for example mode in which a plurality of processing main bodies perform the same processing target or different processing targets at the same time or may be a combination thereof In the description to follow sequential processing is mainly illustrated.

The service providing apparatus has a service processing module a reliability and security level relevant table storage module . It provides processing for the processing target in response to operation of the user . The service providing apparatus mainly provides service processing of a plurality of Web services in cooperation with each other.

The service processing module has an input output interface an initial security level determination module a data quality adjustment module a data division module a data integration module a security level management module a service cooperation module and a service relevant table storage module .

The input output interface is connected to the service cooperation module accepts operation of the user and passes the operation to the service cooperation module . It also performs output from the service cooperation module . For example the input output interface contains hardware of a keyboard a mouse a display a touch panel etc. and controls them. The input output interface for example may be provided by HTTP protocol and may be controlled through a Web browser etc. via a communication line from an information processing terminal operated by the user .

The initial security level determination module is connected to the service cooperation module and determines reliability hereinafter also called security level required for processing a processing target based on the processing target. The initial security level determination module passes the determined reliability to the service cooperation module .

The reliability required for processing the processing target is an evaluation value concerning the security that when the processing target is processed the processing main body for performing the processing must include. The reliability required for the processing target is previously set for the processing target. The setting is determined according to a processing security level determination flow described later for example. The reliability included by the processing main body is also previously set for the processing main body. The setting is made according to a Web service reliability table described later for example.

For example when the processing target is an image if a text area or a face image is contained by object recognition etc. the security level is set high. More specifically the topic is described later with and .

The initial security level determination module may determine the reliability of each portion of the processing target divided by the data division module . The reliability is determined for each portion if the whole processing target is high reliability the reliability of a portion may be lower than that of the whole processing target and processing can also be performed for each portion.

The service cooperation module is connected to the input output interface the initial security level determination module the data quality adjustment module the data division module the data integration module the security level management module the Web service providing apparatus A and the Web service providing apparatus B. If the security level management module determines that the processing main body can perform processing the processing target the service cooperation module requests the Web service of the processing main body to perform processing of the processing target. For example more specifically Web service having reliability more than the reliability required by the processing target is used for perform processing. The service cooperation module passes the reliability determined by the initial security level determination module to the security level management module . The service cooperation module accepts operation of the user from the input output interface and passes the operation to the security level management module as required. The service cooperation module presents a service menu of the processing result and items etc. to the display of the input output interface . The service cooperation module passes the processing target or a portion of the processing target to the data quality adjustment module the data division module and the data integration module based on a command from the security level management module and passes the processing result to the security level management module or the Web service. For example the service cooperation module requests the Web service to perform processing for the processing target changed by the data quality adjustment module .

As Web service request processing for example specifically the processing target and a processing parameter is transmitted and received to and from each Web service in accordance with the order of cooperation processing in accordance with service cooperation information. The service cooperation information is information required for performing cooperation processing and at least has information of the names and the order of Web services required processing parameters etc.

The security level management module is connected to the service cooperation module makes a comparison between the reliability determined by the initial security level determination module and the reliability of the processing main body and determines whether or not the processing main body can be caused to perform the processing target. The processing main body as the determination target may be one processing main body for performing next processing in cooperation processing or may be a plurality of processing main bodies for performing cooperation processing as one body.

When a plurality of processing main bodies perform a sequence of processing before each processing main body performs processing the security level management module may determine whether or not the processing main body can be caused to perform the processing target. The determination is made before each processing main body performs processing. This means that the processing main body as the determination target is one processing main body for performing next processing in cooperation processing. Therefore the number of determination times is as many as the number of processing main bodies in cooperation processing and determination and processing are repeated.

When a plurality of processing main bodies perform a sequence of processing before the processing main bodies perform the sequence of processing the security level management module may determine whether or not the processing main bodies can be caused to perform the processing target. The determination is made before the sequence of processing is performed before processing by the first processing main body in cooperation processing is performed each processing main body performs processing. This means that the processing main bodies as the determination target are processing main bodies for performing cooperation processing as one body. Therefore the number of determination times is only one and after determination is made the sequence of processing is performed.

If the security level management module determines that there is no processing main body that can process the processing target the security level management module may determine whether or not a processing main body stored in a service menu correspondence table corresponding to the item selected based on operation of the user is caused to process the processing target.

The security level management module also holds the reliability of the processing target changes the reliability of the processing target in response to the processing description according to a security level change table etc.

The data quality adjustment module is connected to the service cooperation module and receives the processing target from the service cooperation module . If the security level management module determines that the processing target cannot be processed the data quality adjustment module changes the processing target so as to change the reliability of the processing target. The data quality adjustment module passes the processing result changed processing target and reliability after the processing target is changed to the service cooperation module . For example a change is made in the direction of degrading the quality of the processing target. More specifically if the processing target is an image the resolution is set to low resolution reduced to degrade the image quality noise is added a color image is changed to a monochrome image mosaic processing is performed if the processing target contains an information image the information image is erased etc. The image information refers to a code created systematically to represent electronic data in a machine readable mode specifically a one dimensional bar code a two dimensional code etc. exists. For example as the two dimensional code QR code registered trademark Quick Response code etc. exists.

The data quality adjustment module changes a portion of the processing target so as to change the reliability of the portion of the processing target divided by the data division module . A change is made in the direction of degrading the quality conforming to the type of processing target portion for example an image text a pattern etc. . A change is made for each portion and the portion may be deleted. If the portion is deleted the reliability of the portion does not exist equal to the lowest level .

The data division module is connected to the service cooperation module and divides the processing target. For example for each type of processing target portion the processing target is divided into portions. For example if the processing target is a combination of an image text a pattern etc. the processing target is divided for each type. If the processing target is an image document and has a structure a structure analysis may be made and the processing target may be divided into portions. As the structure analysis image processing is performed for the image portion in a document the document is divided into portions of an image text a pattern etc. and further the text portion is divided into a title paragraphs etc. and the pattern portion is divided into a table a pattern etc.

If processing is performed by the data division module the initial security level determination module the data quality adjustment module the security level management module and the service cooperation module perform processing the portions into which the processing target is divided by the data division module as the processing target.

If the security level management module determines that processing cannot be performed the data division module may divide the processing target.

The data integration module is connected to the service cooperation module and integrates processed portion to form a processing target. It passes the integration result to the service cooperation module . That is the data integration module integrates the processing result after processing is performed by Web service for the portions into which the processing target is divided by the data division module to form a processing target. In this case if the security level management module determines that processing cannot be performed the service cooperation module may cause the data division module to divide the processing target into portions and may cause the Web service to process the portions into which the processing target is divided and the data integration module may integrate them to form a processing target.

If the security level management module determines that processing cannot be performed the service cooperation module may cause the data division module to divide the processing target into portions and may cause the data quality adjustment module to change the portions of the processing target so as to change the reliability for each of the portions into which the processing target is divided and degrade the reliability of the whole processing target until the processing target can be processed and then may cause the data integration module to integrate them to form a processing target and may cause the Web service to process the processing target.

The service relevant table storage module stores a service compatibility table and the service menu correspondence table .

The service compatibility table stores different processing main bodies corresponding to the processing main body. For example it stores a combination of the processing main body and different processing main bodies required for performing equivalent processing to processing performed by the processing main body also the case of one processing main body is also contained in correspondence with each other. Specifically a service compatibility table illustrated in exists. is a schematic representation to show a data structure example of the service compatibility table . The service compatibility table has a default Web service URL column a processing parameter column a compatible Web service URL column and a processing parameter column . That is the service compatibility table stores a pair of a different Web service compatible Web service URL column and a parameter processing parameter column for performing processing equivalent to compatible with processing performed by a pair of Web service default Web service URL column and a parameter required for the Web service to perform processing processing parameter column in correspondence with each other. To perform equivalent processing in cooperation more than one pair of the different Web service compatible Web service URL column and the parameter processing parameter column is used. For example http 123.45.78.1 service on the first row in the default Web service URL column has Skew true in the processing parameter column as a parameter and as services for performing equivalent processing to the processing http 23.46.111.4 service http 22.33.44.55 skew and http 99.88.7.66 service2 in the compatible Web service URL column perform processing in sequence. The parameters in the processing parameter column corresponds to each processing.

The default Web service URL column stores URL Uniform Resource Locator for providing standard Web service.

The processing parameter column stores a parameter required for the Web service to perform processing.

The compatible Web service URL column stores the URL of each Web service for performing equivalent processing to the Web service in the default Web service URL column .

The processing parameter column stores parameters required for the Web services in the compatible Web service URL column to perform processing.

More than one pair of the compatible Web service URL column and the processing parameter column may exist for the pair of the default Web service URL column and the processing parameter column . That is if cooperation processing is required for performing processing equivalent to the Web service in the pair of the default Web service URL column and the processing parameter column the URLs and the parameters for providing a plurality of Web services are stored.

The security level management module etc. searches the service compatibility table for the equivalent Web service pair as a value with the Web service as a key.

The service menu correspondence table stores an item and a processing main body corresponding thereto. For example it stores an item that can be selected by the user and the processing main body corresponding to the item the number of processing main bodies may be one or may be a combination of processing main bodies for performing cooperation processing in correspondence with each other. Specifically a service menu correspondence table illustrated in exists. is a schematic representation to show a data structure example of the service menu correspondence table .

The service menu correspondence table has a service menu column a processing parameter column and a service cooperation information column . This means that the service menu correspondence table stores information required for indicating processing for the user .

The service menu column stores the name item of a service menu that the input output interface presents the user on the display etc.

The service cooperation information column stores Web services for providing service the number of Web services may be one . Each URL for providing Web service and the parameter required for the processing are paired and in cooperation processing the pairs are stored in the processing order.

The security level management module etc. searches the service menu correspondence table for the Web service set for providing the service as a value with the service menu as a key.

The service providing apparatus uses the service menu correspondence table for the user of the end user and the service menu correspondence table is provided as an option and may be omitted.

The reliability and security level relevant table storage module records a Web service reliability table and a security level change table .

The Web service reliability table is a correspondence table between the processing main body and security. Specifically a Web service reliability table illustrated in exists. is a schematic representation to show a data structure example of the Web service reliability table . The Web service reliability table has a Web service URL column and a reliability column . This means that the Web service reliability table represents the correspondence between the URL of each Web service and the reliability of the Web service. The Web service reliability table represents the correspondence between the Web service and the security level that can be allowed as the processing service by the Web service. This means that the table indicates the processing target at the security level equal to or less than the reliability corresponding to the Web service.

The security level management module etc. searches the Web service reliability table for the reliability of the Web service as a value with the service menu as a key.

As the numeric value of the reliability the digit following the letter C is smaller processing with higher reliability can be performed. As the numeric value of the security level the digit following the letter S is smaller processing with higher reliability is required. For example the Web service with reliability Si can apply to the processing target at higher security level than the Web service with reliability S. For example if the reliability of Web service is lower than the security level of the processing target the reliability of Web service is insufficient and the Web service cannot process the processing target. If a positive value is added as the change degree of the security level the security level is made higher for example if change degree 1 is added to the security level S the security level becomes S. Conversely if a negative value is added as the change degree of the security level the security level is made lower for example if change degree 1 is added to the security level S the security level becomes S.

The reliability of each Web service is previously determined using criteria as to whether or not the service is intra company service whether or not the service is de facto standard service whether or not information security measures are taken etc. For example the administrator may previously determine the reliability or the reliability may be set according to whether or not the above described condition is included. More specifically the intra service is set to higher reliability than extra company service the de facto standard service is set to higher reliability than other services and if information security measures are taken the service is set to higher reliability than the service for which information security measures are not taken.

The URL of Web service may be provided for each Web service or may be provided for each domain by assuming that the reliability degrees of Web services belonging to the domain are the same.

The security level change table is a table describing how the reliability required by the processing target is changed by performing one processing. Specifically a security level change table illustrated in exists. is a schematic representation to show a data structure example of the security level change table . The security level change table has a Web service URL column a processing parameter column and a change degree column . That is a combination of the URL of Web service and a given processing parameter is the processing description and the change degree of the security level according to each processing description namely how the security level of the processing target changes by the processing is indicated.

The processing parameter column stores parameters given to the Web services in the Web service URL column .

The change degree column stores each value for changing the security level of the processing target when each Web service in the Web service URL column performs processing with the parameter in the processing parameter column .

For example the change degree of skew correction processing of processing of improving the quality service on the first row of the security level change table is plus and the change degree of mosaic processing of processing of degrading the quality service on the third row of the security level change table is minus . For example if the processing target is an image the change degree is previously determined using criteria as to whether or not extraction of metadata and recognition of an image object are facilitated etc. For example the administrator may previously determine the change degree or the change degree may be set according to whether or not the above described criteria are included. More specifically if extraction of metadata etc. is facilitated the change degree is set to a plus high value.

In a system assuming no change of the security level for each processing according to each Web service namely the change degree is 0 in all Web services the security level change table is not required.

The Web service providing apparatus has Web services A A B etc. . For example it is a program for performing service for performing actual processing provided by SOAP Simple Object Access Protocol REST REpresentational State Transfer etc. or is an information processing apparatus for executing the program.

Next an outline of service processing examples when the exemplary embodiment is realized is shown using .

The user requests the service providing apparatus to perform service processing in cooperation of services. It is assumed that the initial security level of a document of the processing target is determined when processing is started. It is assumed that the security level described in the following description and processing flows is given to the processing target and the reliability is given to service.

The service providing apparatus can perform processing using show through removal service C with reliability Cl skew correction service D with reliability C A company sky blue correction service E with reliability C and B company face recognition service F with reliability C. The show through removal service C and the skew correction service D are intra company services and thus are set to high reliability. The A company sky blue correction service E and the B company face recognition service F are in other companies and thus are set to low reliability. The reliability of the Web services is set according to the Web service reliability table .

For example if the security level of the document of the processing target is S the reliability of each Web service is equal to or more than C C C C and thus processing according to any Web service is also possible.

In the example in the example of the document is shown as the document of the processing target. shows an example of handling text data as the processing target. As Web services morphological analysis service J with reliability C structuring processing service K with reliability C X company translation service X with reliability C and Y company PDF conversion service Y with reliability C exist. The security level of a document of the processing target is evaluated from the viewpoints of suiting for automatic processing and meaning because the document is text data. The security level S higher than the reliability C of the Y company PDF conversion service Y is set for the document . Therefore the security level management module determines that the Y company PDF conversion service Y cannot be caused to process the document .

The security level of structured XML eXtensible Markup Language document etc. is set higher than that of the document of text data of a natural language for management.

The case where the security level management module determines that Web services the B company face recognition service F and the Y company PDF conversion service Y cannot be caused to perform processing has been described. If the quality of the processing service lowers the user may want to perform processing. Then in the exemplary embodiment processing shown in an example in is performed.

Here it is assumed that the security level management module adopts services with low change degree for cooperation processing. In the example in the show through removal service C is selected in the show through removal service group CS skin color correction service G is selected in skin color correction service group GS face recognition service E is selected in face recognition service group FS. For example assuming that the security level of a document before processing is S the document becomes a document whose security level is S by performing processing according to the show through removal service C and next the document becomes a document whose security level is S by performing processing according to the skin color correction service G . The security level management module determines that the show through removal service C can be caused to process the document and determines that the skin color correction service G can be caused to process the document .

Next service must be selected out of the face recognition service group FS but service whose reliability is equal to or more than C does not exist. Therefore the security level management module determines that the face recognition service E or the face recognition service E cannot be caused to process the document .

Then in a first exemplary embodiment processing as shown in an example in is performed. That is in the first exemplary embodiment cooperation processing is performed and in processing in which service satisfying the reliability that can be processed is not found the data quality adjustment module performs processing of lowering the security level of the processing target data to the level at which the processing can be executed. is a schematic representation to show a service processing example when the exemplary embodiment is realized. Processing to the skin color correction service G in is equal to the processing to the skin color correction service G in . However to clarify distinction between the processing targets the reference numeral of the document is document rather than document . The security level of a document is S.

If the security level management module determines that the face recognition service E cannot be caused to process the document the data quality adjustment module changes the document so as to lower the security level of the document namely lower the quality of the document to generate a document with security level S. For example processing of noise addition etc. is performed. Accordingly the security level management module determines that the face recognition service E can be caused to process the document .

In a second exemplary embodiment processing as shown in an example in is performed. That is in the second exemplary embodiment the initial security level at which whole processing according to cooperation processing is possible is found and the data quality adjustment module adjusts the processing target to the quality corresponding to the found initial security level. is a schematic representation to show a service processing example when the exemplary embodiment is realized. Cooperation processing is equal to that illustrated in . However to clarify distinction between the processing targets the reference numeral of the document is document rather than document . The security level of the document is S.

The case where the subtraction value of the change degree is applied in 2 described above will be discussed. is a schematic representation to show an example of applying the subtraction value of the change degree.

The processing at the preceding stage is the skin color correction service group GS and the security level of the processing target before processing by the skin color correction service group GS is found.

For example when the reference security level accepted by processing at the following stage is S if the skin color correction service G with the lowest change degree in the skin color correction service group GS is selected and a comparison is made between the value S S resulting from subtracting the change degree 1 and the security level S corresponding to the reliability C of the skin color correction service G the subtraction value S is lower and thus is adopted as the reference security level.

The case where the reliability correspondence level is applied in 2 described above will be discussed. is a schematic representation to show an example of applying the reliability correspondence level. As with the case in the processing at the preceding stage is the skin color correction service group GS and the security level of the processing target before processing by the skin color correction service group GS is found. However reliability differs.

For example when the reference security level accepted by processing at the following stage is S if the skin color correction service G with the lowest change degree in the skin color correction service group GS is selected and a comparison is made between the value S S resulting from subtracting the change degree 1 and the security level S corresponding to the reliability C of the skin color correction service G the security level S corresponding to the reliability is lower and thus is adopted as the reference security level. This means that the skin color correction service G with reliability C cannot process processing target at the security level of the subtraction value S .

In third and fourth exemplary embodiments processing as shown in an example in is performed. is a schematic representation to show a service processing example when the exemplary embodiment is realized. They are executed in combination with the first exemplary embodiment or the second exemplary embodiment. This means that processing by the data division module the data integration module is added.

The processing target is divided into parts and processing is performed for each division data at a lower security level than the original security level. For example if the processing target is a curriculum vitae it is divided into a face photo a part of personal information etc. It is general that the security level of each division data piece is lower than that of complete information data namely original processing target . The target whose quality is to be degraded can be limited to a portion at a high security level.

For example in the data division module divides a document . In the example the data division module divides the document into a division document a division document a division document etc. Although the security level of the document is S the security level of the division document becomes S that of the division document becomes S and that of the division document becomes S.

Then the service cooperation module performs cooperation processing for each division document etc. After each processing terminates or after the cooperation processing terminates the data integration module integrates the processing results of portions to generate the final processing result. The data quality adjustment module may change portions of the processing target so as to change the reliability of the portions of the processing target divided by the data division module . Processing of the data quality adjustment module etc. is equal to that of the first or second exemplary embodiment. If the security level management module determines that processing for the document cannot be performed the data division module may perform division processing.

The processing outline of the first to fourth exemplary embodiments has been described. Next specific processing examples of the exemplary embodiments will be discussed.

Service cooperation information order and combination of used Web services and parameter specified for each Web service is specified from other than a service providing apparatus . Before processing according to each Web service is performed whether or not the Web service is Web service with reliability not satisfying the security level if compatible Web service is used is determined. If the Web service does not satisfy the security level the quality of the processing target is lowered to lower the security level of the processing target.

At step S the service cooperation module accepts service cooperation information and the processing target hereinafter the processing target is also called processing data in response to operation of the user. The processing data and the service cooperation information are held in the service cooperation module . Web services W to Wn nth Web service is described as Wn are caused to operate and the specification parameter of each service is Pi.

At step S the initial security level determination module determines the security level to be S. Any of initial security level determination flows illustrated in is used. This topic is described later.

At step S the service cooperation module causes service Wi to execute processing. Processing flow of individual service illustrated in is used. This topic is described later. Processing flow is used under the conditions of Wi Pi and S.

In a system in which the security level does not vary for each processing according to each Web service at step S processing flow of individual service illustrated in is used in place of processing flow of individual service.

At step S the service cooperation module determines whether or not i n. If i n the processing is terminated step S otherwise the process goes to step S.

Flowcharts illustrated in are processing at step S in the flowchart illustrated in . The initial security level determination module performs the processing and the security level management module stores the security level determined at the termination time.

At step S the initial security level determination module extracts the security level given to the processing data and applies it as it is.

At step S the resolution of the processing data is extracted and is set to R. At security level Si i 1 to N of N levels the threshold value of the resolution assigned to each security level is Ri i 1 to N 1 . As the relationship between Ri and Si the higher the resolution the higher the security level.

At step S whether or not R Ri is determined. If R Ri the process goes to step S otherwise the process goes to step S.

At step S the security level of the processing data is determined to be Si. Then the processing terminates step S .

At step S whether or not the variable i is equal to N 1 is determined. If they equal the process goes to step S otherwise the process goes to step S.

At step S object recognition is performed for an image the type of object contained in the image text area pattern area photo area etc. and if a text area or a face image is contained the security level is set higher than the case where it is not contained.

At step S security level is set to S Web service is set to W and service specification parameter is set to P and then the processing is started.

At step S the security level management module acquires reliability C of Web service W from a Web service reliability table .

At step S the security level management module makes a comparison between the reliability C of the Web service W and security level S of processing data and whether or not C

At step S the service cooperation module transmits P and the processing data to the Web service W and requests the Web service W to perform processing.

At step S the service cooperation module determines whether or not the processing at step S ends in success. If the processing ends in success the process goes to step S otherwise the process goes to the step S.

At step S the security level management module acquires change degree S corresponding change degree column in security level change table according to W and P Wi and Pi namely a pair of Web service URL column and processing parameter column in the security level change table from a security level change table .

At step S the security level management module assigns S S to a variable S and terminates the processing step S .

At step S the security level management module acquires Wi and Pi i 1 to n equal to W and P from the service compatibility table acquires reliability Ci of each Wi from the Web service reliability table and sorts the order of i in the descending order of Ci.

At step S the security level management module determines whether or not Wi exists. If Wi exists the process goes to step S otherwise the process goes to step S.

At step S the service cooperation module starts at the position of start B service W of processing flow at the data quality adjustment time illustrated in .

At step S the service cooperation module starts processing flow at the data quality adjustment time illustrated in at the position of start A service W .

At step S the service cooperation module transmits Pi and the processing data to W and requests W to perform processing.

At step S the service cooperation module determines whether or not the processing at step S ends in success. If the processing ends in success the process goes to step S otherwise the process goes to step S.

At step S the service cooperation module determines whether or not i n. If i n the process goes to step S otherwise the process goes to S.

At step S the service cooperation module starts processing flow at the data quality adjustment time illustrated in at the position of start A service W .

At step S the service cooperation module assigns i 1 to the variable i and the process returns to step S.

At step S the security level management module extracts service Wj j 1 to m with the highest reliability from W and equal service Wi i 1 to n to W.

At step S the security level management module selects Wx with the lowest change degree of the security level in service Wj j 1 to m and the process goes to step S.

At step S the data quality adjustment module adjusts processing data so that S becomes equal to the reliability C of Wx namely S becomes the same as or less than the value of C. 

At step S the service cooperation module makes a request for processing with Wx and its processing parameter.

At step S the service cooperation module whether or not the processing at step S ends in success. If the processing ends in success the process goes to step S otherwise error notification is provided step S .

At step S the security level management module acquires change degree S according to Wx and Px from the security level change table .

At step S the security level management module assigns S S to the variable S and terminates the processing step S .

At step S the security level is set to S the Web service is set to W service specification parameter is set to P and processing is started.

At step S the security level management module acquires the reliability C of W from the Web service reliability table .

At step S the service cooperation module transmits P and processing data to W and requests W to perform processing.

At step S the service cooperation module determines whether or not the processing at step S ends in success. If the processing ends in success the process goes to S otherwise the process goes to step S.

At step S the service cooperation module receives the processing result and terminates the processing step S .

At step S the security level management module acquires Wi and Pi i 1 to n equal to W and P from the service compatibility table acquires reliability Ci of each Wi from the Web service reliability table and sorts the order of i in the descending order of Ci.

At step S the security level management module determines whether or not Wi exists. If Wi exists the process goes to step S otherwise the process goes to step S.

At step S the service cooperation module starts at the position of start B service W of processing flow at the data quality adjustment time illustrated in .

At step S the service cooperation module starts at the position of start A service W of processing flow at the data quality adjustment time illustrated in .

At step S the service cooperation module transmits Pi and the processing data to W and requests W to perform processing.

At step S the service cooperation module determines whether or not the processing ends in success. If the processing ends in success the process goes to step S otherwise the process goes to step S.

At step S the service cooperation module determines whether or not i n. If i n the process goes to step S otherwise the process goes to S.

At step S the service cooperation module starts at the position of start A service W of processing flow at the data quality adjustment time illustrated in .

At step S the service cooperation module assigns i 1 to the variable i and the process returns to step S.

At step S service Wx with the highest reliability is selected from W and equal service Wi i 1 to n to W and the process goes to S.

At step S the data quality adjustment module adjusts data so that S becomes equal to the reliability C of Wx namely S becomes the same as or less than the value of C. 

At step S the service cooperation module makes a request for processing with Wx and its processing parameter.

At step S the service cooperation module whether or not the processing at step S ends in success. If the processing ends in success the process goes to step S otherwise error notification is provided step S . The notification is to notify the user that an error occurs through the input output interface .

At step S the service cooperation module receives the processing result and the processing is terminated S .

Service cooperation information is specified from other than a service providing apparatus . Before cooperation processing is performed whether or not the Web service is Web service with reliability not satisfying the security level if compatible Web service is used is determined. If the Web service does not satisfy the security level the quality of the processing target is lowered to lower the security level of the processing target.

At step S the service cooperation module accepts service cooperation information and processing data in response to operation of the user. The processing data and the service cooperation information are held in the service cooperation module .

At step S the initial security level determination module determines the security level to be S. Any of the initial security level determination flows illustrated in is used.

At step S the security level management module executes security determination from the service cooperation information and S. A security determination flow of service cooperation illustrated in is used.

At step S the security level management module determines whether or not the processing result at step S is OK. If the processing result is OK the process goes to step S otherwise the process goes to step S.

At step S the data quality adjustment module adjusts the processing data and changes the initial security level. An initial security level adjustment flow illustrated in is used.

At step S the service cooperation module executes a service cooperation processing flow illustrated in .

At step S the initial security level is set to Sx W to Wn cooperate for Web service the specification parameter of each service is set to Pi and the processing is started.

At step S service Wi whose reliability becomes insufficient security level S and failure are reported and the processing is terminated step S . After this the determination at step S in the processing flow illustrated in is No and the process goes to step S.

At step S whether or not i n is determined. If i n the process goes to S otherwise the process goes to step S.

At step S success is reported and the processing is terminated step S . After this the determination at step S in the processing flow illustrated in is Yes and the process goes to step S.

At step the change degree at the Wi Pi time is acquired from a security level change table and is added to S.

At step S the security level management module finds the highest reliability C of the reliability that the service used at the N the number of cooperation services N th time has. The value of the reliability C is assigned to the security level Sx.

At step S the initial security level determination module determines the initial security level that can be processed to be Sx.

At step S the data quality adjustment module adjusts the security level of the processing data so as to become Sx.

At step S the security level management module finds the minimum value Smin of the change degree of the security level among the change degrees of the security levels corresponding to the i th service and finds the highest reliability Ca in service with minimum value Smin. The value of Sx Smin is assigned to the security level Sx.

At step S the security level management module assigns Ca to the variable Sx and the process goes to step S.

At step S Web services W to Wn are caused to cooperate the specification parameter of each service is set to Pi and the processing is started.

At step S the service Wi is caused to execute the processing. Processing flow of individual service illustrated in is used. Processing flow is used under conditions of Wi Pi S.

At step S whether or not i n is determined. If i n the processing is terminated step S otherwise the process goes to step S.

At step S the Web service is set to W service specification parameter is set to P and processing is started.

At step S the security level management module acquires Wi and Pi i 1 to n equal to W and P from the service compatibility table and extracts service Wj j 1 m with the minimum security level change degree from W Wi.

At step S the security level management module extracts service Wx having the highest reliability from service Wj j 1 to m .

At step S the service cooperation module transmits Px and processing data to Wx requests Wx to perform processing and receives the result and the processing is terminated step S .

The third exemplary embodiment is provided by adding division processing of the processing target to the first exemplary embodiment. The fourth exemplary embodiment is provided by adding division processing of the processing target to the second exemplary embodiment.

At step S the service cooperation module accepts service cooperation information and processing data in response to operation of the user. The processing data and the service cooperation information are held in the service cooperation module . Web services W to Wn are caused to cooperate and the specification parameter of each service is set to Pi.

At step S the data division module divides the processing data into units that can be processed. The division data piece is set to Ij j 1 to m .

At step S the initial security level determination module determines the security level to be S about the data Ij. Any of the initial security level determination flows illustrated in is used.

At step S the service cooperation module causes the service Wi to execute processing about the division data piece Ij. Processing flow of individual service illustrated in is used. Processing flow is used under the conditions of Wi Pi and S.

In a system in which the security level does not vary for each processing according to each Web service at step S processing flow of individual service illustrated in is used in place of processing flow of individual service.

At step S the service cooperation module determines whether or not i n. If i n the process goes to step S otherwise the process goes to step S.

At step S the service cooperation module determines whether or not j m. If j m the process goes to step S otherwise the process goes to step S.

At step S the data integration module integrates the processing results O to Om into one processing data.

At step S the service cooperation module accepts service cooperation information and processing data in response to operation of the user. The processing data and the service cooperation information are held in the service cooperation module . Web services W to Wn are caused to cooperate and the specification parameter of each service is set to Pi.

At step S the data division module divides the processing data into units that can be processed. The division data piece is set to Ij j 1 to m .

At step S the initial security level determination module determines the security level to be S about the data Ij. Any of the initial security level determination flows illustrated in is used.

At step S the security level management module executes security determination from the service cooperation information and S. The security determination flow of service cooperation illustrated in is used.

At step S the service cooperation module determines whether or not the processing result at step S is OK is determined. If the processing result is OK the process goes to step S otherwise the process goes to S.

At step S the data quality adjustment module adjusts the processing data and changes the initial security level. The initial security level adjustment flow illustrated in is used.

At step S the service cooperation module holds processing result Oj based on the service cooperation processing flow.

At step S the service cooperation module determines whether or not j m. If j m the process goes to step S otherwise the process goes to step S.

At step S the data integration module integrates the processing results O to Om into one processing data.

A hardware configuration example of the image processing apparatus of the exemplary embodiment will be discussed with reference to . The configuration shown in includes a personal computer PC etc. for example. A hardware configuration example including a data read section such as a scanner and a data output section such as a printer is shown.

A CPU Central Processing Unit is a control section for executing processing conforming to computer programs describing execution sequences of various modules described above in the exemplary embodiments namely the initial security level determination module the data quality adjustment module the data division module the data integration module the security level management module the service cooperation module etc.

ROM Read Only Memory stores programs operation parameters etc. used by the CPU . RAM Random Access Memory stores programs used in execution of the CPU parameters changing appropriately in the execution of the CPU and the like. They are connected by a host bus implemented as a CPU bus etc.

The host bus is connected to an external bus such as a PCI Peripheral Component Interconnect Interface bus through a bridge .

A keyboard and a pointing device such as a mouse are input devices operated by the user. A display is a liquid crystal display a CRT Cathode Ray Tube or the like for displaying various pieces of information as text and image information.

An HDD Hard Disk Drive contains a hard disk and drives the hard disk for recording or playing back a program and information executed by the CPU . The hard disk stores a document of the processing target a document of the processing result of the data quality adjustment module etc. the service compatibility table the service menu correspondence table the Web service reliability table the security level change table etc. Further the hard disk stores various computer programs such as other various data processing programs.

A drive reads data or a program recorded on a mounted removable record medium such as a magnetic disk an optical disk a magneto optical disk or semiconductor memory and supplies the data or the program to the RAM connected through an interface the external bus the bridge and the host bus . The removable record medium can also be used as a data record area like a hard disk.

A connection port is a port for connecting an external connection device and has a connection section of a USB IEEE 1394 etc. The connection port is connected to the CPU etc. through the interface the external bus the bridge the host bus etc. A communication section is connected to a network for executing data communication processing with an external system. A data read section is for example a scanner and executes document read processing. A data output section is for example a printer and executes document data output processing.

The hardware configuration of the image processing apparatus shown in shows one configuration example and the configuration of each of the exemplary embodiments is not limited to the configuration shown in and may be a configuration that can execute the modules described in the exemplary embodiments. For example some modules may be implemented as dedicated hardware for example Application Specific Integrated Circuit ASIC etc. some modules may exist in an external system and may be connected through a communication line and further a plurality of systems shown in may be connected by a communication line and may cooperate with each other. The system may be built in a copier a fax a scanner a printer a multiple function apparatus an image processing apparatus having the functions of any two or more of a scanner a printer a copier a fax etc. or the like.

The various exemplary embodiments described above may be combined for example a module in one exemplary embodiment is applied to another exemplary embodiment a module in one exemplary embodiment is replaced with another module in another exemplary embodiment etc. . Particularly to deal with the case where Web service is added during processing the case where the reliability is changed during processing etc. the first and second exemplary embodiments may be combined. The arts described in Background Arts may be adopted as the processing substance of each module.

In the description of the exemplary embodiments in comparison with a predetermined value equal to or more than equal to or less than more than and less than may be more than less than equal to or more than and equal to or less than respectively unless a contradiction occurs in the combination.

The described program may be provided as it is stored on a record medium or the program may be provided by communication means. In this case for example the described program may be grasped as the invention of a computer readable record medium recording a program. 

The expression computer readable record medium recording a program is used to mean a record medium that can be read by a computer where a program is recorded used to install and execute the program to distribute the program etc.

The record media include DVD R DVD RW DVD RAM etc. of digital versatile disk DVD and standard laid down in DVD Forum DVD R DVD RW etc. of standard laid down in DVD RW read only memory CD ROM CD recordable CD R CD rewritable CD RW etc. of compact disk CD Blue ray Disc registered trademark magneto optical disk MO flexible disk FD magnetic tape hard disk read only memory ROM electrically erasable and programmable read only memory EEPROM flash memory random access memory RAM etc. for example.

The above described program or a part thereof may be recorded in any of the above described record media for retention distribution etc. The above described program or a part thereof may be transmitted by communications using a transmission medium such as a wired network used with a local area network a metropolitan area network MAN a wide area network WAN the Internet an intranet an extranet etc. or a wireless communication network or a combination thereof etc. for example and may be carried over a carrier wave.

Further the above described program may be a part of another program or may be recorded in a record medium together with a different program. It may be recorded as it is divided into a plurality of record media. It may be recorded in any mode if it can be restored such as compression or encryption.

The foregoing description of the exemplary embodiments of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Obviously many modifications and variations will be apparent to practitioners skilled in the art. The embodiments were chosen and described in order to best explain the principles of the invention and its practical applications thereby enabling others skilled in the art to understand the invention for various embodiments and with the various modifications as are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalents.

