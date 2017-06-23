---

title: Executing soft reset for intelligent terminal in abnormal instruction state and hard reset for intelligent terminal in dead halt state
abstract: The disclosure discloses a method for resetting an intelligent terminal, including: receiving a reset instruction input by a user after a receiving state of reset instructions is started; determining whether the reset instruction is valid, determining a current running state of the intelligent terminal when the received reset instruction is valid, and triggering a reset of the intelligent terminal when the intelligent terminal is in a dead halt state or an abnormal instruction state. The disclosure further discloses a device for resetting an intelligent terminal. The disclosure can perform a soft reset of the intelligent terminal quickly, conveniently and securely, thereby greatly avoiding the instable work state caused by disassembling battery and avoiding the reset misoperation caused by the resetting of the existing single function key.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08874886&OS=08874886&RS=08874886
owner: ZTE Corporation
number: 08874886
owner_city: Shenzhen
owner_country: CN
publication_date: 20100331
---
The disclosure relates to the technology of resetting an intelligent terminal and in particular to a method and device for resetting an intelligent terminal.

Due to the complexity of a system and the diversification of application programs in the usage process an intelligent terminal is getting closer to a daily used personal computer. In the usual usage of an intelligent terminal people often flash and upgrade the intelligent terminal and install various small application softwares in the intelligent terminal particularly game players will frequently install various new mini games however due to the problems such as diversification of terminal models operating systems and platforms of intelligent terminals diversification of radio access device interfaces compatibility of games and the like turning off turning on starting and resetting an intelligent terminal are the more common operations. Taking the most commonly used mobile phone in intelligent terminals as example 

the common resetting methods of a mobile phone are as follows 1 normally turning on and turning off that is pressing the power key for a few seconds to realize the resetting and restarting of the mobile phone 2 hard resetting that is entering into a boot interface in the cooperation of the function key and the power key and restoring the factory settings by inputting the initial resetting password 3 soft starting that is pressing the resetting hole in the terminal for a few seconds by using a sharp object to start the terminal.

In case of the non fatal dead halt of an intelligent terminal in a normal operation the intelligent terminal can be reset and restarted by the power key however if the intelligent terminal encounters dead halt invalid soft reset exceptions of a flashing process and the like it is necessary to restore the intelligent terminal system by hard starting.

If an intelligent terminal has been configured to a long time the registry will be damaged due to junk files and some third party softwares usually installed which makes the intelligent terminal respond slowly stop responding or be dead halt. If an intelligent terminal operates much slowly or some program operates abnormally even a dead halt of the intelligent terminal occurs it is generally required to solve these problems by soft resetting. After some programs are installed soft resetting may also be needed. Meanwhile in the usual usage the intelligent terminal further needs to be reset by soft resetting at intervals so as to clarify the intelligent terminal system and smoothen the operation program.

 1 directly disassembling battery to power off to realize soft starting the defects of this method are as follows sudden power off of an intelligent terminal will result in loss of data being edited and sudden loss of the latest address list and short messages in memory and an abnormal turn off and power off will result in sudden interruption of current resulting in that the terminal cannot be turned on due to permanent damage of partial devices in the terminal 

 2 pressing the resetting hole for a few seconds by using a sharp object to realize soft resetting the defects of this method are as follows it is inconvenient to perform the operation and an extremely sharp and thin tool is needed some resetting holes are arranged in the terminal battery groove thus it is necessary to pull out the battery before resetting the setting of a resetting hole in the intelligent terminal not only influences the appearance of intelligent terminal but also increases cost of opening the resetting hole and

 3 realizing soft resetting by pressing a certain function key or an assemblage of two function keys for a long time the defects of this method are as follows a single function key is very easy to cause a misoperation although an assemblage of two function keys may reduce possibility of misoperation misoperation still be easily caused when a large area of the keyboard is pressed and it is not as convenient as the soft starting in a normal mode.

In view of the problems above the main object of the disclosure is to provide a method and device for resetting an intelligent terminal which are greatly convenient for the resetting of the intelligent terminal.

In order to realize the above object the technical solution of the disclosure is realized as follows.

receiving a reset instruction input by a user after a receiving state of reset instructions is started 

determining whether the reset instruction is valid determining a current running state of the intelligent terminal when the received reset instruction is valid and triggering a reset of the intelligent terminal when the intelligent terminal is in a dead halt state or an abnormal instruction state.

triggering a hard reset of the intelligent terminal when the intelligent terminal is in a dead halt state and

triggering a soft reset of the intelligent terminal when the intelligent terminal is in an abnormal instruction state.

Preferably the reset instruction may be an assemblage sequence of keyboard keys of the intelligent terminal.

starting by the intelligent terminal the receiving state of reset instructions when a duration of the reset starting key being pressed reaches a set threshold.

executing no reset instruction when the reset instruction is valid and the current running state of the intelligent terminal is a normal instruction state.

A device for resetting an intelligent terminal including a starting unit a receiving unit a determining unit a determination unit and a resetting unit wherein

the starting unit is configured to start a receiving state of reset instructions of the intelligent terminal 

the determining unit is configured to determining whether the reset instruction is valid and trigger the determination unit when the reset instruction is valid 

the determination unit is configured to determine a current running state of the intelligent terminal and trigger the resetting unit when the intelligent terminal is in a dead halt state or an abnormal instruction state and

Preferably the resetting unit may trigger a hard reset of the intelligent terminal when the determination unit determines that the intelligent terminal is in a dead halt state and

the resetting unit may trigger a soft reset of the intelligent terminal when the determination unit determines that the intelligent terminal is in an abnormal instruction state.

Preferably the reset instruction may be a assemblage sequence of keyboard keys of the intelligent terminal.

wherein when a duration of the reset starting key being pressed reaches a set threshold the starting unit starts the receiving state of reset instructions of the intelligent terminal.

Preferably the resetting unit may execute no reset instruction when the determining unit determines that the reset instruction is valid and the determination unit determines that the current running state of the intelligent terminal is a normal instruction state.

In the disclosure a reset starting key is set on the keyboard of an intelligent terminal the receiving state of reset instructions of the intelligent terminal is started by pressing the reset starting key for a long time a determining is performed after a reset instruction input by a user is received the current state of the intelligent terminal is determined after the reset instruction is determined to be valid and then a reset operation is performed according to the state of the intelligent terminal. The disclosure can perform a soft reset of the intelligent terminal quickly conveniently and securely thereby greatly avoiding the instable work state caused by disassembling battery and avoiding the reset misoperation caused by the resetting of the existing single function key.

The basic principle of the disclosure is that a reset starting key is set on the keyboard of an intelligent terminal the receiving state of reset instructions of the intelligent terminal is started by pressing the reset starting key for a long time a determining is performed after a reset instruction input by a user is received the current state of the intelligent terminal is determined after the reset instruction is determined to be valid and then a reset operation is performed according to the state of the intelligent terminal.

Wherein when the determination unit determines that the intelligent terminal is in a dead halt state currently the resetting unit triggers a hard reset of the intelligent terminal when the determination unit determines that the intelligent terminal is in an abnormal instruction state the resetting unit triggers a soft reset of the intelligent terminal.

The reset instruction above is an assemblage sequence of the keyboard keys of the intelligent terminal. The reset instruction can be either a key assemblage of letter keys such as adgj ajtwp and the like or a key assemblage of number keys such as 12345 101001 and the like the length and the assemblage mode of the above mentioned reset instruction can be set arbitrarily.

As shown in the device for resetting the intelligent terminal according to the disclosure may further comprise a setting unit configured to set a key of the intelligent terminal as a reset starting key when a duration of the reset starting key being pressed reaches a set threshold the starting unit starts the receiving state of reset instructions of the intelligent terminal.

the reset instruction input module is connected with the sequence detector and is configured to complete the input of the reset instruction here the reset instruction is realized by an assemblage of corresponding keys on the intelligent terminal keyboard specifically the enabling or disabling of the receiving state of reset instructions is realized by pressing a control key for a long time when the control key is pressed for a set period of time the receiving state of reset instructions of the intelligent terminal is started it is indicated that high level is valid and the sequence code input at this moment is valid when the control key is pressed again for a set period of time the receiving state of reset instructions of the intelligent terminal is disabled it is indicated that low level is invalid and the sequence code input at this moment is invalid. Or the enabling or disabling of the receiving state of reset instructions is realized by pressing down or non pressing down of a control key when the control key is pressed down to be in a pressing down state the receiving state of reset instructions of the intelligent terminal is started it is indicated that high level is valid and the sequence code input at this moment is valid when the control key is pressed again to be in a non pressing down state the receiving state of reset instructions of the intelligent terminal is disabled it is indicated that low level is invalid and the sequence code input at this moment is invalid. The input mode of the reset instruction according to the disclosure can prevent a user from entering into a soft reset program by mistake when the input information and dialed number are coincidentally the same as the reset instruction. The reset instruction is an assemblage sequence of the keyboard keys of the intelligent terminal. The reset instruction may be either a key assemblage of letter keys such as adgj ajtwp and the like or the reset instruction may be a key assemblage of number keys such as 12345 101001 and the like the length and the assemblage mode of the above reset instruction can be set arbitrarily.

The sequence detector is connected with the mode selecting module and is configured to complete detection of a keyboard sequence code input by a user that is detecting whether the sequence code input by a user is a reset instruction. The process of detecting the sequence code is as follows when the soft reset instruction is set as 1010 the detector first detects the first instruction and if the first instruction is 1 the detector continues to detect the second sequence otherwise the detector outputs a high resistance Z when detecting that the second sequence is 0 the detector continues to detect the third sequence otherwise the detector outputs a high resistance Z when detecting that the third sequence is 1 the detector continues to detect the is fourth sequence otherwise the detector outputs a high resistance Z when detecting that the fourth sequence is 0 the detector outputs a low level 0 to the mode selecting module and then selects the soft reset. Likewise when the hard reset instruction is set as 0101 in the condition that the enabling of key is valid when the sequence detector detects this sequence according to the rules above the detector outputs a high level 1 to the mode selecting module and then selects the hard reset.

The soft reset enabling module and the hard reset enabling module are connected with the mode selecting module and are configured to output different reset valid signals RST N and RST N corresponding to different inputting modes. The reset enabling signal is of high level at the beginning when it is detected that a user needs to perform a reset operation a low level pulse is generated immediately and lasts for three clock periods then the reset enabling signal is recovered to high level state.

The reset management module is configured to manage the reset work mode of the intelligent terminal when the intelligent terminal works normally the reset management module detects that other modules are in a sleep state even if there is a misoperation during inputting it is unable to activate the soft reset output enabling module to work when the intelligent terminal is in a dead halt state or an abnormal instruction state the soft reset output enabling module is activated immediately to enter into the quick soft reset state. In this way not only faulty reset can be prevented but also energy consuming caused by soft reset of system can be saved to lengthen the standby time of the system.

The baseband chip is connected with the reset module and is communicated with the reset module through a General Purpose Input Output GPIO interface when the GPIO RST pin of the baseband chip receives a reset low level the baseband chip is reset the baseband chip restores the kernel ARM and DSP chip to an initial program line then the system reloads to operate.

The reset display module is connected with the baseband chip when the system is reset successfully the baseband chip outputs a signal level to a turn on indictor lamp of the intelligent terminal and lighting of the indicator lamp indicates that reset is successfully.

The FLASH memory module is connected with the baseband chip when the system receives a hard reset instruction an Application Programming Interface API program is called to clear problematic programs in the intelligent terminal and erase the third party softwares and problematic programs in the FLASH chip and then the intelligent terminal restores the security system.

The power management module is connected with all other modules and is configured to supply voltage required for the normal operation of the system. Meanwhile when the intelligent terminal is in an powered on reset state the power management module receives a reset low level signal PS HOLD from the baseband chip and outputs a reset enabling signal to the resetting module to complete the powering on and resetting process.

step the type of a dead halt is determined in accordance with the response to a user s key pressing when the intelligent terminal is in an abnormal work state step is executed when the intelligent terminal is in a complete dead halt state with no response step is executed and step can be executed when the user starts the receiving state of reset instructions of the intelligent terminal or the current running state of the intelligent terminal can be determined after the user inputs a reset instruction and the reset instruction is confirmed to be correct those skilled in the art should understand that the above execution result corresponds to the execution mode 

step in the cooperation of valid enabling of the control key the user inputs a soft reset password sequence sequentially that is when being in the reset instruction receiving state the intelligent terminal receives the reset instruction input by the user 

step in the condition that control key is valid a sequence detecting module is of the intelligent terminal detects whether the input password sequence is consistent with the originally stored soft reset sequence if yes step is executed otherwise step is executed 

step the intelligent terminal detects that the input sequence is wrong the reset management module resets each module relating to resetting to wait for the inputting of the next instruction the flow is ended 

step in the cooperation of valid enabling of control key the user inputs a hard reset password sequence sequentially and then step is executed 

step in the condition that control key is valid a sequence detector of the intelligent terminal detects whether the input password sequence is consistent with the original hard reset sequence if yes step is executed otherwise step is executed 

step the intelligent terminal detects that the input sequence is wrong the reset management module resets each module relating to resetting to wait for the inputting of the next instruction the flow is ended 

step the mode selecting module detects the output signal of the sequence detector if the output signal is a soft reset signal step is executed and if the output signal is a hard reset signal step is executed 

step after receiving an input enabling signal the soft reset enabling output module generates a low level reset signal RST N and sends the low level reset signal RST N to the baseband processor chip and then step is executed 

step when the GPIO RST pin of the baseband chip receives a soft reset low level the baseband chip is reset the baseband chip restores the kernel ARM and DSP chip to an initial program line and the system reloads to operate and then step is executed 

step after receiving an input enabling signal the hard reset enabling output module generates a low level reset signal RST N and sends the low level reset signal RST N to the baseband processor chip and then step is executed 

step when the system receives a hard reset instruction an API program is called to clear the problematic programs in the intelligent terminal and erase the third party softwares and problematic programs in the FLASH chip and the intelligent terminal restores the security system and then step is executed 

step after the reset operation is successful the reset management module feeds back a signal to the baseband chip and then the baseband chip outputs a signal to the reset display module to complete this reset process and then step is executed and

step the reset management module resets each module relating to resetting to restore to the initial work state and wait for the next reset signal the flow is ended.

The above are only the preferred embodiments of the disclosure and are not intended to limit the protection scope of the disclosure.

