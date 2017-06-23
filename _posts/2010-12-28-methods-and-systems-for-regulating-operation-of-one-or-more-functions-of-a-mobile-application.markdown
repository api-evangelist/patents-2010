---

title: Methods and systems for regulating operation of one or more functions of a mobile application
abstract: Various embodiments include a method for regulating operation of mobile applications executing on a nomadic device. Signals for determining a speed of travel may be received at the nomadic device. The speed may be determined based on the one or more signals. If the determined speed exceeds a speed threshold, a speed restriction flag may be set and one or more functions of the mobile applications may be restricted. If, after setting the speed restriction flag, a speed cannot be determined, the application functions may be continually restricted until a speed can be determined.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08560739&OS=08560739&RS=08560739
owner: Ford Global Technologies, LLC
number: 08560739
owner_city: Dearborn
owner_country: US
publication_date: 20101228
---
Various embodiments relate to regulating operation of one or more functions during use of a mobile application. In some embodiments the functions of the mobile application may be restricted when a nomadic device on which the mobile application is executing is determined to be moving. In some embodiments the nomadic device may be in a vehicle.

Various examples of tools that block mobile phone functionality prevent mobile phone use during vehicle movement. These tools typically disable the touchscreen or the keypad of the mobile phone.

As one example U.S. Publication No. 2010 0216509 to Riemer et al. discloses a portable device which includes a safety feature that prevents some forms of use when the device is moving. The device may detect its speed or movement compare that to a threshold and provide a response or blocking function upon exceeding that threshold. The device may be a cell phone configured to disable transmission and reception of voice text conceal its display screen and disable incorporated features and functions if the cell phone is moving faster than walking speed or the movement is uncharacteristic of walking. The blocking function may be partially overridden based on a safety policy which can be managed and customized. The introduction of hands free devices may serve to override a blocking function and enable other functions.

Other examples include cell phone blocking products offered by TURN OFF THE CELL PHONE LLC. This product automatically turns off the cell phone when the user is driving. It eliminates all phone activity while driving such as phone calls text messaging emails web surfing and others. Notifications are sent to safety managers or parents confirming that the phone is not being used while driving.

One aspect includes a computer implemented method for regulating operation of one or more mobile applications. The method may include receiving one or more signals on a nomadic device for determining a speed at which the nomadic device is travelling. The speed at which the nomadic device is travelling may be determined based on the one or more signals.

If the determined speed exceeds a speed threshold a speed restriction flag may be set and one or more functions of the mobile applications may be restricted. The mobile applications may be executing on the nomadic device.

Further if after setting the speed restriction flag a speed cannot be determined the functions of the one or more applications may be continually restricted until a speed can be determined.

In some embodiments if the speed cannot be determined and the speed restriction flag is not set the one or more functions mobile applications may be enabled until a determination is made that the determined speed exceeds the speed threshold.

In another aspect which may include a computer implemented method for regulating operation of one or more mobile applications the nomadic device may monitor for one or more signals for determining a speed of travel of the nomadic device. If a speed cannot be determined it may be determined if inputs to a mobile application which may be executing on the nomadic device are restricted or unrestricted.

If the inputs restricted the one or more inputs to the application may continually be restricted until a speed can be determined. If the inputs are unrestricted the inputs to the application may be permitted until a determination is made that a determined speed of the nomadic device exceeds one or more speed thresholds.

In another aspect system includes a nomadic device and a mobile application. The mobile application may be executing on the nomadic device. Further the mobile application may have instructions for receiving signals for determining a speed of travel and determining the speed.

If the speed exceeds a speed threshold further instructions may include setting a speed restriction flag and restricting functions of the mobile application.

If after setting the speed restriction flag a speed cannot be determined the instructions may further include continuing the restricting until a speed can be determined.

In some embodiments the nomadic device may be in a vehicle. As such the instructions of the mobile application may be executed if one vehicle occupant is in the vehicle.

In some embodiments further instructions may include receiving instructions to override restricting inputs to the mobile application. The override may be based on a presence of more than one vehicle occupant.

These and other aspects will be better understood in view of the attached drawings and following detailed description of the invention.

The use of mobile applications e.g. applications on a mobile phone is increasingly becoming more pervasive. Mobile applications are available for almost any use such as games social networking news word processing and navigation.

One common example of a mobile application particularly used by owners of a vehicle without a factory installed navigation system is a navigation mobile application. These navigation mobile applications may be as robust as factory installed navigation systems but at a much lower cost. Many times these applications are even less expensive than retail portable navigation systems. Accordingly many owners of a mobile phone typically a smartphone may have at least one navigation application downloaded to the device.

However most if not all mobile applications are unnecessary for communication. Further these mobile applications can be distracting while in a vehicle. While many vehicles today have computing systems that may block mobile phone use or if the vehicle is not outfitted with a computing system software may be downloaded to a mobile phone to block its use entirely blocking cell phone usage may become inconvenient as the phone may still be necessary for communication. It may be helpful to block the use of such mobile applications rather than use of the mobile phone entirely.

Detailed embodiments of the invention are disclosed herein. However it is to be understood that the disclosed embodiments are merely exemplary of an invention that may be embodied in various and alternative forms. Therefore specific functional details disclosed herein are not to be interpreted as limiting but merely as a representative basis for the claims and or as a representative basis for teaching one skilled in the art to variously employ the present invention.

Additionally the disclosure and arrangement of the figures is non limiting. Accordingly the disclosure and arrangement of the figures may be modified or re arranged to best fit a particular implementation of the various embodiments of the invention.

In the illustrative embodiment 1 shown in a processor controls at least some portion of the operation of the vehicle based computing system. Provided within the vehicle the processor allows onboard processing of commands and routines. Further the processor is connected to both non persistent and persistent storage . In this illustrative embodiment the non persistent storage is random access memory RAM and the persistent storage is a hard disk drive HDD or flash memory.

The processor is also provided with a number of different inputs allowing the user to interface with the processor. In this illustrative embodiment a microphone an auxiliary input for input a USB input a GPS input and a BLUETOOTH input are all provided. An input selector is also provided to allow a user to swap between various inputs. Input to both the microphone and the auxiliary connector is converted from analog to digital by a converter before being passed to the processor. Although not shown numerous of the vehicle components and auxiliary components in communication with the VCS may use a vehicle network such as but not limited to a CAN bus to pass data to and from the VCS or components thereof .

Outputs to the system can include but are not limited to a visual display and a speaker or stereo system output. The speaker is connected to an amplifier and receives its signal from the processor through a digital to analog converter . Output can also be made to a remote BLUETOOTH device such as PND or a USB device such as vehicle navigation device along the bi directional data streams shown at and respectively.

In one illustrative embodiment the system uses the BLUETOOTH transceiver to communicate with a user s nomadic device e.g. cell phone smart phone PDA or any other device having wireless remote network connectivity . The nomadic device can then be used to communicate with a network outside the vehicle through for example communication with a cellular tower . In some embodiments tower may be a WiFi access point.

Exemplary communication between the nomadic device and the BLUETOOTH transceiver is represented by signal .

Pairing a nomadic device and the BLUETOOTH transceiver can be instructed through a button or similar input. Accordingly the CPU is instructed that the onboard BLUETOOTH transceiver will be paired with a BLUETOOTH transceiver in a nomadic device.

Data may be communicated between CPU and network utilizing for example a data plan data over voice or DTMF tones associated with nomadic device . Alternatively it may be desirable to include an onboard modem having antenna in order to communicate data between CPU and network over the voice band. The nomadic device can then be used to communicate with a network outside the vehicle through for example communication with a cellular tower . In some embodiments the modem may establish communication with the tower for communicating with network . As a non limiting example modem may be a USB cellular modem and communication may be cellular communication.

In one illustrative embodiment the processor is provided with an operating system including an API to communicate with modem application software. The modem application software may access an embedded module or firmware on the BLUETOOTH transceiver to complete wireless communication with a remote BLUETOOTH transceiver such as that found in a nomadic device .

In another embodiment nomadic device includes a modem for voice band or broadband data communication. In the data over voice embodiment a technique known as frequency division multiplexing may be implemented when the owner of the nomadic device can talk over the device while data is being transferred. At other times when the owner is not using the device the data transfer can use the whole bandwidth 300 Hz to 3.4 kHz in one example .

If the user has a data plan associated with the nomadic device it is possible that the data plan allows for broad band transmission and the system could use a much wider bandwidth speeding up data transfer . In still another embodiment nomadic device is replaced with a cellular communication device not shown that is installed to vehicle . In yet another embodiment the ND may be a wireless local area network LAN device capable of communication over for example and without limitation an 802.11g network i.e. WiFi or a WiMax network.

In one embodiment incoming data can be passed through the nomadic device via a data over voice or data plan through the onboard BLUETOOTH transceiver and into the vehicle s internal processor . In the case of certain temporary data for example the data can be stored on the HDD or other storage media until such time as the data is no longer needed.

Additional sources that may interface with the vehicle include a personal navigation device having for example a USB connection and or an antenna a vehicle navigation device having a USB or other connection an onboard GPS device or remote navigation system not shown having connectivity to network .

Further the CPU could be in communication with a variety of other auxiliary devices . These devices can be connected through a wireless or wired connection. Auxiliary device may include but are not limited to personal media players wireless health devices portable computers and the like.

Also or alternatively the CPU could be connected to a vehicle based wireless router using for example a WiFi transceiver. This could allow the CPU to connect to remote networks in range of the local router .

The mobile application may be installed on a nomadic device which as described above with respect to may communicate with the VCS not shown in . For example in scenarios where the VCS does not include a navigation system ND having the mobile application may be used for navigation while the VCS may be used for for example hands free communication.

Of course the ND does not necessarily need to communicate with the VCS for purposes of operating the mobile application . For example the mobile application and the various embodiments of the mobile application as described herein may be operable on the ND as a standalone device in or out of the vehicle.

The mobile application may be capable of receiving touch based inputs e.g. from a keypad and or a touchscreen and or voice inputs. Further information may be output by the application visually and or audibly.

In some embodiments the TDI application as represented by the dashed lines may be executing on the remote server and operated from the ND via an Internet connection e.g. via network . In this case the application may be an application programming interface API for operating the mobile application . Further details of this remote operation of the mobile application will be described below. Unless otherwise indicated for purposes of simplicity the details of the various embodiments will be described in the context of the mobile application executing on the ND .

The TDI application may provide various navigation related operations when executing on the ND or the remote server s . As non limiting examples the operations may include but are not limited to navigation information and maps traffic maps with speed flow and incident data time s to leave and estimated time of arrival predictive traffic traffic forecast crowd sourced traffic data location search storing locations and traffic maps and alternatives.

The mobile application may be downloaded to the nomadic device and or may be accessible via a web based application. Details of the application download process will be described with respect to .

Operating remotely from the ND one or more systems storing TDI data may be used by the TDI application . The system s may store mapping information traffic information and destination information including but not limited to POIs and reverse geocoded destination information . In some embodiments the TDI system may store destination and or location information for the user. Of course system may comprise multiple systems and is illustrated as a single system for illustration.

Additionally operating remotely from the ND may be a user information system . The user information system may store information about the mobile application user including but not limited to user identification information e.g. name address and the like login information vehicle identification information and mobile identification . In some embodiments subscription information for the service may be stored in the system . In some embodiments the destination and location information may be stored in user information system or if stored in the TDI system s associated with a user via the user information system . In some embodiments the locations and destinations may be synchronized and stored with previously saved destinations and locations.

In one embodiment as described above the mobile application may be installed on the remote server s from which the application may be executing. When executing from the server s the mobile application via remote server may communicate with the TDI information system and communicate with the user information system . When operating the mobile application from the ND an API may be installed on the ND . The API may be downloaded from an application store which may or may not be remote system . The information exchange and operation of the mobile application may occur over the Internet.

In an alternative embodiment when the mobile application is executing on the ND the remote server system s may be a system from which the mobile application is downloaded e.g. via an Internet connection . The mobile application may be downloaded and installed directly from the ND or downloaded to memory e.g. a USB drive or PC and transferred for installation to the ND . In some embodiments the remote system s may be a mobile application store hosted by for example the OEM or a third party.

Once installed on the ND the application may be started and loaded on the ND block . The application may be started and loaded by selecting one or more graphical commands e.g. an icon representing the application selecting the application from a menu and or using audible commands.

When the application is executing remotely use of the application may be enabled from a website. Accordingly the application may be loaded when the website is visited.

The user s login credentials may be requested block . An example of a login credential may include a username and password. The user may or may not have login credentials. If the user does not have login credentials the credentials may be created block . The login credentials may be created by the user and or provided by an OEM. The login credentials may be created and or obtained from the OEM electronically e.g. from a website . Once created the credentials may be stored e.g. at user information system block .

When the user has login credentials the credentials may be received through user entry when requested block . Accordingly the credentials may be received at the ND block .

In some embodiments to use the mobile application the user may need a subscription to the service from the OEM. The subscription may have a time limit. As a non limiting example the subscription may be an annual subscription. Accordingly the subscription status may be verified block . If the user does not have a subscription e.g. it was never created or it has expired a subscription request may be received from the user e.g. at the ND block . The subscription may be received and stored in the user information system block . The subscription may be established electronically or by contacting the OEM or a dealership to obtain a subscription.

When the user has a subscription the application may be operated from the ND block . As will be described in detail below as part of operating the application one or more features of the application may be blocked in order to restrict use of the application while the vehicle is in operation. The locking feature of the application may be activated based on a driving status of the vehicle . Various embodiments of the locking process will be described below with the remaining figures.

The ND may be configured with a device that may be used in calculating vehicle speed. Such devices may include but are not limited to a GPS receiver an accelerometer or a gyro. For purposes of illustration are described in the context of using a GPS receiver.

The ND may monitor for one or more speed detection signals e.g. GPS signals block in order to detect movement of the vehicle and therefore its speed. In the case where a GPS receiver is used for example the signals may be detected from a satellite transmitting GPS signals. Accordingly in order to block use of the application the speed of the vehicle may be detected from the signal s if available block . If the signal s are available the vehicle speed may be calculated based on information obtained from the GPS signals block .

As part of determining the speed the application may use the ND s clock or a GPS clock to measure a passage of one or more periods of time. The speed may thus be determined based on a change in position within one or more periods of time. This determination may be made periodically. For example a period may be based on seconds or minutes or variations of seconds or minutes. By way of example and not limitation the position of the ND may be measured every X seconds. Additionally or alternatively the position may be measured during one or more intervals of time. For example and without limitation the position may be measured during one or more X second intervals.

At a certain time the GPS position of the ND may be determined block . When the time period for determining the position of the ND has been reached a determination may be made if the ND has changed position block based on the GPS information from the ND . If a change has not been detected the application may receive the GPS position from the ND and continue to measure the passage of time. Once a change in position is detected a position at a first time may be received and recorded block . Further a position at a second time may be received and recorded block . The change in position e.g. based on change in latitude and longitude at or within the time periods may be determined. Based on this determination the speed of the vehicle may be determined block .

In some embodiments the speed may be determined based on a distance traveled and one or more periods of time. Accordingly based on the GPS information from the ND a distance traveled over a period of time may be determined. Based on this determination the speed may be detected. Of course other methods of detecting speed may be used without departing from the scope of the invention.

Referring back to based on the calculated speed it may be determined if the speed is above a speed threshold block . The speed threshold may define when to restrict one or more functions for using the mobile application . Restricting functions may include locking one or more input controls of the ND and or restricting input recognition by the application . As a non limiting example if the ND includes a touchscreen display or a keypad the display or keypad may be blocked from use. As another non limiting example the touchscreen and or keypad may be unlocked but inputs may not be recognized or received by the application .

In some embodiments select input controls may be locked. For example and without limitation the display and or keypad may be locked but voice input may be unlocked. As another example voice inputs may be recognized but not inputs from the display and or keypad. As another example the application may provide output however input may be restricted.

Further the ND may be otherwise operable when the speed threshold is exceeded. For example when the application is executing phone calls may be received and placed text messages exchanged and connectivity to the Internet unlocked. Accordingly the mobile application may include logic for restricting functionality with respect to input and or output functions on the ND or the VCS for using the application . However other functions of the ND or the VCS may be available when the mobile application is executing.

If the calculated speed is less than the speed threshold block application operation may be unrestricted block also referred to herein as the application being unlocked . The application via the ND may continue monitoring for GPS signals in order to determine vehicle speed.

In some embodiments there may be multiple speed thresholds. Further each speed threshold may cause different and additional functions of the mobile application to be restricted. As an example select functions may be restricted at low speeds while all functions may be restricted at high speeds. Of course there may be a range of thresholds and a range of functions that may be restricted.

If the speed is greater than the speed threshold block one or more flags also referred to herein as a restriction flag may be set by the application indicating that the speed is greater than the speed threshold block . A non limiting example of a speed threshold that may set the restriction flag may be 5 mphs. Of course any speed may be used without departing from the scope of the invention. Once the flag is set operation of the application may be restricted block hereinafter referred to as the application being locked .

The application may continue to monitor the speed via the ND so long as speed detection signals e.g. GPS signals are available block . Accordingly the application may be locked when the speed is greater than the threshold speed as described above.

In some instances the ND may lose the speed detecting signals. For example the GPS receiver in the ND may lose GPS signals transmitted from the GPS satellite. In cases where the restriction flag is already set block even if the GPS signal is lost and therefore speed cannot be detected the application may be locked block . Once the signals are available based on the monitoring the application may be unlocked for user operation if the speed is determined to be less than the speed threshold.

In some embodiments when the signals are not available block a determination may be made if the device for detecting speed such as a GPS receiver is on. Operation of the application will not be permitted without an active speed detection device. Accordingly the application may automatically lock when the GPS receiver is determined to be turned off block . In some embodiments in cases where the application may be otherwise unlocked e.g. the speed is less than the threshold the application may be locked if the GPS receiver is deactivated.

The restriction flag may be reset after the application is shut down and restarted. At application startup the restriction flag may not be set block . In this case the application may be unlocked block . The application may be unlocked until speed is detected and the restriction flag is set. However if the application is unlocked before the signals are lost but the restriction flag was previously set the application may be locked from user operation block .

In some embodiments regulating application operation may be based on the presence of one or more conditions. Non limiting non exhaustive example of such conditions may include the presence of one or more passengers in the vehicle as determined e.g. from the seat weight sensors or voice recognition and the presence of one or more paired nomadic device.

As an example of a conditional determination if at least one additional passenger is detected the application may be unlocked even if the speed is greater than the speed threshold. Alternatively if it is determined that at least one additional passenger is in the vehicle a speed determination as illustrated in block may not be performed at all. In some embodiments a flag or other identifier may be set by the application indicating that the application is unlocked.

In some embodiments the presence of one or more additional passengers may be determined by the VCS . The information identifying the presence of more than one passenger may be transmitted to the mobile application from the VCS . The identifying information may be for example binary information a flag or the like. Additionally in some embodiments the number of passengers may be provided.

In some embodiments the conditional determination may be made based on the satisfaction of multiple conditions. As one non limiting example the application may be unlocked notwithstanding the speed being greater than the threshold if there is more than one passenger detected based on information from the seat weight sensor and there is at least on additional paired nomadic device.

Additionally a timeout period may be monitored during which the application may be locked block . During this time the user may be restricted from operating application functions as described above. When the timeout period has elapsed the application may be unlocked block .

In some embodiments the unlock timeout period may be determined based on an estimated time to input information to the application . The estimated time may be predetermined by the OEM. Further the timeout period may be measured from when an input defining an instruction for the application is received by the application . As a non limiting example it may be determined by the OEM that a user takes an average of X seconds to input a destination as a POI. Accordingly when inputting a POI the timeout period may be measured at X seconds from the time that the user inputs instructions to enter a destination as a POI.

In some embodiments the estimated time s may be based on the type of information. As a non limiting example if the user is inputting a POI as a destination the timeout period may be shorter than a timeout period for inputting a destination as an address.

In some embodiments the restriction based on timeout periods may be used in conjunction with the operation restriction based on speed. As a non limiting example the application may be locked when the first of the speed threshold is exceeded or the timeout period has elapsed. As another example the application may be unlocked during the unlock timeout period block unless the speed threshold is exceeded. Of course other combinations of the timeout restriction and the speed restriction are contemplated.

In some embodiments the user may override the operation restrictions e.g. inputting an override command . In some embodiments the override may occur automatically when more than one passenger is determined to be in the vehicle.

In some embodiments the user may configure which operation restrictions to use. Further the user may define the timeout period s and or the speed threshold.

During an application lockout the tactile input controls of the application may be locked but voice inputs may be unrestricted. If audible inputs are received the tactile inputs may be locked block and voice inputs received.

Alternatively if tactile inputs are received select inputs may be restricted block . Accordingly when the application is locked select inputs may still be unrestricted block so that entire functionality is not lost.

While exemplary embodiments are illustrated and described above it is not intended that these embodiments illustrate and describe all possibilities. Rather the words used in the specification are words of description rather than limitation and it is understood that various changes may be made without departing from the spirit and scope of the invention.

