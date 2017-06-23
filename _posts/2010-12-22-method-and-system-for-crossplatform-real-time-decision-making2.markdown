---

title: Method and system for cross-platform real time decision making
abstract: According to some embodiments, a system includes a business data provider, collaboration platform, a user client device, and a web application server interfacing with the business data provider, the user client device, and the collaboration platform. In some embodiments, the user client device communicates with the web application using a markup language to request and receive business data and collaboration data from the business data provider and the collaboration platform, respectively.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09569542&OS=09569542&RS=09569542
owner: SAP SE
number: 09569542
owner_city: Walldorf
owner_country: DE
publication_date: 20101222
---
Some embodiments relate to a web application. More specifically some embodiments provide a system and method for a web application to provide contextual business data across a plurality of platforms.

A number of presently developed and developing computer systems are directed with providing a user access to large amounts of data. However many such systems are directed to individuals working in an office environment having the luxury of time to search for an answer as assisted in their search by a powerful computing device. In contrast many people find themselves increasingly in need of information wherever they may be. Many people may have a need for business related data notwithstanding whether they are in an office or not since business opportunities may happen suddenly and unexpectedly.

Likewise there is an ever growing amount of unstructured communication and related information. Such unstructured information may encompass emails text messages social networks instant messages informal team discussion groups and other types of communications. While the data may be referred to as unstructured the knowledge and information conveyed in some unstructured data is helpful both socially as well as in business contexts since business communication does not happen in formal channels alone.

Accordingly a method and mechanism for efficiently requesting and responding to requests for structured and unstructured data in a relevant context and for a wide variety of platforms are provided by some embodiments herein.

In an effort to more fully and efficiently use the resources of a user a system and methods are provided to facilitate the retrieval and sharing of contextual business data as well as the collaborative exchange of information.

In some embodiments communication between WAS and user client devices may be based on the use of a markup language. In some embodiments HTML 5 HyperText Markup Language may be used to communicate with a wide variety of the user client devices. Communication between user client devices and WAS may be possible with any of the user client devices such as for example smart phone eReader netbook laptop tablet and other devices supportive of HTML 5 including devices having web browsers that support HTML 5. Additionally the use of HTML 5 as the communication protocol also means user client devices need only run a browser compatible with HTML 5 in order to communicate with WAS .

Business data providers may comprise for example an enterprise service platform a database management system and a private company that specifically houses and manages business data. In some embodiments business data providers may include web based sources of information such as for example web based search engines. In some instances business data provided by business data providers may relate to a particular industry or industry segment. In some instances business data providers may include data sources such as social networking sites. An example of business data may include customer relationship management CRM data and business reports. In some embodiments business data provided by business data providers may include business analytics data.

Collaboration platform may provide an integrated framework of software components including messaging e.g. email instant messaging text etc. shared calendaring and scheduling sharing of contacts synchronizing of team notes and files. In some embodiments many users may simultaneously gather and collaborate in the space of the collaboration platform .

The data accessible through WAS may include both structured data and unstructured data and may vary from formal hierarchical analytical reports from business data providers to records of team members informal comments regarding customers from collaboration platform .

At S a query for the data associated with the customer is generated. Moreover the query is executed at S. WAS queries the business data provider for information related to the customer.

At S the business data associated with the customer is received from a business data provider . While business data relating to the customer has been retrieved the business data remains to be filtered according to the location of the user client device . At S a location filter is applied to the result of the querying. The location filter corresponds to the location of the user client device.

At S WAS may provide the filtered business data associated with the customer to the user client device. In some embodiments the filtered business data is provided to user client device in HTML 5. Since the user client device supports HTML 5 the filtered business data associated with the customer may be efficiently rendered on the user s smart phone.

On the client side the location of the customer and the current location of the user client device may be rendered in an interactive map on the user s smart phone or other applicable or compatible device. Being an interactive map the user may be able to zoom in and zoom out on the map to provide the user with a different perspective of the data presented therein.

In some embodiments further filters may be applied to the retrieved customer business data. In some instances business filters may be applied to the retrieved business data to further refine the data for use by the user e.g. sales manager . is a flow diagram of a process to further refine the business data retrieved from the business data providers. At S WAS receives business data search criteria from the user client device . The filter or search criteria may include for example a distance the customer is to from the user an industry the customer is in amount of revenue for the company a number or type of open calls a number or type of open opportunities and possibly other criteria.

In some embodiments filtering on business data may be accomplished by WAS while is some other embodiments the filtering on the business data may be performed by querying business data provider for the filtered results. In some embodiments filtering on the business data may be performed by a combination of WAS and business data providers .

Returning to the process of the business search criteria is applied to the previously retrieved business data to produce a second or further filtered data result at S. At S WAS provides the second filtered data result to the user client device. The WAS passes the second filtered result to the user client device in the markup language e.g. HTML 5 .

In some embodiments system may provide a mechanism by which a user may interact with a collaboration platform. Referring to S the web application server receives a request from a user client device for collaborative business data associated with a customer of a user. In accordance with some aspects herein the request for the collaborative business data is provided in a markup language. In this manner the communication between the WAS and the user client device is independent of the particular user client device. It is noted that the request may include an identifier of the customer or subject of a collaboration activity. In some embodiments communication between user client device may be handled directly by the user client device based on logic from WAS .

At S a request for the collaborative business data associated with the customer or other entity including the identifier of the customer is sent to a collaboration platform. Continuing to S the collaborative business data associated with the customer is received from collaboration platform in reply to the request.

At S the collaborative business data associated with the customer is provided by the web application server in the markup language to the user client device.

At S the new entry to the collaborative data from the user client device is served or sent to collaboration platform by the web application server .

As demonstrated by the methods and examples herein WAS handles requests from user or consumers as represented by the user client devices . In handling the requests WAS responds with appropriate Java Script and HTML generated to the multiple types of user client devices . The methods and processes herein also serve to highlight the ability of WAS to expose both structured and unstructured to the user client whether originating from a business provider or a collaboration platform respectively.

Processor communicates with a storage device . Storage device may comprise any appropriate information storage device including combinations of magnetic storage devices e.g. a hard disk drive optical storage devices and or semiconductor memory devices.

Storage device stores a program for controlling the processor and query engine application for determining constructing and executing queries. Processor performs instructions of the programs and and thereby operates in accordance with any of the embodiments described herein. Programs and may be stored in a compressed uncompiled and or encrypted format. Programs and may furthermore include other program elements such as an operating system a database management system and or device drivers used by the processor to interface with peripheral devices.

In some embodiments such as shown in the storage device stores a database to facilitate the determination and construction of queries. The query database may include data structures rules and conditions for determining a query based on user interface selections as described herein.

Each system described herein may be implemented by any number of devices in communication via any number of other public and or private networks. Two or more of the devices herein may be co located may be a single device or may be located remote from one another and may communicate with one another via any known manner of network s and or a dedicated connection. Moreover each device may comprise any number of hardware and or software elements suitable to provide the functions described herein as well as any other functions. Other topologies may be used in conjunction with other embodiments.

The systems and methods herein have been described in some instances in the context of an interactive communication between a user and a customer. It should be appreciated that the systems and methods herein may be utilized by these and other entities whether alone or in combination. For example some entities may include a customer a service call a business organization etc.

All systems and processes discussed herein may be embodied in program code stored on one or more computer readable media. Such media may include for example a floppy disk a CD ROM a DVD ROM magnetic tape and solid state Random Access Memory RAM or Read Only Memory ROM storage units. According to some embodiments a memory storage unit may be associated with access patterns and may be independent from the device e.g. magnetic optoelectronic semiconductor solid state etc. Moreover in memory technologies may be used such that databases etc. may be completely operated in RAM memory at a processor. Embodiments are therefore not limited to any specific combination of hardware and software.

Embodiments have been described herein solely for the purpose of illustration. Persons skilled in the art will recognize from this description that embodiments are not limited to those described but may be practiced with modifications and alterations limited only by the spirit and scope of the appended claims.

