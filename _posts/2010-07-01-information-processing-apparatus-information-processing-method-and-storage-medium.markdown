---

title: Information processing apparatus, information processing method, and storage medium
abstract: When an application is launched, it is determined whether a launching source is a device management. If it is determined that the launching source is the device management, a peripheral apparatus associated with the device management serving as the launching source is controlled as a default peripheral apparatus.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09300820&OS=09300820&RS=09300820
owner: CANON KABUSHIKI KAISHA
number: 09300820
owner_city: Tokyo
owner_country: JP
publication_date: 20100701
---
The present invention relates to an information processing apparatus that can communicate with a peripheral apparatus.

A peripheral apparatus control system enables a user of a personal computer hereinafter referred to as PC to access a peripheral apparatus via an appropriate interface such as USB Ethernet or wireless LAN. This kind of control system can be effectively used for various users in their houses and offices. An example of the peripheral apparatus is for example a printer a copying machine a facsimile machine a scanner a digital camera or a multifunction peripheral.

Windows 7 product name which is provided by Microsoft Corporation includes newly introduced functions to manage peripheral apparatuses connected to a PC. For example Devices and Printers is a window that displays a peripheral apparatus or a plurality of apparatuses connected to the PC. Device Stage international registered trademark is a visual screen that displays a link to a unique application or service provided by each apparatus. Therefore users can easily access various functions and services relating to respective peripheral apparatuses.

Conventionally transmission of a print instruction from a Windows application to a peripheral apparatus e.g. a printer a scanner a copying machine or a multifunction peripheral is performed according to the following procedure. More specifically the procedure includes selecting an apparatus as an output destination and causing the selected apparatus to perform printing as processing to be executed after an application is launched by a user.

For example a technique discussed in Japanese Patent Application Laid Open No. 2005 85132 can be used to select an apparatus as an output destination. More specifically an information processing apparatus can communicate with a plurality of printers. When the information processing apparatus transmits generated print data to a printer selected from the plurality of printers the processing procedure includes acquiring a status of a predetermined printer and switching a registered default printer to another printer based on the acquired status of the predetermined printer. The switching processing can be executed by referring to priority information of each printer serving as a default printer.

The processing procedure further includes detecting a printer whose status is changed determines whether the detected printer is a printer having a highest priority and performing default printer switching processing based on a determination result.

In a case where a linked application is launched from the Device Stage screen printing is executed according to a printing procedure different from the conventional procedure.

More specifically in a case where printing is instructed from an application a default apparatus i.e. usually used printer previously set for the PC is brought into an initially selected state. Therefore in a case where an apparatus associated with the Device Stage screen is not the predetermined apparatus preliminarily set for the system an apparatus that is not intended by a user may be initially set for the system even after the user has recognized completion of the selection of a desired apparatus on the Devices and Printers screen. As a result the user is required to repeat the above described apparatus selection. Therefore the user interface is inferior in operability.

According to an aspect of the present invention an information processing apparatus can communicate with a plurality of peripheral apparatuses. The information processing apparatus includes a setting unit configured to set a predetermined peripheral apparatus as a control target peripheral apparatus of the information processing apparatus a display unit configured to display a management screen that corresponds to a second peripheral apparatus a launch control unit configured to launch an application associated with the management screen in response to an instruction entered via the device management screen that corresponds to the second peripheral apparatus and a selection unit configured to input identification information of the peripheral apparatus in response to the launching of the application thereby causing the second peripheral apparatus to be selected as the control target peripheral apparatus.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

In the following exemplary embodiment a Devices and Printers screen see can be displayed when it is selected from a start menu screen of the Windows. Further a Device Stage screen see of each apparatus can be opened when it is selected from the Devices and Printers screen. For example in a case where the selected apparatus is a printer the Device Stage screen can display a link to an application that enables users to open photos or documents to display or print.

Further the Device Stage screen can display a link to a status monitor that acquires information indicating an operational state of an apparatus e.g. a printer or a scanner and manages the apparatus. Further there are various online services available via the Internet for information processing apparatuses and peripheral apparatuses. For example if the Device Stage screen provides a link to a support site on the Internet that is provided by a manufacturer of an apparatus users can easily access an intended site relating to their apparatuses.

The problem of the above described apparatus is already described. The Device Stage screen is an example of a device management screen associated with a predetermined device.

The MFP is an example of a peripheral apparatus according to the present invention. The MFP is for example a multifunction peripheral having a model name Kmmn which is manufactured by ABC Corporation. The peripheral apparatus according to the present invention is not limited to the MFP and can be constituted by a printer a copying machine a facsimile machine a scanner a digital camera or any other apparatus having comparable functions.

As an example function relating to the present invention the application can display device management screens illustrated in . The PC further includes a printer driver see and a FAX driver . The network is a private network constructed in a house of a user i.e. a client who uses the MFP . The MFP is connected to the PC via the network and can be commonly used among a plurality of users in the house.

The network is an office network provided for use in ABC Corporation. The PC connected to the network includes a Web server that has Web server functions to provide a Web site of ABC Corporation via the Internet. A compact disk read only memory CD ROM is a portable storage medium that can be inserted into the PC . The CD ROM can store software programs and electronic files.

The Web server can distribute a control file data for use in device management hereinafter referred to as control file for device management . The CD ROM can also distribute a control file data for use in device management hereinafter referred to as control file for device management .

The PC can use an analog telephone circuit for facsimile transmission or reception. A flash memory can be inserted into a dedicated slot not illustrated of the MFP . The flash memory serves as a storage that the PC can refer to. A printer is a printer having a model name Defg and manufactured by XYZ Corporation. The printer is a device different from the MFP in type. For example the printer is a laser printer having a single function or an inkjet printer. A print engine is any one of an inkjet type an electrophotographic type a color type or a monochrome type.

As illustrated in the PC includes a random access memory RAM a hard disk drive HDD serving as a storage unit a keyboard KBD serving as an input unit and a central processing unit CPU serving as a control unit. The PC further includes a liquid crystal display device LCD serving as a display unit a network board NB serving as a communication control unit and a bus that connects the above described functional units of the PC .

The HDD can be replaced with a portable CD ROM or a built in ROM that can also serve as a storage unit. An application for device management and respective modules software programs illustrated in and can be stored in the HDD . The CPU can execute each module software program loaded into the RAM from the HDD . Therefore the CPU can realize functions of the application for device management and various functions of respective modules software programs illustrated in and .

The ROM stores software programs that cause the MFP to perform recording printing processing under the control of the printer driver see and perform processing for transmitting information indicating an operational state of the MFP to the PC . The RAM temporarily stores print data mainly transmitted from the PC . The recording unit performs printing based on the print data stored in the RAM . Further the RAM temporarily stores image data read by the reading unit facsimile transmission data received from the PC and facsimile reception data received by the facsimile control unit .

The communication unit includes a connection port for the network and a connection port for the analog telephone circuit . The communication unit controls analog communications such as Ethernet and facsimile. The recording unit includes a recording unit and an electric circuit. The recording unit includes an inkjet type recording head a color ink cartridge a carriage and a recording sheet conveyance mechanism. The electric circuit such as ASIC controls the recording head to generate pulses for printing based on the print data.

When a printing operation or a facsimile transmission operation is made by a user via a print application contents image data of a displayed file that is opened by the application are temporarily stored as an EMF type spool file in the HDD of the PC . Then the image data are converted via the printer driver or the FAX driver into print data or facsimile transmission data including a command for controlling the MFP and then transmitted via the network to the MFP .

When the MFP receives print data the recording unit converts the received print data into pulses for printing and prints an image on a recording sheet. When the MFP receives facsimile transmission data the facsimile control unit converts the received facsimile transmission data into facsimile communication protocols and transmits facsimile data to a facsimile apparatus of another user via the analog telephone circuit .

The operation unit includes a power source button a reset button and other various buttons which enable users to operate the MFP . The display unit is for example constituted by a touch panel or a liquid crystal display device. The display unit can display an operational state of the MFP and can also display various setting information and telephone numbers which may be input by users.

The reading unit includes a color image sensor and an electric circuit constituted by ASIC for image processing. The facsimile control unit is constituted by a facsimile modem or an analog communication circuit. The facsimile control unit controls transmission and reception of facsimile data according to facsimile communication protocols. The apparatus illustrated in can communicate with the MFP via a network . The network is a network constituted by at least one of the network the Internet and the network or a combination thereof.

The Ethernet control stack can control the Ethernet. The IP Network control stack can control the Internet Protocol IP Network. The WSD control stack can control the Device Profile for Web Service WSD . The IHV native protocol control stack can control unique protocols of the Independent Hardware Vendor IHV . The N PnP control stack can control the Network Plug and Play hereinafter referred to as N PnP .

For the purpose of providing a support for network connection devices Windows Vista OS includes an extended plug and play function which is referred to as Plug and Play Extensions PnP X as an initially installed standard function. However the N PnP function is used in the present exemplary embodiment which is a function comparable to the PnP X function.

The device driver group includes a standard driver group incorporated as standard software programs in the program package for the OS. The device driver group further includes an IHV made driver group that can be provided from the IHV. The application DDI interface includes an Application Programming Interface API and a Device Driver Interface DDI . The application for device management hereinafter referred to as device management is a standard software program incorporated in the program package for the OS.

A print application is described below with reference to . The application group includes the device management and the print application . The device management manages and executes a Devices and Printers folder illustrated in and a device management screen illustrated in . The software configuration of the PC illustrated in is applicable to the PC illustrated in .

The OS includes a Graphics Device Interface GDI and a spooler . The spooler includes a printer queue that performs queuing of print jobs. A printer queue folder displays the queued print jobs. The print processor can change a print layout and can perform special processing on a printed image. The graphics driver which serves as a core part of the printer driver performs image processing for printing based on a drawing command transmitted from the GDI and generates a print control command.

The UI module can provide a user interface for the printer driver and can control the user interface. The language monitor serving as a data communication interface I F can control transmission and reception of data. The status monitor can display an ink remaining amount of each ink usable by the MFP and can also display warning error and other states.

A port monitor can perform processing for receiving data from the language monitor and transmitting the received data to an appropriate port. The port monitor can further perform processing for receiving data from the MFP via a class driver . The class driver is a low level module closest to the port. In the present invention the class driver corresponds to a driver for a unique protocol WSD or IHV printer class which controls the port e.g. a network port in the present invention . The printer driver is a driver provided by ABC Corporation i.e. a manufacturer of the MFP .

The N PnP control stack the WSD control stack the IP Network control stack the Ethernet control stack and the application DDI interface are modules provided by the OS. The GDI illustrated in partly corresponds to the module . More specifically the GDI is an interface that can be called by the application. The graphics driver has a function of converting data input via the GDI interface into a DDI command. The graphics driver and the UI module correspond to the standard driver group and the N PnP control stack illustrated in . The IHV native protocol control stack has a function that corresponds to the function of the port monitor illustrated in although it is limited to a portion that the IHV can provide as an extension function of the OS.

In step S the device management starts the processing of the flowchart illustrated in when the PC e.g. the PC is connected to an external device e.g. the MFP via the network . In step S the PC acquires a device ID of the device i.e. the MFP . The device ID acquired in step S is for example MFG ABC MDL Kmmn CLS PRINTER CMD K4 DES ABC Kmmn which is expressed using a character string. The PC can acquire a device ID of any printer function of the MFP from the MFP via the network . The device ID includes the following information.

Next in step S the device management determines whether installation of the driver e.g. the printer driver and the FAX driver is already completed. If it is determined that there is not any installed driver NO in step S then in step S the device management installs the driver e.g. the printer driver and the FAX driver .

If the installation of the driver e.g. the printer driver and the FAX driver is successfully completed a printer mark corresponding to the newly installed driver is added registered to the Devices and Printers folder illustrated in .

If it is determined that the driver the printer driver and the FAX driver is already installed YES in step S the processing proceeds to step S.

Then in step S the device management determines whether the control file for device management see is not yet installed. To perform the determination processing in step S the device management can refer to manufacturer information MFG and model information MDL included in the device ID to check whether the installed control file for device management matches with the driver the printer driver and the FAX driver .

If it is determined that the installation of the control file is not yet completed NO in step S then in step S the device management executes processing for installing the control file for device management as illustrated in and completes the processing. If it is determined that the control file for device management is already installed YES in step S then in step S the device management terminates the processing routine illustrated in .

In step S illustrated in the device management starts file installation processing when the device management determines to execute the processing for installing the control file for device management in step S of . First in step S the device management confirms a device ID of the MFP i.e. the device connected via the network .

In step S the device management searches for a control file for device management dedicated to the MFP i.e. the device connected to the PC based on the manufacturer information MFG and the model information MDL included in the device ID.

A control file for device management illustrated in includes descriptions relating to the device the MFP . More specifically a description relating to the manufacturer MFG ABC is included in an element indicating a description and a description relating to the model MDL Kmmn is included in an element indicating a description .

The device management searches for the control file for device management dedicated to the MFP from various control files for device management stored in the Web server or the CD ROM inserted in the PC based on the information described in the elements and .

In step S the device management determines whether the control file for device management or the control file for device management has been found. If it is determined that the control file for device management or the control file for device management is detected YES in Step S then in step S the device management stores the detected control file for device management in the HDD of the PC .

In step S the device management terminates the file installation processing illustrated in . In the present exemplary embodiment the device management detects installation of the control file for device management that corresponds to the device the MFP .

If it is determined that neither the control file for device management nor the control file for device management was detected NO in Step S then in step S the device management terminates the processing routine without installing any control file for device management.

The print application includes a launching source determination unit an application control unit a default device setting unit a print control unit and a status acquisition unit . The device management screen is launched and displayed when a device is selected from the Devices and Printers folder illustrated in . For example when the device is selected in the device management screen is launched as illustrated in .

In step S the device management starts device management screen launch processing in response to selection of the device from the Devices and Printers folder .

Next in step S the device management control unit acquires a device name of the device selected from the Devices and Printers folder . In the present exemplary embodiment the device management control unit acquires a device name ABC Kmmn of the selected device .

Next in step S the device management control file reading unit loads the control file for device management stored in step S in . Then in step S the device management control file reading unit parses contents of the control file for device management illustrated in . In step S the device management control unit causes the display unit to display the device management screen according to the contents of the parsed data. Then in step S the device management control unit terminates the processing routine illustrated in .

The control file for device management illustrated in includes in addition to the above described element and the element that are information required in installation information required to constitute the device management screen .

The device management screen includes an upper field in which a device icon a device name and manufacturer information are displayed. The data of the device icon is stored as apart of storage data in the device management control file storage unit although not illustrated. Further the displayed device name is the name of the device selected from the Devices and Printers folder . The displayed manufacturer information is a character string designated in the element .

The device management screen includes a lower field in which links to various functions relevant to the device are displayed. More specifically a printer queue button a print setting button an ink remaining amount button a device status button and an application A launch button are displayed. An element indicating a description illustrated in includes five elements denoted by each describing a button and its function.

First the first element is described in detail. An element indicating a description Open Printer Queue includes a character string Open Printer Queue to be displayed on the printer queue button . An element indicating a description open Printer Queue includes a code open Printer Queue that represents a function program for displaying a printer queue folder. Although not illustrated in the drawings the printer queue folder has a function for displaying a state of a print job.

Therefore in step S the device management control file reading unit parses the element and the display unit displays the character string described in the element on the printer queue button illustrated in . If the printer queue button is pressed the function described in the element is executed and as a result the printer queue folder is displayed.

Next the second element is described in detail. An element indicating a description Printing Preferences includes a character string Printing Preferences to be displayed on the print setting button . An element indicating a description printing Preferences includes a code printing Preferences that represents a function program for displaying a print setting dialog. Although not illustrated the print setting dialog is a print setting screen that can be provided by the UI module of the printer driver .

Therefore in step S the device management control file reading unit parses the element and the display unit displays the character string described in the element on or near the print setting button illustrated in . If the print setting button is pressed the function described in the element is executed and as a result the print setting dialog is displayed. Descriptions for the third and fourth elements are omitted because operations to be performed for the third and fourth elements are substantially similar to the operations for the above described first and second elements.

Next the fifth element is described in detail. An element indicating a description Launch Application A includes a character string Launch Application A to be displayed on the application A launch button . An element indicating a description ProgramFiles ABC Application A.exe devmng devname includes a code ProgramFiles ABC Application A.exe devmng devname that represents a function for launching a screen for the application A illustrated in .

Therefore in step S the device management control file reading unit parses the element and the display unit displays the character string described in the element on or near the application A launch button illustrated in . If the application A launch button is pressed the function described in the element is executed and as a result the screen for the application A illustrated in is displayed. The application A corresponds to the print application illustrated in .

If a user presses the application A launch button on the device management screen in step S the device management control unit provided in the device management illustrated in executes the contents of the element illustrated in via the link execution unit and starts the application A launch processing. Next in step S the application control unit sends the contents described in the element to the launching source determination unit .

According to the example illustrated in the element includes a description devmng that indicates a launching from the device management screen and a description devname that indicates a device name. When the print application is launched the link execution unit replaces the description devname with the device name managed by the Devices and Printers folder illustrated in . In the present exemplary embodiment the device is selected when the device management screen is launched. Therefore in step S the OS acquires a device name icon name ABC Kmmn having been set as an icon name illustrated in and sends the acquired information to the launching source determination unit .

Next in step S the launching source determination unit determines whether the launching source is the device management screen based on an argument in launch processing. In the present exemplary embodiment the element includes the description devmng and the print application is already launched. Therefore in step S the launching source determination unit determines that the launching source is the device management screen. For example in a case where the print application is launched by another source other than the device management screen the description devmng is not designated as an argument. Therefore in step S the launching source determination unit determines that the launching source is not the device management screen.

If it is determined that the launching source is the device management screen YES in step S then in step S the application control unit acquires system default device information via the application DDI interface . The system default device is a device to which the default mark is attached in the Devices and Printers folder illustrated in . In the present exemplary embodiment the device XYZ Defg is set as a default device. Therefore in step S the application control unit acquires a device name XYZ Defg. 

Next in step S the application control unit compares the device name of the launching source acquired in step S with the device name acquired in step S. In step S based on a comparison result of step S the application control unit determines whether the device name associated with the device management screen of the launching source is the system default device. If it is determined that the device name associated with the device management screen of the launching source is the system default device YES in step S the processing proceeds to step S.

If it is determined that the device name associated with the device management screen of the launching source is not the system default device NO in step S then in step S the application control unit acquires information indicating a present status of the device of the launching source via the status acquisition unit and determines whether the launching source device is in a usable state.

In the Devices and Printers folder the device is unusable because a printer icon corresponding to the device is indicated by a dotted line and the device is usable because a printer icon corresponding to the device is indicated by a solid line.

In the present exemplary embodiment the launching source device is the device . Therefore in step S the application control unit determines that the launching source device is usable. Then the processing proceeds to step S. On the other hand if it is determined that the launching source device is unusable NO in step S the processing proceeds to step S.

In step S the application control unit sets the device of the launching source as the default device of the print application via the default device setting unit . Then in step S the application control unit terminates the processing routine illustrated in . The information indicating the default device of the print application is stored in a memory area of the RAM managed by the print application .

If it is determined that the launching source is not the device management screen NO in step S the processing proceeds to step S. In step S the application control unit sets the system default device acquired via the application DDI interface as the default device of the print application via the default device setting unit . The information indicating the default device of the print application is stored in a memory area of the RAM managed by the print application . Subsequently in step S the application control unit terminates the processing routine illustrated in .

When the above described launch processing for the print application is terminated the screen for the application A is displayed as illustrated in .

If a user selects a file menu on the print application illustrated in a print menu is displayed as illustrated in . In this state if the user further selects the print menu of the file menu then in step S the application control unit starts print processing of the flowchart illustrated in .

First in step S the application control unit reads information indicating the default device which was set by the default device setting unit in the launch processing and stored in the RAM .

Next in step S the application control unit brings the default device acquired in the S into a default selection state via the print control unit and displays a print dialog . The print dialog includes a device list a print button and a cancel button that are displayed at predetermined positions in the dialog .

More specifically the device and the device are displayed in the device list as devices currently registered in the Devices and Printers folder . In the print dialog the device icon ABC Kmmn is surrounded by a solid line and therefore the device is in the default selection state. The device is associated with the device management screen of the launching source of the print application .

In step S the print control unit receives a notice when a user has pressed any button on the print dialog . Then in step S it is determined whether the print button is pressed. If it is determined that the print button is pressed YES in step S then in step S the print control unit causes the device selected from the device list to execute print processing. Then the processing proceeds to step S. In step S the application control unit closes the print dialog . And in step S the application control unit terminates the processing routine illustrated in .

On the other hand if it is determined that the print button is not pressed NO in step S i.e. when the cancel button is pressed the application control unit skips the above described processing of step S and terminates the processing routine illustrated in after executing the processing of step S.

Through the above described processing the launching source device is set as a default device in a case where the application is launched from the device management screen. Therefore it is unnecessary to repeat the processing for selecting a device. As a result the present exemplary embodiment can improve user operability.

Another exemplary embodiment of the present invention is described below. According to the above described exemplary embodiment the default device control is performed by the print application . The following exemplary embodiment is different from the above described exemplary embodiment in that the default device control is performed by the device management and the application DDI interface .

The device management includes a display unit a device management control unit a link execution unit a device management control file reading unit a device management control file storage unit a launched application management unit and a launched application information storage unit . The device management control file storage unit stores the control file for device management which was stored in step S of the flowchart illustrated in .

The print application includes an application control unit a default device setting unit a print control unit and a default device acquisition unit .

A computer program relating to the flowchart illustrated in is usually stored in the HDD and can be executed by the CPU when the program is loaded into the RAM from the HDD .

If a user presses the application A launch button on the device management screen then in step S the device management illustrated in starts device management link launch processing. In step S the device management control unit of the device management acquires information relating to the element described in the control file for device management via the device management control file reading unit .

In step S the device management control unit launches the print application via the link execution unit according to the information of the element acquired in step S. An example of the processing for launching the print application according to the present exemplary embodiment is described below in more detail with reference to a flowchart illustrated in .

If the print application is launched then in step S the device management control unit acquires a process ID of the application launched in step S via the launched application management unit . Instep S the launched application management unit stores the process ID acquired in step S and the device name associated with the device management screen of the launching source in the launched application information storage unit .

In the present exemplary embodiment the launched application information storage unit stores the data in a registry of the OS. However if the application DDI interface is readable the storage destination of the launched application information storage unit can be the RAM or the HDD . The following is example data of the launched application information in which a process ID 2301 and a device name 2302 are stored as information relating to the launched application.

Next in step S the launched application management unit acquires state of process information with respect to the print application . In step S the launched application management unit determines whether the print application is completed. If it is determined that the print application is completed YES in step S then in step S the launched application management unit discards the launched application information stored in step S.

Subsequently in step S the device management control unit terminates the processing routine illustrated in . On the other hand if it is determined that the print application is not completed NO in step S the processing returns to step S to repeat the above described processing of step S and step S.

When the print application is launched in step S then in step S the application control unit starts launch processing illustrated in . In step S the application control unit executes system default device information acquisition processing see via the default device acquisition unit . The application DDI interface executes the processing illustrated in .

In step S the application control unit sets the system default device acquired in step S as a default device of the print application via the default device setting unit . Then in step S the application control unit terminates the processing routine illustrated in . The application default device information is stored in a memory area of the RAM that can be managed by the print application .

When the above described launch processing for the print application is completed the screen for the application A illustrated in is displayed.

If in step S the default device acquisition unit calls a default device acquisition API that is opened by the application DDI interface then in step S the application DDI interface starts the system default device acquisition processing illustrated in .

Next in step S the application DDI interface acquires process information of the print application that is a calling source of the default device acquisition processing. In the present exemplary embodiment the application DDI interface acquires 01234567 as process ID information of the print application . In step S the application DDI interface determines whether any launched application information is present in the registry.

If it is determined that the launched application information is present YES in step S then in step S the application DDI interface acquires the launched application information from the launched application information storage unit . If the launched application information is present in the registry YES instep S the application DDI interface can determine that the print application was launched from the device management screen .

According to the example illustrated in the element includes a description devmng indicating that the print application was launched from the device management screen . In the present exemplary embodiment no specific description is required because the above described determination is performed based on the launched application information.

Next in step S the application DDI interface acquires a device name that is associated with the device management screen of the source that launched the print application based on the launched application information acquired in step S. In the present exemplary embodiment the application DDI interface acquires the name ABC Kmmn stored in the device name 2302.

In step S the application DDI interface returns the device name ABC Kmmn acquired in step S as default device information to the default device acquisition unit i.e. the calling source of the print application . Then in step S the application DDI interface terminates the processing routine illustrated in . On the other hand if it is determined that the launched application information is not present in the registry NO in step S then in step S the application DDI interface returns system default device information to the default device acquisition unit i.e. the calling source of the print application .

Then in step S the application DDI interface terminates the processing routine illustrated in . In the present exemplary embodiment the application DDI interface returns the name XYZ Defg of the device as system default device information because the device is set as a default device in the Devices and Printers folder illustrated in .

If the file menu is selected on the print application the print menu is displayed as illustrated in . If the print menu is selected from the file menu illustrated in the application control unit executes the print processing illustrated in . The print processing to be performed in the present exemplary embodiment is substantially the same as that of the first exemplary embodiment.

Through the above described processing the device associated with the device management screen is set and selected as a default device in a case where an arbitrary application is launched from the device management screen. Therefore it is unnecessary to repeat the processing for selecting a device. As a result the present exemplary embodiment can improve user operability.

Further another exemplary embodiment is described below. According to the above described exemplary embodiments when the application A launch button is pressed on the device management screen the apparatus launches the application A while setting a device name so as to improve user operability. However as an exemplary embodiment that is not related to the above described application launch processing an entry function of a configuration module of the printer driver can be used to launch at least a part of the driver.

In the third element illustrated in an element indicating a description Show Ink Level includes a character string Show Ink Level to be displayed on the ink remaining amount button . An element indicating a description includes a code rundll32 StatusMonitor.dll FunctionEntry DeviceFriendlyName 1 100 that is set to execute a function for displaying an ink remaining amount of the status monitor .

In the fourth element illustrated in an element indicating a description Show Device Status includes a character string Show Device Status to be displayed on the device status button . An element indicating a description includes a code rundll32 StatusMonitor.dll FunctionEntry DeviceFriendlyName 2 100 that is set to execute a function for displaying a device status of the status monitor .

In this case StatusMonitor.dll is a module of the status monitor which is constituted by Dynamic Link Library of Windows OS and can be shared among a plurality of devices. More specifically StatusMonitor.dll is the module that can display state information e.g. ink remaining amount warning and error not only for the MFP but also for other devices.

For example an ink cartridge of four colors e.g. cyan magenta yellow and black is mounted on the MFP . In this case the status monitor displays an ink remaining amount for each of the four color inks. On the other hand an ink cartridge of six colors e.g. cyan magenta yellow black photo cyan and photo magenta may be mounted on another MFP. In this case the status monitor displays an ink remaining amount for each of the six color inks.

In this case to enable the status monitor to correctly display the state information e.g. ink remaining amount warning and error according to the type of each device it is necessary to identify the device using an appropriate method and perform an appropriate control for the identified device as described below in detail with reference to .

FunctionEntry is a function that the status monitor can export and has the following three arguments.

In a warning mark displayed on top of the remaining amount bar indicates that the corresponding color ink is in a warning level. If the warning mark is added to the remaining amount bar of the magenta ink the magenta ink is running low. The same warning mark is displayed above or near any other remaining amount bar if the corresponding color ink is in a warning level. Although not illustrated in an error mark can be also displayed when the ink remaining amount becomes zero. If an OK button is pressed the ink remaining amount dialog is closed.

If a user presses the ink remaining amount button or the device status button displayed on the device management screen in step S the device management starts executing ink remaining amount device status display processing illustrated in . Next in step S the device management control unit determines whether the ink remaining amount button is pressed.

If it is determined that the ink remaining amount button is pressed YES in step S then in step S the device management control unit acquires the element indicating a description from the control file for device management via the device management control file reading unit . Next in step S the device management control unit loads a code module StatusMonitor.dll of the status monitor via the link execution unit and executes export function FunctionEntry.

On the other hand if it is determined that the ink remaining amount button is not pressed NO in step S then in step S the device management control unit determines whether the device status button is pressed. If it is determined that the device status button is pressed YES in step S then in step S the device management control unit acquires the element indicating a description from the control file for device management via the device management control file reading unit .

Next in step S the device management control unit loads the module StatusMonitor.dll of the status monitor via the link execution unit and executes the export function FunctionEntry. In step S the device management control unit executes the program according to the first argument the second argument and the third argument in the export function FunctionEntry in the module StatusMonitor.dll of the status monitor . DeviceFriendlyName is set in the argument DeviceName that designates a device name i.e. the first argument .

Therefore the OS that detected the above described character string replaces the character string DeviceFriendlyName with a character string ABC Kmmn that indicates a device name friendly name of the MFP and sends the replaced name information to the application. The application determines a printer name to be displayed based on the received information.

In step S the status monitor determines whether the argument ID designating the function i.e. the second argument is 1. If it is determined that the ID is equal to 1 YES instep S then in step S the status monitor displays the ink remaining amount dialog illustrated in . After the processing of step S for displaying the ink remaining amount dialog is completed then in step S the status monitor terminates the ink remaining amount device status display processing routine illustrated in .

If it is determined that the argument ID designating the function i.e. the second argument is not 1 NO in step S then in step S the status monitor determines whether the ID is equal to 2. If it is determined that the ID is equal to 2 YES in step S then in step S the status monitor displays the device status dialog illustrated in . Then in step S the status monitor terminates the ink remaining amount device status display processing routine illustrated in .

If it is determined that the argument ID designating the function i.e. the second argument is not equal to 2 NO in step S then in step S the status monitor displays an error message designated function is unexecutable. Subsequently in step S the status monitor terminates the ink remaining amount device status display processing routine illustrated in .

In normal cases the status monitor does not display the error message. However if the OS malfunctions due to some reasons erroneous information may be designated as the argument ID designating the function i.e. the second argument . In such a case if the export function FunctionEntry is executed the status monitor displays the above described error message. If it is determined that the device status button is not pressed NO in step S the processing returns to step S to repeat the above described processing for confirming whether the ink remaining amount button or the device status button is pressed.

In the drawing the argument Type representing the launching source i.e. the third argument is not referred to. However it is useful to switch the dialog to be displayed according to the Type. For example it may be desirable to differentiate the contents of the ink remaining amount dialog and the device status dialog for various cases for example in a case where the launch source is the device management in a case where the launch source is the application A and in a case where the launch source is another application. The user operability can be improved by referring to the third argument and performing a control for switching the dialog to be displayed according to the third argument.

As described above in executing the function for displaying the ink remaining amount dialog and the device status dialog which is incorporated in the status monitor i.e. a part of the configuration module of the printer driver capable of displaying the state information e.g. ink remaining amount warning and error of a plurality of devices the status monitor can cause a designated device to execute each function by designating and executing the device name . Therefore the ink remaining amount and the device status can be correctly displayed according to the type of each device. As a result a peripheral apparatus control system excellent in operability can be realized.

The above described final exemplary embodiment intends to correctly display an ink remaining amount and a device status for each target designated device. However the present invention is not limited to the above described embodiment. The present invention can be applied to an arbitrary function for example to accurately execute a function of a general driver for a target designated device.

An exemplary embodiment of the present exemplary embodiment is described below. The PC is an example of an information processing apparatus that can communicate with a plurality of peripheral apparatus. Further the device management illustrated in sets the printer i.e. an example of the predetermined peripheral apparatus as a default control target peripheral apparatus of the PC . The default control target peripheral apparatus is a peripheral apparatus that is initially selected as a printer scanner frequently used by the operating system or an ordinary printer scanner .

The display unit causes the LCD to display the device management screen see that corresponds to the MFP an example of another peripheral apparatus other than the printer .

In response to an instruction entered via the device management screen corresponding to the MFP the device management launches and controls an application that is associated with the device management screen.

In synchronization with the launching of the application by the device management identification information e.g. printer friendly name of the peripheral apparatus that corresponds to the device management screen is input to the application. Therefore the MFP can be selected as a control target peripheral apparatus other than the printer . The OS can acquire the printer friendly name according to the procedure described in .

In response to an instruction entered via an instruction unit see in that instructs launching an application on the device management screen identification information e.g. printer friendly name of a peripheral apparatus which is described in association with the application in a control file for device management i.e. an example of setting data of the device management screen can be input to the application when the application is launched.

The application may further include the status acquisition unit that acquires status information of the MFP . Further if the status acquisition unit acquires information indicating that the peripheral apparatus is unusable error paper jam power source etc. the device management does not select the MFP and select the printer that was preliminarily set as a system default device.

The device management may determine whether the application launching source is the device management screen. In this case if the device management determines that the launching source is the device management screen the above described processing for selecting the MFP is performed. If the device management determines that the launching source is not the device management screen the printer i.e. the system default device can be set as a control target peripheral apparatus.

In a case where an action for launching an application on a device management screen is made and execution of the action is instructed to enable the application to select an appropriate printer the device management of the PC sets setting data i.e. data for customizing the device management screen describing identification information e.g. printer friendly name of a peripheral apparatus to be input to the application in a predetermined area of the operating system. The peripheral apparatus includes at least part or all of MFP printer scanner copying machine and digital camera.

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU or MPU that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiment s and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiment s . For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. computer readable medium .

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2009 158939 filed Jul. 3 2009 which is hereby incorporated by reference herein in its entirety.

