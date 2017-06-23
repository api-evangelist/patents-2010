---

title: Particle characterization via doppler distribution
abstract: Systems and methods are provided for determining information about particle geometry are provided. As such, an ultrasonic transducer acts as both a transmitter and a receiver. The transducer insonifies a particle and scattered waves are then received by the transducer—now acting as a receiver. A small flat target moving relative to a stationary receiver will lead to the same radiated field as waves propagating through an equivalent moving aperture. Based on the Doppler distribution of the scattered or radiated waves resulting from relative motion between the particles and a receiver, the acoustic pressure field in the plane of the equivalent two-dimensional aperture can be inferred. The equivalent aperture geometry can be obtained from the inferred field. Hence, the particle geometry can be determined.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08306763&OS=08306763&RS=08306763
owner: The United States of America as represented by the Secretary of the Navy
number: 08306763
owner_city: Washington
owner_country: US
publication_date: 20100205
---
The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

The present invention relates to characterization of particles and more specifically to a system and method for determining information about particle geometry based on the Doppler distribution of scattered or radiated waves resulting from relative motion between the particles and a receiver.

A wide variety of industrial processes require non contact measurement of materials including separation processes agglomeration reactors milling operations and polymerization. For such applications there is a need for the characterization of physical properties such as particle sizes.

Various apparatus and methods for composition and particle size measurement utilizing ultrasound are known in the art. In addition various methods describe the use of attenuation at two discrete frequencies to monitor mean particle size in a slurry. Generally the particle size distributions are determined by assuming a starting particle distribution predicting attenuation at each discrete frequency comparing the predicted attenuations with actual attenuation measurements adjusting the distribution and then repeating this procedure until a suitable match is achieved between prediction and measurement.

Such methods have a disadvantage in that a large number of physical properties of the particles and suspending medium must be known to make the predictions. In addition the numerical computations required to calculate the theoretical attenuations are time consuming and often unstable.

Those skilled in the art readily understand the wide range of potential applications for particle sizing measurements in various industries such as food mining pharmaceuticals chemicals and petroleum. As such what are needed are methods and systems for particle characterization that minimize or overcome the problems discussed above.

It is therefore a general purpose and primary object of the present invention to provide a system and method for inferring information about particle geometry based on the Doppler distribution of scattered or radiated waves resulting from relative motion between the particles and a receiver.

In order to attain the object described an ultrasonic transducer is provided that acts as a transmitter and receiver. The transducer insonifies a particle and scattered waves are then received by the transducer now acting as a receiver.

Using the measured Doppler distribution the acoustic pressure field in the plane of the two dimensional aperture can be inferred. Since it is known that a small flat target moving relative to a stationary receiver will lead to the same radiated field as waves propagating through an equivalent moving aperture then accordingly the aperture geometry in this case the particle geometry can be determined.

In one embodiment a method for determining information about particle geometry includes insonifying a particle measuring a Doppler distribution of waves scattered from the particle comparing the Doppler distribution to a lookup table distributions and obtaining the particle geometry from the distribution best matching the Doppler distribution.

In one embodiment the method includes generating lookup table distributions. Generating the lookup table distributions includes obtaining the lookup table distributions p x y z t from the relationship

In one embodiment a method for inferring information about particle geometry includes insonifying a particle measuring a Doppler distribution of acoustic pressure waves scattered from the particle given by p x y z t and determining the particle geometry based on the relationship

In some embodiments measuring further includes adjusting an axis of insonification to maximize an extent of the Doppler distribution and determining the amount of adjustment.

In one embodiment a system for inferring information about particle geometry includes a sonic wave transmitter that insonifies a particle a receiver that measures a Doppler distribution of waves scattered from the particle and a processor that compares the Doppler distribution to lookup table distributions.

In one embodiment the system further includes a processor program product disposed on a processor readable medium and having instructions for causing the processor to generate the lookup table distributions p x y z t from the relationship

As is known in the art diffraction causes bending of sound waves. Diffraction can affect Doppler Shifts when there is relative motion between a source and a receiver. The change in Doppler shifts is due to the fact that the received signal is not in the form of a plane wave. Rather the received signal has some characteristics of a spherical wave.

As is also known in the art a spherical wave can be shown to be the summation of plane waves propagating in all directions the Weyl integral . Plane waves propagating at an angle with respect to the receiver will have a lower group velocity than those waves that propagate normal to the receiver. Thus there will be a continuous distribution of Doppler Shifts due to plane waves arriving at different angles with respect to the receiver. However the distribution of Doppler Shifts will occur only under diffraction dominated conditions i.e. when the effective radius of the object is on the order of a wavelength and the distance between the object and receiver is small enough so that the wave front curvature is still important . When diffraction effects are important the Doppler distribution which is governed by the particle geometry can be used to infer information about the particle geometry.

According to Babinet s principle a small flat target moving relative to a stationary receiver will lead to the same radiated field as waves propagating through an equivalent moving aperture. Therefore the field radiated from a simplified particle can be analyzed using the result of a plane wave propagated through an equivalent aperture. Three dimensional particles introduce further complications that generally require numerical modeling. However much of the physics of a three dimensional particle can be captured with a simplified two dimensional model.

It has been shown that the acoustic field due to diffraction by an aperture in a two dimensional infinite screen is 

The diffracted field can be interpreted as an angular spectrum of plane waves a continuous distribution of plane waves originating from the screen wherein the direction of propagation varies from being perpendicular to being parallel to the screen. The group velocity of the diffracted field thus assumes a continuous distribution.

In the far field the integration limits can be truncated to k k where C is the speed of sound since energy at higher wavenumbers is evanescent or nonpropagating in nature. Further assuming that P k k is an even function for illustration purposes leads to 

The integrand represents a summation of pairs of plane waves oriented at varying opposite angles with respect to the planar screen wherein each pair has the form 

The process of separating the acoustic field into pairs of plane waves can be visualized more clearly using the method of exhaustion an expansion for Riemann integrals having the form 

Each pair of terms in this infinite series represents a pair of plane waves propagating at equal and opposite angles with respect to the screen that contains the equivalent aperture that represents the target by Babinet s principle. Depending on the pair of plane waves the phase velocity varies from c to while the group velocity varies from 0 to c. The relationship between the phase and group velocity is similar to that of a waveguide having a constant cross section. However a significant difference is that a waveguide has discrete modes due to finite dimensions while an aperture has a continuous distribution of modes.

The group velocity distribution leads to a distribution in Doppler shifts when there is relative motion between the aperture and the receiver. An aperture moving relative to a stationary receiver with a velocity u leads to a received frequency of f 1 u u for the pair of plane waves having a group velocity of u. For a circular aperture the acoustic pressure can be expressed in polar coordinates as follows Doppler effects included 

The minimum Doppler shift is u c identical to that when there is no distribution. At this Doppler shift the spatial Fourier transform in Equation 12 reduces to P 0 . When u c the amplitude of the Doppler distribution is estimated by Equation 14 to be that of the minimum Doppler shift or 9 dB lower and the power proportional to the square of the pressure amplitude is 18 dB lower.

With a sufficient signal to noise ratio the Doppler distribution should be measurable allowing the possibility of inferring P k k and thus the aperture geometry from a single receiver. However if the radius is large relative to a wavelength then P in Equation 12 approaches zero quickly as increases from so that the distribution will be so narrow in frequency extent that the distribution probably cannot be measured. In this case the only added information is that the effective particle radius is large compared to a wavelength.

The above analysis of an aperture moving relative to a stationary receiver can also be used for an equivalent particle that is moving relative to a stationary receiver again by Babinet s principle.

Referring now to there is depicted a system for obtaining particle geometry information. In the system an ultrasonic transducer acts as both a transmitter and a receiver. Acting as a transmitter the transducer insonifies a particle . Acting as a receiver the transducer receives waves w scattered by the particle and measures the Doppler distribution of the energy scattered from the particle.

As described in the above analysis inferring P k k based on the measured Doppler distribution spectrum can lead to information on the particle geometry in addition to relative velocity of the particle. This can be done with lookup tables of solutions providing Doppler distributions for circular apertures of various radii as well as and also for other shapes. Such lookup tables can be generated from the above analysis given the aperture or particle geometry.

A processor is in communication with the transducer and receives data from the transducer . The processor compares the measured Doppler distribution to known distributions in the lookup tables. The particle geometry corresponding to the distribution in the lookup table that best matches the measured distribution is taken as the geometry for the particle .

In many cases an irregularly shaped particle can be approximated as an equivalent flat circular particle. Lookup tables can also be included incorporating irregular shapes. When three dimensional effects are important lookup tables can be generated with finite element models for spheres and other important shapes.

In addition to obtaining particle geometry information the system can be used to localize particles such as the particle to a greater degree of accuracy than otherwise possible. This localization can be accomplished by taking advantage of diffraction effects as seen from the second term Bessel function J in Equation 12 . When the particle moves from r 0 the value of the Bessel function term changes quickly.

Referring back to the particle can be localized by adjusting the transducer until the particle lies along axis X so that the extent of the Doppler distribution is maximized. In the adjustment is illustrated by dotted line x. In this case the transducer acts as a continuous array steered in the broadside direction. The distance from x to axis X can be directly inferred using Equation 12 . With an array of receivers a particle moving across the received beams can be localized in r more precisely by the variation in the Doppler distribution.

The maximum distance L between the particle and the transducer is governed by L d 8 wherein d is the receiver diameter of the transducer and is the acoustic wavelength. At this distance the wavefront curvature will lead to a phase difference of 2n between the center of the transducer and an edge of the transducer. For example a 2 MegaHertz MHz transducer having a diameter of one inch will lead to a maximum distance of 4 inches. To increase the maximum distance a higher frequency transducer can be used.

Referring now to there is shown a block diagram of method for obtaining information about particle geometry. At block a particle is insonified. The Doppler distribution of the scattered or radiated waves from the particle resulting from relative motion between the particle and the transducer is measured at block .

The measured Doppler distribution is compared to distribution lookup tables at block . The lookup tables are generated block from the above analysis given the aperture or particle geometry. For example p x y z t can be determined from Equation 1 knowing P k k . The lookup tables can be generated at any point prior to the comparison step of block . The distribution in the lookup tables best matching the measured distribution is obtained at block . The particle geometry corresponding to the best matching lookup table distribution is obtained from the lookup table at block .

What have thus been described are systems and methods for inferring information about particle geometry. A transducer insonifies a particle and then measures the Doppler distribution of the scattered or radiated waves resulting from relative motion between the particle and the transducer . The measured Doppler distribution is compared to distribution lookup tables. The particle geometry for the distribution in the lookup table best matching the measured distribution is taken as the geometry of the insonified particle.

Obviously many modifications and variations of the present invention may become apparent in light of the above teachings. For example the system can include a separate transmitter and a separate receiver instead of the transducer being both a transmitter and receiver. Furthermore the processor can be incorporated into the transducer or vice versa.

Additionally the method can infer the particle geometry directly from the measured distribution without the use of lookup tables. As shown in phantom form in once the Doppler distribution is measured at block trial and error solutions for P 0 and the corresponding particle geometry can be obtained block from Equation 14 . However it is recognizable to those skilled in the art that such solutions can be computationally intense.

Still further the method can localize the particle shown in phantom in by adjusting the axis of the insonification of the particle block until the extent of the Doppler distribution is maximized at block . At block the amount of adjustment is directly inferred using Equation 12 . Upon determining the adjustment the particle geometry can be obtained as described previously blocks .

In light of the above it is therefore understood that within the scope of the appended claims the invention may be practiced otherwise than as specifically described.

