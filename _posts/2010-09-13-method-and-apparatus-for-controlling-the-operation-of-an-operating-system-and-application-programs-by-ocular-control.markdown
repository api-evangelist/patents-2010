---

title: Method and apparatus for controlling the operation of an operating system and application programs by ocular control
abstract: The method and apparatus object of this invention refer to a system for using generic software applications by means of ocular control characterized by simple interaction techniques which minimize the cognitive effort of the user required to manipulate the software and which permit to overcome the problems resulting from the intrinsic problem of accuracy of eye-tracking systems. Indeed, such technique does not provide using the pointer of the mouse moved by means of the gaze to control the various software applications but to use a separate application which through the use of suitable interaction techniques is comfortable and does not involve an increased effort of concentration by the user. An attempt has indeed been made to simplify the process of interaction between the user and machine also by means of the use of visual feedback which allows the same operations of the mouse to be performed by the user without the typical user frustration due to the problems of accuracy of the eye-tracking device.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09372605&OS=09372605&RS=09372605
owner: SR LABS S.R.L.
number: 09372605
owner_city: Brescia
owner_country: IT
publication_date: 20100913
---
This application claims benefit under 35 U.S.C. 371 to international application No. PCT IB2010 002271 filed on Sep 13 2010 which claims priority to Italian application no. FI2009A000198 filed Sep. 11 2009 the contents of which are incorporated by reference in their entirety.

The present invention refers to the field of systems and methods for the control of generic software applications by means of eye tracking devices i.e. by using ocular movements.

Not having the opportunity to use the mouse for access to the software applications the user should take advantage of the techniques which permit him her to carry out by means of ocular movements the same operations which are possible to carry out with the mouse. To this end techniques and contrivances have been developed which permit the user to significantly decrease the cognitive effort to be performed.

The tracking of the ocular movements potentially offers the user the possibility of controlling the software of a personal computer by simply looking at the display thereof.

However there are problems which frustrate the user during the use of the tracking systems of ocular movements or eye tracking systems for controlling the software of a personal computer. In particular the eyes should simultaneously behave as input and output devices i.e. they should explore and carry out true actions. Again the eye tracking devices suffer intrinsic problems of accuracy in measuring the position of the gaze on the screen. Therefore the accuracy of the sensor is always affected by an error the difference between the current position of the cursor on the display compared with the position of the cursor wanted by the user and this does not make controlling most of the software applications easy given that many software programs require an accuracy of some millimeters and others also require an accuracy assessable in terms of pixels.

Thus the use of eye tracking systems is generally limited to software made specifically for disabled users in which a low pointing precision is required. Indeed the user should make his her selection from a list of relatively large cells in which the effect of the error of accuracy is small.

Instead in the field of software applications of common use the employment of eye tracking systems for controlling the application e.g. by means of the movement of the cursor which is updated many times per second by following the direction of the gaze the error of accuracy makes the user s task very difficult to whom a significant effort of concentration is required which very soon generates fatigue.

Any attempt by the user to correct the error by re directing his her gaze towards the position where the cursor should be positioned does nothing more than making the use of the cursor increasingly problematic and tiring.

Some solutions in use in the state of the art provide resolving the aforesaid problem by means of enlarging a part of the display of the personal computer so as to improve the accuracy in the positioning of the cursor.

However this approach is insufficient because the error of compensation also remains in these cases thus continuing to frustrate the user and moreover implies an increased complexity of the interface which may create confusion and distraction.

Other solutions currently available imply the appearance of off screen menus which permit the user to select which action to carry out by emulating the different operations which may be carried out with the mouse single click double click right click drag and drop .

Again in some cases the functions wanted may be activated by pointing the gaze on icons arranged on strips of thin plastic coated cardboard which are positioned on the vertical perimeter of the monitor thereby the eye should select the functions external thereto before activating them on the icon or on the function wanted and then move the cursor which will be steered by the gaze towards the icons or applications wanted.

In further other cases it is also possible to steer a second PC connected with the eye tracking system whose monitor should be installed beside the monitor of the eye tracker to give the user the opportunity to easily observe the control of the mouse over the applications.

The directions of the mouse pointer are activated with the gaze on the screen view on the monitor of the eye tracking device and once the direction is selected the effect is observed on the other PC as soon as the gaze is removed from the PC wanted to be controlled the pointer stops and the commands wanted may be selected. Thereby the second PC connected may be steered with the eye tracking system by means of the emulation of the mouse.

In principle we may assert that contrarily to what has been implemented to date it would be desirable to have a display on which the elements depicted do not interfere too much with the normal use of the software for the following reasons the attention of the user declines exponentially with the increasing number of elements depicted on the screen the user normally has little familiarity with the eye tracking devices and moreover may be affected by cognitive disabilities such as to make the use of an eye tracking device prohibitive.

For the aforesaid reasons it is the object of the present invention to provide a method for controlling a personal computer by means of an eye tracking system which overcomes the drawbacks listed above.

One of the main requirements remains that of minimizing the cognitive effort required to manipulate the software by ensuring that the interface accepts natural inputs and responds naturally and is easily comprehensible.

For this reason it will be necessary to develop an interface which uses interaction techniques which are not stressful for the user. Given that many of the inputs are unintentional the system should interpret them correctly without producing unrequested responses caused by involuntary actions. Such system therefore should be capable of distinguishing between the true will of the user while letting him her observe the interface peacefully if it is not his her intention to give a command on the other hand the user should be capable of assessing what the current status of the system is so as to realize if his her intentions were interpreted properly to avoid the execution of involuntary commands.

It should also be underlined that while the systems of the state of the art control operating systems by means of the emulation of the mouse via ocular control conversion of the movement of the gaze into movement of the cursor the object of the present invention provides a new mapping of the original native interactors of the operating system of the personal computer icons etc. in new interactors modified and made suitable to the selection mode by means of ocular control.

Therefore the present invention establishes a sort of direct channel as the emulation of the cursor is overcome by the fact that the native interactors are replaced by those modified and adapted to the need to use the gaze as input system.

Also the use of a Virtual Machine which permits to manage and create a virtual environment to carry out a further operating system with related software applications and which the user may use simultaneously to the one started provides further advantages. One of them is security a virtual machine is completely isolated and independent and a sudden crash of the virtual machine does not involve the hosting operating system to crash therefore restarting the computer is not required but only terminating the virtual machine and starting it again while avoiding damaging e.g. the file system.

As the method according to the present invention is integrated in a communication suite by using the virtual machine it is possible to simply quickly and safely move by means of suspension of the virtual machine from using the classic PC applications by means of the control techniques described below to the communication suite designed specifically for being used via ocular control thus overcoming the problems of the systems in the state of the art which provide rather complicated procedures for moving from one mode to the other.

At the same time the user may directly choose by means of suitable shortcuts to carry out some predefined applications inside the communication suite thus overcoming the problem of the possible direct execution from the operating system.

The object of the present invention consists of a method and an apparatus for using a generic operating system and generic software applications connected thereto by means of ocular control. A further object of the present invention consists of suitable methods of interaction developed by means of interaction techniques and an intuitive and easy to use user interface as described in the claims which form an integral part of the present description.

The method object of the present invention therefore depicts a possible implementation of an assistive technology extremely innovative in terms of control of a generic operating system and of the applications connected thereto based on the use of alternative and natural inputs such as the gaze.

In a preferred embodiment of the present invention the apparatus object of the present invention comprises electronic means of data and of information processing means for memorizing said data and information and user interfacing means.

Said electronic data and information processing means comprise a suitable control section preferably based on at least a micro processor and may e.g. be provided by a personal computer.

Said memorizing means preferably comprise hard disks and storage devices of flash type. Said user interfacing means preferably comprise data visualising means such as e.g. displays monitors or analogous external output units and eye tracking devices adapted to interpret the direction of the user s gaze.

Said micro processor is preferably equipped with an operating system with a suitable virtual environment by means of the use of a virtual machine and by a suitable software program which implements a method whose architecture described in comprises the following modules in turn comprising a series of instructions adapted to performing a specific task a filtering module in which the coordinates of the user s gaze are processed so as to make the rough data coming from the used eye tracking device more stable a module namely an Operating System Applications Control responsible for controlling the operating system and the applications associated therewith and for running the developing application graphic interfaces interface which contains the information about the interactors in the screen view and carries out the native action associated with the interactor fixed by the user at that moment said interactors being the activatable elements in the interface the icons the pop down menus the check boxes etc. adapted to make the user carry out actions on the applications program to be controlled.

Said Operating System Applications Control Module is formed by two component sub modules a Controller Module and a Client Module .

Said Controller Module is in charge of managing the presentation of the interactors and of defining the native action associated with each of them and in turn comprises three further modules which interact with each other 

a Coordinate Mapping Module A which is in charge of carrying out new mapping of the coordinates relating to the screen views and to the interactors therein different between Client and Controller 

an Interactor Managing Module B which is in charge of carrying out the comparison with the incoming gaze to define which interactors are fixed by the user and presents them suitably and possibly modified on the interface e.g. on a side panel 

a Native Action Definition Module C which is in charge of defining the native action associated with each interactor of the Operating System and of sending it to said Client Module thus making it available for successive processing.

Said Coordinate Mapping Module A in turn consists of two sub modules which interact with each other a Coordinates Translation Sub Module which carries out a translation of the coordinates relating to screen views and interactors and an Adaptive Calibration Sub Module which carries out a further re adjustment of the coordinates by means of geometrical deformation of the plane obtained by comparing the information on the interactors which the user may select and the coordinates of the gaze coming from the eye tracker the results of the combined actions of these 2 modules is the one described above concerning the Coordinates Mapping Module A.

Said Client Module is adapted to defining the position and the function of the interactors in the screen view and in turn comprises two further modules which interact with each other the Interface Managing Module A which is in charge of analysing the screen views and sending the information relating thereto and to the present interactors detected by means of different search methods to the Controller Module the Native Action Managing Module B which is in charge of receiving the information relating to the associated native action and of carrying it out as action on said operating system.

In reference to there is shown a diagram which depicts the operation of the modules mentioned above and the interconnections with each other by illustrating the steps of the method according to the present invention 

The filtering procedure of rough data according to step c is carried out according to the sequence indicated below and illustrated in 

The filtered data sent to the Operating System Applications Control Module are processed according to the sequence indicated below and illustrated in 

The process of mapping the coordinates again according to step m of the sequence illustrated in occurs according to the sequence indicated below and illustrated in 

The Interface Managing Module carries out the search of the interactors in the view screens continuously during the entire process described above by means of the use of the steps described below and illustrated in 

The method described allows e.g. a disabled user to use a personal computer equipped e.g. with an operating system and with application programs such as Windows and the Microsoft Office package.

The user is arranged in front of the eye tracker connected to a monitor in which is visualised the screen view of the operating system application wanted to be controlled by means of ocular movements.

The user fixes e.g. the Start icon on the Windows application bar close to which is the icon for the Word application and the Windows bar the gaze moves in specific surroundings for the intrinsic features of the eye tracker. Due to this and to the possible and intrinsic error of accuracy of the eye tracking device what the user is fixing on and what his her intention is may not be said with certainty. To obviate this problem all the interactors in the surrounding of the gaze e.g. Start button Word program icon Windows bar are shown in a side panel suitably for selection by means of ocular control well spaced and of suitable sizes . Such interactors are detected by means of suitable data recovery strategies type position etc. relating to the interactors in the screen view accessibility API query recursive crossing of windows diagram database of predefined applications and are shown in a weighted manner according to the order obtained by means of heuristic techniques from the most probable to the least probable .

The user fixes the interactor of interest on the side panel and as the buttons are well spaced and of suitable sizes there is no ambiguity with respect to the user s choice. The button is therefore selected and the consequent action is carried out. In greater detail and in reference to accompanying the user firstly arranges him herself in front of the eye tracker connected to a monitor in which is visualised the screen view of the operation system application wanted to be controlled by means of ocular movements .

The user fixes e.g. the Start icon on the Windows application bar close to which is the icon for the Word application and the Windows bar the gaze moves in specific surroundings for the intrinsic features of the eye tracker. Due to this and to the possible and intrinsic error of accuracy of the eye tracking device what the user is fixing on and what his her intention is may not be said with certainty .

All the interactors in the surrounding of the gaze e.g. Start button Word icon Windows bar are shown in a side panel suitably for selection by means of ocular control well spaced and of suitable sizes . Such interactors are detected by means of suitable data recovery strategies type position etc. relating to the interactors in the screen view accessibility API query recursive crossing of windows diagram database of predefined applications and are shown in a weighted manner according to the order obtained by means of heuristic techniques from the most probable to the least probable .

The user fixes the interactor of interest on the side panel as the buttons are well spaced and of suitable sizes there is no ambiguity with respect to the choice of the user . The button is selected and the consequent action is carried out.

After the selection of the Start button from the interactors panel the action is consequently carried out or the window is opened relating to the request. The interactors panel is emptied while waiting to be filled again with new interactors following the successive gazes of the user.

