---

title: Computer readable medium for access right management, access right management apparatus and data processing system
abstract: A non-transitory computer readable medium for an access right management includes: reading correspondence information from a storage unit for storing correspondence information indicating the correspondence between (i) a unique access right of an access right in a data management unit for managing electronic data and the access right to the electronic data and (ii) a common access right of an access right in an interface providing unit intervening between an operation main body for giving an operation command to the electronic data and the data management unit; accepting a setting request for requesting setting of the common access right; and determining whether or not the setting request of the common access right accepted by the accepting is a non-match request.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08302207&OS=08302207&RS=08302207
owner: Fuji Xerox Co., Ltd.
number: 08302207
owner_city: Tokyo
owner_country: JP
publication_date: 20100811
---
This application is based on and claims priority under 35 USC 119 from Japanese Patent Application No. 2010 013122 filed on Jan. 25 2010.

This invention relates to a computer readable medium for access right management an access right management apparatus and a data processing system.

Hitherto a document management system for managing objects electronic data of data of a document a photo a pattern etc. created using a computer and a storage area of the data for example a folder and the access right to the electronic data has been known. In an environment in which plural of document management systems are included a document processing system is constructed using a component for providing an operation interface made common about different types of document management systems for an operation main body of an operator a system etc. for giving an object operation command. In the description to follow the document management system is abbreviated as DR Document Repository and the component is abbreviated as DRC Document Repository Connector where appropriate.

 DRC API is API Application Programming Interface defining a common operation interface independent of the type of DR and DRC SPI is SPI Service Provider Interface defining an interface for each DR as a service provider they are provided by DRC. DR API and DR API are APIs defining the functions provided in DR and DR respectively and are provided by DR and DR . DRC Adapter For DR and DRC Adapter For DR are adapters for DRs implementing the function defined in DRC API using mapping of the access right and DR API and DR API for subcomponents implementing DRC SPI. 

In such a document processing system the common access right systematized in DRC and the access right systemized uniquely in each DR do not necessarily match and thus the correspondence between the access right in DR and the access right in DRC is mapped.

In this case to perform version addition operation of an object defined in DRC in DRC Adapter For DR version addition of the object is performed in DR . To perform version addition in DR the management right in DR is required and the version addition right of DRC is mapped in the management right of DR . Likewise the deletion right of DR is also is mapped in the management right of DR . Plural of access rights of DRC mapped in one access right of DR like the relationship between the version addition right and the deletion right of DR mapped in the management right of DR are referred to as the equivalent access right in the Specification.

If common access right is set in response to a request for setting common access right associated with unique access right from the user it is feared that unique access right contrary to the user will become effective.

According to an aspect of the invention a non transitory computer readable medium storing a program causing a computer to execute a process for an access right management includes 

reading correspondence information from a storage unit for storing correspondence information indicating the correspondence between i a unique access right of an access right in a data management unit for managing electronic data and the access right to the electronic data and ii a common access right of an access right in an interface providing unit intervening between an operation main body for giving an operation command to the electronic data and the data management unit the common access right providing an operation interface made common about different types of the data management unit for the operation main body 

determining whether or not the setting request of the common access right accepted by the accepting is a non match request wherein correspondence with a different common access right exists for the unique access right corresponding to that the common access right based on the correspondence information read by the reading.

Before the description of one exemplary embodiment of the invention access right setting in DRC when the equivalent access right exists in a related art will be discussed with reference to .

It is assumed that Mr. Suzuki recognizes that the version addition right of DRC is required to perform version addition of an object in DRC and the deletion right of DRC is required to delete an object in DRC and permits Ms. Tanaka to perform version addition of object obj but does not want to permit Ms. Tanaka to delete object obj.

In this case Mr. Suzuki issues a request for giving only the version addition right of object obj to Ms. Tanaka through DRC. However in mapping for DR the version addition right of DR is mapped in the management right of DR . Thus upon reception of the set request of the version addition right of DR from Mr. Suzuki DRC Adapter For DR sets access right control information ALC Access Control List so that Ms. Tanaka has the management right for object obj for DR see .

The case where Ms. Tanaka deletes object obj through DRC in the situation is considered. As described above Ms. Tanaka has the management right for making deletion operation possible in DR and thus may delete object obj.

Thus Mr. Suzuki gives only the version addition right of object obj to Ms. Tanaka through DRC and does not give the deletion right and thus does not think that Ms. Tanaka may delete object obj. However since the version addition right and the deletion right are the equivalent access right a contradiction situation in which actually the object may be deleted occurs.

Then a data processing system according to one exemplary embodiment of the invention performs the following processing to realize suppressing occurrence of the above described situation etc.

The DR is a document management system for storing and managing electronic data and the access right to the electronic data. The data processing system in the example includes plural of DRs like DR DR . . . but DR is shown as a representative in .

The DRC is intervened between an operation main body operator system etc. for giving an operation command to electronic data managed in each DR and each DR and is a component for providing an operation interface API made common about different types of DRs for the operation main body. The DRC also provides SPI for DRC Adapter.

The DRC Adapter implements the function stipulated in API of DRC using API of each DR for a subcomponent implementing SPI of DRC and access right mapping. The data processing system in the example includes plural of DRC Adapters for each DR like DRC Adapter For DR DRC Adapter For DR . . . but DRC Adapter For DR is shown as a representative in .

The mapping storage section stores correspondence information indicating the correspondence mapping between the common access right systemized in DRC and the access right systemized uniquely in each DR unique access right . Each DRC Adapter sets and acquires the access right common access right in DRC based on the correspondence information. The data processing system in the example includes mapping storage sections for each DR like mapping for DR mapping for DR . . . but mapping for DR is shown as a representative in .

Such a configuration enables the operation main body for giving an operation command to electronic data to operate electronic data set the access right etc. using the common operation interface provided by DRC without considering the characteristic etc. of DR for managing electronic data to be operated and real data perpetuation data of the access right.

Although not shown in the data processing system in the example is also provided with function sections of a request acceptance section an access right setting processing section etc.

The request acceptance section accepts an access right set request specifying the common access right access right of DRC to electronic data entered using an input device of a mouse a keyboard etc. by a set requester. The request acceptance section in the example is realized by DRC . The access right set request contains ACL information containing the identifier of electronic data to which the access right is to be set and an access right set a pair of the identifier of the access right to be set and the identifier of the person or the system given the access right set for the electronic data as parameters. In the example the request acceptance section is realized using the function of DRC .

When the request acceptance section accepts an access right set request the access right setting processing section performs access right setting processing of setting the unique access right access right of DR corresponding to the common access right access right of DR specified in the access right set request for the corresponding DR based on the correspondence information stored in the mapping storage section for DR for managing the target electronic data. In the example processing of converting the common access right in ACL contained in the access right set request into the unique access right and storing the unique access right in DR is performed.

When the request acceptance section accepts an access right set request before the access right setting processing of the access right setting processing section the equivalent access right determination section determines whether or not the request is a non match request wherein a different access right having the relationship of the equivalent access right with the common access right specified in the access right set request exists namely correspondence with the common access right not specified in the access right set request for the unique access right corresponding to the common access right specified in the access right set request exists is determined based on the correspondence information stored in the mapping storage section for DR for managing the target electronic data.

The equivalent access right determination section is included whereby if the access right set request is a non match request it is made possible to perform processing different from usual access right setting.

In the data processing system in the example if the access right set request is not a non match request the access right setting processing section executes the access right setting processing and outputs the result to the setting requester if the access right set request is a non match request the access right setting processing of the access right setting processing section is stopped and the fact is output to the setting requester. If the access right set request is a non match request access right setting processing may be executed and a message to the effect that the request is a non match request may be output to the setting requester so that the setting requester is caused to recognize a state in which contradictory access right setting is made.

 Step S DRC request acceptance section accepts an access right setting request to electronic data. The access right set request contains ACL information containing the identifier of electronic data to which the access right is to be set and an access right set a pair of the identifier of the access right to be set common access right and the identifier of the person or the system given the access right set for the electronic data as parameters. In the example the request acceptance section is realized using the function of DRC .

 Step S Equivalent access right determination step S is repeated for all entries of the ACL information received at step S.

 Step S In the equivalent access right determination whether or not the access right in the target entry is appropriate valid is determined described later in detail . In the example two values of true if the access right in the target entry is appropriate valid and false if the access right is inappropriate invalid are returned as the determination result. In addition to the mode of returning the determination result in two values if the access right is inappropriate a set of different equivalent access right to be set together with the access right in the target entry may be returned if the access right is valid null may be returned .

 Step S Processing is switched based on the result of the equivalent access right determination step S . If the determination result is appropriate true the process goes to determination of the next entry step S and if the determination result is inappropriate false the process goes to step S.

 Step S An error is returned as a non match request in which specification lacks specification of equivalent access right specification description is contradictory . If a set of different equivalent access rights rather than false is returned the set of different equivalent access rights may be contained in the error.

 Step S If it is determined that all are appropriate as the result of executing the determination step S about all entries of the ACL information received at step S the unique access right access right of DR corresponding to the common access right access right of DRC in the ACL information is acquired from the mapping storage section and is set for the DR .

 Step S Information required for executing equivalent access right determination is acquired. As the necessary information an access right set of DRC that the setting requester desires to set and mapping of the access right of DRC and the access right of DR correspondence information read from the mapping storage section are named. In the description to follow the former is called DRC Permissions and the latter is simply called mapping.

 Step S Access right check step S is repeated for each element of DRC Permissions acquired at step S common access right called DRC Permission .

In the access right check whether or not all of equivalent access rights of DRC Permission are contained in DRC Permissions whether or not unspecified equivalent access right exists is checked. Specifically the access right unique access right called DR Permission on DR corresponding to DRC Permission is acquired from mapping the equivalent access right set is acquired based on the DR Permission and a comparison is made between the acquired equivalent access right set and DRC Permissions. Basically if all of the equivalent access right set is contained in DRC Permissions the process goes to determination of the next element DRC Permission if not all is contained the process goes to S.

For example if both access rights A and B of DRC are mapped in access right C of DR and DRC Permissions is A and check is made about A the equivalent access right set is A and B and DRC Permissions do not contain B and thus the process goes to step S.

When the process goes to determination of the next element DRC Permission It is self evident that the equivalent access right of DRC Permission determined this time is contained in DRC Permissions and thus determination about another DRC permission in DRC Permissions namely equivalent access right may be skipped.

 Step It is determined that the access right in the target entry is inappropriate specification lacks specification of equivalent access right false is returned. In the example only the determination result is returned but a set of insufficient equivalent access right may be returned.

 Step If the access right check step S about each element DRC Permission of DRC Permissions normally terminates true is returned.

Access right setting in the data processing system in the example will be discussed with reference to about the correspondence between access rights illustrated in .

 Step T Mr. Suzuki issues a request for giving only the version addition right to object obj to Ms. Tanaka through DCR .

 Step T DRC Adapter receiving the request entrusts determination of equivalent access rights to the equivalent access right determination section .

 Step T The equivalent access right determination section first determines the equivalent access right of the specified DRC access right common access right . In the example the DR access right unique access right corresponding to the version addition right is the management right and the DR management right is also mapped from the DRC deletion right and thus and the version addition right and the deletion right become equivalent access rights. When the equivalent access rights are determined then whether or not both the version addition right and the deletion right are contained in the access right set to be set is checked. In the example only the version addition right is contained and thus it is determined that the check result is inappropriate and false is returned. A set of equivalent access rights here deletion right and version addition right to be set together with the access right requested for setting rather than false may be returned.

 Step T If it is determined at step T that the check result is inappropriate DRC Adapter returns an error. Accordingly setting of the deletion light is not made implicitly. A set of equivalent access rights to be set together with the access right requested for setting may be set in the error.

 Step S Since an error is returned Mr. Suzuki may recognize that it is impossible to give only the version addition right. As the later step to be taken for example both the deletion right and the version addition right are given or if it is impossible to give only the version addition right Mr. Suzuki gives up the idea of giving the access right or the like.

The data processing system in the configuration example further includes a mapping expansion section as indicated by a dashed line in .

The mapping expansion section stores rank information defining the rank about common access rights DRC access rights having the relation of equivalent access rights. The equivalent access right determination section checks whether or not high order equivalent access right not specified in an access right setting request exists for the unique access right DR access right corresponding to the common access right DRC access right specified in the access right setting request based on the rank of the equivalent access rights according to the rank information stored in the mapping expansion section and then if high order equivalent access right not specified in the access right setting request exists the equivalent access right determination section determines that the access right setting request is a non match request otherwise the equivalent access right determination section determines that the access right setting request is not a non match request.

Thus lower rank equivalent access right than the common access right to be set need not specified explicitly in the access right setting request.

The equivalent access right determination in the configuration example will be discussed with reference to . The processing except access right check step S is the same as the processing described above and therefore will not be discussed again.

 Step S In the access right check whether or not higher rank equivalent access rights than the equivalent access right of DRC Permission are all contained in DRC Permissions high order unspecified equivalent access right exists is checked. Specifically access right on DR DR Permission corresponding to DRC Permission is acquired from mapping an equivalent access right set is acquired based on the DR Permission and a comparison is made between the acquired equivalent access right set and DRC Permissions. If higher order rights than target DR Permission in the equivalent access right set are all contained in DRC Permissions the process goes to determination of the next element DRC Permission if not all is contained the process goes to S.

That is for example if the deletion right is higher order than the version addition right when only the deletion right is specified the specification is determined to be appropriate whereas only the version addition right is specified the specification is determined to be inappropriate.

In the example the system is implemented as a computer having hardware resources of a CPU for performing various types of computation processing main memory of RAM used as a work area of the CPU ROM recording a basic control program etc. auxiliary storage for storing programs and various pieces of data according to the exemplary embodiment of the invention for example a magnetic disk of HDD etc. rewritable nonvolatile memory of flash memory etc. or the like an input output I F of an interface with a display for displaying various pieces of information and input devices of operation buttons a touch panel etc. used for input operation by an operator a communication I F of an interface for communicating with another apparatus in a wired or wireless manner and the like.

The program according to the exemplary embodiment of the invention is read from the auxiliary storage etc. is expanded in the RAM and is executed by the CPU whereby the function of an access right management apparatus according to the exemplary embodiment of the invention is realized on the computer.

In the data processing system in the example the function sections are distributed to plural of computers but may be provided in one computer.

The program according to the exemplary embodiment of the invention for example is read from an external storage medium of CD ROM etc. storing the program or is received through a communication line etc. whereby the program is set in the computer according to the example.

The function sections need not necessarily be implemented as software as in the example and each function section may be implemented as a dedicated hardware module.

The foregoing description of the exemplary embodiments of the present invention has been provided for the purposes of illustration and description. It is not intended to be exhaustive or to limit the invention to the precise forms disclosed. Obviously many modifications and variations will be apparent to practitioners skilled in the art. The exemplary embodiments are chosen and described in order to best explain the principles of the invention and its practical applications thereby enabling others skilled in the art to understand the invention for various exemplary embodiments and with the various modifications as are suited to the particular use contemplated. It is intended that the scope of the invention be defined by the following claims and their equivalents.

