---

title: Automated communications response system
abstract: In one embodiment, a system provides for end-user control over the automatic recognition of communication situations by detection of unique telecommunication event characteristics and the consequential responses to those situations by invocation of related programmatic responses. The system allows an end user to specify various patterns of telecommunication event characteristics that describe various situational aspects of incoming communications, such as the timing and originator of voice calls, the content of, timing of, and author of chat messages, etc., as well as appropriate sets of programmatic response actions to be performed in response to those communications, such as initiating conference calls, sending chat messages, routing calls to other users, etc. The system monitors incoming communications, matches characteristic patterns to recognize the situations, and then invokes the matching response actions, thereby automating many functions of the communication system that previously would have had to be performed manually.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09100465&OS=09100465&RS=09100465
owner: Eolas Technologies Incorporated
number: 09100465
owner_city: Tyler
owner_country: US
publication_date: 20100811
---
This application claims priority from the provisional application entitled AUTOMATED COMMUNICATIONS RESPONSE SYSTEM application No. 61 273 952 filed Aug. 11 2009 which is hereby incorporated by reference for all purposes.

The present disclosure relates generally to controlling and managing VOIP and Instant Messaging IM applications.

Skype is a software system that allows users to make audio and video calls over the Internet. It supports conference calls instant messaging file transfer and video conferencing. Skype uses a proprietary Internet telecommunication VoIP network that works on a peer to peer model.

Skype includes an Application Programming Interface API that allows other programs to interact with Skype. The Skype API supports three types of messages 1 commands to control Skype 2 directives i.e. out of band commands that control the API itself and 3 information messages that Skype sends about its status.

One of Skype s distinguishing features is that it can operate behind firewalls and Name Address Translation NAT routers. It achieves this by using super nodes to relay calls between clients not directly connected to the Internet. Any Skype client can become a super node if it connects to the Internet without NAT and or an appropriate firewall which means Skype can and does borrow bandwidth and computing power.

A disadvantage of such a borrowing feature is that the end user has little control over the conditions or timing of such borrowing. Despite the existence of APIs to provide developers with programmability of such systems tools are not available that enable end users to take control of the telephony and chat facilities in a way that they can automate their various functions to allow end user control of such features as the borrowing described above or to allow automatic detection of and response to a variety of other telecommunications circumstances that might arise.

What is needed is a system that enables the end user to simply and precisely define a set of telecommunications circumstances such as any set of characteristics which apply to particular classes of voice calls or chat messages and to define appropriate programmatic responses to relevant circumstances to allow automatic detection of and response to a wide variety of such telecommunications circumstances thereby expanding the usefulness of telecommunications systems.

An example embodiment provides a system for end user control over the automatic recognition of communication situations by detection of unique telecommunication event characteristics and the consequential responses to those situations by invocation of related programmatic responses. The system allows an end user to specify various patterns of telecommunication event characteristics that describe various situational aspects of incoming communications such as the timing and originator of voice calls the content of timing of and author of chat messages etc. as well as appropriate sets of programmatic response actions to be performed in response to those communications such as initiating conference calls sending chat messages routing calls to other users etc. The system monitors incoming communications matches characteristic patterns to recognize the situations and then invokes the matching response actions thereby automating many functions of the communication system that previously would have had to be performed manually.

Reference will now be made in detail to various embodiments of the invention. Examples of these embodiments are illustrated in the accompanying drawings. While the invention will be described in conjunction with these embodiments it will be understood that it is not intended to limit the invention to any embodiment. On the contrary it is intended to cover alternatives modifications and equivalents as may be included within the spirit and scope of the invention as defined by the appended claims. In the following description numerous specific details are set forth in order to provide a thorough understanding of the various embodiments. However various embodiments may be practiced without some or all of these specific details. In other instances well known process operations have not been described in detail in order not to unnecessarily obscure the present invention. Further each appearance of the phrase an example embodiment at various places in the specification does not necessarily refer to the same example embodiment.

A first example embodiment is an interface software tool named Skybot as depicted in and is programmed utilizing the Tool Command Language Tcl . Referring to in this example embodiment an Internet telecommunication platform the Internet telecommunication platform API and the Interface Software Tool are implemented as software modules on a user s personal computer PC .

The Interface Software Tool includes an extension language module used to specify rules and actions for interacting with an Internet telecommunication platform a generalized state engine that evaluates the rules and automatically triggers Tcl code in response to various events a database for holding rules and an interface not shown to the API of the Internet telecommunication platform so that actions can access state and configuration information of the Internet telecommunication platform. In this example embodiment the Internet telecommunication platform is Skype.

In this example embodiment the rules are stored in a normalized database and presented to users as tables. There is a single maintenance screen with multiple tabs one for each table in the database.

There are three classes of rules 1 call rules 2 chat rules and 3 watch rules watch for someone changing to a particular status used in this example embodiment.

The interface includes a button for each characteristic. When creating a new rule using the interface the button for the characteristic is clicked on and the user selects a characteristic that has either been previously pre specified or specified by the user. The specification of characteristics will be further described below.

The first thing to note is that rules may be defined but not enabled. This makes it easier to create rules without affecting the behavior of the interface software tool.

Turning now to the first rule which specifies that Skype should not accept calls at night when the user is at home. In this example the Enable characteristic is activated by checking the box under the Enable label. With regard to the rest of the characteristics note the following 

In this example embodiment all rules and actions are stored as data in tables and are abstracted and normalized

The Who characteristic is defined in the Groups tab. In this example embodiment there are two groups defined by default the all group which is a wild card that matches all Skype users and a friends group which is the list of people on the user s Skype contact list as returned by the Skype API call SEARCH FRIENDS .

Alternatively a Skype user name or a pattern e.g. corporate can be entered or a groupings to be entered can be specified for example wheaton might expand to cyndy maury mike . Groups can be recursive as in wheaton cyndy maury mike or corporate wheaton steveh stevel .

This scheme also allows convenient aliases to map to real Skype user names for example the above names might be aliased to corporate cyndy corporate maury and so on. During data entry a check is performed to ensure a group isn t defined with the same name as an alias or a Skype name on the users contact list.

Locations are based on IP address and are defined in the Locations tab. The interface software tool recognizes a new location and pops up a dialog so the user can give it a name e.g. Home Office etc. .

The Action interface includes a left pane having columns defining type action name input and description of a specific action and a right pane that lists the commands that are run for a specified action.

Note that there are rules that apply to calls chats watches and to all events. In the above example you can see the Tcl commands that are run when the event is detected. These make use of some pre defined Tcl commands but the intention is to eventually allow definition of arbitrary Tcl procedures in the database as well.

The when command creates a Tcl trace on the call status variable allowing event driven actions within rules. This means that the rules will be re evaluated whenever the call status is changed by Skype.

The Details variable is passed in from the call chat watch rule and will be substituted so that any variables it contains will be expanded. This will allow rules to be parameterized. The following example would be useful in an organization that spans time zones or where team members are semi nocturnal.

Because rules and actions are just data stored in database tables the interface software tool is both flexible and extensible and can be extended by adding new rows to the tables in the database or by modifying existing rows.

For example to refuse all incoming calls when in a meeting but let Mike know that the user is available via chat use something like the following Calls definitions abbreviated for clarity 

The default rule will only match if there is no other matching response. In this case Mike would see I m available via chat but everyone else would see I m unavailable .

Note that there are a set of pre defined variables available corresponding to the call properties obtained from Skype e.g. the above pstn number .

The derivation of the commands to execute involves a join of the calls chat watch table with the Groups Time Location and Action table then a substitution of variables in the Commands field of the action table.

For example to set the user s status to Offline when idle during prime time to prevent the super node based bandwidth borrowing described above and to Invisible to allow Skype proxying when idle during non prime time use the following this would override the default screensaver based idle behavior 

The Skype API provides a mechanism for third party scripts applications and devices to control Skype UI functions and implement additional or improved features to complement Skype.

The Skype API has two layers a Communication Layer which is a set of methods for external applications to establish connection to the Skype client and communicate with it and a Command Protocol Layer which is a text based language that external applications can use to speak to the Skype client once a communication channel is established by the Communication Layer.

Additionally there are several Skype API wrapper libraries that encapsulate the functionality of the Skype API. Such wrappers can act as optional third layers.

The Communication Layer provides a mechanism for external application to communicate with Skype. This layer is platform dependent and the transport mechanism to exchange data with Skype is different on Windows Linux and Mac operating systems.

There are two types of information available to the interface software tool via the Skype API data that is pushed from Skype to the interface software tool when certain events occur and data that may be pulled by the interface software tool from Skype when required.

Messages pushed from Skype to the interface software tool include in part notification of an incoming call or chat message the chat topic the call duration on completion or a call failure reason if there was a problem but all data may potentially be pushed by Skype and so must be recognized by interface software tool.

Data that may be pulled by the software interface software tool includes information about the call or chat message e.g. when an incoming call is detected the interface software tool needs to pull information about the call type and the caller ID.

In process block the interface software tool checks if Skype is running and if necessary starts it. In process block the interface software tool attaches itself to Skype and registers to receive messages from Skype via the Skype API.

In process block the location is initialized. If the user s location cannot be automatically recognized by using the IP address the user will be prompted e.g. home office etc and information received will be saved. The extensible design of the software interface tool allows for additional location methods to be incorporated such as using RFID or GPS devices.

The interaction routine then enters a loop where messages from Skype will be recognized and the appropriate response will be performed. In process block the interaction routine waits for a message from Skype. As specified by the Skype API definition each of the messages from Skype is either a command from the software interface tool to Skype and a corresponding response from Skype to the software interface tool or a notification a pushed message from Skype to the software interface tool . These messages are textual messages like CALL or CHAT followed by additional information e.g. CALL 25069 STATUS RINGING .

The software interface tool contains rules that map between Skype API messages and internal software interface tool commands. These rules may be viewed and maintained by the user through the Skype tab on the software interface tool UI thus allowing users to extend the software interface tool if required. In process block when a notification message is sent from Skype to the software interface tool the message is matched against the list of patterns in the software interface tool s Skype tab.

When there is an incoming call Skype sends the interface software tool a message like the following CALL id STATUS RINGING where id is the Skype message identifier. The pattern matching recognizes the message and calls the command call id property value where property is STATUS and value is RINGING.

The call procedure sees that there is not an existing call id and so creates a new one creating a separate interpreter to hold its state.

In process block the software interface tool then pulls any required extra data from Skype e.g. the PARTNER HANDLE property which contains the Skype username of the incoming call which is extracted and stored within the software interface tool.

For example the software interface tool then requests extra information about the call from Skype such as the Caller ID e.g. GET CALL 25069 PARTNER HANDLE and Skype returns this information as a response e.g. CALL 25069 PARTNER HANDLE 61812345678 which is again matched against the Skype rules in the software interface tool.

In processing block the data pulled from Skype and the data previously pushed from Skype are used to recognize a situation defined by the user when creating a rule. The recognition process will be described more fully below with reference to .

In process block the appropriate rule defined response based on the recognized situation is performed.

The RECOGNIZE SITUATION and PERFORM RESPONSE process blocks of will now be described more fully with reference to and respectively. These subroutines match the information obtained from Skype to the rule characteristics defined for example as described above with reference to and if a match occurs the interface software tool performs the action specified in the rule.

Turning to in process block the recognition subroutine is entered. At this point the software interface tool knows several pieces of information about the call or chat such as the person or number the incoming call chat came from the time of day the call chat arrived and where the user is currently located.

In process blocks this information is further processed according to the rules in the Groups and Time tabs. In process block the Who value that is the person or number making a call or chat is first matched against the Groups tab allowing rules to be specified for multiple people for brevity. Default rules exist for all and friends i.e. Skype friends . In process block Who is set for the message.

In process block the Time value is matched against a range of times such as morning night afternoon and so on these can be modified by the user as required. In process block When is set for the message.

Once the extra processing defined in process blocks occurs the recognition subroutine has all it needs to recognize a situation and decide on an appropriate response. In process blocks searches are made through enabled rules to match characteristics of the received message to characteristics of enabled rules.

In process block the type of call call chat watch is matched in process block who made the call is matched in process block when the call was made is matched in process block where the user is located is matched in process block the type of event ringing connection finish is matched and in process block the direction of the call or chat incoming outgoing is matched.

Once the matching process determines the situation defined by an enabled rule then the action defined in the enabled rule is performed in process block and the subroutine exits in process block .

The response operation will now be described in more detail with reference to . When a situation is recognized i.e. a rule in the Calls Chats or Watch tab matches the associated action is run by the software interface tool. Actions are specified in the Action tab and can be modified or extended by users using a spreadsheet paradigm as described above with reference to .

Actions can relate to either calls chats watches or all three are named e.g. mail message mute and may have one or more corresponding commands within the software interface tool. Commands can be Skype commands software interface tool commands or any arbitrary command to be run on the computer hosting Skype. This allows the situation specific combination of arbitrary Skype and non Skype functionality

The Actions tab specifies optional information that is passed to the action by the interface software tool as per the Details information associated with each entry in the Calls Chats and Watch tabs.

The Input column in the Actions tab specifies the optional information expected by each action. For example the mail action expects three pieces of information the email addressee the subject a text value and the contents of the message another text value 

Many different default actions can be appropriate for calls and chats including for example to accept the incoming call chat refuse the call respond using a speech to text subsystem send to voice mail redirect to another number or initiate a conference call.

As depicted in corresponding to each entry in the actions tab is a list of the command s to be run to implement the response.

By way of example illustrates the interaction between Skype and the software interface tool via the Skype API when performing the conference action depicted in . The conference action can be specified to automatically set up a conference call between designated parties when a particular set of characteristics are matched from an incoming message.

In this example the conference call action accepts two inputs both phone numbers for the conference call attendees and gets response data from the database in process steps and then performs six steps in responding.

In process block the response subroutine instructs the interface software tool to convert the message You will be called back soon from text to speech and instructs Skype to play the sound to the originating caller.

In process block the response subroutine instructs Skype to HANG UP CALL and in process block Skype finishes the call

In process block the response subroutine instructs Skype to CALL NUMBERS and utilizes the numbers obtained in process blocks and . In process blocks and Skype calls the two conference call attendees. In this example one would be the original caller and one would be the interface software tool user s cell phone number.

In process block the response subroutine instructs Skype to MUTE SPEAKERS and in process block Skype itself is muted so that no sound comes from the speakers during the call.

In process block the response subroutine gives Skype focus so that Skype is brought to the front on the computer running the interface software tool so that it is apparent a conference call is in progress.

In process blocks the response subroutine waits for the call to finish and when the call finishes Skype is un muted. The response subroutine exits at process block .

The variable types are defined in the Types tab using Tcl expressions similar to as shown in . The reformat column specifies if the Tcl command returns a value that should replace the original value useful for example when forcing phone numbers to a standard format . The Trigger specifies the name of a Tcl command to call whenever the Value of a Name changes. This allows for Watch rules to be triggered by changes pushed from Skype.

The Skype tab exposes the internal mapping from Skype messages to the interface software tool Tcl commands that parse them and invoke the state machine.

The embodiments described above allow an unlimited amount of additional functionality to be defined by the user including for example rules to call back when current call finishes send chat message when current call finishes change the Skype icon when on a call initiate conference call send call to voice mail refuse a call accept a call reply via chat and send an SMS via smsgateway service.

There are many additional actions that can be specified to route incoming calls in specific ways such as actions based on the identity of the caller and or the time of day or day of the week.

Many simple practical solutions are possible using this approach such as during off hours routing calls from a client to a work voice mail system routing calls from the user s spouse to go to the user s cell phone and causing calls from a manager to trigger an email alert to be sent to the user s PDA.

But the potential exists for unlimited types of creative automation as well. For example if a user wished to appear to others to be present at her machine even if she was not then rules could be specified to keep the user s online status looking as if she were at the machine periodically switching it between online and away . Perhaps if someone were to send a chat message during this time the software interface tool could initiate a conversation between the user and the sender and a customized Eliza engine could simulate the user s presence by sending plausible yet non committal chat responses that make it appear that the user were present at the machine.

The modules depicted in could be implemented as software modules in the system memory to be executed by a processor or be implemented as combinations of program code and hard wired logic.

Various example embodiments have been described above. Alternatives and substitutions will now be apparent to persons of skill in the art. For example embodiments of the invention could be used with any telecommunication system or chat system having an API allowing control by an external application. Such systems include for example Google Voice AIM or Yahoo Messenger. Accordingly it is not intended to limit the invention except as provided by the appended claims.

