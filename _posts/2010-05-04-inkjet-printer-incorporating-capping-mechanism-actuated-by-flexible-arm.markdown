---

title: Inkjet printer incorporating capping mechanism actuated by flexible arm
abstract: An inkjet printer includes a printhead assembly for ejecting ink upon print media; a capping molding for engaging a face of the printhead assembly; and an actuator for actuating the capping molding against and away from the printhead assembly. The actuator includes a flexible arm attached at one end to the capping molding and at the other end to slip and drive wheels. The slip and drive wheels facilitating actuation of the capping molding via the flexible arm. The flexible arm facilitates conformation of the capping molding against the printhead assembly.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08348378&OS=08348378&RS=08348378
owner: Zamtec Ltd
number: 08348378
owner_city: Dublin
owner_country: IE
publication_date: 20100504
---
This is a Continuation of U.S. Ser. No. 11 775 156 filed on Jul. 9 2007 now issued U.S Pat. No. 7 717 538 which is a Continuation of U.S. Ser. No. 11 006 663 filed on Dec. 8 2004 now issued U.S. Pat. No. 7 265 877 which is a Continuation of U.S. Ser. No. 10 636 230 filed on Aug. 8 2003 now issued U.S. Pat. No. 7 591 522 which is a divisional of Ser. No. 09 436 747 filed on Nov. 9 1999 now granted U.S. Pat. No. 6 687 022 all of which are herein incorporated by reference in their entirety for all purposes.

This invention concerns a resource held in computer memory and multiple parallel processors which require simultaneous access to the resource. The resource may be a dither matrix or dither volume used for digitally halftoning a contone color image in the form of an array of contone color pixel values to bi level dots and this may be required to be accessed by different thresholding units in parallel. In another aspect the invention is a method of accessing such a resource.

Where multiple parallel processors require simultaneous access to a resource held in computer memory several strategies are possible. First the processors could take turns to access the resource however this reduces the performance of the processors. Second multi ported memory could be employed and third the entire resource could be replicated in different memory banks both the last options are expensive.

A particular example of a resource held in computer memory is a dither matrix or dither volume used for digitally halftoning a contone color image. When dither cell registration is not desired between different color planes of the image a set thresholding units handling the dithering of individual color components may require simultaneous access to a different dither cell locations.

According to an aspect of the present disclosure an inkjet printer includes a printhead assembly for ejecting ink upon print media a capping molding for engaging a face of the printhead assembly and an actuator for actuating the capping molding against and away from the printhead assembly. The actuator includes a flexible arm attached at one end to the capping molding and at the other end to slip and drive wheels. The slip and drive wheels facilitating actuation of the capping molding via the flexible arm. The flexible arm facilitates conformation of the capping molding against the printhead assembly.

The invention will be described with reference to a high performance color printer which combines photographic quality image reproduction with magazine quality text reproduction. The printer utilizes an 8 page width drop on demand microelectromechanical inkjet MEMJET printhead which produces 1600 dots per inch dpi bi level CMYK Cyan Magenta Yellow blacK . It prints 30 full color A4 or Letter pages per minute and is intended as an entry level desktop printer. The printer has been designated as iPrint and will be referred to by that name in the following description.

iPrint reproduces black text and graphics directly using bi level black and continuous tone contone images and graphics using dithered bi level CMYK. For practical purposes iPrint supports a black resolution of 800 dpi and a contone resolution of 267 pixels per inch ppi .

iPrint is in use attached to a workstation or personal computer PC via a relatively low speed 1.5 MBytes s universal serial bus USB connection. iPrint relies on the PC to render each page to the level of contone pixels and black dots. The PC compresses each rendered page to less than 3 MB for sub two second delivery to the printer. iPrint decompresses and prints the page line by line at the speed of the MEMJET printhead. iPrint contains sufficient buffer memory for two compressed pages 6 MB allowing it to print one page while receiving the next but does not contain sufficient buffer memory for even a single uncompressed page 119 MB .

The standard MEMJET nozzle layout has a half inch unit cell and so can be trivially adapted to page widths which are multiples of half an inch. Arbitrary page widths can be achieved with custom nozzle layouts in markets which justify such specialisation. The initial MEMJET building block is a widely useful four inch printhead which makes efficient use of a six inch silicon wafer. The iPrint design therefore assumes an eight inch MEMJET printhead made up of two four inch printheads joined together. The use of a wider printhead to achieve full bleed on A4 Letter pages only affects a few aspects of the iPrint design specifically the exact mechanical design and the logic of the printhead interface.

A MEMJET printhead produces 1600 dpi bi level CMYK. On low diffusion paper each ejected drop forms an almost perfectly circular 22.5 micron diameter dot. Dots are easily produced in isolation allowing dispersed dot dithering to be exploited to its fullest. Since the MEMJET printhead is page width and operates with a constant paper velocity the four color planes are printed in perfect registration allowing ideal dot on dot printing. Since there is consequently no spatial interaction between color planes the same dither matrix is used for each color plane.

A page layout may contain a mixture of images graphics and text. Continuous tone contone images and graphics are reproduced using a stochastic dispersed dot dither. Unlike a clustered dot or amplitude modulated dither a dispersed dot or frequency modulated dither reproduces high spatial frequencies i.e. image detail almost to the limits of the dot resolution while simultaneously reproducing lower spatial frequencies to their full color depth. A stochastic dither matrix is carefully designed to be free of objectionable low frequency patterns when tiled across the image. As such its size typically exceeds the minimum size required to support a number of intensity levels i.e. 16 16 8 bits for 257 intensity levels . iPrint uses a dither volume of size 64 64 3 8 bits. The dither volume provides an extra degree of freedom during the design of the dither by allowing a dot to change states multiple times through the intensity range rather than just once as in a conventional dither matrix.

Human contrast sensitivity peaks at a spatial frequency of about 3 cycles per degree of visual field and then falls off logarithmically decreasing by a factor of 100 and becoming difficult to measure beyond about 40 cycles per degree. At a normal viewing distance of between 400 mm and 250 mm this translates roughly to 150 250 cycles per inch cpi on the printed page or 300 500 samples per inch according to Nyquist s theorem. Taking into account the fact that color sensitivity is less acute than grayscale sensitivity contone resolution beyond about 400 pixels per inch ppi is therefore of limited utility and in fact contributes slightly to color error through the dither.

Black text and graphics are reproduced directly using bi level black dots and are therefore not antialiased i.e. low pass filtered before being printed. Text is therefore supersampled beyond the perceptual limits discussed above to produce smooth edges when spatially integrated. Text resolution up to about 1200 dpi continues to contribute to perceived text sharpness assuming low diffusion paper of course .

USB Universal Serial Bus is the standard low speed peripheral connection on new PCs. The standard high speed peripheral connection IEEE 1394 is recommended but unfortunately still optional in the PC 99 specification and so may not be in widespread use when iPrint is first launched. iPrint therefore connects to a personal computer PC or workstation via USB and the speed of the USB connection therefore imposes the most significant constraint on the architecture of the iPrint system. At a sustained printing rate of 30 pages minute USB at 1.5 MByte s imposes an average limit of 3 MB page. Since the act of interrupting a MEMJET based printer during the printing of a page produces a visible discontinuity it is advantageous for the printer to receive the entire page before commencing printing to eliminate the possibility of buffer underrun. Since the printer can contain only limited buffer memory i.e. two pages worth or 6 MB then the 3 MB page limit must be considered absolute.

Other desktop connection options provide similar bandwidth to USB and so impose similar constraints on the architecture. These include the parallel port at 2 MB s and 10Base T Ethernet at around 1 MB s

Page rendering or rasterization can be split between the PC and printer in various ways. Some printers support a full page description language PDL such as Postscript and contain correspondingly sophisticated renderers. Other printers provide special support only for rendering text to achieve high text resolution. This usually includes support for built in or downloadable fonts. In each case the use of an embedded renderer reduces the rendering burden on the PC and reduces the amount of data transmitted from the PC to the printer. However this comes at a price. These printers are more complex than they might be and are often unable to provide full support for the graphics system of the PC through which application programs construct render and print pages. They often fail to exploit the high performance of current PCs and are unable to leverage projected exponential growth in PC performance.

iPrint relies on the PC to render pages i.e. contone images and graphics to the pixel level and black text and graphics to the dot level. iPrint contains only a simple rendering engine which dithers the contone data and combines the results with any foreground bi level black text and graphics. This strategy keeps the printer simple and independent of any page description language or graphics system. It fully exploits the high performance of current PCs. The downside of this strategy is the potentially large amount of data which must be transmitted from the PC to the printer. We consequently use compression to reduce this data to the 3 MB page required to allow a sustained printing rate of 30 pages minute.

An 8 by 11.7 A4 page has a bi level CMYK pagesize of 114.3 MBytes at 1600 dpi and a contone CMYK pagesize of 32.1 MB at 300 ppi.

Although JPEG is inherently lossy for compression ratios of 10 1 or less the loss is usually negligible. To obtain an integral contone to bi level ratio and to provide some compression leeway we choose a contone resolution of 267 ppi. This yields a contone CMYK pagesize of 25.5 MB a corresponding compression ratio of 8.5 1 to fit within the 3 MB page limit and a contone to bi level ratio of 1 6 in each dimension.

A full page of black text and or graphics rasterized at printer resolution 1600 dpi yields a bi level image of 28.6 MB. Since rasterizing text at 1600 dpi places a heavy burden on the PC for a small gain we choose to rasterize text at a fully acceptable 800 dpi. This yields a bi level image of 7.1 MB requiring a lossless compression ratio of less than 2.5 1 to fit within the 3 MB page limit. We achieve this with a two dimensional compression scheme adapted from Group 4 Facsimile all indicated generally at .

As long as the image and text regions of a page are non overlapping any combination of the two fits within the 3 MB limit. If text lies on top of a background image then the worst case is a compressed pagesize approaching 6 MB depending on the actual text compression ratio . This fits within the printer s page buffer memory but prevents double buffering of pages in the printer thereby reducing the printer s page rate by two thirds i.e. to 10 pages minute.

As described above the PC renders contone images and graphics to the pixel level and black text and graphics to the dot level. These are compressed by different means and transmitted together to the printer.

The printer contains two 3 MB page buffers one for the page being received from the PC and one for the page being printed. The printer expands the compressed page as it is being printed. This expansion consists of decompressing the 267 ppi contone CMYK image data halftoning the resulting contone pixels to 1600 dpi bi level CMYK dots decompressing the 800 dpi bi level black text data and compositing the resulting bi level black text dots over the corresponding bi level CMYK image dots .

Because of the simplicity of the page width MEMJET printhead iPrint is very compact. It measures just 270 mm wide 85 mm deep 77 mm high when closed. is a pictorial view of the iPrint when closed.

The cover opens to form part of the paper tray as shown in . A second part is hinged within cover and opens to extend the paper tray. A paper exit tray is slideably extendable from the front of the printer.

The front panel revealed when cover is opened contains the user interface the power button and power indicator LED the paper feed button and the out of paper and ink low LEDs.

iPrint uses a standard paper transport mechanism. The paper path is illustrated in in which a single stepper motor drives both the sheet feed roller and the paper transport. When running in the forward direction the stepper motor drives the paper drive roller and the pinch wheels at the start and end of the active paper path respectively. When reversed the stepper motor drives the sheet feed roller which grabs the topmost sheet from the sheet feeder and transports it the short distance to the paper drive roller where it is detected by the mechanical media sensor .

The paper centering sliders ensure that the paper is centered. This ensures that a single centered media sensor detects the sheet and also ensures that sheets wider than the printhead are printed with balanced margins.

The replaceable MEMJET printhead cartridge is also shown in . This represents one of the four possible ways to deploy the printhead in conjunction with the ink cartridge in a product such as iPrint 

Under the printhead cartridge is a printhead assembly and a printhead capping mechanism illustrated in pictorial cut away view in and in section in . When not in use the MEMJET printhead remains filled with ink and so must be capped to prevent evaporation of ink through the nozzles. Ink evaporation can lead to gradual deposition of ink components which can impair nozzle operation.

iPrint includes a mechanical page width capping mechanism which consists of a pivoting capping molding with an elastomeric seal and sponge . When the printhead is not in use the capping molding is held by a spring against the face of the printhead assembly and the elastomeric seal conforms to the face of the printhead assembly and creates an airtight seal around the printhead . The sponge is used to catch drops ejected during the printhead cleaning cycle. When the printhead is in use the capping molding is held away from the printhead assembly and out of the paper path.

The capping molding is offset by a set of flexible arms from a rod . The capping molding and arms pivot with the rod about its axis. A slip wheel is mounted at the end of rod . The slip wheel makes contact with a drive wheel . When printing is occurring the drive wheel is coupled to the paper transport motor and is driven in the uncapping direction . This causes the slip wheel and rod to rotate about its axis and swings the capping molding away from the printhead. Once the slip wheel rotates to the uncapping slip point the slip wheel and the capping molding stop rotating. When printing is complete the drive wheel is reversed and driven in the capping direction . Once the slip wheel rotates to the capping slip point the slip wheel and the capping molding stop rotating and the capping spring holds the capping plate in place against the face of the printhead assembly. The flexible arms help the capping plate conform to the face of the printhead assembly .

The printer controller is illustrated in and consists of a small PCB with only a few components a 64 Mbit RDRAM the iPrint Central Processor ICP chip a speaker for notifying the user of error conditions a QA chip an external 3V DC power connection an external USB connection a connection to the paper transport stepper motor and the flex PCB which connects to the media sensor LEDs and buttons and and a link the printhead .

There are two versions of the ink cartridge one large one small. Both fit in the same ink cartridge slot at the back of the iPrint unit.

This section describes the printer control protocol used between a host and iPrint. It includes control and status handling as well as the actual page description.

The USB device class definition for printers provides for emulation of both unidirectional and bidirectional IEEE 1284 parallel ports. At its most basic level this allows the host to determine printer capabilities obtain printer status and reset the printer

Personal computer printing subsystems typically provide some level of IEEE 1284 sup port. Compatibility with IEEE 1284 in a printer therefore simplifies the development of the corresponding printer driver. The USB device class definition for printers seeks to leverage this same compatibility.

iPrint supports no control protocol beyond the USB device class definition for printers. Note that if a higher level control protocol were defined then conditions such as out of ink could also be reported to the user rather than just via the printer s out of ink LED .

iPrint receives page descriptions as raw transfers i.e. not encapsulated in any higher level control protocol.

iPrint reproduces black at full dot resolution 1600 dpi but reproduces contone color at a somewhat lower resolution using halftoning. The page description is therefore divided into a black layer and a contone layer. The black layer is defined to composite over the contone layer.

The black layer consists of a bitmap containing a 1 bit opacity for each pixel. This black layer matte has a resolution which is an integer factor of the printer s dot resolution. The highest supported resolution is 1600 dpi i.e. the printer s full dot resolution.

The contone layer consists of a bitmap containing a 32 bit CMYK color for each pixel. This contone image has a resolution which is an integer factor of the printer s dot resolution. The highest supported resolution is 267 ppi i.e. one sixth the printer s dot resolution.

The contone resolution is also typically an integer factor of the black resolution to simplify calculations in the printer driver. This is not a requirement however.

The black layer and the contone layer are both in compressed form for efficient transmission over the low speed USB connection to the printer.

iPrint has a printable page area which is determined by the width of its printhead the characteristics of its paper path and the size of the currently selected print medium.

The printable page area has a maximum width of 8 . If the physical page width exceeds 8 then symmetric left and right margins are implicitly created. If the physical page width is less than 8 then the printable page width is reduced accordingly. The printable page area has no maximum length. It is simply the physical page length less the top and bottom margins imposed by the characteristics of the paper path.

The target page size is constrained by the printable page area less the explicit target left and top margins specified in the page description.

In theory iPrint does not impose a top or bottom margin i.e. it allows full bleed in the vertical direction. In practice however since iPrint is not designed as a full bleed A4 Letter printer because it uses an 8 printhead an artificial top and bottom margin is imposed to avoid having to include a sponge large enough to cope with regular off edge printing.

Apart from being implicitly defined in relation to the printable page area each page description is complete and self contained. There is no data transmitted to the printer separately from the page description to which the page description refers.

The page description contains a signature and version which allow the printer to identify the page description format. If the signature and or version are missing or incompatible with the printer then the printer can reject the page.

The page description defines the resolution and size of the target page. The black and contone layers are clipped to the target page if necessary. This happens whenever the black or contone scale factors are not factors of the target page width or height.

The target left and top margins define the positioning of the target page within the printable page area.

The black layer parameters define the pixel size of the black layer its integer scale factor to the target resolution and the size of its compressed page data. The variable size black page data follows the fixed size parts of the page description.

The contone layer parameters define the pixel size of the contone layer its integer scale factor to the target resolution and the size of its compressed page data. The variable size contone page data follows the variable size black page data.

The variable size black page data and the variable size contone page data are aligned to 8 byte boundaries. The size of the required padding is included in the size of the fixed size part of the page description structure and the variable size black data.

The entire page description has a target size of less than 3 MB and a maximum size of 6 MB in accordance with page buffer memory in the printer.

The following sections describe the format of the compressed black layer and the compressed contone layer.

The Group 3 Facsimile compression algorithm losslessly compresses bi level data for transmission over slow and noisy telephone lines. The bi level data represents scanned black text and graphics on a white background and the algorithm is tuned for this class of images it is explicitly not tuned for example for halftoned bi level images . The 1D Group 3 algorithm runlength encodes each scanline and then Huffman encodes the resulting runlengths. Runlengths in the range 0 to 63 are coded with terminating codes. Runlengths in the range 64 to 2623 are coded with make up codes each representing a multiple of 64 followed by a terminating code. Runlengths exceeding 2623 are coded with multiple make up codes followed by a terminating code. The Huffman tables are fixed but are separately tuned for black and white runs except for make up codes above 1728 which are common . When possible the 2D Group 3 algorithm encodes a scanline as a set of short edge deltas 0 1 2 3 with reference to the previous scanline. The delta symbols are entropy encoded so that the zero delta symbol is only one bit long etc. Edges within a 2D encoded line which can t be delta encoded are runlength encoded and are identified by a prefix. 1D and 2D encoded lines are marked differently. 1D encoded lines are generated at regular intervals whether actually required or not to ensure that the decoder can recover from line noise with minimal image degradation. 2D Group 3 achieves compression ratios of up to 6 1.

The Group 4 Facsimile algorithm losslessly compresses bi level data for transmission over error free communications lines i.e. the lines are truly error free or error correction is done at a lower protocol level . The Group 4 algorithm is based on the 2D Group 3 algorithm with the essential modification that since transmission is assumed to be error free 1D encoded lines are no longer generated at regular intervals as an aid to error recovery. Group 4 achieves compression ratios ranging from 20 1 to 60 1 for the CCITT set of test images.

The design goals and performance of the Group 4 compression algorithm qualify it as a compression algorithm for the bi level black layer. However its Huffman tables are tuned to a lower scanning resolution 100 400 dpi and it encodes runlengths exceeding 2623 awkwardly. At 800 dpi our maximum runlength is currently 6400. Although a Group 4 decoder core might be available for use in the printer controller chip it might not handle runlengths exceeding those normally encountered in 400 dpi facsimile applications and so would require modification.

Since most of the benefit of Group 4 comes from the delta encoding a simpler algorithm based on delta encoding alone is likely to meet our requirements. This approach is described in detail below.

The edge delta and runlength EDRL compression format is based loosely on the Group 4 compression format and its precursors.

EDRL uses three kinds of symbols appropriately entropy coded. These are create edge kill edge and edge delta. Each line is coded with reference to its predecessor. The predecessor of the first line is defined to a line of white. Each line is defined to start off white. If a line actually starts of black the less likely situation then it must define a black edge at offset zero. Each line must define an edge at its left hand end i.e. at offset page width.

An edge can be coded with reference to an edge in the previous line if there is an edge within the maximum delta range with the same sense white to black or black to white . This uses one of the edge delta codes. The shorter and likelier deltas have the shorter codes. The maximum delta range 2 is chosen to match the distribution of deltas for typical glyph edges. This distribution is mostly independent of point size.

An edge can also be coded using the length of the run from the previous edge in the same line. This uses one of the create edge codes for short 7 bit and long 13 bit runlengths. For simplicity and unlike Group 4 runlengths are not entropy coded. In order to keep edge deltas implicitly synchronised with edges in the previous line each unused edge in the previous line is killed when passed in the current line. This uses the kill edge code. The end of page code signals the end of the page to the decoder.

Note that 7 bit and 13 bit runlengths are specifically chosen to support 800 dpi A4 Letter pages. Longer runlengths could be supported without significant impact on compression performance. For example if supporting 1600 dpi compression the runlengths should be at least 8 bit and 14 bit respectively. A general purpose choice might be 8 bit and 16 bit thus supporting up to 40 wide 1600 dpi pages.

Note that there is no end of line code. The decoder uses the page width to detect the end of the line. The lengths of the codes are ordered by the relative probabilities of the codes occurrence.

Table 5 shows the compression performance of Group 4 and EDRL on the CCITT test documents used to select the Group 4 algorithm. Each document represents a single page scanned at 400 dpi. Group 4 s superior performance is due to its entropy coded runlengths tuned to 400 dpi features.

Magazine text is typically typeset in a typeface with serifs such as Times at a point size of 10. At this size an A4 Letter page holds up to 14 000 characters though a typical magazine page holds only about 7 000 characters. Text is seldom typeset at a point size smaller than 5. At 800 dpi text cannot be meaningfully rendered at a point size lower than 2 using a standard typeface.

Table 7 shows Group 4 and EDRL compression performance on pages of text of varying point sizes rendered at 800 dpi. Note that EDRL achieves the required compression ratio of 2.5 for an entire page of text typeset at a point size of 3. The distribution of characters on the test pages is based on English language statistics.

For a point size of 9 or greater EDRL slightly outperforms Group 4 simply because Group 4 s runlength codes are tuned to 400 dpi.

These compression results bear out the observation that entropy encoded runlengths contribute much less to compression than 2D encoding unless the data is poorly correlated vertically such as in the case of very small characters.

The JPEG compression algorithm lossily compresses a contone image at a specified quality level. It introduces imperceptible image degradation at compression ratios below 5 1 and negligible image degradation at compression ratios below 10 1.

JPEG typically first transforms the image into a color space which separates luminance and chrominance into separate color channels. This allows the chrominance channels to be subsampled without appreciable loss because of the human visual system s relatively greater sensitivity to luminance than chrominance. After this first step each color channel is compressed separately.

The image is divided into 8 8 pixel blocks. Each block is then transformed into the frequency domain via a discrete cosine transform DCT . This transformation has the effect of concentrating image energy in relatively lower frequency coefficients which allows higher frequency coefficients to be more crudely quantized. This quantization is the principal source of compression in JPEG. Further compression is achieved by ordering coefficients by frequency to maximise the likelihood of adjacent zero coefficients and then runlength encoding runs of zeroes. Finally the runlengths and non zero frequency coefficients are entropy coded. Decompression is the inverse process of compression.

The CMYK contone layer is compressed to an interleaved color JPEG bytestream. The interleaving is required for space efficient decompression in the printer but may restrict the decoder to two sets of Huffman tables rather than four i.e. one per color channel . If luminance and chrominance are separated then the luminance channels can share one set of tables and the chrominance channels the other set.

If luminance chrominance separation is deemed necessary either for the purposes of table sharing or for chrominance subsampling then CMY is converted to YCrCb and Cr and Cb are duly subsampled. K is treated as a luminance channel and is not subsampled.

The JPEG bytestream is complete and self contained. It contains all data required for decompression including quantization and Huffman tables.

An 8 inch MEMJET printhead consists of two standard 4 inch MEMJET printheads joined together side by side. The two 4 inch printheads are wired up together in a specific way for use in iPrint. Since the wiring requires knowledge of the 4 inch printhead an overview of the 4 inch printhead is presented here.

Each 4 inch printhead consists of 8 segments each segment an inch in length. Each of the segments prints bi level cyan magenta yellow and black dots over a different part of the page to produce the final image.

Since the printhead prints dots at 1600 dpi each dot is approximately 22.5 microns in diameter and spaced 15.875 microns apart. Thus each half inch segment prints 800 dots with the 8 segments corresponding to the positions shown in Table 8.

Although each segment produces 800 dots of the final image each dot is represented by a combination of bi level cyan magenta yellow and black ink. Because the printing is bi level the input image should be dithered or error diffused for best results.

Each segment then contains 3 200 nozzles 800 each of cyan magenta yellow and black. A four inch printhead contains 8 such segments for a total of 25 600 nozzles.

The nozzles within a single segment are grouped for reasons of physical stability as well as minimization of power consumption during printing. In terms of physical stability a total of 10 nozzles share the same ink reservoir. In terms of power consumption groupings are made to enable a low speed and a high speed printing mode.

The printhead supports two printing speeds to allow speed power consumption trade offs to be made in different product configurations.

In the low speed printing mode 128 nozzles are fired simultaneously from each 4 inch printhead. The fired nozzles should be maximally distant so 16 nozzles are fired from each segment. To fire all 25 600 nozzles 200 different sets of 128 nozzles must be fired.

In the high speed printing mode 256 nozzles are fired simultaneously from each 4 inch printhead. The fired nozzles should be maximally distant so 32 nozzles are fired from each segment. To fire all 25 600 nozzles 100 different sets of 256 nozzles must be fired.

The power consumption in the low speed mode is half that of the high speed mode. Note however that the energy consumed to print a page is the same in both cases.

A single pod consists of 10 nozzles sharing a common ink reservoir. 5 nozzles are in one row and 5 are in another. Each nozzle produces dots 22.5 microns in diameter spaced on a 15.875 micron grid. shows the arrangement of a single pod with the nozzles numbered according to the order in which they must be fired.

Although the nozzles are fired in this order the relationship of nozzles and physical placement of dots on the printed page is different. The nozzles from one row represent the even dots from one line on the page and the nozzles on the other row represent the odd dots from the adjacent line on the page. shows the same pod with the nozzles numbered according to the order in which they must be loaded.

The nozzles within a pod are therefore logically separated by the width of 1 dot. The exact distance between the nozzles will depend on the properties of the MEMJET firing mechanism. The printhead is designed with staggered nozzles designed to match the flow of paper.

One pod of each color that is cyan magenta yellow and black are grouped into a chromapod . A chromapod represents different color components of the same horizontal set of 10 dots on different lines. The exact distance between different color pods depends on the MEMJET operating parameters and may vary from one MEMJET design to another. The distance is considered to be a constant number of dot widths and must therefore be taken into account when printing the dots printed by the cyan nozzles will be for different lines than those printed by the magenta yellow or black nozzles. The printing algorithm must allow for a variable distance up to about 8 dot widths between colors. illustrates a single chromapod.

5 chromapods are organized into a single podgroup . Since each chromapod contains nozzles each podgroup contains nozzles 50 cyan 50 magenta 50 yellow and 50 black nozzles. The arrangement is shown in with chromapods numbered 0 4. Note that the distance between adjacent chromapods is exaggerated for clarity.

2 podgroups are organized into a single phasegroup . The phasegroup is so named because groups of nozzles within a phasegroup are fired simultaneously during a given firing phase this is explained in more detail below . The formation of a phasegroup from 2 podgroups is entirely for the purposes of low speed and high speed printing via 2 PodgroupEnable lines.

During low speed printing only one of the two PodgroupEnable lines is set in a given firing pulse so only one podgroup of the two fires nozzles. During high speed printing both PodgroupEnable lines are set so both podgroups fire nozzles. Consequently a low speed print takes twice as long as a high speed print since the high speed print fires twice as many nozzles at once.

Two phasegroups PhasegroupA and PhasegroupB are organized into a single firegroup with 4 firegroups in each segment . Firegroups are so named because they all fire the same nozzles simultaneously. Two enable lines AEnable and BEnable allow the firing of PhasegroupA nozzles and PhasegroupB nozzles independently as different firing phases. The arrangement is shown in . The distance between adjacent groupings is exaggerated for clarity.

A single 4 inch printhead contains a total of 25 600 nozzles. A Print Cycle involves the firing of up to all of these nozzles dependent on the information to be printed. A Load Cycle involves the loading up of the printhead with the information to be printed during the subsequent Print Cycle.

Each nozzle has an associated NozzleEnable bit that determines whether or not the nozzle will fire during the Print Cycle. The NozzleEnable bits one per nozzle are loaded via a set of shift registers.

Logically there are 4 shift registers per segment one per color each 800 deep. As bits are shifted into the shift register for a given color they are directed to the lower and upper nozzles on alternate pulses. Internally each 800 deep shift register is comprised of two 400 deep shift registers one for the upper nozzles and one for the lower nozzles. Alternate bits are shifted into the alternate internal registers. As far as the external interface is concerned however there is a single 800 deep shift register.

Once all the shift registers have been fully loaded 800 load pulses all of the bits are transferred in parallel to the appropriate NozzleEnable bits. This equates to a single parallel transfer of 25 600 bits. Once the transfer has taken place the Print Cycle can begin. The Print Cycle and the Load Cycle can occur simultaneously as long as the parallel load of all NozzleEnable bits occurs at the end of the Print Cycle.

The Load Cycle is concerned with loading the printhead s shift registers with the next Print Cycle s NozzleEnable bits.

Each segment has 4 inputs directly related to the cyan magenta yellow and black shift registers. These inputs are called CDataIn MDataIn YDataIn and KDataIn. Since there are 8 segments there are a total of 32 color input lines per 4 inch printhead. A single pulse on the SRClock line shared between all 8 segments transfers the 32 bits into the appropriate shift registers. Alternate pulses transfer bits to the lower and upper nozzles respectively. Since there are 25 600 nozzles a total of 800 pulses are required for the transfer. Once all 25 600 bits have been transferred a single pulse on the shared PTransfer line causes the parallel transfer of data from the shift registers to the appropriate NozzleEnable bits.

The parallel transfer via a pulse on PTransfer must take place after the Print Cycle has finished. Otherwise the NozzleEnable bits for the line being printed will be incorrect.

Since all 8 segments are loaded with a single SRClock pulse any printing process must produce the data in the correct sequence for the printhead. As an example the first SRClock pulse will transfer the CMYK bits for the next Print Cycle s dot and . The second SRClock pulse will transfer the CMYK bits for the next Print Cycle s dot and . After 800 SRClock pulses the PTransfer pulse can be given.

It is important to note that the odd and even CMYK outputs although printed during the same Print Cycle do not appear on the same physical output line. The physical separation of odd and even nozzles within the printhead as well as separation between nozzles of different colors ensures that they will produce dots on different lines of the page. This relative difference must be accounted for when loading the data into the printhead. The actual difference in lines depends on the characteristics of the inkjet mechanism used in the printhead. The differences can be defined by variables Dand Dwhere Dis the distance between nozzles of different colors and Dis the distance between nozzles of the same color.

Data can be clocked into the printhead at a maximum rate of 20 MHz which will load the entire data for the next line in 40 Ts.

A 4 inch printhead contains 25 600 nozzles. To fire them all at once would consume too much power and be problematic in terms of ink refill and nozzle interference. Consequently two firing modes are defined a low speed printing mode and a high speed printing mode 

When one of the PodgroupEnable lines is set only the specified Podgroup s 4 nozzles will fire as determined by ChromapodSelect and NozzleSelect. When both of the PodgroupEnable lines are set both of the podgroups will fire their nozzles. For the low speed mode two fire pulses are required with PodgroupEnable 10 and 01 respectively. For the high speed mode only one fire pulse is required with PodgroupEnable 11.

The duration of the firing pulse is given by the AEnable and BEnable lines which fire the PhasegroupA and PhasegroupB nozzles from all firegroups respectively. The typical duration of a firing pulse is 1.3 1.8 Ts. The duration of a pulse depends on the viscosity of the ink dependent on temperature and ink characteristics and the amount of power available to the printhead.

The AEnable and BEnable are separate lines in order that the firing pulses can overlap. Thus the 200 phases of a low speed Print Cycle consist of 100 A phases and 100 B phases effectively giving 100 sets of Phase A and Phase B. Likewise the 100 phases of a high speed print cycle consist of 50 A phases and 50 B phases effectively giving 50 phases of phase A and phase B.

For the low speed printing mode the firing order is similar. For each phase of the high speed mode where PodgroupEnable was 11 two phases of PodgroupEnable 01 and 10 are substituted as follows 

When a nozzle fires it takes approximately 100 Ts to refill. The nozzle cannot be fired before this refill time has elapsed. This limits the fastest printing speed to 100 Ts per line. In the high speed print mode the time to print a line is 100 Ts so the time between firing a nozzle from one line to the next matches the refill time. The low speed print mode is slower than this so is also acceptable.

The firing of a nozzle also causes acoustic perturbations for a limited time within the common ink reservoir of that nozzle s pod. The perturbations can interfere with the firing of another nozzle within the same pod. Consequently the firing of nozzles within a pod should be offset from each other as long as possible. We therefore fire four nozzles from a chromapod one nozzle per color and then move onto the next chromapod within the podgroup.

In the low speed printing mode the podgroups are fired separately. Thus the 5 chromapods within both podgroups must all fire before the first chromapod fires again totalling 10 2 T cycles. Consequently each pod is fired once per 20 Ts.

In the high speed printing mode the podgroups are fired together. Thus the 5 chromapods within a single podgroups must all fire before the first chromapod fires again totalling 5 2 T cycles. Consequently each pod is fired once per 10 Ts.

As the ink channel is 300 microns long and the velocity of sound in the ink is around 1500 m s the resonant frequency of the ink channel is 2.5 MHz. Thus the low speed mode allows 50 resonant cycles for the acoustic pulse to dampen and the high speed mode allows 25 resonant cycles. Consequently any acoustic interference is minimal in both cases.

The printhead produces several lines of feedback accumulated from the 8 segments . The feedback lines are used to adjust the timing of the firing pulses. Although each segment produces the same feedback the feedback from all segments share the same tri state bus lines. Consequently only one segment at a time can provide feedback.

A pulse on the SenseSegSelect line ANDed with data on Cyan selects which segment will provide the feedback. The feedback sense lines will come from the selected segment until the next SenseSegSelect pulse. The feedback sense lines are as follows 

The printing process has a strong tendency to stay at the equilibrium temperature. To ensure that the first section of the printed photograph has a consistent dot size the equilibrium temperature must be met before printing any dots. This is accomplished via a preheat cycle.

The Preheat cycle involves a single Load Cycle to all nozzles with 1 s i.e. setting all nozzles to fire and a number of short firing pulses to each nozzle. The duration of the pulse must be insufficient to fire the drops but enough to heat up the ink. Altogether about 200 pulses for each nozzle are required cycling through in the same sequence as a standard Print Cycle.

Feedback during the Preheat mode is provided by Tsense and continues until equilibrium temperature is reached about 30 C. above ambient . The duration of the Preheat mode is around 50 milliseconds and depends on the ink composition.

Preheat is performed before each print job. This does not affect performance as it is done while the data is being transferred to the printer.

In order to reduce the chances of nozzles becoming clogged a cleaning cycle can be undertaken before each print job. Each nozzle is fired a number of times into an absorbent sponge.

The cleaning cycle involves a single Load Cycle to all nozzles with 1 s i.e. setting all nozzles to fire and a number of firing pulses to each nozzle. The nozzles are cleaned via the same nozzle firing sequence as a standard Print Cycle. The number of times that each nozzle is fired depends upon the ink composition and the time that the printer has been idle. As with preheat the cleaning cycle has no effect on printer performance.

An 8 inch MEMJET printhead is simply two 4 inch printheads physically placed together. The printheads are wired together and share many common connections in order that the number of pins from a controlling chip is reduced and that the two printheads can print simultaneously. A number of details must be considered because of this.

Since firing of nozzles from the two printheads occurs simultaneously the ChromapodSelect NozzleSelect AEnable and BEnable lines are shared. For loading the printheads with data the 32 lines of CDataIn MDataIn YDataIn and KDataIn are shared and 2 different SRClock lines are used to determine which of the two printheads is to be loaded. A single PTransfer pulse is used to transfer the loaded data into the NozzleEnable bits for both printheads. Similarly the Tsense Vsense Rsense and Wsense lines are shared with 2 SenseEnable lines to distinguish between the two printheads.

Therefore the two 4 inch printheads share all connections except SRClock and SenseEnable. These two connections are repeated once for each printhead.

The joining of two 4 inch printheads and wiring of appropriate connections enables an 8 inch wide image to be printed as fast as a 4 inch wide image. However there is twice as much data to transfer to the 2 printheads before the next line can be printed. Depending on the desired speed for the output image to be printed data must be generated and transferred at appropriate speeds in order to keep up.

As an example consider the timing of printing an 8 12 page in 2 seconds. In order to print this page in 2 seconds the 8 inch printhead must print 19 200 lines 12 1600 . Rounding up to 20 000 lines in 2 seconds yields a line time of 100 Ts. A single Print Cycle and a single Load Cycle must both finish within this time. In addition a physical process external to the printhead must move the paper an appropriate amount.

From the printing point of view the high speed print mode allows a 4 inch printhead to print an entire line in 100 Ts. Both 4 inch printheads must therefore be run in high speed print mode to print simultaneously. Therefore 512 nozzles fire per firing pulse thereby enabling the printing of an 8 inch line within the specified time.

The 800 SRClock pulses to both 4 inch printheads each clock pulse transferring 32 bits must also take place within the 100 T line time. If both printheads are loaded simultaneously 64 data lines the length of an SRClock pulse cannot exceed 100 Ts 800 125 nanoseconds indicating that the printhead must be clocked at 8 MHz. If the two printheads are loaded one at a time 32 shared data lines the length of an SRClock pulse cannot exceed 100 Ts 1600 62.5 nanoseconds. The printhead must therefore be clocked at 16 MHz. In both instances the average time to calculate each bit value for each of the 51 200 nozzles must not exceed 100 Ts 51 200 2 nanoseconds. This requires a dot generator running at one of the following speeds 

The printer controller consists of the iPrint central processor ICP chip a 64 MBit RDRAM and the master QA chip as shown in .

The ICP contains a general purpose processor and a set of purpose specific functional units controlled by the processor via the processor bus as shown in . Only three functional units are non standard the EDRL expander the halftoner compositor and the printhead interface which controls the MEMJET printhead.

Software running on the processor coordinates the various functional units to receive expand and print pages. This is described in the next section.

Page expansion and printing proceeds as follows. A page description is received from the host via the USB interface and is stored in main memory. 6 MB of main memory is dedicated to page storage. This can hold two pages each not exceeding 3 MB or one page up to 6 MB. If the host generates pages not exceeding 3 MB then the printer operates in streaming mode i.e. it prints one page while receiving the next. If the host generates pages exceeding 3 MB then the printer operates in single page mode i.e. it receives each page and prints it before receiving the next. If the host generates pages exceeding 6 MB then they are rejected by the printer. In practice the printer driver prevents this from happening.

A page consists of two parts the bi level black layer and the contone layer. These are compressed in distinct formats the bi level black layer in EDRL format the contone layer in JPEG format. The first stage of page expansion consists of decompressing the two layers in parallel. The bi level layer is decompressed by the EDRL expander unit the contone layer by the JPEG decoder .

The second stage of page expansion consists of halftoning the contone CMYK data to bi level CMYK and then compositing the bi level black layer over the bi level CMYK layer. The halftoning and compositing is carried out by the halftoner compositor unit .

Finally the composited bi level CMYK image is printed via the printhead interface unit which controls the MEMJET printhead.

Because the MEMJET printhead prints at high speed the paper must move past the printhead at a constant velocity. If the paper is stopped because data can t be fed to the printhead fast enough then visible printing irregularities will occur. It is therefore important to transfer bi level CMYK data to the printhead interface at the required rate.

A fully expanded 1600 dpi bi level CMYK page has a size of 114.3 MB. Because it is impractical to store an expanded page in printer memory each page is expanded in real time during printing. Thus the various stages of page expansion and printing are pipelined. The aggregate traffic to from main memory of 174 MB s is well within the capabilities of current technologies such as Rambus.

Each stage communicates with the next via a shared FIFO in main memory. Each FIFO is organised into lines and the minimum size in lines of each FIFO is designed to accommodate the output window in lines of the producer and the input window in lines of the consumer. The aggregate buffer space usage of 6.3 MB leaves 1.7 MB free for program code and scratch memory out of the 8 MB available .

Contone page decompression is carried out by the JPEG decoder . Bi level page decompression is carried out by the EDRL expander . Halftoning and compositing is carried out by the halftoner compositor unit . These functional units are described in the following sections.

Each functional unit contains one or more on chip input and or output FIFOs. Each FIFO is allocated a separate channel in the multi channel DMA controller . The DMA controller handles single address rather than double address transfers and so provides a separate request acknowledge interface for each channel.

Each functional unit stalls gracefully whenever an input FIFO is exhausted or an output FIFO is filled.

The processor programs each DMA transfer. The DMA controller generates the address for each word of the transfer on request from the functional unit connected to the channel. The functional unit latches the word onto or off the data bus when its request is acknowledged by the DMA controller . The DMA controller interrupts the processor when the transfer is complete thus allowing the processor to program another transfer on the same channel in a timely fashion.

In general the processor will program another transfer on a channel as soon as the corresponding main memory FIFO is available i.e. non empty for a read non full for a write .

The granularity of channel servicing implemented in the DMA controller depends somewhat on the latency of main memory.

The EDRL expander unit EEU shown in decompresses an EDRL compressed bi level image. The input to the EEU is an EDRL bitstream . The output from the EEU is a set of bi level image lines scaled horizontally from the resolution of the expanded bi level image by an integer scale factor to 1600 dpi.

Once started the EEU proceeds until it detects an end of page code in the EDRL bitstream or until it is explicitly stopped via its control register. The EEU relies on an explicit page width to decode the bitstream. This must be written to the page width register prior to starting the EEU. The scaling of the expanded bi level image relies on an explicit scale factor. This must be written to the scale factor register prior to starting the EEU.

It represents a bi level image in terms of its edges. Each edge in each line is coded relative to an edge in the previous line or relative to the previous edge in the same line. No matter how it is coded each edge is ultimately decoded to its distance from the previous edge in the same line. This distance or runlength is then decoded to the string of one bits or zero bits which represent the corresponding part of the image.

The EEU consists of a bitstream decoder a state machine edge calculation logic two runlength decoders and and a runlength re encoder .

The bitstream decoder decodes an entropy coded codeword from the bitstream and passes it to the state machine . The state machine returns the size of the codeword to the bitstream decoder which allows the decoder to advance to the next codeword. In the case of a create edge code the state machine uses the bitstream decoder to extract the corresponding runlength from the bitstream.

The edge calculation logic is quite simple. The current edge offset in the previous reference and current coding lines are maintained in the reference edge register and edge register respectively. The runlength associated with a create edge code is output directly to the runlength decoders and is added to the current edge. A delta code is translated into a runlength by adding the associated delta to the reference edge and subtracting the current edge. The generated runlength is output to the runlength decoders and is added to the current edge. The next runlength is extracted from the runlength encoder and added to the reference edge . A kill edge code simply causes the current reference edge to be skipped. Again the next runlength is extracted from the runlength encoder and added to the reference edge.

Each time the edge calculation logic generates a runlength representing an edge it is passed to the runlength decoders. While the runlength decoder decodes the run it generates a stall signal to the state machine. Since the runlength decoder is slower than the edge calculation logic there s not much point in decoupling it. The expanded line accumulates in a line buffer large enough to hold an 8 800 dpi line 800 bytes .

The previously expanded line is also buffered . It acts as a reference for the decoding of the current line. The previous line is re encoded as runlengths on demand. This is less expensive than buffering the decoded runlengths of the previous line since the worst case is one 13 bit runlength for each pixel 20 KB at 1600 dpi . While the runlength encoder encodes the run it generates a stall signal to the state machine. The runlength encoder uses the page width to detect end of line. The current line buffer and the previous line buffer are concatenated and managed as a single FIFO to simplify the runlength encoder .

Runlength decoder decodes the output runlength to a line buffer large enough to hold an 8 1600 dpi line 1600 bytes . The runlength passed to this output runlength decoder is multiplied by the scale factor so this decoder produces 1600 dpi lines. The line is output scale factor times through the output pixel FIFO . This achieves the required vertical scaling by simple line replication. The EEU could be designed with edge smoothing integrated into its image scaling. A simple smoothing scheme based on template matching can be very effective. This would require a multi line buffer between the low resolution runlength decoder and the smooth scaling unit but would eliminate the high resolution runlength decoder.

The EDRL stream decoder illustrated in decodes entropy coded EDRL codewords in the input bitstream. It uses a two byte input buffer viewed through a 16 bit barrel shifter whose left most significant edge is always aligned to a codeword boundary in the bitstream. The decoder connected to the barrel shifter decodes a codeword according to Table 17 and supplies the state machine with the corresponding code.

The state machine in turn outputs the length of the code. This is added modulo 8 to the current codeword bit offset to yield the next codeword bit offset. The bit offset in turn controls the barrel shifter . If the codeword bit offset wraps then the carry bit controls the latching of the next byte from the input FIFO . At this time byte is latched to byte and the FIFO output is latched to byte . It takes two cycles of length to fill the input buffer. This is handled by starting states in the state machine .

The EDRL expander state machine controls the edge calculation and runlength expansion logic in response to codes supplied by the EDRL stream decoder . It supplies the EDRL stream decoder with the length of the current codeword and supplies the edge calculation logic with the delta value associated with the current delta code. The state machine also responds to start and stop control signals from the control register and the end of line EOL signal from the edge calculation logic.

The state machine also controls the multi cycle fetch of the runlength associated with a create edge code.

The runlength decoder shown in expands a runlength into a sequence of zero bits or one bits of the corresponding length in the output stream. The first run in a line is assumed to be white color . Each run is assumed to be of the opposite color to its predecessor. If the first run is actually black color then it must be preceded by a zero length white run. The runlength decoder keeps track of the current color internally.

The runlength decoder appends a maximum of 8 bits to the output stream every clock. Runlengths are typically not an integer multiple of 8 and so runs other than the first in an image are typically not byte aligned. The run decoder maintains in the byte space register the number of bits available in the byte currently being built. This is initialised to 8 at the beginning of decoding and on the output of every byte.

The decoder starts outputting a run of bits as soon as the next run line latches a non zero value into the runlength register . The decoder effectively stalls when the runlength register goes to zero.

A number of bits of the current color are shifted into the output byte register each clock. The current color is maintained in the 1 bit color register . The number of bits actually output is limited by the number of bits left in the runlength and by the number of spare bits left in the output byte. The number of bits output is subtracted from the runlength and the byte space. When the runlength goes to zero it has been completely decoded although the trailing bits of the run may still be in the output byte register pending output. When the byte space goes to zero the output byte is full and is appended to the output stream.

The 16 bit barrel shifter the output byte register and the color register together implement an 8 bit shift register which can be shifted multiple bit positions every clock with the color as the serial input.

The external reset line is used to reset the runlength decoder at the start of a line. The external next run line is used to request the decoding of a new runlength. It is accompanied by a runlength on the external runlength lines. The next run line should not be set on the same clock as the reset line. Because next run inverts the current color the reset of the color sets it to one not zero. The external flush line is used to flush the last byte of the run if incomplete. It can be used on a line by line basis to yield byte aligned lines or on an image basis to yield a byte aligned image.

The external ready line indicates whether the runlength decoder is ready to decode a runlength. It can be used to stall the external logic.

The runlength encoder shown in detects a run of zero or one bits in the input stream. The first run in a line is assumed to be white color . Each run is assumed to be of the opposite color to its predecessor. If the first run is actually black color then the runlength encoder generates a zero length white run at the start of the line. The runlength decoder keeps track of the current color internally.

The runlength encoder reads a maximum of 8 bits from the input stream every clock. It uses a two byte input buffer viewed through a 16 bit barrel shifter whose left most significant edge is always aligned to the current position in the bitstream. The encoder connected to the barrel shifter encodes an 8 bit partial runlength. The encoder uses the current color to recognise runs of the appropriate color.

The 8 bit runlength generated by the 8 bit runlength encoder is added to the value in the runlength register . When the 8 bit runlength encoder recognises the end of the current run it generates an end of run signal which is latched by the ready register . The output of the ready register indicates that the encoder has completed encoding the current runlength accumulated in the runlength register . The output of the ready register is also used to stall the 8 bit runlength encoder . When stalled the 8 bit runlength encoder outputs a zero length run and a zero end of run signal effectively stalling the entire runlength encoder.

The output of the 8 bit runlength encoder is limited by the remaining page width. The actual 8 bit runlength is subtracted from the remaining page width and is added to the modulo 8 bit position used to control the barrel shifter and clock the byte stream input.

The external reset line is used to reset the runlength encoder at the start of a line. It resets the current color and latches the page width into the page width register. The external next run line is used to request another runlength from the runlength encoder. It inverts the current color and resets the runlength register and ready register. The external flush line is used to flush the last byte of the run if incomplete. It can be used on a line by line basis to process byte aligned lines or on an image basis to process a byte aligned image.

The external ready line indicates that the runlength encoder is ready to encode a runlength and that the current runlength is available on the runlength lines. It can be used to stall the external logic.

The JPEG decoder shown in decompresses a JPEG compressed CMYK contone image. The input to the JPEG decoder is a JPEG bitstream. The output from the JPEG decoder is a set of contone CMYK image lines.

When decompressing the JPEG decoder writes its output in the form of 8 8 pixel blocks. These are sometimes converted to full width lines via an page width 8 strip buffer closely coupled with the codec. This would require a 67 KB buffer. We instead use 8 parallel pixel FIFOs with shared bus access and 8 corresponding DMA channels as shown in .

The halftoner compositor unit HCU shown in combines the functions of halftoning the contone CMYK layer to bi level CMYK and compositing the black layer over the halftoned contone layer.

The input to the HCU is an expanded 267 ppi CMYK contone layer and an expanded 1600 dpi black layer . The output from the HCU is a set of 1600 dpi bi level CMYK image lines .

Once started the HCU proceeds until it detects an end of page condition or until it is explicitly stopped via its control register.

The HCU generates a page of dots of a specified width and length. The width and length must be written to the page width and page length registers prior to starting the HCU. The page width corresponds to the width of the printhead . The page length corresponds to the length of the target page.

The HCU generates target page data between specified left and right margins relative to the page width. The positions of the left and right margins must be written to the left margin and right margin registers prior to starting the HCU. The distance from the left margin to the right margin corresponds to the target page width.

The HCU consumes black and contone data according to specified black and contone page widths. These page widths must be written to the black page width and contone page width registers prior to starting the HCU. The HCU clips black and contone data to the target page width . This allows the black and contone page widths to exceed the target page width without requiring any special end of line logic at the input FIFO level.

The relationships between the page width the black and contone page widths and the margins are illustrated in .

The HCU scales contone data to printer resolution both horizontally and vertically based on a specified scale factor. This scale factor must be written to the contone scale factor register prior to starting the HCU.

The consumer of the data produced by the HCU is the printhead interface. The printhead interface requires bi level CMYK image data in planar format i.e. with the color planes separated. Further it also requires that even and odd pixels are separated. The output stage of the HCU therefore uses 8 parallel pixel FIFOs one each for even cyan odd cyan even magenta odd magenta even yellow odd yellow even black and odd black.

The input contone CMYK FIFO is a full 8 KB line buffer. The line is used contone scale factor times to effect vertical up scaling via line replication. FIFO write address wrapping is disabled until the start of the last use of the line. An alternative is to read the line from main memory contone scale factor times increasing memory traffic by 65 MB s but avoiding the need for the on chip 8 KB line buffer.

A general 256 layer dither volume provides great flexibility in dither cell design by decoupling different intensity levels. General dither volumes can be large a 64 64 256 dither volume for example has a size of 128 KB. They are also inefficient to access since each color component requires the retrieval of a different bit from the volume. In practice there is no need to fully decouple each layer of the dither volume. Each dot column of the volume can be implemented as a fixed set of thresholds rather than 256 separate bits. Using three 8 bit thresholds for example only consumes 24 bits. Now n thresholds define n 1 intensity intervals within which the corresponding dither cell location is alternately not set or set. The contone pixel value being dithered uniquely selects one of the n 1 intervals and this determines the value of the corresponding output dot.

We dither the contone data using a triple threshold 64 64 3 8 bit 12 KB dither volume. The three thresholds form a convenient 24 bit value which can be retrieved from the dither cell ROM in one cycle. If dither cell registration is desired between color planes then the same triple threshold value can be retrieved once and used to dither each color component. If dither cell registration is not desired then the dither cell can be split into four sub cells and stored in four separately addressable ROMs from which four different triple threshold values can be retrieved in parallel in one cycle. Using the addressing scheme shown in the four color planes share the same dither cell at vertical and or horizontal offsets of 32 dots from each other.

The Multi threshold dither is shown in . The triple threshold unit converts a triple threshold value and an intensity value into an interval and thence a one or zero bit. The corresponding logic is shown in .

Referring to in more detail four separate triple threshold units indicated generally at each receive a series of contone color pixel values for respective color components of the CMYK signal. The dither volume is split into four dither subcells A B C and D indicated generally at . A dither cell address generator and four gates indicated generally at control the retrieval of the four different triple threshold values which can be retrieved in parallel in one cycle for the different colors.

The composite unit composites a black layer dot over a halftoned CMYK layer dot. If the black layer opacity is one then the halftoned CMY is set to zero. Given a 4 bit halftoned color CMYKand a 1 bit black layer opacity K the composite and clip logic is as defined in Table 22.

The clock enable generator generates enable signals for clocking the contone CMYK pixel input the black dot input and the CMYK dot output.

As described earlier the contone pixel input buffer is used as both a line buffer and a FIFO. Each line is read once and then used contone scale factor times. FIFO write address wrapping is disabled until the start of the final replicated use of the line at which time the clock enable generator generates a contone line advance enable signal which enables wrapping.

The clock enable generator also generates an even signal which is used to select the even or odd set of output dot FIFOs and a margin signal which is used to generate white dots when the current dot position is in the left or right margin of the page. The clock enable generator uses a set of counters.

The printhead interface PHI is the means by which the processor loads the MEMJET printhead with the dots to be printed and controls the actual dot printing process. The PHI contains 

The units within the PHI are controlled by a number of registers that are programmed by the processor . In addition the processor is responsible for setting up the appropriate parameters in the DMA controller for the transfers from memory to the LLFU. This includes loading white all 0 s into appropriate colors during the start and end of a page so that the page has clean edges.

The line loader format unit LLFU loads the dots for a given print line into local buffer storage and formats them into the order required for the MEMJET printhead. It is responsible for supplying the pre calculated nozzleEnable bits to the MEMJET interface for the eventual printing of the page.

A single line in the 8 inch printhead consists of 12 800 4 color dots. At 1 bit per color a single print line consists of 51 200 bits. These bits must be supplied in the correct order for being sent on to the printhead. 32 bits are transferred at a time to each of the two 4 inch printheads with the 32 bits representing 4 dots for each of the 8 segments.

The printing uses a double buffering scheme for preparing and accessing the dot bit information. While one line is being loaded into the first buffer the pre loaded line in the second buffer is being read in MEMJET dot order. Once the entire line has been transferred from the second buffer to the printhead via the MEMJET interface the reading and writing processes swap buffers. The first buffer is now read and the second buffer is loaded up with the new line of data. This is repeated throughout the printing process as can be seen in the conceptual overview of

The actual implementation of the LLFU is shown in . Since one buffer is being read from while the other is being written to two sets of address lines must be used. The 32 bits DataIn from the common data bus are loaded depending on the WriteEnables which are generated by the State Machine in response to the DMA Acknowledges.

A multiplexor chooses between the two 4 bit outputs of Buffer and Buffer and sends the result to an 8 entry by 4 bit shift register . After the first 8 read cycles and whenever an Advance pulse comes from the MJI the current 32 bit value from the shift register is gated into the 32 bit Transfer register where it can be used by the MJI.

Each of the two buffers and is broken into 4 sub buffers and 1 per color. All the even dots are placed before the odd dots in each color s buffer as shown in .

The 51 200 bits representing the dots in the next line to be printed are stored 12 800 bits per color buffer stored as 400 32 bit words. The first 200 32 bit words 6400 bits represent the even dots for the color while the second 200 32 bit words 6400 bits represent the odd dots for the color.

The addressing decoding circuitry is such that in a given cycle a single 32 bit access can be made to all 4 sub buffers either a read from all 4 or a write to one of the 4. Only one bit of the 32 bits read from each color buffer is selected for a total of 4 output bits. The process is shown in . 13 bits of address allow the reading of a particular bit by means of 8 bits of address being used to select 32 bits and 5 bits of address choose 1 bit from those 32. Since all color buffers share this logic a single 13 bit address gives a total of 4 bits out one per color. Each buffer has its own WriteEnable line to allow a single 32 bit value to be written to a particular color buffer in a given cycle. The 32 bits of DataIn are shared since only one buffer will actually clock the data in.

Address Generation for reading is straightforward. Each cycle we generate a bit address which is used to fetch 4 bits representing 1 bit per color for the particular segment. By adding 400 to the current bit address we advance to the next segment s equivalent dot. We add 400 not 800 since the odd and even dots are separated in the buffer. We do this 16 times to retrieve the two sets of 32 bits for the two sets of 8 segments representing the even dots the resultant data is transferred to the MJI 32 bits at a time and another 16 times to load the odd dots. This 32 cycle process is repeated 400 times incrementing the start address each time. Thus in 400 32 cycles a total of 400 32 4 51 200 dot values are transferred in the order required by the printhead.

In addition we generate the TransferWriteEnable control signal. Since the LLFU starts before the MJI we must transfer the first value before the Advance pulse from the MJI. We must also generate the next 32 bit value in readiness for the first Advance pulse. The solution is to transfer the first 32 bit value to the Transfer register after 8 cycles and then to stall 8 cycles later waiting for the Advance pulse to start the next 8 cycle group. Once the first Advance pulse arrives the LLFU is synchronized to the MJI. However the MJI must be started at least 16 cycles after the LLFU so that the initial Transfer value is valid and the next 32 bit value is ready to be loaded into the Transfer register.

The write process is also straightforward. 4 DMA request lines are output to the DMA controller. As requests are satisfied by the return DMA Acknowledge lines the appropriate 8 bit destination address is selected the lower 5 bits of the 13 bit output address are don t care values and the acknowledge signal is passed to the correct buffer s WriteEnable control line the Current Write Buffer is CurrentReadBuffer . The 8 bit destination address is selected from the 4 current addresses one address per color. As DMA requests are satisfied the appropriate destination address is incremented and the corresponding TransfersRemaining counter is decremented. The DMA request line is only set when the number of transfers remaining for that color is non zero.

The MEMJET interface MJI transfers data to the MEMJET printhead and controls the nozzle firing sequences during a print.

The MJI is simply a State Machine see which follows the Printhead loading and firing order described previously and includes the functionality of the Preheat Cycle and Cleaning Cycle as also described previously. Both high speed and low speed printing modes are available. Dot counts for each color are also kept by the MJI.

All 1s. This means that all nozzles will fire during a subsequent Print cycle and is the standard mechanism for loading the printhead for a preheat or cleaning cycle.

From the 32 bit input held in the Transfer register of the LLFU. This is the standard means of printing an image. The 32 bit value from the LLFU is directly sent to the printhead and a 1 bit Advance control pulse is sent to the LLFU. At the end of each line a 1 bit AdvanceLine pulse is also available. The MJI must be started after the LLFU has already prepared the first 32 bit transfer value. This is so the 32 bit data input will be valid for the first transfer to the printhead. The MJI is therefore directly connected to the LLFU and the external MEMJET printhead.

The duration of firing pulses on the AEnable and BEnable lines depend on the viscosity of the ink which is dependant on temperature and ink characteristics and the amount of power available to the printhead. The typical pulse duration range is 1.3 to 1.8 Ts. The MJI therefore contains a programmable pulse duration table indexed by feedback from the printhead. The table of pulse durations allows the use of a lower cost power supply and aids in maintaining more accurate drop ejection.

The Pulse Duration table has 256 entries and is indexed by the current Vsense and Tsense settings. The upper 4 bits of address come from Vsense and the lower 4 bits of address come from Tsense. Each entry is 8 bits and represents a fixed point value in the range of 0 4 Ts. The process of generating the AEnable and BEnable lines is shown in . The analog Vsense and Tsense signals are received by respective sample and hold circuits and and then converted to digital words in respective converters and before being applied to the pulse duration table . The output of the pulse duration table is applied to a pulse width generator to generate the firing pulses.

The 256 byte table is written by the CPU before printing the first page. The table may be updated in between pages if desired. Each 8 bit pulse duration entry in the table combines 

The MJI maintains a count of the number of dots of each color fired from the printhead in a dot count register . The dot count for each color is a 32 bit value individually cleared by a signal under processor control. At 32 bits length each dot count can hold a maximum coverage dot count of 17 12 inch pages although in typical usage the dot count will be read and cleared after each page.

The dot counts are used by the processor to update the QA chip in order to predict when the ink cartridge runs out of ink. The processor knows the volume of ink in the cartridge for each of C M Y and K from the QA chip. Counting the number of drops eliminates the need for ink sensors and prevents the ink channels from running dry. An updated drop count is written to the QA chip after each page. A new page will not be printed unless there is enough ink left and allows the user to change the ink without getting a dud half printed page which must be reprinted.

The layout of the dot counter for cyan is shown in . The remaining 3 dot counters MDotCount YDotCount and KDotCount for magenta yellow and black respectively are identical in structure.

The processor communicates with the MJI via a register set. The registers allow the processor to parameterize a print as well as receive feedback about print progress.

The processor runs the control program which synchronises the other functional units during page reception expansion and printing. It also runs the device drivers for the various external interfaces and responds to user actions through the user interface.

It must have low interrupt latency to provide efficient DMA management but otherwise does not need to be particularly high performance DMA Controller.

The DMA controller supports single address transfers on 27 channels. It generates vectored interrupts to the processor on transfer completion.

The Rambus interface provides the high speed interface to the external 8 MB 64 Mbit Rambus DRAM RDRAM .

The speaker interface contains a small FIFO used for DMA mediated transfers of sound clips from main memory an 8 bit digital to analog converter DAC which converts each 8 bit sample value to a voltage and an amplifier which feeds the external speaker. When the FIFO is empty it outputs a zero value. The speaker interface is clocked at the frequency of the sound clips. The processor outputs a sound clip to the speaker simply by programming the DMA channel of the speaker interface.

The serial interface provides two standard low speed serial ports. One port is used to connect to the master QA chip . The other is used to connect to the QA chip in the ink cartridge . The processor mediated protocol between the two is used to authenticate the ink cartridge. The processor can then retrieve ink characteristics from the QA chip as well as the remaining volume of each ink. The processor uses the ink characteristics to properly configure the MEMJET printhead. It uses the remaining ink volumes updated on a page by page basis with ink consumption information accumulated by the printhead interface to ensure that it never allows the printhead to be damaged by running dry.

The QA chip in the ink cartridge contains information required for maintaining the best possible print quality and is implemented using an authentication chip. The 256 bits of data in the authentication chip are allocated as follows 

Before each page is printed the processor must check the amount of ink remaining to ensure there is enough for an entire worst case page. Once the page has been printed the processor multiplies the total number of drops of each color obtained from the printhead interface by the drop volume. The amount of printed ink is subtracted from the amount of ink remaining. The unit of measurement for ink remaining is nanolitres so 32 bits can represent over 4 litres of ink. The amount of ink used for a page must be rounded up to the nearest nanolitre i.e. approximately 1000 printed dots .

A standard JTAG Joint Test Action Group interface is included for testing purposes. Due to the complexity of the chip a variety of testing techniques are required including BIST Built In Self Test and functional block isolation. An overhead of 10 in chip area is assumed for overall chip testing circuitry.

We assume that the printer driver is closely coupled with the host graphics system so that the printer driver can provide device specific handling for different graphics and imaging operations in particular compositing operations and text operations.

We assume that the host provides support for color management so that device independent color can be converted to iPrint specific CMYK color in a standard way based on a user selected iPrint specific ICC International Color Consortium color profile. The color profile is normally selected implicitly by the user when the user specifies the output medium in the printer i.e. plain paper coated paper transparency etc. . The page description sent to the printer always contains device specific CMYK color.

We assume that the host graphics system renders images and graphics to a nominal resolution specified by the printer driver but that it allows the printer driver to take control of rendering text. In particular the graphics system provides sufficient information to the printer driver to allow it to render and position text at a higher resolution than the nominal device resolution.

We assume that the host graphics system requires random access to a contone page buffer at the nominal device resolution into which it composites graphics and imaging objects but that it allows the printer driver to take control of the actual compositing i.e. it expects the printer driver to manage the page buffer.

The printer s page description contains a 267 ppi contone layer and an 800 dpi black layer. The black layer is conceptually above the contone layer i.e. the black layer is composited over the contone layer by the printer. The printer driver therefore maintains a page buffer which correspondingly contains a medium resolution contone layer and a high resolution black layer .

The graphics systems renders and composites objects into the page buffer bottom up i.e. later objects obscure earlier objects. This works naturally when there is only a single layer but not when there are two layers which will be composited later. It is therefore necessary to detect when an object being placed on the contone layer obscures something on the black layer.

When obscuration is detected the obscured black pixels are composited with the contone layer and removed from the black layer. The obscuring object is then laid down on the contone layer possibly interacting with the black pixels in some way. If the compositing mode of the obscuring object is such that no interaction with the background is possible then the black pixels can simply be discarded without being composited with the contone layer. In practice of course there is little interaction between the contone layer and the black layer.

The printer driver specifies a nominal page resolution of 267 ppi to the graphics system. Where possible the printer driver relies on the graphics system to render image and graphics objects to the pixel level at 267 ppi with the exception of black text. The printer driver fields all text rendering requests detects and renders black text at 800 dpi but returns non black text rendering requests to the graphics system for rendering at 267 ppi.

Ideally the graphics system and the printer driver manipulate color in device independent RGB deferring conversion to device specific CMYK until the page is complete and ready to be sent to the printer. This reduces page buffer requirements and makes compositing more rational. Compositing in CMYK color space is not ideal.

Ultimately the graphics system asks the printer driver to composite each rendered object into the printer driver s page buffer. Each such object uses 24 bit contone RGB and has an explicit or implicitly opaque opacity channel.

The printer driver maintains the two layer page buffer in three parts. The first part is the medium resolution 267 ppi contone layer . This consists of a 24 bit RGB bitmap. The second part is a medium resolution black layer . This consists of an 8 bit opacity bitmap. The third part is a high resolution 800 dpi black layer . This consists of a 1 bit opacity bitmap. The medium resolution black layer is a subsampled version of the high resolution opacity layer. In practice assuming the medium resolution is an integer factor n of the high resolution e.g. n 800 267 3 each medium resolution opacity value is obtained by averaging the corresponding n n high resolution opacity values. This corresponds to box filtered subsampling. The subsampling of the black pixels effectively antialiases edges in the high resolution black layer thereby reducing ringing artefacts when the contone layer is subsequently JPEG compressed and decompressed.

When a black object of opacity is composited with the black layer the black layer is updated as follows 

The object opacity is simply ored with the black layer opacity Rule 1 and the corresponding part of the medium resolution black layer is re computed from the high resolution black layer Rule 2 .

When a contone object of color Cand opacity is composited with the contone layer the contone layer and the black layer are updated as follows 1 if x y 0 Rule 3 x y 0 if x y 0 Rule 4 x y 0 if x n y n 0 Rule 5 1 Rule 6 

Wherever the contone object obscures the black layer even if not fully opaquely the affected black layer pixels are pushed from the black layer to the contone layer i.e. composited with the contone layer Rule 3 and removed from the black layer Rule 4 and Rule 5 . The contone object is then composited with the contone layer Rule 6 .

If a contone object pixel is fully opaque i.e. x y 255 then there is no need to push the corresponding black pixels into the background contone layer Rule 3 since the background contone pixel will subsequently be completely obliterated by the foreground contone pixel Rule 6 .

The output image represented to the two layers is shown without a pixel grid since the actual rendering of the image is not the focus of discussion here.

The medium resolution foreground black layer is not illustrated but is implicitly present. Whenever Rule 1 is applied to the high resolution foreground black layer Rule 2 is implicitly applied to the medium resolution foreground black layer. Whenever Rule 4 is applied Rule 5 is also implicitly applied.

The final image shows darkening of those contone pixels which transparently obscure parts of the existing black object.

Once page rendering is complete the printer driver converts the contone layer to iPrint specific CMYK with the help of color management functions in the graphics system. The printer driver then compresses and packages the black layer and the contone layer into an iPrint page description. This page description is delivered to the printer via the standard spooler. Note that the black layer is manipulated as a set of 1 bit opacity values but is delivered to the printer as a set of 1 bit black values. Although these two interpretations are different they share the same representation and so no data conversion is required.

In the Windows 9x NT printing system a printer is a graphics device and an application communicates with it via the graphics device interface GDI . The printer driver graphics DLL dynamic link library implements the device dependent aspects of the various graphics functions provided by GDI.

The spooler handles the delivery of pages to the printer and may reside on a different machine to the application requesting printing. It delivers pages to the printer via a port monitor which handles the physical connection to the printer. The optional language monitor is the part of the printer driver which imposes additional protocol on communication with the printer and in particular decodes status responses from the printer on behalf of the spooler.

The printer driver user interface DLL implements the user interface for editing printer specific properties and reporting printer specific events. The structure of the Windows 9x NT printing system is illustrated in . Since iPrint uses USB IEEE 1284 emulation there is no need to implement a language monitor for iPrint. The remainder of this section describes the design of the printer driver graphics DLL. It should be read in conjunction with the appropriate Windows 9x NT DDK documentation.

GDI provides functions which allow an application to draw on a device surface i.e. typically an abstraction of a display screen or a printed page. For a raster device the device surface is conceptually a color bitmap. The application can draw on the surface in a device independent way i.e. independently of the resolution and color characteristics of the device.

The application has random access to the entire device surface. This means that if a memory limited printer device requires banded output then GDI must buffer the entire page s GDI commands and replay them windowed into each band in turn. Although this provides the application with great flexibility it can adversely affect performance.

GDI supports color management whereby device independent colors provided by the application are transparently translated into device dependent colors according to a standard ICC International Color Consortium color profile of the device. A printer driver can activate a different color profile depending for example on the user s selection of paper type on the driver managed printer property sheet.

GDI supports line and spline outline graphics paths images and text. Outline graphics including outline font glyphs can be stroked and filled with bit mapped brush patterns. Graphics and images can be geometrically transformed and composited with the contents of the device surface. While Windows 95 NT4 provides only boolean compositing operators Windows 98 NT5 provides proper alpha blending.

A raster printer can in theory utilize standard printer driver components under Windows 9x NT and this can make the job of developing a printer driver trivial. This relies on being able to model the device surface as a single bitmap. The problem with this is that text and images must be rendered at the same resolution. This either compromises text resolution or generates too much output data compromising performance.

As described earlier iPrint s approach is to render black text and images at different resolutions to optimize the reproduction of each. The printer driver is therefore implemented according to the generic design.

The driver therefore maintains a two layer three part page buffer and this means that the printer driver must take over managing the device surface which in turn means that it must mediate all GDI access to the device surface.

DrvEnablePDEV indicates to GDI via the flGraphicsCaps member of the returned DEVINFO structure the graphics rendering capabilities of the driver. This is discussed further below. DrvEnableSurface creates a device surface consisting of two conceptual layers and three parts the 267 ppi contone layer 24 bit RGB color the 267 ppi black layer 8 bit opacity and the 800 dpi black layer 1 bit opacity. The virtual device surface which encapsulates these two layers has a nominal resolution of 267 ppi so this is the resolution at which GDI operations take place.

Although the aggregate page buffer requires about 33 MB of memory the PC 99 office standard specifies a minimum of 64 MB. In practice managing the device surface and mediating GDI access to it means that the printer driver must support the following additional functions 

Copying images stroking paths and filling regions all occur on the contone layer while rendering solid black text occurs on the bi level black layer. Furthermore rendering non black text also occurs on the contone layer since it isn t supported on the black layer. Conversely stroking or filling with solid black can occur on the black layer if we so choose .

Although the printer driver is obliged to hook the aforementioned functions it can punt function calls which apply to the contone layer back to the corresponding GDI implementations of the functions since the contone layer is a standard format bitmap. For every DrvXxx function there is a corresponding EngXxx function provided by GDI.

When an object destined for the contone layer obscures pixels on the black layer the obscured black pixels must be transferred from the black layer to the contone layer before the contone object is composited with the contone layer. The key to this process working is that obscuration is detected and handled in the hooked call before it is punted back to GDI. This involves determining the pixel by pixel opacity of the contone object from its geometry and using this opacity to selectively transfer black pixels from the black layer to the contone layer.

It is possible to determine the geometry of each contone object before it is rendered and thus determine efficiently which black pixels it obscures. In the case of DrvCopyBits and DrvPaint the geometry is determined by a clip object CLIPOBJ which can be enumerated as a set of rectangles.

In the case of DrvStrokePath things are more complicated. DrvStrokePath supports both straight line and B zier spline curve segments and single pixel wide lines and geometric wide lines. The first step is to avoid the complexity of B zier spline curve segments and geometric wide lines altogether by clearing the corresponding capability flags GCAPS BEZIERS and GCAPS GEOMETRICWIDE in the flGraphicsCaps member of the driver s DEVINFO structure. This causes GDI to reformulate such calls as sets of simpler calls to DrvPaint. In general GDI gives a driver the opportunity to accelerate high level capabilities but simulates any capabilities not provided by the driver.

What remains is simply to determine the geometry of a single pixel wide straight line. Such a line can be solid or cosmetic. In the latter case the line style is determined by a styling array in the specified line attributes LINEATTRS . The styling array specifies how the line alternates between being opaque and transparent along its length and so supports various dashed line effects etc.

When the brush is solid black straight lines can also usefully be rendered to the black layer though with the increased width implied by the 800 dpi resolution.

In the case of a DrvTextOut things are also more complicated. Firstly the opaque background if any is handled like any other fill on the contone layer see DrvPaint . If the foreground brush is not black or the mix mode is not effectively opaque or the font is not scalable or the font indicates outline stroking then the call is punted to EngTextOut to be applied to the contone layer. Before the call is punted however the driver determines the geometry of each glyph by obtaining its bitmap via FONTOBJ cGetGlyphs and makes the usual obscuration check against the black layer.

If punting a DrvTextOut call is not allowed the documentation is ambiguous then the driver should disallow complex text operations. This includes disallowing outline stroking by clearing the GCAPS VECTOR FONT capability flag and disallowing complex mix modes by clearing the GCAPS ARBMIXTXT capability flag .

If the foreground brush is black and opaque and the font is scalable and not stroked then the glyphs are rendered on the black layer. In this case the driver determines the geometry of each glyph by obtaining its outline again via FONTOBJ cGetGlyphs but as a PATHOBJ . The driver then renders each glyph from its outline at 800 dpi and writes it to the black layer. Although the outline geometry uses device coordinates i.e. at 267 ppi the coordinates are in fixed point format with plenty of fractional precision for higher resolution rendering.

The driver must set the GCAPS HIGHRESTEXT flag in the DEVINFO to request that glyph positions again in 267 ppi device coordinates be supplied by GDI in high precision fixed point format to allow accurate positioning at 800 dpi. The driver must also provide an implementation of the DrvGetGlyphMode function so that it can indicate to GDI that glyphs should be cached as outlines rather than bitmaps. Ideally the driver should cache rendered glyph bitmaps for efficiency memory allowing. Only glyphs below a certain point size should be cached.

As described earlier the contone layer is compressed using JPEG. The forward discrete cosine transform DCT is the costliest part of JPEG compression. In current high quality software implementations the forward DCT of each 8 8 block requires 12 integer multiplications and 32 integer additions. On a Pentium processor an integer multiplication requires 10 cycles and an integer addition requires 2 cycles. This equates to a total cost per block of 184 cycles.

The 25.5 MB contone layer consists of 417 588 JPEG blocks giving an overall forward DCT cost of about 77 Mcycles. At 300 MHz the PC 99 desktop standard this equates to 0.26 seconds which is well within the 2 second limit per page.

