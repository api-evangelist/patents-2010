---

title: Automated image analysis with GUI management and control of a pipeline workflow
abstract: Automated image screening operations of pipelined image processing systems and methods are controlled with a graphical user interface enabling user control of screening analysis process setup and execution and user viewing of results. A gating interface is provided to include and/or exclude cells in an aggregation of individual cell data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08861810&OS=08861810&RS=08861810
owner: Vala Sciences, Inc.
number: 08861810
owner_city: San Diego
owner_country: US
publication_date: 20100105
---
This application claims priority to U.S. Provisional Application for Patent 61 204 506 filed Jan. 6 2009 and to U.S. Provisional Application for Patent 61 212 992 filed Apr. 17 2009 both commonly owned herewith.

The following applications contain subject matter related to this application. Both applications are incorporated herein by this reference 

U.S. patent application Ser. No. 11 285 691 filed Nov. 21 2005 for System Method And Kit For Processing A Magnified Image Of Biological Material To Identify Components Of A Biological Object and 

PCT application PCT US2006 044936 filed Nov. 17 2006 for System Method And Kit For Processing A Magnified Image Of Biological Material To Identify Components Of A Biological Object published as WO 2007 061971 on May 31 2007 

U.S. patent application Ser. No. 12 454 081 filed May 12 2009 for User Interface Method And System For Management And Control of Automated Image Processing In High Content Screening Or High Throughput Screening and 

U.S. patent application Ser. No. 12 459 146 filed Jun. 26 2009 for User Interface Method And System With Image Viewer For Management And Control Of Automated Image Processing In High Content Screening Or High Throughput Screening .

Inventions described herein were made in part with government support under Grant No. 1R03 DA026213 01 Grant No. 5R42 HL086076 03 Grant No. 1R41 DK082087 01 and Grant No. 1R41 AR055604 01A2 all awarded by the National Institutes of Health. The US government has certain rights in this invention.

The technical field concerns image processing. More particularly the technical field covers automated analysis of magnified images. More particularly still the technical field concerns an instrumentation system in which magnified images of material are subjected to image processing in an image processing system with a graphical user interface that enables a user to selectively select and initialize an image analysis algorithm and to screen results.

Magnified images of biological material are obtained for purposes of study diagnosis or determination of experimental results. Such images may be obtained by instrument systems from material disposed in multi well plates plastic or glass culture dishes cells disposed on plastic or glass slides and or tissue sections mounted to plastic or glass slides. The magnified images are subjected to analysis by means of an automated image processing system constructed to execute image processing algorithms in order to determine characteristics of the material important to the intended purposes.

An automated image processing system incorporating inventions described in U.S. patent application Ser. No. 12 454 081 and U.S. patent application Ser. No. 12 459 146 has contributed a number of key advances to image cytometry high content screening and high content analysis software packages. The system is designed for ease of use accessibility and scalability and includes a graphical user interface GUI for analysis and data viewing that is much more accessible for the non expert user than previous tools. The image input and numerical data structures of the system conform to standard open formats and the system works natively on commercially available versions of standard operating systems. Multithreading support enables speed and straightforward scale up. This system is designed to automate the analysis of images from digital microscope cameras and high content screening analysis instruments. For most assays an assay development step is required to determine the best image analysis settings and biological preparation. It is an iterative plate by plate and well by well process cycling between image acquisition image analysis and statistics. Once the assay conditions and image processing conditions are set these settings are applied in more routine conditions.

In the automated image analysis of the pending applications analysis starts by breaking down each image into core biological component masks for cells and tissues. Then measurements are aggregated as needed for experiments with slides wells plates etc. First all of the nuclei available from the nuclear images are identified. A nuclear mask for each cell is established where the mask contains all of the pixels locations automatically identified as nuclear for a given cell. Then a second image is analyzed. Presuming an RNA image for example analysis assigns RNA spots in the image to an RNA mask. These masks are determined by the algorithm but roughly correspond to the brightest pixels in the RNA image. A rich set of data parameters are then calculated on a per cell basis .

As per an RNA example of the cell is analyzed wherein Nm is a nuclear mask and corresponds to the number of pixels that make up the nuclei Cm is a cytoplasmic mask which extends from the cell boundaries to the nucleus and Rm is an RNA mask and corresponds to the number of pixels found within RNA dots.

In an automated image analysis system incorporating inventions of the pending 081 and 146 applications system functionality is presented to users through a GUI including a main window an image window and a data viewer.

The main window seen in is what users see at launch. The image viewer and data are accessed from this main window. As may be appreciated the main window constitutes a simple easily understood and operated interface. This simplicity is especially stark relative to other similar packages. The steps required to analyze a slide a single well a multi well plate or an arbitrarily large batch of multi well plates are similar. In the simplest case a user selects an appropriate image processing algorithm indicates a storage location of an image or images to be processed and clicks a run button.

The Thread count displayed in this window refers to how many of the computer s processors are to be used for analysis. This multithreading capability is useful in providing speed and scalability for larger data sets and more sophisticated image analysis. Multithreading is useful for common multi core laptops and workstations as well as for larger scale dedicated servers with many processors.

Once the initial analysis is complete image processing results may be inspected in an image viewer. See in this regard. This window displays raw unprocessed images overlaid with masks created by automated image processing. an original image. Here again the emphasis is on usability and simplicity. Every cell is identified with a unique number and the results of the image segmentation are clearly displayed. The controls offer instant updates as to which image well mask or mask edge is displayed and transparently integrate well with image zooming contrast enhancement screenshot pseudo color control features. The result is a facile interface enabling a user to verify image segmentation and inspect areas of interest within a screen. The example shown in is a two color RNA example with automatically generated cell masks unique cell IDs and control dialog windows.

The numbers derived from the segmentation are then viewed and manipulated through a data viewer. See . Though hundreds of measurements may be routinely available during image processing a far smaller number may be relevant to any one experiment. To afford ease of use the data viewer is built to offer access to measurements of interest without overwhelming users. Users can create and export raw data tables histograms scatter plots. All of the data can be filtered through a very powerful gating interface.

Per automated image analysis generates a number of measurements for each cell within an image. These data are aggregated and analyzed as required by the experiment within the data viewer.

The data viewer of enables inspection of numerical data for each individual cell well plate and experiment. For example the automated image processing systems of the referenced provisional applications may work with plates up to 3456 in size and may store an experimental condition for each well. Such conditions may include for example time points in a time course or chemistry dose information. All the data are stored and can be exported into commonly used text formats csv jpeg files .

While the automated image analysis system incorporating inventions of the pending 081 and 146 applications provides fast intuitive user control and management of automatic image processing data calculation and result presentation in high content screening and or high throughput screening further functionality and adaptability are desirable in order to enrich the results produced.

It is desirable for a gating interface to be able to take advantage of automatic segmentation of the raw images into an aggregation of individual cell data. Once the data is transformed into cytometry data the ability to filter the cells into subpopulations provides a useful analysis tool.

It is desirable to be able to selectively initialize image processing by selecting or assembling an image processing algorithm from a library of routines.

It is desirable to be able to screen images by visual inspection before during and after image and data processing by the algorithm in order to assess the quality of results obtained.

Automated image processing operations of pipelined image processing systems and methods are controlled with a graphical user interface enabling user control of setup and execution of an image processing algorithm and user viewing of results.

The graphical user interface enabling a user to control setup and execution of an image processing algorithm and to view results remove with a gating function that removes outliers and artifacts from the image analysis results.

Cell by cell well and experiment data are easily manipulated by tools accessed via a tools window such as is shown in . For example tools for image analysis may include gating histogram and scatter plotting. Any combination of raw or gated numerical cell data can be viewed and exported into common Excel compatible formats.

With reference to gating may be used routinely to remove outliers and artifacts from the image analysis results. When imaging hundreds of cells per well over thousands of wells it is frequently desirable to view results based solely on data from relevant cells.

Gating may be used broadly in a wide variety of situations to include and exclude cells based on the values of one of more measurements. Some representative examples include cells with protein expression beyond a certain level successfully transfected cells in a transient transfection removal of outliers and artifacts from images studying only dividing cells and finding rare cells that express a unique combination of size shape and fluorescent markers. Most interesting cell biology involves heterogeneous populations of cells. Combining image analysis with a powerful gating tool helps scientists access more subtle data.

The gating interface provides a significant step forward in usability. Previous implementations of gating required a detailed understanding of how to logically construct an interesting gate the result of which was a long character string of ANDs and NOTs . Such a gating interface is very difficult for routine use by biologists. The gating interface demonstrated and illustrated herein is driven by easily manipulated and understood drop down lists and buttons. Additional steps within a gate are created by pressing the and removed by pressing the buttons.

A system and a method for processing an original image of biological material to identify components of a biological object may be implemented in a software program written in the C and or Java programming languages and a counterpart system may be a general purpose computer system programmed to execute the method. Of course the method and the programmed computer system may also be embodied in a special purpose processor provided as a set of one or more chips. Further there may be a program product constituted of a program of computer or software instructions or steps stored on a tangible article of manufacture that causes a computer to execute the method. The tangible article of manufacture may be constituted of one or more real and or virtual data storage articles.

With further reference to the processor may be a programmed general purpose digital processor having a standard architecture such as a computer work station. The processor includes a processing unit CPU that communicates with a number of peripheral devices by way of a bus subsystem . The peripheral devices include a memory subsystem MEMORY a file storage subsystem FILE user interface devices USER an input device INPUT and an interface device INTERFACE . It is not necessary that the processor be connected directly to the microscope it may receive magnified images produced by the microscope from a portable storage device or by way of a local or wide area network. For example magnified images obtained by a microscope may be transported to the processor over the internet.

The bus subsystem includes media devices ports protocols and procedures that enable the processing unit and the peripheral devices and to communicate and transfer data. The bus subsystem provides generally for the processing unit and peripherals to be collocated or dispersed

The memory subsystem includes read only memory ROM for storage of one or more programs of instructions that implement a number of functions and processes. One of the programs is an automated image process for processing a magnified image of biological material to identify one or more components of an image. The memory subsystem also includes random access memory RAM for storing instructions and results during process execution. The RAM is used by the automated image process for storage of images generated as the process executes. The file storage subsystem provides non volatile storage for program data and image files and may include any one or more of a hard drive floppy drive CD ROM and equivalent devices

The user interface devices include interface programs and input and output devices supporting a graphical user interface GUI for entry of data and commands initiation and termination of processes and routines and for output of prompts requests screens menus data images and results.

The input device enables the processor to receive digital images directly from the camera or from another source such as a portable storage device or by way of a local or wide area network. The interface device enables the processor to connect to and communicate with other local or remote processors computers servers clients nodes and networks. For example the interface device may provide access to an output device by way of a local or global network .

Methods and apparatuses for practicing the teachings of this specification may be constituted in whole or in part of a program product with a computer readable storage medium network and or node that enables a computer a processor a fixed or scalable set of resources a network service or any equivalent programmable real and or virtual entity to execute a GUI and or perform image processing as described and illustrated below. The program product may include a portable medium suitable for temporarily or permanently storing a program of software instructions that may be read compiled and executed by a computer a processor or any equivalent article. For example the program product may include a programmed CD such as is seen in or a network accessible site node center or any equivalent article.

Known means acquire format and store magnified images in digital formats. For ease of illustration and explanation the magnified images may be acquired from multi well plates containing biological chemical and or pharmaceutical material. The magnified images are stored for processing. The system of includes capabilities to process magnified images and to conduct analysis of the image processing results.

It is desirable to provide a user with a simple intuitive graphical user interface GUI giving the user the power of a plug in processing architecture in which algorithmic procedures for image processing may be added to and deleted from a processing pipeline to enable it to process various image components or features. A user may begin working quickly using established routines embodying image processing algorithms. A user may also create complex pipelines of plug in routines to do advanced image processing without having to write any source code.

The desirable simplicity of the solution depends on the fact that nearly all of the complexity in image processing especially for biological applications happens in one place at the point where several image channels must be overlaid segmented into cells and measured for biological properties.

Inputs for the complex part of an image processing operation may be constituted of a set of grayscale images. The outputs may include images including a set of labeled masks which identify for example the interesting parts of cells and data in a variety of formats for example a table of measurements on each cell.

The GUI provides the user with a simple way to define the input grayscale images. It then automatically runs the exact same complex image analysis on every image in every designated well of every designated plate of a batch producing labeled masks and databases of measurements. Once this analysis has been performed the GUI gives the user access to image and data viewer tools to view the images and masks along with tools to examine the measurements.

In order to do such complex image analysis it is desirable that certain common operations be factored out . In this regard 

DataTable an object which contains either the set of all measurements on all cells in a well or contains a statistical summary of another DataTable.

Functions the following processor or computer executed functions manage the analysis of batches of plates 

analyzePlate As seen in this function creates an empty DataTable that will hold a statistical summary of the measurements performed on every well in the plate. It then examines the list of gates that will be applied to each well s DataTables and creates a similar empty DataTable for the corresponding statistical summary of each gated DataTable. The function then loops through every well in the plate. For each well an output folder is created and the well is analyzed using the function analyzeWell which returns a list of statistical summary DataTables for the well. These are then appended to the corresponding DataTables for the plate. When all wells have been analyzed the list of summary DataTables are saved to the output folder. This function is implemented in a programmable processor or computer as follows 

analyzeWell As seen in this function creates an empty DataTable that will hold the complete set of measurements for all cells in the well. In general it is impossible to analyze all images in the well at once because there may be hundreds of images in a well arranged in a rectangular scan that may be very large. The WellScanManager provides tools to sew these into clusters of adjacent images and takes care of the logic at the edges. It loops through each cluster of images and also loop through each channel loading the cluster for each channel and analyzing them as an overlaid set of images using the function analyzeImage. This function returns a set of labeled masks which we save to the output folder. It also inserts data into our DataTable. When all clusters have been analyzed for the well the DataTable is saved to the output folder. Any gating operations are then performed on this DataTable and all resulting DataTables are also saved. For each of the DataTables that we produce we also create a statistical summary which is saved to the output folder. These summary DataTables are returned to the calling function. This function may be implemented in a programmable processor or computer as follows 

analyzeImage As seen in this function segments a set of grayscale images to produce labeled masks where the labeling provides a unique ID for each cell. The function also computes any required measurements and appends the results into a DataTable which grows each time this function is called until the entire well has been analyzed. In general different algorithms will perform different segmentation operations and compute different measurements so this analyzeImage function is unique to each algorithm. Some algorithms implement this with hard wired code but there is also an option to simply apply a pipeline of plug ins directly to the images. This pipeline makes certain assumptions it assumes it will take grayscale images as inputs perform segmentation on them to produce labeled masks as outputs and will also perform measurements on the images using the labeled masks and insert the results into a DataTable. In this way we restrict the set of pipelines to a very useful subset of all possible pipelines. By doing this we have a very simple user interface and yet still have a powerful plug in architecture for doing complex image processing. This function may be implemented in a programmable processor or computer as follows 

applyGates As seen in this function applies a set of gates to a DataTable to produce a set of gated DataTables. The gates can be chained together so that the output DataTable of one gate becomes the input DataTable for another one. This function takes care of the logic of connecting them together and returning all the DataTables in a list. This function may be implemented in a programmable processor or computer as follows 

As seen in and the GUI includes a pipeline editor having a dialog with four tabs that match the conceptual workflow of creating a new pipeline. The tabs are Inputs Pipeline Details and Test.

Inputs Tab As is evident with reference to the GUI enables a user to define the input channels for an image processing algorithm with the following fields 

Number of Channels Integer spinner field that allows the user to specify the number of channels. Changing this value changes the number of rows in the table Channels and Their Default Values. 

Channels and Their Default Values A table in which each row represents a channel. Each column is editable by clicking the field. The names data types and edit controls include 

Channel Image Abbreviation Alphanumeric string editor that is used as the abbreviation for this channel.

Pipeline Tab As is evident with reference to the GUI enables a user to assemble a pipeline image process using selected plug in functions and the following fields 

Pipeline Inputs Table of the pipeline inputs based upon the Channels and Their Default Values table on the Inputs tab. Note that each row on the Channels and Their Default Values table contributes several rows to this table.

Pipeline Plugins List of plugins that make up the current pipeline. The plugins appear in order from top to bottom. The inputs for the currently selected plugin appear in the Plugin Inputs table on the right. Note that plugins with properly connected inputs appear in black while improperly connected plugins are indicated in red.

Details . . . Button that brings up the Plugin Resource Editor dialog for the selected plugin. This button is disabled when no plugin is selected. See section below.

Remove Button that removes the selected plugin in the Pipeline Plugins list. The list is then updated removing the selected plugin and updating any plugins that relied on the output of the deleted plugin so that they now have an invalid connection and appear in red. This button is disabled when no plugin is selected.

Move Up Button that moves the currently selected plugin up by one position in the Pipeline Plugins list. The list is then updated updating any plugins that now has invalid connections so they appear in red. This button is disabled when no plugin is selected or when the top item on the list is selected.

Move Down Button that moves the currently selected plugin down by one position in the Pipeline Plugins list. The list is then updated updating any plugins that now have invalid connections so they appear in red. This button is disabled when no plugin is selected or when the bottom item on the list is selected.

Plugin Inputs Table with columns Plugin Inputs and Connections That represent the inputs for the currently selected plug in. The values in the connections column are editable with a combo box that shows all valid options for that input i.e. of the same type that are pipeline inputs or are outputs of a previous pipeline. Note that when all inputs are set the plug in will appear in black on the Pipeline Plugins list. Plug ins that do have unconnected inputs will appear in red.

Add Button that creates a new output of the type selected on the list Pipeline Types and adds it to the Connect Outputs table. This button is disabled when no item is selected on the Pipeline Types list.

Remove Button that removes the selected row from the Connect Outputs table. This item is disabled when no items are selected on the Connect Outputs table.

Connect Outputs Table with three columns Type of Output Name and Connection. The name and connection columns are editable. Name is an alphanumeric field that is simply the name of the output. Connection is a menu of items of based on the type column from the pipeline plug ins or pipeline inputs.

Plugin Resource Editor dialog As is evident with reference to the GUI enables a user to assemble a pipeline image process using selected plug in functions and the following fields. This dialog appears in response to the Details button on the pipeline tab and it contains the details of the currently selected plug in.

Plugin Name Alphanumeric name of the associated plug in. This field can be edited to change the name.

Input Types Table with the columns Input Types Input Names and Modified In Place none of which are editable. Information associated with the currently selected row appears in the Selected Resource group.

Output Types Table with the columns Output Types and Output Names neither of which are editable. Information associated with the currently selected row appears in the Selected Resource group.

Selected Resource Group of controls that represent the current state of the selected row in either the input types or output types tables. Note only one item on both those list can be selected at one time.

Clone From Context Before Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

View After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

View In Debug Mode Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Write To File After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Write To File In Debug Mode Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Save To Context After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Remove From Context After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Default Checkbox that is only enabled and can only be checked when it applies to the currently selected resource. Controls associated with this checkbox appear depending on the resource type selected.

Details Tab As is evident with reference to the GUI Details tab plays the same role for the plugin as a whole as the Plugin resource editor above does for a single plugin within the pipeline. Thus it has the same controls and behaves the same.

Input Types Table with the columns Input Types Input Names and Modified In Place none of which are editable. Information associated with the currently selected row appears in the Selected Resource group.

Output Types Table with the columns Output Types and Output Names neither of which are editable. Information associated with the currently selected row appears in the Selected Resource group.

Selected Resource Group of controls that represent the current state of the selected row in either the input types or output types tables. Note only one item on both those list can be selected at one time.

Clone From Context Before Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

View After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

View In Debug Mode Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Write To File After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Write To File In Debug Mode Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Save To Context After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Remove From Context After Plugin Executes Checkbox that is only enabled and can only be checked when it applies to the currently selected resource.

Default Checkbox that is only enabled and can only be checked when it applies to the currently selected resource. Controls associated with this checkbox appear depending on the resource type selected.

Test Tab As is evident with reference to the GUI Test tab allows the user to test the current pipeline.

Imaging Naming Convention Combo box with list of known or applicable naming conventions. Naming conventions are naming format of source folders

Source Folder The string path to the folder that contains the source images. The browse button associated with this control brings up a dialog to allow the user to traverse the file system and select a source folder. Selecting a folder using this dialog will fill in the source folder field path.

Destination Folder The string path to the folder that contains or will contain the data and images created by running this algorithm. The browse button associated with this control brings up a dialog to allow the user to traverse the file system and select a destination folder. Selecting a folder using this dialog will fill in the destination folder field path.

Channel table Table that allows the user to specify the input fields for each channel of this algorithm for the test run. It has the following columns 

Test Pipeline Button that allows the user to test this pipeline. Only enabled when all folders and channels values are valid.

The processing workflow and GUI features disclosed above enable a user to select and initialize an image processing algorithm establish and configure processing channels for features in the images to be processed and specify parameters for performing data analysis of the image processing results. With reference to an example of a method for performing automated image analysis with GUI management and control of an image processing pipeline workflow and data analysis is discussed. In the form of a workflow the method includes the following acts 

Initially presume that a user creates a hypothesis about how a certain type of biological cell or tissue sample will respond to a new set of conditions. In an example image is made of cells in an experiment measuring hormone regulation of pHSLserine660. The representative image has nuclei shown in blue lipid droplets shown in green and the pHSLserine660 shown in red. An antibody was used that specifically recognizes hormone sensitive lipase that has been phosphorylated on amino acid 660 which is a serine. Hormone Sensitive Lipase HSL is phosphorylated on serine 660 by cAMP dependent protein kinase and likely by other kinases that are regulated by hormones. The hormone that was used was Lys gamma Melanocyte Stimulating Hormone and the concentrations are in nM. There is increasing interest in this hormone in adipocyte biology.

A biologist would like to measure the exact nature of this response. Presume that she can visualize the qualitative response but can t readily systematically quantify the response. The quantification requires a prohibitive amount of time and is error prone if possible at all. The tissues of interest are prepared such that a digital microscope such can acquire and save an image of the relevant features can be acquired and saved for further processing. In this case lipids and pHSLserine660 are tagged with fluorescent labels and imaged with a standard fluorescent digital microscope. Using a GUI Opening screen seen in the user is able to select initialize and launch an image processing algorithm. Then using one or both of an image viewer and a data viewer selected from the Opening screen drop down menu of the user can view and assess image processing results and view data analysis of those results.

With reference to if a validated algorithm for this type of sample already exists there is a Define Algorithm interface for the user to choose the correct algorithm. The user may optimize one or two basic parameters for the specific experiment. Due to variable staining and imaging conditions an algorithm s sensitivity may need adjusting using the GUI menu of . Using the Opening screen Wells to Run Algorithm On the wells whose images are to be processed are identified. Given a known algorithm the analysis is executed.

Once the image processing algorithm processing is complete the user may want to visually verify that the masks created match her expectations. An image with masks created by the algorithm is viewed using the Image Viewer entry in the menu seen in the image is viewed as in . In the image an overlay of yellow and red outlines of the automatically generated masks of the nuclei and lipids are assessed by the user. If the masks do not meet expectations then the user may elect to have the designated images reprocessed with new sensitivity settings. This may be repeated heuristically until the user is either satisfied with how well the algorithm is generating a representative mask or decides that a more sophisticated algorithm is required.

If the user believes the masks are good enough she may proceed to the numerical analysis of the biological question How does the biology vary with respect to different conditions 

With the image processing algorithm processing completed many measurements are now available for every cell well and sub cellular region defined algorithm generated masks and the user may select the Data Viewer via the Opening screen menu seen in . Some of the data viewer outputs are seen in .

In this regard image shows two representative bar graphs comparing groups of wells that share the same experimental conditions. In this case the response is with respect to Melanocyte Stimulating Hormone. The user may not know exactly which measurement will be the most reliable or responsive. She may explore and select from the data viewer outputs set forth in the list of measurements displayed in the left most column to see what kind of data is generated.

The summary statistics viewed in constitute a final snapshot of the experiment in question. It may be important to understand how different the two populations of wells represented in are with respect to one another. It may be important to describe how reliable the measurement will be in a large scale screening environment. The scope and manner that users may want to interrogate their data can be very broad.

If the statistical results aren t good enough for the experiment to be considered complete opportunities for improvement are 

During image processing the algorithm has identified every cell in the image and assigned a cell ID. demonstrates that each cell has a unique ID and that each unique cell has a set of unique measurements. Using the gating screen of an arbitrary set of filters can be set up so that only the cells of interest are used in the numerical analysis of image processing results. If changing the settings and adjusting the gating of an existing algorithm doesn t give the needed results a new algorithm may be required. The user then returns to the Input screen as per .

One set of algorithms may comprise combinations of core functions from the other algorithms. For example for an arbitrary number of colors the nuclear segmentation function of one algorithm might be combined with cell border segmentation of another algorithm and the sub cellular body segmentation of a third known algorithm. All of the names and default parameters are set to fit the experiment. An algorithm to measure lipid droplets may only require minor naming and key parameter adjustments to be suitable measure myofibrils in heart cells. Sometimes a completely new algorithm is required. These are characterized by the use of well established image processing techniques to manipulate the images. The core architecture of managing the images results masks statistics gating and graphing are all maintained but novel core segmentation or analysis technique may need development.

Although the invention has been described with reference to presently preferred embodiments it should be understood that various modifications can be made without departing from the spirit of the invention. Accordingly the invention is limited only by the following claims.

