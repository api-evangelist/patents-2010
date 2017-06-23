---

title: Method of processing images captured by digital camera to reduce distortion
abstract: A method of processing, in a digital camera, an image captured by the camera is provided, which includes locating faces within the captured image by detecting regions of contiguous color which map a hue, saturation and value of the range of human face colors and passing the detected regions through heuristic tests which produce a resulting probability of a face being present in the image, locating eyes of the located faces, and determining if the captured image of the located eyes has been modified by the act of capturing the image. If the image has been modified any unwanted distortions of the located eyes are located in the captured image that have occurred as a result of the act of capturing the image, and the captured image is modified to at least reduce the effect of the unwanted distortions and to produce a modified image.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08013905&OS=08013905&RS=08013905
owner: Silverbrook Research Pty Ltd
number: 08013905
owner_city: Balmain, New South Wales
owner_country: AU
publication_date: 20100423
---
This is a Continuation of U.S. application Ser. No. 10 636 224 filed Aug. 8 2003 which is a Continuation of U.S. application Ser. No. 09 112 742 filed on Jul. 10 1998. The following Australian provisional patent applications are hereby incorporated by cross reference. For the purposes of location and identification US patent applications identified by their US patent application serial numbers USSN are listed alongside the Australian applications from which the US patent applications claim the right of priority.

The present invention relates to an image processing method and apparatus and in particular discloses a process for correcting for flash induced distortions in a Digital Image Camera.

The present invention further relates to the field of digital image processing and in particular the field of processing of images taken via a digital camera.

Recently digital cameras have become increasingly popular. These cameras normally operate by means of imaging a desired image utilizing a charge coupled device CCD array and storing the imaged scene on an electronic storage medium for later down loading onto a computer system for subsequent manipulation and printing out. Normally when utilizing a computer system to print out an image sophisticated software may be available to manipulate the image in accordance with requirements.

Unfortunately such systems require significant post processing of a captured image and normally present the image in an orientation in which it was taken relying on the post processing process to perform any necessary or required modifications of the captured image. Further much of the environmental information available when the picture was taken is lost.

It is an object of the present invention to utilize flash information in a digital image camera for processing digital images.

In accordance with a first aspect of the present invention there is provided a method of processing an image captured utilizing a digital camera and a flash said method comprising the steps of 

In accordance with the second aspect of the present invention there is provided a digital camera having reduced flash distortion effects on captured images comprising 

In another broad form the invention includes a method of processing in a digital camera an image captured by the camera the method including 

Unwanted distortions may include red eye effects reflections in the captured image and modification of the colors captured.

At least one predetermined image may be added to the captured image if it is determined that the image has or has not been modified by the act of capture.

The at least one onboard processor may be configured to determine if a flash was used in capturing the image.

Unwanted distortions may include red eye effects reflections in the captured image and modification of the colors captured.

At least one predetermined image may be added to the captured image by the at least one processor if it is determined that the image has or has not been modified by the act of capture.

Preferably the camera includes a display upon which modified and or unmodified images may be displayed.

The preferred embodiment is preferably implemented through suitable programming of a hand held camera device such as that described in patent application having applicant s reference ART01 U.S. Ser. No. 09 113 060 filed concurrently herewith by the present applicant the content of which is hereby specifically incorporated by cross reference.

The aforementioned patent specification discloses a camera system hereinafter known as an Artcam type camera wherein sensed images can be directly printed out by an Artcam portable camera unit. Further the aforementioned specification discloses means and methods for performing various manipulations on images captured by the camera sensing device leading to the production of various effects in any output image. The manipulations are disclosed to be highly flexible in nature and can be implemented through the insertion into the Artcam of cards having encoded thereon various instructions for the manipulation of images the cards hereinafter being known as Artcards. The Artcam further has significant onboard processing power in an Artcam Central Processor unit ACP that is interconnected to a memory device for the storage of important data and images.

As disclosed in U.S. Ser. No. 09 113 060 issued as U.S. Pat. No. 6 750 901 the Artcards contain on one surface encoded information and on the other surface contain an image distorted by the particular effect produced by the Artcard. The Artcard is inserted in an Artcard reader in the side of camera and upon insertion results in an output image being distorted in the same manner as the distortion appearing on the surface of Artcard.

One important form of processing is the removal of red eye effects that can result in captured images as result of utilization of a flash.

Turning now to in the preferred embodiment the image as originally captured by the CCD device is subject to a processing step when a flash has been utilized so as to produce a processed output image for printing.

Turning now to there is illustrated in more detail one particular image processing algorithm which can be utilized when a flash has been utilized in capturing an image by a CCD device. The algorithm is preferably only utilized when a flash was used 11 to take the picture captured by the CCD. The purpose of the algorithm is to reduce the image effects due to the utilization of the flash. Such image effects can include the well known red eye effect of individual eyes appearing red in a photographic image. Other effects such as flash reflections off reflective surfaces can also be separately processed utilizing other algorithms. The first step in eliminating red eye effects in the images is to determine the faces within the image. The face detection process can proceed by detecting regions of contiguous color which map the hue saturation and value HSV of the range of human face colors under the range of normal lighting encountered after any other applied image enhancements or hue corrections. The detected regions can then be passed through various heuristic tests including determining the presence of eyes mouth overall shape and overlap. The heuristic tests produce a resulting probability of a face being present in the image and where this is above a threshold a face is determined to be located in the image.

Once a face has been determined within an image the eyes are located within the face in step . Each eye in step is then independently processed to determine its special range of colors so as determine whether a red eye removal process is required instep .

If the red eye removal process is required a retouching algorithm is applied to the eye area so as to reduce the red saturation whilst simultaneously not introducing any discontinuities or likely artifacts in the output image. Of course many different techniques could be utilized including a form of Gaussian alteration around a central point of the eye. Finally the image is written in step in its updated form back to the memory device of the ACP.

Preferably any other retouching algorithms including remapping colors affected by the spectral nature of the flashlight are also utilized at this time.

Alternatively the Artcard inserted could have a number of manipulations applied to the image that are specific to the flash setting. For example clip arts containing candles light globes etc could be inserted in an image utilizing a flash and large suns inserted in non flash images.

It would be appreciated by a person skilled in the art that numerous variations and or modifications may be made to the present invention as shown in the specific embodiment without departing from the spirit or scope of the invention as broadly described. The present embodiment is therefore to be considered in all respects to be illustrative and not restrictive.

The embodiments of the invention use an ink jet printer type device. Of course many different devices could be used. However presently popular ink jet printing technologies are unlikely to be suitable.

The most significant problem with thermal ink jet is power consumption. This is approximately 100 times that required for high speed and stems from the energy inefficient means of drop ejection. This involves the rapid boiling of water to produce a vapor bubble that expels the ink. Water has a very high heat capacity and must be superheated in thermal ink jet applications. This leads to an efficiency of around 0.02 from electricity input to drop momentum and increased surface area out.

The most significant problem with piezoelectric ink jet is size and cost. Piezoelectric crystals have a very small deflection at reasonable drive voltages and therefore require a large area for each nozzle. Also each piezoelectric actuator must be connected to its drive circuit on a separate substrate. This is not a significant problem at the current limit of around 300 nozzles per print head but is a major impediment to the fabrication of pagewidth print heads with 19 200 nozzles.

Ideally the ink jet technologies used meet the stringent requirements of in camera digital color printing and other high quality high speed low cost printing applications. To meet the requirements of digital photography new ink jet technologies have been created. The target features include 

All of these features can be met or exceeded by the ink jet systems described below with differing levels of difficulty. Forty five different ink jet technologies have been developed by the Assignee to give a wide range of choices for high volume manufacture. These technologies form part of separate applications assigned to the present Assignee as set out in the table under the heading Cross References to Related Applications.

The ink jet designs shown here are suitable for a wide range of digital printing systems from battery powered one time use digital cameras through to desktop and network printers and through to commercial printing systems

For ease of manufacture using standard process equipment the print head is designed to be a monolithic 0.5 micron CMOS chip with MEMS post processing. For color photographic applications the print head is 100 mm long with a width that depends upon the ink jet type. The smallest print head designed is IJ38 which is 0.35 mm wide giving a chip area of 35 square mm. The print heads each contain 19 200 nozzles plus data and control circuitry.

Ink is supplied to the back of the print head by injection molded plastic ink channels. The molding requires 50 micron features which can be created using a lithographically micromachined insert in a standard injection molding tool. Ink flows through holes etched through the wafer to the nozzle chambers fabricated on the front surface of the wafer. The print head is connected to the camera circuitry by tape automated bonding.

Eleven important characteristics of the fundamental operation of individual ink jet nozzles have been identified. These characteristics are largely orthogonal and so can be elucidated as an eleven dimensional matrix. Most of the eleven axes of this matrix include entries developed by the present assignee.

The complete eleven dimensional table represented by these axes contains 36.9 billion possible configurations of ink jet nozzle. While not all of the possible combinations result in a viable ink jet technology many million configurations are viable. It is clearly impractical to elucidate all of the possible configurations. Instead certain ink jet types have been investigated in detail. These are designated IJ01 to IJ45 which match the docket numbers in the table under the heading Cross References to Relation Applications.

Other ink jet configurations can readily be derived from these forty five examples by substituting alternative configurations along one or more of the 11 axes. Most of the IJ01 to IJ45 examples can be made into ink jet print heads with characteristics superior to any currently available ink jet technology.

Where there are prior art examples known to the inventor one or more of these examples are listed in the examples column of the tables below. The IJ01 to IJ45 series are also listed in the examples column. In some cases a print technology may be listed more than once in a table where it shares characteristics with more than one entry.

Suitable applications for the ink jet technologies include Home printers Office network printers Short run digital printers Commercial print systems Fabric printers Pocket printers Internet WWW printers Video printers Medical imaging Wide format printers Notebook PC printers Fax machines Industrial printing systems Photocopiers Photographic minilabs etc.

The information associated with the aforementioned 11 dimensional matrix are set out in the following tables.

