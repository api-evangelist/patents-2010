---

title: Holographic map
abstract: A holographic map is formed of one or more holograms or images conforming to the open/closed aperture theorem and grazing angle compensated. A hologram can be thought of as the sum of all images over a range of angles, wherein the frequency and aspect information is coded into two dimensions. An open/closed aperture image is an image having all points in the image observed over the same range of angles. Grazing angle compensation projects the data onto a representation of the sea floor and the image is rescaled by the cosine (or secant) of the angle between a ray connecting the sonar to a point on the sea floor. A valid range of viewing aspects is defined. The images in the holographic map have both a frequency band and range of aspects that, after grazing angle compensation, describe all locations in the map.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08937641&OS=08937641&RS=08937641
owner: The United States of America as represented by the Secretary of the Navy
number: 08937641
owner_city: Washington
owner_country: US
publication_date: 20100315
---
This patent application claims priority to U.S. Provisional Patent Application No. 61 216 567 filed on May 18 2009 the contents of which are incorporated herein by reference in their entirety. This patent application is related to co pending patent application entitled SYSTEM AND METHOD FOR SPATIALLY INVARIANT SIGNAL DETECTION Ser. No. 12 454 486 filed on May 18 2009 and Provisional Patent Application No. 61 216 566 entitled HOLOGRAPHIC NAVIGATION filed on May 18 2009 the contents of which are incorporated herein by reference in their entirety. These co pending applications are by the same inventor as this application.

The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

The present invention relates to holographic maps and more specifically to maps consisting of coherent imagery using well defined aspect and frequency content to estimate position.

As is known in the art traditional maps describe relationships between phenomena and position. The two most common map types are contour or field maps and feature based maps. Contour or field maps relate the intensity of some phenomena to position. For instance a topographical map relates elevation to position. This relationship can be represented as the function E x y . Bathymetric and gravitometric maps have similar representations.

Feature based maps represent the world in terms of discrete landmarks. Although feature specific information can be encoded into the map such as object type color texture etc the classical feature based map simply combines object locations into a state vector with each coordinate pair corresponding to a distinct landmark as shown in Equation 1.

Both of these approaches break down when using sonar images because what is observed with sonar changes so dramatically with position and angle. A scene cannot be adequately described in terms of a single function I x y . Nor can features be reliably extracted and recognized as part of a feature based representation.

To best understand the underwater scene it is necessary to describe it using more variables. Each point on the bottom has a signature which is both aspect and frequency dependent. As such a better representation might be I x y f where f is frequency and e is the observation aspect. However this representation is cumbersome because it requires populating a four dimensional space.

What is needed is an approach that codes the frequency and aspect information into two dimensions. Such an approach would require less storage than a four dimensional representation.

It is therefore a general purpose and primary object of the present invention to provide a holographic map wherein the frequency and aspect information is coded into two dimensions. The frequency and aspect content can be well defined such that terrain reacquisition sonar can be designed and operated in such a manner that coherent correlation is possible.

A hologram can be thought of as the sum of all images over some range of angles. It requires less storage than the four dimensional representation and is ideal for correlation. A holographic map can be formed of one or more holograms or images that conform to the open closed aperture theorem and that have been grazing angle compensated as will be explained in further detail hereinafter. The open closed aperture theorem is described in more detail in co pending patent application Ser. No. 12 454 486 entitled SYSTEM AND METHOD FOR SPATIALLY INVARIANT SIGNAL DETECTION incorporated by reference above.

A closed radiative aperture surrounds a point p arbitrarily disposed within the closed aperture. Any radiation emitted from point p including reflected radiation will be incident upon the inner surface of the closed aperture. The net signal detected by the aperture is the point spread function of point p integrated over the inner surface i.e. integrated over all points s on the inner surface. Consideration of this integral leads to the Closed Aperture Theorem.

If for each point on the inner surface one weights this integral by the cosine of the angle between a normal and a position vector directed between points s and p the integral becomes spatially independent of the position vector in the direction of the normal i.e. the radial component of the position vector and depends solely on the position on the inner surface of the closed aperture not on the distance from s to p. Subject to the assumption that point p is far enough from the closed aperture that the spreading loss to the main lobe and side lobes of the point spread function are approximately equal the radiative signal from point p detected by the closed aperture will be spatially invariant.

The spatial resolution of a typical sonar is about an inch that of a radar on the order of a micrometer an acoustical signal in a human the human body on the order of millimeters n.b. ultrasound . Thus for practical purposes the signal which the closed aperture receives from point p is unrelated to the location of p. This result is wholly independent of the shape of the closed aperture. For an aperture of any shape that completely encloses point p radiation from point p would still be spatially invariant in the manner above described.

For the Open Aperture Theorem consider a first aperture generally enclosing point p but with a portion removed so as to permit lines of sight for point p outside of the aperture. Because radiation from point p can now escape the aperture the Closed Aperture Theorem does not hold. However because the theorem does hold independent of aperture geometry any additional aperture that in conjunction with the first aperture would close the removed portion would again render detection of radiation from p spatially invariant.

This implies that all apertures sized and positioned to receive the identical radiation from point p as would an aperture plugging the removed portion must necessarily be radiatively identical with respect to point p. Thus any aperture sized and shaped to subtend the same solid angle having point p as its vertex as is subtended by the removed portion with point p as its vertex must necessarily be radiatively equivalent to one another as concerns point p.

By way of further comment to subtend the same solid angle means here more than simply containing the same number of steradians. It means that the aperture be sized and shaped to receive the same illumination from point p. To the extent one deviates from this one deviates from both the Open and Closed Aperture Theorems the deviation being in effect a source of noise to the process of signal detection. As an aperture moves farther away from a point of interest such as p simple geometry dictates that the change in solid angle the aperture subtends changes by increasingly small amounts and the noise error thereby introduced decreases correspondingly. Thus at distances large compared to the dimensions of the aperture one would expect solid angle mismatches to be negligible.

Quantitatively if the mismatch is characterized by area of solid angle overlap area desired to be overlapped then for an aperture having an inherent signal to noise ratio SNR the signal to noise of the aperture SNR having such a mismatch is SNR SNR 1 SNR 1 . As overlap becomes perfect 1 SNR goes to SNR i.e. the aperture s signal to noise is unchanged as one would expect. For no overlap at all 0 SNR goes to zero and the aperture will receive no signal at all from point p. Because this mismatch becomes less pronounced at large distances at such distances the cosine weighting provides the predominant benefit.

An ideal open closed aperture image is an image where all points in the image are observed over the same range of angles. A suboptimal system observes points over different ranges of angles. Such images are typically formed by broadside squinted or circular Synthetic Aperture Sonars SAS s .

Grazing angle refers to the angle between a ray connecting the sonar to a point on the sea floor. For a given sonar frequency the spacing between peaks in the sound waves arriving at the sea floor gets closer together as the horizontal range increases. Thus geometric relationships between objects on the sea floor are distorted.

Grazing angle compensation projects the data onto a representation of the sea floor. By rescaling the image by the cosine of the grazing angle or alternately by the secant it is possible to shift the frequencies and create a grazing angle invariant image. The simplest form of grazing angle compensation assumes a flat bottom and a sonar platform operating at a constant altitude. More advanced algorithms project the image onto terrain with relief which scales the frequencies in a more complicated manner.

In addition to grazing angle compensation a valid range of viewing aspects needs to be defined. If a target is viewed from different angles the information about the target will lie along a different line in the frequency domain and the signals will not correlate.

Accordingly the holographic map consists of one or more sonar images having both a frequency band and range of aspects that after grazing angle compensation describe all locations in the map.

In one embodiment a holographic map is formed by one or more images that conform to the open closed aperture theorem. The images are grazing angle compensated and both a frequency band and a range of aspects of the images describe all locations in the holographic map.

In one embodiment the images are formed by a synthetic aperture sonar. The synthetic aperture sonar may be a one of a broadside squinted or circular synthetic aperture sonar. In one embodiment the holographic map can be formed of a plurality of distinct holograms or a mosaicked hologram.

In one embodiment a method of generating a holographic map includes the steps of forming an image conforming to the open closed aperture theorem grazing angle compensating the image and defining a frequency band and a range of aspects of the image to describe all locations in the holographic map.

In one embodiment the image is formed using a synthetic aperture sonar. In one embodiment a plurality of images are formed and combined to form the holographic map. In one embodiment a plurality of images are mosaicked to form the holographic map.

Presented herein is a new type of map for navigation using sonar or radar. Traditional representations used in feature based navigation are problematic when combined with sonar or radar systems because they require reliable feature detection and object recognition. If instead coherent image correlation is used it is possible to recognize terrain without detection or object recognition.

This approach requires a map which is well suited to image correlation. The map must have well defined frequency and aspect content such that terrain reacquisition sonar can be designed and operated in such a manner that coherent correlation is possible. The map can comprise images that conform to the open closed aperture theorem and that have been grazing angle compensated or images created by open closed apertures which are surfaces.

An ideal open closed aperture image is an image where all points in the image are observed over the same range of angles a suboptimal system observes points over different ranges of angles . These images are typically formed by broadside squinted or circular Synthetic Aperture Sonars SAS s .

Grazing angle compensation projects the data onto a representation of the sea floor. This causes a scaling of frequencies. The simplest form of grazing angle compensation assumes a flat bottom and a vehicle operating at a constant altitude. More advanced algorithms project the image onto terrain with relief which scales the frequencies in a more complicated manner.

A hologram codes the frequency and aspect information into two dimensions and is well suited for forming the above described map. A hologram can be thought of as the sum of all images over some range of angles. It requires less storage than a four dimensional representation and is ideal for correlation. Two holograms are correlated by multiplying their Fourier transforms and taking the inverse Fourier transform of the result. A hologram can be coherently correlated with a single image through the same process. Even though it is nearly impossible to correlate two sonar images it is straightforward to correlate two sonar holograms or a sonar hologram and a sonar image.

A holographic map is a collection of holograms that are suitable for navigation. Navigation is accomplished by correlating images or holograms with the holographic map. A holographic map can be a collection of distinct holograms a mosaicked hologram or some combination of the two. In all cases a holographic map is coherent.

In order to form a holographic map it is necessary to be able to form a hologram. To form a hologram coherent echoes from a scene have to be gathered over some range of angles points in the scene cannot be observed from only one aspect. Synthetic Aperture Sonars and Radars SAS s and SAR s are existing systems which form holograms although they are typically referred to as SAS or SAR images. Their images holograms are suitable for this type of mapping. Accordingly a holographic map consists of coherent imagery with well defined aspect and frequency content that can be used to estimate position.

Referring to there is shown a diagram illustrating grazing angle. The horizontal axis corresponds to the sea floor while the vertical axis is distance above the sea floor. The region with arcs defines the beam of sonar which is illustrated as the dot located at 0 10 . As illustrated in the spacing between peaks in the arriving sound waves gets closer together as the horizontal range increases.

For purposes herein grazing angle can be defined as the angle between the sound impinging on the sea floor and the sea floor itself. It is the angle between a ray connecting the sonar to a point on the sea floor and a ray tangent to the sea floor at that point. When looking at the horizon the grazing angle is zero when looking straight down the grazing angle is 90 degrees. On a flat bottom at a constant altitude grazing angle varies with range. At a constant horizontal range grazing angle changes as the vertical position of the sonar is varied. For a contoured bottom changes in the bottom slope can also affect the grazing angle.

In order to appreciate the holographic map an understanding of the frequency domain representation of a sonar image is desirable. Consider the case of a sonar image created in the image plane. The sonar transmits a signal with center frequency fand bandwidth f. Since the frequency varies from

If the same scene was imaged with a different sonar signal that lay outside the 20 40 kHz band the two images would not be correlated. This is because image correlation corresponds to frequency domain multiplication. The frequency domain extent of the annular region is important since it describes the range of frequencies that can be used with the map. Any frequencies that are not included in the map will be multiplied by zero during the correlation operation and will be of no use.

However only describes an image plane image. Image plane images correlate very poorly because geometric relationships are distorted. Two objects spaced 10 centimeters apart in range will be 10 cm apart in the image plane image when viewed on the horizon but only 7 cm apart when viewed at a grazing angle of 45 . Since the sound has to travel to the scene and back the scatterers would constructively reinforce a wavelength of 20 cm when viewed on the horizon but only 14 cm when viewed from 45 degrees.

By rescaling the image by the cosine of the grazing angle it is possible to shift the frequencies and create a grazing angle invariant image. However after rescaling the frequency band is range varying. This means that the annular region varies spatially. However this is acceptable.

What is desired is that all possible annular regions after grazing angle compensation contain a common annular region or a common set of spatial frequencies such that there are always some frequencies that can be used for correlation which are independent of range. After grazing angle compensation there will always be additional frequencies in the image which do not overlap at all ranges. These can be kept as they do not hurt the image or they can be filtered out. If they are kept images which are correlated from nearly the same position will have a higher correlation precision.

Those of skill in the art will recognize that grazing angle compensation typically breaks down as the grazing angle approaches 90 i.e. straight down to the sea floor. This results from the frequency being rescaled by dividing by the cosine of the angle. As the grazing angle approaches 90 the cosine approaches zero and the frequencies approach infinity directly under the sonar. Consequently there are only a limited range of angles which can be compensated for meaning that the sonar swath that is included in the map typically has a minimum and maximum grazing angle.

A well designed map has a frequency band that after grazing angle compensation describes all locations in the map. However this is not sufficient to guarantee correlation. The valid range of viewing aspects also must be defined.

If instead information about the target is gathered over a range of angles then an entire sector will contain information in the frequency domain. This sector when multiplied by another sector which overlaps will yield a non zero region corresponding to the overlap. This overlap defines the resolution of the correlation.

Accordingly a well designed map has both a well defined range of frequencies and aspects which describe all locations in the map. The map implicitly contains all possible images that can be created at those frequencies and aspects making it ideal for correlation based navigation.

The ideal holographic map has after grazing angle compensation a frequency domain extent with a fixed range of frequencies and a fixed range of aspect angles. This is ideal because holograms can be neatly combined to form the circular spectrums shown in . Closed aperture holograms with frequency content comparable to that shown in have the highest possible resolution for a given range of frequencies.

Most sonar transmitters do not transmit all frequencies over the same angles. Typically most transmitters have a constant aperture meaning that their beam pattern narrows as frequency increases i.e. the higher frequencies have a narrower range of angles and the lower frequencies a wider range of angles.

However by observing the targets over a wider range of angles for low frequencies and a narrower range of angles for high frequencies the aperture used for mapping is frequency varying. As it turns out these two effects conspire to result in a range invariant spatial resolution in mapping a target. This means in turn that spatial bandwidth in the sonar image may be independent of frequency.

The spectral representation shown in illustrates this effect. Both frequency bands shown in illustrate beam pattern narrowing as frequency increases. illustrates the beam pattern narrowing of a constant aperture sonar more clearly. The sonar for the hologram illustrated in observes the terrain from 30 to 30 with 20 40 kHz. However instead of fanning out along the 30 and 30 radial lines comparable to the holograms of at 40 kHz the hologram spans only from about 15 to 15 region designated with vertical hatching . If these sorts of holograms are combined to form larger apertures there will either be holes in the combined aperture at higher frequencies or significantly more overlap at lower frequencies.

Therefore a system which uses this style of map for navigation will need to account for the local aspect direction of the map. Where they appear in a globally referenced frequency domain will depend on the vehicle heading but unless a re acquisition sonar has an incredibly broad beam or can look in opposite directions at the same time it will only be able to correlate its imagery with one of the images at a time.

In order to be of use as a holographic map the frequency band of the image and the range of aspects of the image are defined at blocks and respectively such that they describe all locations in the holographic map. As previously described herein this map definition provides the criteria for correlating other images with the map.

Optionally a number of images can be formed as determined at block . If there is more than one image as determined at block the images can be combined block to increase the coverage area frequency band and or range of aspects of the holographic map. Combining can be in the form of overlaying images or mosaicking images.

Holographic maps have many applications. Primarily they are intended for use in holographic navigation. In holographic navigation terrain is recognized using real or synthetic aperture images. Holographic maps also may be of use for multi image focusing. The simplest case of this involves two holograms each constituting a separate map of the area.

First the individual signals used to form the second image are correlated with the first image to estimate their location. This is done to best estimate the gaps between the real apertures. This error can be corrected for in the second hologram. Then the signals used to create the first hologram are compared with the new second image the array gaps are estimated and the first hologram SAS image is corrected. Then if desired they can be combined or mosaicked.

Additional applications include multi pass interferometry wherein phase differences between two holograms formed from different locations are used to determine bottom relief. Also a holographic map is ideal for change detection due to its correlation properties. A prior hologram can be correlated against one or more new images or holograms and regions that exhibit sudden de correlation can be flagged.

Additionally holographic maps can be used for map maintenance. In this scenario a high resolution sonar system such as a synthetic aperture sonar forms a hologram of terrain in an area of interest. By correlating real aperture sonar signals with the hologram maintenance robots are able to position themselves with high accuracy. These well positioned robots then use their signals to re image the terrain or add to the existing scene. If a change is detected the robots can form synthetic apertures possibly closed apertures around the object of interest to form the highest quality imagery to best aid a decision maker.

Obviously many modifications and variations of the present invention may become apparent in light of the above teachings. It will be understood that many additional changes in details materials and arrangements of parts which have been described herein and illustrated in order to explain the nature of the invention may be made by those skilled in the art.

