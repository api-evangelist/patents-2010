---

title: Phased array antenna system with intermodulation beam nulling
abstract: A phased array antenna system with intermodulation beam nulling device includes nulling phase shifters.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08643543&OS=08643543&RS=08643543
owner: The Aerospace Corporation
number: 08643543
owner_city: El Segundo
owner_country: US
publication_date: 20100910
---
This invention was made with government support under Contract No. FA8802 04 C 0001 awarded by the Department of the Air Force. The government has certain rights in the invention.

The present invention relates to improving transmitted signal quality in an active phased array antenna utilizing solid state power amplifiers transmitting two or more fundamental communications beams. In particular selected intermodulation beams arising from nonlinear amplifier operation are nulled to improve signal quality.

Active phased array antennas include a plurality of radiators driven by respective amplifiers. shows a prior art active phased antenna . The antenna has radiators located at the intersections of lines of a corresponding x y rectangular grid. Radiators may be located in the grid by reference to an x y coordinate such as or . This two coordinate referencing system is used in some antenna equations. Another coordinate referencing system uses one coordinate each element being sequentially numbered. For example in a 3 3 array element becomes element and element becomes element . This referencing system is used in some antenna equations.

As used herein the term processor refers to a device for processing information. In particular digital processors such as microprocessors and other digital processing devices are included. Various processor embodiments include one or more processors. And some processor embodiments include one or more memory device s such as semiconductor and or hard disc drive memory devices and input output device s such as bus communications parallel communications and serial communications devices.

Beam forming section inputs include a plurality of signals and their related angles . For each signal S Stwo angles commanded elevation and azimuth determine the direction of the beam carrying the signal and therefore the intended receiver of the signal. For example a first fundamental beam might be directed to a receiver in a first city at the angle pair and a second fundamental beam might be directed to another receiver in another city at the angle pair . Manipulating the direction of a communication beam is sometimes referred to as steering the beam.

Beam forming entails creation of a phase front for each beam that is normal to the desired direction of the beam. These phase fronts are created by appropriately shifting the phases of the incoming signals S Sin beam forming elements . Each one of i antenna beam forming elements includes steering phase shifters PS PSthat create corresponding shifted signals S S. In various embodiments the phase shifters include one or both of digital and analog phase shifters.

Phase shifts Z Zare applied to the signals S Sto create shifted signals S S. In an embodiment the phase shifts are calculated within the fundamental beam steering processor . And in an embodiment these applied phase shifts are functions of uniform progressive phases as shown in equations 1a b below. Equation 1a Equation 1b

As shown in equations 2a d below the uniform progressive phases x are determined by the commanded beam angle pairs and .

Phase shifter outputs Sand Sare combined and amplified in the ifeed chain element that includes a signal combiner and a solid state amplifier . The signal combiner is coupled to the input signals S Sand its output is amplified in the amplifier. The iradiator element is coupled to the amplifier via an amplifier output .

A phased array antenna system includes phase shifters for nulling selected intermodulation beams. In an embodiment a nulling section is interposed between a beam forming section and a feed chain section and an antenna has a plurality of radiators each radiator being coupled to a respective amplifier in the feed chain section. Each amplifier is coupled to a respective nulling phase shifter in the nulling section and each nulling phase shifter is coupled to a respective steering phase shifter in the beam forming section. One or more processors are for activating the phase shifters. The phased array antenna system is operative to simultaneously transmit a plurality of signals to respective locations.

In an embodiment the phased array antenna system includes one or more processors for calculating directivity patterns and one or more memory devices for storing calculated directivity patterns. A signal sampler is for sampling fundamental and intermodulation forward and reflected traveling wave signal levels at the input of each radiator and one or more processors are for updating the stored directivity patterns in accordance with the sample values.

In an embodiment a single processor is used. And in an embodiment the beam forming section includes a processor and the nulling section includes a processor.

The disclosure provided in the following pages describes examples of some embodiments of the invention. The designs figures and descriptions are non limiting examples of the embodiments they disclose. For example other embodiments of the disclosed device and or method may or may not include the features described herein. Moreover disclosed advantages and benefits may apply only to certain embodiments of the invention and should not be used to limit the disclosed invention.

As used herein the term coupled includes direct and indirect connections. Moreover where first and second devices are coupled other devices including active devices may be interposed between them.

A nulling section incorporating i nulling elements is coupled with commanded angle inputs . Signals with an applied phase shift for beam steering are outputs of the beam forming section and are coupled to the nulling section . Nulling section outputs are coupled with a feed chain section incorporating i feed chain elements . The feed chain section is coupled with i radiators of an antenna array .

A comparison of shows that present invention improves over the prior art by adding a nulling section to an active phased array antenna system A.

During operation of the invention s nulling function attenuators AT ATare used to equalize radiator amplitudes by applying suitable attenuations A A A A. . . A A where M represents the number of elements in the array and nulling phase shifters PN PNare used to apply a nulling phase distribution. In various embodiments the phase shifters include one or both of digital and analog phase shifters. Because it is not always beneficial to operate this nulling functionality embodiments of the invention adapt by selectively operating the nulling function.

When the nulling function is not in operation a attenuators AT ATapply a uniform attenuation to signals such that A A . . . A A A . . . A 0 and b nulling phase shifters PN PNapply a uniform phase distribution to signals such that . . . . . . 0. Adaptive functionality is discussed further below after operation of the nulling phase shifters has been described.

In the nulling section the once shifted signals S Sare attenuated by respective attenuators AT ATto equalize their levels. Nulling phase shifters PN PNare provided to process the attenuated signals creating twice shifted signals S S. One or more processors perform these functions. In an embodiment an intermodulation beam nulling processor is coupled to the commanded angle signals and provides a attenuating outputs A Acoupled to respective attenuators AT ATand b phase shifting outputs coupled to respective phase shifters PN PN.

Nulling unwanted intermodulation beams IM beam or IMB entails applying a nulling phase distribution to signals passing through the nulling section . The nulling phase distribution shifts the phases of all of the signals S Sby a nulling angle with a magnitude of 90 N degrees where N is the order of the intermodulation beam to be nulled. See the appendix to this specification for further explanation of these nulling phase shifts.

Referring to as the nulling phase change for the usignal and the ith array element in an exemplary 3 3 phased array antenna the nulling phase distribution in degrees for the first signal is below.

In some embodiments a single set of phase shifters applies both the steering and the nulling phase shifts. In these embodiments the steering phase shifts Z Zare added to the respective nulling phase shifts and the combined shifts are applied to respective phase shifters. For example the phase shifts can be combined in a single processor carrying out the functions of the fundamental beam steering processor and the intermodulation beam nulling processor .

Turning now to the question of whether nulling phase distributions should be applied a means for comparing the attenuation of fundamental beams undesirable and the attenuation of intermodulation beams desirable is required. For example if application of the nulling phase distribution increases the directivity of selected intermodulation beam s while the corresponding fundamental beam is little changed the application is detrimental.

As shown in Section 2.0 of the appendix the directivity D of a beam depends on the complex amplitude and phase excitation of the mnelement designated I elevation and azimuth angles and the spacing between rows dand columns dof the phased array. In particular the peak directivity of the fundamental beams can be expressed as functions of these variables. 1 Equation 3a 2 Equation 3b

The peak directivity of the intermodulation beams of a selected order N also depends on these variables. In particular the values of progressive phases corresponding to an Norder intermodulation beam are calculated as indicated below.

Peak directivity of the intermodulation beams is calculated using the directivity equation discussed above. 1 Equation 6a 2 Equation 6b

Directivities before and after application of the nulling phase distribution can now be calculated and compared.

Simulations indicate in a 14 14 array with analog phase shifters PN PNthe directivity of any odd order intermodulation beam can be degraded by about 35 dB at a cost of fundamental beam degradation of less than 0.25 dB. Notably using present day technology digital phase shifter performance can be expected to fall short of that of analog devices owing to introduction of analog digital conversion quantization errors.

In some embodiments a collection of directivity patterns P are stored in a memory device such as a semiconductor or disc drive memory device. The value of P is the directivity of a particular beam. In some embodiments the memory device is a part of the intermodulation beam nulling computer and in some embodiments the memory device is a part of the beam forming section .

Pre calculation and storage of directivity patterns avoids the need to calculate directivities after angle commands are given. Among other things pre calculation and storage saves time and reduces processor requirements. Notably where commanded angles differ from stored angles a selection methodology is required such as selection of the closest stored angle data and or interpolation of the stored angle data to fit the commanded angles.

As persons of ordinary skill in the art will appreciate stored directivity patterns P can be referenced in different ways. For example the stored patterns can be stored in a multidimensional matrix such that where

In some embodiments adaptation utilizing radiator feedback updates pattern values P to account for radiator element changes such as radiator degradation.

Radiator degradation modifies the radiator s complex excitation coefficient I. As shown above a radiator s modified excitation coefficient changes values of directivity D that were earlier stored as pattern values P. In essence actual pattern values change as radiators degrade and stored pattern values are updated to maintain the performance of the nulling system.

If performance is not improved by applying a checkerboard nulling phase distribution flow passes from decision block to attenuation block where a uniform attenuation and phase distribution is applied to the signals where A A . . . A A A . . . A 0 and . . . . . . 0.

If there is no significant change then the process A is ready to accept another set of commanded angles . If there is a significant change control passes to the pattern update process which updates the antenna directivity patterns in read write memory containing fundamental and intermodulation antenna patterns using the directivity equation D and the new signal levels P j k .

After pattern updating is completed the process A is ready to accept another set of commanded angles .

While various embodiments of the present invention have been described above it should be understood that they have been presented by way of example only and not limitation. It will be apparent to those skilled in the art that various changes in the form and details can be made without departing from the spirit and scope of the invention. As such the breadth and scope of the present invention should not be limited by the above described exemplary embodiments but should be defined only in accordance with the following claims and equivalents thereof.

