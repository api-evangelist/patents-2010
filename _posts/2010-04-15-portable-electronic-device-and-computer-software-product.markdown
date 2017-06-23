---

title: Portable electronic device and computer software product
abstract: The invention relates to a portable electronic device and computer software product. The portable electronic device comprises a motion detector for generating motion data characterizing the local movement of the portable electronic device, a motion intensity determiner for determining a instantaneous motion intensity value of the user of the portable electronic device from the motion data, and an active time counter for determining an active time accumulation that sums up the time periods, during which the instantaneous motion intensity value meets predefined activity criteria.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08169326&OS=08169326&RS=08169326
owner: Polar Electro Oy
number: 08169326
owner_city: Kemple
owner_country: FI
publication_date: 20100415
---
This application is a continuation of pending U.S. patent application Ser. No. 11 789 024 filed on Apr. 23 2007 which claims priority to Finnish Patent Application Serial No. 20065259 filed on Apr. 24 2006 which are incorporated herein by reference.

The invention relates to a portable electronic device and a computer software product. The portable electronic device and computer software product implement a process for determining the intensity of a performance.

Recommendations provided by international organizations and professionals exist on the suitable amount of daily exercise for boosting health. Examples of such organizations are AGSM American College of Sports Medicine and CDC Centers for Disease Control .

When doing normal daily routines or an irregular and long term performance such as a physical exercise it is however difficult for an ordinary person to estimate the intensity and duration of the performance and whether the recommended amount of exercise is reached. The performance may be interrupted for indefinable time periods or the intensity of the performance may decrease such that the person finds it difficult to estimate whether the criteria set for the performance are met.

It is an object of the invention to provide a portable electronic device and a computer software product in such a manner that the intensity of a performance may be estimated through measuring. A first aspect of the invention presents a portable electronic device that comprises a motion detector for generating motion data characterizing the local movement of the portable electronic device a motion intensity determiner configured to determine a instantaneous motion intensity value for the user of the portable electronic device from the motion data and an active time counter configured to determine an active time accumulation that sums up the time periods during which the instantaneous motion intensity value meets predefined activity criteria.

A second aspect of the invention presents a computer software product that comprises encoded instructions for executing in a digital processor a computer process that is suitable for determining the intensity of a performance and comprises the following process steps inputting motion data characterizing the local movement of a portable electronic device determining a instantaneous motion intensity value of the user of the portable electronic device from the motion data and determining an active time accumulation that sums up the time periods during which the instantaneous motion intensity value meets predefined activity criteria.

The invention is based on determining an active time accumulation from instantaneous motion intensity data and the active time accumulation sums up the time periods during which the instantaneous motion intensity value meets predefined activity criteria.

The method and system of the invention provide several advantages. One advantage is that the invention provides an objective estimate on the time accumulation of the activity of the user.

With reference to the example of the portable electronic device PED comprises a central processing unit CPU and memory unit MEM . The central processing unit comprises a digital processor and executes a computer process according to encoded instructions stored in the memory unit the process being suitable for determining the intensity of a performance.

The portable electronic device is a mobile phone or pedometer for instance. In one embodiment the portable electronic device is a wrist device that may for instance be the wrist device of a performance monitor shown in . A performance monitor may comprise not only the wrist device but also one or more auxiliary devices such as a motion sensor fastened to a limb of the user of the portable electronic device and or a pulse transmitter indicating electric pulses induced by the heart. The auxiliary device may communicate over wire or wirelessly with the wrist device . In this context the user of the portable electronic device is referred to as the user .

In one embodiment the portable electronic device comprises a wrist device and at least one auxiliary device .

With reference to the portable electronic device also comprises a motion detector MD that generates motion data characterizing the local movement of the portable electronic device.

The local movement of the portable electronic device is typically the movement of a limb or other body part of the user with a motion component related to the step of the user included therein. The amplitude of the local movement is typically in the range of the amplitude of the movement of the user s limbs.

In one embodiment the motion detector comprises an acceleration sensor that measures the acceleration related to the movement of the user . The acceleration sensor transforms the acceleration caused by a movement or gravity into an electric signal.

In one embodiment the acceleration sensor is based on piezo resistor technology that uses a material whose resistance changes as the piezo resistor compresses as a result of the acceleration of the mass. When directing a constant current through the piezo resistor the voltage over the piezo resistor changes according to the compression caused by the acceleration.

In one embodiment the acceleration sensor is based on piezoelectric technology in which a piezoelectric sensor generates a charge when the acceleration sensor is accelerated. In silicon bridge technology a silicon chip is etched in such a manner that a silicon mass remains on the silicon chip at the end of a silicon beam. When acceleration is directed to the silicon chip the silicon mass directs the force to the silicon beam whereby the resistance of the silicon beam changes.

The acceleration sensor may also be based on micromachined silicon technology that is based on the use of a differential capacitor. In addition the acceleration sensor may be based on voice coil technology that is based on the same principle as a microphone. Examples of suitable motion detectors include Analog Devices ADXL105 Pewatron HW and VTI Technologies SCA series.

The motion data generated by the acceleration sensor may be brought to the central processing unit or memory unit . The motion data may for instance comprise acceleration data and or motion pulse data related to the movements of the user .

The motion detector may also be based on other technologies suitable for the purpose such as a gyroscope integrated on a silicon chip or a micro vibration switch placed in a surface mounting component.

The motion detector may comprise a pre processing unit for processing primary motion data such as acceleration data and or vibration data. The processing may comprise transforming primary motion data into secondary motion data for instance transforming acceleration data related to a user generated movement into motion pulse data. The processing may also comprise filtering primary and or secondary motion data.

The portable electronic device may also comprise a user interface UI that typically contains a display unit DISP and display adapter. The display unit may contain LCD Liquid Crystal Display components for instance. The display unit may display graphically and or numerically the instantaneous motion intensity or active time accumulation for instance to the user .

The user interface may also contain a keypad KP with which the user may input commands into the performance monitor .

With reference to the example of let us examine a motion intensity curve that shows the time dependence of the instantaneous motion intensity value of the user . The horizontal axis shows time using a time unit such as minute and the vertical axis shows the motion intensity value using a motion intensity unit such as pulse minute p min .

The motion intensity value characterizes the quantity of the user s movement in a time unit. In one embodiment the motion intensity value characterizes the number of motion pulses per minute or per some other suitable time unit.

An instantaneous motion intensity value is a motion intensity value calculated for a time instant. A instantaneous motion intensity value at a time instant may be determined for instance by calculating the motion pulses accumulated during a measuring period such as minute and dividing the number of motion pulses by the measuring period. The time instant associated with a determined instantaneous motion intensity value may for instance be the start time or end time of the measuring period or a time instant in the middle of the measuring period.

An active time accumulation is an accumulating time accumulation that contains summed up time periods during which the instantaneous motion intensity value meets predefined activity criteria. A predefined activity criterion is for instance a predefined motion intensity level that defines the low limit of the instantaneous motion intensity value. An active time accumulation is a quantity that when presented to the user helps the user to estimate the intensity of the performance.

In the example of the predefined activity criterion is for instance motion intensity level marked with a dotted line in which case the time periods meeting the activity criteria are T T T T T and T.

In one embodiment the active time accumulation is calculated for a specified time period that in the example of the figure may be the period between the start time and end time . The active time accumulation during the specified time period is then T T T T T T when the predefined activity criterion is motion intensity level . The time periods may be implemented in such a manner that the periods overlap each other. For instance let us examine 60 second time periods at 10 second intervals. Instantaneous motion intensity values are then added to the 60 second time period at 10 second time intervals for the most recent 10 seconds and at the same time the motion intensity values for the oldest 10 seconds are deleted. This arrangement provides advantages for instance when a person has a 60 second active period that does not occur on the minute.

The start time may be the turn of the day or a time instant 24 hours before the current time. The end time may be the turn of the day without limiting the present solution to the present embodiment.

When active time determination is being done the end time may be the current time instant. The active time accumulation then indicates the active time accumulation from the start time to the current time instant.

In one embodiment the portable electronic device determines an inactive time accumulation that contains the summed up time periods during which the instantaneous motion intensity value meets predefined inactivity criteria. A predefined inactivity criterion is for instance a predefined motion intensity level that defines the high limit of the instantaneous motion intensity value.

In the example of the predefined inactivity criterion is for instance motion intensity level that is marked with a dotted line in which case the time periods meeting the inactivity criteria are T T T T T T and T. The inactivity time accumulation for the time period between the start time and end time is thus T T T T T T T.

In one embodiment the portable electronic device distributes the instantaneous motion intensity values into at least two intensity classes on the basis of predefined intensity class limits and the active time accumulation is determined by intensity class. The example of shows intensity classes A B and C. Intensity class C comprises the motion intensity values that are between motion intensity levels and intensity class B comprises the motion intensity values that are between motion intensity levels and and intensity class A comprises the motion intensity values that are above motion intensity level .

Intensity class D comprises motion intensity values that are below motion intensity level and it may also be defined as an inactivity class.

Motion intensity levels and may be 2 p min 30 p min and 50 p min respectively. Intensity class D may then be defined as an idle intensity class C as an extremely light intensity class B as a light and intensity class A as a moderate to high intensity class.

Activities that require that the user move belong to intensity classes A and B. They are suitable for providing performance instructions. Intensity class A may be applied to general exercises that require at least 30 minutes of moderate to high intensity class exercise daily several days a week. Intensity classes C and D may also be referred to as inactivity classes.

In an embodiment of the invention an intensity class is set according to a predefined physiological benefit effect that is obtained by the user s activity exceeding the predefined activity criterion.

In an embodiment of the invention the predefined physiological benefit effect is a health benefit that sets an activity level at which the user is expected to perform an activity in order to maintain or increase the current health. In this case the activity criterion may be equivalent to 30 to 65 percent of the maximum oxygen uptake VO during an exercise. The maximum oxygen uptake may also be referred to as the maximum aerobic fitness level.

The health benefit may typically be obtained with continuous low intensity motion such as walking cleaning or gardening.

In an embodiment of the invention the predefined physiological benefit effect is a fitness benefit that sets an activity level at which the user is expected to perform an activity in order to maintain or increase the current fitness level. In this case the activity criterion may be equivalent to more than 65 percent of the maximum oxygen uptake VO during an exercise.

The fitness benefit may typically be obtained with continuous intermediate or high intensity training such as brisk walking and jogging.

In an embodiment of the invention the predefined activity criterion is calculated from user parameters such as age gender weight length and or user specific health indicators. A user specific health indicator may indicate blood pressure level or a disease such as diabetes. The user parameters may be input into the portable electronic device through the user interface . The central processing unit may include encoded instructions for calculating the predefined activity criterion from the user parameters.

In an embodiment of the invention the user parameters include heart rate variables obtained from heart rate measurement carried out by the pulse transmitter . The predefined activity criterion may then be proportional to a heart rate variable such as resting heart rate of heart rate variation. The central processing unit may include encoded instructions for calculating the predefined activity criterion from the heart rate variables.

In an embodiment of the invention the active time counter starts determining the active time accumulation after a time threshold that is proportional to a user parameter. A user having a high performance expectation indicated by the user parameters may have a longer time threshold than a person having a lower performance expectation. The time threshold defines a time of continuous activity which should precede the actual active time accumulation determination.

With reference to the example of let us examine a portable electronic device PED that comprises a motion detector MD motion intensity determiner MID and an active time counter ATC .

The motion detector generates motion data characterizing the local movement of the portable electronic device and inputs it into the motion intensity determiner .

The motion intensity determiner determines instantaneous motion intensity values from the motion data .

In one embodiment the motion intensity determiner filters motion data on the basis of predefined time properties. The motion intensity determiner may accept motion pulses meeting predefined criteria and use the accepted motion pulses to determine the motion intensity values.

In one embodiment the motion intensity determiner determines a motion intensity value from motion pulses the interval between which is within predefined limits. The determination of the motion intensity values is then focused on motion frequencies that are typical of the human body and typically 1 to 2 pulses per second. The filtration may be implemented by rejecting consecutive motion pulses whose time interval is below a predefined low limit or above a predefined high limit.

The predefined high and low limits may depend on the location of the motion detector on the user s body. In the case of attachment to an upper limb the predefined low limit may be 0.4 seconds for example. The predefined high limit may be 2.0 seconds for example.

The motion intensity determiner may be implemented by a computer process execute in the central processing unit the computer process being encoded into encoded instructions stored in the memory unit .

In one embodiment the motion intensity determiner inputs instantaneous motion intensity values into the active time counter . The motion intensity determiner may also input into the active time counter the time instant associated with each instantaneous motion intensity value. The active time counter compares the motion intensity values with a predefined motion intensity level and calculates the active time accumulation and possibly also inactive time accumulation on the basis of the comparison. The inactive time accumulation information may be included in the active time accumulation information .

In one embodiment the portable electronic device comprises a classifier CL that receives the motion intensity values from the motion intensity determiner and performs comparison between the motion intensity values and motion intensity levels . Using the comparison the classifier divides the instantaneous motion intensity values into intensity classes.

The classifier inputs the classified motion intensity values into the active time counter that calculates class specific active time accumulations.

The active time counter may be implemented by a computer process execute in the central processing unit the computer process being encoded into encoded instructions stored in the memory unit .

The classifier may be implemented by a computer process execute in the central processing unit the computer process being encoded into encoded instructions stored in the memory unit .

In one embodiment the portable electronic device comprises an active time indicator ATI for indicating the active time accumulation time instant preceding the time period between the start time and end time to the user. The active time accumulations of earlier such as day specific time periods may be stored into the memory unit and shown graphically or numerically by means of the display unit to the user . The user may then follow the performance history and for instance compare the active time accumulation of the ongoing time period with the earlier values.

In one embodiment the portable electronic device comprises an intensity indicator II for indicating the latest time instant of the motion intensity value meeting the activity criteria to the user . With reference to let us assume that the current time instant is instant and the activity criterion is determined from motion intensity level . The latest time instant of the motion intensity value meeting the activity criteria with respect to time instant is time instant . The central processing unit may input for storage into the memory unit the latest time instant of the motion intensity value meeting the activity criteria. The display unit may point the memory space of the memory unit in such a manner that the contents of the memory are displayed in the display unit . By detecting the latest time instant of the motion intensity value meeting the activity criteria the user may determine the duration of the ongoing inactive time for instance. The display unit may for instance display the text inactive since T1 T2 wherein T1 T2 is the time instant when the activity criteria was last met.

With further reference to in one embodiment the portable electronic device comprises a performance instruction generator PIG for generating a performance instruction on the basis of the active time accumulation.

The active time counter inputs the active time accumulation data into the performance instruction generator that may compare the active time accumulation with reference values. The reference values may form ranges of variation that are associated with the performance instructions. The performance instruction may contain the following instructions REST LIGHT EXERCISE and MODERATE TO HIGH EXERCISE. For instance if the accumulation of the present day or the previous 24 hours in intensity classes A and B is less than 30 minutes the user may be instructed to do light or moderate to heavy exercise. If the accumulation of intensity class A is less than 30 minutes for the previous three days or the previous 72 hours the performance instruction given may be moderate to high exercise.

In one embodiment the intensity classification may be defined by exercise type. In addition to the above mentioned intensity classes an E intensity class may be used which defines the limits between walk and run.

The performance instruction may also be determined by several day specific activity time accumulations.

The performance instruction generator may be implemented by means of a computer process execute in the central processing unit the computer process being encoded into encoded instruction stored in the memory unit .

In one embodiment the portable electronic device comprises at least one game application GAPPL whose operation depends on at least one parameter proportional to the active time accumulation. A parameter proportional to the active time accumulation may be a control parameter that adjusts the operating time of the game application . A high active time accumulation then may enable a longer use of the game application than a low active time accumulation would.

In one embodiment the game application comprises an electronic figure such as a pet whose condition is dependent on the control parameter. With a high active time accumulation the electronic figure may indicate satisfaction. With a low active time accumulation the electronic figure may indicate dissatisfaction or switch to inactive.

The game application may be implemented by a computer process execute in the central processing unit the computer process being encoded into encoded instructions stored in the memory unit . In addition the game application may be connected to the user interface with which the user may use the game application .

In one embodiment the portable electronic device comprises a motion detector controller connected to a motion detector and an active time counter . The motion detector controller receives inactive time accumulation information with active time accumulation information and compares the inactive time accumulation with a predefined threshold value. If the inactive time accumulation exceeds the predefined threshold value the motion detector controller switches with a mode change command the motion detector into a measuring mode in which motion data is generated discontinuously at predefined time intervals.

The predefined threshold value is for instance 15 minutes whereby after a 15 minute inactive time accumulation the motion detector is switched to a discontinuous measuring mode. In the discontinuous measuring mode the motion detector may be switched on at 5 minute intervals for 30 seconds for instance. If the motion detector detects activity the motion detector controller may switch the motion detector into a continuous measuring mode. If the motion detector does not detect activity the discontinuous measuring mode may be continued. The above 15 minute 5 minute and 30 second time values are examples and the present solution is not restricted to them.

With reference to the portable electronic device may in one embodiment comprise a communication unit COM that connects the portable electronic device to an application platform AP . The application platform comprises an application platform communication unit COM that receives active time accumulation information from the communication unit . The application platform communication unit transmits the active time accumulation information to an application platform game application . The application platform game application may be controlled and or monitored through a user interface . The operation of the game application depends on at least one parameter proportional to the active time accumulation.

The communication unit and application platform communication unit may be connected to each other wirelessly or over wire.

The application platform may be a PC personal computer portable computer laptop PDA personal digital assistant fixed or portable game console mobile phone or any other electronic device that comprises sufficient processing and memory capacity for executing the game application and a user interface for using the game application .

Controlling the game application with a parameter proportional to the active time accumulation makes it possible to motivate children and young people to exercise. It is known that game applications have an addictive effect on children and young people and a passivating effect on the sports activities of children and young people. The active time accumulation may directly affect the operating time of the game application points distributed in the game application performance of the electronic figure quantity of commodities used in the game application such as virtual money power and or number of virtual weapons or other features pursued in the game application . The user of the game application then benefits from high active time accumulation in the use of the game application and is motivated to exercise so as to achieve an as high active time accumulation as possible.

With reference to and let us examine the computer processes of some embodiments shown by means of process steps. The process steps may also be interpreted as the method steps of the method.

In step a instantaneous motion intensity value of the user of the portable electronic device is determined from the motion data.

In step an active time accumulation is determined which contains summed up time periods during which the instantaneous motion intensity value meets predefined activity criteria.

In one embodiment in step an inactive time accumulation is determined which contains summed up time periods during which the instantaneous motion intensity value meets predefined inactivity criteria.

In one embodiment in step a performance instruction is generated on the basis of the active time accumulation.

In step instantaneous motion intensity values are divided into at least two intensity classes based on predefined intensity class limits.

In step the time instant of the active time accumulation preceding the ongoing time period is communicated to the user.

In step the latest time instant of the motion intensity value meeting the activity criteria is communicated to the user.

In step an inactive time accumulation is determined which contains summed up time periods during which the instantaneous motion intensity value meets predefined inactivity criteria.

If the threshold value is exceeded in step a measuring mode is started which generates motion data discontinuously at predefined time intervals.

The computer process shown in and may be included into a computer software product as encoded instructions that may be execute in the central processing unit of the portable electronic device . The encoded instructions may be stored in the memory unit of the portable electronic device .

In one embodiment the computer software product comprises encoded instructions for executing a game application . The game application may be executed in the central processing unit of the portable electronic device and or the central processing unit of the application platform .

The encoded instructions may be transferred by means of a distribution medium. The distribution medium is an electronic magnetic or optic distribution medium for instance. The distribution medium may be a physical distribution medium such as a memory unit or optic disk or a telecommunications signal.

Even though the invention is described above with reference to the example according to the drawings it is clear that the invention is not limited thereto but may be modified in many ways within the scope of the attached claims.

