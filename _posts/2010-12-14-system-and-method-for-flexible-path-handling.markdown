---

title: System and method for flexible path handling
abstract: A method for a computer system includes receiving a mapping schema between a plurality of asset-types within an asset-type hierarchy and a plurality of paths within an on-disk storage structure, receiving an asset-type definition list from a user, wherein the asset-type definition list comprises an asset-type from the plurality of asset types, and determining at least one path from the plurality of paths for providing access to assets of the asset-type in response to the mapping schema and the asset-type definition list.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09286297&OS=09286297&RS=09286297
owner: Pixar
number: 09286297
owner_city: Emeryville
owner_country: US
publication_date: 20101214
---
This application is a continuation application of and claims priority from U.S. Nonprovisional patent application Ser. No. 11 115 987 filed Apr. 26 2005 which claims priority from and is a non provisional of U.S. Provisional Patent Application No. 60 571 229 filed May 13 2004 and the entire disclosures of these applications are incorporated herein by reference for all purposes. The present application also incorporates by reference for all purposes U.S. patent application Ser. No. 10 810 487 filed Mar. 26 2004 now U.S. Pat. No. 7 548 243 .

The present invention relates to asset management systems. More particularly the present invention relates to methods and apparatus for mapping between an asset name and type and an on disk file location. Some embodiments provide a centralized configuration standard code libraries and a callable executable to allow assets to be located on disk based on name type and search parameters rather than hard coded asset path fragments.

Throughout the years movie makers have often tried to tell stories involving make believe creatures far away places and fantastic things. To do so they have often relied on animation techniques to bring the make believe to life. Two of the major paths in animation have traditionally included drawing based animation techniques and stop motion animation techniques.

Drawing based animation techniques were refined in the twentieth century by movie makers such as Walt Disney and used in movies such as Snow White and the Seven Dwarfs 1937 and Fantasia 1940 . This animation technique typically required artists to hand draw or paint animated images onto a transparent media or cels. After painting each cel would then be captured or recorded onto film as one or more frames in a movie.

Stop motion based animation techniques typically required the construction of miniature sets props and characters. The filmmakers would construct the sets add props and position the miniature characters in a pose. After the animator was happy with the arrangements one or more frames of film would be taken of that specific arrangement. Stop motion animation techniques were developed by movie makers such as Willis O Brien for movies such as King Kong 1933 . Subsequently these techniques were refined by animators such as Ray Harryhausen for movies including Mighty Joe Young 1948 and Clash Of The Titans 1981 .

With the wide spread availability of computers in the later part of the twentieth century animators began to rely upon computers to assist in the animation process. This included using computers to facilitate drawing based animation for example by painting images by generating in between images tweening and the like. This also included using computers to augment stop motion animation techniques. For example physical models could be represented by virtual models in computer memory and manipulated.

One of the pioneering companies in the computer aided animation CA industry was Pixar. Pixar is more widely known as Pixar Animation Studios the creators of animated features such as Toy Story 1995 and Toy Story 2 1999 A Bugs Life 1998 Monsters Inc. 2001 Finding Nemo 2003 The Incredibles 2004 and others. In addition to creating animated features Pixar developed computing platforms specially designed for CA and CA software now known as RenderMan . RenderMan was particularly well received in the animation industry and recognized with two Academy Awards . RenderMan renders images based upon conceptual software assets including geometric scene descriptors including references to object models.

Typically scenes to be rendered are specified assembled by one or more users e.g. animators lighters etc. . These scenes include descriptions of the objects camera angles lighting sources and the like. The scene data file also known as a scene descriptor file that describes the entire scene is typically very large on the order of gigabytes. Because the sizes of typical scene descriptor files are typically large Pixar developed an internal technique for segmenting a scene descriptor file from one large file into a series of smaller files. As described in the co pending application described above Pixar developed and used the concept of hook set files and references to hook files to describe a scene. Hook files may include geometric object data shader dada lighting data and the like. Accordingly a typical scene is actually composed of a number of separate data files. Generally logical assets such as a scene a shot a group of scenes an object and the like are now themselves composed of any number of separate assets.

The inventors of the present invention have recognized that when rendering a lengthy animated feature such as a feature film hundreds to thousands of assets e.g. scene descriptor files hook files object and the like need to be retrieved from memory efficiently.

One method considered by the inventors to provide access to assets has been the storage and retrieval of assets from hard coded directory structures. As an example a rigid directory structure is first created to store assets and when a particular asset is required the appropriate directory in the directory structure is accessed for that asset. In such examples hard coded asset paths may use variable substitution such as foo bar name where name is the asset name stored in directory foo bar. 

The inventors had determined that drawbacks to these methods includes that the scene descriptor file or the like must be manually updated when the asset directory structure changes. For example when a reference to foo bar should be changed to foo bar1 due to a version update files with references to foo bar must be manually updated to refer to foo bar1. 

Another method considered by the inventors to provide access to assets has been with operating system environmental variables path search lists such as UNIX PATH format. The inventors have determined a number of drawbacks to such methods including that new variables would have to be established for each new type mapping. Other drawbacks includes that search methods would typically be performed linearly through the list until a name match is made which would be inefficient. Other drawbacks include that without a type hierarchy there would be no way to specify more than one level of type refinement in a search without creating a compound type. Still other drawbacks include that environment variables are often managed by the operating system and outside direct control of the users. Further the operating system would have to be rebooted when the user changes working environments.

Accordingly what is desired are improved method and apparatus for asset management without the drawbacks described above.

The present invention relates to asset management systems. More particularly the present invention relates to methods and apparatus for mapping between an asset name and type and an on disk file location. Embodiments of the present invention provide a centralized configuration standard code libraries and a callable executable to allow assets to be located on disk based on name type and search parameters rather than hard coded asset path fragments.

An overarching design goal of a flexible path handling system described in embodiments of the present invention is to store and retrieve assets based upon a hierarchal data structure that makes sense to a user workflow and not necessarily a hard disk structure. Accordingly a configurable mapping between assets e.g. element character shot etc. types or asset model shader etc. types and the directory paths that they reside in is desired.

In some embodiments of the present invention one such configurable mapping is for toolpaths. With the toolpaths mechanism a configuration file can be used to set the global UNITTREE. For example user anim running could be changed to shows running Additional the toolpath mechanism may be used to set the production and shot element directories below the UNITTREE and set the model shader etc. asset paths relative to production and shots as well as in global directories . In various embodiments toolpaths exist for a variety of asset types .mdl models .sl shaders etc. and modeling environments and other tools and scripts search for files of the appropriate type in the paths returned by the toolpaths script.

In various embodiments toolpaths may return one or more complete path strings. In such embodiments to get subpath data either the toolpath must define the subpath or the subpath would require prior knowledge as to the directory structure. Additionally in some embodiments toolpaths are run as a program to reduce overhead.

In light of the above in various embodiments of the present invention a configuration file is provided to define both new structure for existing assets as well as new path variables to support new types of assets and workflow. Additional stand alone executable programs may include APIs that return paths based upon asset data and may provide hierarchal lists based upon paths.

a A centralized configuration file encoded in the XML standard which allows hierarchal mappings between on disk structure and type to be established for one or more asset trees of potentially different structure.

b Ability to handle compound and aggregate assets and still reference sub assets using hierarchal definitions. Complex assets can therefore use singly rooted on disk storage instead of spreading sub assets out over parallel paths so that a one level type system can handle them.

c Precedence of conceptual asset type over on disk path allows for data oriented workflow tools to be created without codifying an on disk structure in the tools.

d Configurable search defaults per type per asset tree allows some asset collections to be searched top down some bottom up or at a single level.

e Ability to query assets by passing in names or wildcards for levels of the type hierarchy above that asset. This can be done without modifying environment variables. For example in a film production system it is possible to ask for all shaders named foo which belong to characters of any name in movie A or B . This can be done without explicit path construction in the code or restarting the program after changing environment variables.

f Ability to request asset paths using code libraries in C C Python Perl TCL and csh or as a callable executable from other languages on the command line or from other programs that can accept a path from a remotely called executable.

d Choice of globally configurable defaults or a custom written walk in code library calls to acquire asset location by type.

e Ability to call deep assets by specifying names to fill in type variables throughout the hierarchy without using explicit string parsing on paths in the code or environment variables.

A simplified system and method for flexible path handling may include the following processes according to embodiments of the present invention. These processes are merely examples which should not unduly limit the scope of the claims. One of ordinary skill in the art would recognize many variations alternatives and modifications.

According to one aspect of the invention a method for a computer system is disclosed. One technique includes receiving a mapping schema between a plurality of asset types within an asset type hierarchy and a plurality of paths within an on disk storage structure and receiving an asset type definition list from a user wherein the asset type definition list comprises an asset type from the plurality of asset types. Techniques may also include determining at least one path from the plurality of paths for providing access to assets of the asset type in response to the mapping schema and the asset type definition list.

According to another aspect of the invention a computer program product for a computer system including a processor is described. A computer program product may include code that directs the processor to receive a mapping schema between a plurality of asset types organized in an asset type hierarchy and a plurality of paths within an storage and code that directs the processor to receive an asset type definition list wherein the asset type definition list comprises an asset type from the plurality of asset types. The codes may also include code that directs the processor to determine at least one path from the plurality of paths for providing access to assets of the asset type in response to the mapping schema and the asset type definition list. The codes typically reside on a tangible media such as an magnetic media optical media semiconductor media or the like.

According to yet another aspect of the invention a computer system is disclosed. One apparatus includes a memory configured to store a plurality of assets within a plurality of paths and configured to store a mapping between a plurality of asset types organized in a hierarchy and the plurality of paths. An apparatus also includes a processor coupled to the memory wherein the processor is configured to receive an asset type definition list wherein the asset type definition list comprises an asset type from the plurality of asset types and wherein the processor is configured to determine at least one path from the plurality of paths to provide access to assets of the asset type in response to the mapping and the asset type definition list.

In the present embodiment computer system typically includes a monitor computer a keyboard a user input device a network interface and the like.

In the present embodiment user input device is typically embodied as a computer mouse a trackball a track pad wireless remote and the like. User input device typically allows a user to select objects icons text control points and the like that appear on the monitor . In some embodiments monitor and user input device may be integrated such as with a touch screen display or pen based display such as a Cintiq marketed by Wacom.

Embodiments of network interface typically include an Ethernet card a modem telephone satellite cable ISDN asynchronous digital subscriber line DSL unit and the like. Network interface are typically coupled to a computer network as shown. In other embodiments network interface may be physically integrated on the motherboard of computer may be a software program such as soft DSL or the like.

Computer typically includes familiar computer components such as a processor and memory storage devices such as a random access memory RAM disk drives and system bus interconnecting the above components.

In one embodiment computer is a PC compatible computer having multiple microprocessors such as Xeon microprocessor from Intel Corporation. Further in the present embodiment computer typically includes a UNIX based operating system.

RAM and disk drive are examples of tangible media for storage of animation asset data audio video files computer programs operating system embodiments of the present invention including an asset management tools custom code logical and aggregate animation assets object data files a dependency analyzer dependency graphs an operating system and the like. Other types of tangible media include floppy disks removable hard disks optical storage media such as CD ROMS and bar codes semiconductor memories such as flash memories read only memories ROMS battery backed volatile memories networked storage devices and the like.

In the present embodiment computer system may also include software that enables communications over a network such as the HTTP TCP IP RTP RTSP protocols and the like. In alternative embodiments of the present invention other communications software and transfer protocols may also be used for example IPX UDP or the like.

In embodiments of the present invention computer system retrieves a scene from storage system based upon a geometric description of a scene for a variety of different purposes e.g. scene design rendering .

Storage system may include any organized and repeatable way to access the geometric description of a scene including animation assets such as object models lighting models camera models and the like. For example in one embodiment storage system includes a simple flat directory structure on a local drive or a network drive or the like. Additionally locations of object models may be specified by absolute file path locations relative file paths specific directories aliases UNIX symlinks and the like.

In operation to access a scene descriptor and or data files referenced by the scene descriptor file mapping program is used to refer to configuration file to locate one or more paths in storage system . Once the specified paths are identified data files in that path or in sub directories of the path can be retrieved.

In one embodiment of the present invention a geometric scene descriptor is typically a text file that specifies the animation assets within the scene. Animation assets include lighting objects camera objects geometric objects and the like. These objects are used to specify the scene. In the present embodiments the scene descriptor file also specifies the position of objects in the scene the orientation of objects the colors and textures for the objects properties for objects and the like. In the present invention the scene descriptor file is a textual file referred to as a hook set or hook file. A scene descriptor file may be associated with only the frame may be associated with a shot of images may be associated with a portion of a feature may be associated with the entire feature or the like. In other embodiments other types of representation of a scene descriptor can be used with embodiments of the present invention.

An example of the content of a simple hook file may include the following text references to a camera object a light object and a three dimensional object 

In one embodiment for a camera object properties may include type of projection e.g. perspective field of view width position azimuth pitch pan and roll aspect ratio focusing option cropping shifting tv aspect ratio pan and scan option number of tracks number of cranes and the like. An example of a portion of a camera hook is as follows 

As seen in this example reference to a file including a specification of a camera model is illustrated as a .m file. The .m file is accessed and used when rendering the scene using the camera object. In embodiments of the present invention other file types for objects are contemplated such as model files compatible with other three dimensional creation and manipulation programs such Maya SoftImage or the like.

In another embodiment for a light object properties may include light quality light type light shape light color and the like. Not all camera objects or light objects need to support the same properties. For example an atmospheric fog light may have a unique fog properties. An example of a portion of a lighting object hook is as follows 

As seen in this example reference to a file including a specification of a light model is also illustrated as a .m file. The .m file is accessed and used when rendering the light object in the scene.

In embodiments of the present invention geometric objects may include three dimensional descriptions of objects such as an animated character e.g. Bob Marlin Woody a prop e.g. a table a chair and the like. Additionally geometric objects may include virtually any imaginable properties supported. For example one geometric parameter may be number of wheels for an automobile object number of eyeballs for a monster object or other animation variable and the like. Additionally a geometric object may include references to files including physical models. An example of a portion of a geometric object hook is as follows 

In this example a first geometric description file is specified object1 full.mdl and a second geometric description file is also specified object1 standin.mdl. These respective .mdl files are accessed and used when rendering the geometric object in the scene. In the present embodiment each model descriptor file is an industry standard .mdl file that specifies how object1 is to be rendered in the scene. In other embodiments the model descriptor files may include procedurally generated geometric components procedurally generated textures and the like for object1. In still other embodiments combinations of both pre defined and procedurally generated aspects of object1 may be used.

Further the .mdl files or the like typically store pre defined geometric components shaders textures colors or the like. In embodiments of the present invention assets may themselves be aggregate assets for example the geometric components may include references to other geometric components a referenced shader may be an aggregate of other shaders and the like.

The techniques illustrated above use representations of objects that are referenced at hard coded or relative computer locations such as at specific computer disk directories at specific network directories with specific file names or aliases or the like. In embodiments of the present invention the examples above access files via the use of callable executables centralized configuration files and the like described below.

In the present embodiment server includes a centralized configuration file and may include asset management software or the like. In various embodiment server may also include database management software that provides organized access to data store .

In operation to access a scene descriptor and or data files referenced by the scene descriptor file mapping program is used to refer to configuration file to locate one or more specified locations in storage system . Once the specified path s are identified data files at the path or in sub directories of the path may be retrieved.

In operation computer system may retrieve a scene descriptor file from server . In such embodiment the asset management software provides input to mapping program which in turn refers to centralized configuration file to identify one or more specified paths in data store . Once the specified paths are identified data files at the specified paths or in sub directories may be retrieved or accessed by the asset management software.

Initially a centralized configuration file is created step . In some embodiments of the present invention the configuration file specifies a hierarchical mapping between on disk structure and type and one or more asset trees having similar or different hierarchy. In the present embodiment XML is used to specify configuration file. In other embodiments any other representation of a map from on disk structures to nodes may be used including ASCII text file or the like.

In embodiments of the present invention search order among parallel nodes may also be specified in the configuration file. For example for show sequence and shot elements locations for similar asset types can be specified to search from top down or bottom up order. As another example the configuration file may be restricted to search only at a particular hierarchal level. In other examples rules may be established that all subdirectories beneath a given root are of a named type of asset if they contain files otherwise they are a collection of that named type of asst if not. Still further default search parameters may also be set in the configuration file for example by using one of the three search orders top down bottom up or look 1 level only.

As illustrated in in some embodiments of the present invention a computer server is provided with the centralized configuration file as well as a file access program mentioned above step . In various embodiments the file access program includes a number of application programming interfaces APIs that allow a user to specify parameters such as asset names asset types asset version context information or the like. In other embodiments the file access program may be part of a third party program such as asset management software.

Next once the configuration file and APIs have been provided a user searching for a particular asset path calls the APIs with specified search parameters step . In various embodiments the search parameters for the APIs include type definition lists e.g. type name1 instance 1 type name2 instance 2 . The type definition lists typically specify asset types defined in the asset tree and instance names for the asset types.

In embodiments of the present invention contexts are also typically provided. Contexts also typically include one or more asset types and instance names e.g. setContext show Toy Story character Woody shot Pizza Planet Entrance . In various embodiments Contexts are provided to reduce the amount of data the user has to provide to the APIs. Contexts also allow the user to request path data without having to worry about where data is being retrieved from. Additionally Contexts are provided so that different users can operate with the same APIs to access data that may have the same name but are in different features without rebooting the system.

In various embodiments the user may also specify a search order that overrides a default search order step . For example an API parameter may include a search type parameter such as search search type 1 search search type 2 or the like.

In embodiments of the present invention in response to the user provided parameters the computer attempts to determine one or more paths that match the defined parameters mapping configuration step .

In various embodiments if the defined parameters are specific enough and what is automatically returned is a directory path string with variables specified search parameters inserted into the directory path string step . As an example in an animated feature Huey a character named Louie is defined and a character shader named Dewy is also defined. In such an example the filled in API parameters may include shader Dewy character Louie movie Huey . According to the embodiment discussed above in return the API returns the appropriate directory path such as Huey characters Louie shaders Dewy movies Huey models characters main Louie components shaders Dewy or the like depending upon the specific storage structure defined. In the present embodiments a number of shaders may reside in sub directories of the given path. For example subdirectories may exist for the returned path such as Huey characters Louie shaders Dewy Dirt Huey characters Louie shaders Dewy texturemap Huey characters Louie shaders Dewy scratches and the like.

In various embodiments the APIs return the first matched path. In other embodiments the APIs may return any matched paths. In such embodiments various filters may also be used to narrow down the desired path.

In embodiments where the request is not specific enough to identify a path an error condition may be returned step . For example using the example above the filled in API parameters may include shader Dewy character movie Huey . Using this example an error occurs because more than one result at the same level in the hierarchy may be returned. To reduce the number of error conditions the path may be the first found path or all paths if multiple paths are found. Additional filtering may also be used.

In some embodiments of the present invention the user provides a disk path for one or more assets and in return the computer server returns the appropriate hierarchal list for the asset. For example the user calls the APIs with a specified path. In response a typed definition list e.g. type name1 instance 1 type name2 instance 2 is returned. Similar to above in some cases more than one answer may be provided by the computer server. Accordingly filters may be provided error conditions may be flagged and the like.

In some embodiments of the present invention the APIs are called from within third party programs such as an asset management system discussed above. The responses from the APIs may then serve as input to the asset management system. For example the responses can be incorporated into configuration files for such third party programs.

In one embodiment of the present invention an example of two specific APIs are illustrated below. The psuedo code shown is merely an example which should not unduly limit the scope of the claims. One of ordinary skill in the art would recognize many variations alternatives and modifications.

returns shows Bugs2 sequences h23 shots h2315 assuming current context specifies show Bugs2 and useLocal never .

findPaths returns ordered list of path s where the requested asset s are found similar to toolpaths search paths .

In various embodiments if the requested asset type exists in more than one location in the tree and the associated asset tags have an order attribute they may be returned in the specified order.

An example of a configuration file is illustrated below. This configuration file is merely an example which should not unduly limit the scope of the claims. One of ordinary skill in the art would recognize many variations alternatives and modifications. The configuration file defines hierarchical relationships between assets from which the path of an asset can be determined by looking in the tree at the node for that particular asset type and then traversing the tree upward. Each parent node represents an asset container. In some embodiments if each containing asset is specified in the context its name is used as a directory name in the path. Otherwise if the asset container node has a name attribute that is used as the directory name. If the asset container node has no name attribute and that asset is not specified in the context an error may occur since the path to the requested asset cannot be determined . If an asset has a source file associated with it the source file should be a separate asset type and should have its own location within the configuration file.

localbasepath ditto for the local working tree. This functions as the default working path overridden by the SHOWWORKPATH environmental variable.

metatype the metatype tells what kind of thing the asset is and can be used in logic for example characters sets and props are all model based so logic that operates on models can find out that these are model based and know that it can ask for model files.

dbequivalent for backwards compatibility for mappings such as unit is show and in some contexts prod is sequence. 

associatedtask a way of associating a workflow role with an asset and its path for helping to configure the AB workflow engine and also as a shortcut for getting task specific paths .

name Specifies the directory name that should be used for this asset. If unspecified the name of an asset will be acquired from the context. This can be overridden by the context as well.

order Specifies the order in which assets of the given type should be returned for calls to findPaths . Assets that should be returned first should have 1 for the value of its order attribute.

Many changes or modifications are readily envisioned. In light of the above disclosure one of ordinary skill in the art would recognize that many variations may be implemented based upon the discussed embodiments. Further the embodiments discussed above may also be combined.

Further embodiments can be envisioned to one of ordinary skill in the art after reading this disclosure. In other embodiments combinations or sub combinations of the above disclosed invention can be advantageously made. The block diagrams of the architecture and flow charts are grouped for ease of understanding. However it should be understood that combinations of blocks additions of new blocks re arrangement of blocks and the like are contemplated in alternative embodiments of the present invention.

The specification and drawings are accordingly to be regarded in an illustrative rather than a restrictive sense. It will however be evident that various modifications and changes may be made thereunto without departing from the broader spirit and scope of the invention as set forth in the claims.

