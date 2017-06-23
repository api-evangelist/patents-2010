---

title: Declarative and multi-mode wizard framework
abstract: A user interface mechanism may be defined by a story from which a wizard engine may create a user interface. The engine may present the story using various user interface containers that define a layout and general functions of a user interface, along with styles that may define the ‘look and feel’ of the user interface. The story may define an action performed once data are collected from the user. The story may also define data passed to the action, as well as the data collected from a user. The story may further define translation routines or other actions that may be launched in response to receiving user action and used to generate data that may be passed to the action.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08869048&OS=08869048&RS=08869048
owner: Microsoft Corporation
number: 08869048
owner_city: Redmond
owner_country: US
publication_date: 20101108
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 382 685 entitled Declarative Wizard Framework filed Sep. 14 2010 by Gaurav Kapila et al. which is incorporated herein in its entirety.

Wizards and other user interface mechanisms may collect data from a user and launch various actions. For smaller applications such user interfaces may be individually designed and programmed As applications become larger and more complex the sheer number of user interface mechanisms may become unwieldy to design and manage.

A user interface mechanism may be defined by a story from which a wizard engine may create a user interface. The engine may present the story using various user interface containers that define a layout and general functions of a user interface along with styles that may define the look and feel of the user interface. The story may define an action performed once data are collected from the user. The story may also define data passed to the action as well as the data collected from a user. The story may further define translation routines or other actions that may be launched in response to receiving user action and used to generate data that may be passed to the action.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

An interactive user interface mechanism may be defined by a story that may define an action to be performed as well as data collected from a user. The story may be consumed by a wizard engine that may create a user interface from one of a set of user interface containers and various styles. A single story may be used to create several different user interfaces by applying a different user interface container.

The story may include definitions for an action to be performed as well as parameters that may be passed to the action. The action may be a script application service or other executable function that may accept data and perform some type of function.

The story may also include definitions of data collected from a user. The data may be defined using various types and a wizard engine may interpret the types to create user interface components corresponding to the types. In some cases the types may correspond with data passed to the action while in other cases the data collected from the user may be analyzed or processed using various routines defined in the story.

The story may be defined in a declarative manner such that a wizard engine may process the story to create a user interface. The declarative manner may simplify user interface creation as well as the maintenance and modification of user interfaces for many different types of applications.

Throughout this specification like reference numbers signify the same elements throughout the description of the figures.

When elements are referred to as being connected or coupled the elements can be directly connected or coupled together or one or more intervening elements may also be present. In contrast when elements are referred to as being directly connected or directly coupled there are no intervening elements present.

The subject matter may be embodied as devices systems methods and or computer program products. Accordingly some or all of the subject matter may be embodied in hardware and or in software including firmware resident software micro code state machines gate arrays etc. Furthermore the subject matter may take the form of a computer program product on a computer usable or computer readable storage medium having computer usable or computer readable program code embodied in the medium for use by or in connection with an instruction execution system. In the context of this document a computer usable or computer readable medium may be any medium that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The computer usable or computer readable medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or propagation medium. By way of example and not limitation computer readable media may comprise computer storage media and communication media.

Computer storage media includes volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and may be accessed by an instruction execution system. Note that the computer usable or computer readable medium can be paper or other suitable medium upon which the program is printed as the program can be electronically captured via for instance optical scanning of the paper or other suitable medium then compiled interpreted of otherwise processed in a suitable manner if necessary and then stored in a computer memory.

Communication media typically embodies computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media. The term modulated data signal can be defined as a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above mentioned should also be included within the scope of computer readable media.

When the subject matter is embodied in the general context of computer executable instructions the embodiment may comprise program modules executed by one or more systems computers or other devices. Generally program modules include routines programs objects components data structures and the like that perform particular tasks or implement particular abstract data types. Typically the functionality of the program modules may be combined or distributed as desired in various embodiments.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be operating system level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the described functions.

Embodiment is an example of a device or network environment where a wizard engine may be deployed. The wizard engine may define user interfaces using a minimum set of information but may allow very sophisticated and complex user interfaces to be created. In many cases a user may interact with the user interface to review and input data then cause an action to be performed when the conditions for the action are met or when the user launches the action.

In a typical use scenario a wizard engine may create a wizard type user interface where a user may be stepped through various user interface pages to input data or select various options. At the end of the wizard an action may be launched consuming the data collected from the user.

In another use scenario a wizard engine may create a property sheet style user interface. In such a user interface a user may be able to navigate through various pages which may display existing data values and give the user opportunity to view or change the value. The user may launch an action from the property sheet user interface by manually selecting a user interface button for example.

In the examples of the wizard type user interface and the property sheet style user interface the same story definition may be displayed using different user interface containers. The wizard engine may apply a different user interface story to give a different user experience depending on the design of the application.

The wizard engine may allow a programmer to create very complex user interfaces with a minimum of programming effort and resulting in a consistent unified look and feel across multiple user interfaces. A user interface container may define the general layout and function of a user interface and the user interface container may be reused for many different stories. A set of styles may also be defined that contain color font and other definitions and the styles may be applied across multiple user interface containers.

Because the user interface containers may be reused throughout an application a user may become comfortable with the navigation and operation of the user interfaces because of the consistency of the user interfaces. The programmer may merely create new stories rather than recreating the mechanism of the user interface.

Further the modular design may allow updates to be performed in an economical manner. For example a complete facelift may be performed on an application by merely updating a few user interface containers or adjusting the styles without affecting the underlying functionality.

The user interfaces generated by a wizard engine may be defined using a declarative story that may contain several elements. The story may contain an action and data collection consumed by the action. The action may be a routine function application service call application programming interface call or any type of executable function that may consume data.

The data collection may be a set of data types that are consumed by the action. The data collection may contain mandatory and optional data that may be transmitted to the action.

The story may also contain a series of user interface sections that may be interpreted by the wizard engine and turned into user interface pages. The user interface sections may contain various data types that may be collected on each page. The sequence of user interface sections may define a sequence of pages displayed to a user in a wizard style user interface.

The user interface sections may contain data types. The data types may be defined with a name that may or may not correspond with the data collection that may be consumed by the action. When the names of the data types correspond with the names of data consumed by the action the wizard engine may link the two together. When the names of the data types do not correspond a transformation operation may be defined to generate data consumed by the action from the user input.

A wizard engine may examine the data types and create a user input component corresponding with the data type. For example a string data type may be displayed using a text box. In another example a string data type defined with four different options may be displayed using a drop down selector that has the four options listed.

The data types may also be defined with a various layout hints. The layout hints may be used by a wizard engine to select and configure a user input component. In some cases the layout hints may override preferences defined in a user interface container or style while in other cases a wizard engine may ignore some layout hints depending on the user interface container or style definitions.

For example a layout hint for a data type with a set of options may request a set of radio buttons rather than a default drop down list user input component. In another example a layout hint may define that a particular data type may be positioned to the upper left corner of a page or that the data type may be presented in a bold or emphasized format.

In some cases a data type definition may include validation information. The validation information may be as simple as defining an acceptable range of values. In more complex definitions the validation information may include a call to an external function application programming interface or other service. For example a data type for a postal code may include a function call to a remote service that may validate the data collected from the user.

The user interface may present error messages to a user when data may be invalid. The error messages may be defined as part of a user interface container or style or may be a default configuration defined by the wizard engine. The data type definition may include configuration information that may allow a user to continue with invalid information or may prohibit the user to continue when invalid information is detected.

The wizard engine may include many default settings or selections that may be overridden by a user interface container by the style definitions or by the story definition. The default settings may produce a reasonable but generic user interface. In some cases layout hint contained in the story may override settings defined in the user interface container or in the style definitions. In other cases the layout hints may be ignored in favor of the user interface container or style definitions.

In many embodiments different priorities may be defined for different components. When multiple components define different settings the setting from the highest priority component may be implemented. In general the default settings used by a wizard engine may be the lowest priority. In some embodiments the style definitions may be the second lowest priority with the user interface container being the next priority and layout hints being the highest priority.

In some cases the layout hints may be disregarded in favor of a definition in a user interface container or style definition. In some cases a layout hint may be implemented in one user interface container but not another. Such cases may be defined by specially designating certain properties in a user interface container. For example certain portions of a user interface container may be specially designated as not able to be overridden while the default property of user interface container definitions may be overridden by a layout hint.

Embodiment illustrates a device that may have a wizard engine to generate user interfaces. The device may generate a user interface that may be displayed on the device or on a remote device.

The device is illustrated having hardware components and software components . The controller device as illustrated represents a conventional computing device although other embodiments may have different configurations architectures or components.

The controller device may be a server computer desktop computer or comparable device. In some embodiments the controller device may be a laptop computer netbook computer tablet or slate computer wireless handset cellular telephone or any other type of computing device.

The hardware components may include a processor random access memory and nonvolatile storage . The hardware components may also include a user interface and network interface . The processor may be made up of several processors or processor cores in some embodiments. The random access memory may be memory that may be readily accessible to and addressable by the processor . The nonvolatile storage may be storage that persists after the device is shut down. The nonvolatile storage may be any type of storage device including hard disk solid state memory devices magnetic tape optical storage or other type of storage. The nonvolatile storage may be read only or read write capable.

The user interface may be any type of hardware capable of displaying output and receiving input from a user. In many cases the output display may be a graphical display monitor although output devices may include lights and other visual output audio output kinetic actuator output as well as other output devices. Conventional input devices may include keyboards and pointing devices such as a mouse stylus trackball or other pointing device. Other input devices may include various sensors including biometric input devices audio and video input devices and other sensors.

The network interface may be any type of connection to another computer. In many embodiments the network interface may be a wired Ethernet connection. Other embodiments may include wired or wireless connections over various communication protocols.

The software components may include an operating system on which various applications and services may operate. An operating system may provide an abstraction layer between executing routines and the hardware platform and may include various routines and functions that communicate directly with various hardware components.

A wizard engine may execute on the device as part of a larger application. The wizard engine may consume various stories user interface container and styles to generate various user interfaces . Each user interface may have an associated action application that may be launched from the user interface and may consume data collected by the user interface .

The wizard engine may be part of or called by an application . The application may be any type of application for which a user may view and enter data. As an example the application may be a network management application where an administrator may configure and monitor devices across a network. In such an application an administrator may launch various actions that may configure devices add and remove services and perform various administrative tasks. For each function performed by the application a user interface may be generated that collects data from a user and launches an action.

The story may define an action to perform a data collection that may be transmitted to the action and a series of user interface sections that may include data types that are collected in each user interface section. The wizard engine may combine the story with one of several user interface containers to create a user interface . The styles may be applied to give the user interface a specific look and feel. An example of a story and resulting user interfaces may be found later in this specification.

The architecture of the components may vary with different embodiments. In some embodiments the wizard engine may be a standalone application or service that may receive a story user interface container and style from an application . In another embodiment the wizard engine may be a set of functions or routines that are incorporated into the executable code of the application . In still another embodiment the wizard engine may be a dynamic linked library assembly or other group of routines that may be called by the application .

In some embodiments the application may have a database that may supply and store some of the information processed by a user interface. In some cases a story may define certain data items that may be displayed in the user interface. Such items may be retrieved from the database prior to displaying the items and the data collected from the user may be stored in the database after collection.

The action application may be any routine or function called from a user interface. In some cases the action application may be a standalone application. In other cases the action application may be a service operating system function or other executable within the device . In some cases the action application may be a remote application or executable located on a device accessed over a network . In a typical use the action application may be a routine within the application .

The device may be any type of device on which a callable application service function or other callable entity may reside. The device may have a hardware platform which may be similar to the hardware platform of device . The device may be accessed from the device over a network which may be any type of communications network such as a wired or wireless local area network wide area network or other network.

In some embodiments the wizard engine may be located on a client device while the application that called the wizard engine may reside on a server or other remote device. For example a remote device may have a hardware platform which may be similar to the hardware platform and may also have an application and database . The application may call the wizard engine on the device where the device may be the user s local device.

In such an embodiment the application may transmit a story user interface container and styles to the device and the locally operable wizard engine may create a user interface for display on the device . In such an embodiment the computing power of the device may be used for creating and operating the user interface which may offload such functions from the remote device .

In another architecture the device may create user interfaces that are displayed on another device. For example the wizard engine may create a user interface that may be displayed on a client device . In such an embodiment the device may operate as a server and the device may operate as a client.

The client device may include a hardware platform and a locally running application which may display a user interface that may be generated by the wizard engine . In one example the user interface generated by the wizard engine may be defined using a Hyper Text Markup Language HTML description. In such an example the application may be a web browser that may display the HTML user interface description as a local user interface .

In another embodiment the user interface on the device may connect to the device using a remote desktop or remote display application. In such an embodiment the application may provide a real time connection to the device and the user interfaced generated on the device may be displayed as the user interface on a remote client device .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment is a simplified example of the steps a programmer may perform to create a story. An example story may be found later in this specification. The steps represent the general design steps that may create a story that performs a specific action and consumes a data collection. In order to generate the data collection definitions may be created for the data collected by a user along with any transformation functions or analyses that may be performed to transform the collected data into the data transferred to the action.

The action may be defined in block . The action may be any routine function application or other executable that may be called from the user interface. The action may be the final step when a user interface is presented and the data collected from the user interface may be passed to the action.

In many embodiments the action may represent the purpose or end goal of the user interface. For example a user interface may assist a user in performing a specific task such as changing a configuration on a device. The action may be a script or function call to the device with the desired settings for making the configuration change.

The data consumed by the action may be defined in block . Such data may be referred to as a data collection and may represent various data objects that may be transferred to the action so that the action operates as intended.

The data collected from the user may be defined in block . The data collected by the user may not be the same as the data consumed by the action in some cases. In some cases the user may supply data that may be transformed processed or analyzed to generate the data consumed by the action. In a simple example an action may consume data in the form of a city and state. However the information collected from the user may be a postal code. A transformation routine may convert the postal code received from the user to city and state consumed by the action.

Each information point collected from the user may be analyzed in block . For each information point in block a data type may be defined in block .

The data type in block may be used by a wizard engine to determine an appropriate user interface component to incorporate into a user interface. For example a string type may be presented as an editable text box or a real number type may be presented with a numerical input mechanism.

A user interface component may be an input mechanism presented on a user interface for presenting and capturing a specific data type. In many programming environments several predefined user interface components may exist and a wizard engine may select between the various user interface components to include in a user interface. In some embodiments a user interface component may be defined in a user interface container. Such embodiments may include user interface components for complex data types corresponding to the complex data types defined in a story.

In some embodiments the data type in block may be a complex data type. A complex data type may be made up of primitive data types such as strings integers real numbers binary or Boolean or other primitive data types. In some cases complex data types may have corresponding user interface components. In other cases a wizard engine may disassemble a complex data type to assign user interface components that can be used to collect and capture a complex data type.

Each data type may have a name assigned in block . In many cases a wizard engine may use the name as a label for a user interface component. In other cases various user interface hints may include labels tags or other information that may be presented to the user.

If the data type may not be directly consumed by the action in block a transformation function may be defined in block . The transformation function may define how an input from a user may be transformed or changed to match the data collected by the user interface. For example a transformation function may convert a telephone number received in one of several formats to a specific format used by an action.

In some embodiments the transformation function may be defined using simple arithmetic such as adding to figures together to create a third. In other embodiments the transformation function may be quite complex and may be implemented by calling an external routine or function. In one such embodiment a piece of data collected from a user may be transmitted to an external routine for lookup in a database. The value returned from the database may be placed in the data collection and consumed by the action.

Whether or not the transformation function is defined in block validation criteria may be defined in block . In some embodiments no validation criteria may be defined for certain data types. Validation criteria may define acceptable and unacceptable values of input data. In some cases the criteria may be formatting related such as requesting a five digit integer while in other cases the criteria may be to accept certain values such as to accept only valid five digit postal codes.

In some embodiments the validation may be defined in a story. Such embodiments may be useful when the validation may be expressed simply. In other embodiments the validation may be performed by a call to an external function. For example a postal code may be sent to a remote server for validation against a database of valid postal codes.

Layout hints may be defined in block . A user interface hint may be any setting definition or other information that may be used by a wizard engine to modify the placement function look and feel or other parameter with regard to the data item. For example a layout hint may define that a certain data type may be displayed at the top of a page or displayed with bold type. Other layout hints may define labels associated with the user interface component or define help text or detailed descriptors that may be optionally displayed.

After processing each information point that may be collected in block the information points may be organized into sections in block . The sections may be converted by the wizard engine into pages with some user interface containers. The pages may define groups of data types that may be collected together. In some embodiments the pages may be defined with descriptive text help text images or other information.

The sequence and branching of the sections may be defined in block . In some embodiments the sequence of data collection may be defined to be in a special order or may include branch points and conditions for certain sections. The sequencing and branching may allow a programmer to collect a data item from a user then select different pages to show based on the data received from the user.

Each section may be evaluated in block . For each section in block section layout hints may be defined in block . A section layout hint may operate similarly to a layout hint applied to a specific data type but the section layout hint may define layout information that may be applied to the section as a whole. Section layout hints may define how an entire section may be presented or how groups of data items may be laid out or organized visually.

For each section a transition may be defined to another section in block . The transition may define visual transitions as well as data processing transitions. A visual transition may define how an animated change between one section and another or may define a barrier or junction between two sections for example. A data processing transition may define a function that may be performed to analyze and transform data once the data items in a section are populated and when a user moves to the next section. Such functions may be defined in the story and may include a call to an external function.

In some embodiments a set of story layout hints may be defined in block . Story layout hints may define various layout parameters that may apply to the entire story. In some cases the layout parameters may define for example which user interface containers are appropriate for the particular story or certain look and feel options that may be applied to the entire story. In some cases the story layout hints may define a set of validation settings that apply to all parameters in the story or for other settings that may be applied across many data items or sections of the story.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment is a simplified example of creating and operating a user interface based on a story. In block the story may be read. In many cases the story may be defined using XML or other declarative language.

A user interface container may be selected in block . In many cases a particular story may be used with several different user interface containers. The selection of a specific user interface container may be aided by an application that provides the story to a wizard engine. For example a conventional wizard user interface container may be selected when a user first attempts to perform a function or when little data are preexisting. When a user performs a function for a second time or when much of the data for executing an action preexists an application may select a property sheet user interface container.

In some embodiments a story may contain a list of user interface containers for which the story is designed. The list may be used by the wizard engine to select an appropriate user interface container.

In other embodiments a wizard engine may analyze a story to determine the data types collected and general arrangement of the story then select an appropriate user interface container that matches the characteristics of the story. Such characteristics may include matching the number of sections with a user interface container supporting the number of sections or matching the data types layout hints or other items in the story with those of a user interface container.

The user interface container may be laid out in block . In many embodiments the user interface container may contain various layout and operational characteristics of the user interface. In performing the layout of block a wizard engine may determine the output characteristics of a user interface device such as the screen width resolution and various other settings. These output characteristics may be used to layout the user interface.

The styles may be applied to the user interface in block . The styles may define various styles of text images and other items in a user interface. The styles may use Cascading Style Sheet CSS or other similar technologies to apply styles that may be assigned to various components.

In block a page may be created to display. In many embodiments a user interface may have several pages within a single display. For example a wizard user interface may have several pages that are presented in succession or a property sheet user interface may have several pages that are accessed through tabs in a user interface.

In some embodiments a wizard engine may create each page as requested by the user. For example when a user completes one page of a wizard the wizard engine may create the next page. In some embodiments a wizard engine may create all of the pages of a user interface prior to presenting the first page to the user.

The user interface may be presented to the user in block . The user interface may be an interactive user interface that may contain several pages. Within the user interface several navigation options may be available to the user. For example some user interfaces may include tabs breadcrumbs tables of contents or other navigation aids that may allow the user to browse to different sections of the user interface. Some user interfaces may have navigation buttons that advance or return from one page to the next.

In general a user interface may allow a user to perform three general classes of actions input data navigate or launch the action associated with the user interface.

User input may be received in block . When a validation is defined for a data type the validation may occur in block . If the validation fails in block the user interface may be updated with an error message in block and the process may return to block . If the data passes validation in block any actions related to the data may be performed in block and the data may be stored in block .

The actions performed in block may be any actions that may be linked to the data. For example the actions in block may include querying a database to collect related data that may be displayed on another page of the user interface or collected for transmission to an action.

A navigation input may be received in block . The navigation input may be from any type of navigation object within the user interface. In a classic wizard type user interface the navigation buttons may advance or go back within the sequence of user interface pages. In a property sheet style user interface a user may be able to navigate by selecting any tab for example. Some embodiments may have several ways a user may navigate through the user interface.

The new page to display may be identified in block . In embodiments where all of the pages are not previously created the page may be created in block .

When a transition is defined for the page in block the transition may be performed in block . The user interface may be updated to reflect the new page in block and the process may return to block .

An action request may be received in block . In some embodiments the action request may be in response to a selection by a user to launch the action. In other embodiments the action request may be made automatically when all of the data items for the action have been populated.

If an action request is received and all of the data are not available in block the user interface may be updated with an error in block . If the all of the data are available in block the action may be launched in block and the data collection may be transmitted to the action in block . In many embodiments once the action is launched the user interface may be removed.

The two properties are collected from the user interface and used to launch an action . The action is to call MyWizardAction from an assembly entitled MyActionsAssembly .

The story contains two sections and . Section is an introductory page and does not contain any user input. Section defines two data items and which are Name and Description respectively. For item the definition include a property IsRequired True which indicates that the user is required to complete item for this user interface. The definition further includes a validation definition that defines a minimum and maximum length of 1 and 256 respectively.

Item does not have the IsRequired True statement indicating that item is optional. The validation of item is merely that it does not exceed 1024 characters. Item also includes a layout hint in the form of a Property.LayoutOverrides Height 300 statement. This statement gives a recommended height for any user input component such as a text box that the wizard engine may assign for the item.

The user interface contains a title that is an artifact of a page layout hint defined embodiment . The user interface shows two steps and corresponding to the sections and of embodiment . The step is illustrated showing the descriptor and text box as well as the descriptor and text box . The descriptors and correspond to the data items and .

The wizard style user interface of embodiment shows the steps and on the left hand column In some embodiments the steps and may be active controls that may allow the user to return to step by clicking on the Welcome item.

The wizard style user interface may also contain a set of navigation buttons . The navigation buttons may be the mechanism by which a user progresses through the sequence of a wizard.

The user interface of embodiment represents a very rich and complex user interface having navigation features layout and a look and feel that may all be defined in default values within a wizard engine or values defined within a user interface container or set of styles. The programmer merely defines the data to be collected an action to perform and data passed to the action and the wizard engine may create a sophisticated interactive user experience without any further programming.

User interface is an example of a continuous property sheet style user interface. A property sheet style user interface may allow access to all of the properties displayed in the user interface in contrast to a wizard style user interface where a user is presented with different pages in sequence. In a property sheet style user interface the user may browse through different pages or portions of the user interface editing or filling data as the user pleases.

In a continuous property sheet style user interface each of the pages of the user interface may be displayed in a large window. The user interface has a table of contents which may contain references to each of the pages . In some embodiments the table of contents may be active navigation buttons which may scroll the user interface to a selected page when clicked.

Each of the pages and are displayed with expanders and respectively. The expanders and may toggle to expand or collapse the respective page.

The user interface may contain a set of action launch buttons which are different from the navigation buttons of embodiment . In a property sheet style user interface a user may select the OK action launch button to cause the action to be performed. In such embodiments the user interface may check to see if all of the data has been collected when launching the action.

In a wizard style user interface the navigation buttons may allow the user to launch the action after the last page has been processed by the user.

The user interface represents a second type of property sheet style user interfaces. In contrast to the continuous property sheet style user interface of embodiment embodiment has each page separated and accessible through tabs and . Embodiment is illustrated with tab selected which corresponds with the page of embodiment the configuration of embodiment and the section of embodiment .

Embodiment also includes a set of action launch buttons that correspond with the action launch buttons of embodiment .

The foregoing description of the subject matter has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the subject matter to the precise form disclosed and other modifications and variations may be possible in light of the above teachings. The embodiment was chosen and described in order to best explain the principles of the invention and its practical application to thereby enable others skilled in the art to best utilize the invention in various embodiments and various modifications as are suited to the particular use contemplated. It is intended that the appended claims be construed to include other alternative embodiments except insofar as limited by the prior art.

