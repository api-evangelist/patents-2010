---

title: Method and apparatus for monitor and notification in a network
abstract: A user specifies one or more monitoring/probing rules on a client station. These rules specify user instructions for monitoring and probing conditions, events, and data on monitored sites on the Internet. The client station transfers the rules to the monitoring site, which also processes and interprets the rules. When the monitoring site processes these rules, it results in (1) allocation of space and (2) creation or initialization of agent programs, which will effect periodic monitoring of Internet sites and send data back to the monitoring site. If the retrieved information at the monitoring site satisfies the user-specified conditions, the monitoring site will conduct further exploration to gather more information that may help determine the causes of these conditions. The results of such a probe may be obtained from the monitoring site or the Internet, and are communicated by the monitoring site to the client station.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08719403&OS=08719403&RS=08719403
owner: New York University
number: 08719403
owner_city: New York
owner_country: US
publication_date: 20101213
---
This invention relates to a method and apparatus for monitoring and searching a network such as the Internet and for notifying one or more user s of the results.

In recent years the Internet has become more popular allowing users to access information in ways never before possible. Information on the Internet is useful to a broad spectrum of individuals including investors financial analysts entrepreneurs and academics. Changes reflected in a Web page a large dip in a stock s value or a new merger amongst competing companies for instance may be of critical importance to the users of the network.

However keeping track of this constantly changing information is not easy. Logging on to the Internet every day to monitor changes can be time consuming. Thus Web utilities have been developed for instance FirstFloor s Smart Bookmarks which periodically monitor user defined Web sites and automatically notify the user when changes occur at a Web site e.g. a change in the text without the user having to log on.

Unfortunately such monitoring utilities generally do not allow the user to customize the type of change or information being monitored to the particular interests of the user. In addition while such utilities can monitor changes within a particular Web site they cannot monitor relationships amongst changes in several Web sites. Such changes for example the addition of a keyword reflecting a new product at several Web sites may indicate the move to a new technology. Similarly newly created links amongst a group of Web sites may indicate an industry alliance is forming. Such industry wide not company specific information may be of greater importance to the user than changes reflected at a single Web site. Thus a user may be forced to constantly monitor several Web sites in search of such new relationships an even more time consuming and difficult task than monitoring a single Web site.

Another limitation of such utilities is that once a change is detected at a given Web site the change is automatically communicated to the user regardless of its importance. Thus a great deal of information irrelevant to the user may nevertheless be communicated again wasting the user s time.

What is needed is a utility which 1 monitors the Internet for the occurrence of user defined conditions including relationships amongst one or more Web sites 2 performs a search for information of importance to the user upon detection of such conditions and 3 provides the user with the results of the search.

Various embodiments of the present disclosure overcome the above mentioned disadvantages of prior art Web monitoring and search utilities. The present invention 1 periodically monitors for user defined conditions including relationships amongst one or more network sites 2 probes for further information upon detection of such conditions and 3 automatically reports results to the user.

Thus one advantage of at least one embodiment of the present disclosure is that it automatically monitors for conditions and relationships specified by a user thus customizing the automatic monitoring according to his or her interests.

Another advantage of at least one embodiment of the present disclosure is that it allows automatic monitoring of changes and relationships involving more than one Web site or Web page. Such relationships e.g. industry wide as opposed to company specific trends may be of particular import to users.

Another advantage of at least one embodiment of the present disclosure is that upon the detection of a user specified condition s the system performs a user specified search for information which may be of import to the user or which may explain the occurrence of the user specified condition s . In other words the system does not immediately alert the user as soon as a minor change in the domain of his interest takes place. The system continues to explore to see if this change is accompanied by some activities that are of interest to the user and returns a more refined list of those changes. This probing feature provides at least two related benefits.

First it acts as an information filter. Thus it avoids the information overload that makes most simple monitoring mechanisms less than useful.

Second the feature allows for intelligent information gathering from the Internet or other related networks. The feature allows the user to define triggers that make an explicit connection between what is a symptomatic event and what needs to be further investigated. For example the occurrence of an event e.g. the deletion of a link to a site may be significantly correlated with one phenomenon e.g. addition of a link from a different site but may be entirely meaningless in the context of other phenomena say a surge in the number of visits to the site . Thus the combination of a monitoring feature and probing feature allows an Internet user to find logical relationships between events as well as learn their possible implications.

Another advantage of at least one embodiment of the present disclosure is that monitoring searching and notification functions may take place without a user log on into the Internet.

Another advantage of at least one embodiment of the present disclosure is that a user may specify the monitoring conditions and searches in a high level language similar to English. Thus a user need not have specialized computer programming knowledge to benefit from the present disclosure.

Further advantages and benefits shall become apparent upon review of the following detailed description and the drawings.

The client station s comprises a computer processing device storage device memory device display device user input device and user interface element . The computer processing device can be for example a single microprocessor chip such as an Intel Pentium chip printed circuit board several boards or other processing device. The storage device can be for example an internal or external disk tape cartridge or CD ROM. The faster access and greater storage capacity the storage device provides the more preferable the implementation. The memory device can be implemented with for example a collection of RAM chips. The display device can be implemented for example with a monitor whether analog or digital. The user input device can be implemented for example with a keyboard mouse or scanner. The client station s also include a user interface element which can be implemented as separate software i.e. a program process whose instructions are executed by the computer processing device . However there is no reason the computer processing device e.g. microprocessor chip could not include the user interface element process itself.

The monitoring site comprises a computer processing device storage device memory device rule interpretation element database allocation and search element and agent creation modification element . The computer processing device can be implemented with for example a single microprocessor chip such as an Intel Pentium chip printed circuit board several boards or other device. The storage device can be implemented with for example an internal hard disk tape cartridge or CD ROM. The faster access and greater storage capacity the storage device provides the more preferable the embodiment. The memory device can be implemented with for example a collection of RAM chips. The rule interpretation element database allocation and search element and agent creation modification element can be implemented as separate software i.e. programs processes whose instructions are executed by the computer processing device . Again however there is no reason the computer processing device e.g. microprocessor chip could not be used to implement the rule interpretation element database allocation and search element and agent creation modification element processes itself.

If the client station s are connected to the monitoring site via a telephone system or other system lines not carrying digital pulses the client station s and monitoring site may both also include a communications converter . The communications converter can be implemented with any communications converter device such as for example a modem. The communications converter converts digital pulses into the frequency signals carried by the line and also converts the frequency signals back into digital pulses allowing digital communication.

As depicted in the monitoring site is connected to one or more client station s and its resources may be shared by one or more clients in most common implementations. Thus for such implementations the monitoring site may be referred to as a server with clients i.e. client stations wherein the server is coupled to a usually remote network.

However despite the embodiment described above it is worthy of note that client station s may each contain the elements included in the monitoring site . Therefore a monitoring site is unnecessary.

In step depicted in a user at client station specifies via user input device one or more monitor probing rule s using the facilities of the user interface element which is displayed on the display device . Put simply the monitor probing rule specifies what information the user wants monitored what information the user wants retrieved and under what circumstances. The user interface element can be a set of choices in a displayed menu a displayed form or other means for facilitating preferably easy intuitive input.

In step the monitor probing rule s data is sent from client station to monitoring site . Again the communication converter may be necessary to effect this communication.

In step the rule interpretation element running off the computer processing device at the monitoring site converts the monitor probing rule data into a set of instructions the computer processing device is already designed to execute.

The computer processing device on the monitoring site executes the interpreted instructions of the monitor probing rule which are in memory device for this purpose. This execution results in two operations.

First in step the database allocation and search element running off the computer processing device at the monitoring site allocates space on the storage device . Conceptually in one possible embodiment of the present disclosure this can be thought of as creating space for a table s of records with one or more fields per record. Initially the conceptual table s are empty but records are added to the table s later on as information is retrieved for monitoring purposes.

Second in step the agent creation modification element also running off the computer processing device at the monitoring site alters a template agent program already existing in the storage device. In an alternative embodiment the computer processing device may create a new agent if one does not already exist.

Agents are well known in the art. Briefly agents are programs which can run off the computer processing device of a computer be sent over communications lines and can then be run off the computer on the receiving end. They are therefore particularly suited for search and retrieval of information over the Internet.

In the above described embodiment of the present disclosure once created modified the agent program periodically executes retrieval and monitoring operations. Also in a possible embodiment of the present disclosure once user specified monitored conditions are satisfied the database allocation and search element running off computer processing device of the monitoring site will execute a user specified exploring request e.g. search or retrieval operation in storage device through files therein i.e. through conceptual table s of records retrieved by agent operations from Internet . Results of the search can be sent from monitoring site to client station s and then can be displayed on display device for the user s benefit.

The method and apparatus of the embodiment heretofore described will become more apparent from the more detailed description below.

Note that the monitor probing rules which may be specified by a user step are preferably in a high level language i.e. like English or otherwise such that the user can write instructions without a specialized programming language . In order to accomplish this the embodiment should preferably include means to convert the high level language in which the monitor probing rule is specified into a set of instructions that may be executed by a processing device of a computer.

For example in the presently described embodiment the monitoring probing rule data is sent to monitoring site step which includes rule interpretation element i.e. a language processor in the form of software . Rule interpretation element performs the rule interpretation function depicted in step . Such a translator must necessarily encompass rules governing the structure of the higher level language being translated. A possible set of such rules is more fully described as follows.

The WHEN and IF clauses form the monitoring part of the rule trigger and the THEN clause forms the probing part of the rule. The monitoring part of the trigger will effect a watching for certain events to occur that satisfy certain conditions. Once the system detects appropriate events it does not necessarily inform the user about this. Instead the system tries to explore the situation in which these events occur by executing certain probing actions specified in the probing part of the trigger i.e. the THEN clause. The structure of a rule is similar to the structure of triggers used in active databases however the nature of the events conditions and especially probing actions is substantially different as will be explained below.

In the case of the WHEN portion of the statement the user specifies an event parameter step . An event is a change in the state of one or more of the objects e.g. Web sites on the Internet that are being monitored. For instance an appearance or disappearance of one or more keywords the appearance of a new link between two sites a change of physical attributes of a Web page or the like are examples of events.

In the case of the IF portion of the statement the user specifies a condition parameter step . Conditions are constraints that the user applies to events and act as filters that refine the space of the events to result in a smaller subset that are of interest to the user.

In the case of the THEN portion of the statement the user specifies a probing action parameter step . In general the probing action investigates what is going on at the site or a collection of sites once the events in the WHEN clause occurred and satisfied the conditions of the IF clause.

The following examples illustrate the general structure of the WHEN IF THEN monitor probing rule s translated in plain English.

WHEN the keyword cable modem appears on a site IF the keyword push technology is not included in the text of the site THEN find out how many sites from the predefined list of sites the word cable modem appeared and of these how many featured the keyword push technology .

IF several Web sites are linked into a star configuration AND the keyword cable modem is found on all the nodes in the configuration THEN find all such star configurations.

IF a keyword consisting of push technology Web TV channels appears in all Nodes members of a user defined configuration THEN find all such configurations where such keywords appeared and return the list of the corresponding Uniformed Resource Locators URLs .

IF the number of visits to a site increases at a rate greater than R AND the sites contain the keywords set cable modems Web TV THEN find all sites that contain the same keywords and whose visit rate was greater than R return the set of corresponding URLs.

WHEN a keyword appears at a site AND links to that site from other sites disappear THEN find all the sites from which links to this site disappeared find out if these sites have any keywords in common find all the sites which are now linked to this site find out if these sites have any keywords in common and return the four lists.

Notice also from the above examples that although events in the monitoring part of the rule are useful it is not necessary to use them in general for monitoring Web activities. The reason for that is that they can be simulated through the conditions of the IF clause alone the events describing a set of circumstances which are a subset of those described by the conditions and events . Also a monitoring probing rule may contain only the WHEN and THEN clauses i.e. no IF clause .

For simplicity s sake in the embodiment described more fully below events in the WHEN clause step will be specified by indicating certain conditions in the IF clause step using the methods known to a person having skills in the art. Therefore we will focus only on the structure of conditions and probing actions in the rest of this section. Again the present disclosure is by no means limited to the embodiment described below.

Note that an event may be atomic or composite. The composite event is the conjunction of two or more atomic events. One of the most popular methods to define composite events is through a conjunction of atomic events i.e. as E1 and E2 and . . . En where E1 and E2 and . . . En are atomic events such as a link between two sites appears a keyword appears within a site or a page or link was deleted. However composite events can be defined in more general terms as well e.g. as a conjunctive or disjunctive form CNF or DNF of its atomic events . Atomic events may belong to one of the following classes but atomic events are not limited to just these classes 1 a link appears disappears 2 a keyword or a group of keywords appears on a page 3 a page s text is modified 4 a change in the physical attributes of a page 5 a visitor visits a page. One way to specify conditions in the IF clause of a monitoring probing rule would be through a conjunction of atomic conditions i.e. as P1 and P2 and Pn where Pi is an atomic condition. Consistent with this method in general the IF clause can be defined as the conjunctive normal form or a disjunctive normal form of atomic conditions. Conjunctive and disjunctive normal forms are well known in the art. An example of an IF clause is IF Site S1 is Linked to Site S2 AND keyword Ki appears in S2 AND keyword Kj exists in S1 where Site S1 is Linked to Site S2 keyword Ki appears in S2 and keyword Kj exists in S1 are atomic conditions .

In order to define atomic conditions it is also necessary to explore the modeling primitives or the basic entities used in our monitored environment. In one possible embodiment of the present disclosure the information to be monitored searched and retrieved is on the Internet or more specifically the World Wide Web. In this environment the modeling primitives basic entities might be 

1. Web Pages A Web page is a collection of text pictures video and or audio objects and or other media that are on the Web and share the same URL. Two different Web pages will not have the same URL. A Web page may have physical attributes such as size date of last change title etc. Web pages may also be referred to as pages below.

2. Web Sites A Web site is a collection of one or more Web pages. Pages within a site are linked by links. A Web site also has a URL which uniquely identifies the site. Web sites may also be referred to as sites.

3. Keywords These are text objects words phrases etc. found in a Web page and therefore by extension found in a Web site.

4. Links Links are embedded in Web pages and allow a visitor to move from one location to another. A link may take a user from one page to another or may simply take him her to another location on the same page.

In addition to these basic entities composite conditions can be derived from the basic entities using a data definition language for example if the basic entities are defined in terms of a relational data model as tables the composite entities are defined as relational views i.e. as SQL expressions . Examples of these composite entities are 

1. Configuration A collection of Web sites that are linked to each other. A configuration can have one trivial case or more Web sites. For example a set of sites linked in a circular fashion forms a ring configuration or a configuration consisting of a central site that is linked to all other sites in the configuration and other sites being linked only to the central site forms a star configuration.

2. Reach relation Specifies which sites can be reached from a given site. This relation can be defined as a transitive closure of the LINKS relation described herein.

In the present disclosure basic and derived entities are modeled as data objects in the corresponding data model. For example if the data model is relational then these entities are modeled as relations predicates . If the data model is objectoriented then they are modeled as data objects.

In the embodiment described below the relational data model is used in building the rule interpretation means and database allocation and search means and the basic entities are modeled as predicates using relational terminology they can sometimes be called relations or tables . For example LINKS is a predicate of the form LINKS site1 site2 where site1 is the site from which the link originates and points to site2. However the present disclosure is not limited to the relational data model and is applicable to other data models as well.

Moreover some of the predicates are temporal because they change over time. For example the predicate LINKS may change over time because links can be added and removed over time .

Once the basic entities of the data model are defined e.g. as predicates relations the atomic conditions in the IF clause of the monitor and its structure can be defined as illustrated in . depicts a possible syntax and component structure of atomic conditions.

As depicted in an atomic condition can either be a literal a past unary temporal operator followed by a literal or a literal followed a binary past temporal operator followed by a literal. Some examples of unary past temporal operators include Always in the past Sometimes in the past Sometimes within the past T time units and Always within the past T time units . An example of a binary temporal operator is Since. 

As depicted in a literal is either a predicate or a negation operator e.g. NOT followed by a predicate.

Based on the rules described above some examples of atomic conditions which may appear in the IF portion of the monitoring probing rules are as follows 

1. Key Words site keyword count a predicate meaning that the user has specified that the cite keyword keyword has count count at site site .

2. LINKS site1 site2 Sometimes within the past 2 weeks meaning that a link existed at some point between sites site1 and site2 within the past 2 weeks. Note that LINKS is a temporal predicate because it implicitly changes over time.

3. Key Words XYZ cable modem count Since LINKS XYZ ABC meaning that the keyword cable modem appeared at cite XYZ since the link was established between sites XYZ and ABC.

Turning now to the THEN clause portion of the monitoring probing rule the THEN clause consists of a sequence of probing operations. In one possible embodiment of the present disclosure the structure of the THEN clause can be defined as a query in Structured Query Language SQL . SQL is well known in the art and is suited to search and retrieval in a relational database environment such as the one described above. Thus the rule interpretation means may include SQL interpretation means well known in the art. However the THEN clause can include numerous other constructs some of which are discussed in greater detail later.

Examples of probing actions expressed as SQL queries follow. Assume that in the monitoring part of a trigger it was detected that a certain configuration among a group of sites was broken when a certain keyword appeared in one or more of these sites. Then in the probing part we may want to find the list of all sites whose links to those sites where the keyword appeared were deleted after the appearance of the keyword. Such probing actions can be expressed with SQL queries three examples of which follow.

The first query extracts the list of all sites that point to one particular site e.g. www.target.com in the previous monitoring period before the keyword appeared 

The second query extracts all those sites that do not have a link with that site in the present monitoring period and stores them as a temporary table called TEMP Sites with no current link 

The third query joins the two temporary tables in an SQL Query and extracts the list of those sites that have deleted a link in the current monitoring period.

Thus the WHEN IF THEN or as described above IF THEN rule can be described by constructs such as those described above as well as for example SQL interpretation means and thus translated by rule interpretation element into instructions executed at monitoring site by computer processing device .

The computer processing device executes the interpreted instructions of the monitor probing rule which are in memory device for this purpose. In the embodiment described herein this execution results in two operations.

First turning again to in step the database allocation and search element running off the computer processing device at the monitoring site allocates space on the storage device . Conceptually this can be thought of as creating space for a table s of records with one or more fields per record. Initially the conceptual table s are empty but records are added to the table s later on as information is retrieved for monitoring purposes.

For example assuming that the IF portion of a monitor probing clause consists entirely of an atomic condition in the form Key Words site keyword count a file is created on the monitoring site which can be conceptualized as a Key Words table with site keyword and count fields or columns . Each time a new keyword entry at a site is retrieved from the Internet the entry can be conceptualized as another row of the table which includes the appropriate count of the number of times this keyword appears at that site.

Alternatively assuming that the IF portion of a monitor probing clause consists entirely of an atomic condition Links site1 site2 Sometimes within past 2 weeks a file may be created on the monitoring site that is represented as a temporal relation using methods well known in the art. Alternatively such temporal atomic conditions may be represented on the monitoring site using the implemenation methods described later.

Next in step of the agent creation modification element also running off the computer processing device at the monitoring site alters a template agent program already existing in the storage device . In an alternative embodiment the computer processing device may create a new agent if one does not already exist.

A more detailed description of steps and is as follows Without loss of generality in the following description assume that triggers have only the IF clause and the THEN clause no WHEN clause .

First determine the set of temporal predicates for each atomic condition in the IF clause either temporal predicates or the auxiliary predicates as described later . Allocate data storage for these tables using the methods known in the art.

Second given an IF clause determine for each temporal or non temporal predicate generated in step 1 real predicate not the auxiliary predicate the set of Web sites S from which information should be obtained to evaluate that predicate. For example if the If statement is

Third for each predicate and each site in set S computed in step 2 generate an agent that goes to that site and periodically downloads the necessary data needed to evaluate that predicate note that the agent is permanently allocated to the monitored site once in a while it can be moved out by the site but then it tries to get back again .

The agent is developed as follows. An agent template is written for each type of predicate by the system developer at the time the monitoring system is designed this means that the Web monitoring system is shipped to the user with a set of predefined agent templates that can be extended later by the user . For example for the LINKS predicate the agent template is a software program that travels to a Website specified as an argument for that template and periodically downloads all the links to which this site points note that the downloading period is another argument . When the agent template is initiated as a part of the agent generation sending procedure the arguments of the template are initiated with real parameters. For example in the case of the LINKS predicate the agent template is instantiated with the parameters indicating the site to which the agent must travel and the downloading period. In the most general case every monitoring period the agent brings back to the monitoring site the entire predicate from that monitored site. For example the keywords agent at the site site sends back to the monitoring site all the keywords and their counts from that site i.e. that are parts of predicate KeyWords for that site .

However certain optimization methods may minimize the amount of data sent by the agent to the monitoring site. For example if nothing changed at a site from the previous monitoring period there is no need to transmit any data back to the monitoring site.

Once the data arrives to the monitoring from the monitored site it is stored in the tables allocated in step 1 using the methods known to a person with an ordinary skill in the art.

In the above described embodiment of the present invention once created modified the agent program periodically executes retrieval and monitoring operations step as follows.

Turning now to it depicts a flowchart showing steps which may be performed by an agent program and by database search and allocation element at monitoring site in accordance with instructions specified in the probing part of the monitoring probing rule depicted in .

In step at the first monitoring period the agent program is communicated from the monitoring site to monitored site s via the network e.g. the Internet . Once at the monitored site s the agent program evaluates data sends information back to monitoring site based on user defined criteria specified in the IF portion of the monitoring probing rule and may remain at monitored sites until completion of its tasks if the agent is terminated by the monitored site another copy of the agent attempts to get back to the site. That copy may come from either the monitoring site or elsewhere in the pipeline between the monitoring site and the monitored site .

For example assuming that the IF portion of a monitor probing clause consists entirely of an atomic condition in the form Links site1 site2 the agent program retrieves the URLs corresponding to relevant first sites and second sites back to monitoring site . More specifically an agent program may be sent to each of the relevant sites corresponding to the first argument of Links i.e. Links site1 . Each of the agents sitting at site1 then sends back URLs of all the sites linked to the site at which the agent is sitting.

The database search and allocation element running off computer processing device on the monitoring site stores the URL data into a file on the storage device . This file can be conceptualized as a Links table. Each link can be defined by URLs of site1 and site2. Thus the table can be conceptualized as a table of columns site1 and site2 with each new Link entry forming a new row. In addition to this simple case if the IF clause contains a temporal LINKs condition the past history of links between sites would also be stored as discussed in more detail later.

One main implementation issue relating to applications using the World Wide Web is that it is stateless in the sense that it does not remember its history. For example there is no way to test whether the volume of visits at the site has been monotonically increasing within the past 3 months unless the client station or monitoring site maintains the information about the volume of visits over time i.e. the Web site does not maintain this information itself . Therefore it is the responsibility of the client station or the monitoring site to maintain the necessary information. Thus two related implementation issues arise as a result of the agent s data retrieval from the Internet .

The first issue involves what historical information needs to be maintained and where for monitoring purposes.

Given a set of triggers monitoring site or client station needs to maintain the temporal predicates that would allow processing device to evaluate temporal expressions contained in these triggers. This means that monitoring site or client station hereinafter monitoring site alone will be referred to must store the current values of these predicates and in certain cases their past histories. For example assume that in the IF clause user specified predicate LINKS site1 site2 within past 2 months specifying that a link existed between site1 and site2 at some time within the past 2 months. To be able to monitor and evaluate such a predicate monitoring site needs to maintain the current state of predicate LINKS at the present time as well as its past history within the last two months. Since time is continuous and processing device can evaluate the presence of links between site1 and site2 only at some finite set of times this means the user needs to specify the sampling monitoring rate for the evaluation of predicate LINKS. For example the user may specify to check the status of predicate LINKS every day or every 8 hours or every hour. The agent will then retrieve information and the information will be checked at the time points corresponding to the user specified sampling rate.

Notice that it can be assumed that no abnormal changes happen to predicate LINKS between the sampling points. For example assume that the agent samples predicate LINKS every day. Then if the link between site1 and site2 existed yesterday and still exists today this means that nobody deleted and inserted the same link within the last day but it is of course possible to delete the link during that day in this case the system detects the change at the next sampling point .

Rather than storing the whole past history of temporal predicates it is more efficient to store the temporal information in compressed format using the methods described below. To illustrate how this can be done consider the example of the temporal predicate always past LINKS site1 site2 stating that there was always a link between site1 and site2 in the past. In that case the monitoring site may maintain two predicates LINKS site1 site2 and Always Past Links site1 site2 in order to monitor condition Always Past Links site1 site2 where Always Past Links is updated each monitoring period by removing from it the records that do not appear in predicate LINKS.

In general information to be maintained at the monitoring site can be determined as follows. Take the set of all the temporal predicates appearing in the monitoring parts of all the triggers. If the predicate is non temporal no trigger refers to its past history database search and allocation element will store the current copy of that predicate on the storage device of the monitoring site the copy at the latest sampling period . If the predicate is temporal some triggers refer to its past history database search and allocation element stores the current copy of that predicate and the following additional information. For each temporal operator e.g. Always past Sometimes past etc. database search and allocation element stores an auxiliary copy of the predicate pertaining to this operator. For example for the temporal expression Always past LINKS site1 site2 appearing in one of the triggers database search and allocation element store the current copy of LINKS site1 site2 and an auxiliary predicate Always Past Links site1 site2 . Always Past Links site1 site2 is true if and only if there was always a link from site1 to site2 in the past. Similarly we store an auxiliary predicate Sometimes Past Links for the temporal expression Sometimes Past Links. In general storage device at monitoring site maintains one auxiliary operator for every predicate temporal operator pair appearing in one of the monitoring triggers e.g. IF clause created by the user. These auxiliary predicates can be maintained using the methods known to the person having an ordinary skill in the art e.g. as described in Chomicki J. History Less Checking of Dynamic Integrity Constraints 8th IEEE Conference on Data Engineering Phoenix Ariz. 1992 pp. 25 26 .

For example predicate table Always Past Links is updated by database search and allocation element every monitoring period by removing records site1 site2 from it that do not appear in the current copy of Links site1 site2 . Note that these auxiliary predicates are non temporal they only simulate temporal predicates but do not have any temporal component as part of their structure and can be stored using the conventional methods known to someone with an ordinary skill in the art.

The retrieval of information from the Internet also raises a second related issue. One of the steps in predicate maintenance noted above is the step of the agent obtaining the current copy of the predicate. This means the agent must visit the monitored site s e.g. on the Internet and evaluate the present conditions of the predicate s at that site. One of the central issues in this process is what information should the agent check and even more importantly what information it should bring back from the monitored site s to the monitoring site . This is a critical issue because we want to monitor many sites and need to minimize the data to be transferred back to the monitoring site in order not to clog the communication lines.

As was demonstrated above for the monitoring purposes it is necessary for the agent program to bring back at each monitoring period only the current states of the predicates that are maintained on the storage means of the monitoring site such as Links Web Sites Key Words etc.

An optimization issue arises when less data than is in the current copy of the predicate being monitored can possibly be brought back to the monitoring site . For example assume that the temporal predicate being monitored in the IF clause of a trigger is Always Past LINKS site1 site2 . As was explained above this predicate can be monitored through the database search and allocation means creating and storing an auxiliary predicate Always Past Links site1 site2 . Note that this predicate is monotonically decreasing over time. Also note that rather than retrieving the relation LINKS in its entirety at each monitoring period the agent program may retrieve only the records from the intersection of Always Past Links and Links.

In general if auxiliary predicates are monotonically decreasing such as Always past Links then the agent retrieves auxiliary predicates rather than the current predicates e.g. LINKS . To the contrary if auxiliary predicates do not decrease over time such as Sometimes Past Links the current predicates are retrieved by the agent from the Web sites on the network being monitored.

Data transmission can be further optimized when no significant changes occur at the monitored sites. In that case data need not be transmitted to the monitoring site . For example the agent may have stored a previous copy of the predicate either at monitored or in the event this is impossible at other intermediate sites in the network . To determine whether a predicate has changed since the last monitoring period the agent may then compare the previous copy with a current copy of the predicate using techniques known in the art. If the copies differ then and only then is the predicate transmitted to the monitoring site . Alternatively the agent may determine the differences between current and previous copies and transmit only those differences.

The optimization and implementation issues noted above are effected by agent creation modification element at monitoring site .

Turning now to step in one embodiment of the present disclosure once the agent program retrieves user specified data to the monitoring site and database search and allocation element stores the information processing device checks the stored information to determine if it satisfies the userspecified condition e.g. in IF clause using methods well known in the art .

In one embodiment of the present disclosure when the user specified condition is satisfied then in step database search and allocation element running off processing element at 3 monitoring site performs an SQL search on files tables of data on storage device already retrieved from Internet as described above or performs other probing actions described later.

In step the results of the SQL search or other probing actions are sent from monitoring site to client station s via e mail or other notification means where they may be displayed on display means for the user s benefit. E mail is commonly used and its implementation is well known in the art. Of course such notification becomes even simpler when the system does not include monitoring site as noted above.

Notice that in an alternative embodiment the probing operation may search and return information from the Internet instead of monitoring site as just mentioned. Where information is returned from the Internet one of ordinary skill may use any of the existing known Web related information retrieving methods.

In addition in other alternative embodiments other types of probing or other operations may also be performed as a part of the THEN clause upon satisfaction of user defined conditions of the IF clause.

As a first example monitoring site may send back to client station information corresponding to user defined condition detected by processing means at monitoring site and client station simultaneously issues an alarm. For example the IF THEN clause in English 

As a second example at least one embodiment of the present disclosure may execute a program written in a general purpose programming language e.g. C that examines certain conditions. For example such program may visit different Web sites in some sequence and return the URLs of those sites that satisfy certain properties e.g. have increasingly higher visitation traffic .

As a third example a data mining query may be executed. Data mining queries also known as pattern templates are constructs for the specification of types of patterns to be discovered. Therefore probing actions can further explore what is going on on one or several network sites when the IF condition s of a rule are satisfied by letting the data mining query discover network related patterns. Several researchers considered data mining queries pattern templates in the context of knowledge discovery. Imielsinki T. Virmani A. and Abdulghani A. DataMine Application Programming Interface and Query Language for Database Mining Proceedings of the Second International Conference on Knowledge Discovery and Data Mining August 1996 Klemettinen M. Mannila H. Ronkainen P. Toivonen H. and Verkamo A. I. Finding Interesting Results from Large Sets of Discovered Association Rules Proceedings of the Third International Conference on Information and v Knowledge Management December 1994 Han J. Fu Y. Wang W. Koperski K. and Zaiane O. DMQL A Data Mining Query Language for Relational Databases Proceedings of the SIGMOD Workshop on Research Issues on Data Mining and Knowledge Discovery June 1996 Shen W. Ong K. Mitbander B. and Zaniolo C. Metaqueries for Data Mining Advances In Knowledge Discovery and Data Mining chap. 15 AAAI Press 1996.

Imielsinki et al. introduce the M SQL query language as an extension of SQL by including a small set of primitive data mining operations. M SQL queries operate on the underlying database and on a set of previously discovered rules and return a set of rules discovered in the data that satisfy the conditions of the query.

For example the query Find all rules in Table T involving attributes Disease Age and ClaimAmt which have a confidence of at least 50 can be expressed in M SQL Imielsinki et al. as 

The Mine operator returns all the association rules Agrawal R. Mannila H. Srikant R. Toivonen H. and Verkamo A. I. Fast Discovery of Association Rules 12 AAAI Press 1996 Imielsinki et al. 1996 that are true in T and the WHERE clause imposes conditions on them such as that the body of a rule should not be empty and should contain attributes Disease Age and ClaimAmt. Also the consequent of the rule must contain one of these attributes and the confidence should be at least 50 .

M SQL queries are evaluated by launching discovery methods as described in DataMine Application Programming Interface and Query Language for Database Mining Proceedings of the Second International Conference on Knowledge Discovery and Data Mining August 1996.

Han et al. designed the data mining language DMQL. A query in DMQL consists of the specification of four data mining primitives 

 2 the kind of knowledge to be discovered i.e. a characteristic discriminant classification or an association rule 

 3 the background knowledge consisting of a set of concept hierarchies or generalization operators which provide corresponding higher level concepts and

 4 the interestingness of the knowledge to be discovered which is specified with a set of different mining thresholds.

For example the query Classify students according to their GPAs and find their classification rules for those majoring in computer science and born in Canada with the attributes birth place and address in consideration can be expressed Han et al. 1996 as 

It was Shen et al. that defined metaqueries which can be viewed as a two part specification. The left hand side LHS of a metaquery specifies a constraint on how data should be prepared and the right hand side RHS specifies an action to be applied on the prepared data. For example consider metaquery 

This metaquery is a template that instantiates various transitivity patterns depending on the predicates to be substituted for templates P Q and R and the attributes and values substituted for variables X Y and Z.

For instance consider the transitivity pattern p X Y AND q Y Z r X Z with probability Pr . This pattern satisfies the earlier specified metaquery where predicates p q and r are specific database relations and Pr is the ratio of the X Z pairs satisfying the LHS and the RHS of the rule and those satisfying only the LHS. Then the action in the RHS of the metaquery lies in computing the value of Pr.

The notion of a pattern template was also introduced in Klemettinen et al. for the purpose of identifying interesting patterns. A pattern template in Klemettinen et al. is a rule A1 AND . . . AND A k A k 1 where each A i is either an attribute name a class name or an expression C or C corresponding respectively to one or more and zero or more instances of the class C. Such a template defines a class of rules that are instances of the template pattern.

For example consider a pattern template that says that students can take an advanced elective in some department if they have taken a core course offered by that department and one or several electives 

The above references to user notification and program execution operations upon satisfaction of a condition can be implemented by a person having ordinary skills in the art. In addition whenever information is to be returned from the monitoring site to the user one of ordinary skill in the art can use any of the known database information retrieval methods such as the utilization of any of the existing database query languages.

It is readily apparent that numerous other modification combinations of and minor additions to the above disclosure may be made for the benefit of network users while remaining within the scope of the present disclosure. For example a useful way of implementing at least one embodiment of the present disclosure is for the monitoring site to act as server to more than one client station and to maintain a separate account file for each such client station .

The account files could include the monitoring conditions and probing instructions associated with their respective client station. Accordingly more than one client at more than one location could simultaneously benefit from the present disclosure each according to their own needs in the manner described above.

