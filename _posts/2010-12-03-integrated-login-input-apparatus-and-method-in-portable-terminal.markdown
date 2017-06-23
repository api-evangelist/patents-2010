---

title: Integrated login input apparatus and method in portable terminal
abstract: An apparatus and method in a portable terminal for an integrated login input are provided. The integrated login input method includes, displaying a plurality of images during registration of a password, displaying a plurality of images, selecting one of the plurality of displayed images, determining a coordinate system according to an encryption level to be set for the password and applying the determined coordinate system to the selected image, changing a tilt of the portable terminal by an angle and detecting the changed tilt, receiving a selection of the user on a region of the selected image, and combining the detected tilt and coordinates corresponding to the region where the user's selection is generated and registering the combination as the password.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09053314&OS=09053314&RS=09053314
owner: Samsung Electronics Co., Ltd.
number: 09053314
owner_city: Suwon-si
owner_country: KR
publication_date: 20101203
---
This application claims the benefit under 35 U.S.C. 119 a of a Korean patent application filed in the Korean Intellectual Property Office on Dec. 11 2009 and assigned Serial No. 10 2009 123192 the entire disclosure of which is hereby incorporated by reference.

The present invention relates to an apparatus and a method for inputting information into a portable terminal. More particularly the present invention relates to an integrated login input apparatus and method in a portable terminal by which a password having a high encryption level is set by using a coordinate system and a tilt sensor that is included in the portable terminal.

When a personalized Internet service such as a Social Networking Service SNS is used in a portable terminal a basic login process is required to ensure a user s privacy. However the login process results in an inconvenience to the user when there are multiple login processes for an SNS that becomes more finely subdivided.

To enter a password in the login process a keyboard for a Personal Computer PC a QWERTY board for a Personal Digital Assistant PDA terminal a keypad button for a portable terminal and the like are generally used. However if a Liquid Crystal Display LCD is provided for any of those devices it typically has a smaller size such that when the LCD is also used as a touch screen for input an input error is very likely to occur due to the small size and if touch sensitivity is not good. To address the foregoing problem an integrated password scheme using an auto fill function has been proposed.

Referring to a portable terminal may be provided with a 3 set keyboard for entering a password. However password input using a 3 set keyboard is difficult as it requires many keystrokes. Referring to during an authentication process a user may be inconvenienced by having to input not only a password but also a username. Moreover the user may be required to answer additional questions regarding the saving of and use of the password in the future. Referring to a user may input a password using a single key such as a numeric key. Input of a single key is easy when used for a one digit password. However because the keyboard has a limited number of keys the degree of encryption is reduced in comparison to an input number.

Moreover in an input scheme using motion input detected by a motion detector of a portable terminal users hand shakes may vary from user to user so that the input scheme may have an error according to the slight differences in degree of vibration. In this case when a number of input attempts is higher than a predetermined level the multiple inputs may cause a lock down of the device. Thus a scheme having large input variation such as the motion input scheme is not suitable for password input requiring accuracy.

An aspect of the present invention is to address at least the above mentioned problems and or disadvantages and to provide at least the advantages described below. Accordingly an aspect of the present invention is to change a tilt of a portable terminal to a user desired angle and then display a particular image to which a predetermined coordinate system is applied on a display screen having a touch screen such that a user s touch input on a predetermined region of the display screen and the tilt of the portable terminal are sensed for password registration.

According to an aspect of the present invention an integrated login input method in a portable terminal is provided. The integrated login input method includes displaying a plurality of images during registration of a password selecting one of the plurality of displayed images determining a coordinate system according to an encryption level to be set for the password and applying the determined coordinate system to the selected image changing a tilt of the portable terminal by an angle and detecting the changed tilt receiving a selection of the user on a region of the selected image and combining the detected tilt and coordinates corresponding to the region where the user s selection is generated and registering the combination as the password.

According to another aspect of the present invention an integrated login input apparatus in a portable terminal is provided. The integrated login input apparatus includes a tilt sensor for acquiring a tilt according to a tilt state of the portable terminal and a controller for applying a coordinate system to an image selected through a display unit of the portable terminal on the display unit for detecting the tilt acquired by the tilt sensor and coordinates corresponding to a region of the displayed image selected by a user for combining the tilt and the coordinates to store the combination as a password and for performing an auto fill function with a value stored in the memory when driving an Application Programming Interface API of a program to be executed.

Other aspects advantages and salient features of the invention will become apparent to those skilled in the art from the following detailed description which taken in conjunction with the annexed drawings discloses exemplary embodiments of the invention.

Throughout the drawings it should be noted that like reference numbers are used to depict the same or similar elements features and structures.

The following description with reference to the accompanying drawings is provided to assist in a comprehensive understanding of exemplary embodiments of the invention as defined by the claims and their equivalents. It includes various specific details to assist in that understanding but these are to be regarded as merely exemplary. Accordingly those of ordinary skill in the art will recognize that various changes or modifications of the embodiments described herein can be made without departing from the scope and spirit of the invention. In addition descriptions of well known functions and constructions may be omitted for clarity and conciseness.

The terms and words used in the following description and claims are not limited to the bibliographical meanings but are merely used by the inventor to enable a clear and consistent understanding of the invention. Accordingly it should be apparent to those skilled in the art that the following description of exemplary embodiments of the present invention is provided for illustration purpose only and not for the purpose of limiting the invention as defined by the appended claims and their equivalents.

It is to be understood that the singular forms a an and the include plural referents unless the context clearly dictates otherwise. Thus for example reference to a component surface includes reference to one or more of such surfaces.

A portable terminal as described below denotes a complex terminal that provides a Social Networking Service SNS over a wired wireless public network. However the present invention is not limited thereto. Therefore the portable terminal as described in the following exemplary embodiments of the present invention is applicable to any mobile communication terminal and obviously may be applied to any kind of information communication devices and multimedia devices such as a digital broadcasting terminal a Personal Digital Assistant PDA a smart phone 3Generation 3G terminals such as an International Mobile Telecommunication IMT 2000 terminal a Wideband Code Division Multiple Access WCDMA terminal a Global System for Mobile Communication General Packet Radio Service GSM GPRS terminal and a Universal Mobile Telecommunication Service UMTS terminal and applications thereof.

In the following description the term tilt denotes a tilt of the portable terminal. Furthermore according to an exemplary implementation the tilt of the portable terminal is recognized as 0 degrees when the portable terminal with reference to a normal viewing orientation is positioned perpendicular to the ground.

According to an exemplary embodiment of the present invention a password is established according to a tilt of the portable terminal that is associated with a location of a touch input on a displayed image.

Referring to when an Application Programming Interface API of a particular SNS to which the user logs in is driven a tilt sensor included in the portable terminal determines an angle or tilt of the portable terminal with respect to a benchmark orientation. For example the tilt sensor measures a tilt as 0 degrees when the portable terminal with respect to its upright viewing orientation is positioned perpendicular to the ground as indicated by . Similarly the tilt sensor measures a tilt as 90 degrees when the portable terminal is positioned parallel to the ground as indicated by and as 45 degrees when the portable terminal is positioned intermediate to the positions perpendicular to the ground and parallel to the ground as indicated by . Furthermore although not illustrated in the tilt sensor determines a tilt of the portable terminal with respect to both a horizontal plane and a vertical plane.

The portable terminal also determines an input of a user touch on a predetermined region of an image displayed on a display screen . More specifically when the user tilts the portable terminal at an angle such as an angle or or any angle there between coordinates corresponding to the location of the touch input are detected.

The detected coordinates and the measured tilt are combined and the combination is stored as a password for the driven SNS.

Thereafter when the API of the SNS is driven to login to the SNS site the stored password is used for determining authenticity of the user.

A synopsis of the integrated login input process in a portable terminal according to an exemplary embodiment of the present invention has been described above. Hereinafter a more detailed description will be made of an integrated login apparatus in a portable terminal according to an exemplary embodiment of the present invention.

Referring to the portable terminal includes a controller a memory a tilt sensor a display unit a filtering unit and a Radio Frequency RF unit .

The tilt sensor is a sensor for determining a tilt of the portable terminal. Upon sensing execution of a particular function e.g. driving of an API of an SNS the tilt sensor senses a horizontal tilt and a vertical tilt of the portable terminal and outputs the sensed tilts to the controller . In other words the tilt sensor acquires the horizontal tilt and the vertical tilt according to a tilt state of the portable terminal and outputs the tilts to the controller .

The controller controls operations of the portable terminal. For example the controller performs processing and control for voice communication and data communication.

In addition when a password is to be registered the controller applies a coordinate system to an image displayed through the display unit detects a tilt acquired by the tilt sensor detects coordinates corresponding to a region selected by the user in the displayed image and combines the tilt and the coordinates to store the combination as a password for the SNS.

Thereafter when the API of the SNS is driven to login to the SNS site the password stored in the memory is used to determine authenticity of the user.

More specifically the API of a particular SNS is driven when the portable terminal needs to enter a password in order to join the SNS. In that case the controller displays a plurality of images stored in the memory through the display unit and receives a selection of one of the displayed images from the user.

The display unit is implemented with a touch screen and may also serve as a key input unit. As an example a selection from the user may correspond to a tapping motion on the touch screen.

The controller determines a coordinate system according to an encryption level to be set for the password and applies the determined coordinate system to the image selected by the user.

Referring to a Cartesian coordinate system may be applied to the image selected by the user. Alternatively a cylindrical coordinate system as shown in a spherical coordinate system as shown in or a toroidal coordinate system as shown in may be used. Also the coordinate system provided by the controller may be previously set according to the encryption level of the registration password or may be selected by the user.

Referring to the image to which the coordinate system is applied is displayed through the display unit

It can also be seen in that coordinates of the coordinate system change with a tilt of the portable terminal.

As the tilt of the portable terminal increases a weight value is applied to the coordinate system applied to the image by using the filtering unit to acquire coordinates of the coordinate system as shown in respective images of .

In other words after a filter is applied to the previously set or user selected coordinate system according to the tilt acquired by the tilt sensor of the portable terminal and then a weight value is applied to the filter applied coordinate system coordinates of a region selected by the user on the respective images shown in are detected.

As such the aforementioned operation of the controller is performed to register a password due for joining an SNS when it is determined during the driving of the API that there is no password corresponding to the SNS in the memory .

The password registration in the controller is also performed in substantially the same way as described above when the password needs to be changed for example when the password is forgotten.

Afterwards when the SNS is driven if the password corresponding to the driven SNS has already been stored in the memory the controller displays an image and a coordinate system used at the time of password registration through the display unit and determines if the same value as a tilt detected at the time of password registration is generated with a change in the tilt state of the portable terminal. If the same value is generated the controller determines if a selection on a particular region of the displayed image is input from the user.

If the user s input selection on the predetermined region of the image to which the coordinate system is applied matches coordinates stored in the memory the controller permits the user to log in to the SNS site.

In an exemplary implementation an auto login operation may be performed by automatically providing corresponding IDentification ID and password at the time of login to the SNS site under the control of the controller .

Meanwhile the memory includes a Read Only Memory ROM a Random Access Memory RAM and a flash ROM and stores not only programs for operating the controller but also a plurality of images a plurality of coordinate systems and a combination of a tilt and coordinates generated in a particular image as a password corresponding to a particular SNS. The RF unit performs a wireless communication function of the portable terminal.

Hereinafter an integrated login input method in a portable terminal according to an exemplary embodiment of the present invention will be described.

Referring to in step an API of a particular SNS to which a user logs in is driven in the portable terminal. In step it is determined whether a password corresponding to the driven SNS has been stored. If it is determined in step that a password corresponding to the driven SNS has not been stored the method proceeds to step to register a password due to joining of the SNS and login to the SNS.

In step a plurality of images are displayed and one of the displayed images is selected by the user. A coordinate system is selected according to an encryption level to be set for the password and the selected coordinate system is matched to the selected image by the user so that the selected coordinate system can be applied to the selected image by the user.

If a tilt state of the portable terminal changes in step a tilt is detected with a tilt sensor in step . A selection on a predetermined region of the displayed image is input from the user in a state where the portable terminal is tilted in step . The selection input may be generated simultaneously or sequentially.

Coordinates corresponding to the predetermined region selected on the displayed image in step are detected in step and the detected coordinates and the detected tilt are combined to be stored as a password for the SNS in step . The stored password is registered as the password for the SNS in step .

In an exemplary implementation the coordinate detection in step is performed by applying a filter to the coordinate system previously set or selected by the user according to the tilt detected in step and applying a weight to the filter applied coordinates.

Referring to a filter for weight application is applied to a particular image to which an orthogonal coordinate system has been applied. The result of the filter application is illustrated in .

Furthermore although application of the filter as illustrated in was to a graphical design image the filter operation may be similarly applied to an actual image as shown in .

Referring again to if it is determined in step that the password corresponding to the SNS has already been stored the process follows path A illustrated in for login using the password.

Referring to an image used at the time of password registration and a coordinate system applied to the image are displayed in step .

After the tilt state of the portable terminal is changed in step it is determined whether the same value as a tilt detected at the time of password registration is generated in step . If it is determined in step that the same tilt value is detected as the value at the time of password registration a selection on a particular region of the displayed image is input from the user in step .

In step it is determined if the tilt and the user s selection input on the predetermined region match previously stored coordinates. If it is determined in step that the tilt and the user s selection input on the predetermined region match previously stored coordinates the auto login to the SNS site is performed in step . On the other hand if it is determined in step that the tilt and the user s selection input on the predetermined region do not match previously stored coordinates the method returns to step to again receive the user s selection. Similarly if it is determined in step that the same tilt value is not detected as the value at the time of password registration the method returns to step to again receive a changed tilt state.

As can be appreciated from the foregoing description a recognition rate of a user input can be improved by a coordinate system using a filter and a tilt sensor. Moreover in a portable terminal using a touch screen a password having a high encryption level can be set through a user s simple touch input and a tilt state of the portable terminal.

The integrated login input method and apparatus according to exemplary embodiments of the present invention can be achieved as described above.

While the present invention has been shown and described with reference to certain exemplary embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the spirit and scope of the invention as defined by the appended claims and their equivalents.

