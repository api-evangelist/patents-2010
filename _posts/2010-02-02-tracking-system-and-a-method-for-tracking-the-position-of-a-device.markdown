---

title: Tracking system and a method for tracking the position of a device
abstract: For allowing a reliable and fast determination of the position of devices with a high degree of privacy preservation a tracking system for determination of the position of devices within a wireless network is claimed, wherein the tracking system is including a number of tracking stations, each tracking station being adapted for wireless communication with at least one device. The system is characterized by a management unit for control of a tracking activity of the tracking stations. Further, an according method for tracking the position of a device within a wireless network is claimed, preferably for use with the above mentioned tracking system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08676228&OS=08676228&RS=08676228
owner: NEC Europe Ltd.
number: 08676228
owner_city: Heidelberg
owner_country: DE
publication_date: 20100202
---
The present invention relates to a tracking system for determination of the position of devices within a wireless network wherein the tracking system is comprising a number of tracking stations each tracking station being adapted for wireless communication with at least one device. Further the present invention relates to a method for tracking the position of a device within a wireless network wherein the tracking system is comprising a number of tracking stations each tracking station being adapted for wireless communication with at least one device.

Tracking systems and methods for tracking the position of a device within a wireless network of the above mentioned type are known from the state of the art. For example U.S. Pat. No. 6 717 516 B2 is showing a tracking system with multiple tracking stations and zones for tracking. Further from U.S. Pat. No. 6 674 403 B2 is known a tracking system in a wireless network. The known tracking system uses knowledge of adjacency to improve the location and position determination.

Further known tracking systems determine the position of devices by scanning for a radio signal emitting from that device utilizing multiple tracking stations. Using various forms of triangulations and trilateration the device position can be determined. But this requires the tracked devices to emit a radio signal. Usually this radio signal can be measured by not authorized listeners thus providing several privacy and security problems.

Tracking and positioning systems are used to determine the location of users and the proximity of users devices. There is a huge commercial interest in this type of supporting services. Unfortunately there are great problems with privacy. These problems are a major reason preventing the large scale use of location proximity. Further technical problems are issues with costly deployments speed of measuring the information and accuracy of the measurements e.g. environment condition like indoor outdoor.

Tracking systems sometimes use existing wireless technologies invented for non tracking purposes e.g. Bluetooth UWB Ultra Wideband IEEE 802.15.x for tracking. These wireless networks provide means for discovering devices in their vicinity. This is usually a needed first step in establishing connectivity. For example Bluetooth in INQUIRY mode allows finding visible devices in the vicinity. This mode can be used for tracking systems without introducing new hardware devices. But they introduce even more security privacy risks as mentioned above as they use methods designed for different purposes and not having security privacy in mind. Furthermore the method is slow and might therefore not be suitable for some application areas.

 Invisible devices i.e. devices not in discovery mode cannot be found with this method. As said devices want to be invisible in order to protect the privacy of their users. Nevertheless especially in Bluetooth but probably also in other existing and future wireless technologies when initial contact has been established once a device can check the availability of an invisible device in its proximity through e.g. trying to invoke an operation such as establishing a L2CAP Logical Link Control and Adaptation Protocol connection and do a service discovery in the Bluetooth case. This is sometimes called pinging the device though it is not an IP ping and technically not really a ping.

Furthermore device discovery and device pinging can be used for detecting a device in proximity with various characteristics. For example a Bluetooth ping is much faster then a Bluetooth discovery operation 0.8 2 s seconds compared to 7 20 seconds see http www.sigmobile.org mobisys 2006 posters Handurukande.pdf . This gives further reasons to use the ping operation speed of discovery adds to the fact that the device can stay in invisible mode. On the other hand the discovery mode can discover several near by devices at the same time.

Given the increasing need for privacy and hiding devices future wireless networks will have even more and strict security mechanisms built into them. One example is a changing MAC address in order to support a Virtual Identity see Daidalos V ID concept. Utilizing this technology above mentioned detecting of invisible device might get even more complicated and needs sophisticated support systems.

In summary current state of the art wireless tracking systems are usually utilizing a discovery mode violating the user s privacy and usually allowing everybody to scan for devices in the vicinity. Some problems related to this are

It is an object of the present invention to improve and further develop a tracking system and a method for tracking the position of a device within a wireless network for allowing reliable and fast determination of the position of devices with a high degree of privacy preservation.

In accordance with the invention the aforementioned object is accomplished by a tracking system comprising the features of claim and a method for tracking the position of a device within a wireless network according to claim . According to claim the system is characterized by a management unit for control of a tracking activity of the tracking stations. According to claim the method for tracking the position of a device within a wireless network is characterized by controlling of a tracking activity of the tracking stations by a management unit.

According to the invention it has been recognized that a fast and reliable determination of the position of devices is possible by a tracking system which is comprising a management unit for control of a tracking activity of the tracking stations. By such a management unit an individual and selective control and activity of each tracking station is provided. Further the inventive tracking system and method do not rely on periodically broadcast and visible to all radio signals. Instead the system and method can ping the devices it knows about. This will reduce overall traffic and will result in a fast detection and determination of the position of devices. By the possibility of using the ping mechanism security privacy risks are avoided. Further the inventive system and method can use existing widely used technology such as Bluetooth technology.

Within a preferred embodiment of the invention the tracking stations could be adapted for pinging of a device and or for invoking an operation of a device. Using the pinging mode the devices tracked by the tracking stations can stay hidden and must not be put into discover mode.

Preferably the management unit could be adapted for scheduling which device shall be pinged by which tracking station preferably within which time interval. Thus not all tracking stations have to track all devices and a very selective tracking process is possible saving system resources. Such a scheduling can be dynamically adapted over the time.

Preferably the scheduling could be based on previous sightings and or on the importance of previous sightings of the respective device and or on the necessary accuracy or QoS Quality of Service . This could include learning some movement patterns and the respective probabilities. As a result the tracking system and method are using wireless discovery and pinging with a management unit that schedules discovery or ping mode.

Within a preferred embodiment the scheduling could be based on a potential walkway of the respective device. Based on the potential walkway the management unit could activate tracking stations which are near such a walkway or within such a walkway.

Within a preferred special operation the tracking stations could be controlled by the management unit for immediately pinging a definable device. In other words the management unit could ask the tracking stations to immediately ping a device. As a result a highly reactive system can be realized.

Within a further preferred embodiment the management unit could comprise a registration module for registering a device and or an identity and or an access policy. A user can register multiple devices and or identities by such a registration module.

Further the management unit could comprise an activation module for activation and or deactivation of tracking of a device. Utilizing an activation module users can activate and deactivate tracking for a registered device. By the registration and activation the user can provide an opt in for enabling tracking of the respective device.

Preferably an access policy and or a priority and or a definable QoS Quality of Service is determinable preferably as part of an activation of tracking. Such a determination of characteristics of the tracking as part of an activation of tracking will provide a very simple handling of the tracking system and a simple method for tracking the position of the device.

Regarding QoS the users will most likely not specify directly the QoS parameters at measurement time but rather a user oriented range of parameters e.g. ensure guaranteed detection at walking speed ensure guaranteed detection while reading sign ensure guaranteed detection while staying in area . These two modules are also used to support future wireless technologies with changing MAC Media Access Control addresses.

Preferably the management unit could comprise an access module for permitting access by services to a tracking information.

Within a further preferred embodiment the management unit could comprise a mash up module for receiving events and or information from other systems or sources. Further such a mash up module could provide for communicating with other systems or sources. A mash up with external other systems could improve the tracking behaviour based on observations by the other systems. Such other systems or sources could comprise a preferably GPS based positioning system a cell phone and or a calendar which can generate relevant events.

The mash up module could further comprise an API Application Programming Interface with access control.

Within a further preferred embodiment of the invention the management unit could comprise a learning module for predicting a movement pattern or a potential walkway of a device. Such a prediction could be used for scheduling the tracking stations relevant for the device.

Further preferably the management unit could comprise a communication module for communication with tracking stations.

Within a very simple embodiment of the invention the management unit could be connected to the tracking stations by a wireless or cable connection. The specific realization of the connection is depending on the individual application case. Within a further simple construction the management unit could be integrated in a tracking station.

With regard to a very fast operation of the tracking system each tracking station could have several scanning queues that are scheduled with different priorities and or timing. The tracking management unit could make sure that desired QoS for detecting devices is fulfilled. The management unit could insert the devices to be scanned into the right queue of the tracking stations.

For providing a widely usable system each tracking station could support multiple radio interfaces and or multiple interfaces of the same technology.

Preferably the tracking system could be realized as part of a display system an indoor navigation system or a surveillance system. However other applications are possible.

By the opt in of users into the tracking system a high level of privacy is realized. Especially for future wireless networks with changing MAC addresses this opt in mode is a very important feature. As also the ping operation is taking time the amount of devices that can be pinged is limited. As a consequence the amount of devices that can be discovered is limited.

An advantage of the tracking management system and method according to the present invention is that it could manage the ping activity in such a way that the management unit could perform high precision measurements for devices already discovered in a specific area and or needing close monitoring while it occasionally checks for devices coming into a definable range. For that it could utilize information about the geo position of tracking devices to estimate where a given device might be heading. For tracking stations along a definable or predictable walkway of a device the device being tracked could be added to a queue of potentially arriving devices at said tracking stations. In such a way the system can track a higher amount of devices while maintaining good QoS for the devices close by.

Preferably the tracking could only be started when a positioning system is providing the information that the device might come into a definable range. Thus the tracking system could benefit from events from other systems. For example it could start the scanning process only when a GPS based positioning system tells the tracking system that the device is close by and might come into the tracking range. For that a variety of mash up APIs could be used.

Within a further preferred embodiment the management unit could schedule the time needed to perform one or more trackings of devices. In such a way a very effective tracking is possible.

As the amount of devices which can be tracked by one tracking station is limited due to the time needed for detecting the device the invention is providing a system and a method that optimizes the pinging of a device by respective scheduled tracking stations. In other words the scale of system can be balanced against speed of discovery. As devices are scanned or individually pinged a single device is discovered fast but detecting many devices introduces scaling problems as each device needs to be pinged individually. Such scale problems can be counteracted with multiple tracking stations and intelligent scheduling of the pings. This is one advantage of the present invention and the control of a tracking activity of the tracking stations by a management unit.

The inventive tracking system is of high commercial relevance for all types of location and proximity based systems. This includes digital signage location based advertisement guidance system personalization system e.g. for IPTV and many more.

For a realization of the tracking system a variety of existing technologies in existing devices can be used. This allows a cheap implementation of tracking stations e.g. on the basis of Bluetooth technology.

The inventive system and method are allowing for preserving privacy by avoiding putting devices into discover mode. Further it is possible to control who gets the tracked information based on user s policies. For privacy reasons users can be asked to opt in for being tracked. In this case known properties of their devices can be used.

The inventive system and method allow fast detection of devices in case such a high QoS is needed. The tracking system can intelligently schedule the activities of the various tracking stations in order to scan more devices while preserving privacy and speed. By learning algorithms the system can learn the expected behavior of users in order to improve prediction and a prediction based scheduling of tracking stations.

Further a mash up with external systems is possible to improve the tracking behavior based on observations by the systems. These external systems can be location based systems calendar systems or other types of systems generating relevant events.

Such influencing of the tracking management can be realized by the mash up module that allows receiving events or information from other systems. This could be for example a GPS based positioning system that tells the tracking system that a user is coming into its vicinity. It could be the cell phone detecting a cell id of a base station close the tracking area. Or it could be a calendar telling the tracking system that the user is now scheduled to arrive in the area. Using the Mash up module the tracking system can improve scheduling of the tracking actions based on further knowledge about the user. Usage of the Mash Up module can be organized during registration and activation.

The invention is providing a tracking system and method with the following summarized preferred features and properties 

The tracking system or method could utilize wireless discovery and pinging with the following important features 

In addition to that data privacy laws may be introduced that restrict what is allowed to do with blind discovery or user tracking . But most of the laws allow tracking in case the user has consented to being tracked. This is another reason for requesting an opt in module which could be realized by a combination of a registration and activation module.

The tracking station of is comprising different modules for tracking system communication for tracking schedule and for tracking device management. Further there are provided three tracking modules.

The present invention can be used to enhance a supermarket or shopping mall. Users are provided with a service that enables them to first define their shopping list. Second when they go to the supermarket the supermarket provides a system that navigates the user to the desired products and informs him about special offers.

For that the users send their shopping list to the supermarket including their tracking activation. When arriving at the shop the tracking system starts monitoring the user. For optimization the tracking system was set up in such a way that the shop is divided into several zones each of them tracked by one or more tracking stations. The tracking management system or unit knows the zones and knows from previous measurements that when users are tracked by a station at the edge of the zone that there is a certain likelihood that they move into another zone. For that case it instructs the tracking stations in that other zone to scan for the devices at a lower schedule. When sighted in the other zone the tracking management system or unit removes the devices from being tracked in Zone A and instructs the tracking stations in Zone B to ping the devices at a higher rate.

The service the tracking is used for might require a better QoS of the tracking in certain areas of the shop to ensure that a service is reactive and well received by the users. For that case the tracking system can decide to increase the scan rate once the user enters specific zones of the shop.

In this scenario a visitor schedules a meeting at a fair booth. For supporting measurements the user allows the system to track him and also gives access to his calendar saying when he plans to be at the booth. At the scheduled time the tracking system looks for the user and informs the hosting party about the user. This is an example for using the mash up module.

In this scenario tracking stations might be deployed at each booth and the management system might be operated by the fair management.

The Tracking Management System will run on a server machine that is connected to the network wired or wireless inside the supermarket. Several tracking stations will be set up e.g. at the entrance and exit areas at the cashier in front of in store displays close to highly searched shelves. The tracking stations will be equipped with

Standard mobile phones with Bluetooth are handled by Bluetooth special mobile phones with NFC or Customer Loyalty cards with NFC are handled by the NFC reader. In areas like entrance and exits the tracking stations are equipped with multiple Bluetooth readers to increase the scanning capacity.

The Tracking Management System is also running a Web server and an application that allows customers to register their devices using the Registration module . Furthermore the application enables customers to provide an edit of a shopping list. When finishing the shopping list the customer can activate the tracking system and set a specific time when he will be at the shop.

Furthermore he activates a GPS tracking application on his mobile phone that sends the GPS coordinates to a server on the Internet. He also instructs that server to send a WithinArea event to the shop using the Mashup module in case the GPS coordinates are close to the shop.

When entering the shop activated users are detected and tracked throughout the system. Their position information is exposed to the shop navigation system which leads the user to the products on his shopping list.

In this scenario the end user is equipped with either Bluetooth or UWB systems running a new type of MAC that can change its MAC addresses as needed. This new feature might be included in future wireless standards to protect users privacy. The fair system provides the tracking management unit and the tracking stations. They furthermore provide a Meeting Facility in which participants can make an appointment and get directions for meeting at the fair. As part of the system setup end user register their identity and the devices with the right MAC for the selected identity with the tracking management system and allow the meeting facility access to the information.

When the time of the appointment comes close the Meeting Facility service tells the Tracking service to track the persons at higher QoS. It then guides them to meet.

Many modifications and other embodiments of the invention set forth herein will come to mind the one skilled in the art to which the invention pertains having the benefit of the teachings presented in the foregoing description and the associated drawings. Therefore it is to be understood that the invention is not to be limited to the specific embodiments disclosed and that modifications and other embodiments are intended to be included within the scope of the appended claims. Although specific terms are employed herein they are used in a generic and descriptive sense only and not for purposes of limitation.

