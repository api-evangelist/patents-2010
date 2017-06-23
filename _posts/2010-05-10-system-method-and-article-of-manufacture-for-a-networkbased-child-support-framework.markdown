---

title: System, method and article of manufacture for a network-based child support framework
abstract: A system, method and article of manufacture are provided for providing a network-based child financial support framework. First, a database is maintained including information on a received financial support payment utilizing a network. Further, general information is provided relating to the financial support payment utilizing the network. The calculation of a proper amount of the financial support payment may also be allowed based on a profile a user. Still yet, a history associated with the financial support payment is displayed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08065159&OS=08065159&RS=08065159
owner: Accenture Global Services Limited
number: 08065159
owner_city: Dublin
owner_country: IE
publication_date: 20100510
---
This application is a continuation of U.S. patent application Ser. No. 09 560 665 filed Apr. 27 2000 now U.S. Pat. No. 7 716 059 the entire contents of which are incorporated herein by reference.

The present invention relates to databases and more particularly to databases for tracking parental financial support.

Currently child support systems rely heavily on telephonic or in person communications between custodial and non custodial parents and state agency staff. Even simple questions about such things as status of support payments have to be answered by talking to a staff member with dedicated computer terminals connected directly to intra agency computer systems resulting in the custodial parents having very little active participation in the management of their cases.

Parents and state staff members also rely on mail to communicate. However correspondence sent through the postal system is slow and may get lost. Further postage costs place a heavy burden on already strained budgets.

What is needed is a system that allows parents involved in a child support case to access information immediately without speaking directly to a state agency staff member or waiting for correspondence.

A system method and article of manufacture are provided for providing a network based child financial support framework. First a database is maintained including information on a received financial support payment utilizing a network. Further general information is provided relating to the financial support payment utilizing the network. The calculation of a proper amount of the financial support payment may also be allowed based on a profile a user. Still yet a history associated with the financial support payment is displayed.

In one embodiment of the present invention the profile may include data such as income number of children basic support insurance premium child care cost and or additional expenses. The history may include a date an amount received on the date an amount retained of the amount received and a disbursement of the amount received to the custodial parent.

In yet another embodiment of the present invention a plurality of frequently asked questions may be presented relating to the financial support payment.

The present invention provides an eChild Support Enforcement intention based interactive web application that allows parents and employers to exchange information that previously could only be handled on the phone or in person with state agency staff. Using an intention based question answer based approach eChild Support Enforcement lets case participants inquire about the status of their support cases. Thus custodial and non custodial parents are allowed access to information which was previously only available to specially trained state agency staff using dedicated computer terminals connected directly to intra agency computer systems. The application actively engages custodial parents in the management of their cases. The eChild Support Enforcement application provides better methods and tools allowing the custodial parent and the case worker to share information.

A preferred embodiment is written using JAVA C and the C language and utilizes object oriented programming methodology. Object oriented programming OOP has become increasingly used to develop complex applications. As OOP moves toward the mainstream of software design and development various software solutions require adaptation to make use of the benefits of OOP. A need exists for these principles of OOP to be applied to a messaging interface of an electronic messaging system such that a set of OOP classes and objects for the messaging interface can be provided.

OOP is a process of developing computer software using objects including the steps of analyzing the problem designing the system and constructing the program. An object is a software package that contains both data and a collection of related structures and procedures. Since it contains both data and a collection of structures and procedures it can be visualized as a self sufficient component that does not require other additional structures procedures or data to perform its specific task. OOP therefore views a computer program as a collection of largely autonomous components called objects each of which is responsible for a specific task. This concept of packaging data structures and procedures together in one component or module is called encapsulation.

In general OOP components are reusable software modules which present an interface that conforms to an object model and which are accessed at run time through a component integration architecture. A component integration architecture is a set of architecture mechanisms which allow software modules in different process spaces to utilize each others capabilities or functions. This is generally done by assuming a common component object model on which to build the architecture. It is worthwhile to differentiate between an object and a class of objects at this point. An object is a single instance of the class of objects which is often just called a class. A class of objects can be viewed as a blueprint from which many objects can be formed.

OOP allows the programmer to create an object that is a part of another object. For example the object representing a piston engine is said to have a composition relationship with the object representing a piston. In reality a piston engine comprises a piston valves and many other components the fact that a piston is an element of a piston engine can be logically and semantically represented in OOP by two objects.

OOP also allows creation of an object that depends from another object. If there are two objects one representing a piston engine and the other representing a piston engine wherein the piston is made of ceramic then the relationship between the two objects is not that of composition. A ceramic piston engine does not make up a piston engine. Rather it is merely one kind of piston engine that has one more limitation than the piston engine its piston is made of ceramic. In this case the object representing the ceramic piston engine is called a derived object and it inherits all of the aspects of the object representing the piston engine and adds further limitation or detail to it. The object representing the ceramic piston engine depends from the object representing the piston engine. The relationship between these objects is called inheritance.

When the object or class representing the ceramic piston engine inherits all of the aspects of the objects representing the piston engine it inherits the thermal characteristics of a standard piston defined in the piston engine class. However the ceramic piston engine object overrides these ceramic specific thermal characteristics which are typically different from those associated with a metal piston. It skips over the original and uses new functions related to ceramic pistons. Different kinds of piston engines have different characteristics but may have the same underlying functions associated with it e.g. how many pistons in the engine ignition sequences lubrication etc. . To access each of these functions in any piston engine object a programmer would call the same functions with the same names but each type of piston engine may have different overriding implementations of functions behind the same name. This ability to hide different implementations of a function behind the same name is called polymorphism and it greatly simplifies communication among objects.

With the concepts of composition relationship encapsulation inheritance and polymorphism an object can represent just about anything in the real world. In fact one s logical perception of the reality is the only limit on determining the kinds of things that can become objects in object oriented software. Some typical categories are as follows 

With this enormous capability of an object to represent just about any logically separable matters OOP allows the software developer to design and implement a computer program that is a model of some aspects of reality whether that reality is a physical entity a process a system or a composition of matter. Since the object can represent anything the software developer can create an object which can be used as a component in a larger software project in the future.

If 90 of a new OOP software program consists of proven existing components made from preexisting reusable objects then only the remaining 10 of the new software project has to be written and tested from scratch. Since 90 already came from an inventory of extensively tested reusable objects the potential domain from which an error could originate is 10 of the program. As a result OOP enables software developers to build objects out of other previously built objects.

This process closely resembles complex machinery being built out of assemblies and sub assemblies. OOP technology therefore makes software engineering more like hardware engineering in that software is built from existing components which are available to the developer as objects. All this adds up to an improved quality of the software as well as an increased speed of its development.

Programming languages are beginning to fully support the OOP principles such as encapsulation inheritance polymorphism and composition relationship. With the advent of the C language many commercial software developers have embraced OOP. C is an OOP language that offers a fast machine executable code. Furthermore C is suitable for both commercial application and systems programming projects. For now C appears to be the most popular choice among many OOP programmers but there is a host of other OOP languages such as Smalltalk Common Lisp Object System CLOS and Eiffel. Additionally OOP capabilities are being added to more traditional popular computer programming languages such as Pascal.

Class libraries are very flexible. As programs grow more complex more programmers are forced to reinvent basic solutions to basic problems over and over again. A relatively new extension of the class library concept is to have a framework of class libraries. This framework is more complex and consists of significant collections of collaborating classes that capture both the small scale patterns and major mechanisms that implement the common requirements and design in a specific application domain. They were first developed to free application programmers from the chores involved in displaying menus windows dialog boxes and other standard user interface elements for personal computers.

Frameworks also represent a change in the way programmers think about the interaction between the code they write and code written by others. In the early days of procedural programming the programmer called libraries provided by the operating system to perform certain tasks but basically the program executed down the page from start to finish and the programmer was solely responsible for the flow of control. This was appropriate for printing out paychecks calculating a mathematical table or solving other problems with a program that executed in just one way.

The development of graphical user interfaces began to turn this procedural programming arrangement inside out. These interfaces allow the user rather than program logic to drive the program and decide when certain actions should be performed. Today most personal computer software accomplishes this by means of an event loop which monitors the mouse keyboard and other sources of external events and calls the appropriate parts of the programmer s code according to actions that the user performs. The programmer no longer determines the order in which events occur. Instead a program is divided into separate pieces that are called at unpredictable times and in an unpredictable order. By relinquishing control in this way to users the developer creates a program that is much easier to use. Nevertheless individual pieces of the program written by the developer still call libraries provided by the operating system to accomplish certain tasks and the programmer must still determine the flow of control within each piece after it s called by the event loop. Application code still sits on top of the system.

Even event loop programs require programmers to write a lot of code that should not need to be written separately for every application. The concept of an application framework carries the event loop concept further. Instead of dealing with all the nuts and bolts of constructing basic menus windows and dialog boxes and then making these things all work together programmers using application frameworks start with working application code and basic user interface elements in place. Subsequently they build from there by replacing some of the generic capabilities of the framework with the specific capabilities of the intended application.

Application frameworks reduce the total amount of code that a programmer has to write from scratch. However because the framework is really a generic application that displays windows supports copy and paste and so on the programmer can also relinquish control to a greater degree than event loop programs permit. The framework code takes care of almost all event handling and flow of control and the programmer s code is called only when the framework needs it e.g. to create or manipulate a proprietary data structure .

A programmer writing a framework program not only relinquishes control to the user as is also true for event loop programs but also relinquishes the detailed flow of control within the program to the framework. This approach allows the creation of more complex systems that work together in interesting ways as opposed to isolated programs having custom code being created over and over again for similar problems.

Thus as is explained above a framework basically is a collection of cooperating classes that make up a reusable design solution for a given problem domain. It typically includes objects that provide default behavior e.g. for menus and windows and programmers use it by inheriting some of that default behavior and overriding other behavior so that the framework calls application code at the appropriate times.

Thus through the development of frameworks for solutions to various problems and programming tasks significant reductions in the design and development effort for software can be achieved. A preferred embodiment of the invention utilizes HyperText Markup Language HTML to implement documents on the Internet together with a general purpose secure communication protocol for a transport medium between the client and the Newco. HTTP or other protocols could be readily substituted for HTML without undue experimentation. Information on these products is available in T. Berners Lee D. Connoly RFC 1866 Hypertext Markup Language 2.0 November 1995 and R. Fielding H Frystyk T. Berners Lee J. Gettys and J. C. Mogul Hypertext Transfer Protocol HTTP 1.1 HTTP Working Group Internet Draft May 2 1996 . HTML is a simple data format used to create hypertext documents that are portable from one platform to another. HTML documents are SGML documents with generic semantics that are appropriate for representing information from a wide range of domains. HTML has been in use by the World Wide Web global information initiative since 1990. HTML is an application of ISO Standard 8879 1986 Information Processing Text and Office Systems Standard Generalized Markup Language SGML .

To date Web development tools have been limited in their ability to create dynamic Web applications which span from client to server and interoperate with existing computing resources. Until recently HTML has been the dominant technology used in development of Web based solutions. However HTML has proven to be inadequate in the following areas 

With Java developers can create robust User Interface UI components. Custom widgets e.g. real time stock tickers animated icons etc. can be created and client side performance is improved. Unlike HTML Java supports the notion of client side validation offloading appropriate processing onto the client for improved performance. Dynamic real time Web pages can be created. Using the above mentioned custom UI components dynamic Web pages can also be created.

Sun s Java language has emerged as an industry recognized language for programming the Internet. Sun defines Java as a simple object oriented distributed interpreted robust secure architecture neutral portable high performance multithreaded dynamic buzzword compliant general purpose programming language. Java supports programming for the Internet in the form of platform independent Java applets. Java applets are small specialized applications that comply with Sun s Java Application Programming Interface API allowing developers to add interactive content to Web documents e.g. simple animations page adornments basic games etc. . Applets execute within a Java compatible browser e.g. Netscape Navigator by copying code from the server to client. From a language standpoint Java s core feature set is based on C . Sun s Java literature states that Java is basically C with extensions from Objective C for more dynamic method resolution. 

Another technology that provides similar function to JAVA is provided by Microsoft and ActiveX Technologies to give developers and Web designers wherewithal to build dynamic content for the Internet and personal computers. ActiveX includes tools for developing animation 3 D virtual reality video and other multimedia content. The tools use Internet standards work on multiple platforms and are being supported by over 100 companies. The group s building blocks are called ActiveX Controls small fast components that enable developers to embed parts of software in hypertext markup language HTML pages. ActiveX Controls work with a variety of programming languages including Microsoft Visual C Borland Delphi Microsoft Visual Basic programming system and in the future Microsoft s development tool for Java code named Jakarta. ActiveX Technologies also includes ActiveX Server Framework allowing developers to create server applications. One of ordinary skill in the art readily recognizes that ActiveX could be substituted for JAVA without undue experimentation to practice the invention.

In one embodiment of the present invention the user may be linked to another site on the network including information on financial support field offices. As an option the information may relate to services provided by a governmental financial support organization. Further the information may relate to an eligibility for the services provided by the governmental financial support organization or identify financial support violators.

In one embodiment of the present invention the date may include a date when the payment was received. Further the date may include a date when the payment was sent to the user. An amount of time required for the received financial support payment to be available for withdrawal may also be displayed. In another embodiment of the present invention the information may include a case number associated with the received financial support payment.

In an aspect of the invention the tracking information can take the form of a chart. In another aspect of the invention the tracking information can be selected from the group consisting of a date an amount received on the date an amount retained of the amount received and a disbursement of the amount received to the custodial parent. In still another aspect of the invention the network includes the Internet. In still yet another aspect of the invention the tracking information is displayed only after a user logs in.

In one embodiment of the present invention the data may be received by allowing a user to fill in a plurality of fields on a chart. Further a user may be permitted to change a profile thereof in response to the display of the calculated amount of child support due. Still yet the data may indicate whether a father or a mother is the custodial parent.

This section describes the general design for the 25 Most Wanted Page for an electronic Child Support Enforcement Web Application eCSE . This is achieved by providing an overview of the system s various infrastructure components and their interdependencies.

The eCSE 25 most wanted web page is designed to include the functionality required perform the following 

Data will be retrieved from the SQL7 Server through the ICBAM Architecture. The ICBAM Architecture was built using Microsoft Object Component Technologies COM .

Data will pass through the business logic using the page controller COM component to from the Active Server Pages.

Active server pages will be used to display the top 25 most wanted non Custodial parents who haven t pay their child support sorted from the highest outstanding balance to the lowest. Any errors encountered during the data retrieval will be documented in a server error log.

There are no user inputs required for the 25 Most Wanted Page. However when user clicks on the 25 Most Wanted Link from the side menu to access the page the page will retrieve the 25 Most Wanted data and display back to the user on the web page.

SQL7 Data Repository on Web Server . An established area on the State web server where all files to be used by the eCSE SQL7 data warehouse will be deposited.

Server Microsoft SQL7 Data Warehouse . A robust relational database containing tables with data necessary to encompass the functionality of the current State Child Support Enforcement system monthly process.

Client Web Browser Graphical User Interface . The client web based front end of the application in Hyper Text Markup Language HTML which a client user will use to enter new data from the client s web browser into the appropriate sql server tables and generate requested results back to the client web browser.

25 Most Wanted Active Server Page ASP . The client web based front end of the application in Hyper Text Markup Language HTML calls on the 25 Most Wanted Active Server Page to display a list back to the client browser of the top 25 non custodial parents who has the highest outstanding child support payments to date. The 25 Most Wanted active server page should contain the following 

25 Most Wanted Business Component . The 25 Most Wanted Business Component defines all of the public interfaces for the 25 most wanted business related components. It is responsible for all the data access to the SQL7 Server Database related to the 25 most wanted data. In addition the 25 Most Wanted business component will contain the following 

The output result will display a list of the top 25 non custodial parents who have the highest outstanding child support payments to date back to the client s web browser.

25 Most Wanted Page Controller . The 25 Most Wanted page controller is a Microsoft Transaction Server MTS component that will provide a standard way of transporting data to and from the 25 Most Wanted Active Server Page through dictionary objects. It implements business logic that would otherwise reside in the 25 most wanted active server page. It is the co ordinator between the interactions of the 25 Most Wanted ASP and the 25 Most Wanted Business Components. In addition the 25 Most Wanted Page Controller will interface with the Internet Information Server event handlers.

ICBAM Architecture Component . The Internet Component Based Architecture Model ICBAM component that will provide a the following common architecture services 

The architecture component has error handling routines that ensure data integrity when retrieving data.

Name of Absent Parent Date of Birth Last Known Address and the Amount Owed will be displayed from the 25 Most Wanted Active Server Page. The data is viewable online and printable.

This portion describes the general design for the Recent News on Case Display Page for the electronic Child Support Enforcement Web Application eCSE . This is achieved by providing an overview of the system s various infrastructure components and their interdependencies.

The eCSE Recent News on Case web page is designed to include the functionality required perform the following 

Custodial Parent will click the Recent News on Case link from the Home Page using a certified web browser.

Data will be retrieved from the SQL7 Server through the ICBAM Architecture. The ICBAM Architecture was built using Microsoft Object Component Technologies COM .

Data will pass through the business logic using the page controller COM component to from the Active Server Pages.

Active server pages will be used to display information the Recent News on Case as of current date. This includes any developments that occur throughout the child support process. Any errors encountered during the data retrieval will be documented in a server error log using the ICBAM Architecture.

There are no user inputs required for the Recent News on Case Page. However when Custodial Parent user clicks on the URL to access the page the page will retrieve the Recent News on Case data by the Case Number selected and display case news information back to the Custodial Parent user s web browser.

Social Security logon and password is required. Please see Logon Screen Security and Authentication general design for more details.

SQL7 Data Repository on Web Server . An established area on the web server where all files to be used by the eCSE SQL7 data warehouse will be deposited.

Server Microsoft SQL7 Data Warehouse . A robust relational database containing tables with data necessary to encompass the functionality of the current Child Support Enforcement system monthly process.

Client Web Browser Graphical User Interface . The client web based front end of the application in Hyper Text Markup Language HTML which a Custodial Parent client user will use to click on a Case Number link from the client s web browser to initiate querying the appropriate SQL server tables and generate requested results back to the client web browser.

Recent News on Case Active Server Page ASP . The client web based front end of the application in Hyper Text Markup Language HTML calls on the Recent News on Case Active Server Page to display back to the client browser the most recent information about the progress of a case. The Recent News on Case Active Server Page will contain the following 

Recent News on Case Business Component . The Recent News on Case Business Component defines all of the public interfaces for the Recent News on Case business related components. It is responsible for all the data access to the SQL7 Server Database related to the Recent News on Case data. In addition the Recent News on Case Display business component will contain the following 

Implementation of a declarative and or programmatic security if necessary. The output result will display a list of the top 25 non custodial parents who has the highest outstanding child support payments to date back to the client s web browser.

Recent News on Case Display Page Controller . The Recent News on Case Page Controller is a Microsoft Transaction Server MTS component that will provide a standard way of transporting data to and from the Recent News on Case Active Server Page through dictionary objects. It implements business logic that would otherwise will reside in the Recent News on Case Display active server page. It is the co ordinator between the interaction of the Recent News on Case Display ASP and the Recent News on Case Display Business Components. In addition the Recent News on Case Page Controller will interface with the Internet Information Server event handlers.

ICBAM Architecture Component . The Internet Component Based Architecture Model ICBAM component that will provide a the following common architecture services 

A list of recent case action events related to the case number followed by month date and year of the action will be displayed from the Recent News on Case Active Server Page. The said data will be viewable online and printable.

This portion describes the general design for the Amount Due For The Current Month display Page for the electronic Child Support Enforcement Web Application eCSE . This is achieved by providing an overview of the system s various infrastructure components and their interdependencies.

The eCSE Amount Due For The Current Month web page is designed to include the functionality required perform the following 

Custodial Parent will click the Amount Due For The Current Month link located in the main menu selection bar in the Custodial Parent Case Payment Information Page using a certified web browser.

Data will be retrieved from the SQL7 Server through the ICBAM Architecture. The ICBAM Architecture was built using Microsoft Object Component Technologies COM .

Data will pass through the business logic using the page controller COM component to from the Active Server Pages.

Active server pages will be used to display the Amount Due For The Current Month Information in a paragraph form. The data will display in the form of three paragraphs 

The first paragraph displays as of last case process date the amount that the non Custodial Parent owes the Custodial Parent the amount that has been paid to date and the total amount still owed to Custodial Parent.

The second paragraph displays the total of all past payments in arrears that the non Custodial Parent owed to the Custodial Parent and the scheduled payment that the non Custodial Parent owes the Custodial Parent.

Any errors encountered during the data retrieval will be documented in a server error log using the ICBAM Architecture.

There are no user inputs required for the Amount Due For The Current Month Web Page. However when the Custodial Parent logs on access the case payment information page and clicks on the Amount Due For The Current Month link the page will capture the following 

The active server page will retrieve the Amount Due For The Current Month data information formatted in three paragraphs back to the Custodial Parent user s web browser.

Social Security logon and password is required. Please see Logon Screen Security and Authentication general design document for more details.

SQL7 Data Repository on Web Server . An established area on the web server where all files to be used by the eCSE SQL7 data warehouse will be deposited.

Server Microsoft SQL7 Data Warehouse . A robust relational database containing tables with data necessary to encompass the functionality of the current Child Support Enforcement system monthly process.

Client Web Browser Graphical User Interface . The client web based front end of the application in Hyper Text Markup Language HTML which a Custodial Parent client user will use to click on a Case Number link from the client s web browser to initiate querying the appropriate SQL server tables and generate requested results back to the client web browser.

Amount Due For The Current Month Active Server Page ASP . The client web based front end of the application in Hyper Text Markup Language HTML calls on the Amount Due For The Current Month Active Server Page to display back to the client browser the most recent information about the progress of receiving a payment. The Amount Due for the Current Month Active Server Page will contain the following 

Amount Due For The Current Month Business Component . The Amount Due For The Current Month Business Component defines all of the public interfaces for the Amount Due For The Current Month business related components. It is responsible for all the data access to the SQL7 Server Database related to the Amount Due For The Current Month data. In addition the Amount Due For The Current Month business component will contain the following 

The output result will display three paragraphs which contains the last case process date the amount that the non Custodial Parent owes the Custodial Parent the amount that has been paid to date the total amount still owed to Custodial Parent the total of all past payments in arrears that the non Custodial Parent owed to the Custodial Parent and the scheduled payment that the non Custodial Parent owes the Custodial Parent and the combined total due payable for the current amount back to the custodial parent s web browser.

Amount Due For The Current Month Page Controller . The Amount Due For The Current Month Page Controller is a Microsoft Transaction Server MTS component that will provide a standard way of transporting data to and from the Amount Due For The Current Month Active Server Page through dictionary objects. It implements business logic that would otherwise reside in the Amount Due For The Current Month Active Server Page. It is the co ordinator between the interaction of the Amount Due For The Current Month Active Server Pages and the Amount Due For The Current Month Business Components. In addition the Amount Due For The Current Month Page Controller will interface with the Internet Information Server event handlers.

ICBAM Architecture Component . The Internet Component Based Architecture Model ICBAM component that will provide the following common architecture services 

A list of recent case action events related to the case number followed by month date and year of the action will be displayed from the Amount Due For The Current Month Active Server Page. The said data will be viewable online and printable. The Amount Due For The Current Month display format where the output results are stored in the areas.

This portion describes the general design for the Contact Us Email Connection to Case Worker Display Page for the electronic Child Support Enforcement Web Application eCSE . This is achieved by providing an overview of the system s various infrastructure components and their interdependencies.

The eCSE Contact Us Email Connection to Case Worker web page is designed to include the functionality required perform the following 

Custodial Parent will click the Contact Us link located in the top menu selection bar in the Home Page using a certified web browser. The Contact Us link will be displayed throughout the Child Support Enforcement Web Site.

Data will be retrieved from the SQL7 Server through the ICBAM Architecture. The ICBAM Architecture was built using Microsoft Object Component Technologies COM .

Data will pass through the business logic using the page controller COM component to from the Active Server Pages.

Active server pages will be used to display the Contact Us case worker email link Office phone local and 800 toll free and mailing address. Any errors encountered during the data retrieval will be documented in a server error log using the ICBAM Architecture.

There are no user inputs required for the Contact Us Web Page. However when an Internet User clicks on the URL to access the page the page will retrieve the Contact Us Email Connection to Case Worker data by the Case Number selected and display case news information back to the Custodial Parent user s web browser.

SQL7 Data Repository on Web Server . An established area on the web server where all files to be used by the eCSE SQL7 data warehouse will be deposited.

Server Microsoft SQL7 Data Warehouse . A robust relational database containing tables with data necessary to encompass the functionality of the current Child Support Enforcement system monthly process.

Client Web Browser Graphical User Interface . The client web based front end of the application in Hyper Text Markup Language HTML which a Custodial Parent client user will use to click on a Case Number link from the client s web browser to initiate querying the appropriate SQL server tables and generate requested results back to the client web browser.

Contact Us Email Connection to Case Worker Active Server Page ASP . The client web based front end of the application in Hyper Text Markup Language HTML calls on the Contact Us Email Connection to Case Worker Active Server Page to display back to the client browser the most recent information about the progress of a case. The Contact Us Email Connection to Case Worker Active Server Page will contain the following 

Contact Us Email Connection to Case Worker Business Component . The Contact Us Email Connection to Case Worker Business Component defines all of the public interfaces for the Contact Us Email Connection to Case Worker business related components. It is responsible for all the data access to the SQL7 Server Database related to the Contact Us Email Connection to Case Worker data. In addition the Contact Us Email Connection to Case Worker Display business component will contain the following 

Contact Us Email Connection to Case Worker Display Page Controller . The Contact Us Email Connection to Case Worker Page Controller is a Microsoft Transaction Server MTS component that will provide a standard way of transporting data to and from the Contact Us Case Worker Active Server Page through dictionary objects. It implements business logic that would otherwise reside in the Contact Us Display active server page. It is the co ordinator between the interaction of the Contact Us Active Server Pages and the Contact Us Business Components. In addition the Contact Us Page Controller will interface with the Internet Information Server event handlers.

ICBAM Architecture Component . The Internet Component Based Architecture Model ICBAM component that will provide the following common architecture services 

TCP IP Network . Internet user will send an email correspondence through the TCP IP network to the State s email server into a case worker s inbox.

The architecture component has error handling routines while retrieving data. For the email form the email address in the To field must be in the standard email address format 

A list of recent case action events related to the case number followed by month date and year of the action will be displayed from the Contact Us Email Connection to Case Worker Active Server Page. The data will be viewable online and printable.

This portion describes the general design for the Have You Found the Non Custodial Parent of My Children display Page for electronic Child Support Enforcement Web Application eCSE . This is achieved by providing an overview of the system s various infrastructure components and their interdependencies.

The eCSE Have You Found the Non Custodial Parent of My Children web page is designed to include the functionality required in performing the following 

Custodial Parent will click the Have You Found the Non Custodial Parent of My Children link located in the main menu selection bar in the Custodial Parent Case Payment Information Page using a certified web browser.

Data will be retrieved from the SQL7 Server through the CBAM Architecture. The CBAM Architecture was built using Microsoft Object Component Technologies COM .

Data will pass through the business logic using the page controller COM component to from the Active Server Pages.

Active server pages will be used to display the Have You Found the Non Custodial Parent of My Children Information in a paragraph form. The data will display in the form of two paragraphs 

The first paragraph displays the as of last processed date non Custodial Parent s full name and whether or not the non custodial parent has been located.

The second paragraph displays a message which informs the Custodial Parent to make sure the home and work addresses are correct. If there is new information about the non Custodial Parent it will contain a link to the Manage My Case Page.

Any errors encountered during the data retrieval will be documented in a server error log using the CBAM Architecture.

There are no user inputs required for the Have You Found the Non Custodial Parent of My Children Web Page. However when the Custodial Parent logs on access the case payment information page and clicks on the Have You Found the Non Custodial Parent of My Children link the page will capture the following 

The active server page will retrieve the Have You Found the Non Custodial Parent of My Children data information formatted in two paragraphs back to the Custodial Parent user s web browser.

Social Security logon and password is required. Please see Logon Screen Security and Authentication general design document for more details.

SQL7 Data Repository on Web Server . An established area on the web server where all files to be used by the eCSE SQL7 data warehouse will be deposited.

Server Microsoft SQL7 Data Warehouse . A robust relational database containing tables with data necessary to encompass the functionality of the current Child Support Enforcement system monthly process.

Client Web Browser Graphical User Interface . The client web based front end of the application in Hyper Text Markup Language HTML which a Custodial Parent client user will use to click on a Case Number link from the client s web browser to initiate querying the appropriate SQL server tables and generate requested results back to the client web browser.

Have You Found the Non Custodial Parent of My Children Active Server Page ASP . The client web based front end of the application in Hyper Text Markup Language HTML calls on the Have You Found the Non Custodial Parent of My Children Active Server Page to display back to the client browser the most recent information about the reasons of locating or not locating the non Custodial Parent. The Have You Found the Non Custodial Parent of My Children Active Server Page will contain the following 

Have You Found the Non Custodial Parent of My Children Business Component . The Have You Found the Non Custodial Parent of My Children Business Component defines all of the public interfaces for the Have You Found the Non Custodial Parent of My Children business related components. It is responsible for all the data access to the SQL7 Server Database related to the Have You Found the Non Custodial Parent of My Children data. In addition the Have You Found the Non Custodial Parent of My Children business component will contain the following 

The output result will display two paragraphs which contains the Custodial Parent full name Case Number non Custodial Parent full name links to the Current Home Address and the non Custodial Employers Address page back to the custodial parent s web browser.

Have You Found the Non Custodial Parent of My Children Page Controller . The Have You Found the Non Custodial Parent of My Children Page Controller is a Microsoft Transaction Server MTS component that will provide a standard way of transporting data to and from the Have You Found the Non Custodial Parent of My Children Active Server Page through dictionary objects. It implements business logic that would otherwise reside in the Have You Found the Non Custodial Parent of My Children Active Server Page. It is the co ordinator between the interaction of the Have You Found the Non Custodial Parent of My Children Active Server Pages and the Have You Found the Non Custodial Parent of My Children Business Components. In addition the Have You Found the Non Custodial Parent of My Children Page Controller will interface with the Internet Information Server event handlers.

CBAM Architecture Component . The Component Based Architecture Model CBAM component that will provide the following common architecture services 

A list of recent case action events related to the case number followed by month date and year of the action will be displayed from the Have You Found the Non Custodial Parent of My Children Active Server Page. The said data will be viewable online and printable.

This portion describes the general design for the Where is My Money Display Page for the electronic Child Support Enforcement Web Application eCSE . This is achieved by providing an overview of the system s various infrastructure components and their interdependencies.

The eCSE Where is My Money web page is designed to include the functionality required perform the following 

Custodial Parent will click the Where is My Money link located in the main menu selection bar in the Custodial Parent Case Payment Information Page using a certified web browser.

Data will be retrieved from the SQL7 Server through the ICBAM Architecture. The ICBAM Architecture was built using Microsoft Object Component Technologies COM .

Data will pass through the business logic using the page controller COM component to from the Active Server Pages.

Active server pages will be used to display the Where is My Money Information in a paragraph form. The data will display the current month s payment The date the payment was mailed to the Custodial Parent When will the check be delivered and an option link to set up a direct deposit into the Custodial Parent s account. Any errors encountered during the data retrieval will be documented in a server error log using the ICBAM Architecture.

There are no user inputs required for the Where is My Money Web Page. However when an Internet User clicks on the Where is My Money link the page will retrieve the Where is My Money data in a paragraph back to the Custodial Parent user s web browser.

Social Security logon and password is required. Please see Logon Screen Security and Authentication general design document for more details.

SQL7 Data Repository on Web Server . An established area on the web server where all files to be used by the eCSE SQL7 data warehouse will be deposited.

Server Microsoft SQL7 Data Warehouse . A robust relational database containing tables with data necessary to encompass the functionality of the current Child Support Enforcement system monthly process.

Client Web Browser Graphical User Interface . The client web based front end of the application in Hyper Text Markup Language HTML which a Custodial Parent client user will use to click on a Case Number link from the client s web browser to initiate querying the appropriate SQL server tables and generate requested results back to the client web browser.

Where is My Money Active Server Page ASP . The client web based front end of the application in Hyper Text Markup Language HTML calls on the Where is My Money Active Server Page to display back to the client browser the most recent information about the progress of receiving a payment. The Where is My MoneyActive Server Page will contain the following 

Where is My Money Business Component . The Where is My Money Business Component defines all of the public interfaces for the Where is My Money business related components. It is responsible for all the data access to the SQL7 Server Database related to the Where is My Money data. In addition the Where is My Money business component will contain the following 

The output result will display a paragraph of the amount of money the date the money was mailed back to the custodial parent s web browser.

Where is My Money Page Controller . The Where is My Money Page Controller is a Microsoft Transaction Server MTS component that will provide a standard way of transporting data to and from the Where is My Money Active Server Page through dictionary objects. It implements business logic that would otherwise will reside in the Where is My Money Active Server Page. It is the co ordinator between the interaction of the Where is My Money Active Server Pages and the Where is My Money Business Components. In addition the Where is My Money Page Controller will interface with the Internet Information Server event handlers.

ICBAM Architecture Component . The Internet Component Based Architecture Model ICBAM component that will provide the following common architecture services 

A list of recent case action events related to the case number followed by month date and year of the action will be displayed from the Where is My Money Active Server Page. The said data will be viewable online and printable. The Where is My Money display format where the output results are stored in the areas.

This portion describes the general design for the Why Didn t I Get My Child Support Payment display Page for the electronic Child Support Enforcement Web Application eCSE . This is achieved by providing an overview of the system s various infrastructure components and their interdependencies.

The eCSE Why Didn t I Get My Child Support Payment web page is designed to include the functionality required perform the following 

Custodial Parent will click the Why Didn t I Get My Child Support Payment link located in the main menu selection bar in the Custodial Parent Case Payment Information Page using a certified web browser.

Data will be retrieved from the SQL7 Server through the ICBAM Architecture. The ICBAM Architecture was built using Microsoft Object Component Technologies COM .

Data will pass through the business logic using the page controller COM component to from the Active Server Pages.

Active server pages will be used to display the Why Didn t I Get My Child Support Payment Information in a paragraph form. The data will display in the form of two paragraphs 

The first paragraph displays the reason the payment was not received and the non Custodial Parent s full name.

The second paragraph displays a message which informs the Custodial Parent to make sure the current address is correct. In addition the second paragraph will contain the links to the Current Address Page and Current Employers Address Page of the non Custodial Parent.

Any errors encountered during the data retrieval will be documented in a server error log using the ICBAM Architecture.

There are no user inputs required for the Why Didn t I Get My Child Support Payment Web Page. However when the Custodial Parent logs on access the case payment information page and clicks on the Why Didn t I Get My Child Support Payment link the page will capture the following 

The active server page will retrieve the Why Didn t I Get My Child Support Payment data information formatted in two paragraphs back to the Custodial Parent user s web browser.

Social Security logon and password is required. Please see Logon Screen Security and Authentication general design document for more details.

SQL7 Data Repository on Web Server . An established area on the web server where all files to be used by the eCSE SQL7 data warehouse will be deposited.

Server Microsoft SQL7 Data Warehouse . A robust relational database containing tables with data necessary to encompass the functionality of the current Child Support Enforcement system monthly process.

Client Web Browser Graphical User Interface . The client web based front end of the application in Hyper Text Markup Language HTML which a Custodial Parent client user will use to click on a Case Number link from the client s web browser to initiate querying the appropriate SQL server tables and generate requested results back to the client web browser.

Why Didn t I Get My Child Support Payment Active Server Page ASP . The client web based front end of the application in Hyper Text Markup Language HTML calls on the Why Didn t I Get My Child Support Payment Active Server Page to display back to the client browser the most recent information about the reasons of not receiving a payment. The Why Didn t I Get My Child Support Payment Active Server Page will contain the following 

Why Didn t I Get My Child Support Payment Business Component . The Why Didn t I Get My Child Support Payment Business Component defines all of the public interfaces for the Why Didn t I Get My Child Support Payment business related components. It is responsible for all the data access to the SQL7 Server Database related to the Why Didn t I Get My Child Support Payment data. In addition the Why Didn t I Get My Child Support Payment business component will contain the following 

The output result will display two paragraphs which contains the Custodial Parent full name Case Number non Custodial Parent full name links to the Current Home Address and the non Custodial Employers Address page back to the custodial parent s web browser.

Why Didn t I Get My Child Support Payment Page Controller . The Why Didn t I Get My Child Support Payment Page Controller is a Microsoft Transaction Server MTS component that will provide a standard way of transporting data to and from the Why Didn t I Get My Child Support Payment Active Server Page through dictionary objects. It implements business logic that would otherwise will reside in the Why Didn t I Get My Child Support Payment Active Server Page. It is the co ordinator between the interaction of the Why Didn t I Get My Child Support Payment Active Server Pages and the Why Didn t I Get My Child Support Payment Business Components. In addition the Why Didn t I Get My Child Support Payment Page Controller will interface with the Internet Information Server event handlers.

ICBAM Architecture Component . The Internet Component Based Architecture Model ICBAM component that will provide the following common architecture services 

A list of recent case action events related to the case number followed by month date and year of the action will be displayed from the Why Didn t I Get My Child Support Payment Active Server Page. The said data will be viewable online and printable.

Although only a few embodiments of the present invention have been described in detail herein it should be understood that the present invention may be embodied in many other specific forms without departing from the spirit or scope of the invention. Therefore the present examples and embodiments are to be considered as illustrative and not restrictive and the invention is not to be limited to the details given herein but may be modified within the scope of the appended claims.

