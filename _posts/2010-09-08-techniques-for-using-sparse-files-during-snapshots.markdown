---

title: Techniques for using sparse files during snapshots
abstract: Techniques for using sparse files during snapshots are provided. Snapshots are managed and maintained for a source volume via sparse files. Metadata defines the sparse files and operations of a file system are used to create, define, and manipulate the metadata. When a write operation is detected during a snapshot, sparse files are used to copy the write operation before the write operation is performed on the source volume; the sparse files server as the snapshot data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08880820&OS=08880820&RS=08880820
owner: Novell, Inc.
number: 08880820
owner_city: Provo
owner_country: US
publication_date: 20100908
---
Enterprises go to great lengths to ensure that their data is properly backed up and always available online. Information has become the lifeblood of organizations and any access downtime whatsoever is problematic.

In addition many times an organization wants to maintain versions of its information so that desired states of the information can be acquired as needed. States of data or information is generally handled via snapshot technology.

To avoid delays associated with accessing primary data when that primary data is being backed up enterprises will back up snapshots of the primary data which are being maintained as read only copies of the primary data. So access to the primary data is always available even when the primary data is being actively backed up because the backup occurs off a snapshot.

A snapshot of a disk volume takes the original volume origin or source and a second volume as inputs and creates a new snapshot volume which is a virtual volume that uses both of these volumes underneath for its operations. This second volume is often referred to as a Copy On Write COW device. When there are multiple snapshots for the same origin volume then the complexity to manage the COW devices grows and many problems are encountered.

Some issues associated with managing and creating COW devices include fragmentation predicting size of COW devices in advance optimal use of disk space etc.

In various embodiments techniques for copying on write are presented. More specifically and in an embodiment a method for maintaining a snapshot of a source volume is provided. Specifically a write operation that is directed to a first block of data on a source volume is detected. Next metadata associated with a sparse file of a file system is accessed for purposes of locating a second block within the sparse file. The first block of data is copied to the second block within the sparse file and the first block of data is updated on the source volume by processing the write operation.

A resource includes a user service system device directory data store groups of users combinations of these things etc. A principal is a specific type of resource such as an automated service or user that acquires an identity. A designation as to what is a resource and what is a principal can change depending upon the context of any given network transaction. Thus if one resource attempts to access another resource the actor of the transaction may be viewed as a principal.

An identity is something that is formulated from one or more identifiers and secrets that provide a statement of roles and or permissions that the identity has in relation to resources. An identifier is information which may be private and permits an identity to be formed and some portions of an identifier may be public information such as a user identifier name etc. Some examples of identifiers include social security number SSN user identifier and password pair account number retina scan fingerprint face scan etc.

A processing environment defines a set of cooperating computing resources such as machines storage software libraries software systems etc. that form a logical computing infrastructure. A logical computing infrastructure means that computing resources can be geographically distributed across a network such as the Internet. So one computing resource at network site X and be logically combined with another computing resource at network site Y to form a logical processing environment.

Various embodiments of this invention can be implemented in existing network architectures. For example in some embodiments the techniques presented herein are implemented in whole or in part in the Novell network and proxy server products operating system products cloud based products or services directory based products and other products and or services distributed by Novell Inc. of Waltham Mass.

Also the techniques presented herein are implemented in machines such as processor or processor enabled devices. These machines are configured to specifically perform the processing of the methods and systems presented herein. Moreover the methods and systems are implemented and reside within a non transitory and computer readable or processor readable storage media and processed on the machines processing devices configured to perform the methods.

Of course the embodiments of the invention can be implemented in a variety of architectural platforms devices operating and server systems and or applications. Any particular architectural layout or implementation presented herein is provided for purposes of illustration and comprehension only and is not intended to limit aspects of the invention.

It is within this context that embodiments of the invention are now discussed within the context of .

At the COW service detects a write operation to a first block of data on a source volume. In other words a volume is being actively snapshotted and is being monitored and some volatile operation is issued for data located at the first block. Typically in a normal snapshot process the first block of data would be written to a second block on a second volume that is being used as a snapshot of the source or origin volume. However with the teachings presented herein the second or snapshot volume is not a volume set aside for snapshotting rather the second volume is a logical volume constructed as a sparse file using the file system.

Thus at the COW service accesses metadata associated with a sparse file of a file system to locate a second block of data defined and contained within the sparse file. A sparse file uses metadata to define unused space rather than actually reserving and occupying unused space. So the file system supports the notion of a sparse file and the metadata for the sparse file defines the space needed for the snapshot volume of the source volume but does not actually write or use empty space not in use by the snapshot volume. As used herein the phrase sparse file and snapshot volume may be used interchangeably because the sparse file is effectively being managed and used as a snapshot volume for the source volume.

According to an embodiment at the COW service manages the metadata as a matrix that maps blocks of data on the source volume to blocks of data on the file system having prior versions of those blocks of data. In other words when a block of data is modified or updated in some manner can include deleted any volatile operation on the source volume the previous pre update state or version of the data being modified is written to a block defined in the sparse file. The mapping of modified and unmodified blocks is defined via the matrix metadata .

Continuing with the embodiment of and at the COW service maps all blocks within the source volume to sparse blocks within the matrix via bits or via a bit flag for each block. So when a particular bit is set a corresponding block from the source volume exists in the sparse file. Conversely when a particular bit is unset then there is no corresponding block that exists in the sparse file within the file system. In other words only modified or previous versions of the data are recorded and housed in the sparse file if something is unmodified from the source volume it does not have to have empty space recorded in the sparse file at all.

Continuing with the embodiment of and at the COW service identifies specific blocks that exist within the sparse file that are discontinuous or fragmented within the file system from one another. Here the sparse file is a fragmented file that spans multiple discontinuous locations within the file system and the metadata helps properly reconstruct and re assemble as needed the sparse file to acquire the snapshot of the source volume.

In another case at the COW service sets a bit in the metadata that indicates the first block is updated and different on the source volume from that which is located at the second block within the sparse file. Again the metadata provides a mapping via its location within the metadata structure to a spot on the file system where the second block is to be found within the sparse file. That second block is a prior pre updated version of the first block of data as it appears on the source or origin volume.

At the COW service copies the first block of data to the second block within the sparse file. That is before the first block of data is modified or updated via some volatile operation detected at the COW service takes the contents of the first block of data as it appears before modification and writes it to a second block within the sparse file. So the source volume and the sparse file combine to provide snapshot services to users or consumers of the source volume by maintaining states of the source volume via the sparse file. This is the copy on write process used for snapshotting however what is different is an entire second snapshot volume is not reserved and being used rather a dynamically mapped and modified sparse file is used as a logical snapshot volume and existing file system operations are used to manage the metadata of that defines the sparse file.

At the COW service updates the first block of data on the source volume by processing the write volatile operation. Once the prior version of the first block of data is recorded in the sparse file at the second block the update to the first block of data on the source volume can occur. So if the source volume was in the process of being backed up when the volatile write operation was issued by a user the source volume is still capable of being backed up via the sparse file s second block of data while the user continues to access and modify the source volume. This provided uninterrupted access to the source volume even during a backup scenario. This is but one example of the benefits associated with snapshotting others include version control and the like.

According to an embodiment at the COW service receives a request to delete the sparse file. So the snapshot is being cleared from the file system. Here the COW service clears the metadata to delete the sparse file from the file system. That is only the definition of what comprises the sparse file metadata needs to be removed. This is more efficient then clearing a volume out for the next snapshot.

In another case at the COW service manages a second snapshot of the source volume as a different state of the source volume. The different state and second snapshot is managed by the COW service as a second sparse file within the file system. Each different state or version of the source volume can be managed via the file system as a different sparse file.

Continuing with the embodiment of and at the COW service creates different metadata within the file system to manage the second snapshot. In other words the second or different sparse file is managed via a different set of metadata via operations supported via the file system.

In an embodiment at the COW service manages the source volume and the sparse file as one logical volume where the sparse file is a logical snapshot volume on the file system. This has been explained in detail above. The prior state versions of the data from the source file are recorded dynamically and as needed within the sparse file and the metadata describes the locations and details for access the sparse file. The file system supports sparse files and sparse file operations so normal file system operations can be performed to managing the snapshot volume.

Continuing with the embodiment of and at the COW service detects a read request from the first block of data and provides the updated first block of data from the source volume. Here the read request is directed to the most recent version of the first block of data which is consistently maintained in the first block of data on the source volume.

An alternative to the embodiment of and at is where the COW service detects a read request for the first block of data and provides data located at the second block within the sparse file. Here the read request is directed to a specific version or state of the first block of data which is actively maintained in the sparse file via the second block of data.

The snapshot manager is another and different perspective of the COW service represented by the method of the .

At the snapshot manager configures a snapshot service to use a sparse file as a snapshot volume for a source volume. In some cases the snapshot service is the COW service represented by the method of the and discussed in detail above.

According to an embodiment at the snapshot manager initiates the snapshot service to use the file system operations for reading and writing from the sparse file as if the sparse file were the snapshot volume. In other words the snapshot service uses file system operations to manage the sparse file as the snapshot volume.

Continuing with the embodiment at and at the snapshot manager uses the file system operations to manage metadata that defines locations within the file system to reconstruct and dynamically assemble the snapshot volume as the sparse file. So at the snapshot manager can identify locations as being discontinuous and fragmented storage areas within the file system via the metadata.

At the snapshot manager manages the sparse file via a file system that supports the sparse file as the snapshot volume. The snapshot volume is for the source volume and the snapshot volume represents a particular state of the source volume that is being actively and dynamically maintained via the sparse file.

In an embodiment at the snapshot manager only dynamically acquires space on the file system for the sparse file when something is written by the snapshot service from the source volume to the snapshot volume. So empty space is not written to the sparse file although the empty space is identified and described via the metadata. This alleviates a lot of processing that normally would have to take place for snapshot volumes.

The COW snapshot system includes a snapshot service and a file system . Each of these will now be discussed in turn.

The snapshot service is implemented in and resides within a non transitory computer readable storage medium and executes on one or more processors of the network. The processors are configured to execute the snapshot service . Example processing associated with the snapshot service was presented in detail above with reference to the methods and of the respectively.

The snapshot service is configured to manage one or more snapshots of a source volume via sparse files that are created and managed via operations supported by the file system .

In an embodiment the source volume includes one unique sparse file for each independent snapshot maintained by the snapshot service .

In one situation each sparse file dynamically grows when written to by the snapshot service on an access basis.

In yet another scenario the snapshot service defines and manages each of the sparse files via metadata that a number of the operations for the file system define and manipulate.

The file system is implemented in and resides within a non transitory computer readable storage medium and executes on one or more processors of the network. Example aspects of the file system were presented above with reference to the methods and of the respectively.

The file system includes operations or an Application Programming Interface API for creating and managing sparse files. The snapshot service uses these operations or API to logically create and maintain a snapshot volume for the source volume each snapshot volume represented by a single sparse file.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

The Abstract is provided to comply with 37 C.F.R. 1.72 b and will allow the reader to quickly ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

