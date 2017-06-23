---

title: Joint signal processing across a plurality of line termination cards
abstract: In one embodiment, the line termination card includes a data output terminal configured to output a data sequence. The card further includes a vectoring entity configured to parse and encode the data sequence into frequency samples according to a carrier loading parameter, configured to scale the frequency samples into scaled frequency samples according to a carrier scaling parameter, and, configured to process the scaled frequency samples for crosstalk compensation. A controller is configured to adjust the carrier loading parameter and the carrier scaling parameter, and a forwarder is coupled to the data output terminal and to the controller. The forwarder is configured to forward the data sequence, the carrier loading parameter and the carrier scaling parameter towards a further line termination card.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09100506&OS=09100506&RS=09100506
owner: Alcatel Lucent
number: 09100506
owner_city: Boulogne-Billancourt
owner_country: FR
publication_date: 20100610
---
The present invention relates to joint signal processing for crosstalk compensation and more specifically to a line termination card for connecting subscriber devices through subscriber lines and operable to compensate for the induced crosstalk.

Crosstalk or inter channel interference is a major source of channel impairment for multiple Input multiple output MIMO communication systems such as Digital subscriber Line DSL communication systems.

As the demand for higher data rates increases DSL systems are evolving toward higher frequency bands wherein crosstalk between neighboring transmission lines that is to say transmission lines that are in close vicinity such as twisted copper pairs within a cable binder is more pronounced the higher frequency the more coupling .

A MIMO system can be described by the following linear model 1 wherein the N component complex vector X respectively Y denotes a discrete frequency representation of the symbols transmitted over respectively received from the N channels wherein the N component complex vector Z denotes additional noise present over the N channels such as alien interference thermal noise and Radio Frequency Interference RFI and wherein the N N complex matrix H is referred to as the channel matrix. The i j th component of the channel matrix H describes how the communication system produces a signal on the i th channel output in response to a symbol being transmitted to the j th channel input. The diagonal elements of the channel matrix describe direct channel coupling and the off diagonal elements of the channel matrix describe inter channel coupling.

Different strategies have been developed to mitigate crosstalk and to maximize effective throughput reach and line stability. These techniques are gradually evolving from static or dynamic spectral management techniques to multi user signal coordination 

One technique for reducing inter channel interference is joint signal precoding with precoding signals are passed together through a precoding matrix before being transmitted over the respective communication channels. The precoding matrix is such that the concatenation of the precoder and the communication channel results in little or no interference at the receivers.

However a typical DSL deployment practice is to choose termination ports in a random or first come first serve fashion. In most situations subscriber lines sharing the same cable binder may not be terminated at the same line termination card. This makes crosstalk compensation operations complicated ineffective or even impossible.

A known solution to this problem is to rearrange subscriber lines. Two known solutions are 1 to manually rearrange or groom subscriber lines in the field so that all lines sharing the same binder are properly terminated at the same line termination card and 2 to employ a sophisticated cross connect device between the subscriber lines and line termination ports so that the subscriber lines to termination ports mapping are properly managed. Solution 1 involves dispatching a technician in the field to reconfigure the wiring. Not only is this truck roll a costly operation but it also takes considerable time to complete the process. Solution 2 requires a high quality cross connect device. This technology is as of today still immature. It is either very expensive or introduces too much signal distortion thus limiting or even eliminating the expected gains of crosstalk compensation.

It is an object of the present invention to efficiently and inexpensively perform crosstalk compensation on a selected group of subscriber lines that are terminated at different line termination cards.

In accordance with a first embodiment of the invention a line termination card for connecting subscriber devices through subscriber lines comprises 

In accordance with another embodiment of the invention said vectoring entity is for further parsing and encoding a further data sequence into further frequency samples according to a further carrier loading parameter for scaling said further frequency samples into further scaled frequency samples according to a further carrier scaling parameter and for processing said further scaled frequency samples for crosstalk compensation 

and the line termination card further comprises a further forwarder coupled to said vectoring entity for receiving said further data sequence said further carrier loading parameter and said further carrier scaling parameter from said further line termination card.

The mappers and the precoder are merged into a single entity herein named a vectoring Entity VE and there are as many VEs per line termination card as there are groups of signals to be jointly processed or crosstalk compensation groups or vectoring groups or precoding groups on that line termination card. The unmapped data sequences are fed into the respective VEs according to their membership of a crosstalk compensation group. The data output terminals are coupled to the VE s through a forwarder. The forwarder selectively duplicates and transmits the data sequences to a collection of line termination cards which perform joint signal processing on line signals of the same crosstalk compensation group.

The carrier loading and scaling parameters are also forwarded so as the data sequences are correctly mapped into the frequency domain for accurate crosstalk compensation.

This innovative architecture greatly reduces the required communication throughput between line termination cards e.g. if complex values at the output of the mappers quantized with a sufficient number of bits were to be supplied to a centralized precoder for further precoding and still one may suffer some quantization loss making that solution nearly optimal.

This is achieved by grouping the mappers and the precoder into one single entity and inputting that entity with locally available data sequences as well as with data sequences from further line termination cards.

The same VE that is to say making use of the same precoding matrix or related to the same crosstalk compensation group being duplicated over multiple line termination cards the data sequences and related mapping information need only be forwarded once e.g. whereas complex values before and after precoding would have to be exchanged back and forth with one centralized precoder .

The data sequence as outputted by the data output terminal may refer for instance to the framed data as outputted by the Physical media specific Transmission convergence PMD TC layer at the reference point in the VDSL2 reference model described in G.993.2 recommendation entitled very High speed Digital subscriber Line Transceivers 2 VDSL2 published by the International Telecommunication union ITU in February 2006.

If crosstalk compensation is carried out on a subset of tones only e.g. higher frequency bands only then the part of the data sequence that is mapped on these tones is forwarded while the remaining part is not.

The carrier loading parameter may refer for instance to bit loading information such as determined during the initialization or operation of a data communication path over a subscriber line based on the measured signal to Noise Ratio SNR or may refer to a carrier or tone ordering table whereby carriers are sorted for mapping according to the measured noise and or further criteria.

The carrier scaling parameter may refer for instance to relative carrier gains as determined during the initialization or operation of a data communication path over a subscriber line based on the measured signal to Noise Ratio SNR or may refer to a transmit power spectral mask as configured over a subscriber line.

In accordance with another embodiment of the invention said data sequence or a part thereof is multicast based on its membership of a crosstalk compensation group.

crosstalk compensation groups and multicast groups are in one to one relationships and a line termination card subscribes to the appropriate multicast groups so as to be supplied with any data sequence to be jointly processed with the locally available data sequences.

Alternatively the data sequence is unicast to the appropriate line termination cards or broadcast to all the line termination cards.

The related carrier loading and scaling parameters can be advertised together with the data sequence as part of the same multicast or broadcast stream or sent apart through a dedicated channel.

The line termination card may form part of an access node such as a Digital subscriber Line Access Multiplexer DSLAM being located at a central location or at a remote location closer to subscriber premises.

The present invention also relates to a method for connecting subscriber devices through subscriber lines.

In accordance with the first embodiment of the invention the method comprises the steps of by a line termination card 

Embodiments of a method according to the invention correspond with the embodiments of a line termination card according to the invention.

There is seen in and a line termination card with emphasis on the outgoing and incoming data flows respectively.

The input terminals are drawn as solid triangles whereas the output terminals are drawn as hollow triangles. A terminal is herein meant to be a means for passing information or signal from one hardware or software entity to another being one or more hardware pins a function or procedure call an Application Programming Interface API a Remote Procedure call RPC etc.

In a preferred embodiment of the invention the line termination card is operable to terminate VDSL2 subscriber lines and it forms part of a DSLAM.

One or more data output terminals are coupled to input terminals of the VE depending on their group membership. The one or more data output terminals are also coupled to input terminals of the first forwarder for outputting data sequences towards one or more further line termination cards. One or more output terminals of the second forwarder are coupled to input terminals of the VE for inputting data sequences from one or more further line termination cards into the VE . Eventually the controller is coupled to the VE and to the first forwarder .

The input terminals Ito Iare coupled to respective ones of input terminals of the mappers to output terminals of the mappers to are coupled to respective ones of N input terminals of the precoder and N output terminals of the precoder are coupled to respective ones of the output terminals Oto O.

One or more control output terminals of the controller are coupled to control input terminals of the mappers and also to input terminals of the first forwarder . one or more output terminals of the second forwarder are coupled to control input terminals of the mappers . A control output terminal of the controller is further coupled to a control input terminal of the precoder .

The couplings between the data output terminals and the input terminals of the mappers between the control output terminals of the controller and the control input terminals of the mappers between the data output terminals and the input terminals of the first forwarder between the control output terminals of the controller and the input terminals of the first forwarder and between the output terminals of the second forwarder and the input terminals and the control input terminals of the mappers depends on the respective memberships of the crosstalk compensation groups as it will be set forth further in the description.

The data output terminals are adapted to output data sequences that are ready for mapping into the frequency domain. A data sequence herein refers to framed data as outputted by a PMD TC layer at the reference point in the VDSL2 reference model. Each data frame of the data sequence corresponds to one DMT symbol.

The mappers divide the incoming bit stream into small groups of bits where each group is assigned to modulate a specific carrier of the DMT symbol. Each group is further encoded by the trellis encoder optionally and eventually mapped to a constellation point in a constellation grid.

During initialization the receive PMD function shall calculate the numbers of bits or bit loading band the relative gains gto be used for every carrier k in the MEDLEY set based on the measured SNR of the carrier and specific system configuration settings. The receive PMD function shall also determine the tone ordering table that is to say the order in which the carriers are assigned bits. The calculated bits and gains and the tone ordering table shall be sent back to the transmit PMD function during the channel Analysis Exchange phase of the DSL path initialization.

Constellation points shall be scaled to normalize their average power to achieve a frequency dependent transmit PSD and to equalize the SNR margin over the carriers in use.

The scaling required to normalize the average power is dependent only on the size of the constellation. It is represented by the factor b . The gain adjuster gis used to equalize the SNR margin over the carriers in use. The PSD shaping mechanism is based on the so called tsscoefficients.

For carriers in the MEDLEY set each constellation point X Y corresponding to the complex value X jYat the output of the constellation mapper shall be scaled by the power normalization factor b the gain adjuster g and a frequency domain spectrum shaping coefficient tssto result in a complex number Z defined as 2 

The precoder is adapted to perform joint signal processing in the downstream direction i.e. from the central office towards the subscriber premises .

Signal precoding is achieved by jointly processing the transmitted symbols in the frequency domain so as to compensate for inter channel interference.

Precoding should ideally result in a transfer function matrix that preserves the direct channel transfer functions frequency equalization at the receive end compensates for the direct channel attenuation and phase shift and simultaneously zeroes all the crosstalk channel transfer functions. This is achieved by using the following precoding matrix 5 

The latter is a first order approximation that is valid if the amplitude of the crosstalk channel coefficients is small with respect to the amplitude of the direct channel coefficients which is a valid assumption in DSL deployments.

That is to say with precoding the received signals are not impaired by inter channel interference but only by alien noise.

Eventually the precoded frequency samples modulate the carriers of the DMT symbol using an Inverse Discrete Fourier Transform IDFT . After the IDFT the resulting symbol is cyclically extended and windowed converted into an analog signal and sent through the transmission medium.

The controller is adapted to control the operation of the mappers and the precoder more specifically the controller passes PMD communication parameters and more noticeably carrier loading and scaling parameters to the mappers and a precoding matrix to the precoder .

Carrier loading and scaling parameters for lines that terminate on the line termination card are made available by the controller whereas carrier loading and scaling parameters for lines that terminate on a further line termination card are retrieved from the further line termination card through the second forwarder .

Carrier loading parameters herein refer to bit loadings band a tone ordering table as determined by the PMD layer. Carrier scaling parameters herein refer to relative carrier gains gas determined by the PMD layer and possibly to a transmit power shaping mask i.e. the tsscoefficients as configured over a subscriber line.

The precoding matrix is determined according to estimates of the crosstalk channel transfer functions. The estimates are computed based on noise measurements from a subscriber device.

The first forwarder is adapted to supply further line termination cards with data sequences as outputted by the data output terminals as well as with the related carrier loading and scaling parameters for joint signal processing by the further line termination cards.

The second forwarder is adapted to receive data sequences as well as the related carrier loading and scaling parameters from a further line termination card for joint signal processing by the VE .

An output terminal of the first forwarder is coupled to an input terminal of a further second forwarder forming part of a further line termination card and an input terminal of the second forwarder is coupled to an output terminal of a further first forwarder forming part of a further line termination card.

The first forwarder and the second forwarder are built upon a communication facility such as an Ethernet switch fabric or a shared data bus or alike that connects the line termination cards to each other.

One or more data frames within the data sequences as outputted by the data output terminals are encapsulated into a format appropriate for further transmission towards one or more further line termination cards e.g. by appending a destination and source address identifying a source and destination line termination card respectively or by appending a multicast address identifying a particular crosstalk compensation group which the corresponding line termination cards shall listen to. The one or more data frames are next extracted thereat and further fed into a VE. Each data frame is identified by a DMT symbol index and by a line identifier to which the data frame relates.

Whereas data sequences are continuously duplicated and fed into the respective VEs the carrier loading and scaling parameters are only exchanged when their value is adjusted being upon initialization or by means of On Line Reconfiguration OLR commands.

An encoded data sequence is denoted as s wherein m denotes a data output terminal index ranging from 1 to M with M being lower than or equal to N and t denotes a DMT symbol index. After constellation mapping and scaling this data sequence yields a sequence of complex numbers Z which represent the frequency samples of the signal before precoding. The sequence of complex numbers Z is then passed through the precoder for crosstalk pre compensation thereby yielding a new sequence of complex numbers Z which represents the frequency samples of the signal after precoding and before modulation by an IDFT unit.

The scaling factors could be directly integrated into the precoder matrix s coefficients so as to reduce the number of required arithmetic operations and the quantization loss in which case the unscaled frequency samples are directly passed to the precoder for further scaling and precoding.

The carrier loading information and carrier scaling information for parsing mapping and scaling the data sequence s are denoted as CLm and CSm respectively.

There is seen in the line termination card and a further line termination card that accommodates a similar VE with N input terminals to I to I and N output terminals O to O . The controllers and carrier loading and scaling information have been purposely omitted in in order to not clutter the drawing.

As an illustrative embodiment three data output terminals and forming part of three encoders ENC  ENC m and ENC M respectively and outputting three data sequences s s and s respectively are shown. The encoders ENC  and ENC M form part of the line termination card and the outputted data sequences s and s are transmitted over subscriber lines Land L not shown connected to the line termination card . The encoder ENC m forms part of the further line termination card and the outputted data sequence s is transmitted over a subscriber line L not shown connected to the further line termination card . The lines L Lm and LM share the same cable binder and form part of the same crosstalk compensation group.

The data output terminals and are coupled to the input terminals Iand Iof the VE respectively and are coupled via the first forwarder to the input terminals I and I of the VE respectively. The data output terminal is coupled to the input terminals I of the VE and is coupled via the second forwarder to the input terminal Iof the VE n denoting an input terminal index of the VE ranging from 1 to N.

The output terminals Oand Oof the VE are coupled to IDFT units IDFT  and IDFT M respectively whereas the output terminal Oof the VE is left open such a terminal is terminated with a cross in . The output terminal O of the VE is coupled to an IDFT unit IDFT m whereas the output terminal O and O of the VE are left open. The IDFT units IDFT  IDFT m and IDFT M are further coupled to the lines L Lm and LM respectively.

P which is a N N square matrix denotes a precoding matrix for pre compensating the crosstalk induced over the lines L Lm and LM and is used by both the VEs and . The precoding matrix P is obtained from e.g. a crosstalk estimating unit not shown .

The data sequences s and s are forwarded with the carrier loading parameters CLand CLand the carrier scaling parameters CSand CStowards the VE by the first forwarder . More specifically the data sequence s is forwarded towards the input terminal of the VE and the carrier loading and scaling parameters CLand CSare forwarded towards the corresponding input control terminal of the VE . The data sequence s is forwarded towards the input terminal I of the VE and the carrier loading and scaling parameters CLand CSare forwarded towards the corresponding input control terminal of the VE .

Similarly the data sequence s is forwarded together with the carrier loading parameter CLand the carrier scaling parameter CStowards the VE by the second forwarder . more specifically the data sequence s is forwarded towards the input terminal Iof the VE and the carrier loading and scaling information CLand CSare forwarded towards the corresponding input control terminal of the VE .

The signals forming part of the same crosstalk compensation group need to be aligned at the DMT symbol level for them to be jointly processed. Consequently a common timing reference shall be supplied e.g. by a central clock distribution unit to each line termination card and the operation of each transceiver shall be synchronized with this common timing reference.

Signal forwarding between line termination cards may involve one or more intermediary communication units for forwarding unmapped data sequences and or related carrier loading and scaling parameters.

As an exemplary embodiment signal forwarding together with crosstalk channel estimation line management and timing and synchronization functions could be merged into one or more crosstalk compensation cards. This card may be installed in a specific slot e.g. the slot provided for the redundant network termination card or any other slot with the appropriate connectivity so that signals from any subscriber line on any line termination card can be sent receive to from this card. The crosstalk compensation card maintains information of all the crosstalk compensation groups and depending on the memberships selectively relays signals to a collection of line termination cards which perform joint signal processing on line signals in this group.

It is to be noticed that the term comprising also used in the claims should not be interpreted as being restricted to the means listed thereafter. Thus the scope of the expression a device comprising means A and B should not be limited to devices consisting only of components A and B. It means that with respect to the invention the relevant components of the device are A and B.

It is to be further noticed that the term coupled also used in the claims should not be interpreted as being restricted to direct connections only. Thus the scope of the expression a device A coupled to a device B should not be limited to devices or systems wherein an output of device A is directly connected to an input of device B and or vice versa. It means that there exists a path between an output of A and an input of B and or vice versa which may be a path including other devices or means.

The description and drawings merely illustrate the principles of the invention. It will thus be appreciated that those skilled in the art will be able to devise various arrangements that although not explicitly described or shown herein embody the principles of the invention and are included within its spirit and scope. Furthermore all examples recited herein are principally intended expressly to be only for pedagogical purposes to aid the reader in understanding the principles of the invention and the concepts contributed by the inventor s to furthering the art and are to be construed as being without limitation to such specifically recited examples and conditions. Moreover all statements herein reciting principles aspects and embodiments of the invention as well as specific examples thereof are intended to encompass equivalents thereof.

The functions of the various elements shown in the figures may be provided through the use of dedicated hardware as well as hardware capable of executing software in association with appropriate software. when provided by a processor the functions may be provided by a single dedicated processor by a single shared processor or by a plurality of individual processors some of which may be shared. moreover a processor should not be construed to refer exclusively to hardware capable of executing software and may implicitly include without limitation digital signal processor DSP hardware network processor application specific integrated circuit ASIC field programmable gate array FPGA etc. Other hardware conventional and or custom such as read only memory ROM random access memory RAM and non volatile storage may also be included.

