---

title: Apparatus and method for grazing angle independent signal detection
abstract: 



url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08374054&OS=08374054&RS=08374054
owner: The United States of America as represented by the Secretary of the Navy
number: 08374054
owner_city: Washington
owner_country: US
publication_date: 20100517
---
This application has the priority of U.S. Provisional Patent Application Ser. No. 61 216 566 filed May 18 2009.

The invention described herein may be manufactured and used by or for the Government of the United States of America for governmental purposes without the payment of any royalties thereon or therefor.

A basic function of radiative systems such as sonar or radar is to reliably correlate echoes received from an object scanned from different locations. This permits identification classification or imaging of objects or surfaces examples of which might be in a marine environment sea shells pebbles rocks shoals patches of seafloor terrain naval mines undersea pipes or cables or sunken vessels. Unfortunately echo signature varies with the angle of incidence or grazing angle at which the object is scanned which means that echoes received back from the same object at different grazing angles will correlate poorly. In particular increasing grazing angle progressively foreshortens the apparent size of an object along the line of sight between the sonar radar generator and the object. This in turn changes the frequency of radiation necessary to duplicate the signature of the object requiring different frequencies for different grazing angles.

Accordingly an object of the invention is to permit good correlation between echoes returned at different grazing angles.

Another object is to permit a priori identification of the bandwidth necessary to recognize all physical objects of a given size at a given set of grazing angles.

Another object is to permit mapping of the spectrum of an echo from one surface at one grazing angle to the corresponding spectrum for that echo at a second grazing angle to permit good correlation with a pre existing echo from the same surface at the second grazing angle.

In accordance with these and other objects made apparent hereinafter the invention concerns an apparatus and method in which a surface or object is irradiated at a known grazing angle so as to produce detectable echoes. The spectrum detected at one grazing angle is related to a corresponding spectrum for the echo at second grazing angle by the relationship 

These and other objects are further understood from the following detailed description of particular embodiments of the invention. It is understood however that the invention is capable of extended application beyond the precise details of these embodiments. Changes and modifications can be made to the embodiments that do not affect the spirit of the invention nor exceed its scope as expressed in the appended claims. The embodiments are described with particular reference to the accompanying drawings wherein 

With reference to the drawing figures wherein like numbers indicate like parts throughout the several views shows an embodiment of the invention employing sonar. A side scanning sonar is mounted on ship disposed on marine surface above bottom and generates a broad beam sonar signal of azimuthal width . Beam irradiates a broad swath of bottom with a pulse of known spectral content and receives back echoes here in the form of complex pressure intensities from bottom and preferably records the echoes for example by digitally sampling the echoes and recording the samples on a digital storage device for processing. Included among these echoes are returns from patches of bottom which have respective lines of sight to sonar at azimuthal angles and . As illustrated in bottom patches are at different distances from sonar and at different orientations i.e. different grazing angles thereto. These patches can be any radiative feature on bottom for example pebbles sea shells a sandy bottom or in the case of patch a reef or shoal extending from bottom .

For two points at respective distances Rand Rfrom a radiator such as sonar the difference t in round trip times of radiation to and from the two points is 2 where c is signal velocity here the speed of sound in water for radar the speed of light in free space. In the round trip difference between echoes received at sonar from opposite ends of bottom patch is the distance wavefront travels after it hits end until it hits end i.e. 2 0 Cos 

Any sinusoidal signal of frequency fand wavelength obeys the relationship where is signal wavelength. To produce an echo capable of characterizing the sea floor at spatial frequency for wavelength one must irradiate the sea floor with a signal containing wavelength which for the embodiment of is 

This means that in order to characterize the sea floor at spatial frequency fand at a grazing angle one must irradiate the sea floor with a signal whose spectrum contains temporal frequency f or alternatively if a temporal frequency f can characterize the sea floor at 0 incidence at incidence one needs a spectrum containing at least one spatial frequency f .

In bottom slopes at an angle to horizontal and has a bottom patch extending between points and and of dimension L . Wavefront first strikes the patch at when wavefront is still a distance L Cos from opposite end as seen in the diagram in making the effective grazing angle in contrast to the grazing angle of in .

From the foregoing one can see that a knowledge of grazing angle permits a user aboard ship to correct echo signatures returned from an artifact on bottom at different grazing angles so that the echoes will correlate well. This in turn permits a wide range of applications. For example survey data describing the contour of a marine bottom is frequently available and storable in a computer aboard ship . Ship can then send out a broadbeam sonar pulse and record the echoes returned from bottom as a function of time typically by digitally sampling the echoes and storing the samples in computer memory. This permits formation of a reference data base that relates echo signature to both locations on bottom as well as grazing angle. A later ship that similarly scans bottom albeit from a different location and hence different grazing angles can use the knowledge of its own position to correct the echoes it receives back for differences in grazing angle from the reference data base. One simple way to do this is to use the above equations to transform the spectrum of an echo of interest as follows 

In practice a large range of vehicles could advantageously use the foregoing scheme for example autonomous underwater vehicles AUVs or submarines or other submersibles. So too could unmanned aerial vehicles UAVs or airplanes helicopters or spacecraft with radars like that currently on the Space Shuttle or satellites.

In the foregoing embodiments the natural reference for grazing angle 0 is the horizon. This however is a consequence of the particular applications of the embodiments. Ultimately the selection of reference direction is arbitrary so long as all subsequent measurements and data are referenced to the same 0 0 direction or mapped thereto using the foregoing teachings.

The invention has been described in what is considered to be the most practical and preferred embodiments. It is recognized however that obvious modifications to these embodiments may occur to those with skill in this art. As an example the foregoing discusses embodiments concerning sonar and radar but the invention pertains to any radiation that can irradiate a surface so as to produce detectable returns. Accordingly the scope of the invention is to be discerned from reference to the appended claims wherein 

