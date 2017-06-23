---

title: Social network system and method for identifying cluster image matches
abstract: A social network application may identify images having common links between a first user's image collection and a second user's image collection. The common links may be identified through metadata or similar portions of the images. Using the first user's image collection, elements of interest may be identified and compared to a second user's image collection to find matches. When matches are found, the results may be selected from groups of results to show a diverse set of matches. The user may be presented with options to select and add matched images to the user's collection, as well as to browse more images that match one or more of the groups.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08983210&OS=08983210&RS=08983210
owner: Microsoft Corporation
number: 08983210
owner_city: Redmond
owner_country: US
publication_date: 20100521
---
This patent application claims priority to and the benefit of U.S. Provisional Patent Application Ser. No. 61 309 059 entitled Social Network System with Recommendations filed 1 March 2010 by Eyal Krupka et. al. the entire contents of which are hereby expressly incorporated by reference.

Social networks are applications that allow users to share personal and professional information with friends. In many instances social networks may allow users to post photographs videos and other content to be shared with their network of friends or associates.

A social network application may identify images having common links between a first user s image collection and a second user s image collection. The common links may be identified through metadata or similar portions of the images. Using the first user s image collection elements of interest may be identified and compared to a second user s image collection to find matches. When matches are found the results may be selected from groups of results to show a diverse set of matches. The user may be presented with options to select and add matched images to the user s collection as well as to browse more images that match one or more of the groups.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key features or essential features of the claimed subject matter nor is it intended to be used to limit the scope of the claimed subject matter.

A social network application may find images in other user s image collections that may be relevant to a first user. The images may be found by creating clusters that represent the images in the first user s image collection. In some embodiments images may be clustered on several orthogonal axes and independently analyzed on each axis. Comparisons between one image and the clusters may be performed by calculating a distance between the image and a centroid of a cluster as well as to an image that may be a nearest neighbor.

The size of the clusters may be used as a general measure of the relative importance of each cluster. When a set of image results are presented to a user images representing matches to each cluster may be included in the user interface according to the cluster size.

Throughout this specification like reference numbers signify the same elements throughout the description of the figures.

When elements are referred to as being connected or coupled the elements can be directly connected or coupled together or one or more intervening elements may also be present. In contrast when elements are referred to as being directly connected or directly coupled there are no intervening elements present.

The subject matter may be embodied as devices systems methods and or computer program products. Accordingly some or all of the subject matter may be embodied in hardware and or in software including firmware resident software micro code state machines gate arrays etc. Furthermore the subject matter may take the form of a computer program product on a computer usable or computer readable storage medium having computer usable or computer readable program code embodied in the medium for use by or in connection with an instruction execution system. In the context of this document a computer usable or computer readable medium may be any medium that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The computer usable or computer readable medium may be for example but not limited to an electronic magnetic optical electromagnetic infrared or semiconductor system apparatus device or propagation medium. By way of example and not limitation computer readable media may comprise computer storage media and communication media.

Computer storage media includes volatile and nonvolatile removable and non removable media implemented in any method or technology for storage of information such as computer readable instructions data structures program modules or other data. Computer storage media includes but is not limited to RAM ROM EEPROM flash memory or other memory technology CD ROM digital versatile disks DVD or other optical storage magnetic cassettes magnetic tape magnetic disk storage or other magnetic storage devices or any other medium which can be used to store the desired information and may be accessed by an instruction execution system. Note that the computer usable or computer readable medium can be paper or other suitable medium upon which the program is printed as the program can be electronically captured via for instance optical scanning of the paper or other suitable medium then compiled interpreted of otherwise processed in a suitable manner if necessary and then stored in a computer memory.

Communication media typically embodies computer readable instructions data structures program modules or other data in a modulated data signal such as a carrier wave or other transport mechanism and includes any information delivery media. The term modulated data signal can be defined as a signal that has one or more of its characteristics set or changed in such a manner as to encode information in the signal. By way of example and not limitation communication media includes wired media such as a wired network or direct wired connection and wireless media such as acoustic RF infrared and other wireless media. Combinations of any of the above mentioned should also be included within the scope of computer readable media.

When the subject matter is embodied in the general context of computer executable instructions the embodiment may comprise program modules executed by one or more systems computers or other devices. Generally program modules include routines programs objects components data structures and the like that perform particular tasks or implement particular abstract data types. Typically the functionality of the program modules may be combined or distributed as desired in various embodiments.

The diagram of illustrates functional components of a system. In some cases the component may be a hardware component a software component or a combination of hardware and software. Some of the components may be application level software while other components may be operating system level components. In some cases the connection of one component to another may be a close connection where two or more components are operating on a single hardware platform. In other cases the connections may be made over network connections spanning long distances. Each embodiment may use different hardware software and interconnection architectures to achieve the described functions.

Embodiment illustrates an example of a social network in which a user may have collection of images. The social network may be a web application in which various users may establish accounts in the social network and may manage image collections within the social network. A service operating within the social network infrastructure may analyze and compare the image collections.

The social network of embodiment may be any type of social network in which express or implied relationships may exist between users. In some social networks the relationships may be expressed by one user formally establishing a relationship with another user. Some social network may establish a one way relationship through such a relationship declaration while other social networks may establish a relationship when both users approve the relationship.

Some social networks may have informal relationships between users. For example an informal relationship may be established when two users exchange email messages or when the users communicate using another mechanism. For example a social network may be established for users who communicate in a chat room instant messaging service or other mechanism. In some cases a person s list of contacts in an email system or a mobile telephone may be used as an implied relationship for the purposes of establishing a social network relationship.

In some social networks a user may determine how images within their image collections may be shared. In some cases a user may select images that may be sharable to friends for which a relationship exists. In other cases a user may permit any user with which to share images.

The social network may be a formal social network in which each user may create an account to access the social network. In many such embodiments the users may access the social network through a web browser and the social network may be a web application. In many such embodiments a user may upload images to create an image collection inside the social network environment.

In less formal versions of a social network a user may store and manage an image collection on a personal computer or in repositories that are personally controlled or managed by the user. In such a social network the user may identify various storage locations from which images may be shared with other people. In some such social network the social network relationships may be maintained using infrastructure that may be merely an address exchange forum or other mechanism by which members may connect with each other.

The client device may have a set of hardware components and software components . The client device may represent any type of device that may communicate with a social network service .

The hardware components may represent a typical architecture of a computing device such as a desktop or server computer. In some embodiments the client device may be a personal computer game console network appliance interactive kiosk or other device. The client device may also be a portable device such as a laptop computer netbook computer personal digital assistant mobile telephone or other mobile device.

The hardware components may include a processor random access memory and nonvolatile storage . The hardware components may also include one or more network interfaces and user interface devices . In many cases the client device may include cameras or scanners that may capture images that may become part of a user s image collection.

The software components may include an operating system on which various applications may execute such as a web browser . In many social networking applications a web browser may be used to communicate with a social network service to access a social network application. In other embodiments a specialized client application may communicate with a social network service to provide a user interface. In some such embodiments such a client application may perform many functions that may be described in the social network service .

The client device may have a local image library that may include images that are collected from many different sources such as a camera scanner or other devices that may have image capture capabilities. The local image library may include images that are stored on other devices such as a server within a local area network or within a cloud storage service for example.

The client device may have several applications that may allow a user to view and manage the local image library . Example of such applications may be an image editor and image browser . In some cases a client device may have several such applications.

The local image library may include both still images and video images. In some embodiments still images and video images may be stored in different libraries and may be accessed edited and manipulated with different applications.

In some embodiments the client device may have an image pre processor . The image pre processor may analyze the image contents as well as various metadata associated with the image prior to associating the image with a social network. The pre processing may perform facial image analysis background analysis color histograms or other analyses on images available to the client. In other embodiments some or all of the functions performed by the image pre processor may be performed by the social network service . When an image pre processor is located on the client device a server device may be offloaded from performing such operations.

The client device may connect to the social network service through a network . In some embodiments the network may be a wide area network such as the Internet. In some embodiments the network may include a local area network which may be connected to a wide area network through a gateway or other device.

In some embodiments the client device may connect to the network through a hard wired connection such as an Ethernet connection for example. In other embodiments the client device may connect to the network through a wireless connection such as a cellular telephone connection or other wireless connection.

The social network service may operate on hardware platform . The hardware platform may be a single server device that has a hardware platform similar to the hardware components of the client device . In some embodiments the hardware platform may be a virtualized or cloud based hardware platform that operates on two or more hardware devices. In some embodiments the hardware platform may be a large datacenter in which many hundreds or thousands of computer hardware platforms may be used.

The social network service may operate within an operating system in some embodiments. In embodiments that have cloud based execution environments the notion of a separate operating system may not exist.

The social network may include multiple user accounts . Each user account may include metadata relating to the account as well as relationships that may be established between two or more users.

The user account metadata may include information about the user such as the user s name home address location as well as the user s likes and dislikes education and other relevant information. Some social networks may have emphasis on work related information which may include items like work history professional associations or other job related information. Other social networks may emphasize friends and family relationships where personal items may be emphasized. In some social networks very large amounts of personal metadata may be included while other social networks may have very little amount of personal metadata .

The relationships may associate one user account to another. In some embodiments the relationships may be one way relationships where a first user may share information with a second user but the second user may not reciprocate and may share no information or a limited amount of information with the first user. In other embodiments the relationships may be two way relationships where each user agrees to share information with each other.

In still other embodiments a user may allow some or all of their information to be shared to anyone including people who are not members of the social network. Some such embodiments may allow a user to identify a subset of information that may be shared to anyone as well as subsets that may be shared with other members of the social network. Some embodiments may allow a user to define subsets that are shared with different groups of social network members.

Each user account may include one or more image collections . The image collections may include images . Each image may include metadata which may be general metadata such as timestamp location information image size title and various tags. The tags may include identifiers for different social network members to which the image may relate.

In some embodiments the image metadata may contain metadata derived from the image contents. For example a facial analysis may be performed to identify any faces within the image and to create a facial representation or facial vector. The facial representation may be used to compare with other images for example. Other image contents that may be used to derive metadata may include texture analysis of background areas or a person s clothing color histograms of the entire image or portions of the image or other analyses.

The image metadata may be used to create clusters . The clusters may be groupings of images or elements from images. For example facial representations may be analyzed to identify clusters that contain similar facial representations. Similarly clusters may be created by grouping image analysis results from background areas of the images.

In some embodiments clusters may be created by grouping images based on metadata. For example several images that are taken during a certain time period may be grouped together as a cluster or images that are tagged with the same tag parameter may form a cluster. Examples of uses clusters may be found in embodiments and presented later in this specification.

In some embodiments the social network service may include an image pre processor that may analyze images to derive image metadata. The image pre processor may be used for instances where a client device may not have an image pre processor or when image pre processing is not performed prior to analysis. An example of the pre processing steps may be illustrated in embodiment presented later in this specification.

A comparison engine may compare two or more images using image analysis techniques or metadata analysis to determine the clusters . An example of the operations of a comparison engine may be found in portions of embodiment presented later in this specification.

A ranking engine may compare the various clusters to extract information such as the ranking or importance of the images or information attached to the images. An example of the operations of a ranking engine may be found in embodiment presented later in this specification.

An analysis engine may analyze and compare image collections to identify matches between the image collections. The analysis engine may use metadata analysis and image content analysis to identify matches.

In many embodiments a social network service may operate with a web service that may communicate with browsers or other applications operable on a client device. The web service may receive requests in Hyper Text Transmission Protocol HTTP and respond with web pages or other HTTP compliant responses. In some embodiments the web service may have an application programming interface API through which an application on a client device may interact with the social network service.

Image may represent a birthday party with two people. From the image two faces and may be identified. Several different facial recognition mechanisms or algorithms may be used to identify the faces and .

Once identified the faces and may be processed to create representations of the faces. The representations may be facial vectors or other representations that may allow numerical comparisons of different faces to each other.

In some embodiments additional image analyses may be performed. For example the clothing areas and may be identified by determining a geometrical relationship from the faces and respectively and capturing a portion of an image that may relate to the clothing being worn by the respective people.

Image analysis of clothing may be used to compare two images to determine if those images were taken at the same event. Such a conclusion may be drawn when two images contain similar faces and the images additionally contain similar clothing textures or color histograms. Such an analysis may assume that the images represent the same event because the people in the images may be wearing the same clothes.

Additionally a background area may be analyzed for texture analysis color histogram or other analyses. Such results may be compared to other images to determine similarities and matches between the images.

In the image the faces and may be identified and captured. Because the size of the faces and may be relatively small the clothing areas for the people of image may not be performed but a background area may be identified and analyzed.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment may be an example of a method by which the number of occurrences of a person s face in a user s image collection may be used as an approximation of the user s interest in the person or the importance of the person to the user.

The faces within the images may be analyzed compared and grouped together into clusters. Based on the size of the clusters the persons associated with the clusters may be ranked.

An image collection may be received in block . The image collection may be pre processed to identify faces and facial representations. An example of such a pre processing method may be illustrated in embodiment presented later in this specification.

Each image may be processed in block . For each image in block if no faces exist in block the process may return to block to process the next image. If one or more faces appear in the image in block each face may be separately processed in block . For each face in block the face object and the associated image reference may be added to a list in block . The image reference may be a pointer or other indicator for the image from which the face is taken.

In block the list may be analyzed to identify clusters based on a threshold value in block . The clusters may define a group of facial representations that relate to a single person.

One mechanism to determine a cluster may be to consider a facial representation as a vector. The similarity between any two vectors may be considered a distance in the vector space. When multiple facial representations reflect many different images of the same person the facial representation vectors may create clusters of vectors.

In many embodiments a threshold may be used as part of a mechanism to determine whether or not a given facial representation is close to another facial representation to be a match. The threshold may be determined in several different manners and one such manner may be illustrated in embodiment .

Each cluster may be analyzed in block . For each cluster in block if any members of the cluster do not have tags or other associated metadata in block the process may return to block to process another cluster.

If one or more of the members of the cluster in block contains tags or other metadata those tags may be applied to other cluster members in block . In some cases the user may be presented with a user interface device in block where the user may approve or disapprove the tags. If the user approves the tags in block the tags may be applied to all members of the cluster in block . If the user does not approve the tags in block the tags may not be applied to the members in block .

In many social network applications users may tag images with identifiers for specific people for example. The process of blocks through may represent a method by which such tags may be applied to other images automatically. In some embodiments the tags applied to the members of the cluster may be tags that relate to the person the cluster may represent. A simple example may be a tag that defines the person s name.

The clusters may be analyzed in block to rank the clusters according to size. The ranking may reflect the relative importance of the people to the user. The cluster rankings may be used in block to prioritize people in various applications.

For example a newsfeed may include messages status updates or other information that relate to people in a user s social network. Those items relating to important people may be highlighted or presented in a manner that captures the user s attention. Other items concerning people who do not appear often in the user s image collection may be presented in a secondary or non emphasized manner.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment illustrates an example of a method by which images from a second image collection may be compared to a first image collection to identify images in the second image collection that contain the same people as the first image collection.

A second image collection may be received in block . The second image collection may be pre processed in block . One example of a method for pre processing may be illustrated in embodiment presented later in this specification.

Each image in the second image collection may be processed in block . For each image in block if no faces are found in block the process may return to block to process the next image.

If faces are found in block each face object may be processed in block . For each face object in block a comparison may be made to the clusters of the first image collection in block to find the closest match. If the match does not meet the threshold in block the process may return to block to process the next face object. If the match is within the threshold in block the image is associated to the cluster in block .

After processing all of the images in block the result may be a list of images from the second image collection that match clusters in the first image collection. The list may be ranked in block according to the ranking that may be determined from the process of embodiment and presented to the user.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

The pre processing of embodiment may identify faces and create face vectors or some other numerical representation of a facial image for all images in an image collection.

If faces are found in block each face may be separately processed in block . For each face in block the image may be cropped to the face in block and a face object may be created from the cropped image in block . A face vector may be created in block which may be a numerical representation of the face image. The face vector and face object may be stored as metadata for the image in block .

After all the faces are processed in block if another image is available in block the process may loop back to block otherwise the process may stop in block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment may determine a threshold setting that may minimize false positive comparisons when comparing image collections. In many social network applications a relatively high confidence threshold may be useful to minimize the likelihood of incorrectly identifying a match. When selecting photographs or video images from a second user s image collection to match a first user s image collection an incorrect match may give a user a low confidence in the matching process. However a missed match where the match exists but the threshold does not permit the match to be detected may not be as detrimental to the user s confidence.

The process of embodiment gathers representative images from a user s friend s image collection to serve as a training set for comparisons. Facial comparisons may differ based on race skin color and other physical characteristics of those people associated with the user. The images selected may be from the user s friend s friends and may reflect the probable physical characteristics of the people in the user s image collection.

The process of embodiment may attempt to remove any people from the training set who may be likely to be in the user s image collection. This may be performed by examining any tags associated with the friend s images to ensure that the tags do not match the user s friends.

The user s friends may be identified in block . The user s friends may be determined from relationships within the social network as well as any other source. In some cases a user may belong to several social networks each with a different set of relationships. In such cases as many of those relationships may be considered as possible.

Each of the user s friends may be processed in block . For each friend in block each image in the friend s image collection is processed in block . For each image in block the tags associated with the image may be identified in block . If the tags are associated with friends of the user in block the image is not considered in block . By excluding the friends of the user in block the training set may not include images that are likely to be matches for the user but may include images of people having similar characteristics as people likely to be in the user s image collection.

If the tags indicate that the image may not be related to the user in block the image may be selected for the training set in block . In many cases the images selected for the training set may be a subset of all of the images in the friend s image collection. For example a process may select one out of every 100 or 1000 candidate images as part of a training set. In some embodiments a random selection may be made for the training set.

After selecting images to be in a training set in blocks through a facial pre processing may be performed on the training set in block . The pre processing may be similar to that of embodiment .

Each image of the user s image collection may be processed in block to set the threshold so that none of the images in the user s image collection match the training set. For each image in block if the image does not contain faces in block the process returns to block .

When the image contains faces in block each face may be processed in block . For each face in block the face object may be compared to face objects in the training set find the most similar face object in block . If the similarity is less than the threshold in block the process may return to block . If the similarity is greater than the threshold in block the threshold is adjusted in block so that the threshold is lower than the similarity in block .

After processing all of the images in the user s image collection in block the current threshold value may be stored in block and used for subsequent comparisons.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment is an example of a method that may be used to detect an event from metadata. The metadata may be metadata that may be derived from an image such as from facial analysis or other image analysis. The metadata may also be metadata that is not derived from the image such as a title timestamp or location information.

Embodiment may infer an event from the intersection of the image collections of two users. Such an intersection may occur when both users attend the same event and both take images of the event. For example two users may attend a birthday party or family gathering and take pictures of a family gathered for a meal. In another example two users may attend a conference sporting event or other public event and may take images of the gathering. In some cases the users may know about each other s attendance of the event and in other cases the users may be unaware that the other person has attended.

In block an image collection may be received from a first user. In block an image collection may be received from a second user. In some embodiments the information received may be just the metadata related to the images in the collection and not the actual images themselves.

The metadata from each image collection may be compared in block to find matches. The matches may be based on image analysis such as finding matching faces in images from two different collections. The matches may be based on metadata analysis such as finding images that have timestamps tags location information or other metadata that are matches.

In many cases the matches may be determined with some level of tolerance or variance. The matches identified in block may have a large amount of variance or tolerance as each match may be further evaluated in later steps. The matching in block may be a coarse or preliminary matching that may be further refined to identify a match with greater certainty.

The results of block may be a pair of images from each collection. In some cases the results may be a group of images from each collection that share similar metadata.

Each set of matched images may be compared in block . For each set of matched images in block the metadata may be compared in block to determine if an event can be inferred.

An event may be inferred based on several factors. Some factors may be weighted highly while other factors may be of a secondary nature. The determination of whether a match indicates an event or not may be determined using various heuristics or formulas and such heuristics or formulas may depend on the embodiment. For example some embodiments may have extensive metadata available while other embodiments may have fewer metadata parameters. Some embodiments may have sophisticated image analysis while other embodiments may have less sophisticated or even no image analysis.

A highly weighted factor may be in cases where the second user identifies the first user in one of the second user s images. Such metadata expressly identifies a link between the two image collections and indicates that both users were likely to be in the same place at the same time.

In some embodiments users may tag images in their collections with persons from their social network. In such embodiments a user may manually select an image and create a tag that identifies a friend in the image. Some such embodiments may allow the user to point to the face and attach the tag to a location on the image. Such tags may be considered reliable indicators and given higher weight than other metadata.

Other highly weighted factors may be very close proximity in space and time. Very close timestamps and physical location information may indicate that two users were at the same time and place. In some embodiments an image may include a point from which an image was taken as well as a direction that a camera was facing when the image was taken. When such metadata are available the overlap of the area covered by two images may be evidence of an event.

Some images may be tagged with various descriptors that are manually added by a user. For example an image may be tagged with Anna s Birthday Party or Tech Conference . When images from both image collections are similarly tagged the tags may be good indicators of an event.

The matches may be analyzed using image analysis to identify common events. For example a facial image match between images in both collections may be a good indicator of an event attended by and captured by both users. A facial image match may be further confirmed by similar background image areas and by clothing analysis of people associated with the matched faces.

When identifying a common event different combinations of factors may be used in different situations and different embodiments. For example an event may be determined by image analysis alone in some cases even when the metadata do not correlate. For example one user may purchase a camera device and may never correctly set the time and date in the camera or may have the time set to a different time zone than the other user. In such a case the timestamp metadata may be incorrect but the image analysis may indentify a common event.

In another example the metadata may identify a common event even though the image analysis may not identify any common faces background or other similarities.

Different embodiments may have different thresholds for identifying an event. In a typical social network use of embodiment the analysis may be performed to automatically apply tags to images based on the events. In such an embodiment a higher degree of certainty may be desired so that incorrect tags are not introduced into the image collection as noise. In another use the matching may be used to identify possible events that a user may manually examine to determine if an event actually did occur. In such a use the threshold to determine an event may have a much lower degree of certainty than in the other use case.

If an event is identified in block all images associated with the event may be identified in block . A metadata tag may be defined for the event in block and the tag may be applied to the images in block .

The images associated with the event may be determined by identifying images that are related to or share common metadata or other features with the matched images. For example two images may be matched one from either image collection. Once those images are matched any related images to the matched images within their respective collections may be identified in block .

The metadata tag in block may be generated by scanning the related images to determine if an event tag is associated with any of the related images. For example one of the images that was gathered in block may be tagged with an event tag such as Anna s Birthday . That tag may then be applied to all of the related images in block .

In some embodiments the event tag of block may be an automatically generated event tag that may identify how the match was determined. For example a match that was determined by common metadata having time and location information may have a tag that includes Jerusalem 22Feb2010 . Each embodiment may have different mechanisms for determining a tag.

In some embodiments the tag applied in block may not be visible to a user. Such a tag may be used by a social network to link different image collections together to provide enhanced search or browsing capabilities and may not expose the tag to the user for viewing or modification.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment compares a user s image collection to those of the user s friends. The comparison may identify events that were shared by the two users and may identify images in the friend s image collection that the first user may like to add to his or her image collection.

Embodiment may be a powerful tool for linking two image collections together in a social network. In some uses the two users may know that they have attended the same event and may wish to share their images with each other. In other uses the users may not remember attending the same event or may not realize that both were there. The method of embodiment may enhance the users interaction by identifying the intersections in their lives and allowing them to share the event through their images.

In block a user s image collection may be received. The user s friends may be identified in block and each friend may be processed in block . For each friend in block event matching may be performed in block between the user and the user s friend to identify common events. The event matching may be performed in a similar manner as described in embodiment .

Each new event that was found in block may be analyzed in block . For each new event in block images may be selected from the friend s image collection in block that match the event. Any metadata from the selected images from the friend s image collection may be identified in block and applied to the user s images that are related to the event in block .

The operations of block and may propagate tags and other metadata from the friend s image collection to the user s image collection. In some embodiments a user may be given an option to approve or disapprove the tagging. The tags and other metadata may enrich the user s image collection by applying useful tags automatically or semi automatically.

The friend s images may be presented to the user in block and may be grouped by event. An example of a user interface may be illustrated in embodiment presented later in this specification.

After processing each event in block the user may browse the friend s images and select one or more of the friend s images in block . The selected images may be added to the user s image collection in block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment compares two of a user s friend s image collections to identify events that can be inferred from two of the user s friends. Images from the inferred events may be presented to the user and the user may add those images to the user s image collection.

Embodiment may be useful in a social network scenario where a user may or may not be present at an event and may wish to view images of the event and may add some of those images to the user s image collection. For example grandparents who are unable to attend a grandchild s party may wish to see images of the party. The party may be inferred by analyzing image collections from two or more people that attended the party. By inferring the event from analysis of the image collections all of the relevant images to the event may be gathered and presented to the grandparents for them to enjoy.

Embodiment operates in a similar manner as embodiment however the image collections used for the event matching may be pairs of collections from the user s friends as opposed to comparing a user s collections to those of his or her friends.

A user s friends may be identified in block and placed in a list. The friends may be identified through a social network. Each friend may be processed in block . For each friend in block each remaining friend on the list of friends may be analyzed in block . The remaining friends are those friends for which an image collection has not been processed. For each remaining friend in block an event matching process may be performed between the two friend s image collections in block to identify common events. The process of blocks and may be arranged so that each pair of friends may be processed to identify common events.

Each common event may be processed in block . For each common event in block some embodiments may include verification in block to determine if the user could have been present.

The verification of block may be used to prevent showing an event to which the user was not invited. For example two of a user s friends may get together for a night on the town and may not invite the user. To prevent the user from being insulted some embodiments may include verification such as block to prevent the user from finding out that the event occurred. In other embodiments such as with the example with the grandparents above the verification of block may not be included or may be overridden.

In some social networks a user may be able to select whether or not to share the events with other users and may be able to select which users may view their common events and which users may not.

In block images from the friend s image collection may be selected from the common event and presented to the user in block grouped by the event. After processing all the common events in block the user may browse and select images in block and may add selected images to the user s collection in block .

A user interface may display the results of an event matching process. In the user interface results from three events are illustrated. Event may have a tag Birthday Party event may have a tag Holiday at Beach and event may have a tag Skiing Vacation . The various tags may be identified from tags defined from the image collections of the friends. In some cases the tags may be determined from the user s images that match the detected events.

Each event may be presented with a source for the images. For example event may have an image source of From Mom s and Joe s Collection . Event may have an image source of From Joe s Collection and event may have an image source of From Lora s Collection . The image sources may be created using the user s labels for the user s friends.

The user interface may also include various metadata relating to the event. For example event may be presented with metadata that indicates which of the user s friends were determined to be at the event. Similarly event and may have metadata and respectively.

Each event may have a selection of images presented. Event is shown with images and . Event is shown with images and and event is shown with image . Next to each image may be a button or other mechanism by which a user may select one or more images to add to the user s image collection.

The user interface of embodiment is merely one example of some of the components that may be presented to a user as a result of image matching analysis such as event matching. The user interface may be a mechanism by which a user may browse the results of a match analysis and perform operations on the results.

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

Embodiment may illustrate a simplified method for creating clusters of images. A cluster may be a group of images that may share common features and may be useful in grouping faces as well as grouping images as a whole.

A cluster may be created by identifying a vector that represents the image and by grouping the vectors together. A cluster may have a centroid and radius and numerical comparisons may be made between an image and the cluster to determine a distance between the image and cluster to determine a match.

An image collection may be received in block and each image in the image collection may be analyzed in block . In embodiments where facial recognition is used the images may be face objects that may contain only the facial features of people cropped from larger images. In such embodiments the analysis may create a vector that represents the face object. In other embodiments the entire image may be analyzed to create an image vector.

The image may be analyzed in block to create an image vector. The image vector may contain numerical representations of various elements of the image including facial image analysis clothing analysis background image analysis and texture analysis.

In some embodiments the analysis of block may create several image vectors. For example an image having two faces may be represented with two image vectors representing the faces two image vectors representing the clothing of the two people and one or more vectors representing background images or various textures in the image.

After each image is analyzed in block the images may be grouped together in block . The grouping may be using both metadata grouping and image analysis grouping. One mechanism for grouping may be to group images together on independent or orthogonal grouping axes for each metadata category or type of image analysis. For example one grouping axis may be established for facial image analysis. On such an axis all facial image representations or vectors may be grouped. Separately each image may be grouped according to different metadata such as timestamp or location.

Within each axis clusters may be identified in block . The definition of a cluster may be controlled using a threshold that may limit clusters to tight groupings of images. The clusters may be used to represent actual matches of images with a high degree of certainty so that other operations such as image comparisons and ranking may have a high degree of certainty.

Each axis on which the images are grouped may have a different threshold for identifying a cluster. For example facial image matching may have a relatively tight threshold so that only matches with very high degree of similarity may be considered a cluster. Conversely images that are matched by background image analysis may have a less restrictive threshold so that a wider range of images may be grouped.

Each cluster may have a centroid and radius calculated in block . The centroid and radius may be used to determine matches when other images are compared to the image collection. The clusters as well as the centroid and radius may be stored in block .

Other embodiments may use different sequencing additional or fewer steps and different nomenclature or terminology to accomplish similar functions. In some embodiments various operations or set of operations may be performed in parallel with other operations either in a synchronous or asynchronous manner. The steps selected here were chosen to illustrate some principles of operations in a simplified form.

A user s image collection may be received in block and a friend s image collection may be received in block . The user s friend s image collection may be pre processed in block . An example of a pre processing method may be embodiment . The pre processing of embodiment may apply to facial image analysis and may be extended to background image analysis texture analysis color histogram analysis clothing analysis and other image analysis pre processing.

The pre processing of block may correspond to any analysis performed prior to clustering of the user s image collection.

Each image in the friend s image collection may be analyzed in block . For each image in block each cluster associated with the user s image collection may be analyzed in block .

As described in embodiment each image collection may contain multiple clusters in multiple orthogonal axes. Each cluster may represent an important aspect or element of the user s image collection and those aspects may be used to compare with the images from the friend s image collection.

For each cluster in block a distance from the analyzed image to the nearest cluster may be determined in block . If the distance is within a centroid matching threshold in block the image may be associated with the cluster in block .

If the distance is not within the centroid matching threshold in block a distance to the nearest neighbor may be determined in block . If the distance to the nearest neighbor is not within the neighbor threshold in block no match is determined.

The nearest neighbor may be an image that is within the cluster. The nearest neighbor evaluation may identify images that fall outside of the cluster but very near one of the images that has been grouped with the cluster. In a typical embodiment the neighbor threshold may be small when compared to the centroid threshold.

After analyzing all of the images in the friend s image collection in block the friend s images may be selected for presentation to the user.

The user s clusters may be ranked by size in block . The ranking may be used as a proxy for importance to the user. Each cluster may be evaluated in block . For each cluster in block the matched images may be compared to the clusters to find the closest image to a neighbor in block and to a cluster centroid in block . The best match may be determined in block and added to a user interface display in block .

The process of blocks through may identify those matches that may be the most relevant to the user as well as the most likely to be good matches. The relevance may be determined by the ranking of the clusters derived from the user s image collection. The best matches may be those images that are nearest to the centroid of a cluster or very near to another image which may be represented by the nearest neighbor.

Image matching may be prone to noise and many image matching algorithms may result in false positive results where an image is incorrectly matched. In a social networking application that has image matching user satisfaction with the matching mechanism may be higher when the user is presented with quality matches.

The process of blocks through may select the best match from the available matches to present to the user. Such a process may select a representative match for each cluster and present each match to the user enabling the user to view a wide variety of matches.

After selecting the images the images may be presented to the user organized by cluster in block . The user may browse and select images in block and may add the images to the user collection in block .

In some embodiments the user may be able to drill down into the matches for a particular cluster to view additional matches. In such a case the process of blocks through may be used to organized and select the most appropriate images from the subset of images matching the particular cluster.

The foregoing description of the subject matter has been presented for purposes of illustration and description. It is not intended to be exhaustive or to limit the subject matter to the precise form disclosed and other modifications and variations may be possible in light of the above teachings. The embodiment was chosen and described in order to best explain the principles of the invention and its practical application to thereby enable others skilled in the art to best utilize the invention in various embodiments and various modifications as are suited to the particular use contemplated. It is intended that the appended claims be construed to include other alternative embodiments except insofar as limited by the prior art.

