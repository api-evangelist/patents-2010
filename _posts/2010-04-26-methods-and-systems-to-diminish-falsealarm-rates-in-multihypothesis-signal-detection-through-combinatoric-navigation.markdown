---

title: Methods and systems to diminish false-alarm rates in multi-hypothesis signal detection through combinatoric navigation
abstract: Methods and systems to detect navigation signals, including to identify up to multiple range-Doppler hypotheses from each of j range-Doppler correlation grids based on a relatively low first threshold, generate navigation solutions from combinatorial sets of k of the identified hypotheses, evaluate the navigation solutions to identify plausible solutions, iteratively and combinatorially augment the plausible solutions with additional hypotheses from grids that are not represented in the corresponding k-hypotheses based navigation solutions, replace plausible solutions with corresponding augmented plausible solutions when appropriate, and select one of a plurality of plausible solutions as a best plausible solution, j and k being positive integers. Where a grid energy peak exceeds a second threshold, a corresponding hypothesis may be identified as a sole hypothesis for the corresponding navigation signal. The relatively low first threshold permits detection of weaker signals. Subsequent evaluations effectively transform a per-navigation-signal false alarm rate to per-navigation-solution false alarm rate.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08325086&OS=08325086&RS=08325086
owner: The Johns Hopkins University
number: 08325086
owner_city: Baltimore
owner_country: US
publication_date: 20100426
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 172 267 filed on Apr. 24 2009 which is incorporated herein by reference in its entirety.

This invention was made with U.S. Government support under contract number 2004 H009000 000. The U.S. Government has certain rights in the invention.

Methods and systems are disclosed herein related to detection of navigation signals based on correlations amongst the navigation signals and to computation of a navigation solution from the detected navigation signals.

In satellite based navigation a navigation solution is computed from navigation signals received from multiple navigation satellites. A received navigation signal may have a relatively low signal to noise ratio which may make it difficult to distinguish the signal from noise. Additionally motion of a receiver or a satellite may impart a Doppler frequency shift to the signal. Atmospheric and or other environmental conditions may impart propagation delay to the signal. These issues may impact detection accuracy of the navigation signal which may impact accuracy of a navigation solution.

In a deep fade global navigation satellite system GNSS such as a global positioning system GPS signals received from navigation satellites may be detected along two dimensions delay or range and frequency or Doppler shift . For each received signal correlation energies of various range Doppler hypotheses may be calculated and assembled into a range Doppler correlation grid.

A navigation signal may be detected from a range Doppler correlation grid by identifying the range Doppler hypothesis having the highest grid energy and comparing the highest grid energy to a threshold. The threshold may be set sufficiently high to minimize false alarms. If the maximum grid energy is greater than the threshold the corresponding range Doppler hypothesis may be considered valid. Navigation signals received from other satellites may be detected in a similar fashion. Where a range Doppler hypothesis greater than the threshold is identified from each of multiple range Doppler correlation grids a navigation solution may be calculated using a least squares method.

As described above each of the multiple signals is individually detected based on a relatively high per signal threshold. This may preclude detection of a signal from one or more satellites which may reduce the accuracy of a navigation solution or preclude determination of a navigation solution.

Disclosed herein are methods and systems to detect multiple navigation signals based on correlations performed across the multiple navigation signals.

A range Doppler correlation grid may be generated for each of multiple received navigation signals. Energy peaks of the grids may be compared to a relatively low first threshold to identify up to multiple range Doppler hypotheses per grid. The first threshold may be less than a conventional per signal or per grid false alarm threshold.

The relatively low signal detection threshold permits detection of weaker signals. Subsequent evaluations to identify plausible and a most plausible navigation solution effectively transform a per navigation signal false alarm rate to per navigation solution false alarm rate.

Where a grid energy peak exceeds a second threshold that is higher than the first threshold a corresponding hypothesis may be identified as a sole hypothesis for the corresponding navigation signal.

At least one hypothesis may be identified from each of j grids where j may be less than a total number of received navigation signals.

Multiple navigation solutions may be computed from corresponding sets of identified hypotheses each set including one hypothesis from each of k of the j grids where k is less than or equal to j. The sets of k hypotheses may be generated combinatorially to cover all or substantially all possible combinations of k identified hypotheses.

The k hypotheses based navigation solutions may be evaluated to identify one or more plausible navigation solutions. The evaluations may include determining an integrity measure with respect to each of the navigation solutions.

Where hypotheses are identified from more than k of the range Doppler correlation grids where j is greater than k a k hypotheses based plausible navigation solution may be iteratively augmented and evaluated with respect to hypotheses of grids not represented in the k hypotheses based plausible navigation solution. The k hypotheses based plausible navigation solution may be replaced with the augmented navigation solution based on the corresponding evaluations and the iterative augmentation and evaluation may continue with respect to the augmented navigation solution. Augmentation and testing may be performed with respect to each k hypotheses based plausible navigation solution and may be performed with respect to all or substantially all possible combinations of hypotheses of corresponding unrepresented grids.

Where multiple plausible navigation solutions are identified a most plausible navigation solution may be selected based on the corresponding evaluations.

Methods and systems disclosed herein may be referred to herein as vector acquisition methods and systems.

Methods and systems disclosed herein may be implemented to simultaneously detect a set of navigation signals and to simultaneously determine the set of navigation signals and a corresponding navigation solution.

Methods and systems disclosed herein and or portions thereof may be implemented for example in relatively weak signal and or fade prone environments such as a deep fade GNSS signal acquisition environment which may include cellular telephone based navigation environments and automobile based navigation environments.

In the drawings the leftmost digit s of a reference number identifies the drawing in which the reference number first appears.

At a range Doppler correlation grid is generated for each of multiple navigation signals to map energies of the signals with respect to potential delay times or ranges and with respect to potential Doppler shifts.

Range and Doppler values of a point within grid represent a potential time delay and Doppler shift of the signal respectively and are referred to herein as a range Doppler hypothesis of the signal.

At in range Doppler hypotheses having grid energy levels that meet a first threshold are identified from at least a subset of the range Doppler grids. A range Doppler correlation grid may include zero or more energy peaks that meet the first threshold.

In grid includes energy peaks and . Coordinate sets and and and and identify range Doppler and energy values of corresponding peaks and . The range and Doppler values represent corresponding range Doppler hypotheses of the energy peaks.

In the identifying at may include identifying only one range Doppler hypothesis from a range Doppler correlation grid when the energy level of the one range Doppler hypothesis meets a second threshold that is greater than the first threshold such as described below with respect to .

Where multiple energy peaks exceed second threshold second threshold may be ignored and all energy peaks that meet first threshold may be identified at . Alternatively a highest one of the peaks may be identified at .

At of navigation solutions are computed for multiple sets of the identified range Doppler hypotheses wherein each set includes one hypothesis from each of a plurality of grids. The navigation solutions may be computed in accordance with a least squares technique.

The evaluating at may include evaluating a reasonableness of a navigation solution. Reasonableness may be evaluated with respect to one or more of a residual of the navigation solution measurements associated the navigation solution such as range pseudo range and Doppler measurements and states associated with the navigation solution such as position velocity and clock error. Example evaluation techniques are disclosed further below.

Where multiple plausible navigation solutions are identified at a most plausible one of the plausible navigation solutions may be selected at .

The most plausible navigation solution may be output such as to a system which may include one or more of a display a computational system a communication system and a storage system. The most plausible navigation solution may be utilized for one or more of location position determination tracking and guidance.

Navigation solutions may be computed from k range Doppler hypotheses corresponding to k navigation signals wherein k is a positive integer. k may represent a minimum or desired number of navigation signals to compute a navigation solution and may be equal to for example and without limitation 4 5 or 6 as is well known. For a GPS application k may be equal to 5. Where elevation is known k may be equal to four. Methods and systems disclosed herein are not however limited to these examples.

A number of j range Doppler correlation grids for which an energy peak exceeds the first threshold may be equal to or greater than k such as illustrated below with respect .

At range Doppler hypotheses having grid energies that meet a first threshold are identified from j of the range Doppler grids.

In system includes a range Doppler correlation grid generator and threshold detector to generate range Doppler correlation grids from corresponding received navigation signals and to identify energy peaks that meet the first threshold. Where a range Doppler correlation grid does not include an energy peek that meets the first threshold no hypothesis is output by grid generator and threshold detector .

In identified range Doppler hypotheses include hypotheses through including one hypothesis from each of grids and and multiple hypotheses from each of grids and . No hypotheses are identified from grids and .

At a k hypothesis based navigation solution is computed for each of a plurality of sets of k identified hypothesis. The sets of k hypotheses may be selected so that no set includes more than one hypothesis from a grid. An example is provided below for with respect to for k 5.

In system includes a combinatorial hypothesis set generator to generate multiple sets of various combinations of k hypotheses.

System further includes a navigation solution generator to compute a k hypothesis based navigation solution for each set of k hypotheses.

At in the k hypotheses based navigation solutions are evaluated to identify one or more k hypotheses based plausible navigation solutions.

In system includes a navigation solution evaluator to evaluate the k hypotheses based plausible navigation solutions and to identify one or more of the k hypotheses based plausible navigation solutions as plausible navigation solutions .

Where multiple plausible k hypotheses based navigation solutions are identified at a most plausible one of the k hypotheses based plausible navigation solutions may be selected at . Alternatively one or more k hypotheses based plausible navigation solutions may be further processed and evaluated such as described below with respect to and .

Where more than k grids have an energy peak that exceeds the first threshold i.e. j k such as in a k hypotheses based plausible navigation solution may be augmented and tested with one or more additional hypotheses selected from one or more of the j grids that are not represented within the plausible navigation solution . For example where a plausible navigation solution is computed from highlighted hypotheses and the navigation solution may be augmented and tested hypotheses from grids and such as described below with respect to and .

System includes range Doppler grid generator and threshold detector and selector described above with respect to . System further includes a combinatorial hypotheses set generator a navigation solution generator and a navigation solution evaluator which may be configured to perform functions described above with respect to elements and respectively in and to perform additional functions described below.

Method is described below with respect to system . Method is not however limited to the example of system .

At through of one or more k hypothesis based navigation solutions are identified as plausible navigation solutions such as described above with respect to through in .

At where j is not greater than k and where multiple plausible k hypotheses based navigation solutions are identified at processing proceeds to described below.

At for each plausible navigation solution one or more augmented navigation solutions are computed each from a set that includes the k hypotheses from which the plausible navigation solution is computed and one or more additional hypotheses each selected from one of the j grids not represented in the k hypotheses.

Where a grid includes multiple identified hypotheses multiple corresponding augmented navigation solutions may be computed one for each of the identified hypotheses.

The computing of an augmented navigation solution at may be performed for each j grid not represented in the corresponding plausible navigation solution.

Augmented navigation solutions may be computed from all or substantially all potential combinations of identified hypotheses valid for a given plausible navigation solution.

At a most plausible navigation solution is selected from the plausible navigation solutions. The identification at may be based on corresponding evaluations.

In at the outset of plausible navigation solution may include a k hypotheses based navigation solution computed from highlighted hypotheses and .

In accordance with of navigation solution evaluator may provide an indication of the highlighted hypotheses to combinatorial hypotheses set generator .

Combinatorial hypotheses set generator may generate an augmented hypotheses set including the highlighted hypotheses and one or more identified hypotheses from one or more of grids and .

Navigation solution generator may compute an augmented navigation solution from augmented hypotheses set .

One or more additional augmented navigation solutions may be generated from the highlighted hypotheses and or from one or more other sets of k hypotheses.

In accordance with of navigation solution evaluator may evaluate augmented navigation solutions to identify plausible navigation solutions.

System may perform the above described process with respect to all or substantially all plausible k hypotheses based navigation solutions and may augmented navigation solutions iteratively such as disclosed below with respect to .

Upon conclusion of the augmentation evaluations plausible navigation solutions may include one or more k hypothesis based navigations and or augmented navigation solutions.

At of a most plausible navigation solution may be selected from amongst plausible navigation solutions .

At a plausible navigation solution is selected from a set of one or more k hypotheses based navigation solutions. The set of one or more k hypotheses based navigation solutions may be generated such as described above with respect to through in . The selected plausible navigation solution may correspond to a k hypotheses based plausible navigation solution generated from a set of hypotheses. For example hypotheses and such as described above with respect to .

At a j grid that is not represented in the selected plausible navigation solution is selected. In one of grids and may be selected.

At an identified hypothesis is selected from the selected grid. In where grid is selected at hypotheses may be selected at .

At the hypotheses set of the navigation solution selected at is augmented with the hypothesis selected at . In the current example the set of hypotheses and may be augmented with hypothesis .

At if the grid selected at has multiple identified hypotheses another hypothesis is selected at and processing returns . In hypothesis may be selected at .

When all identified hypotheses of the selected grid have been processed processing proceeds from to .

At the augmented navigation solution computed at and any additional augmented navigation solutions computed in subsequent iterations of through are evaluated.

At evaluation results of the one or more augmented navigation solutions for grid selected at are compared with evaluation results of the plausible navigation solution selected at .

At one navigation solution is retained from amongst the one or more augmented navigation solutions evaluated at and the plausible navigation solution selected at based on the comparison at .

At if multiple of the j grids are not represented in the k hypotheses plausible navigation solution selected at another grid is selected at and processing returns to .

When all unrepresented grids of the navigation solution selected at have been processed processing proceeds from to .

At where there are multiple k hypotheses based navigation solutions another plausible k hypotheses based navigation solution is selected at and processing returns to .

Evaluation of a navigation solution may include vetting one or more parameters. An example parameterization is provided below.

Let tilde over y represent a stacked vector of measurements which may include without limitation range pseudo range and Doppler measurements.

Let tilde over x represent a stacked vector of navigation states. Navigation states may include for example and without limitation one or more of position velocity and clock error.

Let H represent a sensitivity matrix used in a least squares fit process at convergence. The sensitivity matrix may be a Jacobian matrix to represent a sensitivity of the measurements tilde over y tilde over to the navigation states tilde over x . The sensitivity matrix may be represented as 

If state tilde over x is regarded as fixed but unknown a covariance of the navigation states at convergence may be represented as 

A measurement error vector y may be represented as tilde over y minus the estimated measurements at convergence. At convergence this may be zero mean with covariance given by .

The matrix may be singular with a number of non zero eigenvalues given by p n m where n is the total number of the measurements and m is the total number of states estimated. By setting k such that a navigation solution is over determined p may be greater than 0.

A reasonableness of a navigation solution may be determined by determining whether the measurement vector is consistent with its assumed covariance such as by application of a chi squared test to the measurement vector projected into a non degenerate subspace of .

The covariance of the measurement vector at convergence may first be factored by a singular value decomposition USV 

There may be p singular values that are not small in the factorization. The singular values may be assumed to be sorted and U V to have been permuted so that the non zero singular values will occur at the beginning upper left of the main diagonal. The measurement vector at convergence may be transformed to eigen coordinates q Uy.

If the test statistic corresponding to a navigation solution is relatively much larger than the expected value compared to its standard deviation the navigation solution may be deemed invalid and may be discarded.

Alternatively or additionally a navigation solution may be evaluated with respect to positional dilution of precision PDOP test.

One or more features disclosed herein may be implemented in hardware software firmware and combinations thereof including discrete and integrated circuit logic application specific integrated circuit ASIC logic and microcontrollers and may be implemented as part of a domain specific integrated circuit package or combination of integrated circuit packages. The term software as used herein refers to a computer program product including a computer readable medium having computer program logic stored therein to cause a computer system to perform one or more functions in response thereto.

Computer system includes one or more computer instruction processing units illustrated here as a processor to execute computer program product logic also known as instructions code and software.

Computer system further includes memory storage including a computer readable medium having computer program product logic or instructions stored thereon to cause processor to perform one or more functions in response thereto.

Memory storage further includes data to be used by processor in executing instructions and or generated by processor in response to execution of instructions .

In the example of logic includes navigation logic to cause processor to detect navigation signals and to compute a navigation solution from the detected navigation signals.

Logic includes range Doppler correlation grid logic to cause processor to generate range Doppler correlation grids such as described above with respect to grids through .

Logic further includes threshold comparison logic to cause processor to identify range Doppler hypotheses that meet one or more thresholds such as described above with respect to one or more of first threshold second threshold and identified hypotheses trough .

Logic further includes combinatorial hypotheses set generator logic to cause processor to generate hypotheses sets such as described above with respect to one or more of k hypotheses sets and augmented hypotheses sets .

Logic further includes navigation solution generator logic to cause processor to compute navigation solutions such as described above with respect to one or more of navigation solutions and augmented navigation solutions .

Combinatorial hypotheses set generator logic and navigation solution generator logic may be collectively referred to herein as combinatorial computation logic or computation logic.

Logic further includes navigation solution evaluation logic to cause processor to evaluate navigation solutions and to identify plausible navigation solutions such as described above with respect to plausible navigation solutions .

Logic further includes selector logic to cause processor to select a most plausible navigation solution such as described above with respect to selector .

Computer system may include a communications infrastructure to communicate amongst components of computer system .

Computer system may include an input output controller to communicate with one or more other systems.

Navigation system includes a receiver to receive navigation signals perform one or more front end processes on navigation signals and output corresponding information to a vector acquisition and navigation solution generator system .

System may be configured to detect navigation signals based on correlations amongst the navigation signals and to output a most plausible navigation solution such as described in one or more examples above. System may include for example one or more of systems and portions thereof and or combinations thereof.

Navigation system may include an output system to receive most plausible navigation solution . Output system may include a display to display most plausible navigation solution . Alternatively or additionally output system may include a processing system to process multiple navigation solution . Processing system may include for example a tracking guidance and or avoidance system to accumulate and process most plausible solutions over time.

Output system or portions thereof may be implemented remotely and navigation system may include a transmitter to transmit most plausible navigation solution to the remote portion of output system .

Navigation system or portions thereof may be implemented within a deployment system which may include for example and without limitation a hand held GPS based positioning device a mobile telephone and or an automobile and or other mobile platform.

Methods and systems are disclosed herein with the aid of functional building blocks illustrating the functions features and relationships thereof. At least some of the boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries may be defined so long as the specified functions and relationships thereof are appropriately performed.

One skilled in the art will recognize that these functional building blocks can be implemented by discrete components application specific integrated circuits processors executing appropriate software and combinations thereof.

While various embodiments are disclosed herein it should be understood that they have been presented by way of example only and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail may be made therein without departing from the spirit and scope of the methods and systems disclosed herein. Thus the breadth and scope of the claims should not be limited by any of the example embodiments disclosed herein.

