---

title: Superconducting digital mixer
abstract: Digital mixers which permit mixing of asynchronous signals may be constructed of Rapid Single Flux Quantum (RSFQ) logic elements. The logic elements may include an RSFQ non-destructive readout cell (NDRO), an RSFQ D flip-flop, an RSFQ XOR circuit, and an RSFQ T flip-flop. A binary tree arrangement of T flip-flops can be used to provide in-phase and quadrature phase-divided replicas of a reference signal. The mixing elements can be either an XOR circuit, a dual port NDRO circuit functioning as a multiplexer or an RS type NDRO functioning as an AND gate. The RSFQ logic elements utilize Josephson junctions which operate in superconducting temperature domains.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08050648&OS=08050648&RS=08050648
owner: Hypres, Inc.
number: 08050648
owner_city: Elmsford
owner_country: US
publication_date: 20100316
---
The present application is a continuation of U.S. application Ser. No. 11 243 019 filed Oct. 4 2005 now U.S. Pat. No. 7 680 474 the entirety of which is expressly incorporated herein by reference.

This invention was made with Government support under Contract Numbers N00014 02 C 0005 N00014 03 C 0082 and N00014 03 C 0370 awarded by the Department of the Navy. The Government has certain rights in the invention.

The invention described herein relates to the field of superconductivity and more specifically relates to circuits and techniques for implementing digital quadrature mixers using Josephson junctions.

Josephson junctions are quantum mechanical circuit elements of superconducting devices. The Josephson effect in particular results from two superconductors acting to preserve long range order across a barrier such as an insulating barrier. With a thin enough barrier the phase of the electron wave function in one superconductor maintains a fixed relationship with the phase of the wave function in another superconductor. This linking up of phases is called phase coherence.

A Josephson junction is the interface between two superconducting materials separated by a non superconducting barrier. A current may flow freely within the superconductors but the barrier prevents the current from flowing freely between them. However a supercurrent may tunnel through the barrier depending on the quantum phase of the superconductors. The amount of supercurrent that may tunnel through the barriers is restricted by the size and substance of the barrier. The maximum value the supercurrent may obtain is called a critical current of the Josephson junction.

Josephson junctions have two basic electrical properties. The first is that the junctions have inductive reactance. That is similar to inductors the voltage difference across the junction is related to the time rate of change of the current. The second is that a constant voltage across the junction will produce an oscillating current through the barrier and vice versa. Thus Josephson junctions convert a direct current voltage to an alternating current.

A family of logic memory devices were proposed using Josephson junctions the IEEE Transactions on Applied Superconductivity Volume 1 Number 1 March 1991 by K. K. Likharev and V. K. Semenov in an article entitled RSFQ Logic Memory Family A New Josephson junction Technology For Sub Terahertz Clock Frequency Digital Systems. That article is hereby incorporated by reference in its entirety into specification of this application.

RSFQ circuits are widely recognized as the fastest digital circuits in any electronic technology and this is also true of RSFQ digital mixers. The digital mixers described in the present invention constitute the first practical circuits for the implementation of digital mixers in a complete RSFQ digital receiver system and have been demonstrated for clock speeds up to 40 GHz.

Prior art attempts at producing digital mixers in the superconducting domain required synchronism between an incoming signal and a reference signal.

The invention described herein is related to circuits and techniques for implementing digital mixers utilizing Josephson junction technology which don t require synchronism between the incoming signal and a reference signal.

The purpose of the invention is to provide a digital quadrature mixer which overcomes the problems of the prior art.

An important component of any digital receiver is a digital I Q Mixer for converting narrowband about 5 MHz signals down from a few GHz. To achieve this goal with maximum efficiency the invention uses a circuit that is similar in principle to the Gilbert quadrature mixer. See article by B. Gilbert A Precise Four Quadrant Multiplier With Sub nanosecond Response IEEE. J. Solid State Circuits Vol. SC 3 pp. 365 373 December 1968. The basic idea of this mixer is to use square waves as a local oscillator signal instead of sine waves. The mathematical representation of a square wave is G t sign sin t where t is a local oscillator frequency. The digital version of such a mixer is comparably easy to implement in RSFQ in case of single bit coding such as at the output of a delta sigma modulator.

The first implementation of a square wave digital mixer in RSFQ is shown in . The right side of the device on the block diagram serves as a single bit square wave generator with quadrature outputs. Although is shown as a two channel I Q Mixer the principles of the invention apply to a single channel mixer as well. As shown the binary tree of resettable T flip flops creates two I and Q local oscillator signals with 90 degree relative phase shift. The T flip flops control RS type NDRO cells which in turn create digital square waves turning on and off a stream of SFQ pulses. A modulated signal gets mixed with 90 degree. shifted square waves in XOR cells producing I channel and Q channel output products. An RS type NDRO cell and a T flip flop is used instead of a T type NDRO cell in order to avoid a possible collision between the NDRO read out pulse and reference pulse. Such a collision may cause a wrong phase shift between I and Q local oscillator signals. If such a problem occurs the only way to correct it is by applying a RESET signal and one would not want to do that too often. Despite its simple design this version of the mixer has issues with timing limiting its performance.

To avoid this problem we have designed a second novel mixer performing single bit stream XOR multiplication . In this case we use the simple fact that A XOR 0 A and A XOR 1 . A Rapid Single Flux Quantum RSFQ D flip flop with complementary outputs DFFC schematics and optimal parameters are in Kirichenko et al. A 4 bit Single Flux Quantum Decoder IEEE Transactions on Applied Superconductivity Vol. 5 No. 2 p. 2857 June 1995 converts the modulated signal into a single bit data stream along with its inverted complementary representation. Multiplexing direct and inverted data outputs to the proper channel it performs digital Quadrature signal down conversion. After the modulated signal passes through a D flip flop with complementary outputs DFFC it becomes asynchronous. Multiplexing direct and inverted data outputs to the proper channel we effectively perform digital I Q signal down conversion. The multiplexing is done by two multiplexer cells controlled by the same T flip flop binary tree as in providing a 90 degree phase shift between I and Q channels. Again this circuit can be applied to single channel mixing as well as to I Q quadrature mixing.

The multiplexer cell is shown in . This cell basically comprises a dual port NDRO cell. From this cell a designer can build either a demultiplexer by merging inputs A and B or a multiplexer by merging outputs A and B. See article by Kirichenko et al. A 4 bit Single Flux Quantum decoder IEEE Transactions on Applied Superconductivity Vol. 5 No. 2 p. 2857 June 1995.

We have designed and fabricated the version of the digital I Q Mixer using the standard HYPRES 1 kA cmfabrication process. The same design was also converted to the standard HYPRES 4.5 kA cmfabrication process.

The multiplexing is done by two 2 1 RSFQ switches. The basic switch cell shown in comprises a dual port RSFQ Non Destructive Read Out NDRO cell with merged outputs i.e. electrically connected outputs . Applying an SFQ pulse to the input Set A causes the switch to connect input terminal In A to the output terminal Out A and disconnect terminal In B . Applying an SFQ pulse to the input Set B causes the switch to connect input terminal In B to the output terminal Out B and disconnect terminal In A . The optimized parameters for the cell in are in Table 1.

Both switches are controlled by a resettable T flip flip binary tree. See description of T1 cell in S. Polonsky et al. Single Flux Quantum T flip flop and its possible applications IEEE trans. On Appl. Supercond. vol. 4 p. 9 1994 for the schematics and optimal parameters of the resettable TFF. The TFF tree converts a periodic reference signal into a control sequence of the switches effectively creating two 90 degree phase shifted Local Oscillator square wave signals of a half reference signal frequency.

Each of the three mixers described heretofore have their advantages and drawbacks. The circuit shown in employing an AND operation has a poor signal to noise ratio because of a DC component in the local oscillator. However it is feasible for a multi bit implementation.

The digital I Q Mixer employing XOR operation shown in has good gain and a good signal to noise ratio but there is no obvious multi bit implementation.

The streaming I Q Mixer shown in takes care of timing and synchronization issues but may be hard to design for multi bit data streams. Thus each of the three mixers described is preferred for a particular application.

The XOR mixer shown in utilizes a T flip flop an RS type NDRO an XOR cell and a D flip flop single output .

The streaming I Q Mixer shown in utilizes the multiplexer shown in and a D flip flop with complementary outputs.

The AND gate mixer shown in utilizes T flip flops a multiplexer such as that shown in and a D flip flop with complementary outputs. Each of these elements utilized to construct the mixers described so far will now be described in more detail.

The normalized Personal Superconducting Circuit ANalayzer Polonsky S. Shevchenko P. Kirichenko A. Zinoviev D. Rylyakoy A. PSCAN 96 New Software for Simulation and Optimization of Complex RSFQ Circuits IEEE Transactions on Applied Superconductivity Volume 7 Issue 2 June 1997 Page s 2685 2689 PSCAN units are normalized to 125 pA for junction critical currents in and bias current values I and to 2.63 pA for inductance values L.

This cell functions as a Non Destructive Read Out with a single bit memory. One can change the state of the NDRO by applying the Reset or Set inputs. If the cell is in state 1 then the Read input pulse goes to the Output. If the cell is in state 0 then the Read input pulse is prevented from going to the Output.

This RSFQ logic circuit functions as a multiplexer or demultiplexer combining two input pulse streams into a single output stream or conversely. This was described in the U.S. Pat. No. 5 982 219 invented by A. Kirichenko 1999 .

The normalized PSCAN values for the circuit of are as follows L1 4.51 L2 1.77 L3 0.37 L4 0.60 L5 0.30 L6 0.62 LC1 1.14 LC2 0.75.

Turning to Raw analog RF input is applied to an analog to digital convener ADC preferably to an oversampled delta modulator or delta sigma modulator. The output of the ADC is passed to a D flip flop with complementary outputs and then to a multiplexer MUX. The output of the multiplexer is then passed to a chain of T flip flops TFF1 TFF13 in this example the output Digital Output is taken from the last T flip flop. The Digital Output is passed to another D flip flop with complementary outputs to control the phase shift imported to a frequency reference by a string of alternating inverters and T flip flop TFF 4 cells. The output of the last T flip flop connects to the set reset inputs of the multiplexer of the streaming mixer.

While various embodiments of the present invention have been illustrated herein in detail it should be apparent that modifications and adaptations to those embodiments may occur to those skilled in the art without departing from the scope of the present invention as set forth in the following claims.

