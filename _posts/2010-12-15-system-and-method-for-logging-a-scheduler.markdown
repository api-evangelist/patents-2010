---

title: System and method for logging a scheduler
abstract: A computer system including instructions recorded on a non-transitory computer-readable storage medium and readable by at least one processor, the system including a logging module, a receiving module, and a transmission module. The logging module is configured to log information associated with a scheduler. The receiving module is configured to receive a request for information associated with the scheduler. The transmission module is configured to transmit information associated with the scheduler.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08965966&OS=08965966&RS=08965966
owner: SAP SE
number: 08965966
owner_city: Walldorf
owner_country: US
publication_date: 20101215
---
At times it can be desirable to analyze or monitor information and activities of a scheduler within a computer system. More specifically it can be desirable to analyze or monitor information and activities associated with a scheduler that is operatively coupled to a queue and an application server. For example analyzing or monitoring such information may provide information regarding errors or delays in the execution of tasks within a computer system.

For example in some cases qRFC schedulers inbound outbound cannot process logical units of work LUWs or process the LUWs with delays for example in case of a resources failure . It can be difficult to determine the reasons for such problems. Often the analysis of such problems is not very easy and involves support to find out the reason for the problem. Specifically incidents may occur when schedulers are starting an asynchronous remote function call RFC with answer in Group and one of the following problems occurs a system failure a communication failure or a resources failure.

Accordingly it is desirable to provide a logging system that efficiently logs information associated with a scheduler. It is also desirable for such information to be readily available for users to review and analyze.

According to one general aspect a computer system including instructions recorded on a non transitory computer readable storage medium and readable by at least one processor the system including a logging module a receiving module and a transmission module. In one embodiment the logging module is configured to log information associated with a scheduler. The receiving module is configured to receive a request for information associated with the scheduler. The transmission module is configured to transmit information associated with the scheduler.

In some embodiments the receiving module is configured to receive a request for information associated with the scheduler from a third party via a network connection. In some embodiments the transmission module is configured to transmit information associated with the scheduler to a third party via a network connection.

In some embodiments the scheduler is a high priority scheduler. In some embodiments the high priority scheduler is operatively coupled to a queue and an application server.

In some embodiments the scheduler is a first scheduler and the first scheduler is operatively coupled to a queue and an application server. In some embodiments the queue is operatively coupled to a second scheduler.

In some embodiments the information associated with the scheduler includes global information about the scheduler. In some embodiments the information associated with the scheduler includes at least one of a an identification of the user for which the scheduler is running b processing time of the scheduler c an identification of an application server where the scheduler is running and d a status of the scheduler.

In some embodiments the information associated with the scheduler includes information regarding the runtime behavior of queue names that are associated with the scheduler.

According to another general aspect a computer implemented method for causing at least one processor to execute instructions is recorded on a computer readable storage medium. In one embodiment the method includes a logging information associated with a scheduler b receiving a request for information associated with the scheduler and c transmitting information associated with the scheduler.

In some embodiments the receiving includes receiving a request for information associated with the scheduler from a third party via a network connection. In some embodiments the transmitting includes transmitting information associated with the scheduler to a third party via a network connection.

In some embodiments the scheduler is a high priority scheduler that is operatively coupled to a queue and an application server.

In some embodiments the logging information associated with a scheduler includes logging information associated with at least one of a an identification of the user for which the scheduler is running b a processing time of the scheduler c an identification of an application server where the scheduler is running and d a status of the scheduler.

In some embodiments the logging information associated with a scheduler includes logging information associated with the runtime behavior of queue names that are associated with the scheduler.

According to another general aspect a computer program product the computer program product being tangibly embodied on a computer readable medium and comprising instructions that when executed are configured to cause at least one processor to a log information associated with a scheduler b receive a request for information associated with the scheduler and c transmit information associated with the scheduler.

In some embodiments the scheduler is a high priority scheduler that is operatively coupled to a queue and an application server.

In some embodiments the information associated with the scheduler includes at least one of a an identification of the user for which the scheduler is running b a processing time of the scheduler c an identification of an application server where the scheduler is running and d a status of the scheduler.

In some embodiments the scheduler is a first scheduler and is operatively coupled to a queue and an application server. The queue is operatively coupled to a second scheduler.

In some embodiments the information associated with the scheduler includes information associated with the runtime behavior of queue names that are associated with the scheduler.

The details of one or more implementations are set forth in the accompanying drawings and the description below. Other features will be apparent from the description and drawings and from the claims.

In some embodiments the system includes a logging module . The logging module is operatively coupled to the scheduler and is configured to log information associated with the scheduler . More specifically the logging module is configured to store or cause to be stored information or details associated with the scheduler . For example as described in detail below in some embodiments the logging module is configured to log global information about the scheduler . In other embodiments the logging module is configured to log the runtime behavior of specific queues.

For example in some embodiments the logging module is configured to log global information about the scheduler . Specifically in some embodiments the logging module is configured to log global information about the scheduler such as at least one of the following 

 2 technical user information in accordance to the user and terminal identification of the scheduler 

 8 the number of total dialog resources available to the server group for load balancing and the number of free resources.

In other embodiments the logging module is configured to log other global information about the scheduler .

In some embodiments the logging module is configured to log information about the runtime behavior of specific queue names that are started by the scheduler . For example in some embodiments the logging module is configured to log information about the runtime behavior of the scheduler such as at least one of the following 

 3 navigation to existing qRFC monitor SMQ to reuse the current status of qRFC LUWs within the current specific queue name 

 7 remote terminal identification of RFC server session for example this information may be relevant to find out very detailed technical RFC server session information in case of incidence and

 8 root cause analysis of incidents and presentation of error texts in case of error when starting the queue.

In some embodiments the logging module includes a memory . The memory is configured to store the information that is logged by the logging module . For example in some embodiments the memory is configured to store the global information about the scheduler as well as the information about the runtime behavior of the scheduler .

The memory can be of any known type of memory such as a random access memory RAM or a disk drive memory. Although not shown in some embodiments the memory can be implemented as more than one memory component e.g. more than one random access memory RAM component or disk drive memory within the system or logging module . In some embodiments the memory can be or can include a non local memory e.g. a memory not physically included within the system . For example the memory can be or can include a memory shared by multiple client devices not shown .

In some embodiments the memory is or includes a shared memory of an application server that is operatively coupled to the scheduler .

In some embodiments the logging module allows for a determination as to why LUWs have not been processed or why LUWs have been processed with delays. In some embodiments such determination or analysis is relatively simple and does not involve support to find out the reason for the problem or the delay.

The system also includes a receiver or a receiving module and a transmitter or a transmission module . The receiver may be configured to receive a request for information associated with the scheduler . In some embodiments the receiver is configured to receive a request for information from a client outside of the system . In some embodiments the receiver is configured to receive a request for information associated with the scheduler over a network such as a wide area network WAN . In some embodiments the logging of the scheduler begins upon request of such information.

The transmitter is configured to send information associated with the scheduler to the client . In some embodiments the transmitter is configured to send information associated with the scheduler to the client outside of the system . In some embodiments the transmitter is configured to send information associated with the scheduler over a network such as a wide area network WAN or other network.

In some embodiments the scheduler is a qRFC scheduler. For example in some embodiments the scheduler is an inbound scheduler and in other embodiments the scheduler is an outbound scheduler.

As will be discussed in more detail below in some embodiments the scheduler is operatively coupled to a queue and the application server . In some embodiments the queue is an qRFC queue and messages are stored in the queue to be processed by a scheduler such as scheduler . In some embodiments the application server is configured to process the messages that are stored in the queue and processed by the scheduler .

A request for information associated with the scheduler is received . For example the receiver of is configured to receive a request for information associated with the scheduler . In some embodiments the request is received via a network connection.

Information associated with the scheduler is transmitted to a client . For example the transmitter of is configured to transmit information to a client . In some embodiments the information is transmitted via a network connection.

In some embodiments a high priority scheduler is logged by a logging module. is a schematic illustration of a system that includes a high priority scheduler that may be logged using a logging module not illustrated .

High priority messages are scheduled or queued in qRFC queues and should be processed as fast as possible. In process integration PI all messages are scheduled in qRFC queues and processed by one scheduler instance. The scheduler uses the pre defined server group for resource management and distributes all PI messages to the included application server s in the server group.

In some instances a qRFC scheduler starts if the application uses the advanced business application programming ABAP statement COMMIT WORK in a qRFC context. For example in some instances a qRFC scheduler will perform the following at least one of the following steps to process the logical units of work LUWs of each qRFC application 

Because the messages of several qRFC applications can be processed in parallel by the qRFC scheduler for example at commit work the messages of supply chain management SCM PI and computer relationship management CRM applications can be processed by the same qRFC scheduler instance and the qRFC scheduler is sorting the fetched data records in ascending order it can happen that the qRFC scheduler is not able to process the PI messages in name space XBT in time because a huge number of queues must be processed and the number of available resources is not large enough to process the PI messages accordingly although they must be processed as high priority. In this case it might be possible that specific qRFC queues in name space AAA cause delay of the processing of PI messages in queue name space XBT .

Additionally in some instances all registered qRFC queue name spaces are using the same resources for only one server group and qRFC applications can t use its own server group to be processed separately.

Accordingly in one embodiment these high priority queues and high priority messages are scheduled by a high priority scheduler. In some embodiments a high priority scheduler will get its own resources and looks only for its registered or high priority queue names. In some embodiments the high priority scheduler is an ABAP program which can be started by an application using the ABAP statement Submit Report and Return. For example an application may call the high priority scheduler with the information about the name spaces of high priority queues and determine the alternative RFC server group for load balancing.

As illustrated in in one embodiment the system includes a queue . In the illustrated embodiment the queue is a qRFC queue and is configured to queue messages. Some of the messages may be high priority messages.

In the illustrated embodiment the high priority scheduler and a second scheduler are operatively coupled to the queue . Additionally the high priority scheduler is operatively coupled to an application server through an RFC servergroup . Similarly the second scheduler is operatively coupled to an application server different than the application server though an RFC servergroup different than the RFC servergroup .

In the illustrated embodiment the high priority scheduler processes the high priority messages in the queue . The second scheduler processes all of the messages in the queue that are not high priority. In some embodiments the high priority scheduler searches the queue for messages that are identified as high priority. Messages may be identified as high priority for a number of reasons and in a number of ways. For example a message may be identified as high priority because it needs to be addressed quickly or because it is going to consume a large amount of resources. Additionally any type of identifier in the queue may be used to identify the high priority messages.

In some embodiments qRFC logging may be activated to analyze problems associated with processing the messages in a queue such as the messages processed by the high priority scheduler. For example in some embodiments a system administrator is able to activate the qRFC logging on demand and analyze the problem while processing PI high priority queue messages. In some embodiments others such as customers are able to activate the qRFC logging and analyze any problems.

In the illustrated embodiment the high priority scheduler is implemented as a logging data provider and can write the log data records via an application programming interface API into a data collector such as a shared memory of the application server . In some embodiments the high priority scheduler runs by default with inactive logging. Accordingly in some such embodiments there is no negative impact on the performance of the system.

In some embodiments the on demand logging can be used to analyze more detailed information about internal functions of the high priority scheduler . For example in some embodiments a system administrator can activate the logging on demand to acquire more detailed information about internal functions of the high priority scheduler to for example find out the root cause of a problem. In some embodiments a user such as a customer is able to activate the logging during the time the high priority scheduler is running. In some embodiments this activation of the logging and the associated request for information and receipt of information of the log may be made via a network communication. In some embodiments this on demand feature allows the analysis of an incident or presents a log runner in PI context.

In some embodiments the high priority scheduler is configured to process all PI messages which are inserted during runtime in PI queues. Specifically in some embodiments the high priority scheduler performs an iteration loop and re process all PI messages of the queue name spaces for as long as the high priority scheduler is running

For example in some embodiments the high priority scheduler is provided with a list of PI specific queue names spaces while it is being started by a PI application. The high priority scheduler may then search for specific queue names in the generic name spaces for example in some embodiments it will find the specific queue name XBT within generic queue name space XBT . The high priority scheduler will then start an asynchronous RFC with reply and try to process the PI messages.

In some embodiments an attempt to start the high priority messages in the queue can result in an error for example communication system or resource failure which will be present in the high priority scheduler with the appropriate human readable error text.

In some embodiments the system is an ABAP system. In some such embodiments if the system does not have enough resources for processing of PI messages the high priority scheduler uses a fallback mechanism to process at least one PI message as asynchronous RFC call. Accordingly an entry X for fallback in high priority scheduler indicates the resource failure in a system and the system administrator can find the error using the error text.

In some embodiments the logging of the high priority scheduler logs when the high priority scheduler does not process any PI messages. For example in some embodiments the system logs the incidents of when the high priority scheduler does not process any PI messages. In some such embodiments such a log can be accessed on demand or at a user s request.

In some embodiments the system provides on demand logging of long term logical units of work of an application such as a PI application. For example in certain circumstances qRFC schedulers Inbound Outbound cannot process LUWs or process the LUWs with delays for example in case of Resources Failure . In some embodiments the logging of the high priority scheduler allows customers and the support organization to find out the reason for the problem in an easy way.

For example an incident may occur when a scheduler starts an asynchronous RFC Call with answer in Group and one of the following problems occur a a system failure b a communication failure or c a resources failure.

In some embodiments in case of a system and or a communication failure an error text provided by the CPIC layer is logged or sent to a data storage like a database or a shared memory . In case of a resources failure the logging may be used to show the kind of problem and provide customers with the error text that was the reason for the problem.

In some embodiments the system raises an alert about the problem situation and the customer can register him herself and receive notifications from the alerting framework of SAP computer center management system CCMS . For example the alerting framework may be used to aggregate equal error messages and make the reason for incidents available to customers.

In some embodiments the logging of the high priority scheduler provides a link to statistical records to determine some or all of the programs running with the same transaction identification. In some embodiments the logging of the high priority scheduler provides a link to statistical records to determine some or all of the programs running with the same SAP Passport ID. Using the correlation with the statistical records the processing times and other helpful information using the READ API or CCMS group.

In some embodiments the system links the information about the transaction identification or the Passport ID to an SAP Solution Manager to localize the corresponding business process chain. Accordingly in some embodiments one may determine which program in the process chain had a long processing time. The correct application may be addressed to improve the processing time. Alternatively a maximum allowed processing time may be increased in the system .

 2 ST using transaction ID it is possible to search for SQL data records and analyze a performance issue 

 4 ST search for ABAP runtime error if the high priority scheduler or a involved thread of it is terminated while PI message processing and

 5 SM SAP system log using the user name under that the high priority scheduler is currently running it is possible to search for system log entries and does an exception analysis .

In some embodiments the high priority scheduler can be started on demand by a system administrator and will record the specific logging data at processing of high priority queues of a PI application.

In some embodiments some or all of the following categories of logging data can be displayed in the high priority scheduler 

B Detailed Information on the Runtime Behavior of Specific Queue Names which are Started by the High Priority Scheduler

In some embodiments the high priority scheduler does not use an inbound queue RFC. Thus it may be necessary to have a logging mechanism to analyze the incidents and processing times of every queue for inbound queue processing. In some embodiments the high priority scheduler is configured to activate the logging during the business process execution. In some embodiments customers are able to activate the high priority scheduler to analyze the incidents or to determine or analyze any delays in process times.

In some embodiments the logging of the high priority scheduler is advantageous to get additional information about the scheduler . For example in some embodiments the logging may help provide answers to at least one of the following questions 

As illustrated in in the online mode the scheduler writes information to a memory or a data collector for example via an API . In some embodiments the data memory or data collector is associated with or a part of the application server . The information may be provided to a high priority online monitor . The online monitor is operatively coupled to a scheduler status module and to a set of analytical tools .

In some embodiments the scheduler status module is configured to allow the system to provide real time updates of the information of the scheduler to the analytical tools . The analytical tools may be used by a user to filter interpret and analyze the information associated with the scheduler .

In some embodiments the online mode of analyzing the information associated with the scheduler may be done in real time. In other words information associated with the scheduler may be streaming and provide an accurate and current information regarding the scheduler .

As illustrated in in the offline mode the scheduler writes to an offline data collector . The offline data collector is operatively coupled to a database which stores the information. The database is operatively coupled to an offline analyze monitor . In some embodiments the offline analyze monitor may be used to interpret sort and analyze the information stored in the database and associated with the scheduler .

In some embodiments the offline mode may be used to analyze historical information associated with the scheduler .

As illustrated in a system administrator or other user may use the entry for conversion identification Conv ID and navigate to the transaction SMA to setup the RFC business chain and identify the communication partner. In this case as illustrated in the RFC destination A RUNTIME JCOSERVER is connected to Java service via Jco connector for conversion identification .

The business chain as illustrated in shows the RFC client and server part in an RFC chain. The RFC connection with conversation ID was called by high priority scheduler conversation ID and it has called the J2EE service via Jco and RFC destination AI RUNTIME JCOSERVER with conversation ID . The same information can be shown in communication table if you use the transaction SM Server Name Information Communication Table and search for the conversation ID .

As further information in some embodiments the system administrator can find the error text in case of errors. illustrates a resource failure error text while PI message processing the error text can be displayed by clicking on the error symbol .

In some embodiments Return Code RC indicates that the resource failure while starting of high priority queue via asynchronous RFC with reply RC indicates system failure and RC presents the communication failure error.

In order to find the detailed technical information about the RFC server session in every specific queue name in some embodiments the system administrator can press on the remote Terminal ID and get detailed information about the RFC server session. As best illustrated in one can thus find out in which dialog work process the RFC server session was rolled in the last action. The last action can be display and more detailed information from basis point of view.

As illustrated in in some embodiments the navigation to SMQ transaction is also possible to get the current status of PI specific queue name by clicking on the queue name one can jump into SMQ .

In some embodiments the exception analysis can be performed using at least one of the following KPIs 

Implementations of the various techniques described herein may be implemented in digital electronic circuitry or in computer hardware firmware software or in combinations of them. Implementations may implemented as a computer program product i.e. a computer program tangibly embodied in an information carrier e.g. in a machine readable storage device computer readable medium or in a propagated signal for processing by or to control the operation of data processing apparatus e.g. a programmable processor a computer or multiple computers. A computer program such as the computer program s described above can be written in any form of programming language including compiled or interpreted languages and can be deployed in any form including as a stand alone program or as a module component subroutine or other unit suitable for use in a computing environment. A computer program can be deployed to be processed on one computer or on multiple computers at one site or distributed across multiple sites and interconnected by a communication network.

Method steps may be performed by one or more programmable processors executing a computer program to perform functions by operating on input data and generating output. Method steps also may be performed by and an apparatus may be implemented as special purpose logic circuitry e.g. an FPGA field programmable gate array or an ASIC application specific integrated circuit .

Processors suitable for the processing of a computer program include by way of example both general and special purpose microprocessors and any one or more processors of any kind of digital computer. Generally a processor will receive instructions and data from a read only memory or a random access memory or both. Elements of a computer may include at least one processor for executing instructions and one or more memory devices for storing instructions and data. Generally a computer also may include or be operatively coupled to receive data from or transfer data to or both one or more mass storage devices for storing data e.g. magnetic magneto optical disks or optical disks. Information carriers suitable for embodying computer program instructions and data include all forms of non volatile memory including by way of example semiconductor memory devices e.g. EPROM EEPROM and flash memory devices magnetic disks e.g. internal hard disks or removable disks magneto optical disks and CD ROM and DVD ROM disks. The processor and the memory may be supplemented by or incorporated in special purpose logic circuitry.

To provide for interaction with a user implementations may be implemented on a computer having a display device e.g. a cathode ray tube CRT or liquid crystal display LCD monitor for displaying information to the user and a keyboard and a pointing device e.g. a mouse or a trackball by which the user ca provide input to the computer. Other kinds of devices can be used to provide for interaction with a user as well for example feedback provided to the user can be any form of sensory feedback e.g. visual feedback auditory feedback or tactile feedback and input from the user can be received in any form including acoustic speech or tactile input.

Implementations may be implemented in a computing system that includes a back end component e.g. as a data server or that includes a middleware component e.g. an application server or that includes a front end component e.g. a client computer having a graphical user interface or a Web browser through which a user can interact with an implementation or any combination of such back end middleware or front end components. Components may be interconnected by any form or medium of digital data communication e.g. a communication network. Examples of communication networks include a local area network LAN and a wide area network WAN e.g. the Internet.

While certain features of the described implementations have been illustrated as described herein many modifications substitutions changes and equivalents will now occur to those skilled in the art. It is therefore to be understood that the appended claims are intended to cover all such modifications and changes as fall within the scope of the embodiments. It should be understood that they have been presented by way of example only not limitation and various changes in form and details may be made. Any portion of the apparatus and or methods described herein may be combined in any combination except mutually exclusive combinations. The embodiments described herein can include various combinations and or sub combinations of the functions components and or features of the different embodiments described.

