---

title: Communication device, server, program, and communication system
abstract: A communication device including: a communication unit; and a control unit controlling the communication unit to inquire if one upload service allows direct upload to a server storing service information of each of a plurality of upload services, to have the communication unit obtain desired information from the server for directly uploading data to the one upload service when the one upload service allows direct upload, and to have the communication unit directly upload data to the one upload service according to the desired information.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08676934&OS=08676934&RS=08676934
owner: Sony Corporation
number: 08676934
owner_city: Tokyo
owner_country: JP
publication_date: 20100114
---
The present invention relates to a communication device a server a program and a communication system which are suitably applicable when for example data is uploaded from a communication device.

Recently various services are provided via networks. As an example there is a service of uploading content data such as a video image taken by a user from a terminal of the user which may also be referred to as a client to a server on a network for making an archive. Such a service may also be referred to as an upload service. The server to which to upload content data in a service of this type may also be referred to as the service providing server.

In many upload services it is possible to publish content data uploaded to the service providing server to other users and the content data can then be shared by a plurality of users.

In order to let many users utilize an upload service as described above it is desirable to enable upload quickly and easily.

In many existing upload services however the user usually searches for a web page of a desired service by utilizing a web browser to upload content data so it is hard to say that upload can be carried out quickly and easily.

In view of the above situation a system is proposed not to upload directly from the client to the service providing server but to upload via a relay server to the service providing server for example refer to Japanese Unexamined Patent Application Publication No. 2008 211732 .

In this system the relay server maintains information of various services such as the address of the service providing server and a desired service can be selected by accessing from the client to the relay server. When the desired service is selected and the content data to be uploaded is submitted from the client the relay server transfers it to the service providing server of the selected service for upload.

In this way in this system a desired service can be selected just by accessing a relay server a time for example to search for a web page of a desired service can be saved.

However in the system described above since content data is designed to be uploaded to the service providing server of a desired service via the relay server accesses from clients are concentrated on the relay server. As a result the load on the relay server increases and time taken for uploading becomes longer than in direct upload.

In upload services of related art it is hard to say that uploading can be carried out quickly and easily.

It is desirable to propose a communication device a server a program and a communication system that can perform upload quickly and easily.

According to an embodiment of the present invention a communication device controls a communication unit to inquire if one upload service allows direct upload to a server having service information of each of a plurality of upload services maintained therein to make it obtain desired information from the server for directly uploading data to the one upload service when the one upload service allows direct upload and to make it directly upload data to the upload service according to the desired information.

Thus compared to a case of uploading via a server as in related art access concentration on the server can be reduced. Even when an upload service is added or deleted or an upload method is changed it suffices to update the service information in the server and it is possible to prevent an increase in user tasks in a communication device.

That is while keeping the ease of upload which is an advantage in a case of uploading via a server as in related art upload can be carried out quickly.

Accordingly it is possible to provide a communication device a server a program and a communication system that enable to upload quickly and easily.

A description is given below to preferred modes referred to below as embodiments for carrying out embodiments of the present invention. The description is given in the following order 

First a description is given to an outline of an embodiment. After describing the outline the description moves to specific examples of the embodiment.

In the communication system includes a communication device uploading data to an arbitrary upload service and a server storing and maintaining service information of each of a plurality of upload services.

The communication device has a communication unit communicating via a network and a control unit controlling the communication unit .

The control unit of the communication device is designed to control the communication unit to inquire if one upload service allows direct upload to the server .

When the one upload service allows direct upload as a result of the inquiry the control unit controls the communication unit to obtain desired information for uploading data directly to the one upload service from the server .

The control unit then controls the communication unit according to the desired information to upload data directly to the one upload service. Specifically it transfers data to an upload location specified by the one upload service.

The server has a communication unit communicating via a network a control unit controlling the communication unit and a memory unit storing and maintaining service information of each of the plurality of upload services.

The control unit of the server then controls the communication unit to respond to the inquiry if the one upload service allows direct upload from the communication device according to the service information stored and maintained in the memory unit .

Further when the one upload service allows direct upload the control unit controls the communication unit according to the service information stored and maintained to submit desired information to the communication device for uploading data directly to the one upload service.

With such a configuration in the communication system compared to a case of uploading via the server as in related art it is possible to reduce access concentration on the server . In the communication system even when an upload service is added or deleted or an upload method is changed it suffices to update the service information in the server and it is possible to prevent an increase in user tasks in the communication device .

That is in the communication system while keeping the ease of upload which is an advantage in a case of uploading via the server as in related art upload can be carried out quickly.

A detailed description is given below to specific examples of the communication system with such a configuration.

Next a description is given to a configuration of an upload system as a specific example of the present embodiment using .

As illustrated in the upload system is configured with clients A B a web server a relay server and service providing servers A to C . These devices have a function of communicating via a network such as the Internet. Here the clients are the specific examples of the communication device described above. The relay server is a specific example of the server described above.

The service providing servers A to C are servers operated respectively by providers A to C providing upload services to users. Specifically the service providing servers A to C archive image data uploaded from the clients . The image data uploaded to the service providing servers A to C is managed per uploading user and can not only be browsed freely by the uploading user but can also be published to other users via the network.

Although the respective providers A to C operating each of the service providing servers A to C are common in the point of providing an upload service for image data they are different in service forms of the upload services.

Here a specific description is given to the differences in the service forms of the upload services A to C provided by the providers A to C using . As shown in the service forms of each of the upload services A to C can be represented by a plurality of items. In other words each of the upload services A to C is different in at least a part of the contents shown by the plurality of items and this indicates the differences in the service forms.

For example SUPPORTED FORMAT is one of the items which shows which of still image data upload and video image data upload is supported by each of the upload services A to C. For example the upload service A only supports still image data upload and that is shown in SUPPORTED FORMAT . The upload service C supports both still image data upload and video image data upload and that is shown in SUPPORTED FORMAT .

 PUBLISH UNPUBLISH SETTING shows whether or not each of the upload services A to C allows setting of publishing unpublishing uploaded image data. For example the upload service A allows setting of publishing unpublishing image data and that is shown in PUBLISH UNPUBLISH SETTING . The upload service B does not allow setting of publishing unpublishing image data and that is shown in PUBLISH UNPUBLISH SETTING .

 ALBUM FUNCTION shows whether or not each of the upload services A to C has a function of managing a plurality of uploaded image data pieces as an album which may also be referred to as an album function . For example the upload service A has an album function and that is shown in ALBUM FUNCTION . The upload service B does not have an album function and that is shown in ALBUM FUNCTION .

 ALBUM TITLE INPUT shows whether or not each of the upload services A to C allows inputting a title of an album that is an album title for managing a plurality of uploaded images as an album. For example the upload service A allows inputting an album title and that is shown in ALBUM TITLE INPUT . The upload service B does not allow inputting an album title and that is shown in ALBUM TITLE INPUT .

 IMAGE TITLE INPUT shows whether or not each of the upload services A to C allows inputting a title of uploaded image data that is an image title . For example the upload service A allows inputting an image title and that is shown in IMAGE TITLE INPUT .

 IMAGE DESCRIPTION INPUT shows whether or not each of the upload services A to C allows inputting a description of uploaded image data that is an image description . For example the upload service A allows inputting an image description and that is shown in IMAGE DESCRIPTION INPUT . The upload service B does not allow inputting an image description and that is shown in IMAGE DESCRIPTION INPUT .

 TAG INPUT shows whether or not each of the upload services A to C allows inputting a tag of uploaded image data. A tag is information as a key for searching image data.

For example the upload service A does not allow inputting a tag and that is shown in TAG INPUT . The upload service B allows inputting a tag and that is shown in TAG INPUT .

 LOGIN PARAMETER shows a type of a login parameter that each of the upload services A to C requests to the client when uploading image data. For example the upload service A requests an email address and a password as such a login parameter and that is shown in LOGIN PARAMETER . The upload service B requests an ID and a password as such a login parameter and that is shown in LOGIN PARAMETER .

 STILL IMAGE MAXIMUM SIZE in shows the maximum size of still image data that each of the upload services A to C allows for upload. For example the upload service A allows uploading still image data of 5 MB at a maximum and that is shown in STILL IMAGE MAXIMUM SIZE .

 VIDEO IMAGE MAXIMUM SIZE shows the maximum size of video image data that each of the upload services A to C allows for upload. For example the upload service B allows uploading video image data of 100 MB at a maximum and that is shown in VIDEO IMAGE MAXIMUM SIZE .

 VIDEO IMAGE MAXIMUM TIME PERIOD shows the maximum time period of video image data that each of the upload services A to C allows for upload. For example the upload service B allows uploading video image data of 10 minutes at a maximum and that is shown in VIDEO IMAGE MAXIMUM TIME PERIOD .

 MAXIMUM NUMBER OF CONTENTS shows the maximum number of image data pieces that each of the upload services A to C allows each user to upload. For example the upload service B allows each user to upload up to 20 image data pieces and that is shown in MAXIMUM NUMBER OF CONTENTS .

 SERVICE LOGO shows an image file of a service logo that is used in each of the upload services A to C.

 SERVICE TRADEMARK TEXT shows a content of a service trademark text that is used in each of the upload services A to C.

 DIRECT UPLOAD SUPPORT shows whether or not each of the upload services A to C supports direct upload.

The direct upload is as illustrated in to upload image data from one of the clients to one of the service providing servers not via the relay server . In contrast as illustrated in to upload image data from one of the clients to one of the service providing servers via the relay server may also be referred to as relay upload.

Although described in detail later either direct upload or relay upload does login issuing of an session ID and the like via the relay server from the clients to the service providing servers . In other words the relay server plays a role as a common contact point portal when utilizing each of the upload services A to C from the clients .

Here for example the upload service B supports direct upload and that is shown in DIRECT UPLOAD SUPPORT . The upload service A does not support direct upload and that is shown in DIRECT UPLOAD SUPPORT .

 AUTOMATIC PROCESS IN SERVER shows a process automatically executed by the service providing servers A to C when each of the upload services A to C uploads image data.

In such a way the upload services A to C provided by the providers A to C are respectively different in the service forms so that they employ different methods of uploading image data.

For example although both upload services B and C support direct upload they employ different upload methods.

In other words the clients are desired to execute direct upload in a method corresponding to each of the upload services B and C.

Accordingly for example it is considered to store information desired for direct upload which may also be referred to as desired information for utilizing each of the upload services B and C in the clients in advance.

However in this case it is not allowed to support adding and deleting an upload service changing an upload method and the like. To enable supporting the desired information should be updated in the clients every time forcing the users to do such a task.

In the upload system the clients are designed to obtain the desired information corresponding to the utilized upload service from the relay server upon direct upload.

Actually the relay server is designed to maintain service information related to each of the upload services A to C and the desired information is obtained from the service information to provide it to the clients .

Upon direct upload the clients access the relay server to obtain desired information corresponding to the utilized upload service and perform direct upload according to the obtained desired information.

Thus in the upload system even when an upload service is added or deleted or an upload method is changed it suffices to update the service information in the relay server and labors on the clients can be reduced.

By directly uploading image data to the service providing servers not via the relay server in such a way it is possible to reduce access concentration on the relay server compared to a case of uploading image data via the relay server .

On the other hand as the upload service A there is also a service not supporting direct upload. In a case of utilizing such a service relay upload via the relay server is carried out.

That is one of the clients submits image data to the relay server . The relay server uploads the image data submitted from the client to the service providing server A of the upload service A.

The client A has a function of directly accessing the relay server and the service providing servers A to C to upload image data whereas the client B does not have such a function.

Instead the client B has a web browser function and is designed to be able to upload image data by accessing from a web page provided by the web server to the relay server and the service providing servers A to C. In other words the client B is designed to provide a function equivalent to the client A in cooperation with the web server .

In such a way in the upload system both clients A and B are designed to be able to upload image data similarly.

Next using a description is given to a configuration of the clients the relay server and the service providing servers . The clients A and B are considered to have an identical configuration. The service providing servers A to C are also considered to have each identical configuration.

Each of the clients has a control unit a communication unit a memory unit a display unit and an operation input unit .

The control unit is configured with for example a CPU a ROM and a RAM and integrally controls the whole according to various programs and various APIs and also executes various processes relating to image data upload described later in detail . API stands for an application programming interface which is a program called for executing a particular process. CPU ROM and RAM stand for respectively a central processing unit a read only memory and a random access memory.

The communication unit communicates with the relay server and the service providing servers A to C via the network under the control of the control unit . The memory unit is for example a hard disk drive or a flash memory and stores various programs various APIs various image data pieces and the like.

The display unit is for example a liquid crystal display and displays a GUI screen with images icons and the like disposed thereon under the control of the control unit . GUI stands for a graphical user interface. The operation input unit is for example operation buttons or touch panels and accepts a user operation as an input to send a command corresponding to the input to the control unit .

Although the client B basically has a configuration identical to that of the client A it has a weaker function of executing programs and APIs in comparison with that of the client A. The client B is designed to provide an execution function equivalent to that of the client A by cooperating with the web server .

The relay server has a control unit a communication unit and a memory unit . The control unit is configured with for example a CPU a ROM and a RAM and integrally controls the whole according to various programs and various APIs and also executes various processes relating to image data upload described later in detail .

The communication unit communicates with the client A the web server and the service providing servers A to C via the network under the control of the control unit . The memory unit is for example a hard disk drive or a flash memory and stores various programs various APIs various image data pieces service information related to each of the upload services A to C and the like.

Each of the service providing servers has a control unit a communication unit and a memory unit . The control unit is configured with for example a CPU a ROM and a RAM and integrally controls the whole according to various programs and various APIs and also executes various processes relating to image data upload described later in detail .

The communication unit communicates with the client A the web server and the relay server via the network under the control of the control unit . The memory unit is for example a hard disk drive or a flash memory and stores various programs various APIs various image data pieces service information of the upload services A to C and the like. In the memory unit a database is built for managing the uploaded image data.

The web server is considered to have a configuration for example of omitting the display unit and the operation input unit from the configuration of the client A. That is the web server has an execution function equivalent to that of the client A. The web server is then designed to execute various processes relating to image data upload described later in detail corresponding to a request from the client B.

Next using a description is given to sequences for uploading image data from one of the clients to one of the service providing servers which may also be referred to as upload sequences . Here a description is given to an example of directly uploading image data from the client A to the service providing server B of the upload service B which supports direct upload. The upload sequences are sequences executed mainly by the control unit of the client A the control unit of the relay server and the control unit of the service providing server B in cooperation.

First in step SP shown in it is assumed that a user instructs the client A to start an upload program via the operation input unit . The control unit of the client A then starts the upload program stored in the memory unit in step SP. The upload program is a program common in each of the upload services A to C which may also be referred to as a common program .

The control unit of the client A requests a list of currently available upload services to the relay server via the communication unit in step SP according to the upload program.

Upon receiving the request via the communication unit the control unit of the relay server generates a list of currently available upload services in step SP to reply to the client A with the list via the communication unit .

The relay server is designed to occasionally obtain service information in which the latest service forms and the like are shown from each of the service providing servers A to C to store it in the memory unit . The control unit of the relay server then generates the list of upload services on the basis of the service information to submit it to the client A. In the list a name of the provider and a part of the service forms for example supported format for example are entered per currently available upload service.

Upon receiving the list via the communication unit the control unit of the client A makes the display unit display the list as a GUI screen not shown in step SP. The client A can thus let the user confirm the currently available upload services.

The GUI screen is designed to allow selecting a desired upload service from the list. The user is then assumed to select a desired upload service for example the upload service B from the list via the operation input unit in step SP. The control unit of the client A then requests detailed information on the selected upload service to the relay server via the communication unit in step SP.

Such a request for the detailed information is executed in such a manner that the control unit of the client A calls an API for obtaining detailed information stored in the memory unit . Such an API for obtaining detailed information is an API common in each of the upload services A to C which may also be referred to as a common API .

Upon receiving the request via the communication unit the control unit of the relay server replies to the client A via the communication unit with the detailed information on the selected upload service in step SP.

Here the control unit of the relay server is designed to extract information corresponding to the selected upload service from the service information of each of the upload services A to C stored in the memory unit to reply with it as the detailed information.

In other words in the detailed information the contents shown in each of the items shown in are included as the information related to the service forms of the selected upload service. Accordingly the service forms of the selected upload service which of still image upload and video image upload is supported if direct upload is supported and the like are understood from the detailed information.

The detailed information is for example text data described in an XML format and also includes information to configure a GUI screen displayed by the display unit of the client A when utilizing the selected upload service.

Upon receiving the detailed information via the communication unit the control unit of the client A makes the display unit display a GUI screen based on the detailed information in step SP. The GUI screen displayed at this point differs depending on the selected upload service. illustrates a GUI screen displayed at this point. The GUI screen is a GUI screen displayed when the upload service B is selected.

In the GUI screen icon and logo of the provider B of the upload service B is displayed at the upper left. To the right of the icon and logo a login information input field for inputting information desired for login which may also be referred to as login information and a submit button for giving an instruction to submit the inputted login information are provided.

Further in the GUI screen at the center an upload image display region is provided to display a listing of image data to be uploaded. Below the upload image display region a size display region is provided to display the size of the image data to be uploaded.

Still below the size display region an album specification check box is provided to specify whether uploading the image data as a new album or by adding to an existing album.

Still below the album specification check box a title input field is provided to input a title of the image data. Yet below the title input field a comment input field is provided to input a description comment of the image data.

Further in the GUI screen at the lower right an upload execution button is provided to give an instruction for upload execution.

It is designed that via the GUI screen the user can input the login information select the image data to be uploaded specify the album to store the image data input the title and the description execute upload and the like.

The GUI screen illustrated in is one example and an input field to input a tag a check box to specify a publish unpublish setting of the image data to be uploaded and the like may also be provided based on the detailed information.

The user is then assumed to input the login information in the login information input field via the operation input unit and presses the submit button in step SP shown in . The control unit of the client A then sends the inputted login information to the relay server via the communication unit in step SP.

The submission of the login information by the client A is executed in such a manner that the control unit of the client A calls an API for processing login stored in the memory unit . This API for processing login is also a common API. However the login information to be submitted differs depending on the selected upload service.

Upon receiving the login information via the communication unit the control unit of the relay server transfers the login information to the service providing server B of the selected upload service B via the communication unit in step SP.

The transfer of the login information to the service providing server B by the relay server is executed by calling an API for processing login. Such an API for processing login is an API unique to each of the upload services A to C which may also be referred to as a unique API . Such unique APIs are for example provided from each of the service providing servers A to C to be stored in the memory unit of the relay server .

Upon receiving the login information via the communication unit the control unit of the service providing server B verifies the login information in step SP. If it is confirmed as a login request from a user having a valid uploading authority as a result of the verification the control unit then issues a session ID for the relay server . The control unit then submits the issued session ID and the login result indicating the login permission to the relay server via the communication unit in step SP.

The session ID issued by the service providing server B is an ID utilized for keeping a session between the service providing server B and the relay server . That is the following communication between the service providing server B and the relay server is executed by assigning this session ID. Such a process can be thus omitted to submit the login information every time the relay server accesses the service providing server B for verification of the login information in the service providing server B. Such a session ID may also be referred to as a session ID for a service providing server.

Upon receiving the login result and the session ID for a service providing server via the communication unit the control unit of the relay server issues a session ID for the client A. The control unit stores the session ID for a service providing server in the memory unit . The control unit then submits the issued session ID and the received login result to the client A via the communication unit in step SP.

The session ID issued by the relay server is an ID utilized for keeping a session between the relay server and the client A. That is the following communication between the relay server and the client A is executed by assigning this session ID. Such a session ID may also be referred to as a session ID for a relay server.

Upon receiving the login result and the session ID for a relay server via the communication unit the control unit of the client A stores the session ID for a relay server in the memory unit . The control unit displays on the GUI screen that for example it has logged in normally on the basis of the received login result in step SP.

Then in step SP it is assumed that the user presses the upload execution button via the GUI screen after carrying out a preparatory task for upload such as selection of image data to be uploaded and inputs of a title and a description.

The control unit of the client A then carries out direct upload because the detailed information on the upload service B received in advance indicates that the upload service B supports direct upload.

That is the control unit of the client A firstly in step SP submits metadata of the uploading image data and its parameter composed of a file name and a size to the relay server via the communication unit .

Here the metadata is the title and the description of the image data the ID of the album to store the image data the publish unpublish setting of the image data and the like inputted or specified via the GUI screen .

The submission of the metadata and the parameter is executed in such a manner that the control unit of the client A calls a direct upload initiation API stored in the memory unit . Such a direct upload initiation API is a common API. The content of the submitted data is however different.

Upon receiving the metadata and the parameter the control unit of the relay server submits the desired information for direct upload to the service providing server B to the client A in step SP.

The desired information is generated on the basis of the metadata and the parameter received from the client A the service information and the session ID for a service providing server obtained from the service providing server B of the upload location.

That is the desired information includes for example the metadata and the parameter the address of the upload location the service providing server B in this case the data format of the image data desired header information the session ID for a service providing server and the like.

Upon receiving the desired information from the relay server the control unit of the client A appropriately processes the image data and metadata to be uploaded according to the desired information. For example in a case of the image data to be uploaded not being in a specified data format it converts to the specified data format.

Taking the image data and metadata as upload data the control unit further gives the specified information to the upload data according to the desired information. For example the header information and the session ID for a service providing server entered in the desired information are given.

The control unit then directly uploads the upload data in step SP to the address of the upload location described in the desired information in other words the service providing server B. In other words direct upload to the service providing server B is carried out.

Upon receiving the upload data from the client A via the communication unit the control unit of the service providing server B makes the memory unit store the upload data and register it in a database for management.

Upon terminating direct upload from the client A the control unit then replies to the client A via the communication unit with the result which may also be referred to as an upload result in step SP.

Upon receiving the upload result the control unit of the client A transfers the upload result to the relay server together with the metadata and the parameter of the uploaded image data in step SP .

Here the upload result provided from the service providing server B is in a format unique to each of the upload services in this case upload service B and it is difficult for the client A to understand the contents directly.

In the upload system it is designed that the client A submits the upload result to the relay server to make the relay server convert to a common format that can be recognized by the client A.

The submission of the metadata the parameter and the upload result is executed in such a manner that the control unit of the client A calls a direct upload termination API stored in the memory unit . Such a direct upload termination API is an API identical to the direct upload initiation API other than the point of submitting the upload result and is a common API.

Upon receiving the metadata the parameter and the upload result the control unit of the relay server converts the upload result to the common format that can be recognized by the client A in step SP.

The conversion of the upload result is executed in such a manner that the control unit of the relay server calls an API for converting an upload result stored in the memory unit . Such an API for converting an upload result is a unique API and for example is provided from each of the service providing servers A to C to be stored in the memory unit of the relay server .

The control unit then replies to the client A via the communication unit with the upload result in the common format in step SP.

Upon receiving the upload result in the common format the control unit of the client A displays that the upload is succeeded or failed on for example the GUI screen on the basis of the upload result in step SP.

With such an upload sequence the upload system is designed to directly upload image data from the client A to the service providing server B.

In the upload sequence described using the image data and the metadata are taken as the upload data for uploading in one time. However depending on the upload service there may be a request for two phase upload such as uploading image data followed by uploading the metadata separately.

Here for example it is assumed that the upload service C is a service requesting such two phase upload.

In this case the control unit of the client A directly uploads the image data to the service providing server C in step SP described above according to the desired information received from the relay server . At this point the control unit does not upload the metadata.

After that in step SP the result of uploading the image data is replied to the client A. Further in step SP the client A submits the upload result and the metadata and the parameter of the uploaded image data to the relay server .

Upon receiving the upload result the metadata and the parameter the control unit of the relay server uploads the metadata to the service providing server C in step SP shown in .

In such a way when two phase upload of image data upload and metadata upload is requested the image data is directly uploaded from the client A to the upload location firstly. After that the metadata of the image data is relay uploaded from the client A via the relay server to the upload location.

The upload of metadata by the relay server to the service providing server C is executed by calling an upload API. Such an upload API is a unique API and for example is provided from each of the service providing servers A to C and stored in the memory unit of the relay server .

Upon receiving the metadata the control unit of the service providing server C makes the memory unit store the metadata and register it in the database by matching with the image data uploaded in advance for management.

Upon terminating the upload of the metadata from the relay server the control unit replies to the relay server via the communication unit with the upload result of the metadata in step SP.

Upon receiving the upload result of the metadata the control unit of the relay server converts the upload result and the upload result of the image data received in advance from the client A to the common format in step SP.

The control unit replies to the client A via the communication unit with the upload result in the common format in step SP. The control unit of the client A displays that the upload is succeeded or failed on for example the GUI screen in step SP on the basis of the upload result.

With such an upload sequence the upload system is designed to support two phase upload of image data and metadata as well.

In the upload sequence described using the upload data is directly uploaded to the upload location. However there is also an upload service not supporting direct upload. In a case of utilizing such an upload service relay upload is carried out.

In this case the control unit of the client A submits the metadata and parameter of the image data to the relay server in step SP described above .

Upon receiving the metadata and parameter of the image data the control unit of the relay server uploads them as the upload data to the service providing server A in step SP shown in .

At this point the control unit of the relay server appropriately processes the image data and the metadata and or gives desired information to the upload data according to the service information obtained from the service providing server A.

This upload is executed in such a manner that the control unit of the relay server calls a relay upload API stored in the memory unit . Such a relay upload API is a unique API.

Upon receiving the upload data from the relay server the control unit of the service providing server A makes the memory unit to store the upload data and register it in the database for management.

Upon terminating the upload from the relay server the control unit replies to the relay server with the upload result in step SP.

Upon receiving the upload result the control unit of the relay server converts the upload result to the common format that can be understood by the client A in step SP.

Upon receiving the upload result in the common format the control unit of the client A displays that the upload is succeeded or failed on for example the GUI screen on the basis of the upload result in step SP.

With such an upload sequence the upload system is designed to relay upload the image data from the client A via the relay server to the service providing server A.

As thus far described in the upload system this relay server is designed to store and maintain the service information related to each of the upload services A to C.

The relay server is then designed to obtain the desired information for direct upload from the service information to submit it to the client A.

The client A performs direct upload to the specified upload location according to the desired information.

Thus in the upload system the access concentration on the relay server can be reduced compared to a case of uploading via the relay server as in related art. As a result the time taken for upload can be remarkably cut compared to a system that carries out relay upload for each time.

In the upload system even when an upload service is added or deleted or an upload method is changed it suffices to update the service information in the relay server and the labors on the client A can be reduced.

In the upload system in a case of utilizing an upload service not supporting direct upload it is designed to carry out relay upload via the relay server similar to related art.

In the upload system it is thus possible to provide both services of allowing direct upload and allowing only relay upload and diverse upload services can be provided for users.

Next using a description is given to a procedure RT of upload processes executed by the client A in the upload sequence described above which may also be referred to as an upload processing procedure .

The upload processing procedure RT is a processing procedure executed in accordance with the upload program started by the control unit of the client A.

As the upload program is instructed to start the control unit of the client A initiates the upload processing procedure RT. The control unit obtains a list of currently available upload services from the relay server to display it on the display unit and the sequence proceeds to step SP.

In step SP the control unit stands by for the selection of an upload service to be utilized from the displayed list and when selected it obtains a positive result in step SP and the sequence proceeds to step SP.

In step SP the control unit obtains detailed information on the selected upload service from the relay server and the sequence proceeds to step SP. In step SP the control unit displays the GUI screen as illustrated in according to the obtained detailed information on the display unit and the sequence proceeds to step SP.

In step SP the control unit stands by for an instruction of upload via the displayed GUI screen and when instructed it obtains a positive result in step SP and the sequence proceeds to step SP.

In step SP the control unit determines whether or not the upload service utilized at this time is a service supporting direct upload on the basis of the detailed information received in advance.

When the control unit obtains a positive result in step SP because the upload service utilized at this time is a service supporting direct upload the sequence proceeds to step SP at this point.

In step SP the control unit submits the metadata of the image data to be uploaded and its parameter the file name and the size of the image data to the relay server and the sequence proceeds to step SP.

In step SP the control unit receives the desired information for direct upload that is in a reply from the relay server as a result of the submission of the metadata and the parameter and the sequence proceeds to step SP.

In step SP the control unit submits the image data and the metadata to be uploaded as the upload data to the specified address on the basis of the received desired information in other words carries out direct upload and the sequence proceeds to step SP.

In step SP the control unit receives the upload result in a reply from the service providing server of the upload location and the sequence proceeds to step SP. In step SP the control unit transfers the received upload result to the relay server and the sequence proceeds to step SP .

In contrast when the control unit obtains a negative result in step SP described above because the upload service utilized at this time is a service not supporting direct upload the sequence proceeds to step SP.

In step SP the control unit submits the image data and the metadata to be uploaded to the relay server in other words carries out relay upload and the sequence proceeds to step SP .

In step SP the control unit receives the upload result in the common format in a reply from the relay server and the sequence proceeds to step SP. In step SP the control unit determines whether or not the contents of the upload result in the common format indicates a success of the upload.

When the control unit obtains a positive result in step SP because the contents of the upload result indicate a success of the upload the sequence proceeds to step SP. In step SP the control unit displays that the upload is succeeded on the GUI screen to terminate the upload processing procedure RT.

In contrast when the control unit obtains a negative result in step SP described above because the contents of the upload result indicate a failure of the upload the sequence proceeds to step SP. In step SP the control unit displays that the upload is failed on the GUI screen to terminate the upload processing procedure RT.

In accordance with such an upload processing procedure RT the client A is designed to carry out direct upload or relay upload.

In the above configuration in the upload system the relay server stores and maintains the service information related to each of the upload services A to C. The relay server is then designed to obtain the desired information for direct upload from the service information to provide it to the client A.

On the other hand the client A determines whether or not the upload service selected by the user supports direct upload on the basis of the detailed information obtained from the relay server . Then in a case of the selected upload service supporting direct upload the client A utilizes the selected upload service to carry out direct upload.

At this point the client A firstly obtains the desired information from the relay server for direct upload utilizing the upload service.

The client A then carries out direct upload to the upload location specified by the upload service according to the desired information. In other words data is uploaded not via the relay server but directly to the upload location.

Thus in the upload system access concentration on the relay server can be reduced compared to a case of uploading via the relay server . As a result the time taken for upload can be remarkably cut compared to a system that carries out relay upload for each time.

In the upload system even when an upload service is added or deleted or an upload method is changed it suffices to update the service information in the relay server and labors on the client A can be reduced. In other words it can prevent an increase in user tasks in the client A.

According to the above configuration the upload system can remarkably cut the time taken for upload compared to a system that carries out relay upload for each time as in related art. In the upload system even when an upload service is added or deleted or an upload method is changed it suffices to update the service information in the relay server and it is possible to prevent an increase in user tasks in the client A. That is in the upload system it is possible to upload quickly while keeping the ease of upload which is an advantage in a case of relay upload as in related art.

Next a description is given to another embodiment. In the embodiment described earlier direct upload is carried out when the utilized upload service supports direct upload. In contrast in the other embodiment it is designed to select either of direct upload and relay upload according to the network traffic.

Since the configurations of the upload system the clients A and B the relay server and the service providing servers A to C are similar to those of the embodiment described earlier they should be referred to the embodiment described earlier. Therefore a description is given here only to an upload processing procedure RT executed by the client A using .

In the upload processing procedure RT shown in FIGS. and steps identical to those in the upload processing procedure RT in the embodiment described earlier are assigned identical step numbers.

As the upload program is instructed to start the control unit of the client A initiates the upload processing procedure RT. The control unit then carries out the processes in steps SP to SP as in the upload processing procedure RT of the embodiment described earlier and the sequence proceeds to step SP.

In the other embodiment the address of the upload location is assumed to be included in addition to the service forms of the selected upload service in the detailed information on the upload service obtained from the relay server in step SP.

In step SP the control unit determines whether or not the upload service utilized at this time supports direct upload on the basis of the detailed information received in advance.

When the control unit obtains a positive result in step SP because the upload service utilized at this time is a service supporting direct upload the sequence proceeds to step SP at this point.

In step SP the control unit submits dummy data directly to the service providing server of the upload location on the basis of the address of the upload location included in the detailed information. Such dummy data is dummy upload data and assumed to be data smaller in size compared to an actual upload data for example several tens in kilobyte .

The service providing server which receives the dummy data returns some response for example an error to the client A. The control unit of the client A measures the time from when submitting the dummy data until the response is returned that is a communication time . The communication time indicates the traffic in a case of direct communication of the client A with the service providing server of the upload location. The control unit then stores the communication time as a direct upload time in the memory unit and the sequence proceeds to step SP.

In step SP the control unit submits the dummy data which is identical to the dummy data submitted in step SP to the relay server . The relay server which has received the dummy data submits the dummy data to the service providing server to which the client A has directly submitted the dummy data.

The service providing server which has received the dummy data returns some response for example an error to the relay server . This response is then transferred from the relay server to the client A. The control unit of the client A measures the time from when the dummy data is submitted until the response is returned that is a communication time . The communication time indicates the traffic when the client A communicates with the service providing server of the upload location via the relay server . The control unit then stores the communication time as a relay upload time in the memory unit and the sequence proceeds to step SP.

In step SP the control unit compares the direct upload time with the relay upload time and the sequence proceeds to step SP. In step SP the control unit determines whether to perform direct upload or not on the basis of the result of comparison in step SP.

Specifically the control unit estimates that when the direct upload time is shorter than the relay upload time there is a less traffic in direct upload than in relay upload. In other words it estimates that the direct upload takes a shorter time for upload and is more effective. At this point the control unit is designed to determine that direct upload should be carried out.

In contrast when the expected direct upload time is longer than the expected relay upload time the control unit estimates that there is a less traffic in relay upload than in direct upload. In other words it estimates that the relay upload takes a shorter time for upload and is more effective. At this point the control unit is designed to determine that relay upload should be carried out.

When the control unit determines execution of direct upload and obtains a positive result in step SP the sequence proceeds to step SP . The control unit then carries out direct upload of the upload data by processing steps SP to SP as in the upload processing procedure RT of the embodiment described earlier and the sequence proceeds to step SP.

In contrast when the control unit determines execution of relay upload and obtains a negative result in step SP described above the sequence proceeds to step SP. The control unit then carries out relay upload of the upload data in cooperates with the relay server in step SP and the sequence proceeds to step SP.

The control unit then performs processes in steps SP to SP or SP as in the upload processing procedure RT of the embodiment described earlier and then terminates the upload processing procedure RT.

In accordance with such an upload processing procedure RT the client A is designed to carry out direct upload or relay upload.

In such a way in the other embodiment the client A is designed to select the one which is estimated to terminate upload in a shorter time from direct upload and relay upload according to the network traffic.

That is the client A carries out relay upload as long as relay upload is estimated to terminate in a shorter upload time even for a service supporting direct upload.

Thus in the other embodiment it is possible to upload more quickly compared to a case of carrying out direct upload for each time utilizing a service supporting direct upload.

There may be a case in which the physical distance between the relay server and the service providing server is longer than the physical distance between the client A and the service providing server . In such a case the time for upload may take longer in direct upload than in relay upload. Even in this case the other embodiment can upload more quickly in such a manner that the client A estimates the situation from the comparison of the communication times described above and selects relay upload.

In the embodiment described first when direct upload is failed the client A indicates the failure on the GUI screen and terminates the upload processing.

Without limiting to this when direct upload is failed the client may also relay upload the same upload data again.

That is when the upload result received from the relay server shows a failure of direct upload the control unit of the client A submits the same image data and metadata to the relay server .

The relay server uploads the image data and the metadata as the upload data to the service providing server .

In such a way by designing to carry out relay upload when direct upload is failed data can be uploaded more certainly.

Without limiting to this when an upload result is not returned even after passing a predetermined time since direct upload has initiated the client may also cancel the direct upload and instead carry out relay upload.

The predetermined time in such a case which may also be referred to as a timeout period is assumed to be set per upload service corresponding to for example the format video image or still image the size and the like of the image data to be uploaded.

The timeout period is then stored and maintained in the relay server as for example the service information of each of the upload services to be also provided to the client A as the detailed information.

That is the control unit of the client A cancels direct upload when the upload result is not returned even after passing a timeout period included in the detailed information since the direct upload has initiated.

The control unit of the client A then submits the same image data and metadata to the relay server . The relay server uploads the image data and the metadata as the upload data to the service providing server .

In such a way although depending on the traffic condition it is possible to upload data more quickly than continuing direct upload in many cases.

Without limiting to this direct upload and relay upload may also be carried out in parallel not cancelling the direct upload after passing the timeout period.

In this case when either upload result is returned the control unit of the client A cancels the other upload.

In the embodiment described first upon receiving the upload result from the service providing server the client A transfers it together with the metadata and the parameter of the uploaded image data to the relay server .

Without limiting to this only the upload result may also be transferred to the relay server at this point.

Actually the client A has submitted the metadata and the parameter of the image data to be uploaded also immediately before obtaining the desired information from the relay server . Therefore as long as the relay server makes the memory unit store the metadata and the parameter received at this point they may not be transferred from the client A to the relay server again.

Further in the embodiment described first in a case of utilizing a service in which the image data and the metadata should be uploaded separately the image data is directly uploaded and the metadata is relay uploaded.

Without limiting to this the metadata may also be directly uploaded. In this case however the relay server also provides the desired information to the client A for direct upload of the metadata.

Further in the embodiment described first the relay server provides the text data which is described in an XML format as the desired information for direct upload to the client A.

Without limiting to this the relay server may also provide a direct upload API to the client A as the desired information. Such an API is a unique API and for example is provided from each of the service providing servers A to C and stored in the memory unit of the relay server .

Further in the embodiment described first in a case of carrying out direct upload from the client A the service providing server directly replies to the client A with the upload result.

Without limiting to this the upload result may also be in a reply to the relay server for each time and the relay server may also convert the upload result to the common format and then transfer to the client A.

In such a way the client A does not have to transfer the upload result in a reply from the service providing server to the relay server and the load on the client A can be more reduced.

Further in the embodiment described first the client A obtains the detailed information in which whether or not the upload service to be utilized supports direct upload and the like are shown from the relay server . Then from the detailed information the client A determines whether or not the upload service to be utilized supports direct upload.

In other words in the embodiment described first the relay server notifies the client A of whether or not the upload service to be utilized supports direct upload via the detailed information.

Without limiting to this the client A may also directly inquire to the relay server whether or not the upload service to be utilized supports direct upload.

In this case the control unit of the relay server determines whether or not the upload service to be utilized supports direct upload on the basis of the stored and maintained service information. It may then reply to the client A with the result of determination.

Further in the other embodiment described earlier either of the direct upload and relay upload is selected based on the network traffic.

Without limiting to this either of direct upload and relay upload may also be selected based on for example the image data format.

In this case the client A selects direct upload for example when the format of the image data to be uploaded is a video image to directly upload the image data. In contrast when the format of the image data to be uploaded is a still image the client A selects relay upload to relay upload the image data.

In such a way as well access concentration on the relay server can also be reduced compared to a system that only carries out relay upload. By changing an upload path corresponding to the format of the image data in such a way the network traffic can be distributed.

Without limiting to this the selection of either direct upload or relay upload may also be made based on for example the size of the image data.

In this case the client A selects direct upload when for example the size of the image data to be uploaded is not less than a predetermined size to direct upload the image data. In contrast when the size of the image data to be uploaded is less than the predetermined size the client A selects relay upload to relay upload the image data.

In such a way as well access concentration on the relay server can also be reduced compared to a system that only carries out relay upload. By changing an upload path corresponding to the size of the image data in such a way the network traffic can be distributed.

The present invention is not limited to the embodiments described so far. That is embodiments of the present invention also cover forms of any combinations of part or all of these embodiments described so far and forms of extracting part of them.

For example the other embodiment described earlier and still the other embodiment 1 may also be combined. In other words as in the other embodiment described earlier the client A selects either of direct upload and relay upload. As a result of carrying out the selected upload it is assumed that selected upload is failed. Then the client A may also carry out the other type of upload as in still the other embodiment 1.

The present application contains subject matter related to that disclosed in Japanese Priority Patent Application JP 2009 030112 filed in the Japan Patent Office on Feb. 12 2009 the entire content of which is hereby incorporated by reference.

It should be understood by those skilled in the art that various modifications combinations sub combinations and alterations may occur depending on design requirements and other factors insofar as they are within the scope of the appended claims or the equivalents thereof.

