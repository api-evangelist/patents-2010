---

title: Component integration apparatus and method for collaboration of heterogeneous robot
abstract: Provided is a technique that enables a robot to be remotely controlled (by a server) and enables a robot component to access an external component (a component of a server) in order for cooperation of heterogeneous robots operating on the basis of different component models. A component integration apparatus for collaboration of a heterogeneous robot according to an embodiment of the present invention comprises: a standard interface unit that provides a common standard interface for controlling components that control the individual functions of the robot; an adapter component that transmits commands to enable external components to call the components through the standard interface unit; and a proxy component that transmits commands to enable the components to call the external components through the standard interface unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08660693&OS=08660693&RS=08660693
owner: Electronics and Telecommunications Research Institute
number: 08660693
owner_city: Daejeon
owner_country: KR
publication_date: 20101215
---
This application claims the benefit of Korean Patent Application No. 10 2009 0126722 filed on Dec. 18 2009 and Korean Patent Application No. 10 2010 0029956 filed on Apr. 1 2010 which are hereby incorporated by reference in its entirety into this application.

The present invention relates to a component integration apparatus and method for collaboration of a heterogeneous robot and more particularly to a component integration apparatus and method for collaboration of heterogeneous robot which enables a robot to be externally controlled and enables a component of a robot to access an external component in order for collaboration of heterogeneous robots operating on the basis of different component models.

In general it is a recent trend for robot platforms having various actuators and sensors to use component based application programming models in order to controlling and integrating the individual actuators and sensors. In other words component based application programming models define individual component specifications with respect to controls of the individual unit devices of robots for example wheel control head control touch censor control distance sensor control position sensor control etc and robot apparatus developers implement and provide robot apparatuses based on corresponding specifications.

However such component based application programming models have the following limits in distribution robot applications in which heterogeneous robots cooperate.

First since it is difficult to standardize component models used in robot platforms because of practical reasons and so on heterogeneous robots have different component models which make it difficult and complicated to make distribution robot applications.

Second if standard component models which all robot platforms use in common are defined in spite of various practical reasons it is possible to solve the first problem. However there is a problem that such an approach does not still solve. In order to perform a robot application not only integration of components operating inside a robot but also integration with an external legacy system or various devices in a circumstance or others are inevitable. For example in order to provide news or weather information integration with a corresponding information system is necessary and in order to control a TV set or a gas valve integration with a home network is necessary. Consequently components outside robots still have different models.

An object of The present invention is to provide an apparatus and method for enabling heterogeneous robot platforms having different component models to collaborate through minimum standardized interfaces such that integration of robots or integration of robots and the external is possible.

An embodiment of the present invention provides a component integration apparatus for collaboration of a heterogeneous robot includes a standard interface unit that provides a common standard interface for controlling components that control the individual functions of the robot an adapter component that transmits commands to enable external components to call the components through the standard interface unit and a proxy component that transmits commands to enable the components to call the external components through the standard interface unit.

The common standard interface may be a general purpose remote procedure call model capable of controlling and integrating the components in a standardized method.

The adapter component may convert a command having a form of the standard interface into a command having a form of the component model.

The proxy component may convert the command having the form of the component model into the command having the form of the standard interface.

The adapter component may transmit commands to enable an external application to call the components through the standard interface unit.

When a command is input through the standard interface unit the adapter component may call a corresponding component among the components on the basis of the specifications.

Another embodiment of the present invention provides a component integration method for collaboration of a heterogeneous robot comprises receiving a command for controlling components that control the individual functions of the robot by a standard interface unit and determining the transmission path of the command by the standard interface unit when it is determined in the determining that the command has been transmitted from external components transmitting the command to call the components through the standard interface unit and when it is determined in the determining that the command has been transmitted from the components transmitting the command to call the external components through the standard interface unit.

According to the embodiments of the present invention heterogeneous robot platforms having different component models are enabled to cooperate through minimum standardized interfaces such that integration of robots or integration of a robot and the external is possible.

Further the embodiments of the present invention make it possible not only integration of robots but also integration with an external information system or various devices in a circumstance.

Hereinafter embodiments of the present invention will be described with reference to the accompanying drawings.

Referring to a system adapting a component integration apparatus for collaboration of a heterogeneous robot according to an exemplary embodiment of the present invention comprises a heterogeneous robot platform having different component models a robot platform server and external applications and .

Here the robot platform may adapt an OP ROS open platform for robotic services and so on but is not limited thereto. Here individual components of the system include standard interfaces and for integrating and controlling the components in a standardized method for control.

Further the standard interfaces are standard APIs application programming interfaces and provide language or message forms used for communication between heterogeneous robot platforms and external applications.

The standard interfaces are based on a general purpose RPC remote procedure call model for integrating and controlling heterogeneous robots having different components in a standardized method. In general robot platforms include functions for processing a number of component models having various functions. The remote procedure call provides a method capable of calling a function providing a connection to a specific component model for executing a component in a robot platform. Therefore the standard interfaces make heterogeneous robot platforms cooperate through a remote procedure call framework .

In embodiments of the present invention robot platforms include a number of sensors or actuators for individual functions. Further components for controlling the sensors or actuators for individual functions are formed. A common standard interface provides an interface configuration for integrating the above mentioned components.

Also the external application includes a device in a circumstance an external information device and legacy systems . This external application is integrated through the standard interfaces in the system.

That is since the standard interfaces are general purpose RPC models they may define standard interfaces not only for the components of the robot but also for the external application.

Referring to a component integration apparatus for collaboration of a heterogeneous robot according to an exemplary embodiment of the present invention comprises a standard interface unit an adapter component and a proxy component .

The standard interface unit provides a common standard interface for controlling components that control individual functions of the robot as described above. Here the standard interface may adapt the standard API application programming interface as described above. That is the standard interface unit provides language or message forms used for communication between the heterogeneous robot platforms and the external application through a standard interface.

Here the components are functional units for controlling the individual functions of the robot. That is the components control corresponding functions of the robot according to control commands input output through the standard interface unit . In this case the components include specifications for control based on the individual component models. That is the specifications define calls of functions of robots corresponding to the individual components. For example in a case of a component for controlling a camera of a robot a corresponding component specification includes control commands for performing control of power supply to the camera left and right rotations of the camera etc.

Also as described above the standard interface unit is based on the general purpose RPC remote procedure call model for integrating and controlling a heterogeneous robot having different components in a standardized method. For example in a case of a component for controlling wheels of a robot a specification for controlling the corresponding component is implemented in a function form. Therefore functions defined in the specification are implemented to be able to call control commands for performing control of power supply to the wheels of the robot clockwise and counterclockwise rotations of the wheels of the robot left and right rotations of the wheels of the robot etc.

The adapter component transmits commands such that external components for example components of a server or external applications etc can call internal components through the standard interface unit . In order to enable access to the components inside the robot platform through the standard interface unit the adapter component is in accordance to a component model of the corresponding component.

For example referring to when an internal component for controlling a camera of a robot is a component and an external component is a control component of a server the external component issues a series of commands for driving the camera to acquire images and receiving the images through the standard interface. Then the commands issued from the external component are transmitted to an adapter component through a standard interface unit of the robot having the camera as a component. Next the adapter component transmits the received commands to the internal component to drive the camera according to the corresponding commands.

Also the external components have component models different from the internal components . That is since the external components and the internal components cannot cooperate in a direct method they cooperate through the above mentioned standard interface unit .

The proxy component transmits commands such that components can call the external components through the standard interface unit . The proxy component enables components operating inside the robot to be integrated with external applications or external components on the basis of unique component models of the robot.

For example referring to it is assumed that an internal component for controlling wheels of the robot is a component and an external component is a control component of a server. First the internal component issues a drive state of the wheels as a command. Then the proxy component converts the corresponding command into the command appropriate for the standard interface and transmits it to the standard interface unit . Next the standard interface unit transmits the corresponding command to the external component . Then the external component may determine the state of the remote wheels without requiring a separate process.

Also the adapter component may convert a command having a form of a standard interface into a form of a component model. That is when the external component calls the internal component through the standard interface unit the adapter component converts the corresponding command into an internal component model form and transmit it to the internal component . For example when the internal component shown in is the component for controlling the wheels of the robot and the external component is the control component of the server the external component issues a series of commands for driving the wheels of the robot or controlling the drive speed through the standard interface. Then the commands issued from the external component are transmitted to the adapter component through a standard interface unit of the robot having the wheels as components. Next the adapter component converts the received commands appropriately for the component model of the internal component and transmits them to the internal component . Then the internal component drives the wheels according to the corresponding commands without a separate process.

Further the adapter component may transmit a command to enable the external applications to call the components through the standard interface unit . That is as described above the external applications include a device in a circumstance an external information device and legacy systems. Therefore the external applications transmit their information through the standard interface. Then the adapter component receives the information of the external applications through the standard interface unit and provides the information to corresponding components. For example it is assumed that the internal component shown in is the component for controlling the camera of the robot and the specification of the internal component has a command to turn on the camera when brightness is equal to or greater than a reference value. When the external application is a brightness sensor the external application issues a current brightness information through the standard interface. Then the adapter component receives the current brightness information through the standard interface unit and provides the current brightness information to the internal component . When the corresponding brightness information is equal to or greater than the reference value the internal component turns on the corresponding camera.

Also the proxy component may convert a command having a component model form into a command having a standard interface form. This has an inverse order to the process of the adapter component described above and thus a detailed description thereof is omitted.

Referring to a component integration method for collaboration of a heterogeneous robot according to an embodiment of the present invention comprises receiving commands for controlling components that control the individual functions of the robot S determining the transmission path of the commands S transmitting the commands to call internal components through a standard interface unit if it is determined in S that the commands have been transmitted from external components S and S and transmitting the commands to call the external components through the standard interface unit if it is determined in S that the commands have been transmitted from the internal components S and S .

The component integration method for collaboration of a heterogeneous robot described above will be described in regards to examples according to the transmission path.

First a case in which it is determined in S of that a command has been transmitted from an external component will be described. Here it is assumed that an internal component is the component for controlling the camera of the robot and an external component is the control component of the server see .

Next the external component issues a series of commands for driving the camera to acquire images and receiving the images through the standard interface. Then the standard interface unit receives the commands issued from the external component and calls the adapter component connected to the camera component. Then the adapter component transmits the received commands to the internal component to drive the camera according to the corresponding commands.

Meanwhile a case in which it is determined in S of that a command has been transmitted from an external component will be described. Here it is assumed that an internal component is the component for controlling the wheels of the robot and an external component is the control component of the server. First the internal component issues the drive state of the wheels or others as a component. Then the proxy component converts the corresponding command appropriately for the standard interface and transmits the command to the standard interface unit . Next the standard interface unit transmits the corresponding command to the external component . That is the external component receives the state of the remote wheels through the standard interface without a separate process see .

As such according to the exemplary embodiments of the present invention heterogeneous robot platforms having different component models are enabled to cooperate through minimum standardized interfaces such that integration of robots or integration of a robot and the external is possible.

Further the exemplary embodiments of the present invention make it possible not only integration of robots but also integration with various devices in a circumstance or an external information system.

While this invention has been described in connection with what is presently considered to be practical exemplary embodiments it is to be understood that the invention is not limited to the disclosed embodiments but on the contrary is intended to cover various modifications and equivalent arrangements included within the spirit and scope of the appended claims. Accordingly the actual technical protection scope of the present invention must be determined by the spirit of the appended claims.

