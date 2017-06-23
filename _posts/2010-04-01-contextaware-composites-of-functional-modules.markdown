---

title: Context-aware composites of functional modules
abstract: A computer-implemented system to receive user input at a first functional module, to issue an instruction from the first functional module to change a value of a first context item in response to the user input, to receive the instruction at a context services provider, and to issue, via the context data services provider, a notification of the changed value of the first context item. The notification is received at a second functional module based on an association of the second functional module with the first context item, and first functionality of the second functional module is generated based on the notification of the changed value of the first context item.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08930830&OS=08930830&RS=08930830
owner: Business Objects Software Limited
number: 08930830
owner_city: Dublin
owner_country: IE
publication_date: 20100401
---
A mashup is generally defined as a web page or application that combines information from two or more external sources to create a new service. Web applications e.g. Google Maps Yahoo Search increasingly provide Application Programming Interfaces APIs that enable software developers to create mashups based on the data and functions of these applications.

Mashups may be used to combine functions provided by different sources. For example a mashup may include a particular visualization of particular data provided by a first application and a particular visualization of particular data provided by a second application. This mashup simply reflects an aggregation of the two visualizations. Advantages to such an aggregation are minimal and no new or unanticipated functionality is provided thereby.

Some conventional mashups attempt to overcome the foregoing by providing some interaction between their constituent functions. is a representative block diagram of mashup including widgets through . Each of widgets through includes processor executable program code to provide data and or functionality. For example widgets through may comprise a weather icon a photo viewer a clock and a music player respectively.

A developer of mashup has written code i.e. wiring to provide interaction between widget and . The wiring may determine a location corresponding to a picture displayed by widget and may instruct widget to indicate the current weather at that location. Development of this wiring and any other desired wiring between widgets through requires expertise and resources.

The requirements for creating useful mashups are magnified in an enterprise environment. First the demand for application development resources in an enterprise environment is usually far greater than the supply. Additionally the internal wiring of enterprise mashups must be consistently maintained in view of changes to the source applications.

What is needed is a system for efficiently creating and enabling the operation of a composite of function providing modules which provides some degree of interaction among the modules.

The following description is provided to enable any person in the art to make and use the described embodiments and sets forth the best mode contemplated for carrying out some embodiments. Various modifications however will remain readily apparent to those in the art.

The program code of modules through may comprise Java Advanced Business Application Programming ABAP Flash and or any other type of code that is or becomes known. Each of modules through may be associated with a respective one or more data sources. For example module may provide visualizations of data stored in a Human Resource Management system while module may provide visualizations of data stored in a Customer Relationship Management system.

Each of modules through includes a different combination of context consuming logic and context producing logic. Specifically module includes both context consuming logic and context producing logic module includes context consuming logic module includes context producing logic and module includes neither context consuming logic nor context producing logic. Composite may include zero or more of each type of module shown in .

The depicted context consuming logic and context producing logic may support respectively a context consuming API and a context producing API. Generally and as will be described in more detail below the context consuming API may be used to notify a module of a change in the value of a context item and the context producing API may be used by a module to change the value of a context item. As a result modules through may interact with one another via changes in context item values.

Accordingly the context producing logic of a module may determine whether context services provider should be notified of a change to a value of a specific context item while the context consuming logic of a module may determine which context items are to be consumed as well as functionality to execute upon receipt of a notification of a change to a value of a consumed context item.

In a simple example module invokes the context producing API to issue an instruction to change a value of the context item Year to 2009. Context services provider receive the instruction and issues a notification of the change. The notification is received by module which is associated with the context item Year. Module may then execute its functionality based on the changed value of the context item. For example module may produce a visualization of data associated with the year 2009.

Module may also be associated with the context item Year may also receive the notification via the context consuming API and may also generate a data visualization based on the changed value of the context item. According to the present example module does not include logic supporting the context consuming API and is therefore unaffected by the change to the value of the context item.

The module functional logic of one or more of modules through may provide for reception of user input. With reference to the above example module may change the value of the context item Year to 2009 in response to received user input. Moreover module may execute its own functionality based on the changed value.

Composite thereby allows one or more modules to contribute to influence the environment in which they reside and as a result influence one or more other modules which share the same environment. Context provides the basic mechanism through which the environment is encapsulated and influenced.

Context is abstraction of what a user of system is currently doing or intending to do with modules through . Context is a set of information that can be used to characterize entities that are considered relevant to the interaction between a user and an application including the user and the application themselves. Context includes a set of context items and their associated values e.g. Year 2009 .

In a sample business scenario a user may performing a Budget Planning task in a specific application. At a point of time a snapshot of a current Context may include the following 

Provided below is an example of Context and Context Item using an eXtensible Markup Language XML based format.

Returning to context services provider collectively presents and manage context through its lifecycle. Context services provider allows a developer to produce and consume context items within context . During design time a developer of a functional module can use context services provider to declare the data structure of temperature as a context item and make the context item visible for other developers. As a result when runtime temperature data is made available the data can be well understood and therefore consumed by consuming modules.

1 A context data declaration exposure service to allow modules to expose their data structure to context services used for data production and consumption. These context services may use a publish subscribe protocol to provide the exposed data to modules. For example a module may subscribe to a particular set of context items and receive published notifications from the context services indicating changes in values of those context items.

2 A context data discovery service for discovering any data exposed through these context services. Developers may use the context data discovery service to determine what data are available visible and implement consuming producing behavior supported by typed structured context data.

3 A data serialization service to allow serialization deserialization of data using XML for example as a common data description language.

Although the embodiments described herein include module interaction through the use of context some embodiments do not preclude the use of programmatic wiring between modules as described with respect to widgets in the above Background.

System includes processor operatively coupled to communication device data storage device one or more input devices and one or more output devices . Communication device may facilitate communication with external devices. Input device s may comprise for example a keyboard a keypad a mouse or other pointing device a microphone knob or a switch an infra red IR port a docking station and or a touch screen. Input device s may be used for example to provide user input to system . Output device s may comprise for example a display e.g. a display screen a speaker and or a printer.

Data storage device stores program code for execution by processor as well as any data files for providing functions as described herein. In a case that system is operated by a user as described herein the program code may comprise program code of a Web browser to access a Web server providing functionality as described below with respect to process . Data storage device may also or alternatively store program code of a proprietary client application for operation by a user as described herein. Data storage device may comprise any appropriate information storage device including combinations of magnetic storage devices e.g. magnetic tape and hard disk drives optical storage devices and or semiconductor memory devices such as Random Access Memory RAM devices and Read Only Memory ROM devices.

Process and all other processes mentioned herein may be embodied in processor executable program code read from one or more of a tangible computer readable medium such as a floppy disk a CD ROM a DVD ROM a flash memory device and a magnetic tape and then stored in a compressed uncompiled and or encrypted format. In some embodiments hard wired circuitry or programmable logic arrays may be used in place of or in combination with program code for implementation of processes according to some embodiments. Embodiments are therefore not limited to any specific combination of hardware and software.

Initially at a context services provider is selected. A developer user may select a context services provider at in order to build a composite of modules based thereon. Accordingly the context services provider may be selected at within a development environment.

In one example a developer user operates system to initiate a development application. The development application may be stored in storage device and executed by processor and or may be executed by a remote system in communication with system . The development application may comprise a component within another application e.g. a business planning application which is to create manage and operate on the data to be visualized within the composite or an application within a bundled suite of applications e.g. an Enterprise Resource Planning suite an Enterprise Performance Management suite .

Continuing with this general example output device may display interface of prior to upon execution of the development application. Interface includes Create New Composite control . Upon user selection of control interface of may be displayed. Interface allows the user to assign a name to a new composite and at to select a context services provider upon which the new composite will be based.

The context services provider may be selected from a drop down menu of available context services. Each of the available context services providers may be associated with a set of context items. Accordingly upon selection of a context services provider at an associated set of context items may be displayed as shown in .

During development of a context services provider a developer may declare the set of context items to be associated with the context services provider. The developer may in some embodiments determine these context items based on an underlying Online Analytical Processing OLAP model. For example the dimensions of the OLAP model may include as members data that may be used to populate the context items. The determination of context items associated with a context services provider may therefore benefit from the typically well defined data structure of an OLAP model. However embodiments may support any underlying data.

Context items are selected at . illustrates the use of interface to select three context items. Also depicted in is the selection of default values for each of the selected context items. The composite is then initialized by selecting control .

Returning to process functional modules for canvas are selected at . The modules may be selected from a pre existing repository of functional modules. The selected modules may exhibit any of the characteristics described above with respect to modules through . Again and for each selected context item each of the selected modules may include none one or both of context producing logic and context consuming logic.

According to some embodiments one or more selected modules may be locked . A locked module does not re execute its functionality regardless of any changes to values of the context items which are consumed by the module. Therefore it may be determined at whether the user has issued an instruction to lock one of more modules of the composite. If so the one of more modules are locked at and flow proceeds to . If not flow proceeds directly from to .

At it is determined whether user input has been received to change a value of a context item with which the composite is associated. For example the user may operate input device of system to change a value of a context item via a pull down menu of context panel . In another example illustrated in the user may operate a pointing input device to select France within module . If no such input has been received flow returns to and cycles as described above while waiting for user input to either lock a module or to change a value of a context item.

Continuing with the example flow proceeds to to issue an instruction to change the value of the context item. With reference to the embodiment of module may be represented by module because module includes producing logic but does not consume context items. Therefore may comprise issuing an instruction from module via the context producing API to change the value of the Region context item to France .

Next at the instruction is received by the selected context services provider and a notification of the changed value is issued therefrom. The notification is received at at zero or more modules which are associated with the context item. Steps and may therefore include reception of the instruction at context services provider and transmission of a notification of the changed value from context services provider to modules and .

The notification might be transmitted to all modules of a composite or may be transmitted only to those modules which have indicated an interest in the particular changed context item. Moreover the notification might be received by all modules of a composite or may be received only by those modules which have indicated an interest in the particular changed context item. If the notification is transmitted to and received by a module which does not use the particular changed context item the notification may simply be ignored.

Although any communication mechanism may be employed at some embodiments utilize a publish subscribe protocol. For example a consuming UI module may subscribe to a particular set of context items and receive only notifications from the context services which are related to changes in values of those context items.

The following illustrates one example of a context consuming API implementing a publish subscribe protocol.

In operation when a notification of a change in a value is published the API will be triggered based on its registered TOPIC on the context bus using INTEREST TOPIC. The registered Interest for DATA and TAGS is logic implemented by the consuming module to go through the Context Item property to filter consumer.doContextAction Context ctx .

The following code snippet may be used to implement a context producing API under a publish subscribe protocol.

The functionality of each unlocked module associated with the context item is executed at based on the notification. The functionality may include one or more of data generation data processing data storage e.g. temporary persistent data reception data display and or other functions. In some embodiments execution of the functionality of at least one unlocked module associated with the context item may simply comprise determining that no action is to be performed based on the notification.

Flow returns to from as proceeds as described above. Values of other context items may be changed during subsequent cycles of steps through .

In some embodiments a user may add a module to an existing composite. illustrates the addition of module . After the addition of module process may proceed through steps through as described above.

Module consumes context items Region Product and Year and also produces context item Year in response to user manipulation of menu . Therefore modules and of may be represented by modules and of respectively.

Context communication bus may support the above described publish subscribe protocol and may therefore provide the sole means of external communication for context consumers context producers and context consumers producers of rich client . Context client manager delegates context services for the context consumers context producers and context consumers producers and also coordinates context aware communication within a composite visualization.

Application server may serve applications in addition to that described herein. Context manager provides a single entry point for client to access context services that are running on server . These context services may include context lifecycle management context sharing and context data service .

Context lifecycle management allows a composite visualization to create read update delete CRUD both context and context items through a well defined CRUD API. Context sharing provides functionality to persist a well defined context and specify how a context can be shared among users other visualizations. For example a well defined context may be saved and shared for creating a new composite visualization including UI modules reflecting the shared context. Context data service provides the functionality described above with respect to context services provider .

Context repository of persistency layer provides application server with storage and retrieval of context i.e. a set of context items via context persistency API . Each context may be persisted with a unique name which can be used for sharing and retrieval. Context data type registry allows for the registration of context items to be associated with contexts and available during creation of a composite visualization.

As described above embodiments are not limited to any particular behavior of modules within a composite. For example the functional logic of a module may be executed to perform any function based on any type of change or lack of change to the value of any context item. Similarly the functional logic may implement any behavior for producing values of one or more context items.

According to one example shows composite including module within canvas and specifying three context items in context panel . Module unlike the other modules described herein does not discard a previous value of a context item with which it is associated upon receiving a notification of a new value. Rather module uses both the previous value and the new value to generate a visualization.

Specifically module consumes context item Year with an initial value of 2006 in . Module therefore generates a single column chart for year 2006. The user may then manipulate context panel to change the value of Year to 2007 as shown in . Module receives a notification of this change and as also shown adds another column corresponding to the new context item value.

Context item Region is defined as a group context item for each of Groups and . If the user changes the value of Region in context panel i.e. at the root level modules and will not be affected by that change. Modules and may therefore be considered to have context autonomy with respect to the Region context item at the root level. If the user changes the value of Region using menu then only modules and will react to that change. Moreover if the user changes the value of Year at the root level all modules within composite will consume the new value i.e. if they are associated with the Year context item and behave accordingly.

Groupings as shown in may reduce complexity and increase comprehension of composite . Visually the user can easily identify the context boundaries for the Region context item and understand how the context item affects the different modules.

Embodiments described herein are solely for the purpose of illustration. Those in the art will recognize other embodiments may be practiced with modifications and alterations to that described above.

