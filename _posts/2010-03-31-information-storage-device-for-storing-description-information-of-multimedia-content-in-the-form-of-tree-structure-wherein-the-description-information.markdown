---

title: Information storage device for storing description information of multimedia content in the form of tree structure wherein the description information is generated using a keyword and ID information representative of the keyword as new leaves of the tree structure
abstract: There are provided a storage device and a computer-readable medium capable of efficiently storing keywords contained in description information and efficiently retrieving the keyword. A list producing portion () extracts the keywords from the description information and produces a keyword list correlating the keywords with the scene information containing the keywords. A description information converter () converts the keywords contained in the keyword list received from the list producing portion () among the keywords contained in the externally received description information into reference information for specifying the keywords in the keyword list received from the list producing portion (). A storage () stores the converted description information provided from the description information converter () and the keyword list provided from the list producing portion ().
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08260819&OS=08260819&RS=08260819
owner: Sharp Kabushiki Kaisha
number: 08260819
owner_city: Osaka
owner_country: JP
publication_date: 20100331
---
This application is a divisional application of U.S. patent application Ser. No. 11 667 815 entitled STORAGE DEVICE AND RECORDING MEDIUM by Shuichi Watanabe and Jiro Kiyama the same inventors as the inventors of this divisional application filed on 15 May 2007 which application claims priority from International Application PCT JP2005 020289 dated 4 Nov. 2005 and Japanese Application No. JP 2004 351558 dated 3 Dec. 2004.

The present invention relates a storage device and a computer readable medium and particularly to a storage device and a computer readable medium that efficiently store description information describing details of multimedia.

Owing to increase in capacity of movie recording devices and widespread use of fast broad band networks in recent years a large amount of movies have been handled more often than ever and therefore a manner for efficiently retrieving and managing movies has been required.

Intrinsically a movie is searched for details of scenes contained therein. For such searching or retrieval it is necessary to replay successively the movie and determine the details. However this is not practical for a large amount of movies. Therefore description information describing details of movies are prepared in advance for each movie so that the movie retrieval can be performed based on the description information.

As disclosed in Japanese Patent Laying Open Nos. 05 282379 patent reference 1 and 08 110912 patent reference 2 the description information is often configured as data having a tree structure for allowing easy retrieval.

Referring to a whole movie is formed of four scenes 1 4 . For each scene the description information describes time information start time and length of the scene a title of the scene and actors appearing in the scene.

Based on the above description information a user can know that an actor Keiko KUBO appears in a scene 1 and can reproduce the scene 1 in which Keiko KUBO appears from the whole movie according to the time information of start time 00 00 00 length 3 mins of the scene 1 . As described above the description information is very effective at the movie retrieval.

Referring to the actual description information is given as data strings and each of items in each scene is individually described as the data. The individual data describing details of each item such as names of actors will be referred to as a keyword .

However from the keywords in the description information illustrated in and particularly from the keywords representing the actors it can be seen that some of the actors appears in a plurality of scenes.

More specifically even when a keyword in a certain scene is the same as a keyword included in another scene each of these keywords is recorded as an independent keyword so that the description information becomes redundant and large in total quantity.

The invention has been made for overcoming the above problem and an object of the invention is to provide a storage device and a computer readable medium that can efficiently store keywords included in description information.

According to the invention a storage device for storing description information describing details of multimedia contents and including a keyword includes a description information converter providing a converted description information by converting the keyword in the description information into reference information for specifying the keyword and a storage storing a list correlating the keyword with the reference information and the converted description information provided from the description information converter.

Preferably the storage device further includes a list producing portion producing the list by extracting the keyword in the description information.

Preferably the storage device further includes a position information extractor extracting position information indicating a position in the multimedia contents of the keyword to be converted into the reference information by the description information converter and the storage further stores the position information extracted by the position information extractor.

Preferably the list producing portion adds the position information extracted by the position information extractor to the list in such a fashion that the position information is correlated with the keyword.

Preferably the list producing portion adds the position information extracted by the position information extractor to the list in such a fashion that the position information is correlated with the reference information specifying the keyword.

Preferably the description information converter converts in addition to the reference information the position information indicating another position of the same keyword in the multimedia contents as the keyword to be converted into the reference information based on the position information extracted by the position information extractor.

Preferably the description information converter converts a list correlating the keyword with the reference information in addition to the description information.

According to the invention a storage device for storing description information describing details of multimedia contents and including keywords includes a description information converter converting each of a plurality of the same keywords included in the description information except for at least one of the same keywords into reference information specifying the above at least one keyword and a storage storing the converted description information provided from the description information converter.

Preferably each of the at least one keyword in the description information bears ID information representing itself and the reference information specifies the at least one keyword by indicating the ID information.

According to the invention a computer readable medium bears description information describing details of multimedia contents and including a keyword. The description information includes description data describing details of the multimedia contents using reference information for specifying the keyword instead of using the keyword and a list correlating the keyword with the reference information.

Preferably the description information further includes position data representing a specific position in the multimedia contents of each of the keywords described using the reference information.

Preferably the position data is added to the list in such a fashion that the position data is correlated with each of the keywords.

Preferably the position data is correlated with the reference information specifying each of the keywords in the list.

Preferably the description data includes position data representing a specific position in the multimedia contents of the same keyword as the keyword described using the reference information.

Preferably the description data includes a list correlating the keyword with the reference information.

According to the invention a computer readable medium bears description information describing details of multimedia contents and including a keyword. The description information is formed by replacing each of a plurality of the same keywords included in the description information except for at least one of the same keywords with reference information specifying the at least one of the keywords.

Preferably each of the above at least one keyword in the description information includes ID information representing itself and the reference information specifies the at least one keyword by indicating the ID information.

According to the invention since the details of the multimedia contents are described using the reference information specifying the keyword included in the description information instead of using the keyword the data quantity of the keywords included in an overlapping fashion can be reduced to a data amount of the reference information and the data of the whole description information can be reduced. Therefore the keywords included in the description information can be efficiently stored.

Embodiments of the invention will now be described with reference to the drawings. The same or corresponding portions bear the same reference numbers and description thereof is not repeated.

Referring to a storage device receives description information from a description information producing device . When a movie already including the description information is provided description information producing device can be eliminated. Storage device is formed of a keyword determining portion a position information extractor a list producing portion a description information converter and a storage .

Keyword determining portion determines whether a keyword included in the externally received description information is present in a keyword list received from list producing portion or not. When the keyword included in the externally received description information is not present in the keyword list keyword determining portion provides the keyword in question and an instruction for newly registering this keyword to list producing portion . When the keyword included in the externally received description information is present in the keyword list keyword determining portion provides information specifying the keyword in the keyword list and an instruction for additionally registering this keyword to list producing portion . The keyword that is determined to be registered is provided to position information extractor by keyword determining portion .

From the description information position information extractor extracts data representing scene information as to where the keyword that is provided from keyword determining portion for the new registration or additional registration is contained and provides the extracted data to list producing portion .

List producing portion produces a keyword list that correlates the keyword with the scene information as to where the keyword in question is contained. When list producing portion receives the keyword and the instructions for newly registering the received keyword from keyword determining portion it registers the keyword in the keyword list and further registers the scene information received from position information extractor in a fashion related to the registered keyword. When list producing portion receives the information specifying the keyword and the instructions for additionally registering the received keyword from keyword determining portion it adds the scene information received from position information extractor to the list in a fashion related to the keyword. Further list producing portion provides the keyword list thus produced to description information converter and storage .

Description information converter converts the keyword that is among the keywords in the externally received description information and particularly is included in the keyword list received from list producing portion . By this conversion description information converter produces the reference information for specifying the keyword in the keyword list received from list producing portion and provides the converted description information to storage .

Storage stores the converted description information provided from description information converter and the keyword list provided from list producing portion .

Description information producing device produces the description information from the movie provided thereto. For example description information producing device may be configured to analyze the input movie e.g. using a movie recognizing technology and thereby produce the description information or may be configured such that a user provides the description information while recognizing the movie.

Storage device according to the first embodiment receives the conventional description information illustrated in and produces the keyword list as described below.

Referring to the keywords representing the actors describes specific names of the actors and the same data repetitively appears in a plurality of scenes.

Therefore for retrieving scenes in which the same actor Wataru WADA appears it is necessary to determine throughout the description information whether the keyword Wataru WADA is present or not. Therefore the retrieval requires a long time and lowers a performance for other processing during the retrieval processing. Accordingly processing is performed to produce a keyword list additionally including information about positions where the same keywords are present.

According to the first embodiment processing is performed primarily on the keywords that may repetitively appear in the description information. The processing is performed on some other items such as character names i.e. names of characters in the movie and object names i.e. names of objects appearing in the movie.

In an ordinary case it is merely required to perform the keyword determination on the same items and the determination on different items is not required e.g. for the following reason. Since each actor is assigned a character name in a play or the like each keyword stored in the character names differs from any keyword stored in the actors except for the case where the actor s name is used as the character name as it is.

Referring to list producing portion produces an ID information a keyword value value and scene information scenes .

Scene information stores information about scenes in which the keywords stored in keyword value are present.

Referring to and when the second keyword Keiko KUBO described in the item of the actors is provided to storage device keyword determining portion provides the keyword Keiko KUBO and an instruction for newly registering to list producing portion because this keyword Keiko KUBO is not present in the keyword list received from list producing portion . Also keyword determining portion provides the keyword Keiko KUBO to position information extractor .

Position information extractor receives the keyword Keiko KUBO determined by keyword determining portion extracts the scene information storing this keyword and provides a scene number 1 to list producing portion .

List producing portion performs new registration in the keyword list according to the keyword Keiko KUBO received from keyword determining portion and the instruction for new registration as well as the scene number 1 received from position information extractor .

Thereby the keyword Keiko KUBO and the scene number 1 are stored in the keyword list produced by list producing portion with an ID number 2 .

Referring to and when an initial keyword Wataru WADA stored in the item of actors of the scene 2 is provided to storage device keyword determining portion provides an ID number 3 and an instruction for additional registration to list producing portion because the keyword Wataru WADA is present at the ID number 3 in the keyword list received from list producing portion . Keyword determining portion provides the keyword Wataru WADA to position information extractor .

Position information extractor receives keyword Wataru WADA determined by keyword determining portion extracts the scene information storing the keyword and provides a scene number 2 to list producing portion .

List producing portion stores the scene number 2 in the row designated by the ID number 2 received from keyword determining portion .

Thereafter list producing portion produces the keyword list from the externally provided description information in a similar manner.

Referring to list producing portion produces a list that relates to the keywords stored in the item of the actors included in the description information illustrated in and this list correlates each keyword with the scene information storing the keyword in question.

Referring to list producing portion may provide the details of the list illustrated in in the description information form.

In the foregoing description the scene numbers allocated to the respective scenes are handled as the position information to be handled as the scene information in the contents. For example when a multi level or hierarchical structure in which each scene is subdivided into sub scenes two dimensional data M N representing a sub scene N of a scene M may be handled as the scene information position information . An expression form of scene M sub scene N representing a path in the tree structure may be handled as the scene information position information . Further a start time of the like of the scene may be handled as the position information.

In the above example ID information of the keywords is formed of consecutive numbers assigned to the respective keywords. However another information may be employed provided that it can distinguish each keyword from the others. Further ID information is not essential and the list may consist of only a keyword value and scene information . In this case keyword value itself is used as the information for the keyword distinction.

The purpose of producing the keyword list in is to avoid overlapping of the same keywords recorded in the description information and to avoid increase in data quantity due to such overlapping. Therefore the data quantity can not be effectively reduced in connection with a keyword such as Keiko KUBO that appears only once in the description information as illustrated in . Accordingly list producing portion may perform the processing of eliminating the keywords not overlapping in the description information from the list.

Keyword determining portion may receive the description information in which each keyword has already born a flag indicating whether the keyword is to be registered in the keyword list or not and thereby may determine according to the flag whether the keyword is to be registered in the keyword list or not. For example keyword determining portion receives for each keyword included in the description information the description information bearing a flag indicating that the keyword in question appears only once in the description information or that it appears multiple times and determines according to the value of the flag not to register the keyword appearing only once in the keyword list. Thereby the keyword appearing only once does not require the determination with respect to the keyword registered in the keyword list so that the processing can be performed faster.

Further the order of the keywords in the keyword list produced by list producing portion may be the same as that of the appearance in the description information but the keywords may be arranged in the dictionary order the alphabetical order or the order of the Japanese syllabary . It can be expected that the arrangement of the keywords in the dictionary order can further improve the retrieval efficiency.

Referring to and description information converter receives the keyword list from list producing portion and converts the keywords included in the externally provided description information into reference information used for specifying the keywords in question in the keyword list. Description information converter provides the converted description information to storage .

In the first embodiment the ID number stored in ID information in the keyword list illustrated in is used as reference information .

As described above by using the keyword list produced by list producing portion and the description information converted into the reference information the same details as those described in the original description information can be stored while reducing a data quantity.

When a plurality of lists are present it is desired that the information for specifying the keyword list itself is employed as the reference information in addition to ID number of the keyword list.

As the reference information the position of the path in the description information format illustrated in may be used instead of the foregoing ID number. Further the keywords stored in the keyword list may employ actual data record positions absolute addresses of data or relative addresses from a fixed position . When the list and the description information are recorded on the same record medium the offset distances between the reference information and the keywords in the list may be employed.

Description information converter that converts the keyword in the description information into the reference information may also convert the keyword into the keyword and the reference information. Thus it may be configured to add the reference information while holding the keyword.

A comparison may be made between the data quantity of the keywords and the data quantity of the reference information and the keywords or the reference information having a smaller data quantity may be used so that the whole data quantity can be reduced. Accordingly description information converter may be configured to select the operation i.e. to convert each keyword to the reference information or to use the keyword as it is before converting the keyword into the reference information. In this case it is desired that the description information additionally includes additional information such as a flag indicating that the keyword data itself is recorded or that the converted reference information is recorded.

Referring to keyword determining portion extracts the keyword from description information and provides the extracted keyword to position information extractor step S .

Position information extractor extracts the scene information corresponding to the keyword provided from keyword determining portion step S . Position information extractor provides the extracted scene information to list producing portion .

Keyword determining portion determines whether the extracted keyword is present in the keyword list received from list producing portion or not step S .

When the extracted keyword is not present in the keyword list NO in step S keyword determining portion provides the keyword and an instruction for newly registering the keyword to list producing portion . Thereby list producing portion newly registers the keyword received from keyword determining portion and the scene information received from position information extractor in the keyword list step S .

When the extracted keyword is present in the keyword list YES in step S keyword determining portion provides the information specifying the keyword in question and the instruction for additionally registering the keyword to list producing portion . Thereby list producing portion additionally registers the scene information received from position information extractor in a fashion related to the keyword that is already registered and is specified by the specifying information received from keyword determining portion step S .

Since no keyword is registered in the initial state the keyword that is first read is always newly registered.

List producing portion determines whether the reading of the description information has ended or not step S .

When the reading of the description information has not ended NO in step S list producing portion provides an instruction for continuing the keyword extraction. Thereby keyword determining portion continues the keyword extraction from the description information step S .

When the reading of the description information has ended YES in step S list producing portion notifies description information converter of the end of the description information reading and provides the produced keyword list to storage . Thereby description information converter converts the keyword data in the externally provided description information into the reference information for the keyword list and provides it to storage step S .

Storage stores the converted description information provided from description information converter as well as the keyword list provided from list producing portion step S .

Description will now be given on the case where the movie retrieval is performed using the description information stored in a storage according to the first embodiment.

Referring to the user provides an instruction for starting a retrieval process while an intended scene is being replayed or paused step S . The retrieval process thus started obtains the scene information at the time of reception of the user s start instruction step S . The retrieval process obtains a data type included in the obtained scene step S . Further the retrieval process describes a retrieval display according to the obtained data type step S .

The user selects the data type used for the retrieval on the display. For example the user selects the data type of the actor. Thereby the retrieval process obtains the keywords included in the selected data type step S . Further the retrieval process describes the keywords included in the selected data type on the retrieval display step S .

Further the user selects the intended keyword. For example the user selects the keyword Akira ABE . Thereby the retrieval process obtains the scene information in the description information containing the selected keyword step S . The retrieval process displays the scene including the keyword selected by the user based on the obtained scene information step S .

In the foregoing first embodiment as illustrated in the description information includes for each scene the time information start time and length the title and the information of the actors appearing in the scene. However the structure and details of the description information are not restricted to the above. For example the description information may have a multi level or hierarchical structure in which each scene is subdivided into sub scenes. Also the description information may additionally include as the information belonging to the scene feature information such as a representative color and a degree of motion in addition to text information such as a commentary. Instead of the tree that represents one movie as a whole a tree structure may be configured such that a root node highest node represents all programs broadcasted on one channel divided nodes at the first level represent the programs respectively and each of divided nodes at the second level represents the scene included in the program.

As illustrated in it has been described that the description information that is prepared in advance is received and converted. However the process may be configured to perform the analysis in the same stage as the production of the description information and to perform simultaneously the production of the keyword list and the conversion into the reference information.

According to the first embodiment the details of the multimedia contents are described using the reference information specifying the keywords instead of using the keywords included in the description information. Therefore the data quantity of the keywords that are included in the description information in the overlapping fashion can be reduced to the data quantity of the reference information and the data quantity of the whole description information can be reduced. Accordingly the keywords included in the description information can be efficiently stored.

According to the first embodiment the keyword list stores all the scene information including the keywords. Therefore even when the keyword included in the overlapping fashion in the description information is to be retrieved the scene information including the keyword in question can be obtained using the keyword list. Accordingly it is not necessary to search the whole description information for the keyword and the retrieval can be performed efficiently and rapidly.

According to the first embodiment it is not necessary to reregister the keyword included in the description information that is once registered in the keyword list. Therefore the description information can be prepared while avoiding such a problem that an intended scene cannot be retrieved due to misspelling during entry of the same keyword. Accordingly it is possible to prevent lowering of the retrieval precision that may be caused by a mistake in entry during production of the description information. Further the keywords included in the description information can be edited only by editing the details of the keyword list so that the description information can be efficiently edited.

The first embodiment has been described in connection with the case where the keywords are extracted from description information to produce the keyword list.

A second embodiment will now be described in connection with the case where a list formed of keywords included in description information is provided in advance.

In some cases movie contents include as production information a credit list including a list of actors of the movie and the like.

When the credit list is annexed the keyword list is not produced and reference information referring to the annexed list is used.

Referring to storage device externally receives the description information and the credit list. Storage device is formed of a keyword determining portion a position information extractor a list producing portion a description information converter and a storage .

Keyword determining portion extracts the keyword included in the externally received description information and obtains the reference information that specifies the extracted keyword in the externally received credit list. Keyword determining portion provides this reference information to list producing portion and position information extractor .

Position information extractor receives the keyword determined by keyword determining portion extracts the data representing scene information storing this keyword from the description information and provides it to list producing portion .

List producing portion externally receives the credit list. List producing portion produces a keyword list that correlates the reference information specifying the keywords in the credit list with the scene information storing the keywords. List producing portion adds the scene information received from position information extractor and correlates it with the reference information received from keyword determining portion . Further list producing portion provides the keyword list thus produced to storage .

Description information converter replaces the keywords that are included in the externally received description information and particularly are included in the externally received credit list with the reference information for specifying the keywords in the credit list. Description information converter provides the converted description information to storage .

Storage stores the converted description information provided from description information converter as well as the keyword list provided from list producing portion .

Referring to the keywords included in the items of the description information are stored on an item by item basis.

Referring to credit list is formed of ID information and a keyword value . Description information converter converts the keywords included in description information into reference information for specifying the keywords in credit list . Reference information is ID information in credit list .

Therefore the keyword of keyword value included in credit list can be specified using reference information .

Keyword list is formed of ID information that is the same as ID information in credit list as well as scene information . List producing portion adds the scene information received from position information extractor and correlates it to the reference information received from keyword determining portion .

Since reference information specifying the keywords in credit list and scene information are recorded in a correlated fashion ID information of credit list is obtained according to the keyword required by the user and scene information corresponding to ID information that is the same as ID information thus obtained is obtained in keyword list . Thereby the scene information containing the keyword in question can be retrieved.

Keyword list includes ID information for establishing the correlation with the keywords recorded in credit list . However the keyword list may have the rows arranged in the same order relationship as the keywords in the credit list whereby the ID information can be eliminated.

According to the second embodiment the keyword list is produced by correlating the reference information specifying the keywords in the credit list with the scene information so that the keyword list does not store the keywords. Therefore even when the description information includes many keywords the data quantity of the keyword list can be kept small. Accordingly the data quantity of the whole description information including the keyword list can be small.

According to the second embodiment it is not necessary to produce the keyword list by extracting the keywords from the description information so that the conversion processing of the description information can be performed fast.

The second embodiment has been described in connection with the case where the keyword list stores all the scene information items each including the keyword.

A third embodiment will now be described in connection with the case where the description information additionally includes information that specifies for each keyword the other scene s in which the same keyword is present.

A storage device according to the third embodiment has substantially the same structure as storage device according to the second embodiment shown in and therefore description thereof is not repeated.

Credit list is substantially the same as that in the second embodiment and therefore description thereof is not repeated.

Referring to the keyword included in description information is converted into reference information specifying the keyword in credit list as well as link information specifying the scenes where the same keyword is present.

Link information represents the scene information about the next scene in which the same keyword will appear.

For example link information next 2 is added to the keyword Akira ABE indicated by reference information ref 1 included in the scene 1 . This link information next 2 represents that the same keyword Akira ABE will appear in a second scene from the current scene. Thus the scene 3 that is the second scene from the scene 1 includes the same reference information ref 1 for specifying the keyword Akira ABE . Since link information corresponding to reference information ref 1 included in the scene 3 is next 1 the same keyword will appear in the next scene 4 . Link information of reference information ref 1 included in the scene 4 is next 0 . Link information next 0 represents that the same keyword will not appear in the subsequent description information and entry list is referred to when link information next 0 is received.

Entry list stores the scene information of the scenes each correlated with the keyword which appears first in the description information. In the foregoing example when entry list is referred to according to link information next 0 the entry point corresponding to the ID number 1 correlated with the keyword Akira ABE is the scene 1 .

As described above all the scenes including the keywords Akira ABE can be obtained by substantially circulating through description information and entry list .

The link information may be required merely to indicate linkages about the scenes in which the same keyword is present. Alternatively it may indicate next storage positions of the same keywords specifically of the reference information indicating the same keywords . Therefore the link information may be provided by the path information of the tree or may be implemented using the data positions absolute relative addresses where the reference information is stored or offset distances to the next reference information storage positions.

According to the third embodiment the scene information containing the respective keywords is described in the description information so that the entry list has a constant size regardless of the data quantity of the description information. The scene information items described in the description information are mutually linked. Therefore when the scenes including the same keyword are to be continuously retrieved or in a similar case the storage capacity can be reduced as compared with the case where all the scene information is to be obtained in advance.

In the first to third embodiments described above the list correlating the keywords with the reference information is separated from the description information.

In a fourth embodiment described below the description information contains the list correlating the keywords with the reference information.

A storage device according to the fourth embodiment has substantially the same structure as storage device according to the first embodiment of the invention shown in and therefore description thereof is not repeated.

Description information converter in the fourth embodiment performs converting processing on each of the keywords registered in the keyword list produced by list producing portion and particularly at one position of the description information such as a position where each of the keywords is first stored and thereby converts the keyword into the keyword data itself and the reference information for specifying the keyword data. Further description information converter converts the keywords that are the same as the keyword in question but are present in different positions and more specifically converts the same keywords in the description information into the reference information for specifying the keywords in question.

Referring to description information converter adds ID information for specifying the keywords Akira ABE Keiko KUBO and Wataru WADA for scene 1 where these keywords are first stored. Each of the keywords stored after the scene 1 is converted into reference information correlated with ID information .

As described above since the description information includes the list for storing the respective keywords and the reference information in the correlated fashion it is not necessary to store each keyword in a separated fashion. Therefore list producing portion produces the keyword list formed of the reference information and the scene information similarly to keyword list illustrated in .

Further storage stores the description information provided from description information converter and containing the list that correlates the keywords with the reference information and also stores the keyword list provided from list producing portion and correlating the reference information with the scene information.

In view of data error resistance the same keyword and the same ID information may be described at a plurality of positions in the description information so that these can be referred to at each position.

According to the fourth embodiment since it is not necessary to store the list of the keywords correlated with the reference information the details of the movie can be described using only the data in the description information. Therefore even when the description information for many movies is present it is required to process only the reference information so that the information can be handled more easily than the case where the reference information and the lists are to be processed simultaneously.

According to the fourth embodiment the data can be held without causing any change in format of the original description information. Therefore a routine for newly interpreting a data format is not required and the original description information and the converted description information can be handled in substantially the same manner.

Computer includes a CPU Central Processing Unit executing programs a ROM Read Only Memory a RAM Random Access Memory and an HDD Hard Disk Drive for storing the programs and data an interface for connection to external record devices such as a DVD Digital Versatile Disk and a memory card a communications device for connection to various communications networks including the Internet and a bus for data transmission reception between various sections and portions.

Output is formed of a monitor a speaker a display and or the like that display or output movies sounds characters and the like.

ROM RAM or HDD stores a keyword determining program a position information extracting program a list producing program and a description information converting program that implement keyword determining portion or position information extractor or list producing portion or and description information converter or in storage device or according to the first to fourth embodiments respectively. CPU loads and executes the stored programs. Alternatively the above various programs may be recorded on an external record medium of a computer readable type and the device may be configured to load the programs therefrom via interface for executing the programs.

CPU executes the loaded keyword determining program. Thereby CPU reads the keywords included in the description information stored in RAM or HDD compares them with the keywords included in the keyword list stored in RAM or HDD and determines whether the keywords in question are registered or not.

CPU executes the loaded position information extracting program and extracts the scene information corresponding to the keywords.

CPU executes the loaded list producing program and operates according to the result of the determination by the keyword determining program to register newly or additionally the keywords and the scene information of the keywords in the list that is stored in RAM or HDD .

Further CPU executes the loaded description information converting program. Thereby CPU converts the keywords in the description information stored in RAM or HDD into the reference information according to the list stored in RAM and HDD and records the description information thus converted in RAM or HDD . Further CPU records the keyword list and the entry list produced by the list producing programs as well as the externally received credit list in RAM or HDD .

Instead of directly overwriting the original description information with the information thus changed the description information may be copied to RAM or HDD and the copied description information may be converted.

CPU may record the converted description information on an external computer readable medium via interface . Further CPU may record it on another device via a communications network connected to communications device .

The computer readable mediums storing the description information keyword list entry list credit list and the like are not restricted to ROM RAM and HDD and may be mediums fixedly bearing the description information such as a flexible disk cassette tape MO Magneto Optical Disk MD Mini Disk DVD Digital Versatile Disk ROM RAM R RW SD memory card IC card including memory card optical card mask ROM EPROM EEPROM flash ROM and other semiconductor memories.

According to the fifth embodiment since transmission reception of data such as description information to from another device can be readily performed via the record medium or communications network even a movie reproducing device not having a function of efficiently storing the description information can achieve substantially the same effects as those in the first to fourth embodiment.

Although the present invention has been described and illustrated in detail it is clearly understood that the same is by way of illustration and example only and is not to be taken by way of limitation the spirit and scope of the present invention being limited only by the terms of the appended claims.

