---

title: Method and apparatus for monitoring quality of service of network
abstract: When capturing packets at the application level for the purpose of QoS monitoring, a QoS monitor needs to be bound to the same IP address and port as those of a media player. However, due to the unicast duplicate binding problem, a unicast packet captured by the QoS monitor will not be received by the media player, which means the QoS monitor have affected the operation of the media player. The present invention provides a solution to make the QoS monitor, upon the receipt of a unicast packet, forward the packet to the socket of the media player. In order to guarantee that the forwarded packet can be received by the socket of the media player, the QoS monitor needs to keep the port unchanged and replace the destination IP address with the local host address (127.0.0.1). According to the invention, the QoS monitor can sniff the media player without interference to the normal operation of the media player.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09276975&OS=09276975&RS=09276975
owner: Thomson Licensing
number: 09276975
owner_city: Issy-les-Moulineaux
owner_country: FR
publication_date: 20100324
---
This application claims the benefit under 35 U.S.C. 365 of International Application PCT CN2010 000362 filed Mar. 24 2010 which was published in accordance with PCT Article 21 2 on Sep. 29 2011 in English.

The present invention relates to method and apparatus for monitoring quality of service QoS of network.

In a TCP IP communication network a session between two applications on different hosts needs to be established for a communication therebetween which is usually composed of source IP address and port as well as destination IP address and port. When a host is created for a specific session a host is a kind of application programming interface through which the application can access TCP IP protocol stack to implement inter application communication packets in the session can be received or sent through it.

For a TCP IP network QoS monitor at an application level it is a general idea to bind the socket of a sniffing application of the monitor to the same destination IP address and port as those of an application to be monitored.

SO REUSEADDR is one of the generic socket options which allows completely duplicate bindings if a pair of IP address and port has already been bound to one socket then the same pair can be bound to another socket if the transport protocol support this feature. Normally this feature is supported only for UDP User Datagram Protocol sockets.

This feature is used in multicasting to allow one or more applications to run multiple times on the same host simultaneously. When a UDP datagram which is destined for either a broadcast IP address or a multicast IP address arrives every bound socket of the multiple applications is able to receive a copy of the datagram. However a datagram which is destined for a unicast address can be delivered to only one socket. If there are multiple sockets that match a unicast datagram the result of which socket will receive the datagram is implementation dependent. That is to say among the bound sockets in unicast sessions only one indefinite socket can receive the unicast packets. This is called the unicast duplicate binding problem UDBP .

According to one aspect of the invention a communication method of two socket bound applications in conformity with TCP IP protocol is provided wherein the sockets of the two applications are bound to the same IP address and port. The method comprising at the level of either application the steps of upon the detection of a unicast packet received in its socket replacing the destination IP address of the unicast packet with the local host address 127.0.0.1 and forwarding the unicast packet.

According to another aspect of the invention a Quality of Service monitor for a media player is provided. The socket of the Quality of Service monitor is bound to that of the media player for capturing media plackets sent to the media player. The monitor comprises means for detecting whether a captured media packet is a unicast one and means for replacing the destination IP address of the captured unicast media packet with the local host address 127.0.0.1 and forwarding the packet.

In the following description various aspects of an embodiment of the present invention will be described. For the purpose of explanation specific configurations and details are set forth in order to provide a thorough understanding. However it will also be apparent to one skilled in the art that the present invention may be practiced without the specific details present herein.

To improve the accuracy of QoE Quality of Experience assessment of media applications or services the QoS Quality of Service of a communication network needs to be monitored or measured. There are some known network QoS measurement methods all of which need to sniff the interested packets. Then the captured packets can be traced and analyzed to get real time QoS metrics such as PLR Packet Loss Rate PLF Packet Burst Loss Frequency etc.

Media packets can be captured at different layers in TCP IP protocol stack. For example raw packets can be captured at the data link layer by BPF BSD Berkeley Software Distribution Packet Filter . However according to an architectural principle known as Application Level Framing ALF which is based on a concept that applications understand their own needs better it is preferable to sniff media packets at the application level.

When capturing packets at the application level for the purpose of QoS monitoring a QoS monitor needs to be bound to the same IP address and port as those of a media player. In this case it is important that the bound QoS monitor should not interfere with the operation of the media player.

However due to the above described UDBP the media player can play a multicast session normally when the QoS monitor is sniffing while it is not the case for a unicast session. This is shown respectively in . is an exemplary diagram showing the internal operating mechanism of a multicast duplicate binding of the media player and the QoS monitor. As shown in when a packet arrives the media player and the QoS monitor will gain a copy of the packet separately. is an exemplary diagram showing the internal operating mechanism of a unicast duplicate binding of the media player and the QoS monitor. As shown in only one of the bound devices the QoS monitor or the media player can receive a unicast packet. That is a unicast packet captured by the QoS monitor will not be received by the media player which means the QoS monitor has affected the operation of the media player.

In view of the above problem a solution is provided to make the QoS monitor upon the receipt of a unicast packet forward the packet to the socket of the media player. is an exemplary diagram showing a QoS monitoring process according to an embodiment of the invention. As show in when the QoS monitor detects that a unicast packet is received by its socket master it will forward this unicast packet to the bound socket slave of the media player. In order to guarantee that the forwarded packet can be received by the socket of the media player the QoS monitor needs to keep the port unchanged and replace the destination IP address of the packet with the local host address 127.0.0.1 . If the destination IP address is used the forwarded packet will be received again by the QoS monitor itself rather than by the socket of the media player.

Next a process of a QoS monitor for sniffing a media player at the application level according to an embodiment of the invention will be described in detail.

In order to monitor media packets of a media player a QoS monitor needs to bind its socket to the same destination IP address and port as the media player. is a flow chart showing the process of creating the duplicate binding socket for the QoS monitor.

As shown in at the step S the QoS monitor creates a datagram socket by calling socket AF INET SOCK DGRAM IPPROTO UDP which returns a socket ID for other socket functions to refer to.

Next the QoS monitor sets receiver buffer size at the step S and enables reuse of session IP and port at the step S by setsocketopt call with arguments SO RCVBUF and SO REUSEADDR respectively.

Then at the step S the QoS monitor binds its socket to the same destination IP address and port as the media player by bind call.

In current multimedia communication normally audio and video packets are transmitted in different sessions with different ports. Therefore the QoS monitor will receives audio and video packets respectively by its different master sockets and forward if needed the audio and video packets to respective slave sockets of the media player. This process is shown in .

As shown in the QoS monitor firstly creates RTP Real time Transport Protocol header log file and all QoS metrics log files at the step S.

Then the QoS monitor determines at the step S whether a unicast packet arrives by monitoring this socket using select call. If the result is Yes the QoS monitor will determine at the step S whether a video packet is received via the type of socket through which this packet arrived. It can be appreciated by a person skilled in the art that if the result is No which means a multicast or broadcast packet is received the normal process instead of the method of the embodiment of the invention will be applied.

If the result of the step S is Yes at the step S the monitor will replace the destination IP address of the unicast video packet with the local host address 127.0.0.1 and forward the packet to the video socket of the media player. If the result of the step S is No which means that an audio packet is received at the step S the QoS monitor will replace the destination IP address of the unicast audio packet with the local host address 127.0.0.1 and forward the packet to the audio socket of the media player.

Since the QoS monitor in the embodiment is used to evaluate the video QoS of the media player for the captured video packets the QoS monitor will analyze the packet to update the statistics data of QoS metrics. Specifically at the step S the monitor records RTP header and arrival timestamp into log file and at the step S it uses sequence number in RTP header to determine the loss of packet and accumulate statistical data for example into statData which is a data structure for accumulating statistical data including PLR PLL PLF and PDR.

In this embodiment the QoS monitor directly forwards the received unicast audio packets to audio slave socket. However it can be appreciated by a person skilled in the art that audio packets can also be analyzed if needed.

As shown in if there is an error in any one of the steps S S S and S the RTP header log file will be closed at the step S.

The principle of the invention was described with reference to a QoS monitor of a media player. However it can be appreciated by a person skilled in the art that the invention can be applied to all two bound applications for purpose of overcoming the unicast duplicate binding problem as described above.

It is to be understood that numerous modifications may be made to the illustrative embodiments and that other arrangements may be devised without departing from the spirit and scope of the present invention as defined by the appended claims.

