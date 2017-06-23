---

title: Using symbolic evaluation to validate models that have incomplete information
abstract: An arrangement calculates a description of potential responses of a distributed system in response to at least one input stimulus. The distributed system including nodes whose operation is described by respective node behavior descriptions. The method involves applying symbolic evaluation to plural node behavior descriptions so as to produce plural response descriptions that describe responses of nodes, and combining at least the plural response descriptions so as to arrive at the description of potential responses of the distributed system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08065125&OS=08065125&RS=08065125
owner: AT&T Intellectual Property II, L.P.
number: 08065125
owner_city: Reno
owner_country: US
publication_date: 20100817
---
This is a continuation of U.S. application Ser. No. 12 283 054 filed Sep. 9 2008 now U.S. Pat. No. 7 827 013 issued Nov. 2 2010 which was a continuation of U.S. application Ser. No. 10 770 759 filed Feb. 3 2004 now U.S. Pat. No. 7 487 073 issued Feb. 3 2009 which claimed priority to U.S. provisional application 60 472 362 filed May 21 2003.

The invention generally relates to arrangements for validating models having incomplete information. More particularly the invention relates to arrangements for validating Multi Stakeholder Distributed Systems MSDSs having nodes whose structure and operation are not completely or accurately known.

Behavioral modeling of for example compute networks or software systems in general can be applied to help users understand and predict system behavior to help administrators comprehend and debug configurations and to help developers better analyze the potential interactions of a new service with its online environment. However in order to produce results conventional behavioral modeling requires access to fully detailed configuration and operational data of all relevant nodes of a system. It would be desirable to know in detail have a model demonstrating how each node computes its outputs from its inputs more than a mere I O description. Unfortunately for a variety of reasons node deployers are unwilling or unable to provide complete or accurate data. Thus a key problem is to design use or debug a system while ignorant of how most of its nodes work.

Multi Stakeholder Distributed Systems MSDSs may be defined as distributed systems in which nodes are designed owned or operated by different stakeholders in ignorance of one another and with different possibly conflicting goals. Examples include the email system networks of web services telephone networks the Internet as a whole and so forth. Such MSDSs have globally inconsistent high level requirements and therefore have behavior that is impossible to validate according to the usual meaning of the term. In general as the term will be used in this disclosure a validation process may be a process in which a client such as for example a human user states a requirement describing a system behavior and in which a validation tool method then evaluates whether the system meets the stated requirement.

All users administrators and developers of networked services in either the public Internet or within corporate or government intranets face the problems mentioned above. Thus there is a need for a technique for tolerating incomplete data in the validation process so that benefits of behavioral modeling can still be obtained even though node deployers are unwilling or unable to provide complete or accurate data.

An arrangement calculates a description of potential responses of a distributed system in response to at least one input stimulus. The distributed system including nodes whose operation is described by respective node behavior descriptions. The method involves applying symbolic evaluation to plural node behavior descriptions so as to produce plural response descriptions that describe responses of nodes and combining at least the plural response descriptions so as to arrive at the description of potential responses of the distributed system.

In describing embodiments illustrated in the drawings specific terminology is employed for the sake of clarity. However the invention is not intended to be limited to the specific terminology so selected and it is to be understood that each specific element includes all technical equivalents that operate in a similar manner to accomplish a similar purpose. Various terms that are used in this specification are to be given their broadest reasonable interpretation when used to interpret the claims.

Moreover features and procedures whose implementations are well known to those skilled in the art are omitted for brevity. For example initiation and termination of loops and the corresponding incrementing and testing of loop variables may be only briefly mentioned or illustrated their details being easily surmised by skilled artisans. Thus the steps involved in methods described herein may be readily implemented by those skilled in the art without undue experimentation.

Further various aspects features and embodiments may be described as a process that can be depicted as a flowchart a flow diagram a structure diagram or a block diagram. Although a flowchart may describe the operations as a sequential process many of the operations can be performed in parallel concurrently or in a different order than that described. Operations not needed or desired for a particular implementation may be omitted. A process or steps thereof may correspond to a method a function a procedure a subroutine a subprogram and so forth or any combination thereof.

In the present technical description certain terms in common usage may be used to more easily communicate with those skilled in the art. However it is to be understood that those common usage terms are merely employed as embodiments of broader concepts that may be recited in the claims. Accordingly the scope of the claims should not be limited by particular references made in the specification.

As used herein the term symbolic evaluation is intended to cover what those in the art may also call symbolic execution partial evaluation and the like.

As introduced in the Background Multi Stakeholder Distributed Systems MSDSs do not satisfy traditional assumptions of Requirements Engineering RE . For example conflicting stakeholder goals lead to inconsistent global requirements and decentralized control leads to uncontrolled and chaotic change. Accordingly the inventor has recognized that the problem focus should be changed from global to local that is changing the focus to personal ephemeral requirements engineering. That is the inventor has recognized that it would be desirable to change the problem from Does the system do the right thing to a generally simpler problem Will the system do the right thing for me now 

But to solve that simpler problem there is a need to predict behavior of the system on inputs of interest. The inventor has recognized that it is desirable to solve this by establishing open standards for behavioral modeling in which each node provides via http or through a central registry for example a behavioral model expressed in terms of shared domain specific function object theories. The present arrangement supports validation by assembling these models and by simulating animating or formally analyzing the assembled model thus helping the user to detect unfavorable behaviors or feature interactions in advance.

An important feature of the present validation arrangement is to use symbolic evaluation as opposed to concrete testing or concrete simulation over a distributed system model that lacks information in order to reason about the correctness of the system. The arrangement combines symbolic evaluations of primitive sub models to ultimately come to useful conclusions about the functionality of the system being modeled.

Before embarking on a detailed description of a motivating example and an implementation of a validation arrangement the following definitions and descriptions are provided with the understanding that the scope of the claims should not be limited to particular examples.

A model is a formal description of the behavior of a computational node or service within such a node. It could be represented in any of a variety of formalisms such as for example 

Each device for example computer taking part in implementing a Multi Stakeholder Distributed System MSDS may host a number of nodes of the logical MSDS within it with each node identified uniquely within the device. Each such node may be described formally by a model instance 

Typically a model instance is an abstraction of a particular running service at a particular place and time in the network hosting the MSDS.

In general a validation process may be a process in which a client such as for example a human user states a requirement describing a system behavior and in which a validation tool method then evaluates whether the system meets the stated requirement. The behavior stated by the client need not be a desired behavior. The client could also state an undesired behavior and the validation process would attempt to determine whether the system could behave that way. For example the client could ask whether it is possible that an email message will appear unencrypted that is be compromised in transit between sender and desired recipient.

In one common class of validation processes a client user states an input class he is interested in applying to the system as the requirement and the validation process computes a set of possible outcomes and presents them to the user who then determines whether they are desirable. In a variant of that technique the system automatically evaluates the desirability of the possible outcomes and present to the user those that are determined to be definitely or possibly undesirable.

In one particular embodiment to which the scope of the invention should not be limited a validation process may be considered to be a process of using symbolic reasoning to incrementally construct a tree of generalized scenarios or Generalized Scenario Tree abbreviated GST . During the validation process a user supplies as much initial information as is available and the validation process itself produces a tree of classes of possible outcomes. For example one set of implementations of the validation process may involve iteration of steps 

Generally connector information is used to direct the flow of data or events between nodes of a system. In one embodiment a particular type of connector information in terms of host port and event transformation is used but one skilled in the art can readily recognize other styles of connector information could be used including for example 

In such implementations each deduced event is appended to current generalized scenario tree GST . Branching in result tree is caused by missing information. The output of process is full scenario tree. A user can examine each branch and evaluate the desirability of outcomes.

Per commonly accepted computer science terminology a GST node x is above GST node y if x is a node on the path from y to the root node including the root node but not y.

 Input stimulus includes an input event in the common usage of the term. A reactive system such as one represented by a node model can have a range of different types of responses to an input stimulus. Input stimuli could include for example 

 Response including a possible response includes an intermediate or ultimate state change or other occurrence that takes place in response to an input event or other input stimulus 

 Classes. In describing a system s input stimuli intermediate occurrence responses and ultimate occurrence responses it is advantageous to use classes to provide a single compact description. For example an input event class may refer to a parameterized description of an input event and a response class may refer to zero one or a sequence of possibly parameterized responses. More specific examples include 

 Behavior description of a node includes not only node model in the common usage of the term generally a description of behaviors of a node . The term node behavior description also refers to a much broader class of description styles. For example a node behavior description may include 

Motivating example. Referring now to a first network element is capable of communicating through a network with a second network element . Network elements have respective model instances E D that may be considered part of the same Multi Stakeholder Distributed System MSDS . also shows a validation tool configured to retrieve a model instance E from network element and model instance D from network element . A client user uses a validation tool that embodies teachings of the present disclosed embodiments. Validation tool can gauge operation of model instances E and D in certain usage scenarios even when the operational characteristics of model instances E and or D may be known only incompletely.

An embodiment of a validation process is explained below with reference to the flowcharts of . Thereafter the manner in which that process may be applied in the practical usage scenario is described in detail with reference to .

Embodiments of the Validation Arrangement. From the foregoing motivating example it is seen that arrangement described herein provides tools to help users administrators and developers to comprehend analyze and validate correct behavior of transactions in a complex distributed system such as a computer network. The arrangement compensates for incomplete information by leaving placeholders in behavior scenarios and presents the user with alternative outcomes based upon different sets of assumptions. In a particular embodiment automated reasoning techniques such as logical and functional algebraic simplification are applied to simplify the resulting symbolic scenarios based upon what information is disclosed.

The present arrangement applies a technique from program optimization and correctness proof to a modeling problem within distributed systems in order to compensate for the missing information.

Debugging distributed systems is known to be difficult and time consuming. Designing new services and nodes to interoperate with existing nodes is also difficult to get right at the detailed level and users are having more and more difficulty understanding and using feature rich distributed systems such as email or web service networks such as proposed and actual supplier management work flow systems .

The conventional approach is to essentially ignore detailed validation questions and abstract to a black box level nodes and services controlled by others. The missing information is then not necessary since the detailed level is ignored. However this approach also implies that important questions such as whether an email message will arrive securely at its intended destination cannot be answered except by trial and error.

A significant difficulty is as stated above that stakeholders simply will not divulge all of the information necessary to understand in detail at the concrete level what their nodes and services do. One can easily argue that even though they are likely willing to divulge some information they will never release all of it. Thus any technique must tolerate this lack of information. Conventional validation techniques such as testing or simulation cannot tolerate this.

Reference is now made to for a model validation arrangement that overcomes the shortcomings of conventional validation approaches.

Referring to block indicates reception of INPUTS the input data structure representing an ordered list of input events to be applied to the modeled system.

In block GST denotes the variable that holds the result of the process a Generalized Scenario Tree GST . Block initializes the GST to a dummy no op node.

Decision block indicates a determination of whether or not the data structure INPUTS is empty. If the INPUTS data structure is empty this indicates that the processing is complete and control passes to block for outputting the result GST such as by a return to a higher level calling program. Thereafter control may pass to a block representing the output storage or other use of the GST such as reading the GST s meaning. In one embodiment reading a GST may be accomplished by a tool that interprets the GST s symbolic description of potential responses of the distributed system and generates a natural language for example English paraphrasing for output to a client such as a human user. In another embodiment reading may be accomplished by presenting an interactive graphical visualization of the steps of the various potential responses.

Block indicates the setting of variable i a current input event being operated upon to the first input event of the INPUTS data structure. Step removes this front input event from Inputs such as through a REST INPUTS function so that INPUTS is smaller for future iterations of the loop.

Block indicates the retrieval from the MSDS of the model instance that the input event designates by for example a host port specification. Here host port may be thought of as the unique coordinates of a model instance located somewhere within the MSDS.

Block indicates construction of an input event node one of the types of tree nodes of which a GST is constructed corresponding to the input event in current input event i. Distinct copies of this input event node attach at all fringe nodes or alternatively at only selected fringe nodes of the GST thus making the GST grow. As used herein a fringe node is a node that does not as yet have any children nodes. Each such attached new node is marked as unprocessed . In addition to attaching new nodes to the growing GST the system also processes them using process described with reference to . As each node is processed the system records this fact by marking the node.

Decision block indicates a determination of whether any nodes in the existing GST are as yet unprocessed. If there are no unprocessed nodes in the GST then control returns to decision block . However if there are unprocessed nodes in the GST control passes to block one embodiment of which is decomposed in .

The first block in is block which indicates selection of an unprocessed node herein called f in the GST. Because control reaches block only if the GST contains at least one unprocessed node this step selects one such node. The present arrangement provides many ways to select the next node to be processed such as for example 

Block indicates application of a method to a node f yielding a resulting generalized scenario tree R. Block is drawn with double lines to indicate that it may be implemented as a function that may be called recursively. One implementation of block is decomposed in discussed below.

Block indicates attaching the resulting tree R as determined in block as a child of all fringe nodes or alternatively only selected fringe nodes that are below or equal to f. Thereafter control returns to block for determination of whether there are still any unprocessed nodes in the GST.

A process by which block may be implemented is now explained with reference to the flowchart of . Using terms and symbols to be used immediately hereafter block takes a Generalized Scenario Tree GST node g as input and then computes a new GST R corresponding to the elaboration of the input node according to model evaluation semantics. If block is implemented as a called function the new GST may be returned to the calling process as a value of the called function before control returns to block .

Referring to decision block indicates a multi way decision branch that may be implemented for example as a switch statement. The following description of refers to various data entries that for completeness are described below in the paragraphs following the sub heading Data Entities. In branching from decision block is determined by the specific type of the input node g 

Block is executed when g is of type input event node. Accordingly it may be assumed that g includes the following information and specifications 

Block applies the well known symbolic evaluation technique to model g using input data from input event g and state information from model instance g . Concerning symbolic evaluation techniques see for example N. Jones C. Gomard and P. Sestoft Prentice Hall 1993 which is incorporated herein by reference in its entirety. As is well known in the art the result is a symbolic description of possible entire executions or merely possible outcomes which are here represented as a generalized scenario tree R.

Block indicates that R is determined to be the tree resulting from the symbolic evaluation conducted in block . If process is a called function R may be returned to the calling process as a value of the called function before control returns to FIG. block .

Referring now to one decomposition of block is shown as a flowchart. Block indicates the substitution of parameters of output event g into the expressions of connections g .

Block indicates application of symbolic automated reasoning well known in the art to simplify the host and port expressions in the substituted connections g .

Decision block indicates the determination of whether the results of simplifying the host and port expressions are concrete data values as opposed to remaining indefinite symbolic expressions . If the results of simplifying the host and port expressions are indefinite symbolic expressions then control passes to block which determines R to be a null tree before control returns to . However if the results of simplifying the host and port expressions are concrete data values then control passes to block .

Block indicates the access of the MSDS infrastructure to retrieve the model instance information at host port of the MSDS. Publishing and retrieval can be implemented in a number of ways including for example 

Block predicated on the g being an output event node indicates substitution of the data obtained from the parameters of output event g into the translated event expression of connection g . This results in an input event expression that is then incorporated into a new input event node g .

Finally block indicates the determination of R by recursively invoking or otherwise carrying out the functions of process using g as a node argument instead of g. Symbolically this invocation may be represented as R Process g . Control then returns to with R bearing the result of that recursive invocation.

Data Entities. The foregoing description of refers to various data entries. For completeness the following description of one implementation of those data entities is provided. Generalized Scenario Tree GST node types include types A through E 

 A input event node X. This type of node represents application of an input event to a state machine representing a running MSDS node at a given instant of time.

 B output event node X This type of node represents the communication of some output result s from one running MSDS node to the input of another running MSDS node at a particular instant of time.

 C state change node X represents the change of a state variable during the computation resulting from applying an input event to a running MSDS node at a given time.

 D if node X represents a branch based upon a condition predicate in the computation resulting from applying an input event to a running MSDS node at a given time.

 E loop node X represents the iteration of a sub computation resulting from applying an input event to a running MSDS node at a given time.

Applications. Advantageously the present arrangement is applicable to modeling of any multistakeholder distributed system MSDS . Examples of MSDSs include 

Email. depicts a two node MSDS having model instances E and D that are assumed to be running at respective network elements a.net and b.net on port of each. also shows a client user and a validation tool configured to retrieve the model instance information for E and D.

An example of a Requirement that the user states to tool is shown in colloquial language in Table III 

Further computation involving processing nodes through in accordance with results in no further nodes being added to the tree.

Of course as noted above the foregoing example of application to an email system is only one of a plethora of applications in which the present invention is useful.

More generally also provided for the methods described herein are computer program products such as storage media storing computer executable code or program instructions for execution on a computer system having at least one data processing device which code or instructions when executed by the computer system cause the computer system to perform the methods described herein.

Further provided are systems for performing the methods described herein the systems including at least one data processing element. Generally these elements may be implemented as any appropriate computer s employing technology known by those skilled in the art to be appropriate to the functions performed. The computer s may be implemented using a conventional general purpose computer programmed according to the foregoing teachings as will be apparent to those skilled in the computer art. Appropriate software can readily be prepared by programmers based on the teachings of the present disclosure. Suitable programming languages operating with available operating systems may be chosen.

General purpose computers may implement the foregoing methods in which the computer housing may house a CPU central processing unit memory such as DRAM dynamic random access memory ROM read only memory EPROM erasable programmable read only memory EEPROM electrically erasable programmable read only memory SRAM static random access memory SDRAM synchronous dynamic random access memory and Flash RAM random access memory and other special purpose logic devices such as ASICs application specific integrated circuits or configurable logic devices such GAL generic array logic and reprogrammable FPGAs field programmable gate arrays .

Each computer may also include plural input devices for example keyboard microphone and mouse and a display controller for controlling a monitor. Additionally the computer may include a floppy disk drive other removable media devices for example compact disc tape and removable magneto optical media and a hard disk or other fixed high density media drives connected using an appropriate device bus such as a SCSI small computer system interface bus an Enhanced IDE integrated drive electronics bus or an Ultra DMA direct memory access bus. The computer may also include a compact disc reader a compact disc reader writer unit or a compact disc jukebox which may be connected to the same device bus or to another device bus.

The arrangement provides at least one computer readable medium. Examples of computer readable media include compact discs hard disks floppy disks tape magneto optical disks PROMs for example EPROM EEPROM Flash EPROM DRAM SRAM SDRAM.

Stored on any one or on a combination of computer readable media is software for controlling both the hardware of the computer and for enabling the computer to interact with other elements to perform the functions described above. Such software may include but is not limited to user applications device drivers operating systems development tools and so forth.

Such computer readable media further include a computer program product including computer executable code or computer executable instructions that when executed causes a computer to perform the methods disclosed above. The computer code may be any interpreted or executable code including but not limited to scripts interpreters dynamic link libraries Java classes complete executable programs and the like.

From the foregoing it will be apparent to those skilled in the art that a variety of methods systems computer programs on recording media and the like are provided.

For example the present disclosure supports a method for calculating a description of potential responses of a distributed system in response to at least one input stimulus the distributed system including nodes whose operation is described by respective node behavior descriptions. The method may involve applying symbolic evaluation to plural node behavior descriptions so as to produce plural response descriptions that describe responses of nodes and combining at least the plural response descriptions so as to arrive at the description of potential responses of the distributed system.

The producing and combining steps may collectively constitute incrementally forming a generalized scenario tree GST from which the description of potential responses of the distributed system may be derived.

The method of may further involve selecting a next node behavior description from the GST to process in order to carry out a next iteration of the response description producing step the selecting step being chosen from a group including 

The method may further involve using connector information from a first node behavior description to determine which second node behavior description should receive a previously produced response description as a new input stimulus description.

The method may further involve retrieving at least one node behavior description the retrieving step being selected as at least one from a group of retrieving steps including 

The connector information using step may include simplifying a host port expression that is referenced by the connector information the host port expression defining a coordinate of a node behavior description in the distributed system determining whether the simplified host port expression is a concrete data value or an indefinite expression and if the simplified host port expression is a concrete data value determining the second node behavior description as that corresponding to the coordinates within the distributed system defined by the simplified host port expression.

The connector information using step may include simplifying a host port expression that is referenced by the connector information the host port expression defining a coordinate of a node behavior description in the distributed system determining whether the simplified host port expression is a concrete data value or an indefinite expression and if the simplified host port expression is an indefinite expression determining the second node behavior description as that corresponding to the coordinates within the distributed system defined by the simplified host port expression.

The method may further involve inputting from a client at least one requirement describing at least one input stimulus description. The method may further involve in response to the input requirement outputting the description of potential responses of the distributed system.

The method may further involve inputting from a client at least one requirement describing at least one criterion describing acceptable responses of the distributed system. The method may further involve in response to the input requirement outputting a description of at least one potential response of the distributed system that does not satisfy the at least one requirement.

The present disclosure also supports a computer program product including computer executable code or computer executable instructions that when executed cause a computer to perform the methods described herein.

Many alternatives modifications and variations will be apparent to those skilled in the art in light of the above teachings. For example there are many ways to implement embodiments including choices of description language choice of reasoning technology and designs of protocols for exchanging partial information. It is therefore to be understood that within the scope of the appended claims and their equivalents the invention may be practiced otherwise than as specifically described herein.

