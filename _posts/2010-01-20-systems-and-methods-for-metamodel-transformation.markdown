---

title: Systems and methods for metamodel transformation
abstract: Some aspects relate to systems and methods to receive a first metamodel conforming to a first meta-metamodel associated with first modeling unit types. A second metamodel conforming to a second meta-metamodel is generated based on the first metamodel and on a mapping between the first meta-metamodel and the second meta-metamodel, where the second meta-metamodel is associated with second modeling unit types, and where the first modeling unit types are different from the second modeling unit types.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08413109&OS=08413109&RS=08413109
owner: SAP AG
number: 08413109
owner_city: Walldorf
owner_country: DE
publication_date: 20100120
---
Some embodiments relate to the use of object models within an application platform. More specifically some embodiments relate to the transformation of a first metamodel conforming to a first meta metamodel of a first application platform to a second metamodel where the second metamodel conforms to a second meta metamodel supported by a second application platform.

According to conventional business software terminology a business object is an object model representing real world items used during the transaction of business. For example a business object may represent a business document such as a sales order a purchase order or an invoice. A business object may also represent items such as a product a business partner or a piece of equipment. Particular documents e.g. SalesOrder SO435539 and or items e.g. ACME corporation are represented by instances of their representing business object or business object instances.

A business process platform such as the Application Platform provided by SAP of Walldorf Germany provides application programming interfaces for read and write access to business object instances. Notably each specific business object i.e. object model conforms to a same metadata model or metamodel . As a result a business process platform may employ similar application programming interfaces services and persistencies to support all instances of each specific business object.

As described in commonly assigned co pending U.S. application Ser. No. 12 339 339 a business process platform may include other metamodels describing technical entities such as but not limited to a Web Service a view a floorplan i.e. a user interface layout a work center UI texts and process components. Each metamodel including the business object metamodel may in turn conform to a same meta metamodel. More specifically each metamodel may comprise an instance of a same meta metadata model.

Some application development tools e.g. Eclipse based tools operate based on specific metamodels e.g. Eclipse Modeling Framework EMF models . These metamodels are also instances of a specific meta metamodel e.g. eCore . As such these tools are unable to utilize metamodels which conform to different meta metamodels. In some cases the native meta metamodel e.g. eCore of a development tool exposes the same modeling unit types as another meta metamodel e.g. UML . Accordingly desired metamodels of the other meta metamodel may be directly mapped to metamodels of the native meta metamodel for use by the development tool.

The foregoing approach is unsuitable in a case that the meta metamodel of the desired metamodels does not expose the same modeling unit types as the native meta metamodel of a development tool.

First metamodel is an instance of the first meta metamodel and second metamodel is an instance of the second meta metamodel. Moreover the first meta metamodel is associated with first modeling unit types and the second meta metamodel is associated with second modeling unit types which are different from the first modeling unit types. For example in some embodiments the first meta metamodel is the SAP APM3 meta metamodel and the second meta metamodel is the eCore meta metamodel.

The elements of system may be embodied using any combination of hardware and or software that is or becomes known. For example metamodel transformation engine may comprise a general purpose computer processor executing program code stored on a tangible medium to provide the functions described herein. Moreover data store may comprise a database storing data and or executable program code for facilitating the above described transformation.

Data storage device may comprise any appropriate information storage device including combinations of magnetic storage devices e.g. magnetic tape and hard disk drives optical storage devices and or semiconductor memory devices such as Random Access Memory RAM devices and Read Only Memory ROM devices.

Data storage device stores program code for execution by processor . Metamodel transformation engine may comprise a set of such code and may be executed by processor to cause system to operate as described above with respect to metamodel transformation engine of . This operation may initially include operation of communication device to receive a first metamodel from an external system.

Data storage device also stores mappings between meta metamodels . Mappings may include mappings between first and second meta metamodels associated with different modeling unit types as well as mapping between one or more other pairs of meta metamodels e.g. between the first meta metamodel and a third meta metamodel between a fourth meta metamodel and a fifth meta metamodel . Mappings may comprise any combination of data and or executable code.

Process and all other processes mentioned herein may be embodied in processor executable program code read from one or more of a tangible computer readable medium such as a floppy disk a CD ROM a DVD ROM a Zip disk and a magnetic tape and then stored in a compressed uncompiled and or encrypted format. In some embodiments hard wired circuitry may be used in place of or in combination with program code for implementation of processes according to some embodiments. Embodiments are therefore not limited to any specific combination of hardware and software.

Initially a first metamodel conforming to a first meta metamodel is received. As described in the Background the first metamodel may represent a business object or a technical entity such as a Web Service a view a floorplan i.e. a user interface layout a work center UI texts and a process component. Process may be initiated to facilitate usage of the first metamodel within an application development tool.

The first meta metamodel of the first metamodel is associated with first modeling unit types. Table of lists modeling unit types i.e. Node Node Element Action Query Association Business Object of a first meta metamodel according to some examples. Continuing with the above example the first meta metamodel represented in may be the SAP APM3 meta metamodel.

Next at S a second metamodel conforming to a second meta metamodel is generated. The second metamodel is generated based on the first metamodel and on a mapping between the first meta metamodel and the second meta metamodel. The second meta metamodel is associated with second modeling unit types which are different from the first modeling unit types.

Table illustrates lists modeling unit types i.e. Class Attribute Operation Association Packet of a second meta metamodel according to some examples. The second meta metamodel represented in may be the eCore meta metamodel.

Table also represents a mapping between the modeling unit types of the first and second meta metamodels. Generally mapping rules specify how to generate instances of the class modeling unit type based on instances of the node modeling unit type of the first metamodel to generate instances of the attribute modeling unit type based on instances of the node element modeling unit type of the first metamodel etc.

For example and according to some embodiments of S each MetaObject representing the first metamodel is mapped to a package representing a second metamodel. The MetaObject name is converted to lower case to generate the package name. The namespace prefix of the package is the same as the package name. The MetaObject namespace e.g. http sap.com xi Metamodel is concatenated with the name of the MetaObject namespace Uniform Resource Indicator to generate the namespace Uniform Resource Indicator of the package.

In a particular example the first metamodel is represented by the MetaObject ProcessComponent. Accordingly a package name namespace prefix and namespace Uniform Resource Indicator are generated at S as processcomponent processcomponent and http sap.com xi Metamodel ProcessComponent http sap.com xi Metamodel ProcessComponent respectively. Each package resides in an eCore file which is named based on the name of the package e.g. processcomponent.ecore . An EMF genmodel is also generated for each package to include metadata for code generation associated with the second metamodel.

The package includes a class representing each node of the first metamodel. Except for the class representing the root node a class name is identical to the name of the node it represents. The class name representing the root node shares the name of the MetaObject e.g. ProcessComponent . In the case of the eCore meta metamodel a data type that defines the node structure is not needed.

Node elements of the first metamodel which are not associated with complex types are mapped to attributes of the second metamodel. According to some embodiments the specified attribute properties include Changeable false if node element is read only EType EBoolean for indicators EString otherwise EInt constraints e.g. restricted length Name i.e. node element name Lower Bound i.e. according to cardinality and Upper Bound i.e. according to cardinality .

A node element associated with a complex data type is mapped to a reference and a class that represents the complex data type. Continuing with the present example the following reference properties are specified Changeable false if node element is read only Containment always true EType i.e. name of the class that represents the complex type Name i.e. node element name Lower Bound i.e. according to cardinality and Upper Bound i.e. according to cardinality .

The name of the second metamodel class i.e. representing the complex type is determined by the data type name. The classes representing complex types reside either in a metamodel package e.g. namespace http sap.com xi Metamodel or in a global package e.g. namespace http sap.com xi BASIS Global .

As further shown in table associations of the first metamodel may be mapped to references of the second metamodel. The references are uni directional and are located at the class representing the source node. The following reference properties may be specified Changeable false if node association is read only Containment true for composite associations false otherwise EType i.e. name of the class that represents the target node Name i.e. association name at the source node Lower Bound i.e. according to cardinality and Upper Bound i.e. according to cardinality .

More specifically tool development environment is used to develop business tools applications based on metamodels of a native meta metamodel which will be referred to as the second meta metamodel. Environment may access AP backend to retrieve metamodels therefrom. Metamodels conform to a first meta metamodel associated with modeling unit types which are different from the modeling unit types of the second meta metamodel. Accordingly tool development environment is unable to use metamodels in their stored format.

Metamodel importer plug in of environment may therefore implement system apparatus and or process to transform a first metamodel of metamodels to a second metamodel of the second meta metamodel. According to some embodiments the transformation results in eCore metamodel file and EMF genmodel file the contents of which are known in the art.

Environment may then access and utilize the resulting eCore metamodel file and EMF genmodel file using native processes. For example is a outward view of user interface provided by environment according to some embodiments. A developer may manipulate user interface to access metamodels and develop tools based thereon.

For example pane of interface allows a developer to select from native metamodels i.e. Package Explorer and non native metamodels of a non native meta metamodel i.e. SAP Explorer . Upon selection of a non native metamodel the remaining areas of interface present a second metamodel which conforms to the native meta metamodel and which has been generated as described above based on the selected non native metamodel and on a mapping between the non native meta metamodel and the native meta metamodel.

During runtime of a tool developed using such a generated metamodel runtime component may access model data of AP backend which corresponds to the selected non native metamodel.

The above described block diagrams illustrate logical architectures for describing some embodiments and actual implementations may include more or different components arranged in any manner. Each device and method described herein may be implemented by any number of devices in communication via any number of other public and or private networks. Two or more of devices of may be located remote from one another and may communicate with one another via any known manner of network s and or a dedicated connection. Moreover each device may comprise any number of hardware and or software elements suitable to provide the functions described herein as well as any other functions. Other topologies may be used in conjunction with other embodiments.

The embodiments described herein are solely for the purpose of illustration. Those in the art will recognize other embodiments may be practiced with modifications and alterations limited only by the claims.

