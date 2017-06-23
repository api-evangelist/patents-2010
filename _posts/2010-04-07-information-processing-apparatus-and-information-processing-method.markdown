---

title: Information processing apparatus, and information processing method
abstract: A client is used in an environment in which a printing method for causing a device to print printing data via a print server coexists with a printing method for transmitting print data to the device without the intervention of the print server for printout. If it is determined that a printer driver to be set up on the local printer is a newer version than that of a printer driver for a network printer and is shared therewith, a printer driver to be set up on the local printer is set up, and setting processing regarding a printer driver on the print server so as to cause the network printer to operate normally is performed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08472057&OS=08472057&RS=08472057
owner: Canon Kabushiki Kaisha
number: 08472057
owner_city: Tokyo
owner_country: JP
publication_date: 20100407
---
The present invention relates to a printing system and a method for controlling the same in particular relates to an information processing apparatus for managing a device a client machine which are provided on a network and software required for printing by using an administration server and a program for controlling the same. Hereinafter the term client machine as used herein is referred to simply as client . Print data forming software installed on a client is so called a printer driver and hereinafter is also referred to as driver .

Conventionally a network printing environment provided with a client a print server a printer and an administration server for managing these has been proposed. A printing method using the printer driver corresponding to a shared printer on the print server and the driver corresponding to the network printer object is known. There is another printing method using a printer driver that corresponds to the local printer object locally connected to the client. The technique for forming a network printer object corresponding to a shared printer on the client is disclosed for example in Windows Point and Print Technical Overview Microsoft Published Mar. 21 2003 Update Nov. 20 2006.

On the client for example when the printer driver corresponding to the local printer object is updated its printer object may overwrite the printer driver corresponding to the network printer object. Consequently the versions and the like between the print server side printer driver corresponding to the shared printer object and the printer driver corresponding to the network printer object may become inconsistent.

As a result printing via the print server may be disabled from the client using the network printer or incorrect print results may be obtained. Therefore a printing system environment cannot be appropriately maintained in the prior art resulting in problems associated with maintenance and management.

In order to solve these situations the present invention provides an information processing apparatus that has a function of transmitting print data to a network printer via a locally connected local printer or a print server for print processing. In addition the information processing apparatus is used in an environment in which a printing method for processing print data by using a printer driver installed on the print server to cause the network printer to print the print data coexists with a printing method for transmitting print data to the locally connected local printer without the intervention of the print server for printout. The information processing apparatus includes a determination unit and a setting unit.

The determination unit determines whether or not a printer driver to be set up on the local printer is newer version than that of a printer driver for a network printer which is set up on the information processing apparatus and is shared therewith.

The setting unit sets up a printer driver to be set up on the local printer driver as well as perform settings on a printer driver for the print server so as to cause the network printer to operate normally if the determination unit determines that a printer driver to be set up on the local printer is a newer version than that of a printer driver for a network printer which is set up on the information processing apparatus and is shared therewith.

When a local printer is updated in a printing environment where a network printer coexists with the local printer the settings for a printer driver on the print server are performed so as to cause the network printer to operate normally. With this arrangement a driver version can be appropriately managed and thereby a normal printing system environment can be maintained and the convenience of maintenance and management can be improved as well.

Further features of the present invention will become apparent from the following description of exemplary embodiments with reference to the attached drawings.

Hereinafter preferred embodiments of the present invention will now be described with reference to the attached drawings.

In the network printing system environment exemplified in a device having a printing function a client a print server and a management server for managing these components are connected to each other via a communication line . Here the client transmits print data to a locally connected local printer or a network printer via the print server for print processing.

One is a method for processing print data by using the printer driver installed on the print server so as to cause the network printer to print the print data. As shown in print paths indicated by the solid line in this is a printing method via a print server in which print data is transmitted from the client to the device A via the print server for printout. In other words in this method a shared printer object is generated on the print server and a network printer object corresponding to the printer is generated on the client so as to perform printing via the print server .

Another is a method for transmitting print data to a local printer without the intervention of the print server for printout. In this case as shown in the print path indicated by the dotted line in print data is transmitted from the local printer of the client directly to the device B for printout. In other words printing is directly performed from the client without the intervention of the print server .

First the term administration server as used herein refers to a server that comprehensively performs device searching operating state monitoring various settings and the like mainly conducted by the IT information technology administrator. In other words the administration server searches for a device to be managed monitors whether or not the found device is in normal operation and further sets MIB Management Information Base information and the like held by the device. Furthermore the administration server has an additional function that directs installation processing or uninstallation processing for an appropriate print driver corresponding to the device with respect to a plurality of clients or a print server. Here as used herein the printer object is the settings for a printer which is registered at a registry managed by the print server or the OS provided in the client . More specifically a print destination address a printer name a driver path and printer attributes shared printer network printer local printer and the like are stored in the printer object.

Next the term shared printer method as used herein refers to an installation mode of a printer driver in which settings are made to share the printer driver installed on the print server so as to allow for use from a plurality of clients. The shared printer object is a structure that includes various settings of a shared printer to be set on the print server. The shared printer object performs communication between a network printer to be described below and various objects so as to realize print processing.

The term network printer object as used herein refers to a structure to be installed on a client in a manner corresponding to a shared printer in order to utilize the shared printer on the client. For example the network printer corresponding to the shared printer can be formed on the client by using the Point and Print function provided by the operating system Windows developed by Microsoft e.g. see Windows Point and Print Technical Overview Microsoft Published Mar. 21 2003 Update Nov. 20 2006 .

In this system it is important that the shared printer on the print server and the printer driver for the network printer on the client are synchronized. The synchronization for the printer drivers here means maintaining the identity of the driver attributes. In other words the print driver includes attributes such as the manufacturer direction PDL e.g. page description language for forming a print job such as PCL PostScript or the like and version. The synchronization for the printer drivers means maintaining the identity of these attributes. In particular when focusing on a single printer driver the version of the print driver is often upgraded to deal with fault countermeasure and functional improvement. In such a case if the printer driver of a shared printer is version 1.00 for example the network printer on the client which corresponds to the shared printer also needs to be upgraded to version 1.00.

In the printing method via a print server the network printer on the client essentially performs document settings for forming a print job and the shared printer on the print server performs device settings and spooling. As used herein the term document settings means the items to be set individually for printing such as sheet size copies the method for feeding sheets and the like for forming a print job. On the other hand the term device settings refers to the items to be uniquely determined by the device which include port settings sheet discharging options that can be used in the device and the like. In other words document settings are the items to be set individually for each client and device settings are the items to be set for clients in common. Note that in the printer driver for Windows such settings can be made by a property function held by each of the printer drivers. In addition rendering processing for forming a print job may be performed by the print server.

In this way in the printing method for printing via the print server print processing is realized by the client and the printer driver on the print server in a pair wise form.

For the Point and Print function when a version upgrade of the shared printer on the print server is made an automatic version upgrade of the client network printer corresponding to the shared printer is also made.

Next the term local printer as used herein generally refers to a printer connected locally to a client. For a local printer the client may perform all processing for printing such as document settings device settings rendering processing spool processing port processing and the like. Hence in the printing method using a local printer a print job formed by the client printer driver is transmitted directly to the device without the intervention of the print server.

As described above there are two different modes for realizing printing from the client to the device. One is a mode for employing the network printer corresponding to the shared printer on the print server and the other is a mode for employing an individually installed local printer.

Here it should be noted that a version upgrade of the printer driver on the client is different between the network printer and the local printer. In other words there is no need for the client to perform individual updates for the network printer. This is because the network printer corresponding to the shared printer is automatically updated when the version of the shared printer on the print server is upgraded.

However in the prior art described above the problem of the integrity of the printer driver exists when the network printer and the local printer are present on the client.

In other words assume the case where the version of the printer driver for the local printer is upgraded when the network printer and the local printer have the same kind of the printer driver and are shared with an output device. With this version upgrade the version of the same printer driver for the network printer is also upgraded. Consequently the print driver of the shared printer on the print server and the print driver of the network printer on the client become different and are inconsistent with each other.

Next using the Point and Print function the network printer A v100 corresponding to the shared printer A is generated on the client.

Thereafter the printer driver A v200 for the local printer B is installed on the client. In other words the term v200 as used herein means the printer driver version 2.00 the printer driver A v200 is an upgraded version of the printer driver A v100 .

With this arrangement the version of the network printer A v100 on the client is also upgraded to the printer driver A v200 .

As a result although the network printer A on the client is upgraded to version 2.00 the shared printer A for the print server corresponding thereto remains at version 1.00.

Hereinafter the preferred embodiments of the present invention will now be described with reference to the attached drawings.

Prior to the explanation of the flowchart shown in the configuration of the printing system environment will be described.

Each of the information processing apparatuses is configured with a computer includes one central processing unit and respectively and functions as a main control unit. In other words the management server includes the first central processing unit and the device includes the second central processing unit . The client includes the third central processing unit and the print server includes the fourth central processing unit .

For each of the information processing apparatuses program and relevant data are stored on a storage medium such as FD CD ROM IC memory card and the like and are read out from storage medium reader devices and respectively. In other words the management server includes a first storage medium reader device and the device includes a second storage medium reader device . The client includes a third storage medium reader device and the print server includes a fourth storage medium reader device . The storage medium may be configured with a hard disk an optical magnetic disk or the like or may be configured in combination with these units.

The storage sections and are provided in each of the apparatuses and the system program and the application program are loaded from these storage sections to data control sections and respectively. In other words the management server includes a first storage section and a first data control section and the device includes a second storage section and a second data control section . The client includes a third storage section and a third data control section and the print server includes a fourth storage section and a fourth data control section . Note that the first data control section is configured using a device management application section . In addition the third data control section is configured using an executable file section and the fourth data control section is configured using a driver management service section . The details of which will be described later.

The system program and the application program process display information on display sections and of each apparatus and information that has been input from input sections and of each apparatus. In other words the management server includes a first display section and a first input section and the device includes a second display section and a second input section . The client includes a third display section and a third input section and the print server includes a fourth display section and a fourth input section . Note that a display device such as a CRT display a liquid crystal display or the like can be used for the display sections and . Also the input sections and can be configured with a pointing device such as keyboard mouse or the like. Each apparatus is provided with input output data control sections and . In other words the management server includes a first input output data control section and the device includes a second input output data control section . The client includes a third input output data control section and the print server includes a fourth input output data control section .

Each apparatus performs the input and output of data via interface control sections and thereof. In other words the management server includes a first interface control section the device includes a second interface control section . The client includes a third interface control section and the print server includes a fourth interface control section .

Components in the apparatus are communicatably connected with each other via a bus. For example each component of the device is connected to each other via a bus .

The device is a printing device having a print processing function and includes a device interface control section and a printer engine section . The device may be a single function peripheral SFP having only a printing function or a multi function peripheral MFP having a scanner function copying function fax function and the like in addition to the print function. Furthermore the device holds device information such as MIB. Acquiring and setting such information are performed by an IT administrator from the management server via a network.

On the client printing becomes possible either by performing printing using the network printer from the device via the print server or by transmitting print data directly to the device via the local printer. These print paths are as shown in .

In a printing method via a network printer as shown by the solid line in print data is transmitted from the client to the device device A via the print server .

In a printing method via a local printer as shown by the dotted line in print data is directly transmitted from the client to the device device B . In other words this method does not pass through the print server as a print path.

Here on the print server a driver is installed as a shared printer so as to provide a network printer to the client using the Point and Print function from the client .

Next an essential part of a system configuration to which the present invention is applied will be described with reference to .

The main components are the device management application section of the management server the executable file section of the client and the driver management service section of the print server .

Furthermore the device management application section is configured with a driver management control section an information management section and a driver storage section .

The device management application section has a search function for the device . As a result of device searching the device name IP address for the device or the like is acquired. Here the term device searching means searching with a known SNMP IP Broadcast SLP Multicast and the like.

The driver management control section has a driver task function for realizing an addition of a printer or a driver update and an executable file download function for realizing driver installation.

Hereinafter in the present embodiment the driver task function that realizes the addition of a printer and driver update is referred to as a PUSH function and the executable file download function for realizing driver installation is referred to as a PULL function .

The PUSH function denotes a function in which an IT administrator remotely installs a driver corresponding to any device on the client or the print server .

On the other hand the PULL function permits the download of an executable file for installing a driver corresponding to any device from the client .

By executing the executable file on the client the executable file acquires information required for installation of the driver from the driver management control section so as to realize installation. Here the term information required for installation of the driver as used herein means information such as location information about the entity of the driver to be installed the IP address of the device required for generating a printer port or the like. Hereinafter the term information required for installation of the driver is referred to as driver information .

Information exchange between the executable file section and the driver management control section is carried out by communication with a Web service that employs a protocol such as so called SOAP Simple Object Access Protocol .

In other words the PUSH function is an installation of a driver to the client and the print server on the initiative of the management server whereas the PULL function is an installation of a driver on the initiative of the client.

However in the PUSH function an agent service needs to be previously installed on the client or the print server of the target in order to execute a driver task. Here the driver management service section for the print server is configured by using the agent service. In other words this process is carried out by using what is termed a service program having a driver installation function.

Information exchange between the driver management service section and the driver management control section is carried out by communication with a Web service that employs a protocol such as SOAP or the like as in information interaction between the executable file section and the driver management control section .

Also as in the executable file section the driver management service section has functions such as acquiring the driver stored in the driver storage section acquiring printer port information and installing a driver.

The driver storage section is an FTP File Transfer Protocol server an HTTP Hypertext Transfer Protocol server a file server or the like and is a server on which a driver is stored. The driver is a printer driver that serves as software for forming print data. The driver stored on the driver storage section can be downloaded from the executable file section and the driver management service section .

On the other hand the information management section is configured using so called database DB . The information management section manages table information as shown in for example. In addition the information management section manages update mode setting information see provided by the driver management control section and attribute information of the driver managed by the driver storage section .

Note that the information management section and the driver storage section may be provided on the same server as the management server as in the present embodiment or may be provided in a separate server.

Hereinafter the details of the control procedure according to the present embodiment will be described with reference to in addition to and .

Each of is a flowchart illustrating exemplary client processing performed by the executable file section of the client . Note that numbers and shown in a pentagonally shaped frame in denote the corresponding positions shown in .

The first update mode hereinafter referred to as update mode is a mode for changing a network printer to a local printer when a driver to be installed on the local printer is the same kind as that of the network printer and both printers are used in common. In other words when the driver to be newly installed on the local printer is the same kind as that of the existing network printer and the driver itself is also the same kind the network printer is changed to the local printer so as to ensure the integrity of the drivers. In the update mode the local printer to be newly generated on the client is prioritized and hence it is understood that the PULL mode is prioritized.

The second update mode hereinafter referred to as update mode brings the print server under control when the print server is not brought under control. With the present mode the integrity of the drivers to be used by the shared printer on the print server the network printer on the client and the local printer is ensured. Here the term to bring the print server under control means to bring the print server under the control of the driver management control section . At this time the driver management service section is installed on the print server and then as shown in shared printer information on the print server is managed by the information management section .

The third update mode hereinafter referred to as update mode is a mode for ensuring the integrity between drivers when the print server is a client under the control of the driver management control section . In other words the update mode ensures the integrity of the drivers among the shared printer on the print server the network printer on the client and the local printer.

The fourth update mode hereinafter referred to as update mode is a mode for prioritizing the driver version of the network printer on the client irrespective of whether or not the print server is brought under the control of the driver management control section .

In the aforementioned description the term to ensure the integrity of the drivers means to ensure the identity of the kind and version of the drivers so as to make each driver operate normally.

Commonly when the drivers are the same kind but a different version the driver with a higher version number is prioritized.

For example the version of the driver for the existing network printer is 1.00 and the output destination device is assumed to be the device A see V100 and device A in the left field . Assume the case where a local printer in which the version of the driver A is 2.00 and the output destination device is the device B is to be newly generated on the client see V200 and device B in the top field .

In this case the rule among the installation rules in is applied. In other words it means that the existing network printer is changed to the local printer in which the output destination device is the device A by using the driver A of version 2.00. Furthermore the rule means generating a newly specified local printer object in which the output destination is the device B.

Another example is that the version of the driver for the existing network printer is 3.00 and the output destination device is the device A see V300 and device A in the left field . Assume the case where a local printer in which the version of the driver A is 1.00 and the output destination device is the device B is to be newly generated on the client see V100 and device B in the top field .

In this case the rule among the installation rules in is applied. In other words it means that the existing network printer is generated after changing to the local printer in which the output destination device is the device A by using the existing driver A of version 3.00. Furthermore in the rule it means that a new local printer in which the output destination is the device B is also generated by using the existing driver A of version 3.00.

As described above an appropriate installation rule is obtained depending on the existing network printer information and the driver information to be newly installed. Note that the installation rules in are intended as an example a different installation result from that of the present embodiment can of course be obtained by changing the installation rules.

For example in the latter example the version of the driver for the existing network printer is compared with that of the newly specified driver. When the version of the driver for the existing network printer is newer than that of the newly specified driver it is also possible that the existing network printer is not changed to the local printer. For the newly specified local printer the local printer object in which the output destination is the device B is generated by using the driver constituting the existing network printer. Note that the installation rules in may be acquired from the first driver management control section of the management server see step in to be described below or may be incorporated as a part of the executable file section .

First assume that a printer name printer A which is supported by a driver having a driver name of driver A and a version of 1.00 is installed on the print server . Also the printer A is a shared printer having the shared name shared printer A and the print server is not yet managed by the driver management control section of the management server . In other words management data as shown in is not in the table. Furthermore assume that the driver management service section see the dotted line frame shown in that communicates with the driver management control section of the administration server is not yet installed on the print server .

On the other hand the network printer having the printer name of printer A corresponding to the shared printer having the shared name of shared printer A is installed on the client using the Point and Print function. The driver used for the shared printer shared printer A and the driver of the network printer printer A for the client are both the same kind and the same version and are in the state where they are mutually consistent.

In such a printing system environment the following driver is assumed to be managed by the information management section and the driver storage section of the driver management control section in the management server .

The driver which is the same kind as that for the network printer its version is newer that that of the driver for the network printer i.e. 2.00 .

In other words the driver name is driver A and its version is 2.00 and the printer name is printer A . Here the printer name may be same as or different from that of the network printer. When the driver is installed on the client processing for updating a driver used in the network printer on the client is involved.

Under the aforementioned assumed conditions processing shown in which is performed by the management server will now be described.

First an IT administrator accesses the device management application section of the first data control section by using the first input section and the first display section of the management server see step .

Here when the application used for the device management application section is a Web application such an application can be accessed from a separate client for administrator instead of the management server . When the client for an administrator can remotely access the management server the device management application section may use what is referred to as a native application.

Next an IT administrator uses the first input section and the first display section of the management server so as to perform a selection operation under the update mode setting menu on the first driver management control section see step . This means that the user interface screen exemplified in is displayed so as to prompt the IT administrator to carry out an operation and this screen is under the control of the driver management control section .

Next during execution of the executable file in the client the driver management control section selects the update mode for the user interface screen shown in when the network printer is present in the client see step .

Subsequently when any operation of the registration button on the screen in has been detected the driver management control section stores data indicating the selected update mode into the information management section see step . For example as shown in the update mode is selected as the update mode.

The above processing is defined as pre processing. Hereinafter processing for installing a new driver on the client will be described.

First the client accesses the driver management control section of the device management application section in the management server see step .

The client executes the downloaded executable file see step . Here the processing being activated by executing the downloaded executable file has the same meaning as the executable file section on the third data control section being in operation.

Also the executable file section is assumed to hold location information such as IP address or DNS of the management server as a part of the executable file section when the executable file is downloaded from the driver management control section .

On the other hand when location information about the management server is absent the executable file section can also have a search function for the management server using SLP Multicast or the like.

The executable file section accesses the driver management control section of the management server and acquires driver information about the driver to be installed from the information management section see step .

Next the executable file section acquires the target driver to be newly installed the driver to be installed from the driver storage section of the management server see step .

In the present embodiment it is assumed that the version of the acquired driver is 2.00 and its output destination device is the device B.

Subsequently the executable file section acquires information about the driver installed on the client see step .

In the present embodiment the driver of the client is the same kind as that which has been acquired in step . However this driver is the driver of version 1.00 for the network printer and its output destination is the device A. In other words the existing driver and the driver to be newly installed are both the same kind but different versions and have a different output destination device as well.

Next the executable file section determines whether or not any network printer is present on the client see step . Here when a network printer is present and the determination result is Yes the processing advances to step . If the determination result is No the processing advances to step .

Next the executable file section determines whether or not the network printer having the same kind of driver as the driver to be newly installed is present see step . Here the determination result is Yes the processing advances to step . If the determination result is No the processing advances to step .

Subsequently the executable file section acquires update mode information from the driver management control section of the management server see step . This information is stored in the information management section in step shown in .

In the present embodiment the executable file section acquires update mode information indicating the update mode as shown in .

Next the executable file section determines whether or not the acquired update mode is the update mode see step . Here the determination result is Yes and thereby the processing advances to step . However if the determination result is No the processing advances to step .

The executable file section determines whether or not the version of the driver to be newly installed i.e. the version of the printer driver to be set up is newer than that of the driver for the existing network printer see step . Here the determination result is Yes the processing advances to step .

Subsequently the executable file section generates a local printer object using the driver to be newly installed in accordance with the pre defined installation rules shown in see step .

Next the executable file section determines whether or not the output destination device for the driver to be newly installed is the same as that for the existing network printer step . Here the determination result is No the processing advances to step .

Next the executable file section generates a local printer object in which the output destination device for the existing network printer is to be the printer port by using the driver to be newly installed see step .

Then setting processing for the printer driver on the print server is performed see step . This processing includes deletion of the printer settings on the print server corresponding to the network printer. For example the executable file section deletes the existing network printer object.

On the other hand if the determination result in step is No the processing advances to step . Here the executable file section generates a local printer object by using the driver for the existing network printer in accordance with the installation rules shown in .

Next the executable file section determines whether or not the output destination device of the driver to be newly installed is the same as that of the existing network printer see step . If the determination result is No the processing advances to step whereas if the determination result is Yes the processing advances to step .

The executable file section generates a local printer object in which the output destination device for the existing network printer is to be the printer port by using the driver for the existing network printer see step . The process is terminated via step .

When the update mode shown in is the update mode determination processing in step is performed after steps to . Here the determination result is No and the processing advances to step .

The executable file section determines whether the update mode is either the update mode or the update mode see step . Here the determination result is Yes the processing advances to step .

The executable file section determines whether or not the version of the driver to be newly installed is newer than that of the driver for the existing network printer see step . If the determination result is Yes the processing advances to step whereas if the determination result is No the processing advances to step .

The executable file section requests the task execution for the print server with respect to the driver management control section of the management server see step . Note that the executable file section also requests the driver information driver type version output destination device for the driver to be newly installed.

Next the driver management control section requests network printer information with respect to the executable file section on the client see step .

The executable file section acquires the network printer information on the client see step . Here the network printer information includes the driver information constituting the network printer and information indicating which shared printer on the print server is synchronized with the network printer.

The name of the driver on the print server named print server A is driver A and its version is 1.00 and the name of the network printer consisting of the shared printer named shared printer A is printer A .

Note that the aforementioned information is registered on a storage area such as the registry of the client and can be acquired either by searching the registry or by employing API Application Programming Interface provided by the operating system.

Next the executable file section sends network printer information to the driver management control section see step .

Referring again to the continuation of the processing performed by the management server will be described.

In step the driver management control section receives network printer information from the executable file section on the client so as to store it in the information management section . In the present embodiment the network printer A corresponding to the driver of the shared name shared printer A on the print server A is installed on the client and its version is 1.00.

Next the driver management control section accesses the information management section and acquires information about the print server and its shared printer that are managed therein see step . An example of this is shown in . In the present embodiment it is assumed that there is no print server information under the control of the driver management control section at that time.

The driver management control section accesses the information management section and acquires update mode setting information see step . In this case the update mode in the acquired update mode setting information is the update mode .

Next the driver management control section determines whether the update mode is the update mode or the update mode see step . Here the determination result is Yes and the processing advances to step .

The driver management control section compares the network printer information that has been acquired in step with the print server and its shared printer information that have been acquired in step step . Here comparison means to determine whether or not the driver management control section manages the print server on which the shared printer corresponding to the network printer on the client is installed. If the determination result is No the processing advances to step .

The driver management control section generates a task for distributing the driver management service section which is an agent to the print server in order to place the print server under the control of the driver management control section see step .

Subsequently the driver management control section executes an agent distribution task to the print server see step . The installation of the driver management service section to the print server means for example to utilize a remote distribution technique such as WMI which is incorporated in the OS of Microsoft Corp. Note that WMI is an abbreviation for Windows Management Instrumentation .

The fourth data control section of the print server performs installation processing of the driver management service section as an agent task process from the driver management control section see step .

Next the fourth data control section determines whether or not the installation processing of the driver management service section has been completed successfully see step . If the determination result is Yes the processing advances to step whereas if the determination result is No the processing advances to step .

The driver management service section acquires print server information that indicates whether or not the shared printer has already been installed on the print server see step .

Subsequently the driver management service section returns the information indicating the success or failure of installation in step and the information that has been acquired in step to the driver management control section of the management server see step .

Referring again back to the continuation of the processing performed by the management server will be described.

In step on the basis of the agent task results obtained from the driver management service section of the print server the driver management control section determines whether or not the agent task has been completed successfully. If the determination result is Yes the processing advances to step .

The driver management control section registers the print server information obtained from the driver management service section of the print server to the information management section see step . In the present embodiment the information of the print server named print server A as shown in is assumed to be registered.

Next the driver management control section returns to step and performs determination processing. This time the determination result is Yes and the processing advances to step . Here the driver management control section generates a driver update task for the shared printer located on the print server . In the present embodiment the driver update task refers to generating a task for updating the driver A on which the shared name of the print server is shared printer A from version 1.00 to version 2.00.

Next the driver management control section executes the generated driver task for the driver management service section of the print server see step .

The driver management service section updates the driver for the shared printer A such that the version of the driver is updated from 1.00 to 2.00 see step .

Next the driver management service section returns the task execution results back to the driver management control section of the management server see step .

Referring again back to the continuation of the processing performed by the management server will be described.

In step the driver management control section determines whether or not the driver update task in step has been completed successfully. If the determination result is Yes the processing advances to step .

The driver management control section directs driver update task processing involving an update for the network printer to the executable file section of the client see step .

In step the executable file section executes installation processing of the local printer involving a driver update for the network printer. Then the series of processes is terminated.

On the other hand if the determination result in step shown in is No or if the determination result in step is No the processing advances to step after step in determination result is Yes . The executable file section of the client does not perform processing such as the addition of a printer or an update of a driver and the series of processes is terminated.

In this case it is assumed that the driver management control section of the management server brings the print server for the shared printer corresponding to the network printer on the client under its control. In other words this means that information shown in has been registered on the information management section .

In step the driver management control section brings the print server for the shared printer corresponding to the network printer on the client under its control. Hence the determination result is Yes and the processing advances to step . The following processing is the same as that described in steps to in steps and in and steps and in and the description thereof will be omitted herein to avoid repetition.

Processing in steps to is the same as that described above. The determination result in step is No and the processing advances to step . Here the determination result in step is No and the processing advances to step . The executable file section determines whether or not the update mode is the update mode . Here the determination result is Yes and the processing advances to step .

The executable file section determines whether or not the version of the driver to be newly installed is newer than that of the driver for the existing network printer see step . If the determination result is Yes the processing advances to step . Here the executable file section of the client does not perform processing such as an addition of a printer or an update of a driver and the series of processes is terminated.

If the determination result in step or is No that is if the version of the driver to be newly installed is the same as or older than that of the existing network printer the processing advances to step . Here the executable file section newly installs the local printer by using the driver constituting the existing network printer and the series of processes is terminated.

Also if the determination result in steps and is No the processing advances to step . Here the executable file section performs processing such as an addition or an update for a local printer and the series of processes is terminated.

If the determination result in step shown in is No the processing advances to step . Here the driver management control section provides instructions about which version of the network printer is prioritized to the executable file section of the client . After the executable file section has executed the processing in steps to shown in the series of processes is terminated.

Note that after the processing in steps and shown in the installation processing result may be displayed. In other words the processing result is displayed on the third display section of the client by using a message box which provides an attention to an operator.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium .

While the embodiments of the present invention have been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all such modifications and equivalent structures and functions.

This application claims the benefit of Japanese Patent Application No. 2009 096011 filed Apr. 10 2009 which are hereby incorporated by reference herein in its entirety.

