---

title: Aerial bogey discrimination technique
abstract: A computer-implemented analysis method is provided for identifying a flight trajectory of a bogey relative to earth's surface. The method includes a first step of obtaining first and second altitudes and velocities of the bogey separated by a first time interval. The second step calculates a first difference between the first and second velocities divided by the first time interval to obtain an acceleration vector. The third step determines the direction of the velocity vector. The fourth step determines whether direction of the second velocity vector exceeds an upward pointing threshold. The fifth step determines whether the acceleration vector is negative and substantially perpendicular to earth's surface as a second result being valid. The sixth step reports that the bogey represents a ballistic projectile in response to the first and second results.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08914253&OS=08914253&RS=08914253
owner: The United States of America as represented by the Secretary of the Navy
number: 08914253
owner_city: Washington
owner_country: US
publication_date: 20101208
---
Pursuant to 35 U.S.C. 119 the benefit of priority from provisional application 61 336 131 with a filing date of Jan. 15 2010 is claimed for this non provisional application.

The invention described was made in the performance of official duties by one or more employees of the Department of the Navy and thus the invention herein may be manufactured used or licensed by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

The invention relates generally to discrimination of aerial bogeys. In particular the invention relates to techniques to distinguish between ballistic and flat trajectory airborne vehicles and categorize accordingly for appropriate interception response.

An unidentified aerial object or bogey represents a prospective threat to a defended asset. To intercept the threat as a target the defender must categorize ballistic trajectories on the basis of intermittent observation of an object s trajectory. This has represented a difficult problem by conventional analysis techniques using observably available data.

Conventional techniques for categorizing intermittently observed object trajectories yield disadvantages addressed by various exemplary embodiments of the present invention. In particular various exemplary embodiments provide an indication of apparent acceleration direction with respect to an object s local horizontal plane associated with the intermittently observed object trajectory.

Various exemplary embodiments provide a computer implemented analysis method to identify a flight trajectory of a bogey relative to earth s surface. The method includes a first step of obtaining first and second altitudes and velocities of the bogey separated by a first time interval. The second step calculates a first difference between the first and second velocities divided by the first time interval to obtain an acceleration vector. The third step determines the direction of the velocity vector.

The fourth step determines whether direction of the second velocity vector exceeds an upward pointing threshold. The fifth step determines whether the acceleration vector is negative and substantially perpendicular to earth s surface as a second result being valid. The sixth step reports that the bogey represents a ballistic projectile in response to the first and second results. Various additional embodiments provide transformations to aid in processing the vector information.

In the following detailed description of exemplary embodiments of the invention reference is made to the accompanying drawings that form a part hereof and in which is shown by way of illustration specific exemplary embodiments in which the invention may be practiced. These embodiments are described in sufficient detail to enable those skilled in the art to practice the invention. Other embodiments may be utilized and logical mechanical and other changes may be made without departing from the spirit or scope of the present invention. The following detailed description is therefore not to be taken in a limiting sense and the scope of the present invention is defined only by the appended claims.

In accordance with a presently preferred embodiment of the present invention the components process steps and or data structures may be implemented using various types of operating systems computing platforms computer programs and or general purpose machines.

In addition those of ordinary skill in the art will readily recognize that devices of a less general purpose nature such as hardwired devices or the like may also be used without departing from the scope and spirit of the inventive concepts disclosed herewith. General purpose machines include devices that execute instruction code. A hardwired device may constitute an application specific integrated circuit ASIC or a floating point gate array FPGA or other related component.

Conventional techniques for bogey identification rely on additional information beyond observations of the object s trajectory. Conventional techniques include independent indicators that the object s trajectory is accelerating or that the object s altitude is above earth s surface. Such techniques potentially assume that the object s behavior is associated with the object s position. This condition is not always valid which can lead to interception failure. The instant disclosure describes a technique for categorizing ballistic tracks based on a sequence of system reports of a target s velocity.

For the notional diagram view the A and Dphases correspond to ballistic motion phases of the trajectory. Observed velocity and acceleration vector quantities have distinct characteristics during each phase 

B During boost mode until burnout acceleration points up close to the direction of the velocity which may approach vertical in the upward direction.

A During coast after boost and through apogee acceleration points down while velocity gradually changes from up to horizontal.

D During descent both quantities point down with velocity changing from horizontal to potentially near vertical down.

In the diagram view lower arrows on the V line indicate the velocity direction while upper arrows on the A line indicate the acceleration direction. For aircraft trajectories having constant velocity the acceleration is substantially zero for all directions in comparison to a ballistic missile . These considerations enable development of a procedure to distinguish between ballistic and non ballistic type trajectories.

The following information describes an algorithmic process for calculating the velocity and acceleration directions of a bogey referred to herein as a target generally. The process starts with an observed or calculated velocity data stream. The process then tests those values to determine transition from Bphase to Aintervals for purpose of categorizing the velocity data stream as representative of a ballistic type trajectory. The analysis assumes that input velocity stream is or can be represented in the coordinate system horizontal to the earth surface at the target s position.

An observed target s velocity components can be transformed from the observed position and velocity coordinates to the target s coordinate system using supplementary formulae described subsequently. Within the target s frame both the Flight Path Angle FPA and the Acceleration Path Angle APA formulae indicated herein may be applied to the transformed velocity coordinates.

The relative processes considered are described herein. Velocity vector components are provided in the axial x lateral y and vertical z directions for time increments denoting previous i 1 and instant i described as arrays 

An exemplary comparison can be described for explanatory purposes. The examples include a bottle rocket and a balsa wood toy airplane. The high performance bottle rocket produces thrust against the force of gravity causing the rocket to move upwards. During this Bphase both gravity and thrust forces affect the rocket s motion. After exhaustion of its propellant at cutoff the rocket continues upward until the gravity overcomes its inertia so as to reduce vertical ascent speed. This is labeled as the BAphase during which gravity gradually overcomes the upward velocity until the rocket reaches its maximum height on an inverted parabolic trajectory. Upon the rocket reaching its peak at apogee it begins to descend in the mode labeled as BD.

As a simplified numerical example a massless bottle rocket exerting thrust to accelerate at 20 m s meters per second squared with an acceleration angle of 75 from horizontal and subject to 9.8 m sgravity achieves a velocity vector x y z of

For example the rocket s boost mode has initially zero velocity vectors whereas these vectors are non zero for end of boost ascent and descent . Thus the rocket s FPA shifts from positive to slight negative after apogee and its APA shifts from positive to negative vertical after cutoff . In addition the airplane exhibits constant velocity and no change in altitude so that the airplane s FPA remains zero and its APA is indefinite.

The exemplary discriminator has the advantage of being applicable on the basis of a target velocity data stream. Additional target position data and knowledge of earth radius may be incorporated to support conversion of observed target data to local target coordinate system.

Conventional interpretation assumes that acceleration components derive from measured velocity values. However these have large noise characteristics and calculations based on observer based information have low reliability. Additionally concern over ballistic threats has only recent origins as compared to airplanes such as bomber aircraft with design choices possibly influenced by computational capabilities of prior generation computers comparatively slow leading to reluctance to perform calculations that may have questionable reliability.

Results of investigation in support of exemplary embodiments indicate that despite high noise characteristics for acceleration quantities the angle computed from these can be suitable to support categorization for ballistic type motion even when noisy resulting in the technique presented herein.

Conventional system results indicate less than 15 of a specific set of targets can be correctly categorized as ballistic. Based on desktop analysis using the same data stream applied to the exemplary algorithm various exemplary embodiments improve this performance to over 90 being correctly categorized.

Based on the earth s spheroidal surface coordinates can be translated for the observer s position to a remote horizontal and a remote vertical . The elevation distance of the target s position from the surface can be expressed as altitude vector from the surface . The remote vertical vector is approximately collinear to the horizontal velocity vector right arrow over v passing between the earth s center and the target position and offset from the displacement vector Rby the transition angle .

From the observer s position the local horizontal and the local vertical coordinates can translate to the remote horizontal and the remote vertical coordinates. Gravitational acceleration operates perpendicular to the surface and thus along the local and remote verticals and . The target s position can be described relative to the observer s position as a distance vector right arrow over v as a horizon distance vector right arrow over r as line and an elevation distance right arrow over R as line .

Formulae can be sought for the velocity angle of velocity vector right arrow over v with respect to the remote horizontal to the spheroid surface at the target position . Components of the velocity can be solved for the target horizontal coordinate system THCS labeled as Remote Horizontal. The following parameters can be defined 

right arrow over v velocity vector coordinates of the target position e.g. in local frame coordinates.

The position vector right arrow over r is provided in local frame coordinates horizontal and vertical as rrr in which superscript T denotes matrix transpose. Altitude is provided at target position . Expectant angle between the local horizontal and the target remote horizontal is given by eqn. 6 as 

A first local transition unit vector as line aligns along the right arrow over r position vector associated with a second local transition unit vector as line orthogonal to the first within the plane of the x and y axes . The unit vectors and define the horizontal portion of an intermediate coordinate system . The first unit vector as lies collinear to the position vector right arrow over r as from the observer position to the target position . The transition vector as line is perpendicular to as line but also lies within the original local horizontal plane.

A remote system includes a horizontal transition unit vector also tangent along the surface and a vertical transition unit vector parallel to earth radius Ras line . A local target velocity vector right arrow over v as line represents a velocity whose components are known within the local coordinate system but whose components have not yet been determined within the remote coordinate system.

The intermediate coordinate system transforms the local coordinate system to the non standard remote coordinate system . Construction of the intermediate coordinate system provides for the axis to run from the origin of the local coordinate system in the direction of the target position while both unit vectors and remain in the original local horizontal plane. The remote coordinate system represents a subsequent portion of the transformation involving transformation using the transition angle described subsequently.

Generally obtaining the flight path angle with respect to horizontal plane involves determining the components of the velocity vector right arrow over v in the plane of the local horizontal then performing the calculation of eqn. 7 

This calculation can be used in either local frame coordinates or remote frame coordinates with the former employed in this example. These can be transformed to the remote frame coordinates through the intermediate coordinate system . New coordinates can be developed by defining an intermediate set of coordinates that are aligned with the radial vector between the two coordinate systems in this case target position vector right arrow over r and apply the transformation from local to target frame using the transition angle . The process for accomplishing this is described below.

First the local intermediate frame coordinate axes where subscript i represents the three orthogonal coordinates 1 2 3 can be developed from the position vector coordinates for all three directions given by eqn. 8 

This defines a local intermediate coordinate system whose coordinates are represented in the local frame coordinate system . In this system the unit vector lies in the horizontal plane in the direction of the target. The unit vector lies along the local tangent plane vertical axis. The unit vector also lies in the horizontal plane and is perpendicular to the other two vectors and .

The target velocity vector right arrow over v can be denoted in the local radial aligned system . The calculation for intermediate velocity vector v is given by eqn. 9 

The transformation through the transition angle occurs along the radial about the unit vector . The transformation can be written as eqn 10 

As an aside one end of the vector right arrow over r as line is coincident with the origin 0 0 0 of the local horizontal plane at point . The other end lies at r r 0 in the local horizontal coordinate system . For the remote horizontal coordinate system the other end of the position vector right arrow over r lies along the remote vertical axis direction of that runs in the remote horizontal coordinate system through either the origin 0 0 0 or else the coordinates 0 0 alt .

From this the coordinates for the remote radially aligned target velocity coordinate system are formed by the calculation in eqn. 12 12 which may alternatively be written as eqn. 13 

Upon establishing the coordinates the calculation is straightforward. For any coordinate system obtaining the flight path angle or FPA with respect to the horizontal plane involves determining the components of the velocity vector right arrow over v in the horizontal plane for that coordinate system and subsequently performing the calculation by eqn. 14 

An exemplary problem can be demonstrated in association with signal to noise. For a vector of variables

From Bar Shalom the expected value of a function of a random variable may be provided for expected value E of a function g for random variable x may be provided by integration 21 where g x represents a deviation in the x variable.

Both Maxwell Boltzman and Rayleigh distributions can be assumed to have the same standard deviation. The distribution of a function of two well known distributions can follow a normal i.e. Gaussian distribution and have the same standard deviation. The function g defined is the vector angle calculation defined in eqn. 17 .

As an exemplary test a true transient axial displacement vector right arrow over x t can be generated as a first step 

As a fifth step a difference function t can be computed as 26 with the difference function representing the absolute value of the differences between true angle right arrow over x t and noisy measured angle right arrow over y t .

For a numerical example true vector right arrow over x values for true displacements x y z can be 3 4 5 in scalar form. These values would yield true angle value of 45 . For the corresponding measured vector right arrow over y values to be extremely noisy this may produce measured displacements u v w 5.5 6.5 7.5 . Under this circumstance the measured angle would be 41.4 .

Alternatively for corresponding measured values being nominally noisy with measured displacements may be u v w 3.25 4.25 5.25 the measured angle would be 44.5 . For corresponding measured values being only slightly noisy measured displacements correspond to u v w 3.025 4.025 5.025 . For that example the measured angle would be 44.9 . Consequently the difference function t can be plotted in a histogram.

Plots and demonstrate the difference in response to increasing the original magnitude of the input quantities. At all the left side plots their respective fixed points x y z are set to zero. This is followed by performing the angle calculation with noisy values resulting in an arbitrary angle calculated from noisy zeroes. On the right side the point values x y z have been increased while maintaining a fixed measurement noise.

This causes somewhat unintentionally the original magnitude of the vector x y z to increase with respect to the noise. This was realized to be similar to a signal to noise type problem. Typically the greater the vector length the less likely that its direction is be affected by comparatively small noise. The high speed of missiles constitutes a benefit to this aspect of the problem.

For the graphical views the left side histogram plots and have steady state conditions as x t y t z t 0. The right side histogram plots and are transient with x t y t 25.0 t and z t 0.1 t. For both sides true x y and z values can be computed to calculate true angle. Also noisy x y and z as u v and w values can be computed for a noisy angle t . The difference t can be calculated between true and noisy angles and can be plotted as histograms.

For plot in the expected value integral provides the analytical predicted maximum based on an integral restriction 

The first expected plot features results from a fixed length z against a variable input noise calculating output statistics of the distance function in a simulation curve . The second expected plot includes a legend identifying an analytical predicted curve of eqn. 27 and a simulated actual curve which corresponds to the same curve of plot .

The deviation angle in eqn. 27 represents a variable of integration developed based on transformation from Cartesian coordinates to spherical coordinates when attempting to evaluate the three dimensional version of eqn. 21 which is not readily amenable to closed form solutions. Thus the solutions presented employ a Monte Carlo type approach for generating an expectation plot in and providing an adequate approximation plot in .

The approach described herein has resulted from an investigation into resolving considerations for operating an existing conventional system. The conventional system included ability to indicate circumstances in which an observed track exhibits ballistic behavior. Many analytical paths have been investigated to distinguish ballistic and flight trajectories. The difference method provides the most preferred results and from approximating the Expectation integral of eqn. 21 due to difficulty in developing closed solutions.

A coordinate query can be performed on the resulting estimated state as to whether that state is provided in the target horizontal coordinate system THCS . If false as generally expected the process diverts to a conversion operation using the coordinate transformations described above. Then or otherwise if the query is true the process proceeds to a signal quality query as to whether the filtered and transformed state has an adequate signal to noise SNR ratio. If not the process determines at operation that the bogey s state is indeterminate and that further information may be required. Noisy signals compromise the ability to determine acceleration unless change in velocity exceeds some SNR threshold such as for a ballistic missile.

If SNR is adequate the process diverts to a calculation operation to determine flight path and acceleration path angles FPA and APA respectively from eqns. 1 and 5 . A trajectory decision query uses the calculated path angles to inquire whether acceleration path angle vertically points downward 90 and whether flight path angle is significantly greater than zero 0 . For a bogey in which both conditions are satisfied the process determines that the signal indicates a ballistic target . Otherwise at such a determination cannot be made such that the bogey constitutes a possible aircraft or other aerial object.

These operations and portions thereof can be performed as operational steps being performable by machine operation e.g. a programmable code for a general purpose computer or else an ASIC. The process results in an automated determination based on noisy input data and optional transformations with an identity determination that a bogey constitutes a ballistic threat.

The considerations are indicated in letter from Naval Surface Warfare Center Dahlgren Division to Aegis Ballistic Missile Defense Program Office reference 9000 Ser WO5 058 Certification of Aegis Ballistic Missile Defense BMD Aegis Weapon System AWS Baseline 3.6.1.1 Computer Programs dated 20 Mar. 2009.

In summary conventional systems rely on information other than velocity and are sensitive either to relative position information or to delays in reporting the alternative information. Testing indicated the referenced system would perform poorly against certain types of targets which led to an examination of techniques in use by that system and subsequent development of the exemplary process described above.

While certain features of the embodiments of the invention have been illustrated as described herein many modifications substitutions changes and equivalents will now occur to those skilled in the art. It is therefore to be understood that the appended claims are intended to cover all such modifications and changes as fall within the true spirit of the embodiments.

