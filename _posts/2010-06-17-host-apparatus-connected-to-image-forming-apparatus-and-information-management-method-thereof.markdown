---

title: Host apparatus connected to image forming apparatus and information management method thereof
abstract: An information management method of a host apparatus which is connected to at least one image forming apparatus includes executing an integrated administration program which is installed in the host apparatus and integrally manages at least one application, receiving device information of at least one image forming apparatus, storing the received device information of the image forming apparatus, executing one of applications which are managed by the integrated administration program, loading the stored device information corresponding to the executed application; and performing a function of the application by using the loaded device information. With this, the method efficiently uses a storage space and improve user's convenience.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09128654&OS=09128654&RS=09128654
owner: SAMSUNG ELECTRONICS CO., LTD.
number: 09128654
owner_city: Suwon-Si
owner_country: KR
publication_date: 20100617
---
This application claims priority under 35 U.S.C. 119 a from Korean Patent Application No. 10 2009 0094001 filed on Oct. 1 2009 in the Korean Intellectual Property Office the disclosure of which is incorporated herein by reference in its entirety.

Apparatuses and methods consistent with the present general inventive concept relate to a host apparatus connected to an image forming apparatus and an information management method thereof and more particularly to a host apparatus and an information management method thereof which stores and manages device information and user information of an image forming apparatus by using an integrated application program integrally managing at least one application.

An image forming apparatus forms an image on a print paper. The image forming apparatus may include a printer a photocopier a facsimile a multi function device which has at least two functions etc.

Recently demand for an image forming apparatus as an office automation device performing not only a document print function but also a scanning function and faxing function has increased. Accordingly the image forming apparatus has extended its original functions to perform various functions with high performance.

To more efficiently manage an image forming apparatus connected in a network a user or administrator uses a host apparatus such as a personal computer PC to set and manage devices i.e. image forming apparatus.

Thus various applications are installed in the host apparatus to use various functions of the image forming apparatus enabling a user to use the functions of the image forming apparatus by executing the applications.

The host apparatus manages and stores information corresponding to the image forming apparatus device information and information corresponding to a user who uses the image forming apparatus user information for each application.

In case of sharing information which can be shared by a plurality of applications a conventional host apparatus which stores information per application stores the sharing information in a predetermined area corresponding to an application. Then the sharing information is copied and stored in another storage area by another application.

Then the same sharing information is stored in several storage areas of each application. That is more various the types of applications are the more storage space is needed to store the same information.

Accordingly it is a feature of the present general inventive concept to provide a host apparatus connected to an image forming apparatus and an information management method thereof which stores device information and user information by an integrated application program to integrally manage a plurality of applications and which loads and uses stored information with an application programming interface API function when executing each application to thereby efficiently use storage space and enhance user s convenience.

Additional features and or utilities of the present general inventive concept will be set forth in part in the description which follows and in part will be obvious from the description or may be learned by practice of the present general inventive concept.

Features and or utilizes of the present general inventive concept may be realized by an information management method of a host apparatus which is connected to at least one image forming apparatus the method including executing an integrated administration program which is installed in the host apparatus and integrally manages at least one application receiving device information of at least one image forming apparatus storing the received device information of the image forming apparatus executing one of applications which are managed by the integrated administration program loading the stored device information corresponding to the executed application and performing a function of the application by using the loaded device information.

The method may further include setting the device information and the user information wherein the loading the information may include loading at least one of the set device information and the user information.

The loading the information may include calling an application programming interface API and loading at least one of the device information and the user information by using the called API.

The device information may include status information on at least one image forming apparatus and setting information on a function of at least one image forming apparatus.

The user information may include at least one of user ID and password information alert settings information and job accounting information.

The application may include a printer driver corresponding to a predetermined image forming apparatus.

Features and or utilizes of the present general inventive concept may also be realized by a host apparatus which is connected to a plurality of image forming apparatuses and has an integrated administration program installed therein the host apparatus including a user interface unit which executes the integrated administration program and an application managed by the integrated administration program a communication unit which receives device information of at least one image forming apparatus a storage unit which stores therein the received device information of the image forming apparatus and a controller which controls the communication unit to receive the device information upon an execution of the integrated administration program loads the device information from the storage unit corresponding to the executed application and performs a function of the application by using the loaded device information.

The user interface unit may set the device information and the user information and the controller may load at least one of the set device information and the user information from the storage unit.

The controller may call an application programming interface API and load at least one of the device information and the user information by using the called API.

The device information may include status information on at least one image forming apparatus and setting information on a function of at least one image forming apparatus.

The user information may include at least one of user ID and password information alert settings information and job accounting information.

The application may include a printer driver corresponding to a predetermined image forming apparatus.

Features and or utilities of the present general inventive concept may also be realized by a method of storing image forming apparatus data including executing an integrated administration program on a host device to control a plurality of functions of at least one image forming apparatus receiving image forming apparatus data from the at least one image forming apparatus in response to a request from the integrated administration program of the host apparatus and storing the image forming apparatus data in the host device.

The method may include executing at least one function of the plurality of functions of the at least one image forming apparatus and retrieving the stored image forming apparatus data to execute the at least one function.

The method may include displaying the stored image forming apparatus data on a display of the host device.

The method may include executing at least one function of the plurality of functions of the at least one image forming apparatus and retrieving the stored image forming apparatus data and the stored user data to execute the at least one function.

The method may include performing a plurality of functions of the at least one image forming apparatus and retrieving the stored image forming apparatus data and the stored user data from the host device to execute each function.

The integrated administration program may retrieve the stored image forming apparatus data and user data from a single location within the host device to execute each function.

The integrated administration program may store the image forming apparatus data at a single location in memory of the host device so that each of the plurality of functions of the image forming apparatus accesses the image forming apparatus data from the same single location in memory.

The at least one image forming apparatus may include a plurality of image forming apparatuses receiving image forming apparatus data from the at least one image forming apparatus in response to a request from the integrated administration program of the host apparatus may include receiving image forming apparatus data from each of the plurality of image forming apparatuses and storing the image forming apparatus data in the host device may include storing the image forming apparatus data corresponding to each of the image forming apparatuses in the host device.

Features and or utilities of the present general inventive concept may also be realized by a host device to control at least one image forming apparatus including a data storage device to store user data and image forming apparatus data a communication unit to transmit data to and receive data from at least one image forming apparatus connected to the host device and a first controller to control operation of the communication unit to request image forming apparatus data from the at least one image forming apparatus and to transmit image forming apparatus data to the data storage device.

The data storage device may store an integrated administration program and the first controller may use the integrated administration program to retrieve the user data and image forming apparatus data from the data storage device to perform a plurality of functions of the connected at least one image forming apparatus.

The host device may include a display device to display a graphical user interface corresponding to the integrated administration program.

The controller may perform the plurality of functions of the at least one image forming apparatus in response to a user interaction with the graphical user interface displayed on the display device. The host device may include a user interface unit to receive a user input corresponding to the user data.

The data storage device may store the user data and the image forming apparatus data at a single location in memory so that each of the plurality of functions of the at least one image forming apparatus access the user data and the image forming apparatus data from the same single location in memory.

Features and or utilities of the present general inventive concept may also be realized by an image forming system including at least one image forming apparatus and a host device connected to the at least one image forming apparatus to control an image forming operation of the image forming apparatus.

The at least one image forming apparatus may include a plurality of image forming apparatuses and the data storage device may store image forming apparatus data corresponding to each of the plurality of image forming apparatuses.

The image forming system may include a server to store image forming apparatus data from the at least one image forming apparatus and to transmit the image forming apparatus data to the host device in response to a data request.

Features and or utilities of the present general inventive concept may also be realized by a computer readable medium having stored thereon a computer program to perform a method of storing image forming apparatus data on a host device the method including executing an integrated administration program on the host device to control a plurality of functions of at least one image forming apparatus receiving image forming apparatus data from the at least one image forming apparatus in response to a request from the integrated administration program of the host apparatus and storing the image forming apparatus data in the host device.

Reference will now be made in detail to the embodiments of the present general inventive concept examples of which are illustrated in the accompanying drawings wherein like reference numerals refer to the like elements throughout. The embodiments are described below in order to explain the present general inventive concept by referring to the figures.

As shown therein the image forming system according to the present general inventive concept may include the host apparatus at least one of image forming apparatuses . . . and and an image forming apparatus server . The image forming apparatus server may be provided separately as illustrated in it may be included in the host apparatus or it may be omitted altogether.

According to an exemplary embodiment of the present general inventive concept if the image forming apparatus server is omitted the host apparatus is connected to at least one of the image forming apparatuses . . . and to receive device information from the image forming apparatus and to transmit image data to the image forming apparatus.

The host apparatus may include a personal computer PC and the image forming apparatuses . . . and may include a printer or a multi function device connected in a network by a local connection in parallel or by UNC and including an image forming unit to perform a print operation according to a print command from the host apparatus .

The print operation may include a print operation to copy a scanned document a print operation to print received fax data and a print operation to print data received from an external device via the host apparatus such as from a server. The print operation may also be to print data stored in a data storage device located inside the host device or an image forming apparatus such as a hard disk drive or outside the host device or an image forming apparatus such as a USB memory stick.

The image forming apparatuses . . . and according to the present general inventive concept may be connected to the host apparatus by a local connection or shared as a network image forming apparatus having their own IP addresses assigned in a network.

If the image forming apparatuses . . . and are connected by a local connection to the host apparatus the host apparatus may include the image forming apparatus server .

If the image forming apparatuses . . . and are network image forming apparatuses the image forming apparatus server may be provided separately to manage at least one of the image forming apparatuses . . . and . The host apparatus may receive various information on at least one of the image forming apparatuses . . . and from the image forming apparatus server .

According to an exemplary embodiment of the present general inventive concept a device integrated administration program or an integrated desktop solution IDS may be installed in the host apparatus to integrally manage at least one of the image forming apparatuses . . . and . The IDS may integrally manage an integrated printer driver or universal printer driver depending on the type of the image forming apparatuses . . . and and various applications to enhance functions of the image forming apparatuses . . . and 

A user may execute at least one application including a printer driver but not limited thereto by using the integrated administration program may input various setting values for the image forming apparatuses . . . and through the executed application and may control the image forming apparatuses . . . and to perform imaging functions.

The integrated administration program which is installed in the host apparatus according to the exemplary embodiment of the present general inventive concept integrally manages at least one application to enhance functions of the image forming apparatuses . . . and . To support the foregoing function the host apparatus stores therein device information of the image forming apparatuses . . . and and user information on a user using the integrated administration program. A user may include an administrator for example or a user having permission on the host apparatus to change settings of the host apparatus .

As illustrated in the host apparatus includes a first user interface unit a first display unit a first storage unit a first communication unit a first controller and an image processor .

The first user interface unit receives various commands from a user. The first user interface may include a keyboard mouse touch pad or other device to receive input from a user.

A user may use the first user interface unit to enter a command to execute the integrated administration program or integrated desktop solution IDS to integrally manage the device. Specifically the user may use the single IDS to operate the plurality of image forming apparatuses . . . and to select one of the image forming apparatuses . . . and displayed in an image forming apparatus list of the management screen displayed on the first display unit to be described later corresponding to the execution of the IDS or to select one of applications managed by the IDS.

A user may log into the IDS through the first user interface unit . For example a user may log in an administrator mode which enables the user to setup and change of any most or all of the settings associated with the image forming apparatuses . . . and . The user may input a user ID and password such as an administrator ID and password into the first user interface unit and the first controller may authenticate the user. The integrated administration program or an integrated desktop solution IDS may be configured to only be accessed or have settings changed by an administrator. Alternatively various settings of the IDS may be changeable by users having less access than an administrator.

In addition to an input device such as a keyboard or mouse the first user interface unit may also include a graphic user interface GUI which may be generated by executing a driver or an additional application. The GUI may be displayed on the first display unit . The GUI may include an icon a button or a text input window to be selected by a user.

If the first user interface unit includes a GUI the host apparatus executes the IDS and receives various commands from a user corresponding to the management screen displayed on the first display unit .

The first display unit may display the management screen of at least one of the image forming apparatuses . . . and which is connected to the host apparatus . The first display unit may be any type of display unit including a CRT monitor an LED monitor a TV a thin film transistor liquid crystal display TFT LCD and a driver not shown to drive the TFT LCD or any other display device.

If a user executes the integrated administration program or an integrated desktop solution IDS to configure or operate an image forming apparatuses . . . and the first display unit may display thereon the management screen of the IDS corresponding to the selected image forming apparatus as illustrated in .

The management screen may include a device list area to display a list of the image forming apparatuses . . . and an inherent function area to display an icon corresponding to at least one application supported by the host apparatus through the IDS a common function area to display an icon corresponding to at least one application supported by the host apparatus through the IDS regardless of a compatibility with the image forming apparatuses . . . and and a contents area to display status information of a predetermined image forming apparatus.

Information which is displayed in the inherent function area and the contents area includes information corresponding to an image forming apparatus selected from the device list area .

The device list area displays a list of the image forming apparatuses . . . and connected to the host apparatus . The first controller may determine the image forming apparatuses . . . and that are connected in a network by using a printer driver installed in the host apparatus or the first communication unit for example.

The first controller may include a processor memory and supporting logic to control operations of the first user interface unit first display unit first storage unit or data storage unit first communication unit image processor and any other functional units of the host device . In addition one or more of the functional units of the host device may include dedicated processors memory and logic circuits to control respective functional operations. For example the image processor may include a processor and or memory to perform image processing and to transmit and receive image data to and from the first controller .

The image processor may generate print data in a predetermined print language according to a print command through the first user interface unit . The generated print data are transmitted to one of the image forming apparatuses . . . and through the first communication unit . The image forming apparatuses . . . and receive the print data from the host apparatus and perform a print operation.

The first communication unit may include one or more data ports to communicate with external devices. The data ports may be wired ports such as USB Ethernet telephone or other wired ports or may include wireless ports such as a wireless network transceiver to transmit and or receive data via an antenna.

Referring to the device list area displayed on the first display unit may classify the image forming apparatuses . . . and into active printers and inactive printers depending on the current status of the respective image forming apparatuses detected by the first controller . That is an image forming apparatus that has had a corresponding driver or software installed in the host apparatus and that is not available may be listed up as inactive. 

A user may select one of the image forming apparatuses displayed on the device list area via the first user interface unit . The management screen displayed on the first display unit may provide information about the selected image forming apparatus in the inherent function area and the contents area .

The inherent function area may display a model name of the image forming apparatus selected from the device list area and an icon corresponding to one or more applications to control functions of the selected image forming apparatus. For example in the inherent function area displays icons to perform a print operation a conversion to .pdf and a scan to email function.

The inherent function area may display the icon of each application as enabled or disabled depending on whether the host device is compatible with the particular application to control the selected image forming apparatus or whether the selected image forming apparatus is capable of performing the function associated with the particular icon . For example if the selected image forming apparatus is unable to scan a document to an email address the scan to email icon may be partially covered by a symbol representing disabled. 

The common function area may include an icon corresponding to at least one application managed by the host apparatus through the integrated administration program or integrated desktop solution IDS . The common function area may display an icon which is enabled or disabled depending on support of the host apparatus or depending upon whether the application has been installed in the host apparatus .

The first controller may determine whether applications corresponding to the icons and of the inherent function area or the common function area are installed in the host device by using registry information stored in the first storage unit . The first storage unit is a data storage device and may include any type of data storage device including non volatile memory volatile or dynamic memory a hard disk or any combination of memory devices.

The contents area may include device information of the selected image forming apparatus and information corresponding to the user that is presently logged in to the IDS. The device information may include status information of the image forming apparatus and setting information set by a user corresponding to settings of the image forming apparatus.

The contents area may also display a status message indicating the current status of the selected image forming apparatus supplies information such as information regarding toner type and quantity paper and tray information and network status information as an example of the status information of the selected image forming apparatus.

A user may select one of menu items provided in an upper part of the management screen and execute an application to confirm or set device information and user information of a selected image forming apparatus .

The menu item may include icons corresponding to Home Device Settings PC FAX Settings Alert Settings Advanced Settings etc.

If a user selects the Device Settings icon the contents area may display settings of the device information of the image forming apparatus to confirm and change the settings. If a user selects the Alert Settings icon the contents area may display an error status of the selected image forming apparatus . If a user selects the Advanced Settings icon the contents area may display information such as Job Accounting Alert History etc.

The device information and the user information which are displayed in the contents area may be separately stored in different areas of the first storage unit .

The device information storage area stores status information and setting information of the image forming apparatuses . . . and . The device information may be inherent information of an image forming apparatus or information that corresponds particularly to one image forming apparatus and not necessarily to another image forming apparatus. For example the device information may include current toner level information and print setting information of a predetermined image forming apparatus.

The user information storage area may store data that corresponds to a specific user. For example if a user selects the Alert Settings icon of and adjusts the alert settings the user information stored in the user information storage area may include data corresponding to the alert settings. The user information may be organized according to user and may be kept confidential from other users. As illustrated in the user information may include ID and password information on the job accounting and administrator ID and password information . Each of password information is encoded and stored.

The user information may include data which may be applied to one or more of the image forming apparatuses . . . and and information which varies depending on a user. For example the user information may include user s ID and password information job accounting information and preferred image forming apparatus settings such as alert settings. The user information may include authentication information to authenticate a particular user or an administrator.

The first storage unit may also store data including a computer program or data to be utilized by a computer program corresponding to an application managed by the IDS.

If the integrated administration program or integrated desktop solution IDS is executed the first controller controls the first communication unit to receive device information of at least one of the external image forming apparatuses . . . and and stores the received device information in the first storage unit .

If an application which is managed by the IDS is executed such as an application to print a document convert a file to .pdf or scan a document to email the first controller controls the first display unit to display the management screen including the contents area . The controller may display information corresponding to the executed application by retrieving stored device information and stored user information from the device information storage area and the user information storage area respectively of the first storage unit .

The first communication unit may directly receive device information from at least one of connected image forming apparatuses . . . and or the first communication unit may receive status information of the image forming apparatuses from the image forming apparatus server . The device information may be received periodically or may be received when a user executes or refreshes the IDS.

The received device information of the image forming apparatuses . . . and may include a predetermined file e.g. XML including capability information of the image forming apparatuses . . . and 

As illustrated in a file including capability information as received device information of the image forming apparatus may include manufacturing information including a model name and a manufacturer hardware information including color software information including information of each application managed by the IDS and alert information including a preferred alert destination and method of transmitting an alert.

If the software information includes printer settings utility PSU as illustrated in the device settings icon of the management screen of may be enabled. Then a user may select the enabled icon and set change and confirm the device settings of the selected image forming apparatus .

If a user selects the device settings icon a device setting application may be executed and the first controller may retrieve the device information including the device settings from the device information storage area of the first storage unit . The controller may then cause the display unit to display the setting information in the contents area of the management screen .

Likewise if a user executes a printer information displaying application the first controller may retrieve status information e.g. toner information out of the device information stored in the first storage unit and may display the status information in the contents area .

The first communication unit may include a wired wireless communication module which communicates with at least one of the image forming apparatuses . . . and and the image forming apparatus server and is connected to an external device such as the image forming apparatuses . . . and or the image forming apparatus server by a local connection or in a network using a predetermined protocol.

As shown therein a user may select a PC Scan Setting icon from the menu item of the management screen and confirm and input scan setting information as device information. When the user selects the PC Scan Setting icon the first controller controls the first display unit to display a setting screen in the contents area corresponding to the scan setting selected by a user.

The first controller may retrieve status information of a predetermined image forming apparatus stored in the first storage unit and display the retrieved status information for the predetermined image forming apparatus in the contents area .

A user may input device setting information with respect to the scan setting corresponding to the displayed contents area . The input device setting information may be stored in the device information storage area of the first storage unit . The stored device setting information may also be used in scan 2 PC or Twain Scanner Driver applications which require scan setting information.

As illustrated in the user information may be stored in a user s account folder of an operating system OS such as Windows and may be kept confidential from other users. All the user data may be stored in one Users folder as illustrated in or each user data for each user may be stored in a different User folder.

The first controller receives the user information corresponding to each user via the first user interface unit and stores the user information in the user information storage area of the first storage unit as illustrated in .

As illustrated in if a user executes the IDS in operation S the first controller accesses information about a device or an image forming apparatus in operation S. illustrates a process of accessing device information.

As illustrated in the first controller may control the first communication unit to access at least one of the image forming apparatuses . . . and in operation S and may transmit a command or request to obtain device information in operation S. The first controller may receive the requested device information via the first communication unit in operation S and may store the received device information in the first storage unit in operation S. The stored device information may include status information and setting information as illustrated in and may be an XML format for example.

The first controller may compare the device information already stored in the first storage unit with the received device information and may update the information stored in the first storage unit as necessary. The updated device information may be reflected in the management screen of the IDS as illustrated in .

A user may set the user information by using the executed IDS as illustrated in . Although illustrates accessing user information after accessing device information the user information and device information may be obtained in any order.

As illustrated in upon logging into the IDS in operation S the IDS may display a user interface in operation S such as the management screen of . In operation S the user may input user information such as an ID password and preferences in response to the user interface displayed by the IDS. The user may input the information via the first user interface unit for example and the user information may then be stored in the first storage unit in operation S.

When a user requests that an operation corresponding to one of the image forming apparatuses be performed the first controller may retrieve the user information and device information stored in the first storage unit to operate the image forming apparatus in operation S. In addition the controller may control the IDS to request additional information from the user via the first display unit or from the image forming apparatuses via the first communication unit before performing the requested operation of the image forming apparatuses .

As illustrated in a user may input a predetermined user ID and password and input a command to store the user ID and password when the UI displays a log in area to set the user ID and password. The input user information ID and password may be stored in the first storage unit .

The stored user information may include PC fax information alert option information and job accounting information as illustrated in .

The device information and the user information which are stored by the IDS may be loaded and used without copying and storing processes by the sub application program of the IDS. For example a print application a scan to email application and a print to pdf application would not each have to separately copy and store device and user data to perform an operation of an image forming apparatus. Instead each application may communicate with the IDS to retrieve the device and user data previously stored via the IDS in the first storage unit .

As illustrated in the first controller may call an application programming interface API function and may load the device information and the user information through the called API function if one of applications including a printer driver managed by the IDS is executed. The API may be a component of the integrated administration program or integrated desktop solution IDS or the API may be a separate program from the IDS to allow a variety of applications to access the device and user information and stored in the first storage device .

Accordingly a plurality of applications which are managed by the IDS may share the device information and the user information stored in the first storage unit .

As illustrated in if a user executes the IDS the first controller may execute a toner information displaying application or printer information displaying application in operation S to display status information such as toner information in the contents area of the management screen in . The first controller may execute the toner information displaying application corresponding to a user s selection of the Home icon from the menu item for example.

If the toner information displaying application is executed the first controller calls the API function in operation S to confirm color to display the toner information as in . The API function may include GetTonerColorInfo to confirm colors for example.

In operation S the first controller opens the XML file stored in the device information area of the first storage unit by using the called color confirming API and confirms tag of tag refer to in operation S.

The XML file which is stored in the device information area may include the device information received from the image forming apparatuses . . . and and stored or updated when the IDS is executed.

The API function may provide the confirmed color information to the first controller in operation S and the first controller may control the first display unit in operation S to display in the contents area the toner information per color by using the provided color information.

As illustrated in if a job accounting displaying application is executed to confirm the job accounting information for a predetermined user the first controller may generate a user information UI in operation S to confirm the job accounting information and may display the login UI on the first display unit in operation S.

If a user inputs the ID and password corresponding to the displayed login UI in operation S the first controller calls the API function to confirm the job accounting information as in in operation S. The API function may include GetJobAccountingInfo to confirm the job accounting information for example.

In operation S the first controller opens the XML file stored in the user information area of the first storage unit by using the called API function and confirms and loads tag refer to in operation S.

The API function provides the loaded ID and password information to the controller in operation S. The first controller compares the provided ID and password information with those input by a user. If the provided ID and password information is consistent with that input by a user the first controller controls the first display unit to display the job accounting information in the contents area in operation S.

As illustrated in when a user selects the alert settings icon from the menu item of the management screen in the first controller may control the first display unit to display the print alert settings UI .

A user inputs a user setting value corresponding to the setting UI in . The input value is stored in the user information storage area of the first storage unit as the user information.

As illustrated in if a user executes the IDS and implements a print operation for a predetermined image forming apparatus in operation S the first controller may automatically execute the alert program in operation S according to the alert setting value set by a user.

If the alert program is executed the status displaying application is automatically executed. The first controller confirms a location of the status information list in operation S and calls the API function. The API function may include GetStatusListNetworkLocation to confirm the location of the status information list for example.

In operation S first controller may open the XML file stored in the device information area of the first storage unit by using the called API function and may confirm tag of tag refer to in operation S.

The XML file which is stored in the device information area may include device information which is received from the image forming apparatuses . . . and and stored or updated when the IDS is executed.

The API function confirms and provides URL information of the tag to the first controller in operation S. The first controller accesses the URL and downloads the status list by using the provided URL information and determines whether to display the alert in operation S. As illustrated in the first controller controls the first display unit to display the alert message according to the determination result. For example the alert message may include graphic audio visual and text representations or signals of toner or ink levels corresponding to different types of toner and ink.

An application that displays the alert message when toner in a predetermined color is low in an image forming apparatus may initiate a process of downloading a status information list of each device from a URL of the device since the image forming apparatuses have different status information.

Referring again to the image forming apparatuses . . . and include a second storage unit to store print data and device information a second communication unit to communicate with the host apparatus a second controller to control the image forming apparatus as a whole and an image forming unit to perform a print operation based on received print data. The device information which is stored in the second storage unit may include status information of the image forming apparatus and setting information set for a predetermined function by using a user manipulation unit not shown provided in the image forming apparatus .

The second controller controls the second communication unit to transmit the device information of the image forming apparatuses . . . and to the host apparatus or the image forming apparatus server .

As illustrated in if the image forming system includes an image forming apparatus server the image forming apparatus server receives the device information from at least one of the image forming apparatuses . . . and through a third communication unit .

A third controller stores in a third storage unit the device information received from at least one of the image forming apparatuses . . . and 

The host apparatus may access the image forming apparatus server through the first communication unit and receive device information of the image forming apparatus selected from the device list area in .

The host apparatus may transmit a management history of an application managed by the IDS to the image forming apparatus server through the first communication unit . The image forming apparatus server may store the received management history in the third storage unit .

The host apparatus according to the present general inventive concept may store the device information and the user information by the execution of the IDS and load and use the stored information by using the API function upon execution of the application to thereby efficiently use the storage space and improve user s convenience.

In the image forming system with the foregoing configuration an information management process of the host apparatus will be described with reference to .

A user may execute the integrated administration program installed in the host apparatus in operation S. The integrated administration program may include an integrated desktop solution IDS which integrally manages at least one application.

In operation S the host apparatus may receive the device information of at least one of the image forming apparatuses . . . and upon execution of the integrated administration program. The host apparatus may receive the device information from at least one of the image forming apparatuses . . . and or the image forming apparatus server . The received device information may include an XML file including the capability information as in .

The device information received at operation S may be transmitted from the image forming apparatus selected by the execution of the integrated administration program or from at least one of the image forming apparatuses connected to the host apparatus . The received device information may include the manufacturing information including a model name and a manufacturer hardware information including colors and software information including information on each application managed by the integrated administration program as the status information of a predetermined image forming apparatus.

In operation S the first controller stores in the first storage unit the received device information. The first controller may compare the received device information with the device information already stored in the first storage unit and may update the stored device information.

In operation S the host apparatus may set at least one of the device information and the user information by using the executed integrated administration program. The set device information includes information set by a user with respect to the functions of the image forming apparatuses and may include scan setting information as in .

The user information may include the ID and password information for a user to log in the alert settings information to alert an error and job accounting information to count print volume of a user as information set for a predetermined user.

The operation S may include a user login process to set the device information or the user information.

In operation S a user may execute an application managed by the executed integrated administration program.

The first controller may load at least one of the device information and the user information corresponding to the executed application in operation S. The loaded device information or user information includes information needed by the application executed at operation S out of the device information stored at operation S and the device information or user information set at operation S.

At operation S the first controller may load the API function corresponding to the executed application and load the device information and the user information stored in the first storage unit by using the called API function.

In operation S the first controller performs a function of the application executed at operation S by using at least one of the device information and the user information loaded at operation S.

At operation S the first controller may control the first display unit to display at least one of the device information and the user information loaded at operation S to thereby perform a function of the application.

According to the exemplary embodiment of the present general inventive concept the host apparatus stores the device information and the user information by using the integrated administration program to integrally manage the application and loads and uses the stored information by using the API function upon execution of each application to thereby efficiently use the storage space and improve user s convenience.

The present general inventive concept can also be embodied as computer readable codes on a computer readable medium. The computer readable medium can include a computer readable recording medium and a computer readable transmission medium. The computer readable recording medium is any data storage device that can store data as a program which can be thereafter read by a computer system. Examples of the computer readable recording medium include read only memory ROM random access memory RAM CD ROMs DVDs magnetic tapes floppy disks and optical data storage devices. The computer readable recording medium can also be distributed over network coupled computer systems so that the computer readable code is stored and executed in a distributed fashion. The computer readable transmission medium can transmit carrier waves or signals e.g. wired or wireless data transmission through the Internet via a server . Also functional programs codes and code segments to accomplish the present general inventive concept can be easily construed by programmers skilled in the art to which the present general inventive concept pertains.

Although a few exemplary embodiments of the present general inventive concept have been shown and described it will be appreciated by those skilled in the art that changes may be made in these exemplary embodiments without departing from the principles and spirit of the general inventive concept the scope of which is defined in the appended claims and their equivalents.

