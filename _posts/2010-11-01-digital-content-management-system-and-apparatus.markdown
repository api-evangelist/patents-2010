---

title: Digital content management system and apparatus
abstract: There are provided a digital content management apparatus which further embodies a digital content management apparatus used with a user terminal, and a system which protects the secrets of a digital content. The system and the apparatus are a real time operating system using a micro-kernel, which is incorporated in the digital content management apparatus as an interruption process having high priority. When a user uses the digital content, whether there is an illegitimate usage or not, is watched by interrupting the usage process. In the case where illegitimate usage is carried out, a warning is given or the usage is stopped. The decryption/re-encryption functions of the digital content management apparatus having the decryption/re-encryption functions are not restricted to the inside of the user apparatus. By providing the decryption/re-encryption functions between the networks, the exchange of secret information between different networks is secured. By using this apparatus for converting a crypt algorithm, information exchange is made possible between systems which adopt different algorithms.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08448254&OS=08448254&RS=08448254
owner: Intarsia Software LLC
number: 08448254
owner_city: Las Vegas
owner_country: US
publication_date: 20101101
---
This application is a continuation of U.S. application Ser. No. 10 013 507 filed Dec. 13 2001 now U.S. Pat. No. 7 827 109 which is a divisional of prior application Ser. No. 08 868 488 filed Jun. 3 1997 now U.S. Pat. No. 6 424 715 which is a continuation in part of prior applications Ser. No. 08 549 270 filed on Oct. 27 1995 now abandoned and prior application Ser. No. 08 573 958 filed on Dec. 13 1995 now U.S. Pat. No. 5 740 246 which in turn claim the benefit of priority of Japanese Appl. Nos. 6 264200 filed Oct. 27 1994 6 299835 filed Dec. 2 1994 and 06 309292 filed Dec. 13 1994. The disclosures of each of the above referenced applications are incorporated by reference herein in their entireties.

The present invention relates to a system for managing digital content specifically for managing a copyright of digital content claiming the copyright and for securing secrecy of digital content and also relates to an apparatus implementing the system.

In information oriented society of today a database system has been spread in which various data values having been stored independently in each computer so far are mutually used by computers connected by communication lines.

The information handled by the prior art database system is classical type coded information which can be processed by a computer and has a small amount of information or monochrome binary data like facsimile data at most. Therefore the prior art database system has not been able to handle data with an extremely large amount of information such as a natural picture and a motion picture.

However while the digital processing technique for various electric signals develops development of the digital processing art has shown progress for a picture signal other than binary data having been handled only as an analog signal.

By digitizing the above picture signal a picture signal such as a television signal can be handled by a computer. Therefore a multimedia system for handling various data handled by a computer and picture data obtained by digitizing a picture signal at the same time is recognized as a future technique.

Because hitherto widely spread analog content is deteriorated in quality whenever storing copying editing or transmitting it copyright issues associated with the above operations has not been a large problem. However because digital content is not deteriorated in quality after repeatedly storing copying editing or transmitting it the control of copyrights associated with the above operations is a large problem.

Because there is not hitherto any exact method for handling a copyright for digital content the copyright is handled by the copyright law or relevant contracts. Even in the copyright law compensation money for a digital type sound or picture recorder is only systematized.

Use of a database includes not only referring to the contents of the database but also normally effectively using the database by storing copying or editing obtained digital content. Moreover it is possible to transmit edited digital content to another person via on line by a communication line or via off line by a proper recording medium. Furthermore it is possible to transmit the edited digital content to the database to enter it as new digital content.

In an existing database system only character data is handled. In a multimedia system however audio data and picture data which are originally analog content are digitized to a digital content and formed into a database in addition to the data such as characters which have been formed into a database so far.

Under the above situation how to handle a copyright of digital content formed into a database is a large problem. However there has not been adequate copyright management means for solving the problem so far particularly copyright management means completed for secondary utilization of the digital content such as copying editing or transmitting of the digital content.

Although digital content referred to as software with advertisement or as freeware is generally available free of fee it is copyrighted and its use may be restricted by the copyright depending on the way of use.

In view of the above the inventor of the present invention has made various proposals thus far in order to protect a copyright of the digital content. In GB 2269302 and U.S. Pat. No. 5 504 933 the inventor has proposed a system for executing copyright management by obtaining a permit key from a key management center through a public telephone line and has also proposed an apparatus for that purpose in GB 2272822. Furthermore in EP 677949 and in EP 704785 a system has been proposed for managing the copyright of the digital content.

In these systems and apparatus those who wish to view encrypted programs request to view a program using a communication device to a management center via a communication line and the management center transmits a permit key in response to the request for viewing and charges and collects a fee.

Upon receipt of the permit key those who wish to view the program send the permit key to a receiver either by an on line or an off line means and the receiver which as received the permit key decrypts the encrypted program according to the permit key.

The system described in EP 677949 uses a program and copyright information to manage a copyright in addition to a key for permitting usage in order to execute the management of a copyright in displaying including process to sound storing copying editing and transmitting of the digital content in a database system including the real time transmission of digital picture content. The digital content management program for managing the copyright watches and manages to prevent from using the digital content outside the conditions of the user s request or permission.

Furthermore EP 677949 discloses that the digital content is supplied from a database in an encrypted state and is decrypted only when displayed and edited by the digital content management program while the digital content is encrypted again when stored copied or transmitted. EP 677949 also describes that the digital content management program itself is encrypted and is decrypted by the permit key and that the decrypted digital content management program performs decryption and encryption of the digital content and when usage other than storing and displaying of the digital content is executed the copyright information is stored as a history in addition to the original copyright information.

In U.S. patent application Ser. No. 08 549 270 and EP 0715241 relating to the present application there is proposed a decryption re encryption apparatus having configuration of a board PCMCIA card or an IC card for managing the copyright and a system for depositing a crypt key. Also a reference is made to apply the copyright management method to a video conference system and an electronic commerce system.

In U.S. patent application Ser. No. 08 549 271 and EP 709760 a system has been proposed wherein the protection of an original digital content copyright and an edited digital content copyright in case of the edited digital content using a plurality of digital contents is carried out by confirming the validity of a usage request according to a digital signature on an edit program by combining a secret key cryptosystem and a public key cryptosystem.

In U.S. patent application Ser. No. 08 573 958 and EP 719045 various forms have been proposed for applying the digital content management system to a database and a video on demand VOD systems or an electronic commerce.

In U.S. patent application Ser. No. 08 663 463 EP 746126 a system has been proposed in which copyrights on an original digital content and a new digital content are protected by using a third crypt key and a copyright label in case of using and editing a plurality of digital contents.

As can be understood from the digital content management systems and the digital content management apparatus which have been proposed by the inventor of the present invention described above the management of a digital content copyright can be realized by restricting encryption decryption re encryption and the form of the usage. The cryptography technology and the usage restriction thereof can be realized by using a computer.

In order to use the computer efficiently an operating system OS is used which supervises the overall operation of the computer. The conventional operating system OS used on a personal computer or the like is constituted of a kernel for handling basic services such as memory control task control interruption and communication between processes and OS services for handling other services.

However improvement in the functions of the OS which supervises the overall operation of computers is now being demanded where circumstances change on the computer side such as improved capability of microprocessors a decreased price of RAMs Random Access Memory used as a main memory as well as improvement in the performance capability of computers is required by users as a consequence the scale of an OS has become comparatively larger than before.

Since such an enlarged OS occupies a large space itself in the hard disk stored OS the space for storing the application programs or data needed by the user is liable to be insufficient with the result in which the usage convenience in the computer becomes unfavorable.

In order to cope with such a situation in the latest OS an environmental sub system for performing emulation of other OS and graphics displaying and a core sub system such as a security sub system are removed from the kernel as a sub system that is a part that depends on the user. The basic parts such as a HAL hardware abstraction layer for absorbing differences in hardware a scheduling function an interruption function and an I O control function is a micro kernel and a system service API Application Programming Interface is interposed between the sub system and the micro kernel thereby constituting the OS.

By doing so extension of the OS by change or addition of functions will be improved and portability of the OS can be facilitated corresponding to the applications. By a distributed arrangement for elements of the micro kernel to a plurality of network computers the distributed OS can also be realized without difficulty.

Computers are used in computer peripheral units various control units and communication devices in addition to the personal computers represented by the desktop type or notebook type computers. In such a case as an OS unique for embedding applicable to each of the devices a real time OS is adopted in which execution speed is emphasized unlike in a general purpose personal computer OS in which the man machine interface is emphasized.

Naturally the development cost for a respective OS unique to each device embedded will be high. There has recently been proposed therefore that a general purpose OS for personal computers as a real time OS for embedding is used instead. By arranging a specified program for embedding in a sub system combined with the micro kernel a real time OS for embedding can be obtained for embedding.

As the major functions of an OS there is a task control such as scheduling interruption processing and the like. With respect to task control there are two kinds of OS s the single task type in which only one task is executed at the same time and the multi task type in which a plurality of task processes are executed at the same time. The multi task type is further classified into two kinds one multi task type changing of tasks depends on the task to be executed and the other multi task type the changing does not depend on the task to be executed.

In the aforementioned single task type the single task type assigns one process to a CPU Central Processing Unit and the CPU is not released until the process comes to an end and a non preemptive multi task type performs time division for the CPU and the CPU can be assigned to a plurality of processes. As long as the process which is being executed does not give control back to the OS other processes are not executed. And a preemptive multi task type interrupts the process which is being executed during a certain time interval and thereby forcibly move the control to another process. Consequently real time multi task can be available only in the case of the preemptive type.

Task control in a computer is performed according to processes being units having system resources such as a memory and a file. Process control is performed according to a thread being a unit in which CPU time is assigned in which the process is minutely divided. Incidentally in this case the system resources are shared in all the threads in the same process. More than one threads therefore may exist which share the system resources in one process.

Each task which is processed by the multi task type has a priority spectrum which is generally divided into 32 classes. In such a case a normal task without interruption is classified into dynamic classes which are divided into 0 to 15 classes while a task performing interruption is classified into real time classes divided into 16 to 31 classes.

Interruption processing is carried out using interruption enabling time generally 10 milliseconds referred to as a time slice as one unit. A normal interruption is carried out during a time slice of 10 milliseconds. In such a situation a time slice has recently been proposed wherein the interruption enabling time is set to 100 microseconds. When such a real time slice is used an interruption can be carried out with greater priority than the conventional 10 milliseconds.

In the present application there is proposed a digital content management apparatus which further embodies a digital content management apparatus which can be used with the user terminal proposed in EP 704785 for managing a digital content specifically a copyright of the digital content claiming the copyright. And also there is proposed a system to which the idea applied to the digital content management apparatus is further applied to secrecy protection of the digital content.

In the present application a system for watching the illegitimate usage of the digital content and an apparatus therefor are proposed. These system and apparatus are a real time operating system using a micro kernel and are incorporated in the digital content management apparatus as an interruption process having a high priority or are arranged in a network system using the digital content. It is watched whether an illegitimate usage or not by interrupting into the use process when a user utilizes the digital content. In the case where illegitimate usage is performed a warning or a stop for the usage is given.

Furthermore in the present application decryption re encryption functions in the digital content management apparatus having the decryption re encryption functions are not restricted within the user apparatus but are provided in a gateway or a node between the networks so that the exchange of secret information is secured between different networks.

By using the apparatus according to the present invention for the conversion of crypt algorithm information exchange can be made possible between systems which adopt different crypt algorithms.

The present invention is a copyright management system and an apparatus for digital content. In the following description numerous specific details are set forth to provide a more thorough description of the present invention. It will be apparent however to one skilled in the art that the present invention may be practiced without these specific details. In other instances well known features have not been described in detail so as not to obscure the present invention.

The description of the preferred embodiments according to the present invention is given below referring to the accompanied drawings.

In this digital content management system illustrated in reference numerals and represent databases stored text data binary data of a computer graphics screen or a computer program and digital content of sound or picture data which are not encrypted. represents a communication network constituted of using a public telephone line offered by a communication enterprise or a CATV line offered by a cable television enterprise represents a primary user terminal represents a secondary user terminal represents a tertiary user terminal and represents an n order user terminal and represents a digital content management center.

On the above arrangement the databases the digital content management center primary user terminal secondary user terminal tertiary user terminal and n order user terminal are connected to the communication network .

In this Figure a path shown by a broken line represents a path for transferring encrypted digital content a path shown by a solid line represents a path for transferring requests from each of the user terminals to the digital content management center a path shown by a one dot chain line represents a path through which a permit key corresponding to a usage request a digital content management program and a crypt key are transferred from each of the databases and the digital content management center to each of the user terminals .

This digital content management system employs a first public key Kb a first private key Kv corresponding to the first public key Kb a second public key Kb and a second private key Kv corresponding to the second public key Kb that are prepared by the user and a first secret key Ks and a second secret key Ks prepared by the database. The database encrypts digital content M by using the first secret key Ks 1 1 and further encrypts the first secret key Ks by the first public key Kb 11 1 1 and the second secret key Ks by the second public key Kb 22 2 2 .

The database then transfers these encrypted digital content Cmks the first and second secret keys Cks and Ck to the user.

The user decrypts the encrypted first secret key Cks using the first private key Kv 1 1 11 and decrypts the encrypted digital content Cmks by the decrypted first secret key Ks 1 1 and uses it. The user decrypts encrypted second secret key Cks by the second private key Kv 2 222 which is subsequently used as a crypt key for storing copying or transferring digital content.

If the primary user copies digital content obtained and then supplies it to the secondary user the digital content does not involve the copyright of the primary user because no modifications have been made to the digital content. If however the primary user produces new digital content based on the digital content obtained or using a means for combining with other digital content the new digital content involves a secondary copyright for the primary user and the primary user has the original copyright for this secondary work.

Similarly if the secondary user produces further new digital content based on the digital content obtained from the primary user or combining with other digital content the new digital content involves a secondary copyright for the secondary user and the secondary user has the original copyright of this secondary work.

Databases and store text data binary data constituting computer graphics screens or programs and digital content such as digital audio data and digital picture data which are encrypted and supplied to the primary user terminal via network during a digital content read operation in response to a request from the primary user terminal .

Managing the digital content obtaining from the database is carried out by the method described in Japanese Patent Laid open No. 185448 1996 or in Japanese Patent Laid Open No. 287014 1996 which have been proposed by the present inventor.

Recently a PCI Peripheral Component Interconnect bus has attracted attention as means for implementing a multiprocessor configuration in a typical personal computer. The PCI bus is a bus for external connection connected to a system bus of a personal computer via a PCI bridge and allows to implement a multiprocessor configuration.

The digital content includes graphics data computer programs digital audio data still picture data by JPEG and also moving picture data by MPEG 1 or MPEG 2 in addition to character data. In case that the digital content to be managed is moving picture data by JPEG still picture system or moving picture data by MPEG 1 or MPEG 2 as having remarkably large amount of data with high speed managing the digital content by a single processor is difficult.

The digital content management apparatus comprises a first digital content management apparatus connected to a user terminal and a second digital content management apparatus .

The first digital content management apparatus has a computer configuration having a MPU MicroProcessor Unit a local bus of MPU ROM Read Only Memory connected to the local bus RAM and EEPROM Electrically Erasable Programmable Read Only Memory .

A PCI bus is connected to a system bus for a microprocessor via a PCI bridge and the local bus for the MPU of the digital content management apparatus is connected to the PCI bus and also a local bus for MPU of the digital content management apparatus . Also connected to the system bus of the user terminal are a communications device COMM which receives digital content from external databases and transfers digital content to the external of the terminal a CD ROM drive CDRD which reads digital content supplied on CD ROM a flexible disk drive FDD which copies received or edited digital content in a flexible disk to supply to the external of terminal and hard disk drive HDD used for storing digital content. COMM CDRD FDD and HDD may also be connected to the PCI bus . While ROM RAM etc. of course are connected to the system bus of the user terminal these are not shown in .

The decryption and re encryption operations are performed by either of the MPU of the first digital content management apparatus and the MPU of the second digital content management apparatus i.e. one performs decryption and the other performs re encryption at the same time. Since the configuration of the MPU and MPU in is a multiprosessor configuration which performs parallel processing with a PCI bus high processing speed can be achieved.

In the digital content management apparatus shown in the storage medium such as HDD for storing re encrypted digital content is connected to the system bus of the user terminal . In order to store re encrypted digital content therefore the encrypted digital content must be transferred by way of the system bus of the user terminal and the local bus or of the digital content management apparatus or and consequently processing speed can be slowed.

In the digital content management apparatus shown in a communications device COMM and a CD ROM drive CDRD are connected to a local bus of a digital content management apparatus for decryption and a storage device such as HDD for storing re encrypted digital content are connected to the local bus of a digital content management apparatus for re encryption.

The digital content management apparatus for decryption has the computer system configuration having a MPU a local bus for the MPU and ROM RAM and EEPROM connected to the local bus and a communication device COM and a CD ROM drive CDRD are connected to the local bus . The encrypted digital content supplied from the communication device COM and the CD ROM drive CDRD are decrypted in this apparatus.

The digital content management apparatus for re encryption has the computer system configuration having a MPU a local bus for the MPU and ROM RAM and EEPROM connected to the local bus and HDD is connected to the local bus . The digital content which has been re encrypted in the digital content management apparatus for re encryption is stored in HDD .

In the protection of a digital content copyright the greatest issue is how to prevent from illegitimate usage of the digital content on the user side apparatus. Decryption re encryption and restriction on usage are carried out by a digital content management program for this purpose.

However since decryption re encryption of the digital content to be protected the copyright is performed using an apparatus on the user side it is virtually impossible to expect that processing of the decryption re encryption and the management of the crypt key which is used for the purpose will be complete. There is a possibility that the digital content will be illegitimately stored copied transmitted and edited by invalidating the digital content management program.

In order to restrict such illegitimate usage it is required that a digital content management program for decryption re encryption of the digital content and for managing the crypt key cannot be altered by the user. For this purpose incorporation of the digital content management program into the hardware is the most secure method.

For example there is a configuration in which a dedicated scramble decoder is currently used for descrambling scrambled broadcast programs in analog television broadcast so that decryption re encryption of the digital content and management of the crypt key are available only by using a dedicated digital content management apparatus.

Although such a configuration is reliable the system structure is lacking in flexibility. When the apparatus on the user side is changed or the digital content management program is changed it is very hard for the user to respond to such changes. In case of a network computer on which has been recently focused since the network computer does not have a function for storing the digital content management program it would be impossible to realize the digital content management program in the hardware.

In order to correspond with flexibility to a case where the apparatus on the user side changes or a case where the digital content management program is changed it is desirable for the digital content management program to be software. However there is a possibility that the digital content management program is altered as long as the digital content management program is an application program.

For the digital content management program being software the digital content management program is required to be incorporated in a kernel that is a fixed area and cannot be altered by the user. However it is not practical for the digital content management program to be incorporated in the fixed area of a kernel where the digital content management system and the cryptosystem are differentiated between the databases.

As described above some real time OS can perform interruption in real time slice time which is one or two Figures faster than the time slice of the system in another OS that includes kernel area. By using this technology the usage status of the digital content which is claiming the copyright is watched without affecting the overall operation. And if an illegitimate usage is found it is possible to give a warning or to forcibly stop the usage thereof.

Next a method for reinforcing a digital content management program by using a real time OS is described.

The digital content management apparatus shown in has a multi processor structure in which a first digital content management apparatus and a second digital content management apparatus are connected to an apparatus on the user side via a PCI bus. The decryption and re encryption operations of the first digital content management apparatus and the second digital content management apparatus are controlled by the digital content management program in the user terminal .

The digital content management program of the user terminal also manages the operation of the communication device the CD ROM drive the flexible disk drive and the hard disk drive which manage loading or downloading of encrypted digital content and storing into the hard disk drive copying to the flexible disk drive and uploading to the communication device of re encrypted digital content.

Since illegitimate usage of the digital content is carried out by unauthorized editing unauthorized storing unauthorized copying or unauthorized uploading of the decrypted digital content whether the illegitimate usage has been carried out or not can be detected by whether editing storing copying or uploading of the decrypted digital content is performed or not. As a consequence the process for watching the illegitimate usage interrupts a digital content use process which is being executed in a certain time interval while interrupting by a preemptive type multi task which forcibly carries out watching of the process.

The multi task time slice normally carried out is 10 milliseconds and the decryption re encryption process is carried out in this time unit. On the other hand the fastest real time slice is 100 microseconds which is 1 100 of the normal time unit. Consequently the watching task which has high interruption priority can watch the digital content as to whether the decrypted digital content is being edited stored copied or uploaded so that the usage status of the digital content for which the copyright is claimed can be watched without affecting regular usage by the user and a warning can be given and usage thereof can be forcibly stopped.

The digital content management program with such a watching function is incorporated into a sub system area which is operated in the user mode in place of the kernel of the OS and the watch process is regarded as a process with a high priority. By constituting the system in this way the usage status of the digital content by decryption re encryption and also the illegitimate usage other than the permitted usage can be watched at the same time and such watching can be executed smoothly.

The digital content management apparatus shown in has a multi processor structure in which a first digital content management apparatus and a second digital content management apparatus are connected to an apparatus on the user side via a PC1 bus. The decryption and re encryption operations of the first digital content management apparatus and the second digital content management apparatus are controlled by the digital content management program in the user terminal .

The digital content management program of the user terminal also manages the operation of the communication device the CD ROM drive the flexible disk drive and the hard disk drive which manage loading or downloading of encrypted digital content and storing into the hard disk drive copying to the flexible disk drive and uploading to the communication device of re encrypted digital content.

Since illegitimate usage of the digital content is carried out by unauthorized editing unauthorizing storing unauthorized copying or unauthorized uploading of the decrypted digital content it can be detected as to whether the illegitimate usage has been carried out or not by checking whether editing storing copying or uploading of the decrypted digital content is performed or not. As a consequence the process for watching the illegitimate usage interrupts a digital content use process which is being executed in a certain time interval while interrupting by a preemptive type multi task which forcibly carries out watching of the process.

The multi task time slice normally carried out is 10 milliseconds and the decryption re encryption process is carried out in this time unit. On the other hand the fastest real time slice is 100 s which is 1 100 of the normal time unit. Consequently the watching task which has high interruption priority can watch the digital content as to whether the decrypted digital content is being edited stored copied or uploads so that the usage status of the digital content for which the copyright is claimed can be watched without affecting regular usage by the user and if illegitimate usage is found a warning can be given and usage thereof can be forcibly stopped.

The digital content management program with such a watching function is incorporated into a sub system area which is operated in the user mode in place of the kernel of the OS and the watching process is regarded as a process with a high priority. By constituting the system in this way the usage status of the digital content by decryption re encryption and also the illegitimate usage other than the permitted usage can be watched at the same time and such watching can be executed smoothly.

Next a structure for watching the illegitimate usage of the digital content in the distributed OS is described referring to . illustrates a structure of a general distributed type OS in which servers to and clients to are connected to a network .

The network is a restricted network such as LAN Local Area Network in an office. Each of the servers to stores basic OS elements of the micro kernel application elements which are a sub system or the digital content. In order to manage the digital content the digital content management program which has been described so far is required. This digital content management program is stored for example in the server . And the watch program for watching the illegitimate usage of the digital content having a high priority for interruption is stored for example in the supervisory server for supervising the overall operation of the distributed Os.

Although the terminal apparatus of the clients to is a simple terminal the terminal is provided with a copying device such as a flexible drive or the like when necessary.

In such a structure when the clients to use the digital content which is stored in the servers to the clients to are supplied the micro kernel that is the basic OS elements from each of the servers and also supplied the digital content management program which is stored in the server and thus the digital content can be used.

The digital contents stored in the server are either encrypted or not encrypted. In either of these cases the digital content is supplied with encrypted when supplied to the clients. Therefore in order for the client to use the encrypted digital content it is necessary to obtain the crypt key and to decrypt by the digital content management program as has been described above.

The fact that the client uses the digital content and the digital content management program is grasped by the supervisory server . This watch process automatically interrupts the process which is being executed by the client at regular intervals without the client s request and watches and gives a warning or stop of the usage if an illegitimate usage is detected.

Since such a watch process can be completed with a process having a small size and therefore that affects little on the operation on the client side and the user does not notice the operation of the watch program.

In the distributed OS the servers and the clients have been explained as separated. However the aforementioned structure may be applied when a client machine is provided with a hard disk drive and the client machine also serves as the server machine. When the network is not a restricted one as LAN in a office but a non restricted one such as the Internet system the aforementioned structure can be also applied.

In particular such a structure is effective in a network computer system. Even in the case where the user modifies a computer not provided with a storage device a copying device or a communication device for transmission or use a normal computer pretending to be of a network computer system the digital content can be managed by remote control.

Furthermore the structure can be applied to the digital content management system shown in . In such a case the watch program is stored in the digital content management center of to regularly watch whether users illegitimately use the encrypted digital content supplied from the database through the network by remote control.

In case where the digital content is broadcast via analog data broadcast or via digital data broadcast the watch program may be transferred by inserting to the digital content. Also the watch program may be resident in an apparatus of the digital content user so that the remote control is made possible by periodically broadcasting watch program control signal.

In the case where the digital content having a large amount of information such as digital picture content is handled in the digital content management system which is carried out via the network an ISDN Integrated System for Digital Network line is used in many cases as a communication line.

As the ISDN line there are generally used two data channels having a data transmission speed of 64 Kbps Kilo bits per second referred to as B channels and a control channel having a data transmission speed of 16 Kbps referred to as D channel. Naturally the digital content is transmitted through one or two data channels while the D channel is not used in many cases.

Thus if the D channel is used for the interruption watching by the watch program it would be possible to watch the usage status by remote control without affecting the usage of the digital content at all.

When the user uses information to which a copyright is claimed the real time OS is automatically linked to the digital content management center it is also possible to watch and manage the re encryption mechanism with a real time OS as a result.

Further in the case where a digital content creator or an end user uses information to which a copyright is claimed a re encryption program resident in the PC uses the real time OS so that remote watching and management can be made possible.

Next application of the digital content management system to the prevention of the leakage of information is described. illustrates a structure of the system for preventing from the leakage of information by applying the system to an intranet system in which a LAN is connected to the Internet system.

In reference numerals and represent the network systems which are connected to each other by a public line . In particular the network system is a LAN system established in a office or the like. These network systems are connected with each other via a public communication line or the like to constitute an Internet system as a whole. Clients are connected to the LAN system and servers not shown in the Figure are connected in addition.

The LAN system has secret data such as business secrets and the like therein. Since the LAN system is connected to the outside network the problems of the leakage of the secret information to the outside or of the access to the secret information from the outside may arise. As a consequence although an information partition called a fire wall is normally provided between the LAN system and the public line that is not technologically perfect. Also even in the case of the business secret data it may be necessary to supply the business secret data to another party where the another party network has a common interest and in such a case the presence of the fire wall becomes an obstacle.

As has been described repeatedly the management of the secret data can be completely carried out through encryption. In the case where the crypt algorithm used in the other party network is common with the algorithm used in the one s own network the secret data can be shared by sending the crypt key to the other party by some means. In the case where the crypt algorithm used in the other party network is different from the algorithm which is used in one s own network such means cannot be adopted.

In order to cope with such a problem crypt key conversion devices and are arranged in place of or together with the fire wall in the Internet system shown in . These crypt key conversion devices and have the same configuration as the digital content management apparatus which have been described by using and perform decryption re encryption by two different crypt keys.

For example the crypt key conversion device decrypts an encrypted data from the network and re encrypts the decrypted data by using the crypt key common to the whole Internet system. The crypt key conversion device which has received the re encrypted data decrypts the re encrypted data by using the crypt key common to the whole Internet system and re encrypts the decrypted data and supplies it to the client . By doing this the problem of sending the crypt key is alleviated.

These crypt key conversion devices and can be arranged in a gateway or a node which is used as a connection between networks. Further even in a closed network system other than the Internet which is a liberated system this system functions efficiently in such cases where individual information such as reliability information medical information or the like is handled and where access to the data is necessary to differ by levels.

These crypt key conversion devices also can be used so as to convert the crypt algorithm. There are plurality of crypt algorithms which are currently used or proposed. In the worst case a plurality of networks using different crypt algorithm respectively coexist and thus compatibility is lost which becomes an obstacle to the development of the information oriented society. Even if a new effective crypt algorithm is developed and if it has not compatibility with the existing crypt algorithm an obstacle to the development of the information oriented society may similarly be brought.

In order to cope with such problems the crypt algorithm can be converted by arranging the crypt key conversion devices and of in the gateway on the network. These crypt algorithm conversion devices decrypt the encrypted data to be re encrypted with a different crypt algorithm.

For example the crypt algorithm conversion device decrypts the data which is encrypted by a crypt algorithm unique to the network and re encrypts the decrypted data by a crypt algorithm which is common in the whole Internet system. The crypt algorithm conversion device that has received the re encrypted data decrypts the re encrypted data encrypts the decrypted data by the crypt algorithm unique to the network and supplies it to the client .

By doing so it becomes possible to handle the encrypted data between networks that adopt different crypt algorithms. Here there may be two cases one is a case in which the crypt key is not changed at all and the other is a case in which the crypt key is changed at each stage.

In using databases in a case where a data storing server referred to as proxy server or cache server is used and where the digital content is encrypted the crypt key or crypt algorithm used between a data server and the proxy server may be differentiated from the crypt key or crypt algorithm used between the proxy server and a user and then the conversion of them is carried out by using the crypt key conversion device or crypt algorithm conversion device so that the encrypted digital content can be prevented from illegitimate usage thereof.

The conversion of the crypt algorithm by these devices can be effected by units of countries. Even in the case where crypt algorithms are used which differ from one country to another it becomes possible to adopt a key escrow system unique to the respective country or a key recovery system using the key escrow system.

It is understood that particular embodiments described herein are illustrative and the present invention is not limited to these particular embodiments. It will be apparent to those skilled in the art that changes can be made in the various details described herein without departing from the scope of the invention. The present invention is defined by the claims and their full scope of equivalents.

