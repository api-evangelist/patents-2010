---

title: Information service for facts extracted from differing sources on a wide area network
abstract: In one general aspect, a wide area network fact information service method is disclosed. This method includes storing a plurality of canonical fact entries, storing one or more fact descriptor entries for each of the canonical fact entries, and ranking the canonical fact entries relative to each other based on the descriptor entries.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08468153&OS=08468153&RS=08468153
owner: Recorded Future, Inc.
number: 08468153
owner_city: Cambridge
owner_country: US
publication_date: 20100121
---
This patent application claims the benefit of provisional application 61 205 567 filed on Jan. 21 2009 which is herein incorporated by reference. This patent application also relates to the subject matter of U.S. provisional application No. 60 940 643 filed on May 29 2007 U.S. provisional application No. 61 068 967 filed on Mar. 11 2008 and U.S. patent application Ser. No. 12 156 455 filed on May 29 2008 which are all herein incorporated by reference.

This application relates to information services such as information services for facts extracted from content meaning across differing sources on a wide area network. Content meaning can be derived through linguistic analysis metadata or other approaches.

Many approaches for extracting and using information from large networking environments such as the Internet have been proposed and implemented. Search engines and manually generated indexes are among the most common tools used for this purpose today but there are literally hundreds of other specialized and or complex data mining techniques that have been developed. And a large amount of effort is constantly being expended to improve and reengineer existing approaches as well as to develop new ones.

In one general aspect the invention features a wide area network fact information service method that includes storing a plurality of canonical fact entries storing one or more fact descriptor entries for each of the canonical fact entries and ranking the canonical fact entries relative to each other based on the descriptor entries.

In preferred embodiments the step of ranking can be a continuous process that recalculates the rank of canonical fact entries based on new descriptor entries. The step of ranking cam be an iterative process that recalculates the rank of canonical fact entries based on new descriptor entries. The step of ranking can be a parallel process that recalculates the rank of canonical fact entries based on new descriptor entries. The ranking can be based on a predetermined ranking for entities associated with the canonical fact entries. The entity ranking can be based on a number of descriptor entries. The entity ranking can be based on a number of descriptor entries within a category. The entity ranking can be based on a sentiment attitude value. The entity ranking can be based on co occurrence with other facts and their rankings. The ranking can be based on a ranking of source credibility for data source providers associated with the descriptor entries. A same source provider can have different credibility values for different sources that it provides. A same source provider can have different credibility values for different categories of sources that it provides. The credibility ranking can be based on at least one user interest measure. The ranking can be based on a proximity measure for the descriptor entries. The proximity measure can be a temporal proximity measure. Proximity measures can be combined using a fading factor. The ranking can be based on a plurality of similarity measures that express a similarity between the canonical fact entries and or fact descriptor entries. The similarity measures can relate to fact type and temporal overlap. The similarity measures can operate according to a hierarchy. The ranking can be based on publication times.

In another general aspect the invention features a wide area network fact information service system that includes canonical fact entry storage fact descriptor entry storage for storing one or more fact descriptor entries for each of the canonical fact entries and a ranker for ranking the canonical fact entries relative to each other based on the descriptor entries.

In a further general aspect the invention features a wide area network fact information service system that includes means for storing a plurality of canonical fact entries means for storing one or more fact descriptor entries for each of the canonical fact entries and means for ranking the canonical fact entries relative to each other based on the descriptor entries.

Systems according to the invention can be beneficial in that they can allow users to approach temporal information about facts in new and powerful ways enabling them to search analyze and trigger external events based on complicated relationships in their past present and future temporal characteristics.

Referring to an illustrative embodiment of a system according to the invention can include one or more sources of information about facts. In the case of the Internet the information about facts can be retrieved from a wide variety of sources such as news feeds newspapers and magazines blogs websites corporate calendars political calendars weather sensor data and stock market data streams. These are of course only examples of the types of data sources that can be used and the concepts and principles presented in connection with the invention can be applied to other types of data sources such as private networks government data services or enterprise industrial automation tools.

The system can also include research monitoring analysis and execution machinery which is responsive to the information sources . This part of the system can cooperate with a fact data warehouse as well as several external interfaces. A data cache can also be provided to speed up data retrieval in certain circumstances.

The external interfaces include a user interface which is temporal logic based for searching historical present and future facts and a user interface for defining complex sequences of facts . The external interfaces also include a Web services interface which is temporal logic based for searching historical present and future facts and a Web services based programming interface for defining complex sequences of facts . The system can also generate a subscribable fact stream for generated facts in the real world e.g. buying a stock creating a news story triggering a supply chain update .

Facts are pieces of information about occurrences that can take place anywhere and can then be described reported or otherwise manifested or revealed in some form on a computer network. A sports feed can report facts for a game for example such as by updating a score tally. A sports blog can also focus on different facts from the same game and or can describe the same facts from the same game in different ways.

The facts themselves can also be network based. In the case of an electronic corporate securities filing for example the occurrence on the network of the filing itself can be a fact. And it can also act as a source of descriptive material for facts that it describes such as a company s product release dates.

The existence of facts and information about them are typically acquired by applying software such as entity and event extractors to text documents sources. One approach to extraction is to linguistically analyze plain text such as through the use of services from Reuters ClearForest InXight and or Attensity. Extraction can also involve simple harvesting where the content already contains meta data such as Resource Description Framework RDF tags.

 Fort Orange financial completes 3.3M stock offering. the system can use linguistic analysis to map the document date to the investment fact. Note that in some circumstances techniques amounting to less than perfect linguistic analysis such as entity verb clustering can be used without excessive loss of performance.

Future facts can be scheduled facts such as the expected Yahoo lawsuits or events extracted from an Internet calendar. They can also be predicted based on a variety of prediction methods. These can range from complex statistical forecasting methods to simple inferences such as where a company s next annual meeting is predicted to be on the same day as all of its past annual meetings.

Referring to a system according to the invention can be organized according to a layered model. At the lowest level is a fact loading layer that includes data message stream and adapters. These receive data and or message streams such as news flow fact streams stock tick data fact streams and or RFID sensor fact streams .

Above the fact loading layer is a fact transformation layer which can operate based on linguistics semantics and or mathematics statistics. Above the fact transformation layer is relations storage a fact data warehouse and fact in memory segment cache and an inverted future timelines module . At the next level is a fact modeling and computation engine which can work with prediction correlation and probabilities. Layered above the fact modeling and computation engine is a temporal based fact query language . A text search modeling user interface a graphical user interface framework and an application programming interface software development kit are all layered over the temporal based fact query language. Domain specific applications are in turn layered above these modules.

Referring to the system can be based on fact ontology that categorizes facts into categories and subcategories such as financial information and types of financial transactions and a source ontology that categorizes sources. The system also maintains fact counts page context rank and user click counts to be used in qualifying fact information. These are used to categorize and rank facts and information about facts. A newspaper article from a reputable newspaper for example will be ranked higher than an unknown blog entry for the same facts and or entities. The categorization of facts and information about facts is similarly used to determine the relevance of a database entry to a service request such as a search query. The overall ranking in relation to the service request will determine which database entries are selected and in what order they are presented to the user.

The system can present its results to the user in a variety of formats. It can present them in a simple hit list based result output similar to that of a traditional search engine or it can use a temporally oriented format such as a timeline. It can also use any other suitable user oriented or machine oriented format such as more elaborate graphical user interfaces RSS feeds e mail alerts XML documents or proprietary binary formats. Advertising can be associated with results and this advertising can be targeted based on the specific facts and or entities involved.

The system can provide a variety of types of services. A fact based searching system can be provided for use by the general public or a specific segment. Fully customized minimally filtered or even raw fact feed subscriptions can also be provided. And more quantitative searching solutions could be provided as well such as for financial services applications.

One type of service is a news service. The service receives a user profile which allows a user to specify interests. Information about facts relevant to these interests can then be provided to the user in a variety of formats such as feeds or an electronic newspaper format.

Mapping facts to temporal information in the database allows the system to answer questions that may be difficult to answer with traditional search engines. Here are some examples 

Systems according to the invention can also answer more complex questions about the relationship between facts such as what happened to similar entities in similar chains of events 

Referring to in one embodiment of a system information sources are accessed through spiders and RSS subscriptions. An entity extraction module and a fact extraction module extract entity and fact information based on an entity database and fact ontology storage . The resulting information is time normalized and stored in a large scale fact database . This database can be partitioned based on the fact ontology. Fact ranking and fact prediction processes can be used to augment the database with ranking and predictive information. Entities can include a wide variety of subjects such as people places or timepoints.

A software development kit allows developers to iterate facts perform transformations and predictions and implement user interface elements. The system can also provide a search query engine as well as user experience templates and rendering to produce different types of interfaces such as search timeline and newspaper interfaces. RSS feeds can also be generated from the database.

The system described above has been implemented in connection with stored special purpose software program instructions running on a general purpose computer platform but it could also be implemented in whole or in part using special purpose hardware. And while the system can be broken into the series of modules and steps shown in the various figures for illustration purposes one of ordinary skill in the art would recognize that it is also possible to combine them and or split them differently to achieve a different breakdown.

Fact ranking is of vital importance to give a good user experience both for monitoring alert and search applications. A ranking approach based on six concepts is proposed and several ways of computing the event ranking are suggested.

Referring to the system can use an information model where facts are discovered in documents. Documents are delivered to the system through media streams e.g. RSS feeds blogs or other means from various sources. From each document a number of entities and facts are extracted and stored in a database. illustrates this at a high level.

Facts e.g. events detected in documents are of course descriptions of real world facts even though they are therefore fact descriptors they are still referred to as facts . These event descriptors can be thought of as being related with a corresponding canonical fact as shown in .

In the model a canonical fact has just a fact type and a set of entities whereas a fact or fact descriptor has additional information such as publication date source etc.

The entities take different roles e.g. for an acquisition event the two roles are Company Acquirer and Company BeingAcquired these are Calais event types . All fact descriptors of the same type and with the same entities in the corresponding roles are linked to the canonical fact.

Different existing entity extractors can be used such as Calais or Basis. These can exhibit some shortcomings however in that they can have several entity IDs for what should be the same entity for example Microsoft Microsoft Corp Microsoft Corp. and IBM International Business Machines . Even if and when disambiguation is improved the system will keep its own identities to guard from future changes in the entity extractor. In the system s ontology pointers are kept to the different entity extractor identities hash values . In addition pointers are kept to other information about the tsup entity. The tsup entities and the mapping to entities are implemented with two tables tsup entity and tsup extractor entity map.

The data set is built incrementally as new entities are detected in the output from the entity extractor. Initially the data set can be populated from the Entity table in the database and adding to the tsup extractor entity map table using the equivs file home truve equivs with the following format alias master 

For a fact E with source S and included entities e. . . e and with the source credibility function c and entity ranking function r the following holds IER . . . The functions c f and g all have the value range 0 . . . 1. There are many ways to choose the functions f and g one choice is to multiply the source credibility with the aggregated entity rankings i.e. f x y x y. The entity weight aggregation function g can be chosen e.g. as the maximum ranking of any included entity or the mean ranking. Other aggregation functions are of course also possible. Derived Event Ranking

The simplest DER function used DER just boosts events if they are similar to other events with higher ranking or more precisely higher ranking times similarity DER e FOR ALL EVENTS i 1 . . . max SUM DER e SM e e m WHERE m number of events 1 . . . max for which SM e e 0 and DER e 

Assuming there are two documents document 1 with fact A and B and document 2 with facts C and D. The facts have the following IER IER 4.0 IER 2.0 IER 4.0 IER 1.0 Furthermore assume that there is one SM 0 apart from entities being fully similar to themselves SM 0.8 This is a high degree of similarity for example the same event type and same entities but different times. This example is shown graphically in . The DERfunction converges after 29 iterations with the following values DER 4.0 DER 3.2 DER 4.0 DER 1.0 So event B has been given a higher ranking than its IER and all other rankings remain unchanged.

Here is a slightly more complicated example shown graphically in IER 4.0 IER 2.0 IER 4.0 IER 10.0 SM 0.8 SM 0.5 In this case the iterative method converges after 34 iterations with the following result DER 4.0 DER 4.0 DER 5.0 DER 10.0 So both B and C have now been boosted although C has not been boosted so much since the similarity to the highly ranked D is not so big. Proof Sketch that DERAlways Converges

The DERmethod uses the fact similarity measure SM to allow similar facts to influence each other s ranking. Taking this one step further a system can start counting the number of occurrences of each canonical fact . As an example there will be many facts relating to the possible Microsoft acquisition of Yahoo with different times sources and other differences but all relating to the canonical fact 

A system can thus count the number of events relating to this canonical fact and use the canonical fact count as a complementary way of ranking events.

The ranking of a document in which a fact occurs is also a useful measure. Using the Google PageRank of the document is the most straightforward way to do this.

In summary referring to a method has been presented for calculating an initial event ranking IER and several for calculating derived event rankings DER.

The IER is calculated when a fact is added to the database using semi static information from the database about entity ranking source credibility and potentially additional information document page ranking would be one example . The IER for a fact can be recomputed at any time using updated input data.

The DER methods iteratively update the DER value or values of each fact using the IER and DER values of all other facts to which it relates.

Ahmad Shah Massoud was the head of the Northern Alliance in Afghanistan. He was killed on Sep. 9 2001. A search in the event database on September 9th would have classified this to be a relatively unimportant event and this would have been in accord with general sentiment about its importance. 48 hours later however it was deemed to be an extremely important event.

This change in importance resulted from reports of Massoud s killing being published on or just around Sep. 11 2001 in high ranked sources along with co occurrence in documents with another very key event the 9 11 terrorist attacks that for various reasons have been ranked high . Accordingly 48 hours later the event s generally agreed upon importance and likewise its ranking in our system would be high.

While the temporal co occurrence of the two events would no doubt be sufficient by itself to greatly increase the ranking of the Massoud story the following factors could also have an effect 

1 Its importance within its category e.g. Afghan politics or Middle East politics was high and that category became more important after 9 11.

3 There may have been a relatively close proximity measure between the 9 11 attacks and Massoud s name in the co occurring documents.

4 The assassination and the 9 11 attacks are similar types of events terrorist attacks involving explosives .

5 The two events were both involved the same lower level hierarchical entity Afghanistan rather than higher level entities such as Middle East. 

It is important to distinguish between publication times for a fact and the occurrence time of the fact. Articles that predict an impending bankruptcy for example may describe its expected date with more and more precision as time progresses. Later published articles can therefore be weighted more heavily in predicting the date of a fact. Trends about the expected time of occurrence of a fact can even be extracted from the evolution of its prediction in articles over time. And these trends can point to a more accurate prediction of the date of occurrence of the fact.

Referring to the output of the system can be presented to the user in a variety of formats such as a social network graph. In this example documents are first accessed . Entities relating to these documents are then extracted . The relationship between canonical entries and fact descriptors can then be mapped out for the user .

The present invention has now been described in connection with a number of specific embodiments thereof. However numerous modifications which are contemplated as falling within the scope of the present invention should now be apparent to those skilled in the art. It is therefore intended that the scope of the present invention be limited only by the scope of the claims appended hereto. In addition the order of presentation of the claims should not be construed to limit the scope of any particular term in the claims.

