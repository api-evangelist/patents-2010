---

title: Characterizing artificiality in object code
abstract: One embodiment of the present invention provides a system that characterizes content in object code. During operation, the system receives the source code of a program. The system also receives one or more pieces of object code of the program, or creates one or more pieces of object code from the source code. Next, the system identifies a construct in the object code. The system then determines whether the construct is physically present in the source code. If the construct is not physically present, the system determines whether the construct is logically present in the source code, wherein a construct is logically present if it is required by the programming language. If so, the system sets a construct flag to indicate that the construct is “synthesized.” However, if not, the system sets the construct flag to indicate that the construct is “synthetic.” Finally, the construct flag is made available to a reflective API.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08843888&OS=08843888&RS=08843888
owner: Oracle America, Inc.
number: 08843888
owner_city: Redwood Shores
owner_country: US
publication_date: 20100126
---
The present invention relates to computer programming. More specifically the present invention relates to a method and an apparatus for characterizing artificiality in object code. The object code may have been produced by transforming a source language into object code via a compiler.

Computer programs are typically written in source code and then compiled into object code for execution on a specific platform or by a specific virtual machine. During the transformation from source code to object code some constructs from the source code are preserved in the resultant object code while other constructs may not be preserved. Furthermore the resultant object code typically incorporates constructs that were not present in the original source code such as implementation details specifying how the compiler implements the semantics of the programming language.

In many instances programmers find themselves in the situation where they have a collection of object code and they want to ask questions about the object code in terms of source code semantics. In these instances programmers often use reflective tools to analyze the object code to create corresponding source code or to answer their questions about the object code in terms of source code semantics if the source code is unavailable. Various techniques have been developed to help the programmer distinguish between constructs in the object code that correspond to constructs in the source code and constructs in the object code that associated with a specific compiler implementation.

For example the ClassFile format used by the JAVA Virtual Machine is able to flag classes fields and methods as synthetic. Note that the terms JAVA JVM and JAVA VIRTUAL MACHINE are trademarks of SUN Microsystems Inc. of Santa Clara Calif. The synthetic flag indicates that the class field method was generated implicitly by a compiler and does not appear in source code. This flag is typically used to mark ClassFile content that is an implementation detail of how the compiler implements the semantics of a programming language such as JAVA. As such in most cases a synthetic artifact should not be relied on by JAVA Virtual Machine implementations nor exposed by Application Programming Interfaces APIs nor manipulated by tools. Please note that in some instances certain synthetic artifacts can be relied upon to be created in a particular way.

Separately the semantics of a programming language sometimes mandate that artifacts be automatically provided if not written explicitly by the programmer. For example in the JAVA programming language a class has a default no args constructor if the programmer does not supply any constructor and an enum type has certain methods which are part of the type s public API but which cannot for safety reasons by written by a programmer. It is useful for a number of reasons to mark such artifacts in the ClassFile as implicitly generated. However this cannot be accomplished with the synthetic flag because the artifacts are not implementation details and should not be hidden in reflective APIs presenting a source level view.

One embodiment of the present invention provides a system for characterizing content in object code. During operation the system receives the source code of a program. Note that this can include receiving multiple pieces of source code as well as paths to other source material. The system also receives one or more pieces of object code of the program or creates one or more collections of object code from the source code. Next the system identifies a construct in the object code. The system then determines whether the construct is physically present in the source code. If the construct is not physically present the system determines whether the construct is logically present in the source code wherein a construct is logically present if it is required by the programming language. If so the system sets a construct flag to indicate that the construct is synthesized. However if not the system sets the construct flag to indicate that the construct is synthetic. Finally the construct flag is available to a reflective API.

In some embodiments of the present invention the construct can include any artifact in the object code that has a relationship to the programming language of the source code.

In some embodiments of the present invention the construct can include at least one of a piece of object code a method including constructors and static initializers a method parameter a field a local variable or an annotation.

In some embodiments of the present invention the system identifies a method in the object code. Next the system identifies a parameter of the method. The system then determines whether the parameter is physically present in the source code. If the parameter is not physically present the system determines whether the parameter is logically present in the source code. If so the system sets a parameter flag to indicate that the parameter is synthesized . However if not the system sets the parameter flag to indicate that the parameter is synthetic .

In some embodiments of the present invention the system sets the parameter flag to indicate that the parameter is natural if the parameter is physically present and logically present in the source code. Furthermore in some embodiments the system sets the parameter flag to indicate that the parameter is commentary if the parameter is physically present but not logically present in the source code.

In some embodiments of the present invention the system identifies a further parameter of the method wherein the further parameter is logically present at runtime but is neither physically present in the source code nor present in the object code. The system then sets a second parameter flag to indicate that the further parameter is implicit. 

In some embodiments of the present invention the system sets the construct flag to indicate that the construct is natural if the construct is physically present and logically present in the source code. Furthermore in some embodiments the system sets the construct flag to indicate that the construct is commentary if the construct is physically present but not logically present in the source code.

In some embodiments of the present invention constructs flagged as synthetic are suppressed by the reflective API.

In some embodiments of the present invention constructs flagged as synthesized are revealed by the reflective API.

In some embodiments of the present invention the program is a compiler. Note that in these embodiments the program receives the one or more pieces of object code by creating the one or more pieces of object code from the source code.

TABLE 1 presents the conditions associated with flags for constructs in the object code in accordance with an embodiment of the present invention.

TABLE 3 presents JAVA object code ClassFile C in accordance with an embodiment of the present invention.

TABLE 4 presents JAVA object code ClassFile C D in accordance with an embodiment of the present invention.

TABLE 5 presents JAVA object code ClassFile C 1 in accordance with an embodiment of the present invention.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a particular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. The computer readable storage medium includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing code and or data now known or later developed.

The methods and processes described in the detailed description section can be embodied as code and or data which can be stored in a computer readable storage medium as described above. When a computer system reads and executes the code and or data stored on the computer readable storage medium the computer system performs the methods and processes embodied as data structures and code and stored within the computer readable storage medium.

Furthermore the methods and processes described below can be included in hardware modules. For example the hardware modules can include but are not limited to application specific integrated circuit ASIC chips field programmable gate arrays FPGAs and other programmable logic devices now known or later developed. When the hardware modules are activated the hardware modules perform the methods and processes included within the hardware modules.

Embodiments of the present invention introduce a synthesized flag that allows a compiler to flag a class field or method in a ClassFile as implicitly generated because it is logically present in source code but not physically present in source code. Because the flagged artifact is logically present in source code it is not an implementation detail of the compiler. The existing synthetic flag then indicates true implementation details by adopting the meaning that it flags a class field or method that is not logically present in source code and not physically present in source code.

TABLE 1 presents the conditions associated with flags for constructs in the object code in accordance with an embodiment of the present invention. If a construct in the object code is flagged as natural the construct is both physically and logically present in the source code. As described previously if a construct in the object code is flagged as synthetic the construct is neither physically present nor logically present in the source code such as a compiler implementation detail.

One major advantage provided by embodiments of the present invention is to indicate when constructs in the object code are not physically present in the source code but are indeed logically present in the source code. These constructs are flagged as synthesized and may include constructs that are mandated by the programming language and are implicitly generated by the compiler.

Note that while some constructs may be physically but not logically present in the source code such as programmer comments they typically will not be found in the object code. However if they are preserved in the object code during compilation embodiments of the present invention can flag these constructs as well to indicate their original status in the source code.

While the description herein describes a compiler flagging the constructs during compilation embodiments of the present invention are not meant to be limited to the flagging of constructs by a compiler during compilation. In some embodiments the flagging may be applied by a separate program or mechanism. Furthermore it is possible for a programmer to create object code manually in a hex editor and to manually flag constructs. Less importance should be placed on how a construct is flagged and the focus should remain on the meaning of the flag for a construct.

One embodiment of the present invention provides a system for characterizing content in object code. During operation the system receives the programming language source code of a program. The system also receives one or more pieces of object code comprising the program or creates one or more pieces of object code from the source code. Next the system identifies a construct in the object code. The system then determines whether the construct is physically present in the source code. If the construct is not physically present the system determines whether the construct is logically present in the source code wherein a construct is logically present if it is required by the programming language. If so the system sets a construct flag to indicate that the construct is synthesized. However if not the system sets the construct flag to indicate that the construct is synthetic . Finally the construct flag is available to a reflective API.

Note that object code may refer to machine code that is executed directly or bytecode that is interpreted via an interpreter or virtual machine. In some embodiments of the present invention object code refers to any code other than the source code in the original programming language. For example in some embodiments the object code is a ClassFile or other suitable executable output capable of running the JAVA Programming Language.

In some embodiments of the present invention the construct can include any artifact in the object code that has a relationship to the programming language of the source code. For example the construct can include at least one of a piece of object code a method including constructors and static initializers a method parameter a field a local variable or an annotation. Note that this is not intended to be an exhaustive list of what a construct can include and is included for exemplary purposes only.

In some embodiments of the present invention the system identifies a method in the object code. Next the system identifies a parameter of the method. The system then determines whether the parameter is physically present in the source code. If the parameter is not physically present the system determines whether the parameter is logically present in the source code. If so the system sets a parameter flag to indicate that the parameter is synthesized . However if not the system sets the parameter flag to indicate that the parameter is synthetic . Examples of flagging parameters are provided in more detail with regard to the description of tables 2 5 below.

In some embodiments of the present invention the system sets the parameter flag to indicate that the parameter is natural if the parameter is physically present in the source code. Furthermore in some embodiments the system sets the construct flag to indicate that the construct is natural if the construct is physically present in the source code.

In some embodiments of the present invention the system identifies a further parameter of the method wherein the further parameter is logically present at runtime but is not physically present in the source code and not physically present in the object code. The system then sets a second parameter flag to indicate that the further parameter is implicit . For example at runtime every method includes a zero th parameter that refers back to itself. This zero th parameter is not physically present in either the source or the object code but is logically present at runtime.

In some embodiments of the present invention constructs flagged as synthetic are suppressed by the reflective API while constructs flagged as synthesized are revealed by the reflective API. Note that in some embodiments the construct flag is saved in the object code. This can be accomplished at compile time by the compiler or another program but it could also occur sometime after compile time.

TABLE 2 presents JAVA source code C.java in accordance with an embodiment of the present invention. C.java includes public class C as well as private class D.

In one embodiment of the present invention compiling C.java results in the following three files containing object code ClassFile C TABLE 3 ClassFile C D TABLE 4 and ClassFile C 1 TABLE 5 .

Source class C from C.java compiles to ClassFile C. Note that ClassFile C is NATURAL because it is physically present in both the source code and object code. Furthermore the compiler has added a no args constructor to ClassFile C which is flagged as SYNTHESIZED because it is not physically present in the source code but it is logically present in the source code.

Source class C.D from C.java compiles to ClassFile C D. Note that ClassFile C D is SYNTHESIZED because it is the executable embodiment of a source type C.D contained within the source for class C. There is no independent source file for type C.D. ClassFile C D is not physically present in the source code C.java but the type C.D is logically present in C.java.

C D s method is marked SYNTHESIZED because the JAVA language says source class C.D has a default no args constructor. Furthermore both parameters of should be marked SYNTHETIC because they are about connecting a C D object to a C object. These parameters are implementation details of the compiler and are not logically present in C.java.

ClassFile C D has a field this 0. C D s constructor sets this 0 to the parameter containing the reference to the enclosing C object. Note that this 0 is marked SYNTHETIC because it is logically present in C.java.

In ClassFile C D reading C s variable i is achieved by calling C.access 000 and passing C D s this 0 field which references an enclosing C object. Assigning C s variable i is achieved by calling C.access 002 and again passing this 0. C.access 000 and C.access 002 methods are marked SYNTHETIC.

ClassFile C 1 is the synthetic secret class used to ensure private communication between ClassFile C and ClassFile C D. C 1 is flagged as SYNTHETIC because it is an implementation detail of the compiler and is not logically present in the source code C.java.

Clients can include any node on a network including computational capability and including a mechanism for communicating across the network. Additionally clients may comprise a tier in an n tier application architecture wherein clients perform as servers servicing requests from lower tiers or users and wherein clients perform as clients forwarding the requests to a higher tier .

Similarly servers can generally include any node on a network including a mechanism for servicing requests from a client for computational and or data storage resources. Servers can participate in an advanced computing cluster or can act as stand alone servers. In one embodiment of the present invention server is an online hot spare of server .

Users and can include an individual a group of individuals an organization a group of organizations a computing system a group of computing systems or any other entity that can interact with computing environment .

Network can include any type of wired or wireless communication channel capable of coupling together computing nodes. This includes but is not limited to a local area network a wide area network or a combination of networks. In one embodiment of the present invention network includes the Internet. In some embodiments of the present invention network includes phone and cellular phone networks.

Database can include any type of system for storing data in non volatile storage. This includes but is not limited to systems based upon magnetic optical or magneto optical storage devices as well as storage devices based on flash memory and or battery backed up memory. Note that database can be coupled to a server such as server to a client or directly to a network.

Devices can include any type of electronic device that can be coupled to a client such as client . This includes but is not limited to cell phones personal digital assistants PDAs smart phones personal music players such as MP3 players gaming systems digital cameras video cameras portable storage media or any other device that can be coupled to the client. Note that in some embodiments of the present invention devices can be coupled directly to network and can function in the same manner as clients .

Appliance can include any type of appliance that can be coupled to network . This includes but is not limited to routers switches load balancers network accelerators and specialty processors. Appliance may act as a gateway a proxy or a translator between server and network .

Note that different embodiments of the present invention may use different system configurations and are not limited to the system configuration illustrated in computing environment . In general any device that is capable of executing computer instructions may incorporate elements of the present invention.

Furthermore note that some embodiments of the present invention include an apparatus such as system for performing these flagging techniques automatically without the assistance of a human. In some embodiments the object code is not human readable code and the flagging technique requires the use of the apparatus.

Next identification mechanism identifies a construct in the object code operation . As described previously the construct can include any artifact in the object code that has a relationship to the programming language of the source code. This can include sub artifacts such as method parameters. Determination mechanism then determines whether the construct is physically present in the source code operation . Determination mechanism also determines whether the construct is logically present in the source code if the construct is not physically present operation .

Once the determinations have been made flagging mechanism sets a construct flag to indicate that the construct is synthesized if the construct is logically present in the source code and not physically present in the source code operation . Additionally flagging mechanism sets the construct flag to indicate that the construct is synthetic if the construct is not logically present in the source code and not physically present in the source code operation . Next if the construct is physically present in both the source code and the object code and is logically present in the source code flagging mechanism sets the construct flag to indicate that the construct is natural operation . Finally if the construct is physically present in both the source code and the object code and is not logically present in the source code flagging mechanism sets the construct flag to indicate that the construct is commentary operation .

Note that the construct flags can be implemented in numerous ways depending on the programming language in question. Also note that the various construct states are mutually exclusive by nature.

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

