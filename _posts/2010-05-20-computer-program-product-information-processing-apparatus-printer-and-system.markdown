---

title: Computer program product, information processing apparatus, printer, and system
abstract: A set of files making up a plug-in that is to be added to a base printer driver is stored all together in a single plug-in storage file. While no plug-in is added, the plug-in storage file is kept empty. A file making up the printer driver and the plug-in storage file are included as printer driver configuration files, and are described in a file list in a driver information file. When the printer driver is copied to a client computer, the files making up the printer driver and the plug-in storage file are transferred, following the descriptions in the file list.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08848217&OS=08848217&RS=08848217
owner: Ricoh Company, Limited
number: 08848217
owner_city: Tokyo
owner_country: JP
publication_date: 20100520
---
The present application claims priority to and incorporates by reference the entire contents of Japanese Patent Application No. 2009 132450 filed in Japan on Jun. 1 2009.

The present invention relates to a computer program product an information processing apparatus a printer and a system for adding a printer operation controlling function to a printer driver.

A system in which a host computer a client computer a printer and the alike are connected to a network such as a local area network LAN has been conventionally known. In such a system the client computer uses the host computer as a print server and can cause the host computer to execute a print over the network.

In such a system a printer driver corresponding to the printer needs to be installed on each of the host computer and the client computer. In a scenario where a number of client computers executing prints using the printer are connected to the network a work of installing the printer driver to each of the client computer requires a high cost.

Therefore a mechanism for allowing the printer driver to be easily installed to the client computer has conventionally been provided. For example in the Windows registered trademark that is an operating system OS developed by Microsoft Corporation in the United States such a mechanism is provided as a function referred to as Point Print .

In the Point Print function when a shared printer on the host computer is selected using an application programming interface API on the client computer the client computer and the host computer exchange information about functions of the selected shared printer information about an OS on the client computer and the like. The host computer then selects a printer driver based on the information obtained by way of the exchange and transfers a set of files that makes up the selected printer driver to the client computer over the network. The client computer copies the set of files making up the printer driver and transferred over the network to a predetermined folder for example registers the same to the OS and installs the same. In this manner the client computer becomes able to cause the shared printer connected over the network to print.

A mechanism called a plug in for allowing an additional function to be attached or removed freely to a base program is widely known. By incorporating plug in software for adding a predetermined function into application software the function not included in the application software by default or a more advanced function becomes available.

Recently the number of examples in which not only in general application software but also a printer driver includes such a plug in mechanism has been increasing. By allowing a printer driver to have the plug in mechanism a printing function for the printer can be added or removed easily without upgrading the printer driver itself.

Let us now consider a scenario in which the plug in mechanism is used in the system in which the host computer the client computer and the printer are connected over the network. In this scenario to utilize the function of the plug in software installed in the host computer on the client computer the same plug in software installed in the host computer needs to be installed on the client computer.

Japanese Patent Application Laid open No. 2005 208895 discloses an installer that manages an addition and a removal of plug in software to printer driver that has been installed on a host computer as well as that manages an addition and a removal of the plug in software to a client computer connected to the host computer over the network.

According to Japanese Patent Application Laid open No. 2005 208895 upon adding plug in software to the printer driver on the host computer the installer makes a copy of the plug in software to be added to a predetermined directory for installing the printer driver on the host computer. At the same time the installer temporarily stops the printing queue on the host computer and restarts the printing service.

The host computer then notifies to each of the client computer that the plug in software has been added and the host computer transfers the files of the added plug in software to each of the client computers.

The installer also operates on the client computer to make a copy of the plug in software files that is to be added and has been transferred over the network to a predetermined directory for installing the printer driver on the client computer.

However in the printer driver having a conventional plug in mechanism it has been difficult to cause the plug in software to be installed automatically.

This point will be explained using the example of the Point Print function. In the Point Print only the files specified in a driver information file inf file as an example illustrated in describing configuration information of the printer driver are downloaded and copied from the host computer to the client computer. In the example illustrated in a list of the files making up the printer driver is described in a file list section in the driver information file .

The driver information file is used when the printer driver is installed and describes therein configuration information of a package of the printer driver that is information such as the names of the files making up the printer driver and an installing directory. In other words as the example in indicates when a printer driver is copied from a host computer to a client computer the host computer refers to the descriptions in the driver information file to select files that are to be transferred to the client computer . The OS manages the configuration information described in the driver information file until the printer driver is uninstalled.

The plug in software extends the functions of the printer driver that is already installed. Therefore the configuration information of the plug in software such as the names of files making up the plug in software is not described in the driver information file that is used when the printer driver is installed.

Even if the printer driver has the plug in mechanism the printer driver cannot change the configuration information managed by the OS. In other words the printer driver cannot change the contents of the driver information file . Therefore the plug in software files that are added after the printer driver has been installed to the host computer are not copied to the client computer by way of the Point Print function provided by the OS.

Therefore as illustrated in the example in even if a printer driver on the host computer has functions thereof extended by way of plug in software the package of the printer driver which is the one before the function is added is downloaded and installed to the client computer following the driver information file .

On the contrary Japanese Patent Application Laid open No. 2005 208895 solves this problem by allowing the installer to manage the files that are not described in a driver information file and added as plug in software. In other words in Japanese Patent Application Laid open No. 2005 208895 when the plug in software is added to the host computer the installer notifies the same to the client computer and transfers the plug in software that is added to the client computer.

However according to Japanese Patent Application Laid open No. 2005 208895 the plug in software file cannot be copied to the client computer by way of the Point Print function provided in the OS by default alone and the installer that is a dedicated module that is independent from the OS needed to be used.

Furthermore because the module that is independent from the OS is used compatibility with the OS is sacrificed and it would be difficult to support a version change of the OS for example.

It is an object of the present invention to at least partially solve the problems in the conventional technology.

According to an aspect of the present invention there is provided a computer program product including a computer usable medium having computer readable program codes embodied in the medium for installing a plug in that adds a function to a printer driver. The program codes when executed causes a computer to execute storing a file that makes up a plug in that is to be newly added to the printer driver in a plug in storage file without changing a file name of the plug in storage file. A file name of a file making up a main part of the printer driver and the file name of the plug in storage file storing therein the plug in adding a function to the main part of the printer driver are described as file names of files making up the printer driver in a printer driver configuration information file in advance. The printer driver configuration information file is referred by an operation system to obtain the file names of the files making up the printer driver upon copying the files making up the printer driver to a different information apparatus and installing the printer driver to the different information apparatus.

The above and other objects features advantages and technical and industrial significance of this invention will be better understood by reading the following detailed description of presently preferred embodiments of the invention when considered in connection with the accompanying drawings.

An embodiment of a printer driver according to the present invention will now be explained in detail with reference to the accompanying drawings. According to the present invention a set of files making up plug in software for adding a function to a base printer driver is stored in a single file referred to as a plug in storage file . When any plug in software is not added thereto the plug in storage file is kept as a dummy for example kept empty. The files making up the base printer driver and the plug in storage file are used as the configuration files of the printer driver and are described in a file list that specifies a driver configuration and is included in the driver information file.

When a printer driver package is copied to the client computer the files making up the base printer driver and the plug in storage file are transferred from the host computer to the client computer following the description in the driver configuration file list. Because the description in the driver configuration file list does not change depending on whether plug in software is added the transferring process executed upon installing the plug in software to the client computer can be performed in the same manner as when only the base printer driver is transferred.

Before explaining an embodiment according to the present invention a system that is applicable to the present invention will be explained. schematically depicts an example of the system configuration that is applicable to the present invention. A host computer a client computer and a printer are connected to a network such as local area network LAN . The host computer has a function of a print server and manages the printer . A printer driver corresponding to the printer is installed in each of the host computer and the client computer to allow the client computer to cause the printer to print. Upon installing the printer driver to the client computer files are downloaded from the host computer in the manner to be described later.

In the host computer a central processing unit CPU a read only memory ROM a random access memory RAM a network interface I F a hard disk HD an input output interface I F a drive and a display control unit are connected to a bus . Each of these units connected to the bus is configured to exchange data via the bus .

The CPU controls overall operations of the host computer following computer programs stored in the ROM or the hard disk in advance and using the RAM as a working memory.

The hard disk stores therein the computer programs for enabling the CPU to operate and various data. Examples of the computer programs stored in the hard disk include an operating system OS that performs basic controls for the operations of the host computer and a printer driver for managing and controlling the printer . The hard disk may also temporarily store therein data generated while the CPU executes the computer programs.

The input output I F controls inputs and outputs of data to and from the host computer . For example input devices such as a keyboard and a mouse are connected to the input output I F . Controlling signals corresponding to operations a user makes on these input devices are output from the input output I F and supplied to the CPU via the bus . The input output I F may also support a serial interface such as the Universal Serial Bus USE or the Institute Electrical and Electronics Engineers IEEE 1394.

The drive reads data from a storage medium such as a compact disk CD or a digital versatile disk DVD . Without a limitation thereto a storage medium supported by the drive may also be a nonvolatile semiconductor memory for example. The computer programs for causing the CPU to operate are provided stored in the CD the DVD and the nonvolatile semiconductor memory for example and are read by the drive and stored in a predetermined location in the hard disk . The display control unit is connected with a display and converts and outputs a display controlling signal generated by the CPU into a signal in a format displayable on the display .

The network I F supports the Transmission Control Protocol Internet Protocol TCP IP for example and can communicate with an external information apparatus such as the client computer or the printer over the network . The computer programs for causing the CPU to operate may be provided from an external server for example over the network received at the network I F and stored in a predetermined location in the hard disk .

For example the client computer has application software and a printer driver installed therein and has a communication unit for communicating with the printer . The application software is for example word processing software spreadsheet software or imaging software. The communication unit includes a communication device that physically communicates with the printer and software that controls the communication device.

The printer driver has a print setting module and a drawing module . In the example in it is assumed that the printer driver does not have any plug in function. The print setting module performs various printing related settings based on a user operation or a command from the application software . A displaying module causes the display to display thereon print setting information and presents the print settings to the user. The drawing module converts data that the application software requests to have printed into a format printable by the printer according to the print settings set by the print setting module to generate drawing data. The drawing data is passed to the communication unit .

The plug in module stores therein a plug in for adding a function to the base printer driver . The plug in module can store therein a plurality of plug ins e.g. a plug in a plug in . . . . In the example in the plug in module stores therein two plug ins a plug in A plug in and a plug in B plug in and the functions of the plug in A and the plug in B are added to the functions of the base printer driver .

The plug in body has a print setting module and a drawing module . The print setting module performs various printing related settings based on a user operation or a command from the application software in the same manner as the print setting module . The print setting module may also include a displaying module for causing the display to display thereon a setting window.

The drawing module converts the data to be printed into a format printable by the printer to generate the drawing data in the same manner as the drawing module . This drawing data as well as the drawing data generated by the drawing module in the base printer driver or by other plug in stored in the printer driver is respectively printed as a layer.

Either one of the print setting module and the drawing module included in the plug in body may be omitted depending on the function of the plug in to which the plug in body belongs. For example if the function of the plug in is for always printing with a stamp regardless of print settings the plug in body may include only the drawing module and the print setting module may be omitted as illustrated in the example in .

The plug in information module stores therein internal configuration information of the plug in or information that is referred within the plug in. For example the plug in body refers to the information stored in the plug in information module within the same plug in to perform the print settings or to generate the drawing data. The plug in information module is used if the plug in requires some settings therefore if the plug in does not need to use the plug in information module the plug in information module may be kept empty or may be omitted as illustrated in the example in .

The plug in body includes for example a library that is read and used by the base printer driver as required and an executable file that can be executed by itself. In the Windows registered trademark that is one of the OSes a library is referred to as a dynamic link library DLL and represented by an extension .dll . An executable file is an EXE file in the Windows registered trademark and represented by an extension .exe .

The file format of the plug in information module is not especially limited as long as the plug in body can interpret such a format. In practice the plug in information module is a file described in a text and in the Windows registered trademark for example file formats indicated by extensions such as .txt .ini or .xml are used. The extension .xml indicates that the file is described in the Extensible Markup Language XML and defines each of stored information with tags.

The plug in the plug in A illustrated in is an example of a configuration of a plug in for extending the functions of the base printer driver so that a user is allowed to decide the print settings to generate drawing data converted into a format printable by the printer based on the setting. In this plug in the plug in body has the print setting module and the drawing module . Because information unique to the plug in is also used the plug in information module is included as well.

The plug in the plug in B illustrated in is an example of a configuration of a plug in for extending the function of the base printer driver so that a print is always made with a stamp regardless of the print settings. In this scenario because it is not necessary to perform the print settings or to use the plug in information the plug in body includes only the drawing module

An embodiment of the present invention will now be explained. depicts an exemplary configuration of a printer driver package according to an embodiment of the present invention. The printer driver package is stored at a predetermined directory in the host computer . A package herein means a structure of files that are grouped together to make up the printer driver. In other words the printer driver package stores therein a file set required for operating as the printer driver.

In the embodiment the file set includes a file set making up the base printer driver and a plug in storage file storing therein a plug in for adding a function to the base printer driver . The content of the plug in storage file is kept empty when no function is added to the base printer driver by way of a plug in.

Without limitation thereto if no function is added to the base printer driver by way of a plug in another file that is not a plug in may be stored in the plug in storage file .

In descriptions in the driver information file a file name of the plug in storage file rplgprn.zip in the example in is described in a file list section together with each of the names of files belonging to the file set that makes up the base printer driver .

In the example in the plug in the plug in A and the plug in the plug in B are stored in the plug in storage file adding the two plug ins to the base printer driver . The plug in includes files pluginAu.dll pluginAg.dll and pluginA.ini . The plug in includes a file pluginB.exe . A directory may be created in the plug in storage file for each of the plug ins and store therein each of these files corresponding to each of the pair of the plug ins at the directory together or each of the files may be stored one dimensionally without creating any directory.

The OS controlling an installing operation performed by the printer driver obtains the file names of the files making up the printer driver package based on the descriptions in the file list section of the driver information file and executes installing operations based on the obtained file names.

According to the embodiment in the initial condition where no plug in is added to the base printer driver the plug in storage file is created as a dummy in advance and information thereof is described in the file list section of the driver information file . A set of files making up a plug in to be added then is stored in the plug in storage file . Therefore as described above even if a plurality of plug ins is added to the base printer driver the descriptions in the file list section do not change and the OS recognizes the plug in storage file as one of the files that make up the printer driver package .

In a ZIP file pieces of file data that are to be archived are respectively appended with local file headers . . . including file name information information indicating compression non compression and the like and are stored sequentially from the head of the ZIP file. The file data . . . may be compression coded or may not be compressed. The file data . . . and the corresponding local file headers . . . are referred to as archive data.

A central directory is appended at the end of the archive data in other words at the tail of the ZIP file. The central directory is definition information for the archive data and includes file headers . . . respectively corresponding to the local file headers . . . . In the file headers . . . the file names of the file data . . . to which the corresponding local file headers . . . are appended are described for example. A footer that is a definition of an end is appended following the central directory .

To read each of the file data . . . stored in the ZIP file the central directory located at the tail of the ZIP file is accessed to begin with to read the file headers . . . . Each of the file data . . . is then accessed based on the read file headers . . . information. Therefore each of the file data . . . stored in the ZIP file can be accessed individually.

A process of taking out each the files stored in a group in the plug in storage file and having a respective original file format is referred to as an extraction or an extracting process. In the example of the ZIP file the central directory is accessed and the file headers . . . are read to take out each of the file data . . . in the respective original format by way of the extraction or the extracting process. If each of the file data . . . is compression coded each of the file data . . . is expanded in a corresponding method based on information such as file headers . . . .

The installer lists up printer drivers that are installed in the OS on the host computer and retrieves a printer driver to which the new plug in should be installed Step S . At next Step S the installer refers to a directory at which the printer driver to which the new plug in is to be installed is installed and retrieves the plug in storage file in the printer driver package for the printer driver. The plug in storage file thus retrieved is extracted at Step S.

At next Step S the installer checks the contents of the extracted plug in storage file and determines whether any other plug in is already stored. When it is determined that no plug in is stored in the plug in storage file the process proceeds to Step S that is to be described later. On the contrary when it is determined that the plug in storage file already stores therein a plug in at Step S the process proceeds to Step S.

At Step S a set of files making up the plug in that is to be newly installed is merged with a set of files making up the other plug in that is taken out from the plug in storage file by way of the extracting process at Step S. In other words by way of this merging process the set of files making up the plug in that is to be newly installed is placed in parallel with the set of files making up the other plug in that is already installed. Upon completing the merging process the process proceeds to Step S.

At Step S the plug in storage file containing the plug in that is to be newly added is generated. In other words when the process directly proceeds from Step S to Step S the plug in storage file containing the set of files making up the plug in that is to be newly added is generated. On the contrary when the process proceeds from Step S to Step S the plug in storage file containing the entire data merged at Step S is generated.

In the example of the ZIP file for example the local file header is generated for each of the files to be stored in the plug in storage file and the local file header and the file data for each of the files are sequentially written. Upon completing writing all of the files to be stored in the plug in storage file the file headers . . . are generated based on each of the local file headers . . . and each of the file data . . . and the central directory is built. The built central directory is written to the end of the archive data including each of the local file headers . . . and each of the file data . . . the footer is further written thereto the plug in storage file is thus generated. The generated plug in storage file for example overwrites the original plug in storage file .

At Step S the file data . . . may include the archive data that is compression coded in a predetermined format or may be used uncompressed to be included in the archive data.

In the embodiment the dummy plug in storage file is created while no plug in is added to the base printer driver and information of the plug in storage file is written to the file list section of the driver information file . Therefore at Step S and Step S even if the files making up a new plug in is added to the plug in storage file the descriptions in the driver information file do not change.

After the plug in storage file is generated at Step S the process proceeds to Step S. At Step S an update time and date timestamp of the plug in storage file generated at Step S is changed.

More specifically at Step S the update time and date of the plug in storage file is changed to the time a little for example approximately one second after the updated time and date of the plug in storage file before the extracting process is performed at Step S. This is for avoiding a trouble upon upgrading the base printer driver .

In other words depending on the update time and date of the plug in storage file there is a possibility that the update time and date of the plug in storage file is considered later than that of a printer driver of a newer version. In such a situation a plug in that is made available with the printer driver of the newer version ends up having the update time and date older than that of the plug in storage file . Therefore the version of the plug in made available with the printer driver of the newer version could be determined to be older than the version of the plug in that is currently installed thus preventing such a plug in from being installed.

To avoid such a trouble in the embodiment the update time and date of the plug in storage file is changed back to the update time and date of the original plug in storage file . In practice to avoid an unexpected error the update time and date of the plug in storage file is changed a little later a few seconds to a few minutes than the update time and date of the original plug in storage file as mentioned earlier.

This example is not limited thereto and the update time and date of the plug in storage file may be set to any time between the update time and date of the original plug in storage file and the update time and date of the printer driver of the next version. More preferably the update time and date of the plug in storage file is changed to time that is after the update time and date of the original plug in storage file not matching such update time and date and appearing approximately the same time as the update time and date for example the time a few seconds to a few minutes after the update time and date .

It is assumed herein that the plug in storage file storing therein a plug in that is to be additionally installed is generated using the process explained with the flowchart of and the printer driver package including the plug in storage file is formed on the host computer before performing the process in .

On the client computer by way of a user operation for example the OS is requested to update or to install the printer driver corresponding to the printer connected thereto over the network . In response to the request the OS on the client computer requests the host computer to update the printer driver using the Point Print function SEQ .

In response to the request the OS on the host computer performs predetermined exchanges such as those for setting a port or for obtaining identification ID information of the printer between the host computer the printer and the client computer according to the Point Print function. By way of such exchanges the Point Print function is made available.

Once the Point Print function is made available the client computer requests the host computer to copy the printer driver package of the printer driver corresponding to the printer to the client computer according to the Point Print function SEQ . In response to this request the host computer transmits a set of files including the plug in storage file making up the printer driver package to the client computer following the descriptions in the file list section of the driver information file by way of the Point Print function.

When the client computer receives the set of files making up the printer driver package the OS on the client computer starts installing the set of files to the client computer SEQ .

For example the OS copies the files contained in the set of files making up the base printer driver and the plug in storage file to predetermined directories. The installer then registers predetermined information related to the copied files to the OS.

The function of the plug in added to the printer drive is called as appropriate when required such as upon executing a print. For example when a function realized by a plug in becomes necessary upon executing a print the printer driver extracts the plug in storage file to take out the files making up the plug in and copies the same to a predetermined directory.

As explained above according to the embodiment the plug in added to the printer driver can be copied to the client computer using only the function included in the OS on the host computer .

A variation of the embodiment will now be explained. The process for generating the plug in storage file explained above in the embodiment using is executed using the installer dedicated to the added plug in. On the contrary in the variation a plug in is installed using a general process without using the installer dedicated to the plug in.

In other words the installer attached to the plug in could have information unique to the plug in information about the corresponding printer driver or information related to files making up the plug in for example . Therefore as explained above in the embodiment using the process of installing the plug in can be automatically performed by initiating the installer.

On the contrary if the installer is not used and the printer driver itself has a plug in installing function for example such an installing function becomes generally applicable in the printer driver. Therefore the information unique to the plug in cannot be recognized and it is difficult to execute the plug in installing process just by initiating the printer driver.

Even in such a scenario if the set of files making up the plug in to be installed is placed to a location of the storage area specified by the printer driver on the host computer the plug in installing process can be performed automatically.

Before the process whose example is illustrated in the flowchart in the set of files making up the plug in that is to be newly added to the printer driver is placed to a location of the storage area specified by the printer driver by way of a user operation for example. The location in which the set of files making up the plug in is placed is not especially limited as long as the printer driver can refer thereto.

The printer driver checks whether the set of files making up the plug in is placed at the location of the storage area specified by printer driver at a predetermined timing Step S . If not placed the installing process is ended for example not illustrated .

One possible timing at which the installer checks whether the set of files making up the plug in is placed is when some kind of a command a Device Driver Interface DDI call for example in the example of the Windows registered trademark that is one of the OSes is issued from the OS to the printer driver. Without limitation thereto the installer may check whether the set of files is placed at the specified location based on a user operation.

When it is confirmed that the set of files making up the plug in is stored in the location of the storage area specified by the printer driver the process proceeds to Step S. Step S and thereafter the process proceeds in the same manner as in that in the flowchart illustrated in according to the embodiment.

In other words the plug in storage file in the printer driver package is extracted at Step S and it is determined whether any other plug in is stored in the extracted plug in storage file at Step S. When it is determined that no plug in is stored in the plug in storage file the process proceeds to Step S and the plug in storage file containing the plug in to be newly added is generated thereat.

On the contrary when it is determined that other plug in is stored in the plug in storage file at Step S the process proceeds to Step S. The set of files making up the plug in that is to be newly installed is then merged with the set of files making up the other plug in that is already stored in the plug in storage file . Upon completing merging the process proceeds to Step S and the plug in storage file containing the plug in that is already added and the plug in that is to be newly added is generated.

After the plug in storage file is generated at Step S the update time and date timestamp of the generated plug in storage file is changed at next Step S. For example the update time and date of the generated plug in storage file is changed to time and date that is a little for example one second or so after the time and the date when the original plug in storage file is generated.

The printer driver package containing the plug in storage file thus generated is copied and installed to the client computer by way of the Point Print function provided by the OS for example. Because the process of installing to the client computer is the same as that according to the embodiment illustrated using. the explanation thereof is omitted herein.

The installing program or the printer driver executed on the host computer according to the embodiment and the variation of the embodiment is recorded to and provided in the computer readable storage medium such as a CD a flexible disk FD or a DVD as files in an installable or an executable format read by way of the drive and installed to the host computer .

Alternatively the installing program or the printer driver executed on the host computer according to the embodiment or the variation of the embodiment may also be stored on a computer connected to a network such as the Internet or a LAN and made available for a download over the network. Moreover the installing program or the printer driver executed on the host computer according to the embodiment or the variation of the embodiment may be provided or distributed over a network such as the Internet.

Furthermore it is possible for the installing program or the printer driver executed on the host computer according to the embodiment or the variation of the embodiment to be provided incorporated in the ROM in advance.

The installing program and the printer driver executed on the host computer according to the embodiment or the variation of the embodiment are read from the storage medium and executed by the CPU to become loaded onto the main memory the RAM generating the installer and the printer driver on the main memory.

According to the present invention a function that is added to the printer driver on the host computer can be easily added to the client computer advantageously.

Although the invention has been described with respect to specific embodiments for a complete and clear disclosure the appended claims are not to be thus limited but are to be construed as embodying all modifications and alternative constructions that may occur to one skilled in the art that fairly fall within the basic teaching herein set forth.

