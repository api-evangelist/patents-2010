---

title: Apparatus and method for drawing a stereoscopic image
abstract: Coordinate values of an object located in a coordinate space are stored in a memory. The coordinate space is represented by a first direction, a second direction and a third direction each different. The coordinate values include first coordinate values along the first direction, second coordinate values along the second direction and third coordinate values along the third direction. A stereoscopic image of the object having a parallax along one of the first direction and the second direction is displayed. A direction of the parallax is detected. When the direction of the parallax is the first direction, the first coordinate values are subjected to a parallel projection. When the direction of the parallax is the second direction, the second coordinate values are subjected to the parallel projection.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08441523&OS=08441523&RS=08441523
owner: Kabushiki Kaisha Toshiba
number: 08441523
owner_city: Tokyo
owner_country: JP
publication_date: 20100204
---
This application is based upon and claims the benefit of priority from Japanese Patent Application No. 2009 24989 filed on Feb. 5 2009 the entire contents of which are incorporated herein by reference.

In a method for drawing a stereoscopic image as the prior art an integral imaging Hereinafter it is called II system is well known. In this system each pixel of a plurality of images multi view image having a parallax is dispersedly positioned on one image Hereinafter it is called elemental image . By controlling an orbit of a light from each pixel composing the elemental image with a lenticular lens an observer can perceive a stereoscopic image the II system is called integral photography system . This II system is known as an ideal method for drawing a stereoscopic image regenerated with nearly actual light. However in the II system a resolution of the image is low because each pixel of a plurality of images is dispersedly positioned on one elemental image.

Accordingly one dimensional II system which prevents the resolution from lowering by assigning a parallax along a horizontal direction of the elemental image is proposed. In this one dimensional II system a coordinate x y z of each vertex of a drawing object three dimensional CG model is multiplied with a perspective projection matrix. After that values of y coordinate and z coordinate are respectively divided by 1 z d d a center of projection . As a result a value along the horizontal direction x coordinate is subjected to a parallel projection and a value along the vertical direction y coordinate is subjected to a perspective projection.

In JP A 2004 257124 Kokai above mentioned method i.e. a value along the horizontal direction is subjected to the parallel projection and a value along the vertical direction is subjected to the perspective projection is disclosed Hereinafter it is called a first method for drawing a stereoscopic image . However another method i.e. a value along the horizontal direction is subjected to the perspective projection and a value along the vertical direction is subjected to the parallel projection is not disclosed Hereinafter it is called a second method for drawing a stereoscopic image . Accordingly a stereoscopic image cannot be drawn by switching the first method for drawing a stereoscopic image and the second method for drawing a stereoscopic image.

The present invention is directed to an apparatus and a method for drawing by switching a stereoscopic image having a parallax along the horizontal direction and a stereoscopic image having a parallax along the vertical direction.

According to an aspect of the present invention there is provided an apparatus for drawing a stereoscopic image comprising a storage unit configured to store coordinate values of an object located in a coordinate space the coordinate space being represented by a first direction a second direction and a third direction each different the coordinate values including first coordinate values along the first direction second coordinate values along the second direction and third coordinate values along the third direction a display unit configured to display a stereoscopic image of the object the stereoscopic image having a parallax along one of the first direction and the second direction a detection unit configured to detect a direction of the parallax and a projection operation unit configured to subject the first coordinate values to a parallel projection when the direction of the parallax is the first direction and subject the second coordinate values to the parallel projection when the direction of the parallax is the second direction.

Hereinafter embodiments of the present invention will be explained by referring to the drawings. The present invention is not limited to the following embodiments.

It is difficult for a regular camera that a value along the horizontal direction is subjected to the perspective projection and a value along the vertical direction is subjected to the parallel projection and a value along the horizontal direction is subjected to the parallel projection and a value along the vertical direction is subjected to the perspective projection. Accordingly in the first embodiment as to an object drawn in a virtual three dimensional space by CG a mode to switch a stereoscopic image having a parallax along the horizontal direction and a stereoscopic image having a parallax along the vertical direction is explained. In this case having a parallax along the horizontal direction means stereoscopically visualizing the image along the horizontal direction. Furthermore having a parallax along the vertical direction means stereoscopically visualizing the image along the vertical direction.

As shown in the stereoscopic image drawing apparatus includes a GPU Graphic Processing Unit a VRAM a CPU a RAM an I F an HDD an input unit such as a mouse or a key board a display unit and a transformation unit .

When data is input from the input unit or the HDD the CPU or the RAM sends the input data for graphics processing to the GPU . The GPU generates a plurality of image data multi view image having a parallax based on the input data and writes the image data into the VRAM . The transformation unit dispersedly locates each pixel of the multi view image generated by the GPU on one image and transforms the multi view image to an elemental image. The display unit displays the elemental image transformed from the image data written into the VRAM by the transformation unit . The transformation unit may be omitted by using the GPU or the CPU .

As shown in the stereoscopic image drawing apparatus includes a storage unit a model view matrix multiplication unit a projection matrix multiplication unit a perspective division unit a viewport transformation unit a rasterize unit a pixel processing unit the display unit the transformation unit and a perspective division control unit .

The model view matrix multiplication unit and the projection matrix multiplication unit are included in a vertex shader . The perspective division unit the viewport transformation unit the rasterize unit and the perspective division control unit are included in a rasterizer . The pixel processing unit is included in a pixel shader .

Furthermore the projection matrix multiplication unit the perspective division unit and the perspective division control unit are included in a projection operation unit. The perspective division unit and the perspective division control unit are included in a first perspective operation unit.

Recently as to a graphics processor operation of the vertex shader and the pixel shader are often controlled with a program by a user. Accordingly function of the vertex shader and the pixel shader can be change by the software. Furthermore function of the rasterizer is fixed. Accordingly in order to change the function of the rasterizer change of a hardware circuit is necessary.

Hereinafter detail function of the stereoscopic image drawing apparatus of the first embodiment is explained.

The storage unit stores coordinate data Hereinafter it is called object coordinate of each vertex of an object drawn in a virtual three dimensional space by CG. The coordinate of each vertex of the object is represented as four dimensional coordinates x y z w .

X axis Y axis and Z axis are mutually perpendicular and form a three dimensional perpendicular coordinates. X axis is defined as a horizontal direction first direction Y axis is defined as a vertical direction second direction and Z axis is defined as a depth direction third direction on a screen of the display unit . In this case the reason why a coordinate of each vertex of the object is represented as four dimensional coordinates x y z w is a transformation matrix used for API Application Programming Interface such as OpenGL is four dimensional coordinates of four rows four columns . By using four dimensional coordinates as the transformation matrix a coordinate transformation of rotation and parallel moving can be described as one matrix. Regularly w coordinate is set to 1 .

The storage unit stores a model view matrix used by the model view matrix multiplication unit and a projection matrix used by the projection matrix multiplication unit . Furthermore the storage unit stores data related to program describing steps of vertex shader processing and pixel shader processing. Various formats are applicable to data format stored in the storage unit. Briefly the storage unit stores data necessary for drawing desired CG.

Next projection is explained. In general a projection used for CG includes a perspective projection and a parallel projection.

The perspective projection is a method for converging a light axis from the object to one point eye . In the perspective projection an object near the eye is largely represented than an object far from the eye.

As shown in in the perspective projection a shape of a view volume O is a truncated square pyramid. The view volume O is a volume in a scene located relative to the eye P. An object located in the view volume O is a drawing object which is displayed on the display unit .

A projection matrix perspective projection matrix to perspectively project is represented as follows.

In n is a length between the eye P and a near clip plane S f is a length between the eye P and a far clip plane S r is a length of the right side of the near clip plane S l is a length of the left side of the near clip plane S t is a length of the upper side of the near clip plane S b is a length of the lower side of the near clip plane S.

The parallel projection is a method for parallely projecting a light axis from the object to an arbitrary axis parallel axis . The parallel projection includes an orthographic projection and an oblique projection.

The orthographic projection is for example on an eye coordinate centering the eye a parallel projection which a projection axis is parallel to a depth direction Z axis direction . Briefly an angle between a projection plane and a projection line is perpendicular.

On the other hand the oblique projection is a parallel projection which the projection axis is not parallel to the depth direction Z axis direction . Briefly an angle between the projection plane and the projection line is not perpendicular. In the stereoscopic image drawing apparatus using II system the oblique projection is used for drawing a stereoscopic image. Hereinafter in case of describing parallel projection the oblique projection is indicated. As shown in in the parallel projection a shape of a view volume O is a rectangular parallelepiped.

In n is a length between the eye P and a near clip plane S f is a length between the eye P and a far clip plane S r is a length of the right side of the near clip plane S l is a length of the left side of the near clip plane S t is a length of the upper side of the near clip plane S b is a length of the lower side of the near clip plane S. Furthermore as shown in is an angle between a vector which a projection axis is projected onto XZ plane and Z axis and is an angle between a vector which a projection axis is projected onto YZ plane and Z axis.

In the stereoscopic image drawing apparatus of the first embodiment an image having a parallax along a horizontal direction or a vertical direction is displayed on the display unit . In case of displaying the image having a parallax along the horizontal direction as to each vertex of the object x coordinate is subjected to a parallel projection and y coordinate is subjected to a perspective projection. In case of displaying the image having a parallax along the vertical direction as to each vertex of the object x coordinate is subjected to the perspective projection and y coordinate is subjected to the parallel projection.

In order to realize such special projection the storage unit stores a projection matrix Hereinafter it is called first projection matrix used for displaying an image having a parallax along the horizontal direction and a projection matrix Hereinafter it is called second projection matrix used for displaying an image having a parallax along the vertical direction.

In the first projection matrix at a position first row related to calculation of x coordinate corresponding elements of a parallel projection matrix are set. At each position second row fourth row related to calculation of y coordinate z coordinate and w coordinate corresponding elements of a perspective projection matrix are set.

In the second projection matrix at each position first row third row fourth row related to calculation of x coordinate z coordinate and w coordinate corresponding elements of a perspective projection matrix are set. At a position second row related to calculation of y coordinate corresponding elements of a parallel projection matrix are set.

The model view matrix multiplication unit reads a model view matrix and object coordinates from the storage unit and transforms the object coordinates to eye coordinates by multiplying the model view matrix with the object coordinates.

This transformation is called a model view transformation . In the model view transformation object coordinates represented in a local coordinate system is transformed to eye coordinates. The eye coordinates are coordinates centering the eye of a camera user observing the object.

The projection matrix multiplication unit prepares a detection unit not shown in Fig. to detect a type of the display unit the type is stored in a type maintenance unit . Based on a detection result by the detection unit the projection matrix multiplication unit reads a projection matrix stored in the storage unit . Briefly when the display unit displays an image having a parallax along the horizontal direction the projection matrix multiplication unit reads the first projection matrix. When the display unit displays an image having a parallax along the vertical direction the projection matrix multiplication unit reads the second projection matrix. By multiplying the projection matrix with eye coordinates calculated by the model view matrix multiplication unit the projection matrix multiplication unit calculates a clip coordinate of each vertex of the object.

The perspective division control unit prepares a detection unit not shown in Fig. to detect a type of the display unit the type is stored in the type maintenance unit . Furthermore the perspective division control unit prepares a memory not shown in Fig. storing table data shown in .

When the display unit displays an image having a parallax along the horizontal direction after multiplying the projection matrix x coordinate of each peal is not divided. Other coordinates of each vertex are divided by w coordinate.

On the other hand when the display unit displays an image having a parallax along the vertical direction after multiplying the projection matrix y coordinate of each peal is not divided. Other coordinates of each vertex are divided by w coordinate.

In order for the perspective division unit to realize perspective division processing by selecting specified coordinate values the perspective division control unit controls the perspective division unit based on a type of the display unit . Concretely based on the horizontal direction or the vertical direction along which the display unit has a parallax a control signal to validate or invalidate a division of each coordinate value is generated and input to the perspective division unit .

The perspective division control unit uses table data stored in the memory based on a detection result by the detection unit. If the display unit has a parallax along the horizontal direction the perspective division control unit uses table data shown in . In this case the perspective division control unit generates a control signal to invalidate a perspective division of x coordinate and validate a perspective division of y z w coordinates and inputs the control signal to the perspective division unit .

If the display unit has a parallax along the vertical direction the perspective division control unit uses table data shown in . In this case the perspective division control unit generates a control signal to invalidate a perspective division of y coordinate and validate a perspective division of x z w coordinates and inputs the control signal to the perspective division unit . The table data shown in may be stored in the storage unit and read by the perspective division control unit based on the detection result.

Based on the control signal input from the perspective division control unit the perspective division unit divides a clip coordinate value x y z w of each vertex input from the projection matrix multiplication unit by w coordinate.

From the control signal input from the perspective division control unit the perspective division unit decides a coordinate element to validate a perspective division. As to the coordinate element decided to validate the perspective division the perspective division unit operates following equations 5 8 . 5 6 7 8 

In this way a normalized device coordinate of each vertex is calculated. When the display unit displays an image having a parallax along the horizontal direction the normalized device coordinate is x y z w . Furthermore when the display unit displays an image having a parallax along the vertical direction the normalized device coordinate is x y z w .

Based on a size of a viewport drawing area read from the storage unit the viewport transformation unit enlarges or reduces x coordinate and y coordinate of the normalized device coordinates of each vertex of the object calculated by the perspective division unit and calculates a window coordinate of each vertex of the object.

In order for a display to draw or for a printer to print a text or an image processed by a computer the rasterize unit decomposes an inner area of a polygon defined by each vertex having the window coordinate calculated by the viewport transformation unit into a set of pixels.

The polygon calculated by the viewport transformation unit represents an image by the window coordinate of each vertex and connection information thereof. This representation method is called a vector graphics . On the other hand the display processes the image as a set of pixels. Information of the vector graphics cannot be directly drawn or printed. Accordingly by exposing information of the vector graphics the rasterize unit decomposes the information into the set of pixels.

The pixel processing unit calculates a drawing color of each pixel output from the rasterize unit and writes the drawing color into an image memory of the storage unit .

The transformation unit dispersedly locates each pixel of the image written into the storage unit by the pixel processing unit on one image and generates an elemental image. The elemental image is written into the storage unit .

The display unit prepares a type maintenance unit to maintain a type of the display unit . Furthermore the display unit displays the elemental image stored in the storage unit by the transformation unit . The display unit equips a display screen to display each elemental pixel of the image to be stereoscopically displayed and a lenticular lens array lens or a pin hole plate to control a light from the display screen. In this case if the display screen is a type on which pixels are fixedly located as a matrix shape the display screen may be a liquid crystal display apparatus of a projection type or a direct view type a plasma display apparatus a display apparatus of field emission type or a display apparatus of organic EL.

Next processing of the stereoscopic image drawing apparatus of the first embodiment is explained. is a flow chart of processing of the stereoscopic image drawing apparatus . First the model view matrix multiplication unit multiplies a model view matrix with an object coordinate and transforms the object coordinate to an eye coordinate S .

The projection matrix multiplication unit detects a type of the display unit from the type maintenance unit of the display unit . Based on the type of the display unit the projection matrix multiplication unit decides the horizontal direction or the vertical direction along which the display unit displays the image having a parallax S .

If the display unit displays the image having the parallax along the horizontal direction the projection matrix multiplication unit reads a first projection matrix from the storage unit S . Furthermore if the display unit displays the image having the parallax along the vertical direction the projection matrix multiplication unit reads a second projection matrix from the storage unit S . By multiplying the projection matrix with eye coordinates calculated by the model view matrix multiplication unit the projection matrix multiplication unit calculates a clip coordinate of each vertex of the object S .

The perspective division control unit detects a type of the display unit from the type maintenance unit of the display unit . Based on the type of the display unit the perspective division control unit decides the horizontal direction or the vertical direction along which the display unit displays the image having a parallax S .

If the display unit displays the image having the parallax along the horizontal direction the perspective division control unit generates a control signal to invalidate a perspective division of x coordinate and validate a perspective division of y z w coordinates and inputs the control signal to the perspective division unit S .

Furthermore if the display unit displays the image having the parallax along the vertical direction the perspective division control unit generates a control signal to invalidate a perspective division of y coordinate and validate a perspective division of x z w coordinates and inputs the control signal to the perspective division unit S .

Based on the control signal input from the perspective division control unit the perspective division unit divides a clip coordinate of each vertex input from the projection matrix multiplication unit by w coordinate S .

The viewport transformation unit calculates a window coordinate of each vertex of the object S . The rasterize unit decomposes an inner area of a polygon defined by each vertex having the window coordinate calculated by the viewport transformation unit into a set of pixels S .

The pixel processing unit calculates a drawing color of each pixel output from the rasterize unit and stores a multi view image having the drawing color into an image memory of the storage unit S . The transformation unit transforms the multi view image stored into the storage unit by the pixel processing unit to an elemental image and stores the elemental image into the storage unit S . The display unit displays the elemental image stored in the storage unit by the transformation unit S .

As mentioned above in the stereoscopic image drawing apparatus of the first embodiment from vertex coordinates multiplied with a projection matrix a specified coordinate value is selected and divided. As a result by using the GPU a stereoscopic image of one dimensional II system can be quickly drawn. Furthermore based on a type of the display unit the stereoscopic image having a parallax along the horizontal direction and the stereoscopic image having a parallax along the vertical direction can be drawn by switching.

The type of the display unit may be input from the input unit by a user. In this case based on the type of the display unit input from the input unit the projection matrix multiplication unit reads a projection matrix from the storage unit . Based on the type of the display unit the perspective division control unit utilizes table data shown in or .

In this case even if the type of the display unit is not stored in the type maintenance unit by inputting the type of the display unit from the user a stereoscopic image suitable for the type of the display unit can be drawn.

In the first embodiment by controlling operation of the perspective division unit included in the rasterizer a specified coordinate value is selected from vertex coordinates and perspectively divided. However in order to control operation of the rasterizer as a fixed function installed in a graphics processor a hardware circuit must include the perspective division control unit.

In the second embodiment by executing necessary processing with a vertex shader controlled by a user program a specified coordinate is selected from vertex coordinates and perspectively divided. In the stereoscopic image drawing apparatus of the second embodiment the vertex shader selects a specified coordinate value from vertex coordinates and subjects the specified coordinate value to a perspective multiplication inverse operation of a perspective division . After that by dividing all coordinate values of each vertex by the perspective division unit effect of the perspective division of the specified coordinate value by the perspective division unit is canceled. Accordingly the hardware circuit need not include the perspective division control unit and the specified coordinate value of vertex coordinates is selectively subjected to a perspective division.

The model view matrix multiplication unit the projection matrix multiplication unit the perspective multiplication unit and the perspective multiplication control unit are included in a vertex shader A. The perspective division unit A the viewport transformation unit and the rasterize unit are included in a rasterizer A. The pixel processing unit is included in a pixel shader A.

Furthermore the projection matrix multiplication unit the perspective division unit A the perspective multiplication unit and the perspective multiplication control unit are included in a projection operation unit. The perspective division unit A the perspective multiplication unit and the perspective multiplication control unit are included in a second perspective operation unit.

The hardware component is same as that of the stereoscopic image drawing apparatus of the first embodiment. Accordingly its Figure and explanation are omitted. Furthermore as to component elements already explained in the same sign is assigned and its explanation is omitted.

Hereinafter detail of the stereoscopic image drawing apparatus of the second embodiment is explained.

The perspective multiplication control unit prepares a detection unit not shown in Fig. to detect a type of the display unit the type is stored in the type maintenance unit . Furthermore the perspective multiplication control unit prepares a memory not shown in Fig. storing table data shown in .

The perspective multiplication control unit controls the perspective multiplication unit based on a type of the display unit . Concretely in order for the perspective multiplication unit to realize perspective multiplication processing by selecting specified coordinate values based on the horizontal direction or the vertical direction along which the display unit has a parallax a control signal to validate or invalidate a multiplication of each coordinate value is generated and input to the perspective multiplication unit .

The detection unit of the perspective multiplication control unit detects a type of the display unit maintained in the type maintenance unit . If the display unit has a parallax along the horizontal direction the perspective multiplication control unit uses table data shown in . In this case the perspective division multiplication control unit generates a control signal to validate a perspective multiplication of x coordinate and invalidate a perspective multiplication of y z w coordinates and inputs the control signal to the perspective division unit .

If the display unit has a parallax along the vertical direction the perspective multiplication control unit uses table data shown in . In this case the perspective multiplication control unit generates a control signal to validate a perspective multiplication of y coordinate and invalidate a perspective multiplication of x z w coordinates and inputs the control signal to the perspective division unit . The table data shown in may be stored in the storage unit and read by the perspective multiplication control unit based on the type of the display unit .

Based on the control signal input from the perspective multiplication control unit the perspective multiplication unit multiplies a clip coordinate value x y z w of each vertex input from the projection matrix multiplication unit by w coordinate. This multiplication is an inverse operation of the perspective division.

From the control signal input from the perspective multiplication control unit the perspective multiplication unit decides a coordinate element to validate a perspective multiplication. As to the coordinate element decided to validate the perspective multiplication the perspective multiplication unit operates following equations 9 12 . 9 10 11 12 

The perspective division unit A divides all coordinate values of a clip coordinate of each vertex input from the perspective multiplication unit by w coordinate and calculates a normalized device coordinate of each vertex.

If the display unit displays an image having a parallax along the horizontal direction the perspective multiplication unit multiplies x coordinate of vertex coordinates with w coordinate. After that the perspective division unit A divides x coordinate multiplied with w coordinate by w coordinate. As a result by canceling effects of the multiplication and the division x coordinate is returned to an original value output from the projection matrix multiplication unit .

On the other hand if the display unit displays an image having a parallax along the vertical direction the perspective multiplication unit multiplies y coordinate of vertex coordinates with w coordinate. After that the perspective division unit A divides y coordinate multiplied with w coordinate by w coordinate. As a result by canceling effects of the multiplication and the division y coordinate is returned to an original value output from the projection matrix multiplication unit .

Briefly as to the drawing apparatus of one dimensional II system of which the display unit has a parallax along the horizontal direction a normalized device coordinate of each vertex is x y z w which is the same result as the first embodiment. Furthermore as to the drawing apparatus of one dimensional II system of which the display unit has a parallax along the vertical direction a normalized device coordinate of each vertex is x y z w which is the same result as the first embodiment.

Next processing of the stereoscopic image drawing apparatus of the second embodiment is explained. is a flow chart of processing of the stereoscopic image drawing apparatus . First in the stereoscopic image drawing apparatus processing of S S first processing explained in is executed S .

The perspective multiplication control unit detects a type of the display unit from the type maintenance unit of the display unit . Based on the type of the display unit the perspective multiplication control unit decides the horizontal direction or the vertical direction along which the display unit displays the image having a parallax S .

If the display unit displays the image having the parallax along the horizontal direction the perspective multiplication control unit generates a control signal to validate a perspective multiplication of x coordinate and invalidate a perspective multiplication of y z w coordinates and inputs the control signal to the perspective multiplication unit S .

Furthermore if the display unit displays the image having the parallax along the vertical direction the perspective multiplication control unit generates a control signal to validate a perspective multiplication of y coordinate and invalidate a perspective multiplication of x z w coordinates and inputs the control signal to the perspective multiplication unit S .

Based on the control signal input from the perspective multiplication control unit the perspective multiplication unit multiplies a clip coordinate x y z w of each vertex input from the projection matrix multiplication unit with w coordinate S .

The perspective division unit A divides all coordinate values of a clip coordinate of each vertex input from the perspective multiplication unit by w coordinate and calculates a normalized device coordinate of each vertex S . After that in the stereoscopic image drawing apparatus processing of S S second processing explained in is executed S .

As mentioned above in the stereoscopic image drawing apparatus of the second embodiment after a projection matrix is multiplied with vertex coordinates by selectively multiplying a specified coordinate value from the vertex coordinates effect of the perspective division of the specified coordinate value is cancelled. As a result a general perspective division function as a fixed function installed in the graphics processor can be used. Accordingly by using the existing graphics processor a stereoscopic image of one dimensional II system can be quickly drawn. Another effect is same as that of the stereoscopic image drawing apparatus of the first embodiment.

In the disclosed embodiments the processing can be performed by a computer program stored in a computer readable medium.

In the embodiments the computer readable medium may be for example a magnetic disk a flexible disk a hard disk an optical disk e.g. CD ROM CD R DVD an optical magnetic disk e.g. MD . However any computer readable medium which is configured to store a computer program for causing a computer to perform the processing described above may be used.

Furthermore based on an indication of the program installed from the memory device to the computer OS operation system operating on the computer or MW middle ware software such as database management software or network may execute one part of each processing to realize the embodiments.

Furthermore the memory device is not limited to a device independent from the computer. By downloading a program transmitted through a LAN or the Internet a memory device in which the program is stored is included. Furthermore the memory device is not limited to one. In the case that the processing of the embodiments is executed by a plurality of memory devices a plurality of memory devices may be included in the memory device.

A computer may execute each processing stage of the embodiments according to the program stored in the memory device. The computer may be one apparatus such as a personal computer or a system in which a plurality of processing apparatuses are connected through a network. Furthermore the computer is not limited to a personal computer. Those skilled in the art will appreciate that a computer includes a processing unit in an information processor a microcomputer and so on. In short the equipment and the apparatus that can execute the functions in embodiments using the program are generally called the computer.

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and embodiments of the invention disclosed herein. It is intended that the specification and embodiments be considered as exemplary only with the scope and spirit of the invention being indicated by the claims.

