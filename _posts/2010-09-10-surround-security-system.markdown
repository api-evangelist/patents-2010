---

title: Surround security system
abstract: A surround security system which screens packets transitioning a TCP/IP stack of a computer system from being broadcast over a network or being communicated to applications installed on the computer system. The surround security system may further include protections for the operating system, applications and security configurations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08595820&OS=08595820&RS=08595820
owner: RPX Corporation
number: 08595820
owner_city: San Francisco
owner_country: US
publication_date: 20100910
---
This application is a continuation of U.S. patent application Ser. No. 10 739 552 filed on Dec. 17 2003 to common inventors and an assignee the parent application Ser. No. 10 739 552 is hereby incorporated by reference as if fully set forth herein.

An inventive embodiment relates to computer security and more specifically to providing a surround security system.

Computer systems are threatened by external dangers such as viruses worms and other malicious computer programs. illustrates a block diagram of the software portions of a computer system including end point vulnerabilities. The elements typically reside in the operating system or in applications installed on a machine. The operating system and other resources and the Internet applications interface to the outside world through the TCP IP stack .

A malicious individual or program can access the operating system or other resources through the TCP IP stack . Vulnerabilities in the operating system can enable others to obtain confidential information from the computer system or use the computer system to attack other systems.

Traditional firewall applications are an interface between the TCP IP stack and the outside world. They attempt to prevent unauthorized access to the computer system. However they do not address all of the threats that endanger computer systems.

A surround security system is described in various exemplary embodiments. The surround security system in one exemplary embodiment surrounds the TCP IP stack to ensure the integrity of the computer system.

A system method and computer program product for securing a computer system is described in various exemplary embodiments herein. The types of attacks a computer system may suffer through its network include attacking vulnerabilities in the operating system various applications security implementations on the computer system and on the TCP IP stack itself. For example the operating system may have a known exploit which can be fixed with a patch a small application designed to correct a vulnerability or remove the availability of an exploit .

However users often fail to apply the current patches to their operating system and applications. Additionally users will often select a password that is trivially obtainable such as their name the word password or similar easily guessed passwords. Traditional security such as a firewall does not verify the adequacy of such security implementations. The current inventive embodiments provide a surround architecture security structure in which all available vulnerabilities of a computer system are protected.

The vulnerability scanner periodically checks whether patches have been released for the applications and operating system running on the computer system. In one embodiment the vulnerability scanner also verifies that the system settings provide a level of security that complies with the preset security levels. Thus the vulnerability scanner protects the operating system and application from threats based on settings and known exploits that have patches available.

The file monitor monitors the integrity of the various files including executables and DLLs . The file monitor in one embodiment also monitors system usage to verify that usage is commensurate with the legitimate applications that are running.

The packet enforcement engine resides between the network and the TCP IP stack and determines which packets are routed through to the TCP IP stack and which are discarded. In on embodiment the packet enforcement engine handles encrypted packets as well and includes a packet decryption ability to enable the packet enforcement engine to correctly route or discard virtual private network VPN and other encrypted packets.

The application enforcement engine resides between the TCP IP stack and the applications on the computer system. The application enforcement engine routes the packets to the appropriate protective layer to ensure that only safe packets are routed to the applications.

In this way the surround security system architecture surrounds the TCP IP stack and shields the computer system from attacks at all levels. By providing a single integrated system the protection is complete and there is no repetition or overlap in the services provided. This ensures that the time overhead is minimized.

The packet filtering module receives packets from the network driver and filters out unacceptable packets as will be described below. The remaining packets are passed to the TCP IP stack . Generally the TCP IP stack is part of the operating system.

The packets are then sent to the protocol filtering module which rejects those packets that do not meet the requirements. The protocol filtering module TCP IP stack and packet filtering module use smart packet forwarder to forward the subset of packets that are acceptable to be passed to the next stage. In one embodiment application controller is connected to the smart packet forwarder to perform correlation based on the events received from the Packet and Protocol filtering modules and program the application controller to prohibit certain applications from running.

The Winsock DLL if the system is using a Windows operating system forwards the packets to the appropriate applications . The processes described are discussed in more detail below.

Server interaction logic interacts with the server periodically. In one embodiment server interaction logic is initiated periodically such as once a week or once a month. Alternatively in one embodiment the user may set the frequency of the interactions. In another embodiment the interaction is initiated directly by the user. In another embodiment every time the system is rebooted the interaction is initiated. The interaction sends the profile to the server and receives any applicable patches to the operating system and applications. In one embodiment the patches themselves are not sent to the system. Rather links to the applicable patches are provided.

Patch installer downloads and installs patches. In one embodiment patch installer automatically installs any downloaded patches. In another embodiment the patch installer indicates to the user that update patches are available and should be installed. The patch installer also initiates the profile updater to update the profile when a patch is installed.

Settings vulnerability identifier ensures that the user is using a level of security that is acceptable. For example the settings vulnerability identifier may require that the password for accessing the system be at least 5 characters and not be any standard dictionary word. Similarly the settings vulnerability identifier may require that an application such as Outlook be set to not open attachments automatically.

In one embodiment the settings preferences may be modified for the settings vulnerability identifier . In one embodiment such changes to the settings may be made only by an administrator.

At block the system determines whether it is time to determine whether there are any needed updates. In one embodiment the updater is triggered whenever the profile is updated. In another embodiment the updater is triggered periodically i.e. every week. In yet another embodiment the updating is triggered every time the computer is booted or on a similarly regular schedule. In another embodiment the updater is triggered whenever the system is coupled to a network and has bandwidth. If the process determines that it is time to update the process continues to block .

If it is not yet time to check for updates the process continues to block . At block the process scans the settings of the computer to ensure that the settings meet the requirements for the system. For example the system administrator may require that a password be at least 8 characters long and not be a dictionary word. The settings scanner determines whether these requirements are met. If they are met the process returns to block .

If the settings do not meet the requirements the process continues to block . At block the user is notified that the settings are below the thresholds set for the system and is requested to change their settings. In one embodiment the process then does not permit use of the computer until the settings have been altered. The process then continues to block to restart the process.

If at block the process determined that it was time to interact with the server and determine if new updates should be downloaded the process continued to block .

At block the process connects to the server using the profiles and determines at block whether any patches or updates should be downloaded. If no patches or updates are needed the process returns to block to determine whether the settings meet requirements.

If one or more patches are needed the system receives at block pointers to the patches and downloads the patches from those locations.

At block the process determines whether the preferences set that the patches should be automatically installed. If automatic installation is not set the process at block waits until the user has authorized the installation of the patch and then continues to block to download and install the patches.

If auto installation is enabled the process continues directly to block and installs the patches onto the system. The process then returns to block to check on the settings of the system.

At block the server compares an application profile with the current most up to date set of patches for the particular application. At block the process determines whether the application profile indicates that one or more patches have not yet been installed or if there has been a report of another problem with the application. For example a user may inadvertently install spyware or a malicious user may install a key logger or similar application onto the user s system. In one embodiment at block the server also determines whether the application is in a list of dangerous applications or if the application requires a patch i.e. is an accepted application which should be upgraded because of security of functionality issues. If the application does not have any issues the process continues to block .

If the application needs to be upgraded the server prepares a response to the user at block and adds the link to a patch or an uninstall application link to the response. The process then continues to block .

At block the process determines whether there are any more applications to evaluate. If so the process returns to block . Otherwise the process at block sends the response to the user with the list of patches updates uninstalls and other actions to keep the user s system up to date. The process then terminates at block .

The real time monitor constantly monitors memory usage CPU usage process spawning executables and DLLs and any other relevant processes threads or characteristics that may be monitored. In one embodiment the real time monitor couples to the existing tracking mechanism within the computer system to obtain this information. In another embodiment the real time monitor may obtain this information directly.

The real time monitor then ensures that only legitimate applications are spawning processes using CPU time etc. In one embodiment the real time monitor includes a list of possible viral processes to ensure that none of them are active on the system. In one embodiment vulnerability scanner when it connects to the server receives an updated list of possible viral processes.

The periodic monitor periodically monitors the executables DLLs Windows Registry items and files which are resident on the computer system. The periodic monitor ensures that only legitimate files can be uploaded to the computer system. In one embodiment the periodic monitor may be set to remove or disable inappropriate files such as games on a work computer. In one embodiment the periodic monitor includes a connection to profile updater indicating which new applications have been installed on the computer system.

The monitor also includes in one embodiment a file encryption module . The file encryption module enables the user to add additional protection for critical files or applications using encryption. The use of encryption is well known in the art.

At block the process determines whether SAFE mode is enabled. SAFE mode restricts the computer system to disable any new processes from being started. If SAFE mode is enabled the process directly continues to block and kills the newly spawned processes. In one embodiment the application associated with the process is identified and the application is killed. Killing processes without properly closing the application may cause instability in the system. Therefore generally the system closes down the application entirely when a process is deemed unacceptable.

If SAFE mode is not on the process at block determines whether profile mode is enabled. Profile mode limits the applications that may be run on the system. If profile mode is not enabled the process continues to block to continue monitoring the system.

If profile mode is enabled the process continues to block . At block the process determines whether the application is configured to be killed. In one embodiment the applications that may be active on a system are preset by a system administrator or by the user. If the application associated with the newly created active processes are not configured to be killed the process returns to block to continue monitoring.

If the system appears secure at block the process continues to block . At block recording is turned on. Recording is a process by which the surround security system monitors all newly spawned threads processes activated DLLs running applications and other aspects associated with the system as it is being used.

At block the user is prompted to use all normally used applications. In one embodiment the recording process may be over multiple days. In another embodiment this process is only on for a few minutes. In another embodiment the recording runs until the user turns off recording. In one embodiment there is a visual indication that the recording is active. This is to remind the user to use all acceptable applications. At block the recording is ended. As noted above this may be automatic or may be manually executed by the user.

At block the processes and associated network accesses are displayed to the user. The user is then able to disallow any applications or network accesses as preferred. For example the user may be unaware that one of the permitted applications reports back over the network. The user may chose to disable the application or disallow network accesses by the application. In another embodiment this step may be skipped. In another embodiment the display may be made to a system administrator who is better able to evaluate the results of the recording.

At block the recording is used to tune the system. In one embodiment the tuning may include tuning the firewall IDS packet recorder and real time monitor. This ensures that only those applications considered acceptable are provided network access.

At block the process determines whether operating system vulnerabilities should be scanned. In one embodiment the decision is on what to scan and the intervals between scanning is determined by the user by selecting options and selecting the frequency of the scans. In another embodiment the process will detect user change of password and will in addition initiate a scan when new attack signatures for intrusion detection system become available.

If OS vulnerabilities are not to be scanned the process continues directly to block . If OS vulnerabilities are to be scanned the process continues to block to perform a best practices scan.

At block the process tests whether the auto log on feature is enabled. The auto log on feature enables anyone who uses the same computer system to log on without knowing the password. This is insecure since the physical system is rarely secured properly.

At block the policy for passwords is applied for all users. In one embodiment the policy may be defined by a system administrator. The policy may require passwords of a certain length passwords that are not proper words in English passwords that are not in a global dictionary that may include languages other than English passwords that are the user s name or user s spouse s name or other easily guessed passwords. In one embodiment the password policy may further include changing policy which forces each user to regularly update his or her passwords.

The above blocks comprise the best practices vulnerability scan. In one embodiment after the operating system vulnerability scan is performed the process then performs the version scan for security on applications running on the operating system.

At block a vulnerability database is downloaded. The vulnerability database in one embodiment is a database provided by the software vendor such as the MSSecure file provided by Microsoft Corporation. In one embodiment multiple databases are downloaded.

At block the process determines which version of the operating system and products are installed on the computer system.

At block by comparing the list of active applications and operating system versions with the vulnerability database a list of actual vulnerabilities applicable to the system are derived.

At block the process determines if automatic download and application of the patches is selected. If so the process continues to block . Otherwise the process continues to block .

At block the process determines whether the user has opted to download and install patches. In one embodiment the user may select a subset of the patches to be installed. If the user elects to install one or more patches the process continues to block . Otherwise the process continues to block to prepare a scan report without actually installing any patches.

At block the required patches are downloaded. In one embodiment the system provides a URL to download patches directly from the manufacturer of the program. Thus downloading the patches in one embodiment comprises going to one or more predefined URLs provided by the manufacturer of each of the applications that require patches and downloading the patches.

At block the patches are applied. In one embodiment the patches are applied in a hierarchical order. That is the patches are applied to the operating system first then to first tier applications etc.

At block a scan report is prepared. The scan report lists all of the applications that were tested and the patches that were applied.

At block the system prompts the user to reboot the computer if any patches were installed. In one embodiment the system may cause the computer to automatically reboot.

At block if the reboot is not automatic the process determines whether the user selected reboot. If so the system is rebooted at block . The process then ends at bock .

The periodic scanner has a variable scanning interval. The interval in one embodiment has a default setting of XXX. However an administrator may alter the interval. In one embodiment a user may also alter the interval for scanning. In one embodiment the interval for scanning defines a next scan based the date and time of last scan information. In one embodiment the next scan is defined as a date and time. When the date and time is reached the periodic scanner is automatically initiated. In one embodiment the periodic scanner may be delayed temporarily by a user for example if the user is in the middle of a complex process and needs the processing power otherwise diverted to the scanner. Once the scan is initiated the process described above is followed.

Intelligent packet router in packet enforcement engine determines where the packet received should be routed. In one embodiment the possible evaluators which determine whether a packet is passed on to the TCP IP stack include a firewall a network intrusion detection system IDS a packet filter a session monitor and a pass through path .

The firewall in one embodiment is a stateful inspection firewall engine. The firewall examines each message and blocks those that do not meet the specified security criteria. In one embodiment firewall acts as a circuit level gateway applying security mechanisms when a TCP or UDP connection is established. Once the connection has been made packets can flow between the hosts without further checking.

The Intrusion Detection system IDS inspects all inbound and outbound network activity and identifies suspicious patterns that may indicate a network or system attack from someone attempting to break into or compromise a system.

The packet filter looks at each packet entering or leaving the network and accepts or rejects it based on predefined rules. In one embodiment packet filter is part of firewall .

The session monitor monitors the communication sessions to make sure that packets in each session have the correct sequence response Syn Ack etc in the correct order including the session s packet sequence numbers.

The bypass or pass through provides a way to pass through packets for established sessions that require no further monitoring. In one embodiment the bypass is only available for secured transmissions with trusted systems.

The network decision engine receives any packets not discarded by the evaluators . The output of the network decision engine is passed to the TCP IP stack .

At block the process tests whether the packet is IPvX compliant. IPvX is Internet Protocol version X i.e. any supported version. In one embodiment IPv4 and IPv6 are supported. However other IP versions may be supported as well. In one embodiment if the packet is not of a supported type the process at block allows the packet through and ends. In another embodiment if the packet is not of a supported type it may be dropped.

If the packet is an IPvX compliant packet the process continues to block . At block the session history is updated to include the packet currently being received.

At block the process tests whether the packet is being sent over a virtual private network VPN . VPN packets are generally encoded to provide security privacy. If the packet is a VPN packet at block the transforms are applied to the packet to permit standard processing of the packet. In one embodiment the transforms include decrypting the packet. The process then continues to block . If the packet is not a VPN packet the process continues directly to block .

At block the process determines whether the packet is a session start or session stop. If so the firewall rules are applied at block . Otherwise in one embodiment the firewall is bypassed speeding up processing by bypassing packets for established sessions.

At block the IDS intrusion detection system rules are applied to determine whether the packet is an attack on the user s system. If so as determined at block the packet is dropped at block . If not the process continues to block .

At block the packet content filter is applied. The packet content filter permits only packets whose content complies with the IP packet specification. If the content is bad as determined at block the packet is dropped at block . Otherwise the state for the session correlation is updated at block and the packet is sent to the TCP IP stack at block . The packet is then forwarded at block to the next stage of processing.

At block the process determines whether the emergency stop is on. As discussed above the emergency stop enables the user to simply block all incoming and outgoing traffic. This is useful by providing a simple user interface that enables sudden disconnection from the network if a virus worm security problem is discovered without requiring the unplugging of physical cables. If the emergency stop is on the process at block blocks the packet preventing it from entering the system. The process then terminates. Of course this process is actually continuously monitoring packets as they come in. However for simplicity the present flowcharts illustrate an example of a single packet being received.

At block if the emergency stop was not on the process determines whether the network packet firewall rules match the packet. The firewall rules identify those packets that should not be permitted through the firewall. If the packet matches the rules i.e. is identified as an unacceptable packet the process continues to block and blocks the packet. Otherwise the process continues to block .

At block the process determines whether a VPN is required for this transaction. If so at block the VPN profile is identified and the packet is encrypted and or otherwise transformed to meet the VPN profile. The process then continues to block . If the VPN is not required the process continues directly to block .

At block the correlation state is updated and at block the packet is forwarded to the network driver. The process then ends at block .

The application decision engine receives the packets from the application sensitive filters . The application decision engine supervises the correlation between communications and applications by making sure that requests to communicate match approved ports and protocols for the application as well as linked to the correct application and path from where the application is started. The packets from the application decision engine are routed to the Internet applications .

If the packet corresponds to an authorized application the process continues to block where it determines whether the packet should go through the firewall. In one embodiment only the initial packets are passed through the firewall. In one embodiment once a session is established further packets are not passed through the firewall to decrease the load on the system. If the firewall need not be used the process continues to block .

If the firewall is applicable at block the process applies the firewall rules. Then at block the process determines whether the packet should be dropped. Packets that do not meet the exclusion rules of the application firewall are dropped. The packet is dropped at block . Otherwise the process returns to block and configures the firewall to recognize that packets for this connection are acceptable in the future.

At block the process determines whether profile allows for access at this time. The system configuration may set up to prohibit access to applications based on user specific access configuration rules profiles . If the profile prohibits access the process continues to block and drops the packet. Otherwise the process continues to block .

At block the application IDS intrusion detection system is applied to determine whether the packet matches any of the signatures of intrusion block . If so the process continues to block to drop the packet. Otherwise the process continues to block .

At block the process checks the application content for the configured port match. Most applications use a designated port or set of ports. The process determines whether the port through which the packet came matches the designated ports for the application to which the packet is targeted. If there is a port filter match as determined at block the process continues to block to drop the packet. Otherwise the process continues to block .

At block the session correlation is updated. The packet is then passed up to the application. In one embodiment the packet is passed to the application through the Winsock DLL.

In one embodiment if the packet is dropped the system sends a notification. Depending on the configuration a notification can create log entries and notify the user through a pop up message on the screen. Furthermore if connected to a central system alarming notifications can trigger an alert to a system administrator on the management system console.

At block the process determines whether the profile permits access. The application profile may prohibit access. If the profile does not allow access the packet is blocked at block . Otherwise the process continues to block .

At block the content filter is applied. In one embodiment the content filter is used to remove content that is not acceptable such as pornography code for prohibited application types attached files with matching filtered file extension types etc. At block the process determines whether content access is allowed. If not at block the content is blocked.

If the content filter passes the packet the packet is compared to the firewall match rules. If it matches excluded packets at block it is blocked. Otherwise at block the access status is updated. The packet is then forwarded to the TCP IP stack.

At block the process determines whether the operating system running on the system is supported. In one embodiment if the installation executable is designated for a single OS and this step verifies that the operating system is the correct one. If the OS is not supported the process continues to block and the installation is failed. The user is informed in one embodiment that the OS is not supported by the current installation file. In one embodiment the process determines if there is an installation file for the OS running on the system and if so advises the user to acquire the correct installation file. The process then ends at block . If the OS is supported the process continues to block .

At block the communications related drivers and services are loaded at the appropriate places in the communication stack in order to provide the correct filtering at the appropriate levels.

At block the main monitoring and administration applications are then installed in the correct directory and at block the system creates a database for storing configuration data securely. At block pre configured applications data is matched up with the appropriate directory paths to the applications. At block a checksum used for the application integrity when matching a communication stream with an application is calculated for each configured application and stored securely. In one embodiment the checksum is one way encrypted

At block the system is rebooted so that installed drivers services will be loaded at the appropriate places in the communication stack. The installation process is then considered complete and the process ends at block .

The client will receive configuration information and commands via messaging and the client uses messaging to report logs as well as status information back to the central management system.

The command configuration feedback logic in one embodiment includes an email component . The email component is a separate mail client tied to the application on the computer itself. Having a separate email client tied to the application has several advantages. First it would not rely on the user to start checking mail. It will be independent of user s email client and would have certain features that would make it compatible with the communication filtering techniques. A separate email client could be configured to automatically check for new mail and send mail when needed. Using the existing messaging infrastructure also has its advantages. It enables the system to make user configurations follow wherever the user logs in as long as the known email address is used.

In one embodiment the command configuration feedback logic includes a filter to filter email messages or instant messenger messages. In one embodiment the filter uses the Application Enforcement Engine described above to remove the packets directed toward the command configuration feedback logic . In this way the process is transparent to the user. In other words even if the configuration messages are sent through the user s standard email program or standard instant messenger application it is removed before the user encounters it. In one embodiment the emails are addressed to the person that owns the computer. In another embodiment the configuration logic has a separate address associated with it.

Note that the messages sent to the client include configuration information and may include commands such as shut down export and send back logs commands to go to an website and download newest release etc.

A configurator takes the message received through email component or obtained by filter . The configurator then uses this data to configure the surround security system based on the information contained in the messages. As noted above this technique may be used to manage other applications than the surround security system. One of skill in the art would understand how this technique may be used for updating any other application.

Logger maintains a log. In one embodiment the information that is logged may be set by the administrator. For example the log may only include the results of various scans which patches were installed and the like. In another embodiment the logging may include additional details about the computer system. In one embodiment the logging is restricted to the functionalities connected to the application coupled to the logging configuring logic . The term log includes in this context alerts status information currently used configuration data or any other data reported back to the server. Note that in one embodiment the feature of logging may be present without the configuration feature described above and vice versa.

Message constructor constructs a message with logging data to be sent back to the server. If a separate email client is used the message is sent using the separate email client . If the main messaging system email or instant messaging is used when the user sends an email the system intercepts the traffic to the server and inserts a new message addressed to the management system containing logs or status information or any other information requested by the central management system . This is done without the user having to know that it is happening in the background.

At block the email component is monitored to detect if a configuration message is received. The email component is only used for configuration messages and the like in one embodiment so any message triggers the detection block . If a message is received the process continues to block . If no message is received the process continues to block .

If at block no email component was detected the process continues to block . At block the network traffic is intercepted. As described above this is part of the surround security features available to the user.

At block the process determines whether the network traffic includes any information for the managed application. The information may be sent over a standard email application via an instant messenger application or via any similar path. If there is no information for the managed application the process continues to block . If there is information for the managed application the process continues to block .

At block the information for the managed application is filtered out. This means in one embodiment that the user never receives the management information in his or her email inbox. Rather the packets are diverted before the email application encounters them. Similarly for instant messaging the user would not see the message which would appear as gibberish in one embodiment. 

At block the managed application is configured based on the information received through the network traffic. In one embodiment this is done transparently to the user. In another embodiment this may require a reboot or similar action so this may require user interaction i.e. a pop up to inform the user that a reboot is needed and permitting the user to click OK or Cancel. In one embodiment since updating configuration may take computer resources the user may be warned and may be permitted to delay installation.

At block the process determines whether there are any log files to return to the server. If there are no log files the process returns to block to restart the scan. If there are log files to be sent the process continues to block .

At block a log message is constructed. At block the log message is sent. If the system has an email component the message is simply sent using the email component. If there is no email component the network traffic to the server is intercepted and the message is inserted addressed to the management system. The process then returns to block to restart the scan.

Note that while this is illustrated in a flowchart form as are other processes above and below the actual implementation may use interrupts or similar mechanisms. In other words the system may not use a monitoring mechanism but rather may depend on an interrupt mechanism or the like to indicate when there is an incoming message to be processed or an outgoing message to be sent back to the management system.

If there is configuration information to be sent at block the process continues to block . At block configuration information to be sent to one or more users is received. At block the message is created. The message includes the alteration to the configuration data. In one embodiment the message is essentially executable data which when received by the client system can simply be executed to perform the requested alterations to the managed application.

At block the process determines which client systems should receive a copy of the message. In one embodiment the administrator may name individual systems users to whom the message should be sent. In another embodiment the administrator may identify systems with a current configuration of a certain sort to receive the message. For example the administrator may indicate that all users running Version 1.6 of Surround Security on a Windows 98 system should receive the message update. The log information for each of the users is then used to identify which systems need to receive the configuration message.

At block the configuration message is sent to each of the targeted users. The process then returns to block to continue scanning.

The present application includes software running on the user s computer system described above in detail as well as an updating server . The updating server in one embodiment maintains a list of current state for applications that may be installed on the computer system . The updating server may furthermore provide links to patch server if appropriate. Patch server may be the server maintained by a vendor such as Microsoft from which a patch for a vulnerability of bug may be downloaded. Upon receiving the link to the patch server the user on computer system may download the patch directly from patch server ensuring that only the application vendor authorized patches are available to the user.

The data processing system illustrated in includes a bus or other internal communication means for communicating information and a processor coupled to the bus for processing information. The system further comprises a random access memory RAM or other volatile storage device referred to as memory coupled to bus for storing information and instructions to be executed by processor . Main memory also may be used for storing temporary variables or other intermediate information during execution of instructions by processor . The system also comprises a read only memory ROM and or static storage device coupled to bus for storing static information and instructions for processor and a data storage device such as a magnetic disk or optical disk and its corresponding disk drive. Data storage device is coupled to bus for storing information and instructions.

The system may further be coupled to a display device such as a cathode ray tube CRT or a liquid crystal display LCD coupled to bus through bus for displaying information to a computer user. An alphanumeric input device including alphanumeric and other keys may also be coupled to bus through bus for communicating information and command selections to processor . An additional user input device is cursor control device such as a mouse a trackball stylus or cursor direction keys coupled to bus through bus for communicating direction information and command selections to processor and for controlling cursor movement on display device .

Another device which may optionally be coupled to computer system is a communication device for accessing other nodes of a distributed system via a network. The communication device may include any of a number of commercially available networking peripheral devices such as those used for coupling to an Ethernet token ring Internet or wide area network. The communication device may further be a null modem connection or any other mechanism that provides connectivity between the computer system and the outside world. Note that any or all of the components of this system illustrated in and associated hardware may be used in various embodiments of an inventive embodiment.

It will be appreciated by those of ordinary skill in the art that any configuration of the system may be used for various purposes according to the particular implementation. The control logic or software implementing an inventive embodiment can be stored in main memory mass storage device or other storage medium locally or remotely accessible to processor .

It will be apparent to those of ordinary skill in the art that the system method and process described herein can be implemented as software stored in main memory or read only memory and executed by processor . This control logic or software may also be resident on an article of manufacture comprising a computer readable medium having computer readable program code embodied therein and being readable by the mass storage device and for causing the processor to operate in accordance with the methods and teachings herein.

The various inventive embodiments may also be embodied in a handheld or portable device containing a subset of the computer hardware components described above. For example the handheld device may be configured to contain only the bus the processor and memory and or . The handheld device may also be configured to include a set of buttons or input signaling components with which a user may select from a set of available options. The handheld device may also be configured to include an output apparatus such as a liquid crystal display LCD or display element matrix for displaying information to a user of the handheld device. Conventional methods may be used to implement such a handheld device. The implementation of an inventive embodiment for such a device would be apparent to one of ordinary skill in the art given the disclosure of an inventive embodiment as provided herein.

The various inventive embodiments may also be embodied in a special purpose appliance including a subset of the computer hardware components described above. For example the appliance may include a processor a data storage device a bus and memory and only rudimentary communications mechanisms such as a small touch screen that permits the user to communicate in a basic manner with the device. In general the more special purpose the device is the fewer of the elements need be present for the device to function. In some devices communications with the user may be through a touch based screen or similar mechanism.

It will be appreciated by those of ordinary skill in the art that any configuration of the system may be used for various purposes according to the particular implementation. The control logic or software implementing an inventive embodiment can be stored on any machine readable medium locally or remotely accessible to processor . A machine readable medium includes any mechanism for storing or transmitting information in a form readable by a machine e.g. a computer . For example a machine readable medium includes read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices electrical optical and any other tangible and non transient media.

In the foregoing specification the various inventive embodiments have been described with reference to specific examples thereof. It will however be evident that various modifications and changes may be made thereto without departing from the broader spirit and scope of the invention as set forth in the appended claims. The specification and drawings are accordingly to be regarded in an illustrative rather than a restrictive sense.

