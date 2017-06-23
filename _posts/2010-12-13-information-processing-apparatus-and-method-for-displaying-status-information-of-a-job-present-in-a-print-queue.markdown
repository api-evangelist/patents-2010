---

title: Information processing apparatus and method for displaying status information of a job present in a print queue
abstract: An information processing apparatus provided with a display unit includes a status information display unit configured to display status information of a job present in a print queue via the display unit, an acquisition unit configured to acquire setting information of the job present in the print queue, and a job determination unit configured to determine, based on the setting information acquired by the acquisition unit, whether the job is a job to be output to a printing apparatus. The status information display unit displays, without displaying status information of a job determined not to be output to the printing apparatus by the job determination unit, status information of a job determined to be output to the printing apparatus by the job determination unit via the display unit.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08922810&OS=08922810&RS=08922810
owner: Canon Kabushiki Kaisha
number: 08922810
owner_city: Tokyo
owner_country: JP
publication_date: 20101213
---
The present invention generally relates to information processing and more particularly to an information processing apparatus and an information processing method for controlling status displaying of a print job according to presence of an output at a printing apparatus.

There has conventionally been provided a technology for appropriately displaying status information of a print job during a period from issuance of a print instruction from an application to completion of printing on a recording medium by a printing apparatus as discussed in Japanese Patent Application Laid Open No. 2008 107980. According to the technology discussed in Japanese Patent Application Laid Open No. 2008 107980 a status monitor continues monitoring of print jobs as long as they are present in a print queue. When processing is started from a standby status and the printing has become in progress print in progress status a display unit displays the status.

A printer driver that generates and manages print jobs may delete from the print queue a print job set to a print in progress status based on print setting set for the print jobs. For example a preview activation module which is a module of the printer driver temporarily deletes the print job at the time of print preview displaying.

A status information display module checks setting of the print job to have become a print in progress status and displays a status information display screen to notify a user of the status of the print job.

For the print job to which displaying of a print preview screen has been set the status information display screen is displayed since the print job has been set to the print in progress status. However the print job is not output by the printing apparatus and is deleted from the print queue by the preview activation module during print previewing. Thus the status information display module immediately deletes the status information display screen that has been displayed.

Thus when the printer driver processes the print job to which the print preview displaying has been set the status information display screen is displayed and then immediately deleted. This results into a possibility that the user may misunderstand that the print job is cancelled even when the print job itself is being previewed.

According to an aspect of the present invention an information processing apparatus is provided having a display unit includes a status information display unit configured to display status information of a job present in a print queue via the display unit an acquisition unit configured to acquire setting information of the job present in the print queue and a job determination unit configured to determine based on the setting information acquired by the acquisition unit whether the job is a job to be output to a printing apparatus. The status information display unit displays without displaying status information of a job determined not to be output to the printing apparatus by the job determination unit status information of a job determined to be output to the printing apparatus by the job determination unit via the display unit.

Further features and aspects of the present invention will become apparent from the following detailed description of exemplary embodiments with reference to the attached drawings.

Various exemplary embodiments features and aspects of the invention will be described in detail below with reference to the drawings.

Exemplary embodiments described below are in no way intended to limit the scope of the present invention according to the appended claims. In addition all the combinations of features of the exemplary embodiments are not essential to solutions provided by the present invention.

Referring to a block diagram of a configuration of a printing system that includes a printing apparatus printing apparatus and an information processing apparatus personal computer connected to the printing apparatus according to an exemplary embodiment will be described.

The ROM stores an initialization program. The external storage device stores an application program group an operating system OS a printer driver and other various data. The RAM is used as a work memory by various programs stored in the external storage device .

The printing apparatus includes an input output interface a RAM a print engine a ROM and a CPU . The input output interface is connected to the input output interface of the personal computer . The present exemplary embodiment is described on the assumption that a connection interface is a universal serial bus USB . However any type of a connection interface can be used. An extension option for extending a function of the printing apparatus can be connected to the input output interface .

The RAM is used as a main memory and a work memory for the CPU and stores a reception buffer for temporarily storing a received print job and various data. The print engine performs printing based on the data stored in the RAM . The ROM stores various control programs such as a status management program and data used by each control program. The CPU controls the respective units of the printing apparatus according to the control programs.

The status management program monitors a status of the printing apparatus based on information from various sensors not illustrated in the printing apparatus and generates status information and stores it in the RAM .

The assigning example of processing tasks to the personal computer and the printing apparatus has been described above. However the assignment is not limited to this example. Other forms can be employed.

Print data generated by an application is temporarily stored as spool data in a print queue of a spooler via a print support function of the OS to be used as a print job. The print job is converted by the printer driver into a print command that is interpretable by a printing apparatus and is then transmitted to the printing apparatus to be printed.

The application adds when instructing printing print setting information returned from a user interface module to the print job via the print support function of the OS. The print setting information is set before the application instructs a start of printing. The user interface module activates a status information display module after receiving a printing start notification from the print support function of the OS.

The print job that has been passed to the printer driver is first processed by a page configuration module . The page configuration module performs page configuration processing such as sorting of pages of the print job or collection of a plurality of pages into one for the print job according to the print setting information.

The print job is then passed to a preview activation module . The preview activation module calls a print preview display module when the print setting information contains an instruction of displaying print preview information. The print preview display module displays a print preview screen illustrated in each of on the display unit of the personal computer so that a user can check a printing result beforehand.

When the print setting information contains no instruction of displaying the print preview information the preview activation module passes the print job to a command generation module . The command generation module converts print data of the print job into a print command that is interpretable by the printing apparatus according to the print setting information. Such print commands are sequentially transmitted to the printing apparatus by a command transmission reception module .

The command transmission reception module reads a status of the printing apparatus such as information of error generation in the printing apparatus or currently printed page information to pass it to a status information display module . The status information display module analyzes the status of the printing apparatus displays information of the printing apparatus on a status information display screen illustrated in each of on the display unit of the personal computer thereby enabling the user to check a status of the print job or the status of the printing apparatus .

According to the present invention for example this module performs processing such as job determination as to whether a job is to be output to the printing apparatus command determination as to whether command transmission has been started or status determination as to a status of the print queue.

Referring to the first exemplary embodiment of the present invention will be described in detail. is a flowchart illustrating processing of each of the user interface module the page configuration module and the status information display module.

In step S the user interface module starts processing after reception of a print start notification from the print support function of the OS. In step S the user interface module activates the status information display module . In step S the user interface module finishes the processing. The processing of the status information display module activated in this processing will be described below.

In step S after reception of a print job from the OS the page configuration module starts processing. In step S the page configuration module checks the print job or print setting of the print job. In step S the page configuration module records it as print job information in a file.

The print setting of the print job is designated before a printing start from the application on a print setting screen of the user interface module illustrated in . The print setting screen has a preview display setting place as one of print setting items illustrated in .

The information recorded in the file includes as illustrated in job ID a total number of pages and a printer output . The print job information recorded in the file is passed to the status information display module . In the present exemplary embodiment as an inter process communication method between the modules file sharing is taken as an example.

During the processing of step S the user interface module has received only a job identifier from the OS. Thus the user interface module cannot accurately acquire print setting of the print job. For example the user interface module cannot acquire print setting for each page. The print setting of the print job is accordingly fed to the status information display module by the page configuration module .

In step S after step S the page configuration module executes page configuration processing such as page sorting of the print job. In step S the page configuration module passes the print job to the subsequent preview activation module . In step S the page configuration module finishes the processing.

In step S the status information display module activated in step S starts processing. In step S the status information display module checks print jobs in the print queue. In step S the status information display module determines whether there is any print job in the print queue.

When there is no print job NO in step S in step S the status information display module finishes the processing. When it is determined that there is a print job YES in step S in step S the status information display module checks whether there is a file recording print job information.

In step S the status information display module determines whether there is print job information. When there is no print job information NO in step S the processing returns to step S to stand by until the page configuration module generates a file that records print job information.

When it is determined that there is print job information YES in step S in step S the status information display module determines whether the print job is a print job to be output to the printing apparatus.

When a job being processed is JOB ID 26 in the column of the job ID illustrated in NO is written in the column of the printer output and the status information display module determines that the print job is a print job not to be output to the printing apparatus. When it is determined that the print job is a print job not to be output to the printing apparatus NO in step S in step S the status information display module finishes the processing.

When the job being processed is JOB ID 25 in the column of the job ID illustrated in YES is written in the column of the printer output and the status information display module determines that the print job is a print job to be output to the printing apparatus. When it is determined that the print job is a print job to be output to the printing apparatus YES in step S then in step S the status information display module displays a status information screen illustrated in and the processing returns to step S.

After the command transmission reception module has transmitted the print command to the printing apparatus and has confirmed the completion of the printing at the printing apparatus the print job is deleted from the print queue . When the status information display module determines that there is no print job in the print queue NO in step S then in step S the processing is terminated. Thus information of the print job can be informed to the user until the printing apparatus completes the printing.

Through the processing described above in the case of the print job to be output to the printing apparatus the status information display module displays the status information screen . On the other hand in the case of the print job not to be output to the printing apparatus the status information display module does not display the status information screen . Thus the status information display module can perform appropriate display determination.

In step S after reception of the print job the preview activation module starts processing. In step S the preview activation module checks print setting information of the print job to determine whether there is an instruction of displaying the print preview screen .

When it is determined that the print preview screen is not displayed NO in step S in step S the preview activation module passes the print job to the command generation module . In step S the processing is finished. When it is determined that the print preview screen is displayed YES in step S in step S the preview activation module activates the print preview screen illustrated in . Processing of the print preview display module activated in this case will be described below.

In step S the preview activation module stores print data of the print job in a RAM . The RAM is similar to the RAM illustrated in . In the present exemplary embodiment the storage of the print data in the RAM is taken as an example. However the print data can be stored on other storage media. In step S the preview activation module deletes the print job from the print queue . In step S the processing is finished.

Deleting the print job from the print queue by the preview activation module in step S enables printing processing of other print jobs not subjected to print previewing even during displaying of a print preview of the print job.

In step S the print preview display module activated in step S starts processing. In step S whether there is print data in the RAM is checked. In step S the print preview display module determines whether there is print data in the RAM . When there is no print data yet or storage of print data is not completed NO in step S the processing returns to step S to stand by until completion of the print data storage.

When it is determined that the storage of the print data in the RAM has been completed YES in step S then in step S the print preview display module displays a print preview image illustrated in .

By setting previewing for a plurality of jobs the plurality of jobs can be temporarily stored in the RAM and collectively previewed. Data relating to the plurality of jobs being previewed can be combined into one job to be re input to the print queue.

In step S the print preview display module determines whether there is any print execution instruction from the user. When the user presses a print start button illustrated in then in step S the print preview display module adds print data as a print job to the print queue thereby resuming the printing of the print job for which the preview screen has been displayed. In step S the print preview display module deletes the stored print data from the RAM . In step S the processing is finished.

According to the present exemplary embodiment the print job input in step S is determined to be a job actually output to the printing apparatus. Thus the job for which previewing is set and which is deleted from the print queue in step S is determined to be a job not actually output to the printing apparatus.

In the present exemplary embodiment the preview activation module is an independent driver configuration module. However the preview activation module can be included in the page configuration module . When the page configuration module includes the preview activation module the print preview display module is called by the page configuration module .

Print data generated by an application is temporarily stored as spool data in a print queue of a spooler via a print support function of an OS to be used as a print job.

A normal print job is converted by a printer driver into a print command that is interpretable by a printing apparatus and then fed to the printing apparatus to be printed. However there are other types of jobs such as a cleaning job for instructing cleaning of the printing apparatus . The cleaning job is temporarily stored as a print job in the print queue in the form of a print command that is interpretable by the printing apparatus .

Special jobs such as a cleaning job different from the normal print jobs have been converted into a print command that is interpretable by the printing apparatus . Thus the page configuration module the preview activation module and the command generation module perform no processing for this special job.

For example the jobs such as a cleaning job are sequentially transmitted to the printing apparatus by a command transmission reception module . The printing apparatus performs cleaning based on a received cleaning job command. In the execution of the cleaning job the print support function of the OS notifies a user interface module of a start of printing.

The user interface module that has been notified of the start of printing calls a status information display module . The command transmission reception command reads a status of the printing apparatus such as information on an error generated in the printing apparatus and passes it to the status information display module .

The status information module analyzes the status of the printing apparatus and displays the information of the printing apparatus on the display unit of the personal computer thereby enabling the user to check the status of the printing apparatus .

The status information display module checks in the file recording the print job information illustrated in that a job is a print job to be output to the printing apparatus and then displays a status information display screen .

However the page configuration module performs no processing for the special job and hence the file cannot be fed. This disables the status information display module from displaying the status information display screen . Referring to a method for solving this problem will be described.

In step S the status information display module activated by the user interface module starts processing. In step S the status information display module checks print jobs in the print queue . In step S the status information display module determines whether there is any print job. When there is no print job NO in step S in step S the processing is finished. When it is determined that there is a print job YES in step S in step S the status information display module checks whether there is a file recording print job information. The file recording the print job information is similar to the file illustrated in .

In step S the status information display module determines whether there is print job information. As described above no file is generated in the cleaning job. When there is no print job information NO in step S in step S the status information display module checks whether there is command transmission information in a registry.

The command transmission information is generated by the command transmission reception module which will be described below. In step S the status information display module determines based on the command transmission information whether the command transmission reception module has started command transmission to the printing apparatus .

When it is determined that the command transmission has been started YES in step S in step S the status information display module displays the status information display screen . More specifically even in a case of a print job such as the cleaning job on which the page configuration module performs no processing when the command transmission reception module has started the command transmission to the printing apparatus the status information display module displays the status information display screen .

When the status information display module determines that the command transmission has not been started NO in step S the processing returns to step S. As a result a status in which the status information display screen is not displayed continues.

In a case of the normal print job the page configuration module performs processing on the job and hence a file is generated by the page configuration module . Thus the status information display module determines that there is print job information YES in step S . In step S the status information display module determines whether the print job is a print job to be output to the printing apparatus.

When it is determined that the print job is a print job to be output to the printing apparatus YES in step S in step S the status information display module displays the status information display screen . When it is determined that the print job is not a print job to be output to the printing apparatus NO in step S in step S the status information display module finishes the processing.

Processing of the command transmission reception module will be described. In step S the command transmission reception module starts processing after reception of print commands. In step S the command transmission reception module transmits a first print command to the printing apparatus . In step S the command transmission reception module writes the command transmission information in the registry.

In step S the command transmission reception module sequentially transmits the subsequent print commands to the printing apparatus . In step S the command transmission reception module transmits a last print command to the printing apparatus . In step S the command transmission information written in the registry is returned to its initial value. In step S the processing is finished.

Data of 0x00000001 is written in a registry value of SendingData . This indicates that the command transmission reception module has started command transmission. After reading of the status of 0x00000001 in step S the status information display module determines that the command transmission reception module has started command transmission to the printing apparatus .

After the transmission of the last print command to the printing apparatus in step S the command transmission reception module returns the command transmission information in the registry to the initial value 0x00000000 indicated by the data .

Through the processing even in a case of the data that is not processed by the page configuration module whether the status information display screen is displayed can be appropriately determined. In the present exemplary embodiment the cleaning job has been described as the example of the job not processed by the page configuration module . However the present invention is applicable to other special jobs that are not processed by the page configuration module .

The spooler does not pass any temporarily stored print job when an error generated in the printing apparatus connected to web services on devices WSD is detected. In this case the status information display module cannot check the print job information or the print command transmission information and hence the status information display screen cannot be displayed. Referring to a method for solving this problem will be described.

In step S the status information display module activated by the user interface module starts processing. In step S the status information display module checks print jobs in the print queue.

In step S the status information display module determines whether there is any print job. When there is no print job NO in step S then in step S the processing is finished. When it is determined that there is a print job YES in step S in step S the status information display module checks whether there is a file recording print job information. The file recording the print job information is similar to the file illustrated in .

In step S the status information display module determines whether there is print job information. When it is determined that there is print job information YES in step S in step S the status information display module determines whether the print job is a print job to be output to the printing apparatus.

When it is determined that the print job is a print job to be output to the printing apparatus YES in step S in step S the status information display module displays the status information display screen . When the status information display module determines that the print job is not a print job to be output to the printing apparatus NO in step S in step S the processing is finished.

On the other hand when it is determined that there is no print job information NO in step S in step S the status information display module checks whether there is command transmission information in the registry. The command transmission information is similar to the command transmission information illustrated in .

In step S the status information display module determines based on the command transmission information whether the command transmission reception module has started command transmission to the printing apparatus . When it is determined that the command transmission has been started YES in step S in step S the status information display module displays the status information display screen .

When it is determined that the command transmission has not been started NO in step S in step S the status information display module checks a status of the print queue . The status information display module acquires the status of the print queue by using an application programming interface API .

In step S the status information display module determines whether the status of the print queue indicates an error generated in the printing apparatus . The status indicating the error generated in the printing apparatus is for example DOOR OPEN or NO TONER .

When the status information display module determines that no error has been generated in the printing apparatus NO in step S the processing returns to step S to continue the state where the status information display screen is not displayed.

When it is determined that an error has been generated in the printing apparatus YES in step S in step S the status information display module displays the status information display screen . In this case the status information display module instructs the command transmission reception module to acquire a status of the printing apparatus and displays the error information in the printing apparatus on the status information display screen in detail.

As described above even in the case of the printing apparatus connected to the WSD and in an error state the status information display module can appropriately display the status information display screen .

Aspects of the present invention can also be realized by a computer of a system or apparatus or devices such as a CPU a micro processing unit MPU and or the like that reads out and executes a program recorded on a memory device to perform the functions of the above described embodiments and by a method the steps of which are performed by a computer of a system or apparatus by for example reading out and executing a program recorded on a memory device to perform the functions of the above described embodiments. For this purpose the program is provided to the computer for example via a network or from a recording medium of various types serving as the memory device e.g. a computer readable medium . In such a case the system or apparatus and the recording medium where the program is stored are included as being within the scope of the present invention.

While the present invention has been described with reference to exemplary embodiments it is to be understood that the invention is not limited to the disclosed exemplary embodiments. The scope of the following claims is to be accorded the broadest interpretation so as to encompass all modifications equivalent structures and functions.

This application claims priority from Japanese Patent Application No. 2009 286891 filed Dec. 17 2009 which is hereby incorporated by reference herein in its entirety.

