---

title: Methods for improved single photon emission computed tomography using exact and stable region of interest reconstructions
abstract: The present invention provides systems, methods, and devices for improved computed tomography (CT) and, more specifically, to methods for improved single photon computed tomography (SPECT) using exact and stable region of interest (ROI) reconstructions. This technology can be extended across all tomographic modalities. Embodiments provide a method and a system for reconstructing an image from projection data provided by a single photon emission computed tomography scanner comprising: identifying a region of interest in an object; defining an attenuation coefficient and object boundary; computing the generalized Hilbert transform of the data through the defined region of interest and a known subregion; and reconstructing the image with improved temporal resolution at lower radiation doses, wherein the reconstructing comprises performing a reconstruction method that yields an exact and stable reconstruction. Embodiments also provide a method and a system for reconstructing an image from projection data provided by a single photon emission computed tomography scanner comprising: identifying a region of interest in an object; defining an attenuation coefficient and object boundary; and reconstructing the images by minimizing the high order total variation while minimizing the data discrepancy.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08952333&OS=08952333&RS=08952333
owner: Virginia Tech Intellectual Properties, Inc.
number: 08952333
owner_city: Blacksburg
owner_country: US
publication_date: 20101102
---
This application claims priority to and the benefit of the filing date of U.S. Provisional Application No. 61 257 443 filed Nov. 2 2009 which is hereby incorporated by reference herein in its entirety.

This invention was made with government support under grants EB002667 EB004287 and EB011785 awarded by The National Institutes of Health National Institute of Biomedical Imaging and Bioengineering. The government has certain rights in the invention.

The present invention provides systems and methods for improved computed tomography CT . More specifically the invention provides methods for improved single photon computed tomography SPECT using exact and stable region of interest ROI reconstructions. The inventive technology can be extended across all biomedical tomography based modalities.

Classic CT theory targets exact reconstruction of a whole cross section or of an entire object from complete projections while practical applications such as medical CT micro and nano CT often need to focus on a much smaller internal region of interest ROI . Current CT theory cannot exactly reconstruct an internal ROI only from projections associated with x rays through the ROI because this interior problem does not have a unique solution. When applying traditional CT algorithms for interior reconstruction from projection data features outside of the ROI may create artifacts overlapping inside features rendering the images inaccurate or useless. Moreover even more problems are associated with clinical imaging as well as in the case of small animals. Although there has been an explosive growth in the development of cone beam micro CT scanners for such studies the efforts are generally limited to cross sectional or volumetric imaging at high spatial resolution of 20 100 m and only at large radiation doses. These high radiation doses have devastating results on the patients and the animals and therefore eliminate the use of frequent CT as a possibility for medical use and pre clinical laboratory investigations.

Facing the increasing radiation risk cause by CT examinations a number of image reconstruction algorithms were developed to reduce the amount of necessary raw data. A recent milestone is the two step Hilbert transform method developed by Noo et al. In their framework an object image on a PI line chord can be exactly reconstructed if the intersection between the chord and the object is completely covered by the field of view FOV . In 2006 Defrise et al. proposed an enhanced data completeness condition that the image on a chord in the FOV can be exactly reconstructed if one end of the chord segment in the object is covered by the FOV.

While the CT reconstruction algorithms are being advanced rapidly the single photon emission computed tomography SPECT techniques are also experiencing remarkable improvements. As a unique biomedical tomographic imaging technique SPECT is able to reconstruct an image from the radioactive source distribution. SPECT is performed with a gamma camera to acquire multiple 2D projections from multiple angles. Then a tomographic reconstruction algorithm is applied to the fanbeam cone beam projections yielding a 2D 3D image. Different from the line integral model for x ray imaging the SPECT projections can be mathematically modeled as an exponentially attenuated Radon transform. In this context the CT reconstruction may be regarded as a special case of SPECT since all the attenuation coefficients are zeros which would allow for a better reconstruction method. However the reconstruction techniques of CT cannot be directly used for SPECT.

Despite the impressive advancement of the CT technology there are still unmet critical and immediate needs such as those mentioned above for better image quality at lower radiation doses in many biomedical uses and other investigations.

The numerous limitations inherent in the scanning systems described above provide great incentive for new better systems and methods capable of accounting for one or more of these issues. If CTs are to be seen as an accurate reliable therapeutic answer then improved methods for reconstructing an image should be developed that can accurately predict the image with improved temporal resolution and less artifacts at lower radiation doses.

Embodiments of the invention provide images with less than about 500 ms temporal resolution or less such as e.g. about 100 ms temporal resolution or less about 80 ms or less or about 60 ms or less or about 50 ms or less or about 30 ms or less or even about 10 ms or less and so forth. Ideally embodiments of the invention provide methods systems and devices capable of reconstructing images based on scanned regions of interest with resolution than is improved as compared with such images obtained by SPECT without the algorithms of the invention. Even further preferred are methods systems and devices capable of achieving high quality images e.g. same or better quality as compared with conventional SPECT based images with a radiation dose that is less than would be administered in a conventional SPECT based situation.

The primary limitation to the above mentioned state of the art treatment planning system is its need to provide good temporal resolution and image reconstruction when low doses of radiation are involved. However as more complex applications for scanning are encountered reconstruction of key subject areas such as the heart lung head and neck is cumbersome at best and may be inadequate to develop reliable diagnosis and therapies. Therefore a more advanced system that allows for the production of better object reconstruction at lower radiation doses would be ideal. The present invention allows for the adaptation of interior SPECT to provide such improved reconstructions.

Accordingly embodiments of the invention provide methods and systems for reconstructing an image from projection data provided by a single photon emission computed tomography scanner comprising identifying a region of interest in an object defining a constant attenuation coefficient and object boundary measuring the Hilbert transform of the data through the defined region of interest and reconstructing the image with improved temporal resolution at lower radiation doses wherein the reconstructing comprises performing a reconstruction method that yields an exact and stable reconstruction.

In some embodiments the reconstructed image is a portion of a heart a lung a head or a neck in a patient.

In preferred embodiments the single photon emission computed tomography projections are uniformly attenuated local projections.

In other preferred embodiments the single photon emission computed tomography projections are modeled as a Radon transform.

In yet another embodiment the present invention provides a method for reconstructing an image from projection data provided by a single photon emission computed tomography scanner comprising identifying a region of interest in an object defining the region of interest as piecewise polynomial measuring the Hilbert transform of the data through the defined region of interest and reconstructing the image with improved temporal resolution at lower radiation doses wherein the reconstructing comprises performing an improved high order TV minimization.

In such embodiments the improved high order TV minimization has an explicit formula for cases with polynomial order of about 2 or more.

The features and advantages of embodiments of the present invention will be apparent to those skilled in the art. While numerous changes may be made by those skilled in the art such changes are within the spirit of the invention.

Specific embodiments include a computed tomography based reconstruction method comprising reconstructing a region of interest ROI of an object into an image from single photon emission computed tomography SPECT projection data of the ROI by modeling the projection data as an attenuated Radon transform comprising formula 

Such methods can further comprise defining a constant attenuation coefficient and object boundary and measuring the Hilbert transform of the data through the ROI. Even further methods according to embodiments of the invention can further comprise defining the region of interest as piecewise polynomial and reconstructing the image by performing a high order TV minimization.

Other embodiments of the invention include a method further comprising scanning an object using a SPECT scanner to acquire projection data relating to the object. Methods can also include single photon emission computed tomography projection data which are uniformly attenuated local projections. Further the projection data P s can be acquired with gamma camera. According to method embodiments the reconstruction image can be reconstructed using guided computed tomography and or nano computer tomography.

Also included within the scope of the invention is a SPECT system comprising a SPECT scanner operably configured for scanning an object to acquire projection data relating to the object a processing module operably configured for reconstructing the scanned portion of the object into an image by identifying a region of interest ROI measuring the Hilbert transform of the data through the defined ROI performing a reconstruction method that yields an exact and stable reconstruction and a processor for executing the processing module.

Such systems can be operably configured for scanning and reconstructing a heart lung head or neck of a subject. Even further such systems can be operably configured such that the reconstructing employs singular value decomposition.

Systems of the invention can be operably configured wherein the single photon emission computed tomography projection data are uniformly attenuated local projections.

Preferred system embodiments of the invention are operably configured such that the processing module is capable of modeling the projection data as an attenuated Radon transform comprising formula 

where subscript o indicates original projection data cos sin sin cos and x is the attenuation coefficient map on the whole compact support .

Projection data P s can be acquired with a gamma camera according to some embodiments of the present invention.

Even further systems of the invention can be operably configured for reconstructing the image using guided computed tomography and or nano computer tomography.

It is noted that although only specific embodiments or methods systems and devices are listed in this summary these embodiments can be expanded to cover methods systems and or devices regardless of the type of embodiment is listed. For example when referring to only a method such disclosure should be construed to include devices and systems comprising the same elements. Further these specific embodiments can be altered or modified by omitting one or more elements specifically listed and or by combining elements of another listed embodiment therewith. For example if a method embodiment refers to having two method steps that embodiment can be construed as a system capable of performing only one of those functions and or as a system capable of performing both of the listed functions and any other function listed for another embodiment. It is within the capabilities of those of ordinary skill in the art to modify this disclosure in this way.

In the context of this disclosure accuracy or theoretically exact means that the algorithm is theoretically exact for a good portion of voxels in the object or theoretically exact if a practically insignificant portion of data could be handled in a more complicated fashion.

SPECT is an important biomedical imaging modality. However since gamma cameras are expensive and bulky truncated projection data are either preferred or unavoidable. Inspired by the recent results on interior tomography in the x ray CT field the present invention describes an interior SPECT approach for exact and stable reconstruction of a region of interest ROI from uniformly attenuated local projection data. In certain embodiments the reconstruction is aided by prior knowledge of a sub region in the ROI. The present invention provides exact and stable interior SPECT systems methods and devices.

In accordance with embodiments of the present invention a method of the present invention may comprise introducing analytic continuation of the algorithms for use with conventional CT technologies in order to obtain better reconstruction images in SPECT. One of the many potential advantages of the methods of the present invention only some of which are discussed herein is that images with less blurring and improved temporal resolution may be obtained even when there is much lower radiation exposure in the object being scanned when compared with conventional radiation doses.

The current invention may provide benefits to various types of interior tomography including but not limited to cardiac lung head e.g. dental neck tomography guided CT procedures and nano CT. In the medical field and in biomedical science the methods disclosed herein may greatly reduce the amount of radiation necessary to obtain a good image and thereby potentially allow increased early detection of diseases reduced exposure to radioactivity in patients and or reduced costs associated with CTs. Better temporal resolution at low radiation doses in the images may provide a cost savings by reducing the number of images needed to conclude a finding. This type of scanning may likewise provide more flexibility in designing experiments in small animals in order to better study these diseases and develop effective treatments.

Another potential advantage is the use of an improved high order TV minimization to better reconstruct an image at lower radiation doses through interior SPECT without a defined object boundary. In such embodiments the ROI is assumed to be piecewise polynomial. There are at least two more advantages associated with interior SPECT. First of all the size of a SPECT camera can be accordingly reduced substantially lowering the system cost. This is especially desirable when an expensive high resolution camera is needed or a low cost system is intended for wider healthcare coverage. Use of a smaller field of view would also allow the camera to be closer to a subject under study improving the signal to noise ratio.

The results from the SPECT interior reconstruction are summarized herein. In certain embodiments the constant attenuation coefficient and the object boundaries are known. In other embodiments discussed in detail below the object boundaries are not known. In embodiments where the constant attenuation coefficient and the object boundaries are known x may be a 2D smooth distribution function defined on a convex compact support with x x y . Mathematically in a parallel beam geometry the SPECT projections of x can be modeled as the attenuated Radon transform seen in EQUATION 1 

where the subscript o indicates original projection data cos sin sin cos and x is the attenuation coefficient map on the whole compact support . For practical applications P s can be acquired by a gamma camera. For most imaging subjects such as the brain the attenuation map can be approximated as a uniform distribution 

where is a constant. Since the object function is compactly supported the maximum coordinate along the direction of the intersection between support and the integralline of the projection P s can be determined. Without loss of generality and without wishing to be limited by theory the coordinate is denoted as t s and EQUATION 1 becomes EQ. 3 

For certain embodiments we can assume that the convex compact support and the constant attenuation coefficient are known. Once the coordinate system is chosen we can determine t s for all the whole projection dataset. By multiplying a weighting factor eo the projection model of SPECT can be reduced to EQUATION 4 

where the subscript w indicates that the weighted projection data. A weighted backprojection of the differential projection data may be denoted by EQUATION 5 

In 2004 Rullgard proved a relationship linking the object image x and the weighted backprojection g x as

When 0 chbecomes the Hilbert transform kernel may be in consistence with the results in the CT field. EQUATION 6 depicts a generalized Hilbert transform and the corresponding Hilbert filtering line a generalized PI line. The backprojection operation for g x in EQUATION 5 may only involve local projection data whose integral paths intersect with the point x. Hence inside a field of view FOV or region of interest ROI any point may be irradiated at least from an angular range of 180 degrees and its backprojection g x of differential data can be exactly computed.

Without loss of generality or wishing to be limited by theory let us denote a 2D x on a PI line chord as u and the backprojection g x as g u where u is a 1D coordinate along the PI line.

In 2007 Noo et al. extended their two step Hilbert CT method to the case of SPECT and showed that an object image u can be exactly reconstructed on the whole compact support interval c c if c

In certain embodiments the parameter c cin the above theorem were omitted and in practical applications mcould be directly computed from the projection datum along the path through the corresponding PI line. In such embodiments it can be assumed that the known u are on any subinterval of the line segment c c or a union of such intervals. The corresponding results can be directly obtained by applying Theorem 2.1 repeatedly.

Without loss of generality or wishing to be limited by theory we assume c 1 and c 1. In other embodiment we can arrive at this standardization by a linear coordinate transform. For the case c

Noo et al. proved that the Cauchy principle value integral in EQUATION 14 can be removed because EQUATION 15 is a smooth function leading to that u is a smooth and continuous function over the region u 1 1 1 1 . Using the following identical equation

Note that both u v and u are analytical with respect to the variable u and u is analytical with respect to the variable u. Hence Kh u can be analytically extended to the whole complex plane.

By our assumption in Theorem 1 of the present invention h u is known for u R and h u is known on the interval c c we obtain that EQ. 22

can be known on the interval c c . Because the principal integral of the first term of Eq. 21 is defined on 1 c c 1 h u is analytic on the interval c c and it can be analytically extended to the complex plane with cuts along the real axis from to cand from cto . Therefore h u can be determined on the interval c c by its value on the interval c c . As a result h u or u can be uniquely reconstructed on the interval c c .

In some embodiments a stability analysis can be performed for our Theorem 1 as follows. In practice we have the measurement g u of g u and reconstruct u from g u . Assume that these functions satisfy the following conditions for is known in i for ii 

In order to obtain a upper bound of h u on the interval c tilde over c the present invention uses Nevanlinna s principle.

then D B where D tilde over c c and B is the circle with diameter tilde over c tilde over c . Recall that

and the u axis can be discretized with a uniform sampling interval satisfying sampling theorem for both u and g u . Denote u at the discrete sampling points on the interval c c as . . . . . . . Also denote g u at sampling points on the interval c c as g g . . . g . . . g.

In EQUATIONS 38 and 39 T represents the transpose operator and in EQUATION 40 Arepresents the weighting coefficient of . Let u and u g be the coordinates on the u axis for and g.

With the sampling method of the present invention u always produces integers and the case u 0 in EQUATION 42 exactly corresponds to the singular point in the Cauchy principal integral in EQUATION 36. Because u can be known on c c F may be divided into two parts

where Fis the known part on the sampling points in c c while Fis the unknown part on the sampling points in c c c c . Correspondingly the matrix A can be divided into two parts EQ 44

Although EQUATION 45 is generally ill posed we can still stably reconstruct the part of in the interval c c using the singular value decomposition SVD method 19 20 . Note that the dimension of is M. If the dimension of is the dimension of will be . According to the SVD theory 19 21 the matrix has a SVD decomposition in the following form EQ 46

where U and V are orthogonal matrices of and respectively and is an diagonal matrix whose diagonal elements satisfying . . . . . . Q min . In this way a stable numerical solution for can be obtained EQ 47

and 0 is a free small constant parameter. The system defined by EQUATIONS 47 and 48 can be called a truncated SVD TSVD which is a special case of regularization.

The present invention numerically analyzes the stability of Theorem 1 from a signal processing viewpoint. In certain embodiments the unknown u and known g u are linked by EQUATION and u is assumed to be smooth. Based on the sampling theorem in the classical signal processing theory u can be exactly recovered from its values at sampling points if i u can be band limited and ii the sampling frequency may not be smaller than the Nyquist frequency. In addition to the smoothness of u the present invention can further assume that u may be essentially band limited which may be reasonable in most practical engineering applications. Hence the present invention can stably reconstruct u at its finite sampling points on the interval c c using the aforementioned SVD method.

where Irepresents an unit diagonal matrix. Let E circumflex over F Fas the error vector of F and S V UA Ias an matrix. Then EQUATION 49 can be reduced as EQ 50

where defines the maximum noise magnitude. Recall that G AFand the noise expression of can be written as EQ 54

To demonstrate the exactness and stability of interior reconstruction of SPECT in the present invention c 1 c 1 c 0.6 c 0.6 and c 0.2 are set for numerical computation. Assume that the number of sampling points on 1 1 is N and the small constant in the TSVD method is . For different combinations of N and we computed the precision and stability measures Cand Cas shown in respectively. Because u was known on c c the corresponding portions of Cand Cin the interval c c were set to 0. From the following three comments can be made. First there are little differences in terms of the precision and stability measures with respect to the number of sampling points on the whole support of u . If the number N continuously increases the sampling interval will become smaller and smaller. Eventually the continuous case when N is reached. It is expected that there would still be little difference in terms of the precision and stability measures of N from what can be obtained which is of course a numerical observation lack of mathematical rigor . Second the precision measure Cin is very close to zero in the interval c c especially the portions near c. When the constant is reduced in the TSVD method the precision measure Cwould decrease in the interval c c which means a higher accuracy. Undoubtedly Cshould ideally approach zero on the interval c c when 0. Meanwhile a small constant attenuation parameter yields a better precision. Third the stability measure in was smaller on the interval c c than elsewhere especially the portion near c which means a better stability. If the constant is continuously decresased in the TSVD method the stability measure would correspondingly increase in an order of 1 which means the stability would become worse and worse.

In this present invention an interior reconstruction technique for SPECT in a parallel beam geometry is provided. Using a rebinning scheme EQUATION 5 can be extended into a fan beam geometry and other variants such as the varying focal length fan beam geometry. A major difference lies in the involved Jacobian factor of EQUATION 5 in the backprojection step while the generalized Hilbert transform based reconstruction method may remain the same as that for parallel beam imaging. Using analytic techniques similar to our generalized backprojection filtration method our interior SPECT methodology can be further extended to more complex cone beam configurations and more general focal spot trajectories.

When the reconstruction formula was derived and the exactness and stability analyzed in some embodiments it is possible to assume a uniform attenuation map. Without giving a detailed proof and analysis it should be pointed out that in other embodiments similar results can be obtained for a nonuniformly attenuated background. In that case both analytic continuation and SVD techniques remain important tools to analyze the uniqueness exactness and stability as well as to reconstruct a distribution of radioactive sources. In addition to the SVD method disclosed in this application other reconstruction methods such as POCS can be also developed for reconstruction from generalized attenuated Hilbert transform data.

As another important nuclear medicine imaging modality positron emission tomography PET produces 3D images of functional and cellular features in the body. Different from SPECT a radio active source emits pairs of particles in opposite directions and they are detected in the coincidence mode i.e. only events with two particles arriving at opposite detectors within a narrow time window are counted. Thus the projection model of PET can be written as

After an attenuation correction the both uniform and non uniform PET reconstruction can be done as from CT projection data.

In the embodiments discussed above the limitation of knowing and clearly defining the object boundaries exist. Although the CT numbers of certain sub regions such as air in a trachea and blood in an aorta can be indeed assumed how to obtain precise knowledge of a sub region can be difficult in important cases such as in contrast enhanced functional studies. Therefore it would be very valuable to develop more powerful interior tomography techniques. Fortunately the compressive sampling CS theory has recently emerged which shows that high quality signals and images can be reconstructed from far fewer data than what is usually considered necessary according to the Nyquist sampling theory. The main idea of CS is that most signals are sparse in an appropriate system that is a majority of their coefficients are close or equal to zero when represented in an appropriate domain. In light of the CS theory and using the specific gradient transform we proved that it is possible to accurately reconstruct an ROI only from truncated projections by minimizing the total variation TV if the ROI is piecewise constant without knowledge of any known sub region in the ROI which. Very recently we extended this piece wise constant result to allow a piecewise polynomial model and the inventive interior tomography systems and methods by the high order TV HOT minimization. See e.g. High Order Total Variation Minimization for Interior SPECT Yang Jiansheng et al. 2010 which is incorporated herein by reference in its entirety.

HOT minimization based interior tomography can be generalized for interior SPECT. The present invention seeks to accurately reconstruct an ROI only from the uniformly attenuated local SPECT projections through the HOT minimization under the assumption that the underlying distribution function is piecewise polynomial. Without loss of generality in certain embodiments the following conditions are assumed 

It is well known that under Conditions 4 and 5 the interior problem does not have a unique solution. The following theorem characterizes the structure of solutions to the interior SPECT problem.

Any image x satisfying Conditions 4 and 5 can be written as x x u x for x where u x is an analytic function in the disc and Ru s 0 a

Let u x x x . Clearly u x is a piecewise smooth function and compactly supported on the disc by Condition 1 and 4 and 0 EQUATION 60

By Tretiak and Metz s Inversion formula which was derived from the shift property 5 and Corollary 2 we have

Hence the function u x is an analytic function in . From now on let u x always represent an ambiguity image unless otherwise stated. We will rely on the HOT minimization to solve the interior SPECT problem with uniformly attenuated local projection data under the assumption that x is piecewise polynomial in a ROI .

If an object image x is piecewise polynomial in ROI we can prove that x is the only candidate image that minimizes the HOT. First let us prove that if an ambiguity image is polynomial in then it must be zero. This result will be formally stated as Theorem 3. In order to prove Theorem 3 we will need Lemmas 1 2 and 3.

Suppose that a is a positive constant. If a g z is an analytic function in a a b p x is a polynomial function c 

Assume that a is a positive constant. If a g z is an analytic function in a a b p x is a polynomial function d 

If an artifact image u x satisfies a with x where p x is a 2 D polynomial function b Ru s 0 with s a a then u x 0.

As illustrated in for an arbitrary 0 let Ldenote the line through the origin and tilted at cos sin . When u x is restricted to the line L it can be expressed as cos sin . EQUATION 82

By the relationship between the differentiated backprojection of the attenuated projection data and the generalized Hilbert transform of the image 5 we have

where p t cos sin is a polynomial function with respect to t. By b and EQUATION 83 we have 0 for . EQUATION 87

Suppose that x is piecewise constant in ROI that is can be decomposed into finitely many sub domains such that for 1 EQUATION 90

and each sub domain is adjacent to its neighboring sub domains with piecewise smooth boundaries j N. For any candidate image x x u x where u x is an arbitrary ambiguity image let sup div 1 in EQUATION 91

Under the assumption that x is piecewise constant in ROI through the TV minimization we can establish the uniqueness of interior SPECT as follows.

Suppose that x is piecewise constant in a ROI as defined by Eq. 3.28 . If h x is a candidate image and

An expression for high order TV HOT was previously introduced. In certain embodiments the present invention provides an alternative expression. We define the n 1 th n 1 order TV as the limit of the following sum 

Under the assumption that x is a piecewise n th n 1 order polynomial function in an ROI through the HOT minimization we can establish the uniqueness of interior SPECT just as what we have done for interior CT. First we will derive an explicit formula of HOT for any candidate image under the assumption that x is a piecewise n th n 1 order polynomial function in .

Suppose that x is a piecewise n th n 1 order polynomial function in that is can be decomposed into finitely many sub domains such that for 1 EQUATION 108

where x is a n th order polynomial function and each sub domain is adjacent to its neighboring sub domains with piecewise smooth boundaries j N. Then for any candidate image x x u x we have

Note that x x u x where u x is an analytic function. Let Qbe an arbitrary partition of . First let us consider Qthat covers a common boundary of a pair of neighboring sub domains and and is contained in . The normal vector of the curve pointing from towards is denoted by . For g g C Q we have

Performing integration by parts for the two terms on the right hand side of Eq. 3.48 respectively and utilizing the fact that g x 0 0 near the boundary of Q we have

On the other hand for C Q repeatedly performing the 2 D integration by parts and utilizing the fact that x 0 . . . 0 near the boundary of Q we have

I was evaluated in several cases and lemma 5 was proven. Finally we have the following Theorem 5 on the uniqueness of interior SPECT.

Suppose that x is a piecewise n th n 1 order polynomial function in as defined in Lemma 5. If h x is a candidate image and

In conclusion by analytic continuation interior CT reconstruction technique has been extended from CT to that for SPECT. The uniqueness and stability of interior SPECT have been analyzed. Using the SVD technique we have implemented an interior SPECT algorithm. Both theoretical analysis and numerical simulations have demonstrated the feasibility of embodiments of the inventive interior SPECT approach.

To facilitate a better understanding of the present invention the following examples of certain aspects of some embodiments are given. In no way should the following examples be read to limit or define the scope of the invention.

To verify and showcase the inventive interior reconstruction for SPECT of the present invention we performed several numerical tests. In our simulation a modified Shepp Logan phantom of SPECT version was employed inside a circular support of radius 10 cm. As shown in the phantom consists of 10 ellipses whose parameters are the same as that given by Noo et al. We assumed that a uniform attenuation coefficient 0 throughout the whole support of the phantom. In parallel beam geometry 360 view angles were uniformly sampled for an angle range 0 . For each view angle there were totally 600 detector elements uniformly distributed along a 20 cm linear detector array. For different attenuation coefficients 0 0.0 cm 0.15 cm 0.30 cm we analytically computed non truncated projection datasets. Hence the backprojection of differential data can be easily calculated at any point to simulate different fields of view FOVs . Without loss of generality here we assumed a rectangular FOV and the distribution function x was known in the stripe region in the FOV . We implemented the TSVD method described in Section 3.2 to reconstruct the distribution image x in the whole FOV. The constant parameter was set to be 0.02 and there were 512 uniform sampling points along each 20 cm side length in the image space. In the reconstructed procedure the prior information of x in the strip region was chosen as that reconstructed from the non truncated data with 0. The reconstructed results are presented in . Because there was noise in the prior information we had some errors in the reconstructed images especially in the case 0.30 cm. These results are consistent with our aforementioned stability analysis. To verify the stability of the inventive techniques we added 1 Gaussian white noise into the raw projection data and repeated the above testing steps. The reconstructed images are also presented in which also support our analysis on the exactness and stability discussed in this application.

To verify our theoretical findings obtained in the present invention we developed a HOT minimization based interior SPECT algorithm in an iterative framework. This algorithm is a modification of our previously reported HOT minimization based on an interior tomography algorithm. One difference between this algorithm and previous algorithms lies in the formulations for the steepest gradient of HOT and the ordered subset simultaneous algebraic reconstruction technique OS SART . Let u v be a digital image reconstructed from the available local projections where represents the sampling interval u and v are integers. To demonstrate the computation for the steepest gradient direction here we use the piecewise linear case as an example. From the definition of HOT 

which consists of the terms for characterizing discontinuities between neighboring regions and also high order derivatives. The first term of HOTis for discontinuities between neighboring regions. These discontinuities are due to the jumps of image intensities. In the discretization the first term of HOTwould be implemented as the difference of neighboring pixel values which is proportional to the finite difference in image intensities at relevant pixels. Therefore we implemented HOT as follows 

where the intensity differences from the first term of HOT have been incorporated D u v 2 D u v 4 D u v 2 D u v D u v are the second order and first order finite differences along the coordinate directions for i j 1 2 respectively. There are different orders of discontinuities in the image intensity i.e. pixel values first order derivatives and second order derivatives etc. which HOT combine in a certain way. Numerically higher order finite differences dominate lower order ones in quantifying discontinuities. Therefore instead of the above discretization HOT we used the following approximation for HOT 

For CT scanning systems the discrete model of projections in terms of Radon transform can are expressed as EQUATION 141

where data b b . . . b Rrepresents the measured projections and each bis a x ray path 1D vector . . . Rreformatted from 2D image and a known non zero matrix A a whose component ais the intersection area between the mx ray path and npixel. The SART solution is 

Considering the attenuation Radon transform of SPECT as expressed by EQUATION 59 EQUATION 139 can be modified as EQUATION 144

with aw where wis the corresponding discrete term ein EQUATION 59 and the SART solution for SPECT can be expressed as 

Clearly the CT reconstruction formula is the special case 0 of the SPECT solution. Because key details of our algorithm were already reported here we omit the implementation steps for simplification.

In our numerical simulation we assumed a popular parallel beam imaging geometry in the SPECT field. All other imaging geometry parameters and reconstruction control parameters are well known in the art. At the origin we assumed a disk shaped compact support of radius 100 mm with a uniformly attenuation coefficient . Inside the compact support there is a modified and piecewise linear Shepp Logan phantom. Representative reconstructed images are shown in . As seen from the reconstructed SPECT images using the inventive HOT minimization algorithm are in an excellent agreement with the truth inside the ROI. However it can be observed that the profiles near the edges deviate substantially from the truth. Although a rigorous stability analysis has not been performed yet it is conjectured that this phenomenon is a stability issue of interior tomography. We believe that this behavior is similar to what we analyzed for the knowledge based interior CT. The closer the distance to the peripheral region of an ROI the less the stability of the interior reconstruction. A different numerical implementation could reduce this discrepancy. However it cannot be completely removed unless stronger prior knowledge is incorporated for interior reconstruction.

The present invention has been described with reference to particular embodiments having various features. It will be apparent to those skilled in the art that various modifications and variations can be made in the practice of the present invention without departing from the scope or spirit of the invention. One skilled in the art will recognize that these features may be used singularly or in any combination based on the requirements and specifications of a given application or design. Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention. It is intended that the specification and examples be considered as exemplary in nature and that variations that do not depart from the essence of the invention are intended to be within the scope of the invention.

Therefore the present invention is well adapted to attain the ends and advantages mentioned as well as those that are inherent therein. The particular embodiments disclosed above are illustrative only as the present invention may be modified and practiced in different but equivalent manners apparent to those skilled in the art having the benefit of the teachings herein. Furthermore no limitations are intended to the details of construction or design herein shown other than as described in the claims below. It is therefore evident that the particular illustrative embodiments disclosed above may be altered or modified and all such variations are considered within the scope and spirit of the present invention. While compositions and methods are described in terms of comprising containing or including various components or steps the compositions and methods can also consist essentially of or consist of the various components and steps. All numbers and ranges disclosed above may vary by some amount. Whenever a numerical range with a lower limit and an upper limit is disclosed any number and any included range falling within the range is specifically disclosed. In particular every range of values of the form from about a to about b or equivalently from approximately a to b or equivalently from approximately a b disclosed herein is to be understood to set forth every number and range encompassed within the broader range of values. Also the terms in the claims have their plain ordinary meaning unless otherwise explicitly and clearly defined by the patentee. Moreover the indefinite articles a or an as used in the claims are defined herein to mean one or more than one of the element that it introduces. If there is any conflict in the usages of a word or term in this specification and one or more patent or other documents that may be incorporated herein by reference the definitions that are consistent with this specification should be adopted.

Throughout this application various publications are referenced. The disclosures of these publications in their entireties are hereby incorporated by reference into this application in order to more fully describe the state of the art to which this pertains. The references disclosed are also individually and specifically incorporated by reference herein for the material contained in them that is discussed in the sentence in which the reference is relied upon.

The present invention has been described with reference to particular embodiments having various features. It will be apparent to those skilled in the art that various modifications and variations can be made in the practice of the present invention without departing from the scope or spirit of the invention. One skilled in the art will recognize that these features may be used singularly or in any combination based on the requirements and specifications of a given application or design. Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention. It is intended that the specification and examples be considered as exemplary in nature and that variations that do not depart from the essence of the invention are intended to be within the scope of the invention.

Throughout this application various publications are referenced. The disclosures of these publications in their entireties are hereby incorporated by reference into this application in order to more fully describe the features of the invention and or the state of the art to which this pertains. The references disclosed are also individually and specifically incorporated by reference herein for the material contained in them that is discussed in the portion of this disclosure in which the reference is relied upon.

