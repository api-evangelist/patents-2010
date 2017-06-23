---

title: Mobile device and control method thereof
abstract: The mobile device includes a communication unit which performs communication through a network; and a control unit which executes an application prepared by an application programming interface (API) of the network function provided by a platform, and controls the communication unit to perform communication in accordance with a setup of a preferred network if the application includes the setup of the preferred network.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08904017&OS=08904017&RS=08904017
owner: Sansung Electronics Co., Ltd.
number: 08904017
owner_city: Suwon-si
owner_country: KR
publication_date: 20101201
---
This application claims priority from U.S. Patent Provisional Application Nos. 61 265 923 and 61 265 939 filed Dec. 2 2009 and Korean Patent Application No. 10 2010 0116091 filed Nov. 22 2010 in the Korean Intellectual Property Office the disclosures of which are incorporated herein by reference in their entireties.

Apparatuses and methods consistent with exemplary embodiments relate to a mobile device and a control method thereof and more particularly to a mobile device capable of providing a network function and a control method thereof.

A mobile device such as a cellular phone a smart phone a tablet personal computer PC etc. performs communication through various networks such as third generation 3G Wi Fi etc. Such various networks have their merits and deficiencies regarding connectivity speed costs etc. Thus it is desirable to selectively use various networks in accordance with purpose or intention.

Meanwhile an application of a mobile device often uses a network service supported by an operating system OS a platform or the like of the mobile device in order to provide a function useful to a user.

However the OS the platform or the like of a related art mobile device does not sufficiently support an application developer to conveniently develop an application in association with the network. Therefore enhancement of an application developing environment is desirous.

Exemplary embodiments address at least the above problems and or disadvantages and other disadvantages not described above. Also an exemplary embodiment is not required to overcome the disadvantages described above and an exemplary embodiment may not overcome any of the problems described above.

One or more exemplary embodiments provide a mobile device capable of providing a developing environment in which a preferred network can be more easily set up and a control method thereof.

According to an aspect of an exemplary embodiment there is provided a mobile device providing a network function the mobile device including a display unit which displays an image a user input unit which receives an input of a user a communication unit which performs communication through a network and a control unit which executes an application prepared by an application programming interface API of the network function provided by a platform and controls the communication unit to perform communication in accordance with setup of a preferred network if the application includes the setup of the preferred network.

The platform may define a plurality of operation modes related to the preferred network the application may include setup of a variable representing one of the plurality of operation modes and the control unit may control the communication unit to operate in the operation mode corresponding to the setup of the variable.

The plurality of operation modes may include use of Wi Fi first use of only a packet switched PS domain and use of only Wi Fi.

A network connection by the platform may include a default network connection where the application does not specify the network connection and a custom network connection where the application is enabled to directly control the network and the control unit may control the communication unit to perform communication in accordance with the setup of the preferred network in the case of the default network connection.

According to another aspect of an exemplary embodiment there is provided a control method of a mobile device providing a network function the control method including executing an application prepared by an API provided by a platform of the mobile device and performing communication in accordance with setup of a preferred network if the application includes the setup of the preferred network.

The platform may define a plurality of operation modes related to the preferred network the application may include setup of a variable representing one of the plurality of operation modes and the performing the communication may include performing communication to operate in the operation mode corresponding to the setup of the variable.

The plurality of operation modes may include use of Wi Fi first use of only a PS domain and use of only Wi Fi.

A network connection by the platform may include a default network connection where the application does not specify the network connection and a custom network connection where the application is enabled to directly control the network and the performing the communication may include performing the communication in accordance with the setup of the preferred network in the case of the default network connection.

Certain exemplary embodiments are described in greater detail below with reference to accompanying drawings.

In the following description like drawing reference numerals are used for like elements even in different drawings. The matters defined in the description such as detailed construction and elements are provided to assist in a comprehensive understanding of exemplary embodiments. However exemplary embodiments can be practiced without those specifically defined matters.

The communication unit performs communication through a network. The contents and type of the communication performed by the communication unit may vary depending on use and function of the mobile device . For example in the case of a telephone function the communication unit calls the other device not shown for telephone conversation. In this exemplary embodiment the calling type includes 3G. In the case of an Internet function the communication unit performs Internet connection with a predetermined server not shown for transmitting receiving data. Further the communication unit may perform communication with a peripheral device not shown through local communication such as Bluetooth WiFi etc. The communication unit performs the communication under control of the control unit .

The display unit displays an image representing the operation or state of the mobile device . The display unit may display an image by using various display devices including for example a liquid crystal display LCD an organic light emitting device OLED etc. The audio output unit outputs an audio representing the operation or state of the mobile device . The audio output unit may include an audio processor not shown that processes an audio signal and a loudspeaker not shown that outputs an audio based on an audio signal.

The user input unit receives a user s command. The user input unit may receive a user s command in various forms which may include a key input unit not shown that receives a user s command by a key input and a touch input unit not shown that receives a user s command by a touch input. A touch input unit may include a touch screen provided in the display unit .

The storage unit is a non volatile memory including for example a flash memory a hard disk drive etc. which stores data or programs for operating the mobile device . The power unit supplies power for operating the mobile device . The camera unit takes an image and the audio input unit may include a microphone or the like and receives an audio. Some of the above described elements for example the camera unit or the like may be omitted from the mobile device in consideration of its function or use.

The control unit controls the operation of the elements in the mobile device . The control unit may include a read only memory ROM where a control program for performing an operation is stored a random access memory RAM where the control program is at least partially loaded and a central processing unit CPU which executes the loaded control program. The control program of the control unit may be stored in the storage unit as well as in the ROM . The control program of the control unit may include a plurality of programs. is a block diagram showing an exemplary configuration of the control program in the control unit .

As shown in the control program of the control unit may include an OS a device driver a platform and an application . The OS manages and controls overall operations of the mobile device . The device driver performs an interface between a hardware device such as the communication unit and the OS . The platform performs an interface between the OS and the application and includes an API for supporting the application .

The application performs at least one function and may be prepared using the API of the platform . The function performed by the application includes a network function. The application may be transmitted from the external device through the communication unit and installed on the mobile device . That is a user can download the application via the Internet or the like and install it on the mobile device .

The API of the platform includes an API for the network function which is also referred to as a network service. For example a network connection representing an actual run time session is initially established for transmitting and receiving data through a network using the platform . To set up the network connection a network account may be used. The network account encapsulates configuration parameters such as a protocol type an access point name a local Internet protocol IP address a domain name system DNS address authentication information etc. After the network connection is successfully established a data communication protocol such as a hyper text transfer protocol HTTP socket methods etc. may be applied.

Referring to the application requests a network service of the platform without a network connection via a request . The network service e.g. HTTP socket methods etc. internally starts the default network connection in accordance with a preset default as indicated by a reference numeral . Next the network service of the platform accesses a network via a connection .

The default network connection shown in is established because the application does not specify the network connection and therefore usage of the network is simplified in view of the application developer. Also the platform is allowed to fully manage the network connection. Thus the application developers can easily and simply develop the application even though they do not know complicated contents of the API .

Referring to the application creates the custom network connection and starts it as indicated by a reference numeral . Program shows an example of the application that creates and starts a custom network connection.

Referring back to the application requests a network service of the platform with a network connection via a request . Next the network service of the platform accesses the network via a connection .

The custom network connection described with reference to may be for an advanced developer and enables the application to directly control the network . Thus the application can use a specific network account and start or stop the network connection at any time. That is the application developer is allowed to develop the application that provides a more enhanced function.

The control unit of an exemplary embodiment may enable the developer to perform communication with a desired network which may be referred to as a preferred network in accordance with a setup of the application . is a view for explaining a preferred network of the mobile device in this exemplary embodiment. The preferred network in this exemplary embodiment includes Wi Fi and 3G . The 3G is an example of a PS domain. The control unit may be connected to one of the preferred networks i.e. the Wi Fi and the 3G in accordance with the setup of the application .

The API of the platform defines a plurality of operation modes related to the preferred network. The application includes setup of variables that represents one of the operation modes defined by the API of the platform . Table 1 shows an example of variables corresponding to the operation modes related to the preferred network of the present exemplary embodiment and Program shows an example of the application that sets up the preferred network. The platform accomplishes connection to one preferred network between the Wi Fi and the 3G with reference to the variables set up in the application .

In this exemplary embodiment the platform provides the foregoing simple API in association with the preferred network so that the application developer can readily perform the setup related to the preferred network by simply selecting the given variable of the API . Also the setup of the preferred network may be applied to the default network connection described with reference to . In other words although the application developer does not completely know the API to accomplish the custom network connection described with reference to the developer is enabled to set up the preferred network even when the default network connection is used. Accordingly there is provided an environment for more easily developing the application .

As described above there is provided a developing environment in which a preferred network can be more easily set up.

The foregoing exemplary embodiments and advantages are merely exemplary and are not to be construed as limiting. The present teaching can be readily applied to other types of apparatuses. Also the description of the exemplary embodiments is intended to be illustrative and not to limit the scope of the claims and many alternatives modifications and variations will be apparent to those skilled in the art.

