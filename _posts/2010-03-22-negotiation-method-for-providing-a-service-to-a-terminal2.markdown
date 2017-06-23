---

title: Negotiation method for providing a service to a terminal
abstract: A negotiation method and server are provided for delivery of a service to a terminal. Also provided are a method for configuring a terminal and a terminal using the method. In particular, the methods and apparatus relate to interfaces for interaction with services available to users of a service. The negotiation method includes sending to the terminal of a set of proposals for interactions with a delivery component of the service capable of enabling the terminal to indicate to the delivery component that the terminal accepts at least one proposal from the set of interaction proposals.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09635543&OS=09635543&RS=09635543
owner: FRANCE TELECOM
number: 09635543
owner_city: Paris
owner_country: FR
publication_date: 20100322
---
This Application is a Section 371 National Stage Application of International Application No. PCT FR2010 050513 filed Mar. 22 2010 and published as WO 2010 112729 on Oct. 7 2010 not in English.

The disclosure relates to a negotiation method for the delivery of a service to a terminal a server using said method a method for configuring a terminal and a terminal using said method. In particular the disclosure relates to the interfaces for interaction with services available to users of a service.

On the one hand rich and sophisticated interfaces are being developed that rely on the precise knowledge of the terminal accessing the service. These are so called closed environments. Such is the case for example for services or applications dedicated to the iPhone television offerings based on receivers or boxes which are clearly known and so on.

This first approach requires in particular the users to invest in a full and often proprietary solution.

On the other hand conversely in a desire to make access to the resources of the Internet universally available web browsers have emerged. These are so called open environments. So as to be accessible to a very large number of terminals these browsers have remained highly independent of the capabilities of the terminal since all that is needed is a pointing device a mouse in particular to use a browser.

This second approach through its attempt at genericity is ill suited to the growing diversity of the types of terminals used to access a service culminating in an under use of the capabilities of the terminal or on the other hand in the failure to recognize its limitations.

Also in addition it does not take into account usage contexts in particular the mobility of the terminal the fact that a conversation is already in progress etc. Now these usage contexts could have been indicated by the user or been deduced from the configuration set up by the user on his or her terminal terminal in Meeting mode microphone deactivated etc. .

A number of solutions now exist that make it possible to indicate to a terminal to indicate its hardware and software characteristics to a service or an application such that the latter adapts its content and or the presentation of its content on the terminal concerned.

In particular the specifications RFC 2534 and 1999 provide for a terminal to be able to indicate information describing its capabilities concerning the display printing and reception of faxes. However because of its age they are no longer suited to the current complexity of the applications and of the terminals.

In its recommendation CP PP1.0 dated 15 Jan. 2004 of which version 2.0 is in the working document state the W3C World Wide Web Consortium consortium is drawing up a standard enabling each terminal to describe its capabilities. These are essentially capabilities concerning the hardware the operating system the Web browser and where appropriate the type of network connectivity. The aim is to enable a Web server to adapt the content delivered and its formatting to the limitations of the terminal. This recommendation draws on the RDF Resource Description Framework standard based on the XML language to describe the capabilities of a terminal.

The OMA Alliance Open Mobile Alliance has adopted the recommendation of the W3C consortium to detail its modalities of use in the context of mobile terminals. These modalities of use essentially specify the use of the composite capabilities preferences profiles CC PP on session according to the WAP or WSP protocol WSP standing for WAP session protocol and on session according to the wireless http or W http standing for WAP Wireless profiled http protocol in a ratified document entitled User Agent Profile version 2.0.

Now all these solutions are essentially focused on the passive playback capabilities of the terminals such as the display possibilities the presence of loudspeakers etc. and partially on its capabilities to send information texts voice etc. . In all these cases the single and unique objective of such information is to enable the Web server to adapt the delivered content Content Adaptation . This content adaptation is then performed either by the selection of a content having a suitable format the same content being available in several formats or by formatting of the content in a different manner according to the playback and or sending capabilities indicated or by transforming the content notably by reducing resolution transcoding etc. .

The interactions of the terminal with the service remain limited either in the first approach to the one proposed by the proprietary interface solution with its drawbacks or in the second approach to the generic interactions.

In this second approach the potentialities of the terminal are therefore not fully exploited because this approach levels down the interactions between the terminal and the services leading to the underuse of the interaction capabilities of the terminal.

One subject of an embodiment of the invention is a negotiation method for the delivery of a service to a terminal comprising the sending to said terminal of a set of proposals for interactions with means for delivery of said service capable of enabling said terminal to indicate to said means for delivery of said service that said terminal accepts at least one proposal from the set of interaction proposals.

Thus the service proposes to the terminal alternatives in terms of possible interaction modes. The terminal can thus indicate the interaction mode s corresponding to the best possible use of its capabilities or even choose an interaction mode that is compatible with the handicap of the user of said terminal.

Advantageously the step for sending a set of interaction proposals is repeated during a session of said service.

Thus if there has been an update to the service s interaction modes and or to the terminal s interaction capabilities and or if the user of the terminal has changed during the session these new elements can be taken into account to readapt to the interaction mode of the terminal with the service.

Another subject of an embodiment of the invention is a program comprising program code instructions for executing the steps of the negotiation method when said program is executed by a processor.

The subject of an embodiment of the invention is a server delivering a service to a terminal comprising means for sending to said terminal a set of proposals for interactions with means for delivery of said service capable of enabling said terminal to indicate to the server that said terminal accepts at least one proposal from the set of interaction proposals.

Another subject of an embodiment of the invention is a method for configuring a terminal with a view to the delivery of a service comprising the reception of a set of proposals for interactions with means for delivery of said service capable of enabling said terminal to indicate to said means for delivery of said service that said terminal accepts at least one proposal from the set of interaction proposals.

Advantageously said method comprises the choice of at least one proposal from the set of interaction proposals according to the capabilities of said terminal.

Thus the terminal can be configured to interact best with the service according to its own capabilities.

Advantageously said method comprises the repetition of the step for reception of a set of interaction proposals capable of enabling said terminal to modify the at least one accepted proposal.

Advantageously on starting the use by said terminal of said service said method comprises a configuration of said terminal according to one of the at least one accepted proposals.

Thus the terminal dedicates its interface to interact with the service during the time that this service is used by the user of the terminal. The terminal dynamically adapts its interface to the service according to the interaction proposal set proposed by the service.

Another subject of an embodiment of the invention is a program comprising program code instructions for executing the steps of the configuration method when said program is executed by a processor.

A subject of an embodiment of the invention is a terminal comprising the reception of a set of proposals for interactions with means for delivery of a service capable of enabling said terminal to indicate to said means for delivery of said service that said terminal accepts at least one proposal from the set of interaction proposals.

Another subject of an embodiment of the invention is a terminal comprising means for delivery of a service and an interface enabling a user of said terminal to interact with said service said means for delivery of said service comprises means for sending to said interface a set of proposals for interactions with said means for delivery of said service capable of enabling said interface to indicate to said means for delivery of said service that said interface accepts at least one proposal from the set of interaction proposals.

The term stimuli should be understood to mean information passed form the terminal to the means for delivery of a service. The sending thereof is provoked by a usage action directed toward the means for delivery of a service. The stimulus is therefore an interaction between the terminal and the means for delivery of a service.

The term service designates both the service delivered by the core application and in a misuse of language can be used to designate this core application that is to say the means for delivery of the service. The means for delivery of a service may consist of a logic entity which delivers a service to the user. These means for delivery of a service may be local or remote which means that the means for delivery of the service may be respectively located in the terminal or in a remote server. It is in these means for delivery of the service that the requests from the terminal are processed and that the content which is intended for said terminal is prepared according to these requests before being transmitted.

The negotiation comprises at least a first exchange p of the means for delivery of a service to the terminal . In this exchange the means for delivery of a service formulate a set of interaction proposals. In a variant of the invention the proposals are arranged hierarchically notably according to the wealth of interactions that they offer to the user. Each proposal brings together a set of interactions taken over by the means for delivery of the service. The expression set of interactions is understood to mean at least one interaction. For each interaction or stimulus the set of interaction proposals p sent by the means for delivery of a service comprises 

The first exchange therefore constitutes an offer to the terminal of stimuli or interactions taken over by the means for delivery of a service .

The tables below give an example of a set of interaction proposals that can be sent by means for delivery of a service in particular of an advanced voice messaging service to a terminal such as a mobile terminal.

The means for delivery of a service can inform the terminal thereof by indicating in the sending of a set p of interaction proposals a preference indication. In the above example this preference indication is given by a Pref parameter ranging from 1 to 10 from the most interesting proposal to the least interesting proposal according to the means for delivery of the service. The interest may be a simple recommendation from the provider of the service or be estimated by the means for delivery of the service . This interest is based on one more criteria such as the wealth of the interaction the genericity of the interaction proposal etc.

The first proposal enables the user of the terminal who will use this interaction mode to interact with his voice messaging service only by sending voice frequencies to the means for delivery of the service DTMF keys . This proposal has the advantage of allowing the service to be accessed by the least sophisticated of terminals.

The second proposal enables the user to use the right left confirm return keys of the keyboard of a mobile terminal illustrated by and optionally to use the cancel key 0 F field set to F . To implement this second interaction proposal the terminal must therefore configure these keys so that the commands are suitably associated to allow interaction with the means for delivery of the service.

In the case where the terminal is configured according to this second proposal to interact with the means for delivery of the voice messaging service the means for delivery of the voice messaging service will represent for example in the form of a list of messages here of sealed envelopes which will be displayed on the screen of the mobile terminal and which can be browsed through from right to left arrows on the screen . The means for delivery of the service will not allow up down browsing in this list. Thus a user who is familiar with the terminal will intuitively use the left key and the right key of the keyboard of the mobile terminal to browse through the list proposed by the means for delivery of the service.

The third proposal enables the user to use the touchscreen of his mobile terminal illustrated by allowing for movement in all directions four arrows of the touchscreen but also for an element to be pointed to and if necessary selected. The means for delivery of the voice messaging service can supply the messages in the form of a mosaic displayed on the touchscreen as illustrated by that the user of the mobile terminal can browse through in all directions. Optionally the third proposal provides for a selection of a set of icons representing the messages on the touchscreen by the user to generate a command to select the messages represented in this way in order for example to carry out a common action on this group of messages deleting them moving them to a directory etc. .

From the set p of the interaction proposals illustrated by the above tables the terminal chooses one or more interaction proposals and indicates its choice via the exchange c to the means for delivery of the service . The possibility of accepting several proposals at a time enables the terminal to enrich and diversify the interaction modes and possibly to be adapted to its user. The means for delivery of the service indicate where appropriate the acceptable proposal combinations for example in an additional parameter of the set p of interaction proposals.

The indication c of choice of proposal choice of stimuli taken over may be the fact that the terminal does not support any of the proposed interaction modes. In this case the indication c constitutes a notification of the fact that the terminal does not satisfy the prerequisites allowing for the use of the service delivered by the means for delivery of the service .

In a variant of the invention the means for delivery of the service indicate via the exchange a that the choice of the terminal has been taken into account. This message may if necessary be used to manage some or even all error cases.

In a variant of the invention the negotiation method comprises the sending sa of a confirmation of the stimuli taken over by the terminal. This confirmation makes it possible to check that the terminal and the means for delivery of the service will correctly use the same interaction proposals.

In a variant of the invention a service session is opened ss sv and the negotiation method can be renewed one or more times during this service session as shown by the negotiation method illustrated by broken lines.

In a variant of the invention the configuration method comprises the reception ra by delivery means of a confirmation of the stimuli taken over by the terminal .

In a variant of the invention the configuration method comprises a dynamic configuration config c of the terminal and in particular of these interaction means or interaction interface .

To carry out both the selection from the set p of interaction proposals and the dynamic configuration config c a terminal can use one or more of the following methods taken alone or in combination 

Thus the choice of one or more proposals from the set p of interaction proposals will be dependent on this list of interactions supported by the terminal.

Thus the choice of one or more proposals from the set p of interaction proposals will be dependent on the interaction parameters defined by the user and notably his preferences.

Once one or more proposals have been retained and this choice has been notified sc the terminal is dynamically configured by assigning a command or function of the terminal to each stimulus or interaction.

In the case of the voice messaging service of the dynamic configuration of the terminal according to the second proposal will result as illustrated by in a terminal whose keys allow access to the messaging functions. The messages are presented linearly on the screen of the terminal because the terminal does not have up and down keys. The keys of the interaction interface of the terminal are configured as follows key provides access to the previous message key to the next message key opens the message key provides a return to the main menu key deletes the message.

In the case of the voice messaging service of the dynamic configuration of the terminal according to the third proposal results as illustrated in in a terminal whose touchscreen allows access to the messaging functions. The browsing by touching the screen allows for travel in all directions the messages being presented in tabular form.

When a corresponding service session ss sv is set up by the processing means processor of the means for delivery of the service and the processing means processor of the terminal the configuration means of the terminal dynamically configure the terminal according to the accepted interaction proposal s c.

The means for delivery of a service may be remote from a terminal notably in an application server or local that is to say implemented in the terminal not illustrated . The connectivity between the means for delivery of the service and the terminal covers all types wired wireless GSM Bluetooth Wifi Ethernet or even a simple application relationship between two software components etc.

In a variant of the invention the configuration method complements the existing mechanisms enabling a terminal to communicate its information playback capabilities screen size etc. to an application server.

In a variant of the invention the means for delivery of the service exploit the information supplied to it by the negotiation method to adapt the way in which it interacts with the terminal . In the case of architectures such as the three tier web architectures for example the interaction will be notably taken over by the Presentation layer. In this way the Service logic layer also called Application layer can be used to deliver the service agnostically to the terminal the Presentation layer taking over the interaction with the terminal.

In some applications some elements may act as relays that is to say that they implement both the terminal for a first service and the means for delivery of a second service such as a television receiver which acts both as means for delivery of a second service with respect to the remote control and as a terminal accessing a first service television service located on the network.

By virtue of an embodiment of the invention the developer of the service does not have to have a priori knowledge of the terminals that will be used to access his service since the terminal and the means for delivery of the service will dialogue using the negotiation method enabling the terminal to dynamically adapt its configuration. Furthermore the user can make best use of his or her terminal according to the interfaces of the terminal and the set of interaction proposals of the means for delivery of the service.

By customizing the configuration in relation to the users constraints mobility meeting handicap the interaction of the terminal with the service will also be adapted to the user of the terminal and for any service.

The services targeted by an embodiment of the invention correspond to any usage type non exhaustive list 

The negotiation method and the configuration method constitutes a protocol which can be implemented in the form of an application programming interface or API enabling the means for delivery of a service to dialogue with the terminal on which they are installed to discover the interaction capabilities thereof. For example for the downloading of applications to mobile telephones each application embeds this API which enables it to exchange with the mobile to know which stimuli it can take over. Thus the application can support a large number of mobiles without having to know them all.

Although the present disclosure has been described with reference to one or more examples workers skilled in the art will recognize that changes may be made in form and detail without departing from the scope of the disclosure and or the appended claims.

