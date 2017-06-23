---

title: Method and apparatus for distributing published messages
abstract: A method for delivering published messages to subscribers comprises: —storing a set of subscriptions (F_top, F_top, F_top) in a routing table (RTO) of a first broker (BRO), —sending a set of messages (e, e, e) from the first broker (BRO) to a second broker (BR) according to at least one subscription (F_top) stored in the routing table (RTO) —receiving a subsequent message (e), —determining a search term (topi) based on a data element of the subsequent message (e), —comparing the search term (topi) with a set of data elements stored in a relation repository (CRR), and —controlling sending of the subsequent message (e) to the second broker (BR) according to a result of said comparison, wherein the set of data elements stored in the relation repository (CRR) comprises data elements of the messages (e, e, e) previously sent to the second broker (BR), and wherein said set of subscriptions (F_top, F_top, F_top) contains at least one subscription (F_top), which specifies a topic (top), which is not contained in the set of data elements stored in the relation repository (CRR).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09413702&OS=09413702&RS=09413702
owner: Nokia Technologies Oy
number: 09413702
owner_city: Espoo
owner_country: FI
publication_date: 20101029
---
This Application is a National Stage Entry of Patent Cooperation Treaty Application number PCT CN2010 078219 which published as WO 2012 055111 the contents of which are herein incorporated by reference.

Within a messaging network messages may be delivered from a publisher to a subscriber via message brokers that provide routing of the published message. The brokers are typically located at communication hubs within the network.

Publishers may send messages having a topic. The messages may be delivered to a set of subscribers who have registered their interest in receiving messages having said topic. Typically the messages may be delivered so that the publishers do not need to know the identity or address of the subscribers.

The subscribers may register with a broker and identify the categories of information they wish receive and this information is stored at the broker. In publish subscribe implementations subscribers specify one or more topic names which represent the information they wish to receive. Publishers assign topic names to messages that they send to the publish subscriber broker. The broker may use a matching engine to compare the topics of received messages with the stored subscription information for a set of registered subscribers. This comparison determines which subscribers the messages should be forwarded to.

An object of the invention is to provide a broker for publish subscribe communications network. An object of the invention is to provide a method for operating a broker of a publish subscribe communications network.

sending a set of messages e e e from the first broker BR to a second broker BR according to at least one subscription F top stored in the routing table RT 

controlling sending of the subsequent message e to the second broker BR according to a result of said comparison 

wherein the set of data elements stored in the relation repository CRR comprises data elements of the messages e e e previously sent to the second broker BR and wherein said set of subscriptions F top F top F top contains at least one subscription F top which specifies a topic top which is not contained in the set of data elements stored in the relation repository CRR .

According to a second aspect of the invention there is provided an apparatus comprising a first broker BR wherein the first broker BR is configured 

to send a set of messages e e e from a first broker BR to a second broker BR according to at least one subscription F top 

to control sending of the subsequent message e to the second broker BR according to a result of said comparison 

wherein the set of data elements stored in the relation repository CRR comprises data elements of the messages e e e previously sent to the second broker BR and said set of subscriptions F top F top F top contains at least one existing subscription F top which specifies a topic top which is not contained in the set of data elements stored in the relation repository CRR .

According to a third aspect of the invention there is provided a computer program which when executed by a data processor is for performing a method comprising 

sending a set of messages e e e from the first broker BR to a second broker BR according to at least one subscription F top stored in the routing table RT 

controlling sending of the subsequent message e to the second broker BR according to a result of said comparison 

wherein the set of data elements stored in the relation repository CRR comprises data elements of the messages e e e previously sent to the second broker BR and wherein said set of subscriptions F top F top F top contains at least one subscription F top which specifies a topic top which is not contained in the set of data elements stored in the relation repository CRR .

According to a fourth aspect of the invention there is provided a computer readable medium storing computer code which when executed by a data processor is for performing a method comprising 

sending a set of messages e e e from the first broker BR to a second broker BR according to at least one subscription F top stored in the routing table RT 

controlling sending of the subsequent message e to the second broker BR according to a result of said comparison 

wherein the set of data elements stored in the relation repository CRR comprises data elements of the messages e e e previously sent to the second broker BR and wherein said set of subscriptions F top F top F top contains at least one subscription F top which specifies a topic top which is not contained in the set of data elements stored in the relation repository CRR .

Thanks to the invention in coming messages which substantially correspond to previously subscribed messages may be forwarded fast and efficiently without a time consuming search in a subscription database.

When a first broker has previously sent several messages to a second neighboring broker the in coming message may be compared with the previously sent messages. For example a first in coming message may contain an image of a flower. If several images of a flower have been previously forwarded to a second broker the first broker may determine that the first in coming message sufficiently matches with the previously sent messages. In this case the in coming message may be rapidly forwarded to the same address as said previous messages i.e. to the second broker.

If a second in coming message does not match with the previously forwarded messages then the second in coming message may be forwarded at a later stage by using a conventional routing table.

Conventionally the messages are processed and distributed according to a routing table which contains the existing subscriptions. A routing table may comprise e.g. millions of subscriptions which should be individually checked. In the worst case an individual message should be matched with each subscription of the routing table.

Searching and matching in the routing table may represent a first level of operation. At the first level messages are delivered according to individual subscriptions. The method and apparatus according to the invention provide a second level of operation in addition to the searching and matching in a subscription database. At the second level of operation priority may be given to delivering those messages which represent a large proportion of all published messages and which also correspond to the most popular topics specified in the existing subscriptions. The second level of operation could be called as a wholesale level of operation whereas the first level of operation could be called as a retail level of operation. Thanks to the invention the available data processing capacity may be allocated in an optimum way taking into account the supply of published messages and the existing demand for messages.

Before having to check through a long list of subscribed topics the broker may fast and efficiently distribute a major fraction of the messages according to a shorter list CRR repository associated with the most popular topics. Subscriptions and publications contribute to the list.

A certain topic may be defined in several subscriptions but the topic is not entered into the CRR repository until at least one message matches with the topic. Thus the matching may be performed in a space partitioned by typical message contents instead of a space partitioned by individual subscriptions. Thanks to the invention a significant fraction of the in coming messages may be processed and distributed according to a classification scheme indexing which is optimized for handling the most typical subscribed messages. This may improve speed of the communications network i.e. to increase the number of different messages delivered per unit time.

Thanks to the invention an in coming message may be forwarded also in cases where the subscription does not exactly match with the in coming message. This may increase the probability for delivering a message successfully also in a situation where the subscription is not accurately defined and where conventional publication subscription matching methods have a low efficiency.

Referring to messages e e e eprovided by publishers PUB PUB PUB may be distributed to subscribers SUB SUB via a communications network NET. The network NET may comprise a plurality of brokers BR BR BR BR. The subscribers SUB SUB may order messages by submitting subscriptions F F to the network NET. A single subscription F may specify one or more topics top top top top . . . . A subscription F top sent by a first subscriber SUB may specify a first topic top and a subscription F top sent by a second subscriber SUB may specify a second topic top. An individual subscriber SUB may have several subscriptions associated with different topics e.g. top top . Two or more different subscribers SUB SUB may subscribe the same topic e.g. top .

The network NET may be e.g. the Internet a Local Area Network LAN or a Wide Area Network WAN . The network NET may comprise e.g. the Internet a Local Area Network LAN and or a Wide Area Network WAN .

A message e e eemay also be called as an event. A topic of a message may be specified by a data element of the message.

For example a subscription F top may be associated with an identifier Fid a topic top and a broker address BR. A subscription Fn topx may be associated with an identifier Fidn a topic topx and a broker address BRi. The identifiers Fid Fid Fid Fid . . . Fidn may be associated with the 1subscription F top the 2subscription F top the 3subscription F top the 4subscription F top and the nsubscription Fn topx .

When a new message earrives at the first broker BR the topic of the message may be compared with topics of the subscriptions stored in the routing table RT. For example a message emay have a topic top a message emay have a topic top and a message emay have a topic top. According to the routing table RT shown in the message emay be forwarded from the first broker BR to the second broker BR and the message emay be forwarded to the third broker BR. In this example the topic top of the message edoes not match with any items of the routing table RT and the message eis not forwarded.

The messages e e e emay be optionally stored in a memory of the first broker BR. The messages e e e emay be deleted from a memory of the first broker BR after forwarding or after it has been determined that there are no existing subscriptions. In particular a message may be deleted from a memory of the broker BR if all subscriptions for a topic of the message have been canceled.

Referring to a message ereceived by the first broker BR may be compared with topics of previously forwarded messages in order to establish whether the message should be sent forward and in order to establish the address of a next broker e.g. BR and or BR where the message should be sent to.

The comparison may be performed by using a relation repository BCN. The repository BCN may comprise a semantic relation repository SRR and a clustering relation repository CRR.

Instead of containing a list of individual subscriptions F F the clustering relation repository CRR may comprise data elements of messages previously received and forwarded. The data elements may be called as topics .

The number of different topics stored in the clustering relation repository CRR may be substantially smaller than the number of subscriptions stored in the routing table RT.

The data elements of the previously forwarded messages may be partitioned into clusters according to various different criterions. The data elements stored in the clustering relation repository CRR may be arranged such that they can be rapidly searched according to relevant search terms. The data elements stored in the clustering relation repository CRR may be arranged as an indexed table. The data elements stored in the clustering relation repository CRR may represent messages previously forwarded to a next broker. The data elements stored in the clustering relation repository CRR may be data elements of messages previously forwarded to a next broker.

Each data element stored in the clustering relation repository CRR may be associated with a broker address. The data elements top top . . . topx stored in the clustering relation repository CRR may be associated with broker addresses e.g. BR BR . . . BRi . The data elements top top . . . topx stored in the clustering relation repository CRR may also be associated with subscription identifiers Fid Fid . . . Fidm. Subscriptions stored in the routing table RT corresponding to data elements stored in the clustering relation repository CRR may be rapidly identified and retrieved by using the subscription identifiers Fid. The topics the associated identifiers and the associated addresses may be stored in the clustering relation repository CRR. For example a topic top stored in the clustering relation repository CRR may be associated with a subscription identifier Fid and a broker address BR. This means that a message having the topic top has been previously forwarded to the broker address BR and that the previously forwarded message corresponds to a subscription specified by the identifier Fid.

The topics the identifiers and the addresses may be stored as nodes in the clustering relation repository CRR. The clustering relation repository CRR may comprise a plurality of nodes wherein an individual node may in turn comprise a topic top an associated identifier Fid and an associated broker address BR. For example a node may comprise a data element top a subscription identifier Fid and a broker address BR. In an embodiment a single node may comprise only one subscription identifier and only one broker address associated with a single topic.

The node may comprise a data element top a subscription identifier Fid and a broker address BR. The node may comprise a data element top a subscription identifier Fid and a broker address BR. The node may comprise a data element topx a subscription identifier Fidm and a broker address BRi.

The routing table RT and the clustering relation repository CRR may be stored in separate memory areas.

However the clustering relation repository CRR may also be an indexed part of the routing table RT. It may be noticed that the routing table RT and the clustering relation repository CRR may comprise similar nodes See . An individual subscription node stored in the routing table RT may comprise a combination of a subscription identifier a topic and a broker address. An individual node of the clustering relation repository CRR may also comprise a combination of a subscription identifier a topic and a broker address. Thus the clustering relation repository CRR may also be an indexed portion of the routing table RT supplemented with pointers and or additional identifiers. Some of the subscriptions of the routing table RT may also belong to the clustering relation repository CRR. Subscriptions of the routing table RT belonging to the clustering relation repository CRR may be rapidly identified and retrieved e.g. by using pointers stored in an auxiliary pointer table.

Referring to the semantic relation repository SRR may contain a location semantic relation repository a time semantic relation repository a tag semantic relation repository and an author semantic relation repository. The semantic relation repository SRR may comprise e.g. semantic trees TREE TREE TREE in order to provide additional search terms See . The author semantic relation repository may comprise one or more personal relation graphs.

The clustering relation repository CRR may comprise a location clustering relation repository a time clustering relation repository a tag clustering relation repository and an author clustering relation repository.

Advantageously the clustering relation repository CRR should not contain data elements which do not match with data elements of previously forwarded messages. The clustering relation repository CRR may contain fewer data elements than the routing table RT in order facilitate fast searching. For example the number of nodes of a clustering relation repository CRR may be smaller than 50 of the number of individual subscriptions in the routing table RT. In particular the number of nodes of a clustering relation repository CRR may be smaller than 10 of the number of individual subscriptions stored in the routing table RT.

Several subscriptions stored in the routing table RT may specify topics which are not contained in the set of data elements stored in the relation repository BCN . At least one subscription e.g. F top stored in the routing table RT may specify a topic e.g. top which is not contained in the set of data elements stored in the clustering relation repository CRR.

For simplicity the notation e may refer to a message and or to a data element topic of a message in the following discussion and in the drawings. In particular the notation emay refer to a message eand or to a data element of the message e. Matching a message e may refer to matching a data element of a message e. Partitioning a message einto a cluster may refer to partitioning a data element of the message einto said cluster .

It is emphasized that the clustering relation repository CRR does not need to store the entire contents of the previously sent messages. For example if the previously forwarded messages contained photographs it is not necessary to store the photographs in the repository BCN. It may be enough if the topics data elements and the associated addresses are stored. The topics and the addresses of the previously forwarded messages may be stored in the clustering relation repository as indexed clusters.

The repository BCN may also be called as a Broker Context Network . In particular the repository BCN may be optimized and indexed for handling image data.

When handling messages associated with different topics priority may be given to delivering those messages which represent a large proportion of all published messages and which also correspond to the most popular topics specified in the existing subscriptions.

As to the topics top top and top it may be noticed that the number of published messages and or the number of subscriptions is low. Consequently handling of messages having the topic top top top may be of secondary importance when forwarding the messages to the predetermined broker e.g. BR . The topics top top top may have a low merit value.

When delivering the messages an individual merit value may be determined for each combination of a topic and a broker address. For example a message may get a priority delivery to a predetermined broker only when the merit value determined for the topic of the message and the address exceeds a certain limit. Messages having a low merit value may be stored in a buffer memory and they may be delivered later according to the routing table RT e.g. when the data processing capacity of the broker BR is not in heavy use.

Referring to the data elements of previously received messages may partitioned into nodes of clusters C C C. . . Caccording to a single property. The single property may be e.g. location time subject or identity of an author.

For example data elements of messages e whose data element topic is within a first distance rfrom a first clustering center Omay form a first cluster C. In other words when a difference or a distance between the data element of a message eand the first clustering center Ois smaller than a predetermined limit r then the data element of a message emay belong to the first cluster C.

Data elements of messages e whose data element topic is within a distance rfrom a second clustering center Omay form a second cluster C. Data elements of messages e whose data element topic is within a distance rfrom a third clustering center Omay form a third cluster C. Data elements of messages e whose data element topic is within a distance rfrom a clustering center Omay form a cluster C. The distances r r r rmay be substantially equal.

The difference or distance rmay be determined in a time space temporal distance or in a location space spatial distance .

A spatial distance rmay be e.g. a Euclidian distance Manhattan distance or a difference between coordinates. For example if images have been taken at locations which are less than 1 km from each other then the corresponding messages may be partitioned into the same cluster.

The location may also be determined e.g. by GPS coordinates Global Positioning System or by using another spatial coordinate system. An additional database may be used for converting location names to coordinates. For example according to a coordinate system the location coordinates of Beijing may be 39 55 44 North and 116 231 18 East. A distance may also be defined by using spatial coordinates.

Also the height coordinate may be taken into consideration. For example data elements of messages containing photographs taken below the sea level may be partitioned into a first cluster and data elements of messages containing photographs taken at heights above 4000 meters e.g. at mountain regions may be partitioned into a second cluster.

A temporal distance rmay be a temporal separation between two events. For example if the date of taking a photograph of a first message is within two days from the date of taking a photograph of a second message the first message and the second message may be partitioned into the same time cluster.

An additional database may be used for converting verbally expressed dates to numerical dates. E.g. labor day has the same meaning as 1 May .

Messages associated with the same subject may be partitioned into the same cluster. Messages containing identical tag strings may be partitioned into the same cluster.

Additionally messages containing different tag strings may be partitioned into the same cluster if the tag strings have the same meaning. An additional dictionary or thesaurus may be used for establishing the meanings.

Messages associated with the same author may be partitioned into the same cluster. Additionally messages containing different author strings may be partitioned into the same cluster if the different author names are known to refer to the same person. A data element of a message may contain a nickname of a person instead of the real name of said person. An additional database may be used for establishing the identity of the author.

In case of the distances for the clusters C C C. . . Care evaluated in the same space. For a given set of distances r r r r the clustering centers O O O Omay be selected such that the number of the clusters C C C. . . Cis minimized. One of the previously received messages may be selected to be a clustering center O. Alternatively the clustering center Omay be an artificial point which does not exactly match with a data element of any previously received message.

The clusters C C C. . . Cmay be arranged such that they may be rapidly identified and or retrieved by using hash pointers pC pC pC. . . pC. Each cluster Cmay be described by a clustering center Oand the radius r. The center Oof each cluster may be indexed by using a hash pointer pC. The pointers associated with the clustering centers Omay be stored in an index table ITC. The pointers pC pC pC. . . pCmay be stored by e.g. using a B tree B plus tree in order to allow rapid search.

Thus the index table ITC may comprise a plurality of indexed data elements associated with pointers pC pC wherein a pointer pCassociated with an indexed data element Oindicates a cluster Cof data elements stored in the repository CRR and the distance between each data element of the cluster Cand the indexed data element Ois smaller than or equal to a predetermined distance r.

In spatial clustering the nodes of a cluster Cmay be spatially close to a data element of the in coming message e. The nodes e e eof the cluster Cmay be rapidly retrieved after the relevant cluster Chas been identified. A search by using the clustering centers Omay provide a fast way for identifying a cluster C which is relevant to the in coming message e.

A data element topic of a message stored in the clustering relation repository CRR may be called as a node. Each node e e eof the cluster Cmay represent a message which has been previously sent to a next broker. Thus each node e e eof the cluster Cmay be associated with a broker address BR BR . . . BRi. An individual node of the cluster C may comprise a topic associated with a subscription identifier and a broker address.

As several nodes e e . . . of the cluster Cmay be relevant regarding a data element of the in coming message e a search in the context relation clusters may provide one or more broker addresses BR BR . . . BRi where the in coming message eshould be forwarded to.

However the in coming message eis not typically forwarded to all broker addresses BR BR associated with nodes e e eof the relevant cluster CEach address BR BR . . . BRi may be associated with a merit value. For example a merit value for delivering the message eto a broker address NRi may be marked as SCORE.

The in coming message emay be forwarded to specific broker address e.g. BK when the merit value SCOREexceeds a predetermined limit e.g. LIM . The merit value may also be called as a rank .

If a majority of the nodes e e . . . of a cluster Care associated with the same broker address e.g. BK then the clustering center Oof the cluster Nmay be associated with the same broker address BK .

Referring to the same message i.e. data element of the message or node comprising the data element emay be related to several different clusters C C C Caccording to the context. The context may be e.g. location time subject or author. e e e e. . . edenote different messages. The subject may also be called as a tag .

The data elements of the cluster Cmay be spatially close to each other and the data elements of the cluster Cmay be temporally close to each other. The data elements of the cluster Cmay refer to the same subject. The data elements of the cluster Cmay refer to the same author.

The messages e e e . . . may comprise e.g. photographs. Based on the clustering it may be deduced that the message eis spatially related to the messages e e e because the corresponding images were taken at locations which were close to each other. The data element of the in coming message emay be considered to substantially match a message ebecause a difference between the data element of the in coming message eand a data element of the message eis smaller than a predetermined spatial distance limit LIM .

The in coming message emay be related to a message e because the images included in the messages e ewere taken e.g. during the same day.

The in coming message emay be related to a message e because the images included in the messages e edepict the same subject e.g. a rose.

Data elements of e e e emay belong to the same cluster Cwhen images included in the messages were taken by the same author.

In this example an image included in the message ewas taken by a different author than the images included in the messages e e e e. Thus the in coming message eis not related to the cluster C.

A search in the clustering relation repository CRR may comprise checking whether a data element of an in coming message ematches a data element of a previously sent message e e. A search in the clustering relation repository CRR may comprise checking whether a data element of an in coming message eexactly matches a data element of a previously sent message e e. A search in the clustering relation repository CRR may comprise checking whether a data element of an in coming message eapproximately matches a data element of a previously sent message e e. Partitioning of the previously sent messages e einto clusters C C . . . Cmay facilitate rapid identification of the relevant messages.

A data element may be considered to match with the data element of an in coming message ewhen a difference or a distance between the data element in the clustering relation repository CRR and the data element May 2008 of the in coming message eis smaller than a predetermined limit r.

A data element may be considered to approximately match with the data element of an in coming message ewhen a difference or a distance between the data element in the clustering relation repository CRR and the data element May 2008 of the in coming message eis smaller than a predetermined limit r and the distance is greater than zero. In case of approximate matching the data element of an in coming message eis different from the data element in the clustering relation repository CRR.

A data element may be considered to exactly match with the data element of an in coming message ewhen a difference or a distance between the data element in the clustering relation repository CRR and the data element May 2008 of the in coming message eis zero.

When searching for previously sent messages which are related to the in coming message e the query may be expanded also by using semantic hierarchy trees shown e.g. in . For a single message e several searches may be performed by using auxiliary search terms which are semantic ancestors or semantic descendants of the data element of the in coming message e.

A semantic ancestor node has a broader meaning than the original data element of the in coming message e. The ancestor node of a specific node is at a higher level of a hierarchy three than the specific node.

A semantic descendant node has a narrower meaning than the original data element of the in coming message e. The descendant node of a specific node is at a lower level of a hierarchy tree than the specific node.

The auxiliary search terms may be provided by using semantic hierarchy trees shown in . Auxiliary search terms may also be provided by using a personal relation graph shown in

The root node Nof the tree TREE may define e.g. the year of the date. The root node Nmay be called as the year node. The year node may have 12 child nodes N N . . . N wherein each child node defines the month of the date. These child nodes N N . . . Nmay be called as the month nodes. Each month node may in turn have 28 31 child nodes wherein each child node defines a day of the date.

The nodes N N. . . Ndenote the child nodes of the node N. Nis the parent node of the nodes N N . . . N. The nodes N Ndenote the child nodes of the node N. Nis the parent node of the nodes N N . . . N. The nodes Nand Nare ancestor nodes for each of the nodes N N . . . N. The node Nis not an ancestor node of the node N. The nodes N N N N N . . . Nare descendant nodes of the node N. The node Nis not a descendant node of the node N.

A search in the clustering relation repository CRR may be expanded by using a semantic hierarchy tree stored in the semantic relation repository SRR. For example when a data element of the in coming message especifies a topic Shang Hai node N the search term may also be an ancestor node N of the node Nand or a descendant node Nor N of the node.

When searching and matching in the clustering relation repository CRR the search term may be a data element of the in coming message eor an ancestor node of the data element of the in coming message e. For example if subscribers associated with a certain broker address have requested the topic China it is likely that the same subscribers will also be interested in receiving messages associated with a narrower topic Shang Hai or Huangpu District . If messages with the topic China have previously been forwarded via the broker BR the data element China of these messages may appear as nodes in the clustering relation repository CRR. Now when a message with the topic Huangpu District arrives at the broker BR the node having the data element China may be found in clustering relation repository CRR by looking for an ancestor node of the data element Huangpu District .

Also the descendant nodes may be used as search terms. However in that case it may be less likely that the subscribers will have an interest in the forwarded messages. For example if subscribers associated with a certain broker address have requested the relatively narrow topic Huangpu District it is less likely that they will be interested in receiving messages having the topic Shang Hai or China . However the probability that these subscribers would be interested in receiving messages having the topic Shang Hai or China may still be substantially greater than zero. In this sense use of the descendant nodes as search terms may also be relevant. If messages with the topic Huangpu District have previously been forwarded via the broker BR the data element Huangpu District of these messages may appear as nodes in the clustering relation repository CRR. Now when a message with the topic China arrives at the broker BR the node having the data element Huangpu District may be found in the clustering relation repository CRR by looking for a descendant node of the data element China .

The type of the relationship associated with each link L may be defined in a table PRGTAB. For example the type of relationship associated with the link Lmay be family the type of relationship associated with the links Land Lmay be friend the type of relationship associated with the link Lmay be classmate and the type of relationship associated with the link Lmay be colleague .

For example when the in coming message ecomprises a data element A the relation graph PGR may indicate that the nodes A A and A are directly linked to the node A. Thus a search in the context relation clusters may comprise finding nodes which at least approximately match the nodes A A A and A. It may be noticed that the node A is not directly linked to the node A in the graph PRG. In an embodiment the node A may be omitted when searching for nodes related to a data element A.

For example a message containing a photograph taken by a family member A a message containing a photograph taken by a friend A and a message containing a photograph taken by a classmate A may be considered relevant whereas a message containing a photograph taken by a friend A of the classmate A may be ignored.

In particular the repository BCN should be updated so that a data element of a subsequent message ewhich arrives at the first broker BR after the message ecan be searched fast and efficiently. The updating may comprise a step where a new node is added to the context cluster repository CRR see and . The updating may comprise adding one or more data elements of the message eto one or more of the existing clusters C C C C. The updating may comprise creating one or more new clusters C C C C.

The updating may comprise a step where a new node is added to a semantic hierarchy tree stored in the semantic relation repository SRR. See . . The updating may comprise a step where a new node is added to a personal relation graph . A new node may be added to a semantic hierarchy tree by using semantic information provided by an external service. The external service may be e.g. a hierarchical dictionary. The broker may send a request for establishing the location of a new node in a semantic hierarchy tree to an external service. The external service may send a response and the broker may update the semantic hierarchy tree according to the response. The request may be sent e.g. when a data element of the in coming message edoes not match with any nodes of the existing semantic hierarchy tree and the data element is not close to any of the existing clusters.

The clustering relation repository CRR may contain nodes which correspond to data elements of previously forwarded messages. In an embodiment the clustering relation repository CRR may be substantially empty when the operation of the broker BR is started for the first time.

The semantic relation repository SRR may contain a considerable number of nodes already when the broker BR is started for the first time.

Nodes stored in the clustering relation repository CRR may also contain one or more links e.g. hash pointers to individual subscriptions F F stored in the routing table RT. Thus when a matching node has been found in the clustering relation repository CRR the broker BR may also check whether the routing table RT still contains at least one subscription F for a topic of the matching node. Thus nodes may be eliminated from the clustering relation repository CRR according to cancelled subscriptions. Thus the number of nodes associated with less popular topics may be kept low when compared with the number of nodes associated with very popular topics.

Alternatively nodes may be deleted from the clustering relation repository CRR according to cancelled subscriptions by a process called as the cascading delete.

Alternatively each node of the clustering relation repository CRR may be deleted if a data element of a received and subscribed message has not matched with said node during a predetermined time period.

Searches in the clustering relation repository CRR may be performed fast by using indexed tables See . In particular the indices may be arranged as search trees preferably as B trees.

Several searches may be performed for the same in coming message e. The searches may be performed e.g. in terms of spatial location time subject and or author. The searches may be performed successively or substantially simultaneously.

The semantic relation repository SRR may contain data elements topics arranged in semantic hierarchy trees. The clustering relation repository CRR may contain data elements topics which are partitioned into clusters such that the data elements of an individual cluster are close to each other in terms of time location subject or author. Information stored in the semantic relation repository SRR may be used for finding auxiliary search terms. Information stored in the clustering relation repository CRR may be used for identifying the data elements of messages e e e . . . which at least approximately match with the search terms.

A search in the semantic relation repository SRR may provide auxiliary search terms i.e. auxiliary data elements which are semantic descendants of a data element of the in coming event e. The auxiliary search terms may be found by using semantic hierarchy trees and or by using relation graphs stored in the semantic relation repository. SRR

The search may be expanded by using auxiliary data elements which are ancestor nodes or descendant nodes of a data element of the in coming message e. A broker BR may utilize the semantic trees and or relation graphs TREE TREE TREES PRG when performing searches in the context cluster repository. The broker BR may make additional queries for auxiliary nodes search terms which are semantic ancestors or descendants of a data element of the in coming message e. The broker BR may make additional queries for auxiliary nodes search terms which are directly linked to a data element of the in coming message ein relation graph PRG.

For example when the data element of the in coming message especifies a time May 2008 the search may be expanded by using an auxiliary search term Year 2008 in addition to the original search term May 2008 . The time period Year 2008 is a semantic ancestor of the time period May 2008 . For example when the data element of the in coming message especifies a location Shang Hai then the search may be expanded by using semantic ancestors of the node Shang Hai . According to the location semantic tree TREE shown in a search in the context cluster repository CRR may include 

finding messages whose data elements are spatially close to the data element China node Nin . The node Nis an ancestor node of the node N.

Additionally a search in the context cluster repository CRR may also include finding messages whose data elements are spatially close to the data element Huangpu District node N or close to the data element Hongkou District node N . The nodes Nand Nare descendant nodes of the node N.

Thus the search in the context cluster repository CRR may be expanded by searching for nodes which at least approximately match a semantic ancestor and or a descendant of the data element of the in coming message e.

The semantic trees may contain a high number of levels. Consequently the number of descendant nodes may be very high. When expanding a query the path length may be limited in order to avoid excessive high number of search terms. When expanding the search query the path length from the data element of the in coming message eto an auxiliary search term may be kept smaller than or equal to a predetermined limit.

The path length between a first node and a second node means the number of links edges between the first node and the second node. For example the path length from a node to a parent node is equal to 1 and the path length from a node to a grandparent node is equal to 2. The path length from a node to a child node is 1 and the path length from a node to a grandchild node is equal to 2. When expanding the search the path length may be e.g. smaller than or equal to 2 which means that a parent node a grandparent node child nodes and or grandchild nodes may be included in the search.

A search in the context cluster relation repository CRR may comprise searching for nodes which at least approximately match a data element of the in coming message eand or which at least approximately match a semantic ancestor of the data element of the in coming message e and or which at least approximately match a semantic descendant of the data element of the in coming message e and or which at least approximately match a node which is directly linked to the data element of the in coming message ein a relation graph PRG.

The merit value SCOREmay be changed e.g. increased by a predetermined amount each time when an exact match or an approximate match is detected. The exact match means that the data element is identical to the topic. The approximate match means that the data element is close to the topic but different from the topic. In particular the merit value SCOREmay be increased when an exact match or an approximate match is detected. An approximate match may increase the merit value SCOREby a smaller amount than an exact match. A match with a semantic descendant may increase the merit value SCOREby a smaller amount than a match with a semantic ancestor. For example a match with a semantic descendant may increase the merit value SCOREby a value 0.7 and a match with a semantic ancestor may increase the merit value SCOREby a value 1.0. Corresponding searches may be performed also for time subject and or author of the in coming message e. Each matching or approximately matching node found during the searches may increase the merit value SCORE.

The first broker BR may be arranged to send the in coming message eto the broker BR when the merit value SCOREhas reached or passed a predetermined value. In particular the first broker BR may be arranged to send the in coming message eto the broker BR when the merit value SCOREexceeds a predetermined value.

If desired the matching data elements and or the approximately matching date elements found in the cluster relation repository CRR may be arranged as nodes of a multidimensional graph in the vicinity of a data point corresponding to the in coming message e. The data point is defined by the data elements of the in coming message e. The data point is a point of a multidimensional space defined by the date elements of the in coming message e. The position of the point in the multidimensional space may be specified by three coordinates for location one coordinate for time one or more coordinates to define a subject and one or more coordinates to define an author.

If desired detected matches between nodes of the cluster relation repository CRR associated with a predetermined broker BR and the data point of the in coming message emay be described as edges links of the multidimensional graph. A merit value SCOREfor sending the message eto the broker BR may be equal to the number of the edges links of the multidimensional graph.

Alternatively an individual merit value may be determined for each individual node of the multidimensional graph by counting the number of edges of said individual node. Only a predetermined number e.g. 10 of nodes having the highest merit values may be considered when sending the message eto the next broker s .

Referring to the nodes of may be represented as a single multi dimensional graph MDG. The messages efound in a time context search and the message efound in a location context search may represent the same message. Thus they may be merged and represented as a single node ein the multi dimensional graph MFG of . The link edge between the node eand the in coming message emay have a higher merit value w wthan the remaining nodes because the node eis more relevant than the remaining nodes e e e e. The node eis temporally and spatially related to the in coming message e whereas the nodes e eare only temporally related to the in coming message e and the nodes e eare spatially related to the in coming message e. If the combined merit value w wpasses the limit LIM the first broker BR may be arranged to send the in coming message eto a broker address of the previously sent message e.

In principle fusing the results into a multidimensional graph MDG and determining the merit values for nodes of the multidimensional graph may provide the same result i.e. one or more broker addresses as making several separate searches and summing the merit values.

In step additional search terms may be provided based on an original data element of the new message e by using the semantic relation repository SRR. For example when the original data element search term is Shang Hai an additional search term may be e.g. China .

A data element may be considered to match with a search term when a difference or a distance between the data element in the repository CRR and the search term is smaller than a predetermined limit r .

If desired search and matching in semantic relation repositories and in context cluster repositories may be repeated for location subject and or author. Thus for a single in coming message e several searches may be performed by using location specific search terms time specific search terms subject specific search terms and or author specific search terms.

The search may be continued until the search is complete checking step i.e. when all relevant search terms have been queried.

The merit value SCOREmay be determined in the determining step . The search step may provide one or more matching data elements stored in the clustering relation repository CRR. The matching data elements found in the steps and may be considered successively. Each matching data element associated with the broker address BRi may increase the merit value SCOREassociated with the new message eand the broker address BRi. Each matching node may increase change the value of the merit value SCOREe.g. by one. For each new message eand broker address BRi the initial value of the merit value SCOREmay be e.g. equal to zero.

The merit value SCOREmay be compared with a limit LIM in a comparing step . The limit LIM may be a predetermined value or a dynamically determined value. For example the limit LIM may be dynamically determined such that the message eis sent to a predetermined number of brokers.

The broker BR may be arranged to send the message eto a broker address BRi if the merit value SCOREreaches or passes the limit LIM. In particular if the merit value SCOREexceeds the limit LIM then the message emay be sent to the corresponding broker BRi in step .

If the merit value SCOREdoes not exceed the limit LIMafter a topic e.g. top of a previous message e has been taken into consideration the identifier Fid of the subscription F for the message emay be added to a list of identifiers Fid stored in an operational memory in step . The identifiers Fid stored in the operational memory may be used for accelerating a subsequent search in the routing table RT.

In step it may be checked whether all relevant messages have been taken into consideration. If all relevant matching messages found in the search step have not yet been handled a next message may be taken into consideration by repeating the merit value determining step after the checking step . The step may be repeated for each matching node found in the search step . The operational memory may comprise several identifiers Fid. The list of identifiers Fid stored in the operational memory may be used for accelerating a subsequent search in the routing table RT in step .

Substantially all matching elements may be taken into consideration by repeating the steps and . When all matching data elements have been taken into consideration the steps may be repeated for a next broker address BRuntil all relevant broker addresses have been taken consideration. The searching and matching process may be repeated for several brokers directly connected to the first broker BR. The relevant broker addresses may be determined based on the matching nodes found in step .

When the relevant broker addresses have been considered the data elements of the in coming message emay be compared with existing subscriptions F F . . . in step . In step a search may be carried out by checking whether there are any subscriptions for the topic of the new message ein the routing table RT.

The search may accelerated by checking only those subscriptions which were not taken into consideration in the previous steps . As mentioned above the operational memory may now comprise a list of identifiers Fid for subscriptions which had a matching topic. There is no need to search for those matching subscriptions for a second time because they can already be identified by using the list of identifiers Fid stored in the operational memory. If the topic of the new message edid not match with any of the data elements stored in the clustering relation repository CRR then the list of identifiers Fid stored in the operational memory may be empty and the whole routing table RT may be searched.

The existence of at least one subscription for the message emay be checked. If there are no subscriptions for the message e the message may be deleted stored or processed in some other predetermined way in step .

If there is at least one subscription for the in coming message e the message emay be forwarded according to the routing table RT in step . Processing by using the conventional routing table RT was shown e.g. in .

carrying out a first search in the clustering relation repository CRR in order to find at least one data element matching with the search term 

carrying out a second search in the routing table RT in order to find a subscription matching the topic of the new message e wherein at least one subscription associated with a matching data element found in the first search is excluded from the second search in order to accelerate the second search and

controlling sending of the new message eto a next broker BR according to the result of the first search and the second search.

If a search in the cluster relation repository CRR does not provide a match the repository may be updated in step .

In step the topic of the new message emay be associated with the identifiers Fid Fid of one or more matching subscriptions F F the identifiers were found in step . In step the topic of the new message eand the associated identifiers may be stored in the clustering relation repository CRR.

In step one or more nodes corresponding to data elements of the in coming message emay be added to the clustering relation repository CRR. If desired updating of the cluster relation repository CRR may conditional. For example a new node may be added to the cluster relation repository CRR only if there is a certain minimum number of subscriptions for the message e.

The above mentioned method steps may also be carried out in a different order. For example the semantic relation repository SRR may be updated before updating the clustering relation repository CRR. For example the semantic relation repository SRR and the clustering relation repository CRR may be updated substantially simultaneously. For example queries by using the different search terms may be carried out substantially simultaneously. For example the step for updating the list of identifiers Fid may be carried out between the determining step and the comparing step . For example merit values SCOREmay be determined substantially simultaneously for several different broker addresses BRi. Parallel data processing may be used. For example the message emay be sent substantially simultaneously to several different broker addresses BRi

If a previous message ehas been stored in the relation repository when a subsequent new message earrives and if the topic of the new message ematches with the topic of the previous message e there is no need to check the whole routing table RT. It may be enough if only the incremental parts of the routing table RT are checked.

Without the clustering relation repository CRR the whole routing table RT should be searched again. The routing table RT may comprise e.g. millions of subscriptions and the associated time cost may be very high.

Using the clustering relation repository CRR and using the routing table RT represent a first step and a second step. In the first step matching data elements may be searched in the clustering relation repository CRR. In the second step matching subscriptions may be searched in the routing table RT. In the second step the search in the routing table RT may be accelerated because there is no need to search for those matching subscriptions which were identified already during the first step.

Thus the use of the clustering relation repository CRR may accelerate the matching procedure. Even in the worst case the matching time may be equal to the matching time of a conventional method which only utilizes the routing table RT. When using the clustering relation repository CRR it is likely that the matching time can be considerably reduced.

A publisher PUB may call an application programming interface API for sending a message eto the broker network NET.

A subscriber SUB may call an application programming interface API for sending a subscription to the broker network NET

A broker BR may comprise an index service IS and a query service QS. The index service IS may implement updating the semantic relation repository SRR and or the context cluster repository CRR. The query service QS may implement search and matching in the semantic relation repository SRR and the context cluster repository CRR.

The publishers PUB PUB PUB may be e.g. computers Personal Digital Assistants PDA mobile phones digital cameras automatic surveillance cameras automatic weather stations or measuring instruments. The subscribers may be e.g. computers Personal Digital Assistants PDA televisions or mobile phones.

The message emay be an image e.g. an image of a person family animal plant building and or landscape. The message may comprise metadata which specifies the topic or topics of the message. The metadata may specify e.g. that the message is an image of a lily flower taken in Hai dian district on 1 Jan. 2008 by a person A. In this case the metadata may contain e.g. the following elements 

The data elements topics of a message may also be generated automatically by analyzing the contents of the message. For example the topic of an image may be generated by an image recognition method. The image recognition method may comprise comparing the image with other images stored in a database.

The broker BR may be configured to perform normalizing data elements identifying data elements deleting stop words stemming data elements terms extracting index entries creating index e.g. inverted lists tokenizing and or parsing

Initially when no messages have arrived at the first broker BR the clustering relation repository CRR may be empty.

The embodiments of the invention may be methods apparatus and computer programs for distributing messages in a publish subscribe messaging network NET.

The broker BR may be configured to provide a query service QS an updating service IS index service and or a subscription service SS. The query service QS may take care of the searching and matching in the clustering relation repository CRR and for expanding the search by using the semantic relation repository SRR. The query service QS may also take care of forwarding an in coming message when a sufficient number of matching nodes are found in the clustering relation repository CRR. The index service may update the clustering relation repository CRR according to previously forwarded messages by taking into account existing subscriptions. The subscription service SS may take care of updating the routing table and or the subscription service SS may take care of delivering messages according to existing subscriptions.

For an in coming message the query service QS may be carried out considerably earlier than the index service IS and or the subscription service SS. This may facilitate reliable operation of the broker in an overload situation i.e. when the broker BR receives messages at a higher rate than what can be processed and forwarded according to the routing table RT. In an embodiment the index service IS and or the subscription service SS may be carried out when messages arrive at the broker BR at a low rate e.g. during nighttime.

The node matching engine may search for matching nodes in the clustering relation repository CRR. The node manager may add a node to the clustering relation repository CRR and or the node manager may remove a node from the clustering relation repository CRR based on subscriptions stored in the routing table RT. The node manager may control operation of the node matching engine .

The subscription manager may add a subscription to the routing table RT and it may cancel a subscription from the routing table RT. The subscription matching engine may search for matching subscriptions in the routing table RT. The subscription manager may control operation of the subscription matching engine .

When subscriptions are canceled from the routing table RT corresponding nodes may be removed from the clustering relation repository CRR e.g. by a process called cascading delete . In particular the subscription manager and or the node manager may be arranged to delete nodes from the clustering relation repository CRR according to canceled subscriptions.

The marking com denotes communication between the node matching engine and the repository BCN com denotes a communication between the node manager and the repository BCN com denotes communication between the node manager and the node matching engine com denotes communication between the node manager and the routing table RT com denotes communication between the subscription manager and the routing table RT com denotes communication between the routing table RT and the subscription matching engine com denotes communication between the subscription manager and the subscription matching engine and com denotes communication between the node manager and the subscription manager .

The list of identifiers Fid associated with matching nodes found in the clustering relation repository CRR may be communicated com e.g. from the node manager or from the node matching engine to the subscription manager or to the subscription matching engine . The list of identifiers Fid may be used for accelerating a search in the routing table RT see discussion of .

Publishers PUB PUB PUB running on respective data processing systems may publish messages ethat can be received by multiple subscribers SUB SUB. The publishers PUB PUB PUB may send messages eto an intermediate publish subscribe message broker BR. The publishers PUB PUB PUB and subscribers SUB SUB do not need direct connections between them and do not need each other s address information. Instead the publishers may send messages eto the broker BR. The message emay include metadata such as data elements specifying message topics. The publishers PUB PUB PUB may use application programs that rely on message transfer functions of underlying messaging infrastructure product that hold network address and other communication information for the broker BR.

The message broker BR may be implemented on a data processing system that is separate from the publisher systems and separate from subscriber s systems. The message broker BR may comprise a subscription matching engine and an associated routing table RT. Subscribers SUB SUB may register with the broker BR and indicate their interest in particular information such as by specifying a particular message topic or topics. The subscribers requirements may be stored at the broker BR. A broker can store network addresses and protocol requirements for individual subscriber systems and the broker can initiate a connection. Alternatively the broker BR may merely store names of subscriber systems and of their subscriptions and the network and communications information may be held at the subscriber s system. The network and communications information may be used when the subscriber initiates a connection to the broker.

The node matching engine at the broker BR may be arranged to compare search terms with data elements stored in the clustering relation repository CRR in order to determine whether an in coming message eshould be forwarded to a predetermined broker address. Consequently the broker BR may be arranged to forward the in coming message eto relevant brokers BR BR which in turn may forward the in coming message eto the interested subscribers. Although only a small number of publishers and subscribers are shown in and there may be many publishers and many subscribers within the network and the publish subscribe broker may be part of a distributed broker network 

For cost reasons and in order to facilitate ongoing development the units and or of the broker BR may be implemented in computer program code. The computer program code may be stored in a machine computer readable medium. The program code when executed by a data processor may implement the message forwarding according to the present invention.

The publish subscribe broker BR the publisher applications and the subscriber applications may be implemented in computer program code. The code may be written in an object oriented programming language such as C Java or SmallTalk or in a procedural programming language such as the C programming language. These program code components may execute on a general purpose computer or on a specialized data processing apparatus. Program code implementing some features and aspects of the invention may be executed on a single data processing device or may be distributed across a plurality of data processing systems within a data processing network such as a Local Area Network LAN a Wide Area Network WAN or the Internet. The connections between different systems and devices within such a network may be wired or wireless and are not limited to any particular communication protocols or data formats and the data processing systems in such a network may be heterogeneous systems.

The publish subscribe broker BR may be a component of an edge server i.e. the broker may be one of a set of Web server or application server components or a network gateway device. The broker BR may also be used e.g. in remote telemetry applications.

The invention may be implemented in networks that include wirelessly connected PDAs mobile telephones and or automated sensor devices as well as networks that include complex and high performance computer systems.

The invention may be applicable to publish subscribe communications environments that rely on a distributed broker network.

Other brokers BR BR of the network NET and or the subscribers SUB SUB may also be configured to use proximity matching and or semantic matching in order to match messages topics with subscriptions so that the messages can be delivered all the way to the relevant subscribers SUB SUB. Otherwise a subsequent broker or a subscriber might reject a message which does not exactly match with a subscription.

The broker BR may comprise a deadlock handling system in order to prevent indefinite circulation of the same message in the network.

For the person skilled in the art it will be clear that modifications and variations of the devices according to the present invention are perceivable. The figures are schematic. The particular embodiments described above with reference to the accompanying drawings are illustrative only and not meant to limit the scope of the invention which is defined by the appended claims.

