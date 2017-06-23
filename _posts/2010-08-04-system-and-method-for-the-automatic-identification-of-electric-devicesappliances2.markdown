---

title: System and method for the automatic identification of electric devices/appliances
abstract: A system for automatic identification of a device or appliance includes: at least one sensor associatable with the device or appliance to be identified, and able to monitor an evolution in time of an electrical quantity indicative of device or appliance energy consumption; an analyzer communicating with the at least one sensor including receiving reports of the monitored electrical quantity, and automatically identifying the device or appliance by analyzing the evolution in time of the monitored electric quantity. The analyzing calculates a cross-correlation between the evolution in time of the monitored electric quantity and at least one reference pattern representative of at least one sample device or appliance; and when more than one sample device or appliance is included in a candidate list, identifies the device or appliance by performing a selection among the candidates based on characteristic parameters related to the respective calculated cross-correlations.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09606153&OS=09606153&RS=09606153
owner: Telecom Italia S.p.A.
number: 09606153
owner_city: Milan
owner_country: IT
publication_date: 20100804
---
This is a U.S. National Phase Application under 35 U.S.C. 371 of International Application No. PCT EP2010 0613541 filed Aug. 4 2010 which was published under PCT Article 21 2 the entire contents of which are incorporated herein by reference.

The present invention generally relates to the field of home automation domotics. More specifically the present invention concerns a method and a related system allowing the automatic recognition of electric devices apparatuses like household appliances and in particular a method and a system conceived to enable automatic detection of devices appliances for example electric devices appliances connected to the power supply through the use of a home area network for example and not limitatively a Wireless Sensor Network WSN .

Home automation is an evolving field. In this context several solutions have been and are being deployed for energy management purposes and standards are emerging for covering the application scenarios. Some of the known solutions exploit WSNs. As known a WSN is a network of spatially distributed autonomous nodes with sensors to cooperatively monitor physical or environmental conditions such as temperature sound vibration pressure motion pollutants. WSNs are nowadays used in many industrial and civilian application areas including industrial process monitoring and control machine health monitoring environment and habitat monitoring healthcare applications home automation traffic control. In addition to one or more sensors each node in a WSN is equipped with a radio transceiver or other wireless communications device a small microcontroller and possibly an energy source usually a battery. A WSN normally constitutes a wireless ad hoc network meaning that each sensor supports multi hop routing several nodes may forward data packets to a base station .

GB 2451001 describes a smart metering system using low power radio transmission the system is composed of several sensors which generate consumption signals and a central unit for display information and graphical data about metering.

WO 2009 097400 discloses systems and methods for monitoring and controlling the power consumption of a power consuming device. During the installation phase the information about position of smart plugs is set this information is then used to process the power signal accordingly.

The Applicant has observed that most of the known solutions require a start up procedure that involves direct human intervention in order to specify what system the specific sensor node is going to monitor and control. This is believed to be a significant drawback especially in view of the fact that the average domestic user may be and often actually is not accustomed to technical tasks and may thus be discouraged.

The Applicant tackled the technical problem of devising a solution that allows monitoring and possibly controlling devices appliances particularly although not limitatively electric devices appliances using a home area network like for example a WSN without the need of direct or indirect human interaction at least not in the system set up phase.

The Applicant has found a solution that enables an automatic procedure for the discovery of the devices appliances particularly electric devices appliances connected to the home area network particularly the WSN leveraging on this functionality the solution according to the present invention avoids direct human intervention for specifying the devices appliances to be monitored and possibly controlled.

Essentially according to an aspect of the present invention there is provided a system for the automatic identification of a device or appliance. The system comprises 

In particular said at least one reference pattern comprises at least two reference patterns each one corresponding to a respective observed evolution in time of the monitored electric quantity in respect of a specific operating mode of a same sample device or appliance.

Said at least one reference pattern may be generated by averaging observed evolutions in time of the monitored electric quantities of devices or appliances or by observing the evolution in time of the monitored electric quantity of the device or appliance to be identified during a first cycle of operation thereof or by detecting characteristic events in the observed evolution in time of the monitored electric quantity.

In particular said detecting characteristic events comprise detecting peaks in the evolution in time of the monitored electric quantity.

In an embodiment of the present invention said calculating the cross correlation may comprises determining an observation temporal window and cross correlating the monitored electric quantity and the at least one reference pattern in at least one time interval corresponding to the determined observation temporal window.

Preferably said calculating the cross correlation is repeated in at least two different time intervals of length equal to the determined temporal window.

Said observation temporal window may for example be determined by detecting characteristic events in the observed evolution in time of the monitored electric quantity.

In an embodiment of the present invention said analyzing comprises before calculating the cross correlation transforming the observed evolution in time of the monitored electric quantity and the at least one reference pattern into the frequency domain and wherein said calculating the cross correlating is performed on the results of the transformation.

In particular said characteristic parameters may include at least one among a mean value relative maximum values standard deviation.

The system may advantageously be embedded into a smart socket through which the electric device or appliance is pluggable to an electricity socket.

According to another aspect of the present invention a method is provided for the automatic identification of a device or appliance the method comprising 

in case more than one sample device or appliance is included in the candidate list identifying the device or appliance by performing a selection among the candidate devices or appliances based on characteristic parameters related to the respective calculated cross correlations and different from said value.

Referring to the drawings in there is schematically shown an architecture of a system according to an embodiment of the present invention particularly a system for energy management and control of devices appliances capable of automatically discovering and detecting the devices and or appliances plugged to an electricity distribution network i.e. in the described embodiment electric devices appliances based on a processing that as will be described in detail later exploits measurements of the absorbed power performed on the devices appliances themselves by means of sensors of a home area network for example a WSN.

In reference numeral denotes a house e.g. an apartment wherein there are deployed electric devices and or appliances by way of example a personal computer a television set and a washing machine clearly different and or additional electric devices appliances may be installed in the apartment like for example a refrigerator an oven a dishwasher a laundry dryer as well as devices appliances that not necessarily are powered by electric power e.g. thermal energy devices appliances .

The electric devices appliances are plugged to the AC sockets of the house through smart sockets each one incorporating a sensor node of a home area network preferably a wireless network e.g. a WSN hereinafter and unless the contrary is stated reference numeral will be used equivalently to denote the smart socket or the sensor node embedded therein the use of smart sockets including sensor nodes is advantageous because there is no need to have dedicated devices appliances already embedding sensor nodes so that the present invention can be practiced also in conjunction with already deployed devices appliances however nothing prevents from exploiting the present invention also in case devices appliances with embedded sensor nodes are used. The sensors in the sensor nodes are configured to perform electric power and energy measurements on the devices appliances that are connected to the respective smart sockets the sensors may comprise an integrated circuit operating the measurements and a relay to manage the electric power to be distributed to the loads connected to the physical AC socket.

In embodiments of the present invention the home area network is for example as mentioned above a WSN. Each sensor node includes a wireless transceiver adapted to wirelessly communicate with other nodes of the WSN based on a wireless communication protocol for example and not limitatively a ZigBee protocol or other suitable mesh networking protocols. Some or possibly each one of the nodes of the WSN are configured to act as relay nodes i.e. as wireless routers between the other WSN nodes and a gateway moreover nothing prevents that the gateway function be embedded in one of the WSN nodes .

The gateway is configured to manage the electric devices appliances and to gather from the respective WSN nodes the information related to the different devices appliances.

The gateway is also configured to communicate through a communication network like a telephone network either mobile or not or a combination of the two and or a packet data network like the Internet with a remote platform comprising one or more possibly distributed servers the remote platform is configured to gather the data sent by the WSN nodes to the gateway and to store them in suitable databases in order to make the stored data accessible by remote applications the access to the data managed by the remote platform by the remote applications may for example be performed using high level APIs Application Programming Interfaces .

A method according to an embodiment of the present invention for the automatic recognition i.e. identification of the type of electric devices appliances plugged to the electricity distribution network will be now described.

The electric devices appliances are plugged by the user to the sockets of the AC distribution network through the smart sockets which incorporate the sensor nodes block . In case the device appliance already embeds a sensor node the smart socket is not required and the device appliance can be plugged to the AC main socket directly.

In a configuration phase the sensors in the sensor nodes are automatically configured by the gateway block for example using a wireless communication protocol like the ZigBee protocol the configuration is aimed at enabling the sensors nodes and the sensors embedded therein to perform on the associated electric devices appliances measurements of instantaneous electric power consumption and energy absorbed. For example the sensor nodes are configured in such a way as to cause the sensor nodes to report to the gateway information related to the measured device appliance power consumption and absorbed energy block . The reporting procedure by the sensor nodes to the gateway may for example follow the following guidelines 

According to an embodiment of the present invention in order to avoid the need of a manual configuration of the association between the sensor nodes and the respective devices appliances a procedure is performed for automatically recognizing the electric device appliance plugged to AC socket through the smart socket containing the sensor node s block . In an embodiment of the present invention the automatic device appliance recognition procedure may preferably comprise the following three phases which are described in detail in the following 

The device appliance recognition procedure is repeated until the device appliance is identified blocks and .

The phase for the selection of the training sets may according to an embodiment of the present invention be carried out as schematized in the flowchart of . A training set may be defined as a reference pattern for the evolution in time of the power consumption corresponding to a known electric device appliance or class of electric devices appliances. For example the instantaneous power over time may be chosen as the quantity to be monitored and to be used for the identification of the devices appliances.

According to the above described reporting procedure the generic sensor node is configured to report the measured data to the gateway in case of changes in the measured values above predetermined thresholds or in any case even when no changes greater than the predetermined thresholds occur after the maximum amount of time Tfrom a previous measurement data report is elapsed. In particular the generic sensor node measures the instantaneous power consumption of the associated device appliance. Thanks to this the reported instantaneous power measurements can advantageously be used by the gateway or by the remote platform to track the real power consumption curve of the electric device appliance concerned.

It is observed that the reporting procedure of the measurements data from the sensor nodes to the gateway involves a reduction in the number of measurement samples available at the sensor nodes the number of measurement samples taken by the sensor e.g. a power meter is significantly higher than the number of samples transmitted to the gateway by the sensor node . This reduction in the number of measurement samples can be described as a noise perturbing the measure of the monitored quantity e.g. the instantaneous power. Such a noise can nevertheless be filtered out by means of the matching check process described later on.

A sliding temporal window of suitable time length is used to process the incoming data about real power consumption measurements provided by the generic sensor node to the gateway . The data contained in the current temporal window a snapshot of the data flow received at the gateway are compared to one or more training sets.

According to an embodiment of the present invention three options are provided for the selection of the training set s 

a one i.e. single training set block the data contained within the current temporal window are compared to a single training set this way can be useful for those kinds of electric devices appliances that in operation exhibits substantially always the same behavior 

b family of training sets block in this case the data contained in the current temporal window are compared to two or more possibly several different training sets of a training stets family which can for example describe different behaviors of the electric device appliance e.g. a washing machine which may be programmed to operate according to different washing programs 

c auto test block in this case the measured data collected in respect of the first cycle s of operation of the electric device appliance i.e. the instantaneous power measured data corresponding to and collected in respect of the first cycle s of operation of the electric device appliance are taken as the training set i.e. as the reference pattern to be used thereafter for the comparisons with the data contained in the sliding temporal window.

In cases a and b the nature of the source of the training set is then chosen block . Possible training set sources are 

In case c the collected data are scanned looking for the first peak in the curve of the instantaneous power consumption block . The scan of the data is for example done using the same technique as the one described in the following for the recognition of events process in the segmentation phase . Then the power consumption curve following the first peak of power is recorded until the measured instantaneous power returns to zero for a certain time. The recorded data becomes the training set to be used afterwards block .

The segmentation phase may according to an embodiment of the present invention be carried out as schematized in the flowchart of .

The segmentation process carried out in the segmentation phase is directed to identify the cycle of operation of the electric device appliance connected to the sensor node enabling comparison between discrete sets of data that need to be classified properly. In particular the segmentation process aims at creating the temporal window that will thereafter be exploited in matching phase.

Firstly the data received from the sensor nodes are gathered in a database block the data may be collected locally on the gateway or remotely in the remote platform the processing of the gathered data may be carried out by the gateway or by the remote platform . Before the data are processed data relating to an observation time period are gathered the observation time period may be configurable and may for example be set to correspond to one day one week or a longer period.

Due to the different times of arrival of each measurement data sample the collected data should be managed and put in a same time base. This may be done by linearly interpolating e.g. by performing a Spline interpolation using a polynomial of degree higher than 1 the data and time of arrival the latter being for example described by a timestamp assigned to the received data block in an embodiment of the invention the interval between two successive data samples may be about 10 seconds so as to avoid excessive growth of the dataset.

The temporal window to be used in the subsequent matching phase is then chosen block . The temporal window may be defined in two ways 

b using a recognition of events method that allows recognizing the presence of an event and isolating a proper temporal window in respect of it.

The main difference between these two methods resides in the computational time because the sliding window method calls for verifying the matching continuously.

Let case a be considered. The length width of the training set is calculated block . The width of the temporal window is defined by the length of the training set. Since the choice can be made among several possible training sets each one with its own length the temporal windows created by the segmentation process may be different from case to case. The temporal window is then created the temporal window is created for each sample and has a width defined by the length of the training set block .

In case b leading edges of the power consumption curve relating to the device appliance to be recognized are located block . To this purpose two thresholds may be defined 

A scan is then performed over the whole observation time period looking for the leading edges using the above defined thresholds. At the end of the process a list of start points of all the leading edges is created. After each detected leading edge the end of the event is determined block . To this purpose a search is performed to find the first sample that satisfies the two following threshold 

The temporal window is then created block based on the positions of the detected leading edges and the respective ends of the events.

According to an embodiment of the present invention the matching check phase is based on the Bayesian decision theory. The formula for decision is 

where P r H is the a posteriori probability of hypothesis H P r H is the a posteriori probability of hypothesis H. The ratio on the left of the inequality is called plausibility function and can be regarded as the distance between the two hypotheses H and H. If the plausibility function is bigger than the decision threshold the hypothesis H is chosen otherwise hypothesis H is chosen.

The method described below aims at identifying the device appliance that minimizes the distance between its own instantaneous power consumption curve x t and the curve y t defined by the selected training set. The formula for the distance used is the Euclidean distance 

The integral in the above formula is developed in its components by applying the linearity property of integral transformation f x y f x f y and f ax af x Eand Eare the energy of each function instantaneous power consumption curve of the device appliance to be recognized and of the training set respectively while the last addend in the formula on the right can be seen as the cross correlation in a temporal window where the two functions overlap. The cross correlation is a function that is useful to provide a measure the affinity of two different signals and the delay needed for them to overlap. The formula in a time discrete scenario as the one here considered is 

The value of the cross correlation is compared to a threshold that preferably can be configured. The correlation can be normalized to the energy by dividing Rby a norm factor obtained for example as follows 

Once the temporal window is identified block using the segmentation procedure described above iterations are performed among all the classes groups of devices appliances i.e. washing machine refrigerator dishwasher oven microwave oven television set personal computer etc. that might be recognized in the stream of data received by the sensor nodes . A running index i in the flowchart is used to iterate the procedure for the different classes of devices appliances and at each iteration a new class of devices appliances is selected blocks and .

For each class of devices appliances one or more training sets for example a family or group of training sets is are available and is are used for the matching check each training sets group contains a set of signal patterns to be used for trying the match with the data within the current temporal window. When more than one training sets are available the training sets at least some of them possibly all within the group corresponding to the selected group of devices appliances are considered in succession running index j in the flowchart and blocks and .

For evaluating the match between the selected training set j and the data within the current temporal window the energy normalized cross correlation is calculated as described above block .

If the calculated energy normalized cross correlation is below a predetermined minimum threshold MINthreshold block exit branch Y i.e. if the correlation between the selected training set and the data in the current temporal window is too weak this means that with a probability proportional to 1 MINthreshold the data contained in the current temporal window do not correspond to any device appliance belonging to the currently selected device group. No further attempts are made with other training sets of the family and the next group of devices is then selected block to search a potential match in the data set provided that there are further device appliance groups still to be tried block exit branch Y .

On the other hand if the calculated energy normalized cross correlation is not below the minimum threshold MINthreshold block exit branch N it is checked whether the calculated energy normalized cross correlation is below or above a predetermined maximum threshold MAXthreshold block . If the calculated energy normalized cross correlation is below the maximum threshold MAXthreshold block exit branch N a new training set j j 1 is selected for the device appliance group i under consideration block in order to iterate the pattern matching and check if it is possible to improve the match likelihood by verifying the cross correlation against the new training set block . If however there are no more training sets available for the currently selected group of devices appliances block exit branch N the currently selected device appliance group i is not put in a list of candidate devices appliances responsible for the generation of the data block and the procedure is iterated on a new group of devices appliances block after assessing whether other devices appliances groups exist decision block exit Y other devices appliances groups available or exit N no more devices appliances groups to be tested .

In case the calculated cross correlation is bigger the maximum threshold MAXthreshold block exit branch Y then the currently selected class of devices appliances is put in the candidate list block .

At the end of all the iterations if the list of candidates is void the currently selected temporal window is discarded.

The above described process is repeated for a number of e.g. consecutive temporal windows minimum 1 the number of consecutive temporal windows depends on the number of groups of events that one wishes to take into account .

In this way a list of candidate classes of devices appliances is built which contains candidate classes of devices appliances for which the energy normalized cross correlation between the data measured by the sensors and the reference pattern s defined by the training set s in at least one of the considered temporal windows is above the maximum threshold MAXthreshold.

If there are candidates in the list the device appliance that generated the collected data stream is one of the devices appliances in the candidates list.

According to an embodiment of the present invention a cross comparison is performed to reduce the probability of false positives included in the list of candidates and thus improving the reliability of the matching block .

Reference is made to . As mentioned above the matching process is operated separately on each temporal window index i from to R in respect of different classes of devices appliances training set TS index j from to N each class having associated therewith one or more possibly a family of training sets created for example as described in the foregoing.

Each training set TS or each family of training sets corresponds to and identifies a single class of devices appliances e.g. washing machine dishwasher refrigerator oven etc. .

For each class of devices appliances an array of R elements is created each element of the array corresponding to the outcome of the matching process i.e. calculation of the cross correlation and comparison with the thresholds MINthreshold and MAXthreshold in a respective one of the R temporal windows. In the arrays the result of every matching is for example indicated as a 1 in case the event is recognized i.e. the calculated cross correlation is above the maximum threshold MAXthreshold and it is indicated as 0 if the event is not recognized i.e. the calculated cross correlation is below the maximum threshold MAXthreshold . In this way N arrays are created containing the results of the matching process in every temporal window i of the set of R temporal windows.

Then the N arrays are joined together to create a single matrix of matching results of dimensions R N. In the matrix the generic row j provides the results of the matching process in the R temporal windows for a certain class of devices appliances whereas the generic column i provides the results of the marching process in the generic temporal window in respect of the different classes of devices appliances.

The combined results matrix can be scanned column by column looking for those temporal windows in which an event has been recognized and matched by more than one training sets i.e. by more than one class of devices appliances. For example if the scan for column i i th temporal window returns a 0 the event in the temporal window i has not been recognized by using any training set i.e. none of the devices appliances classes corresponds to the device appliance that generated the data stream if the matrix scan returns a single 1 on row j block exit branch N the event is recognized as having been caused by a device appliance belonging the class of devices appliances of row j block . If the matrix scan returns more 1 s block exit branch Y meaning that more than one class of device appliance matched the event a second comparison is performed using the value of the calculated cross correlation in the temporal window i. Then the event of temporal window i is recognized as caused by a device appliance of the class in respect of which the highest cross correlation was obtained block .

As an alternative to performing the selection based only on the comparison of the calculated value of the cross correlation the cross correlation functions and their characteristic parameters such as mean value relative maximum values standard deviation or others may also be taken into consideration and analyzed. In this way an increased number of parameters can be used to improve the reliability of the outcome of the matching process.

A different technique can also be applied for certain classes of devices appliances that generate pseudo periodical data sets such as refrigerators or boilers in such cases exploiting an analysis in the frequency domain instead of in the time domain can simplify the matching process. In this case besides the segmentation process described above that leverages on the recognition of the events a broader temporal window containing several pseudo periods of the signal are considered. Both the data set and the training sets are transformed into the frequency domain using for example a Fourier transform . The transformed signals have the advantage to highlight the harmonics of pseudo periodic behaviors leading to a faster recognition then the signals in the time domain the recognition can be performed using the pattern matching technique with the cross correlation described above.

Possible alternative embodiments of the invention could be the usage of a distributed algorithm to operate the classification of the signal the processing could be performed in this case locally by the sensor nodes if the processing capabilities of the nodes allow that.

The method according to the herein described embodiment of the present invention can be performed as a software implementation in the network gateway typically a device having limited computational resources or as a remote middleware in case the data gathered from the sensor nodes are logged in a remote database and processed remotely in a more powerful device.

In alternative or in combination at least part of the method previously described can be implemented directly in the smart sockets . schematically shows the main components of a smart socket block denotes one or more sensors of electrical quantities like current voltage or power for example a current meter or a voltage meter. The sensor sends the measured data to a microprocessor or microcontroller . A transceiver enables e.g. wireless communications with the gateway and with other nodes of the network. The method according to the present invention may be performed by the microprocessor which executes a specific program.

The method described can be also used for automatically detecting events on the monitored devices appliances like for example changes in the proper behavior of the appliances based on which imminent faults or degradation of their performances can be predicted.

The present invention is applicable and useful in different technical fields such as residential energy management system in order to detect the devices connected to the main power using a home area network like a WSN to operate energy management applications e.g. stand by control peak avoidance and commercial energy management systems in order to detect event related to the energy monitoring and operate self recognition of devices monitored by using the WSN.

The present invention has here been disclosed by describing some embodiments thereof. Those skilled in the art will be able to devise several modifications to the described embodiments without departing from the protection scope defined in the appended claims. For example other types of home area network can be used instead of WSNs for networking the sensor nodes like Power Line Carrier PLC and more generally ultra low power networks e.g. Bluetooth WiFi or also a wired LAN.

Also although the present invention has been here described making reference to electric devices appliances the present invention can be applied as well to non electric devices appliances like for example thermal energy devices appliances for example a system of independent heat radiators each one equipped with its own thermostat and thus each one exhibiting a peculiar behavior in terms of absorbed thermal energy. In this case a sensor may be provided in operative association with each device appliance that transduces the monitored quantity for example thermal energy into an electrical signal and the analysis may thus be performed on the transduced electrical signal.

