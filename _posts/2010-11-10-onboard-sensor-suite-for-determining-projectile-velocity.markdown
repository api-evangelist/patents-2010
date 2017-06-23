---

title: Onboard sensor suite for determining projectile velocity
abstract: An onboard sensor suite generally includes two main components: a proximity sensor suite for measuring the projectile muzzle velocity; and a pressure sensor suite for measuring the projectile airspeed. The flight velocity of the projectile can then be estimated with a high degree of accuracy using either the muzzle velocity by itself or the airspeed by itself, or, in a preferred embodiment, by using both the muzzle velocity and the airspeed. The proximity sensor suite includes proximity sensors that are mounted along a projectile body; a wire harness; and an onboard computer or CPU. The pressure sensor suite includes a Pitot pressure transducer and two static pressure transducers that are mounted within the projectile body; a wire harness; and a CPU.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08433460&OS=08433460&RS=08433460
owner: The United States of America as Represented by the Secretary of the Army
number: 08433460
owner_city: Washington
owner_country: US
publication_date: 20101110
---
The invention described herein may be manufactured and used by or for the Government of the United States for U.S. Government purposes.

The present invention relates in general to the field of munitions. More specifically this invention relates to onboard sensors and associated method to determine the munition velocity by measuring parameters that are directly related to the munition flight velocity in a continuous manner during flight without relying on external systems or signals. The onboard sensors predict the projectile position accurately and improve the performance of mid course trajectory correction.

A control system for a projectile often requires a measurement of the projectile velocity in order to improve the projectile navigation and accuracy. The need for the projectile velocity has become increasingly important due to the desire for accuracy particularly at longer ranges. Conventional solutions to the measurement of the projectile velocity propose using GPS signals to obtain the projectile velocity and position measurements as well as using Doppler measurements.

Projectile flight velocity estimates are conventionally used for navigation or fuzing purposes. These estimates are typically processed from accelerometer measurements which could lead to measurement bias errors in the velocity estimates.

Although the conventional solutions have proven to be satisfactory they are faced with certain limitations. As an example GPS measurements cannot be used for all applications since some projectiles might not be readily equipped with GPS. More specifically using GPS measurements for a projectile might be unacceptable for at least the following two reasons First if the projectile is not already equipped with GPS capability fitting an entirely new typically complicated GPS system into the existing design might be problematic. Second it might be desirable to maintain the projectile guidance capability in the absence of GPS measurements.

As another example Doppler radar measurements might be limited to certain types of projectiles. More specifically using a Doppler radar might in certain circumstances be unsatisfactory particularly if the projectile is not equipped with a radar seeker or if the projectile does not have sufficient capability or physical space to enable the addition of a new radar seeker. In addition it might be desirable to maintain a passive non RF non radio frequency emitting design.

What is therefore needed is an onboard sensor suite that is capable of determining the munition muzzle velocity without modification to the gun system and that is further capable of accurately determining the in flight munition velocity independently of GPS measurements. The need for such an onboard sensor suite has heretofore remained unsatisfied.

The present invention satisfies this need and presents an onboard sensor suite for long range precision performance of munitions such as guided projectiles. The onboard sensor suite is integrated in a projectile to measure the projectile airspeed in order to estimate its velocity. Based on the estimated velocity the onboard sensor suite predicts the projectile position accurately and improves the performance of mid course trajectory correction.

A feature of the present onboard sensor suite is its relatively small footprint and readily adaptable operation and simple construction that does not require moving parts.

Another feature of the present onboard sensor suite is that it allows the munition or projectile to passively self measure its muzzle velocity at tube exit and its airspeed or in flight velocity in a continuous manner during its in flight trajectory in order to estimate the projectile in flight velocity.

Still another feature of the present onboard sensor suite is its independence of external data inputs from external data systems such as GPS.

To this end the present onboard sensor suite generally includes a proximity sensor suite for measuring the projectile muzzle velocity and a pressure transducer sensor suite for measuring the projectile airspeed in order to estimate the flight velocity of the projectile.

The advantages of the present onboard sensor suite are numerous among which are the following. The onboard sensor suite provides passive measurements without emitting RF signals and without relying on external signals such as GPS satellite signals thus avoiding enemy notification of incoming projectiles. Since the onboard sensor suite is independent from GPS measurements it is not affected by GPS jamming by for example enemy combatants. The onboard sensor suite is relatively small in size and simple to operate in that it does not include moving parts.

The onboard sensor suite begins providing projectile velocity estimates within fractions of a second of muzzle exit. This presents an advantage over conventional systems in that GPS systems require a convergence time on the order of several seconds to start providing projectile velocity estimates which is often a large percentage of the total flight time.

Furthermore the estimates obtained from the onboard sensor suite are updated as fast as the onboard processor can read the analog pressure sensors which can be on the order of 1 kHz or faster. GPS systems currently provide estimates at a rate of about 1 Hz. Faster updates are advantageous to the system using the estimates in that it allows for more sophisticated signal processing to occur in a reasonable amount of time.

The onboard sensor suite generally includes at least one of the following two main components a proximity sensor suite for measuring the projectile muzzle velocity and a pressure sensor suite for measuring the projectile airspeed. The flight velocity of the projectile can then be estimated with a high degree of accuracy using either the muzzle velocity by itself the airspeed by itself or in a preferred embodiment by using both the muzzle velocity and the airspeed.

To this end the proximity sensor suite includes proximity sensors that are mounted along a projectile body a wire harness and an onboard computer or CPU. The proximity sensor suite can be employed on munitions that are either provided with a guidance system or on munitions that are not provided with a guidance system. This proximity sensor suite helps air bursting munitions to have more accurate fuze airburst times.

The pressure sensor suite includes a Pitot pressure transducer and two static pressure transducers that are mounted within the projectile body a wire harness and a CPU. The pressure sensor suite determines in flight munition velocity and therefore it can be integrated in various munitions with guidance systems.

The onboard sensor suite that integrates both the proximity sensor suite and the pressure sensor suite provides an overall velocity profile to munition control systems for more accurate function. These munition control systems include for example guidance fuzing and in flight data link updates.

It should be understood that the sizes of the different components in the figures might not be in exact proportion and are shown for visual clarity and for the purpose of explanation.

According to a preferred embodiment of the present invention the proximity sensor suite measures the velocity of the projectile as it exits a weapon muzzle shown in dashed lines . This velocity is referred to herein as projectile muzzle velocity.

The proximity sensor suite generally includes a plurality of proximity sensors that are disposed along the projectile body . The proximity sensor suite further includes a wire harness that connects the proximity sensors to a central processing unit CPU or computer .

While the present embodiment of the proximity sensor suite is illustrated with two proximity sensors it should be understood that the proximity sensor suite could be provided with more than two proximity sensors that are capable of measuring the projectile muzzle velocity according to the present invention.

The proximity sensors are preferably mounted onto the projectile body so that they are disposed in close proximity to the muzzle from which the projectile exits. The proximity sensors are spaced apart by a predetermined distance D.

Each proximity sensor independently detects its own exit from the muzzle . In one embodiment each sensor uses electromagnetism to defect a forward tip or edge of the muzzle . The exit or egress time for each proximity sensor is recorded by the CPU .

With further reference to each proximity sensor such as the representative proximity sensor is connected to the CPU by means of a wire harness . The wire harness carries the information from the proximity sensors to the CPU .

The proximity sensor i.e. can be formed for example by a magnetic core and a coil of electrical wire that is wrapped around the magnetic core. The magnetic field generated by the proximity sensor is affected by the ferrous or metallic composition of the gun muzzle . The proximity sensor senses changes in the magnetic field as it moves past the forward edge of the muzzle .

While the CPU is illustrated as being mounted in the aft section of the projectile it should be understood that the CPU may alternatively be disposed at other suitable locations within the projectile .

In operation the distance D between the proximity sensors is stored in a memory or storage device along with the exit time t t of each sensor . The CPU calculates the average velocity V of the projectile by dividing the distance D by the difference in exit time t where t t t.

This average projectile velocity V is substantially close to and is approximated to the muzzle projectile velocity. The muzzle projectile velocity V can be used to initialize the guidance and navigation algorithms for the projectile in order to estimate the projectile states during flight.

According to a preferred embodiment of the present invention the sensor suite measures the airspeed of the projectile in order to estimate the flight velocity of the projectile during flight. This allows the sensor suite to predict the position of the projectile more accurately and to improve the performance of mid course trajectory correction.

The pressure sensor suite generally includes a plurality of pressure sensors that are preferably disposed in the nose of the projectile and a wire harness that connects the pressure sensors to a central processing unit CPU or computer .

While the present embodiment of the sensor suite is illustrated with three pressure sensors it should be understood that the sensor suite could be provided with a different number of pressure sensors that are capable of measuring the projectile airspeed. As an example one static pressure transducer could be used with one Pitot pressure transducer although such embodiment might introduce some error resulting from the projectile angle of attack.

In the preferred embodiment illustrated herein the pressure sensors include one Pitot pressure transducer and two static pressure transducers . The Pitot pressure transducer is preferably disposed at the forwardmost tip of the projectile nose and measures the total air pressure at the projectile nose . According to a preferred embodiment of the present invention the Pitot pressure transducer is located along a longitudinal central axis of symmetry of the projectile .

While one Pitot pressure transducer is illustrated herein it should understood that a different pressure transducer that measures the total air pressure at the projectile nose may be used. The measured air pressure is transmitted to the CPU via the wire harness . According to another embodiment one or more Pitot pressure transducers may be disposed at different locations within the projectile nose .

While two static pressure transducers are illustrated herein it should be understood that a different number and types of pressure transducers may be used to measure the static pressure of air at the nose section that is located rearward and in proximity to the forwardmost tip of the projectile nose . According to a preferred embodiment of the present invention the two static pressure transducers are located symmetrically relative to the longitudinal central axis of symmetry of the projectile .

Each of the two static pressure transducers measures the air pressure exerted at its corresponding location. The data collected by the two static pressure transducers is transmitted to the CPU via the wire harness . The data is averaged by the CPU in order to compensate for the projectile s angle of attack.

The resulting air pressure average is then compared with the air pressure at the projectile nose that is measured by the Pitot pressure sensor . The relationship between the average static air pressure P and the Pitot air pressure at the forwardmost tip of the projectile nose P is directly related to the velocity of the projectile as it will be explained later in more detail.

The ratio of the average static air pressure P and the Pitot air pressure P is can be related to the free stream Mach number of the projectile . The CPU performs the necessary calculations to estimate the projectile airspeed.

A subsonic flow relationship and a supersonic flow relationship exist between the average static air pressure P the Pitot air pressure P and the free stream Mach number of the projectile are described below.

Using the foregoing subsonic equation the CPU calculates the Mach number M between the bow shock wave and the nose of the projectile for supersonic freestream conditions and the freestream Mach number M for subsonic freestream conditions.

For supersonic freestream conditions using the foregoing supersonic equation the CPU calculates the free stream Mach M. The CPU thus continuously calculates the projectile airspeed A according to the present equation Speed of sound in air assuming the temperature of the air is known a priori.

According to a preferred embodiment of the present invention the sensor suite includes a combination of a proximity sensor suite that has been described in connection with and a pressure sensor suite that has been described in connection with .

The proximity sensor suite measures the projectile muzzle velocity while the pressure sensor suite of the pressure sensor suite measures the airspeed of the projectile in order to estimate the flight velocity of the projectile during flight. This allows a CPU which performs the functions of the CPUs and to predict the position of the projectile more accurately and to improve the performance of mid course trajectory correction.

As explained earlier the projectile muzzle velocity is the velocity the projectile has at muzzle exit. The projectile muzzle velocity can be used to initialize the navigation algorithms contained on the CPU . The airspeed is equal to the velocity of the projectile minus the velocity of the wind that the projectile is flying through. Its measurement can be used by the CPU to update the estimate of the velocity of the projectile throughout flight. Since the CPU has an estimate of its velocity during flight it can use that information in another part of the guidance algorithms to direct the projectile in how it needs to maneuver to get to its intended target location.

The present onboard sensor suite can be used in a projectile that has at least some of the following characteristics fired from a ferrous tube usually steel requires a muzzle velocity estimate in that some projectiles do not rely on muzzle velocity measurements for their navigation which projectiles might not benefit totally from the muzzle velocity measurement requires a continuous airspeed measurement over a large portion of the trajectory in that some projectiles do not rely on velocity measurements for navigation which projectiles might not benefit totally from the airspeed measurement cannot use GPS or requires a redundant system to improve performance when jammed cannot modify the gun tube or cannot broadcast ground measurements.

It should be understood that the geometry compositions values and dimensions of the components described herein can be modified within the scope of the invention and are not intended to be the exclusive. Other modifications can be made when implementing the invention for a particular environment.

