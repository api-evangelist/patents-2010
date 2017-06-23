---

title: Cluster computing—NIC based OS provision
abstract: A network interface card with read-only memory having at least a micro-kernel of a cluster computing operation system, a server formed with such network interface card, and a computing cluster formed with such servers are disclosed herein. In various embodiments, on transfer, after an initial initialization phase during an initialization of a server, the network interface card loads the cluster computing operation system into system memory of the server, to enable the server, in conjunction with other similarly provisioned servers to form a computing cluster. Other embodiments are also disclosed and claimed.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08688812&OS=08688812&RS=08688812
owner: Intel Corporation
number: 08688812
owner_city: Sant Clara
owner_country: US
publication_date: 20100923
---
Embodiments of the present disclosure relate to the field of data processing in particular to methods apparatuses and articles associated with provisioning cluster computing operating systems for heterogeneous servers of a computing cluster.

Unless otherwise indicated herein the materials described in this section are not prior art to the claims in this application and are not admitted to be prior art by inclusion in this section.

With continuing advances in integrated circuit and computing technology today scale out server clustering is becoming increasingly larger. Thus to be able to scale out efficiently is of increasing importance. Equally important is the enabling of each basic input output service BIOS vendor to support the various application programming interfaces APIs Unified Extensible Firmware Interface Rapid Boot and so forth. Unfortunately most computing platforms include mixtures of ingredients from different vendors that generally do not work well with each other. As a result under today s technology it is increasingly difficult to get servers of different vendors to work consistently or cohesively to form a computing cluster.

Methods components and systems associated with cluster computing are disclosed herewith. In embodiments a network interface card may be provided with a read only memory having stored therein a number of programming instructions configured to program the network interface card to provision a cluster computing operating system for a server hosting the network interface card. The programming instructions may be configured to implement at least a micro kernel of the cluster computing operating system.

In embodiments a method may include transferring control to a network interface card after an initial initialization period during an initialization of a server hosting the network interface card. In response the network interface card may load a copy of a cluster computing operating system into system memory of the host server. Thereafter execution control may be transferred to the cluster computing operating system to complete initialization. On completion of initialization cluster computing may ensue.

In embodiments the server and at least one other server have respective copies of the same or similar cluster computing operating systems and form a computing cluster. The server and the at least one other server may be heterogeneous provided by different vendors.

Various aspects of the illustrative embodiments will be described using terms commonly employed by those skilled in the art to convey the substance of their work to others skilled in the art. However it will be apparent to those skilled in the art that alternate embodiments may be practiced with only some of the described aspects. For purposes of explanation specific numbers materials and configurations are set forth in order to provide a thorough understanding of the illustrative embodiments. However it will be apparent to one skilled in the art that alternate embodiments may be practiced without the specific details. In other instances well known features are omitted or simplified in order not to obscure the illustrative embodiments.

Further various operations will be described as multiple discrete operations in turn in a manner that is most helpful in understanding the illustrative embodiments however the order of description should not be construed as to imply that these operations are necessarily order dependent. In particular these operations need not be performed in the order of presentation.

The phrase in one embodiment is used repeatedly. The phrase generally does not refer to the same embodiment however it may. The terms comprising having and including are synonymous unless the context dictates otherwise. The phrase A B means A or B . The phrase A and or B means A B or A and B . The phrase at least one of A B and C means A B C A and B A and C B and C or A B and C . The phrase A B means B or A B that is A is optional.

Still referring to servers may be coupled to one another and a gateway via a local area network . Gateway may in turn be coupled with public network . Local area network gateway and public network are intended to represent a broad range of these elements devices known in the art. In particular public network may include the Internet.

Similarly except for the teachings of the present disclosure servers are intended to represent a broad range of computer servers known in the art. While for ease of understanding four servers are illustrated in the present disclosure is not so limited. The present disclosure may be practiced with more or less servers in a computing cluster.

Additionally computing system may include bridge mass storage devices such as diskette hard drive compact disc read only memory CDROM or other non transitory computer readable storage medium and input output devices such as display keyboard cursor control and so forth coupled with each other and the earlier enumerated elements.

Each of these elements may perform its conventional functions known in the art. In particular system memory and mass storage may be employed to store a working copy and a permanent copy of the programming instructions implementing various applications . The cluster computing operating system and the various applications may be selectively implemented by assembler instructions supported by processor s or high level languages such as for example C that can be compiled into such instructions.

The permanent copy of the programming instructions of applications may be placed into permanent storage in the factory or in the field through for example a distribution medium not shown such as a compact disc CD or other non transitory computer readable storage medium or through NIC from a distribution server not shown . That is one or more distribution media having implementations of applications may be employed to distribute the applications and program various servers .

Except for the circuitry and or logic provided to support and or implement the initialization process of computer system server to be described more fully below the constitution of these elements and are known and accordingly will not be further described.

Referring now to wherein an initialization process suitable for the servers of according to various embodiments of the present disclosure is shown. As illustrated in the event of power on or reset the BIOS of a server may proceed to initialize the server i.e. initializing the various components of the server up to an option ROM scan stage . For ease of understanding this period may be referred to as the initial initialization phase during an initialization of the server. When the option ROM scan stage is reached the BIOS may proceed to transfer to the network interface card to continue initialization .

Upon transferring the network interface card may proceed to load a copy of the cluster computing operating system into the system memory of the server . In various embodiments where an entire copy of the cluster computing operating system is stored in the ROM of the network interface card the cluster computing operating system is copied into the system memory from the ROM of the network interface card. In other embodiments where only a micro kernel of the cluster computing operating system is stored in the ROM of the network interface card the rest of the cluster computing operating system may be copied into the system memory by the micro kernel from a remote server.

Upon copying the cluster computing operating system into the system memory the network interface card may transfer to the cluster computing operating system in system memory to continue initialization . On transfer the cluster computing operating system in system memory may complete initialization . Thereafter cluster computing may ensue with the server and at least one other server similarly provisioned forming a computing cluster.

Although specific embodiments have been illustrated and described herein it will be appreciated by those of ordinary skill in the art that a wide variety of alternate and or equivalent implementations may be substituted for the specific embodiments shown and described without departing from the scope of the embodiments of the present invention. This application is intended to cover any adaptations or variations of the embodiments discussed herein. Therefore it is manifestly intended that the embodiments of the present invention be limited only by the claims and the equivalents thereof.

