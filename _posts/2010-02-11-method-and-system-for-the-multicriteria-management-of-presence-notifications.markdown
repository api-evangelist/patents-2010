---

title: Method and system for the multi-criteria management of presence notifications
abstract: Multicriteria management method for presence notifications proposed by a means of instant communications comprising a list of contacts that is not empty and connected to a presence server, such method comprising the following steps:


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08930488&OS=08930488&RS=08930488
owner: Alcatel Lucent
number: 08930488
owner_city: Boulogne-Billancourt
owner_country: FR
publication_date: 20100211
---
The present invention pertains to the technical field of telecommunications and more particularly to presence notifications intended for users of means of instant communications.

Internet development has brought about a great number of means of communication and collaboration which continue to develop mailing lists instant messaging wikis weblogs e mail forums etc.

In particular instant messaging IM services have experienced explosive popularity. They have the particular feature that interactions between users are online and in real time thereby enabling an active dialogue unlike other means of communication whose interactions are carried out off line and with a delay. It should be noted that instant messaging services are sometimes designated by the terms chat and chatting.

Instant messaging is a computer system that enables the instant exchange of data text voice visual emoticons between multiple remote terminals computers. PDAs and mobile telephones for example connected to the same network most commonly the Internet.

As it has evolved instant messaging has increasingly integrated features such as voice video and all sorts of collaborative applications shared whiteboards text editing and gaming for example. To achieve this instant messaging requires the use of a software application or web interface that connects to an instant messaging server. Instant messaging users therefore in general have an account associated with an instant messaging program or web interface such as Windows Live Messenger Microsoft Office Communicator or Yahoo Messenger ICQ My Teamwork published by Alcatel Lucent and MSN Web messenger.

Most instant messaging services offer a system for announcing presence and availability notifications in real time which indicates the members who are online to interact with as well as their availabilities and sometimes even their mood. The announced presence status may also be explained in order to indicate for example the cause of an unavailability busy writing the report absence out to eat back in 10 minutes do not disturb on the phone in a meeting at the office .

By way of example Windows Live Messenger offers a plurality of presence statuses symbolizing the availability of each of the contacts in a user s list. Each user may display his or her status meaning his or her current activity logged out logged in away unavailable invisible. Invisible status can be used to view the list of people logged in without becoming visible to one s contacts.

Presence management has proven particularly useful for users who can verify the status of their contacts before any attempt to contact them through instant messaging. In doing so it makes it possible to simplify and encourage the establishment of communication.

By way of example a user who has all members of his or her remote collaborative work team in his or her list can tell the availability of his or her collaborators in real time and synchronize their interactions as a result.

Citable examples of presence management systems used by instant messaging services include DynamicSoft Indigo Software and Hotsip.

Other means of communication offering the presence service have been as successful as instant messaging services. This is particularly true of the latest generations of means of mobile communication and of social networking and microblogging tools Twitter Jaiku Co op Yammer and SocialCast .

Most social networking and microblogging tools enable a user to display indicators of his or her presence to his or her network. By way of example a user can use short messages to inform his or her network of what he she is now doing. These messages are updated manually by the user retrieved from an instant messaging service or retrieved from other sources using an RSS feed.

Below the term instant means of communication shall designate all means of real time communication such as instant messaging services means of mobile communication and social networking and microblogging tools.

Presence management is deployed throughout the means of instant communications in a transparent manner so that the status is displayed to the list of contacts in response to each change. In other words if a user s presence status changes for example from logged out to logged in from busy to available or from invisible to absent a notification indicating the new status is distributed to all or to some selective distribution of the contacts in the list. Thus a user 

In practice presence management involves multiple problems both for the generator and for the observer. This is because a user who has a plurality of contacts in his or her list may 

Furthermore in general a user s presence information in a social networking or microblogging tool are unchanged as long as the user does not edit them manually. Thus a user registered for more than one means of instant communications is constrained to indicate his or her presence information as many times as there are means of communication for which he or she is registered.

The document WO 2008 041830 describes one method enabling an observer to define rules dealing with the manner grouped notifications and time of reception when the number of them is at least at most exactly equal to a predetermined number of the presence notifications related to a set of contacts in his or her list. The observer receives a constructed notification once the rule is satisfied.

The presence notification management solution recently introduced by Wind Mobile is devoted to mobile telephones. It enables the user of a mobile telephone to assign him herself a presence status for some duration and to net that period of time. A caller who unsuccessfully attempted to reach a called party with the status busy will receive a notification once the called party s status is changed to available. 

Microsoft Office Communicator 2007 allows an observer to label a contact from his or her list in order to be automatically informed of that person s availability.

The FriendFeed aggregator published by FriendFeed Inc makes it possible to group together updates from several social network and microblogging tools such as Twitter and from several instant messaging services such as Google Talk for the purpose of separately displaying the most up to date presence information of users in Google Talk and Twitter for example. However this solution only relates to 

Thus few methods and systems are known to ensure multi criteria management of the presence notifications supported by the means of instant communications. Furthermore these systems are very specific. They mainly relate to 

Consequently known systems and methods are imperfect particularly due to the absence of any management that would enable service that 

One object of the present invention is to remedy the aforementioned drawbacks. In particular the invention aims to propose a method system and computer program product enabling unified multi criteria management of the presence notifications supported by the means of instant communications that propose the presence service.

To that end according to a first aspect the invention proposes a multicriteria method for managing presence notifications proposed by a means of instant communications comprising a non empty list of contacts and connected to a presence server which method comprises the following steps 

According to a second aspect the invention proposes a multicriteria system for managing presence notifications proposed by a means of instant communications comprising a non empty list of contacts and connected to a presence server which system comprises the following means 

According to a third aspect the invention pertains to a computer program product implemented on a memory medium which may be implemented within a computer processing unit and comprises instructions for implementing the method summarized above.

The invention enables multicriteria management of presence notifications to be sent or received by a means of instant communications incorporating the presence server independently of the means of instant communications itself.

It particularly makes it possible to filter out the presence notifications to be broadcast or received with the help of rules defined by the user of the means of instant communications.

By way of nonlimiting examples the rules may deal with time the new status the change in status the previous status and the number of notifications coming from one or more contacts. These rules may concern one or more contacts simultaneously.

The invention is particularly applicable in the event that the user has a plurality of contacts in his or her contact list in a means of instant communications and is heavily requested through it.

In the present description of the method and system for multi criteria management of presence notifications supported by the means of instant communications the assumption is made that a user has an account in a means of instant communications and has a non empty contact list.

With reference to the user connects by means of instant communications via a user interface associated with it. By way of non limiting examples this user interface is 

The means of instant communications makes it possible to establish a communication between two users via a communications network . The communications network may be a heterogeneous communications networking operating multiple interconnected communications networks such as the Internet and the public land mobile network PLMN . Generally speaking the connection to the means of instant communications is preceded by a step of authentication with the assistance of a user name and password or more generally speaking an identifier.

The presence information offered by the means of instant communications is generally retrieved transmitted from a presence server . The presence server may be 

The present invention enables a user to define presence notification rules concerning one or more contacts. Whenever the rule is satisfied a notification window appears to that user. The management of the notification s display is generally handled by the user interface of the means of instant communications. It may take the form for example 

In order to enable a user to define a rule for filtering presence notifications at least the means of instant communication is associated with a graphical interface for configuring rules as shown in . This interface displays default rules such as

According to another rule configuration mode it is also possible to pair the rule with a certain frequency of displaying presence notifications. By way of examples one may 

This type of rule may particularly apply in the context of remote collaborative work requiring the presence of a plurality of contacts.

In one variant it is possible to pair of rule with the time. By way of example a rule is to be applied only 

According to another mode of configuring the filtering rules the user may define his or her own role thereby making it possible to define more selective and more complex rules. For example define a rule dealing with.

According to another variant a notification is displayed to the user whenever there is a failure in establishing a communication with the contact. In other terms whenever a user attempts to interact requesting to turn on a webcam to pick up or to agree to receive data for example with a contact when the contact is not available a notification appears offering one or more appropriate dictated rules in accordance with the current status of the contact and the user s request .

By way of example whenever a user A requests a voice communication with a user B who appears in his or her list of contacts while that user is already in a phone call and his or her current status is in a call or on the phone a notification 

In particular this notification does not appear when user A s request is satisfied even if user B s status at the time of the request did not necessarily involve the satisfaction of that request. This may for example occur when 

Based on another variant illustrated in a notification may display different actions to be activated by the user A within the limits of the capacities and current configuration of the means of instant communication available to user A and to the contact. This notification displays the contact s new presence status as well as other actions such as call this contact change my status and send a message to this contact .

A user logged in to an instant messaging application that only allows text based and voice based communication does not display a visual communication option with a contact who has just logged in for example even if his or her means of instant communication which is compatible with that of user A supports visual communication.

According to another mode for associating actions with a rule an action is automatically triggered once this rule is met. By way of example the action of beginning a voice based communication with a contact who currently has the status in a call once he or she has changed his or status or the action of automatically changing my status to invisible once a certain contact s status is logged in .

Furthermore the notification generator who was the originator of a notification reviewed by an observer may manage the notifications to be transmitted to the presence server and broadcast afterwards to his or her list of contacts or to social networking and microblogging tools.

Referring again to the user of the means of instant communications as a generator may configure personal presence messages which will be broadcast based for example on 

The presence information personal message and or presence status of a user is broadcast information push to social networking and microblogging tools such as Twitter or Yammer by means of application programming interfaces APIs such as the API offered by Twitter. This is because the means of instant communications automatically forwards the presence information to the social networking and microblogging tools without these tools needing to search for them via the corresponding application programming interfaces. This operation is commonly designated information push. This operation enables an automatic configuration of presence information.

A means of instant communication that supports a certain communication format voice or visual for example and that has the tool appropriate to that format headset microphone telephone or webcam camera can detect the state of that tool available busy and change the user s status accordingly. By way of example once the user picks up a telephone associated with at least one means of instant communications the user s status becomes on the phone . Once the user hangs up the telephone his or her status becomes phone call over or returns to the presence information that preceded that call.

A user may define different profiles for managing presence notifications. A profile comprises at least one configuration rule of received or sent notifications. This profile is saved so that it can be imported exported from one means of instant communications to another as well as from one account to another within a single means of instant communications offering the presence service.

Preferably the rules for filtering the notifications and or the configuration of the presence statuses concerning a profile are stored in a file in a format compatible with most of the means of instant communications.

In order to simplify the ability to access the functions offered by this multi criteria management of presence notifications it is preferable to add a Notify Me function to the appropriate menus of this service by way of example getting this function from among the functions accessible via right clicking on a contact or in a configuration menu.

The presence notifications accompanied by the details relating to them are at least for a moment recorded in a database. The details comprise the date of receipt and the contact.

It should be noted that the invention is not limited to the configuration described by . The implementation of the features proposed by the present invention shall be adapted to the capacities of the means of instant communications a mobile terminal a web interface an instant messaging application .

The management of presence notifications just described exhibits a certain number of advantages. In particular it makes it possible to 

It should be noted that the presence information comprises the presence status and or a personal message. The personal message may comprise by way of example the explanation for an unavailability the mood of the user or more generally speaking a comment.

At this point it is important to note that the present invention is independent of the programming language used to implement these features.

It should be noted that the expression means of instant communications here designates any means of communications enabling an instant remote communication via a communication network regardless of the form of the communication text based voice based visual or any combination of same.

