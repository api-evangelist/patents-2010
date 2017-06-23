---

title: Information device, program, method, and computer readable recording medium for preventing execution of malicious program code
abstract: An information device performs data processing by executing program codes loaded in a memory with a central control unit. The information device includes a detection unit which detects a timing when any one of the program codes is called, a return address acquisition unit which sequentially acquires return addresses of the program codes loaded in the memory at the timing detected by the detection unit, and a termination unit which searches for an illegal access based on destination addresses that are respectively pointed by the return addresses sequentially acquired by the return address acquisition unit at the timing detected by the detection unit and which terminates the data processing when the illegal access is detected.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09177136&OS=09177136&RS=09177136
owner: FFRI, INC.
number: 09177136
owner_city: Tokyo
owner_country: JP
publication_date: 20100412
---
This application is a U.S. National Phase Application under 35 USC 371 of International Application PCT JP2010 056500 filed Apr. 12 2010.

The present invention relates to an information device in which execution of malicious program code is preventable a program for preventing execution of malicious program code a method for preventing execution of a malicious program code and a computer readable recording medium which stores a program for preventing execution of malicious program code.

Generally on information devices such as PC Personal Computer and WS Work Station there exists a control unit such as CPU Central Processing Unit which executes various types of data processing by sequentially executing program codes loaded in a working area of a storage unit such as a RAM Random Access Memory . In recent years illegal accesses to the information devices has been occurring by way of unauthorized execution using program codes created by malicious users.

Data managed by the information devices are generally assigned with access rights. Accordingly the illegal accesses will not occur as long as the user has no access right. The illegal accesses will be possible if an unauthorized operation is made using a general program code assigned with the access rights to data. One known technique of this sort is using the so called buffer overflow allowing data at the time of execution of the program codes overflow out from a predetermined area allocated in the RAM or anything similar to RAM.

The illegal access using the buffer overflow will now be described in detail by showing comparison between the case where the program codes are properly ran and the case where the program codes are ran with an illegal action.

The information about running the program code illustrated in is stored in a call stack area allocated in the RAM. In the call stack area the data are stored according to a LIFO Last In First Out or FILO First In Last Out structure.

For example in the program code based on the source code illustrated in Return Address1 ebp backup 1 char buf 8 and so forth are stored as a single stack frame when main function is processed. Next when strcpy helloworld function in main function is called ReturnAddress2 ebp backup2 int i and so forth are also stored as a single stack frame.

ReturnAddress return address indicates an address value to which the process is to return upon the completion of a program. Return address is also an address value to which the process is to return upon completion of the subprogram or a function being called. ReturnAddress is automatically stored in the stack area by the CPU immediately after the execution of the program or immediately after the subprogram i.e. function is called.

Ebp is one type of CPU register and indicates an address which is located just before the address of a temporary memory area currently being used. In the example illustrated in ebp indicates addresses before char buf 8 and int i and ReturnAddresses in the stack frame correspond to ebp. Accordingly in the stack frame by backing up the register value as ebp backup an area in the stack frame can be easily used as a memory area for storing temporary data variables and arrays .

In char buf 8 buf which is an array used in main function is stored. The above mentioned buf is an array which can store eight char type 1 byte variables and 8 byte data can be stored in the above mentioned buf. Int i is an int type variable used in strcpy helloworld function.

Accordingly by executing the above mentioned program code a stack frame for main function is allocated in the stack area and a stack frame for strcpy helloworld function is allocated in the stack area. Then the value of int i is sequentially incremented and the 6 byte character string Hello is to be stored in char buf 8 . Next upon completion of strcpy helloworld function ReturnAddress2 is read out to return to main function and upon completion of main function ReturnAddress1 is read out and the program is terminated normally.

Next a case where an illegal act took place when the program code is executed will be described with reference to and .

In the stack area illustrated in the allocation of areas is sequentially carried out downward from the top to the bottom and the writing of data into the allocated areas is carried out upward from the bottom to the top. Accordingly ReturnAddress1 and ebp backup are illegally overwritten with the 12 byte data Hello World if strcpy helloworld function is executed. When the content of ReturnAddress1 is rewritten with an address where an executable program code is located by the above mentioned overwriting process ReturnAddress1 is read out upon completion of main function and the program code is executed.

According to the source code illustrated in the overflow is caused by the character string named Hello World which is defined in advance. However in practice there is a case where data received through a network port of a mail server or Web server or data entered through a console or files is stored into the buf array. In such case an arbitrary program code may be executed by a malicious user through network entry through a console or entry through files and thereby illegal access such as data theft and falsification may occur.

As a method of detecting such illegal access one possible method is by detecting whether any illegal access is executed or not by inspecting the return addresses stored in the stack area and comparing the arrangement pattern of the return addresses under execution of the normal program and the arrangement pattern of the return addresses under operation of an attack code. For example the program may be judged as normal if a destination memory attribute pointed by the return address has a program code attribute or if the memory areas have a non writable attribute.

However return to libc attack see Non Patent Document 1 may not be detected by the above described method of detecting illegal access. The return to libc attack refers to a technique of making an illegal access by calling a function preliminarily stored in a computer without adding any malicious code into the program code.

A possible attack could be an attack using the return to libc attack in which a predetermined program code is executed by combining program codes of programs which are stored in a storage unit of an information device in advance. Also in this method of attack the return addresses in the stack area seem to have similar pattern as those in the return to libc attack so that the program including the attack using the return to libc attack may not be distinguishable from the normal program.

Patent Document 1 discloses a technique using branch trace which is one of the CPU functions so as to detect an action of returning back to the top address of the OS standard function when returning from the function which is being executed to the process of the function at a caller.

 Patent Document 1 U.S. patent application Ser. No. 10 763 867 published as United States Patent Application Publication No. 2005 0166001

 Non Patent Document 1 Return to libc attack online presented by Wikimedia Foundation retrived on Mar. 23 2009 through the Internet URL http en.wikipedia.org wiki Return to libc attack 

However while the technique described in Patent Document 1 might successfully detect the return to libc attack making use of the function called branch trace the technique may increase process load of the CPU since it uses the function owned by the CPU and may also restrict the use of other applications such as performance measurement tool and so forth which make use of the branch trace function. In other words the technique may increase the process load of the computer in a period over which the process for detecting the return to libc attack continues and may thereby degrade the usability of the computer.

The present invention was conceived after considering the above described problems in the prior art and an object of which is therefore to provide a technique of preventing an illegal access using buffer overflow in a reliable and simple manner without depending on the OS functions owned by CPU.

In order to solve the above problems according to one aspect of the present invention an information device which performs data processing by executing program codes loaded in a memory with a central control unit includes a detection unit which detects a timing when any one of the program codes is called a return address acquisition unit which sequentially acquires return addresses of the program codes loaded in the memory at the timing detected by the detection unit and a termination unit which searches for an illegal access based on destination addresses respectively pointed by the return addresses that are sequentially acquired by the return address acquisition unit at the timing detected by the detection unit and which terminates the data processing when the illegal access is detected.

Preferably the memory has a stack area used for storing the return addresses of the program codes and the return address acquisition unit traces and acquires the return addresses stored in the stack area.

Preferably the termination unit detects the illegal access when any of the destination addresses respectively pointed by the return addresses that are acquired by the return address acquisition unit is a starting address of a function and terminates the data processing when the illegal access is detected.

Preferably the termination unit detects the illegal access when an instruction located just before any of the destination addresses respectively pointed by the return addresses that are acquired by the return address acquisition unit is not a call instruction and terminates the data processing when the illegal access is detected.

According to another aspect of the present invention a computer which executes program codes loaded in a memory functions as a detection unit which detects a timing when any one of the program codes is called a return address acquisition unit which sequentially acquires return addresses of the program codes loaded in the memory at the timing detected by the detection unit and a termination unit which searches for an illegal access based on destination addresses respectively pointed by the return addresses that are sequentially acquired by the return address acquisition unit at the timing detected by the detection unit and which terminates the data processing when the illegal access is detected.

According to another aspect of the present invention a method for preventing execution of a malicious program code in a computer which executes program codes loaded in a memory includes detecting a timing when any one of the program codes is called sequentially acquiring return addresses of the program codes loaded in the memory at the detected timing detecting an illegal access based on destination addresses respectively pointed by the acquired return addresses and terminating data processing when the illegal access is detected.

According to another aspect of the present invention a computer readable recording medium stores a program configured to make a computer which executes program codes loaded in a memory function as detection unit which detects a timing when any one of the program codes is called a return address acquisition unit which sequentially acquires return addresses of the program codes loaded in the memory at the timing detected by the detection unit and a termination unit which searches for an illegal access based on destination addresses respectively pointed by the return addresses that are sequentially acquired by the return address acquisition unit at the timing detected by the detection unit and which terminates the data processing when the illegal access is detected.

According to the present invention an illegal access using buffer overflow can be prevented in a reliable and simple manner without depending on the CPU functions.

Hereinafter embodiments of the present invention will be described referring to the attached diagrams. However the scope of the present invention is not limited to the embodiments.

The CPU controls operations of the information device in a centralized manner. The CPU loads program codes and various data which are stored in the storage unit in a work area of the RAM and outputs control signals to the individual units in cooperation with the data loaded in the RAM .

In the storage unit data which includes program codes and various setting information is stored. The data is stored in the storage unit so as to be readable and writable by the CPU . The storage unit is a HDD Hard Disk Drive semiconductor memory and the like for example. The storage unit may alternatively be configured to store the data in a ROM Read Only Memory . The program codes stored by the storage unit includes basic software such as OS Operating System various application programs provided by vendors and programs relevant to the processing described later.

ExitProcess is a function for terminating the program and a termination code of the program to be terminated is set to the argument of ExitProcess. WinExec is a function for allowing execution of a designated program. Since ReturnAddress is located just before ebp backup ReturnAddress can sequentially be traced and acquired by following ebp backup.

The stack frames included in the stack area are sequentially allocated as the program codes being executed when the individual program codes are sequentially executed. For a model case where the main program code is executed and another program code which is relevant to a subroutine is called within the main program code and further another program code is called the area corresponding to each of the above program codes is allocated according to the order of the stack frames. When the process according to each program code is terminated returning to the main program code or a process to be performed after termination of the program will be carried out by the ReturnAddress in the stack frame being read out.

The operation unit accepts an entry of operation made by a user and outputs an operation signal according to the operation to the CPU . The operation unit herein is a keyboard having character keys numeral keys and other keys assigned to various functions or a pointing device such as mouse for example.

The display unit displays an image on a screen the image being based on a display control signal output from the CPU . The display unit may be a CRT Cathode Ray Tube LCD Liquid Crystal Display and the like.

The I F unit has a data network IC Integrated Circuit connectors and so forth all of them not illustrated and is connected to external devices and a communication network so as to communicate with each other. The I F unit may typically be a USB Universal Serial Bus network port of a computer for example or a network interface card NIC which allows connection with LAN Local Area Network WAN Wide Area Network or the Internet for example.

Next operations of the information device when detecting execution of malicious program code will be explained. In order to prevent execution of malicious program code in the information device it is necessary to insert a process for checking a malicious program code execution by detecting an API library function system call and so forth which are required for the execution of the malicious program code. In the information device of this embodiment detection of malicious code used for calling a predetermined library function and insertion of a process for checking illegality are realized by using hooks.

The hook process is a mechanism for enabling a user to insert his or her unique process at a specific position in any given program. In other words it is a mechanism used when the programmer who created the program code to be hooked and the programmer who created the program code that performs the hook process are different persons and where the source codes relevant to their program codes are not created by the same programmer. Accordingly the mechanism is used for modifying the functions or API Application Programming Interface of the OS or functions or APIs provided by the vendor or for adding arbitrary processes.

The hook process may be used also when the programmer himself or herself is able to modify the subprograms such as functions which are a target for checking. Note that for the case where the programmer himself or herself is able to modify the subprograms and he or she actually modified the subprograms so as to be checked for illegality upon execution of the subprograms it is no longer necessary to use the hook process and the existing functions and library can be used as safe functions and library.

First a model case for checking whether a malicious program code is executed or not by performing API hook process performing hook process on library function will be explained with reference to .

Hereinafter a hook process to be performed on a library function named WinExec provided by a vendor and a stack layout check process to be executed upon the library function being called will be shown as examples. Note that the following examples are similarly applied to the hook process performed on other library functions ExitProcess for example .

As illustrated in first the starting address of a function of WinExec is acquired step S . The acquisition of address of the function is enabled by calling the function provided from a vendor.

Next a small function temporary function for hooking execution of API is dynamically generated step S . The dynamically generated function is a function for calling the stack layout check process described later.

Next the top code of WinExec is rewritten and modified so as to enable execution of the function generated in step S step S .

By virtue of the hook process described above it is now capable of inserting a process of detecting a call of the subprogram code and checking any illegality in the information device . In general cases where a subprogram of the function is called a function called by a certain function is executed as it is. In contrast in the information device by performing the above described hook process which takes place before the subprogram code is called the stack layout check process may be executed upon calling of the subprogram code.

As illustrated in a StackWalk library is initialized step S . The StackWalk library is a function provided by a vendor which enables the stack trace. By incrementing or decrementing a position to be traced by using StackWalk it is now possible to sequentially acquire the return addresses stored in the stack area.

Next StackWalk is called to trace one stack back so as to sequentially call the stack frames in the stack area step S and whether the return address was correctly acquired or not after the tracing is determined step S .

If it is determined in step S that the return address is not correctly acquired step S NO it is assumed that the termination is normal and the execution of WinExec which is the target for checking is continued. A possible case which corresponds to this situation is such that the stack has been damaged by an unknown reason other than illegal access and thereby StackWalk does not properly operate. While the process in this embodiment is configured to terminate normally when the StackWalk does not operate correctly it is also possible to terminate the program or to output a dialog box on the display unit by which the user can confirm whether to terminate or continue the program even when the stack trace failed.

On the other hand when it was determined that the return address is correctly acquired step S YES the return address is judged whether it is the starting address of the function step S . The starting address of the function may be acquired by various known methods for example by referring to values preliminarily stored in the storage unit or by referring to an IAT Import Address Table which is an array for storing actual memory address of the function to be imported.

If the return address is not determined as the starting address step S NO whether the instruction located just before the return address is a CALL instruction or not is determined step S . The CALL instruction is an instruction for calling a subroutine and in step S it is determined whether the instruction located just before the destination address pointed by the return address is the call instruction.

If the return address is determined as being the CALL instruction step S YES whether there is any unchecked return address or not is determined step S .

If it is determined that there remains unchecked addresses step S YES the process goes back to step S and the next return address is traced.

If it is determined that there are no addresses remained unchecked step S NO it is assumed that the termination is normal and the execution of WinExec which is the target for checking is continued.

On the other hand if the return address is determined as the starting address step S YES or if the instruction was not determined as being the CALL instruction step S NO an attack such as an illegal access is detected and a dialog stating that the data processing is temporarily terminated in order to prevent execution of any malicious program code is displayed on the display unit step S and execution of the program is terminated step S .

In the stack layout check process described above the return to libc attack is detected in step S and step S. When the return to libc attack takes place there is a characteristic that the destination pointed by the return addresses falls on the starting address of the function. For the case of a normal program the destination pointed by the return addresses does not fall on the starting address of the function and the process thereafter continues for the rest of the function.

Further in a Return to libc attack wherein the program code stored in the information device is combined which is an application technique of the return to libc attack there is a characteristic that the instructions located just before the destinations pointed by the return addresses are not the CALL instructions. These two characteristics are not found when a normal program is executed. In the stack layout check process the return to libc attack is detected based on these two characteristics.

Next derivation patterns of the return to libc attack detectable by the stack layout check process will be explained. In the aforementioned stack layout check process the return to libc attack becomes detectable by checking the destinations pointed by the return addresses wherein the return to libc attack has various known attack patterns.

In the case shown in since the destination pointed by the return address does not fall on the starting address of the function the return to libc attack cannot be detected in step S but may be detected in step S by checking whether the instruction located just before the destination pointed by the return address is the CALL instruction or not.

In the case shown in since the destination pointed by the return address is not the starting address of the function the return to libc attack cannot be detected in step S. However the malicious attacker needs to find an instruction code jmp eax from other program code area and set the return address to the address where jmp eax is. In the return to libc attack the instruction just before the instruction code jmp eax is not the CALL instruction in most cases. Thus the return to libc attack can be detected in step S.

Next a return to libc attack which is run in Windows Operating System registered trademark this annotation will be omitted hereinafter will be described as an example and the timing when the information device of the present invention detects the return to libc attack will be described.

First an exemplary return to libc attack caused by executing a file created by the CPU will be explained. In this case the return to libc attack takes place using CreateFile WriteFile WinExec ExitProcess and so forth which are the functions provided by Windows. CreateFile is a function for creating files wherein name of the created file is used as an argument. WriteFile is a function for writing data into the file wherein a file handle which indicates a target where data is to be written data to be written data size and the like are used as arguments.

In the return to libc attack first a predetermined file is created using CreateFile and WriteFile The procedure herein is configured to execute the above created file using WinExec and to terminate the above created file by using ExitProcess .

There may be another case where an attack code of the return to libc attack prompts downloading of a malicious code through the Internet and the file is executed. For example first a malicious file is downloaded through the I F unit from the Internet using a function named URLDownloadTofile provided by Windows. The downloaded file is then executed using WinExec .

As described above according to the information device of the present invention the return to libc attack which is a technique of illegal access using buffer overflow can be prevented in a reliable and simple manner without depending on the CPU function.

Note that the description of the above described embodiments is given merely for exemplary purposes and is not intended to limit the invention to the embodiments. The configurations and operations in the above described embodiments may be modified as needed.

For example while the above description discloses the case where the storage unit and the ROM are used as the computer readable media for storing the program of the present invention the media is not limited to these examples. As other computer readable media portable recording media including non volatile memory such as flash memory and CD ROM can be applied. Further as a medium for providing the program data of the present invention through network lines connected to the I F unit carrier wave can also be applied.

The entire contents of disclosure of Japanese Patent Application No. 2009 107294 filed on Apr. 27 2009 including specifications claims diagrams and abstracts are incorporated hereinto as part of the present application.

The present invention is applicable in the fields of information devices including PC WS mobile phone and network appliances.

