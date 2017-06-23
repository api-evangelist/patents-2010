---

title: Socializing web services
abstract: A Method for sharing and recording achievements obtained in web services, comprising:


url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08725805&OS=08725805&RS=08725805
owner: Vodafone Group PLC
number: 08725805
owner_city: Newbury, Berkshire
owner_country: GB
publication_date: 20100119
---
This application claims the benefit of Spanish Patent Application No. ES 200900135 filed Jan. 19 2009 entitled Socializing Web Services which is incorporated herein by reference in its entirety.

Embodiments of the present invention relate to the field of internet communities and more specifically to interactions within and between such communities. In particular the invention relates to the sharing of Internet achievements in internet communities.

There is a problem when someone tries to find other people with similar tastes. The problem is that people move in time and space. A success for a service is providing user needs just in time when it is required. For that reason a spatial and time distribution of the people s tastes is important.

On the other hand there are many internet communities that could be used to understand user preferences better some of these communities like funky sexy cool tag users results www funkysexycool com and this information can be seen by users as achievements or more generally speaking a profile. There is presently no way to share these achievements and profiles with users except Internet itself .

Nowadays groups of interest and urban tribes know places and hours to find people with their same interest or tastes by written or oral communication i.e. stamp collectors meet on Saturday morning on Plaza Mayor electronic music fans meet in the discotheque s parking area in the evenings etc . This behavior is facilitated by Internet forums reviews or recommendations issued by certain individuals either in media or Internet that may deliver a profile of the place.

Well connected people from some internet communities may launch meetings and events but all these attempts are very limited.

The present invention solves the above commented problems by using the user s mobile device phone PDA etc. and a system for broadcasting Internet achievements that is achievements obtained in the Internet community such as social networks online games forum etc. Some achievements can be cited as examples 

To obtain these achievements users of all ages spend some of their leisure time and they are proud to show off their achievements. Embodiments of the present invention can be used to publish the achievements and obtain information of the achievements of other users facilitating the meetings among different Internet communities at any time and in any city of the world.

It is well known that abbreviations and acronyms are frequently used in the mobile telephony field. Below is a glossary of acronyms terms used throughout the present specification 

Embodiments of the invention relate to methods and systems for sharing and recording achievements obtained in web services.

The broadcasting of the at least one selected achievement may be performed in at least one of the following ways 

The method may additionally comprise broadcasting together with the achievements captured by the broadcasting device data on the measures of at least one sensor device installed in the area.

The broadcasting of said achievements captured by the broadcasting device may be performed in one of the following ways 

In another example there is provided a system for sharing and recording achievements obtained in web services. The exemplary system comprises 

The system may further comprise a broadcasting device installed in each specific area configured for capturing and broadcasting all the achievements received from broadcast users. The broadcasting device can be further configured for broadcasting together with the achievements captured by the broadcasting device data on the measures of at least one sensor device installed in the area. The broadcasting of said achievements captured by the broadcasting device can be performed in at least one of the following ways 

Example embodiments are directed to the notion of people using a mobile terminal i.e. a cellular telephone as a beacon that shows to the rest of the world their community profile or achievements including their location usually a mobile widget with GPS or bluetooth characteristics and a method to publish this information in a centralized database. This can be applied to individuals and also to places bars sightseeing areas etc . The implementation can be in two ways 

b Using local sensors in some places bars discotheques etc to obtain a more focalized info of the profile in the area and include more real time information like number of people environment details etc.

The information profile and the place or the person would be delivered remotely but it is not necessary to identify this information with a specific place or person. The idea is to use the average profile of the people and places in an area at a specific time and the distribution of this data to provide information and services.

Some examples could be the centralized database will provide maps of a city like Madrid where one could find the distribution hours and places of people with a profile higher than 50 sexy in Funky Sexy Cool community www funkysexycool com or areas of Tuenti users Spanish community for young people in Internet in London city. Users and third parties could take advantage of this information to find people with the same preferences or launch innovative vertical services. It must be taken into account that it is very frequent that the same place hosts very different communities music and style in different days of the week or at different opening hours.

The user would decide what achievements and communities want to distribute but using sensors this information service can be improved for example a bar with sensor devices and local broadcasting methods to measure and provide for instance the percentages of people with a specific profile the occupancy and environment measures such as temperature or noise level to attract potential users outside and promote the bar.

The beacon process will be carried out via the mobile phone in essence software connects to the relevant internet community API captures the present value of achievement sexy or not number of friends in Facebook etc. and sends it to the central database or communicates with a short range node to deliver this information.

The local broadcasting process may be performed by any means wireless kiosk local mobile phone broadcasting . . . however the preferred implementation is in mobile devices.

The achievements information server stores the achievements received from the different Internet communities the web services and some information on the user s terminal telephone such as its position and optionally the state of sensors incorporated in the terminal.

The broadcast user who is going to broadcast his achievements uses an application e.g. Java midlet in his mobile device e.g. mobile phone or PDA that manages all the different achievements stored in the achievements information server . This mobile device downloads the achievement information in the mobile device and arranges it by priority. The broadcast user selects which of the achievements are going to be broadcasted and the priority. The connection to manage the information and preference is done using a cellular network such as UMTS GSM LTE etc. or WiFi.

The mobile device can broadcast the achievements in two different ways either using short range technology such as Bluetooth or IEEE 802.15.4 Standard to communicate with other mobile devices belonging to receptors or using the cellular connection or WiFi to send the achievements along with its position and preferences the current profile to be shown to the achievements information server configuring this way his current profile. On the other side receptors can access other user s achievements via short range technology in the case of receptor e.g. those achievements broadcasted by broadcast users via Bluetooth but they can also retrieve achievements from different users by accessing the achievements information server and carrying out the appropriate search this way the receptor can also obtain information on the achievements of other users who are next to him .

The achievement information should contain the unique identity and the different achievements by priority order. Each achievement should contain two fields the name of the web server and the achievement text. For example 

This information is broadcasted regularly using the Bluetooth connections. Other users receptor using mobile devices with the same midlet can capture all the different user information. The midlet will also filter the information obtaining a view of the community achievements around him.

For the communication of the achievements a sensor network air interface ZigBee glowpan or any variation of the IEEE 802.15.4 standard can also be used. The mobile device in this case would be another point in the sensor mesh and will broadcast and capture the achievements using this air interface. It can also be used any other short range radio different from Bluetooth or 802.15.4 such as WiFi or Infrared.

Additionally sensor information can be included in the communication using the sensors in the mobile device or the sensors in the surroundings. The information would be captured using either bluetooth or 802.15.4 air interfaces.

The application loaded in the mobile device will filter all the broadcasted achievements. The filtering will have the following features 

This filtered information can also be sent to the achievements information server so the latter can update the position and current profile of the broadcast users . The filter should delete the information related to erroneous or fake unique identifiers.

The present invention can also be applied to business and public places such as a pub a library a public square etc. where people could meet. There is a specific broadcasting device installed in that area that captures all the achievements received from broadcast users and broadcasts all of them. This broadcasting device can additionally include in the broadcast information some measurements of the area taken from sensor devices forming a wireless sensor network . All the information can be used to provide marketing information about the business e.g. place with a of hip hop users www hiphop net level of noise dB smoke level ug m3N etc. . This broadcasting device can use DSL to be connected with the achievements information server . The broadcasting device does not require internet achievements to broadcast as own achievements but it requires a unique identity in order to be filtered.

The consumers are third parties that use the information provided by the achievements information server to provide services using the achievements information server API to manage the information.

Some examples about possible services provided by the consumers could be although they are not included in the scope of the present invention 

2 Provide offers to certain profiles around the business. e.g. mall center that provide discounts in pet shops only to the people with pikapet www pikapet com achievements. 

3 Provide areas of our interest. e.g. provide information of a pub with a high number of Spanish facebook users in London. 

4 Receive time information in my specific position about sexy achievements percentage www funkysexycoolcom 

5 Provide a phone alarm when a threshold in achievements is reached in the area. E.g. of World of Warcraft an online game achievements reaches 20.

