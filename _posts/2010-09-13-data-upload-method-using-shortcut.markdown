---

title: Data upload method using shortcut
abstract: Provided is a method of uploading data to a data server with minimum manipulations and downloading or retrieving the uploaded data by using a user's mobile terminal or a user-designated recipient's mobile terminal. A data upload method used by a computer system includes: monitoring whether a data upload shortcut command is input; selecting an object to be uploaded when an input of the data upload shortcut command is sensed; and transmitting an upload file, which consists of data of the selected object, to a data server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09307010&OS=09307010&RS=09307010
owner: ENBSOFT INC.
number: 09307010
owner_city: 
owner_country: KR
publication_date: 20100913
---
The following description relates to a data upload method using a shortcut key or a pop up menu and more particularly to a method of uploading data to a data server with minimum manipulations and downloading or retrieving the uploaded data by using a user s mobile terminal or a user designated recipient s mobile terminal.

The so called Internet storage service involves giving a user an account to access a data server through the Internet and allowing the user given the account to use a storage service through the Internet.

As the use of mobile terminals e.g. smart phones that can access the Internet anywhere increases the need for retrieving data uploaded from a computer system to a data server by using a mobile terminal is also increasing.

To upload data stored in a computer system to a data server an application for accessing the data server is executed and data is uploaded to the data server by using the application. In this method however since a certain application must be executed a lot of manipulations are required.

In addition the type of contents that can be used on mobile terminals may be limited as compared with computer systems. For example a moving image in an asf format cannot be played on certain mobile terminals. Thus even when the moving image in the asf format is downloaded from a data server to the mobile terminals it cannot be immediately played on the mobile terminals. Accordingly this has led to a demand for a technology of uploading various contents stored in a computer system to a data server with minimum manipulations but converting a file that is to be uploaded hereinafter referred to as an upload file into a format supported by a recipient s mobile terminal and uploading the upload file in the supported format to the data server.

In computers data is managed on a file by file basis. Likewise there is a demand for a technology of converting contents displayed on a web browser application a document editing application or other viewer applications into a file with minimum manipulations uploading the file to a data server and downloading the uploaded file to a mobile terminal.

The following description relates to a method of uploading data to a data server only with the input of a shortcut command to upload data hereinafter referred to as a data upload shortcut command without executing an application which is required to upload data to the data server and downloading or retrieving the uploaded data by using a user s mobile terminal or a user designated recipient s mobile terminal.

The following description also relates to a method of identifying a model of a recipient s mobile terminal converting an upload file into a format supported by the recipient s mobile terminal when the upload file is in a format unsupported by the recipient s mobile terminal and uploading the upload file in the supported format to a data server.

The following description also relates to a method of converting contents displayed on a certain application into a file and uploading the file to a data server.

In one general aspect there is provided a data upload method used by a computer system. The method includes monitoring whether a data upload shortcut command is input selecting an object to be uploaded when an input of the data upload shortcut command is sensed and transmitting an upload file which consists of data of the selected object to a data server. The data upload shortcut command may be input by inputting a shortcut key or selecting a menu item from a pop up menu that appears upon a right mouse button click. That is an agent application may perform the function of monitoring whether the data upload shortcut command is input.

The monitoring of whether the data upload shortcut command is input the selecting of the object to be uploaded and the transmitting of the upload file may be performed by the agent application which is executed in a background mode by an operating system that controls the computer system. Here the method may further include receiving information about a model of a mobile terminal through the agent application wherein the transmitting of the upload file may include retrieving information about formats supported and unsupported by the model of the mobile terminal and converting the upload file into a supported format when the upload file is in an unsupported format and transmitting the upload file in the support format to the data server.

In another aspect there is provided a data upload method using a shortcut key. The data upload method includes installing an agent application which monitors whether a data upload shortcut key is input on a computer system selecting an object to be uploaded by using the agent application when the data upload shortcut key is input from a user by using the computer system and transmitting an upload file which consists of data of the selected object to a data server by using the agent application.

In another aspect there is provided a data upload method using a pop up menu. The data upload method includes installing an agent application which monitors mouse input signals on a computer system adding a data upload item to a pop up menu by using the agent application when a mouse input signal for generating the pop up menu is received from the computer system selecting an object to be uploaded by using the agent application when the data upload item is selected and transmitting an upload file which consists of data of the selected object to a data server by using the agent application.

Other features and aspects will be apparent from the following detailed description the drawings and the claims.

According to the present invention a user of a computer system can upload data to a data server by inputting a data upload shortcut command without executing an application which is required to upload data and can download or retrieve the uploaded data to his or her mobile terminal or a user designated recipient s mobile terminal.

According to the present invention data in a format unsupported by the mobile terminal of the user having an account in the data server to which data is to be uploaded is converted into a supported format and uploaded accordingly to the data server. Thus the user can download the uploaded data to the mobile terminal and use the downloaded data without conversion.

According to the present invention after contents displayed on an Internet browser application a document viewer application or the like are selected the input of only the data upload shortcut command is required to convert the selected contents into a file and upload the file to the data server.

Throughout the drawings and the detailed description unless otherwise described the same drawing reference numerals will be understood to refer to the same elements features and structures. The relative size and depiction of these elements may be exaggerated for clarity illustration and convenience.

Advantages and features of the present invention and methods of accomplishing the same may be understood more readily by reference to the following detailed description of exemplary embodiments and the accompanying drawings. The present invention may however be embodied in many different forms and should not be construed as being limited to the embodiments set forth herein. Rather these embodiments are provided so that this disclosure will be thorough and complete and will fully convey the concept of the invention to those skilled in the art and the present invention will only be defined by the appended claims. Like reference numerals refer to like elements throughout the specification.

The present invention is described hereinafter with reference to block diagrams or flowchart illustrations of a method of uploading data using a shortcut according to exemplary embodiments of the invention. It will be understood that each block of the flowchart illustrations and combinations of blocks in the flowchart illustrations can be implemented by computer program instructions. These computer program instructions can be provided to a processor of a general purpose computer special purpose computer or other programmable data processing apparatus to produce a machine such that the instructions which execute via the processor of the computer or other programmable data processing apparatus create means for implementing the functions specified in the flowchart block or blocks.

These computer program instructions may also be stored in a computer usable or computer readable memory that can direct a computer or other programmable data processing apparatus to function in a particular manner such that the instructions stored in the computer usable or computer readable memory produce an article of manufacture including instruction means that implement the function specified in the flowchart block or blocks.

The computer program instructions may also be loaded onto a computer or other programmable data processing apparatus to cause a series of operational steps to be performed on the computer or other programmable apparatus to produce a computer implemented process such that the instructions that execute on the computer or other programmable apparatus provide steps for implementing the functions specified in the flowchart block or blocks.

And each block of the flowchart illustrations may represent a module segment or portion of code which comprises one or more executable instructions for implementing the specified logical function s . It should also be noted that in some alternative implementations the functions noted in the blocks may occur out of the order. For example two blocks shown in succession may in fact be executed substantially concurrently or the blocks may sometimes be executed in the reverse order depending upon the functionality involved.

The configuration of a data upload and retrieval system according to an exemplary embodiment of the present invention will now be described with reference to .

An agent application is a software module that monitors whether a data upload shortcut command is input selects an object to be uploaded when sensing the input of the data upload shortcut command creates an upload file which consists of data of the selected object and transmits the created upload file to a data server .

The agent application can be executed on a computer system after an installation file is downloaded to the computer system or after a component object model COM module is installed on a website. After installation the agent application may be executed in the background. That is the agent application process is performed but the agent application may not have its own graphic user interface GUI . Even when the agent application has its own GUI only environment settings and whether to activate each function can be set on the GUI.

The agent application may be installed such that it automatically runs when the computer system having the agent application installed thereon boots up. In the process of installing the agent application a user may decide whether to allow the automatic execution of the agent application.

A device on which the agent application is installed that is a device on which a data upload method according to the current exemplary embodiment is implemented may be any device capable of transmission control protocol Internet protocol TCP IP communication. The TCP IP communication may use a wired communication network or a wireless communication network. For example the agent application can be installed on personal computers PCs personal digital assistants PDAs smart phones and notebooks.

Once installed the agent application starts monitoring in the background whether the data upload shortcut command is input. The data upload shortcut command may be input by inputting a shortcut key or selecting a data upload menu item from a pop up menu. Thus the agent application must monitor mouse inputs as well as key inputs. The mouse inputs may include touches on a touch screen or touchpad.

The monitoring of the key inputs and the mouse inputs may be performed by hooking an input occurrence message provided by an operating system installed on the computer system on which the agent application runs. The operating system may support a GUI.

The message hooking may include registering a callback function which is called when the input occurence message is generated with a kernel of the operating system calling the callback function by using the kernel in response to an input signal generated by an input device determining whether the input signal is related to a data upload function by using the callback function and executing the data upload function when it is determined that the input signal is related to the data upload function.

When the data upload shortcut command is input operation S the agent application selects an object to be uploaded. The object to be uploaded denotes a data set to be uploaded to the data server such as character strings image data moving image data a file or a folder.

The agent application may select an object activated on a GUI as the object to be uploaded. When no activated object is available the agent application may select an object displayed at the position of the cursor on the GUI as the object to be uploaded.

The activated object may be a selected block of text or an object currently selected by a click. shows a pop up menu displayed by selecting and activating a block of character strings from all character strings displayed on a document editing program and clicking the right mouse button on the activated block. For example when a upload to My Account item is selected from menu items of the pop up menu the activated block of character strings is selected as the object to be uploaded.

Next the agent application creates the upload file which consists of data of the selected object to be uploaded and transmits the created upload file to the data server . The above operations of selecting the object to be uploaded creating the upload file and uploading the upload file may be performed by the agent application in response to only the data upload shortcut command input by the user.

When an object activated or displayed at the position of the cursor is one of a file and a folder the agent application may upload all files contained in the file or the folder to the data server .

When the activated object is character strings as shown in the agent application may create a document file containing the character strings. The format of the document file is not limited. For example a general text file .txt a word file .doc of Microsoft Corporation or a Hangul file .hwp of Hancom Inc. may be created. To create the document file an application programming interface API provided by a document editing application may be used.

As shown in if the data upload shortcut command is input in a state where an Internet browser application is activated the object to be uploaded may be at least one of a web document posted on the currently activated Internet browser application and contents embedded in the web document.

The embedded contents may be e.g. an image a moving image clip or a sound clip included in the web document. The type of the object which is displayed at the position of the cursor and from which URL information is to be extracted may be obtained from an API provided by the Internet browser application.

Here the agent application may create a link file containing the URL information and upload the link file to the data server .

In addition the agent application may download a file corresponding to the URL information and upload the downloaded file. For example when the user places the cursor on an image posted on an Internet browser application and inputs a shortcut key or selects a pop up menu item to upload the image the agent application may generate URL information of the image by calling an API provided by the Internet browser application download a file corresponding to the URL information and upload the downloaded file to the data server .

When the upload file is in an unsupported format the agent application may convert the format of the upload file before uploading the upload file to the data server .

For example iPhone models of Apple Inc. are unable to play moving images in an asf format of Microsoft Corporation. Thus when the upload file is in the asf format the application agent converts the upload file into an mp4 format and uploads the upload file in the mp4 format to the data server . Accordingly the user can download the upload file from the data server using an iPhone and play the downloaded upload file without conversion.

To this end the operation of obtaining information about the model of a mobile terminal by using the agent application may further be performed. In addition information about formats supported and unsupported by each mobile terminal model may be stored in the computer system in advance. That is when the upload file is in an unsupported format the agent application may convert the upload file into a supported format and transmit the upload file in the support format to the data server .

The obtaining of the information about the model of a mobile terminal may include receiving a phone number of a mobile terminal and retrieving information about the model of the mobile terminal by using the phone number of the mobile terminal.

The upload file may be uploaded to the user s own account or to a designated recipient s account. When the upload file is to be uploaded to the user s account information about the model of the user s mobile terminal may be extracted from subscriber information. When the upload file is to be uploaded to the designated recipient s account a service ID of the designated recipient or a phone number of the designated recipient s mobile terminal may additionally be input to the computer system .

The upload file may be stored in a certain area of the data server . For example the upload file may be stored in an area allocated to a first account which is received through the agent application. For example login information may be received through the agent application and data may be uploaded to the user s account or to the designated recipient s account.

The upload file can be retrieved or downloaded using the mobile terminal of the user. To this end a data server access application may be installed on the mobile terminal . The mobile terminal may receive information about a second account through the data server access application. When the information about the first account is the same as the information about the second account or when the relationship between the first account and the second account allows the second account to access the first account a list of files stored in the area allocated to the first account can be provided to the mobile terminal . That is when user A uploads moving image file X to his or her account user B who has a data sharing relationship with user A can retrieve or download the moving image file X stored in an area allocated to user A s account as well as files stored in an area allocated to his or her account in the data server . When user A does not have the data sharing relationship with user B user A may designate user B as a recipient and upload data to the area of the user B s account.

When the mobile terminal requests transmission of the upload file stored in the area of the first account the data server may transmit the upload file to the mobile terminal .

Referring to an agent application is installed in the way described above operation S and a login process is performed using the agent application operation S . Before the login process a user subscription procedure may be performed. Subscription information may include information about the model of a user s mobile terminal. The information about the model of the user s mobile terminal may be input directly by the user or may be retrieved from a user information server of a communication service provider based on a phone number of the mobile terminal. The user information server of the mobile communication service provider may be for example a home location register HLR server.

The agent application starts its monitoring operation operation S . When sensing the input of a data upload shortcut command operation the agent application selects an object to be uploaded in the way described above and creates an upload file operation S . In the current embodiment the sensing of the input of the data upload shortcut command operation S denotes sensing the selection of the upload to My Account item from the pop up menu shown in or sensing the input of a shortcut key that is allocated to upload data to the user s account.

When the created upload file is in a format unsupported by the model of the mobile terminal of the user who logged in the agent application converts the upload file into a supported format operation S . The conversion may be performed by e.g. a moving image converter. When the upload file is a document file it may be converted into a text file .txt by extracting only character strings.

The upload file is uploaded to a data server operation S . Then the user can retrieve or download the uploaded upload file by accessing the data server using his or her mobile terminal operation S .

According to the present invention only a single shortcut command input is required for a user to upload a file a folder activated character strings or a selected still or moving image to an area allocated to the user s account in a data server. In addition when data is in a format unsupported by a mobile terminal of the user the data is automatically converted into a supported format and is then uploaded to the data server. Thus after downloading the uploaded data the user can use the downloaded data without conversion.

In the current embodiment sensing the input of a data upload shortcut command operation S denotes sensing the selection of an upload to Friend s Account item from the pop up menu shown in or sensing the input of a shortcut key that is allocated to upload data to a user s account.

After operation S in which an object to be uploaded is selected and an upload file is created a recipient of the upload file is designated.

A recipient may be designated by a phone number of the recipient s mobile terminal. operation S . In this case an agent application may retrieve information about the model of the designated recipient s mobile terminal from a user information server of a mobile communication service provider by using the phone number of the designated recipient s mobile terminal.

When the information about the model of the designated recipient s mobile terminal is retrieved formats unsupported by the model of the designated recipient s mobile terminal can also be identified. Thus the agent application performs file conversion operation S in the same process as that illustrated in and uploads the upload file operation S .

The designated recipient may access the data server using his or her mobile terminal and retrieve or download the upload file uploaded to an area that is allocated to his or her account operation S .

While the present invention has been particularly shown and described with reference to exemplary embodiments thereof it will be understood by those of ordinary skill in the art that various changes in form and detail may be made therein without departing from the spirit and scope of the present invention as defined by the following claims. The exemplary embodiments should be considered in a descriptive sense only and not for purposes of limitation.

