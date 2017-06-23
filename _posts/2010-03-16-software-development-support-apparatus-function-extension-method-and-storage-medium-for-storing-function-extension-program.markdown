---

title: Software development support apparatus, function extension method and storage medium for storing function extension program
abstract: A software development support apparatus includes: a class memory unit which stores a class for generating a unit object which carries out predetermined processing; an object generating unit which reads the class and generates the unit object; an annotation analysis unit which determine whether the class includes annotation information; and an extended-function execution unit which carries out an extended-function object corresponding to the class. When the annotation analysis unit determines that the class includes the annotation information, the object generating unit generates the extended-function object based on the annotation information, and when the unit object to the class is called from a predetermined application and carried out, the extended-function execution unit carries out the extended-function object to the class.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08621429&OS=08621429&RS=08621429
owner: NEC Corporation
number: 08621429
owner_city: Tokyo
owner_country: JP
publication_date: 20100316
---
This application is based upon and claims the benefit of priority from Japanese Patent Application No. 2009 096290 filed on Apr. 10 2009 the disclosure of which is incorporated herein in its entirety by reference.

The present invention relates to a software development support apparatus a function extension method and a storage medium for storing a function extension program.

Nowadays the idea of EoD Ease of Development is spreading in Java the registered trademark of Sun Microsystems incorporated hereinafter the same meaning shall apply . EoD is a specification policy of Java that everyone can perform Java development easily. In particular specifications about implementation of an application in which a business logic such as EJB Enterprise Java Beans and Servlet is included have begun to be provided. By utilizing annotation information these specifications make developer s work simplified and light weighted as far as possible.

Here as a technology related to a scheme to utilize annotation information there are a method disclosed in Japanese Patent Application Laid Open No. 2008 210059 patent document 1 and a method disclosed in Japanese Patent Application Laid Open No. 1997 222974 patent document 2 for example.

According to the method disclosed in patent document 1 an analyzer has a structure which extracts annotation information embedded in a method definition section in a source code and converts the annotation information into a form that can be evaluated on a debugger. By a developer defining a specific conditional expression as annotation information the analyzer can make debugging work when abnormality happening in a program efficient.

Also according to a method disclosed in patent document 2 an analyzer has a structure which extracts annotation information embedded in HTML Hyper Text Makeup Language and a display apparatus has a structure which customizes information to be displayed on a screen based on the information. This annotation information is described as a comment in HTML. The display apparatus can analyze this annotation information. By this structure the display apparatus keeps backward compatibility about display of HTML data in which annotation information is embedded. The display apparatus can customize display based on the annotation information.

An exemplary object of the invention is to provide a software development support apparatus a function extension method and a storage medium for storing a function extension program which can make coding related to JMX Java Management Extensions or the like be simplified and can make processing which is customized more highly and more in detail than the JMX specification be carried out.

A software development support apparatus according to an exemplary aspect of the invention includes a class memory unit which stores a class for generating at least one unit object which carries out predetermined processing an object generating unit which reads the class and generates the unit object an annotation analysis unit which determines whether or not the class includes annotation information which indicates an attribute of the class or operation to the class and an extended function execution unit which carries out an extended function object corresponding to the class wherein when the annotation analysis unit determines that the class includes the annotation information the object generating unit generates the extended function object which adds to the class an attribute of the class or operation to the class indicated by the annotation information on an occasion of generating the unit object and wherein when the unit object corresponding to the class is called from a predetermined application and carried out the extended function execution unit carries out the extended function object corresponding to the class.

A function extension method according to an exemplary aspect of the invention includes storing a class for generating at least one unit object which carries out predetermined processing reading the class and generating the unit object determining whether or not the class includes annotation information which indicates an attribute of the class or operation to the class generating an extended function object which adds to the class an attribute of the class or operation to the class indicated by the annotation information on an occasion of generating the unit object when it is determined that the class includes the annotation information and carrying out the extended function object corresponding to the class when the unit object corresponding to the class is called from a predetermined application and carried out.

A storage medium storing thereon a program product according to an exemplary aspect of the invention causing a computer to execute steps of storing a class for generating at least one unit object which carries out predetermined processing reading the class and generating the unit object determining whether or not the class includes annotation information which indicates an attribute of the class or operation to the class generating an extended function object which adds to the class an attribute of the class or operation to the class indicated by the annotation information on an occasion of generating the unit object when it is determined that the class includes the annotation information and carrying out the extended function object corresponding to the class when the unit object corresponding to the class is called from a predetermined application and carried out.

Next a software development support apparatus a software development support system a function extension method and a storage medium for storing a function extension program in each exemplary embodiment of the present invention will be described with reference to the drawings.

Meanwhile a software development support apparatus indicated in the following each exemplary embodiment operates on a computer controlled by a program. CPU of the computer sends an order to each component of the computer based on a program. Then the computer makes each component perform predetermined processing needed for operation of the software development support apparatus. Such predetermined processing includes such as processing of generating a unit object processing of analyzing annotation information included in a class processing of generating an extended function object based on an analysis result of annotation information and processing of carrying out an extended function object for example. Thus individual processing and operation in a software development support apparatus of each exemplary embodiment of the present invention can be realized by a specific means in which a program and a computer cooperate.

A program is stored in the storage medium such as ROM Read Only Memory and RAM Random Access Memory in advance. This program is read from the storage medium mounted on a computer to be carried out. And for example this program may be read by a computer via a communication line.

The storage medium for storing a program may be constituted by a semiconductor memory a magnetic disk an optical disk or any recording means which is computer readable for example.

The first exemplary embodiment of the present invention relates to a software development support apparatus a software development support system a function extension method and a storage medium for storing a function extension program which performs function extension of JMX. JMX is a standard specification for monitoring and managing an application and a system device using Java.

First the configuration of this exemplary embodiment will be described with reference to . is a block diagram showing a structure of a software development support system Java operations management system of this exemplary embodiment. is a block diagram showing a structure of a software development support apparatus Java operations management apparatus of this exemplary embodiment. is a diagram illustrating a class in Java. is a diagram showing an instantiation of MBean in this exemplary embodiment. is a block diagram showing a structure of an MBean container of this exemplary embodiment. and are diagrams showing an example of an annotation file in this exemplary embodiment. is a diagram showing a code example in MBean class in this exemplary embodiment. is a diagram showing a code example in MBean class in related technology.

A software development support system of this exemplary embodiment is used as a Java operations management system for example. As shown in a software development support system of this exemplary embodiment includes a software development support apparatus Java operations management apparatus and an administrator terminal . A job application in a user terminal includes a structure which can access EJB Enterprise Java Beans and Servlet in the software development support apparatus

The MBean . . . in the software development support apparatus is called from an operations management application in the administrator terminal . Then the MBean inputs information from an EJB container and a web container . Accordingly a software development support system includes a structure which manages EJB . . . and Servlet . . . .

According to this exemplary embodiment when the software development support apparatus generates such MBean an annotation analysis unit analyzes annotation information in the MBean class and an MBean container generates an extended function of the MBean automatically. By this when the MBean is called the MBean container can carry out the extended function of the MBean

Annotation information is information which indicates the content of a predetermined extended function. and are diagrams showing an example of an annotation file which is included in the annotation information memory unit in this exemplary embodiment. An annotation file is a file including annotation information. Referring to the annotation information memory unit includes annotation files and . The annotation file is an annotation file which indicates configuration information on the MBean . An annotation file is an annotation file for monitoring an attribute value which the MBean has. An annotation file an annotation file for carrying out optional processing by interrupting before and after a Java method is called. An annotation file is an annotation file which indicates an effective area of a parameter which has been handed to an argument of a Java method. Referring to the annotation information memory unit includes annotation files and . The annotation file is an annotation file for synchronization of change information. An annotation file is an annotation file including a parameter about an attribute stored in a descriptor area. An annotation file is an annotation file including a parameter about operation stored in a descriptor area.

For example in and a character string which continues following and a character string enclosed in parentheses are annotation information the underlined portions of and . In this specification method information which is information about each Java method included in the MBean class is referred to as management information. Among the management information information which can be updated by a getter method or a setter method that are a public method is referred to as attribute information. Among the management information information about public methods besides a getter method and a setter method are referred to as operational information. In this specification public methods besides a getter method and a setter method are referred to as an operation method .

This annotation information may include such as information which indicates a structure of the MBean and information which indicates an attribute and operation of the MBean . In the examples of and StandardMBean Constructor is information which indicates a structure of the MBean . Also Attribute Monitor DependenceAttribute is information which indicates an attribute of the MBean . Operation is information which indicates operation of the MBean . Interceptors AroundInvoke Validate is information which indicates an attribute and operation of the MBean

As shown in the MBean container generates MBeanInfo . . . corresponding to the MBean automatically using annotation information on an occasion of generation of the MBean . Because the operations management application in the administrator terminal can refer to that annotation information the operations management application can manage the MBean easily.

The software development support apparatus Java operations management apparatus of this exemplary embodiment may be constructed by an information processing apparatus in the server side for managing an application server and a server application which monitors such as a process or a computer. For example the software development support apparatus of this exemplary embodiment may be constructed by a Web server an application server or the like of a Java base. Such a web server an application server or the like of a Java base plays the role as a Java virtual machine.

The JMX agent includes a comprehensive service which manages the MBean . The JMX agent is a managed entity Managed Entity carried out in the software development support apparatus . Connection of the JMX agent is made between the MBean and the job application or the EJB . . . the Servlet . . . or the like which is called by the job application so that it is possible to communicate with each other.

As shown in the JMX agent includes an MBean server and one or more service in the example of . . . and .

The MBean server manages the MBean . The MBean server is a core component of the JMX agent . The MBean server includes a structure which functions as a repository of the MBean for the operations management application in the administrator terminal to access the MBean

The service is a means to carry out predetermined general purpose processing. According to the JMX specification the JMX agent needs to include the predetermined number of the service

In this exemplary embodiment this service carries out processing for storing other specific MBeans and the like generated on an occasion of generation of the MBean to a predetermined memory unit in the MBean server for example.

The MBean is an MBean instance which the MBean container generates based on the MBean class and which conforms to JMX API Application Program Interface . The MBean is a unit object which is a management objective. In the example of the MBean inputs information from the EJB container and the web container . Inputted information may be log information on various processing carried out based on a request from the job application or may be such as the number of current objects of the EJB . . . the Servlet . . . or the like and the number of calls of such objects for example.

In the JMX specification once the MBean is stored in a predetermined MBean memory unit of the software development support apparatus the MBean container may carry out the MBean based on a request from a JMX client. Meanwhile this MBean memory unit is not illustrated and the MBean is included in the MBean container in this exemplary embodiment. However an MBean memory unit which stores the MBean may be provided outside the MBean container or it may be arranged inside the MBean container

The MBean class is for generating the MBean . The MBean container reads the MBean class and generates one or more MBean corresponding to the MBean class

The MBean container generates a class file . A class file includes a code which indicates the MBean class . A class file in Java generally means either one of the following two as shown in .

 1 A class file is a file of a text format in which class definition is described according to the specification of the Java language in a form readable by human beings. Alternatively a class file is a file of a text format in which class definition is coded according to the specification of the Java language in a form readable by human beings. In this case the file name of this file will be .java.

 2 A class file is a data file which is made by converting translating the above mentioned file into a binary form that can be carried out on a Java virtual machine through applying a tool named a compiler to the file . Such a file is taken into a Java process by a class loader of Java. In this case the file name of the file will be .class.

The class loader has a function to take data class data included in any class file of Java into a Java process a function for generating an instance and a function for initializing based on the data taken in. Also the class loader has a function for storing and managing all class data taken in. In this exemplary embodiment a memory unit in this class loader is an MBean class memory unit

Conversion work to a form that can be carried out by a compiler is generally called compilation . In Java there are following two kinds of compilation methods mainly.

 2 By a server Java virtual machine reading a text file class file which is not yet converted and performing a compilation processing dynamically the text file which has been read is converted to a file of an executable form.

Note that although a class file is of a form executable on a Java virtual machine annotation information and the like can be incorporated in data class data of the class file. The annotation analysis unit in this exemplary embodiment may be arranged such that it can analyze such incorporated annotation information. In this exemplary embodiment it is assumed that a method of compilation indicated by 1 is used. However a method of compilation is not limited to this.

The MBeanInfo is an object which is generated along with the MBean on an occasion of generation of the MBean with being correlated to each MBean . The MBeanInfo includes information about a structure an attribute and operation of the MBean that is a management objective. The operations management application in the administrator terminal can access this MBeanInfo and refer to the content of the MBeanInfo

As a result the operations management application can manage the MBean . The operations management application can also manage the EJB . . . and the Servlet . . . which are management objectives of the MBean

The MBean container is an object management means which generates and stores various objects and operates various objects or attribute data and the like of the various objects.

The MBean container generates the MBean and the MBeanInfo based on the MBean class as well as an extended function object corresponding to the MBean . The MBean container carries out a generated extended function object.

As shown in the MBean container includes the MBean class memory unit an MBean generating unit the annotation information memory unit an extended function memory unit an MBean extended function correspondence table and an extended function execution unit

The MBean class memory unit stores the MBean class . As this MBean class memory unit the class loader may be used as mentioned above.

The MBean generating unit reads the MBean class from the MBean class memory unit . Then the MBean generating unit generates the MBean corresponding to the MBean class which has been read.

The annotation analysis unit analyzes annotation information included in the MBean class and the MBean generating unit generates the MBeanInfo which includes this annotation information.

At that time the annotation analysis unit refers to the annotation information memory unit in the MBean container . The annotation analysis unit determines whether annotation information being stored in this annotation information memory unit exists in the MBean class

The annotation information memory unit is a means to store annotation information and it stores an annotation file which includes annotation information as shown in and for example.

When annotation information is included in the MBean class the annotation analysis unit outputs the annotation information to the MBean generating unit

When the MBean generating unit receives annotation information from the annotation analysis unit the MBean generating unit determines whether this annotation information includes information about a predetermined extended function. A developer may set information about a predetermined extended function in advance. For example in the example of it is supposed that Monitor and Interceptors correspond to information about a predetermined extended function.

When the annotation information includes information about a predetermined extended function the MBean generating unit generates one or more extended function objects based on the annotation information. The MBean generating unit stores the generated extended function objects to the extended function memory unit and stores correlating information between the MBean and the extended function objects to the MBean extended function correspondence table

The extended function memory unit stores the extended function objects generated by the MBean generating unit

The MBean extended function correspondence table stores identification information of the MBean and identification information of the extended function objects corresponding to this MBean in a form that they are correlated.

The extended function execution unit watches whether the MBean is called from the operations management application .

When the MBean is called from the operations management application by referring to the MBean extended function correspondence table the extended function execution unit identifies extended function objects corresponding to the MBean . The extended function execution unit acquires the identified extended function objects from the extended function memory unit and carries out the acquired extended function objects.

The extended function objects which the extended function execution unit acquires may be carried out as soon as the MBean is called or may be carried out at predetermined timing after the MBean is called.

As mentioned above in this exemplary embodiment the extended function execution unit identifies extended function objects corresponding to the MBean called from the operations management application by referring to the MBean extended function correspondence table . However the extended function execution unit is not limited to the aforementioned structure. For example when the extended function memory unit stores an extended function object with identification information of the MBean corresponding to the extended function object the MBean container does not have to include the MBean extended function correspondence table

When the MBean container generates the MBean based on a request from the MBean generating unit the annotation analysis unit analyzes annotation information included in the MBean class . The annotation analysis unit returns an analysis result of this annotation information to the MBean generating unit . When the MBean class includes annotation information this analysis result includes the annotation information.

Then the MBean generating unit generates the MBean along with the MBeanInfo including the annotation information. The MBean generating unit generates an extended function object which carries out an extended function corresponding to the annotation information. The MBean generating unit stores the extended function object to the extended function memory unit

In a character string which continues following like Attribute is an annotation definition in annotation information. A character string enclosed in parentheses like description The sample value of this MBean. which is coded continuously after an annotation definition is the body of annotation information.

In this exemplary embodiment annotation definition and a body of annotation information are collectively called annotation information.

In related technology as shown in an underline part of a developer needs to code about an extended function object itself in order for an MBean generating unit to generate an extended function object.

In contrast according to this exemplary embodiment a developer codes such that the MBean class includes annotation information corresponding to that MBean class . Then the MBean generating unit generates the MBean by using the MBean class including such annotation information.

As a result the MBean container can generate an extended function object in addition to the MBean on an occasion of generating the MBean . In the example of the extended function object is monitor dedicated MBean JMX monitor MBean generated based on annotation information Monitor type CounterMonitor.class granularityPeriod 10000 . Generation of this monitor dedicated MBean will be described later.

The MBean container generates the MBeanInfo which includes annotation information along with the MBean . In the example of annotation information about StandardMBean Attribute Monitor and Operation is included in the MBean class . Such annotation information is analyzed by annotation analysis unit in turn.

The class file of the MBean class in the example of includes the above mentioned annotation information and pieces of information which indicate three methods of getSampleValue setSampleValue and reset respectively. In order for the operations management application to be able to refer to annotation information corresponding to the MBean the MBean container generates the MBeanInfo

Thus the software development support apparatus according to this exemplary embodiment can generate MBean or the like which is customized more highly and more in detail than the JMX specification with a less code amount.

Next a processing procedure in the software development support apparatus of this exemplary embodiment will be described with reference to and . and are flow charts showing a processing procedure of MBean generation in the software development support apparatus of this exemplary embodiment.

The MBean class memory unit in the MBean container stores the MBean class corresponding to the MBean which is a generation target in advance.

Specifically as shown in the file of the MBean class is inputted to the class loader including the MBean class memory unit and the class loader may memorize the inputted binary file.

Then as shown in the annotation analysis unit analyzes annotation information included in this MBean class Step S .

Next when annotation information includes information about a predetermined extended function the MBean generating unit carries out the following processing as shown in . That is the MBean generating unit generates an extended function object corresponding to the MBean class and the annotation information based on the annotation information and stores the extended function object to the extended function memory unit . Specifically the MBean generating unit adds a new Java instance. The MBean generating unit stores information which indicates correlation of the MBean and the generated extended function object to the MBean extended function correspondence table Step S .

The processing of Step S is performed for all pieces of annotation information included in the MBean class

Further as shown in the MBean generating unit generates the MBean and also generates the MBeanInfo corresponding to the MBean

At that time the MBean generating unit completes this MBeanInfo by making annotation information which is included in the MBean class included in the MBeanInfo Step S .

Note that the order of generation of an extended function object in Step S and generation of the MBean and the MBeanInfo in Step S may be exchanged.

Next a processing procedure in the software development support apparatus of this exemplary embodiment will be described more in detail with reference to and . are flow charts showing a generation processing procedure of the MBean a calling processing procedure of the MBean and a function extension processing procedure of synchronization of change information in a software development support system of this exemplary embodiment in this order.

A developer creates an optional MBean class according to JMX API Java Management Extensions Application Programming Interface in advance of processing in the software development support apparatus of this exemplary embodiment.

On this occasion instead of coding extended functions a developer codes optional annotation information corresponding to the respective functions. In such case a developer codes individual pieces of annotation information so that they may be included in a class file of the MBean class in a state being correlated to a method a field a constructor and the like in the MBean class respectively.

Then the MBean generating unit instantiates the MBean class created by the developer as mentioned above and generates the MBean . The MBean generating unit stores the generated MBean to an MBean memory unit in the MBean server in the JMX agent . Then an MBean execution unit reads and carries out the MBean stored in the MBean memory unit based on a request from the operations management application . Meanwhile in such as the MBean memory unit is not illustrated.

When generating the MBean the MBean generating unit reads the MBean class from the MBean class memory unit included in a class loader Step S . Then the MBean generating unit generates the MBean and the MBeanInfo corresponding to this MBean class Step S . At that time the MBeanInfo does not include annotation information yet.

Next the annotation analysis unit determines whether the MBean class includes annotation information or not Step S . When the annotation analysis unit determines that the MBean class does not include annotation information NO at Step S the MBean generating unit finishes processing after adding predetermined basic information to the MBeanInfo

When the annotation analysis unit determines that the MBean class includes annotation information YES at Step S the annotation analysis unit carries out analysis processing of annotation information Steps S S . This analysis processing of such annotation information is repeatedly carried out the number of times corresponding to the number of the method included in the MBean class

On this occasion the annotation analysis unit analyzes the annotation information and determines whether information about a structure an attribute operation and the like of the MBean is included in the annotation information Step S .

When the annotation analysis unit determines that the annotation information does not include information about a structure an attribute operation and the like of the MBean NO at Step S the MBean generating unit carries out the following processing. That is the MBean generating unit finishes processing after adding predetermined basic information to the MBeanInfo

On the other hand when the annotation analysis unit determines that the annotation information includes such information YES at Step S the MBean generating unit carries out the following processing. That is when the annotation information includes information about predetermined extended functions the MBean generating unit generates one or more extended function objects corresponding to the information about the predetermined extended functions. The MBean generating unit stores the generated extended function objects to the extended function memory unit Step S .

The MBean generating unit performs processing of Steps S S repeatedly for each method indicated by the annotation information on the MBean class Step S . The MBean generating unit adds predetermined basic information to the MBeanInfo and finishes processing.

At Step S when the annotation information includes information about a predetermined extended function for information monitoring refer to the annotation file of for example the MBean generating unit generates a monitor dedicated MBean JMX monitor MBean and stores the monitor dedicated MBean to the extended function memory unit

When the operations management application calls the MBean corresponding to the monitor dedicated MBean stored in the extended function memory unit the extended function execution unit carries out the monitor dedicated MBean.

Next processing for calling the MBean in the software development support apparatus of this exemplary embodiment will be described with reference to and . is a flow chart showing a calling processing procedure of the MBean in a software development support system of this exemplary embodiment.

When the operations management application of the administrator terminal calls the MBean via the MBean execution unit the MBean execution unit outputs to the extended function execution unit information which indicates that the MBean has been called and the MBean execution unit carries out the MBean

At this occasion when interrupt processing interceptor which is for being performed before processing by the MBean exists as an extended function corresponding to the MBean YES at Step S the extended function execution unit identifies an extended function object. Specifically the extended function execution unit refers to the MBean extended function correspondence table and identifies the extended function object corresponding to the MBean for carrying out the interrupt processing. Then the extended function execution unit acquires the identified extended function object from the extended function memory unit and carries out interrupt processing by carrying out the extended function object Step S .

By such as determining whether annotation information which defines the extended function exists or not by referring to the MBeanInfo the MBean execution unit may determine whether interrupt processing exists or not as an extended function corresponding to the MBean . The same applies to other extended functions. Note that the extended function execution unit may perform such determination.

Next the MBean execution unit checks whether an argument value which is given to the MBean is effective or not Step S . This argument value is a value which is passed as arguments to a setter method or an operation method included in the MBean . When this argument value is invalid NO at Step S the MBean execution unit issues a JMX exception and finishes processing Step S . That is the MBean execution unit returns error information or the like which is an appropriate exception specified by the JMX specification to the operations management application .

When the argument value is valid YES at Step S the MBean execution unit calls a predetermined method included in the MBean and carries out the MBean Step S .

Next when synchronization processing exists as an extended function corresponding to the MBean YES at Step S the extended function execution unit identifies an extended function object. Specifically the extended function execution unit refers to the MBean extended function correspondence table and identifies the extended function object corresponding to the MBean for carrying out the synchronization processing. Then the extended function execution unit acquires the identified extended function object from the extended function memory unit and carries out synchronization processing by carrying out the extended function object Step S .

As shown in this synchronization processing from Step S to Step S repeats calling of a setter method for the attribute of a target of synchronization Step S the number of times corresponding to the number of attributes. By this synchronization processing management information for attributes and operation having a dependence relationship is updated in the extended function execution unit . In the example of the annotation file of SampleValue which is an attribute of a target is synchronized by updating SampleValue with sampleValue .

Next when interrupt processing which is for being performed after processing by the MBean exists as an extended function corresponding to the MBean YES at Step S the extended function execution unit identifies an extended function object. Specifically the extended function execution unit refers to the MBean extended function correspondence table and identifies the extended function object corresponding to the MBean for carrying out the interrupt processing. Then the extended function execution unit acquires the identified extended function object from the extended function memory unit and carries out interrupt processing by carrying out the extended function object Step S .

As a result the operations management application of the administrator terminal that is a JMX client calls the MBean and carries out processing such as update and operation of information of a management objective of the MBean the EJB container and the web container .

As it has been described above the software development support apparatus of this exemplary embodiment can give an extended function which enables to carry out processing which is customized more highly and more in detail than the JMX specification to the MBean

In otherwords the software development support apparatus of this exemplary embodiment applies a concept of a container in Java to MBean in a way that the existing JMX specification is extended. By this the software development support apparatus of this exemplary embodiment can carry out work specific to a monitoring and management application such as initialization processing a parameter check and securing consistency between MBeans in a common manner in the server side. This means that when integrated operational control is performed in large scale applications or the like the effect of applying the software development support apparatus of this exemplary embodiment is high in particular.

The software development support apparatus of this exemplary embodiment reduces the amount of code generation by a developer substantially.

The reason is as follows. In the existing related technology a developer itself has to perform definition work of initial values of management information parameter check processing and synchronization of information. On the other hand according to this exemplary embodiment if a developer newly defines annotation information for performing processing corresponding to definition of initial values of management information parameter check processing and synchronization of information the MBean container manages and controls the annotation information. Accordingly about a code a developer should generate only essential codes for operation management.

The software development support apparatus of this exemplary embodiment facilitates evaluation work for the operations management application and the MBean

The reason is as follows. In the existing related technology in order to test a code which generates the MBean it is necessary to operate the code on an exclusive MBean server . On the other hand by using annotation information the software development support apparatus of this exemplary embodiment can remove a code for such as initial value definition of management information perpetuation processing and synchronization which a developer itself has to create in the previous related technology from an implemented logic in the MBean class . Also in the software development support apparatus of this exemplary embodiment a code for generating the MBean can be evaluated easily using a test framework such as a unit test and JUnit. Further the software development support apparatus of this exemplary embodiment can implement and debug cross sectional and common processing such as log output and performance measurement easily by using annotation information for performing interrupt processing of an MBean method.

Next the second exemplary embodiment of the present invention will be described with reference to . is a block diagram showing a structure of a software development support apparatus Java operations management apparatus of this exemplary embodiment.

This exemplary embodiment is different from the first exemplary embodiment in a point that. Model MBean is used as a type of MBean in the JMX specification. About other points it is the same as those of the first exemplary embodiment. Model MBean is a kind of Dynamic MBean.

In Model MBean an existing Java object . . . not conforming to JMX is modeled and managed like MBean.

That is as shown in the existing Java object is included in a part of an MBean . MBeanInfo . . . corresponding to MBean may include a descriptor area . . . .

Thus by the MBeanInfo including the descriptor area supplementary information may be included in the descriptor area . Such supplementary information includes information such as information about a display method for use in an operations management application displayName and visibility information about an initial value of data default and information about a persistence property of data persistPolicy for example.

In addition to management information such as attribute information and operational information such supplementary information may be used as a component of the MBeanInfo

In this exemplary embodiment an MBean class includes such supplementary information as annotation information in addition to the structure in the first exemplary embodiment. Further on an occasion of generation of the MBean the MBean generating unit performs an update by adding this annotation information to the descriptor area . And then the MBean generating unit generates the MBeanInfo based on the updated descriptor area

According to this exemplary embodiment management information about the MBean including supplementary information is perpetuated by an information storage apparatus and the state of an object concerned is stored semi permanently. Accordingly the software development support apparatus of this exemplary embodiment can restore the MBeanInfo and the MBean at any time.

Next generation processing of the MBean in the software development support apparatus of this exemplary embodiment will be described with reference to . is a flow chart showing a generation processing procedure of the MBean in a software development support system of this exemplary embodiment.

In order to generate the MBean which is an operations management objective the software development support apparatus of this exemplary embodiment may use the existing MBean class

As such an existing MBean class a standard ModelMBean class called RequiredModelMBean is provided in the JMX specification. The software development support apparatus of this exemplary embodiment may use RequiredModelMBean and or may generate and use a subclass of RequiredModelMBean.

On this occasion instead of coding an extended functions used in operations management a developer adds annotation information corresponding to the respective functions to a method a field and a constructor of the above mentioned existing MBean class . By this the software development support apparatus of this exemplary embodiment can generate the MBean and the MBeanInfo based on this existing MBean class like the first exemplary embodiment.

The generation processing procedure of the MBean in the software development support apparatus of this exemplary embodiment is similar to each processing procedure in the software development support apparatus of the first exemplary embodiment. Specifically each processing step from the reading processing of the MBean class to the existence determination processing of annotation information Steps S S is similar to the each processing step in Steps S S of the first exemplary embodiment. Each processing step of the annotation information analysis loop Steps S S is similar to the each processing step in Steps S S.

On the other hand according to this exemplary embodiment an MBean generating unit stores the supplementary information mentioned above to a descriptor area as an initial value of supplementary information to be included in the MBeanInfo Step S . Such supplementary information is information which is defined in annotation information in the annotation file and shown in for example.

According to this exemplary embodiment management information about the MBean is perpetuated by an information storage apparatus . When perpetuated management information exists in the information storage apparatus YES at Step S the MBean generating unit updates annotation information of the MBeanInfo according to this perpetuated management information. On this occasion the initial value of supplementary information stored in the descriptor area is updated by the supplementary information in the perpetuated management information Step S .

Note that processing based on the annotation information besides annotation information mentioned above in generation processing of the MBean of this exemplary embodiment is similar to the processing in the first exemplary embodiment. That is the processing based on the annotation information besides annotation information mentioned above is processing such as information monitoring processing by a JMX monitor function interrupt processing interceptor processing for checking the validity of an argument when executing a setter method or an operation method and processing for synchronizing change information.

Next calling processing of the MBean in the software development support apparatus of this exemplary embodiment will be described with reference to . is a flow chart showing a calling processing procedure of MBean in a software development support system of this exemplary embodiment.

The calling processing procedure of the MBean in the software development support apparatus of this exemplary embodiment is similar to each processing in the software development support apparatus of the first exemplary embodiment. Specifically each processing besides the perpetuation processing of management information of MBean in Step S Steps S S and Steps S S is similar to the each processing of Steps S S and Steps S S of the first exemplary embodiment.

While according to this exemplary embodiment in order to perpetuate management information and the like about the MBean the following processing is performed at Step S. When a target method of such as a setter method or an operation method is carried out a perpetuation unit in an MBean container stores annotation information including management information on the MBeanInfo to the information storage apparatus Step S . For example when such as synchronization is performed based on the annotation file of the perpetuation unit stores to the information storage apparatus annotation information in the updated MBeanInfo

Then when this perpetuated management information exists the MBeanInfo is updated using this management information in the generation processing of the MBean as mentioned above and supplementary information stored in the descriptor area is also updated.

As it has been described above on the occasion that the MBean including the existing Java object is generated the software development support apparatus of this exemplary embodiment can generate an extended function object using annotation information like a case in the first exemplary embodiment. The software development support apparatus of this exemplary embodiment can also generate the MBeanInfo including annotation information.

The software development support apparatus of this exemplary embodiment can include in the descriptor area of the MBeanInfo supplementary information in annotation information and also can perpetuate such annotation information. Thus the software development support apparatus of this exemplary embodiment can update annotation information of the MBeanInfo using this perpetuated annotation information.

Next the third exemplary embodiment of the present invention will be described with reference to and . is a block diagram showing a structure of a software development support system of this exemplary embodiment and is a block diagram showing a structure of a container in the system.

A software development support system of this exemplary embodiment is a system in which a software development support system constituted as a Java operations management system in the first exemplary embodiment is applied to an execution and development environment of a program written in an object oriented programming language besides Java. That is this exemplary embodiment is the same as the first exemplary embodiment except for a point that an object oriented programming language which is used is not limited to Java.

As shown in a software development support system of this exemplary embodiment includes a software development support apparatus system management apparatus and an administrator terminal .

This software development support apparatus corresponds to the software development support apparatus Java operations management apparatus in the first exemplary embodiment. This software development support apparatus includes a container an annotation analysis unit and a unit object . . . . These correspond to the MBean container the annotation analysis unit and the MBean in the first exemplary embodiment respectively.

The container is an object management means for generating and storing various objects and for performing various operations to these objects and attribute data or the like of the objects.

The container includes the class for generating the unit object . The container generates the unit object corresponding to the class using this class . On the occasion of generating this unit object the annotation analysis unit analyzes annotation information included in the class . Then the container generates an extended function object and carries out the generated extended function object.

As shown in the container has a class memory unit an object generating unit an annotation information memory unit an extended function memory unit an object extended function correspondence table and an extended function execution unit . The class memory unit stores the class . The object generating unit generates the unit object . The annotation information memory unit stores annotation information used when the annotation analysis unit performs analysis. The extended function memory unit stores an extended function object which the object generating unit generates. The object extended function correspondence table stores a corresponding relationship between the unit object and an extended function object. The extended function execution unit carries out an extended function object.

As shown in the unit object includes an annotation information object . This annotation information object corresponds to the MBeanInfo in the first exemplary embodiment. The annotation information object is generated by the object generating unit along with generation of the unit object .

The function of the unit object in this exemplary embodiment is not limited in particular. For example the unit object may update and operate various information in a predetermined management objective function execution unit and or may acquire these information. In an example of the management objective function execution unit and carry out a object which is the management objective based on a request from the job application in the user terminal .

According to this exemplary embodiment on an occasion of generation of the unit object the annotation analysis unit analyzes annotation information included in the class . When annotation information for carrying out an extended function is included in this annotation information the object generating unit in the software development support apparatus system management apparatus generates an extended function object defined in the annotation information. The object generating unit also generates the annotation information object including this annotation information.

The operations management application in the administrator terminal connected to the software development support apparatus can refer to this annotation information object .

Then the operations management application calls the unit object and the unit object execution unit carries out the unit object . The extended function execution unit refers to the object extended function correspondence table and identifies the extended function object corresponding to the unit object . The extended function execution unit acquires the identified extended function object from the extended function memory unit and carries out the extended function object.

Such software development support apparatus of this exemplary embodiment has the same effect as the first exemplary embodiment. In other words because the software development support apparatus can generate an extended function object and the annotation information object which extend the function of a unit object it becomes possible to generate an extended function object or the like which has a function customized highly and in detail with a less code amount.

Further the software development support apparatus of this exemplary embodiment may include the same structure as the Java operations management apparatus in the second exemplary embodiment. That is the software development support apparatus may make management information perpetuated by an annotation information object including a descriptor area a container including a perpetuation unit and making supplementary information be included in a descriptor area.

Next the fourth exemplary embodiment of the present invention will be described with reference to . is a block diagram showing a structure of a software development support apparatus of this exemplary embodiment.

The software development support apparatus of this exemplary embodiment includes a container and an annotation analysis unit

The container is an object management means for generating and storing various objects and for performing various operations to these objects and attribute data or the like of the objects.

The container includes a class for generating a unit object . The container generates the unit object corresponding to the class using this class . On an occasion of generating this unit object the annotation analysis unit analyzes annotation information which is information included in the class and indicating the attribute of the class or operation to the class . Then the container generates an extended function object and carries out the generated extended function object.

As shown in the container has a class memory unit an object generating unit and an extended function execution unit . The class memory unit stores the class for generating one or more unit object for performing predetermined processing. The object generating unit reads the class stored in the class memory unit and generates the unit object . When the annotation analysis unit determines that the class includes the annotation information the object generating unit performs following processing. That is the object generating unit generates an extended function object which adds to the class an attribute of the class or operation to the class indicated by the annotation information on an occasion of generating the unit object . The extended function execution unit carries out the extended function object which the object generating unit generates. At the time when the unit object corresponding to the class is called from a predetermined application and carried out the extended function execution unit carries out the extended function object corresponding to the class

According to this exemplary embodiment when generating the unit object the annotation analysis unit analyzes annotation information included in the class . When predetermined annotation information is included in this annotation information the object generating unit in the software development support apparatus generates an extended function object defined in the annotation information.

An administrator terminal which is not illustrated and connected to the software development support apparatus calls the unit object and the software development support apparatus carries out the object. The extended function execution unit identifies an extended function object corresponding to the unit object . The extended function execution unit carries out the identified extended function object.

Such software development support apparatus of this exemplary embodiment has the same effect as the first exemplary embodiment. Because the software development support apparatus can generate an extended function object and an annotation information object which extend the function of a unit object it becomes possible to generate an extended function object or the like which has a function customized highly and in detail with a less code amount.

The fifth exemplary embodiment of the present invention is a software development support system having a software development support apparatus including a class memory unit an object generating unit an annotation analysis unit and an extended function execution unit and a terminal connected to this software development support apparatus. The class memory unit stores a class for generating at least one unit object which carries out predetermined processing. The object generating unit reads the class and generates the unit object. The annotation analysis unit determines whether or not the class includes annotation information which indicates an attribute of the class or operation to the class. The extended function execution unit carries out an extended function object corresponding to the class.

When the annotation analysis unit determines that the class includes the annotation information the object generating unit generates the extended function object which adds to the class an attribute of the class or operation to the class indicated by the annotation information on an occasion of generating the unit object. When the unit object corresponding to the class is called from the terminal and the unit object is carried out the extended function execution unit carries out the extended function object corresponding to the class.

In recent years a general purpose framework for implementation and operations management of a Java application called JMX has appeared. By this framework a developer can monitor and Manage various Java applications through a general purpose API Application Programming Interface .

That is by this specification without using an API and a function for operations management provided uniquely by Java applications in the past a developer can access a monitoring management objective using a common method even in any Java application.

However most of these specifications for the general purpose API are for a basic purpose yet and only basic application processing such as access to management information execution of operation and notification of an event has been standardized.

On the other hand when JMX is used for development of a system for managing an enterprise large scale server application in order for a management objective to be managed efficiently and in detail it is not enough only to use JMX just as it is. A developer has needed to describe a code for performing various kinds of additional implementation to JMX for MBean Managed Bean which is a Java object which becomes a monitoring or a management objective.

For example when JMX is applied to an application server and a server application for performing process monitoring and computer monitoring and the like a developer has to prepare functions such as for an initializing process of MBean status monitoring and synchronizing updated information with other MBeans.

Several types of MBeans exist in the JMX specification. Among MBeans there is an MBean in which the MBean itself possesses metadata such as an item name of information which the MBean manages. There is a case where a developer him herself needs to create the entire definition of an object called MBeanInfo which is definition information for enabling this metadata to be referred to from a predetermined application. The number of lines of such object definition stretches to several dozen hundred lines in large cases.

Also in such additional implementations there are a lot of common portions in individual MBeans. Accordingly it is not desirable that individual developers of MBean describe a similar code independently with each other. JMX has been specified only recently and there are not a lot of developers who can perform implementation using API yet.

From the above a developer cannot concentrate his her energy on implementation of essential operations management logics and thus there has been a problem that the more the scale of implementation becomes large the more difficult it will be to improve development efficiency.

The above mentioned problem is a problem which one faces when realizing high level operations management in JMX. The more a range to which JMX is applied becomes large the larger its implementation volume will be and as a result there may be a case where the work volume and the work level are not improved in comparison with those before JMX introduction. Under such condition advantage of applying JMX fades away.

For example about EJB and Servlet by using annotation information about processing specialized in EJB and Servlet it is possible to reduce the work volume. Processing specialized in EJB and Servlet includes processing of acquiring an object from a service of JNDI Java Naming and Directory Interface controlling transactions and defining relation to a database and associating with a Java object for example.

By EJB and Servlet a developer can implement the functions similar to those of the past with a less code amount than before. However a scheme to utilize annotation information is not enough for use in monitoring and managing an application yet. Also when an operations management application is developed a developer cannot implement the functions similar to those of the past with a less code amount than before. In addition although tools and API for making development of JMX efficient are provided by several open sources those tools and API are in a state that they are not becoming popular sufficiently.

Programs by JMX have relation with life cycle processing such as initialization of all job applications and they operate as a basis of an application execution foundation. Accordingly it is desirable that an application developer is able to implement a operations management function without being conscious of behavior of an object in the JMX layer lower layer as far as possible.

The debugging supporting method described in patent document 1 can extract annotation information embedded in a method definition section and analyze the extracted information. However the debugging supporting method described in patent document 1 is a method for converting annotation information into a form that can be evaluated on a debugger based on an analysis result and thus it is not possible to apply it to reduction in the volume of a program using JMX and to automation or the like of processing for monitoring and management. Accordingly the debugging supporting method described in patent document 1 cannot achieve simplification of coding related to JMX or the like.

Further the language interpretation display method described in patent document 2 can extract and analyze annotation information embedded in HTML. However the language interpretation display method described in patent document 2 is a method for customizing a screen display based on the analyzed annotation information and thus it is not possible to apply it to reduction in the volume of a program using JMX and to automation or the like of processing for monitoring and management. Accordingly the language interpretation display method described in patent document 2 cannot achieve simplification of coding related to JMX or the like.

An exemplary advantage according to the invention is that it is possible to generate an extended function object and MBeanInfo or the like which extend the function of a unit object such as MBean related to monitoring or management. Another exemplary advantage according to the invention is that it is possible to perform processing customized more highly and more in detail than the JMX specification with a less code amount.

The present invention is not limited to the above mentioned exemplary embodiments and it is not necessary to say that various modified implementations are possible within the scope of the present invention.

For example according to each of the above mentioned exemplary embodiments although it is structured such that a unit object of MBean is accessed by being called from an operations management application in an administrator terminal it is not limited to this. for example the structure of access to a unit object may be changed appropriately to such as a structure in which the unit object is called from another application in a general user terminal.

The present invention can be used suitably when a developer customizes a server application for performing monitoring and management more highly and more in detail than the JMX specification and in particular when a developer performs integrated operational control in a large scale application or the like. When the present invention is applied to a product project for developing an application server and a server application for process monitoring and computer control for example each developer does not need to make up a common and complicated implementation from scratch. Such implementation includes implementations needed for initializing processing a parameter check synchronization of information and information monitoring for example. Accordingly each developer can concentrate his her energy only on logics needed for operations management.

When the present invention is applied to a product called IDE integrated development environment such IDE can perform complementation of a code and automatic generation of a related source code. Accordingly this IDE can provide an environment for operations management application development that is made more efficient.

The previous description of embodiments is provided to enable a person skilled in the art to make and use the present invention. Moreover various modifications to these exemplary embodiments will be readily apparent to those skilled in the art and the generic principles and specific examples defined herein may be applied to other embodiments without the use of inventive faculty. Therefore the present invention is not intended to be limited to the exemplary embodiments described herein but is to be accorded the widest scope as defined by the limitations of the claims and equivalents.

Further it is noted that the inventor s intent is to retain all equivalents of the claimed invention even if the claims are amended during prosecution.

The whole or part of the exemplary embodiments disclosed above can be described as but not limited to the following supplementary notes.

a software development support apparatus which includes a class memory unit which stores a class for generating at least one unit object which carries out predetermined processing an object generating unit which reads said class and generates said unit object an annotation analysis unit which determines whether or not said class includes annotation information which indicates an attribute of said class or operation to said class and an extended function execution unit which carries out an extended function object corresponding to said class and

when said annotation analysis unit determines that said class includes said annotation information said object generating unit generates said extended function object which adds to said class an attribute of said class or operation to said class indicated by said annotation information on an occasion of generating said unit object and wherein

when said unit object corresponding to said class is called from said terminal and said unit object is carried out said extended function execution unit carries out said extended function object corresponding to said class.

A software development support system according to Supplementary note 1 wherein when said annotation analysis unit determines that said class includes said annotation information said object generating unit generates an annotation information object which includes said annotation information and which said terminal can refer to on a occasion of generation of said unit object.

said annotation information includes at least information which indicates whether said annotation information is perpetuated or not wherein

an information storage apparatus which stores said annotation information and information indicating said unit object while correlating said annotation information and said information indicating said unit object and a perpetuation unit which determines whether to perpetuate said annotation information or not based on said annotation information and wherein

said perpetuation unit stores said annotation information to said information storage apparatus when said perpetuation unit determined to perpetuate said annotation information.

said annotation information includes at least information which indicates whether said annotation information is initialized or not and wherein

said object generating unit initializes annotation information included in said unit object based on said annotation information when said annotation information corresponding to said unit object is stored in said information storage apparatus.

