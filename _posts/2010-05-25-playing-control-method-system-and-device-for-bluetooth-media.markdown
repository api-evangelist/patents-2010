---

title: Playing control method, system and device for Bluetooth media
abstract: This present invention discloses a method, system and device for a play control of a Bluetooth media. The method includes: sending a JumpTo media play control command to a Bluetooth play device through an extended protocol message by a Bluetooth control device; performing the play control on a played media according to the JumpTo media play control command by the Bluetooth play device. In the present invention, the extension is performed on the protocol reserved manufacturer custom field, which enables the Bluetooth control device to send the extended media play control command in the protocol architecture to the Bluetooth play device, thereby implementing the accurate locating play control for a played media file.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08731467&OS=08731467&RS=08731467
owner: ZTE Corporation
number: 08731467
owner_city: Shenzhen, Guangdong Province
owner_country: CN
publication_date: 20100525
---
The present invention relates to a field of Bluetooth wireless communication and in particular to a method for a play control of a Bluetooth media and a system and device thereof.

Bluetooth technology is an open standard of wireless data and voice transmission mainly used for solving a wireless communication problem in a short distance. Its effective communication distance is commonly within 10 meters. The Bluetooth protocol standard is established and issued by the Bluetooth special interest group SIG .

According to various application modes of the Bluetooth various profiles are defined in the standard. Wherein in order to expediently implement the control for the played media through the Bluetooth control device when listening in stereo music or watching video media on the Bluetooth media output device the standard specifies the audio video remote control profile AVRCP . The common media play control instructions are defined in the AVRCP including Play Stop Pause Forward Backward etc.

At present the multimedia player already enters in the digital age and the multimedia data sources for playing are mainly digital files rather than the audiotapes videotapes etc. of analog format in the early years. The present media player also provides more much powerful much convenient control operation instructions to implement much better audio visual enjoyment. While there is no corresponding operation command word Operation id defined in the AVCRP such as jumping to somewhere to start play etc. So that the powerful control functions which are provided with the media player itself cannot be achieved through the present Bluetooth control device.

The technical problem that the present invention will solve is to provide a method system and device for a play control of a Bluetooth media and an accurate locating play control is implemented for a multimedia file through an extended message command.

To solve the above problem the present invention provides a method for a play control of a Bluetooth media comprising 

sending a JumpTo media play control command to a Bluetooth play device through an extended protocol message by a Bluetooth control device and

performing the play control for a played media according to the JumpTo media play control command by the Bluetooth play device.

A trigger condition of sending the JumpTo media play control command by the Bluetooth control device includes 

The extended protocol message is an extended instruction a manufacturer custom operation Vendor Unique of a PASS THROUGH which is based on a protocol standard a filling action in the extended instruction is defined as JumpTo and a carried time parameter is the time to jump to play.

The step of performing the play control for the played media according to the JumpTo media play control command by the Bluetooth play device comprises 

a Bluetooth controlled terminal after receiving the JumpTo media play control command analyzing the JumpTo media play control command and the time parameter carried by the JumpTo media play control command and sending the analyzed time parameter directly to a media player or directly calling an application programming interface of the media player with the time parameter acting as an input parameter and

the media player from the time specified by the time parameter sending media data to a Bluetooth media output module to implement the JumpTo play control for the played media.

checking validity of the time parameter and performing the step of sending the media data to the Bluetooth media output module only if the time parameter is valid by the media player.

The present invention further provides a system for a play control of a Bluetooth media comprising a Bluetooth control device and a Bluetooth play device wherein 

the Bluetooth control device is configured to send a JumpTo media play control command to the Bluetooth play device through an extended protocol message and

the Bluetooth play device is configured to perform the play control for a played media according to the JumpTo media play control command.

The Bluetooth control device comprises a Bluetooth master control terminal and the Bluetooth master control terminal is configured to send the JumpTo media play control command if a following trigger condition is satisfied 

Further the Bluetooth play device comprises a Bluetooth controlled terminal a media player and a Bluetooth media output module wherein 

the Bluetooth controlled terminal is configured to after receiving the JumpTo media play control command sent by the Bluetooth master control terminal analyze the JumpTo media play control command and a time parameter carried by the JumpTo media play control command and send the analyzed time parameter directly to the media player or directly call an application programming interface of the media player with the time parameter acting as an input parameter and

the media player is configured to from the time specified by the time parameter send media data to the Bluetooth media output module to implement the JumpTo play control for the played media.

the checking module is configured to check validity of the time parameter and send the media data to the Bluetooth media output module only if the time parameter is valid.

The extended protocol message is an extended instruction a manufacturer custom operation of a PASS THROUGH which is based on a protocol standard a filling action in the extended instruction is defined as JumpTo and a carried time parameter is the time to jump to play.

The Bluetooth media output module is configured to send the media data to the Bluetooth control device and

the Bluetooth control device further comprises a Bluetooth media display module and the Bluetooth media display module is configured to receive the media data sent by the Bluetooth media output module and complete the display of the multimedia.

The present invention further provides a Bluetooth control device comprising a Bluetooth master control terminal wherein the Bluetooth master control terminal is configured to send a JumpTo media play control command to a Bluetooth play device through an extended protocol message.

The Bluetooth master control terminal is configured to send the JumpTo media play control command if a following trigger condition is satisfied 

The extended protocol message is an extended instruction a manufacturer custom operation of a PASS THROUGH which is based on a protocol standard a filling action in the extended instruction is defined as JumpTo and a carried time parameter is the time to jump to play.

The device further comprises a Bluetooth media display module and the Bluetooth media display module is configured to receive the media data sent by the Bluetooth play device and complete the display of the multimedia.

An accurate play control can be performed for the Bluetooth play device as required through the technical scheme of the present invention.

The core idea of the present invention is on a Bluetooth control device such as a Bluetooth multimedia output device the extension is performed for the manufacturer custom field reserved in protocol based on the protocol standard which enables the Bluetooth control device to send the media play control command extended in the protocol architecture to the Bluetooth play device such as the JumpTo signaling used for implementing the accurate locating play control etc. Thereby the Bluetooth wireless remote control media player can implement the accurate locating play control for the multimedia file and the powerful control function provided with the media player itself can be implemented.

Based on the above idea the play control method of the media player provided by the present invention adopts below technical scheme 

A Bluetooth control device sends a JumpTo media play control command to a Bluetooth play device through an extended protocol message 

The Bluetooth play device performs a play control for a played media according to the media play control command.

Further the extended protocol message is an extended instruction Vendor Unique id a manufacturer custom operation of a PASS THROUGH which is based on a protocol standard. The filling action in the extended instruction is defined as JumpTo and the carried time parameter is the time to jump to play.

As shown in the present invention provides a play control system of a Bluetooth media including a Bluetooth control device and a Bluetooth play device . Wherein 

the Bluetooth control device is used for sending a JumpTo media play control command to the Bluetooth play device through an extended protocol message 

the Bluetooth play device is used for performing the play control for a played media according to the JumpTo media play control command.

Further the Bluetooth control device includes a Bluetooth master control terminal whose role is a controller CT for short usually being a onboard Bluetooth device a handheld display device with a Bluetooth function etc. and a Bluetooth media display module . The Bluetooth play device includes a Bluetooth controlled terminal whose role is a target TG for short usually being a cell phone a computer with the Bluetooth function an audio and video play device etc. a media player and a Bluetooth media output module .

The Bluetooth controlled terminal after receiving the media play control command sent by the Bluetooth master control terminal analyzes the control command and the time parameter carried therein and sends the analyzed time parameter directly to the media player. Or the time parameter is taken as an input parameter to directly call an application programming interface API which the media player already has 

The media player from the time specified by the time parameter according to the time parameter sends media data to the Bluetooth media output module to implement the play control for the played media and returns the operation result to the Bluetooth controlled terminal . The Bluetooth controlled terminal returns a VendorUniqueResponse a manufacturer custom operation response message to the Bluetooth mater control terminal 

Further the Bluetooth media output module is used for sending media streaming data to the Bluetooth media display module of the Bluetooth control device 

The Bluetooth media display module is used for receiving the media streaming data sent by the Bluetooth media output module and completing the display of the multimedia.

Below taking the JumpTo media play control command as an example the implementing of the technical of the present invention is further illustrated in details. As shown in the play control flow of the media player according to an embodiment of the present invention mainly includes following steps 

Step as a precondition the Bluetooth connection between the Bluetooth multimedia output device and the Bluetooth multimedia play device is established successfully the media channel is open and playing the multimedia through the Bluetooth is in ready state 

Step performing the operation on the CT the time point required to jump to play is input or the process bar is directly slid to the time point required to jump to play requiring to perform the jump to . . . to play operation 

Step the CT sends out the extended instruction Vendor Unique the manufacturer custom field of the PASS THROUGH which is based on the protocol standard through the Bluetooth AVRCP profile. The filling action in the extended instruction is defined as JumpTo. A reserved field therein is set as JumpTo. For example the filed Vendor Unique id can be set as a preset value representing JumpTo. The preset value can be but is not limited to 0x01. When reading the field the multimedia play device knows that the field represents the JumpTo instruction and then it performs the JumpTo. The carried parameter is the above time point input by a user using but not limited to 0x00 to represent the time parameter of JumpTo in the extended instruction. Wherein the 3 time parameters hour minute and second are stored in the 10to 12bytes respectively. The filling form of the extended instruction is as table 1 

Step the TG receives the JumpTo signaling from the CT and analyzes the JumpTo signaling and the carried time parameter 

Step the TG sends the corresponding message to the media player according to the JumpTo signaling or calls the corresponding media player API functions 

Step the media player checks the parameter validity. For example the checking for the parameter validity can be implemented through a checking module in the media player. Step is processed if the parameter is invalid while step is processed if the parameter is valid 

Step the media player returns operation performing failure to the TG. After receiving the performing result the TG sends out the extended instruction VendorUniqueResponse the manufacturer custom operation response of the PASS THROUGH which is based on the protocol standard to the CT. The filling form of the extended instruction is as table 2 wherein the Response field is filled as 0xA REJECTED and the whole flow ends 

Step the media player performs the JumpTo operation successfully and returns an operation performing success result to the TG. The TG sends out the extended instruction VendorUniqueResponse of the PASS THROUGH which is based on the protocol standard to the CT. The filling form of the extended instruction is as table 2 wherein the Response field is filled as 0x9 ACCEPTED 

Step the media player sends the media data to the Bluetooth media output module from the specified time point 

Step the Bluetooth media output module sends the media steaming data to the Bluetooth media display module of the Bluetooth multimedia output device through the Bluetooth completes the multimedia display on the Bluetooth multimedia output device and finishes the whole locating play flow.

Table 1 is a protocol data unit PDU according to an embodiment of the present invention. The PDU is a data frame structure defined in the normalized file by the Bluetooth standard representing the manufacturer custom operation VendorUnique data frame.

Wherein the byte to the byte are all from normalized definition which can be filled in according to the actual situation 

The byte to the byte are the reserved manufacturer custom field operation word Vendor unique id in the standard. Its extension definition is defined in the embodiment of the present invention when the value of the field is 0x01 it represents jump to . . . to play the JumpTo operation. Certainly the value of the Vendor unique id can be any value as long as it represents the JumpTo control instruction when presetting the value.

The byte to the byte are used for representing the play time of jumping to the multimedia file and the hour minute and second are stored in the 3 bytes respectively.

Table 2 is a protocol data unit PDU according to an embodiment of the present invention. The PDU is a data frame structure defined in the normalized file by the Bluetooth standard representing the manufacturer custom operation response VendorUniqueResponse data frame.

Wherein the byte to the byte are all from normalized definition which can be filled in according to the actual situation 

The byte to the byte are the reserved manufacturer custom field operation word Vendor unique id in the standard. Its extension definition is defined in the embodiment of the present invention when the value of the field is 0x01 it represents the response to the operation jump to . . . to play the JumpTo operation. Also certainly the value of the Vendor unique id can be any value as long as it represents the JumpTo control instruction when presetting the value.

The above description is only the preferred embodiments of the present invention and is not intended to limit the scope of the present invention. The present invention can have a variety of other embodiments. Those skilled in the art can make the corresponding modifications and variations according to technical scheme and the conception of the present invention without departing from the spirit and essence of the present invention. And all of these modifications or the variations should be embodied in the scope of the appending claims of the present invention.

The accurate play control can be performed as required for the Bluetooth play device through the technical scheme of the present invention.

