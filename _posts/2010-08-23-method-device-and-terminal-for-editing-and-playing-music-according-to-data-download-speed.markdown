---

title: Method, device and terminal for editing and playing music according to data download speed
abstract: The disclosure discloses a method, a device and a terminal for editing and playing music according to a data download speed. The method includes: generating, according to a preset number of continuously recorded download speed values, a number of preset speed domains, wherein the number of the preset speed domains is one more than the preset number of the download speed values, and setting one set frequency for each preset speed domain, wherein each set frequency corresponds to one preset musical sound; and playing a preset musical sound corresponding to a set frequency which corresponds to a preset speed domain when an immediate subsequent download speed value is within the preset speed domain. By means of the disclosure, an entertainment effect of “playing music randomly” can be achieved, so that entertainment experience of a user is increased and competitiveness of a product is improved.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08914475&OS=08914475&RS=08914475
owner: ZTE Corporation
number: 08914475
owner_city: Shenzhen
owner_country: CN
publication_date: 20100823
---
The disclosure relates to a data communication technology and in particular to a method a device and a terminal for editing and playing music according to a data download speed.

At present a terminal such as a data card or the like is widely applied to the field of a mobile communication technology. With the continuous development of the mobile communication technology functions of various terminals such as the data card and the like are becoming more mature and perfect with a lack of difference between each other such that how to improve an added value of product to enhance a user s awareness is a problem currently concerned by all manufacturers.

In the related art there is a method and a device for enhancing aesthetic perception in use of the terminal such as the data card or the like through enabling a user to intuitively understand a current data transmission speed of a terminal such as the data card or the like. For example the Chinese patent CN101345777 discloses a method a device and a terminal for displaying a running status wherein the method for displaying the running status includes acquiring a current data transmission speed of a data service calculating a ratio of the current data transmission speed to a preset data transmission speed and selecting music corresponding to the ratio and displaying the current data transmission speed of the data service according to the music. An embodiment of the disclosure enables a user to intuitively understand a current data transmission speed of a data card thereby enhancing aesthetic perception in use of the data card. However although the technology in the above patent can display the transmission speed of the data service to enhance the use aesthetic perception in use of the data card an added value of a product is not highly elevated and entertainment effect of the user can not be increased so that entertainment experience of the user is not high.

The main purpose of the disclosure is to provide a method a device and a terminal for editing and playing music according to a data download speed capable of realizing a music playing function by using a playing unit thereby increasing entertainment experience of a user and improving competitiveness of a product.

The disclosure provides a method for editing and playing music according to a data download speed which includes 

generating according to a preset number of continuously recorded download speed values a number of preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values and setting one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound and

playing a preset musical sound corresponding to a set frequency which corresponds to a preset speed domain when an immediate subsequent download speed value is within the preset speed domain.

Preferably the step of generating according to a preset number of continuously recorded download speed values a number of preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values and setting one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound may specifically include 

sorting the preset number of the continuously recorded download speed values in ascending order to generate the preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values and

setting one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound.

Preferably the number of the preset speed domains may be seven and the preset number of the download speed values may be six.

Preferably the step of playing the preset musical sound corresponding to the set frequency which corresponds to the preset speed domain when the immediate subsequent download speed value is within the preset speed domain may specifically include 

determining which preset speed domain the immediate subsequent download speed value belongs to and transmitting the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs to a playing unit and

Preferably the preset musical sound may be preset music or buzzing sound wherein the buzzing sound may include seven buzzing sounds whose frequencies are respectively the same as frequencies of seven tones in sequence.

Preferably the method may further include after playing the preset musical sound corresponding to the set frequency which corresponds to the preset speed domain when the immediate subsequent download speed value is within the preset speed domain 

updating the preset number of the download speed values and prompting a user whether to turn off an audio function 

if the use selects not to turn off the audio function sorting the preset number of the continuously recorded download speed values in ascending order to generate the preset speed domains wherein the number of the preset speed domains is one more than the preset number of download speed values and

The disclosure provides a device for editing and playing music according to a data download speed which includes an audio control module and a playing unit wherein

the audio control module is configured to generate according to a preset number of continuously recorded download speed values a number of preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values and set one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound and

the playing unit is connected with the audio control module and is configured to play a preset musical sound corresponding to a set frequency which corresponds to a preset speed domain when an immediate subsequent download speed value is within the preset speed domain.

a speed recorder configured to record a download speed value at a preset time interval after the device starts to download data sort the preset number of the continuously recorded download speed values in ascending order to generate the preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values set one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound.

Preferably the number of the preset speed domains may be seven and the preset number of the download speed values may be six.

the speed recorder is further configured to determine which preset speed domain the immediate subsequent download speed value belongs to and transmit the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs to the audio master control unit and

the audio master control unit is connected with the speed recorder and the playing unit and is configured to transmit the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs to the playing unit for playing the preset musical sound corresponding to the set frequency.

Preferably the speed recorder may be further configured to update the preset number of the download speed values and output prompt information of whether to turn off an audio function.

The disclosure provides a terminal for editing and playing music according to a data download speed which includes a device for editing and playing the music according to the data download speed.

In the disclosure through combining a terminal such as a data card or the like with a buzzer of a computer or an audio player a buzzing sound or a preset musical sound with a corresponding frequency is continuously selected according to a download speed and then is played via the buzzer of a mainboard of the computer or the audio player when the terminal such as the data card or the like downloads data so that an entertainment effect of playing music randomly can be achieved thereby increasing entertainment experience of a user and improving competitiveness of a product.

To make the technical solution of the disclosure more clear and understood the disclosure will be described in detail with reference to the drawings hereinafter.

The main technical solution adopted by the disclosure includes that after a data card is connected to a network a data download speed value D is recorded at a preset time interval the preset time interval can be one second or two or more seconds the last six take six as an example continuous download speed values D0 D5 the number of the continuous download speed values can be preset is stored only and the six download speed values are sorted in ascending order to generate seven preset speed domains C0 C6 wherein the seven preset speed domains correspond to seven preset musical sounds the preset musical sound can be preset music or buzzing sound with seven different frequencies the preset musical sound corresponding to the set frequency which corresponds to the preset speed domain Cn is played when the immediate subsequent download speed value Dn that is the subsequent download speed value Dn followed by the previous six download speed values is within which preset speed domain Cn and then the last six download speed values D0 D5 are updated to generate seven new preset speed domains C0 C6 and a function of playing music according to a change of a download speed can be realized by repeating the above processing.

A data card is taken as the example in the following specific embodiments however the solution is not limited to the data card and can also be applied to other terminals wherein the solution is the same and so further description is not needed.

As shown in the disclosure provides the method for editing and playing music according to a data download speed which includes the following steps 

Step a number of preset speed domains is generated according to a preset number of continuously recorded download speed values wherein the number of the preset speed domains is one more than the preset number of the download speed values and one set frequency is set for each preset speed domain wherein each set frequency corresponds to one preset musical sound 

in the step the number of the preset musical sounds is the same as that of the preset speed domains wherein in the embodiment the number of the preset musical sounds is seven. Taking downloading data by the data card as an example in order to achieve the purpose of playing the preset musical sound while downloading the data by the data card when the data card starts to download the data a download speed value is recorded at a preset time interval which can be one second to acquire six continuous download speed values then the six download speed values are sorted in ascending order to generate seven preset speed domains and then one set frequency is set for each preset speed domain wherein each set frequency corresponds to one preset musical sound the preset time interval can be one second or two or more seconds and the preset musical sound can be either a preset music composed of some simple single syllables or multi syllables or a buzzing sound and seven buzzing sounds can be seven basic tones 1do 2re 3mi 4fa 5sol 6la and 7si that is the frequencies of the seven buzzing sounds can be respectively the same as that of the seven basic tones 1do 2re 3mi 4fa 5sol 6la and 7si in sequence.

In another embodiment the number of the continuously recorded download speed values can be preset as 4 5 or other values correspondingly the number of preset speed domains generated according to the continuously recorded download speed values is one more than the number of the download speed values furthermore the purpose of playing music according to the download speed values can be achieved through presetting a number of the preset musical sounds wherein the number of the preset musical sounds is the same as the number of the preset speed domains.

Step when the immediate subsequent download speed value is within one preset speed domain the preset musical sound corresponding to the set frequency which corresponds to the preset speed domain is played.

The step specifically includes determining the preset speed domain to which the immediate subsequent download speed value belongs i.e. determining which preset speed domain the immediate subsequent download speed value is within and transmitting the set frequency corresponding to the preset speed domain to a playing unit. In the embodiment the playing unit is an audio player or a buzzer configured on a mainboard of a computer and the buzzer or audio player receives the frequency corresponding to the preset speed domain and plays the preset musical sound corresponding to the set frequency which corresponds to the preset speed domain wherein the preset musical sound is a preset music or a buzzing sound.

In the embodiment through the combination of the data card with the playing unit buzzer of a computer or audio player when the data card downloads data a preset musical sound with a corresponding frequency is continuously selected according to a download speed and then is played by the playing unit buzzer or audio player so that an entertainment effect of playing music randomly is achieved thereby increasing entertainment experience of a user and improving competitiveness of a product.

Step a download speed value is recorded at a preset time interval after the data card starts to download data 

Step a preset number of continuously recorded download speed values are sorted in ascending order to generate preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values 

in the embodiment the preset number of the continuously recorded download speed values can be six and the number of the preset speed domains generated corresponding to the six download speed values is seven.

Step one set frequency is set for each preset speed domain wherein each set frequency corresponds to one preset musical sound 

in the step the number of the preset musical sounds can be pre selected wherein the number of the preset musical sounds is the same as that of the preset speed domains in the embodiment the preset musical sound is preset music and the preset music can be the preset music composed of some simple single syllables or multi syllables.

Step it is determined which preset speed domain the immediate subsequent download speed value belongs to and the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs is transmitted to an audio player.

after one preset musical sound is completely played the data card updates a preset number which is six in the embodiment of download speed values so as to acquire a new preset number which is six in the embodiment of download speed values to be ready to execute Step .

Step a user is prompted whether to turn off an audio function if not i.e. the user selects not to turn off the audio function the step that the preset number of continuously recorded download speed values are sorted in ascending order to generate the preset speed domains wherein the number of the preset speed domains is one more than the preset number of download speed values is executed that is Step is executed otherwise the user selects to turn off the audio function and the application program is exited.

In the embodiment after six download speed values are updated the user is prompted whether to turn off the audio function if the user selects not to turn off the audio function the step that the preset number six of the continuously recorded download speed values are sorted in ascending order to generate the preset speed domains wherein the number of the preset speed domains seven is one more than the preset number of download speed values is executed that is Step is executed otherwise the application program is exited.

In the embodiment through the combination of the data card with the audio player when the data card downloads data a preset music with a corresponding set frequency is continuously selected according to a download speed and then is played via the audio player so that an entertainment effect of playing music randomly is achieved thereby increasing entertainment experience of a user and improving competitiveness of a product.

In another embodiment the number of the continuously recorded download speed values can be preset as 4 5 or other values correspondingly the number of the preset speed domains generated according to the continuously recorded download speed values is one more than the number of the download speed values furthermore the purpose of playing music according to a download speed can be achieved through presetting a number of preset musical sounds wherein the number of preset musical sounds is the same as the number of the preset speed domains.

in the embodiment a preset musical sound is a buzzing sound the frequencies of seven buzzing sounds are respectively the same as that of the seven basic tones in sequence that is the frequencies of the seven buzzing sounds are respectively the same as the frequencies of the seven basic tones 1do 2re 3mi 4fa 5sol 6la and 7si in sequence.

Step it is determined which preset speed domain the immediate subsequent download speed value belongs to and the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs is transmitted to an audio master control unit.

Step the audio master control unit calls a dynamic link library in a computer operating system and sends an instruction having a parameter with the set frequency to an Application Programming Interface API and

the audio master control unit accesses the computer operating system calls a corresponding function of the system dynamic link library and issues the instruction having the parameter with the set frequency.

the called function accesses the API the API generates a recognizable code instruction for a computer and transmits the instruction to a buzzer on a mainboard of the computer.

the buzzer issues a buzzing sound according to the acquired parameter with the set frequency to complete one buzzing sound playing.

Step a user is prompted whether to turn off an audio function if the user selects to not turn off the audio function the step that the preset number of continuously recorded download speed values are sorted in ascending order to generate preset speed domains is executed wherein the number of the preset speed domains is one more than the preset number of download speed values otherwise the application program is exited.

In the embodiment the user is prompted whether to turn off the audio function if the user selects not to turn off the audio function the step that the six download speed values are sorted in ascending order to generate seven preset speed domains is executed the above steps are repeated to achieve an effect of continuously playing music until the user turns off the function.

The process of the method for playing a buzzing sound by combining a data card and a buzzer on mainboard of a computer in the embodiment will be described in detail hereinafter 

the data card starts to download data and the speed recorder starts to record a data download speed value at a speed of one download speed value being recorded every one second.

When the total number of the download speed values for example 24 65 110 70 42 and 12 Kbyte in sequence is equal to 6 a speed recorder generates seven preset speed domains 0 12 12 24 24 42 42 65 65 70 70 110 and 110 infinite . The frequencies corresponding to the seven preset speed domains are set as 400 450 520 620 700 800 and 900 Hz in sequence i.e. the frequencies required by 1do 2re 3mi 4fa 5sol 6la and 7si.

A speed value in the immediate subsequent second for example 96 is acquired it is determined that 96 is within the 70 110 domain and the corresponding frequency is 800 Hz.

The speed recorder sends a response instruction with a parameter the frequency of 800 Hz to the audio master control unit.

The audio master control unit calls a Beep function in a dynamic link library kernel32.dll of a Windows system and transmits the instruction having the parameter with the frequency of 800 Hz and the duration of 1000 milliseconds to the Beep function the Beep issues an instruction to the buzzer through calling an API of the operating system and thus the buzzer can make 6la sound.

It is determined whether the audio function of the data card is turned off if the audio function is not turned off it starts to be performed again from the step that the speed recorder generates seven preset speed domains again according to the updated current six speed values so as to continuously play music to achieve a musical effect if the audio function is turned off the application program is exited.

In the embodiment through the combination of the data card with the buzzer on the mainboard of the computer when the data card downloads data a buzzing sound with a corresponding set frequency is continuously selected according to a download speed and then is played via the buzzer so that an entertainment effect of playing music randomly is achieved thereby increasing entertainment experience of a user and improving competitiveness of a product.

In another embodiment the number of the continuously recorded download speed values can be preset as 4 5 or other values correspondingly the number of the preset speed domains generated according to the continuously recorded download speed values is one more than the number of download speed values furthermore the purpose of playing music according to a download speed can be achieved through presetting a number of the preset musical sounds wherein the number of the preset musical sounds is the same as the number of the preset speed domains.

As shown in Embodiment 4 of the disclosure provides the device for editing and playing music according to the data download speed which includes 

an audio control module configured to generate according to a preset number of continuously recorded download speed values a number of preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values and set one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound and

a playing unit connected with the audio control module and configured to when an immediate subsequent download speed value is within the preset speed domain play a preset musical sound corresponding to a set frequency which corresponds to a preset speed domain.

the speed recorder is configured to record a download speed value at a preset time interval the preset time interval is one second in the embodiment after a data card starts to download data sort a preset number of continuously recorded download speed values in ascending order to generate a number of preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values and set one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound and the speed recorder is further configured to determine which preset speed domain the immediate subsequent download speed value belongs to and transmit the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs to the audio master control unit and

the audio master control unit is connected with the speed recorder and the playing unit and is configured to transmit the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs to the playing unit for playing the preset musical sound corresponding to the set frequency.

In the embodiment the preset number of the continuously recorded download speed values is six correspondingly the number of the generated preset speed domains is seven the speed recorder records after the data card starts to download data one download speed value at the preset time interval such as one second to acquire six continuous download speed values sort the six continuous download speed values in ascending order to generate seven preset speed domains sets one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound when receiving a subsequent download speed value the speed recorder determines which preset speed domain the immediate subsequent download speed value is within and transmits the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs to the audio master control unit and then the audio master control unit transmits the set frequency corresponding to the preset speed domain to which the immediate subsequent download speed value belongs to the playing unit and the playing unit plays the preset musical sound corresponding to the set frequency.

After transmitting the set frequency corresponding to the subsequent download speed value to the playing unit the speed recorder further needs to update the latest six download speed values i.e. the last six download speed values then prompt a user whether to turn off an audio function if the user selects not to turn off the audio function the step of sorting the updated six download speed values in ascending order to generate seven preset speed domains is executed and the above steps are repeated to achieve a continuous playing effect if the user selects to turn off the audio function exit the application program.

In the embodiment the playing unit can be either an audio player or a buzzer configured on a mainboard of a computer the preset time interval can be one second or two or more seconds the preset musical sound can be either a preset music composed of some preset simple single syllables or multi syllables or a buzzing sound and the buzzing sound can be seven basic tones 1do 2re 3mi 4fa 5sol 6la and 7si that is the frequencies of the buzzing sound can be respectively the same as that of the seven basic tones 1do 2re 3mi 4fa 5sol 6la and 7si in sequence.

In another embodiment the number of the continuously recorded download speed values can be preset as 4 5 or other values correspondingly the number of preset speed domains generated according to the continuously recorded download speed values is one more than the number of download speed values furthermore the purpose of playing music according to the download speed can be achieved through presetting a number of the preset musical sounds wherein the number of the preset musical sounds is the same as the number of the preset speed domains.

By comparing the device in Embodiment 5 with the structure of the device in the embodiment shown in both of the devices include the audio control module wherein the audio control module includes the speed recorder and the audio master control unit connected with the speed recorder . Each same functional module has the same function so no further description is needed.

The difference between the device in the embodiment and the device in the embodiment shown in is that the playing unit in the embodiment is specifically an audio player and the preset musical sound can specifically be a preset music composed of some preset simple single syllables or multi syllables.

In another embodiment the number of the continuously recorded download speed values can be preset as 4 5 or other values correspondingly the number of preset speed domains generated according to the continuously recorded download speed values is one more than the number of download speed values furthermore the purpose of playing music according to the download speed can be achieved through presetting a number of the preset musical sounds wherein the number of the preset musical sounds is the same as the number of the preset speed domains.

As shown in the device in the embodiment includes the audio control module and the playing unit wherein the audio control module includes the speed recorder and the audio master control unit .

The functions of the speed recorder and the audio master control unit in the embodiment are the same as that in the embodiment shown in so no further description is needed.

The difference between the embodiment and the embodiment shown in is that the playing unit is different in the embodiment the playing unit includes a buzzer configured on a mainboard of a computer the device in the embodiment is connected with the buzzer on the mainboard of the computer via an audio master control unit and a signal transmission between the audio master control unit and the buzzer includes that 

the audio master control unit is connected with the mainboard of the computer the audio master control unit accesses the operating system of the computer calls a corresponding function of a system dynamic link library and issues an instruction with a parameter the parameter can be a frequency to an API the API generates the instruction into a code instruction recognizable for the computer and transmits the code instruction to the buzzer on the mainboard of the computer and the buzzer plays the buzzing sound with the corresponding frequency.

The number of the buzzing sound in the embodiment can be seven the frequencies of the seven buzzing sounds can be respectively the same as that of seven basic tones in sequence that is the frequencies of the seven buzzing sounds are respectively the same as that of the seven basic tones 1do 2re 3mi 4fa 5sol 6la and 7si in sequence.

As shown in the disclosure provides a terminal for editing and playing music according to the data download speed which includes a device for editing and playing music according to a data download speed wherein the device is configured to generate according to a preset number of continuously recorded download speed values a number of preset speed domains wherein the number of the preset speed domains is one more than the preset number of the download speed values and set one set frequency for each preset speed domain wherein each set frequency corresponds to one preset musical sound and when the immediate subsequent download speed value is within the preset speed domain play the preset musical sound corresponding to the set frequency which corresponds to the preset speed domain.

In the embodiment the device for editing and playing music according to a data download speed is further configured to update a preset number of download speed values and output prompt information of whether to turn off an audio function.

The device for editing and playing music according to a data download speed in the embodiment includes the audio control module and the playing unit connected with the audio control module wherein the playing unit can be a music player or a buzzer.

The audio control module in the embodiment includes the speed recorder and the audio master control unit . The internal structure of the device in the embodiment and the internal structure of the device in the embodiment shown in are the same so no further description is needed.

In the disclosure through the combination of the data card with the computer buzzer or audio player when the data card downloads data a buzzing sound or preset musical sound with a corresponding frequency is continuously selected according to the download speed and then is played via the buzzer of the mainboard of the computer or the audio player so that an entertainment effect of playing music randomly is achieved thereby increasing entertainment experience of a user and improving competitiveness of a product.

In another embodiment the number of the continuously recorded download speed values can be preset as 4 5 or other values correspondingly the number of preset speed domains generated according to the continuously recorded download speed values is one more than the number of download speed values furthermore the purpose of playing music according to the download speed can be achieved through presetting a number of the preset musical sounds wherein the number of the preset musical sounds is the same as the number of the preset speed domains.

The above are only the preferred embodiments of the disclosure and are not intended to limit the scope of protection of the disclosure either and any equivalent structure or flow transformation made or a direct or indirect application in other relevant technical fields shall fall within the scope of protection of the disclosure according to the content of the description and the drawings of the disclosure.

