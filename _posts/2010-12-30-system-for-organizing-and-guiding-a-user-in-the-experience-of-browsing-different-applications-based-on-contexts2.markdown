---

title: System for organizing and guiding a user in the experience of browsing different applications based on contexts
abstract: The present invention provides a system that enhances the experience of using a portable device such as mobile phones, smart phones, Personal Digital Assistants PDA etc. To improve the user experience in the use of a portable device, techniques are used for “context characterization, i.e., from a range of conditions possible to detect by the system, such as time (date/time), current location, motion, etc., as well as the historical use of the device, a certain grouping of actions and settings, called “context” are selected automatically or manually, modifying and setting from that moment the way of user interacts with the device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09575776&OS=09575776&RS=09575776
owner: SAMSUNG ELECTRÔNICA DA AMAZÔNIA LTDA.
number: 09575776
owner_city: Campinas-São Paulo
owner_country: BR
publication_date: 20101230
---
The present invention relates to the field of human interaction with mobile devices more specifically concerns a system to organize and guide a user experience in navigating between different applications based on context.

The document U.S. 2008 0201350 Context Based Information Retrieval published on Aug. 21 2008 proposes a system and method for searching contextual information. The term context in accordance with the teachings of said document U.S. 2008 0201350 does not follow the same definition of the patent described here because it represents a combination of meta data or tokens with other existing data. The object of said system is the medical field particularly through diagnostics using images. In this field the devices responsible for obtaining the images produce a huge amount of data that includes the function performed and the day on which the action occurred errors important and or critical parameters numerical results from sensors or a combination thereof. The document U.S. 2008 0201350 therefore offers an advanced search technique upon these data to optimize and simplify the detection of failures in maintenance of machines using the context of the meta data.

The document U.S. 2004 0172460 Context Filter published on Sep. 2 2004 also proposes the assignment of meta data to pre existing data. In particular the document U.S. 2004 0172460 describes methods for quickly searching to find the data through the metadata. The document U.S. 2004 0172460 however after the detection of context specifies only a pointer to the context in a database. In that document U.S. 2004 0172460 the end result includes a list of concepts common to the context identified.

The document U.S. 2008 0005679 Context Specific User Interface published on Jan. 3 2008 proposes techniques that modify the operation of a device based on the context in which it is inserted. Examples of contextual attributes include the physical location of the device an accessory connected to the device some attribute related to connecting to a data network any attribute linked to the behavior identified of use of the user the execution state of other applications and or the state of the user. Based on these contextual attributes the software undergoes changes in order to adapt to the current context with all configuration done through the contextual attributes of a remote computer not forcing the user to make changes on the device itself.

The document U.S. Pat. No. 7 792 795 published on Sep. 7 2010 presents a centralizing and pooling of resources serving as a facilitator of access to data from other applications. Additionally the term context in U.S. Pat. No. 7 792 795 refers only to data such as name address attributes of a person a user s preferences device data e.g. GPS location and so on. However there is no reference to the control of hardware components.

The present invention provides a system that enhances the experience of using a portable device such as mobile phones smartphones Personal Digital Assistants PDA etc.

To improve the user experience in the use of a portable device techniques are used for context characterization i.e. from a range of conditions possible to detect by the system such as time date time current location motion etc. as well as the historical use of the device a certain grouping of actions and settings called context are selected automatically or manually modifying and setting from that moment the way of user interacts with the device.

For the purposes of the present invention context is defined as a specific group of actions and settings that once selected defines the mode of user interacts with the device.

It is important to note that these characterization techniques are dynamic i.e. they are subject to change and or upgrades either through artificial intelligence techniques present in the device but also by the user the latter attending primarily to the fine adjustments according to the preferred embodiment of the invention.

The present invention also provides a flexible architecture and modular software which includes a well defined set of methods for integrating the concept of context with a system comprising 1 access manager and centralizing to resources acquisition module and automatic information processing by the portable device Artificial Intelligence module for associating metadata tags Tagging Module Mobile Web Server information manager through which the web interface extended manager data Backup Restore module and observer of event sources Observers .

The present invention provides solutions to usability and graphical user interface that organize and guide the user experience in navigating between different applications on clear and well defined contexts. Once identified and assumed the context a set of metadata tags are assigned to all events generated by the portable device.

This portable device allows a context is defined by user where settings and behaviors are attributed to events and metadata tags . Settings can also occur automatically. Thus the portable device demonstrates different executions based on contexts specifically assigned by the user or automatically identified by an artificial intelligence engine.

This portable device captures data automatically from the environment in which it is in operation the data capture can be done through different sensors and applications on that device as well as the events generated by actions that the user runs the device over the day.

This portable device also includes a web server that allows configuration of the same from an external browser. This component allows you to organize information from the device following the directives given by the user in the web service. It is also allowed to access and extract all data from that device using this same server. Thus the user has the option to access the data through a computer modify and synchronize data with a PC and or a remote web server providing a more comfortable alternative to the user.

This portable device can also optionally communicate with a remote server on the web securely to synchronize the information on profiles and preferences settings and data in a unique account of the user. This communication will allow the updating of configuration information preferences and user data on the remote Web server if the user updates content on his portable device as well as it allows users to download ready contexts available in remote web server and shared by other users.

The present invention also allows restoring and backup information contained in said portable device such as images videos contacts audio programs contexts of use maps and tags. In a particular way this backup restore is done using the information manager through web interface extended manager .

The way the architecture developed is one of the different aspects of the present invention. Instead there are several different applications that work individually with a usability feature having a centralized and scalable environment capable of adding new features and let them all communicate and interact. Thus features such as backup and restore extended device management via the web context management among others are really only snapshots of a whole which are provided by the architecture.

The hardware needed to bring the system of the present invention is a portable device and its main features are illustrated in . The CPU Central Processing Unit is responsible for executing the necessary instructions for the management of all sensors and device features and evaluates events and take actions based on defined rules. For example the camera captures images and gyro or accelerometer can set the orientation of the device and the type of movement. The storage medium serves to store information and data including location sequence of events among others. The hardware also consists of information input devices and audio components. Through some connectivity component can communicate with the application and the services provided of synchronization and sharing of contexts. The display means is required for viewing by the user of the change of context.

The architecture of the present invention represented in comprises the following main components Core Artificial Intelligence Tagging System Mobile Web Server Extended Manager context Creator Observers and Backup Restore. Each will be described below.

The Core is the central component of the architecture. It is what makes the interface between the components and features of portable devices such as databases and sensors. The Core was developed with the main objective of isolating the remaining portions tagging system mobile web server extended manager context creator observers and backup restore from accessing these resources thus ensuring that new added features to the devices can be used by those who share the architecture.

Another feature of the Core is to ensure that any changes to the application programming interface Programinmg Application Interface API of resources of the device do not impact the applications that access architecture. This reduces the work of preparing the applications for each API version.

The Core uses a service based policy all components or applications that communicate with it do it through the consumption of one of the many services provided by the same.

Observers are responsible for the sources of device events such as clock accelerometer gyroscope camera ring tones or use the applications installed on the portable device and others that may also exist. Observers analyze the actions taken by users and inform the Core so that it performs the required actions e.g. adding a tag to a photo registering the application use in a log .

The architecture allows the observation of any feature of the device however you can individually choose which events are monitored avoiding thus unnecessary consumption of resources of the device.

Mobile Web Server provides an environment where applications created using web technologies are able to be arranged in the portable device e.g. servlet . Just as a web server on a personal computer it allows multiple applications to be installed and used simultaneously by multiple users. These applications in turn can be accessed through any device that has a web browser connected to the portable device via cable or data network.

Besides being responsible for allowing the use of web applications the server is still responsible for access and security of information carried. For this it deploys policies limiting access to applications and secure traffic information.

The extended Manager is a web application hosted in webserver of the portable device that allows to manage information and resources of the device through a web browser. Its purpose is to promote a new form of user interaction and make the experience of using the portable device more pleasant.

Because the architecture has a tagging system application through its access to the Core is capable of filtering using this feature in addition to presenting information on a map indicating where they were created or added to the portable device e.g. capturing of a photo or adding a contact .

A context is defined by the user in which settings and behaviors are attributed to events and metadata tags . Thus the portable device shows different executions based on the context identified or assigned by the user. Thus value is added to existing information to automatically associate all relevant events and actions in the portable device to metadata tags .

The Context creator is the component that allows you to manage the contexts. You can perform from the process of creating and installing to the context activation and configuration. This component can be accessed through an application on the portable device the computer accessing the service from the context creator by the browser on the portable device or through a widget application.

The contexts typically represent situations such as gym school car work or home but it can represent a specific situation such as a lecture a movie or an event. According to the preferred embodiment of the invention there are two types of contexts the generic which is created by users through the Creator and Premium context that are contexts more advanced and usually take the form of applications.

Each context can represent a range of behaviors content and applications that are commonly used in these situations. Thus allowing a configuration and faster access to user needs in each of these moments.

Behaviors are actions that the context will run on the portable device while being activated and can be settings of the device as changing the state of Wi Fi Bluetooth Wallpaper and volume or linking Tags to information generated by the portable device.

The content is information that will be linked to the context such as photos videos music documents events and contacts. This capability to bind context information is important for the exchanging information between users. An example of this functionality is a context of a lecture which could be linked to the day that the lecture will take place along with a presentation photos and texts used in the lecture.

The context also allows grouping application which represents a faster access to these applications when using a context. Another important advantage of this function is that the exchange between users you can also share applications that are used in this context. The application file is not shared but the address where the set of information applications is stored which allows the user that does have it to download it.

Activation of contexts can be done manually or automatically. The user can choose to activate a context when you need it or make your schedule for it to be activated in specific situations such as in reaching an area at a specific time or date in connecting to a specific network or in activating a specific accessory to the device.

After the creation of contexts it is possible to export them to share with other users. The file generated in the export process contains all the content present in context as behaviors content and applications.

In the process of installing of a context all their information is reported to the user such as name and description behavior content and applications. When you install it it is available for activation by the user.

One of the important features of the architecture of the present invention is a backup and restore system. Commonly such tools need an external software to be installed on your computer. Another common feature is that these tools are only able to backup and restore all information without allowing the user to individually select what he wants.

The system provided by the architecture described herein is available in the portable device and can be accessed through the extended Manager and does not require the user to perform any manual installation. It also allows all information likely to participate in a backup or recover can be chosen individually by the user.

Backup to the portable device is an activity that consumes battery RAM memory and storage space. The proposed backup method uses a mechanism that checks the form that the user is using to access the backup feature. If it is by a web interface and the machine that is accessing has the necessary requirements the system installs the backup application automatically in the user s machine otherwise it uses the resources of the portable device itself.

1 All that is required for the backup is on the portable device. This does not oblige the user to be in possession of an installation CD so that he can make his backup 

2 If the machine you are accessing the system it is possible to access it through the device itself does not have the ability to perform the necessary procedures the entire responsibility of the process is transferred to the device 

3 If the machine that is accessing the system has the capacity to perform the necessary procedures all responsibility will be transferred to the same. The great advantage is that it will consume much less resources and processing power.

The generated file has been thought in order to be independent of the operating system on which it was created. Thus it is possible to generate a backup on an operating system and import it into another. The restore method is similar to backup. If you run a restore the system informs the user that exists within the file and the user can choose what information they want to restore. The system takes care to prevent duplication of data.

The architecture allows essential information e.g. photos videos contacts music messages calls of the portable device to be associated with a metadata tag . The advantage of adding a tag to information is the ability to recover more quickly. shows the flow of operation of the tagging system as explained below 

The architecture of the present invention has a module that allows suggesting to the user events or situations that may be useful to him. To give the portable device the ability to collect environmental data at regular intervals of time a mechanism for Artificial Intelligence IEA is embedded in the device.

The input data will be obtained by capturing the sound when taking a picture the current time the device ID and signal strength GPS receiver compass light sensor and on any input sensor and information online or offline or device available.

The record of the actions taken by the user of the device will also be interpreted as input data for the mechanism of Artificial Intelligence IEA .

After a preset amount of data that were acquired the IEA will process it and the core will have one or more actions.

Each time a process is done the device will update knowledge of EIA and the results makes the decisions of the next iteration more accurate and linked to the user s actions.

This process becomes more accurate for each new interaction with the device has with the environment and the user learning from each interaction how to act better and more efficiently. Over time the device will be able to predict almost the next interaction the user will run and will be promptly prepared for it.

By analyzing the volume ringtone color settings wallpaper a rhythm of walking external sounds etc the IEA can for example identify the mood of the user.

Suggestions that the IEA could make the user for a better experience when using the portable device are for example 

If the IEA considers that the device is at risk of being stolen by sounds and patterns of accelerometer it may allow the password prompt to unlock the phone. If the situation in which the device detects that it is being stolen becomes common and the user has to unlock it regularly the IEA will store it and the device will prevent the lock on these situations again.

Although a preferred embodiment of the present invention is shown and described those skilled in the technical will understand that various modifications can be made without departing from the spirit and scope of the present invention as defined in the appended claims.

It is also expressly stated that all combinations of elements that perform the same function in substantially the same way to achieve the same results are within the scope of the present invention.

