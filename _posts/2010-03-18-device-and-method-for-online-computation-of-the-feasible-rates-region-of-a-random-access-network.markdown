---

title: Device and method for online computation of the feasible rates region of a random access network
abstract: A method is intended for computing online a feasible rates region in a network using a random access MAC protocol and comprising nodes having links there between. This method comprises the steps of i) determining, for each link, a primary extreme point corresponding to a maximum output rate when this link transmits alone at a maximum input rate, and ii) determining secondary extreme points by combining these primary extreme points with a chosen interference model, these primary and secondary extreme points defining a boundary of a feasible rates region.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09060285&OS=09060285&RS=09060285
owner: Thomson Licensing
number: 09060285
owner_city: Issy-les-Moulineaux
owner_country: FR
publication_date: 20100318
---
This application claims the benefit under 35 U.S.C. 365 of International Application PCT EP2010 053577 filed Mar. 18 2010 which was published in accordance with PCT Article 21 2 on Oct. 7 2010 in English and which claims the benefit of European patent application No. 09305284.3 filed Apr. 3 2009.

The present invention relates to random access networks and more precisely to computation of feasible rates regions of such networks.

One means here by random access network a network in which nodes operate based on a random access or contention based MAC Medium Access Control protocol such as ALOHA or CSMA Carrier Sense Multiple Access for instance. So it could be a fixed communication network or a wireless communication network and notably an IEEE 802.11 network i.e. a WLAN Wireless Local Area Network for instance of the WiFi type .

As it is known by the man skilled in the art some of the above mentioned networks deployed in urban and rural areas around the globe and notably 802.11 multi hop wireless mesh networks enable low cost Internet access and emerging community applications.

Random access networks offer advantages such as simple decentralized Medium Access Control MAC protocols that arbitrate transmissions to the wireless medium. However they are also limited by well known performance problems such as lack of predictability unfairness or even complete starvation. These problems are due to the poor synergy of the random access MAC protocol and notably the IEEE 802.11 one and higher layers of the protocol stack. Several solutions have been proposed but most require modifications of the MAC protocol or higher layer legacy protocols like TCP.

These solutions may be classified into three categories throughput prediction solutions capacity estimation solutions and protocol solutions. One focuses hereafter on the IEEE 802.11 solutions but as mentioned above the invention is not limited to this type of network.

Several models have been proposed for throughput prediction in 802.11 random access multi hop networks. Most of them are based on a first solution described in the document of G. Bianchi Performance analysis of the IEEE 802.11 distributed coordination function IEEE Journal on Selected Areas in Communications 18 3 535 547 March 2000 which captures the effect of IEEE 802.11 binary exponential backoff in single hop networks and on a second solution described in the document of R. Boorstyn et al. Throughput Analysis in Multi hop CSMA Packet Radio Networks IEEE Transactions on Communications 35 3 267 274 March 1987 which captures the effect of carrier sensing in multi hop networks.

These models vary in the accuracy with which they model interference either based purely on geometry or seeded with actual measurements and their prediction power single hop throughput prediction or multi hop throughput prediction . These models are impractical for operational multi hop 802.11 networks for two reasons. First many of these models do not provide closed form expressions for throughput and therefore one must exhaustively search through the feasible rates region they defined to predict an optimal multi hop throughput. This search can become prohibitively expensive as the number of flows increases except if feasibility is characterized by means of non linear constraints at the potential cost of reduced accuracy. Second all existing measurement based models require a separate measurement phase where all links are activated backlogged in specific patterns individual node activations or pair wise link activations . As a result they require either O N measurements or O L measurements and each measurement typically requires several seconds to collect sufficient statistics. In practice this imposes an extended mesh network downtime and complicates the network operations with additional signalling mechanisms to switch between measurement and regular operation.

It has been recently proposed in the document of N. Ahmed et al. Online Estimation of RF Interference Proc. ACM CoNEXT Madrid Spain December 2008 a new technique allowing to significantly reduce the time of these measurements in client AP WLANs but this new technique is not applicable to multi hop wireless mesh networks and requires extensive firmware modifications.

The objective of this invention is to offer a method and an associated device allowing determination or computation of feasible rates regions in random access networks i.e. using a random access MAC protocol and possibly an optimization of the performance of these random access networks through rate control. This method does not require modifications of legacy protocols and can be readily implemented or incorporated in today s deployments using traffic shapers and rate limiters that are widely available.

More precisely the invention provides a method intended for computing online a feasible rates region in a network using a random access MAC protocol and comprising nodes having links therebetween. The online computation of the feasible rates region enables applications like admission control or network optimization.

One means here by feasible rates region the set of rates that can be simultaneously sustained by the random access network at a given time. A more formal definition of a feasible rates region is the set of all achievable output rates or throughputs that result from input rates that are scaled down only by the inherent link packet loss rates p . The inherent packet loss rates are measured or estimated when the links transmit alone in backlogged mode i.e. at a maximum input rate . In the special case where the inherent packet loss rates pare zero the feasible rates region is the set of all output rates or throughputs that are equal to their corresponding input rates.

The method according to the invention may include additional characteristics considered separately or combined and notably 

The invention also provides a device intended for computing online a feasible rates region in a network using a random access MAC protocol and comprising nodes having links therebetween and comprising 

This device may further comprise a third computation means arranged for computing a set of target output rates for the network from channel loss rates provided by the nodes neighbourhood relationships between nodes a routing matrix and the primary and secondary extreme points.

This third computation means may be arranged for computing the set of network target output rates by optimizing a utility function of the target output rates subject to constraints based on the routing matrix and the primary and secondary extreme points then by selecting a subset of output rates for which an associated node is a source from this computed set and for generating optimized input rates corresponding to these output rates of the selected subset.

This device may also further comprise a control means arranged for limiting the rate of the flows of the associated node according to the generated optimized input rates.

The appended drawings may serve not only to complete the invention but also to contribute to its definition if need be.

The invention aims at offering a method and an associated device D intended for computing online a feasible rates region in a random access network WN i.e. a network using a random access MAC protocol .

In the following description it will be considered that the network WN is of the wireless type and more precisely that it is an IEEE 802.11 network for instance a WiFi network . But the invention is not limited to this type of network. Indeed it concerns any type of network comprising nodes or network equipments using a random access MAC protocol. So it may be also a fixed network.

Moreover in the following description it will be considered that the wireless network WN is of the multi hop type. So and as illustrated in it comprises wireless routers or access points NEi connected or linked therebetween and defining nodes. But the invention is not limited to this type of wireless network. Indeed it concerns also wireless network of the single hop type i.e. comprising base stations or any equivalent radio network equipments serving user or client wireless communication equipments and defining nodes. It is recalled that a single hop type wireless network is a particular case of a multi hop type wireless network.

In the illustrated example the node index i varies from 1 to 5 but the number of nodes NEi may be greater or smaller than 5.

As mentioned before the invention proposes a method intended for computing online a feasible rates region in a network WN.

One means here by feasible rates region the set of all rates that can be simultaneously sustained by the network WN at a given time.

It is recalled that the 802.11 MAC protocol can be viewed as a function f that maps link input rates x representing load to link output rates y representing throughputs over a time period T y f x . When x is unconstrained and nodes NEi are allowed to transmit at the nominal radio bandwidth the output rate of each link is generally less than its input rate due to interference and poor channel conditions. These two causes manifest themselves either as MAC backoffs and retransmission delays or as network layer packet losses resulting from buffer overflows MAC collisions or poor wireless channel conditions.

Based on the above a formal definition of the feasible rates region is the set of all output rate vectors y y . . . y . . . y that result from constrained input rate vectors x x . . . x . . . x that are scaled down only by the inherent link packet loss rates vector p p . . . p . . . p as follows y 1 p xfor each link l 1 . . . L the packet loss rates p p . . . p . . . p are measured similarly to the maximum output rate or capacity when the links transmit alone at maximum input rate or in backlogged mode . In the special cases where the inherent packet loss rates pare zero the feasible rates region is the set of all output rates that are equal to their corresponding input rates.

It should also be noted that the definition of feasible rates region can also be extended to rate vectors y y . . . y . . . y of S multi hop flows with fixed routes instead of rate vectors y y . . . y . . . y of L links in a similar manner as above. The only difference is that the inherent packet losses for links are replaced by inherent packet losses p p . . . p . . . p for the multi hop routes of these flows. The loss rate pof each route s can be estimated based on the measured channel loss rates pof the links in the route s for instance by means of the relation p 1 1 p .

The method according to the invention can be implemented at least partly by at least one device D according to the invention.

As it is schematically illustrated in a device D according to the invention may be located into several and preferably each network equipment NEi defining a node of the network WN. But this device D could be also a network equipment or element coupled to a network node NEi or a network equipment connected to the network WN such as a management equipment.

So a device D can be made of software modules at least partly or of electronic circuit s or hardware modules or else of a combination of hardware and software modules in this case the device D comprises also a software interface allowing interworking between the hardware and software modules .

When devices D are distributed into the nodes NEi each of them determines a feasible rates region for its node NEi. When there is only one device D for the whole network or for a part of a network this centralized device determines feasible rates region for all the network nodes NEi or for the nodes belonging to its network part.

The method according to the invention comprises two main steps which aim at determining primary and secondary extreme points defining a boundary of a feasible rates region.

This feasible rates region can be modeled by a convex polytope. The feasible rates region is characterized by K extreme points c k c . . . c where k 1 to K and where I represents a link between two nodes NEi with l 1 to L . Any set of output rates y y . . . y that lies inside the polytope including the convex hull or boundary is feasible.

According to the invention and as detailed below each point c c . . . c in the convex hull or boundary of this polytope can be determined as a linear combination of the K extreme points c k defining the polytope boundary or boundary of the network feasible rates region . So each non extreme point c c . . . c can be expressed by the relation

A very simple and non limiting example of a feasible rates region is illustrated in . In this example the number of links L is equal to 2 and the number of extreme points K defining the boundary of the feasible rates region is equal to 4. In this example c c c c c C c and c c c are the four extreme points defining the boundary of the feasible rates region which is included into a rectangle region called independent region the non extreme point c c c belonging to the boundary is a linear combination of the K extreme points and the time sharing region is a part of the feasible rates region where the links interfere but are scheduled in a mutually exclusive manner and therefore the sum of normalized output rates does not exceed unity y c y c 1 . According to the invention any output rate y y y that lies in the polytope defined by the K extreme points is feasible.

It is important to note that TDMA networks or time sharing CDMA networks can be characterized by convex feasible rates regions where the extreme points are readily provided by SINR formulas. However it is not evident how such a model can be applied to networks using random access MAC protocol like 802.11. In contrast to TDMA and CDMA networks in random access networks the feasible rates region is not necessarily convex and it is not given by analytical formulas. The method according to the invention uses a convex approximation to enable online computation. In addition applying this model to a real world random access network 802.11 in this example requires addressing two challenges i define the extreme points for adequate characterization of the feasible rates region and ii compute these extreme points during network operation in a non intrusive manner.

The first main step i of the method consists in determining for each link l established between two network nodes NEi a primary extreme point which corresponds to a maximum output rate when the considered link transmits alone at a maximum input rate or in a backlogged mode .

This first main step i can be implemented by a first computation means CM of a device D. As mentioned before it can be implemented in a distributed manner i.e. in each distributed device D associated to a node NEi or in a centralized manner i.e. in a single centralized device D of the network WN.

The second main step ii of the method consists in determining secondary extreme points by combining these primary extreme points with a chosen interference model.

This second main step i can be implemented by a second computation means CM of a device D. As mentioned before it can be implemented in a distributed manner i.e. in each distributed device D associated to a node NEi or in a centralized manner i.e. in a single centralized device D of the network WN.

The determined primary and secondary extreme points define together the boundary of the network feasible rates region.

In the non limiting example of feasible rates region illustrated in c c and c c are two primary extreme points corresponding to the two maximum output rates or capacities when each link transmits alone while c c c and c c c are two secondary extreme points which capture partial interference when the two links l transmit simultaneously.

Preferably these primary and secondary extreme points are determined or computed online i.e. during network operation and in a non intrusive manner.

Also preferably each primary extreme point of a link l corresponds to a maximum output rate or capacity which is achieved when this link l transmits alone in a backlogged mode i.e. transmits at a maximum input rate .

While this last definition of the primary extreme points is simple their online determination is challenging since during network operations links l do not transmit alone or in backlogged mode. So it is possible to introduce an online capacity estimation procedure to compute the maximum output rates or capacities .

Since wireless link quality and interference patterns vary over time this online capacity estimation procedure comprises preferably a measurement phase. For instance this online capacity estimation procedure may consist in using a capacity representation which relates the maximum output rate or link maximum throughput or capacity to the packet loss rate which is experienced by the MAC protocol.

The packet loss rate can be measured online using network layer broadcast probes which incur low overhead. However when interference is present this packet loss rate includes losses due to both channel errors and collisions. So it is preferable to use a capacity representation that relates the maximum output rate or maximum throughput or capacity of a link to the channel loss rate of this link. In this case one may measure online link packet loss rate that is experienced by the MAC protocol by means of network layer broadcast probes then one may use a channel loss rate estimator to filter out the collisions that are induced by cross traffic into the measured packet loss rate in order to produce a channel loss rate and finally one may use the capacity representation that relates the maximum output rate to the channel loss rate in order to determine this maximum throughput of the considered link.

It is important to note that it is preferable to determine a maximum output rate or maximum throughput or capacity which is a maximum User Datagram Protocol UDP throughput because this provides higher accuracy. In a variant one may use a maximum TCP throughput for instance but this induces less accurate estimation of the feasible rates region.

For instance one may use the following formula 1 to express the relation between the maximum UDP throughput T and the channel loss rate pof a link l 

In formula 1 all quantities are either known in advance or depend on p. Tcan be computed given 802.11 MAC parameters data packet size and data rate as described in the document of J. Jun et al. Theoretical Maximum Throughput of IEEE 802.11 and its Applications Proc. International Symposium on Network Computing and Applications NCA Cambridge Mass. USA April 2003. W Wand m are given by the 802.11 specification. The header H and the packet payload P are also known and ETX depends on p.

As mentioned above the packet loss rate pcan be measured by a probing system that uses network layer broadcast probe packets. Broadcast packets are not subject to MAC retransmissions and reflect the packet loss rate experienced by the MAC protocol. For instance the packet loss rate pcan be computed as 1 1 p 1 p where pand pare DATA and ACK acknowledge packet loss rates respectively. These packet loss rates can be measured as fraction of lost DATA and ACK broadcast probes over a probing window. The broadcast probes emulating DATA and ACK can be sent at the data rate and packet size of the DATA and ACK packets respectively.

During network operations packet losses are due to both channel errors and collisions and the measured loss rates pand pwill be higher than if the links were transmitting alone. In order to use the maximum UDP throughput representation one must be able to distinguish collisions from channel errors and use formula 1 with a pcomputed from the estimated channel loss rates of pand p. Therefore the problem of online maximum UDP throughput estimation translates to the problem of separating channel losses from collisions. Solutions to this problem have been designed for client AP WLAN traffic scenarios or require low level access to firmware. These solutions are notably described in the document of S. Rayanchu et al. Diagnosing Wireless Packet Losses in 802.11 Separating Collision from Weak Signal Proc. IEEE INFOCOM Phoenix Ariz. USA April 2008 and in the document of K. Whitehouse et al. Exploiting the capture effect for collision detection and recovery EmNetS 11 2005.

One may use any technique known from the man skilled in the art for estimating the maximum UDP throughput. Ad Hoc Probe is such a technique which is notably described in the document of L. J. Chen et al. Ad hoc probe path capacity probing in wireless ad hoc networks Proc. International Conference on Wireless Internet WICON Budapest Hungary July 2005 . However Ad Hoc Probe is not appropriate for estimating the link maximum UDP throughput because a in absence of interference it estimates a higher value closer to the nominal throughput because ad hoc probe estimations are based on minimum dispersion delay estimates which do not take into account the inherent link channel losses and b in the presence of interference the minimum delay filter will filter out congestion but again will not account for losses.

As mentioned above during the second main step ii one determines the secondary extreme points by combining the primary extreme points determined during the first main step i with a chosen interference model.

For instance this interference model may rely on two simplifying assumptions. Firstly it may assume pair wise interference where each interference between two links of a pair is assumed to be independent from interferences between other pairs of links. Secondly it may assume binary interference where two links of a pair either interfere in a mutually exclusive manner or do not interfere. If we refer to the example illustrated in simple two dimensional case the interference model captures either the time sharing region or the independent region.

For instance the chosen interference model may be a binary LIR Link Interference Ratio interference model. It is recalled that the Link Interference Ratio LIR is a metric that measures interference between link pairs in CSMA networks as described in the document of J. Padhye et al. Estimation of Link Interference in Static Multi hop Wireless Networks Proc. ACM Internet Measurement Conference IMC Berkeley Calif. USA October 2005.

For instance one may use a binary interference model based on a LIR threshold LIR. If the LIR of two links is greater than the LIR threshold LIR the two links are considered as non interfering and their feasible rates region is captured by the independent region defined by their primary extreme points c and their secondary extreme point C c . Otherwise the two links are considered as interfering and their feasible rates region is the time sharing region defined by only the primary extreme points c .

Other binary interference models can be used and notably a two hop pair wise binary interference model where each link interferes with all links adjacent to its node endpoints and all the links adjacent to their one hop neighbors. This other interference model notably described in the document of S. Rangwala et al. Understanding congestion control in multi hop wireless mesh networks Proc. ACM MobiCom San Francisco Calif. USA September 2008 is easier to use online i.e. during network operation than the LIR interference model. Extensive experiments and measurements in a wireless mesh testbed have shown that it provides an adequate approximation to the binary LIR interference model with LIR threshold LIR 0.95. However one may also use other variations of this hop based interference model to realize a pair wise binary interference model.

One may built a conflict graph of the network WN in which each vertex corresponds to a unidirectional link l and each edge between a pair of vertices corresponds to an interference between the pair of unidirectional links l which correspond to this pair of vertices and one may determine the secondary extreme points from maximal independent sets of vertices of this conflict graph.

It is important to note that the pair wise binary interference model determines whether an edge exists or not between two vertices of the conflict graph. If the corresponding links interfere based on this model one adds an edge between the vertices. Different pair wise binary interference models will in general generate different conflict graphs for the same network.

The independent sets of vertices of the conflict graph indicate sets of links l that can transmit simultaneously without interference. These independent sets can be computed using an independent set enumeration algorithm on the conflict graph. Alternatively they can be computed using a clique enumeration algorithm in the complement of the conflict graph in general a graph G V E with vertex set V and edge set E is called the complement of a graph G V E with the same vertex set V and another edge set E if the edge v v is in E if and only if it is not in E. In other words two vertices vand vare adjacent in G if and only if they are not adjacent in G. So cliques in the complement of the conflict graph are independent sets of the conflict graph .

It is important to note that one only uses here the maximal independent sets to reduce complexity of the enumeration algorithm. But a more accurate estimation would use all independent sets in the conflict graph.

An example of clique enumeration algorithm that can be used is described in the document of K. Makino et al. New algorithms for enumerating all maximal cliques Proc. 9th Scandinavian Workshop on Algorithm Theory Humlebaek Denmark July 2004.

Each maximal independent set m M is represented by a 0 1 L 1 vector v m where the unit elements denote the links corresponding to the vertices of this independent set. Each vector v m can be mapped to a secondary extreme point c m by replacing each unit entry with the corresponding capacity. This can be done using an L L diagonal matrix Cwhere each column corresponds to a primary extreme point c k . Then each secondary extreme point can be built as mentioned hereafter 

As illustrated in a device D may further comprise a third computation means CM coupled to its first CM and second CM computation means. This third computation means CM is arranged for computing a set of target output rates for the network WN from channel loss rates provided by the nodes NEi neighbourhood relationships between nodes NEi a routing matrix and the primary and secondary extreme points.

Routes routing matrices neighbourhood information or relationships and channel loss rate estimates can be disseminated into the network WN by means of a routing protocol such as Srcr that comes with Click . This information is used by each node NEi to update its Srcr topology database to compute routes for instance by using Dijkstra s routing algorithm using a link cost metric such as ETT described in the document of R. Draves et al. Routing in multi radio multi hop wireless mesh networks Proceedings of MobiCom 2004 and to execute the optimization algorithm in the third control means CM.

The set of target output rates can be computed locally i.e. in a distributed manner in each node NEi associated with a distributed device D or in a centralized manner i.e. in a single centralized device D of the network WN.

For instance a set of target output rates y y . . . y can be computed by optimizing a utility function U y of the target output rates subject to constraints based on the routing matrix and the primary and secondary extreme points c k c . . . c .

Then given the network output rate vector y y . . . y the third computation means CM selects the subset of rates yfor which an associated node NEi is a source and it generates the corresponding optimized input rates xcorresponding to these output rates of the selected subset. For instance each optimized input rate xis given by x y 1 p where pis the path loss. This path loss pcan be estimated based on the channel loss rates pin the path s for instance by means of the relation p 1 1 p .

As illustrated in a device D may further comprise a control means CNM arranged for limiting the rate of the flows of its associated node NEi according to the optimized input rates xwhich are generated by the third computation means CM. For this purpose it CNM may use Click BandwidthShaper for instance.

The time scale at which the rate control according to the invention is adjusted depends on the capacity estimation interval determined by the probing window size and period and the computation time that the first CM second CM and third CM computation means take.

The capacity estimation interval is constrained by the network layer probing system. Probing frequency should be low enough for instance every 0.5 second to keep the overhead low but enough probes should be used to ensure sufficient accuracy. Stable channel loss rates and hence stable capacity estimates can be obtained within few minutes typically between approximately 100 seconds and 800 seconds .

The computation time is the time which is necessary to the first CM second CM and third CM computation means to compute the extreme points of the feasible rates region and to solve the optimization problem.

The invention offers an online optimization based network layer rate control for mesh networks at a time scale of a few minutes which allows eliminate a number of common performance problems occurring in such networks e.g. avoid starvation and enforce fairness objectives without sacrificing much output rate or throughput .

Moreover the online computation of the feasible rates region can be also used for admission control e.g. to determine whether a given set of rates can be sustained by the network at a given time in addition to the described optimization method.

The invention is not limited to the embodiments of method device and network equipment described above only as examples but it encompasses all alternative embodiments which may be considered by one skilled in the art within the scope of the claims hereafter.

