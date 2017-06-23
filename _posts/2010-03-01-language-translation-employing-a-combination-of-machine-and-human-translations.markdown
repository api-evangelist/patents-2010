---

title: Language translation employing a combination of machine and human translations
abstract: A computer-implemented method of translating text from a source language to a target language includes the steps of (a) detecting a source language on a first communication device, (b) detecting a location of the first communication device, (c) determining the target language based upon the detected location of the first communication device, (d) receiving an input for translation from the first communication device, (e) displaying a list of popular source phrases that are similar to the received input on the first communication device, (f) translating a user selected similar popular source phrase if the user selects the similar popular source phrase, else translating the input by means of a machine translation engine, and (g) displaying the translation output of the user selected similar popular source phrase if the user selected the similar popular source phrase, else determining if the translation output from the machine translation engine has been approved by a human translator, submitting the translation output from the machine translation engine to a human translator and displaying the translation output from the machine translation engine together with a measure of the accuracy of the translation output from the machine translation engine.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08843359&OS=08843359&RS=08843359
owner: 
number: 08843359
owner_city: 
owner_country: 
publication_date: 20100301
---
The present invention claims priority from provisional patent application Ser. No. 61 156 244 filed on Feb. 27 2009 entitled System Method and Article of Manufacture for Providing a Mobile Device Translation Service the entire disclosure of which is incorporated herein by reference.

The present invention relates generally to language translation systems and more particularly to a system computer implemented method and article of manufacture that provides language translation and employs a combination of machine and human translations.

Machine language translation systems are well known in the art and provide translation of a limited number of languages based upon information stored in a database. The information includes words phrases and sentences in a source language and corresponding translated words phrases and sentences in a target language. As the database is populated with words phrases and sentences derived from dictionaries and translation algorithms the information stored in the database is not always accurate or up to date. Nor does the information include all the words phrases and sentences commonly used in the source and target languages. Furthermore the information typically does not include the variation that characterizes dialects of a same language spoken in different geographical locations.

To provide for a language translation system that is more robust some machine language translation systems include a means by which a user can contribute a translation of a word phrase or sentence. A machine language translation system having this feature is Google Translate translate.google.com . While user submitted translations can provide a translation of a word phrase or sentence not previously found in the database or provide an alternative translation for an existing translation the accuracy of the user submitted translation is not verified by the machine language translation system or by the users of the system.

A human based language translation system that features user ratings of translated phrases is described in U.S. Patent Application Publication No. 2009 0198487 A1 entitled Community Translation on a Social Network . Text phrases including content from social networking objects are translated by members of the social network and stored in a translated phrases store. Within the social network community translations of text phrases include ratings that indicate the perceived quality of the translated phrases by members of the social network. Ratings may be used for determining which translated phrases to display when a translation of a source phrase is requested. Members can vote on the quality of translated phrases submitted by other members and a weight of a member s vote may indicate the voter s credibility and be based on the voter s translation ability as determined by votes received on the voter s translations. The described method does not employ machine translation and relies solely upon member translations of text phrases used within the social network.

The limitations of prior art language translation systems are addressed by embodiments of the invention that combine machine and human translations to provide a language translation system that is accurate up to date and location based.

In accordance with an embodiment of the invention a computer implemented method of translating text from a source language to a target language comprising the steps of a detecting a source language on a first communication device b detecting a location of the first communication device c determining the target language based upon the detected location of the first communication device d receiving an input for translation from the first communication device e displaying a list of popular source phrases that are similar to the received input on the first communication device f translating a user selected similar popular source phrase if the user selects the similar popular source phrase else translating the input by means of a machine translation engine and g displaying the translation output of the user selected similar popular source phrase if the user selected the similar popular source phrase else determining if the translation output from the machine translation engine has been approved by a human translator submitting the translation output from the machine translation engine to a human translator and displaying the translation output from the machine translation engine together with a measure of the accuracy of the translation output from the machine translation engine.

In accordance with another aspect of the invention detecting the location of the first communication device comprises detecting a GPS signal

In accordance with another aspect of the invention detecting the location of the first communication device comprises detecting an Internet Protocol address.

In accordance with another aspect of the invention receiving the input for translation from the first communication device comprises receiving an audio input.

In accordance with another aspect of the invention receiving the input for translation from the first communication device comprises receiving a text input.

In accordance with another aspect of the invention receiving the input for translation from the first communication device comprises receiving an image input.

In accordance with another aspect of the invention translating the user selected similar popular source phrase comprises searching a database phrasebook for a translation output corresponding to the selected similar popular source phrase.

In accordance with another aspect of the invention a context for the translation input is requested from the user.

In accordance with another aspect of the invention the translation output is sent to a second communication device.

In accordance with another aspect of the invention the translation output is provided as an audio signal.

In accordance with another aspect of the invention the translation output is provided as an SMS MMS message.

In accordance with another aspect of the invention the translation output is provided as an email message.

In accordance with another aspect of the invention the translation output is provided as an IM message.

In accordance with another aspect of the invention the translation output is played on the first communication device as an audio output.

In accordance with another aspect of the invention the translation output is displayed on the first communication device as an image output.

In accordance with another aspect of the invention a user suggested translation of the input is received and distributed to a human translator and translation suggestions and ratings from the human translator are provided to a moderator sorted by the ratings.

In accordance with another aspect of the invention approval from the moderator of the user suggested translation is received and a notification of the moderator approval is sent to the first communication device and added to the machine translation engine and a database phrasebook.

In accordance with another aspect of the invention the translation output from the machine translation engine is distributed to a human translator and translation suggestions and ratings from the human translator are provided to a moderator sorted by the ratings.

In accordance with another aspect of the invention the approval from the moderator of the translation output is received and a notification of the moderator approval sent to the first communication device and the approved translation output is added to the machine translation engine and to a database phrasebook.

In accordance with another aspect of the invention additional suggestions from the human translator are requested in the case where the moderator does not approve the received translation suggestions.

The figures show embodiments of the invention for illustration purposes only. Those skilled in the art will recognize that other embodiments of the systems and methods described herein may be employed without departing from the principles of the invention.

The language translation system and method employing a combination of machine and human translations may be implemented in a networked environment such as shown in . A server machine is operatively coupled to a communications network . The communications network is a multi layered network capable of connecting users desiring translations. The server machine includes components and functionality to communicate with a plurality of communication devices through the communications network and to provide language translation services as further described herein.

The plurality of communication devices are operatively coupled to the communications network and include laptop computers tablet computers desktop computers mobile phones smart phones POTS telephones and modems . By means of the plurality of communication devices users may communicate with the server machine to request a translation receive a translation suggest a translation and rate a translation.

With reference to communication devices and the server machine include a processor a memory input output I O components and a communication interface . The components are operatively coupled by means of a bus . The server machine further includes a translation engine and a database having a phrasebook . In an alternate embodiment communication devices may include the translation engine and the database having the phrasebook so that a user can access the language translation system of the invention when the communications network is not available.

A portion of memory is designated as addressable memory for program execution while another portion of memory is reserved for storage. Memory may further include an operating system application programs as well as an object store not shown . During operation the operating system is preferably executed by processor from memory . The operating system is preferably designed for mobile devices and implements database features that can be utilized by applications through a set of exposed application programming interfaces and methods. The objects in the object store are maintained by applications and the operating system at least partially in response to calls to the exposed application programming interfaces and methods.

Communication interface may include devices and programs that enable the mobile devices to send and receive information. These devices include wired and wireless modems satellite receivers and broadcast tuners. The mobile devices may also be directly connected to a computer to exchange data therewith.

Input output components include a variety of input devices such as a touch sensitive screen buttons rollers and a microphone as well as a variety of output devices including an audio generator a vibrating device and a display.

The translation engine is operable to receive and process input text words phrases and sentences and to output a text translation of the input text. The translation engine receives updates in the form of translation suggestions from human translators to provide increasingly accurate and up to date translations tailored to the location of the user . Operations performed by the translation engine may be performed or implemented with one or more hardware or software modules alone or in combination with other components of the server machine and communication devices 

The invention will now be described with reference to which show steps of a computer implemented method that implements the features of the invention. The method first detects whether source and target languages dialects have previously been stored on the communication device . If previously stored source and target languages dialects are detected then the previous source and target languages dialects are displayed to the user . If no source and target languages dialects are detected then a source language locale and location derived from a GPS signal or Internet Protocol address is detected . Device settings generally provide the source language locale. Examples of source language locale include English US English UK Spanish Spain Spanish Mexico and so on.

Following detection of the source language locale and location a list of source and target languages dialects is displayed to the user . The list is ordered by relevance to the device language locale and location data. For example if the detected device language locale is English US and the location of the device is Mexico then the list could include English and Spanish English and Zapotec English and Nahuatl and so on as the source and target languages dialects respectively. The target languages dialects displayed are the languages most commonly used in the location of the user. The user then selects the source and target languages dialects from the list and the user selection is displayed to the user . The user next confirms the selection or the displayed previous language dialect settings.

The invention provides user input of translation requests updates and translation suggestions in the form of voice text and image input. A determination is made and if the input is voice text or image respectively. If the input is voice then the input is detected converted to text and displayed to the user . If the input is text then the input is detected and displayed to the user . If the input is an image then the input is detected converted to text and displayed to the user . The user may then confirm the displayed text. If the user does not confirm the displayed text then user input text update is detected and user confirmation acquired .

A list of Similar Popular Source Phrases SPSPs is then displayed . SPSPs are stored in the phrasebook and include words phrases and sentences the translations of which have been approved by a human translator. SPSPs and translations thereof are stored in the phrasebook in a one to one relationship. SPSPs and their translations therefore provide translations in the target language dialect that are accurate up to date and reflect the target language dialect spoken in the location of the user .

The user may select a SPSP and if he does then the selected SPSP is translated by searching the phrasebook and the translated text displayed to the user . If the user does not select at SPSP then the text is submitted to the machine translation engine for translation. A determination is then made whether the translated text has been previously approved by a human translator. Human translators in accordance with the invention include users and translators compensated for their translation services. Human translators are ranked in relation to the number of translations submitted the accuracy of the translations submitted and the nature of the languages dialects in which the human translator is knowledgeable.

If the translated text has been previously approved by a human translator then the translation is displayed to the user. If not then the translated text is displayed to the user with a measure of the accuracy of the translation and a request for the context of the input text. The translated text and user supplied context is then submitted to a human translator.

Following the display of the translated text to the user the user may suggest an alternate translation. If a user suggestion is detected then the user suggestion is saved and a determination is made whether the translated text is to be sent through the communications network to another communication device . In the case where no user suggestion is detected the determination is made. If it is determined that the translated text is to be sent then a user send method is detected . If the user send method is an audio output then an audio signal of the translated text is sent . If the user send method is email then an email is sent . If the user send method is SMS MMS then a SMS MMS message is sent . If the user send method is IM then an IM message is sent .

If it is determined that the translated text is not to be sent to another communication device then a determination is made whether the translated text is to be output on the user s communication device as an audio output. If it is determined that the translated text is to be output on the user s communication device as an audio output then the audio output is played on the user s communication device. Otherwise a determination is made whether the translated text is to be output as a visual output. If it is determined that the translated text is to be output as a visual output then the translated text is output as a visual output on the user s communication device. Otherwise the method ends.

Translated text that has not been approved by a human translator and user suggestions of translations saved in step are distributed to a human translator or to a group of human translators for translation. Translation suggestions and ratings are received from the human translator or group of human translators and provided to a moderator sorted by ratings. The moderator preferably has knowledge of the source and target languages dialects and either approves or does not approve a translation suggestion. If the translation suggestion is approved by the moderator then a notification including the human approved translation is sent to the user who requested the translation. The human approved translation is also added to the phrasebook as a SPSP and to the machine translation engine .

If the translation suggestion is not approved by the moderator then the human translators are requested to provide more translation suggestions. Additional translation suggestions are received and provided to the moderator.

The method of the invention provides an end to end translation facility between two communication devices . The user may provide a voice text or image input in a source language dialect on his communication device and be provided with a translation in a target language dialect that the user can send to another user . Alternatively the translated text can be output to the user s communication device for local use as when the user is communicating with another person locally.

The translation engine and the database having the phrasebook may be disposed in the server machine or distributed in a plurality of computing machines. The communication devices may include the translation engine and the database having the phrasebook so that the user can access the language translation system of the invention when the communications network is not available

By combining machine and human translations the present invention provides a translation facility including a phrasebook that grows with use. As the number of Similar Popular Source Phrases increases reliance upon both machine translations and human translations is reduced to provide accurate and up to date translations in an efficient manner.

The present invention also provides translations from and to languages dialects that are not available using machine translators. By employing human translators that are fluent in languages not available for translation by machine translators the system and method of the invention is not limited to major languages.

By determining the location of the user the target languages dialects displayed are the languages dialects most commonly used in the location of the user. This feature provides for a level of specificity not provided by prior art machine translators.

The invention has been described in terms of a method including various steps and operations. In another embodiment of the invention a computer program product includes a computer readable medium containing computer program code which can be executed by a computer processor. Execution of the computer program code performs any or all of the steps and operations of the described method. Further in another embodiment of the invention an apparatus and or system may be configured to execute the computer program code. Finally in another embodiment of the invention a computer data signal embodied in a carrier wave or other tangible medium may include any embodiment of the computer program product or other data combination described herein.

The foregoing description of the embodiments of the invention has been presented for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise form disclosed. Many modifications and variations are possible in light of the above teaching. It is intended that the scope of the invention be limited not by this detailed description but rather by the claims appended hereto.

