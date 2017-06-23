---

title: System and method for evaluation of a field programmable gate array (FPGA)
abstract: A method for evaluation of a field programmable gate array (FPGA), the method includes: configuring the FPGA to execute, in parallel, an evaluation program and an additional program; wherein an execution of the additional program is being evaluated by the evaluation program; and executing, by the FPGA the evaluation program and the additional program; wherein the executing includes receiving, by a memory controller of the FPGA, captured signals from multiple points of interest of the FPGA; and transferring, by the memory controller of the FPGA, at least a portion of the captured signals to at least one memory space of a memory block via memory channels of the FPGA.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08769357&OS=08769357&RS=08769357
owner: GiDEL Ltd.
number: 08769357
owner_city: Or-Akiva
owner_country: IL
publication_date: 20100722
---
This application claims the priority of U.S. provisional patent Ser. No. 61 227 970 filing date Jul. 23 2009 which is incorporated herein by reference.

Reconfigurable FPGA designs enable extremely flexible and powerful parallel processing architecture yet have been somewhat impeded by a lack of evaluation tools. The complexity of today s design makes it almost impossible to debug a design using traditional logic analysis methods. Evaluation often captures over 50 of the development time. Thus an efficient flexible evaluation tool that is founded on accurate signal capture and abundant visibility depth is essential to accelerating optimizing the developmental cycle. Another approach for evaluation is Emulation but it is much slower and much more expensive.

A method may be provided. The method may include according to an embodiment of the invention configuring the FPGA to execute in parallel an evaluation program and an additional program wherein the execution of the additional program is being evaluated by the evaluation program and executing by the FPGA the evaluation program and the additional program wherein the executing includes receiving by a memory controller of the FPGA captured signals from multiple points of interest of the FPGA transferring by the memory controller of the FPGA at least a portion of the captured signals to at least one memory space of a memory block via memory channels of the FPGA and optionally outputting by the memory controller of the FPGA at least a portion of the captured signals from the FPGA via a communication element for example to a Host computer.

The method may include receiving captured signals from at least forty eight points of interest and at a rate of at least sixteen bytes per cycle.

The width of a single point of interest can range between a single bit and multiple bits. For example a width of a single point of interest can even exceed 400.

Different points of interest may be sampled at the same rate but may also differ from each other by their sampling rates.

The sampling rate of the points of interest can be low high and even very high. For example the sampling rate can range between 10 Hz to more than 900 MHz.

The configuring may include sending to the memory controller of the FPGA predefined responses to triggers received by the memory controller of the FPGA.

A predefined response may include at least one of the following i storing an outcome of an execution of a predefined response to a trigger at the memory block and outputting the outcome ii storing captured signals of a certain type while ignoring captured signals of another type iii stopping a capture of captured signals from a point of interest and iv starting a capture of captured signals from the point of interest.

A predefined response may include stopping the sampling after a predefined period of time or after a predefined number of samples or frames .

The configuring may include selecting captured signals to be stored in the memory block and selecting captured signals to be ignored of wherein the selecting is responsive to a stage of an evaluation process.

The configuring may include selecting captured signals to be stored in the memory block and selecting captured signals to be ignored of wherein the selecting is responsive to previously obtained data or previously detected errors in an execution of the additional program by the FPGA.

The method may include transferring by the memory controller of the FPGA at least a portion of the captured signals to at least one memory space of a memory block based on a mapping between memory channels of the memory controller and memory spaces of the memory block.

The method may include receiving by the memory controller of the FPGA at least one possibly video related control signal selected from a frame indication and a valid indication and storing possibly video related captured signals from at least one point of interest to the memory block

The method may include duplicating by the memory controller of the FPGA a captured signal to provide two duplicates of the captured signals transferring by the memory controller of the FPGA one duplicate of the captured signal to the memory block and outputting by the memory controller of the FPGA another duplicate of the captured signal from the FPGA via the communication element for example to a Host computer

The method may include receiving a request from a user for obtaining captured signals that have been captured at previous point in time that occurred at least one fraction of a second before the receiving of the request and optionally sending to a host computer the captured signals. The user can receive signals that were captured few seconds few minutes few hours and even a longer period before the request to obtain captured signals.

The method may include receiving a request from a user for stopping an execution of the additional program and ignoring captured signals that have been stored before receiving the request by the memory controller of the FPGA but after the request has been issued by the user.

The method may include tagging captured signals and retrieving captured signals from the memory block based on values of tags associated with the captured signals.

A device for evaluation of a field programmable gate array FPGA may be provided. According to an embodiment of the invention the device may include a memory block and an FPGA coupled to the memory block. The FPGA may include a logic module such as a core a memory controller and multiple probes coupled between points of interest of the logic module and the memory controller wherein the logic module is arranged to execute an additional program while the memory controller is arranged to execute an evaluation program wherein an execution of the additional program is being evaluated by the evaluation program wherein the memory controller is coupled to the multiple points of interest via multiple probes for receiving during the execution of the evaluation program captured signals from multiple points of interest wherein the memory controller is arranged to transfer at least a portion of the captured signals to at least one memory space of a memory block via memory channels of the FPGA and wherein the memory controller is arranged to optionally output at least a portion of the captured signals from the FPGA via a communication element for example to a Host computer.

The device may include at least forty points of interest. For example the device may include at least 50 thousand points of interest.

The memory controller may be arranged to receive captured signals from at least forty eight points of interest and at a rate of at least sixteen bytes per cycle

The memory controller may be arranged to receive predefined responses to triggers received by the memory controller.

The memory controller may be arranged to select captured signals to be stored in the memory block and select captured signals to be ignored of the selecting is responsive to a stage of an evaluation process.

The memory controller may be arranged to select captured signals to be stored in the memory block and selecting captured signals to be ignored of the selecting is responsive to previously obtained data or previously detected errors in an execution of the additional program by the FPGA.

The memory controller may be arranged to transfer at least a portion of the captured signals to at least one memory space of a memory block based on a mapping between memory channels of the memory controller and memory spaces of the memory block.

The memory controller may be arranged to receive at least one possibly video related control signal selected from a frame indication and a valid indication and storing possibly video related captured signals from at least one point of interest to the memory block.

The memory controller may be arranged to duplicate a captured signal to provide two duplicates of the captured signals to transfer one duplicate of the captured signal to the memory block and to optionally output another duplicate of the captured signal from the FPGA via the communication element for example to a Host computer.

The memory controller may be arranged to receive a request from a user for obtaining captured signals that have been captured at previous point in time that occurred at least one fraction of a second before the receiving of the request and to optionally send to host computer the captured signals.

The memory controller may be arranged to receive a request from a user for stopping an execution of the additional program and ignore captured signals that have been stored before receiving the request by the memory controller of the FPGA but after the request has been issued by the user.

The memory controller may be arranged to tag captured signals and retrieving captured signals from the memory block based on values of tags associated with the captured signals.

The subject matter regarded as the invention is particularly pointed out and distinctly claimed in the concluding portion of the specification. The invention however both as to organization and method of operation together with objects features and advantages thereof may best be understood by reference to the following detailed description when read with the accompanying drawings.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numerals may be repeated among the figures to indicate corresponding or analogous elements.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

The following text refers to an evaluation process. It is noted that the evaluation process may be a debugging process a verification process a quality evaluation process a calibration process an optimization process or any feedback based process.

The following text refers to an FPGA. It is noted that the methods and devices illustrated below can be applied mutatis mutandis on ASICs System on Chip SoC or other programmable design integrated circuits.

An FPGA design includes multiple points of interest that can be probed to provide captured signals. The captured signals are sent via probes and a memory controller included in the FPGA to a memory.

The system can be used during various processes or phases of the design process including but not limited to FPGA design verification and simulation stages evaluation of systems that include FPGAs such as but not limited to SOC System On a Chip hardware accelerators that include one or more FPGAs machine vision systems mathematical simulators and the like. The system can be used not only at the debug or simulation phases but also during nominal or normal use in the field or at a customer site.

According to an embodiment of the invention the evaluation process can be adjusted according to user preferences. The configuration process can utilize a configuration graphical user interface GUI that can be provided by a control application that is hosted by host . The configuration process can also utilize an Application Programming Interface API 

A configuration process can include determining which captured signals to send to the memory how to react to triggers which channels to be sent to the host for the evaluation application which FIFOs will act as input FIFOs which FIFOs will act as output FIFOs how to transfer captured signals to the memory what is the probing frequency for each signal and the like. For example a trigger can stop the writing of captured signals to the memory can stop the capture of signals can start the capture of signals by the probe and the like. Yet for another example a user can request to store captured signals of a certain type while ignoring captured signals of another type.

According to an embodiment of the invention the system can output captured signals in parallel to a provision of these captured signals to an external circuit such as but not limited to an evaluation circuit. The parallel operation may be facilitated by connecting one or more probes to the on board memory as well as to data interfaces that are coupled to the evaluation circuit. The real time or almost real time provision of captured signals to an external circuit such as a host facilitates an evaluation process that is responsive to captured signals. The evaluation process can stop continue or issue a triggering signal in response to one or more captured signal or in response to a result of an analysis of one or more captured signals.

The memory can be large for example a few gigabyte few tens of gigabytes 256 gigabytes or more and then a vast amount of captured signals can be stored. This vast amount of captured signals can be obtained over a very long period of time and can be used for one or multiple evaluation processes. In ASIC prototyping applications this vast amount of captured signals is of prime importance. It is noted that the entire memory can be used for storing the captured signals for evaluation purposes or a part of memory can be used for the normal nominal applications while another part is allocated for the evaluation application. Accordingly there may be no need to add memory for evaluation purposes.

Multiple triggers can be sent to the FPGA and the memory can store responses of the FPGA to multiple triggers thus facilitating an analysis of captured signals that are responsive to these multiple triggering signals.

The evaluation process utilizes already existing connections between the FPGA and the host and uses FPGA resources to control and apply the evaluation process. Accordingly a product that is sold or otherwise provided to the customer has extensive evaluation capabilities. In addition there is no need to add additional dedicated hardware controller memory cables connectors probes etc. to the system and the evaluation process can be performed at the full operational speed of the FPGA.

The system allows a user or any other person to evaluate the FPGA even after the FPGA is shipped from the manufacturing facility and can provide a large amount of information that is being captured over long periods of times and from multiple points of interest without using sophisticated and costly analysis tools.

Predefined triggers can be evaluated in real time can be programmed to be very complex and can be changed by altering the definitions provided to the memory controller and without compiling the entire FPGA data base.

Captured signals can be stored in the memory module for a long period even after the FPGA is re configured.

The system is connected via communication element to host . Host hosts various applications such as evaluation application and control application . Evaluation application can retrieve captured signals from various points of interest within FPGA process the captured signals to provide evaluation results display captured signals send the captured signals to other applications and additionally or alternatively display the evaluation results allow a user to send evaluation commands such as stop retrieve information repeat an execution of commands can instruct FPGA to stop a evaluation sequence and the like. A user can interact with FPGA via host . The processing can include decrypting ciphered signals

For example the design support application may generate C Class application drivers for incorporation with the evaluation application . The design support application may generate top level design and interface module entity for each FPGA and program the FPGA accordingly. Yet for another example the design support application may perform hardware initialization may load FPGA and the like.

The host computer can include a man machine interface MMI such as a display a keyboard a mouse and the like. The MMI can be used to display outcomes of the evaluation process can be used to receive commands from the user and the like.

The host computer allows the user to elect a number of memory channels referred to as trace ports in field to elect a memory space allocated for each port field and to elect which memory space to allocate. The screen also displays a total size of memory space allocated field a clock signal frequency that determines the sampling frequency field and a schematic image of multiple ports that are connected via a multiplexer to the host computer . The screen also indicates that the application that is being configured is related to the evaluation application also referred to as total history .

It is noted that each point of interest of each memory channel port can also be configured. illustrate screens and that allow to define different points of interest probes that are referred to as fields. For example if a certain port is 128 bits wide these 128 bits can be allocated between different probes as shown in . for example illustrates the allocation of bits to to a field i.e. a probe designated Field1.

The memory block of device can operate at a higher rate than the memory controller and thus can both receive captured signals and output captured signals without interfering in the sampling process of the captured signals.

Communication element can be a PCI Bridge an Ethernet Controller another Interface or may even not be needed at all. It can include a communication medium such as a bus multiple buses PCI bus Ethernet the Internet and the like.

Communication element connects FPGA to the Host via a communication medium. It is noted that other interfacing circuits can be used and that Communication element is only an example of such an interfacing circuit. For example FPGA can be connected to a Printed Circuit Board PCB that has one or more connectors that provide connectivity between host and FPGA . The connectivity can utilize various communication protocols such as Ethernet but this is not necessarily so. FPGA and memory can be connected to the same PCB. Memory may be an on board memory. Memory denoted memory block communication element and FPGA can all reside on the same PCB. It is noted that a single PCB can include multiple FPGAs and multiple memories.

It is noted that although illustrates a single controller single memory module and a single memory controller per a single FPGA this is not necessarily so and multiple memory controllers memory modules and or controllers can be allocated per FPGA. Different memory controllers can cooperate or operate independently from each other. Different memory controllers can be coupled to different logics or to the same logic of the FPGA can share a memory module or use different memory modules can communicate by the same communication interface or via different communication interfaces.

FPGA is programmed to fulfill one or more tasks such as mathematical calculation acceleration video processing routing data packet processing machine vision processing and the like. These tasks or functions are referred to as nominal or normal functions and are implemented by logic circuits in FPGA such as logics and . Normal tasks may differ from the evaluation of FPGA . Logics and are also referred to as cores of intellectual property IP .

FPGA is designed to include one or more logics such as logics and controller memory controller . Logics and can be video processors video accelerators data processors and the like.

Multiple points of interest may be defined in each of these logics. also illustrates a point of interest that is connected to a pin of FPGA in order to receive signals from a component of system that differs from FPGA . Although illustrates six points of interest three from each logic and and a single external point of interest it is noted that the number of points of interest can differ from seven. For example the number of points of interest can exceed forty one thousand and can even exceed 50 000. It is further noted that the number of points of interest of logic can differ from the number of points of interest of logic .

The points of interest and are coupled via probes to memory controller and controller . A probe can include a sampling circuit a multiplexer logic gates small memory and the like.

The number of points of interest is selected during the design stage of the FPGA. This may be done after the design of the nominal logic as part of the evaluation phase depending on what the user is looking for. More points of interest may provide more detailed information about the FPGA but may require more memory controller channels more memory bandwidth and more memory space. It is noted that FPGA may be dynamically configured to select captured signals from certain points of interest while ignoring captured signals from other points of interest. The selection can be responsive to user preferences stage of the evaluation process errors or possible errors detected from signals provided from a point of interest and the like.

Points of interest are connected via probes illustrates as lines in to memory controller . It is noted that each probe may be connected to a channel of memory controller . A probe can be a conductor can include memory elements can be connected to memory elements can include logic gates can include a selection unit or can be connected to selection unit and the like. It is further noted that a probe can have a configurable throughput. A probe can include some of the components of a memory controller channel such as FIFO logic and the like.

Memory controller is connected to controller and to memory . Memory can include one or more memory chips or a portion thereof. It can include multiple memory banks.

FPGA can include multiple memory controllers that are connected to multiple memories but for simplicity of explanation only illustrates a single pair of memory and memory controller .

Controller participates in an evaluation process by controlling the storage and additionally or alternatively a retrieval of captured signals obtained from points of interest.

Controller controls memory controller by performing at least one of the following operations i sending memory controller memory mapping information indicative of mapping between memory controller channels and memory spaces of memory ii sending control signals such as Valid control signal Frame indication control signal Data indication control signal and the like indicative of when to store captured signals that are sent to the channels of memory controller iii sending reset signals iv sending channel information indicative of which channels of memory controller are allocated for storing or retrieving points of interest information. It is noted that memory controller can be controlled by more than a single controller.

By mapping different memory spaces to different memory controller channels captured information from one point of interest does not overwrite captured information from another point of interest. Typically the size of memory spaces is selected to facilitate storage of point of interest information for a desired period of time. By using a large memory the desired period of time can be very long virtually unlimited for evaluation purposes. In the memory mapping information is illustrated as channel memory mapping .

Control signals are usually sent from logic or logic to describe the information that is being outputted by these logics. If for example logics process video frames they may output control signals such as Valid and Frame indication but this is not necessarily so. A Valid control signal indicates when a point of interest captures valid captured signals. A Frame indication may indicate a start of a logical frame or other significant point in time associated with a logical frame . A logical frame can be for example a video frame part of a video stream or a communications packet received from a communication channel . It is noted that the captured signals other than video can be arranged in frames packets or other data structures and can be accompanied with various control signals that may be also detected and or processed by the memory controller.

It is noted that a single control signal or a single set of control signals can indicate when to sample captured signals from one or more probes. For example a frame indication and a valid indication can trigger storage of captured signals from multiple points of interest. Accordingly not every point of interest may have its own control signals and multiple channels of the memory controller can be controlled by the same control signals or the same set of control signals.

It is noted that controller can receive a control signal and generate derivative control signals by performing logic operations time shifting control signals and the like.

A reset signal can clear a memory controller channel and can also be used to either clear a memory space associated with a channel of the memory controller or to assist in overwriting the content of that memory space. The latter can be achieved by setting a write pointer of a channel to the beginning of the memory space.

The allocation of memory controller channels that will take part in the evaluation process can be made by a user via host but can also be done automatically while taking into account memory controller channels that are allocated for non evaluation tasks such as nominal operation of the FPGA these normal operation may also be referred to as additional operations or additional programs . By allocating memory controller channels for non evaluation purposes system can maintain its normal or nominal operation and also perform evaluation.

By allocating memory controller channels that are not used for normal or nominal operation for evaluation purposes system can maintain its normal or nominal operation and also perform evaluation.

Controller can decide which points of interest to sample based upon the number of vacant memory controller channels and selection parameters such as a priority of points of interest which logic of FPGA is active or should be evaluated and the like. Referring to interconnecting circuit of memory controller can elect which points of interest or other signals providers are sent to channels of memory controller . The interconnecting circuit can include multiplexers logic gates and the like.

Memory controller may receive multiple captured signals at real time and at a full operating frequency of logics and and can also send in real time captured signals via Communication element to host . Captured signals from one or more points of interest can be received by one or more memory controller channels and sent to memory and to host in real time. Accordingly while capture signals are stored in memory some of them are also sent to host . This dual operation can be implemented by allocating a first memory controller channel to send captured signals to memory operate as an input channel and allocating another memory controller channel to send these captured signals to host operate as an output channel . According to an embodiment of the invention captured signals are stored in memory and then are sent to the output channel for example to a Host computer.

According to another embodiment of the invention the captured signals are duplicated in an interconnecting logic of memory controller that includes a bypass circuit . Bypass circuit has an input for receiving captured signals and two outputs that send captured signals and duplicated signals to memory and to the output memory channel.

It is noted that the link between memory controller and memory can have a higher and even much higher throughput than the links between points of interest and memory controller so that sampled signals can be written to memory and read from memory to the output channel while the input channel is fed by other captured signals.

Those of skill in the art will appreciate that the throughput differences can be attributed to clock signal frequency bus width or a combination thereof. For example if there are K channels then in order to obtain a full parallel operation with all K channels the throughput of link between memory and memory controller should be at least K times higher than the throughput of the slowest memory channel.

Memory controller is configured to manage multiple channels. Each channel is associated with a transfer of data such as but not limited to captured signals from memory or to memory . The channels can be mutually independent.

A memory controller channel includes a FIFO and associated logic. For simplicity of explanation the different logics of the different channels are not shown as they are included in memory controller logic . The logic of each channel can maintain a pointer start pointer to a start address of a memory space allocated to the channel can maintain a pointer updated pointer to the next memory entry to be written to or a combination thereof. Each channel logic can prevent invalid data to be sent to FIFO or from the FIFO to memory . Additionally or alternatively interconnecting circuit can prevent the writing of invalid data to the FIFOs.

Arbiter is connected to each of FIFOs and and selects which FIFO is connected to link . Arbiter can apply any prior art time division multiplexing algorithm. It can receive for example from host arbitration scheme information that determines how to arbitrate between the different channels. Non limiting of arbitration schemes include round robin weighted round robin sequential arbitration starvation prevention arbitration schemes priority related arbitration schemes and the like.

According to an embodiment of the invention captured signals can be tagged by one or more tags. These tags can be stored at the memory and can be accessed during the retrieval of captured signals. A tag can indicate for example a type of captures signal for example whether it is a data signal a video signal a control signal a frame delimitation signal and the like. Captured signals can be selectively retrieved by using these tags. Non limiting example of tags can be video frame tag data packet tag and the like.

According to an embodiment of the invention timestamps may be associated with captured signals. The timestamps can be generated by a probe by a time stamp circuit that is utilized by multiple probes and the like. A timestamp can indicate when a signal was captured or at least provide an indication about a time window in which the signal was captured. Additionally or alternatively a timestamp can indicate a triggering signal that triggered to capture of the signal.

Controller includes controller logic and multiple stacks K . Controller logic receives control signals from logics and and additionally or alternatively from host . In response to these control signals it can send to memory controller instructions that determine when to store signals provided from points of interest can select which points of interest will be ignored of and can maintain pointers to groups of captured signals.

A group of captured signals can be a video frame a group of pictures a data packet a data frame and the like. Each stack stores a set of pointers to memory that point to different groups of captured signals of a single channel. In general the j th pointer of the k th stack points to the j th group of captured signals of the k th channel. For example stack stores pointers J to up to J different groups of captured signals of the channel associated with stack in memory. The pointers point to entries of memory .

These stacks facilitate a fast retrieval of information of interest. For example if there is a need to send a certain frame to host the appropriate stack can be scanned and the appropriate pointer can be utilized for obtaining that frame to host .

Controller can generate a pointer when it receives Frame and Valid indications. The value of the pointer should equal the address of the memory entry of memory to which the frame is being written. Controller can track after the progress of writing of each channel controller can have its own counters such as counters or can retrieve the information from memory controller logic .

According to an embodiment of the invention timestamps may be associated with captured signals. The timestamps can be generated by a probe by memory controller by controller or by another timestamp circuit. A timestamp can indicate when a signal was captured or at least provide an indication about a time window in which the signal was captured. Additionally or alternatively a timestamp can indicate a triggering signal that triggered to capture of the signal.

Conveniently the fast capturing of signals and the ability to store a large number of captured signals in memory facilitates extensive analysis of FPGA and especially allows tracking after signals captured during relatively long periods of time.

A user can request to stop the execution of a program that is being executed by FPGA and is also being evaluated. Additionally or alternatively the user can request to trigger. The request can arrive at a significant and even long or unpredictable delay to controller after an interesting event from evaluation point of view occurred. This delay does not hamper the evaluation process because captured signals that were stored at memory even long time before the request can be retrieved and sent to evaluation application .

Method starts by initialization stage . This stage can include loading one or more evaluated program to FPGA loading the evaluation program to FPGA resetting memory controller channels receiving mapping information indicative of mapping between memory controller channels and memory spaces of memory determining which FIFOs to allocate for the evaluation process and out of those FIFOs which will act as input FIFOs and which will act as output FIFOs selecting which points of interest to monitor and the like.

Stage is followed by stage of executing multiple programs by the FPGA one of them being an evaluation program and at least one other program may be program that is being evaluated. Stage may include executing the programs at the full operational speed of the FPGA or at an execution speed that such programs were to be executed at the absence of the evaluation program. Alternatively stage may include executing the programs at a lower speed and even much lower speed than the execution speed that such programs were to be executed at the absence of the evaluation program.

Stage includes at least one of the following stages i stage of sending to multiple memory controller channels included in the FPGA captured signals from multiple points of interest ii stage of storing captured signals at an on board memory iii stage of sending captured signals to host iv stage of interacting with a evaluation application v stage of tagging captured signals vi stage of generating pointers to groups of captured signals vii stage of arbitrating between memory controller channels viii stage of time stamping captured signals.

Stage and even stage can be conditioned by receiving a valid indication receiving a frame or data packet indication and the like.

Stage can include receiving a user command to start the evaluation stop the evaluation resume the evaluation change an execution mode of a program that is evaluated retrieve certain captured signals retrieve captured signals related to a certain time window and the like.

The methods and or processes may be implemented as a computer readable medium having a computer readable code embodied therein the computer readable code including instructions for the carrying out of at least one of the above disclosed methods and processes.

Method starts by stage of configuring the FPGA to execute in parallel an evaluation program and an additional program wherein an execution of the additional program is being evaluated by the evaluation program. In a nut shell stage may include determining which captured signals to send to the memory how to react to triggers which channels to be sent to the host for the evaluation process and which to allocate to nominal processes which FPGA memory controller memory channels will act as input memory channels which will act as output memory channels how to transfer captured signals to the memory what is the probing frequency for each captured signal and the like.

Stage includes sending to the memory controller of the FPGA predefined responses to triggers received by the memory controller of the FPGA. Non limiting examples of the predefined responses may include i storing an outcome of an execution of a predefined response to a trigger at the memory block and outputting the outcome ii storing captured signals of a certain type while ignoring captured signals of another type iii stopping a capture of captured signals from a point of interest iv starting a capture of captured signals from the point of interest v altering a probing scheme that determined how signals are being captured or which signals are being captured changing points of interest changing a sampling rate of captured signals changing a width of points of interest and the like.

Stage includes selecting captured signals to be stored in the memory block and selecting captured signals to be ignored of wherein the selecting is responsive to a stage of an evaluation process.

Stage include selecting captured signals to be stored in the memory block and selecting captured signals to be ignored of wherein the selecting is responsive to previously obtained data or previously detected errors in an execution of the additional program by the FPGA.

Stage is followed by stage of executing by the FPGA the evaluation program and the additional program.

Stage includes receiving by a memory controller of the FPGA captured signals from multiple points of interest of the FPGA. The captured signals can be received at a high rate from many points of interest. For example the number of points of interest may be at least forty and the rate of reception of the data per each point of interest may be at least sixteen bits per clock cycle.

Stage includes processing the captured signals. The outcome of the processing can be stored in the memory block can be outputted from the FPGA can be retrieved from the memory block and the like. The processing may include decoding encoded captured signals decrypting ciphered captured signals and the like.

Stage includes transferring by the memory controller of the FPGA at least a portion of the captured signals to at least one memory space of a memory block via memory channels of the FPGA. The captured signals can be stored in one or more memory spaces of the memory block. The aggregate size of these one or more memory spaces memory block can exceed few megabytes few tens of megabytes few hundred of megabytes few gigabytes and even more. Accordingly a large amount of captured signals can be stored from a very long period of time and from a large number of points of interest.

Stage includes outputting by the memory controller of the FPGA at least a portion of the captured signals from the FPGA via a communication element for example to a Host computer. Stage may include retrieving captured signals from the memory block and outputting the retrieved captured signals to a host computer or to one or more another components located outside the FPGA.

Stage may include transferring by the memory controller of the FPGA at least a portion of the captured signals to at least one memory space of a memory block based on a mapping between memory channels of the memory controller and memory spaces of the memory block.

Stage includes receiving by the memory controller of the FPGA at least one video related control signal selected from a frame indication and a valid indication and storing video related captured signals from at least one point of interest to the memory block. It is noted that stage can include receiving control signals that are related to frames or other data structures that differ from video frames.

Stage includes duplicating by the memory controller of the FPGA a captured signal to provide two duplicates of the captured signals. Stage may include transferring by the memory controller of the FPGA one duplicate of the captured signal to the memory block and stage may include outputting by the memory controller of the FPGA another duplicate of the captured signal from the FPGA via the communication element for example to a Host computer.

For example stage may include receiving a request from a user for obtaining captured signals that have been captured at previous point in time that occurred at least one fraction of a second before the receiving of the request.

In such a case stage may include sending to a host computer the captured signals. The user can detect an event such as an error in a video image and may wish to obtain captures signals that were generated during the event or before the event. The user may respond to the event at a certain delay for example after a fraction of a second or after one or more seconds . The request is generated by a host computer that executed an evaluation program that may assign a time stamp or other identifying information to the request of the user. The time stamp is used to retrieve the relevant captures signals that may be already sent to the memory block or stored in the memory controller.

For example stage may include receiving a request from a user for stopping an execution of the additional program and ignoring captured signals that have been stored before receiving the request by the memory controller of the FPGA but after the request has been issued by the user.

Yet for another example stage may include receiving a request from a user for obtaining captured signals that have been captured at previous point in time that occurred at least one fraction of a second before the receiving of the request and sending to a host computer the captured signals.

The processing may include tagging captured signals. These tagged captures signals may be retrieved from the memory block based on values of tags associated with the captured signals.

The system illustrated in the previous figures can be characterized by the following characteristics captures any FPGA internal signals and nodes including embedded processor busses and IPs provide a direct interface to user s debugged application the probing does not require additional HW logic overhead uses practically unlimited memory capture for example memory block can be at least 4 GB provides scalable ultra deep sampling depth provides embedded real time probing at design s full operating speed supports flexible triggering thus allowing selective tracing uses API methods for user application utilizes PROCWizard automatic user application generator includes a flexible clocking system may be supported by GiDEL s PROCDeveloper s Kit accelerates or expedites debugging process to minutes hour PROCWizard software intuitive GUI to define and configure multiple probe IPs within the user s design includes minimum pin impact for debug letting you free up pins for the rest of your design.

Reconfigurable FPGA designs enable extremely flexible and powerful parallel processing architecture yet have been somewhat impeded by a lack of evaluation visibility. The complexity of today s design makes it almost impossible to debug a design using traditional logic analysis methods. Evaluation often captures over 50 of the development time. Thus an efficient flexible debugging tool that is founded on accurate signal capture and abundant visibility depth is essential to accelerating optimizing the developmental cycle.

The system illustrated in the previous figures may be used as a signal tracing tool for Altera FPGA based GiDEL PROC Boards enabling to trace any of the design signals while providing practically unlimited signal probing depth readily available to the user s choice of debugging verification tools.

The probes illustrated above may form multi probe IP cores that are embedded into the user s design. These probes inserted in any design point of interest may capture signals at full system speed and output them from the on board memory memory block via a communication element such as a PCI e bridge to the user s debug application hosted on host computer . Each FPGA IC can work with multiple for example 48 fully configurable parallel virtual probes each with a multiple for example 16 bytes per cycle bandwidth. Probe trace memory is virtually unlimited with up to 4 GB SODIMM memory per IC thus enabling virtually infinite signal tracing regression to accurately reproduce bugs.

The system may be used for various applications such as but not limited to ASIC prototyping machine vision and algorithm validation.

The system can be a part of various development environments such as but not limited to GiDEL s fully integrative FPGA development platform that includes GiDEL s line of PROC Boards and the PROCDeveloper s Kit software package.

The PROCDeveloper s Kit an intuitive design and debug environment facilitates design development effort and enables simple straightforward insertion of the mentioned above IP Probes. The kit contains a design support application such as PROCWizard the system illustrated above Quartus and USBBlaster and a PROCHIL option.

The PROCWizard performs hardware initialization and automatically generates the following interface documentation in HTML or Microsoft Word C classes application drivers enable simultaneous accesses of multiple applications each to its dedicated section of the PROC board top level designs interface modules entities and on board memory controllers for the application use device constraints as pin outs .

The illustrated above system allows for simultaneous access to multiple parts of the FPGA design at variable clock frequencies. At the same time it enables parallel access to the on board and SODIMM memories while enabling to split the physical memory into multiple logical memories. As a result the system provides a flexibility to set probes at any desired design point a flexibility to trigger control each individual probe virtually unlimited trace history memory selective visibility depth and it may provide a replacement for the need for inventory of special memories by using standard memory and IP.

While certain features of the invention have been illustrated and described herein many modifications substitutions changes and equivalents will now occur to those of ordinary skill in the art. It is therefore to be understood that the appended claims are intended to cover all such modifications and changes as fall within the true spirit of the invention.

