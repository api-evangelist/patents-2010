---

title: Image file as container for widgets in GUI authoring tool
abstract: A method for authoring a graphical user interface (GUI) includes providing a widget builder interface for editing a template widget and receiving user input of widget properties for the template widget. The widget properties including a widget type, one or more widget parameters, and one or more images. The method further includes saving the widget properties and the one or more images into a widget file conforming to a standard image file format.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08458605&OS=08458605&RS=08458605
owner: Amulet Technologies, LLC
number: 08458605
owner_city: Campbell
owner_country: US
publication_date: 20100226
---
A What You See Is What You Get WYSIWYG authoring tool for graphical user interface GUI offers a palette of GUI widgets that the designer can select from visually arrange and manipulate to assemble a GUI. The palette can either be fixed or extendible. Often palette extensions are done by the designer using a conventional programming language such as C or Java. The palette extensions are usually intended for use by an individual customer and are not easily shared with other users of the authoring tool.

More advanced authoring environments have a plug in architecture that allows developers to build reusable GUI widgets that can be distributed to other users so that they can add the GUI widgets to their palettes and use them just like the standard palette. GUI widgets are often a collection of source code and graphics vector bitmap or both . GUI widgets are either distributed as a single file in a proprietary format or as a collection of files. When distributed as a single file the proprietary nature of the file may prevent an operating system OS file explorer from providing a thumbnail of the GUI widget and a standard graphical editing tool from modifying the graphics in the file. When distributed as a collection of files the GUI widget is difficult to manage.

The widgets in the HTML pages may be created from template widgets . Each template widget includes an applet file and optionally includes any number of bitmap image files that form part of the widget. Applet file includes the widget properties nested between applet tags. The widget properties specify a widget type widget parameters for the widget and one or more function calls to jump to another HTML page or for the widget to communicate data with host device other widgets or an input device upon an event. The widget properties optionally include any number of properties for vector graphics that form part of the widget.

Once the GUI is constructed user runs a compiler to compile the HTML pages and the linked images into HTML code to reduce size and execution requirements. User loads HTML code into a nonvolatile memory e.g. a flash memory . Nonvolatile memory also stores a HTML operating system OS and a widget library . A controller chip includes a processor that runs HTML OS which executes HTML code to render the current GUI screen to a frame buffer in a volatile memory e.g. a random access memory . In particular HTML OS accesses widget library for the drawing methods and the behaviors of the widgets. Controller chip also includes a display controller that raster scans the GUI screen in the frame buffer to a display . Controller chip communicates user input with input device such as a touch screen. Controller chip also communicates data and user input with an embedded processor in host device .

For more details see U.S. Pat. No. 7 100 118 and U.S. patent application Ser. No. 11 502 071 which are incorporated by reference. Controller chip may be the Amulet Graphical OS Chip and HTML OS and widget library may be the Amulet OS both available from Amulet Technologies of Campbell Calif. The syntax of the HTML and the widget properties are found in the Programmer s Guide for the Amulet Graphical OS Chip which is available at the website of Amulet Technologies LLC of Campbell Calif.

In accordance with the present disclosure a single widget file is used as the container for all the elements of a widget. The widget file conforms to a standard image file format that allows commenting text that is ignored by compilers and interpreters . Widget properties are stored as comments in the widget file as specified by the image file format. When vector graphics are part of the widget their properties are stored as part of the widget properties in the comments. When bitmap images are part of the widget they are stored as images in the widget file as specified by the image file format. The standard image format is supported by conventional operating systems so an OS file explorer can provide a thumbnail of the widget file and a standard editing tool can modify the bitmaps in the widget file. As a single file the widget is easy to distribute between GUI developers.

First group is optionally followed by groups to which each includes an IHDR chunk an IDAT chunk and an IEND chunk . When additional bitmap images are present they are stored in IDAT chunks of groups to . When a widget does not include any bitmap image a representative thumbnail image may be generated and saved in IDAT chunk in first group . When one or more non PNG images are present they may be stored in one or more fiLe chunks which is a new type of ancillary private and safe to copy chunk. The fiLe chunks may also be used to store PNG images if desired. An fiLe chunk has a length field a chunk type i.e. fiLe the data field and a cyclic redundancy check CRC calculated on the preceding bytes in the chunk but not including the length field. The data field includes a byte count of an image format description the image format descriptor e.g. JPEG and the non PNG image data.

Widget properties begin with a text declaration at line . Line includes a start tag for a template element. When present the template element identifies the widget as a template widget for creating customized widgets. Line includes a start tag for a widget type element nested within the template element. The widget type is RadioButton which identifies the widget as a radio button widget. Nested in the widget type element are widget parameter elements for the widget.

The widget parameter elements each include start and end tags a widget parameter name and one or more attributes in the start tag and one or more values for the widget parameter between the tags. When a start tag includes an attribute of Editable True the widget parameter may be modified by the user when the user creates a widget from the template widget and vice versa. When a start tag includes an attribute of Optional False the widget parameter is a parameter that is automatically included in a properties editor described later with in a widget builder described later with when the user creates a customized widget from a template widget. When a start tag includes an attribute of Optional True the widget parameter is listed as one of the parameters in a popup menu described later with used to add a widget parameter to properties editor . When a start tag includes an attribute of Ignore True the widget is created without a widget parameter in a GUI builder described later with .

Line includes a Name element having a value that specifies a name e.g. RB1 for the radio button widget. Line includes a label element having a value that specifies a label e.g. Button Label appearing with the radio button widget. Lines and include an initialCondition element having values that specify an initial condition for the radio button widget when the UI is initially loaded and choices for the initial condition. For example the values for the initialCondition element are Off On Off where the first Off specifies the set initial condition the On Off thereafter specifies the choices for the initial conditions and the values are separated by a tab delimiter not visible in the XML text . Line includes a groupName element having a value that specifies a group e.g. rbg1 that this radio button widget is part of Line includes a href element having a value that specifies a function e.g. a placeholder function Amulet Nop to be invoked when the radio button widget is set.

Line includes a Width element having a value that sets a width e.g. 164 pixels for the radio button widget. Line includes a Height element having a value that sets a height e.g. 34 pixels for the radio button widget. Lines and include a fontStyle element having one or more values that specify one or more font styles e.g. plain bold and italic for the label. Line includes a font element having values that specify the font and the font size e.g. Amulet Sans Serif 12 pt of the label.

Lines and include elements that identify images to be used for the widget in various states also referred to as state images . Line includes an emptyImage element having one or more values that specify one image or multiple images also referred to as image components that make up the empty state image of the radio button widget when the widget is not set. When image components are specified for a state image the image components are layered over each other to create the state image. Line includes a fullImage element having one or more values that specify one image or multiple image components that make up the full state image of the radio button widget when the widget is set. Line includes a TrackingImage element having one or more values that specify one image or multiple image components that make up the tracking state image of the radio button widget when the widget is being touched in a touch screen or when a cursor is placed over the widget.

Line is the end tag for the widget type RadioButton which has a corresponding start tag on line . Line is the end tag for the template element Template which has a corresponding start tag on line .

Each start tag for a widget parameter element includes an attribute of Type that specifies the data type of the widget parameter. A popup data type is a popup menu in which the user can select only one option for a widget parameter. For example popup data type is used for the initialCondition parameter in line . As described above the values for the initialCondition element are Off On Off where the first Off specifies the set initial condition the On Off thereafter specifies the choices for the initial conditions and the values are separated by tab delimiters a nonprinting character .

A color data type specifies that a widget parameter value is a color. For example color data type is used to describe widget parameters such as text color.

A string data type specifies that a widget parameter value is a string value. For example string data type is used to describe widget parameters such as name and label.

A number data type specifies a widget parameter value as a number. For example number data type is used to describe widget parameters such as width height minimum values and maximum values.

A font data type specifies a widget parameter value as a font and font size. For example font data type is used to describe widget parameters such as font type.

An IWCMethod data type specifies widget parameter values as one or more functions used in a widget and one or more events that trigger the function call. Some of the functions include jumping to another GUI page sending values out setting values halting current widget activity and saving current status to memory. For example a href element in the radio button widget may use the IWCMethod data type to toggle the polarity of a display between positive and negative.

A file data type specifies a widget parameter value as a bitmap file external of the widget filet. For example the Empty Image parameter of the radio button widget uses file data type to point to a file which contains the empty state image. When the radio button widget is not set this image will show on the GUI.

A Boolean data type specifies a widget parameter value that has two choices. For example in a line graph widget a column clear parameter may be classified as Boolean because it has two choices TRUE or FALSE.

A MultiSelectionPopup data type has a popup menu that shows different options the user may choose. This is different than popup data type because the user may select more than one option simultaneously. For this data type the widget parameter values include the selected choices separated by characters the selected choices are separated by a tab delimiter a nonprinting character from the choices for the widget parameter element and the choices are separated by tab delimiters. For example a font element having MultiSelectionPopup data type allows the user to select font size font color and font style at the same time.

An EmbeddedImage data type specifies one or more widget parameter values as one PNG image or multiple PNG image components saved in the widget file. When multiple PNG image components are specified the image components are grouped to form a single image. For example image A B and C can be grouped as a down button image and image B D and E can be grouped as an up button.

An UnsignedFloatingPoint type specifies one or more values as unsigned floating point numbers. For example an Update Rate widget parameter specifies how often a widget calls a href function. The first unsigned floating point number specifies the href function call frequency specified in seconds with a single floating point number . The range is 0.00 655.35 where a value of 0.00 means update never. The second number specifies the delay time from when a GUI page is loaded until the first href function call specified in seconds with a single floating point number . The range is 0.01 655.35. If the second number is not specified then the delay time defaults to the first number frequency .

An ImageArray type specifies an array of images used in the widget. Images may be non PNG. The images can be saved in the widget file or a separate file in itself.

Authoring tool includes a widget builder for building widgets a GUI builder for building a GUI using the template widgets a runtime rendering tool for drawing GUI components including widgets as they would appear in a native environment with controller chip compiler for compiling the GUI for programming the controller chip or running on a simulator of the controller chip. Widgets may be template widgets or customized widgets created from the template widgets. GUI builder saves the GUI in an XML project file. The XML project file includes one or more XML pages having GUI components such as texts widgets images or background images. Widget builder and GUI builder may be part of the same software running on a non native host environment such as a Windows operating system executed by an x86 processor on computer . Widget builder may also be a plug in for a conventional graphics editor.

Runtime rendering tool includes a translator and a library wrapper around the runtime code of widget library . Library wrapper allows widget library to run as a library on a non native platform such as a Windows operating system and provides an application programming interface API to the widget library. Library wrapper may be implemented as a dynamic link library in the Windows operating system.

To generate a widget as it would appear in a native environment with controller chip GUI builder outputs XML widget properties of the widget to translator . Translator translates the XML widget properties from GUI builder into data structures that can be passed to the runtime code of widget library via the API defined by library wrapper . The runtime code of widget library renders the graphic representation of each widget as described by values contained in the data structures passed by library wrapper . The rendered image of the widget is returned to GUI builder . Widget builder may operate similarly to provide a view of the widget as it would appear in the native environment.

To compile the GUI for programming controller chip or running on simulator of the controller chip GUI builder outputs the XML project file to translator . Translator translates the project file into an HTML document including the applet codes for the widgets which compiler uses to generate HTML document that can be executed by controller chip . The HTML document may be programmed into controller chip or ran in simulator of the controller chip. Simulator includes an application wrapper around the runtime code of widget library . Application wrapper allows widget library to run as an application on a non native platform such as the Windows operating system.

In block widget builder provides user interface for the user to create a customized widget from a template widget or create a new template widget. Template widgets are used in GUI builder to create widgets in a GUI.

In block widget builder determines if the user wishes to create a customized widget from a template widget or create a new template widget. The user wishes to create a customized widget from a template widget when the user opens an existing template widget file by double clicking the template widget file by dragging and dropping the widget file into user interface or a user interface for a GUI builder by selecting the widget file through a file menu in user interface not shown or user interface . If so block is followed by block . The user wishes to create a new template widget when the user selects to create a new template widget through the file menu. If so block is followed by block .

In block widget builder populates a properties editor with widget properties from the existing template widget file. Referring to properties editor includes a property column for the widget parameter names a value column for the widget parameter values and a static column for making widget parameter values user editable or not in GUI builder . An image preview window may provide a list of images that may be previewed and a preview panel of a selected image in the list. To add an image to the preview list the user selects an add button to select the image. To view an image in the preview list the user selects a corresponding check box next the image in the preview list and the image is displayed in the preview panel. To delete an image from the preview list the user selects a delete button . Alternatively image preview window provides a preview of a default state image or a selected state image from properties editor . Block is followed by block .

Referring to in block widget builder receives user input for the widget properties. Referring to to add an additional widget parameter the user selects an add button to bring up a popup menu of appropriate widget parameters for the widget type. As described before widget parameter automatically appears in properties editor when it is not optional and it appears in popup menu when it is optional. To edit a widget parameter the user selects the widget parameter and enters one or more value or selects one or more values from a popup menu. The user may make a widget parameter non editable in GUI builder by checking the static box for the widget parameter. To delete a widget parameter the user selects the widget parameter and then a delete button . The user provides default values for non editable widget parameters and optionally provides default values for user editable widget parameters. Any widget parameter that is not provided by the user receives default values predetermined for the widget type.

To select a state image the user selects the box in the value column of the state image to bring up a file explorer and selects an image or multiple image components as the state image. When multiple image components are selected they are superimposed over each other to form the state image. Alternatively the user may drag and drop one image or multiple image components from the preview list in image preview window into the box to form the state image. Block is followed by block .

Referring to in block widget builder saves the widget properties and any embedded images in a customized widget file as described above regarding . The widget properties of the customized widget follow the XML syntax of the template widget as described above regarding but without the template element. Depending on the widget type widget builder may include properties for vector graphics in the widget properties. When the template widget does not include any bitmap image widget builder may generate a representative thumbnail image and save it in the widget file. The customized widget file and any external image files may be saved with other customized widget files in a widget folder known to GUI builder .

In block widget builder receives user input of the widget type for the new template widget. Widget builder may generate a popup menu from which the user selects a widget type. Block is followed by block .

In block widget builder receives user input for the widget properties. Block is similar to block . Depending on the widget type some widget parameters are optional and some are not optional. Block is followed by block .

In block widget builder saves the widget properties in a new template widget file as described above regarding . The widget properties of the customized widget follow the XML syntax of the template widget as described above regarding . The above described blocks of method may be repeated to create additional customized and template widgets.

In step GUI builder provides user interface for the user to build a GUI. Referring to user interface allows the user start a new GUI page or to add delete GUI components including text widget image and background image to from a layout canvas of the current GUI page. In response to the user selecting an add button GUI builder provides a popup menu for the user to add a GUI page a text a widget listed as controls an image or a background image. The GUI components are listed in a properties editor with their property names and values. User deletes a GUI component by selecting the GUI component from properties editor and then a delete button . Once the user adds a GUI component the user may arrange it in layout canvas and edit its properties in properties editor . GUI builder saves the GUI component as part of the GUI in an XML project file . XML project file includes one or more XML pages with XML code for the GUI components. The widgets generally follow the XML syntax of the customized widgets. Referring to step is followed by step .

In step GUI builder receives user input to add a widget which is an instance of a customized widget. The user may create a widget by selecting controls in popup menu which brings up a file explorer for selecting a customized widget file. The user may also drag and drop a customized widget file into layout canvas or right click another widget on the layout canvas and selecting a duplicate option. When a template widget file is opened in GUI builder widget builder is started to create a customized widget from the template widget. Step is followed by step .

In step GUI builder parses the selected customized widget file for the comments to extract the widget properties. Step is followed by step .

In step GUI builder populates properties editor with the user editable parameter names and their values of the selected customized widget. Properties editor includes a property column for the widget parameter names and a value column for the widget parameter values in an expandable file structure. Step is followed by step .

In step GUI builder converts the images of the customized widgets which may be in different image formats into objects of a common class and creates pointers to the image objects. Step is followed by step .

In step GUI builder creates an instance of the customized widget in memory with the widget type the widget parameters and the pointers to the image objects in memory. Step is followed by step .

In step GUI builder calls runtime rendering tool to draw and return a rendered image of the widget. GUI builder provides runtime rendering tool with the XML widget properties and pointers to the image objects.

Referring to runtime rendering tool includes translator and a library wrapper around the runtime code of widget library . Using the pointers to the image objects translator determines the size of the state image of the widget in its initial condition default state image and then translates the XML widget properties and the size of the default state image into data structures that can be passed to the runtime code of widget library via the API defined by library wrapper . The runtime code of widget library renders the graphic representation of the widget as described by the values contained in the data structures passed by the library wrapper . The rendered image of the widget is returned to GUI builder . Note that the runtime code of widget library may not need to render a bitmap default state image since it is a bitmap. Instead the runtime code of widget library returns the appropriate size and the location of the default state image relative to the other graphical elements rendered by the widget library and GUI builder constructs the final image of the widget accordingly. Alternatively the runtime code of widget library may read the default state image and construct the final image of the widget in its entirety. Step is followed by step .

Referring back to in step GUI builder displays the final image of the widget on layout canvas . GUI builder tracks the layering of the various GUI components so that it knows if the widget is displayed in front or behind other GUI components. The user may adjust the layering of the GUI components using buttons . The user may also adjust the alignment of the GUI components using buttons . Step is followed by step .

In step GUI builder determines if the user is repositioning the widget on layout canvas or resizing the widget. If so step is followed by step . Otherwise step is followed by step .

In step GUI builder displays the rendered image of the widget at a new location on layout canvas or at a new size according to user input. Step loops back to step .

In step GUI builder determines if the user is changing an editable widget property. To edit a widget property the user selects the widget property and enters one or more value or selects one or more values from a popup menu. When the user is changing an editable widget property step is followed by step . Otherwise step is followed by step .

In step GUI builder updates the instance of the widget template in memory with changes made by the user. Step is followed by step where GUI builder calls runtime rendering tool to redraw and return a new rendered image of the widget based on the changes made by the user. Note that the rendered image of the widget is updated in real time as the user makes changes e.g. as the user changes a property .

In step GUI builder determines if the user is selecting another widget in layout canvas . If so step is followed by step . Otherwise step is followed by step .

In step GUI builder determines if the user wishes to add another widget. If so step is followed by step . Otherwise step is followed by step .

In step GUI builder determines if the user wishes to compile or run the GUI. The user may compile or run the GUI by selecting a program button or a run button . If so step is followed by step . Otherwise step is followed by step where GUI builder continues to monitor for user input modifying the GUI. Steps to may be repeated for additional GUI pages. The process for adding texts images and background images are not described as they are similar to authoring an HTML page.

In step GUI builder outputs the XML project file of the GUI to translator which outputs an HTML document to compiler which generate the HTML code for programming controller chip or running in simulator of the controller chip

Line includes a start tag for a GUI page element having a NAME attribute of Page1. Lines to include overall properties for the GUI page such as transition effects for the GUI page. Lines to include properties for a background image. Specifically line shows the path to a background image file fringe.png and line shows that the image is not to be cached in volatile memory e.g. RAM in but read from nonvolatile memory e.g. flash in .

Lines to include properties for the body of the GUI page. Lines to include properties for a radio button widget. The start tag of the radio button widget includes an imageSource attribute with the path to the customized widget file. State images are not listed in these lines because they are specified in the customized widget file. shows state images and in the customized widget file in one or more embodiments of the present disclosure.

Referring back to lines to include properties for a function button widget. The start tag of the function button does not include an imageSource attribute because it is a standard widget having its entire graphics either bitmap or vector provided in widget library . Line includes a function call to jump to a GUI page named Page2 when the function button is set.

Line includes an end tag of the GUI page Page1. Line is the start tag of GUI page Page2. Lines to include the GUI components on the GUI page. Line includes an end tag of the GUI page followed by line with an end tag of the project.

In step GUI editor selects one of the one or more GUI XML pages from the project file. Step is followed by step .

In step GUI editor parses widget properties of the widget from the XML page and loads them into memory. Step is followed by step .

In step GUI editor extracts any embedded images and retrieves any external images of the widget and saves them as individual image files in a HTML temporary folder. Step is followed by step .

In step GUI editor calls translator to translate the widget properties into the HTML syntax understood by compiler . Step is followed by step .

In step GUI editor calls compiler to compile the HTML code into HTML code. Block is followed by block .

In step GUI editor determines if there is any remaining widget on the current GUI screen it has not processed. If so step is followed by step . Otherwise step is followed by step .

In step GUI editor determines if there is any remaining GUI page it has not processed. If so step is followed by step . Otherwise step is followed by step .

In block GUI editor programs controller chip with the HTML or calls simulator of the controller chip to run the HTML code.

Various other adaptations and combinations of features of the embodiments disclosed are within the scope of the invention. Instead of a PNG file a graphics interchange format GIF file may be used to container for the widget. In the GIF file the image components are saved in graphic rendering blocks and the widget source code is saved as comments in a comment extension block. Numerous embodiments are encompassed by the following claims.

VALUE color Specifies the color of the channel the handle slides along If no channel color is specified the default color is black.

VALUE color Specifies the color inside of the handle. If no handle color is specified the default color is white.

VALUE color Specifies the color of the handle frame. If no handle frame color is specified the default color is black.

VALUE color Specifies the color of the handle when being touched. If no handle frame color is specified the default color is black.

VALUE function s The function or multiple sequenced functions invoked upon the event specified in hrefEvent.

VALUE onChange onPenUp The event which triggers the launching of the href function. If set to onChange the slider will launch the function call whenever the handle is moved. If set to onPenUp the slider will only launch the function call upon the releasing of the slider handle. If hrefEvent is not specified the default is onChange.

VALUE number FromInitHref Specifies handle position when the page is loaded. The position value becomes the argument given to the href function s . If FromInitHref is selected the function specified by the InitHref attribute is called. The returned value determines the handle position. The range is 0 65535 0x00 0xFFFF .

VALUE number The maximum value used as the argument given to the function s specified in href. Maximum value is achieved when handle is full right on a horizontal slider or full top on a vertical slider. The range is 1 65535 0x01 0xFFFF .

VALUE number The minimum value used as the argument given to the function s specified in href. Minimum value is achieved when handle is full left on a horizontal slider or full bottom on a vertical slider. The range is 0 65534 0x00 0xFFFE .

VALUE LEFT RIGHT TOP BOTTOM Determines where the minimum value of the slider is located. As the handle sweeps from the minAt location the value increases until the maximum value is reached at the opposite extreme of the minAt location. Default values are LEFT for horizontal sliders and BOTTOM for vertical sliders. The options are 

VALUE color Specifies the color of the ticks drawn on the channel. If no tick color is specified the default color is black.

VALUE number NONE AUTO The total number of tick marks along the slider channel. If NONE no tick marks are visible. If AUTO the number of tick marks is derived from the min and max values. If tickCount is not given the default is NONE. The range is 0 255 0x00 0xFF .

VALUE number Specifies the number of pixels from the center of the channel the handle is located. If a vertical slider positive numbers shift the handle to the right and negative numbers shift it to the left. If a horizontal slider positive numbers shift the handle to the bottom and negative numbers shift it to the top. The range is 100 through 100.

VALUE number The width in pixels of the handle if a horizontal slider or the height of the handle if a vertical slider. If handleThickness is not given the default is 11 pixels. The range is 4 255 0x04 0xFF .

VALUE TRUE FALSE Specifies if the slider href function s is launched only upon a hit or not. By default hrefOnHitOnly is false which means the slider will launch its href upon loading the page. The href is also launched after a forceUpdate call. By setting hrefOnHitOnly to true the href will only be launched upon the slider physically being selected or upon a forceHit call.

VALUE function Only valid if FromInitHref is used as the initialCondition. Specifies the function called when the page is loaded. The value returned from this function call will be used as the initial condition of the Slider handle.

VALUE HORIZONTAL VERTICAL Specifies if the handle is to travel horizontally or vertically. The orientation parameter will override the orientation determined by the height and width dimensions.

VALUE number The length size of each tick mark in pixels. The range is 1 255 0x01 0xFF . If tickLength is not given the default is 9 pixels.

VALUE CENTER TOP BOTTOM LEFT RIGHT The position of the tick marks in relation to the channel. The range for a horizontal slider is CENTER TOP or BOTTOM. The range for a vertical slider is CENTER LEFT or RIGHT. If tickPosition is not given the default is CENTER inside the channel .

VALUE TRUE FALSE Only valid if FromInitHref is used as the initialCondition. Specifies if the Slider handle will wait for valid data before being displayed on the channel. If TRUE the Slider handle will not display until the data from the initHref function is received. If FALSE or the attribute is not present the Slider handle momentarily starts at the minAt location until the initHref function receives its data.

VALUE color Specifies the desired list fill color. If no fill color is specified the default color is the current background color.

VALUE font Specifies the font used for the option names within the list box. The corresponding .auf file must be included in the Amulet Color Color Configuration Fonts folder the root folder or the root Fonts folder. Default is Bitstream Vera Sans.

VALUE color Specifies the desired font color. If no font color is specified the default color is black.

VALUE number Specifies the font size for the option names within the list box. It can be one of the HTML sizes 1 7 or an actual point size 8 pt 99 pt such as 9 or 9 pt . Only one value is allowed per list box you cannot mix font sizes. The assigned HTML values are 

VALUE PLAIN BOLD ITALIC UNDERLINE STRIKE Specifies the style associated with the list box font. To create a custom look styles can be combined by using the logical or . However PLAIN overrides any other style. The available font styles are 

VALUE string FromInitHref Specifies which option string is highlighted when the page is loaded. The value associated with the highlighted option string is the argument given to the href function s . If FromInitHref is selected the function specified by the InitHref attribute is called. Whichever option has the same intrinsic value as the returned value from the initHref function will be initially highlighted.

VALUE string1 string2 string3 etc. Specifies the list strings. All strings are comma delimited. Note Any spaces before or after the commas are included in the text string. To specify an intrinsic value append xxx to the individual titles where xxx is a number from 0 65535 0x00 0xFFFF or a STRING. The first option displays at the top of the list and each subsequent option displays directly below the previous.

VALUE color Specifies the color of the highlighted entry in the list box. If no selection color is specified the default color is black.

VALUE color Specifies the color of the font within the highlighted entry in the list box. If no selection color is specified the default color is white.

VALUE image Specifies the page down arrow image to use when the list has more items than can be viewed. If this attribute is not present then a default image downArrow.gif located in Amulet Color Configuration Widgets List is used. Images can be either .GIF .JPG or .PNG. 

VALUE image Specifies the page down arrow image to use when the down arrow is selected. If this attribute is not present then a default image downArrowAlt.gif located in Amulet Color Configuration Widgets List is used. Images can be either .GIF .JPG or .PNG. 

VALUE function Specifies the function called when the page is loaded. Use this attribute whenever FromInitHref is used as the initialCondition. The value returned from this function call will determine which option string starts out highlighted. The value should match the intrinsic value of one of the options strings.

VALUE seconds Specifies the rate at which the list scrolls when selecting the area directly below or above the list box. The default scroll rate is 0.45 seconds. The range is 0.01 655.35.

VALUE image Specifies the page up arrow image to use when the list has more items than can be viewed. If this attribute is not present then a default image upArrow.gif located in Amulet Color Configuration Widgets List is used. Images can be either .GIF .JPG or .PNG. 

VALUE image Specifies the page up arrow image to use when the up arrow is selected. If this attribute is not present then a default image upArrowAlt.gif located in Amulet Color Configuration Widgets List is used. Images can be either .GIF .JPG or .PNG. 

