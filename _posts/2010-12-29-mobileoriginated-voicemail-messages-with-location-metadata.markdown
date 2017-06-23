---

title: Mobile-originated voicemail messages with location metadata
abstract: A voicemail message system may process voicemail messages sent by mobile communication devices. A network interface may receive the voicemail messages over a network communication system. Each voicemail message may include metadata relating to the voicemail message containing location information indicative of the location of the mobile communication device at approximately the time the message is sent by the mobile communication device. A voicemail message processing system may cause each message which is received by the network interface to be stored in a message storage system, along with its location information. Related mobile communication devices, telephone switches, and recipient phone call devices are also described.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08655323&OS=08655323&RS=08655323
owner: Cellco Partnership
number: 08655323
owner_city: Basking Ridge
owner_country: US
publication_date: 20101229
---
This disclosure relates to mobile communication devices such as cell phones and to related message systems such as voicemail message systems.

Mobile communication devices such as cell phones may be configured to place phone calls. When the calls are unanswered the mobile communication devices may record voicemails for the recipients.

Recipients of these voicemail messages may find certain information about the callers to be helpful such as information about the location of the callers. Such location information for example may be of interest to parents of message leaving children emergency personnel who may wish to provide immediate aid to callers and to friends and relatives who may find it helpful to know whether out of town callers are visiting. Callers however may not always provide location information in their voicemail messages. Even when they do the location information may not be very precise.

A message system may process messages sent by mobile communication devices. A network interface may receive the messages over a network communication system. Each message may include metadata relating to the message containing location information indicative of the location of the mobile communication device at approximately the time the message is sent by the mobile communication device. A message processing system may cause each message which is received by the network interface to be stored in a message storage system along with its location information.

The message system may be a voicemail message system the messages may be voicemail messages the storage system may be a voicemail message storage system and the message processing system may be a voicemail message processing system.

The voicemail message processing system may cause the network interface to send a question to each mobile communication device in an audible or text format over the network communication system at approximately the time it receives each voicemail message from each mobile communication device. The question may ask whether location information should be included with the voicemail message. The network interface may receive a response to the question from each mobile communication device over the network communication system in an audible or text format.

The metadata may include recipient information indicative of at least one intended recipient of the voicemail message. The voicemail message processing system may cause the network interface to deliver each voicemail message to its intended recipient over the network communication system in an audible or text format along with its location information.

The voicemail message processing system may cause the network interface to send a question to each intended recipient in an audible or text format over the network communication system asking whether the intended recipient wants to receive the location information in addition to the voicemail message.

The network interface may receive a response to the question from each intended recipient over the network communication system in an audible or text format. The voicemail message processing system may cause the network interface to send the location information to each intended recipient over the network communication system in an audible or text format only if the response from the intended recipient indicates that the intended recipient wants to receive the location information.

The location information in each voicemail message may include information about the geographic coordinates of each mobile communication device. The voicemail message processing system may translate each set of the geographic coordinates into a street address.

A mobile communication device may include a wireless communication system which may wirelessly communicate communications over a network communication system including messages from a user of the mobile communication device to a message system. A location determining system may determine the location of the mobile communication device. A location determining system may cause the wireless communication system to include metadata with each message relating to the message containing location information indicative of the location of the mobile communication device at approximately the time the message is sent.

A user interface may allow the user to specify whether the location information is to be delivered to the voicemail message system. The location delivery system may cause the wireless communication system to deliver the location information to the voicemail message system only when the user has specified through the user interface that it is to be delivered.

The mobile communication device may include a storage system configured to store the specification which the user enters through the user interface about whether the location information is to be delivered to the voicemail message system. The location delivery system may read the stored specification about whether the location information is to be delivered to the voicemail message system from the storage system each time the user leaves a voicemail message with the voicemail message system and cause the wireless communication system to deliver the location information to the voicemail message system only when the stored specification indicates that it is to be so delivered.

The storage system may store information indicative of the identity of intended recipients of communications. The user interface may allow the user to separately specify whether the location information is to be delivered to the voicemail message system in connection with each stored intended recipient.

A telephone communication device may include a phone call communication system configured to receive phone calls over a network communication system from wireless mobile communication devices. Each phone call may include metadata containing location information indicative of the location of the mobile communication device at approximately the time the message is sent by the mobile communication device. A location communication interface may cause the location information to be communicated to a user of the communication device.

The location communication interface may cause the location information to be communicated to the user contemporaneously with the arrival of the phone call and before it is answered.

The telephone communication device may include a storage system configured to store the location information. The location communication interface may cause the location information to be stored in the storage system and to be communicated to the user thereafter upon request of the user.

A telephone switch may call recipients of phone calls from mobile communication devices. A network interface may receive recipient information from each mobile communication device indicative of a recipient for a phone call which the mobile communication device wishes to place along with metadata relating to the phone call containing location information indicative of the location of the mobile communication device at approximately the time the phone call is being placed by the mobile communication device. The network interface may send a notice to each recipient indicating that a mobile communication device is calling along with the location information. A call processing system may cause the network interface to send the notice to each recipient indicating that a mobile communication device is calling along with the location information.

These as well as other components steps features objects benefits and advantages will now become clear from a review of the following detailed description of illustrative embodiments the accompanying drawings and the claims.

Illustrative embodiments are now described. Other embodiments may be used in addition or instead. Details which may be apparent or unnecessary may be omitted to save space or for a more effective presentation. Some embodiments may be practiced with additional components or steps and or without all of the components or steps which are described.

Although illustrated as cell phones the mobile communication devices and may be of any type. For example one of the devices may be a laptop computer a PDA tablet online gaming console or TV console.

The network communication system may be of any type. For example the network communication system may consist of or include a cellular telephone network communication system a cellular data communication system the internet a wide area network a local area network and or a combination of any of these types of network communication systems.

The voicemail message system may be configured to process voicemail messages sent by mobile communication devices such as the mobile communication devices and . The voicemail message system illustrated in may be configured differently than is illustrated in . Similarly the voicemail message system illustrated in may be used in connection with computer networks which are different from the one illustrated in .

The network interface may be configured to receive the voicemail messages over the network communication system . Each voicemail message may include metadata relating to the voicemail message. The metadata may include location information indicative of the location of the mobile communication device at approximately the time the message is sent by the mobile communication device.

The network interface may be of any type. For example the network interface may be based on IMAP HTTP REST over HTTP or any proprietary open source protocol. It may be software only or a combination of a software and hardware based solution.

The voicemail message storage system may be configured to store each voicemail message along with its location information. The voicemail message storage system may be of any type. For example the voicemail message storage system may consist of or include one or more hard disk drives and or RAMs.

The voicemail message processing system may be configured to cause each voicemail message which is received by the network interface to be stored in the voicemail message storage system along with its location information.

The voicemail notification system may be configured to cause notice of a voicemail which is received and stored in the voicemail message storage system to be delivered to the intended recipient of the voicemail message. The voicemail message processing system may be configured to cause the voicemail notification system to issue this notice. The notice may be issued through the network interface .

The voicemail message processing system may be configured to cause the network interface to send a question to each mobile communication device over the network communication system at approximately the time it receives each voicemail message from each mobile communication device. The question may be configured to ask whether location information should be included with the voicemail message. The voicemail message processing system may be configured to cause the network interface to send each question over the network communication system in any format such as in a text and or audible format.

The voicemail message processing system may be configured to receive from the network interface a response to the question from the mobile communication device over the network communication system . The voicemail message processing system may be configured to cause the voicemail message storage system to store the location information if the response is in the affirmative but not to store the location information if the response is in the negative. The response may be in any format such as in a text or audible format.

The voicemail message system may be configured to receive voicemail messages which do not include location information from mobile communication devices which do not send such location information. In this situation the voicemail message system may be configured not to cause the network interface to send a question to the mobile communication device asking whether the location information should be included with the voicemail message.

The metadata which is provided by the wireless mobile communication device may include recipient information indicative of at least one intended recipient of the voicemail message. The voicemail message processing system may be configured to cause the network interface to deliver each voicemail message to its intended recipient over the network communication system along with its location information. The voicemail message may be delivered in any format such as in a text and or audible format.

Before doing so the voicemail message processing system may be configured to cause the network interface to send a question to each intended recipient over the network communication system asking whether the intended recipient wants to receive the location information in addition to the voicemail. The question may be in any format such as in a text and or audible format.

The network interface may be configured to receive a response from each intended recipient to the question and to pass that to the voicemail message processing system . The response may be in any format such as in a text and or audible format. The voicemail message processing system may be configured to send the location information to each intended recipient over the network communication system only if the response from the intended recipient wants to receive the location information. The location information may be in any format such as in a text and or audible format.

The location information which is received from the mobile communication device may include information about the geographic coordinates of each mobile communication device. The voicemail message processing system may be configured to translate each set of geographic coordinates into a street address. It may be configured to do so by consulting a database that cross references geographic coordinates to street addresses. This database may be contained within the voicemail message system and or external to it. The voicemail message processing system may be configured to send the translated location information to each recipient in addition to or instead of the raw geographic coordinates.

One or more of the mobile communication devices illustrated in may be different from the one illustrated in . Similarly the mobile communication device illustrated in may be used in connection with a computer network which is different from the one illustrated in .

The mobile communication device illustrated in may include a wireless communication system a location determining system a user interface a storage system and a location delivery system .

The wireless communication system may be configured to wirelessly communicate communications over a computer network system such as the network communication system . The communications may include voicemail messages from a user of the mobile communication device. The voicemail message may be directed to a voicemail message system. The wireless communication system may include an antenna radio transmitter radio receiver processing system storage system and or user interface.

The location determining system may be configured to determine the location of the mobile communication device. The location determining system may include a GPS receiver and or it may use triangulation or other techniques for determining this location.

The location delivery system may be configured to cause the wireless communication system to include metadata with each voicemail message relating to the voicemail message. The metadata may contain location information obtained from the location determining system which is indicative of the location of the mobile communication device at approximately the time the voicemail message is sent.

The user interface may be configured to allow the user to specify whether the location information is to be delivered to the voicemail message system. The location delivery system may be configured to cause the wireless communication system to deliver the location information to the voicemail message system only when the user has specified through the user interface that such location information is to be delivered.

The user interface may be of any type. For example the user interface may include a display touch screen keyboard mouse pad microphone loud speaker ear phone and or any other type of user interface device.

As illustrated in a display may be part of the user interface and may be configured to ask a user whether the user wants the location information to be included with a voicemail message to a recipient. This may be facilitated by a check box . Check boxes for other characteristics relating to the voicemail message may also be provided as also illustrated.

This type of visual dialog with a person who delivers a voicemail message may be used in connection with what has become known as visual voicemail i.e. voicemail which may be communicated to a recipient in a format similar to an email message.

In other configurations the question may be presented audibly such as through a voice question and responded to audibly such as through a voice answer by the user and or a touch tone response.

Returning to the storage system may be configured to store the specification which the user enters through the user interface about whether the location information is to be delivered to the voicemail message system.

The storage system may be of any type. For example the storage system may include one or more hard disk drives and or RAMs.

The location delivery system may be configured to read a stored specification about whether the location information is to be delivered to the voicemail message system from the storage system each time the user leaves a voicemail message with the voicemail message system. The location delivery system may be configured to cause the wireless communication system to deliver the location information to the voicemail message system only when the stored specification indicates that it is to be so delivered.

The storage system may be configured to store information indicative of the identify of intended recipients of communications. The user interface may be configured to allow the user to separately specify whether the location information is to be delivered to the voicemail message system in connection with each stored intended recipient. In this configuration location information may automatically be provided to the voicemail message system each time a voicemail message is left for a recipient who has been designated in the storage system to receive this location information but not for recipients who have not been so designated.

As illustrated in the metadata that goes along with a voicemail message may be in an envelope also known as a header which is associated with the voicemail message. The envelope may include information such as the sender s mobile directory number MDN the intended recipient s MDN a message priority specification a message sensitivity specification a date time stamp for the message and sender location information indicative of the location of the sender.

The sender location information may be in any format. For example it may include information indicative of the geographic coordinates of the sender and or the address of the sender all at the time the voicemail message is being provided.

The recipient phone call communication device which is illustrated in may be illustrative of the components contained within the recipient phone call communication devices and or illustrated in or in connection with any other type of recipient phone call communication device. Similarly the recipient phone call communication devices and or illustrated in may have a configuration that is different from what is illustrated in .

As illustrated in the recipient phone call communication device may include a network communication system a location communication interface and a storage system .

The network communication system may be configured to receive phone calls over a network communication system from wireless mobile communication devices. Each phone call may include metadata containing location information indicative of the location of the mobile communication device at approximately the time the location information is sent by the mobile communication device.

The location communication interface may be configured to cause the location information to be communicated to a user of the communication device. The communication may be in a textual format which is displayed and or an audible format which may be audibly communicated to a user.

The location communication interface may be configured to cause the location information to be communicated to the user contemporaneously with the arrival of the phone call before it is answered. Again this information may be displayed and or communicated audibly.

The storage system may be configured to store the location information. The storage system may include any type of storage device such as a RAM and or flash memory.

The location communication interface may be configured to cause the location information to be stored in the storage system if the phone call is not answered by the user and to be communicated to the user thereafter upon request of the user.

This type of display may be found in connection with recipient phone call communication devices which subscribe to a visual voicemail service thereby presenting voicemail messages in a form similar to email messages. As illustrated in the record of each voicemail message may include location information such as location information and in addition to more traditional information such as the name of the sender and the time and date of the message.

As illustrated in the telephone switch may include a network interface and a call processing system .

The network interface may be configured to receive from each mobile communication device recipient information indicative of a recipient for a phone call which the mobile communication device wishes to place. Along with the recipient information the network interface may be configured to receive metadata relating to the phone call containing location information indicative of the location of the mobile communication device at approximately the time the phone call is being placed by the mobile communication device. The network interface may also be configured to send a notice to each recipient indicating that a mobile communication device is calling along with the location information.

The call processing system may be configured to cause the network interface to send a notice to each recipient indicating that a mobile communication device is calling along with the location information.

Unless otherwise indicated the voicemail message systems and telephone switches that have been discussed herein may each be implemented with a computer system configured to perform the functions which have been described herein for the component. Each computer system may include one or more computers at the same or different locations. When at different locations the computers may be configured to communicate with one another through a wired and or wireless network communication system. Each computer may include one or more processors memory devices e.g. random access memories RAMs read only memories ROMs and or programmable read only memories PROMS tangible storage devices e.g. hard disk drives CD DVD drives and or flash memories system buses video processing components network communication components input output ports and or user interface devices e.g. keyboards mice displays microphones sound reproduction systems and or touch screens . Each computer may be a personal computer mainframe workstation single user system multi user system server portable computer hand held device cell phone smart cell phone tablet or part of a larger system such as a vehicle appliance and or telephone system. Each computer may include software e.g. one or more operating systems device drivers application programs and or communication programs which may be configured when executed to cause the computer to perform one or more of the functions which have been described herein for the computer system. The software may include programming instructions and associated data and libraries. The software may implement one or more algorithms which may cause the computer to perform each function. The software may be stored on one or more tangible storage devices such as one or more hard disk drives CDs DVDs and or flash memories. The software may be in source code and or object code format. Associated data may be stored in any type of volatile and or non volatile memory.

The components steps features objects benefits and advantages which have been discussed are merely illustrative. None of them nor the discussions relating to them are intended to limit the scope of protection in any way. Numerous other embodiments are also contemplated. These include embodiments which have fewer additional and or different components steps features objects benefits and advantages. These also include embodiments in which the components and or steps are arranged and or ordered differently.

For example the messages which have thus far been discussed have been designated as voicemail messages. In other configurations the various devices which have been discussed may be configured to provide receive question communicate and to otherwise manipulate messages of other types with the same location information such as text based messages such as instant messages text messages and email messages including SMS messages and MMS messages.

Unless otherwise stated all measurements values ratings positions magnitudes sizes and other specifications which are set forth in this specification including in the claims which follow are approximate not exact. They are intended to have a reasonable range which is consistent with the functions to which they relate and with what is customary in the art to which they pertain.

All articles patents patent applications and other publications which have been cited in this disclosure are incorporated herein by reference.

The phrase means for when used in a claim is intended to and should be interpreted to embrace the corresponding structures and materials which have been described and their equivalents. Similarly the phrase step for when used in a claim is intended to and should be interpreted to embrace the corresponding acts which have been described and their equivalents. The absence of these phrases in a claim means that the claim is not intended and should not be interpreted to be limited to any of the corresponding structures materials or acts or to their equivalents.

The scope of protection is limited solely by the claims which now follow. That scope is intended and should be interpreted to be as broad as is consistent with the ordinary meaning of the language which is used in the claims when interpreted in light of this specification and the prosecution history which follows and to encompass all structural and functional equivalents. Notwithstanding none of the claims are intended to embrace subject matter which fails to satisfy the requirement of Sections 101 102 or 103 of the Patent Act nor should they be interpreted in such a way. Any unintended embracing of such subject matter is hereby disclaimed.

Except as stated immediately above nothing which has been stated or illustrated is intended or should be interpreted to cause a dedication of any component step feature object benefit advantage or equivalent to the public regardless of whether it is or is not recited in the claims.

