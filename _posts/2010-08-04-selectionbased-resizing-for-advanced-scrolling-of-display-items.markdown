---

title: Selection-based resizing for advanced scrolling of display items
abstract: A device may receive a selection of a first one of portions of a document, changing sizes of at least some of the portions based on the selection, determining a first location of an index button in an index bar, identify one of the portions based on the determined first location of the index button, and display the identified portion.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08769403&OS=08769403&RS=08769403
owner: Sony Mobile Communications AB
number: 08769403
owner_city: Lund
owner_country: SE
publication_date: 20100804
---
Despite recent advances in technology in writing or constructing software applications computer programmers still assemble graphical user interface GUI software components. The components include for example list boxes checklist boxes combo boxes radio buttons pop up menus tool bars scroll bars etc.

According to one aspect a method may include receiving a selection of a first one of portions of a document changing sizes of at least some of the portions based on the selection determining a first location of an index button in an index bar identifying one of the portions based on the determined first location of the index button and displaying the identified portion.

Additionally changing the sizes may include increasing sizes of portions that are adjacent to the selected portion.

Additionally identifying may include locating a portion of the document that is associated with a symbol.

Additionally changing sizes may include determining a length or height for the first one of the portions based on an available viewing area of a scrollable component that includes the index bar.

Additionally the method may further include receiving a scroll event from an operating system or an application.

Additionally a length or height of a first portion of the document corresponding to a distance traveled by the index button may be different from a length in a second portion of the document corresponding to the same distance traveled by the index button.

Additionally the method may further include determining for each of the portions of the document an input weight based on the selection of the first one of the portions.

According to another aspect a device may include a memory and a processor. The memory may store information representing an index bar including an index button and may store weights assigned to different portions of a document. The processor may modify for each of the weights a size of the portion to which the weight is assigned determine a position of the index button in the index bar and identify in the document a first portion that corresponds to the position and whose size has been modified. Additionally the processor may display the identified first portion.

Additionally the index bar may include at least one of a horizontal index bar or a vertical index bar.

Additionally the document may include a contact list. Additionally a contact in the contact list corresponding to a location of a user selection may be displayed in a larger space or larger font than other portions of the contact list.

According to yet another aspect a computer readable storage device may include computer executable instructions. The computer executable instructions may include instructions for receiving a selection of a first one of portions of a document modifying sizes of the portions based on the selection determining a first location of an index button in a scrollable component identifying one of the portions based on the determined first location of the index button and displaying the identified portion.

Additionally the instructions for identifying one of the portions may include instructions for accessing an indexed portion of the document.

Additionally the instructions for modifying may include instructions for determining a first ratio of a number of contacts under an index to a total number of contacts under all indices determining a second ratio of an input weight for the index to a sum of all weights for the indices determining a first ratio raised to a first power to obtain a first result determining a second ratio raised to a second power to obtain a second result multiplying the first result and the second result to produce a third result and computing a first weight based on the third result.

Additionally the instructions for modifying sizes further include instructions for when the third result is lower than a minimum value setting the third result to the minimum value.

Additionally the instructions for modifying sizes may include instructions for adjusting a total size of second portions of the document based on a viewing area of the scrollable component and a number of the second portions the second portions listed under an index.

Additionally a ratio of a size of the index button to a size of a scroll track of an index bar included in the scrollable component may be approximately equal to a ratio of a size of a viewing port of the scrollable component to a size of the document.

Additionally the instructions for determining the first location of the index button may include instructions for receiving a scroll event and determining the first location of the index button based on the scroll event.

Additionally the scroll event may include an event notifying the scrollable component that the index button is dragged to a particular position on an index bar that is included the scrollable component or an event notifying the scrollable component that a scroll arrow has been activated via a touch screen.

Additionally the instructions for displaying the identified portion may include instructions for graphically rendering the identified portion.

The following detailed description refers to the accompanying drawings. The same reference numbers in different drawings may identify the same or similar elements.

As used herein the term object may include an object in the object oriented programming paradigm. As used herein the term component or graphical user interface GUI component may refer to a GUI object.

In advanced scrolling a scrollable component may allow a viewer to designate or select one or more portions of a document. Once the portions are selected the scrollable component may provide the viewer with a greater viewing area for the selected portions of the document. This may allow the viewer to quickly hone in on a specific item within the document that would otherwise occupy a smaller viewing area and therefore be more difficult to locate.

Scrollable component may include GUI portions of an application not shown that can create edit store read and or delete document . As further shown in scrollable component may include a viewing port e.g. a window pane display etc. though which the application or scrollable component collectively or individually referred to as scrollable component may display a portion or all of document . When scrollable component displays entire document scrollable component may install or activate an index bar as part of scrollable component .

In a different implementation scrollable component may include additional fewer or different components than those illustrated in . For example in one implementation scrollable component may include an index bar that includes a scroll arrow and excludes index button . In another implementation scrollable component may not include index bar and may allow a user to scroll down by dragging a document relative to viewing port or by activating a scroll arrow. In yet another implementation index bar may be touch sensitive and may allow a user to use his her finger to scroll.

As discussed above viewing port may display a portion or all of document . For example in viewing port displays contacts through herein contact or contacts which may be a subset of all contacts that are included in document . Each contact includes a name phone number not shown address not shown etc. In contacts are listed in the alphabetical order of the names e.g. last name .

In one embodiment the position of index button in scroll track may correspond to the position of a document portion in document that viewing port displays. For example assume that index button is located at the top of scroll track . In such a case viewing port may display the top portion of document . In another embodiment the height of index button relative to the height of scroll track may correspond to the height of viewing port relative to the height of document .

When a user drags index button up or down along scroll track contacts in document may slide up down viewing port . However in cases where particular contact occupies a small area the user may miss contact while scrolling document . For example assume that the user is looking for information about contacts whose last name starts with the letter M. In such an instance assuming that each of contacts occupies the same amount of display space in viewing port in scrolling through contacts the user may miss Margaret Major contact .

Scrollable component may then weight the selected portions of document e.g. contacts that appear under letter M such that the selected portions of document occupy greater displayable space than other unselected portions of document . For example assume that a user touches contact . Consequently contacts that are under the letter M may be provided with a larger space as illustrated in and the user may more easily locate contact by scrolling through document . Scrollable component may also adjust the spacing between different indices in index bar e.g. more dots between M and other letters to reflect the changes in displayed document .

In some implementations document portions e.g. contacts under letter L or letter N that are not selected may be given additional space depending on their distances from the selected portions of document . For example in contacts under the letter L and N are given more or larger display spaces than contact under letter K. In some implementations scrollable component may use the additional space in modifying features that are associated with the appearance of contacts e.g. font sizes shades etc. .

By weighting the size of each of document portions selected by the user via a touch scrollable component may increase the ease with which the user may access a particular displayable portion of document . In addition the user may set reset weights on different portions of document by touching one or more areas in document e.g. a letter associated with the name or portions of document .

In this implementation user device may take the form of a smart phone e.g. a cellular phone . As shown in user device may include a speaker display microphone sensors front camera rear camera and housing . Depending on the implementation user device may include additional fewer different or different arrangement of components than those illustrated in .

Speaker may provide audible information to a user of user device . Display may provide visual information to the user such as an image of a caller video images received via cameras or a remote device etc. In addition display may include a touch screen via which user device receives user input. The touch screen may receive multi touch input or single touch input.

Microphone may receive audible information from the user and or the surroundings. Sensors may collect and provide e.g. to user device information e.g. acoustic infrared etc. that is used to aid the user in capturing images or to provide other types of information e.g. a distance between user device and a physical object .

Front camera and rear camera may enable a user to view capture store and process images of a subject in at front back of user device . Front camera may be separate from rear camera that is located on the back of user device . Housing may provide a casing for components of user device and may protect the components from outside elements.

Processor may include a processor a microprocessor an Application Specific Integrated Circuit ASIC a Field Programmable Gate Array FPGA and or other processing logic e.g. audio video processor capable of processing information and or controlling user device .

Memory may include static memory such as read only memory ROM and or dynamic memory such as random access memory RAM or onboard cache for storing data and machine readable instructions. Storage unit may include storage devices such as a floppy disk CD ROM CD read write R W disc hard disk drive HDD flash memory as well as other types of storage devices.

Input component and output component may include a display screen a keyboard a mouse a speaker a microphone a Digital Video Disk DVD writer a DVD reader Universal Serial Bus USB port and or other types of components for converting physical events or phenomena to and or from digital signals that pertain to user device .

Network interface may include a transceiver that enables user device to communicate with other devices and or systems. For example network interface may communicate via a network such as the Internet a terrestrial wireless network e.g. a WLAN a cellular network a satellite based network a wireless personal area network WPAN etc. Network interface may include a modem an Ethernet interface to a LAN and or an interface connection for connecting user device to other devices e.g. a Bluetooth interface .

Communication path may provide an interface through which components of user device can communicate with one another.

In different implementations user device may include additional fewer or different components than the ones illustrated in . For example user device may include additional network interfaces such as interfaces for receiving and sending data packets. In another example user device may include a tactile input device.

Depending on the implementation user device may include additional fewer different or different arrangement of functional components than those illustrated in . For example user device may include an application device drivers application programming interfaces communication software etc. In another example depending on the implementation scrollable component may be part of a program or an application such as a game document editor generator utility program or another type of application.

Operating system may manage resources of user device . For example operating system may allocate clock cycles to different processes allocate disk space allocate memory manage cache perform security checks etc. In particular operating system may translate input from input component e.g. mouse generate a software event corresponding to the input e.g. a scroll event and route the event to recipient components e.g. scrollable component .

Scrollable component may include an application or GUI portions of the application. In some implementations scrollable component may be included in the application. Scrollable component may process e.g. create edit delete store read etc. one or more types of documents e.g. a contact list web page text document table etc. . Scrollable component may install and operate index bar to provide the scrolling function when the size of document exceeds the displayable area of viewing port .

When operating system or another software application component sends a scroll event to scrollable component scrollable component may display a portion of document in viewing port in accordance with the scroll event and place index button at an appropriate location on scroll track . In displaying document scrollable component may perform advanced scrolling in accordance with weights logic and or mapping logic .

Weights logic may include different weights that scrollable component may apply in displaying different portions of document . For example assume that weights logic includes two values 0.333 for letter A and 0.666 for letter B. In such an instance scrollable component may enlarge via viewing port contacts whose last name starts with the letter B. Such contacts may occupy twice the space occupied by contacts whose last name starts with the letter A. Scrollable component may set the weights in weights logic when scrollable component receives user input e.g. touch that selects one or more portions of document . For example in the implementation above the user may have selected contacts beginning with the latter B.

In table input weights which may be determined by scrollable component based on the user s touch on one or more portions of document via viewing port and a number of document portions e.g. contacts under different indices e.g. different areas may be entered at column and respectively. In addition columns and may output the resulting sizes weights that are calculated based on the values input at columns and .

As shown table may include viewing port parameters list weights column relative weights column number of entries column entries percentages column mapping function column a minimum value field bounded values column display percentages column number of pixels column and bar column . In addition table may include a total weights field total relative weights field total entries field total relative entries field total mapping function values field total bounded values field total display percentages field and total number of pixels field . Depending on the implementation table may include additional fewer or different fields columns than those illustrated in .

Viewing port parameters list may include parameters that are associated with viewing port such as the SCREEN HEIGHT e.g. the height of viewing port e.g. in pixels inches centimeters points etc. MINIMUM HEIGHT e.g. the minimum height of displayed items under a letter e.g. contacts and in document TWEAK value to be described below and POWER to be described below .

Weights column may include a list of weights in percentages for each of a number of letters e.g. K L M N and O. in this example . In one implementation the weights in weights column may be determined based on whether a user touches viewing port and or based on the location of the user s touch. For example assume that the user initially touches an area under letter M in viewing port . In such an instance the area associated with letter M may be assigned a weight of 40 areas associated with letters L and N may be assigned the weight of 20 etc.

Relative weights column may include a list of ratios each ratio corresponding to a weight in weights column divided by the value of total weights field . Number of entries column may include a list of number of entries in an area e.g. a number of contacts whose last names begin with the letter L where L corresponds to an area . Entries percentages column may include a list of ratios each ratio corresponding to an entry in number of entries column divided by the value of total entries field .

Mapping function column may include a list of values that are obtained by applying a function e.g. a mathematical function program function etc. to corresponding values in relative weights column and entries percentages column . In table the function is AB where A B X and Y are a value in column a value in column the value of POWER in viewing port parameters list e.g. 1 and the value of TWEAK in viewing port parameters list e.g. 1 respectively. Mapping function ABtakes into account both the number of document portions that are associated with an area e.g. portions that are associated with an index and the input weights to determine weights for resizing the portions of document . The TWEAK value determines the relative contributions of a number of document portions in an area e.g. number of contacts under a letter and the input weight for the area.

Minimum value field may include a minimum value Y that is used for computing the mathematical function MIN X Y for each value X in mapping function column . In table the value of minimum value field is determined by the formula M S F where M S and F are the MINIMUM HEIGHT in viewing port parameters field SCREEN HEIGHT in viewing port parameters field and the value in total mapping function values field respectively.

Bounded values column may include a list of values that are obtained from the values in mapping function column by applying the function MIN C D where the MIN . is the minimum of its arguments. C is a value from mapping function column and D is a value of the minimum value field . Display percentages column may include a list of values obtained by dividing each of the values in bounded values column by the total bounded values field . Display percentages column shows the number of pixels that may be occupied by a group of contacts whose last names begin with one of letters K L M N and O.

Pixels column may include a list of number of pixels. Each number corresponds to the combined heights of contacts in an area e.g. area corresponding to a letter e.g. the height for two contacts and under letter L . Bar column visually illustrates the number of pixels in accordance with number of pixels column for each of the letters whose weights are provided in column e.g. each bar in number of pixels column may correspond to approximately 7 pixels .

Each of fields and includes the sum of the values in the corresponding columns and respectively. Fields and may be used to check the correctness of the values in columns and . For example in one implementation the values in fields and should match and respectively.

Total entries field may include the sum of the values in number of entries column and may be used to obtain the values in entries percentage column e.g. a value in a corresponding value in column divided by the value in . Total mapping function values field may include the sum of the values in mapping function column and may be used to obtain the value in minimum value field see below .

Total bounded values field may include the sum of the values in bounded values column and may be used to obtain the values in display percentages column e.g. value in column a corresponding value in column divided by the value in . Field includes the sum of the values in corresponding column . In an exemplary implementation the values in column to be correct the value in field should be equal to the screen height specified in viewing port parameters list e.g. 320 .

Table is provided for simplicity and illustrates determining weights and or sizes for letters K L M N and O. In other implementations a different table may be used to analyze weights for different letters different alphabet sets e.g. in different languages or other tokens e.g. numbers symbols links coordinates vectors etc. that identify or index different portions of document . Constructing such a table may entail using functions different from function AB using different TWEAK MINIMUM HEIGHT and or SCREEN HEIGHT values using the MAX and or the MIN function etc.

Returning to mapping logic may include a function e.g. software hardware implemented function or a table e.g. a set of values that maps positions of index button to locations in document . In different implementations mapping logic may uniformly or non uniformly map the positions of index button to different locations in document . Scrollable component may perform or enhance advanced scrolling via such mapping logic .

In the mapping is non uniform. For example a position that corresponds to 0.333 e.g. on scroll track may map to 0.38 in document . Because the relative sizes of portions and of scroll track are different from the relative sizes of corresponding portions and of document index button traveling a given unit of distance in portion of scroll track may correspond to scrolling a different amount of document than the amount scrolled when index button travels the same unit of distance in other portions and of scroll track .

Scrollable component may enhance advanced scrolling via mapping logic . In one implementation scrollable component may receive user selection of portions of document e.g. a letter in . Furthermore scrollable component may determine weights for mapping different portions of document to scroll track based on calculations that are similar to those illustrated by table in . Via mapping logic scrolling component may scroll different portions of document e.g. portions and at different rates.

In mapping logic maps three different portions of scroll track to three different portions e.g. areas of document . Depending on the implementation mapping logic may provide for mapping additional or fewer portions of scroll track to additional or fewer portions of document .

Scrollable component may obtain weights and data for weights logic and mapping logic block . For example in one implementation scrollable component may receive user input for selecting one or more portions of document e.g. touching a letter . Based on the selection scrollable component may determine input weights and or data for calculating weights that may be used to resize portions of document . For example assume that a user touches the letter M in . In response scrollable component may generate weights 10 20 40 20 and 10 for letters K L M N O e.g. letters that are shown in viewing port . In some implementations scrollable component may also determine weights data needed for mapping logic to map different portions of scroll track to portions of document .

Scrollable component may set the weights in weights logic and data in mapping logic block . For example after obtaining the weights at block scrollable component may place the weights in column e.g. values that weights logic may use to populate a set of parameters that are similar to the ones included in table . The data may establish an association between portions of scroll track and document . The weights that are determined block and set block may depend on the type of document loaded e.g. a web page contact list etc. and the program for handling the document.

Scrollable component may receive a scroll event block . For example operating system or an application may generate an event e.g. a software event e.g. clicking on scroll arrow touching index button with one s finger etc. that is associated with GUI portions of scrollable component and pass the event to scrollable component .

Scrollable component may determine the location of index button block . For example when a user drags index button to a specific location on scroll track scrollable component may obtain the location of index button from index bar and or a subcomponent of index bar e.g. scroll track or index button . In another example when a user clicks on a scroll arrow not shown scrollable component may obtain the current location of index button by adding or subtracting a fixed value constant from the last location of index button . The location may be determined and or expressed in terms of inches centimeters pixels points a ratio etc.

Scrollable component may determine in document a location that corresponds to the location determined at block block . For example after obtaining the location of index button scrollable component may apply mapping logic to coordinates e.g. one or more numbers corresponding to the location of index button . Mapping logic may provide for uniform or non uniform mapping between different portions of scroll track and document .

Scrollable component may determine items to display block . For example scrollable component may determine a portion of document to be viewed through viewing port based on the location determined at block and the dimensions of viewing port .

In some implementations scrollable component may create or complete a graphical representation of document in memory after weights are set at block . In creating the representation based on the weights in weights logic scrollable component may provide for a magnified or a smaller version of portions of document . For example assume that a user has touched the letter M on viewing port of scrollable component in . After the touch scrollable component may enlarge contact listed under the letter M as illustrated in .

In other implementations scrollable component may dynamically generate a graphical representation of document portions that are to be displayed via viewing port and not yet generate graphical representations of other portions. That is scrollable component may generate the graphical representation on need basis based on user input that specifies which portion of document is to be displayed via viewing port .

At block scrollable component may display the portion of document . In some implementations scrollable component may display previously generated graphical data for needed for displaying document . In other implementations scrollable component may generate on the fly a graphical representation of the document portion that is determined at block .

In process index bar may be scaled in accordance with different settings that are associated with displaying document . Index bar may change when the user changes the appearance of document .

The foregoing description of implementations provides illustration but is not intended to be exhaustive or to limit the implementations to the precise form disclosed. Modifications and variations are possible in light of the above teachings or may be acquired from practice of the teachings.

For example in the above scrollable component is illustrated and described as including a vertical index bar . In other implementations scrollable component may include a horizontal index bar and or index bar .

The functions formulas and weights described above are exemplary. In different implementations different functions formulas and or weights may be used depending on a particular type of document that scrollable component handles. For example scrollable component may determine weights for selected contacts in a manner different from that for selected items in a web page.

In the above while series of blocks have been described with regard to the exemplary process the order of the blocks may be modified in other implementations. In addition non dependent blocks may represent acts that can be performed in parallel to other blocks. Further depending on the implementation of functional components some of the blocks may be omitted from one or more processes.

It will be apparent that aspects described herein may be implemented in many different forms of software firmware and hardware in the implementations illustrated in the figures. The actual software code or specialized control hardware used to implement aspects does not limit the invention. Thus the operation and behavior of the aspects were described without reference to the specific software code it being understood that software and control hardware can be designed to implement the aspects based on the description herein.

It should be emphasized that the term comprises comprising when used in this specification is taken to specify the presence of stated features integers steps or components but does not preclude the presence or addition of one or more other features integers steps components or groups thereof.

Further certain portions of the implementations have been described as logic that performs one or more functions. This logic may include hardware such as a processor a microprocessor an application specific integrated circuit or a field programmable gate array software or a combination of hardware and software.

No element act or instruction used in the present application should be construed as critical or essential to the implementations described herein unless explicitly described as such. Also as used herein the article a is intended to include one or more items. Further the phrase based on is intended to mean based at least in part on unless explicitly stated otherwise.

