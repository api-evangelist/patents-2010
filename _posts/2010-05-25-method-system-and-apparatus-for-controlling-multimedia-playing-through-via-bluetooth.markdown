---

title: Method, system and apparatus for controlling multimedia playing through via bluetooth
abstract: A system and method for controlling subtitle switching through Bluetooth are provided. The method includes the following steps: a Bluetooth control device transmits a media control instruction which instructs a Bluetooth multimedia playing device to perform subtitle switching to the Bluetooth multimedia playing device after a Bluetooth connection is established between the Bluetooth control device and the Bluetooth multimedia playing device; the Bluetooth multimedia playing device performs the subtitle switching after receiving the media control instruction, and after switching successfully, it loads the subtitle file which is obtained through switching and plays after combined with a video stream. By adopting the technical scheme of the present invention, it can realize wirelessly and remotely controlling a multimedia player through Bluetooth to load subtitle files freely and switch between a plurality of subtitle files when playing a multimedia video file.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08861923&OS=08861923&RS=08861923
owner: ZTE Corporation
number: 08861923
owner_city: Shenzhen, Guangdong Province
owner_country: CN
publication_date: 20100525
---
The present invention relates to the field of Bluetooth wireless communication and multimedia video playing and in particular to a method system and apparatus for controlling multimedia playing through Bluetooth.

The Bluetooth technology is an open standard of the wireless data and voice transmission which mainly solves the wireless communication problem within short distance and the effective communication distance is generally within 10 meters. The Bluetooth protocol standard is formulated and released by the SIG organization.

According to the different applications of the Bluetooth the standard defines different application framework profiles. Wherein in order to watch video on the Bluetooth media output device it defines the video distribution profile VDP in order to realize the control function conveniently through the Bluetooth control device as well when listening to the stereosound music or watching the video media on the Bluetooth media output device it stipulates the audiovideo remote control profile AVRCP .

In a section of AVRCP 1.4 4.5 Categories it defines the common media playing control command for example play stop pause forward backward etc. The video file will often carry with the subtitle while playing and may provide a plurality of subtitle files in different languages and these subtitle files can be loaded through the media player and displayed on the output interface of the media player synchronously with the audiovideo but the AVRCP does not stipulate the operation command word operation id corresponding to switching different subtitles so that the strong extension control function which the multimedia player itself possesses is unable to be completed through the Bluetooth control device.

The technical problem to be solved by the present invention is to provide a method system and apparatus for controlling subtitle switching through Bluetooth which can realize wirelessly and remotely controlling a multimedia player to perform the subtitle switching through Bluetooth.

In order to solve the above mentioned problem the present invention provides a method for controlling subtitle switching through Bluetooth comprising a Bluetooth control device transmitting a media control instruction which instructs a Bluetooth multimedia playing device to perform subtitle switching to the Bluetooth multimedia playing device after a Bluetooth connection is established between the Bluetooth control device and the Bluetooth multimedia playing device and the Bluetooth multimedia playing device performing the subtitle switching after receiving the media control instruction and after switching successfully loading a subtitle file which is obtained through switching and playing after combined with a video stream.

The step of the Bluetooth control device transmitting a media control instruction which instructs a Bluetooth multimedia playing device to perform subtitle switching to the Bluetooth multimedia playing device comprises setting a value of a reserved field therein as switching subtitle when the Bluetooth control device transmits a pass through forwarding message to the Bluetooth multimedia playing device.

After the step of the Bluetooth multimedia playing device performing the subtitle switching the method further comprises if switching succeeds then transmitting a message of switching success to the Bluetooth control device and if switching fails then transmitting a message of switching failure to the Bluetooth control device.

The present invention also provides a system for controlling multimedia playing through Bluetooth comprising a Bluetooth control device and a Bluetooth multimedia playing device wherein 

the Bluetooth control device comprises a Bluetooth control module configured to transmit a media control instruction which instructs the Bluetooth multimedia playing device to perform subtitle switching to the Bluetooth multimedia playing device after a Bluetooth connection is established between the Bluetooth control device and the Bluetooth multimedia playing device 

the Bluetooth multimedia playing device comprises a Bluetooth controlled module a multimedia playing and controlling module and a multimedia playing output and display module 

the Bluetooth controlled module is configured to control the multimedia playing and controlling module to perform the subtitle switching after receiving the media control instruction 

the multimedia playing and controlling module is configured to perform the subtitle switching and load a switched subtitle file and transmit to the multimedia playing output and display module after combined with a video stream and

The Bluetooth control module is configured to transmit the media control instruction which instructs the Bluetooth multimedia playing device to perform the subtitle switching to the Bluetooth multimedia playing device through the following way setting a value of a reserved field therein as switching subtitle when transmitting a pass through forwarding message to the Bluetooth multimedia playing device.

The Bluetooth controlled module is further configured to perform analyzing after receiving the pass through forwarding message and acquire that the subtitle switching needs to be performed according to the value of the reserved field.

The Bluetooth controlled module is configured to control the multimedia playing and controlling module to perform the subtitle switching by the following way transmitting a message of switching subtitle to the multimedia playing and controlling module or performing the subtitle switching by directly calling an application programming interface function of the multimedia playing and controlling module.

The multimedia playing and controlling module is further configured to transmit a message of operation success to the Bluetooth control device after a switching subtitle operation is successful and transmit a message of operation failure to the Bluetooth control device after the switching subtitle operation fails.

The present invention also provides a Bluetooth control device comprising a Bluetooth control module configured to 

transmit a media control instruction which instructs a Bluetooth multimedia playing device to perform subtitle switching to the Bluetooth multimedia playing device after a Bluetooth connection is established between the Bluetooth control device and the Bluetooth multimedia playing device.

The Bluetooth control module is configured to transmit the media control instruction which instructs the Bluetooth multimedia playing device to perform the subtitle switching to the Bluetooth multimedia playing device through the following way setting a value of a reserved field therein as switching subtitle when transmitting a pass through forwarding message to the Bluetooth multimedia playing device.

In conclusion the present invention provides a method system and apparatus for controlling multimedia playing through Bluetooth which can realize wirelessly and remotely controlling a multimedia player through Bluetooth to load the subtitle files freely and switch between a plurality of subtitle files when playing a multimedia video file.

In order to solve the above mentioned problem the present invention provides a Bluetooth control device which is based on the protocol standard and extends the customized field of the manufacturer reserved by the protocol so that the Bluetooth control device is able to transmit the SwitchSub signaling extended from the protocol frame to the multimedia playing device with the AVRCP function and the multimedia player is controlled wirelessly and remotely through the Bluetooth which realizes loading the subtitle files freely and switching between a plurality of subtitle files when playing the multimedia video file.

The present embodiment provides a system for controlling subtitle switching through Bluetooth. As shown in the system includes a Bluetooth control device and a Bluetooth multimedia playing device wherein 

the Bluetooth multimedia playing device includes a Bluetooth controlled module a multimedia playing and controlling module and a multimedia playing output and display module 

the Bluetooth control module is configured to transmit a media control instruction which instructs the Bluetooth multimedia playing device to perform subtitle switching to the Bluetooth multimedia playing device after a Bluetooth connection is established between the Bluetooth control device and the Bluetooth multimedia playing device 

the Bluetooth controlled module is configured to control the multimedia playing and controlling module to perform the subtitle switching after receiving the media control instruction

the multimedia playing and controlling module is configured to perform the subtitle switching and load a switched subtitle file and transmit to the multimedia playing output and display module after combined with a video stream and

The Bluetooth control module transmitting the media control instruction which instructs the Bluetooth multimedia playing device to perform the subtitle switching to the Bluetooth multimedia playing device refers that the Bluetooth control module sets a value of a reserved field therein as switching subtitle when transmitting a pass through forwarding message to the Bluetooth multimedia playing device .

The Bluetooth controlled module performs analyzing after receiving the pass through forwarding message and acquire that the subtitle switching needs to be performed according to the value of the reserved field.

The Bluetooth controlled module controlling the multimedia playing and controlling module to perform the subtitle switching refers that the Bluetooth controlled module transmits a message of switching subtitle to the multimedia playing and controlling module or performing the subtitle switching by directly calling the API function of the multimedia playing and controlling module .

The multimedia playing and controlling module is further configured to transmit a message of operation success to the Bluetooth control device after the switching subtitle operation is successful and transmit a message of operation failure to the Bluetooth control device after the switching subtitle operation fails.

The present embodiment provides a method for controlling multimedia playing through Bluetooth which makes it possible to remotely control the Bluetooth video playing device through the Bluetooth control device. The method for controlling switching and loading the subtitle is shown in and the method includes the following steps 

in step as a precondition a Bluetooth connection between the Bluetooth control device A and the Bluetooth multimedia playing device B has already been established successfully and the video stream has already begun to be played 

in step the user operates on the Bluetooth control device A and performs the switching subtitle operation 

in step the Bluetooth control module CT of the device A sends the extended instruction of the pass through forwarding message PASS THROUGH based on the protocol standard through the Bluetooth AVRCP Profile that is customized field of the manufacturer Vendor Unique . The action filled in the extended instruction is defined as switching subtitle SwitchSub and a reserved field therein is set as switching subtitle for example it can set the field Vendor Unique id as a preset value to indicate performing the subtitle switching. That preset value can be but not limited to 0x03 as long as that the value is appointed through the protocol to indicate the switching subtitle instruction and when the multimedia playing device reads that field it can acquire that that field indicates the switching subtitle instruction and perform the subtitle switching the filling format of that extended instruction is shown in Table 1 

in step the Bluetooth controlled module TG of the device B receives the SwitchSub signaling from the device A and it analyzes the SwitchSub signaling and acquires that it needs to perform the subtitle switching according to the value of the field Vendor Unique id therein 

in step TG transmits the message of switching subtitle to the multimedia playing and controlling module of the device B or it calls the API function of the corresponding multimedia playing and controlling module which is called directly by the TG module 

in step the multimedia playing and controlling module of the device B performs the subtitle switching operation like the user directly performs switching subtitle operation on the media player which selects in a plurality of subtitle files and performs the cycle switching and loading between the subtitle files 

in step A the multimedia playing and controlling module fails to perform the SwitchSub operation and the message of performing operation failure is returned to the TG 

in step B the multimedia playing and controlling module performs the SwitchSub operation successfully and the message of performing operation success is returned to the TG 

in step A the TG after receiving the message of performing operation failure transmits the extended instruction VendorUniqueResponse of the PASS THROUGH based on the protocol standard to the device A and the filling format of the extended instruction is shown in Table 2 wherein the Response field is filled as 0xA REJECTED that is the switching fails and the whole procedure ends 

in step B the TG after receiving the message of performing operation success transmits the extended instruction VendorUniqueResponse of the PASS THROUGH based on the protocol standard to the device A and the filling format of the extended instruction is shown in the above Table 2 wherein the Response field is filled as 0x9 ACCEPTED that is the switching is successful and the step is executed 

in step the multimedia playing and controlling module loads the subtitle file which is obtained through switching and sends to the multimedia playing output and display module after combined with the video stream 

The above description is only the preferred embodiments of the present invention and is not intended to limit the present invention. For those skilled in the art the present invention can have various modifications and variations. All of modifications equivalents variations and so on without departing from the spirit and essence of the present invention should be included in the scope of the appended claims of the present invention.

The present invention provides a system and method for controlling subtitle switching through Bluetooth which can realize wirelessly and remotely controlling a multimedia player through Bluetooth to load the subtitle files freely and switch between a plurality of subtitle files when playing a multimedia video file.

