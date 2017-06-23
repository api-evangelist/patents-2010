---

title: Database replication
abstract: A new database design is implemented in which everything in the database is modeled with primitives, including the links and nodes for a graph tuple store. A query syntax provides a nested tree of constraints with a single global schema. Various optimization techniques for queries and replication techniques are also described.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08204856&OS=08204856&RS=08204856
owner: Google Inc.
number: 08204856
owner_city: Mountain View
owner_country: US
publication_date: 20100120
---
This application claims priority to U.S. provisional patent application Ser. No. 61 146 240 filed 21 Jan. 2009 which is incorporated herein in its entirety by this reference thereto.

The invention relates to the organization and use of information. More particularly the invention relates to a graph store.

There is widespread agreement that the amount of knowledge in the world is growing so fast that even experts have trouble keeping up. Today not even the most highly trained professionals in areas as diverse as science medicine law and engineering can hope to have more than a general overview of what is known. They spend a large percentage of their time keeping up on the latest information and often specialize in highly narrow sub fields because they find it impossible to keep track of broader developments.

Education traditionally meant the acquisition of the knowledge people needed for their working lives. Today however a college education can only provide an overview of knowledge in a specialized area and a set of skills for learning new things as the need arises. Professionals need new tools that allow them to access new knowledge as they need it.

In spite of this explosion of knowledge mechanisms for distributing it have remained pretty much the same for centuries personal communication schools journals and books. The World Wide Web is the one major new element in the landscape. It has fundamentally changed how knowledge is shared and has given us a hint of what is possible. Its most important attribute is that it is accessible it has made it possible for people to not only learn from materials that have now been made available to them but also to easily contribute to the knowledge of the world in their turn. As a result the Web s chief feature now is people exuberantly sharing their knowledge.

The Web also affords a new form of communication. Those who grew up with hypertext or have otherwise become accustomed to it find the linear arrangement of textbooks and articles confining and inconvenient. In this respect the Web is clearly better than conventional text.

It has no mechanism for the vetting of knowledge. There is a lot of information on the Web but very little guidance as to what is useful or even correct.

There are no good mechanisms for organizing the knowledge in a manner that helps users find the right information for them at any time. Access to the often inconsistent or incorrect knowledge on the Web thus is often through search engines which are all fundamentally based on key word or vocabulary techniques. The documents found by a search engine are likely to be irrelevant redundant and often just plain wrong.

There are several aspects to how learners obtain knowledge they might look at how authoritative the source is for example or how recent the information is or they might want the ability to ask the author a question or to post a comment. Those with knowledge to share might prefer a simple way to publish that knowledge or they might seek out a well known publisher to maintain their authority.

While books and journals offer the authority that comes with editors and reviewers as well as the permanence of a durable product the Web and newsgroups provide immediacy and currency as well as the ability to publish without the bother of an editorial process. Table A is a summary of the affordances of various forms of publishing.

The invention addresses the problem of providing a system that has a very large e.g. multi gigabyte database of knowledge to a very large number of diverse users which include both human beings and automated processes. There are many aspects of this problem that are significant challenges. Managing a very large database is one of them. Connecting related data objects is another. Providing a mechanism for creating and retrieving metadata about a data object is a third.

In the past various approaches have been used to solve different parts of this problem. The World Wide Web for example is an attempt to provide a very large database to a very large number of users. However it fails to provide reliability or data security and provides only a limited amount of metadata and only in some cases. Large relational database systems tackle the problem of reliability and security very well but are lacking in the ability to support diverse data and diverse users as well as in metadata support.

The ideal system should permit the diverse databases that exist today to continue to function while supporting the development of new data. It should permit a large diverse set of users to access this data and to annotate it and otherwise add to it through various types of metadata. Users should be able to obtain a view of the data that is complete comprehensive valid and enhanced based on the metadata.

The system should support data integrity redundancy availability scalability ease of use personalization feedback controlled access and multiple data formats. The system must accommodate diverse data and diverse metadata in addition to diverse user types. The access control system must be sufficiently flexible to give different users access to different portions of the database with distributed management of the access control. Flexible administration must allow portions of the database to be maintained independently and must allow for new features to added to the system as it grows.

U.S. patent application Ser. No. 12 049 145 filed 14 Mar. 2008 which is incorporated herein in its entirety by this reference thereto provides a system to organize knowledge in such a way that users can find it learn from it and add to it as needed. In connection with such system and especially with schema last approaches to information storage and retrieval two observations are noted 

1. A collaborative database must of necessity support the creation or modification of schema long after data have been entered. While the relational model is quite general current implementations map tables more or less directly into btree based storage. This structure yields optimal performance but renders applications quite brittle. This invention supports a Schema Last approach. 2. A conventional table of tuples implementation is problematic even on a modern column store. The starting point a table of tuples and indexes with compound keys which are permutations of subject predicate object is well studied and subject to obvious limitations of index size and self join performance. Attempting to optimize an existing relational store for this tuple access pattern while possible is burdened both by compatibility with a relational model that is far more general than needed and by an SQL interface in which it is difficult to say what is really meant.

A new database design is implemented in which everything in the database is modeled with primitives including the links and nodes for a graph store. A query syntax provides a nested tree of constraints with a single global schema. An aspect of the invention concerns the process of flushing the log preemptively as well as replicating the database. Various optimization techniques for queries are also described.

A primitive model is provided in which everything in a database is modeled with the primitives including links and nodes. A query syntax provides a nested tree of constraints with a single global schema. An aspect of the invention concerns the process of flushing the log preemptively. Various optimization techniques are also provided.

An embodiment of the invention is implemented in an application found at freebase.com which is a data search and query facility that is powered by the proprietary tuple store i.e. the graph store described herein and which is referred to as graphd. The present embodiment of graphd is a C Unix server that processes commands in a simple template based query language.

An embodiment of the invention see provides a computer implemented method and apparatus for establishing a primitive based graph database. A processor is configured to providing a plurality of primitives that are identified by globally unique identifiers GUIDs which consist of a database id and a primitive id . Once written primitives are read only. The primitives collectively establish a log structured or append only database. The processor assigns primitive ids to primitives in the database sequentially as the primitives are written and provides a plurality of fields for each primitive . Any or all of the fields may be null. The fields comprise a left field comprising a guid representing a first end of a relationship arrow a right field comprising a guid representing a second end of said relationship arrow a type field comprising a guid that is used in conjunction with said left field and right field to specify a type of a relationship a scope field comprising a guid that identifies a creator of a given primitive and a value field comprising a string that carries any of literal values strings numbers and dates.

The processor responds to user interaction with the database to establish one or more primitives that comprise either nodes without a left field or a right field or links which always have a left field and which can also have a right field. Nodes represent identities and carry no other data links represent properties of an identity where the links comprise either a literal value or a relationship. A node and its associated links comprise an object with fields properties described by one or more types.

The processor modifies a primitive to change the primitive s value by writing a new primitive carrying a modification and marking said new primitives as a replacement for the primitive that it is replacing. The processor deletes a primitive by writing a new primitive which marks the primitive to be deleted as deleted. The processor removes deleted or versioned primitives during query execution.

Graphd primitives see are identified by Globally Unique Identifiers GUIDs which consist of a database id and a primitive id. In a database primitive ids are assigned sequentially as primitives are written. For example 9202a8c04000641f8000000000006567 is the GUID which corresponds to the person known as Arnold Schwarzenegger . The front part 9202a8c04000641f8 is the database id and the back part 6567 is the primitive id.

Once written primitives are read only. Graphd is a log structured or append only store. To modify a primitive for example by changing the value one writes a new primitive carrying the modification and marks it as a replacement for the old. To delete a primitive one writes a new primitive which marks the primitive one wishes to delete as deleted. Deleted or versioned primitives are weeded out during query execution.

In addition to many implementation advantages a log structured database makes it easy to run queries as of a certain date.

With few exceptions none of which are visible to the user primitives may be regarded as either nodes i.e. things without a left or right or as links which always have a left and usually a right. Nodes such as . . . 6567 are used to represent identities and carry no other data. Links are used to represent properties of an identity either a literal value for example height or a relationship for example employs employed by. 

Looking at for example Arnold we see a property named people person height meters with a value of 1.88. This is represented by a single tuple whose left is . . . 6567 type is . . . 4561f6b and value is the UTF8 string 1.88. 

A relationship is similar but has a right instead of a value. The property such as type object type which identifies an object as being an instance of a particular type is represented by a guid . . . c. That Arnold is typed as a person is indicated by a primitive whose left is . . . 6567 type is . . . c and right is . . . 1237.

At the MQL level a node and its associated links are regarded as an object with fields properties described by one or more types. Such objects map naturally into the dictionary based objects supported by dynamic languages such as Python and Perl.

While MQL only exposes nodes as identities the notion of identity is so fundamental that graphd could reasonably be described as an identity oriented database. Giving every piece of data a fixed identity is radically different from the relational model which deals only with sets of values and leaves the notion of identity up to the application. Working with identities as a first class notion is essential if schema is to be flexible. Long before we can agree on the exact shape of the data used to represent a person or a building we can agree that individual people or buildings exist and that they have certain obvious attributes that we might want to record height address builder etc.

An embodiment of the invention illustrated in provides a query model that operates in connection with a processor configured for positing a query to the database . The query comprises a template expression that comprises a parenthesized comma separated list of zero or more constraints. One or more of the constraints define which primitives match the query and one or more of the constraints define instructions that detail what information is returned to query matches and or how the information is sorted and formatted 

When a query executes each of a plurality of parenthesized nesting levels of templates is evaluated to a list of primitive components that match the query. If a constraint holds subconstraints the subconstraints are evaluated to nested lists of primitives that match a particular subconstraint. Multiple constraints combine disjunctively.

MQL looks up the GUIDs for people person height meters and topic en arnold schwarzenegger and produces the following graphd query 

The first thing to notice is that all notion of schema has been compiled away. Unlike with a conventional RDBMS which preserves the notion of type all the way through query evaluation i.e. the row source tree we ask graphd a question which is expressed entirely in a simple vocabulary of constraints on a universal primitive type. Graphd does not know anything about people person or any other type or even the general structure of types.

As with MQL and unlike SQL the graph query language is template based the syntax of the query parallels the structure of the desired result. Each parenthesized expression corresponds to a constrained set of primitives. Nested expressions are related to each other via one of the linkage fields. So the outermost expression 

The basis for the query evaluation is a nested loop join we take a candidate satisfying the outermost constraint in this case there is only one and then look for candidates that match the inner constraint right null type . . . 4561f6b which also relate to the candidate for the outer expression in the specified way i.e. with their left.

By itself a nested loop join is hopelessly slow. However there are a variety of optimization techniques discussed herein that we can use to reduce the size of the candidate set at each node in the query.

The traditional approach to create a database is to start with a set of tables into which data are stored. The schema of the database defines the structure of the tables. The tables correspond very closely to the underlying storage mechanisms e.g. hard disks. One problem with this approach is that the design of the data structure has profound implications for the design of an application for accessing data in said data structure. Certain things get fast certain things get slow certain information is redundant there must be carefully structured update routines to keep the database in sync etc.

One approach is to collect the data and then create the schema last. This makes it easy to change the tables in the data structure. Thus if the system stores data denormalized in a certain way it is simple to encode the fact that the data are denormalized in the structure of the database itself such that the data could be broken into two tables at a later time without having to make that structure explicit.

In an approach that comes up with establishing the schema last where the system collects data and then later on a determination is made on how to organize the data the first question concerns what the data are about. In the invention data are collected about identities where an identity is a mathematical notion that corresponds to some identifiable entity. For example there is a single thing that corresponds to Arnold Schwarzenegger and there are lots of data that are related to that identity. The identity in this example is the thing that to the extent that anyone can agree to anything at all is this person called Arnold Schwarzenegger who can be described in many different ways. There is not any further reduction to be made to an identity. It is the atomic particle of information. Thus the data are related to that single identity to which one can add types i.e. the schema later. The schema becomes a way to talk about the data not a definition of how the data are stored. In the invention facts are known about entities in the world and these facts can be grouped in certain ways to create sets of entities which have common sets of facts referred to as types. An embodiment therefore comprises an identity based data store i.e. a graph store.

In an embodiment e.g. where C code implements the graph there is no knowledge of a schema. The graph does not know about any of the types. It does not know about people or authors or publications or any of the types that contributors may come up with. All that the graph knows about are nodes that represent identities and links that represent data about identities see . In considering these identities it is also possible to consider sets of identities e.g. everyone whose first name is Scott. In this example the table has a column that represents the name Scott and corresponding row IDs which comprise an array of numbers. Accordingly there is a single column that comprises the most minimal representation for a set because the column comprises a linear collection of numbers. Representing sets in this way has several advantages. For example it is easy to perform intersections at unions.

In an embodiment an entity such as a person is represented as a node and various bits of data concerning this person are represented by links to the node. There can be another person and once again various bits of data that describe this other person. There can also be a node that does not carry any data. There are links between the nodes that can carry data. The nodes and links are all primitives. When the primitives are written each primitive has an identifier and as the primitives are written it is possible to build up an index that consists of the input sets that are used to drive an optimizer discussed below . The indexes are typically tables e.g. hashed structured dictionaries.

A higher level type has a significant amount of structure. At a bottom level the structure is a node in the graph. For purposes of handling queries only the identity of a node is of concern. A node is encoded into tuples that represent the links. An ID is assigned to links as they are written. In an embodiment the IDs increase sequentially. Information about each link is recorded in an index. The indexes detail for example all of the links of a particular type. Thus if a type is the name type the system can keep track of things for example which are names in a dictionary. Primitives are thus added in numerical order and the system appends them onto an array which provides a sorted set representation that underlies the system. The ID is the manifestation of for example the identity of an individual. The only commonality through all the nodes is they all have unique identities. Thus the only thing that is unique about anything in the system is the ID number.

The node corresponds to an identity in the real world. It is an identity of something that is to be described in the system. Anything accessible in the system must have a node to represent it and optionally it can have links that add data about it such as its relationship to other entities. Accordingly there is a node which comprises an identity of some entity and the identity can have with it various links. These tuples and each of the links can define a type with which they can be associated.

In the example where the object is called Arnold there is an assertion of fact that is substantially independent of the final schema. In other words the Arnold column can be part of any set of relational information. Thus there is any number of things that can be used build the schema but they all devolve down into types associated with the linked tuples. The resulting graph allows the system to keep track in an index of links of type name.

Whenever a primitive is written the system adds the ID for the primitive to all the sets that are appropriate. There is one set for each kind of linkage. As discussed above the primitives have a left and a right and can have a value and have a type. An object is a primitive that has a type but does not have a value. Every link i.e. a left has a type that says what sort of link it is. From the standpoint of the database the system does not know anything about what the type means. All that is known is that the system is asked to constrain the type e.g. find all of the spouses of the object e.g. Arnold. Some of the links have values which are literal actual strings that are stored in the link e.g. names dates of birth etc. Some of the links do not have any values such as an instance of link which means that an identity is an instance of a particular type. For example Arnold is a person. For example there is person and the primitive points to an instance of a type. There is not any value in that case. Rather this situation typically expresses a relationship.

Accordingly it is not necessary to have a separate entry for each instance. One just simply says that Arnold is an actor and he is also a governor he is also a spouse etc. and there is an instance of a governor an instance of an actor an instance of a spouse etc. By using indexing I accordance with the invention it is possible keep track of all of these instances in a simple uniform manner. This typically comprises an array of IDs that may have a further property such as being sorted in ascending order e.g. because as they are created they are added to the index.

Graphd supports a subset of the traditional database ACID guarantees see it is optimized for collaborative wiki style access. We assume a long cycle of read write interactions and so provide no built in read write atomicity. Instead we guarantee only that writes of connected subgraphs of primitives are atomic and durable . In the sense that it never becomes visible to a user it may be the case that q user s write collides with someone else s. However the user s input is always preserved and if the user desires it can easily be re instated by browsing the modification history.

For example in a processor is configured to capture and preserve user input during a long cycle of read write interactions and guarantee that writes of connected subgraphs of primitives are atomic and durable . In this way the user s input is always preserved and if the user desires it can easily be re instated by browsing the modification history.

In the performing of callbacks includes providing a graph server having a time ordered output buffer chain for each connection to each of a plurality of clients comprising data waiting to be sent back in order to a client . A callback is callback to each individual output buffer in the output buffer chain . The call back comprises a function pointer to a function within the graph server. The call back indicate how up to date the data should be at this point in time.

The database maintains a counter as it executes write operations . In coordination with the processor the database executes the write operations and updates the counter to a current state. A callback value is then compared to the counter and the callback is satisfied when the counter indicates that the database is up to date.

A typical query is for a specific node. Initially nothing is known about it. There is a link which refers to the node with its left and its type which is its GUID i.e. a number that corresponds to the node for the type. The node has other links and the type for such links may be for example such things as date of birth etc. There is thus a query which asks for a node with a link of a particular type whose value is for example a name such as Scott and which asks for another link of another particular type whose value is for example a birth date such as 1964. Thus a query in one embodiment comprises a nested loop join.

In satisfying the query instead of using everything in the database as the set of candidates it is preferred get a smaller set. For example two things are known about each link. Each link has a particular type that can be looked up. In this example the type corresponds to the name. There can be an array that has a particular value and that can be looked up as well. These two arrays can be intersected quite rapidly. When the arrays are intersected the result is a much much smaller set. Thus instead of looking at for example 300 million candidates for each part of the query there remain 5 or 100 or 1 000 candidates for example. Accordingly a simple join goes much faster.

A separate search can be made to satisfy both of the links in the query resulting in two lists or sets of candidates. The system then intersects these two sets or lists of candidates. These sets are candidates for the links and it is necessary to get the left of the tuple. In this example the sets for the first link are sorted straight out of the index. Thus it is possible to perform an intersection very rapidly for the first link. When this is done the result is a set of candidates that are represented by the left. When one asks for lefts of this nicely sorted set of candidates e.g. for the next link to satisfy the query they do not come out in order. Rather an unsorted list of candidates is returned. There is no fast algorithm for sorting them. For example the lists may comprise 1 000 Scotts for one link and 20 000 people who were born on that date for another link. Thus there are 1 000 unsorted lefts for one query term and 20 000 unsorted lefts for the other query term.

One way to complete the query is to take a candidate from a first list of candidates and check the candidate against the other list of candidates. Another way to complete the query is to take a candidate from the other list of candidates and check the candidate against the first list of candidates. So how to pick One could select the list having the smallest number. But the main concern is minimizing calculations for example by estimating the size of the result set. That is if an intersection is performed how big is it really Because for example if the results of the intersection are almost the same size either way it is probably a waste of time to even do it. It would be just as fast to pick one list and check the candidates as they come up for the other list. Whereas if the results of the intersection are tiny then it is really valuable to select one list over the other because this technique reduces the number of candidates which go into the nested join.

Typically a first step is to decide which of the lists containing sets of candidates to use as a producer and which to of the lists to use as a checker. One way to do this is to compute or try to compute the first few items in each set of candidates and record how much this costs in terms of an abstract count. Based on the cost it is possible to decide whether to use one list as a producer and check on the other list or vice versa. Because real queries are complex and go down many levels the cost comparison is quite valuable. Thus this aspect of the invention provides a cost based optimization that is applied to a universe of nested sets of identity constraints. Here sets of identities represent a constraint having particular types and values that are combined into the sets. Each node is annotated in the query with a set of candidates which is typically much smaller than everything that could be queried. In a sense this embodiment of the invention runs a race and decides which list is more efficient as a producer than the other.

As discussed above in connection with optimization of query resolution during nested joins it is still not known which list is going to be the winner. If an exhaustive cost based optimizer is used then it goes through every permutation. If one is running a production database where it is necessary to do the same job every night it is completely worthwhile to spend 36 hours in the optimizer figuring out the most optimal way to do this query. But in the world of the invention where queries are whatever people think up it is not practical spend that amount of time. Rather it is necessary to decide at query time how to optimize the query. This is referred to as an ad hoc query in the database literature. Thus the invention performs an ad hoc query while generically traditional relational technology is good for a production query where it is worthwhile to spend the time optimizing because the same thing is encountered a million times.

Thus as shown in this embodiment of the invention performs a cost based optimization that is applied to a universe of nested sets of identity constraints where sets of identities represent a constraint having particular types and values that are combined into the sets. A processor implemented step formulates and presents a database query in a template based query language . The query terms comprise primitives which comprise any of nodes in a graph and links that express relationships between the primitives. Each primitive has a type and a value. A query results in a node returning corresponding first and second lists of candidates. The first list for a first link of a first type having a first value and the second list for a second link of a second type having a second value.

A separate search is performed to satisfy each of the links in the query by taking a candidate from the first list of candidates and checking the candidate from the first list against the second list of candidates and simultaneously taking a candidate from the second list of candidates and checking the candidate from the second list against the first list of candidates. At least a first few items in each of the first and second lists of candidates are computed and how much this costs is recorded for each list in terms of an abstract count. It is then determined which of the first and second lists containing sets of candidates to use as a producer and which of the first and second lists to use as a checker based upon said abstract count . A resulting a list of candidates is returned for each link and the sets of candidates are intersected to resolve said query .

Another embodiment of the invention concerns replication. As shown in the system comprises a master database against which all writes occur . This embodiment of the invention assigns sequential IDs to each item in the database . It is desirable to scale the system up beyond a single machine. Thus in the system there is some number of replica machines . In the invention each replica machine establishes a connection with the master database as a replica. The master database sends every primitive that is written to it to the replicas . A key feature of the invention that allows this to work is that where the write on the master may fail because some constraint is not satisfied if the write succeeds on the master then it is known to succeed on the replica. Thus the replica only needs to write three primitives. It is not concerned about if it would fail halfway through a query or not.

In a situation where it is desired to have the middle tier talk directly to a replica to establish a connection the question becomes What is done with the write In one embodiment of the invention there are two things that could be done. One of the things that could be done is to have the middle tier know when there is a write and then establish a separate connection so that the write comes back down to the replicas. A disadvantage of this approach is that the middle tier then must know a lot more such as where the master is especially because there is a tendency to change masters from time to time. It is preferred to tell the middle tier to go find a database where any one is as good as another. However the middle tier is provided with one connection to whatever database it is using. When it sends a write to the replica the replica cannot process it but it has a second connection to the master. The middle tier forwards the write along to the master . Accordingly all of the replicas have additional connections. The master does the writes and then the resulting primitives come back out. If there is a replica of a replica the replication protocol passes the address of the master along so the replica of a replica also talks directly to the master. Thus when primitive writes come in they are written a response comes back and then the response goes back out to the middle tier.

Another problem arises when one writes something. In this case it is desirable to see that write when a next read is performed see . In this system there is no transactional guarantee about where the replicas are with respect to the master. So in particular one could write something and get a response back and then try and read it. If one is really quick or replication is slow the write might not be available. In this regard the invention provides an approach that relies on the fact that IDs are assigned in sequential order. When a write is performed one or more IDs are returned. It is known what that ID is because it is encapsulated into a virtual time i.e. a virtual time. When a write is performed a virtual time is returned. If one is interested in reading the same thing that virtual time can be provided as a parameter that indicates it is desired to read something at least as new as the virtual time. Here the request waits if the replica is not at least caught up to that point. Thus one could perform a write and get back an ID e.g. 231. When a read is then performed it is necessary to receive a primitive that has an ID of at least 231. If the replica has primitives that only go up to 220 it is at least 11 behind. In this case the system waits to answer the request until it gets the desired primitives e.g. those with an ID of at least 231.

As shown in a processor configured is to use sequential IDs as a virtual time that allows query results to be guaranteed consistent as of any desired virtual time and a read request is pended until a replica is at least caught up to the entry point encapsulated into the virtual time .

The preferred embodiment is a write through arrangement with nothing stored in a buffer. The virtual time mechanism described above comprises a virtual time technique that is associated with the fundamental structure of the data. An embodiment provides a unique entry point i.e. touch that pretends that the system is up to date without actually writing anything. All it does is ask for the current virtual time. Even if one goes all the way back to the master the result is still out of date almost instantly as more writes come in because writes are happening all the time. If a write is performed to one replica and a touch is performed to another replica there is some risk that the system would not catch up with itself unless it was implemented by looking at the master.

As shown in a processor configured to create an index of primitives on the database . The primitives are immediately written to a log file of primitives one after the other without indexing on the database . An up to date cache of primitives to be written to the index is maintained . Flush of the index from the cache to the database is delayed and the index is written from the cache to the database . When writing a primitive to the database a series of callbacks is performed to update the index.

One problem with this index organization where an index is a table is that tables have bad locality reference. What that means is if one is looking at something in a table it is quite probable that the next thing looked at is a long way away from it. If this is first item is stored on a disk it is necessary to read in a new page to look at the table. What this means is that the set of pages that looked at is very large and a lot of time is spent bringing them into memory or bringing them into a cache. There is not anything that emerges out of the structure that corresponds to something that actually means anything to a human being. The query sets however actually do correspond to actual meaning e.g. the set of all authors. That is a meaningful set and something that is actually used. This structure is also extremely compact. The advantage of having a compact structure that sits in memory versus a big expanse of pages that must be read through is huge. Thus this aspect of the invention provides excellent locality of reference with the query sets.

The intermediate results are relatively bulky. They are subpieces of the table. What is typically done with the intermediate results is to read something out of the table and look it up in another table. It is the looking up operation i.e. the random access that hurts the locality of reference. Once the system has filtered through and got all of the authors there actually is a set of authors. This comes out of the organization of the identity organized database and particularly the tuples are issued. Rather than having just the tuple indices there are indices of all of the lefts of everything. Thus the state of anything that could be the subject of a left is instantly known just from the identity. Everything is associated with the identity so it is not necessary to look for other aspects of that identity elsewhere because once the system hits one aspect of the identity it hits everything about that identity. This depends on the specificity and the linkage.

This aspect of the invention thus concerns a straightforward way in which the data are stored on disk and the indexes that allow the system to find data given some component. As discussed above the individual data records are tuples consisting of a value a name and pointers to other records. Thus the primitive has a value i.e. it has a name that is not a text string it has a data type that says something about the meaning of the thing that makes up the value and there are four pointers i.e. scope type left and right where left and right are meaningless and are used to construct the overall meaning of the records in the view of the application. Type and scope are more restrictive in that the type of a link between the left and right GUID describes the nature of the relationship. This is of interest because the indexing scheme herein described treats type plus left and type plus right as things that are desirable to index because people want to look them up. Thus if there are three indexes there is a term lookup where a list of things that relate to something is found.

For example see Arnold has a name of Arnold which connects a featureless node that is identified with the person Arnold and with the language that it has been labeled in e.g. English. It is known that this is the node Arnold because there is a primitive that points to Arnold with one end. The one side points to the namespace. Suppose the left points to the actual Arnold node then the right points to English and together this amounts to the fact that on a featureless node this is in fact named Arnold in English. There are three primitives to make up the assertion that Arnold s name in English is Arnold. This is similar to the primitives in the assertion that Arnold is in fact a person. There is a primitive that is the type person similar to how it is known that this primitive is the language English. A fact is created that indicates that this primitive is connected to the type Leis an instance of relationship. This group has as a type i.e. it points with its type arm to some other node which symbolizes this instance of relationship. Arnold also has a scope because it was inserted at a certain time and all primitives that are created through the same insertion for the same person through the same process are labeled with the same scope. The scope is typically the user who is writing to the database i.e. it comes with a lifeline to a record. Thus the primitive here has a scope and a type.

The example above comprises a tuple in which Arnold has a type which is the display name that is seen by the user and in which there is a scope which is the attribution to the contributor. On the right it is shown to be in English and on the left it points to the Arnold thing. The Arnold thing is another tuple but the Arnold thing is almost completely featureless other than the scope. It stands for the thing in the real world which is Arnold. Even that Arnold s name is Arnold in English is an assertion of a fact. On a higher level if there was another node that represented Maria Shriver there would be another set of three of these things.

As shown in primitives also point to other primitives that they version . If one wants to rename Arnold to Bob another display name is written and a link is put through the Arnold node in the same way that the Arnold tag was named. As soon as Bob is inserted Arnold is no longer valid. The retrieve from the database can be positioned whether or not a node has been versioned. It can be asked Does anybody else function in the same way Then it can be asked whether anybody wants to be the left hand or the right hand or the scope and so on. If a double database query is performed and one of the nodes that is about to be retrieved has been versioned it is known that the system cannot return this value. It must find another one. These lookups at retrieval time amount to always finding the newest version of the data but never throwing away the old version. Thus this aspect of the invention provides an audit trail. If there are indexes pointing to something else with a previous pointer that other thing i.e. the something else at some point asks Does anybody point to me That is quickly answerable because the system keeps an index of who points to whom that can be used to trace these relationships down in reverse. This is referred to as a reverse index. Take for example a sequence of three in time the first one having the second one point to it and the third one pointing to a third one. The second one has a pointer that says Here is the previous. It is known not to go to that because it is previous and the system does not do that unless an investigation is being performed.

Take the example above where the previous arrow is coming up and another arrow is coming in from another one. The one that is in the center knows the previous ones. To find out if there is a subsequent one go to the table. In the table one can look up the index and there is an entry i.e. the next position in the index. Thus this is not the last word on the subject. All the boxes have unique identifiers e.g. GUIDs and all of the GUIDs for everything including the versioned things are in one large namespace. There is also a second mechanism. To remove a tag version it as if it were to be changed but tag the replacement with a fact that says I don t really exist. As shown in this amounts to a tombstone mechanism . That item can be versioned again to reconstitute e.g. Bob so it is not a permanent death. Whenever any primitive is retrieved it is necessary to check to see if that flag is set in which case the item does not actually exist and it is not possible return it. This is determined by looking up in the index whether anything points to it. The indexes are centrally maintained. When writing a primitive to the database it gets handed off to a series of callbacks that update the indexes.

A key point of the invention as shown in is that the primitives are nested stacked or combined to formulate a query. The example above starts with the uppermost piece which in this case is Arnold and the uppermost piece turns into the set of everything that matches it. Then in each element of the set of the things connected to the specific element of the top set there is a respective instance of pointers. Suppose there is a query for Arnold who is married to Maria. The first thing that is going to happen is that the upper primitive is Arnold. The system then tags all of the Arnolds and asks for Arnolds with an instance of Maria for example i.e. all the instances that do not have Maria get pruned out. Different constraints more effectively prune the set than do other constraints. As discussed above to satisfy the query the system tries two different strategies one strategy takes an Arnold instance and sees if it can be proven to be an instance of person and the other strategy takes the first instance and sees if it is easy to prove that it has the name Arnold . The system can process sets of different sizes on both sides but they might yield results faster depending on for example proving that Arnold is a person is going to be more successful than proving that a person is Arnold . For example the system may try for five matching results where whichever strategy gets the first five wins becomes the strategy for the whole query. In this example the system processes by Arnold i.e. it looks up the instance of person because Arnold is a common name. At that point a clear pool of candidates appears and the system then matches these candidates. For example Arnold is a more common name than Ford and this fact might change the direction of processing which is important because there is a very large data set in the system that is full of real world data.

Different optimization strategies work with different queries. This is particularly important because the case of a person called Arnold is a simple query but where there is a complicated nested query such as music for movies in which Winona Ryder appears such as The Breakfast Club such query can take a long time to resolve because the set of movies that Winona Ryder appeared in is difficult to determine quickly. Resolution of such query does not just involve choosing between two branches because there could been branches in the resolution of query. The constraint tree in this example and as shown in is a tree of data structures that describe what the user wrote in their query. Each of these constraints is elevated with iterator trees referred to as iterators which are basic elements of the query optimization scheme disclosed herein. The iterator trees notice such things as the fact that there is a table or that everybody who is valuable is Arnold. It is necessary to identify something that has an entry in the table. It is known what this type is because there is a table of things that have that type and it is necessary to find something that is in all tables returned by the query. One aspect of the invention provided an and iterator that intersects each of these tables. There are several strategies for doing this depending on how big the tables are and how much they actually intersect. Thus an iterator can be added to each constraint . All of these iterators know about their particular piece of the hierarchy. They do not know everything. As one moves up through the constraint tree the iterators are used to build up larger branches until the tree is complicated and has copies of the iterators. They are not just copies they are actually preserved links. If there is a copy of a branch and it learns about what the branch actually looks like e.g. how much the query terms intersect or what is a good strategy for computing this particular branch then the iterators remember this. They have a common background storage e.g. a cache that they all use to optimize processing. Once they do this again e.g. a third time one branch already knows how to resolve a term. The result is a complicated multi armed iterator. At the top level there is an iterator that is determining which of three sub arms to lead with to produce IDs and that then checks them against the other arms or branches. In this example the iterator runs three races in parallel one race between three candidates in parallel. Each of these is in turn also trying to figure out how to do its production. Thus each of the arms in turn also runs races in parallel and so on. With all of this iterating going on at some point there must be a resolution. Because the determinations get easier and easier as the system goes down the tree eventually there are only e.g. five values or it is known that Winona Ryder only appeared in 20 movies and it returns a table of the 20 movies. At this point resolving the next query term is easy. The systems pulls out the ID numbers e.g. for the 20 movies and checks them against the other query terms. At that point one branch is finished processing and the races end . The current iterator becomes more efficient in turn. This determination percolates up but at the same time that this is happening there can be a completely different sub branch where two complicated lists of terms are being processed but in the end they determine that there is no overlap at all. At this point the top level iterator realizes that it has no results for this branch. The result set is empty it sends a message to the client We re over. The process of percolating up results about Winona Ryder movies is stopped.

When answering individual questions about optimization it is necessary to constrain how many resources are invested in an operation. In an embodiment of the invention shown in all of these operations i.e. all of the functions that are called have a budget granter . This is not a fictional unit in an embodiment this unit is expressed in terms of dollars although it has nothing to do with real dollars. When one of the investigations overruns an allocated budget it returns and indicates that it does not have a result yet . Once there is more budget then there can be more research. This use of interruptible budget driven value functions tries to execute its portion of a query and get results back to the top level of the tree as soon as possible but also as accurately as possible.

Thus this aspect of the invention as shown in tries to resolve the query terms at the lowest level first across the various branches where the iterators are resolving these iterations . As the query terms get resolved in a positive way they get passed up to the next level which then starts to run its test also. As this is working its way up if at the top it is determined that the query cannot be resolved even if there are some correct results below but they are not useful because they lead to a dead end then the system can either call the search off or it could keep passing itself up branch by branch to the top of the tree until there is a resolution. At the same time there is a budget function that may determine that the system is putting too many units into the query. In such case the system stalls the resources going into the search and does not search anymore.

There is also a worst case strategy in which every branch is tried until it reaches an end. This approach can be efficient if it turns out that all of the terms match. Alternatively a read query can be performed e.g. read trying every branch. In any event it is always desirable to produce a result. Key to this aspect of the invention is a question of efficiency i.e. allocating resources where they do the most good improving response time as quickly as possible and narrowing down the search space as quickly as possible.

Thus an embodiment of the invention comprises the use of a strategy that employs multiple optimizations at the same time. In a further embodiment the result sets are a subset of all the possible results of a constraint. In other words the system is not always asking for everything that matches a query term. For example a query might ask for five movies that starred Winona Ryder. If there were 30 such movies it is still important to find five quickly and then not look for any more. That is the search hit the constraint of returning only five movies.

Another embodiment of the invention concerns optimizer freezing and thawing. Optimizers are data structures that are interpreted by code. They contain conduits to the database proper onto the disk which is mapped to the memory. Data structures point to the memory but first come to the mapped disk. This means that if a read does not finish quickly it blocks write access to the disk because it is not possible to change the data structures while still pointing to them. It is not desirable for any one call to block access by everybody else. In this embodiment as shown in a scheme is employed to freeze the iterators. That is the iterators are pickled into string form and then the string is stored somewhere . Then the system thaws the string later on once it wants to resume the query . The iterator is thus thawed from its string form back into the iterator shape restoring all the pointers and then the system begins running the operation again .

Another aspect of the invention concerns the use of cursors. In this embodiment if it a client desires to get a very large result set from the database for example all of the people where there are half a million people in the database the client would not want them all at once because the client would not want to digest that large an output. It would take too long to give the client the answer and digesting the answer would take too long and require too much memory. One feature in the database in this embodiment in the example above returns a desired portion of the total result such as 100 at a time or 1 000 at a time. If there are more results available the system indicates this fact and the client can give the system a token i.e. a cursor. The cursor mechanism is used to temporarily suspend long lived accesses. In the example above the client pulls up 100 results from the result set and then the query is suspended. During this period of suspension the users can write keep working in the database. The database is not waiting for the entire result e.g. 3 000 to be returned to the client. The client gets everything that was in the database when the query was started. If there were 200 people and the client asked for 100 of the 200 then the client receives the 100 plus the cursor. If someone adds one to the database while outputting of the results is suspended and then the client goes back to the database e.g. five minutes later with the cursor to get the other 100 results the client gets the other 100 results but only the original 200 results and not item number 201.

This aspect of the invention provides a way of relaxing the consistency guarantee so that many people can use the database at the same time. Thus a client can take a long time to finish retrieving query results without blocking database access by other people. Thus this embodiment of the invention provides a load balancing technique that operates by relaxing the consistency guarantee in return for letting many people use the database at the same time. When reading the database it is not desirable to block other people from writing. What is important to the client at the point that the query is posited is to get the results for the query at that time. If the client retrieves a result of all of the people in the database as of a certain point in time it is possible to identify the point in time and then later on present a query to identify what has been added to the database since the previous query.

As shown in a distributed system includes a write master . The data from the write master is replicated out into multiple read servers and the clients connect to the read servers . The clients do not write directly to the write master. They access the database and if the client writes something the read server that it is talking to forwards the write through to the write master which then updates the database. If there is a query and a cursor is returned by any of the read servers once the cursor is received one of the next e.g. 100 read clients that the querying client is paging through might be talking to another read client that did not give the querying party that cursor. At that point there are two possible strategies 

One strategy provides a status cursor where all the needed information is encoded inside the cursor and by sending that cursor to another read server that other read server is given enough information to find the records that the querying client is paging through. The cursor in this case includes information about the chosen optimization. As discussed above where resolution of a query involves an optimization e.g. trying to intersect two sets one for each query term there is a contest. In this embodiment the optimization strategy is rolled up into the cursor so that the strategy can be sent to another read server that did not produce the cursor. The information is based on the database only it is not based on some internal state of the read server.

The other strategy stores a state shares that state or binds the user to one read server and makes sure that the user always talks to that same read server.

One strategy in a presently preferred embodiment of the invention is an opportunistic mix of stateless and stateful. There is a stateless component that insufficient to reconstruct the last operation and then there is a stateful part that for the same read server allows that client go and look more information up that which it has stored. For instance if the system is in the middle of intersecting large sets of numbers with one another because a query asks for a person who is also a race car driver and born in Monaco it is necessary to intersect all sets of query related data. The result set is too large to return to the client. It would take a long time to send it by TCP. It would be a very large and difficult to return to the client in a URL or as an HTTP result. The set could be stored locally for a while depending upon how much traffic there is. If the client returns to the results and if not too much time has passed the client can look the results up and restart the query much more quickly. But if the system loses the results it takes too long to return them or the client is talking to a different read server then the system reconstructs the query and then resumes it. In a preferred embodiment there is a GUID of the person type and there is a table of everything that this instance of person leads to i.e. a table of primitives. The table is only added to at the end thereof. This means that if the present position in the table is known then that location is valid because when new primitives are created their numbers i.e. their IDs are larger than those that are already in the table. In this case the cursor starts at a certain location and thus indicates the position of client in the table. One can go back to a completely different replica halfway through the half million person set mentioned above and pick up where the process stopped because the read servers all have the same hard set of ID numbers.

The notion of suspended cursors is shown in where a processor pauses execution of a query . The paused query is saved by converting each the iterators to a string form . The strings are stored and execution of the query is resumed by converting the iterators from a string form back into iterators .

There is a marked difference between what is stored in the database and the indices that are built as a byproduct of loading that up with a particular location in the graph. There is a difference between what is in the data model and what remains in that data model through future versions of the graph as well as the new location when that data is loaded which comprises the indices that are made to effect certain kinds of queries. The idea with the indexes is if somebody turns off the power on the machine that the graph is run on and the graph before that sent an OK reply to somebody who sent in a write one can turn off the power on the machine at any point after that and still recover that primitive. As shown in when the primitive is written it is stored in an index sequential access database that has all the primitives and at that point the system can recover. Then the indexes are updated . These updates may or may not go through. They may or not actually have hit the disk by the time the power is turned off but it is known how up to date the indexes are. The indexes are updated in kind of jerky movements 100 things at a time 200 things at a time and the system remembers how far it was. For example one machine may be up to primitive number e.g. 512 and the primitive table that contains everything is up to 680 from the disk. In this case it is necessary to take the primitives 513 to 680 and feed them through this mechanism again.

This very basic kind of security allows relaxation in flushing of these indexes to disk. It is still necessary to make sure that the index actually measures how up to date they really are but this can be done when there is time in the system and with the right primitives. It is not necessary to do that before sending the alternate back which allows the system to be relatively speedy without losing reliability. In the preferred embodiment of the invention the index processing happens immediately. What is delayed is the flush of this index of information to disk. Thus the state of memory is always up to date as long as the server is running and it can immediately answer queries that require the indexes to be answered. That information only makes it to disk once there is room to write and that can be delayed. The log file of the primitives one after the other without indexing is written to disk immediately . Then if there is power loss it is necessary to go back to flushing the actual indexes to disks so that there is a permanent record of the indexes. It is possible to go back and find that the indexes have only gotten flushed so far but at a log file then process from that point forward. It is also possible to rebuild all the indices from scratch.

Uniquely the graph server as a process has an output buffer for each connection to each client process. This is not a single output buffer. It is an output buffer chain. The client process can have sent multiple quants the system writes and then gets all the replies back. That is more efficient than doing it one at a time because it is not necessary to wait a whole roundtrip.

At any one point in time there are many of these time connections. Each time connection has an output buffers chain of character data that waits to be sent back in order to the client. An embodiment of the invention shown in attaches a callback to the individual output buffers that is a function pointer to a function within the graph . The callback knows how up to date the data should be at this point. The code wrote a reply indicating that the data are written data to disk and it knows this if that OK goes out indicated that at least that much data was written to the disk. The process might understand that the system is up to primitive 480 while there is a process that knows it must be up to 512 and there is another process that knows it must be up to 514 and so on.

In this example the callback must be up to date up to 480. It goes to the database proper and it is the database itself that has a similar counter rollover as it writes to disk. The database knows that it is not up to date yet. It starts writing everything to disk waiting for all the data to be identically encoded. Then it updates its counter to its current state which might be for example 530. At this point the callback is satisfied because it is now up to date. Thus these characters can get sent to the client. The system is not making false promises anymore although it was making false promises when it wrote the OK. It is through the callback that it is possible to guarantee that what was written is in fact written.

Even when the writes are completed the system waits before saying OK to make sure that the database is caught up. The system only waits if it remembers where it must be at this point and if it is not there yet i.e. if it is not up to where it needs to be then at that point it writes everything is has. It is not just catching up to its work but it is doing all the work at that point. Because there is a significant latency in operating systems to flush things to disk it is more efficient to do all that it is necessary to do at some point in the future. Thus once the system commits to doing anything it should do everything. The system must reply to the client. There is a buffer chain with several things in it that have been written but before it is sent back to the client it is desirable to make certain that it has been written to disk. If it has not been written to disk then the system writes everything to disk for everything. Thus the whole buffer chain is written to disk so that now everything is caught up on disk and can be sent out to the client. The client does not have to be worried about things disappearing somewhere in the ether. As soon as the system gets ahead of yourself in what it is about to send to the client it stops and takes a one time hit to commit everything.

It is desirable to keep the log file on disk so that if there is a collapse it is possible to go back and reconstitute the system. The client has to rely on the fact that this has taken place. There is a large collection of 100 million things and people come along and ask questions. When a user performs a query the user submits a list of constraints. Constraints are expressions that must be satisfied for the query to be satisfied. By import the user gets back everything that satisfies these expressions. This can be something such as the value should be Arnold. In this particular case it is desirable to get back with this query such things as a node e.g. the Arnold node. In this example it is necessary to ask about nodes that are pointed to with the left side by nodes with Arnold. That is one thing that is known i.e. Arnold. Another thing that is known is that it is a person. There can also be another node pointing with its left side to where it is known that the type is an instance of something. It is known that there is a node and it is known that two things point to it with their lefts. There can be multiple lefts that end in the same place. An aspect of the invention builds up a set of constraints to help find the subset of the primitives that are of interest in a particular case. The primitives encompass value name a timestamp etc. One can stack them or can nest them. In the end what is desired is a sub graph in an overall connector database graph of primitives with a specific primitive that it is anchoring to. The query is satisfied when the system finds all of the matching sub graphs and returns them.

This is the data model for the graph repository as expressed in its access protocols and in guarantees that the repository makes about its internal state. The graph database is a collection of small fixed sized structures we call primitives. Dealing with the graph database means creating and querying primitives.

The graph repository protocol mainly alternates synchronous request from client to server with synchronous replies from server to client.

When sending tuples back and forth they are encoded as a space separated parenthesized list of values. A presently preferred tuple syntax is described in detail in Appendix 3 hereto.

This grammar is part of interface requests that match networks of links and nodes in some manner. They re used with the read command to access primitives a variation is used with the write command to create new primitives. A presently preferred template grammar is described in detail in Appendix 4 hereto.

Appendix 5 describes the search expression language for the graph repository s string operator during read queries.

The Uncopying tokenizer is written in such a way to almost never copy the data in query strings. This makes things fast because it doesn t shuffle data structures about quite as much it uses less memory and it uses memory mostly in more efficient fixed block sizes rather than allocating many small objects.

Appendix 7 hereto addresses a presently preferred design for multiple concentric graphd s where one graphd instance contains a superset of the data in another running instance.

As shown in a graph database contains another graph database . A master database is provided and at least one replica database core comprising an identity of said master database is also provided . A concentric replica database to said replica database core is provided to store any relatively long lived data which relates to the replica database core. For each transaction in a replica stream an equivalent set of writes is produced and applied to the concentric replica database . Thus the concentric replica database comprises a superset of the master database.

As shown in a method is provided for identifying poison queries and preventing connections to a database from trying to execute them . A processor is configured for identifying poison queries by storing a hash of a currently executing query into a shared memory that is used to determine that a crash has occurred during a write . When a parent process determines that a child has crashed the parent process reading the hash identifies a query that was running at the time of the crash . A dictionary is provided which maps a hash version of a query to a death count and date where the death count is a number of crashes associated with a query represented by the hash and the date is the date of a most recent crash. The death count and date is adjusted as poison queries arrive . When an entry s death count exceeds a threshold antidote messages are broadcast to all connections . New connections receive antidote messages for all poison queries immediately after connecting .

As shown in a parallel processing method for a database includes a database against which all writes occur . A plurality of processors are provided each processor establishing a connection with the database where each processor writes every primitive it processes to the database .

The computer system includes a processor a main memory and a static memory which communicate with each other via a bus . The computer system may further include a display unit for example a liquid crystal display LCD or a cathode ray tube CRT . The computer system also includes an alphanumeric input device for example a keyboard a cursor control device for example a mouse a disk drive unit a signal generation device for example a speaker and a network interface device .

The disk drive unit includes a machine readable medium on which is stored a set of executable instructions i.e. software embodying any one or all of the methodologies described herein below. The software is also shown to reside completely or at least partially within the main memory and or within the processor . The software may further be transmitted or received over a network by means of a network interface device .

In contrast to the system discussed above a different embodiment uses logic circuitry instead of computer executed instructions to implement processing entities. Depending upon the particular requirements of the application in the areas of speed expense tooling costs and the like this logic may be implemented by constructing an application specific integrated circuit ASIC having thousands of tiny integrated transistors. Such an ASIC may be implemented with CMOS complimentary metal oxide semiconductor TTL transistor transistor logic VLSI very large systems integration or another suitable construction. Other alternatives include a digital signal processing chip DSP discrete circuitry such as resistors capacitors diodes inductors and transistors field programmable gate array FPGA programmable logic array PLA programmable logic device PLD and the like.

It is to be understood that embodiments may be used as or to support software programs or software modules executed upon some form of processing core such as the CPU of a computer or otherwise implemented or realized upon or within a machine or computer readable medium. A machine readable medium includes any mechanism for storing or transmitting information in a form readable by a machine e.g. a computer. For example a machine readable medium includes read only memory ROM random access memory RAM magnetic disk storage media optical storage media flash memory devices electrical optical acoustical or other form of propagated signals for example carrier waves infrared signals digital signals etc. or any other type of media suitable for storing or transmitting information.

Although the invention is described herein with reference to the preferred embodiment one skilled in the art will readily appreciate that other applications may be substituted for those set forth herein without departing from the spirit and scope of the present invention. Accordingly the invention should only be limited by the Claims included below.

This is the data model for the graph repository as expressed in its access protocols and in guarantees that the repository makes about its internal state.

The graph database is a collection of small fixed sized structures we call primitives . Dealing with the graph database means creating and querying primitives.

There are two kinds of primitives nodes and links. A link is like a node but has two more fields pointers to a left and a right node.

The protocol mainly alternates synchronous request from client to server with synchronous replies from server to client.

The server can also asynchronously notify a client about an error that leads to it shutting down but that s going to be seen as an error response to the next command by the client.

 However smart clients that are able to deal with incoming asynchronous notifications from the server can notice that early and recover from a server restart without causing a delay visible to the user. 

Requests and responses are terminated by a newline outside of a string literal or a parenthesized list.

Requests can be pipelined. Unless the application semantics demand it a request submitter does not have to wait to receive a reply before submitting the next request. Nevertheless replies do arrive in the order of requests to break up requests with large responses use paging.

Requests can span message boundaries of the underlying transport system. A request or reply can be larger than what one write call to a TCP connection can dispose of without blocking.

Any request can result in an error on a couple of different levels. The request may have been syntactically incorrect the user may have exceeded their allowance in storage time or space the repository may be shutting down etc.

Errors are sent to the client in two parts a machine readable code and a more detailed human readable error message filling in details of the code.

Certain parameters can be set on any request. They re specified as an optional space separated list after the request s verb.

Certain parameters can be set on any reply. They re specified as an optional comma separated list after the reply s data.

The data returned by the list request is a list of lists and scalars. The meaning of the list elements depends on the result clause in the template request see cvs graph doc gr template.txt section 14.1.

The write request is similar to the read request with certain restrictions and changes to the template.

When writing valuetypes and datatypes are completely synonymous. Datatype is the old symbolic notation valuetype is the new numeric notation. 

Both accept small integers in the range 1 . . . 255 and the symbolic datatype names null 1 string 2 integer 3 float 4 guid 5 timestamp 6 url 7 bytestring 8 Boolean 9 .

If neither a value nor a valuetype is specified the valuetype defaults to null or 1. If a value is specified in an insert request but no valuetype the valuetype defaults to string or 2.

Other than that value types do not influence the behavior of graphd with respect to the values in any way. They are not evaluated when comparing values or matching them. For all practical purposes they are simply a small integer that is stored in the primitive for arbitrary use by the application.

If a GUID constraint is present in a write request the newly written primitive is intended to version that is to implicitly delete and take the place of another primitive.

If the operator is the most recent version of the primitive must be the one with the specified GUID. If the operator is the specified GUID may have been replaced by another primitive in the mean time and that one in turn by others whatever the most recent primitive in this lineage is versioned.

 In other words is pessimistic is opportunistic to race conditions. If someone else has gotten in the meantime and versioned things fails while will just quietly do the right thing. 

If no GUID is specified the system generates a new GUID. The new GUID will not match any other existing GUID when compared with or .

Similar to timestamp constraints but only real timestamps are allowed as literals not the generational operators newest or oldest . The only possible operator is .

Unspecified parts of the timestamp are set to the minimum allowed by the type. I.e. 1 for months and days 0 for hours minutes seconds. 

If there s no stringexpression prefix it defaults to type . In other words person creates a new node of type person. 

If an url string literal is specified the datatype is implicitly forced to url . It is an error to both have a url string literal and a datatype other than url .

Like primitive constraints primitive literals recursively specify groups of links or nodes that are implicitly connected to their containing expression.

The linkage or linkage specifies how the containing and the contained primitive are connected. It can be omitted once if the outer primitive is tagged with or which implies a form of attachment between outer and inner primitive. 

Flag literals concern flags set for the primitive. There are two flags archival and live . Both are true by default.

By default entries are considered archive worthy. By default they re also intended as data additions to the database state not as markers for deleted records.

This is similar to 6.1.6 Primitive Literal but only connects the primitive to an existing other primitive with a given GUID without actually creating that primitive.

It is an error to specify a left source guid for a link that encloses a primitive or a link that is not at the outermost level. It is an error to specify a right destination guid for a link that isn t at the toplevel or for a link that contains other primitives.

The uniqueness literal places a restrictions on the write expression that contains it. If the part of a write expression that is tagged with a unique modifier already exists at the time the write request is executed the write request fails.

Note that in spite of similar grammar to the result instruction uniqueness checks are limited to a smaller set of features.

The unique modifier has two effects it turns on the existence testing as a precondition for the write to succeed and it specifies what it means for something to already exist do the type and name have to match Type name and value Just the value 

The normal use of unique is in the construction of namespaces. Each namespace has a well known headnode.

Unique labels are implemented as links between the named object and the namespace headnode. When inserting the links they are inserted with a unique qualifier that includes the namespace and the value expressing that the value has to be unique within the namespace.

contains a single unique cluster made up of the nodes tagged Pat and Kim. Pat and Kim both have unique tags and the link between them is part of Pat s unique set.

I get two clusters. Pat and Kim must both be unique but their connection Pat s right isn t part of Pat s unique set.

the write in example 6.1.9.2.1 succeeds but the one in 6.1.9.2.2 fails. The first write was matching a complete cluster of Pat Kim the second write was matching Pat and Kim individually and would then have connected the results.

Key literals used only in write requests help roll a familiar sequence of operations into one a read to see if something is already there a versioning of the old or insertion of a new value with a unique modifier and a final read to get the new GUIDs of the destination.

The key literal designates those parts of a template that identify a location in the graph an Ivalue the remainder of the template describes the state that the caller wants that location to have with the understanding that insertion versioning and partial addition can be used to bring about that state.

If there s no primitive that matches the key constraint the write call inserts the primitive just as a write call without key constraint would.

If the primitive exists with all the values just as described in the write call the call returns the GUID of the existing primitive.

Finally if the key fields match but some of the rest don t the write call makes the minimal set of versioning changes and additions needed to bring about the desired state and returns the set of GUIDs from the finished mix of old versioned and new.

Key primitives cluster just like unique primitives. Each cluster contains the largest possible connected group of primitives that each have keys and are connected with links that are covered by keys. If a read query built from the cluster parts matches the cluster matches and will either version or just reuse the primitive network. Each member of the key cluster versions its own corresponding member of the matched set if needed. 

If a keyed primitive points to an unkeyed primitive and that unkeyed primitive and those it points to already exist in the requested form in the database the unkeyed primitive is not created over again if the pointing keyed primitive exists.

Because keys already imply versioning of a previous match keys cannot occur in graphd constraints that also contain GUID literals.

The comparator literal influences the way unique or key comparators compare values while checking for existence of a value. Its syntax is exactly the same as the comparator constraint syntax.

A cancel request is an announcement from the client that it will not parse i.e. throw away skip the results.

It gives a server that is in the middle of calculating a reply leeway to stop calculating it and just send a perfunctory ok or error response and a server that is in the middle of formatting the response to a reply leeway to stop formatting it close the string it is currently formatting if any and terminate the reply with a single newline. The reply does not have to be syntactically correct or a complete list.

When a client connects to the server there s a brief handshake period in which they both agree on their respective identities transport layer protection and protocol versions.

A status request asks various modules in the graphd interior for information about their status and operation. This is intended as a testing and monitoring tool the operations should be fast enough to not significantly affect server speed or functioning.

The connection reply is a parenthesized list of per connection data one for each connection or session to the server.

The database reply is a parenthesized list of name value pairs. For their meaning consult the gstatus.1 manual page.

The memory reply is just a list of strings the strings are produced by the memory trace module of graphd if graphd is started with the t option. Otherwise the memory reply is null.

The strings internally have a form dictated by the memory trace module cm trace typically something like

Note that if the status reply comes from a session that has a session specific loglevel that loglevel not the server global level will be returned.

A Boolean value indicating whether the server is currently inclined to dump core on programmer error or not.

A Boolean value indicating whether the server is currently guaranteeing that any data has been saved to permanent storage when a command returns.

A string value. The string is a possibly empty series of space separated name value pairs. The names are the same as in the cost request parameter where present they define global limits for any request in the system.

A string value. The string is a the build version of graphd. The detailed syntax depends on the build system currently it is gd trunk graph src 8439 8454M that is the significant parts of the svn URL followed by the svnversion output for the graphd build root.

Any empty peer address string indicates that the corresponding connection does not exist. An empty address url string indicates that the corresponding address has not been configured.

A dump request saves contents from the local database in a textual form fit for use with a later restore command.

If a restore request starts at startstate of zero the existing database state in the server is destroyed prior to the restore. If a restore request doesn t start at zero its startstate must be less than or equal to the highest endstate of the server into which the data is being restored. If the start state is less the highest endstate server s horizon then the restored values will be compared to what is in the database and the restore will fail if they are different. This allows one to retry a failed incremental restore.

 In this context zero is the first startstate returned by a dump command it doesn t matter how it is encoded. 

Setting the access of a server causes requests that don t fit in with the access model to be rejected.

When setting a loglevel the command accepts either a single loglevel or a parenthesized list of loglevels. The server loglevel is set to the union of all the listed loglevels.

Mixed in with the loglevels can be at most one session displayname as listed e.g. in the response to status conn .

If there is a session displayname present the debuglevel set is not that of the global server system but only of that session. In other words while that session serves its requests the loglevel is temporarily set to the level indicated.

To remove the special session loglevel run a set loglevel command with only a session level no specific loglevel.

The sync option is a server wide value that controls whether an ok response from the server immediately followed by a server shutdown or crash still guarantees that the data can be recovered from disk.

A replica request starts the replication protocol. The request is sent by the replication client a replica database to the the replication server the master database .

Each replica write command contains the primitives written by one or more write commands. The first primitive in the dump tuples will always have the TXSTART bit set.

The client sends the server the highest protocol version it is capable of understanding. The server responds with the protocol version it will use or an error if it determines that it cannot talk with the client.

Either side of the replication protocol may drop the connection at any time. If the replication connection is dropped the client is expected to try to re establish it at sensible intervals.

Replica databases use the master url returned in the replica response to forward write requests on to the master graphd. If the connection between a replica and the master graphd fails the replica is expected to drop the replication connection and re establish it with the check master option.

When coupled with the replica sync access mode the sync command produces a stable disk database that can be easily copied to a backup store.

If multiple sync commands are issued simultaneously they will be executed serially each possibly returning a different horizon.

When sending tuples back and forth they are encoded as a space separated parenthesized list of values.

Which value goes where in the tuple is determined by the application in the request and outside of the scope of this document.

The following character is quoted in all strings sent by graphd. It can be quoted or written literally in strings sent to graphd 

 In other words graphd output does not contain literal n within strings but they re acceptable on input. 

The primitive s name as a quoted string or the word null as an atom to indicate that the primitive had no name.

In some older notations a primitive type is rendered as a string. In modern notations it is rendered as a GUID.

The name of the primitive s type as a quoted string or the word null as an atom to indicate that the primitive had no type.

The GUID of the primitive s type or the word null without quotes to indicate that the primitive has no single type.

The guid of the left hand node of a link or the word null without quotes if the link has no left hand node or if we re not talking about a link.

The atom true or false without the quotes depending on whether this primitive has the live flag set or not.

The atom true or false without the quotes depending on whether this primitive has the archival flag set or not.

On output the timestamp is rendered with 16 bits of sub second precision. On input shorter timestamps are accepted.

The 128 bit GUID of a primitive s scope rendered as a 32 byte hex string or the word null without quotes to indicate that the primitive has no scope.

A small integer in the range 1 . . . 255. If unspecified the valuetype assigned to primitives with a value is 2 without a value 1.

Valuetype and datatype see 2.4 are the same underlying value. When accessed as a datatype integers in range 1 . . . 9 are printed as the name of their corresponding datatype datatypes outside that range are printed as numbers. When accessed as a valuetype all values print as numbers.

This grammar is part of interface requests that match networks of links and nodes in some manner. They re used with the read command to access primitives a variation is used with the write command to create new primitives.

Reading this document will give you an idea of the expressive power of the graph repository interface.

Most of the constraints define what primitives match the query some are more properly thought of as instructions that detail what information is passed back once the query matches or how that information is sorted and formatted.

When a query executes each parenthesized nesting level of templates evaluates to a list of primitive components GUID name value and so on that matched the query.

If a constraint holds subconstraints the subconstraints too evaluate to nested lists of the primitives that matched that particular subconstraint. To read more about that see section 8 primitive constraints.

Multiple constraints combine disjunctively the combination matches primitives that match all of the subconstraints.

A valuetype constraint restricts by the valuetype a small integer in the range 1 . . . 255 that nominally refers to the data type of the value string but actually has almost no semantics inside graphd.

For read accesses valuetype and datatype accept the same strings one of nine symbols or a small number. If you re writing new code use the numbers and use your own dictionary.

Null is 1 string is 2. There are names assigned to the rest but they don t influence graphd s behavior in any way and I hope for us to be phasing them out.

In the overwhelming majority of cases the caller knows which primitive they would like to access and simply supplies the primitive s id as a hex byte string.

In the case the caller is looking for something that is has the same underlying identity as the specified GUID. Without further flags on the query that amounts to the newest version of the object by specifying newest 0 and live dontcare the query can be broadened to include old versions and tombstones respectively.

By default queries only return the newest existing version of an object in the repository. Therefore this search will find either the newest version of the object that shares application defined identity with 1234567890abcdef1234567890abcdef or fail because the object has been deleted.

If the returned node has the same guid as the query the version the application knows about is current.

If the returned node is different a comparison against its timestamp will determine whether the application s or the store s version is the more recently created node.

A virtual time constraint is a particular form of timestamp that matches primitives created before virtual time a certain virtual time as returned with the virtual time request modifier.

Omitted timestamp parts default to the minimum value possible 0 for minutes seconds and hours 1 for months and days. 

The virtual time can be specified as a string or a GUID. A virtual time that is a GUID is the time just after the creation of the specified GUID.

The generation of the primitive starting with 0 at the end point implied by the keyword newest oldest is compared to the specified number according to the operator starting with 0.

By default queries have a generational constraint of newest 0 . An explicit newest or oldest overrides that default.

There is no guarantee that the results of a generational query is consistent over different access points.

Strings are compared as US case insensitive UTF 8 strings. That is A and a are considered the same character but the match algorithm makes no attempts to normalize characters outside the US ascii set. 

The type of a primitive is the unique label is either null or the string value of the link connecting the primitive s typeguid to the global type name space primitive a node with name metaweb global type namespace .

A value is equal to a string if it compares equal to it using the comparator by default a case insensitive comparison for US ascii bytewise comparison for everything else. 

The globbing semantics implemented by the default comparator are described in detail in gr simple search.txt. Briefly foo searches for the word foo anywhere in the text anchoring if needed uses to mean beginning and to mean end. An at the end of a word means starting with so foo finds all words starting with foo.. and if used alone means any word but just one word not two . Adjacent words in the query match adjacent words in the document whitespace and punctuation are ignored other than to delimit words with punctuation in the query meaning an optional word boundary .

A comparator constraint can be specified to change the way strings are compared both for a value comparison and for sorting see 7.3 for details.

These queries are going to be less frequent than string queries but will occur in the same context of using the graph repository like a database.

The identity and matching constraints are controlled by a value comparator the sorting constraints are controlled by a sort comparator.

The sort comparator is a list each Nth element of the sort comparator list controls the matching for the Nth sort key. The last element of the list is used for all following keys.

Operationally comparators have names and one changes the default by mentioning the name of the desired comparator

Comparators can be changed per access and do not affect the way primitives are stored in the database.

Internally comparator names have two parts an optional locale specifier separated by a and the comparator s locale independent name. The locale independent names are matched exactly the locale prefixes in a query can be more specific than the ones they match.

For example an en UK casemap comparator requested by a user may match an en casemap comparator installed in the system.

The octet comparator no locale prefix simply compares strings octet by octet. No case mapping and no number parsing takes place. A string compares lexically greater than another if the octet value of the first byte the two strings disagree on is greater than the corresponding octet in the second string.

This does not mean that the strings are octet strings all strings that pass through the graphd interface must have UTF 8 encoding.

The octet comparator is useful for strings that are not human readable e.g. base 64 encoded byte strings.

The default comparator which need not be set explicitly but could be called default if it were performs two services 

Primitive constraints match against a list of primitives specified either as GUIDs or as recursive template expressions.

The primitives matching the contained expression are connected to those matching the container. The linkage describes how the two are connected.

Either the subconstraint matches primitives that point to the outside in one of their four connecting fields 

Flag constraints regulate flags set for the primitive right now there are two live and archival . In addition there is a monadic constraint false that causes the read constraint it appears in not to match.

Records with the live flag set to false are markers that indicate the deletion of a previously existing record. By default they are not returned in query replies.

If the live flag is set to dontcare the query response will include primitives that are deletion markers. If it is set to false only deletion markers will match the record. If it is set to true the default only live non deleted primitives match the query.

A true mirror of a database needs to listen to deletions that is additions of primitives with the live flag set to 0 as well as additions. So the revised first example for a real mirror should be

 Note that the mirror owners can make a separate choice to mirror old versions perhaps further constrained by their number or time range. 

The archival true modifier matches only primitives with the archival bit set i.e. ones considered valuable because they were entered by a user . Its negative matches only primitives that do not have the archival bit set. By default the archival bit does not affect whether a query matches archival dontcare .

Records with the archival flag set to true are primary sources of the information they carry. Records with the flag set to false are deemed ephemeral and can either be regenerated or are just generally not considered important.

If a count constraint has been specified the containing template expression only matches if its total match count is depending on numop less than the given number.

The form atleast number is equivalent to count number . Use count atleast was an early attempt to implement something less powerful than count. 

Note that a constraint that contains count 0 only matches if the rest of its subconstraints don t match anything that s a way of implementing not .

The overwhelming use of the atleast constraint will be in specifying networks that participate in the match results if they re present but aren t required to match.

Note that atleast constraints other than atleast 0 really don t make much sense on nodes there can be more than one link affixed to a node but there s only at most one node at either end of a link.

When writing the next constraint is always null. One cannot write a primitive that is outdated at its time of creation.

When writing the previous constraint behaves exactly like the GUID constraint. If a single GUID is specified with the GUID must be the current version of its lineage at time of writing. If a GUID is specified with the current version of that lineage is versioned. It is an error to specify more than one previous GUID when writing.

When reading with a next constraint and no newest generational constraint an implicit newest 0 is assumed. Without that no constraint with a next pointer is ever visible. 

When reading with a previous constraint no such assumptions are made. Without an added newest 0 the successor of the GUID specified with a previous will only be returned if it is the current version.

Other than its own ID there are four GUIDs embedded in each primitive. Collectively they re known as the primitive s linkage or linkage fields . They can be tested for identity identity to null set membership and for cross version identity.

If they are specified as strings nonexistent types are implicitly created on write queries and the types are implicitly translated from the string form into the GUID form mostly to make a transition possible from the old style name based system to the new style GUID based system. 

They don t affect what matches just what happens to it. Nevertheless they can be used for optimizations while the match is going on. 

Abstractly speaking each parenthesized template expression a constraint results in a list of matches. Often that list only has one element it can have zero elements if a match used the atleast modifier. Each match in that list is one instance of a sub graph that matches the template.

The result instruction controls how that list of matches is mapped to the tuple returned by a READ request. Result instructions are not allowed in any other kind of request. 

The outer list or an outer scalar is returned once per matching list. The inner list is repeated once for each matching list element.

If an element item like value or type appears in the outermost list it is assigned a value from some matching subgraph.

If an element item like value or type appears as a scalar there are no lists the system will similarly select one of the matching subgraphs as a source for returned value.

This is useful because frequently subgraphs are by definition limited to only one match whenever a simple link is being followed for instance.

For each result instruction item the corresponding result response item is rendered in order of appearance in the result instruction as described below.

The following sections will pair some x instruction item with some x response item. In the result list of a read request the x response item appears in the response in a position corresponding to that of the x instruction item in the read request.

These generally yield straightforward renderings of the corresponding primitive data as described in gr tuple.txt.

Whether or is used when displaying a meta literal depends on the relationship of the link to the surrounding expression. If there is neither a surrounding expression nor a directional meta constraint in the search query links default to .

In the reply the token contents is replaced with a comma separated list of the results for dependent links or nodes that were matched by the query.

Each element of the contents response item is the result for one potential query satisfying subgraph sorted and paged if specified according to the sorting and paging criteria in the subgraph.

A link or node is part of the content result set if it returns a result. If it doesn t return a result if its instructions include result null the content still exist but remain empty.

In the reply the token count is replaced with the number of matching records that would be returned if records would be returned.

The token estimate count is replaced with an internal iterator estimate of the number of available records. This estimate will usually exceed the actual count.

If the query specifies a countlimit or pagesize the count will not exceed the countlimit or pagesize.

Note that the result parameters value and count operate on two different levels the count affects the result list as a whole just like sort and page do while other result parameters determine individual repeated elements of the list.

If the query instructions see section 13.4 specify a pagination mechanism or if the query is paginated because of a timeout the cursor result instruction marks a place for an opaque string literal returned as part of the query response.

This cursor string can be submitted by the application in a pagination instruction see below as an aid to the graph store to efficiently regain its place in a sorted paged query.

A special cursor value of null as a quoted string indicates that the cursor is at the end of the iteration and that the next call will return either an EMPTY error or an empty list depending on the count constraints of the query. If conversely the returned cursor does not match the string null then there is at least one more value pending in the enumeration.

 This is a special string and not the atomic value null because that value is a legitimate value for starting a query we didn t want clients that are unaware of the special case to run in an endless loop when re inserting the cursor result. 

If the template matches include an application defined tag in the results. This allows an application to preserve details about exactly how and where something was matched in a transparent manner without having to parse structures of the complexity of its own search query.

Queries can assign results to a named tag. See tag instruction below. Queries can then reference the tag s contents and include them in their results in a controlled fashion.

When a query returns a tag either it or a subquery must assign to the tag. When a query assigns to a tag either it or a parent query must use the tag.

When the use and the assignment happen in the same query the tag works like macro substitution it s just a shorthand for something that could have been expressed directly.

Tag references are important for the efficient translation of graph structure into relational table structures.

An iterator result is an internal mechanism for analyzing the query optimizer. It allows the query sender to see which internal mechanism the server picked to answer the query.

Unlike the cursor string the iterator string doesn t have a use as a client specified argument to graphd it is intended just as documentation of optimizer choices not as guidance.

In other words everything there is to know about a node or link is listed. If there are subconstraints that includes the contents of the subconstraints. Links have their meta type listed explicitly as or nodes don t.

Several aspects of these defaults are by now anachronistic the string type the artificial distinction between nodes and links . Don t use defaults specify what you want instead.

The tagged values can be used by containing result and sort instructions to reach into their sub expressions.

If multiple contained expression of the tag using expression match and set the same tag it is unspecified which of the values gets used.

This is legal but if a user both has a nickname and a first name the application cannot rely on either of these having precedence it is much better off receiving both names in separate tuple elements and just throwing one away.

The sort instructions determine how the items that match the containing template expression are ordered within their list.

Null sorts before present GUIDs. This doesn t matter for the guid criterion that GUID is never null but does matter for left right and scope. 

Note that the sort instruction is in the surrounding context of the thing that is being sorted on the topmost level it is outside of the parentheses.

Pagination instructions ask for a cursor to be returned if not all items could be transmitted specify a previous cursor if any and specify how many matching primitives to return.

Note that these instructions can be given at any level of the hierarchy not just at the toplevel. From a data perspective paging at each level of a tree makes sense from a user perspective it can be confusing. The application will have to solve that. 

The start parameter is optional it defaults to 0. It specifies a zero based count into the list of matching primitives at the cursor s level of hierarchy.

The countlimit is the number up to which the caller wants graphd to report an accurate count. Even if the true count of matching primitives is greater than the countlimit the countlimit is returned.

The resultpagesize is the number of results to return. Unlike the countlimit it interacts with the start parameter the last returned result is result number start resultpagesize 1. But the highest count returned is always countlimit regardless of the start parameter. 

If there is no resultpagesize the system assumes 1024. If the resultpagesize is greater than 64 1024 it is truncated to 64 1024 use a cursor instead . Note that no such truncation happens for the count this constraint has to do with result size not about runtime.

A pagesize parameter if present sets the resultpagesize to its value and the countlimit to start default 0 plus its value. Use of pagesize is deprecated use resultpagesize or countlimit instead.

If the cursor parameter is present its string was returned by a previous paginating query. The string is an efficient encoding of where the previous instance of this same query left off.

A cursor is only valid for the exact query it was generated for. It s an error to use it with a different query.

It is possible to resume at a specified offset rather than at a previously returned cursor position but it s faster to use a cursor.

A constraint with an or constraint matches if the first or second side of the or match. If the or is the first part takes preference if the or is the preference is unspecified.

Subconstraints in an or occupy slots in the contents result set even if their branch is unused if they do not match their result slot is null. To avoid this use variables rather than the built in contents . 

Or constraints always match per individual primitive not per complete set. It is a syntax error to use set level constraints in an or .

This document describes the search expression language for the graph repository s string operator during read queries.

This number match kicks in only if the pattern and the text both have or could match the format of a number. Numbers for our purposes are written as an optional sign followed by digits followed optionally by a decimal point and more digits if there are digits after the decimal point there need not be digits in front of the decimal sign.

If the normalized form of the text doesn t match the match is retried on the unnormalized form. In other words if you write a strange pattern you only match strange numbers but a normal pattern matches both normal numbers and strange ones.

So 7 matches 7 007 7.000 but not 7.00000000001 . Note that the text 7 would match 7.00000007 since it contains 7 as a subword just like it would match 1000.7 . 

The normalization takes place only temporarily at the time of comparison the data actually stored in the database and retrieved as the resuly is unaffected.

Backquoting the search pattern turns off normalization in the corresponding part of the source 7 matches only the literal string 7 not 007. It will match 7.0 because 7.0 contains 7 but 7 will match 7 but not 7.0 . 

Asterisks in valid number expressions match any sequence of zero or more digits and an optional leading sign. If the asterisk is used alone it also matches an optional punctuation mark matches 3.14 even though 4 does not. In a number expression only the sequence . matches an optional floating point punctuation mark followed by zero or more digits so 3.0 003.1 and 3 all match 3. .

We re executing queries that have lots of strings in them. The Uncopying server is written in such a way to almost never copy the data in those strings. This makes things fast because it doesn t shuffle information about quite as much it uses less memory and it uses memory mostly in more efficient fixed block sizes rather than allocating many small objects.

This documents details a server design I ve thought about for a while but am using in graphd for the first time.

Data arrives at an interface and is read into buffer pages. That s the only copy that happens to the request data.

The buffer pages each have a link count associated with them. Two things count for a buffer link count being in the input queue and being in a request.

More than one request can refer to the same buffer page. Buffer pages are linked in a singly linked list. Requests have a pointer to their first and last buffer page.

The sequence of buffers on input is the same as the sequence of requests that s why one next pointer per buffer suffices as long as the input queue and the requests remember where their individual end pointers are.

Note that a request can point to one buffer only request 1 or span more than two buffers request 2 . Note also that requests frequently share a buffer with the input queue or with other requests the buffers are so large that they often hold multiple requests.

As requests execute they keep a link to the input buffers that they were parsed from. A whole buffer is only free ed read recycled in a buffer free list when all the requests that refer to it have been answered.

Because it can rely on the data to stay in place during the whole lifetime of a request the Uncopying Tokenizer doesn t need to copy token data into separate memory areas. Instead it works with start and end pointers to the strings in their incoming buffer.

Generally pointers to the beginning of a 0 terminated string or the self contained String objects higher level programming languages offer are a terrible idea when tokenizing text. They look elegant because one gets to move information about through a small single pointer interface but modifying or copying the underlying data just to delimit it is neither a good use of modification nor a good representation of size information.

I tend to use s . . . e pointers instead s the beginning of the string e pointer just after the end of the string s n notation would probably work just as well just stick with one.

In the tokenizer of the Uncopying Server the s . . . e pointers into an existing buffer break down in two places 

Those tokens are assembled in traditional malloc d buffers and then hooked into the parser mechanic with the existing start and end pointers.

Each request has its own memory heap that such buffers can be allocated in they re free d automatically when the request is free d. That means that after the initial buffer stage these assembled strings can be treated exactly as if they lived in one of the buffers. They re a little less efficient but they don t complicate the back end logic.

A concentric replica is a graph database which contains another graph database. Our current sandbox graph is a close approximation it contains OTG as of some time. Unfortunately the copy of OTG in sandbox is static the only way to get writes from OTG to sandbox is to create a new sandbox but that loses the modifications made to the sandbox.

A concentric replica could be used to store any relatively long lived data which relates to OTG but should not be in OTG. Example applications 

Although a the trivial example of a federated database a concentric replica doesn t provide any relief from the scalability limits of graphd. The concentric replica contains all of OTG and requires an additional property for some portion of OTG.

We assume that C starts life as a replica of O with a different database id. Call the last primitive in this replica C.branch.

We do this with a special property equivalent to. The following algorithm will map from an identity in C say C.y to the equivalent identity in O if there is one 

Yes this burns one extra primitive per identity. It might be reasonable to use the name field for this purpose as such usage would not conflict with the graphd or MQL bootstrap.

C is kept up to date with respect to changes in O by a small program which pretends to be a replica of O. For each transaction in the replica stream delimited by the TX START bit in a primitive record the program produces an equivalent set of writes and applies them to C. New identities nodes are simply created with the mapping back to O . Fundamentally links are created by value that is a link is created if an equivalent link doesn t already exist ie. we use key when writing . If a link versions another link we need to version the equivalent link in C. If the versioned primitive O.x is old ie. C.x

If the versioned primitive is new then we look up the predecessor and using the contents of the predecessor look up the equivalent primitive in C and version that. This has the desirable effect of making writes to OTG take precedence over writes to the concentric store.

Handling links that way is fine from a graph standpoint however links are the implementation of MQL properties so we need to do a bit more work to make sure that MQL property semantics are preserved. Specifically 

Relational databases such as Postgres or Oracle require that a database schema exist prior to data entry and require manual optimization via CREATE INDEX for best performance. We describe the query optimization techniques used by graphd a schema last automatically indexed tuple store which supports freebase.com a world writable database. We demonstrate that the techniques described deliver performance that is generally comparable with traditional cost based optimization techniques applied to the relational model.

Our tuple store graphd manages an append only collection of tuples. Tuples are assigned sequential ids as they are written. The first tuple is 0 the second 1 and so forth. Fundamentally tuples carry two sorts of data immediate scalars strings and references by id to other tuples.

Our database consists of tuples having some statically defined mixture of reference and scalar fields. In our specific case this happens to be 4 references named left right type and creator and several scalar fields the most important of which are known as name and value As you might surmise left and right are used to link things together the type categorizes such a link and creator identifies the user creating the tuple. Of the scalar fields value is the most common and is used to store all user written values. The name field is used to locate primitives.

By convention these tuples are employed in a stylized manner. Nodes have only a creator and serve as identities only and Links have some combination of left right type value and name and are used to describe the identities they reference. The result may be viewed as an object oriented system in which objects are nodes and properties are links or as a relational system in which relations are collections of links usually those having a type in common. While understanding the convention eases comprehension of what the optimizer is actually doing the optimizer is entirely independent of these structural conventions.

A complete description of the query language is beyond the scope of this paper. For the most part we will concern our selves with the following query which asks for parents of people named Bob 

For ease of reading we will replace literal tuple ids with symbolic names in the remainder of the paper 

which returns every primitive in the database. Interesting queries constrain primitives in various ways. Intrinsic constraints such as value bob constrain the content of the set primitives. Linkage constraints for example left specify a relationship between primitives. So the following constraint specifies a primitive which is referred to by the left of a primitive whose value field is bob whose type is name 1 and whose right is en 2 

The basic join algorithm used by graphd is the nested loop join. Working through the syntax tree from the top down we try candidate primitives one at a time. Without optimization the set of candidates is identical to all primitives in the database. Query execution becomes intractable quite rapidly as query complexity or database size increases.

In contrast to conventional query optimizers which search for the optimal join order and employ a variety of join techniques the graphd optimizer does not manipulate the join order or technique rather it seeks to minimize the size of the set of candidate primitives considered by the nested loop join.

Thus far moving computation from the domain of values into the domain of index sets has been hugely profitable.

Fundamentally the graphd index exploits the append only nature of the database and the sequential nature of tuple ids guids . As tuples are appended to the database we can accumulate sorted sets of ids at very modest expense. We are fortunate in that sorted sets are well studied.

While some such sets are naturally exact even approximations are fine as long as the reduce the size of the result set sufficiently. Invalid candidates returned by the optimizer will be weeded out by the nested loop evaluator. As a practical matter we typically spend about 90 of our execution time in the optimizer.

Each constraint maps pretty much directly to a set which accumulates naturally in sorted order as primitives are written. For example writing such a link might look like this 

Conceptually the index is a large dictionary whose keys are type value pairs for example VALUE bob or LEFT 5 and whose values are sorted sets of integers for example 23 145 167 169. We ll use the functional notation I to describe any individual set in the index. The intersection 

Concretely the implementation of the index dictionary is a large hash table tuned to deliver near constant time access to any set or in the case of some of the less sparse domains such as linkage a segmented array of sets indexed by id.

The size of index sets is useful in its own right. The sum of left and right linkages to a node is a good indication of that node s importance relative to others.

Just as with a full text index names and values can be broken into words and indexed by word. The set

Corresponds to the relatively small set of primitives containing the words bob and williams . In practice relying on the evaluator to check the results for bob williams seems to deliver adequate performance for phrase matching.

Since some sets grow quite large for example I RIGHT en the set of all things referring to English and set storage is compact it is worthwhile to precompute some common intersections at index time. We set a threshold value currently 100 and any set which grows larger than that is eligible for VIP treatment. Since names are quite common I TYPE name is larger than 100 and thus every english name that is added to the system will also be added to VIP TYPE RIGHT name en 

The VIP indexes provided a surprising increase in performance. The basic intuition is that if you have a large collection of something it is probably important hence the subject of many queries hence worth extra indexing expense at write time. While we don t currently do so it seems reasonable to extend the VIP indexing concept at least one more level to keep track of instances of people in addition to links defining instances of people. Maintaining the set of instance of people requires a primitive set representation which supports insertion as identities can be added to that set in any order.

Names are unique in the sense that an object has only one name one link with type name. This property isn t enforced by graphd but by the MQL language object model used to interact with the graph. However uniqueness can be discovered by noting that the cardinality of

Uniqueness is just a special case of the more general problem of estimating the cardinality of a join result. By collecting statistics for VIP set cardinalities other than 1 we can make better estimates for the size of a join result along across a given relation.

While traditional index structures naturally present keys in sorted order at the expense of N log N access time our structures are all sorted by guid with near constant access time. This is a fabulous bargain until the user asks for output sorted by something other than guid. With no index support we have no choice but to scan the complete result set. This is fine with relatively small result sets but intractable with large sets.

Unlike the data they index which may be spread arbitrarily around the primitive store index sets have extremely good locality of reference. And they correspond closely to the semantic sets that the user believes himself to be manipulating. For example the set of all links defining instances of people is a contiguous data structure available to the optimizer in near constant time. Even the simplest set data structure an array is compact and algorithmically amenable to current processor cache architectures. From this structure we can easily locate the set of identities which are people and that set corresponds directly to the user s idea of data. Furthermore combining this set with other sets has uniform and predictable performance characteristics. Unlike standard relational structures there s none of the structural liability which allows seemingly innocent schema or query modifications to have dire performance consequences.

The most common form of relational index is some sort of tree structure which naturally accesses keys in sorted order. This is very handy for things like string prefix queries as all prefix matches will follow the first match sequentially. Using compound keys for example type right left type left right etc. extends this prefix matching game to tuples.

Unless you index all permutations of tuple fields queries involving un indexed joins will be considerably slower. Of course tuple size is a matter of considerable flexibility. Arguably pairs are all that is needed but practical systems seem to start with triples and most add at least one additional field. The trade off is basically a large number of simple primitives and more complex conventions for their use against a smaller number of more complex primitives and simpler conventions for their use.

Note the schema difficulty show me everything about X requires that you first discover the schema what is knowable then ask the question.

This is all very nifty but real queries typically involve joining different constraints together and thus far we have only demonstrated how to find individual primitives.

It is easy enough to compute sets for the name and type constraints but what do we do for the identity which connects them Identities have no left or right fields a fact that we could index but that still would leave us with millions of candidates for every identity.

Conversely the name bob is quite unique In fact there are only 97 instances of the value bob in our current graph of nearly 200M primitives and this information is available to us in constant time . What is needed is a way to propagate small sets derived from elementary constraints up or down to the otherwise unconstrained identities which join them. To our basic vocabulary of sets we introduce linkage functions like so 

LF.left is the set of the lefts of primitives in the input set. To compute this set we use the memory mapped primitive store itself essentially an array of offsets to primitive structures. As with the index dictionary access to the primitive store is constant time.

While a bitmap based pigeonhole sort provides a constant time upper bound on the expense of sorting the constant is large. Unless we actually need to scan the entire set it is more efficient to cope with the unsorted nature of the results.

If we consider a set of links to be a relation linkage constraints implement only half of it. We need a way to move from a set of identities Ci to the set of links which link to them. This is the set union 

We ll introduce the linkage to function LT.right Ci to express this as a shorthand. For our specific example candidates for people named bob are given by the following intersection 

We start iterating through constraints of the top level set and sub constraint iterators are always anded with those candidates

Looking at the constraints thus far there s an odd Asymmetry which reveals itself if we were to re dangle it with the person named bob at the root 

We know that the id of any link must be greater than the ids of everything it references. The id of a primitive whose type field references 1001 

Primitive index sets Intersection Union Linkage from and Linkage to this basic vocabulary is sufficient to describe the sets of interest to the optimizer. Unfortunately describing the sets is actually the easy part. If we try and compute these sets we discover three unpleasant facts 

2. Even assuming that we resolve 1 perfectly hard computing complete sets when only a fraction is needed is prohibitively expensive. Quite frequently we need only a tiny fraction of the complete answer. Algorithms which are adept at producing a fraction of a result set rapidly are often suboptimal when computing the complete result set.

We structure the computation of sets with an iterator abstraction. For any set we construct a hierarchy of iterators which is capable of producing members of the set or checking for membership in an interruptible manner. Sets may be sorted by id sorted by some other criterion or they may be in arbitrary order. Sets can be iterated forwards or from low id or sort criteria to high or backwards.

Graphd evaluates queries top down so the first iterator that we need is the one which provides candidates for the top level primitive in the case of our example we iterate over the following set 

Since we will be iterating through all the candidates by calling next we first ask for statistics to be computed which descends the tree recursively. At the leaves for example I VALUE bob we know exactly how items there are in a set 97 and how much each of the various operations will cost. Computing statistics amounts to propagating those leaf costs towards the root using complexity models for each operation.

Index sets are precomputed sorted sets stored in the index. Physically they are arrays of integers or bitmaps.

There are some 15M name links so many that it is more efficient to represent them as a bitmap which yields costs of next 3 find 3 and check 1. There are some 50M things whose right is english a set which are also stored as a bitmap. For intersections involving sets of known size we always take candidates from the smallest set and check results against the others in increasing order of set size.

The next cost of the intersection is thus the cost of the producing a candidate from I VALUE bob plus the cost of checking that candidate against I TYPE name multiplied by the number of times we have to repeat this process in order to get a candidate plus the cost of checking that candidate against I RIGHT english multiplied by the number of times we have to repeat this process to get a candidate.

We could try to estimate the selectivity of the checkers but as a practical matter it turns out to be simpler and more reliable to produce a small number of values and measure the next cost directly. This technique extends easily to complex intersections where some of the operand sets are produced by other iterators.

We can compute the check cost based on the next cost or based on approximations of checker selectivity the chance that a given checker will accept a candidate.

Lastly the find cost for a simple intersection is the find cost of the producer plus the next cost of the intersection.

At the next level up we re looking for tuples referred to by the lefts of candidates from our simple intersection 

Here the primary variables are the fan in the cardinality of the result relative to the cardinality of the argument and the cost of duplicate checking.

In addition to looking up the left of each member of the input set the links from iterator must ensure that its output is a set duplicates must be removed. There are two ways of doing this 

2. Given X LF.leftC for each argument result pair Ci Xi verify that the first result of ILEFT Xi X C is in fact Ci.

In some cases we may be able to determine that no duplicate checking is required. This situation occurs when the type is used to represent a unique property such as name and we only interested in results at a single point in time usually the present.

Unlike sets iterators incorporate a as much knowledge of their environment as possible. So for example while LF.right Ci describes a pure set the corresponding iterator might know that from Ci it generates a series of sorted sets and thus that 

While the idea of intersection is so basic that this paper doesn t even dignify it with an explanation the actual implementation of intersection is the most complex in the iterator system.

A poison query is any of query that reliably causes graphd to crash. As it stands a poison query if retried sufficiently by either our own middle tier or a user program can crash all graphds in a particular pod. If the retries are frequent enough graphd gives up restarting itself and our service grinds to a halt.

Short of a complete solution which I ll sketch out there are some things that we can do to make the situation better in the very near term 

1. Have replica graphs restart themselves indefinitely unless they detect database corruption. Currently graphd shuts down after three crashes in quick succession. The rational for this behavior is to avoid data corruption. This is still the right behavior for master or archive graphs but wrong for replicas where the only value of a valid database is the quick restart that it allows.

2. Handle ECONRESET consistently in the middle tier client. When a graph crashes all sockets connected to it will receive an error usually ECONRESET. Unless the client is sure that the currently active query is known to be good fx the bootstrap it should treat a dropped connection as a potential poison query.

A complete solution involves identifying poison queries and creating set of poison queries shared by all instances of graphd. A graph would check each query against the set prior to executing it and fail any matching query with an error.

We can identify poison queries by storing a hash of the currently executing query into the shared memory that we currently when configured with transactional false use to determine that graphd has crashed in a write. When the parent process determines that the child has crashed it can read the hash identifying the query that was running at the time of the crash.

We don t need to distinguish the poisonous from the unlucky. Our most common failure mode involves a long running query which has been interrupted by a write at just the wrong place. Retrying such a query when we re under heavy write load might be so unlucky as to be indistinguishable from poisonous.

The poison server maintains a dictionary which maps hash version to death count date where date is the date of the most recent death. As poison messages arrive the death count date records are adjusted as follows 

Where window is some length of time probably several hours. When an entry s death count exceeds a threshold probably 3 the server broadcasts antidote messages to all connections. New connections receive antidote messages for all poison queries immediately after connecting.

The use of the compound key hash version has the effect of clearing poison queries when client software is updated usually the right thing to do. If need be an operator can connect to the server and by transforming the initial block of antidote messages into poison featuring the new software version re instate antidotes for poison queries against the new software.

When a connection between client and poison server is re established the client should forward all currently active antidotes as poison.

We ve got powerful N core servers running graphd. We can serve theoretically N times as many queries at a time as we currently do if all processors were working in concert.

Well let s make a version that works in the read only case let s fork a bunch of child processes. Since we re in shared memory everybody can read the graph. As forking causes the open file descriptors to be open in the forked copy everybody is listening on the graph port waiting for commands and queries. Whoever gets the connection is unimportant it s whoever gets there first.

Test this by firing a bunch of queries against the graph simultaneously. The multi process case works pretty well however because the test has an endpoint the greatest pipeline of queries that a single process happens to grab becomes the limiting factor in the throughput of the test. ie queries are atomic 

So now we want to do writes. If we limit the ability to go SMP to replicas then we can limit the point of entry for writes. We don t know who will get an incoming write from the outside but we don t care every process can forward an incoming write to the master. We allow one special process to handle the returning replica write stream the leader process.

We fork the given number of processes each one opens one end of a connection back to the leader and adds it to their es loop and drop their forked copy of the replica write stream. The leader picks up all the other ends of the follower connections.

To the followers and waits for an ok from all of them. It does the write as usual perhaps also any that come in the queue at the time and sends an

This is the easier role to code it s the doing usual thing with an extra step signaling the followers 

A command which receives an exclusive ticket so as to clear up the running sessions. When executed it responds with an ok 

At which time the follower attempts to do any number of useful things that do not involve memory. The simplest thing to do is to spin and do nothing but this becomes one of the first places to optimize figure out what we can do in the short time it takes to do a replica write

At which time it makes proper state updates such as getting the new horizon numbers. In this step if need be further instructions can be sent across in a small struct in shared memory basically all followers reflect the write update and proceed to do their reads and signals ok 

