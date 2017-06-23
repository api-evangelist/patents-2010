---

title: System and method for provisioning and managing network access and connectivity
abstract: Systems and methods for providing distributed network solutions to end user customers by acting as a neutral demarcation point between the last mile and the long haul portion of a telecommunications network. A network provisioning platform evaluates transport alternatives to identify routes and networks having the highest reliability metrics. Access circuits are aggregated to the optical level at the earliest possible point in the network. Service to on-net networks are provisioned rapidly.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09363160&OS=09363160&RS=09363160
owner: HARRIS CORPORATION
number: 09363160
owner_city: Melbourne
owner_country: US
publication_date: 20100331
---
This application claims priority to U.S. Provisional Patent Application Ser. No. 61 165 122 filed Mar. 31 2009 which is hereby incorporated by reference herein in its entirety.

Embodiments of the invention relate generally to carrier network connectivity and more particularly to providing and managing carrier neutral network access connectivity.

The traditional telecommunications carrier model provides bundled access to voice data and Internet services to all users. This carrier strategy places negotiating control between the carrier and users in the hands of the carrier. By requiring access as part of the bundled solution the carrier model restricts users and limits future options based on past design decisions made by the carriers.

Embodiments of the invention are directed to systems and methods for providing distributed network solutions to end user customers by acting as a neutral demarcation point between the last mile and the long haul portion of a telecommunications network. The network provisioning platform in embodiments of the invention evaluate transport alternatives to identify routes and networks having the highest reliability metrics. Access circuits are aggregated to the optical level at the earliest possible point in the network. Service to on net networks are provisioned rapidly.

The following description of the embodiments is provided as an enabling teaching of the invention and its best currently known embodiments. Those skilled in the relevant art will recognize that many changes can be made to the embodiments described while still obtaining the beneficial results. It will also be apparent that some of the desired benefits of the embodiments described can be obtained by selecting some of the features of the embodiments without utilizing other features. Accordingly those who work in the art will recognize that many modifications and adaptations to the embodiments described are possible and may even be desirable in certain circumstances and are a part of the invention. Thus the following description is provided as illustrative of the principles of the embodiments of the invention and not in limitation thereof since the scope of the invention is defined by the claims.

As illustrated in the core network access provisioning platform also referred to herein as Core180 provides secure and dedicated long haul transport over the platform s private backbone network. The platform acts as a neutral gateway and virtual point of presence into significantly more providers than those that are available to the customer premise. The platform intersects hundreds of carrier networks and enables additional control including but not limited to location speed and value. The platform can deliver local connectivity to any endpoint in North America. The dashed lines in the figure represent future segments of the backbone network.

The core network access provisioning platform proactively manages company and client customer networks by providing 1 network visibility through either a web based portal or application programming interface API integration 2 managed cross connections circuit mapping and testing for end to end control 3 a 24 7 network control center for integrated trouble ticketing and resolution and 4 real time remote monitoring and diagnostics.

In one embodiment a customer Order Management System OMS manages a plurality of operational functions including but not limited to sales quotes requests for vendor pricing equipment inventory costs selection and management of vendors i.e. carriers order fulfillment and trouble ticketing. The OMS facilitates the unique process flow for fulfilling orders and supplier management from creating customer quotes to final customer acceptance of service to management and maintenance of the service. The unique process flow captures the network access provisioning platform model which involves identifying ordering and integrating multiple carrier services into the platform s own value added services. Unlike traditional carriers that typically route the bulk of their services through their own networks integrating only tail circuits from other carriers the network access provisioning platform integrates a variety of services and segments from many suppliers at unique integration points in the provisioning platform s backbone network to provide the best price performance value to end user customers.

The OMS provides a plurality of screens processes and data to support the network access provisioning platform. The OMS can obtain orders from multiple customers and or resellers design end to end services with selection of any available supplier for any segment or section manage the ordering installation and integration of multiple supplier services and maintain these services across multiple suppliers through the lifetime of the service.

The major components of the network access provisioning platform can include one or more of the following functions 

In an exemplary embodiment OMS utilizes a unique workflow capability. The workflow identifies a series of tasks for users to perform and complete based on steps for fulfilling a process. The process can be any process requiring user interaction with screens and data to fulfill the process steps. The workflow engine is defined generically herein so that a workflow WF Item can be created for any set of data e.g. a customer order a carrier order a trouble ticket an engineering work request creation of a customer invoice using configuration capabilities only without recoding any software. An example of a new Install Customer Order workflow is show in . The resulting tasks for this workflow are shown in . The tasks for a particular customer order are shown in .

The workflow engine is capable of attaching workflows to other workflows so that a chain of workflows can be created. For example a workflow for carrier orders can be attached to a workflow for customer orders so that a single customer order can initiate tasks for multiple carrier orders.

As can be seen in the workflow also defines a baseline set of tasks that represent the expected start and end dates of tasks for that instance of a workflow. The actual tasks may start and end before or after the baseline start and end dates. The discrepancies can be flagged and reported on as required.

Workflows can be ordered in a number of ways 1 a task can lead to one or more subsequent tasks 2 a task can be initiated by one or more preceding tasks 3 completion of tasks can be made contingent on the status or value of variables associated with the WF Item. For the first method of ordering a task can lead to one or more subsequent tasks either after all subsequent tasks are initiated or after only a subset of the subsequent tasks are initiated. For the second method a task can be initiated by one or more preceding tasks either after all preceding tasks are completed or after one or more of the preceding tasks have been completed. For the third method completion of tasks can be made contingent on the status of a variable associated with the WF Item such as the entry of a FOC date before the get FOC date task can be completed.

Workflows can be owned by specific workgroups and the manager of the workgroup can assign individuals to that workflow or to specific tasks in the workflow. In that case only the manager sees the tasks until they are assigned at which point the tasks become visible to the assigned individual as well as to the manager. The manager can also reassign tasks at any time as required.

The workflow engine can also generate ad hoc tasks based on conditions defined by data configuration. For example if a task is overdue by a certain number of days a reminder task can be initiated such as a customer update task to provide information to the customer on that date. E mail can be sent out to individuals or groups on task initiation or task completion as required. A more detailed description of the OMS and its components follows the description of the price generator application.

In another embodiment a Price Generator application provides and manages pricing requests from the Defense Information Systems Agency DISA . The Price Generator allows DISA users to request and obtain prices for circuits between any combinations of nearly 500 military locations. The circuits can be used for voice data and Internet traffic with circuit speeds bandwidths ranging from 56 Kbps to OC 192 9953 Mbps . Optical Carrier OC levels describe a range of digital signals that can be carried on SONET fiber optic networks. OC 192 is a network line with transmission speeds of up to 9953 Mbps. Pricing is based on the end locations and the speed of the circuits and is provided separately for each year of the DISA contract. The tool the user interface and the pricing database for this embodiment were developed based on extensive analysis of DISA s requirements the geographic distribution of the 500 military locations network costs over time location accessibility currently available network services network transition status among other factors and as such represents a unique tool that captures a significant corporate knowledge base. The resulting pricing database contains nearly 10 000 price point combinations which is expected to continue growing.

The Price Generator software user interface and data represent inseparable components of an integrated application built specifically to meet the needs of DISA s extensive pricing requirements in terms of the number of locations serviced the range of services and the number of years 10 over which pricing is provided.

To effectively manage pricing efforts the following activities have to be coordinated 1 Sales requesting pricing for customers 2 Operations requesting costs from carriers 3 Operations Management setting the customer price based on costs and margin 4 Sales providing a quote to the customer and 5 capturing customer feedback on the price. In the following description references to price relate to quotes to customers and references to cost relate to payments to vendors.

The Pricing Tool is separate from OMS in order to avoid creating facility records and establishing network segments in order to get quotes that may not turn into orders.

A standard interface enables Sales to request pricing from Operations for each distinct customer requirement. In one embodiment an input screen is provided that Sales can populate with the quote details. The applicable data entry fields for the input screen could include 

Once the salesperson has created a customer RFQ Operations could receive an e mail notification that a Customer RFQ has been created with the data entered in the fields above.

The pricing requests sent to each carrier and their responses need to be tracked. The Carrier RFQs can be sent to multiple vendors and may include several network segments per Customer RFQ. In one embodiment the fields that drive the carrier RFQ Customer RFQ Number Customer Name Customer A Z Loc Speed and Term would be carried over from the Sales input screen. Operations would define the network segments that require Carrier RFQs. Operations would select the carriers to receive Carrier RFQs from a list of carrier options . The system would automatically assign a Carrier RFQ number e.g. the Customer RFQ number plus a suffix for each segment and create a database entry for each quote requested. Operations populates the cost fields for each Carrier RFQ as vendor quotes are received.

For example a Customer RFQ 123 could include three network segments two of which are off net and need quotes. Segment could be sent to three carriers and Segment could be sent to two vendors. This would mean that five entries would be generated in the Carrier Request for Quote database Verizon Business XO and Cavalier could have an entry for Carrier RFQ 123 01 and Verizon Business and Qwest could have an entry for Carrier RFQ 123 02. The on net segment would be priced as part of the Sales Quote Generation process.

A table having the following fields would be sent to the vendors 1 Carrier RFQ Number 2 Network A and Z Loc Address City Zip NPA NXX 3 Speed 4 Term 5 MRC 6 NRC and 7 Notes Special Terms.

The system can query the Carrier RFQ database on the following fields 1 Customer RFQ number 2 Carrier RFQ Number 3 Customer A and Z Locs 4 Network Segment A and Z Locs 5 Speed 6 Customer Name 7 Carrier.

After the Sales Quote is completed a form is automatically sent to the Sales originator and or can be created by Sales. The form could include standard language for disclaimers and the following data fields 

After the quote process the system tracks whether the Sales Quote resulted in an order. The applicable fields for Sales to update include the following 

The Sales Request for Quote database could be queried on the following fields 1 Customer Name 2 Customer A and Z Locations 3 Speed 4 Order Received Status and 5 Sales Notes.

The general functionality of order management includes the following 1 customer circuit orders enter edit show status 2 design segments of circuit 3 request carrier quotes for segments or whole circuit 4 order segments from carrier 5 close order send completion notice and 6 show status of order to customer and resellers.

The roles of customer user and reseller are as follows 1 customer can view only customer order status 2 user all functions and 3 reseller can enter edit customer orders and view order status.

The circuit information entered on the order entry screen includes 1 speed 2 CCSD 3 framing 4 line code 5 protection 6 channelization required yes no and 7 TSP Authorization Code.

Customer orders user or reseller can be searched and or edited as follows 1 order ID 2 circuit ID 3 CCSD 4 speed 5 received date date range 6 customer requested date date range 7 site A 8 Site Z.

The purpose of the design segments process is to take an end to end customer circuit and design possible segments that will support the circuit. The segments are sequenced 1 2 3 . . . starting from Site A of the circuit to Site Z of the circuit. Each segment record has one site a site that represents either an intermediate site between Site A and Site Z of the circuit or if it s the last segment or the only segment the Site information is the Site Z of the circuit. Each segment can be an existing facility an in service facility a facility being installed or a potential facility that does not exist and may never actually exist. The designer should be able to create many different designs for the same circuit each design with different segments or different number of segments.

The designer selects the circuit to be designed starts with the first segment selects either an existing segment or creates a new segment and adds information about the segment. The designer then goes to the second segment and repeats the process until all segments desired have been added. The designer can then designate a certain design as the preferred design.

The user searches customer orders or circuits design screen the search criteria would be similar to search order screen. The user selects the order desired from a grid. A screen is displayed with circuit information including Site A and Site Z . Design options are then created as below.

Creating Carrier Queries involves selecting a segment from a design that does not have a carrier associated with design segment and requesting quotes from a number of carriers for the MRC NRC and term of that segment. The queries are e mailed to the selected carriers e mail addresses obtained from contact who are listed as the carrier query ordering contacts . The e mail contains a link to allow the carrier to enter the quote directly into the system. The carriers may also return quotes by e mail by letter or telephone in which case the quotes need to be entered into the system manually.

Validity of quote e.g. number of days or months quote is good for carrier quote number. The e mail also should provide the following data requested date query ID speed site A full address site Z full address expedite TSP authorization code protection.

The network access provisioning platform provides a port cross connect service in which customers with communications equipment located at major hub facilities around the world can manage the data associated with the infrastructure at these locations and request from the network access provisioning platform service provider cross connects between customer equipment and selected carriers. The customers can also make port assignments select the carriers and request network access provisioning platform work. The network access provisioning platform service provider arranges for the implementation of the cross connects at the customer locations.

The network access provisioning platform allows customers to assign and order their cross connects and manage the data on an ongoing basis. The system provides the following functions 1 maintain the inventory of hub facilities devices at the facilities circuits and interconnections for customers 2 allow customers to select devices ports and carriers for interconnection of circuits at the hub facilities 3 allow customers to request manual work from the network access provisioning platform service provider local field operations or carriers for installation of equipment and circuits installation of cross connects test and turn up of equipment and circuits and maintenance activities such as troubleshooting 4 allow service provider personnel to act as agents for the customers 5 allow the network access provisioning platform service provider to generate manage issue and receive Letters of Agency LOAs to perform work on behalf of their customers 6 allow field operations forces to receive and complete work orders 7 allow the network access provisioning platform service provider to track billable events and billable time and 8 provide a high level of data segregation and security between customers.

For work requests the system is generally expected to work as a process flow work requests will flow from requestors to provisioners to field operations personnel and carriers. At each step some manual work tasks will be performed information about that work step will be updated and the work will flow to the next step of the process. In some cases work steps may split and subsequently merge. Examples of provisioner screens are illustrated in .

The high level functions of the system are illustrated in the use case diagram of . Users of the system take on the following roles 

The following describes an example flow for capacity build requests. The flow involves a particular type or work request and the tasks associated with the work request.

A proposed database structure is shown in . An equivalent object class definition may be specified. To maintain separation of customer data tables are dedicated to customers.

The network access provisioning platform ticketing system provides a true system driven solution that simplifies both the ticket creation and reporting processes. The ticketing system described herein provides a system foundation for enhanced ticket functionality.

The platform supports Trouble Ticket type tickets. These are defined as network outages as reported to the network access provisioning platform service provider or customer troubles as reported by DISA and others and then assigned to the network access provisioning platform service provider. Customers have the ability to directly enter tickets into the ticketing system as well as provide request updates via the work log functionality provided within the system.

This paragraph describes some of the key features of the Ticketing System. Direct access support and segregated customer access are provided for the network access provisioning platform via a web based interface. Access permissions are User ID based. Group definitions and user contact information associations are supported for all User IDs. Support is provided for Trouble Ticket entry and updates. Customers can add new tickets and make work log entries. Customer email alerts are sent to indicate when a ticket is opened or updated directly by a customer. Users are allowed to add new contacts and update existing contacts within the system. Order circuit and contact information are imported automatically into Trouble Tickets from OMS. Improved ticket management includes 1 ticket reason and RFO reason tracking 2 ticket status tracking 3 ticket assignment and related interval tracking 4 related vendor ticket tracking and 5 TSP restoration priority support. Data management and integrity includes system enforced data entry to support open and closure of tickets. The data driven solution provides enhanced reporting capabilities. The system further provides system support for mean time to repair MTTR calculations. Email support is provided for work log entries.

Access to the ticketing system is provided via a web interface using Internet Explorer. Other browsers can also be used once they are tested with the system. The ticket system functionality is supported within OMS. Once the user navigates to the network access provisioning platform web site the user will be presented with the OMS login screen and example of which could be the login screen illustrated in . If a valid User ID and password are entered the main OMS system screen shown in could be provided.

In one embodiment the Ticket System Access screen is as illustrated in . The trouble ticket drop down list provides the user with two options as shown i.e. to enter a ticket or to update a ticket. Once a ticket is entered into the system the remaining activity for that ticket will be performed in the Update Ticket area of the ticketing system.

In one embodiment the Enter Ticket screen as illustrated in provides the user with the ability to open a ticket within the Ticketing System. Users must enter all mandatory data and save the ticket. If the data entered is acceptable to the system a Ticket Number is generated and associated with the ticket. Once the ticket is successfully saved the ticket Status is considered to be Opened and can only be accessed via the Update Ticket screens. Therefore the user is pushed by the system into the Update Ticket Screen not shown for that ticket to gain access to the ticket number that was generated and associated with the new ticket.

The Ticket Number is a unique identifier that is generated by the system and associated with the ticket once it has been opened and saved. The Ticket Number can include a three character Ticket Type and an eight digit number incremented by Ticket Type. 

The Ticket Type is the type of the ticket within the system. In one embodiment this will defaulted to Trouble Ticket as the only option. The system can support other ticket types such as Maintenance Ticket MT . With multiple options available the ticket type selection will become mandatory and must be entered for all tickets. In addition Ticket Type options will also be determined by user group permissions.

The Company Name is the name of the company that either opened or requested the ticket to be opened and is selected from a drop down list. If the ticket is opened by an actual customer via direct access to the system the system will auto populate this field based on the company associated with the User ID used to gain access to the system. In this case the Company name will not be allowed to be changed by the user. This is a mandatory field and must be entered for all tickets.

The Ticket Reason is a short text reason that indicates why the ticket was opened. The reason is user selectable but is limited to the options provided within the drop down. The user is required to select the reason that best indicates why the ticket was opened. Any additional detail must be entered into the Open Issue Detail field. If the drop down does not provide a reasonable option to select from a new option can be defined and added to the system by approved personnel. This is a mandatory field and must be entered for all tickets. Table 1 identifies ticket reasons in one embodiment.

The Company Contact is the name of the person from the related company that opened or requested the ticket to be opened and is selected from a drop down. If the ticket is opened by an actual customer via direct access to the system the system will auto populate this field based on the contact information associated with the User ID that was used to gain access to the system. The user will also be allowed to select a different contact associated with that company. If the desired Company Contact does not exist within the system the user will be allowed to add the contact without exiting the Enter Ticket process. This is a mandatory field and must be entered for all tickets.

The Actual Time of Outage is the date and time as reported by the customer when the failure i.e. reason for ticket occurred. This is not the date and time the ticket was actually opened. This field can be manually entered by the user when the ticket is opened. This is an optional field and is not required to open a ticket.

The Contact Phone is the business phone number associated with the company contact within the system. This field is auto populated by the system once the company contact is selected. If the contact s business number does not exist within the system the user will be allowed to edit the contact information within the system without exiting the Enter Ticket process.

The Contact Email Address is the business email address associated with the company contact within the system. This field is auto populated by the system once the company contact is selected. If the contact s business email address does not exist within the system the user will be allowed to update the contact information within the system without exiting the Enter Ticket process.

The Core180 CktID is the network access provisioning platform s unique circuit identification established for all circuits and associated with the related CCSD Cust CktID within OMS. A user must select either Core180 CktID or the CCSD Cust CktID last 4 characters of the CCSD and the other will be auto populated by the system. Both are required for circuit related tickets. This is a mandatory field only if the selected company is DISA. 

The CCSD Cust CktID is the customer s internal circuit identification that is associated with a Core180 CktID and stored within OMS. For DISA this is the CCSD. A user must select either the Core180 CktID or the CCSD Cust CktID last 4 characters of the CCSD and the other will be auto populated by the system. Both are required for circuit related tickets. This is a mandatory field only if the selected company is DISA. 

 Open Issue Detail is a free form field used to provide an additional ticket reason detail not supported by the short text Ticket Reason field. The user may enter any information that is relevant to support the ticket process. This is an optional field and is not required to open a ticket.

 Priority is the priority of the ticket as determined by the user and is selected from a drop down list. The drop down options are Select Critical High Medium and Low. The priority field defaults to Select. This is an optional field and is not required to open a ticket.

The Related Ticket Number is used to relate an existing ticket to a new ticket within the ticketing system and is selected from a drop down list. The related ticket can be in any status within the system. A user may decide to relate a ticket for any reason. This is an optional field and is not required to open a ticket. However when tickets are closed they cannot be reopened after 24 hours. In these cases a new ticket is required and the related ticket field should be used to refer to the previous ticket.

The Company Ticket Number is a free form field used to associate the customer s internal ticket number to the trouble being reported. This is an optional field and is not required to open a ticket.

The Company Type is a drop down field used to indicate the company type of the related contact. The current options are Carrier Customer and Reseller. When accessing the Contact screen via the Enter Ticket screen this field defaults to Customer. 

The Company Name is a drop down field used to indicate the company of the related contact. When accessing the Contact screen via the Enter Ticket screen this field will be defaulted to company associated with the ticket.

The Contact Title is a free form field used to indicate the job title of the related contact. This is an optional field.

The Contact Name is a free form field used to indicate the name of the related contact. This is an optional field.

The Cell Number is a free form field used to associate a cell phone number to the related contact. This is an optional field.

The Home Number is a free form field used to associate a home phone number with the related contact. This is an optional field.

The Business Number is a free form field used to associate a business phone number to the related contact. This is an optional field.

The Email ID is a free form field used to associate an email address to the related contact. This is an optional field.

The Contact Role is a drop down field used to indicate the role of the related contact. The current options are Carrier Order Customer NOC Quotation and Site. All Vendor contacts for trouble tickets will be entered with a contact role of NOC. This is an optional field.

In one embodiment the Update Ticket screens provide the user with the ability to select and update a ticket. Users must enter all mandatory data required to support closing the ticket. The Update Ticket screens include two functional areas one to search for tickets and the other to view and update the ticket detail. The fields that should be included in the update Ticket screens are identified in the following paragraphs. Creating these screens are within the capability of one of ordinary skill in the art of display screen layout and are not shown here.

The Ticket Search screen provides the user with the ability to search for one or more tickets. Users enter select the search criteria based on the fields available within the search window. Once entered users begin the search by selecting a Search push button. Once the search results are returned users can select a specific ticket from the search results by clicking on an icon placed next to the desired ticket. Once selected the user will be pushed into the General Information update screen to view and or update the selected ticket. Field description are as described below.

The Ticket Number is a unique identifier that is generated by the system and associated with the ticket once it has been opened and saved. The Ticket Number includes a three character Ticket Type and an eight digit number incremented by Ticket Type. 

The Priority is the priority of the ticket as determined by the user and is selected from a drop down list. The drop down options are Select Critical High Medium and Low.

The Most Recent OMS Order is the most recent OMS Customer Order related to the Core180 CCSD Cust CktID that is associated with the ticket.

The Core180 CktID is the unique circuit identification established for all circuits and associated with the related CCSD Cust CktID within OMS.

The CCSD Gust CktID is the customer s internal circuit identification that is associated with the Core180 CktID and stored within OMS. For DISA this is the CCSD.

 Status is the status of the ticket within the system and is either automatically or manually selected from a drop down list. The drop down options are Canceled Closed Opened and Reopened. When a ticket is originally entered and saved the system will set this field to Opened. Any future status changes must be selected manually by the user.

The Ticket Date s is the date when the status was set by the system or user. To and from dates are supported to allow searching for tickets either on a specific date or within a date range.

The Carrier is the Carrier Name as entered into the related Carrier Order within OMS. The carrier is the vendor from which the circuit was directly ordered. Table 3 contains a list of vendor values. 

 Site A is the Site A location of the Core180 CCSD Cust CktID that is associated with the ticket as indicated by the OMS Customer Order.

 Site Z is the Site Z location of the Core180 CCSD Cust CktID that is associated with the ticket as indicated by the OMS Customer Order.

The Assigned Group is the group that is actively assigned and responsible for the ticket within the system and is manually selected from a drop down list. The drop down options are Core180 Customer and SMC. SMC is the system default for this field. An Assigned Group must be defined for all tickets during the lifecycle of the ticket.

The Assigned Party is the party that is actively assigned and responsible for the ticket within the system and is manually selected from a drop down list. The drop down options are based on the contacts within the system that are associated with the selected groups Core180 Customer and SMC . An Assigned Party is not required to be defined. This is due to the shift structures that exist in many SMC NOC related organizations.

The TSP Restoration Priority is the restoration priority as indicated by the last character of the TSP Authorization. This allows the user to select tickets with a TSP restoration priority greater than zero.

The Update Ticket screens provide the user with the ability to view and or update a ticket. Access to the Update Ticket screens is achieved by either saving a new ticket or selecting a ticket within the Search screen. In one embodiment the update ticket screens include three functional areas as described below.

The General Information screen not shown is the initial screen all users enter from either the Enter Ticket screen or the Search screen. This screen is used to capture all ticket data generated during the lifecycle of the ticket except the notes. This screen also contains the most recent entries from the work log view only .

The Circuit Detail screen not shown contains read only order and circuit data pulled from OMS for the related circuit.

The Work Log screen supports the entry of all notes issues and free form status information generated during the lifecycle of the ticket.

The General Information screen is used to capture all ticket data generated during the lifecycle of the ticket except the notes. This screen include five functional areas as described below.

The General Information section contains all data originally entered to open the ticket as well as higher level ticket status information. A history of all status changes and associated dates times are also maintained within this section.

The Resolution section captures all data related to the resolution of the ticket. The majority of the fields within this section must be entered prior to closing the ticket.

The Ticket Assignments section tracks all groups and specific parties that were assigned responsibility for the ticket. A history of all group and party assignments and associated dates times are also maintained in the system.

The Related Vendor Tickets section is used to track all vendor related tickets that were opened to support the resolution of the ticket.

The Work Log Summary section contains the last two entries from the work log. This is intended to be used as a quick summary of the work being performed on the ticket. If additional details are required that are not provided on the General Information screen the user can search through the remaining notes within the Work Log. 

The following paragraphs identify the fields within the General Information section of the General Information screen.

The Ticket Number is a unique identifier that is generated by the system and associated with the ticket once it has been opened and saved. The Ticket Number consists of a three character Ticket Type and an eight digit number incremented by Ticket Type. 

The Ticket Reason is a short text reason that indicates why the ticket was opened. The ticket reasons are identified in Table 1 above.

The Company Contact is the name of the person from the related company that opened or requested the ticket to be opened and is selected from a drop down list. If the desired Company Contact does not exist within the system the user will be allowed to add the contact without exiting the Update Ticket process.

The Actual Time of Outage is the date and time as reported by the customer when the failure reason for ticket occurred. This is not the date and time the ticket was actually opened.

The Contact Phone is the business phone number associated with the company contact within the system. If the contact s business number does not exist within the system the user will be allowed to edit the contact information within the system without exiting the Update Ticket process.

The Contact Email Address is the business email address associated with the company contact within the system. If the contact s business email address does not exist within the system the user will be allowed to update the contact information within the system without exiting the Update Ticket process.

The Core180 CktID is the unique circuit identification established for all circuits and associated with the related CCSD Cust CktID within OMS.

The CCSD Cust CktID is the customer s internal circuit identification that is associated with a Core180 CktID and stored within OMS. For DISA this is the CCSD.

 Open Issue Detail is a free form field used to provide additional ticket reason detail not supported by the short text Ticket Reason field.

 Priority is the priority of the ticket as determined by the user and is selected from a drop down list. The drop down options are Select Critical High Medium and Low.

 Status is the status of the ticket within the system and is either automatically or manually selected from a drop down list. The drop down options are Canceled Closed Opened and Reopened. When a ticket is originally entered and saved the system will set this field to Opened. Any future status changes must be selected manually by the user. A history of all status changes and associated dates times are also maintained in the system.

The Related Ticket Number is used to relate an existing ticket to a new ticket within the ticketing system and is selected from a drop down. The related ticket can be in any status within the system. A user may decide to relate a ticket for any reason. However when tickets are closed they cannot be reopened after 24 hours. In these cases a new ticket is required and the related ticket field should be used to refer to the previous ticket.

The Company Ticket Number is a free form field used to associate the customer s internal ticket number with the trouble being reported. This is an optional field and is not required to open a ticket.

 Ticket Status Date Time is the date and time of when the status was set by the system or user as well as the User ID of the person who either opened or changed the status of the ticket.

 Ticket Escalation is a checkbox used to indicate that a ticket escalation has occurred on the ticket. All detail related to the escalation must be entered into the work log. This is an optional field.

 Escalation Date Time is the date time and User ID of when and who set the escalation checkbox and is auto populated by the system.

The Status History field contains the previous status and related date time user information of the ticket. Status is the status of the ticket within the system. Ticket Status Date Time is the date and time of when the status was set by the system or user as well as the User ID of the person who either opened or changed the status of the ticket.

The following paragraphs identify the fields within the Resolution section of the General Information screen.

The Resolution Time is the date time and user ID of when and who determined that the Ticket Reason was resolved. This is set manually by the user. This is a mandatory field and must be entered to close the ticket.

 MTTR is calculated by the system when the Resolution Time field is entered by the user. MTTR is the interval in hours from the time the ticket was opened to the resolution time minus any time assigned to the company. If the RFO Party is equal to Customer the MTTR will be set to zero.

The RFO Party Type is the type of party responsible for the cause of the ticket as determined by the user and is selected from a drop down list. The drop down options are Select Core180 Customer and Vendor. The field will default to Select. This is a mandatory field and must be entered to close the ticket.

 RFO Text is a short text reason used to indicate the cause resolution of the ticket. This is user selectable but is limited to the options provided within the drop down list. The user is required to select the reason that best indicates the cause resolution of the ticket. Any additional detail must be entered into the RFO Detail field. If the drop down list does not provide a reasonable option to select from a new option can be defined and added to the system by approved personnel. This is a mandatory field and must be entered to close the ticket. RFO values are shown in Table 3 below.

The RFO Resp Party field is used to identify a specific vendor. This is user selectable but is limited to the options provided within the drop down list. The user is only required to select a vendor if the RFO Party Type is set to Vendor. If the drop down does not provide the required option to select from a new vendor can be defined and added to the system by approved personnel. This is a mandatory field if the RFO Party Type is set to Vendor and must be entered for all tickets of this type to close the ticket.

 RFO Detail is a free form field used to provide additional RFO detail not supported by the short text RFO Code Text field. The user may enter any information that is relevant to support the ticket process. This is an optional field and is not required to close the ticket.

The following paragraphs provide a description of all fields within the Ticket Assignment section of the General Information screen.

The Assigned Group is the group that is actively assigned and responsible for the ticket within the system and is manually selected from a drop down list. The drop down options are Core180 Customer and SMC. SMC is the system default for this field. An Assigned Group must be defined for all tickets during the lifecycle of the ticket. A history of all group assignments and associated dates times are also maintained in the system.

The Assigned Group Date Time is the date and time of when the Assigned Group was selected by the user as well as the User ID of the person who made the assignment.

The Assigned Party is the party that is actively assigned and responsible for the ticket within the system and is manually selected from a drop down list. The drop down options are based on the contacts within the system that are associated with the selected groups Core180 Customer and SMC . An Assigned Party is not required to be defined. This is due to the shift structures that exist in many SMC NOC related organizations. If the desired party does not exist within the system the user will be allowed to add the party contact without exiting the system. The history of all party assignments and associated dates times are also maintained in the system.

The Assigned Part Date Time is the date and time when the Assigned Party was selected by the user as well as the User ID of the person who made the assignment.

The Assigned Party Phone is the business phone number associated with the Assigned Party within the system. This field is auto populated by the system once the Assigned Party is selected. If the Assigned Party s business number does not exist within the system the user will be allowed to edit the contact information within the system Edit push button without exiting the system.

The Assigned Party Email is the business email address associated with the Assigned Party within the system. This field is auto populated by the system once the Assigned Party is selected. If the Assigned Party s Email address does not exist within the system the user will be allowed to update the contact information within the system without exiting the system.

The following paragraphs provide a description of all fields within the Related Vendor Tickets section of the General Information screen.

The Vendor Ticket Party field is used to identify the specific vendor associated with a vendor ticket. This is user selectable but is limited to the options provided within the drop down list. The drop down values are the same vendors provide in the RFO Resp Party field when the RFO Party Type is set to Vendor. If the drop down list does not provide the required option to select from a new vendor can be defined and added to the system by approved personnel. This is a mandatory field if the RFO Party Type is set to Vendor and must be entered for all tickets of this type to close the ticket. Many to one vendor tickets are allowed to be entered against a single trouble ticket within the system.

The Vendor Ticket is a free form field used to manually document a vendor ticket number. This is a mandatory field once a Vendor Ticket Party has been selected and must be entered to close the ticket.

 Opened is the date and time when the related vendor ticket was opened. This is manually entered by the user. This is a mandatory field once a Vendor Ticket Party has been selected and must be entered to close the ticket.

 Closed Resolution Time is the date and time when the related vendor ticket was resolved. This is manually entered by the user. This is a mandatory field once a Vendor Ticket Party has been selected and must be entered to close the ticket. This field captures the date and time of when the resolution occurred which may or may not be the same time the ticket was closed.

The RFO Code Text is a short text reason that indicates the cause resolution of the ticket. This is user selectable but is limited to the options provided within the drop down. The user is required to select the reason that best indicates the cause resolution of the ticket. Any additional detail must be entered into the work log. If the drop down list does not provide a reasonable option to select from a new option can be defined and added to the system by approved personnel. This is a mandatory field once a Vendor Ticket Party has been selected and must be entered to close the ticket.

The following provide a description of the fields within the Work Log section of the General Information screen. The Notes Date is the date and time of when the related note work log entry was made by the user and is auto populated by the system. The Notes field is a free form field used to make progress entries associated with the ticket. The user may enter any information that is relevant to support the ticket process from open to closure. The Notes Added By field is used to enter the User ID of the person that entered the related notes.

The Circuit Screen not shown contains read only order and circuit data pulled from OMS for the related circuit. The data provided within this screen originates from two functional areas within OMS customer orders and carrier orders. OMS order information data provides high level information related to the orders OMS TSR circuit detail circuit end locations A Z A Z demarcation and extension information as well as A Z customer contacts. Carrier order information data provides high level information for the each segment associated with the higher level circuit including the related carrier carrier circuit ID s A Z end locations and channel terminations DMX assignments etc. .

The Most Recent OMS Order is the most recent OMS Customer Order related to the Core180 CCSD Cust CktID that is associated with the ticket.

 Speed is the speed of the Core180 CCSD Cust CktID that is associated with the ticket as indicated by the OMS Customer Order DS1 DS3 etc. .

 Framing is the framing of the Core180 CCSD Cust CktID that is associated with the ticket as indicated by the OMS Customer Order ESF etc. .

 TSP Auth is the Telecommunications Service Priority authorization as indicated by the OMS Customer Order.

 Line Coding is the line coding of the Core180 CCSD Cust CktID that is associated with the ticket as indicated by the OMS Customer Order B8ZS etc. .

The TSP Restoration Priority is the restoration priority as indicated by the last character of the TSP Authorization. The following text will also be available to the users from a TSP push button. Vendors will dispatch outside normal business hours if necessary to restore TSP services assigned a restoration priority of 1 2 or 3. Vendors are required to dispatch personnel outside normal business hours to restore TSP services assigned 4 or 5 only when the next business day is more than 24 hours away. TSP services will be restored in order of restoration priority level As a matter of general practice service vendors should restore existing TSP services before provisioning new TSP services. 

 Site A is the Site A location of the Core180 CCSD Cust CktID that is associated with the ticket as indicated by the OMS Customer Order.

 Site Z is the Site Z location of the Core180 CCSD Cust CktID that is associated with the ticket as indicated by the OMS Customer Order.

 Customer Demarc A Z is the Site A and Z Customer Demarc information as indicated by the OMS Customer Order.

 Carrier Demarc A Z is the Site A and Z Carrier Demarc information as indicated by the OMS Customer Order.

 Extension Info A Z is the Site A and Z Extension information as indicated by the OMS Customer Order.

 Contacts A Z is the Site A and Z Primary and Secondary Contacts as indicated by the OMS Customer Order.

The following paragraphs provide a detailed description of all Carrier order related fields within the Circuit screen.

The Routing Information is the segment detail for each segment associated with the Core180 CCSD Cust CktID that is related to the ticket. The following is provided from OMS for each segment 

 Channel is the Carrier Order for Channel as entered into the related Carrier Order within OMS. Typically this is the slot used within the parent circuit that is used for CFA Interconnection.

 Circuit ID is the Carrier Circuit ID as entered into the related Carrier Order within OMS. Typically this is the primary vendor circuit ID for the segment i.e. the vendor which received the issued carrier order.

 Site A is the Site A as entered into the related Carrier Order within OMS. In most cases this is the A end of the parent circuit as defined in OMS.

 Site Z is the Site Z as entered into the related Carrier Order within OMS. In most cases this is the Z end of the parent circuit as defined in OMS.

 Chan Term A is the Channel Termination A as entered into the related Carrier Order within OMS. In most cases if provided this is the DMX cross connect information associated with the channel used within the parent circuit for CFA Interconnection.

 Chan Term Z is the Channel Termination Z as entered into the related Carrier Order within OMS. In most cases if provided this is the DMX cross connect information associated with the channel used within the parent circuit for CFA Interconnection.

 Carrier Trouble Reporting Contacts is the trouble reporting contact information for each segment based on the vendor associated with each segment.

The Work Log screen supports the entry of all notes issues and free form status information generated during the lifecycle of the ticket. The Work Log screen has two functional areas general information and notes. The general information section provides read only ticket data for the convenience of the users. The selected data provides reference information related ticket company and circuit information for the user when viewing or updating entries in the work log. The notes section allows the users to enter free form text to describe all issues progress testing results discussions etc. that are generated during the lifecycle of the ticket. Users are allowed to restrict customer access to selected notes as well as email selected notes.

The Ticket Number is a unique identifier that is generated by the system and associated with the ticket once it has been opened and saved. The Ticket Number contains a three character Ticket Type and an eight digit number incremented by Ticket Type. 

 Related Ticket Number is used to relate an existing ticket to a new ticket within the ticketing system. The related ticket can be in any status opened closed etc. within the system. A user may decide to relate a ticket for any reason. However when tickets are closed they cannot be reopened after 24 hours. In these cases a new ticket is required and the related ticket field should be used to refer to the previous ticket.

 Company Contact is the name of the person from the related company that opened or requested the ticket to be opened. If the ticket is opened by an actual customer via direct access to the system the system will auto populate this field based on the contact information associated with the User ID used to gain access to the system. The user will also be allowed to select a different contact associated with that company.

 Contact Email Address is the business email address associated with the company contact within the system.

 Core180 CktID is the unique circuit identification established for all circuits and associated with the related CCSD Cust CktID within OMS.

 CCSD Cust CktID is the customer s internal circuit identification that is associated with a Core180 CktID and stored within OMS. For DISA this is the CCSD.

 Status is the status of the ticket within the system and is either automatically or manually selected from a drop down list. The drop down options are Canceled Closed Opened and Reopened.

 Ticket Status Date Time is the date and time of when the status was set by the system or user as well as the User ID of the person who either opened or changed the status of the ticket.

The following paragraphs provide a description of the fields within the Notes section of the Work Log screen.

 Notes Date is the date and time when the related note work log entry was made by the user and is auto populated by the system.

 Notes is a free form field used to make progress entries associated with the ticket. The user may enter any information they feel is relevant to support the ticket process from open to closure.

The Send Email checkbox provides the user with the ability to select one or more notes to send via email. Once selected an Email Selected Notes push button is then used to email the notes.

The Customer Viewable checkbox is used to indicate which notes are viewable to customers accessing the system. The default for all notes will be set to viewable. The field itself will not be viewable to any customers accessing the system.

The embodiments of the invention have been described as computer implemented processes. It is important to note however that those skilled in the art will appreciate that the mechanisms of the disclosed embodiments are capable of being distributed as program products in a variety of forms regardless of the particular type of tangible signal bearing media utilized to carry out the distribution. Examples of signal bearing media include without limitation recordable type media such as diskettes CD ROMs flash drives memory cards etc.

The corresponding structures materials acts and equivalents of any means plus function elements in any of the claims below are intended to include any structure material or acts for performing the function in combination with other claim elements as specifically claimed.

Those skilled in the art will appreciate that many modifications to the exemplary embodiments are possible without departing from the scope of the invention. In addition it is possible to use some of the features of the embodiments described without the corresponding use of the other features. Accordingly the foregoing description of the exemplary embodiments is provided for the purpose of illustrating the principles of the invention and not in limitation thereof since the scope of the invention is defined solely by the appended claims.

