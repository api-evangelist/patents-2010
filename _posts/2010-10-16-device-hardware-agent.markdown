---

title: Device hardware agent
abstract: A server includes an electronic component, manager baseboard management controller (BMC), and a device hardware agent. The device hardware agent monitors operation of the electronic component and provides updates to the electronic component without utilizing a software agent.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09208047&OS=09208047&RS=09208047
owner: Hewlett-Packard Development Company, L.P.
number: 09208047
owner_city: Houston
owner_country: US
publication_date: 20101016
---
This application is a national stage application under 35 U.S.C. 371 of PCT US2010 52976 filed Oct. 16 2010.

The present invention relates to a device hardware agent that connects to one or more electronic components in a networked computer.

Software agents are often loaded into servers to gather information about electronic components operating in the server. This information is transmitted to another electronic device such as an external management server so a user can manage and diagnose the server. A separate software agent is often required for each of the server components that are managed.

Software agents can provide information and some control over device operation but often require a Network Interface Card NIC on the server to be dedicated to communicate this information to the external management server. In order to communicate with the external management server the software agents consume memory and processing resources on the managed server and can create software issues with the operating system OS .

Example embodiments relate to apparatus and methods that utilize one or more device hardware agents to manage and control components in a computer or server.

In one example embodiment the device hardware agent is a microcontroller that connects to an electronic device and performs various functions such as monitoring for inventory health status and statistics. One or more microcontrollers monitor one or more components in the electronic device. By way of example such components include but are not limited to Network Interface Cards NICs Host Bus Adapters HBAs storage controllers and Central Processing Units CPUs .

The device hardware agents collect information and transmit this information to a baseboard management controller that provides an interface for a user to review the collected information. For example the information is provided on a Graphical User Interface GUI Command Line Interface CLI or Application Program Interface API .

Each device hardware agent has two interfaces. One interface communicates information with an out of band OOB management processor such as a Baseboard Management Controller BMC . Another interface communicates i.e. sends and receives information with the device being monitored and or controlled e.g. communicates information with the NIC HBA CPU etc. .

Communication can occur with various types of communication paths such as serial Inter Integrated Circuit i2C and Ethernet. Further the information being communicated is accessible in a standardized API that is independent of the device being managed. A connection between the microcontroller and the electronic device being monitored is based on the device itself such as Joint Test Action Group JTAG .

The device management interface allows management and control of the device without impacting the OS interface. A interface can be used since it is already embedded in devices like NICs and RAID controllers. Example interfaces include but are not limited to JTAG interfaces i2C serial Ethernet GPIO and SPI. A component can use one or more of these example interfaces.

In order for the device hardware agent to be customized to understand how to access device specific information the device specific parameters are programmed into the device hardware agent in the device specific firmware with details on device specific access JTAG mode address register format of the data user visible name of the information read or read write ability etc. . In addition the device agent can include one or more of each type of a device management interface to allow a single device agent to manage multiple identical devices such as multiple NICs.

Device hardware agent firmware is divided into two sections one section for common API firmware and the other section for device specific firmware. This division allows the computer manufacturer to design the common API firmware to match their baseboard management controller BMC and allows the device manufacturer to design the device specific firmware to interface to their specific device using the device management interfaces and to communicate with the common API firmware provided by the computer manufacturer. A device hardware agent debug interface can be used during device hardware agent firmware development but this debug interface might not be connected in production. Communication between the common API firmware and device specific firmware can be accomplished using the device hardware agent memory but could also use the common API interface.

The device hardware agent provides a common API on the BMC interface so the BMC does not have to code device specific data but provides information and control of the device as indicated in the common API.

The device hardware agent communicates information e.g. inventory health status and statistics to the baseboard management controller and also receives commands to control and or manage the electronic device to which the device hardware agent is connected. For example the device hardware agent receives commands to change a behavior of electronic device such as receiving a command to change a Media Access Control MAC address of a port on a NIC. Other commands to the device hardware agent enable firmware on the electronic device to be updated or to enable or disable a port.

During manufacturing the device hardware agent is programmed to connect and communicate with a specific electronic component in an electronic device e.g. programmed to communicate with an HBA HIC CPU etc. . In this manner two device hardware agents with similar or same hardware components can be used to manage different electronic components. For example one device hardware agent is programmed to interface with the storage controller in a server and another device hardware agent is programmed to interface with a NIC in the server. Having the device hardware agent be data driven on both interfaces allows firmware in the device hardware agent to be flexible enough to support different devices with a customized firmware image for each device.

In one embodiment a single device hardware agent manages a single electronic component. In another embodiment a single device hardware agent manages plural identical electronic components.

In another embodiment multiple device hardware agents could be embedded in a single device such as the baseboard management controller to manage multiple different electronic components in a server or computer.

In another embodiment the device hardware agent could be embedded in the component device providing a BMC interface for direct connection to the BMC without requiring a separate device hardware agent ASIC.

The device hardware agent provides information and control for devices without dependency on installing OS agents. Because the device management is accomplished through a common API both the BMC and external management server can provide device management with common management code without having to write or execute device specific management code.

Hardware agents in accordance with example embodiments thus replace OS software agent functionality i.e. monitoring of the device control of the device and collection operation statistics of the device without any CPU or PCIe bus utilization. This removes the need to develop and maintain OS agent code across all supported operating systems and allows management monitoring of different devices in the server across various operating systems. For example a device hardware agent for the CPU can replace Basic Input Output System BIOS System Management Interface SMI code that performs power management memory error monitoring and other SMI functions to eliminate any server performance impact for CPU monitoring and control.

Furthermore the management of the devices can be accomplished through the BMC using out of band communication to completely isolate management communications from the computer OS.

One exemplary embodiment uses an embedded server management technology such as iLO Integrated Lights Out . A remote server management device facilitates remote access and administration of server computer systems. Remote console functionality allows a user to access a server from another computer known as a management console or a remote management device RMD . The management console enables a user to interact with the server as though the user were physically at the server and interacting with the server with for example a display attached to the server.

The network s can be any sort of network capable of transmitting data between two devices. Without limitation some examples of networks include a local area network LAN a wide area network WAN a hardwired point to point connection a point to point connection over a telecommunications line a wireless connection and an internet connection.

The managed servers are not limited to any particular type of server and include but are not limited to application servers web servers database servers etc. In one exemplary embodiment the managed servers are blade computers such as blade servers operating in a rack enclosure or data center.

Embodiments in accordance with the present invention are not limited to any particular type of networked computer systems. The managed servers and or remote management devices include various portable and non portable computers and or electronic devices including but are not limited to compute portable and non portable servers main frame computers distributed computing devices laptops and other electronic devices and systems whether such devices and systems are portable or non portable.

Device hardware agent A connects to a CPU via a CPU interface . The CPU includes a memory interface and a Peripheral Component Interconnect Express PCI E or PCIe connection . A device manager interface connects the baseboard management controller or server iLO manager to the device hardware agent A.

Device hardware agent B connects to a RAID controller via a RAID interface and a PCIe connection . The RAID controller includes plural device ports . A device manager interface connects the baseboard management controller or server iLO manager to the device hardware agent B.

Device hardware agent C connects to a dual port NIC via a NIC interface and a PCIe connection . The dual port NIC includes plural device ports . A device manager interface connects the baseboard management controller or server iLO manager to the device hardware agent C.

Device hardware agent D connects to an option card device e.g. an HBA via a HBA and a PCIe connection . The option card device includes plural device ports . A device manager interface connects the baseboard management controller or server iLO manager to the device hardware agent D.

Electronic components being managed in the server generally do not include a common debug interface. The device hardware agent however includes one or more interfaces such as i2C serial JTAG GHQ and SPI allowing the vendor specific firmware in the device hardware agent to access internal registers and control the electronic component.

The device manager interfaces and are a standard or common hardware interface. For example this interface can be one already included in an iLO design and can be one that is available on Peripheral Component Interconnect PCI option cards and mezzanine cards.

According to block one or more device hardware agents located in the server collects information about one or more electronic components. For example device hardware agents collect information about the operation of a CPU a RAID controller a HBA a NIC and a server blade mezzanine card.

According to block the information collected by the device hardware agents is read by or transmitted to a baseboard management controller BMC located in the server. Each device hardware agent includes one or more different interfaces to enable the device hardware agent to communicate with different electronic components and the BMC.

In one embodiment each device hardware agent is connected to and collects information about one electronic component. In another embodiment a single device hardware agent is connected to and collects information about a plurality of different electronic components e.g. a NIC HBA CPU controller etc. .

According to block the collected information is transmitted to a remote management server. For example a user at a remote management device logs into server via the server iLO manager and retrieves the collected information. The user can also transmit data and commands to the BMC or server iLO manager and electronic components through the device hardware agents.

According to block a baseboard management controller receives a new firmware update for a device in a networked computer.

According to block the BMC sends the device hardware agent the firmware update command for that device.

According to block firmware in the device hardware agent notifies an OS device driver that a firmware update will occur. This notification causes the device driver to stop further OS data transfer requests to the device.

According to block the firmware in the device hardware agent streams the firmware update from the BMC and updates the device firmware.

According to block after the firmware update is completed the device hardware agent activates the new firmware by a hardware reset of the device. This device hardware reset occurs without rebooting the server.

According to block after the device initializes from the reboot the device hardware agent sends a message through the device to the OS device driver to notify the driver of the completed firmware update. For example an OS specific message is sent indicating that a hot plug PCI event was received for the device and the device was initialized. This initialization does not require an OS reboot.

According to block the OS driver reinitializes the device and notifies the device hardware agent when initialization is complete.

According to block the device hardware agent notifies the BMC that the firmware update is complete including OS driver re initialization.

This method of can also be extended to device driver updates using the device hardware agent and device e.g. with the OS device driver being uploaded from the iLO manager through the device hardware agent to the current OS device driver . The new device driver would reload e.g. using the same hot plug PCI event message and reinitialize the device .

The term common API or standardized API is the application programming interface that abstracts the various different devices into a common set of hardware device manager interface commands example show device name show firmware version or update firmware .

The term hardware is a physical component of an electronic device e.g. a component of a server . Hardware is tangible i.e. can be touched as opposed to software which is not tangible.

The terms Integrated Lights Out iLO or baseboard management controller BMC are server management technologies that enables a remote electronic device or computer to perform activities on a server from a location remote to the server. For example an iLO card has a separate network connection and its own IP Internet Protocol address to which a user can connect through HTTP Hyper Text Markup Language over the Internet. The remote electronic device can perform actions such as reset the server power up the server take over the screen of the server mount remove physical CD DVD drives or images access the server s IML Integrated Management Log and provide a remote console for the server. Further iLO and BMC can be used as an out of band management technology.

The term microcontroller is a single integrated circuit that includes a processor core and memory. The microcontroller can also include programmable input output I O peripherals.

The term out of band communication is the exchange of information e.g. control information that is separate from server OS data. The out of band information can be provided on a separate dedicated channel from the data.

The term out of band management is system console access even in the event of a primary network subsystem hardware or software failure. This access can be provided with a console server or a remote access card.

In one example embodiment one or more blocks or steps discussed herein are automated. In other words apparatus systems and methods occur automatically. The terms automated or automatically and like variations thereof mean controlled operation of an apparatus system and or process using computers and or mechanical electrical devices without the necessity of human intervention observation effort and or decision.

The methods in accordance with example embodiments are provided as examples and should not be construed to limit other embodiments within the scope of the invention. Further methods or steps discussed within different figures can be added to or exchanged with methods of steps in other figures. Further yet specific numerical data values such as specific quantities numbers categories etc. or other specific information should be interpreted as illustrative for discussing example embodiments. Such specific information is not provided to limit example embodiments.

In some example embodiments the methods illustrated herein and data and instructions associated therewith are stored in respective storage devices which are implemented as one or more computer readable or computer usable storage media or mediums. The storage media include different forms of memory including semiconductor memory devices such as DRAM or SRAM Erasable and Programmable Read Only Memories EPROMs Electrically Erasable and Programmable Read Only Memories EEPROMs and flash memories magnetic disks such as fixed floppy and removable disks other magnetic media including tape and optical media such as Compact Disks CDs or Digital Versatile Disks DVDs . Note that the instructions of the software discussed above can be provided on one computer readable or computer usable storage medium or alternatively can be provided on multiple computer readable or computer usable storage media distributed in a large system having possibly plural nodes. Such computer readable or computer usable storage medium or media is are considered to be part of an article or article of manufacture . An article or article of manufacture can refer to any manufactured single component or multiple components.

Example embodiments are implemented as a method system and or apparatus. As one example example embodiments and steps associated therewith are implemented as one or more computer software programs to implement the methods described herein. The software is implemented as one or more modules also referred to as code subroutines or objects in object oriented programming . The software programming code for example is accessed by a processor or processors of the computer or server from long term storage media of some type such as a CD ROM drive or hard drive. The software programming code is embodied or stored on any of a variety of known physical and tangible media for use with a data processing system or in any memory device such as semiconductor magnetic and optical devices including a disk hard drive CD ROM ROM etc. The code is distributed on such media or is distributed to users from the memory or storage of one computer system over a network of some type to other computer systems for use by users of such other systems. Alternatively the programming code is embodied in the memory and accessed by the processor using the bus. The techniques and methods for embodying software programming code in memory on physical media and or distributing software code via networks are well known and will not be further discussed herein.

The above discussion is meant to be illustrative of the principles of various example embodiments. Numerous variations and modifications will become apparent to those skilled in the art once the above disclosure is fully appreciated. It is intended that the following claims be interpreted to embrace all such variations and modifications.

