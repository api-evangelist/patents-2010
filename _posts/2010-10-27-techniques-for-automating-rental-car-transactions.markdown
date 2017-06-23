---

title: Techniques for automating rental car transactions
abstract: A customer uses a wireless portable device to interact with a remote cloud-based car rental service. Details at check in are recorded and the customer is authorized to take possession of the car. At checkout, additional details are noted, a receipt is produced, and the customer leaves the car at the car facility. The check-in and checkout process can be achieved without any car rental attendant. That is, the customer via the wireless portable device and with the assistance of the remote cloud-based car rental service completely achieves check in and checkout for a car rental.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08912883&OS=08912883&RS=08912883
owner: NCR Corporation
number: 08912883
owner_city: Duluth
owner_country: US
publication_date: 20101027
---
Consumers are increasingly using kiosks to conduct business with enterprises. The kiosks come in a variety of sizes and are used for a variety of purposes. Some kiosks are drive through such as fast food establishments pharmacies banks and the like. Other kiosks are stationary located in gas stations airlines grocery stores department stores and the like.

In addition to this level automation transforming the industry consumers are performing more and more transactions using their cell or smart phones. For example consumers can not use bar codes or QR codes to check in through airport security make purchases at point of sale terminals via their phones check in to sporting events and others.

One area that has really not experienced much automation for transactions via phones is the car rental industry.

One reason for this is that the traditional car rental business processes must tradeoff between customer convenience rental car company risk and rental car company labor costs.

In attended environments human attendants are typically used to perform simple tasks during check out and check in of rental cars such as verification of the Vehicle Identification Number VIN mileage fuel level and checking for damage before and after a rental. This is expensive for the rental company and can be slow for customers as they have to wait for an available attendant to check in and checkout.

In unattended environments lack of human verification can lead to disputes between rental car companies and customers as a lack of data acquisition at the time of rental or return creates a situation where the facts from the customer and rental company perspective can be at odds. This can occur as a result of undocumented damage incorrectly documented mileage or fuel level.

In various embodiments techniques for automated rental car transactions are presented. According to an embodiment a method for automated a rental car check in procedure is provided.

Specifically a customer is instructed via a wireless portable device of the customer as to a location for taking possession of a car at a car rental facility. Next a Vehicle Identification Number VIN for the car being rented is received back from the wireless portable device. Then images or a video of items for the car defined by a car rental agreement are acquired from the wireless portable device. Finally a confirmation is sent to the wireless portable device indicating that the customer can leave the car rental facility with the car to complete a car rental checkout transaction.

In an embodiment the network is the Internet. In another embodiment the network is a cellular network. It may also be that the network uses both the Internet and a cellular network. In an embodiment the network is a private network provided via WiFi at the car rental facility and provided for purposes of securely accessing the car rental checkout service.

In an embodiment the car rental checkout service executes on one or more processors over the network in a cloud processing environment.

Cloud computing is often defined as computing capabilities that provide an abstraction between computing resources and the underlying technical architecture e.g. servers storage networks enabling convenient on demand network access to a shared pool of configurable computing resources that can be rapidly provisioned and released with minimal management effort or service provider interaction. From the perspective of the user where and how a computing resource is obtained is irrelevant and is transparent in cloud computing.

As used herein a cloud processing environment refers to a set of cooperating computing resources such as machines storage software libraries software systems etc. that form a logical computing infrastructure.

So the car rental checkout service is cloud or server based and interacts with a customer s cell phone smart phone tablet Personal Digital Assistant PDA and other smart portable devices of the customer. These devices communicate a variety of information to the car rental checkout service for purposes of automating the car rental checkout process for a car rental company in the manners described herein and below.

In some cases the customer s phone may include an application often referred to as an app in smart phone parlance that interacts with the car rental checkout service. An example of such an app is described below with reference to the .

As an overview of the embodiments that are described more particularly with reference to the consider the following scenario that utilizes the car rental checkout service.

A customer is directed to a specific car or row of cars by the mobile application on the customer s phone and communicating with the car rental checkout service. It may also be that the customer has an itinerary already that indicates where the customer s car is located parking space number . The car rental checkout service instructs the customer to frame the VIN on the car in a receptacle displayed by the mobile app. Alternatively a text message sent by the car rental checkout service tells the customer to active the customer s bar code scanner on phone and to the scan the VIN. It may also be that a picture is taken if the phone does not have a native bar code scanner.

At this time the mobile app on the phone or the car rental checkout service recognizes either the barcode or characters that comprise the VIN and records that the customer is taking possession of this car particular car with this VIN. Here the mobile app can send the VIN to the car rental checkout service or the customer can be instructed to send an image of the VIN to a particular number monitored by the car rental checkout service.

The car rental checkout service then remotely unlocks the car through OnStar or similar auto management infrastructure based on verification of the reservation.

Next the customer is instructed via the mobile app or text messages sent by the car rental checkout service to perform a walk around of the car with the camera of the phone framing the car as a 360 degree video or a as series of still images. The app or car rental checkout service stores the images location and time as a video record of any pre existing damage to the car. In the case of the app storing the app sends to the car rental checkout service on behalf of the customer. Without the app the customer is instructed to send to a number monitored by the car rental checkout service or instructed to upload to a predefined site monitored by the car rental checkout service.

Next the customer is instructed via text messages or the app in communication with the car rental checkout service to start the car and frame the dash board in the app provided receptacle or using the phone s camera application . The mobile app or the car rental checkout service recognizes the car s fuel gauge and odometer readings through optical recognition software and notes these values along with the location and time of the photo and confirms the value with the customer. In the case where there is no mobile app the car rental checkout service instructs the customer via a text message to send the image of the gauges via a text to a phone number monitored by the car rental checkout service or to upload the image of the gauges to a site monitored by the car rental checkout service.

For added security the customer may also be asked to enter via an app or via a text message sent the license number of the customer.

Optionally as well a QR code or pass code may be sent by the car rental checkout service to the phone of the customer. The QR code can be scanned at an exit kiosk of the car rental facility for the customer to exist a locked gate or the customer enters a pass code at the exit kiosk for the locked gate to unlock. It is noted that other imaged based tags may be provided besides just a QR code such as but not limited to Aztec DataMatrix MaxiCode and others. Thus any imaged based tags can be used.

The above description provides a sample overview of some of the embodiments capable with the teachings presented herein. The actions of the mobile app or actions initiated by the customer via a smart wireless mobile device are described below with reference to the . The car rental checkout service is described now with reference to the . That is the processing actions of the car rental checkout service are described in the as it interacts with either a mobile app on the customer s portable device or as it interacts directly with existing features of the customer s portable device.

At the car rental checkout service instructs a customer via a wireless portable device such as a smart phone cell phone tablet PDA etc. of the customer to a location for taking possession of a car at a car rental facility. This instruction can occur in a variety of manners.

For example at the car rental checkout service sends a text message with the location for the car to the wireless portable device after accessing a car rental reservation for the customer.

In another situation at the car rental checkout service sends the location after accessing a car rental reservation for the customer to a mobile app processing on the wireless portable device. This may entail consulting a car rental reservation system or it may entail accessing a registered itinerary associated with the customer having the car rental reservation.

In yet another case at the car rental checkout service sends directions to the wireless portable device to communicate to the customer that the customer is to send the VIN for the car at the location back to the car rental checkout service. Examples of what format the VIN is sent in and how it is sent from the wireless portable device was presented above and some of these are also discussed below.

At the car rental checkout service receives from the wireless portable device a VIN for the car. Again this can occur in a variety of manners.

For example at the car rental checkout service obtains the VIN as an image which the car rental checkout service then performs Optical Character Recognition OCR on the image for purposes of acquiring the serial numbers for the VIN which uniquely identifies the car.

As discussed above it may also be that a mobile app on the wireless portable device of the customer performs the OCR on behalf of the car rental checkout service and sends the serial numbers over the network to the car rental checkout service.

Again it should also be noted that the VIN may be in the form of a bar code that permits a bar code scanner and reader on the wireless portable device to scan and read and then send to the car rental checkout service. The mobile app if one exists can also be equipped with a bar code reader or scanner and can likewise send to the car rental checkout service.

Continuing with the embodiment of and at the car rental checkout service sends directions to an automotive management system such as OnStar and others to remotely unlock the car for the customer at the location of the car rental facility. Here the keys for the car are in the ignition or in the glove box or some other location within the car that the customer is informed of once the car is unlocked.

At the car rental checkout service acquires from the wireless portable device images or video of items for the car defined by a car rental agreement. Again these directions can be in the form of text messages to the wireless portable device or via an Application Programming Interface API set of commands or messages send to a mobile app processing on the wireless portable device.

According to an embodiment at the car rental checkout service sends directions to the wireless portable device to inform the customer to obtain the images or video for an exterior of the car and for dashboard readings of gauges fuel gauge mileage odometer etc. inside the car in accordance with the car rental agreement. The exterior images or video is a 360 degree view of the car.

In an embodiment at the car rental checkout service records the images or video to establish a record for the car rental transaction between the car rental company and the customer. If a mobile app exists it may automatically retain the images for the customer on the wireless portable device as well should a dispute about preexisting damage arise when the customer checks the car back in after the car rental period. Alternatively the customer can be informed via a text message to the wireless portable device to retain the images or video for the customers on records should a later dispute arise.

Continuing with the embodiment of and at the car rental checkout service sends the record to a car rental management system to obtain confirmation details for a confirmation permitting the customer to exit the car rental facility with the car.

At the car rental checkout service sends to the wireless portable device a confirmation that indicates that the customer can now leave the car rental facility with the car to complete the car rental checkout transaction.

According to an embodiment at the car rental checkout service provides the confirmation with a pass code a bar code a QR code or other image based tags to the wireless portable device that the customer is to use to exit the car rental facility with the car at an exit kiosk of the car rental facility.

It is now apparent how an entirely unmanned car rental facility can be configured using the techniques described herein above and below below describing the automated check in procedures . This is entirely automated. For security a sole security guard can exist at the car rental facility or a minimal level of staff present to clean and prep the cars and assist customers with questions etc. But a substantial amount of car rental staff can be reduced with the automated techniques described herein. The staff reduced could be used for purposes of opening new car rental facilities that were not previously economically feasible for a car rental company. So the same amount of staff that exists today can be used to support more facilities to enhance revenue while maintaining expenses.

In an embodiment the network is the Internet. In another case the network is a cellular network. It may also be that the network uses both the Internet and a cellular network. In an embodiment the network is a private network provided via WiFi at the car rental facility and provided for purposes of securely accessing the car rental check in service.

The car rental check in service again describes the processing actions of the car rental check in service from the perspective of the server of the cloud processing environment. The processing is associated with the car rental check in process whereas the method of the focused on the car rental checkout process.

Again a brief overview of some of the embodiments that are provided by the car rental check in service is provided first before specific discussion of the automated car rental check in process is presented.

The customer uses the mobile app described below with reference to the or receives instructions from the car rental check in service to indicate that he she is now returning the car. The customer is instructed to start the car and take a picture of the dash board in the. The mobile application or car rental check in service recognizes the car s fuel gauge and odometer readings through optical recognition software and notes these values along with the location and time of the photo and confirms the values with the customer.

Next the customer is instructed to perform a walk around of the car with the camera of the customer s wireless portable device framing the car as a 360 degree video or as a series of still images. The app or server stores the images location and time as a video record of any new damage to the car.

Finally the customer is instructed as to where to return keys or whether to lock them in the car and then instructed to frame the VIN in a receptacle displayed by the app or instructed to do this via the camera app of the portable wireless device. At this time the mobile app or server recognizes either the barcode or characters that comprise the VIN and records that the customer has returned this car. As noted above with the overview presented with the it may also be that the mobile app scans the VIN itself using a barcode scanner of the app or the customer uses a bar code scanner native to the portable wireless device.

Optionally the car rental check in service remotely locks the car through the auto management infrastructure completing the transaction.

The car rental check in service then transmits an electronic receipt to the app completing the customer s rental. The car rental check in service can also send the receipt as a text message or email to the wireless portable device of the customer.

Again the describes the processing of the car rental check in service from the cloud processing environment and the interactions from the wireless portable device can occur via a customized mobile app or can occur via interactions between the customer via the wireless portable device and the car rental check in service with the customer and the car rental check in service using native features of the wireless portable device.

At the car rental check in service receives a VIN from a wireless portable device cell phone smart phone tablet PDA etc. of a customer indicating that the customer is at the car rental facility to check in a car associated with a car rental agreement.

According to an embodiment at the car rental check in service obtains the VIN as an image or a barcode reading from the wireless portable device. Again this can be sent via text message or uploaded to a site by the customer via the wireless portable device or this can be sent by a mobile app processing on the wireless portable device and communicating with the car rental check in service over the network.

In an embodiment at the car rental check in service sends directions to the wireless portable device that defines the items for which the images or the video are to be taken from the car.

So at the car rental check in service obtains from the wireless portable device the images or video of the items for the car which are defined by a car rental agreement.

According to an embodiment at the car rental check in service detects excess miles beyond that which was defined in the car rental agreement or detects lower fuel values beyond what was defined in the car rental agreement.

Continuing with the embodiment of and at the car rental check in service increases a set fee by a predefined amount based on the excess miles and or based the lower fuel values.

Continuing with the embodiment of and at the car rental check in service acquires payment information to obtain payment from the customer via the wireless portable device. The payment is for a set fee pursuant to the rental agreement plus the predefined amount when the set fee was not previously obtained. Alternatively the payment is for the predefined amount when the set fee was previously obtained from the customer.

In some cases at the car rental check in service verifies the items with expected values or conditions. Images or video associated with the car for the exterior exterior items may include minor damage that is subsequently ascertained by manual inspection of the photos. In which case the customer is subsequently contacted by the car rental company for payment associated with the minor damages. In other cases more severe damages may be detected via automated image processing that compares the current sent images or video with prior retained images or video acquired at checkout . In these situations an agent of the car rental company may be automatically contacted to immediately contact the customer or to notify an agent at the car rental facility to contact the customer to discuss the situation and inspect the vehicle.

At the car rental check in service instructs the wireless portable device to inform the customer on actions to perform to complete a car rental transaction.

For example at the car rental check in service identifies the actions as procedures for where the keys are to be placed before the customer exits the car rental facility such as a drop box or as discussed below .

Continuing with the embodiment at and at the car rental check in service provides the actions as directions for placing the keys in the ignition of the car with the car turned off and having the customer lock all doors to the car. Alternatively the car rental check in service provides the actions as directions for placing the keys in the ignition and then the car rental check in service instructs an automotive management system such as OnStar and others to remotely lock the doors to the car.

It should now be apparent how car rental checkouts and check ins can be entirely automated using the cloud based services described herein in connection with a customer s wireless portable device.

The rental car rental transaction system includes a cloud based automated car rental service and a mobile app . Each of these and their interactions with one another will now be discussed in turn.

One or more processors in a cloud processing environment are configured to execute the cloud based automated car rental service . The cloud based automated car rental service is resides and is programmed in a non transitory computer readable storage medium and again executes on the one or more processors of the cloud processing environment. Example processing features associated with the cloud based automated car rental service were presented above in detail with reference to the .

The cloud based automated car rental service is configured to interact with the mobile app that processes on a customer s wireless portable device cell phone smart phone tablet PDA etc. . This is done for purposes of automating a car rental check in transaction and a car rental checkout transaction without the aid of car rental personnel as described in detail above with reference to the methods and of the respectively.

The mobile app resides within and is programmed in a non transitory computer readable medium and is adapted to be downloaded and installed on a wireless portable device of a customer such as a cellular phone a smart phone a tablet a PDA and the like. The wireless portable device includes one or more processors that execute the mobile app . Some features of the mobile app were presented in the overview sections discussed above with reference to the .

The mobile app is configured to acquire details requested by the cloud based automated car rental service for assisting the customer via instructions obtained from the cloud based automated car rental service and via automated features and interfaces of the mobile app . Such automated features can include but are not limited to retaining images video car rental agreements etc. for the customer on the customer s wireless portable device. Such interfaces can include but are not limited to screen interfaces on the wireless portable device that help gather details via customer driven screens and the like and that help instruct the customer as to what is needed to satisfy the cloud based automated car rental service .

In an embodiment the mobile app is downloaded from a mobile app store by the customer and installed on the wireless portable device prior to transacting with the cloud based automated car rental service . The download may be free or a small fee may be charged for the download.

The above description is illustrative and not restrictive. Many other embodiments will be apparent to those of skill in the art upon reviewing the above description. The scope of embodiments should therefore be determined with reference to the appended claims along with the full scope of equivalents to which such claims are entitled.

The Abstract is provided to comply with 37 C.F.R. 1.72 b and will allow the reader to quickly ascertain the nature and gist of the technical disclosure. It is submitted with the understanding that it will not be used to interpret or limit the scope or meaning of the claims.

In the foregoing description of the embodiments various features are grouped together in a single embodiment for the purpose of streamlining the disclosure. This method of disclosure is not to be interpreted as reflecting that the claimed embodiments have more features than are expressly recited in each claim. Rather as the following claims reflect inventive subject matter lies in less than all features of a single disclosed embodiment. Thus the following claims are hereby incorporated into the Description of the Embodiments with each claim standing on its own as a separate exemplary embodiment.

