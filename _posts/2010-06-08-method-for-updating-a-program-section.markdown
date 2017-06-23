---

title: Method for updating a program section
abstract: A method for updating a program section is disclosed; the method is used for an electronic system. The electronic system comprises a control unit and a storage device; the control unit is electrically connected with the storage device; the storage device comprises a program section; the program section comprises an application section and a boot section; the application section comprises a first bootloader and application information, wherein the first bootloader comprises a first driver. The method comprises the following steps of: connecting a data source device, wherein the data source device comprises update data; determining whether the first driver is able to drive the data source device or not; and if the first driver is able to drive the data source device, the first driver performs an updating procedure according to the update data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08316362&OS=08316362&RS=08316362
owner: Wistron Neweb Corp.
number: 08316362
owner_city: Taipei Hsien
owner_country: TW
publication_date: 20100608
---
The present invention relates to a method for updating a program section and more particularly to a program section updating method which allows the bootloader to drive multiple data source devices.

Due to the boot section storage space limitations of a micro controller unit electronic products nowadays are limited in the number of functions and drivers that can be incorporated in the boot section.

However the storage space of boot section is very limited usually a few Kbytes therefore boot section can store very little data. For example when the user needs to update application section of an electronic device but the size of the USB device driver or other system driver is larger than the remaining storage space on boot section then the device cannot be updated through the USB device or through a network. As a result the user needs to return the electronic device to the maintenance shop for further service. This is very inconvenient for a user.

Moreover the storage of application section is often allocated with a larger space usually a few Mbytes but the space is not fully utilized. Therefore a new method for updating a program section by exploiting the storage space of the application section is needed in order to overcome the problem caused by the limited storage space of the boot section.

The object of the present invention is to provide a method for updating a program section more particularly by exploiting the storage space of the application section such that a bootloader is able to drive multiple data source devices.

To achieve the above objective a method for updating a program section is provided by the present invention for an electronic system. The electronic system comprises a control unit and a storage device the control unit is electrically connected with the storage device the storage device comprises a program section the program section comprises an application section and a boot section the application comprises a first bootloader and application information wherein the first bootloader comprises instructions to execute a first driver.

The method comprises the following steps connecting a data source device wherein the data source device comprises update data determining whether the first driver is able to drive the data source device or not and if the first driver is able to drive the data source device the first driver performs an updating procedure according to the update data.

To achieve the above objective another method for updating a program section is provided by the present invention for an electronic system. The electronic system comprises a control unit and a storage device the control unit is electrically connected with the storage device the storage device comprises a program section the program section comprises an application section and a boot section the boot section comprises an initial bootloader the application comprises a first bootloader and application information wherein the first bootloader comprises instructions to execute a first driver.

The method comprises the following steps connecting to a data source device wherein the data source device comprises update data determining whether the initial driver or the first driver is able to drive the data source device or not and if one of the drivers is able to drive the data source device then loading the update information and performing an updating procedure.

The advantages and innovative features of the invention will become more apparent from the following preferred embodiments.

Refer to to which show the first embodiment for the method of updating a program section of the present invention. Take note that although the method is described using an electronic system for example a satellite radio with a micro controller unit as shown in the method for updating a program section of the present invention is not limited to electronic system .

In one embodiment of the present invention as shown in the electronic system comprises a control unit a storage device and a buffer memory . The control unit is electrically connected with the storage device and the buffer memory . The storage device comprises a program section .

As shown in the program section comprises an application section and a boot section the application section comprises a first bootloader and the application information . On the program section the application section ends at an interrupt vector region .

The first bootloader comprises instructions to execute at least a first driver . Please note that In another embodiment as shown in the first bootloader is not limited to executing exclusively on the first driver . The first bootloader can include instructions to execute a second driver and a third driver

As shown in the boot section comprises an initial bootloader the initial bootloader comprises a boot vector a write flash application programming interface write flash API an initial driver and a main program . In one embodiment of the present invention the write flash API is used to control either the first driver or the initial driver to drive the data source device and then to store the information from the data source into the buffer memory . Please note that the initial bootloader does not necessarily require a boot vector component. In one embodiment a boot vector can exist independently at the boot section.

In one embodiment of the present invention the electronic system is demonstrated using a Micro Controller Unit MCU of a satellite radio but the present invention is not limited to this unit. In one embodiment of the present invention the storage device is demonstrated using a flash memory but the present invention is not limited in using a flash memory. Please note that the buffer memory is not an essential component in the electronic system of the present invention the buffer memory can be a separate component connected to the electronic system externally.

The following passage explains the method for updating a program section with the steps of the first embodiment.

As shown in the first embodiment of the present invention begins with step S connecting to the data source device.

In one embodiment of the present invention the electronic system is followed by a power on or a reset procedure after electronic system is electrically connected with data source device as shown in . Data source device comprises the update data. The update data is used to renew the application information . In one embodiment the data source device is demonstrated using a Universal Serial Bus USB device but the present invention is not limited to a USB device. For example the data source device can be a Universal Asynchronous Receiver Transmitter UART or a memory card such as a secure digital memory card .

Next the process continues with step S determining whether the initial driver is able to drive the data source device.

In one embodiment after the electronic system is powered on or reset the main program then determines whether the initial driver is able to drive the data source device . More particularly the main program is used to determine whether the initial driver is able to drive the data source device and retrieve the update data format from the device.

Please take note that step S is not a necessary step in the present invention. In another embodiment as shown in the initial bootloader of the program section does not contain an initial driver therefore step S can be omitted and step S can then be directly executed after step S.

As shown in if the main program determines that the initial driver is able to drive the data source device it then proceeds to step S using the initial driver to perform an updating procedure according to the update data. If the main program determines that initial driver cannot drive the data source device it then proceeds to step S determining whether the first driver is able to drive the data source device.

If main program determines that the first driver is able to drive the data source device it then proceeds to step S using the first driver to perform an updating procedure according to the update data.

With the above method of updating a program section and through the utilization of the application section storage space the bootloader is able to drive more data source devices. Furthermore the sequence of determining which driver is to be used in the boot section or the application section for driving the data source device can be assigned arbitrarily it is not necessary to follow or be limited to the sequence of the present design.

In one embodiment the main program is not only limited to being located in the initial bootloader. For example the main program can also be allocated in the first bootloader but the present invention is not limited to this design.

Refer to and . In one embodiment the updating procedure performed through the first driver comprises the following steps.

Please note that if the update data exceeds the storage space of buffer memory then the first driver will only send partial update data to the buffer memory .

In one embodiment the write flash API sets the application section as a writable but non executable state.

In one embodiment the application section cannot execute the program while the application section is being written therefore the write flash API should be used to write the update data which is stored in the buffer memory into the application section during the data updating process.

In one embodiment the write flash API will set application section as an executable and non writable state after the data which is stored in the buffer memory is written to application section .

If the main program determines that the initial driver is able to drive the data source device it then proceeds with step S using the initial driver to perform an updating procedure according to the update data.

In one embodiment as shown in initial driver retrieves the update data and sends the update data to the buffer memory . Please note that if the update data exceeds the storage space of the buffer memory then initial driver will only send partial update data to the buffer memory .

Next the write flash API sets the application section as a writable but non executable state after which the write flash API writes the update data which is stored in buffer memory into the application section . If the update data is not completely transferred to the buffer memory then the initial driver will continue transferring the remaining update data into the buffer memory and the write flash API will write the update data which is stored in the buffer memory into the application section . After the update data is completely updated the write flash API will set the application section into an executable and non writable state. In one embodiment the write flash API writes the update data which is stored in buffer memory into the application information but the present invention is not limited to this process.

Take note that experienced users with knowledge in this field can alter the sequence of the above steps or execute some of the steps simultaneously to achieve the same result.

Next refer to and which illustrate a second embodiment showing the method for updating a program section.

The difference between the second embodiment and the first embodiment lies within the main program . In this embodiment the main program can be used to determine simultaneously whether the initial driver or the first driver is able to drive the data source device .

The embodiment of connecting to the data source device has been explained above and thus will not be described further.

Next proceed with step S determining whether the initial driver or the first driver is able to drive the data source device.

In one embodiment the main program is used to determine whether the initial driver or the first driver is able to drive the data source device but the present invention is not limited to this configuration. For example as shown in if the first bootloader further comprises executing a second driver and executing a third driver then the main program is used to determine whether the initial driver the first driver the second driver or the third driver is able to drive the data source device.

As shown in if either the initial driver or the first driver is able to drive the data source device then the method proceeds to step S retrieving the update data and performing the updating procedures.

Take note that the data updating procedures initiated by the first driver or the initial driver are described in the first embodiment thus they will not be further described.

Although the present invention has been explained in relation to its preferred embodiment it is also of vital importance to acknowledge that many other possible modifications and variations can be made without departing from the spirit and scope of the invention as hereinafter claimed.

