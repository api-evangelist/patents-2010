---

title: Network calling privacy with recording
abstract: Compliance with a privacy database and call-specific applications is provided within a network. A service control function (SCF), in communication with a privacy database, selectively establishes a call between an origin and a destination. Based on origin or destination identifiers, call parameters are determined for further operations associated with the call. A server, responsive to the call parameters, performs monitoring of the call or post-call disposition to update the privacy database.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08732190&OS=08732190&RS=08732190
owner: Gryphon Networks Corp.
number: 08732190
owner_city: Norwood
owner_country: US
publication_date: 20101130
---
This Application is a Continuation in Part of U.S. application Ser. No. 12 874 864 filed on Sep. 2 2010 the entirety of which is incorporated herein by reference.

Privacy laws that restrict the ability to make and record telephonic and other communications exist in the United States as well as other countries and vary significantly from jurisdiction to jurisdiction.

Certain Do Not Call marketing privacy laws referenced in U.S. Pat. Nos. 6 130 937 6 788 773 7 158 630 7 194 075 and 7 574 471 require marketers to restrict enable manage and otherwise apply specific treatment and business processes to marketing communications based on the jurisdiction associated with the party they are communicating with.

These Do Not Call privacy laws dictate among other things which communications may be made the time of day communications may be made disclosures that must be delivered during communications data that must be captured during communications and minimum periods such captured data must be preserved.

Other marketing privacy regulations including the U.S. Federal Trade Commission s FTC Telemarketing Sales Rule require businesses to audio record a consumer s telephonic authorization to enter into a transaction such as a charge or recurring charge to a credit card or other account.

Certain regulatory authorities including the Financial Industry Regulatory Authority FINRA in the United States and Financial Services Authority FSA in the United Kingdom require audio recording or taping of communications related to client orders negotiations and transactions in the equity bond and derivatives markets.

Similar statutes and regulations apply to other industries such as the U.S. Federal Communications Commission s FCC anti slamming rules that require telecommunications carriers to obtain and preserve audio verification of orders for telecommunications service for a minimum of two 2 years after obtaining verification.

Certain other consumer privacy laws including the U.S. federal Telecommunications Act require the consent of at least one party to a communication in order to allow recording or monitoring of the communication while other more restrictive U.S. state laws including California and Connecticut law only permit monitoring or recording when all parties to the communication have provided consent. Disclosure that a call is or will be recorded or monitored is necessary for consent.

Disclosures of specific information are also required under many other consumer protection laws including the FTC s Telemarketing Sales Rule which requires businesses to clearly provide certain information before marketing to a consumer ex. identify of seller purpose of the call or before a consumer pays for goods or services ex. material restrictions limitations or terms such as refund policy negative option features or number of debits charges or payments .

Certain businesses that are not required by law to record or monitor communications voluntarily do so for quality assurance and training purposes and are thereby subject to privacy laws requiring disclosures and consent from one or more parties to the communication. Businesses required by law to audio record or tape communications must also comply with these consent and disclosure requirements that vary from jurisdiction to jurisdiction.

Similar privacy laws and industry requirements exist and have been proposed in other jurisdictions including Australia Canada and European Union countries and vary from jurisdiction to jurisdiction.

Similar to Do Not Call privacy laws businesses using the telephone to contact consumers must restrict enable manage and otherwise apply specific treatment and business processes to marketing communications based on the jurisdiction associated with the party they are communicating with and or the jurisdiction associated with the calls origin.

Preserving the ability to conduct business using the telephone while avoiding fines criminal penalties and brand damage associated with violating these privacy and consumer protection laws and requirements is a critical and challenging issue for businesses.

Example embodiments of the present invention provide a system for managing communications in a network. A caller may employ a service provided by example embodiments when initiating an outbound or receiving an inbound communication between an origin e.g. a land line telephone mobile telephone or Voice over IP VoIP terminal and a destination.

Example embodiments of the invention may include a Privacy database configured to store call recording rules associated with a plurality of origins and destinations. A service control function SCF is configured to selectively establish a call between an origin and a destination based on the status and jurisdiction of the origin and destination indicated in the Privacy database. The SCF is further configured to provide parameters for the call based on the call recording rules. The parameters can include for example parameters specifying whether a call may be recorded whether a disclosure should be delivered or to record only one of the parties to the call. A server is configured responsive to the parameters to selectively record the call deliver certain disclosures and report an input to update the Privacy database.

Disclosures also referred to as notifications include information conveyed to one or more parties to a call at the origin and or destination that a business desires or is required by privacy or consumer protection laws to deliver including information relating to marketing call recording Do Not Call DNC legal exemptions preferences material terms payment or status or jurisdiction of the origin or destination indicated in the Privacy database or a separate storage database. Such disclosures may be delivered before during or after a call or may be delivered absent a call if the call is prohibited by a parameter indicated by the Privacy database.

A Privacy database may also include a Call Recording Rules engine with processes and information based on jurisdictions associated with the destination and or origin of a telephonic communication. This Call Recording Rules engine determines processes to apply to each individual communication based on the communications destination and or origin jurisdiction including enabling or prohibiting the communication enabling or prohibiting recording or other means of capturing the communication triggering pre and post connection electronic notifications or disclosures to one or both parties to the communication triggering recording or capture of only one or both parties verbal communication or enabling the capture via key press mouse click or otherwise or recording of consent authorization and or an electronic signature from the called party inbound call automatically or as initiated by the calling party key press mouse click or otherwise to consent to call recording authorize a transaction s and or create an legal exemption ex. express consent or written permission to privacy restrictions including DNC laws prerecorded or automated voice message regulations and or automated dialing equipment regulations and transmission or associated updates to the Privacy database or a separate storage database.

A Privacy database may also include a Do Not Call Rules engine with processes and information based on jurisdictions associated with the destination of a telephonic communication. This Do Not Call Rules engine determines processes to apply to each individual communication including checking the federal Do Not Call list appropriate state Do Not Call lists based on jurisdiction appropriate internal Do Not Call lists as well as any valid exemptions including but not limited to existing business relationships that would permit or disallow the call to be completed.

Rules engines within the Privacy database such as the DNC Rules Engine and Recording rules engine may interact with and update each other and storage databases within and outside of the Privacy database to capture and apply parameters to calls. One iteration of this interaction and updating is the capture of a legal exemption to a Do Not Call regulation via a recorded call to update a storage database such that the DNC rules engine applies the exemption to override the Do Not Call regulation during a future communication.

A Privacy database may also include a Data Repository which stores information collected during before during and or after a telephone call. The Data Repository allows analysis of the call information at a later time which may result in updates to the Call Recording Rules engine and or the Do Not Call Rules engine and or other databases such as 3party Customer Relationship Management CRM databases.

A Call Session Control Function CSCF operates within an IP Multimedia Subsystem IMS network to determine how a communication is to be routed. The CSCF in conjunction with a Home Subscriber Server HSS and in communication with the Privacy database is configured to selectively establish or prevent as well as provide disclosures before or during a call between an origin and a destination based on the status and jurisdiction of the origin and or destination as indicated in the Privacy database. The CSCF is further configured to respond to parameters for the call which may indicate further call processing based on destination status and or a subscriber status of the origin and or destination all of which is based on information provided in the Privacy database.

The CSCF also directs the Media Resource Function MRF also referred to as the media server to interact with the origin and or destination caller. These interactions include recording calls delivering disclosures and or listening to and responding to instructions via key press mouse click or other action during or after a call. The media server is configured responsive to the call parameters to conduct further processing of the call. For example the media server may produce a record of the call such as an audio recording of the call based on the originating and or terminating jurisdiction that is then stored in the Privacy database. The media server may report a code entered following establishment of the call that will also update the Privacy database.

In further embodiments the CSCF may be configured to consult and interact with additional rules engines and storage databases within the Privacy database and or other databases such as 3party Customer Relationship Management CRM databases to determine the parameters and treatment to selectively apply to each call based on jurisdiction and or client or other lists a phone number appears on such as a DNC list or DNC exemption list.

In still further embodiments the CSCF may be configured to compare the jurisdiction associated with an origin or destination ID against the Privacy database the comparison being used to update the call parameters. For example the jurisdiction status of the origin or destination may be employed by the CSCF to selectively produce a recording of the call deliver disclosures before or during the call and may provide for preventing establishment of the call.

In still further embodiments the media server may be instructed by the CSCF to monitor codes pressed before during and or following termination of the call. Upon receiving a code entered at the origin or destination before during and or following termination of the call the media server updates the Privacy database based on the code entered.

In still further embodiments the CSCF may be configured further to instruct the media server to deliver notifications or disclosures to relay certain information to the origin and or destination or indicate whether certain parameters apply to the call or the call is prohibited based on the status indicated in the Privacy database.

In still further embodiments the server may be configured responsive to the call parameters provided by the Privacy database to report a code entered at the destination following establishment of the call the code being used e.g. by the CSCF to update the Privacy database. The Privacy database may be configured further to include an indication of legal authorizations or communications preferences for a user associated with the origin or destination.

In still further embodiments the Privacy database may be comprised of multiple physical databases that may reside on separate physical devices and in geographically separate locations.

In still further embodiments the media server may be configured to convey an intervening number associated with the media server to a destination during an outbound call. In subsequent inbound calls a caller at the destination may initiate a call to the origin by dialing the intervening number thereby establishing a call through the media server to enable call recording and call disposition.

The carrier network includes a voice switch also referred to as switch which connects with a number of end terminals that may be employed by an end user to initiate and conduct a call including a land line telephone and a plurality of telephones connected to the switch via a private branch exchange PBX . In some embodiments such as a broadband network the switch may be referred to as the service switching function SSF soft switch or broadband switch. In further embodiments such as an SS7 network the switch is commonly referred to as a service switching point SSP . Also connected to the switch is a server also referred to as media server which is configured to perform functions associated with a call as described in further detail below. A further switch connected to an additional terminal may be a member of the carrier network or may comprise a portion of a second carrier network not shown .

The carrier network includes a service control function SCF operable to establish a call between an origin end terminal e.g. telephone and a destination end terminal e.g. telephone by connecting associated switches and the media server . In some embodiments the connection may be established with the use of signal transfer points STPs not shown . During a typical operation to establish a call an origin end terminal such as the telephone draws a dial tone and dials a number corresponding to a destination e.g. telephone . The dialed number is forwarded by the switch to the SCF . The SCF determines how the call is to be routed between the origin and destination. The SCF routes control messages to the switches selected to carry the voice content of the call. As a result a call is established between the origin telephone the destination telephone and includes the media server as part of the call. Further operations of a typical telecommunications networks are well understood in the art and will not be described further herein.

The Privacy database includes Do Not Call DNC rules which maintains and updates entries on contact information e.g. telephone number and respective permissions. The DNC rules may be maintained and updated based on information available at one or more data stores . The data stores may include exemption management which indicates exemptions to particular entries on a DNC list preferences which indicates particular contact preferences associated with entries internal lists which indicates entries specific to a subscriber of a call compliance service and may include entries provided in response to post call disposition cellular lists which indicates entries for mobile telephone numbers Direct Marketing Association DMA lists which includes entries of potential customers provided by a third party state lists which includes entries corresponding to one or more state DNC list and national lists which includes entries corresponding to a national DNC list.

A rules engine processes the entries and information at the data stores to determine which entries may be contacted and which entries may not be contacted. This determination provides the DNC rules with a unified set of entries and corresponding permissions. The DNC rules data stores and rules engine may incorporate features of a call compliance system as disclosed in U.S. Pat. Nos. 6 130 937 6 788 773 7 158 630 7 194 075 and 7 574 471 the entirety of which are incorporated herein by reference.

The Privacy database further includes recording rules which maintains and updates entries on contact information e.g. telephone number and respective permissions. The recording rules may be maintained and updated based on information available at one or more data stores . The data stores may include consent lists which indicates particular contact preferences associated with entries authorization lists which indicates relevant laws and regulations associated with a jurisdiction corresponding to entries and exemption lists which indicates exemptions to particular entries on a recording permissions list.

A rules engine processes the entries and information at the data stores to determine which entries may be contacted and which entries may not be contacted. This determination provides the recording rules with a unified set of entries and corresponding permissions.

The Privacy database further includes a data store for subscription permissions . The subscription permissions data store maintains entries associated with a subscriber to services provided by the Privacy database including the automatic number identification ANI or telephone numbers of end terminals employed by the subscriber to establish calls. Permissions associated with each of the entries may indicate enforcement of compliance to the DNC rules and recording rules and may further indicate parameters relating to a call. For example an entry for a subscriber terminal may indicate that for calls originating from that terminal the call is to be recorded. This indication is forwarded to the SCF which creates a parameter for an established call based on this indication. As a result the server conducts a recording of the call. A data repository may be configured to store a recording of the call and other information related to the call.

The network supports for a service providing compliance with privacy and recording laws and DNC regulations as well as further operations such as post call disposition and call monitoring. A subscriber to the service possesses one or more end terminals e.g. telephones for initiating and receiving calls. Upon enrollment in the service the subscriber identifies all of the lines at the carrier network that are to be activated for the service. For each of these lines a trigger is set on the switch to direct the switch to query the SCF when calls are placed from or to that line and may detect when the service is enabled or disabled. Based on this query which may indicate the origin ANI and destination number the SCF evaluates the query against the DNC database and the subscription permissions . Based on this evaluation the SCF determines whether the call will be established and whether additional call processing will be provided.

Operation and additional features of the service and communications network are described below with reference to and A C. In particular the network may be configured to conduct one or more of the operations relating to selective establishment of the call call disposition and call monitoring as described below. Further the network may be adapted to one or more communications networks or network technologies such as an IP multimedia subsystem IMS network see a global system for mobile communications GSM network see a long term evolution LTE network see and a signaling system 7 SS7 network .

The origin terminal connects to an originating carrier network via a router of a broadband network. The broadband router routes IMS related communications to a call service control function a configured SCF for establishing a call and once a call is established routes a trunk to a media server . The media server in turn routes the trunk to a second carrier switch at a destination carrier network the second switch being connected to a destination terminal . Alternatively the media server may be communicatively coupled to an additional switch not shown where the additional switch routes the trunk to the second carrier switch .

The network through implementation of a Privacy database including a data repository recording rules and DNC rules provides a service to a subscriber at the origin for monitoring of calls and compliance with privacy and DNC regulations. Bypassing of the network service may be enabled on a per call basis. This may be done by a user at the origin dialing a code that indicates that the dialed number of the next call is not to be processed by the network service.

A process for providing the network DNC service is described below with reference to the numerals shown in .

1 A calling agent at the origin terminal connected via a service subscribed line dials a number corresponding to the destination . If another carrier network not shown is the primary carrier for the subscribed line the agent enters a Carrier Access Code CAC to direct the switch to place the call on the appropriate network.

2 The call is held at the broadband switch while the switch generates a call origination request to the call session control function CSCF for the subscribed line. When the subscribed line sits behind a PBX the PBX provides the identification of the subscribed line e.g. ANI or Calling Party Number on the PRI D channel so that the switch can generate a call origination query to the CSCF for the appropriate line. The calling party and ANI provided by the PBX may be different numbers. In such a case the query may be based on calling party number. In alternative embodiments employing a mobile phone at the origin a Mobile Station ID MSID number is the identifier for mobile numbers.

3 The CSCF receives the call origination request and requests data from the home subscriber server HSS application servers for subscriber information. The query may identify both the origin and terminating destination numbers.

4 The HSS receives the subscriber information request and forwards the request to the Privacy database .

5 The Privacy database receives information including both the origination and terminating numbers corresponding to the request.

6 The Privacy database process the request and returns an allow or not allow call message to the HSS along with indication on whether call recording is to be performed.

7 The call routing results are sent to the CSCF the CSCF then determining how to route the call and the appropriate media server to bridge onto the call.

8 The broadband switch routes the call to the destination carrier switch and bridges onto the call a media server for call recording or playback of automated messages.

9 10 Once the call is completed and the contents of the call have been recorded the media server forwards the file containing the contents of the call to the Privacy database along with identifying information about the call. The contents of the call may be stored to the data repository.

If the call is not allowed as indicated by a not allow message from the Privacy database the media server receives the call and plays an announcement back to the origin terminal agent that the call is not permitted. The announcement may provide information to an end user regarding compliance with privacy or DNC regulations.

If the call is allowed as indicated by an allow message from the Privacy database the CSCF instructs the switch to establish the call to the terminating number connecting the call to the destination terminal . The call may be routed through the media server or through a switch not shown communicatively coupled to the media server to perform additional functions such as call monitoring and call disposition. Alternatively the call may be routed to bypass the media server . When a call is terminated i.e. the parties hang up a message containing information about the call is generated by the switch or by the media server . This message may be processed at a later time by the carrier network and those messages associated with the network DNC service are forwarded to Privacy database . These messages provide call information such as whether or not the call was answered and the length of the call. Additional functions such as call disposition and monitoring may also be performed in the network and are described below with reference to . In some embodiments such as IP Multimedia Subsystem IMS networks these messages may be referred to as web services or Application Programming Interface API calls. In other embodiments such as SS7 networks these messages may be referred to as Call Detail Records CDRs .

An origin terminal such as a computer interface in communication with the CRM network may import the CRM data to inform future calls to a present or prospective client.

1 A calling agent at the origin terminal connected via a service subscribed line dials a number corresponding to the destination . The originating call can be placed from either the home carrier network or a visiting roaming carrier network.

2 The call is held at the mobile switch while the switch generates a call origination query to the Global System for Mobile communication System Control Function gsmSCF of the home network for the subscribed line.

3 The gsmSCF receives the call origination query and sends a call certification query to the Privacy database information sent to the Privacy database include both the origination and terminating numbers.

4 The Privacy database processes the request and send back allow or not allow call message as well as an indication of whether or not call recording should be implemented.

5 The call routing results are then used by the gsmSCF to direct the mobile switch with routing instructions to complete the call and to bridge the media server onto the call for call recording.

6 Once the call is completed and the entire contents of the call have been recorded the media server forwards a file containing the contents of the call to the Privacy database along with identifying information about the call.

1 A calling agent at the origin terminal connected via a service subscribed line dials a number corresponding to the destination .

2 The call is held at the broadband switch while the switch generates a call origination request to the call session control function CSCF for the subscribed line. A Mobile Station ID MSID number may be the identifier for mobile numbers.

3 The CSCF receives the call origination request and requests data from the home subscriber server HSS application servers for subscriber information. The query may identify both the origin and terminating destination numbers.

4 The HSS receives the subscriber information request and forwards the request to the Privacy database .

5 The Privacy database receives information including both the origination and terminating numbers corresponding to the request.

6 The Privacy database process the request and returns an allow or not allow call message to the HSS along with indication on whether call recording is to be performed.

7 The call routing results are sent to the CSCF the CSCF then determining how to route the call and the appropriate media server to bridge onto the call.

8 The broadband switch routes the call to the destination carrier switch and bridges onto the call a media server for call recording or playback of automated messages.

9 10 Once the call is completed and the contents of the call have been recorded the media server forwards the file containing the contents of the call to the Privacy database along with identifying information about the call. The contents of the call may be stored to the data repository.

When call recording is provided and a call is originated from the subscribed line origin terminal the carrier switch connects the call with a media server such that the media server may monitor and generate an audio recording of the call. Once recorded the contents of the call as well as additional information about the call e.g. origin number destination number time and date may be forwarded to the Privacy database for storage and analysis. The Privacy database may include an entry indicating which of the subscribed lines include the call recording feature indicating to the SCF to enable the feature.

The network through implementation of a Privacy database including a DNC database provides a service to a subscriber at the origin for compliance with DNC regulations and call recording. A process for providing the network DNC service with call recording is described below with reference to the numerals shown in .

1 A calling agent at the origin terminal connected via a service subscribed line dials a number corresponding to the destination . If another carrier network not shown is the primary carrier for the subscribed line the agent enters a Carrier Access Code CAC to direct the switch to place the call on the appropriate network.

2 The call is held at the carrier switch while the switch generates a call origination query to the SCF for the subscribed line. When the subscribed line sits behind a PBX the PBX provides the identification of the subscribed line e.g. ANI or Calling Party Number on the PRI D channel so that the switch can generate a call origination query to the SCF for the appropriate line. The calling party and ANI provided by the PBX may be different numbers. In such a case the query may be based on calling party number. In alternative embodiments employing a mobile phone at the origin a Mobile Station ID MSID number is the identifier for mobile numbers.

3 The SCF receives the call origination query and sends a call certification query to the Privacy database. The query may identify both the origin and terminating destination numbers.

4 The Privacy database process the call certification query and returns an allow or not allow call message to the SCF along with call parameters indicating additional service features e.g. call monitoring call disposition to be performed.

5 The call routing results are sent from the SCF back to the carrier switch and the call is processed i.e. established or not established by the switch based on the SCF call routing information.

6 The carrier switch routes the call to a media server in the PSTN cloud in response to the SCF indicating that the call needs to originate through a media server e.g. for call monitoring or playback of automated messages .

7 If the call is not allowed as indicated by a not allow message from the Privacy database the media server receives the call and plays an announcement back to the origin terminal agent that the call is not permitted. The announcement may provide information to an end user regarding compliance with DNC regulations.

If the call is allowed as indicated by an allow message from the Privacy database the SCF instructs the carrier switch to establish the call to the terminating number connecting the call to the destination terminal . The media server may be connected in line with the voice trunk of the call or may be otherwise in communication with the carrier switches in a manner enabling recording of the call.

8 Once the call is completed and the media server has recorded the entire contents of the call the media server forwards the file containing the contents of the call to the Privacy database along with identifying information about the call such as the originating number the terminating number and with the date and time of the call.

When call disposition is provided e.g. as a feature of a network DNC service and a call is originated from the subscribed line origin terminal the carrier switch connects the call with a media server so that dual tone multi frequency signaling DTMF tones can be detected during the call the DTMF tones indicating the call disposition. For example a dialed code 0 would indicate that the dialed number should be added to the internal DNC list e.g. list in for the subscriber. The Privacy database may include an entry indicating which of the subscribed lines include the call disposition feature indicating to the SCF to enable the feature.

The network through implementation of a Privacy database including a DNC database provides a service to a subscriber at the origin for compliance with DNC regulations and call disposition. A process for providing the network DNC service with call disposition is described below with reference to the numerals shown in .

1 A calling agent at the origin terminal connected via a service subscribed line dials a number corresponding to the destination . If another carrier network not shown is the primary carrier for the subscribed line the agent enters a Carrier Access Code CAC to direct the switch to place the call on the appropriate network.

2 The call is held at the carrier switch while the switch generates a call origination query to the SCF for the subscribed line. When the subscribed line sits behind a PBX the PBX provides the identification of the subscribed line e.g. ANI or Calling Party Number on the PRI D channel so that the switch can generate a call origination query to the SCF for the appropriate line. The calling party and ANI provided by the PBX may be different numbers. In such a case the query may be based on calling party number. In alternative embodiments employing a mobile phone at the origin a Mobile Station ID MSID number is the identifier for mobile numbers.

3 The SCF receives the call origination query and sends a call certification query to the Privacy database. The query may identify both the origin and terminating destination numbers.

4 The Privacy database process the call certification query and returns an allow or not allow call message to the SCF along with call parameters indicating additional service features e.g. call monitoring call disposition to be performed.

5 The call routing results are sent from the SCF back to the carrier switch and the call is processed i.e. established or not established by the switch based on the SCF call routing information.

6 The carrier switch routes the call to a media server in the PSTN cloud in response to the SCF indicating that the call needs to originate through a media server to provide call disposition as well as other possible functions e.g. call monitoring or playback of automated messages .

7 If the call is not allowed as indicated by a not allow message from the Privacy database the media server receives the call and plays an announcement back to the origin terminal agent that the call is not permitted. The announcement may provide information to an end user regarding compliance with DNC regulations.

If the call is allowed as indicated by an allow message from the Privacy database the SCF instructs the carrier switch to establish the call to the terminating number connecting the call to the destination terminal . The media server may be connected in line with the voice trunk of the call or may be otherwise in communication with the carrier switches to monitor the call for DTMF tones.

8 When the media server detects a call disposition event e.g. a compliant DTMF code during a call the server generates and forwards a message to the Privacy database that provides the disposition code entered as well as the originating number terminating number and date and time of the call during which the DTMF code was entered.

The network may be configured to perform additional operations such as call recording as described below with reference to .

In some embodiments a network may be configured to selectively monitor and generate a recording of a call across the network. Call recording may be conducted for example to monitor a subscriber s compliance with relevant business practices and regulations. To accomplish call recording for a call initiated by a subscriber an outbound call a query to a Privacy database may include a query as to whether the call should be recorded. If the answer to the query is positive then a media server may be implemented to record the call. To accomplish call recording for a call to a subscriber initiated by an outside line an inbound call a carrier switch may be configured with a trigger to initiate a query similar to that described above. illustrate various methods of call recording and are described below.

2 A Terminating Attempt Trigger TAT is set on the subscriber line such that responsive to the call the carrier switch holds the call for additional call processing rules.

4 Results of the query indicating call routing instructions are sent from the SCF back to the carrier switch . The carrier switch routes the call based on the SCF call routing information.

5 The carrier switch routes the call to a media server in the PSTN cloud in response to the SCF indicating that the call needs to originate through the media server for call recording.

6 The media server receives the call and completes the second leg of the call to the terminal thereby establishing the call. The media server initiates recording of the call.

7 Once the call is completed and the media server has completed an audio recording of the call a file containing the contents of the call are forwarded to the Privacy database along with identifying information about the call.

The origin terminal connects to an originating carrier network via a router of a broadband network. The broadband router routes IMS related communications to a call service control function a configured SCF for establishing a call and once a call is established routes a trunk to a media server . The media server in turn routes the trunk to a second carrier switch at a destination carrier network the second switch being connected to a destination terminal . Alternatively the media server may be communicatively coupled to an additional switch not shown where the additional switch routes the trunk to the second carrier switch . The network through implementation of a Privacy database including a data repository recording rules and DNC rules provides a service to a subscriber at the origin for monitoring of calls and compliance with privacy and DNC regulations.

Under some circumstances a call may not be initiated in a manner that allows the CSCF to selectively establish the call. For example a calling agent may not be on network meaning that the origin terminal may be establishing an outbound call through one or more networks outside of the expected originating carrier network . As a result the CSCF may not receive the call request and the media server may not be configured to record the call contrary to an indication by the Privacy database . Alternatively the calling agent may connect to the network and service using a carrier identification code CIC . Although this connection may enable selective establishment and recording of a call the consumer may receive the caller ID of the calling agent s terminal.

An outbound call circumventing the originating carrier network may also affect subsequent inbound calls. For example a consumer receiving an off network call may view the telephone number of the caller s terminal through a caller ID display or other device. Thus if the customer returns the agent s call by dialing the displayed telephone number then the resulting inbound call may also circumvent the originating carrier network thereby preventing the media server from recording the inbound call.

Under other circumstances a carrier network associated with the customer may initiate and establish a call with a calling agent at a terminal on network i.e. coupled to the carrier network in a manner that prevents the media server from recording the call. This may occur for example when the consumer s network operates independent from the carrier network and establishes a voice trunk to a carrier switch of the carrier network in a manner that does not give sufficient notice to the CSCF to initiate a recording of the call.

Embodiments described below with reference to ensure selective establishment and recording of a call in view of the aforementioned configurations. The network may operate in a manner comparable to the network described above with reference to with the addition of providing an intervening number as a caller ID to the consumer . This intervening number rather than being associated with the origin terminal may be associated with the media server or another component within the carrier network . As a result the consumer may utilize this intervening number when returning a call to the calling agent routing the call first to the media server and ensuring that a recording of the call can be conducted. An example of such an inbound call is described below with reference to .

A process for providing the network service in an outbound call is described below with reference to the numerals shown in .

1 A calling agent at the origin terminal connected via a service subscribed line dials a number corresponding to the destination . If the origin terminal is located at a different carrier network not shown or the calling agent is not a subscriber to the service the agent may access the originating network remotely. For example the calling agent may enter a Carrier Access Code CAC to direct the switch to place the call on the appropriate network.

2 The call is held at the broadband switch while the switch generates a call origination request to the call session control function CSCF for the subscribed line. When the subscribed line sits behind a PBX the PBX provides the identification of the subscribed line e.g. ANI or Calling Party Number on the PRI D channel so that the switch can generate a call origination query to the CSCF for the appropriate line. The calling party and ANI provided by the PBX may be different numbers. In such a case the query may be based on calling party number. In alternative embodiments employing a mobile phone at the origin a Mobile Station ID MSID number is the identifier for mobile numbers.

3 The CSCF receives the call origination request and requests data from the home subscriber server HSS application servers for subscriber information. The query may identify both the origin and terminating destination numbers.

4 The HSS receives the subscriber information request and forwards the request to the Privacy database .

5 The Privacy database receives information including both the origination and terminating numbers corresponding to the request.

6 The Privacy database process the request and returns an allow or not allow call message to the HSS along with indication on whether call recording is to be performed. The Privacy database further provides the intervening number to be displayed to the consumer in place of the calling agent s originating number at the origin terminal .

7 The call routing results are sent to the CSCF the CSCF then determining how to route the call and the appropriate media server to bridge onto the call. The CSCF further instructs the media server to display the intervening number as the caller ID displayed to the consumer .

8 The broadband switch routes the call to the destination carrier switch and bridges onto the call a media server for call recording or playback of automated messages.

9 10 Once the call is completed and the contents of the call have been recorded the media server forwards the file containing the contents of the call to the Privacy database along with identifying information about the call. The contents of the call may be stored to the data repository.

If the call is not allowed as indicated by a not allow message from the Privacy database the media server receives the call and plays an announcement back to the origin terminal agent that the call is not permitted. The announcement may provide information to an end user regarding compliance with privacy or DNC regulations.

If the call is allowed as indicated by an allow message from the Privacy database the CSCF instructs the switch to establish the call to the terminating number connecting the call to the destination terminal . The call may be routed through the media server or through a switch not shown communicatively coupled to the media server to perform additional functions such as call monitoring and call disposition. Alternatively the call may be routed to bypass the media server . When a call is terminated i.e. the parties hang up a message containing information about the call is generated by the switch or by the media server . This message may be processed at a later time by the carrier network and those messages associated with the network DNC service are forwarded to Privacy database . These messages provide call information such as whether or not the call was answered and the length of the call. Additional functions such as call disposition and monitoring may also be performed in the network and are described below with reference to . In some embodiments such as IP Multimedia Subsystem IMS networks these messages may be referred to as web services or Application Programming Interface API calls. In other embodiments such as SS7 networks these messages may be referred to as Call Detail Records CDRs .

1 The consumer places a call to a calling agent at the origin terminal by dialing the intervening number a number that is configured to terminate on the media server . Alternatively the intervening number may terminate at another component not shown that is communicatively coupled to the media server .

3 The media server queries the Privacy database supplying the intervening number to identify the destination number of the agent the number terminating at the origin terminal and to determine if the call should be recorded.

4 The Privacy database processes the request and returns the destination number to the media server along with an indication of whether the call is to be recorded.

5 The media server completes the second leg of the call to the origin terminal and proceeds to record the call as well as monitor for any call disposition according to the parameters at the Privacy database .

6 Once the call is completed and the entire contents of the call have been recorded a file containing the contents of the call may be forwarded to the Privacy database along with identifying information about the call.

It should be understood that the block diagram of and the flow diagrams of are examples that can include more or fewer components be partitioned into subunits or be implemented in different combinations. Moreover the flow diagrams may be implemented in hardware firmware or software. If implemented in software the software may be written in any software language suitable for use in networks and network devices as illustrated in . The software may be embodied on any form of non transitory computer readable medium such as RAM ROM or magnetic or optical disk and loaded and executed by generic or custom processor s .

While this invention has been particularly shown and described with references to example embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of the invention encompassed by the appended claims.

