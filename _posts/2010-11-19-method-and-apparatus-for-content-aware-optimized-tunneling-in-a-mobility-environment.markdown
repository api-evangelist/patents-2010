---

title: Method and apparatus for content aware optimized tunneling in a mobility environment
abstract: A method, computer readable medium and apparatus for performing content aware optimized tunneling in a communication network are disclosed. For example, the method authenticates a user endpoint device, establishes a tunnel to the user endpoint device if the user endpoint device is authenticated, analyzes content of a data packet transmitted through the tunnel to determine if the tunnel should be re-directed, and re-directs the tunnel to a gateway general packet radio services support node light based upon the content of the data packet.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08578447&OS=08578447&RS=08578447
owner: AT&T Intellectual Property I, L.P.
number: 08578447
owner_city: Atlanta
owner_country: US
publication_date: 20101119
---
Current wireless technologies require a wireless data packet to go through a certain number of network elements on the wireless network via general packet radio services GPRS tunneling protocol GTP tunnels before reaching the Internet. Generally all of the wireless communications have to go through a GPRS support node GGSN that can sometimes be located more than 1000 miles away from a device sending the data packet. The cost and complexity of GGSNs limit the number of GGSNs that are deployed across the country. As a result sometimes the wireless communications experienced by a user may be unsatisfactory due to the fact that the wireless communications have to go through a GGSN that may be far away from the user s device.

In one embodiment the present disclosure teaches a method computer readable medium and apparatus for performing content aware optimized tunneling in a communication network. In one embodiment the method comprises authenticating a user endpoint device establishing a tunnel to the user endpoint device if the user endpoint device is authenticated analyzing content of a data packet transmitted through the tunnel to determine if the tunnel should be re directed and re directing the tunnel to a gateway general packet radio services support node light based upon the content of the data packet.

To facilitate understanding identical reference numerals have been used where possible to designate identical elements that are common to the figures.

The present disclosure broadly discloses a method computer readable medium and an apparatus for performing content aware optimized tunneling in a communication network. is a block diagram depicting one example of a cellular communications network architecture related to the current disclosure. In one embodiment the cellular communications network architecture comprises a 3G cellular network such as a universal mobile telecommunications system UMTS network and the like. However it should be noted that the cellular communications network architecture may include other types of cellular communications networks such as general packet radio services GPRS networks global system for mobile communication GSM networks or enhanced data rates for GSM evolution EDGE networks and the like by substituting the appropriate hardware and or hardware configurations for the respective networks.

In one embodiment the UE subsystem includes one or more user endpoint UE devices . The user endpoint devices may include a mobile telephone a smart phone a messaging device a tablet computer a laptop computer an air card and the like. The user endpoint devices may communicate wirelessly with elements of the cellular communications network architecture .

In one embodiment the UTRAN subsystem includes one or more base stations and and a radio network controller RNC . In one embodiment the base stations and may be an eNodeB. The UTRAN subsystem provides connectivity between the user endpoint devices and the core network . The UTRAN subsystem provides features such as packet scheduling radio resource control RRC and handover control via the RNC .

In one embodiment the core network includes a serving GPRS support node SGSN and a gateway GPRS support node GGSN for interacting with the internet . The GGSN serves as a gateway hiding UMTS internal infrastructures from an external network.

The core network is the backbone of the cellular communications network architecture . It should be noted that although various numbers of hardware equipment or network elements are illustrated the actual numbers of illustrated elements should not be interpreted as a limitation of the present disclosure. For example although two base stations and are illustrated the network architecture may include any number of base stations. In fact various additional network elements may actually exist but are not illustrated in .

Generally when the user endpoint device sends a wireless communication the wireless communication must travel through the GGSN that may potentially be located thousands of miles away from the user endpoint device . However the user endpoint device may be situated within a location and the content that the user endpoint device is trying to access may be located in a server e.g. a streaming media server a server e.g. a music server or a server e.g. a security server that is located near the user endpoint device. As a result using current wireless communication protocols the wireless communication would travel thousands of miles away through the GGSN and then travel thousands of miles back to access the content on one of the servers or that is actually located near the user endpoint device .

Due to the complexity and costs associated with the GGSN only a limited number of GGSNs is deployed across the country. To resolve this problem a GGSN light can be deployed closer to the user endpoint device . For example the GGSN light may be located near broadly geographically close to the user endpoint device the base station or the RNC or the SGSN all of which are typically located near the user endpoint device .

In one embodiment a GGSN light broadly a reduced function GGSN may perform only a subset of the functions of the GGSN to reduce complexity and cost thereby allowing the GGSN light to be deployed easily across many locations. For example the GGSN light may perform functions such as supporting communications with an SGSN and the GGSN and supporting protocols to transfer tunnels from the GGSN to the GGSN light . The GGSN light may exclude traditional functions of the GGSN such as for example an authentication function a firewall function and an internet protocol assignment function.

In this manner many GGSN lights may be deployed across the country. For example a GGSN light may be deployed near a user endpoint UE device and a content server at a location . Another GGSN light may be deployed near a user endpoint UE device and a content server at a location . The locations and are all different from one another and are geographically located far away from one another and the GGSN . Although only three GGSN lights and at three different locations and are illustrated it should be noted that any number of GGSN lights may be deployed at any number of different locations.

Each one of the locations and may communicate with the GGSN using their own respective base station RNC and SGSN not shown similar to the base station the RNC and the SGSN at location . One embodiment of the present disclosure is discussed with respect to location for simplicity but it should be noted that the examples discussed herein may be equally applicable to other locations such as locations and as well.

Referring back to the GGSN initially establishes a tunnel to communicate with the user endpoint device after the user endpoint device is authenticated by the GGSN . Then based upon the content of a data packet in the tunnel the GGSN may re direct or hand off the tunnel to the GGSN light as illustrated by line .

In one embodiment the content of the data packet may be analyzed via a traffic analyzer application programming interface API . The traffic analyzer may be configured as a separate module that is located before the GGSN or as part of the GGSN . In one embodiment the data packet may be analyzed by looking at a packet data protocol PDP context. For example based upon the PDP context the type of content requested in the data packet may be determined. For example the PDP context may be modified to include fields that identify the type of content that is in the data packet.

In another embodiment the data packet may be analyzed by removing a header packet and then looking at a body of the data packet to determine the content. In one embodiment both methods of analyzing the data packet may be deployed.

Thus the wireless communication from the user endpoint device does not need to travel thousands of miles away to access content that is actually located near the user endpoint device . For example if the request is for a video content e.g. a YouTube video where YouTube is a trademark of Google Inc. the user endpoint device may access the streaming media server via the tunnel and the GGSN light . If the request is for a music file e.g. an Itunes file where Itunes is a trademark of Apple Computer Inc. the user endpoint device may access the music server via the tunnel and the GGSN light . In addition some of the processing load of the GGSN may be offloaded to the GGSN light .

In one embodiment the GGSN light may also offload some security features from the GGSN . For example if the GGSN determines that the data packet is a suspicious data packet the GGSN may re direct the tunnel to the GGSN light for further processing. The GGSN light may determine whether the suspicious packet should be filtered blocked or remain unchanged. Based upon the analysis performed by the GGSN light the GGSN light may further send the suspicious packet to a security server e.g. a black hole server if the suspicious packet is determined to be a security threat.

In one embodiment the GGSN may need to maintain communications with both the user endpoint device and the GGSN light . As a result a second tunnel may be optionally established. In other words one tunnel may be may be re directed e.g. the tunnel if necessary as shown by line while maintaining the second tunnel .

As a result re directing the tunnel optimizes the tunnel for the network architecture . In one embodiment optimizing can be defined as establishing a tunnel to a server the user endpoint device is trying to access via a GGSN light that is closest to the user endpoint device.

The GGSN lights may be deployed in accordance with various strategies to optimize the tunnels. For example the GGSN light may store copies of popular content such that each user endpoint device may have access to content closest to them via the GGSN light. In another example the GGSN light may store unpopular content e.g. tail ends of a distribution while the most popular content is accessed via the GGSN. The strategies described above are only examples and other strategies for deploying the GGSN light are possible which are within the scope of the present disclosure.

The cellular communications network architecture may also include additional hardware or network components that are not illustrated. In other words only illustrates a simplified cellular communications network architecture and should not be interpreted as a limitation of the present disclosure.

The method begins at step and proceeds to step . At step the method authenticates a user endpoint device. For example any standard authentication protocols may be used.

At step the method establishes a tunnel to the user endpoint device if the user endpoint device is authenticated. For example a GTP tunnel is established between the user endpoint device and the GGSN. Once the tunnel is established data packets may be transmitted via the tunnel.

At step the method analyzes content of a data packet transmitted through the tunnel to determine if the tunnel should be re directed. For example a traffic analyzer may be used to determine what type of content is being requested or what type of content is in the data packet. Based on the content type it may be possible to optimize the tunnel by re directing or handing off the tunnel.

At step the method re directs the tunnel to a GGSN light based upon the content of the data packet. As noted above if it is possible to optimize the tunnel by re directing the tunnel based upon the content of the data packet the tunnel is re directed to the GGSN light. In one embodiment optimization may be defined as establishing a tunnel to a server the user endpoint device is trying to access via a GGSN light that is closest to the user endpoint device. The method ends at step .

The method begins at step and proceeds to step . At step the method authenticates a user endpoint device. For example any standard authentication protocols may be used. At step the method establishes a tunnel to the user endpoint device if the user endpoint device is authenticated.

At step the method analyzes content of a data packet transmitted through the tunnel. For example a traffic analyzer application programming interface may be used to analyze the data packet. In one embodiment the traffic analyzer may be a separate module placed before the GGSN or a part of the GGSN.

In one embodiment the data packet may be analyzed by looking at a PDP context. For example based upon the PDP context the type of content requested in the data packet may be determined. The PDP context may be modified to include fields that identify the type of content that is in the data packet.

In another embodiment the data packet may be analyzed by removing a header packet and then looking at a body of the data packet to determine the content. In one embodiment both methods of analyzing the data packet can be deployed.

In one embodiment if the content of the data packet is multi media content the method proceeds to step . Multi media content may include streaming video e.g. YouTube videos music files e.g. Itunes pictures and the like. If the content of the data packet is a suspicious data packet the method proceeds to step . If the data packet is neither multi media content nor a suspicious packet the method proceeds to step and then to step where the method ends.

Referring back to step after step the method proceeds to step where the method determines if optimization is possible. Some multi media packets may not be optimized for various reasons. For example the user endpoint device may already be near a GGSN and thus redirecting the tunnel to another GGSN light may not be necessary. Alternatively the content may not be accessible using any GGSN lights and therefore the wireless communication may still need to go through the GGSN. These are only a few examples and are not intended to be limiting to the present disclosure.

If optimization is not possible the method proceeds to step and ends. If optimization is possible the method may proceed to optional step where a second tunnel is established. As discussed above in some instances the GGSN may need to maintain communications with the GGSN light and or the user endpoint device.

At step the method re directs a tunnel to a GGSN light. It should be noted that if optional step was performed one of the two tunnels would be re directed to the GGSN light while maintaining the other tunnel with the GGSN.

As discussed above the GGSN light may perform a subset of the functions of the GGSN to reduce complexity and cost thereby allowing the GGSN light to be deployed easily across many locations. For example the GGSN light may perform all of the functions of the GGSN except an authentication function a firewall function and an internet protocol assignment function.

At step the method provides the user endpoint device access to content on a media server close to the user endpoint device via the re directed tunnel and the GGSN light. The method ends at step .

Referring back to step if the data packet is a suspicious data packet the method proceeds to step . At step the method determines if optimization is possible. For example the GGSN may find that analyzing the packet may be more efficiently performed by a GGSN light to offload some processing from the GGSN.

If optimization is not possible the method proceeds to step and ends. However if optimization is possible the method may proceed to optional step where a second tunnel is established. As discussed above in some instances the GGSN may need to maintain communications with the GGSN light and or the user endpoint device.

At step the method re directs a tunnel to a GGSN light for analysis. It should be noted that if optional step was performed one of the two tunnels would be re directed to the GGSN light while maintaining the other tunnel with the GGSN. The GGSN light may determine if the suspicious data packet should be filtered blocked or unchanged. For example if the suspicious data packet poses a security threat the suspicious data packet may be filtered or blocked.

At step the method sends the suspicious data packet to a security server if the suspicious data packet is a security threat. For example the suspicious data packet may be sent to a black hole server via the GGSN light. The method proceeds to step and ends.

It should be noted that although not explicitly specified one or more steps of the methods described herein may include a storing displaying and or outputting step as required for a particular application. In other words any data records fields and or intermediate results discussed in the methods can be stored displayed and or outputted to another device as required for a particular application. Furthermore steps or blocks in that recite a determining operation or involve a decision do not necessarily require that both branches of the determining operation be practiced. In other words one of the branches of the determining operation can be deemed as an optional step.

It should be noted that the present disclosure can be implemented in software and or in a combination of software and hardware e.g. using application specific integrated circuits ASIC a general purpose computer or any other hardware equivalents. In one embodiment the present module or process for performing content aware optimized tunneling in a communication network can be loaded into memory and executed by processor to implement the functions as discussed above. As such the present method for performing content aware optimized tunneling in a communication network including associated data structures of the present disclosure can be stored on a non transitory computer readable storage medium e.g. RAM memory magnetic or optical drive or diskette and the like.

While various embodiments have been described above it should be understood that they have been presented by way of example only and not limitation. Thus the breadth and scope of a preferred embodiment should not be limited by any of the above described exemplary embodiments but should be defined only in accordance with the following claims and their equivalents.

