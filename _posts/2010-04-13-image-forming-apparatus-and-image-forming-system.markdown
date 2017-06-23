---

title: Image forming apparatus and image forming system
abstract: An image forming apparatus includes an application management unit that detects a restricted function of which use by a given user is inhibited from among functions within an application. The image forming apparatus further includes a function monitoring unit that registers the restricted function detected by the application management unit, and inhibits the user from executing the restricted function.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08873081&OS=08873081&RS=08873081
owner: KYOCERA Document Solutions Inc.
number: 08873081
owner_city: 
owner_country: JP
publication_date: 20100413
---
This application is based upon and claims the benefit of priority from corresponding Japanese Patent Application No. 2009 133522 filed Jun. 2 2009 the entire contents of which is incorporated herein by reference.

Some image forming apparatus such as a printer a copier and a multifunction peripheral are provided with an application that becomes available after acquisition of a license. Further in some image forming apparatus a restricted function of which use is inhibited can be set for each user.

In addition there are image forming apparatus having an application in which as a license is acquired for each function within the application the function for which the license is acquired becomes available within the application.

However in a case where license control and function restriction are both implemented in the application for example upon execution of an application of which use is permitted according to the license there is a fear in that a restricted function of which use is inhibited may be executed from the application.

Further in a case of acquiring a license for each function within the application it is necessary to previously specify the restricted function s for each user before acquiring the license which complicates license management.

An object of the present invention is to provide an image forming apparatus and an image forming system which are capable of positively executing function restriction while performing license management for each application.

An image forming apparatus according to the present invention includes at least one application an application management unit that detects a restricted function of which use by a given user is inhibited from among functions within the at least one application and a function monitoring unit that registers the restricted function detected by the application management unit and inhibits the user from executing the restricted function.

An image forming system according to the present invention includes a server device and an image forming apparatus. The server device includes a storage unit that stores account data for each user where the account data includes a restricted function of which use by the user is inhibited from among functions within an application. In addition a communication unit performs communications with the image forming apparatus in order to access the account data. The image forming apparatus includes a communication unit that performs communications with the server device in order to access the account data an application management unit that reads the account data from the storage unit of the server device by using the communication unit and detects the restricted function regarding a given user and a function monitoring unit that registers the restricted function detected by the application management unit and inhibits the user from executing the restricted function.

Additional features and advantages are described herein and will be apparent from the following Detailed Description and the figures.

A multifunction peripheral which is an example of an image forming apparatus includes a printer a scanner a facsimile apparatus an operation panel an example of a display device a communication device a storage unit and an arithmetic processing unit .

The printer is an apparatus that prints a document image based on print data. The scanner is an apparatus that optically reads a document image from a document and generates image data on the document image. The facsimile apparatus is an apparatus that generates a facsimile signal from document data to be transmitted and transmits the facsimile signal and that receives a facsimile signal and converts the facsimile signal into document data.

The operation panel is disposed at a surface of a casing of the multifunction peripheral and includes i a display device that displays thereon various kinds of information with respect to the user and ii an input device that detects a user operation. An example of the display device includes a liquid crystal display. Examples of the input device include a key switch and a touch panel.

The communication device is a device connected to a communication channel which allows data communications with a developer terminal device not shown . In a case where the multifunction peripheral and the developer terminal device are connected to the same computer network a network interface is used as the communication device . In a case where the multifunction peripheral and the developer terminal device are connected to the same telephone network a modem is used as the communication device .

The storage unit is a device capable of storing various programs and various kinds of data. Used as the storage unit may be a hard disk drive a nonvolatile memory or the like.

The arithmetic processing unit which may be a computer including a central processing unit CPU a read only memory ROM and a random access memory RAM loads a program from the storage unit or the like into the RAM and causes the CPU to execute the program.

Pre stored on the storage unit are at least account data and a program required for operation of the multifunction peripheral . Then the program is appropriately executed by the arithmetic processing unit after the start of the multifunction peripheral . Realized by the program are an operating system OS a controller a JAVA virtual machine a controller application program interface API an application management unit a function monitoring unit and an application .

The account data includes a user ID of an authorized user and a restricted function ID of a restricted function of which use is inhibited on a user basis.

The controller controls the printer the scanner the facsimile apparatus and the operation panel and performs input output of data thereto therefrom.

In addition the controller includes a user account management unit . The user account management unit references the account data to perform a login process for the user user authentication and registration of a logged in user and perform a logout process deregistration of the logged in user .

The controller API causes the controller to operate according to an instruction from the application running on the JAVA virtual machine in a case of causing the functions of the printer the scanner the facsimile apparatus and the operation panel to be executed or the input output of data to be performed thereto therefrom. Note that in this embodiment the function monitoring unit is provided between the controller API and the controller and the controller API uses the controller through the intermediation of the function monitoring unit .

The application management unit manages a life cycle installation start stop and uninstallation of the application . For example when license information for an application is input by the user the application management unit may install the application .

In addition the application management unit includes an application account management unit that detects a restricted function of which use by a given user is inhibited from among a plurality of functions within the application .

The function monitoring unit registers the restricted function detected by the application management unit . If a function execution request for the application is made by the user the function monitoring unit determines whether or not the function specified by the function execution request is registered as the restricted function. If the function specified by the function execution request is not registered as the restricted function the function monitoring unit permits the execution of the function specified by the function execution request. If the function specified by the function execution request is registered as the restricted function the function monitoring unit inhibits the execution of the function specified by the function execution request. Note that the function monitoring unit registers the restricted function by writing the restricted function ID such as a code number a class name or a function name of the restricted function to be registered into a table stored in the RAM or on the storage unit .

The application is caused to start and or stop by the application management unit based on an operation performed by the user through the operation panel . Further responsive to detection of the function execution request made by the user the application causes the controller to execute the function for example color printing specified by the function execution request through the intermediate controller API and function monitoring unit . The management of the function restriction is performed by the function monitoring unit and hence the function restriction is not performed within the application . That is without consideration given to the function restriction the application issues the function execution request to the controller API .

Hereafter described is 1 a processing at the start of the application 2 a processing responsive to reception of the function execution request for the application made by the user and 3 a processing at the end of the application.

Note that it is assumed here that the user has already logged in. If the user performs a login operation through the operation panel the user account management unit performs the user authentication. If the user is an authorized user the user account management unit permits the user to use the apparatus and registers the user ID of the user as the logged in user.

For example responsive to detecting a user operation making a start request for the application through the operation panel information on the user operation hereinafter referred to as user operation information is supplied to the application management unit of the arithmetic processing unit . Then based on the user operation information the application management unit detects the start request for the application Step S .

Responsive to detecting the start request for the application the application management unit supplies the application account management unit with a request for account information hereinafter referred to as account information request along with the user ID of the logged in user and the application ID of the application Step S . Then the application account management unit supplies the controller API with the account information request along with the user ID and the application ID Step S . At this time the application account management unit determines whether or not the license for the application exists that is whether or not the license information has already been input . Only in a case where the license exists the processing of Step S and the subsequent steps is executed.

The controller API transfers the account information request to the function monitoring unit along with the user ID and the application ID Step S . Responsive to reception of the account information request along with the user ID and the application ID the function monitoring unit references the account data to read one or a plurality of restricted function IDs associated with the user ID and the application ID and supplies the controller API therewith as a response. The response that is the restricted function ID s is supplied to the application management unit via the application account management unit .

Then based on the response to the account information request the application management unit identifies presence absence of the restricted function considered when the logged in user uses the application for which the logged in user has made the start request Step S . If a restricted function is present in the response the one or a plurality of restricted function IDs are identified from the response.

In a case where there is at least one restricted function to be considered when the logged in user uses the application for which the logged in user has made the start request the application management unit supplies the application account management unit with a monitor request along with the user ID of the logged in user and the restricted function ID Step S . The application account management unit supplies the controller API with the monitor request along with the user ID and the restricted function ID Step S . The controller API transfers the monitor request to the function monitoring unit along with the user ID and the restricted function ID Step S . Responsive to receiving the monitor request the user ID and the restricted function ID the function monitoring unit registers the user ID and the restricted function ID in a monitor object table not shown in association with each other Step S . In addition identification information on a listener called when the execution of the function of the restricted function ID is supplied by the user of the user ID is registered in the monitor object table in association with the user ID and the restricted function ID. The monitor object table may be stored in the RAM within the arithmetic processing unit or on the storage unit .

Then responsive to completing registration the function monitoring unit supplies the controller API with the registered identification information on the listener as the response Step S . The response that is identification information on the listener is transferred to the application account management unit Step S . Then the application account management unit retains the user ID the restricted function ID and the identification information on the listener in association with one another for example in the RAM Step S .

Meanwhile responsive to completing the registration of the restricted function by the function monitoring unit the application management unit starts the application specified by the user Step S .

As described above if there exists a restricted function within the specified application the restricted function is registered at the start of the application . Note that if there exists no restricted function within the specified application Step S the processing of Steps S to S is not performed and the application is started Step S .

After the start of the application if the user operation for executing a given function is input to the operation panel by the user the user operation information is supplied to the application . Then based on the user operation information the application detects the function execution request by the user Step S . For example when the application is started a menu screen for selecting a function is displayed. If one function for example color printing or scanning is selected from the menu screen by the user the selected function is identified based on the user operation information obtained in the selecting and the function execution request by the user is detected.

Responsive to detecting the function execution request the application identifies the function ID such as a code number a class name or a function name of the requested function and issues a call of the function accompanied by the function ID and the user ID of the logged in user with respect to the controller API Step S .

When the call is issued the controller API transfers the call to the function monitoring unit Step S . Responsive to receiving the call from the controller API the function monitoring unit references the monitor object table to read the restricted function ID registered in association with the user ID accompanying the call. Then the function monitoring unit determines whether or not the function ID accompanying the call of the function matches any one of the restricted function IDs Step S .

If the function ID accompanying the call of the function matches none of the restricted function IDs the function monitoring unit transfers the call to the controller and causes the controller to execute the requested function Step S .

Alternatively if the function ID accompanying the call of the function matches any one of the restricted function IDs the function monitoring unit does not transfer the call to the controller but rather calls the listener associated with the restricted function ID Step S . Accordingly the application account management unit detects an execution request for the restricted function. Then the application account management unit causes the operation panel to display thereon a message indicating that the logged in user is inhibited from executing the function requested by the logged in user Step S .

If the function ID accompanying the call of the function matches any one of the restricted function IDs the function monitoring unit discards the call and supplies the controller API with an error notification as the response Step S . The response is then transferred to the application Step S .

As described above the function execution request by the user after the start of the application is constantly monitored by the function monitoring unit provided between the controller API and the controller . The execution request for the registered restricted function is rejected while the execution requests for the other functions are approved.

For example responsive to detecting a user operation for making an end request for the application through the operation panel information on the user operation hereinafter referred to as user operation information is supplied to the application management unit of the arithmetic processing unit . Then based on the user operation information the application management unit detects the end request for the application Step S .

Responsive to detecting the end request for the application the application management unit first causes the application to stop Step S .

Then the application management unit supplies the application account management unit with a monitor ending request along with the user ID of the logged in user and the registered restricted function ID Step S . When the application account management unit receives the monitor ending request it supplies the controller API with a deregistration request along with the user ID and the restricted function ID Step S . The controller API then transfers the deregistration request to the function monitoring unit along with the user ID and the restricted function ID Step S .

Responsive to receiving the deregistration request along with the user ID and the restricted function ID the function monitoring unit deletes the restricted function ID registered in association with the user ID from the monitor object table Step S .

Meanwhile after supplying the deregistration request to the controller API the application account management unit clears the registration of the listener associated with the restricted function ID Step S .

As described above if there is a restricted function within the specified application the registration of the restricted function is cleared at the end of the application . If there is no restricted function within the specified application the application is ended and the process of Steps S to S is not performed.

After that if the user performs a logout operation through the operation panel the user account management unit performs the logout process. At a time of logout all the restricted function IDs registered in association with the logged in user are cleared.

As described above according to the above mentioned embodiment the application management unit detects the restricted function of which the use by a given user is inhibited from among the functions within an application . Then the function monitoring unit registers the restricted function detected by the application management unit . If the function execution request for the application is made by the user the function monitoring unit determines whether or not the function specified by the function execution request is registered as the restricted function. If the function specified by the function execution request is not registered as the restricted function the function monitoring unit permits the execution of the function specified by the function execution request. If the function specified by the function execution request is registered as the restricted function the function monitoring unit inhibits the function specified by the function execution request.

Accordingly the monitoring is constantly performed during the execution of the application so as to prevent the restricted function from being executed which allows the function restriction regardless of the license for the application. Further because the function monitoring unit exists between the controller API and the controller a developer of the application can develop the application without consideration given to the function restriction.

In an image forming system according to another embodiment of the present invention the multifunction peripheral is connected to a server device via a network .

The multifunction peripheral according to the another embodiment does not include the account data . The account data is stored not on the multifunction peripheral but on the server device . The multifunction peripheral instead acquires the account data by accessing the server device via the network .

The server device includes a communication device a storage unit and a processing device . The communication device is a device of the same kind as the communication device and is a device capable of performing data communications via the network . The storage unit is a device of the same kind as the storage unit and stores the account data . The processing device is a device that reads the account data in response to a request from the multifunction peripheral and transmits the account data to the multifunction peripheral .

When the application management unit attempts to acquire the account information the application account management unit controls the communication device to transmit an account information request to the server device along with the user ID of the logged in user and the application ID. Then on the server device the processing device reads the restricted function ID corresponding to the request and uses the communication device to transmit the restricted function ID to the multifunction peripheral as the response. Then the application account management unit receives the response that is restricted function ID via the communication device .

Further in the same manner the user account management unit controls the communication device to acquire user registration information such as the user ID from the account data stored on the server device to thereby perform the login process and the like.

Note that each of the above mentioned embodiments is a preferred example of the present invention but the present invention is not limited thereto and various modifications and changes can be made within the scope that does not depart from the gist of the present invention.

For example in each of the above mentioned embodiments one application is provided but also in a case where a plurality of applications are executed the same process as described above is appropriately executed on each of the applications. However in that case an application ID is registered together in the monitor object table and the registration and the deregistration of the restricted function ID are performed for each individual application.

Further if there is an application that has already started for example resident application at a time of user login the application management unit detects the restricted function based on the account data at the time of login. Then the function monitoring unit registers the restricted function for the application.

Further in each of the above mentioned embodiments one multifunction peripheral is provided but a plurality of image forming apparatus multifunction peripherals printers and the like of the same kind as the multifunction peripheral may be connected to the network and the account data may be managed on one server device that is accessible to the plurality of image forming apparatus.

Further in each of the above mentioned embodiments the restricted function may be set for each of one or more departments. In that case in association with the user ID a department ID of a department to which the user belongs is included in the account data. In addition the restricted function ID of the restricted function regarding the department is included in association with the department ID. In the case where the restricted function ID is acquired the restricted function ID associated with the department ID associated with the user ID may be acquired along with the restricted function ID associated with the user ID.

It should be understood that various changes and modifications to the presently preferred embodiments described herein will be apparent to those skilled in the art. Such changes and modifications can be made without departing from the spirit and scope of the present subject matter and without diminishing its intended advantages. It is therefore intended that such changes and modifications be covered by the appended claims.

