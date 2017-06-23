---

title: Embedded robot control system
abstract: The present invention relates to an embedded robot control system, particularly to an embedded robot control system of a highly expandable distributed control mode. An aspect of the present invention features an embedded robot control system. In accordance with an embodiment of the present invention, the embedded robot control system, which controls a plurality of robot instruments, which have a motor and a sensor, and a robot, which is connected with the plurality of robot instruments, can include a master controller, which is installed on the robot and controls the motor and the sensor of the robot instrument, and a slave controller, which is installed on another robot, connected to the robot, or the robot instrument and receives a control signal of the motor or the sensor from the master controller and controls the motor and the sensor.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09086694&OS=09086694&RS=09086694
owner: Samsung Heavy Ind. Co., Ltd.
number: 09086694
owner_city: Seoul
owner_country: KR
publication_date: 20100513
---
This application is a continuation and claims the benefit of priority under 35 U.S.C. 120 365 and 371 to Patent Cooperation Treaty Patent Application No. PCT KR2008 006699 filed on Nov. 13 2008. This application further claims the benefit of priority to Korean Application No. 10 2007 0115824 filed Nov. 14 2007. The disclosures of the above applications are incorporated herein by reference in their entireties.

The present invention is related to an embedded robot control system more specifically to a distributed control type of embedded robot control system.

Referring to the conventional robot control system includes one unit of an external central control apparatus an external DSP digital signal processor controller which is installed on each of a plurality of robots and and a teaching operator which is connected to each external DSP controller .

The external central control apparatus is connected to the plurality of robots and through each corresponding external DSP controller and controls the plurality of robots and .

The external DSP controller performs computations related to the operation of each of the robots and and controls the robots when a control signal for the operation of the robots is received from the external central control apparatus or a command is inputted in the teaching operator .

The DSP controller handles a large number of computations for the operation of each of the robots and and thus is installed separately from the external central control apparatus .

In addition each external DSP controller requires a large number of relatively complex circuits and in order to be connected to the external central control apparatus .

The teaching operator is connected to each of the robots and through the external DSP controller and receives a command for the operation of the robots.

The conventional robot control system requires separate electronic circuits for the control of robots inevitably increasing the size of the controller and thus it is necessary that a plurality of controllers be used for the control of several robots. As a result it has not been possible to mount the external central control apparatus or the external DSP controller on the robots and .

Moreover the large number of cables required for communication of signals between the external central control apparatus the external DSP controller and the robots and often cause malfunction in the robot control system hampering the operation of the robots.

Contrived to solve the above problems the present invention provides an embedded robot control system having internal controllers that are distributed in each robot instrument.

An aspect of the present invention features an embedded robot control system. As an example only in one embodiment the embedded robot control system which controls a plurality of robot instruments which have a motor and a sensor and a robot which is connected with the plurality of robot instruments can include a master controller which is installed on the robot and controls the motor and the sensor of the robot instrument and a slave controller which is installed on another robot connected to the robot or the robot instrument and receives a control signal of the motor or the sensor from the master controller and controls the motor and the sensor.

The embedded robot control system of the present invention can dramatically reduce the number of cables solve the problem of narrow installing space and overcome the limitation of the robot operation by introducing an FPGA based master controller and encompassing a serial network through the installation of an FPGA based slave controller for each of the robot instruments distributed from the robots.

Moreover the serial network of the embedded robot control system of the present invention can communicate in real time and automatically reconfigure itself when the network is disconnected.

Furthermore the embedded robot control system of the present invention has a logic corresponding to a serial robot a parallel robot and an orthogonal robot and allows the corresponding logic to be selected enabling the operation control regardless of the kind of robot.

Since there can be a variety of permutations and embodiments of the present invention certain embodiments will be illustrated and described with reference to the accompanying drawings. This however is by no means to restrict the present invention to certain embodiments and shall be construed as including all permutations equivalents and substitutes covered by the spirit and scope of the present invention.

Hereinafter some embodiments will be described in detail with reference to the accompanying drawings. Identical or corresponding elements will be given the same reference numerals regardless of the figure number and any redundant description of the identical or corresponding elements will not be repeated.

Referring to the embedded robot control system of the present invention includes a master controller and a plurality of slave controllers which are networked with the master controller .

The master controller includes an FPGA Field Programmable Gate Array a master processor M a master network module an input output module an application programming interface and an application module and handles the multiple operation control and multiple sensor control of a plurality of robot instruments.

Indicating the scope of digital control by one FPGA the master controller allows the controller of the present invention to be smaller and less power consuming.

As a controller includes a number of semiconductor devices the size of the controller and the power consumption by the controller are proportional to the number of the semiconductor devices. The present invention reduces the number of semiconductor devices by allowing the FPGA to handle all digital processes needed for the control of the robots thereby reducing the size of the controller installed in the robot instrument.

The master controller uses a light kernel such as the real time operating system of RT Linux uCOS or xilkernel to handle the multiple operation control and multiple sensor control.

The FPGA elements and consist of a soft processor and a memory or dedicated hardware logic and computes an operation plan for the control of the robot or robot instrument. Here an FPGA element refers to a functional element processed by one FPGA.

Here the FPGA elements and can be expanded to tens or hundreds of elements through for example a method of using an element expansion area or a method of forming logic in an LUT Look up Table by an SRAM not shown . Therefore the present invention does not restrict the number of FPGA elements and which can be expanded or chosen according to the number configuration types and or process speed of the robots.

The FPGA elements and can easily design and or change the logic are relatively smaller and generate less heat. Moreover the FPGA elements and are not memory resource or CPU resource intensive which used to be common in mult task operation of a DSP digital signal processor or a PC personal computer and consume less power.

The FPGA elements and include trajectory generation modules TG hereinafter and robot kinematics modules RM hereinafter for the real time control of the plurality of robots.

The FPGA elements and can change the number of TGs and RMs depending on the required process speed of the TG and RM and thus can use the resource of the robot control system efficiently.

The TG generates a time based trajectory of spatial movement of each robot tool coordinate system or each robot base coordinate system in a work space.

The TG can also rotate move the robot tool coordinate system or robot base coordinate system to respond to an external event such as the sensor in real time.

The RM computes the operating location of motors included in the robot using a tool mount coordinate system and an instrument parameter e.g. DH parameter of the robot. Here the tool mount coordinate system and instrument parameter are determined together with the robot tool coordinate system and robot base coordinate system which are obtained by the TG according to the type of robot.

The RM also computes the torque needed by each joint using same property parameters e.g. friction and inertia of each link of the robots the direction of gravity and external forces applied to the robots.

The RM sends a target location among the computed operation locations and a target torque among the computed torques of the motors to each motor driver through the network. Here the target location and the target torque are used for a feed forward control of each motor.

The RM can also compute a coordinate system on the current work space based on the operating locations of the motors included in the robots.

The master processor M is connected to each of the FPGA elements and and generates a control signal for operating a motor and a plurality of sensors in accordance with an operation plan of the robot instrument. The master processor also manages the operation status of the robot instrument which is operated through the control signal.

In other words the master processor M runs a program in work units such as the operation plan and monitors for example operation errors.

The master processor M also handles connection management between the FPGA elements and monitoring management and input output management.

Moreover the master processor M controls the communication of signals between each of the slave controllers and the FPGA elements and as the master processor is connected to the master network module to handle the communication.

Furthermore the master processor M is connected to the application module APP through the application programming interface API .

The application module includes application programs for robot operating logic and robot resetting operation e.g. calibration and other robot related application programs that are preconfigured for each of the serial robots parallel robots and orthogonal robots. Here the robot operating logic is activated in accordance with the selection of logic by a user and according to a corresponding trajectory generation module controls in real time the movement of trajectory among the control and movement of the robot in the work space where the plurality of robot instruments are operated

The application programming interface is connected to a general purpose input output GPIO represented by G in which handles the input and output of various sensors or the input and output of various signals. For example the GPIO is connected to the robot instrument of a first robot and its various surrounding sensors.

The master network module handles the communication with slave network modules and which are installed in the slave controllers through the cables. The slave network modules and also communicate with one another through the cables.

Here it is preferable that the master network module and the slave network modules and have a plurality of communication ports which comply with the pertinent communication standard for expanded connection of cables.

The master network module and the plurality of slave network modules and form a serial network through the cables. This allows for relatively smaller simpler cable configuration of the present invention over the related art.

The slave controllers includes slave processors S S slave network modules and and motor drivers D D for driving the motors. It is possible that the slave controllers further have a GPIO G which inputs and outputs various signals to and from the robot instrument of a second robot and its surrounding sensors.

The slave controllers realizes distributed control of the plurality of robots and the robot instrument by linking with the master controller through the corresponding slave network modules and and the master network module .

The slave processors S S is connected by the corresponding slave network modules and to be linked with the FPGA elements and of the master controller .

The slave network modules and are connected to the master network module to communicate a signal for linking with the master controller .

The slave network modules and can realize the real time communication and be automatically reconfigured when the network is disconnected by realizing a network technology in which the master network module and the 7 levels of OSI open system interconnection are modified for the present invention.

Each of the motor drivers D D is connected to each of the slave processors S S respectively to drive the motor.

The motor drivers D D can handle the servo control of each motor in accordance with the target location and target torque received from the RM of the master controller . It is also possible that the servo control of each motor is handled independently.

Therefore the motor drivers D D monitor the driver input voltage the driver input current the current applied to each motor and an absolute or relative encoder value of each motor. The motor drivers D D are also capable of performing the switching operation of each motor and have limiting and braking functions for the control of each motor.

The GPIO G is connected with the robot instrument of the second robot and its surrounding various sensors.

As illustrated in the embedded robot control system of in case one master controller and a plurality of slave controllers are installed in two robots that is the first robot and the second robot the master controller and three slave controllers and which are connected for serial communication can be installed in the first robot and the remaining four slave controllers and can be installed in the second robot.

Referring to the master controller is installed at a base such that the master controller can be connected to a robot instrument of a first robot .

Later the slave controllers and are installed such that each of the slave controllers and is connected to each of robot instruments and respectively which are distributed in the first robot .

The master controller is connected with the first slave controller through the cable and the following two slave controllers and are successively connected through the cable .

This way the master controller forms a serial network with the three slave controllers and through the use of a very small quantity of cable thereby enabling a distributed smaller structure over the conventional robot control system.

Likewise the remaining four slave controllers and are installed in the second robot and connected to the corresponding robot instruments and in the same manner of the master controller and corresponding slave controllers and .

It is possible that a separate second robot is configured through the same internal configuration and method as the second robot and that the connection is expanded as long as the serial communication standard is met and the master controller can handle.

The master controller of the first robot and the fourth slave controller of the second robot are connected to each other through the serial network cable and it is also possible that the separate second robot is connected to the second robot through the cable .

As shown in the master controller is not only connected physically with other elements through the cable but also linked logically with each of the motor drivers D D and the GPIO G as indicated with dotted lines .

Moreover the slave processors S S can directly control the GPIOs G and G through dotted lines in order to respond to emergency situations occurred during the operation of the robots.

Since the master controller is logically linked with the GPIOs G and G and the slave processors S S are also logically linked with the GPIOs G and G the plurality of slave controllers can be controlled.

Furthermore the master controller and the slave controllers are formally or physically connected through the cable by the ring topology form.

For example the master network module and the slave network modules and are configured in a full duplex mode i.e. transmission and reception being separated .

In case there is a disconnection or short circuit in any cable the master network module receives information on the disconnected or short circuited cable from one of the slave network modules and that is related to the pertinent cable.

In this case the master network module and all slave network modules and switch to a line topology form from the ring topology form to continue to operate the full duplex mode in the case of disconnection or short circuit of some cable.

That is through data transmission route change information received from the slave network modules and the master network module can send the data which was transmitted through one route through two routes enabling the communication without any interruption in the system.

When the disconnected or short circuited cable is returned to the normal condition the master network module receives information on the normalization from the slave network modules and enabling the transmission of the data through one route again. That is the line topology form can be switched back to the ring topology form.

While the invention has been described with reference to an embodiment shown in the drawings the embodiment is for illustrative purposes only and shall not limit the invention. It is to be appreciated that those skilled in the art can change or modify the embodiment without departing from the scope and spirit of the invention. As such many embodiments other than that set forth above can be found in the appended claims.

