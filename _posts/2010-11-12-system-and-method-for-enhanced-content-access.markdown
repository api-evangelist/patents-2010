---

title: System and method for enhanced content access
abstract: A method and system for facilitating HLR access includes receiving a query request from a query entity, processing the query request to yield an SS7 request message, dispatching the SS7 request message to a HLR, receiving an SS7 response message from the HLR, constructing a query response, and returning the query response to the query entity.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08311538&OS=08311538&RS=08311538
owner: Sybase 365, Inc.
number: 08311538
owner_city: Reston
owner_country: US
publication_date: 20101112
---
This application is a continuation of U.S. application Ser. No. 12 776 890 filed May 10 2010 which is a continuation in part application of U.S. application Ser. No. 11 263 799 filed Nov. 2 2005 which claims the benefit of U.S. Provisional Patent Application No. 60 623 861 filed on Nov. 2 2004 all of which are incorporated herein by reference in their entireties.

The present invention relates generally to telecommunications services. More particularly the present invention facilitates the issuance of inquiries to along with the appropriate processing of responses that are received from Home Location Register HLR facilities and other similarly situated facilities.

A wireless telecommunications environment contains a number of different elements. While the precise nature makeup organization etc. of the elements within a particular environment may vary depending upon the technology at play e.g. Global System for Mobile communications GSM Code Division Multiple Access CDMA Time Division Multiple Access TDMA etc. the portions of a wireless telecommunications environment that are of interest and importance to the present discussion may be illustrated through the high level generalized diagram of a portion of a hypothetical Wireless Carrier s WC s environment that is presented in .

As appropriate and as required additional more detailed information may be obtained from any number of sources including inter alfa references such as Wireless and Mobile Network Architectures by Lin and Chlamtac John Wiley Sons Inc. 2001 and on line treatises.

For purposes of completeness the following elements are noted in the high level diagram that is presented in 

B Base Station BS . A logical aggregation of for example controller e.g. Base Station Controller BSC functionality and transmitter receiver e.g. Base Transceiver Station BTS functionality that realizes a cell which services one or more MSs. Four BSs are depicted in FIG. BSa along with its cell BSb along with its cell BSc along with its cell and BSd along with its cell .

C Mobile Switching Center MSC . A specialized switching system that in the instant depiction supports or services the four BSs BSa BSb BSc and BSd through the connections and respectively .

D Visitor Location Register VLR . A repository containing selected temporary or transient information for those specific MSs that are currently being serviced by the VLR s associated MSC .

E HLR . A permanent repository containing identifying profile subscription etc. information for all of the MSs within the instant WC s environment.

Each MS Wireless Device WD that is supported by a WC may have a logical record in the WC s HLR. Such a logical record 

 1 May be keyed indexed etc. by one or more identifiers that are associated with the WD e.g. the WD s TN perhaps Mobile Directory Number MDN or Mobile Station International ISDN Number MSISDN an International Mobile Subscriber Identity IMSI etc. and

 2 May contain a wide range of MS specific and WD specific information including possibly inter alia MS identifying information MS preferences MS account status services such as for example roaming SMS MMS etc. messaging enhanced data facilities such as General Packet Radio Service GPRS call forwarding call waiting caller identification etc. that are enabled WD capabilities and characteristics an identifier of the MSC that currently services the WD based on the WD s current physical location etc.

G Public Switched Telephone Network PSTN Cloud . Access to the various interconnected public land line etc. telecommunications networks.

Central amongst the elements that are depicted in the hypothetical WC s environment in is the HLR facility . A WC s HLR serves as something of a magic decoder ring of sorts from which key MS information may be retrieved and through which critical activities may be completed. Illustrative uses include inter alia 

A Confirming that a WC does in fact currently own or service a MS. This is of critical importance given for example the increasing presence of Number Portability NP regimes.

B Confirming the specific services options etc. that a MS has elected and for which e.g. based on things such as current account balances etc. a MS is presently eligible.

C Ascertaining the current physical location of a MS e.g. what MSC currently services the MS and as a consequence identifying the viable routing and call message delivery options that are available at that moment in time.

F Supporting the proper routing and delivering of e.g. Short Message Service SMS and Multimedia Message Service MMS and other messages.

An HLR is typically accessed via SS7. As a result the various activities that were described in A F above are commonly accomplished through an exchange of Mobile Application Part MAP and other request and response SS7 messages. One specific MAP message that is of interest is the SendRoutingInformation SRI message which is 

1 Realized as LocationRequest or LOCREQ and defined in the Telecommunications Industry Association TIA Electronic Industries Alliance EIA 41 D specification for an American National Standards Institute ANSI flavor of SS7 as used domestically .

2 Realized as MAP SEND ROUTING INFO and defined in the International Telecommunication Union ITU Q.771 Q.775 specifications for an ITU flavor of SS7 as used internationally .

Access to a WC s HLR is typically very tightly controlled by the WC. This is due partly to the critical importance of an HLR as described above partly to the mechanism that is used to access an HLR typically involving the execution of reciprocal business agreements and the explicit granting of permissions and access rights via a trusted SS7 network and partly to the sensitive MS specific information and other proprietary business information that is housed in an HLR.

As noted above a logical HLR record for a particular MS WD may contain a wide range of MS specific and WD specific information. A WC may consider certain aspects of that information such as for example MS account status to be proprietary business information that among other things the WC does not wish to disclose to outside entities. As well a WC may consider other aspects of that information such as for example a WD s TN to be public information that among other things the WC does not mind disclosing to outside entities.

Thus the conundrum . . . . How does an interested entity e.g. a third party message delivery service efficiently and seamlessly gain access to a range of WC s HLRs The present invention provides a solution.

According to one exemplary aspect the present invention relates to a method for facilitating HLR access comprising receiving a query request from a query entity performing one or more processing steps on the query request yielding an SS7 request message dispatching the SS7 request message to a HLR receiving an SS7 response message from the HLR performing one or more processing steps on the SS7 response message yielding a query response and returning the query response to the query entity.

According to another exemplary aspect of the present invention a system is disclosed for facilitating HLR access. The system includes a query entity a query request a query response and an administration and management interface. The system is operable to accept a query request from a query entity generate an SS7 request message dispatch the SS7 request message to a HLR receive an SS7 response message from the HLR generate a query response and dispatch the query response to the query entity all under the control of operating rules that are dynamically configurable through an administration and management interface.

These and other features of embodiments of the present invention will be more fully explained below in conjunction with the drawings.

To better understand the particulars of the present invention consider for a moment the following hypothetical example. In this example which is illustrated at a high level by the diagram that is presented in the present invention serves as a key portion of a comprehensive routing engine. A complete description of the features capabilities etc. of aspects of an illustrative routing engine facility a Message Routing Subsystem MRS may be found in pending U.S. patent application Ser. No. 10 831 329 entitled AN INTERMEDIARY NETWORK SYSTEM AND METHOD FOR FACILITATING MESSAGE EXCHANGE BETWEEN WIRELESS NETWORKS filed with the U.S. Patent and Trademark Office USPTO on 26 Apr. 2004 and which is herein incorporated by reference in its entirety.

Our hypothetical routing engine which in the instant example is offered under an Application Service Provider ASP like model provides authoritative real time answers to queries such as At this precise moment in time what WC owns or services the MS that resides at 1 703 555 1212 

Referring to the diagram that is presented in entities that are external to the ASP E En including for example third party message processing services and entities that are within the ASP I In including for example elements of the ASP s own message delivery service s connect with and submit inquiries to a consolidated Electronic Numbering ENUM facade . The ENUM facade abstracts away and otherwise isolates a range of behind the scenes complexities including 

A A e.g. Web based user interface that provides comprehensive administration and management capabilities.

B A repository containing a dynamically updatable configuration and control information and b real time usage and tracking information to support inter alia the possible billing of the external and or internal entities i.e. E En and I In respectively .

C A local cache wherein retrieved results may be optionally preserved for subsequent re use. Additionally configurable rules for the use of the cache and configurable logic controlling the aging and expiration of cache entries.

D An Internal LookUp Engine ILUE through which the contents of the environment s Composite Routing Data CRD repository may be accessed via one or more intermediate backing stores Backing Store Backing Storen .

E An External LookUp Engine ELUE through which external lookup Telephone Number TN translation etc. facilities including inter alia foreign NP databases may be accessed.

The various external E En and internal I In entities may communicate with the ENUM facade using any number of mechanisms including inter alia a simple text based request response protocol or a more robust e.g. Extensible Markup Language XML based request response protocol riding atop a secured or an unsecured Internet Protocol IP based or other channel. As one illustrative example an external entity might communicate with the ENUM facade through an XML based Application Programming Interface API over a secure HyperText Transfer Protocol HTTP connection while an internal entity by benefit of it being internal might communicate with the ENUM facade through an XML based API over a regular HTTP connection. It will be readily apparent to one of ordinary skill in the relevant art that numerous other arrangements are easily possible.

It is important to note that while two specific communications approaches are illustrated for the ELUE IP based and SS7 based it will be readily apparent to one of ordinary skill in the relevant art that the addition of other communications approaches is easily possible.

It is important to note that the indicated repositories or stores Configuration Local Cache Backing Store Backing Storen CRD etc. may be physically realized through any combination of inter alia traditional Relational DataBase Management System RDBMS solutions in memory database solutions proprietary solutions etc.

Amongst other things the ILUE and ELUE facilities encapsulate all of the data through for example the CRD application logic etc. that is necessary to support inter alia all of the different TN numbering plans schemes that are found around the world and all of the different NP regimes that are active around the world. These are without risk of overstatement not insignificant matters.

Using the service framework that was presented above it is through the FLUE facility that the present invention may be found. Focusing just on an SS7 based communications model but recognizing that other for example IP based communication models are easily possible we turn to the high level diagram that is presented in .

As depicted in the diagram that is presented in an array of Connection Manager CM processes CM CMn support connections C Cn with query entities for example an ELUE. Through an intermediate set of queues Q Qn which help to balance any fluctuations etc. in the flow of incoming queries and outgoing responses an array of Gateway Interface GI processes GI GIn communicate with mated SS7 Gateway GW instances SS7 GW SS7 GWn to 

A Retrieve a request for a query e.g. What WC owns or services the MS that resides at 1 703 555 1212 from a queue Q Qn .

B Construct an outgoing SRI request SS7 message containing possibly amongst other data elements or values the TN e.g. Mobile Directory Number MDN or Mobile Station International ISDN Number MSISDN of the instant MS.

C Dispatch the outgoing SRI request message to an SS7 GW instance GI GIn for subsequent routing and delivery to the destination WC s Carrier Carriern HLR facility HLR HLR via the SS7 cloud .

E Extract key data elements including possibly amongst other data elements the e.g. E.164 address of the MSC that is currently servicing the instant MS from the received SRI response SS7 message.

F Create a query response construct and populate it with the data elements that were extracted from the received SRI response SS7 message.

G Deposit the completed query response construct on a queue Q Qn for retrieval and subsequent return to the query initiator.

A e.g. Web based user interface provides comprehensive administration and management capabilities. Additionally a dynamically updatable repository of configuration and control information is available.

Thus the present invention provides something of a screen behind which individual WCs may reside. Consider the simple case of numerous WCs and a single ASP that has implemented the present invention 

A A WC may establish a business relationship with and subsequently execute all of the necessary non trivial reciprocal agreements with a single trusted entity i.e. the ASP .

B A WC may grant and subsequently manage access rights privileges permissions etc. to their HLR to a single trusted entity i.e. the ASP .

C The ASP may optionally redact based on dynamically updatable configuration or control information portions of the data that is returned from a WC s HLR before populating a query response construct thus protecting HLR information that a WC may deem to be confidential or otherwise sensitive .

Additionally an ASP may 1 optionally map transform manipulate etc. portions of the data that is returned from a WC s HLR and possibly include aspects of those operations e.g. portions of the results of a mapping operation portions of the results of a transformation operation etc. in a query response construct and 2 optionally include in a query response construct other static or dynamic information. For example in the case of the query What WC owns or services the MS that resides at 1 703 555 1212 an ASP may after possibly inter alia dispatching a request message to an HLR and receiving a response message from the HLR and completing various processing operations populate a query response construct with possibly among other things the specified TN i.e. 1 703 555 1212 a coded value e.g. 132 WC23 etc. that identifies the WC that owns or services the TN and a success failure status indicator.

D The ASP may track each and every query request response exchange and subsequently bill each initiating query entity. One or more of the WCs that reside behind the ASP s screen may optionally share in the revenue through various dynamically configurable fund distribution schemes including inter alia flat rate simple percentage complex percentage etc. that the ASP realizes.

E The ASP may absorb changes by WCs in HLR access models or paradigms e.g. as WCs implement new protocols etc. such as IP SS7 over IP Signaling Transport SigTran etc. .

In the facilities that were described above and a query entity either internal or external may communicate with a CM CM CMn in and CM CMn in process through any number of mechanisms. For example communication may take place through an XML based API over an HTTP connection possibly regular HTTP for internal entities secure HTTP for external entities . It will be readily apparent to one of ordinary skill in the relevant art that numerous other mechanisms along with alternative arrangements etc. within a particular mechanism are easily possible.

In the facilities that were described above and the intermediate queues Q Qn in and Q Qn in may be configured to operate under any number of models or paradigms including inter alia First In First Out FIFO Last In First Out LIFO custom etc. Additionally individual queue entries may optionally be assigned a priority number or level to facilitate different queue entry retrieval orders in support of for example free and or fee based value add Quality of Service QoS offerings .

In the facilities that were described above and a local cache in in may optionally be employed. Such a cache may be used to hold or preserve retrieved results for subsequent re use and would include possibly amongst other items the cache repository itself configurable rules for the use of the cache and configurable logic controlling the aging and expiration of cache entries.

In the facilities that were described above and it is important to note that the indicated repositories or stores Configuration in in Local Cache in in etc. may be physically realized through any combination of inter alia traditional RDBMS solutions in memory database solutions proprietary solutions etc.

In the facilities that were described above and a GI process GI Gin in and GI Gin in was mated to an SS7 GW instance SS7 GW SS7 GWn in and SS7 GW SS7 GWn in . Under an alternative embodiment since the underlying SS7 messaging is in fact idempotent each GI process GI Gin in and GI GIn in could be disassociated from a SS7 GW instance SS7 GW SS7 GWn in and SS7 GW SS7 GWn in and a GI process GI GIn in and GI Gin in could employ a select a GW instance SS7 GW SS7 GWn in and SS7 GW SS7 GWn in as needed model under which a GI process GI Gin in and GI GIn in would momentarily attach itself to an available SS7 GW instance SS7 GW SS7 GWn in and SS7 GW SS7 GWn in when it needs to dispatch an outgoing SS7 message and a SS7 GW instance SS7 GW SS7 GWn in and SS7 GW SS7 GWn in would momentarily attach itself to a GI process GI GIn in and GI GIn in when it needs to hand off an incoming SS7 message . Under such an alternative model techniques such as for example unique GI process ID values and unique SS7 GW ID values and a dynamically updatable ID mapping facility would be used to tie together SS7 request messages and their associated responses.

In the facilities that were described above and ANSI ITU and or a mixture of ANSI and ITU SS7 GWs SS7 GW SS7 GWn in and SS7 GW SS7 GWn in may be employed. The SS7 facing side of each SS7 GW preferably isolates and thus abstracts away all of the SS7 complexities including inter alia SS7 Point Code PC format structure and assignment the specific SS7 cloud that is to be used should multiple clouds be available adjacent SS7 Signaling Point SP addresses etc. thereby facilitating the operation of a mixed ANSI and ITU environment.

Under one possible embodiment of the present invention the outbound SS7 messages that are generated may optionally benefit from the type or sort of dynamic message addressing capabilities that are described in pending U.S. patent application Ser. No. 11 137 351 entitled SYSTEM AND METHOD FOR INTELLIGENT DYNAMIC MESSAGE ADDRESSING and filed with the USPTO on 26 May 2005 which is herein incorporated by reference in its entirety.

While the discussion above included one particular type of SS7 message exchange an outgoing SRI request message and an incoming SRI response message it will be readily apparent to one of ordinary skill in the relevant art that numerous alternatives including possibly inter alia different message types different message sequences etc. are easily possible.

It is important to note that the hypothetical example that was presented above which was described in the narrative and which was illustrated in the accompanying figures is exemplary only. It will be readily apparent to one of ordinary skill in the relevant art that numerous alternatives to the presented example are easily possible and indeed are fully within the scope of the present invention.

