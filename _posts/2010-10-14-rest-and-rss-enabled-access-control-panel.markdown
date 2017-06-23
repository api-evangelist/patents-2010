---

title: REST and RSS enabled access control panel
abstract: A method and apparatus are provided for operating a security system. The method includes providing a security system having at least one sensor, coupling a detected state of the at least one sensor to a web server, the web server publishing the detected state and a remotely located user subscribing to receive the detected state of the at least one sensor via the publication by the web server.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08519842&OS=08519842&RS=08519842
owner: Honeywell International Inc.
number: 08519842
owner_city: Morristown
owner_country: US
publication_date: 20101014
---
The field of the invention relates to security systems and more particularly to the control of security systems.

Security systems are generally known. Such systems typically include a physical barrier e.g. walls doors etc. that define and protect a secured area and number of sensors placed around a periphery or within the secured area for the detection of intruders. The sensors may include one or more switches placed on doors or windows. The sensors may also include passive infrared PIR detectors and or motion detectors.

The sensors of a security system are typically connected to an access control panel. The control panel may be armed or disarmed by an occupant through a user interface on the control panel.

The control panel may typically be armed in one of two modes. In a first alarm away mode the control panel may monitor all sensors for intruders. In a second alarm stay mode the control panel may only monitor sensors on a periphery of the protected space with interior sensors deactivated.

Once armed the control panel may monitor the appropriate set of sensors based upon the mode. Upon activation of an intrusion detection sensor the control panel may activate a local alarm and or send an alarm signal to a central monitoring station.

While such systems work well they are difficult to adapt to different reporting requirements. For example security systems for small areas are typically structured to generate an alarm if any monitored sensor is activated. Often the alarm is only reported locally. In the event that one monitored sensor is to be given a higher priority and is to be reported to a central monitoring station the panel must be reprogrammed. Accordingly a need exists for move flexible methods of adapting alarm systems to varying reporting requirements.

The firmware of the panel may be provided in such a way that the status of the panel and sensors can be published to a predetermined number of authorized outside users under a hyper text transfer protocol http . The status of sensors can also be exposed to inquiries through the Internet using a Representational State Transfer REST protocol so that any authorized outside user can enter the appropriate universal resource locator URL and obtain status information using a conventional web browser. The use of the REST protocol avoids the requirement for host software within the panel in cases where the functionality of the control panel must be altered and where it becomes necessary to provide the status of the panel and individual sensors to outside users.

A Rich Site Summary RSS mechanism may be provided to allow authorized outside users to subscribe to status information from the system that is in turn pushed as an RSS feed to an RSS reader of the outside user. The RSS reader can be web based desktop based or mobile device based. Since the RSS feed is an XML structure it allows for the seamless integration of existing alarm panels with changing reporting needs.

Turning now to the system in general a user interface may be included within or located near the control panel . The user interface may include a keyboard for entry of control commands and a display that displays status information. In this case an authorized user may enter a personal identification number PIN and an alarm away or alarm stay pushbutton to arm the system .

Also included within the control panel is a number of processors that process alarm events. For example an alarm processor may monitor the sensors for activation in the armed away or armed stay modes.

Included within the control panel may be a web server processor that provides the functionality of a web site. The web server may operate under the REST format.

Included within the web server processor may be one or more http documents under the REST format within files . Each of the documents files includes status information for the panel or for at least one of the sensors in an appropriate format e.g. XML .

During normal operation the alarm processor monitors the status of the panel and sensors and writes status changes into one or more of the files . A publication processor operating under the RSS format detects any changes to the files and publishes the respective http documents.

At least some of the files may be structured to receive commands actions from authorized outside users. In this case a command processor may monitor the files for changes from outside parties and execute those commands within the control panel .

During set up of the system a RSS reader is provided within a destination device of each authorized outside user. The destination device in this case could be a portable device e.g. cell phone iphone Blackberry etc. of the outside user. The destination device could also be a central monitoring station .

As part of the set up process a set up technician may use the RSS reader to subscribe to receive notification of changes to one or more of the http documents within files . In this case each time the alarm processor writes a change into one of the files notification of the change and or the http document within the file may be sent to the authorized outside user .

Alternatively the outside user may enter the URL of the http document that the outside user wishes to review through a web browser of the device . In response the web server responds with the http document including the requested status indicator.

In general subscription and access to http documents is determined during set up of the alarm system . Access to the web server is limited to the authorized outside users identified during set up of the system .

As a specific example the system may have access control infrastructure for 3 doors door 1 door 2 and door 3 . Doors 1 and 2 provide access into less secured areas and door 3 is a high security area. As such security personnel may be interested in monitoring the real time alarms and status of only door 3.

In order to monitor only door 3 in a system originally designed to monitor all 3 doors a host application would have had to be installed within the secured area to communicate with the control panel . A user interface application would also have been needed to monitor the status events within the control panel and report those events to authorized users.

In the past it has been difficult to integrate outside access into existing security systems. This difficulty has existed because of the proprietary protocols used in existing alarm panels or because of the non open nature of the application program interfaces APIs of the host applications.

Continuing with the above example assume that the URL address of the web server is http panelService . Assume further that the URL of the devices door 1 door 2 and door 3 is http panelService devices the event URL for retrieving status information regarding changes in status is http panelService events and the action URL for sending commands to the system is http panelService actions. It will be assumed that door 1 has a device identifier ID of DEV1 door 2 has a device ID of DEV2 and door 3 has an ID of DEV3. 

Since the status of the devices is exposed using the REST enabled web server through the URL http panelService devices the status of door 1 can be obtained by entry of the URL http panelService devices devId DEV1 through any web browser or from a small application using the HTTP request response APIs provided through most programming languages. Similarly the status of door 2 can be obtained by entry of the URL http panelService devices devId DEV2 and the status of door 3 can be obtained by entry of the URL http panelService devices devId DEV3. 

Now assume that a valid card swipe through a sensor has an event code of 200 an invalid card swipe has an event code of 201 and the case of an access door being held open has an access code of 202. In the case of the panel having RSS support as described above outside users clients can subscribe to event changes via the URL http panelService events. In this case the occurrence of events are detected by the publication processor and published to authorized users . Event details will be understood by the subscribing user because event details are published along with the event code. If the published event s code is 200 then the client of the authorized user can interpret the event as a Valid Card Swipe and display text indicating this event along with the indicator door 3. 

Actions to be executed by the system can also be accomplished through a web browser of authorized users or a third party HTTP application via the URL http panelService actions with the appropriate parameter. For example to shunt the sensor on door 1 the user may enter the URL command http panelService actions devId DEV1 Action SHUNT. In this case the REST format provides the necessary features for parsing this request command and taking the appropriate action.

In general virtually any third party application can be used by an authorized user to communicate with the panel to request information and execute commands using the standards provided by HTTP REST and RSS. This approach enables the system to be seamlessly integrated with changing reporting requirements.

A specific embodiment of method and apparatus for provide remote access has been described for the purpose of illustrating the manner in which the invention is made and used. It should be understood that the implementation of other variations and modifications of the invention and its various aspects will be apparent to one skilled in the art and that the invention is not limited by the specific embodiments described. Therefore it is contemplated to cover the present invention and any and all modifications variations or equivalents that fall within the true spirit and scope of the basic underlying principles disclosed and claimed herein.

