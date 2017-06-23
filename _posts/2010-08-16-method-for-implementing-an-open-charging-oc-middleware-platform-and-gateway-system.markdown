---

title: Method for implementing an open charging (OC) middleware platform and gateway system
abstract: The art of present discloses a method and system for enabling mobile network operators to collect charging information from various other network elements; and indeed, is intended to exploit the resiliency of open network architecture and lessen the requisite dependency on proprietary network elements services and billing systems. The Open Charging (OC) middleware platform and gateway system interacts with proprietary network elements and effectually creates a unifying, enabling layer in mobile networks. Indeed, the art is directed at permitting mobile subscriber access to, among others, third party content and services with the simplicity and convenience of such charges appearing on either mobile phone bill, or decremented from said mobile subscriber's pre-paid account.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08027360&OS=08027360&RS=08027360
owner: Redknee, Inc.
number: 08027360
owner_city: Mississauga
owner_country: CA
publication_date: 20100816
---
This application is a continuation of U.S. patent application Ser. No. 10 307 335 filed Dec. 2 2002 the contents of which are incorporated herein by reference.

Formerly wireless and or mobile subscribers faced the irksome option of multiple billing for whichever content and or service s they wished to utilize. Needless to say the arrangement remained most inconvenient. With the growth and sophistication of modern telecommunications networks and in particular the subsequent evolution of open service architecture s OSA we have seen the decoupling of application and network layers together with an augmentation of multi party applications and related infrastructure.

The Open Charging OC middleware platform and gateway system disclosed herein presages a new era of mobile subscriber access and ease of access to content and or service s by allowing such content to be charged to subscribers existing account s with their mobile provider.

Indeed none of the prior art reviewed teach or intimate the subject matter hereof seeking the protection of Letters Patent. Consider U.S. Pat. No. 5 963 630 to Dabbs et al. entitled. Mediation service control point within an intelligent network which teaches of a mechanism whereby a mediation SCP provides for a SCCP based mediation and redirection function whereof messages originated by SSPs are directed to the appropriate SCP s on the basis of subscriber identifiers which are encapsulated within the aforementioned messages produced by SSPs. However Dabbs et al. does not teach or suggest a method of providing a mediation capability whereby a plurality of network elements other than SCPs can be accessed in an efficient manner via a variety of interfaces and protocols as the case may be. Furthermore the patent to Dabbs et al. does not teach or suggest a method whereby a mechanism of accessing subscriber attributes e.g. account balance information stored on network elements e.g. SCPs can be extended to other computational platforms which may reside outside of the telecommunications carrier via an object oriented Application Programming Interface API .

Consider similarly U.S. Pat. No. 5 812 533 to Cox et al. entitled Service provision in communications networks which details a service delivery infrastructure whereby a Service Control Point is augmented for the purpose of provisioning selected sets of services to users of the communications network by interacting with network systems via an object oriented architecture. However it does not teach or suggest a method of reducing the number of transactions and therefore increasing the efficiency of nonaugmented Service Control Points. Furthermore the patent to Cox et al. does not teach or suggest a method of mediating and directing object oriented requests to network elements other than Service Control Points.

U.S. patent application Ser. No. 2002 0 058 496 by Bos et al. entitled Charging arrangement for a multimedia communication system provides for a mechanism whereby charging information related to multimedia service provided to a user is directed to a Service Control Point via the CAMEL Application Part CAP bearer network interface for the purpose of facilitating the charging process for the aforementioned service. However Bos et al. s application does not teach or suggest a method of providing a mediation capability whereby a plurality of network elements other than SCPs can be accessed in an efficient manner via a variety of interfaces and protocols other than CAP as the case may be. Furthermore their application does not teach or suggest a method whereby a mechanism of accessing subscriber attributes e.g. account balance information stored on network elements e.g. SCPs can be extended to other computational platforms which may reside outside of the telecommunications carrier via an object oriented Application Programming Interface API .

In relation to the subscriber information caching mechanisms detailed herein among other unique aspects of the invention of present consider U.S. Pat. No. 6 473 402 to Moharram entitled Communications link interconnecting service control points of a load sharing group for traffic management control provides for a mechanism whereby a given a given transaction can be directed to a plurality of SCPs in order to share the transactional load among the SCPs. However Moharram s patent does not teach or intimate a method of aggregating transactions for the purpose of reducing the collective number of transactions which have to be processed by a single SCP or plurality of SCPs. Furthermore it does not teach or intimate a method of reducing the transactional capacity for network elements other than SCPs.

U.S. patent application Pub. Ser. No. 2002 0 156 863 by Peng entitled Apparatus and methods for managing caches on a gateway details art relevant to the caching of data particular to Internet gateways and the prior art deficiencies of wireless internet users who may have inadequate processing capability for retrieving information and similarly very limited memory space for caching such information. Nonetheless nothing therein details or intimates art designed to lessen the impact on IN elements by specifically and uniquely gathering collating and analyzing machine readable records as wireless subscriber balances and so on thereby enabling a single update to such platforms as opposed to a multitude thereof.

The present invention relates generally to wireless communications and gateway services and more specifically to an improved method and system for effectuating and implementing an Open Charging OC middleware platform and gateway system.

In keeping with the evolution of open services and architecture the present method and system is disclosed which provides real time routing profiling and charging of transactable requests. The art of present provides a distributed secure robust and transactional interface to the fabric of existing mobile Service Control Point SCP platforms among other IN Intelligent Network elements.

The Open Charging OC middleware platform and gateway system provides a distributed framework architecture through its implementation of Common Object Request Broker Architecture CORBA and SOAP XML which allows service enablers to build enhanced applications and other such services which interact with the IN platforms of multiple vendors. In addition to Common Object Request Broker Architecture CORBA and Extensible Markup Language XML practitioners skilled in the art shall recognize that a variety of object oriented application programming interfaces will satisfy the implementation of said architecture without affecting the intent and scope of the present invention.

Additionally the platform and system of present can intermediate and process the various protocols required to interact with said former platforms including CSI INAP Prepaid CTP UCP and CAMEL Phase among others .

The art of the Open Charging OC middleware platform and gateway system has been so crafted as to remain fully MVNO Mobile Virtual Network Operator compliant providing as before an abstracted secure robust distributed and transactional interface to distributed mobile network and enterprise elements including among others but in particular IN platforms and in alternate embodiments HLRs while utilizing advanced queuing methods to minimize impact on mobile services. Such an architecture carries with it the unique potential for third party developers and or carriers to develop high capacity services and applications which interact with the nodes within mobile networks.

An aspect of the specification provides an open architecture method and gateway system for implementing an Open Charging OC middleware platform.

The platform can provide a common charging interface to various prepaid postpaid and or hybrid systems in helping facilitate real time event charging.

Charging information can be commonly understood as data necessary for network operators to properly bill subscribers based on their activities behaviors and or use.

The registration and provisioning can be explicit by indicating unequivocally which platform a request for a particular subscriber remains to be routed or it may be implicit providing general criteria in an effort to determine which platform to route requests to.

The Open Charging OC middleware platform and gateway system can be configured to retrieve external application logins and or external application function calls via any number of bespoke or standardly defined interfaces.

Such application logins or function calls may request balance query balance deduction and or balance increment for a particular subscriber as per the parameters of the external application.

Such requests are relayed to the Security Engine of the art to verify whether or not said external application is in fact permitted to make such requests or calls.

The permissions can be determined by whether said external application is permitted to request said function and or whether the application is permitted to access the Intelligent Network IN platform where said subscriber is hosted and or whether the application is permitted to access and or to modify the subscriber data as per MVNO Mobile Virtual Network Operator compliance .

Requests can be routed to the Queuing Module Mechanism upon satisfying said Security Engine parameters.

The Queuing Module can employ standard queuing methodology and implementations as per the priority set by the application which is making said request.

Requests taken off the Queuing Module can be translated into the specific protocol of the IN platform.

Functionality can be provided for by the IN adaptor which inevitably remains tied to the details of the aforementioned IN platform to be interfaced.

Another aspect of the specification provides a subscriber information caching mechanism for writing subscriber account information among other informational or data variables to a cache within the Open Charging C middleware platform and gateway system or similar platforms and systems itself.

The mechanism can comprise a computer program including instructions for implementing said caching mechanisms on a computer readable memory medium.

The mechanism can be calculated to lessen the IN platform s network impact by sending a single update to it as such.

The mechanism can be configured to represent a sum total of all balance increments and balance deductions among other informational variables.

With reference to said architecture depicted consists of the following functional elements and or modules 

Subscriber Registration is a feature of the platform and system which allows said system to determine which IN platform an application s request remains to be forwarded to in systems where subscriber information is disseminated across multiple IN platforms.

Subscriber Provisioning A may be explicit by particular subscriber remains to be routed or it may be implicit providing general criteria in an effort to determine which platform to route requests to as for example in one embodiment subscriber telephone number ranges.

The Open Charging OC middleware platform and gateway system requires that applications register and login before they are permitted to utilize said system. The platform and system maintains application profiles of each application permitted as such. Said profiles indicate the functions of the system which a given application is permitted to use.

Still in reference to the CORBA and SOAP XML servers in tandem with their respective application interfaces A A respectively accept external application logins and external application function calls as per their usual function in a client server system. Said CORBA and SOAP XML servers accept for instance the balance query balance deduction and balance increment function requests for a particular subscriber from an external application 2030 respectively and relays said information to the Security Engine to ensure that said application making the request has the requisite permission to so do. In addition to Common Object Request Broker Architecture CORBA and Extensible Markup Language XML which are delineated herein for the purposes of illustration familiarity and simplicity practitioners skilled in the art shall recognize that a variety of object oriented application programming interfaces will satisfy the implementation of said architecture without affecting the intent and scope of the present invention.

In varying embodiments said permission s are determined by any number of factors of which the follows remain merely illustrative 

c. whether the application is permitted to access and or to modify the subscriber data as per Mobile. Virtual Network Operator MNVO compliance .

Once said request has satisfied the Security Engine verifications the requests are then routed to the Queuing Module . Said Module being responsible for routing the application request to the proper IN platform based on the information entered during the Subscriber Provisioning phase A and of queuing throttling and prioritizing the requests as stored on to the IN platform s .

Each supported IN platform is associated with a corresponding request queue. Each new request is added to the appropriate queue. Its place in said queue is determined by the priority of the application which has made the request. Requests are taken off the queue and passed to the IN platform via the appropriate protocol adapter . The rate at which the requests are taken off the queue and passed is dependent on the throttling settings of each queue. The throttling of transactions is controlled on an IN element basis and can be set to limit transactions to a certain number of transactions per second or per unit time. Once set transactions will be dispatched to the IN element at a rate not exceeding the given limit. The platform and system is able to control the impact to the IN network as well as the relative order of request processing in this manner.

Continuing with reference to the Open Charging OC middleware platform and gateway system has been so articulated as to support multiple IN platforms from a variety of equipment providers. Requests taken off the IN platform queue are translated into the specific protocol of the IN platform A B C D by the IN specific adaptor A B C D respectively for that platform. In alternate embodiments replies from the IN platform may also handled by the adaptor . Said IN adaptor is responsible for executing any login and authorization required by the IN platform prior to sending requests thereof.

Although the IN specific adaptor remains dependent upon the details of the vendor provided IN platform among the various embodiments and workings of the adaptor the following four 4 non limiting instantiations have been distilled merely for the purposes of illustration and are indeed not intended to affect or dilute the intent and scope of the present invention as practitioners skilled in the art shall recognize.

The non real time machine readable record based interface generates a written communications record in a IN platform specific format for each transaction request which has been passed to the IN adaptor A by the queuing module . The communications records are then collated and fed into the IN platform A on a non real time basis to be processed.

A real time TCP IP based IN adaptor B interfaces with the IN platform B via a defined TCP IP connection. The precise protocol employed is TCP IP based and remains representative of a format compliant to the specifics of the interface as defined by the IN platform B manufacturer. Requests which are passed to the IN adaptor B by the queuing module are translated into the IN platform specific protocol and transmitted to the IN platform B for processing.

A generic real time based IN adaptor C interfaces with the IN platform C in the same manner as the real time TCP IP based adaptor B. However the communication is done over that given generic real time protocol rather than the TCP IP protocol.

The Hybrid interface D utilizes a combination of machine readable record based and real time based interfaces as aforementioned. The specifics of which requests are to be processed by which method remain dependent upon the specifications of the interfacing IN platform D.

In the preferred embodiment the art is crafted as to permit the simultaneous interfacing of multiple IN platforms each of which utilize a different IN adaptor . Each adaptor may be of a different type of one of the above types. The CORBA and SOAP XML servers will distribute the application requests to the appropriate queues which will in turn dequeue requests according to throttling parameters to the correct adaptor as described hitherto.

Entrenched within the architecture of the system resides the application activity detection art which innovatively assesses and monitors the sanity and operation of the system itself. Applications which make use of the Open Charging OC middleware platform and gateway system are ordinarily expected to transmit a given number of requests during typical operation. Said system monitors the number of transactions generated by the application per unit time period and reports a possible error condition if the expected number is derogated from.

In alternate embodiments a complementary module may be invoked whereby transactions to the IN platform which update among others a subscriber s account information and in particular the subscriber s account balance is written to a cache within the system itself rather than to the IN platform thereby minimizing network impact thereof . Upon realization of preset activity thresholds the updated subscriber information is then written to the IN Platform by the module . The subscriber information caching or virtual account application VAA module furthermore maintains synchronization with other events which can impact the subscriber balance by monitoring machine readable record which are generated by the IN platform recording such activity.

Now in reference to and which both serve to further elucidate the innovative queuing process the Queuing. Module supports advanced prioritized queuing which allows applications to be given priority over others. Priority is defined at the CORBA login level.

In reference specifically to at A said insertion position is based on transaction attributes of which non limiting illustrative examples include priority of application that generated the transaction type of transaction and length of time in the queue . At steps B and C which are better delineated with reference now to an application with a higher priority B will have its transactions processed ahead of applications with lower priority during congestion periods. Applications with lower priority C will not be starved for resources as an individual transaction s priority increases the longer it stays in the queue. This will allow transactions by the lower priority application to be processed at a lower rate. Returning to at. D said request transactions are propagated at a fixed throttled rate.

With reference now to which details an innovative though elective aspect of the Open Charging OC middleware platform and gateway system the Virtual Account Application VAA subscriber information caching mechanisms. The VAA is situated architecturally amid the Security Engine and the Queuing Module . Now whenever a request is made said Security Engine will route the request to the VAA only where the application has been so configured as to invoke it of course and processed according to the configuration parameters A.

In maintaining an accurate indication of subscriber balances the VAA processes in real time machine readable records D generated by the IN Platform . Said records allow the VAA to maintain an accurate cached balance C for each subscriber. In addition to the said cached balance C for each subscriber the VAA maintains an increment amount for each subscriber. This amount is the sum of all of the balance increments and balance deductions as negatives that the VAA has cached for the user.

The VAA then sends a single update E to The VAA then sends a single update E to the IN Platform via the Queuing Module and so forth as aforementioned in relation to . Said update E representing all of the balance increments and balance deductions. The art of the VAA thus reduces the number of transactions and network burden ultimately placed on the IN Platform as it accommodates multiple updates of the cached virtual accounts C.

The update E to the IN Platform is performed when said subscriber s balance as calculated from the cached balance and the cached increment amount passes a configurable threshold B. In alternate embodiments the update E may be performed where a configurable amount of time B has passed since the previous update.

