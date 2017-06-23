---

title: Methods and systems to implement a physical device to differentiate amongst multiple virtual machines of a host computer system
abstract: Methods and systems to implement a physical device to differentiate amongst multiple virtual machines (VM) of a computer system. The device may include a wireless network interface controller. VM differentiation may be performed with respect to configuration controls and/or data traffic. VM differentiation may be performed based on VM-specific identifiers (VM IDs). VM IDs may be identified within host application programming interface (API) headers of incoming configuration controls and data packets, and/or may be looked-up based on VM-specific MAC addresses associated with data packets. VM IDs may be inserted in API headers of outgoing controls and/or data packets to permit a host computer system to forward the controls and/or packets to appropriate VMs. VM IDs may be used look-up VM-specific configuration parameters and connection information to reconfigure the physical device on a per VM basis. VM IDs may be used look-up VM-specific security information with which to process data packets.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08392625&OS=08392625&RS=08392625
owner: Intel Corporation
number: 08392625
owner_city: Santa Clara
owner_country: US
publication_date: 20101225
---
This application claims the benefit of U.S. Provisional Patent Application No. 61 358 671 filed Jun. 25 2010 titled Wireless Virtualization which is incorporated herein by reference in its entirety.

A computer system may include a virtual machine monitor VMM to host one or more guest operating systems.

The VMM may arbitrate access to resources of the computer system amongst the guest operating systems. The VMM may present a virtual interface or an abstraction of the resources to the guest operating systems. A guest operating system and corresponding virtualized resources and interfaces are referred to herein as a virtual machine VM .

A physical resource may include one or more configurable functions. For example a wireless network interface controller NIC may be configurable with respect to device initialization network scanning network access point selection channel selection connection establishment handover management security and power control.

Techniques have been developed to virtualize wired NICs including software based VMMs and NIC hardware virtualization support based on a single root I O virtualization SR IOV specification v1.0 promulgated by the Peripheral Component Interconnect Special Interest Group PCI SIG .

In the drawings the leftmost digit s of a reference number identifies the drawing in which the reference number first appears.

Disclosed herein are methods and systems to permit each of a plurality of virtual machines VMs to separately configure and access a physical resource or device and methods and systems to implement the physical device to differentiate amongst multiple VMs of a host computer system.

Physical device may include a device controller to configure one or more functions or features of physical device .

Physical device may include one or more of a variety of types of physical devices or resources. For example physical device may include a wireless transceiver and device controller may include a wireless network interface controller NIC . Physical device and device controller are not however limited to a wireless NIC.

Computer system may include one or more processors to provide a processor execution environment referred to herein as a host environment . Host environment may include a virtual machine monitor VMM to host one or more virtual machines VMs through 

Device controller may include another processor which may include a microcontroller to execute instructions or logic which may be provisioned in firmware.

Host environment may include a host device driver to interface between computer system and physical device . Host device driver may execute on processor outside of VMM .

VA system may be configured to permit each of VMs through to separately configure and access physical device .

VMs may each include an instance of a device driver to expose controllable functions of the physical device within each of VMs through . Device driver may be designed specifically for physical device and or device controller and may be provided by a manufacturer of physical device and or device controller . Device driver may be referred to herein as a native device driver.

VA system or portions thereof may be implemented within device controller and or within computer system . Within computer system one or more portions of VA system may be implemented within VMM and or outside of VMM such as within host device driver .

Where a portion of VA system is implemented within device controller device controller may be referred to herein as a virtualization augmented device controller.

Where a portion of I O interface system is implemented within host device driver host device driver may be referred to herein as a virtualization augmented host device driver.

Unified control engine may be configured to maintain VM specific parameters for each of VMs through and to selectively apply VM specific parameters to physical device . Selective application of VM specific parameters is functionally illustrated in with a multiplexer .

Parameters may include one or more of device configuration parameters and or connection information. Types of device configuration parameters and connection information may vary by physical device type.

Where physical device includes a wireless NIC for example configuration parameters may relate to one or more of 

The example configuration parameters listed above are provided for illustrative purposes and is not exhaustive. Methods and systems disclosed herein are not limited to the example listing of controllable features above.

Regarding connection information where physical device includes a wireless NIC connection information may include for example access point MAC address VM specific MAC address data rates supported by the access point channel that the access point operates on and or security keys specific to a connection or session.

Connection information may also include state information. Where physical device includes a wireless transceiver state information may include for example an association state and or a state of a rate scaling algorithm.

Connection information associated with a particular VM connection may be stored and or updated when access to physical device is transferred from the VM to another VM. The connection information may be re applied when the VM later accesses physical device .

Control module may be configured to coordinate transmit and receive messages between VMs and physical device and to permit each of VMs through to separately access physical device based on corresponding VM specific parameters . Control module may be configured to permit VMs through to separately access physical device in a time multiplexed fashion.

Control module or portions thereof may be implemented within host device driver and or within device controller such as with firmware embedded instructions or logic to execute on a microcontroller.

Wireless NIC may include a medium access controller MAC and a physical layer portion or device PHY to interface between MAC and a wireless transceiver. MAC may be reconfigurable to present a virtual instance of MAC to each of VMs through illustrated here as virtual MACs through each of which may be defined by corresponding VM specific device parameters .

Host wireless NIC driver may provide an interface between MAC and VMM illustrated here as a radio . Host wireless NIC driver may be configured to present a virtual instance of radio for each of VMs through illustrated here as virtual radios through which may be defined by corresponding VM specific configuration and context parameters.

Host wireless NIC driver may include a control module which may execute on processor outside of VMM . Control module may be configured to consolidate device configuration controls from VMs through to present a unified control interface to wireless NIC .

VMM may include a device model corresponding to wireless NIC and may be configured to expose virtual instances of the device model to wireless NIC drivers through illustrated here as device models through . The device model may include emulated peripheral component interconnect PCI functions.

Wireless NIC device drivers device models and host wireless NIC driver may be configured to permit VMs to access all or a subset of configurable functions of physical device .

In wireless NIC includes a virtual radio identifier or VR ID tag module and host wireless NIC driver includes a VR ID tag module . VR ID tag modules and are each configured to tag messages and controls sent between wireless NIC and host wireless NIC driver with appropriate VM specific VR ID tags.

MAC is further configured to process messages received from host wireless NIC driver with selected ones of virtual MACs through based on the associated VR ID tags.

Similarly host wireless NIC driver is further configured to process messages received from wireless NIC with selected ones of virtual radios through based on the associated VR ID tags.

Host wireless NIC driver further includes a VM ID tag module and VMM includes a VM ID tag module . VM ID tag modules and are each configured to tag messages and controls sent between host wireless NIC driver and VMM with appropriate VM ID tags.

Host wireless NIC driver is further configured to pass messages received from VMM through selected ones of virtual radios through based on the associated VM ID tags.

Similarly VMM is configured to pass messages received from host wireless NIC driver to selected ones of VMs through based on the associated VM ID tags.

At configuration controls directed to a physical device are received from a plurality of VMs through corresponding instances of a device driver that exposes controllable functions of the physical device within the VMs.

At VM specific configuration parameters and VM specific connection information are maintained for each of the VMs such as described in one or more examples herein.

At the physical device is reconfigured for each of the VMs with the corresponding VM specific configuration parameters and connection information such as described in one or more examples herein.

The receiving of configuration controls at the maintaining of VM specific configuration parameters and VM specific connection information at and the reconfiguring of the physical device at may be performed substantially outside of a VMM that hosts the VMs such as described in one or more examples herein.

The maintaining of VM specific configuration parameters and VM specific connection information at and the reconfiguring of the physical device at may be performed substantially within the physical device.

The physical device may include a wireless NIC and the reconfiguring at may include reconfiguring the wireless NIC for each of the plurality of VMs with respect to one or more of parameters described above.

The example configuration parameters listed above are provided for illustrative purposes. Method is not limited to the example listing of controllable features above.

Methods and systems to differentiate amongst VMs with respect to configuration controls to and from the VMs and with respect to data traffic are described below with reference to . The methods and systems are described with reference to a wireless NIC. The methods and systems are not however limited to a wireless NIC.

Host device driver may be configured to send transmit packets and configuration controls from VMs through to wireless NIC . Wireless NIC may be configured to send received packets and state feedback to host device driver for delivery to corresponding VMs through 

Transmit packets configuration controls received packets and state feedback may be tagged with appropriate VM identifiers VM IDs to permit wireless NIC and host device driver to handle and or process the packets controls and feedback on a per VM basis. VM IDs may relate directly to VMs and or to virtual radios such as described above with reference to .

VM ID tagging may be implemented with one or more of a plurality of techniques and combinations thereof.

For example host environment may include a host application program interface API to interface between wireless NIC and VMs through . The host API may be implemented within host device driver . The host API may be configured with to recognize a VM identifier VM ID field in host API headers. The VM ID header field may be accommodated by reserved bits of an existing or conventional API header. A number of bits used for the VM ID header field may be determined by the number of VMs to be supported.

Regarding state feedback wireless NIC may include a device initiated API call module to call to the host API with state feedback . Wireless NIC may further include a VM ID insert module to insert VM IDs in the host API VM ID header field of state feedback . This may permit host device driver to direct state feedback to appropriate VMs.

Regarding configuration controls device models within a VMM such as device models in may be configured to insert VM IDs into API control calls configuration controls issued from corresponding VMs. Wireless NIC may include a VM differentiator to receive configuration controls and to identify associated VMs from the API VM ID header fields.

Wireless NIC may be configured to handle and or process configuration controls on a per VM basis based on the associated VM IDs. Wireless NIC may include for example a per VM device initialization module to initialize a MAC and or a PHY on a per VM basis such as described further below. Wireless NIC may also include a per VM connection table to maintain per VM parameters such as described further below.

Wireless NIC may receive packets from one or more access points or transceivers which may be associated with one or more service set identifiers SSIDs . Each received packet may include a destination MAC address that is specific to one of VMs .

Wireless NIC may include a receive side VM ID look up module to look up VM IDs in per VM connection table based on MAC addresses of received packets .

Wireless NIC may further include a VM ID insert module to insert the identified VM IDs into API VM ID header fields of received packets such as described above with reference to VM ID insert module .

VM IDs of received packets may permit host device driver to pass received packets to appropriate VMs substantially without processing received packets .

Host environment may be configured to insert VM IDs in transmit packets such as described above with respect to configuration controls . In such a situation configuration parameters and connection information for transmit packets may be retrieved from per VM connection table based on the VM IDs.

Alternatively transmit packets may be received from host device driver without VM IDs. For example host device driver and or the host API may not be configured to insert VM IDs into API headers. To accommodate such a situation wireless NIC may include a transmit side VM ID look up module to look up VM IDs from per VM connection table based on VM specific MAC addresses contained within transmit packets such as described above with respect to receive side VM ID look up module .

Wireless NIC may include a per VM configuration module to retrieve VM specific configuration parameters and connection information from per VM connection table based on VM IDs identified by VMI ID look up module and to configure or reconfigure functions of wireless NIC for transmit packets based on the corresponding VM IDs.

Configuration controls may include device initialization controls from multiple VMs. Device initialization control may be directed to a PHY and or a MAC. Wireless NIC may include a per VM device initialization module to process device initialization controls and to avoid potential conflicting device initialization controls.

For PHY initialization initialization module may be configured to determine a current PHY state and operational channel. Initialization module may be further configured to initialize the PHY only when the PHY is not currently initialized. Where a PHY initialization command specifies a channel or mode other than a current operational channel or mode initialization module may evaluate one or more factors before proceeding. Factors may include whether the new channel or mode is supported by the device and any constraints that may be associated with the new channel or mode.

For MAC initialization initialization module may be configured to initiate a MAC instance for a particular VM when the VM first invokes or initiates a corresponding NIC driver. This may include configuring MAC filters for the virtual MAC with a MAC address of the VM in order to receive packets for the VM.

Per VM connection table may be configured to maintain VM specific configuration parameters and connection information including state information for each of multiple VMs or VM connections.

VM connection table may be configured to store connection information for a particular VM when access to wireless NIC is transferred from the VM to another VM and to re apply the connection information and corresponding configuration parameters when the VM later accesses wireless NIC .

VM connection table and or wireless NIC may include data structures with independent entry per connection to maintain or store per VM or per connection information in association with corresponding VM IDs. Wireless NIC may be configured to maintain e.g. add modify or delete the data structures with specifics associated with each VM. The data structures may include ucode data structures.

Per VM connection table may be configured to store VM specific security information for each VM or VM connection. Security information may include per VM encryption decryption techniques which may include for example one or more of temporal key integrity protocol TKIP and computer mode with cipher block chaining message authentication code protocol CCMP . Security information may include security keys and or indexes to security keys with which to decode received packets and or to encode transmit packets .

On the receive side security module may be configured to retrieve VM specific security decryption techniques and security keys from per VM connection table based on VM IDs of received packets and to decode received packets with the corresponding decryption techniques and keys. Alternatively decoding may be performed by computer system and security module may be configured to retrieve and forward VM specific security key indexes with corresponding received packets .

On the transmit side per VM configuration module may be configured to retrieve VM specific security encryption techniques and security keys from connection table based on VM IDs of transmit packets and to encode transmit packets with the corresponding encryption techniques and keys.

At configuration controls directed to a wireless NIC are received from a plurality of virtual machines VMs hosted by a computer system and for each configuration control one of the VMs is identified as a source of the configuration control.

At VM specific configuration parameters and device connection information are maintained by the NIC for each of the VMs.

At transmit packets are received from the VMs and for each of the transmit packets one of the VMs is identified as a source of the transmit packet and the wireless NIC is configured with the corresponding VM specific configuration parameters and with corresponding VM specific device connection information.

At packets are received from one or more wireless access points and for each received packet one of the VMs is identified as a destination VM and the received packet is forwarded to the computer system with a corresponding VM identifier.

At state feedback and received packets are sent to a computer system as API calls and for each of the API calls a VM identifier is inserted in a header field of the API call.

At configuration controls are received from the computer system as API calls and for each of the configuration controls one of the VMs are identified as a source of the configuration control from a VM identifier in the header field of the corresponding API call.

At a VM specific virtual MAC is initiated for each of a plurality of VMs. Each virtual MAC is configured with a corresponding VM specific MAC address.

At a reference is maintained between each of the VM specific MAC addresses and a corresponding VM identifier.

At a VM identifier is looked up for each received packet based on a destination MAC address of the received packet.

At a VM identifier is looked up for each transmit packet based on a VM specific MAC address of the transmit packet.

On the receive side when the VM identifier may be used to look up security information with which to decode the received packet. The received packet may be decrypted by the wireless NIC or may be sent to the computer system with a security key index such as described in one or more examples herein.

One or more features disclosed herein may be implemented in hardware software firmware and combinations thereof including discrete and integrated circuit logic application specific integrated circuit ASIC logic and microcontrollers and may be implemented as part of a domain specific integrated circuit package and or a combination of integrated circuit packages. The terms software code and instructions as used herein refers to a computer program product including a computer readable medium having computer program logic stored therein to cause a computer system to perform one or more functions in response thereto.

In the example of computer system includes processor to execute computer program product logic hereinafter logic . Processor may represent multiple processors.

Computer system may include one or more of memory cache registers and storage together illustrated here as memory . Memory may include a computer program product including a computer readable medium having computer program logic or instructions stored thereon to cause processor to perform one or more functions in response thereto. Example logic is described below.

Memory may include data to be used by processor in executing logic and or generated by processor in response to execution of logic .

Logic may include operating system logic to cause processor to provide an operating environment for application logic .

Logic may include VMM logic to cause processor to execute operating system logic within a virtual machine.

Logic may include virtualization augmented host device driver logic to cause processor to interface between physical device and a virtual machine monitor such as described in one or more examples herein.

Host device driver logic may include logic to cause processor to configure multiple VM specific virtual radios and data may include corresponding VM specific virtual radio configuration and context parameters .

Computer system may include a communications infrastructure to interface amongst devices within computer system and to communicate with physical device .

Physical device may include one or more computer instruction processing units illustrated here as a controller to execute computer program product logic. Controller may include a micro controller.

Physical device may include one or more of memory cache registers and storage together referred to hereinafter memory . Memory may include a computer program product including a computer readable medium having computer program logic stored thereon to cause controller to perform one or more functions in response thereto. Logic may be provisioned in firmware and may be copied to memory at run time. Example logic is disclosed below.

Memory may include data to be used by controller in executing logic and or generated by controller in response to execution of logic .

Logic may include physical device logic to cause controller to maintain VM specific parameters for each of multiple VMs of computer system and to reconfigure and physical device with VM specific parameters such as described in one or more examples herein.

Physical device logic may include virtualization augmented wireless NIC logic to cause controller to perform as a virtualization augmented wireless NIC such as described in one or more examples above.

Methods and systems are disclosed herein with the aid of functional building blocks illustrating the functions features and relationships thereof. At least some of the boundaries of these functional building blocks have been arbitrarily defined herein for the convenience of the description. Alternate boundaries may be defined so long as the specified functions and relationships thereof are appropriately performed.

While various embodiments are disclosed herein it should be understood that they have been presented by way of example only and not limitation. It will be apparent to persons skilled in the relevant art that various changes in form and detail may be made therein without departing from the spirit and scope of the methods and systems disclosed herein. Thus the breadth and scope of the claims should not be limited by any of the example embodiments disclosed herein.

