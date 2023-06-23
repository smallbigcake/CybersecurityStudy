# Communication and Network Security

## ASSESS AND IMPLEMENT SECURE DESIGN PRINCIPLES IN NETWORK ARCHITECTURES

Recall that there are many different types of networks:
* Local area network (LAN): A local area network is a group of devices that communicate on a single localized network, typically (but not always) within the same building. Office networks are common examples of LANs.
* Metropolitan area network (MAN): A metropolitan area network is a connection of multiple LANs throughout an entire city. An example would be a citywide Wi-Fi network.
* Wide area network (WAN): A wide area network is a larger network that covers a broader space than a LAN, typically larger than most MANs. The internet is the largest, most commonly used WAN.
* Personal area network (PAN): A personal area network connects devices within a narrow distance of each other (typically within 10 yards). Bluetooth networks are common examples of PANs.
* Internet: The internet is a globally connected WAN that enables people, systems, and entities to share information and communicate across vast geographical regions.
* Intranet: An intranet is a local or restricted network that enables users to store and share information within their organization.
* Extranet: An extranet is an externally facing web portal that allows an organization to share select information with vendors, customers, and other external parties.

Two security principles that directly affect network architecture are layering and domain separation.

**Layering** involves designing something in increasingly abstract terms, with each layer offering some aspect of security or assurance.
In the context of hosts communicating over a network, the Open Systems Interconnection (OSI) model is the prevailing example.
The OSI model is one of increasing abstraction, with each layer making room for varying methods of ensuring security.

**Domain separation**, as an architectural principle, applies to secure network design. Separating network traffic at the collision domain helps avoid network congestion.
Separating network traffic into broadcast domains further inhibits an adversary from sniffing valuable clues to the network topology.
Going further, separating a network into segments isolates local network traffic from traveling across routes. This again mitigates the risk of a potential adversary learning about the network design.

A **collision domain** is the part of a network where packet collisions can occur. A network collision happens when two devices send a packet at the same time on a shared network segment.
The packets interfere with each other (or “collide”), and both devices are required to resend their packets, reducing network efficiency.
Each port on a bridge, switch, or router is in a separate collision domain, but all ports on a hub share the same collision domain.

A **broadcast domain** contains all devices that can reach each other at the data link layer (discussed later in this section) by broadcast.
All ports on a router are in different, isolated broadcast domains.

### Open System Interconnection and Transmission Control Protocol/Internet Protocol Models

The OSI and TCP/IP models define and set the standards for network communication and interoperability by using a layered approach (see the earlier definition of layering).

### The OSI Reference Model

The OSI reference model is a conceptual model made up of seven layers that describe information flow from one computing asset to another, over a network.
Each layer of the OSI model performs or facilitates a specific network function.

The layers are listed in numerical order here, but you may also see them arranged from top to bottom (with layer 1 being at the bottom):
* Layer 1: Physical
* Layer 2: Data Link
* Layer 3: Network
* Layer 4: Transport
* Layer 5: Session
* Layer 6: Presentation
* Layer 7: Application

| LAYER        | DESCRIPTION                                                                                                                                                                                                                                                                                 | PROTOCOL DATA UNIT (PDU) | Applied Use                                                                                        |
|--------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------|----------------------------------------------------------------------------------------------------|
| Application  | - Coding and conversion functions on application layer data <br> - Ensures information sent from one system’s application layer is readable at destination system’s application layer                                                                                                       | Data                     | HTTP, HTTPS, DICOM, LDAP, MIME, SMTP, FTP, SFTP                                                    |
| Presentation | - Establishes, manages, and terminates communication sessions between presentation layer entities <br> - Communication sessions consist of service requests and service responses between applications on different network devices                                                         | Data                     | In many references, no distinction between Presentation and Application layer protocols & TLS, SSL |
| Session      | - Session management capabilities between hosts <br> - Assists in synchronization, dialog control, and critical operation management <br> - Remembers session information like password verification so a host does not have to repeatedly supply credentials on subsequent access requests | Data                     | RPC, SMB, SSH, NFS, NetBIOS, H.245, PAP, PPTP, SCP, ZIP                                            |
| Transport    | - Reliable internetwork data transport services transparent to upper layers <br> - Functions include flow control, multiplexing, virtual circuit management, and error checking and recovery                                                                                                | Segment                  | TCP, UDP, BGP, DCCP, FCP, RDP                                                                      |
| Network      | - Provides routing and related functions that enable multiple data links to be combined into an internetwork <br> - Uses logical addressing versus physical addressing of devices                                                                                                           | Packet                   | ATM, Routers, IP, IPSec, ICMP, OPSF, IPv4, IPv6, IPX, DDP, SPB                                     |
| Data Link    | - Provides reliable transit of data across a physical network link                                                                                                                                                                                                                          | Frame                    | Ethernet, FDDI, Frame Relay, VLAN, MAC, Switches, SPB                                              |
| Physical     | - Bit-level transmission between different devices; electrical or mechanical interfaces; activates, maintains, and deactivates the physical link between communicating network systems                                                                                                      | Bits                     | Volts, PINS, bit-rate, serial or parallel, USB, Ethernet 10Base varieties                          |

#### Layer 1: Physical Layer

The physical layer is responsible for the transmission and reception of raw data across a transmission medium (e.g., network cabling or wireless link) from one device to another.
This layer converts digital bits into electrical signals (or other form of energy) that can be transmitted across the given transmission medium.

Physical network topologies are also defined at this layer. The physical topology of a computer network is the structure and arrangement of the various nodes and their connections depicted as links between the nodes.
**Physical topology** is not always the same as **logical topology**, which describes how data flows across the network.
There are four basic physical network topologies: **ring**, **bus**, **star**, and **mesh**.

##### Layer 1 Attack Vectors

Physical layer attacks are attempts to penetrate devices and connection media or interfere with their operation.
This may include passive sniffing, either over the cable or wireless, causing excessive electrical interference, or simply cutting a cable.
However, at the physical layer, attacks that may cause destruction or denial of service are plentiful.

#### Layer 2: Data Link Layer

The data link layer is the second layer in the OSI model, and it transfers data between network nodes on the physical link.
This layer encodes bits into packets before transmission and then decodes the packets back into bits.
The data link layer is where the protocols for the network specifications are established.
Specifically, how devices are to be connected, such as in a bus or a ring topology, is set at this layer.
Data link provides reliability because it establishes capabilities for synchronization, error control, alerting, and flow control.
These services are important because if transmission or packet sequencing fails, errors and alerts are helpful in correcting the problems quickly.
Flow control at the data link layer is vital so the devices send and receive data flows at a manageable rate.

There are two sublayers of the data link layer as established by the Institute of Electrical and Electronics Engineers (IEEE) per the IEEE 802 series of specifications.
These are the **logical link control (LLC)** and the **media access control (MAC)**.

The LLC controls packet synchronization, flow control, and error checking. This upper sublayer provides the interface between the MAC sublayer below and the network layer (layer 3) above.
LLC facilitates node-to-node flow control and error management, such as automatic repeat request (ARQ).

The MAC sublayer is the interface between the LLC above and the physical layer (layer 1) below. The MAC sublayer is responsible for controlling how devices on a network gain permission to transmit data.
MAC provides an addressing mechanism and channel access so nodes on a network can communicate with each other.
MAC addressing works at the data link layer (layer 2). It is similar to IP addressing except that IP addressing applies to networking and routing performed at the network layer (layer 3).
MAC addressing is commonly referred to as physical addressing, while IP addressing (performed at the network layer) is referred to logical addressing.

A MAC address is unique and specific to each computing device. It is a 12-digit hexadecimal number that is 48 bits long.
There are two common MAC address formats, MM:MM:MM:SS:SS:SS and MM-MM-MM-SS-SS-SS.
The first half of a MAC address, called a prefix, contains the ID number of the adapter manufacturer. These IDs are regulated by the IEEE.
The second half of a MAC address represents the serial number assigned to the adapter by the manufacturer.
It is possible for devices from different manufacturers to have the same device portion, the rightmost 24-bit number. The prefixes will differ to accomplish uniqueness.

##### Layer 2 Attack Vectors

An example attack vector unique to the data link layer would include forging the MAC address, otherwise known as Address Resolution Protocol (ARP) spoofing.
By forging ARP requests or replies, an attacker can fool data link layer switching to redirect network traffic intended for a legitimate host to the attacker’s machine.
ARP spoofing is also a common precursor to man-in-the-middle (MITM) attacks and session hijacking attacks.

#### Layer 3: Network Layer

The network layer provides routing and other functions that enable data packets to be sent from one node to another, either on the same network or between interconnected networks.
The network layer receives service requests from the transport layer and issues service requests to the data link layer. Network layer functions include logical connection setup, data forwarding, routing, packet fragmentation, and delivery error reporting.

The primary responsibility of the network layer is routing traffic around the network.
Routing protocols specify how routers communicate with one another on a network, while routed protocols are used to send data from one network to another.
In short, routing protocols transmit routing protocol messages across networks. Routing protocols learn routes (or paths) for routed protocols and are used to transmit packets across those routes (paths).

##### Layer 3 Protocols

Several routing protocols are defined at the network layer:
**Border Gateway Protocol (BGP)**, an internet interdomain routing protocol;
**Open Shortest Path First (OSPF)**, a link-state, interior gateway protocol developed for use in TCP/IP networks;
and **Routing Information Protocol (RIP)**, an internet routing protocol that uses hop count as its metric.

Logical addressing is accomplished at this layer through routed protocols like **Internet Protocol (IP)** and **Internetwork Packet Exchange (IPX)**.

There are several noteworthy functions that occur at the network layer:
* **Internet Protocol (IP):** IP is a set of requirements for addressing and routing data across networks, including the internet.
* **Addressing:** IP facilitates transmission of data from host to destination IP address, traversing the network until the destination address is located and reached.
* **Host addressing:** Each host has a unique address to provide its logical location on the internet. That address is the IP address.
* **Message forwarding:** Gateways or routers are special-purpose devices or hosts on the network that forward data between networks that are segmented, partitioned, or interconnected across a WAN.
* **Fragmentation:** Packet sizes can be large and complex. The network layer facilitates the subdivision of a data packet into a manageable or allowable size without the loss of data integrity.
* **Internet Protocol Security (IPSec):** When implemented, secure communications using virtual private networks (VPNs) and encryption is made possible by this set of protocols that provides security for IP.


###### Border Gateway Protocol

An **autonomous system (AS)** is a large network or group of networks managed or controlled by a single entity or organization.
BGP is a path-vector routing protocol used between separate ASs. It is the most prevalent and scalable of all routing protocols, as it is the routing protocol of the global internet and private networks of service providers too.

When BGP operates between autonomous systems (such as between internet service providers, or ISPs), it is called external BGP (eBGP).
When it operates within a single autonomous system (e.g., within a large private network), it is called internal BGP (iBGP).

BGP operates by choosing the shortest path through the internet by navigating the least number of ASs along the route.
The paths are stored in a Routing Information Base (RIB). Only one route per destination is stored in the routing table, but the RIB is aware of multiple paths to a destination.
Each router determines which routes to store from the RIB, and the RIB keeps track of possible routes. When routes are deleted, the RIB silently removes them without notification to peers. RIB entries never time out.

BGP was initially designed to carry internet reachability information only, but it has expanded in capability to carry routes for Multicast, IPv6, VPNs, and a variety of other data.

There is a vulnerability inherent in the task of determining the optimal path. The vulnerability is that a network in one region can negatively influence the path that traffic takes far outside that region.
Countries with an authoritarian view on controlling network traffic within their borders take advantage of that vulnerability.

###### Routing Information Protocol Versions 1 and 2

Assignment of logical addresses (i.e., IP addresses) to networks requires a mechanism to inform the routers of which networks are directly or indirectly accessible.
In the past, manual entries in routing tables created static routes, forcing traffic between two locations to travel on a designated path.
As more networks were added, maintaining these tables efficiently required the adoption of standards-based protocols to automatically share this information.
The evolution of routing protocols reflects the growth of the internet in order to address the scope and increasingly complex interconnected infrastructure.

Routing Information Protocol (RIP) is one of the earliest routing protocols and the first to use the distance-vector routing method. RIP uses the count of hops that a signal makes along the network path.
RIP allows a maximum of 15 hops, and, at hop number 16, the distance is considered infinite and the destination unreachable.
This constraint limits the size of networks RIP can support, but also is the reason RIP prevents routing loops (which occur when a data packet is continually routed through the same routers over and over).

In addition to hop count, RIP implements split horizon, route poisoning, and hold-down timers to prevent routing loops.
* Split horizon: This routing configuration prevents a route from being advertised back in the direction from which it came.
* Route poisoning: When a router detects that one of its connected routes has failed, the router sets the hop count on the failed route to 16, establishing the route as unreachable.
* Hold-down timers: When a router receives information that a route is bad, it establishes a hold-down period during which the router will neither advertise the route nor accept advertisements about the route.

A RIP router transmits full updates every 30 seconds. When this technology was originated, this was not expected to be a problem.
Over time, the volume of routing devices on the network created the potential for high volumes of traffic bursts.
The theory was that random implementation of new devices would help to normalize the traffic flow over time.

Because time to converge and scalability issues are prevalent in RIP, it is not the preferred choice in most networking environments.
However, RIP is still a potential choice in smaller networks because it is widely supported, is easy to configure, and does not require any parameters, unlike other protocols.

RIP uses the User Datagram Protocol (UDP) as its transport protocol and is assigned the reserved port number 520.

For support of Internet Protocol version 6 (IPv6), RIP next generation (RIPng) is an extension of RIPv2. RIPng sends updates on UDP port 521 using the multicast group FF02::9.

###### Open Shortest Path First Versions 1 and 2

The OSPF protocol is common in large enterprise networks because it provides fast convergence and scalability. Convergence refers to how routing tables get updated.
OSPF is a link-state protocol, specifically one of the interior gateway protocols (IGPs) standardized by the Internet Engineering Task Force (IETF).
Link-state protocols gather information from nearby routing devices and create a network topology, making the protocol very efficient.
OSPF monitors the topology, and when it detects a change, it automatically reroutes the topology. Within seconds, OSPF is able to reroute from link failures and create loop-free routing.

OSPF supports Internet Protocol version 4 (IPv4) and IPv6 networks. The updates for IPv6 are specified as OSPF version 3. OSPF computes traffic load and seeks to balance it between routes.
To do so, several variables are included, such as the round-trip distance (measured in time) of a router, data throughput of a link, or link availability and reliability.
OSPF encapsulates data directly in IP packets at protocol number 89. It does not use a transport protocol like UDP or TCP.

###### Internet Control Message Protocol

The ICMP message has three fields distinguishing the type and code of the ICMP packet, and those values never change in the header while in transit.
They are followed by ICMP-specific information and then the original IP header information.
The most common uses for ICMP traffic are manual troubleshooting (the ping utility) and network diagnostics (the traceroute utility) and system-generated error messages during IP transmissions.

ICMP information is used for troubleshooting and control purposes when there are errors in the IP transmissions.
In ICMP utilities, every device forwards an IP packet, and an ICMP message can be subsequently sent to the source address.
Using ping and traceroute, for example, the source IP address can ascertain several useful network mapping messages such as Destination Unreachable, Echo Request and Reply (Ping), Redirect, Time Exceeded, and Router Advertisement and Router Solicitation.
All are important in the daily operations of security personnel.

Ping and traceroute can also be used by attackers to identify the location of hosts (ping) and, for malicious reasons, to map the network for future attacks of all types (traceroute).

###### Internet Group Management Protocol

The IGMP operates at the network layer but is specific to a host or a router within the group. IGMP is the key protocol necessary for doing IP multicast transmissions.
Multicast becomes useful when you have an application needing to perform a one-to-many transmission, such as a video multicast from the CEO to her employees.
Likely, an attack on IGMP begins with an attack on the multicast routing software or hardware device itself utilizing IGMP.

IGMP is used only on IPv4 networks. IPv6 networks manage multicast transmissions through Multicast Listener Discovery (MLD), which is part of ICMPv6.

##### Layer 3 Attack Vectors

Network layer attacks are generally specific to how network traffic is routed.
A MITM attack, involving traffic being redirected to a malicious actor, is an example of an attack at the network layer.
Spoofing or forging of a network address is another common form of network layer attack.
Assuming the attacker has access to the resources, the simplest attack to execute may be a denial-of-service (DoS) attack that involves simply overwhelming the target’s resources.

#### Layer 4: Transport Layer

The transport layer is responsible for providing reliable data transport and end-to-end transmission control.
The protocols of this layer provide host-to-host communication services and manage the transfer of packets from one host to another, across networks.
The transport layer provides the upper layers (layers 5 through 7) standardized access so that they do not need to be concerned with the details of the lower layers (layers 1 through 3).

Some of the functions that happen at the transport layer are flow control, multiplexing, virtual circuit management, and error checking and recovery.
* Flow control manages data transmission and keeps the sending device from overwhelming the processing capability of the receiving device.
* Multiplexing allows several applications to transmit data along a single physical link.
* Virtual circuits are established, maintained, and terminated by the transport layer.
* Error checking involves creating various mechanisms for detecting transmission errors.
* Error recovery resolves errors such as a request that data be retransmitted. There are two primary transport layer protocols that every security professional must be familiar with: TCP and UDP.

##### Transmission Control Protocol

TCP is a connection-oriented protocol, which means that communicating devices must establish a reliable connection before any data is transmitted (and possibly lost); this connection must also be closed after data transmission is complete.
TCP establishes connections via a three-way handshake.

1. A client node sends a SYN data packet over an IP network to a destination node on the same or an external network. The SYN packet is asking if the destination is open for new connections.
2. The target node must have open ports that can accept and initiate new connections. When the destination target receives the SYN packet from the client node, it responds and returns a confirmation receipt, specifically the ACK packet or SYN/ACK packet.
3. The client node receives the SYN/ACK from the destination and responds with an ACK packet.

Upon completion of this process, the connection is created and the host and target can communicate.

In addition to being connection-oriented, TCP provides extensive error checking mechanisms through flow control and acknowledgment of data.
The protocol enforces data sequencing, such that packets arrive at the receiving host in the order that the sending device sent them, and it supports packet retransmission if packets are lost.

TCP’s connection-oriented nature makes it a reliable protocol, because it is guarantees delivery by acknowledging packets, checking for missing or corrupted packets, and requesting retransmission, when necessary.
Due to the additional overhead associated with the three-way handshake, acknowledging packets, and error checking and correction, TCP is generally a slower protocol than connectionless protocols like UDP.

TCP is used by Hypertext Transfer Protocol (HTTP), Hypertext Transfer Protocol Secure (HTTPS), and File Transfer Protocol (FTP), and other protocols that require reliable data transfer and extensive error checking.

##### User Datagram Protocol

In contrast with TCP, UDP is a connectionless protocol. There is no overhead associated with establishing a connection, maintaining a connection, or terminating a connection, making UDP simpler, faster, and more efficient than TCP.

UDP is often referred to as a “best-effort” communications protocol. It offers none of the features of TCP - no error detection or correction, no sequencing, no flow control mechanisms - and does not use a pre-established session.
In short, UDP is considered an unreliable protocol, which is fine for certain applications.
The protocol’s low overhead permits quick data transmission, which is ideal for real-time streaming of audio and video, where speed is more important than ensuring that every packet arrives perfectly.

UDP is also commonly used by Domain Name System (DNS), Dynamic Host Control Protocol (DHCP), Simple Network Management Protocol (SNMP), and Voice over IP (VoIP), among other applications.
The ongoing rise of Internet of Things (IoT) technologies is also leading to an increased use of UDP, as sensor data is typically ideal for sending via UDP vs. TCP.

##### Layer 4 Attack Vectors

Attack vectors unique to the transport layer would include attacks utilizing TCP and UDP.
One specific example would be the SYN flood attack that drains a target’s network memory resources by continuously initiating TCP-based connections, but not allowing them to complete; this creates a DoS that prevents legitimate connections to the target.
Trojans and other malware also tend to target specific TCP and UDP ports. Session hijacking is another common attack that can operate at layer 4 (as well as other layers).

#### Layer 5: Session Layer

The session layer facilitates the logical, persistent connection between systems on a network. This layer controls the dialogue (connection) between a local application and a remote application.
The session layer is responsible for establishing, coordinating, and terminating a session efficiently and effectively between end-user application processes.
The session layer is commonly implemented in applications that use remote procedure calls (RPCs) to handle requests and responses that occur between applications.

RPCs are the mechanism for application environments to make service requests and service responses between applications on various networked devices.
In other words, RPCs allow a procedure (a sequence of tasks or instructions) to be created on a client and performed on a server device - the session layer manages this process.

There are three primary modes of operation to choose from when a session is established:
* **Full-duplex mode:** This is when data is sent over a connection between two devices in both directions at the same time.
Full-duplex channels can be constructed either as a pair of simplex links or using one channel designed to permit bidirectional simultaneous transmissions.
If multiple devices need to be connected using full-duplex mode, many individual links are required because one full-duplex link can connect only two devices.
* **Half-duplex mode:** Half-duplex has the capability of sending data in both directions, but in only one direction at a time.
While this may seem like a step down in capability from full-duplex, it is widely used and successful across single network media such as cable, radio frequency, and Ethernet, as examples.
The communications work well when the devices take turns sending and receiving.
* **Simplex mode:** This mode involves using a communication channel that operates as a one-way street. An example of simplex construction is where a fiber optics run or a network cable as a single strand sends data and another separate channel receives it.

##### Layer 5 Attack Vectors

What sorts of attacks target the session layer? This layer and the presentation layer aren’t popular targets for common attacks.
Routing or packet-based attacks (lower on the OSI model) and application-level attacks (higher on the OSI model) offer “low-hanging fruit” for attackers, leaving the session and presentation layers at an awkward level of abstraction for identifying vulnerabilities.

Still, given the layer’s functions, you can hypothesize an attack where authentication to establish a session across the network is compromised.
There are also specific session layer protocols, such as NetBIOS and Network File System (NFS), that may be vulnerable to DoS and root privilege attacks, for example.
Weaknesses in the deprecated Secure Sockets Layer (SSL) protocol and less secure versions of Transport Layer Security (TLS) are also prime targets at the session layer.

#### Layer 6: Presentation Layer

The purpose of the presentation layer is to translate data between the lower layers and the application layer. At lower levels, data is sent as datagrams and packets.
The presentation layer is the first layer in the OSI model at which data structure and presentation are evident, as this layer is responsible for applying coding and conversion functions to data being presented to the application layer.

Here are some examples of the coding and conversion at this layer:
* Common data representation formats, such as the use of standard image, sound, and video formats
* Common data compression schemes, such as JPEG and MPEG
* Common data encryption and decryption schemes

These functions enable the interchange of application data between different types of computer systems. In short, the presentation layer ensures that formats are converted and presented to the application layer as needed.

##### Layer 6 Attack Vectors

The most common attacks at this layer involve attacks on the encryption schemes themselves.

#### Layer 7: Application Layer

The application layer is the highest layer of the OSI model and the closest layer to the end user. This layer supports network access for software applications and provides an interface for the user.
The software applications do not reside at the application layer. Instead, this layer facilitates communication through the lower layers to establish connections with applications at the other end of the network connection.
Web browsers (e.g., Chrome, Safari, Firefox), HTTP, FTP, and Telnet all rely on the application layer to function properly.

##### Layer 7 Attack Vectors

Attack vectors specific to the application layer vary wildly, and most security breaches occur at this layer. To begin the list, consider weaknesses in application layer protocols such as HTTP, FTP, Simple Mail Transfer Protocol (SMTP), and SNMP.
Every attack on the user interface falls into this category, as well as web-based attacks such as HTTP flooding or input validation attacks.
SQL injection and cross-site scripting (XSS) are among the most common attacks that operate at the application layer. At the application layer, where services support user applications, user authentication takes place.
In addition to these attack vectors, authentication weaknesses (such as weak or poorly managed passwords) also provide a critical attack vector at this OSI layer.

### The TCP/IP Reference Model

The TCP/IP reference model is a four-layer conceptual model that was initially developed in the 1960s by the U.S. Defense Advanced Research Projects Agency (DARPA).

<div style="text-align: center;">

| TCP/IP Model                                                                                                        |
|---------------------------------------------------------------------------------------------------------------------|
| Application Layer <br> Application programs using the network                                                       |
| Transport Layer (TCP/UDP) <br> Management of end-to-end message transmission, error detection, and error correction |
| Internet Layer (IP) <br> Handling of datagrams: routing and congestion                                              |
| Link Layer <br> Management of cost-effective and reliable data delivery, access to physical networks                |

</div>

#### Link (or Network Access) Layer

The link layer is called by several other names, including the network access layer or the data link layer (and, indeed, the TCP/IP model’s link layer includes some of the same functionality as the OSI model’s data link layer).
Think of it as the physical interface between the host system and the network hardware.

The role of this layer is to facilitate TCP/IP data packets across the network transmission channel in a reliable manner.
This layer can detect transmission errors. This layer determines how common data link standards like IEEE 802.2 and X.25 format data packets for transmission and routing.

The way TCP/IP was designed allows the data format to be independent of the network access method, frame format, and medium that establishes TCP/IP to interconnect across disparate or different networks.
It is this independence from any specific network technology that makes both the TCP/IP and OSI 7 layer models scalable to newer networking technologies like Asynchronous Transfer Mode (ATM).

There are several important services that the link layer provides:
* **Data frame:** This is a defined sequence of bits or symbols from a sender that the receiver uses to find the beginning and end of the payload data within the overall stream of other bits or symbols it receives.
* **Checksums:** Data is used within a data frame to manage the integrity of data and allow the receiver to know the data frame was received error-free.
* **Acknowledgment:** This enables reliability in data transmission because a positive acknowledgment is made when data is received. A timeout notice or a negative acknowledgment is received when data is expected but not received.
* **Flow control:** To maintain traffic and avoid errors due to congestion, the link layer supports buffering data transmissions to regulate fast senders with slow senders.

#### Internet Layer

Using core protocols like IP, ARP, ICMP, and IGMP, the internet layer is responsible for addressing, packaging, and routing functions of data packets.
Unlike the link layer, the internet layer does not take advantage of data sequencing and acknowledgment services.

The internet layer performs several invaluable functions. To transmit packets from host to host, IP selects the next-hop or gateway for outgoing packets across the link layer.
It transfers data packets up to the transport layer for incoming packets if the data meets transmission parameters. To that end, the internet layer helps with error detection and diagnostic capability, so data is not transferred in error.

These are the main protocols residing at this layer:
* IP is the principal routable communications protocol responsible for addressing, routing, and the fragmentation and reassembly of data packets.
* ARP resolves the hardware address of a host from a given IP address.
* ICMP provides diagnostic functions and error reporting when there is an unsuccessful delivery of packets.

#### Transport Layer

At the transport layer, services are provided to the application layer for session and datagram communication. You may also hear this layer referred to as the host-to-host transport layer.
In the TCP/IP model, the transport layer does not make use of the features of the link layer. It assumes an unreliable connection at the link layer.
Therefore, at the transport layer, session establishment, packet acknowledgment, and data sequencing are accomplished to enable reliable communications.
The core protocols of the transport layer are TCP and UDP, both discussed in the earlier “Layer 4: Transport Layer” section of the OSI 7 model.

#### Application Layer

So that applications can access the services of the other layers of the TCP/IP model, the application layer defines the data exchange protocols used by applications.
This is the highest layer in the model, and many application layer protocols exist, while new protocols are constantly being developed.

The most widely known application layer protocols are those used for the exchange of user information:
* HTTP/HTTPS is the foundation of file and data transfer on the World Wide Web that comprises and supports websites.
* FTP/FTPS enables file transfer in the client-server architecture.
* SMTP/SMTPS allows email and associated attachments to be sent and received.
* Telnet is a bidirectional interactive text-oriented communication protocol used to access or log on to networked computers remotely.
Telnet has no built-in security, so it should be avoided in use over the public internet. It is an unsecured terminal emulation protocol.

### Internet Protocol Networking

IP networking is the main protocol of the internet. The protocol resides at the OSI model’s network layer and the TCP/IP model’s internet layer.
For all intents and purposes, IP makes the internet a reality because the protocol makes it possible to relay datagrams across network boundaries.
IP exists in two versions: IPv4 (version 4), which is currently the main version used, and IPv6 (version 6), to which internet-connected devices are evolving.

#### Internet Protocol Version 4

IPv4 uses 32-bit IP addresses, often written as four decimal numbers called octets, each in the range 0–255, such as 172.16.8.93.
The IPv4 address space is partitioned into five network classes of 32-bit IP addresses.
Classes A, B, and C each correspond to a maximum number of networks and number of hosts per network, while class D is used for multicasting, and class E is reserved for experimental use.
Refer to Table 4.1 to see the network classes that subdivide IP addressing.

| CLASS | RANGE OF FIRST OCTET | NUMBER OF NETWORKS | NUMBER OF HOSTS PER NETWORK |
|-------|----------------------|--------------------|-----------------------------|
| A     | 1–127                | 127                | 16,777,214                  |
| B     | 128–191              | 16,384             | 65,534                      |
| C     | 192–223              | 2,097,152          | 254                         |
| D     | 224–239              | Multicast          | Multicast                   |
| E     | 240–255              | Reserved           | Reserved                    |

##### Network Address Translation

NAT is a technique used to map (or translate) one or more local (internal) IP addresses to one or more global (external) IP addresses, and vice versa.

NAT can be implemented on a variety of different devices such as firewalls, routers, gateways, and proxies. It can be used only on IP networks and operates at the network layer (layer 3).
Originally, NAT was designed to extend the use of IPv4, since the pool of available addresses was quickly being exhausted. To that point, NAT is a legacy technology that comes with advantages and disadvantages.

##### NAT Advantages

First, consider its advantages. NAT is used to accomplish network and security objectives to hide the identity of internal clients, mask the routable design of your private network, and keep network addressing costs at a minimum by using the fewest public IP addresses possible.

Through NAT processes, the organization assigns internal IP addresses, perhaps even a private addressing scheme.
The NAT appliance catalogs the addresses and will convert them into public IP addresses for transmission over the internet.
On the internal network, NAT allows for any address to be used, and this does not cause collisions or conflict with public internet hosts with the same IP addresses.
In effect, NAT translates the IP addresses of the internal clients to leased addresses outside the environment.

NAT offers numerous benefits, including the following:
* NAT connects an entire private network to the internet using only a single or just a few leased public IP addresses.
* NAT uses private IP addresses (10.0.0.0 to 10.255.255.255) in a private network and retains the ability to communicate with the internet as the NAT translates to a public, routable address.
* NAT hides the IP addressing scheme and network topography of an internal, private network from the internet.
* NAT ensures that connections originated from within the internal protected network are allowed back into the network from the internet.

##### NAT Disadvantages

Now, consider some of NAT’s disadvantages. Again, remember that NAT was developed to help deal with the fact that IPv4 addressing was being exhausted. To that end, NAT was assumed to be a temporary solution.
Because it was considered only temporary, the IETF, responsible for defining protocol standards, didn’t pursue creating an in-depth official standard for NAT.
In fact, while the IETF recognized the benefits of NAT and published a general specification, it avoided developing a technical specification to discourage NAT’s widespread adoption.
For that reason alone, the biggest disadvantage to NAT is how inconsistent its implementation in devices is.

A few technical disadvantages of NAT have been recognized, but solutions to those problems were discovered or developed without needing to reinvent NAT.

For example, consider how peer-to-peer communication is handled. Without NAT, an initiator communicates with a target. This is not a problem provided both the initiator and the target have routable addresses.
With NAT implemented, an initiator on the internet seeking to connect with a target behind NAT cannot connect with a nonroutable address.
One way to solve this is for the peer-to-peer session to begin “backward,” with the target first connecting with the initiator for the purpose of discovering NAT in place. Then, once NAT’s outside public address is known, the originator can begin a new peer-to-peer session.

Services such as Skype, which rely on peer-to-peer or VoIP protocols, needed to create innovative ways to sidestep how NAT would otherwise break their service.
Skype, for example, employs “SuperNodes” on public addresses to permit a peer-to-peer connection, even if both the target and the initiator are behind NAT.

Another disadvantage is how IPSec checks integrity. IPSec computes a hash value for the purpose of ensuring the integrity of each packet.
That hash value is computed using various parts of the packet, and since NAT changes the packet’s values, that hash value is no longer valid.
To address this, the technology of NAT-Traversal (NAT-T) was developed. NAT-T ensures that IPSec isn’t broken when one or both ends of the IPSec tunnel cross over a NAT device.

While NAT is a critical technology for IPv4 networks, the technology is no longer needed in IPv6. This is one of several improvements offered by the latest version of the Internet Protocol, which is discussed in the following section.

#### Internet Protocol Version 6

As opposed to IPv4’s 32-bit IP addresses, IPv6 uses 128-bit IP addresses to support a significantly larger number of addresses than its older peer.
Each IPv6 address is portioned into four hexadecimal digits, which are separated by colons for addressing, and segmented into two parts: a 64-bit network prefix and a 64-bit interface identifier.

An example IPv6 address looks like 2607:F0F0:1002:00B1:0000:0000:0000:0004. The added complexity allows IPv6 to support 10<sup>28</sup> times the total number of IPv4 addresses, allowing for internet-connected devices to expand for the foreseeable future.
The IPv6 scheme intends also to improve network addressing and routing.

Some of the principal benefits of IPv6 over IPv4 include the following:
* **Scoped addresses:** This adds a layer of security and access control for administrators who can group and then deny or allow access to network services, like file servers or printing.
* **Autoconfiguration:** This removes the need for both DHCP and NAT, thanks to the much larger public address space.
* **Quality of service (QoS) priority values:** Based on the content priority, traffic management is conducted according to preset QoS priority values.

IPv6 was developed by the IETF to manage the anticipated problem of IPv4 address exhaustion, but adoption of IPv6 has been slow. Operating systems since about 2000 have had the ability to use IPv6, either natively or via an add-in.
Adoption hurdles include added cost of some IPv6-capable devices and the fact that IPv4 works well.
Decision-makers are reluctant to either make a change for the sake of change itself or make process improvements that provide a minimal financial return on investment (ROI).
Early adopters of IPv6 are found in private, internal networks in large corporations, research laboratories, and universities.

#### Network Attacks

Networking protocols were designed long before the necessity of security was fully recognized. Consequently, even today, networked hosts remain vulnerable and networked systems fail to implement mitigating controls.
Systems that are hardened against attacks that exploit misconfiguration and unnecessary services can still be vulnerable from attacks exploiting network services.
Several updates and revisions to networking protocols have been adopted, but weaknesses remain due to security being designed as an afterthought, although progress continues to be made.

##### Distributed Denial-of-Service Attacks

When an attacker does not have the skills or tools for a sophisticated attack, they may use a brute-force attack, which can be just as effective.
Simply flooding the targeted system with UDP packets from infected machines has proven successful, especially as IoT devices have been used, unwittingly, to help launch these distributed denial-of-service (DDoS) attacks.
A typical DDoS attack consists of a large number of individual machines that are subverted to bombard a target with overwhelming traffic over a short period of time.
The individual contribution of any one compromised machine - be it a PC, IoT device, networking hardware, or server - would amount to no damage, but the collective sum creates a crushing amount of traffic to the end target.

###### SYN Flooding

In an attempt to overload a system, this type of attack bombards the recipient with an overwhelming number of SYN packets, and the sender or senders do not acknowledge any of the replies.
SYN flooding is a form of DoS attack, exploiting properties of TCP at the transport layer (layer 4). TCP initiates a connection by sending a SYN packet, which when received and accepted is replied to with a SYN-ACK packet.
The SYN flooding DoS attack is executed by sending massive amounts of those SYN packets. The SYN packets accumulate at the recipient system, and the software crashes because it cannot handle the overflow.
The attacker attempts to consume enough server resources to make the system unresponsive to legitimate traffic. Some refer to this attack as the half-open attack because of the partial three-way TCP handshake that underlies the attack.
Eventually, given enough connection attempts, the capacity of the network card to maintain open connections is exhausted.

Even though these types of attacks have such a long history and the mitigations have been in existence for almost as long, SYN flooding is still a common attack.
There are some ways to mitigate a SYN flood vulnerability. A few of the most prevalent approaches are the following:
* **Increasing backlog queue:** This involves raising the allowance for the number of half-open connections a system will sustain. It requires additional memory resources to increase the maximum backlog.
Depending on the availability of memory resources, mitigating the SYN flooding threat can degrade system performance. A risk-benefit analysis is required against unwanted DoS impact and slower performance.
* **Recycling the oldest half-open TCP connection:** This is a first-in, first-out queueing strategy where once the backlog queue limit is reached, the oldest half-open request is overwritten.
The benefit is fully establishing legitimate connections faster than the backlog can be filled with malicious SYN packets. However, if the backlog queue is too small or the attack too voluminous, this mitigation can be insufficient.
* **SYN cookies:** The server responds to each connection request (SYN) with a SYN-ACK packet. The SYN request is dropped from the backlog. The port is open to new, ideally legitimate, new connections.
If the initial connection is legitimate, the original sender will send its ACK packet. The initial recipient, which created the SYN cookie, will reconstruct the SYN backlog queue entry.
Of course, there will be some limitations as some information about the TCP connection can be lost. This is more advantageous than the full DoS outage.

###### DDoS and the Internet of Things

As an emerging technology, IoT devices deserve a little more attention in this chapter. From a security perspective, these devices offer a soft target for potential attackers.
They are delivered with default settings that are easily guessed or, in fact, publicly well known. Administrative credentials and management access are wide open to internet-facing interfaces.

Attackers can exploit the devices with a relatively simple remote access code. What compounds the vulnerabilities is that users do not interact with the devices the same way as they do with office automation or other endpoint computing assets.
The default settings are rarely changed, even if the end user has the ability to make changes. Vendors are typically slow to provide upgrades and patches, if they supply post-sale manufacturing support at all.
For these reasons, the devices are easy prey, and users often have no idea the devices are being hacked until it is too late.

It is estimated that there are already tens of millions of vulnerable IoT devices installed or in use today. That number is growing.
The interconnections are usually always on, left unprotected to ingress and egress unlike a typical LAN or WAN, but they enjoy high-speed connections.
These variables explain why a botnet of huge groups of commandeered IoT devices presents a serious problem.
Common attack sequences consist of compromising the device to send spam or broadcast messages. If spam filters block that attack, a tailored malware insert may be tried, like fast flux, which is a DNS technique to hide spamming attacks.
If that does not accomplish the disruption, a brute-force type of DDoS might be launched.

##### Man-in-the-Middle Attacks

In a communication where sender and receiver believe they are connected, a MITM attack can be hard to detect and presents a significant threat to unprotected communications.
In a MITM attack, the attacker intercepts the signal and secretly relays (and possibly alters) the communication before stopping the transmission or allowing the message to reach the intended recipient.

Eavesdropping is a specific type of MITM attack. In that scenario, the attacker relays the message to complete the circuit.
The entire conversation is overheard, and in some instances controlled, by the attacker, while the sender and receiver think the message is private.

Another type of MITM attack is impersonation. This happens when the attacker circumvents the authentication process and compromises the credentials of one account.
The endpoint communicating with the attacker is not aware that the communication has been intercepted.

There are two main ways to prevent or detect MITM attacks: authentication and tamper detection.
Authentication provides some degree of certainty that a given message has come from a legitimate source. Tamper detection merely shows evidence that a message may have been altered.
* **Authentication:** To prevent  MITM attacks, cryptographic protocols are used to authenticate the endpoints or transmission media. One such technique is to employ a TLS server paired with X.509 certificates.
The X.509 certificates are used by the mutually trusted certificate authority (CA) to authenticate one or more entities. The message and an exchange of public keys are employed to make the channel secure.
* **Tamper detection:** One way to detect MITM attacks is through examination of any latency in the transaction above baseline expectations.
Response times are checked, and normal factors like long calculations of hash functions are accounted for. If a delay is not explained, there may be unwanted, malicious third-party interference in the communication.

##### Packet Sniffing

Administrators often use packet sniffing tools for legitimate purposes, like troubleshooting. But attackers conduct MITM packet sniffing to gain information for adversarial purposes.
Any unencrypted protocols are subject to passive attacks where an attacker has been able to place a packet sniffing tool on the network to monitor traffic.
The monitoring might be used to determine traffic types and patterns or to map network information.

In any case, packet sniffing greatly benefits the attacker in preparing for other types of attacks.
Say, for example, that an attacker using packet sniffing discovers that a company still uses deprecated SSL ciphers or discovers the IP address of the Active Directory (AD) controller.
The attacker is now set up to exploit that outdated protocol or server.

Packet sniffing can also include grabbing packets in transit and attempting to extract useful information from the contents. Contained in some packets are usernames, passwords, IP addresses, credit card numbers, and other valuable payload.

Encrypting sensitive traffic is the best way to protect against network sniffing.

##### Hijacking Attacks

Hijacking attacks describe many different types of MITM attacks. A hijacking attack is any attack that involves the exploitation of a session, which is an established dialogue between devices.
Normally, a session is managed by a control mechanism, such as a cookie or token. An attacker might try to intercept or eavesdrop on the session token or cookie.

In the case where an attacker has sniffed the cookie or token, the attacker may connect with the server using the legitimate token in parallel with the victim.
Or the attacker may intercept the session token to use as well as to send a specially formed packet to the victim to terminate their initial session.

Many websites require authentication and use cookies to remember session tracking information. When the session is terminated as the user logs out, the cookie and credentials are typically cleared.
Hijacking a session and stealing the token or cookie while the session is active can provide an attacker with valuable, sensitive information, such as unique details on what site was visited.
Even worse, hijacking the session cookie may allow the attacker an opportunity to continue a session, posing as the victim.

##### MITRE ATT&CK Framework

This chapter is not intended to present an exhaustive list of network attacks, but the MITRE Organization (usually just called MITRE) maintains quite an extensive knowledge base of adversary tactics and techniques known as MITRE ATT&CK.
This knowledge base is a globally accessible reference that includes hundreds of real-world attack tactics and techniques, which is intended to serve as a foundation for security professionals to develop threat models and methodologies in their organizations.
You can learn all about MITRE ATT&CK at attack.mitre.org.

### Secure Protocols

Secure protocols provide security services for communications channels as well as secure authentication services.
Some common secure communications protocols include SSH, TLS, Kerberos, IPSec, and Internet Key Exchange (IKE).

#### Secure Shell

SSH is a replacement for Telnet, which supports interactive, text-oriented communication over TCP.
SSH is a cryptographic network protocol that creates a secure tunnel that protects the integrity of communication, preventing session hijacking and other MITM attacks.

SSH is also a client-server architecture that is often used to accomplish remote command-line login and remote command execution. Any network service can be secured with SSH.

The protocol specification distinguishes between two major versions, referred to as SSH-1 and SSH-2.
SSH-1 is considered insecure, while SSH-2 provides more secure and efficient protections against eavesdropping, DNS and IP spoofing, and MITM attacks.

#### Transport Layer Security

TLS is a secure protocol that replaced SSL as the primary protocol for secure web traffic. SSL is a session-oriented legacy protocol that was commonly used to secure web, email, FTP, or even Telnet traffic.
SSL is still in broad use despite having known security weaknesses, but it is insecure and should be replaced by TLS whenever possible.
TLS functions in the same general manner as SSL, but it uses stronger authentication and encryption protocols.
Rather than establishing a VPN using IPSec at the network layer and requiring each remote user to have a client installed, SSL or TLS is used to create an on-demand tunnel.
Remote users need no client installed, and access to the private network is via a web browser.

SSL and TLS both have the following features:
* Support secure client-server communications across an insecure network while preventing tampering, spoofing, and eavesdropping
* Support one-way authentication using digital certificates
* Support two-way authentication using digital certificates
* Often implemented as the initial payload of a TCP package, allowing it to encapsulate all higher-layer protocol payloads
* Can be implemented at lower layers, such as the network layer (layer 3) to operate as a VPN. This implementation is known as OpenVPN.

In addition, TLS can be used to encrypt UDP and Session Initiation Protocol (SIP) connections. TLS encrypted sessions are the preferred mechanism for secure e-commerce.

#### Kerberos

Kerberos is a communication protocol that provides protection for logon credentials. It uses the concept of tickets to allow systems communicating over an unsecured network to prove their identity to one another securely.

#### Internet Protocol Security

IPSec is a suite of protocols developed to provide confidentiality, integrity, and authentication (note: this a is authentication, not availability) of data sent over an IP network.

IPSec uses several security services to accomplish authentication and encryption:
* Authentication header (AH): This authenticates the sender, and it discovers any changes in data during transmission.
* Encapsulating security payload (ESP): This not only performs authentication for the sender, but it also encrypts the data being sent.
* Security associations (SAs): These provide the bundle of shared security attributes or keys and data that provide the parameters necessary for AH and/or ESP operations.

There are two modes of IPSec:
* Transport mode: This only encrypts and authenticates the IP payload, which is the data being transmitted in the packet, to ensure a secure channel of communication.
* Tunnel mode: This will encrypt and authenticate the whole IP packet, which includes the data as well as routing information, to form a new IP packet with a new IP header to provide secure communication between two places (i.e., establish a VPN).

#### Internet Key Exchange

IKE is a secure protocol that is part of IPSec suite and is used to establish a secure, authenticated communications channel between two entities.
The IKE protocol typically uses X.509 PKI certificates for authentication and the Diffie–Hellman–Merkle key exchange protocol to establish a shared session secret.

There are two versions of IKE: IKEv1 and IKEv2, where IKEv2 was designed to solve a number of configuration and security issues that exist within the first version.
Even still, both versions of IKE are vulnerable to offline dictionary attacks, which requires a high entropy password to protect against.
In addition, IPSec VPN configurations that support both IKEv1 and IKEv2 may be vulnerable to downgrade attacks that force the less secure version 1.
This can be mitigated by segmenting systems that require IKEv1 from those that are suitable for the stricter IKEv2 configurations.

### Implications of Multilayer Protocols

TCP/IP is an example of a multilayer protocol, in which multiple individual protocols are located across the various protocol stack layers. Encapsulation is an important capability and benefit of multilayer protocol schema.
In the context of networking communication between two hosts, encapsulation means to envelope one protocol’s contents as the payload for the subsequent protocol.

To illustrate the process of encapsulation, consider a web server to web browser data transfer, which is HTTP-encapsulated in TCP. TCP is encapsulated in IP, and that packet is encapsulated in Ethernet.
TCP/IP can also add additional layers of encapsulation. SSL/TLS encryption can be added to the communication to provide additional confidentiality.

There are instances of TCP/IP encapsulation used for adversarial purposes. Some attack tools can hide or isolate an unauthorized protocol within an authorized one.
Using a technique like HTTP tunneling, FTP can be hidden within an HTTP packet to get around egress restrictions.

#### Virtual Local Area Networks

Attackers can also use multilayer protocol encapsulation to provide an ability to fool interior switching devices to gain access to a VLAN.
VLANs are used to isolate network traffic to its own separate broadcast domain. (See Figure 4.7.) The switch knows what VLAN to place that traffic on according to a tag identifying the VLAN ID.
Those tags, per IEEE 802.1Q, encapsulate each packet. Where a VLAN is established through logical addressing, VLAN hopping is an attack using a double-encapsulated IEEE 802.1Q VLAN tag.
To be clear, that is one VLAN tag encapsulating a packet already encapsulated with a different VLAN ID.
The first VLAN tag is removed by the first switch it encounters. The next switch will inadvertently move traffic according to the second layer VLAN encapsulated tag.

#### Supervisory Control and Data Acquisition Systems

An implication of multilayered protocols is the enablement of particular communication protocols across more ubiquitous transport protocols, chiefly TCP/IP.
Probably the most salient examples of that are the industrial control in energy and utility industries using supervisory control and data acquisition (SCADA) systems.
SCADA is a control system architecture that uses computers to gather data on processes and send control commands to connected devices that comprise the system.

SCADA systems utilize a legacy protocol called Distributed Network Protocol (DNP3). DNP3 is found primarily in the electric and water utility and management industries.
Data is transported across various components in industrial control systems like substation computers, remote terminal units (RTUs), and SCADA master stations (control centers).
DNP3 is an open and public standard. There are many similarities between DNP3 and the TCP/IP suite, as they are both multilayer protocols that have link and transport functionality in their respective layers.

Ultimately, to provide some connectivity to these SCADA systems over public networks, there is the solution of encapsulating DNP3 over TCP/IP. This encapsulation, while obviously bridging a connection between disparate standards, does introduce great risk.
Perhaps the most common exploitation of this risk is through MITM attacks.

Proprietary technologies established the SCADA systems, but recently they have moved to more open and standardized solutions.
With this evolution comes security concerns. Initially, the systems were designed for decentralized facilities like power, oil, gas pipelines, water distribution, and wastewater collection systems.

Connections were not a primary concern as the systems were designed to be open, robust, and easily operated and repaired. Any security was a secondary concern.
Increasingly, there have been more connections between SCADA systems, office networks, and the internet. The interconnectedness has ushered the systems into vulnerabilities like all other IP-based LANs and WANs.

Although sensitive personal information is not necessarily the focus of information protection in SCADA systems, the primary concerns with SCADA cybersecurity are system disruption, sensitive configuration information, and national security.

### Converged Protocols

Converged protocols differ from encapsulated, multilayer protocols. Converged protocols are what happens when you merge specialty or proprietary protocols with standard protocols, such as TCP/IP suite protocols.
With converged protocols, an organization can reduce reliance on distinct, costly proprietary hardware, as well as create variations of performance, depending on which converged protocol is being used.

Some common examples of converged protocols are described here:

* **Storage Area Network (SAN):**
A storage area network (SAN) is a secondary network (distinct from the primary communications network) used to consolidate and manage various storage devices into a single consolidated network-accessible storage container.
SANs are often used to enhance networked storage devices such as hard drives, drive arrays, optical jukeboxes, and tape libraries so that they can be made to appear to servers as if they were local storage.
SANs operate by encapsulating or converging data storage signals into TCP/IP communications in order to separate storage and proximity.
A SAN can be a single point of failure, so redundancy needs to be integrated to provide protection of availability. In some instances, a SAN may implement deduplication in order to save space by not retaining multiple copies of the same file.
However, this can sometimes result in data loss if the one retained original is corrupted.

* **Fibre Channel over Ethernet (FCoE):**
Fibre Channel solutions usually need separate fiber-optic cabling infrastructure to deliver network data-storage options, such as a storage area network (SAN) or network-attached storage (NAS).
Fibre Channel is useful because it allows for high-speed file transfers achieving 128 Gbps and today reaching 256 Gbps. FCoE was developed to enable Fibre Channel to work more efficiently, while using less expensive copper cables over Ethernet connections.
Using 10 Gbps Ethernet, FCoE uses Ethernet frames to support the Fibre Channel communications.

With this technology, Fibre Channel operates as a Network layer or OSI layer 3 protocol, replacing IP as the payload of a standard Ethernet network.
**Fiber Channel over IP (FCIP)** further expands the use of Fibre Channel signaling to no longer require any specific speed of network. It is the SAN equivalent of VoIP.

* **Internet Small Computer System Interface (iSCSI):**
iSCSI is often viewed as a low-cost alternative to Fibre Channel. It is also a networking storage standard but based on IP. It facilitates the connection of a remote storage volume over a network as if the device were attached locally.
The iSCSI transmits SCSI commands over IP networks and performs like a virtual SATA (or SCSI) cable.

* **Multiprotocol Label Switching (MPLS):**
MPLS is a high-throughput, high-performance network technology that directs data across a network based on short path labels rather than longer network addresses.
Compared with IP routing processes, which are complex and take a longer time to navigate, MPLS saves significant time. Using encapsulation, MPLS is designed to handle a wide range of protocols.
An MPLS network can handle T1/E1, ATM, Frame Relay, synchronous optical networking (SONET), and DSL network technologies, not just TCP/IP and compatible protocols. MPLS is often used to create a virtual dedicated circuit between two stations.
In the context of the OSI model, MPLS is commonly labeled a layer 2.5 protocol since it operates squarely between the common definitions of data link (layer 2) and network (layer 3) protocols.

* **Voice over Internet Protocol (VoIP):** VoIP is a method using several technologies to encapsulate voice communications and multimedia sessions over IP networks.
VoIP has become a popular and inexpensive way for companies and individuals to operate telephony solution using a TCP/IP network connection.

### Microsegmentation

Microsegmentation is a method of creating zones within a network to isolate resources from one another and secure each segment individually. Microsegmentation requires re-authentication when viewing or otherwise accessing resources across zones.

Networks are not typically configured as a single large collection of systems. Usually, networks are segmented or subdivided into smaller organizational units.
These smaller units, groupings, segments, or subnetworks (i.e., subnets) can be used to improve various aspects of the network:
* **Boosting Performance** Network Network segmentation can improve performance through an organizational scheme in which systems that often communicate are located in the same segment. Also, dividing broadcast domains can significantly improve performance for larger networks.
* **Reducing Communication Problems** Network segmentation often reduces congestion and contains communication problems, such as broadcast storms.
* **Providing Security Network** segmentation can also improve security by isolating traffic and user access to those segments where they are authorized.

#### Software-Defined Networking

SDN is an approach to network management that enables a network to be centrally managed (or programmed), offering holistic management across various vendors, applications, and technologies.
SDN architectures allow dynamic network configuration and management that improves network performance and gives organizations (most notably cloud providers) a centralized view of their entire network architecture.

SDN separates hardware and hardware-based settings from the network services of data transmission.
In other words, SDN abstracts network control from network forwarding capabilities (like routing), creating two layers (infrastructure and control) out of what is traditionally a single function.

These are the three layers of an SDN architecture:
* Infrastructure layer (data plane): Network switches and routers and the data itself as well as the process of forwarding data to the appropriate destination
* Control layer: The intelligence in devices that works in true intermediary fashion, determining how traffic should flow based on the status of the infrastructure layer and the requirements specified by the application layer
* Application layer: Network services, utilities, and applications that interface with the control layer to specify needs and requirements

Using SDN removes the traditional networking concepts of IP addressing, subnets, routing, and the like from needing to be programmed into or deciphered by hosted applications.
It also improves the ability to respond to changes in threats, to adapt quickly to dynamic physical and business conditions, and to take advantage of the best available technology (regardless of the vendor).

Of course, using SDN has security implications along with its benefits. With this architecture being so flexible and scalable, it is not uncommon for SDN to be configured incorrectly. The consequence of misconfiguring SDN leads to unexpected flows of network traffic.
Traffic intended to be on one area of the network is discovered to be on another part of the network.

Another perceived weakness of SDN is the lack of one common standard or implementation. Again, given its extreme flexibility, the absence of one way of doing things is not a surprise. Still, there are standards. One of the first SDN standards is OpenFlow.
OpenFlow started out as a way of defining how the control plane works with the data plane. OpenFlow divides its interaction with the data plane into two separate “directions.”
OpenFlow works with the switches and routers (whether virtual or physical) through southbound application programming interfaces (APIs). Along the same lines, OpenFlow works with the network’s business logic through northbound APIs.

Another interesting development arising out of the concept of virtualized networks is that of a **virtual SAN (VSAN)**. A SAN is a network technology that combines multiple individual storage devices into a single consolidated network-accessible storage container.
They are often used with multiple or clustered servers that need high-speed access to a single shared dataset. These have historically been expensive due to the complex hardware requirements of the SAN.
VSANs bypass these complexities with virtualization. A virtual SAN or a software-defined shared storage system is a virtual re-creation of a SAN on top of a virtualized network or an SDN.

**Software-defined storage (SDS)** is another derivative of SDN. SDS is a SDN version of a SAN or NAS.
SDS is a storage management and provisioning solution that is policy driven and is independent of the actual underlying storage hardware. It is effectively virtual storage.

#### Software-Defined Security

As microsegmentation continues to grow in popularity, new ways of implementing security controls continue to be developed and implemented. Software-defined security (SDS) is a security model in which security mechanisms are controlled and managed by security software.
SDS is software-managed, policy-driven security that consists of network segmentation, intrusion detection and prevention, user and device identification, application controls, and more.
Whereas traditional security architectures may fail to meet the complex security needs of physical infrastructures, SDS enables the implementation and management of more advanced and automated security controls for software-defined networks and environments.

#### Software-Defined Wide Area Network

Software-defined wide area network (SD-WAN) is an extension of SDN practices to connect to entities spread across the internet to support WAN architecture, especially related to cloud environments.
SD-WAN solutions offer an alternative to traditional WAN routers and are agnostic to WAN transport technologies. Much like SDN, SD-WAN decouples the control plane from the data plane.
SD-WAN uses software to control connectivity and management of services between data centers and remote networks, such as cloud service providers (CSPs).

According to Gartner, SD-WAN has four characteristics:
* Must support multiple connection types (e.g., internet, MPLS, LTE, etc.)
* Can perform dynamic path selection to support load sharing across WAN connections
* Provides a simple interface for managing the WAN
* Must support VPNs and other third-party services

#### Virtual eXtensible Local Area Network

Virtual extensible local area network (VXLAN) is a network virtualization technology that uses encapsulation techniques to encapsulate layer 2 Ethernet frames within layer 4 UDP datagrams.
VXLAN technology allows network architects to segment their large networks (much like VLANs do) with scale that VLANs cannot support.
For example, one can theoretically create as many as 16 million VXLANs in a domain, whereas one can only create a maximum of 4,094 VLANs.
This added flexibility for large-scale segmentation allows VXLANs to meet the needs of large multitenant public cloud providers.

#### Encapsulation

As discussed earlier, encapsulation involves wrapping one protocol around the contents (or payload) of a subsequent protocol.
More broadly defined, encapsulation is a method of logically separating functions in a network from their underlying structures (e.g., hardware). All the microsegmentation methods in this section use some form of encapsulation.

### Wireless Networks

By eliminating the dependency on cabling to the endpoint, wireless technologies have expanded networking capabilities significantly. Deploying a wireless network is relatively easy and has become the preference in many home and corporate environments.
With the rapid growth of IoT adoption, the demand for wireless capabilities is consistently increasing.

Wireless networks face the same vulnerabilities, threats, and risks as any cabled network, but they also have additional security considerations.

One of the principal issues with wireless technology is the insecure nature of the technology in the default configuration. For instance, wireless devices are sometimes shipped with default credentials that can be guessed

Wireless networks also face an increased risk of MITM types of eavesdropping and packet sniffing using devices that capture and read data emanating across electromagnetic signals.

Recently, with the proliferation of IoT devices, wireless DDoS attacks have become headline-making attacks of disruption.

#### Wi-Fi

Wi-Fi (or wireless fidelity) is the most common family of wireless protocols today, with Wi-Fi network communications being governed by the IEEE 802.11 family of standards.
Evolutions of the standard are published through amendments that document updated versions of the original standard.
These are highlighted in Table 4.2, and it should be noted that each version or amendment to the 802.11 standard has offered improved maximum data rates.

802.11x is often used to indicate all of the specific implementations as a collective whole, but that is not preferred over a general reference to 802.11.

| STANDARD            | FREQUENCY         | MAX DATA RATE |
|---------------------|-------------------|---------------|
| 802.11              | 2.4 GHz           | 2 Mbps        |
| 802.11a             | 5 GHz             | 54 Mbps       |
| 802.11b             | 2.4 GHz           | 11 Mbps       |
| Wi-Fi 3 (802.11g)   | 2.4 GHz           | 54 Mbps       |
| Wi-Fi 4 (802.11n)   | 2.4 GHz and 5 GHz | 600 Mbps      |
| Wi-Fi 5 (802.11ac)  | 5 GHz             | 3.5 Gbps      |
| Wi-Fi 6 (802.11ax)  | 2.4 GHz and 5 GHz | 9.6 Gbps      |
| Wi-Fi 6E (802.11ax) | 6 GHz             | 9.6 Gbps      |

##### Wired Equivalent Privacy and Wi-Fi Protected Access

Wired Equivalent Privacy (WEP) and Wi-Fi Protected Access (WPA) are the two most used encryption standards for Wi-Fi communications. Today, WEP is considered a highly insecure standard and should not be used.
WPA continues to evolve, with WPA3 being the current standard that should be used to protect Wi-Fi communications.

The IEEE 802.11 standard defines two methods that wireless clients can use to authenticate to WAPs before normal network communications can occur across the wireless link.
These two methods are **open system authentication (OSA)** and **shared key authentication (SKA)**.

* OSA provides no confidentiality or security because no real authentication is required. Communication happens if the radio signal is strong enough to reach a compatible receiver. All OSA transmissions are unencrypted.
* SKA enforces some form of authentication, and if the authentication is not provided, the communication is blocked.
The 802.11 standard defines one optional technique for SKA known as Wired Equivalent Privacy (WEP), with subsequent amendments to the original 802.11 standard adding WiFi Protected Access (WPA), WPA2, WPA3, and other technologies.
WEP, WPA, and WPA2 should all be moved away from in favor of WPA3, wherever possible.

###### Wired Equivalent Privacy (WEP)

WEP was designed to protect against eavesdropping for wireless communications. The initial aim of WEP was to provide the same level of protection against MITM attacks that wired networks have.
WEP implemented encryption of data in wireless transmissions using a Rivest Cipher 4 (RC4) symmetric stream cipher.
Message integrity verification is possible because a hash value is used to verify that received packets weren’t modified or corrupted while in transit. It also can be configured to prevent unauthorized access.
Knowledge or possession of the encryption key provides a basic form of authentication; without the key, access to the network itself is denied. WEP is used at the two lowest layers of the OSI model: the data link and physical layers.
It therefore does not offer end-to-end security.

Over time, WEP has been shown to have major security weaknesses. For instance, WEP uses static encryption keys, the same key used by every device on a wireless network.
It is possible, therefore, that if an eavesdropper intercepted enough encrypted packets, the key could be deduced. In fact, WEP was cracked almost as soon as it was released.
It takes less than a minute to hack through WEP protection, yielding WEP completely useless in wireless security.

###### Wi-Fi Protected Access (WPA)

To improve wireless security, a group known as Wi-Fi Alliance developed a new encryption standard called WPA. As a replacement for WEP, WPA could be retrofitted to WEP firmware on wireless NICs designed for WEP already in the computing environment.
That feature proved to be more problematic than it was worth. The required changes to the WAPs were extensive, and hardware replacement was a better option.

WPA was intended as an interim solution until the IEEE published the promised 802.11i standard (discussed in the following section). That process lingered for years, so WPA was implemented independent of the 802.11 amendment.
The WPA protocol implements the **Lightweight Extensible Authentication Protocol (LEAP)** and **Temporal Key Integrity Protocol (TKIP)**, which support a per-packet key that dynamically generates a new 128-bit key for each packet.
WPA negotiates a unique key set with each host. It improves upon the WEP 64-bit or 128-bit encryption key that had to be manually entered on WAPs and devices and did not change.

WPA uses LEAP and TKIP to perform message integrity check, which is designed to prevent an attacker from altering and resending data packets. This replaces the cyclic redundancy check (CRC) that was used by the WEP standard.
CRC’s main flaw was that it did not provide a sufficiently strong data integrity guarantee for the packets it handled.

Researchers have identified a flaw in WPA similar to the weaknesses in WEP. WPA often employs a static yet secret passphrase for authentication. A brute-force attack theoretically can result in a guessed passphrase.
The likelihood of a sufficient passphrase (no fewer than 14 characters) succumbing to this attack is low, but not impossible.

Collaterally, the message integrity check hash function can then be exploited to retrieve the keystream from short strings of packets to use for injection attacks or spoofing.
Basically, attacks specific to WPA - coWPAtty and a GPU-based cracking tool, to name two - have rendered WPA’s security unreliable.
Both the LEAP and TKIP encryption options for WPA are now considered crackable using a variety of available and easy-to-use cracking techniques.

##### WPA2 (or IEEE 802.11i)

The next evolution of Wi-Fi security was WPA2, which replaced WPA. Originally, it was meant to replace WEP, but as mentioned, the 802.11i standard lingered, and WPA was implemented independently.
This amendment deals with the security issues of the original 802.11 standard. WPA2 is backward compatible to WPA.
It provides U.S. government–grade security by implementing the National Institute of Standards and Technology (NIST) FIPS 140-2 compliant AES encryption algorithm and 802.1x-based authentications, and Counter Mode Cipher Block Chaining Message Authentication Code Protocol (CCMP).
There are two versions of WPA2: WPA2-Personal and WPA2-Enterprise.
WPA2-Personal protects unauthorized network access by utilizing a setup password. WPA2-Enterprise verifies network users through a server using Network Access Control (NAC).

The selection of the name WPA2 is because WPA was already published and in widespread use. However, WPA2 is not the second version of WPA. They are distinct and different.
IEEE 802.11i, or WPA2, implemented concepts similar to IPSec to improve encryption and security within the wireless networks.

In late 2018, shortly after the newer WPA3 (discussed next) was announced, researchers identified a weakness in WPA2 that would allow an attacker to steal pre-shared login passwords, eavesdrop on communications, and perform MITM attacks.

##### WPA3

The Wi-Fi Alliance announced WPA3 as a replacement for WPA2 in January 2018. The newer standard uses 192-bit encryption and individualized encryption for each user.
It also offers weak password mitigation and simplified setup processes for devices with no human interface. As of July 2020, any device certified by the Wi-Fi Alliance must support WPA3.
As a standard practice, you should check your wireless-enabled devices to determine which Wi-Fi standards are supported.
If your network is either WEP or WPA, you must upgrade to a WPA2-compatible or preferably WPA3-compatible router to secure your organization’s network.

##### IEEE 802.1X

WPA, WPA2, and WPA3 support the enterprise authentication known as 802.1X/EAP, a standard NAC that is port-based to ensure client access control to network resources.
Effectively, 802.1X is a checking system that allows the wireless network to leverage the existing network infrastructure’s authentication services.
Through the use of 802.1X, other techniques and solutions such as RADIUS, TACACS, certificates, smart cards, token devices, and biometrics can be integrated into wireless networks providing techniques for multifactor authentication.

##### Extensible Authentication Protocol

Extensible Authentication Protocol (EAP) is an authentication framework versus a specific mechanism of authentication. EAP facilitates compatibility with new authentication technologies for existing wireless or point-to-point connection technologies.
More than 40 different EAP methods of authentication are widely supported. These include the wireless methods of LEAP, EAP-TLS, EAP-SIM, EAP-AKA, and EAP-TTLS.
Two significant EAP methods that bear a closer look are Protected Extensible Authentication Protocol (PEAP) and LEAP.

###### Protected Extensible Authentication Protocol

Using a TLS tunnel, PEAP encapsulates EAP methods to provide authentication and, potentially, encryption. Since EAP was originally designed for use over physically isolated channels and hence assumed secured pathways, EAP is usually not encrypted.
So, PEAP can provide encryption for EAP methods.

###### Lightweight Extensible Authentication Protocol

LEAP is a Cisco proprietary alternative to Temporal Key Integrity Protocol (discussed next) for WPA, but it should not be used. An attack tool known as Asleap was released in 2004 that could exploit the ultimately weak protection provided by LEAP.
Use of EAP-TLS is preferred. If LEAP must be used, a complex password is an imperative. LEAP served the purpose of addressing deficiencies in TKIP before the advent of 802.11i/ WPA2.

##### Temporal Key Integrity Protocol

TKIP was designed as the replacement for WEP without requiring replacement of legacy wireless hardware. TKIP was implemented into the 802.11 wireless networking standards within the guidelines of WPA.
TKIP improvements include a key-mixing function that combines the initialization vector (IV) (i.e., a random number) with the secret root key before using that key with RC4 to perform encryption; a sequence counter is used to prevent packet replay attacks, and a strong message integrity check (MIC) is used.

##### Counter Mode with Cipher Block Chaining Message

Authentication Code Protocol CCMP was created to replace WEP and TKIP/WPA. CCMP uses AES with a 128-bit key.
CCMP is the preferred standard security protocol of 802.11 wireless networking indicated by 802.11i. To date, no attacks have yet been successful against the AES/CCMP encryption.
CCMP is the standard encryption mechanism used in WPA2 and WPA3.

#### Securing Wireless Access Points

A wireless access point (WAP), sometimes just referred to as an access point (AP), is a networking device that allows wireless-enabled devices to connect to a wired network.
WAPs connect directly to a wired LAN and then provides wireless connections into that wired LAN using Wi-Fi or other wireless technologies (e.g., Li-Fi).

##### Conducting a Site Survey

Site surveys are useful techniques for both identifying rogue APs and defining the placement, configuration, and documentation of APs.
They are often required for compliance reasons but should generally be conducted on a periodic basis or whenever your physical environment changes.

Rogue WAPs are WAPs that are installed on an otherwise secure network, but without explicit authorization.
These rogue APs make it difficult for organizations to track and monitor their authorized assets, and they also pose security risks to devices that connect and transfer data over them.
Sometimes, a rogue AP is implemented by an employee for a perceived access or performance need. Even more concerning are cases where a malicious attacker installs a rogue AP to try to fool end users to connect to it.
Such attacks harvest credentials, help launch DDoS attacks, or lead to data theft. It is important for security personnel to conduct searches and scans to be on the lookout for these unwanted devices.

A physical walk-through, or site survey, is a way to discover rogue APs in the physical environment. During the site survey, security personnel investigate the presence, strength, and reach of WAPs deployed in an environment, while looking for unsanctioned signals.
As the walk-through is conducted, a normal endpoint client with a wireless NIC can be used to simply detect signals. Another approach is to use one of a variety of wireless intrusion detection devices to scan the environment.

Site surveys also provide operational benefits, as the review helps define optimal placement and configuration and generate documentation for APs. Optimal placement and configuration consist of ensuring sufficient signal strength is available at all locations where access is desired.
At the same time, where access is not wanted, like in public areas or outside of the facility, the signal availability should be minimized or eliminated.
A site survey is useful for evaluating existing wireless network deployments (such as when there is a change in the external environment), planning expansion of current deployments, and planning for future deployments.

##### Determining Wireless Access Placement

Using information determined by site surveys, optimal WAP locations can be identified. It is not recommended to commit to specific locations until the placements are informed by the walk-through.
Conduct the proper testing of configurations and signal strength with multiple WAPs in place. There will most likely be movements and adjustments in this phase. Once an optimal configuration and location pattern is reached, make the locations permanent.

Here are some general considerations for wireless access placement:
* Use a central location.
* Avoid solid physical obstructions.
* Avoid reflective or other flat metal surfaces.
* Avoid the use of electrical equipment (interference).
* Position external omnidirectional antennas pointing vertically.
* Point a directional antenna toward the area of desired use.

An essential consideration for wireless technology is the impact of the environment on the broadcast signal. Wireless signals are impacted by various types of interference - physical and electromagnetic.
Distance and obstructions are physical concerns. Electricity and other radio signals can conflict with or impede the effectiveness of the wireless signals.
Network administrators will manipulate directional antennas and tune signal strength to accommodate the physical and electromagnetic obstacles to reach the desired areas of access.

A primary security concern for antennas is understanding how the signal pattern (or lobe pattern) extends from the antenna.
This is particularly true with directional antennas where the lobe reaches far beyond the typical unidirectional antenna in one focused direction while being attenuated (i.e., reduced) in the other directions.
Even without special equipment, one can walk concentric circles around an AP and use a mobile device to measure radiation strength.

##### Antenna Types

The antenna is an integral component in wireless communication systems. The antenna transforms electrical signals into radio waves, and vice versa. Signal transmission requirements and reception quality dictate the choice of antenna from the various kinds available.
Standard antennas can be upgraded to signal-boosting, stronger antennas.

Some of the most common types of antennas used are as follows:
* The standard straight, pole-dipole, or vertical antenna sends signals in all directions away from the antenna. This radiation pattern is omnidirectional and is the prevalent type of antenna on base stations and endpoint devices.
* Many other types of antennas are directional. Instead of broadcasting in every direction, the signal is focused to one direction.

There are a few key antenna considerations with regard to securing the wireless network. Most importantly, recognize that directional antennas significantly extend the network’s reach in one focused direction. This is the case for both receiving and transmitting.
Therefore, care must be taken in pointing directional antennas such that the network’s visibility and vulnerabilities are not cast out too far.
For choosing antennas and their placement, bear in mind how the broadcast extends well past walls and through floors, particularly when the organization is in a multitenant building.

##### Wireless Channels

Wireless signals are subdivided within a frequency range in increments called channels. These channels are like the lanes on a road or highway. As an example, for the 2.4 GHz frequency, there are 11 channels in the United States, there are 13 in Europe, and there are 17 in Japan.
In the United States, the FCC regulates the frequencies and has allocated 11. In the other countries and jurisdictions, the frequencies are regulated by national or the member states’ union and explains why there are differences in the number of frequencies.

Normally, a wireless connection is a communication signal between an endpoint client and a WAP. This occurs over a single channel.
It is possible to have interference with devices on separate channels when two or more APs are located too closely together or the radio strength of WAPs is too high.

Security professionals should note that channel selection has little to no impact on mitigating wireless risks such as spoofing, jamming, or the visibility of the network.
Instead, channels get chosen to minimize the interference between APs or other Wi-Fi networks outside their control.

##### Infrastructure Mode and Ad Hoc Mode

When deploying wireless networks, WAPs can be deployed in one of two modes: ad hoc or infrastructure. It is generally better to configure WAPs in infrastructure mode rather than ad hoc mode to enforce restrictions supported by the WAPs.
Ad hoc mode allows wireless devices to communicate without centralized control. Infrastructure mode prevents the devices or the NICs from interacting directly.

There are four distinct variants of infrastructure mode:
* **Standalone:** A WAP connects multiple wireless clients to each other but not to any wired resources.
* **Wired extension:** The WAP acts as a connection point, or hub, to link the wireless clients to the wired network.
* **Enterprise extended:** Multiple WAPs, all with the same extended service set identifier (ESSID), are used to connect a large physical area to the same wired network. This allows for physical device movement without losing connection to the ESSID.
* **Bridge:** A wireless connection is used to link two wired networks, often used between floors or buildings when running cables or wires is infeasible or inconvenient.

##### Service Set Identifiers

Anyone who has connected to a wireless network knows to ask for the network name, the technical term for which is SSID. The SSID is that string of characters that identifies the wireless network.
It represents the logical wireless network, not the unique AP, as there can be multiple access points to provide coverage for one or multiple SSIDs.

There are two types of SSID, namely, ESSID and basic service set identifier (BSSID).
An ESSID is the name of a wireless network in infrastructure mode when a wireless base station or WAP is used. A BSSID is the name of a wireless network when in ad hoc or peer-to-peer mode.

In a scenario where multiple different base stations or WAPs are used in infrastructure mode, the BSSID is the MAC address of the base station hosting the ESSID to differentiate multiple base stations in the overall extended wireless network.

In securing the SSID wireless network, regardless of the types, note that the SSID is comparable to the name of a workgroup. When an endpoint client discovers an SSID, the wireless NIC is configured to communicate with the associated closest or strongest WAP.
The SSID has secure access features so that discovery does not necessarily equate to access. There are additional steps before the client can communicate, such as enabling encryption and ensuring that discovered SSIDs are legitimate.
With enabling encryption, the client is required to enter a password to permit access. Ensuring the legitimacy of the SSIDs that clients might see requires the organization to periodically monitor for rogue access points.

###### SSID Broadcast

A step that can be taken to better secure WAPs is to disable the SSID broadcast of the beacon frame. A beacon frame is a special broadcast transmission that the SSID sends regularly from the WAP.
Discovery by end-user clients occurs as any wireless NIC finds this radio signal. In fact, with a detect and connect NIC feature, the connection can be automatic.

Network administrators can disable, or silence, the broadcast; this is recommended as a security best practice. Disabling SSID broadcast makes connection a little more difficult, as the end user must know the SSID address to search.
Keeping the beacon off and the SSID hidden is not foolproof. Attackers have tools to discover SSID via wireless sniffer technology to capture SSID information used in transmissions between wireless clients and the WAPs, as the SSID is still needed to direct packets.
Disabling SSID is a good first step. Hiding the existence of the network is a best practice, but it is not in itself sufficiently strong security.
Not broadcasting the SSID, coupled with using WPA3, will provide a reliable authentication and encryption solution with fewer failed attempts.

##### Using Captive Portals

Captive portals are authentication safeguards for many wireless networks implemented for public use, such as at hotels, restaurants, bars, airports, libraries, and so on. They are a common practice on wired networks, too.
The process is to force a newly connected device to a starting page to establish authorized access. The portal may require input of credentials, payment, or an access code.
It is also a good location to publish or provide a link to privacy policies and acceptable use terms and conditions. If end-user consent for tracking and information collection is required, the captive portal allows for that as well.
Once the end user satisfies the conditions required by the starting page, only then can they communicate across the network.

###### Captive Portal Security

While captive portals offer some security benefits, they may also pose some security risks. Captive portal authentication provides an easy point of entry for malicious actors seeking entry into a user’s device or an organization’s network.
If a captive portal is compromised, it can be used to automatically load malware or execute unauthorized scripts on a victim’s machine.
For this reason, it is essential that you routinely monitor and conduct application scanning of your captive portal applications and infrastructure.

##### MAC Filters

A MAC filter is a list of authorized wireless client MAC addresses that are permitted to access a WAP. Devices not on the list are blocked. The downsides are that the list is difficult to manage and does not scale to large environments with many changes.
There are two approaches to utilizing MAC filters. In one approach, someone, such as a network security analyst or a security professional tasked with securing wireless access, would determine through asset management what devices are permitted to connect.
The other approach would be using a software solution such as intrusion detection. Some access point vendors offer such features, including the ability to detect MAC address spoofing to mitigate the risk of someone forging a known whitelisted MAC.

#### Wireless Attacks

In spite of increasing attention and capability for securing wireless networks, they remain attractive targets for attackers. The types of attacks continue to grow, and many attacks are effective on wired networks as well as wireless ones.
Attacks such as packet sniffing, MITM, and password theft are common to both wireless and wired networks and are discussed earlier in the chapter.
A few types of attacks focus on wireless networks alone, like signal jamming attacks and a special collection of wireless attacks called war driving.

##### Signal Jamming

Signal jamming is the malicious activity of overwhelming a WAP to the extent that legitimate traffic can no longer be processed. Even though this is illegal in most places, there are inexpensive jamming products available for sale online.

##### War Driving

War driving is a bit of a play on words. The term has roots in a form of attack in the 1980s called war dialing, where computers would be used to make large numbers of phone calls searching for modems to exploit.

War driving, in contrast, is when someone, usually in a moving vehicle, actively searches for Wi-Fi wireless networks using wireless network scanning tools. These scanning tools and software are readily available and often free.
When a wireless network appears to be present, the attacker uses the tools to interrogate the wireless interface or a wireless detector to locate wireless network signals.
Once an attacker knows a wireless network is present, they can use sniffers to gather wireless packets for investigation.

The next step in the attack is to discover hidden SSIDs, active IP addresses, valid MAC addresses, and even the authentication mechanism the clients use.
MITM attacks may progress, or the attackers may conduct advanced attacks with specialized tools, like AirCrack and AirSnort, to attempt to break into the connection and gather additional sensitive information.
When using no security protocols or older ones, like WEP and WPA, attackers have very little difficulty being successful.

#### Li-Fi

Li-Fi(short for light fidelity) is a wireless communication technology that uses light to transmit data.
Li-Fi is similar in use to Wi-Fi, except it uses visible, ultraviolet, or infrared light to transfer data, rather than the radio frequency transmission that Wi-Fi technology relies on.

Because Li-Fi uses light for transmission, it cannot transfer data through walls or other physical barriers. As a result, Li-Fi offers a security benefit over Wi-Fi, in that it can be contained within a physical space.
Li-Fi is a disruptive technology that is still not widely adopted, as of this writing.
Li-Fi’s security benefits and speed improvements (roughly 100x the max bandwidth of today’s Wi-Fi) have many projecting mass adoption in the near future and even potentially replacing Wi-Fi in the next 10 years.

#### Bluetooth

Bluetooth is a wireless technology standard that supports point-to-point wireless transmissions over a short distance. In general use, the maximum effective distance is about 30 feet.
However, there are industrial or advanced versions of Bluetooth that can reach 300 feet. Many types of endpoint devices support Bluetooth, such as mobile phones, laptops, printers, radios, and digital personal assistants, along with an increasing number of other IoT devices.

One benefit of Bluetooth is that it does not require base stations, as it is a direct connection between devices. It also requires very little power, which is good for use with the battery-operated end devices that typically feature Bluetooth.

There are also a few downsides. The transmission speed is slower than the 802.11b wireless standard. It conflicts and interferes with existing 802.11b and 802.11g networks as it uses the 2.4 GHz broadcasting spectrum, causing problems for endpoint devices relying on the transmissions.
Another significant downside is Bluetooth’s inherent weakness because of its lack of encryption. Using Bluetooth to create a PAN carries security implications, too, since a PAN most likely has vulnerabilities that are not easily identified by corporate sweeps.
The reason is that a PAN is a nonroutable section or extension of an existing LAN or WAN, so it is not easily assessed.

#### ZigBee

ZigBee is a standard (based on IEEE 802.15.4) for low-cost, low-power, and low-latency wireless communication.
ZigBee’s protocols were designed to be simpler than other wireless technologies (like Wi-Fi) and used in applications that require short-range, lower-bandwidth data transfer.
Common applications include medical data collection, industrial control systems, building automation, home energy monitors, and other home automation uses.

ZigBee’s widespread use in IoT applications has brought a lot of scrutiny over its security. The ZigBee standard includes security features such as access control lists (ACLs), frame counters, and encryption (using 128-bit AES keys).
Despite these security features, the protocol is not without its flaws, as introduced in the “Smart Lightbulb Hack” sidebar in Chapter 3.

### Cellular Networks

Cellular or mobile networks are wireless communications that traverse across cells. The cells are geographically dispersed areas that consist of one or more cell sites or base stations. The cell site or base station is a transceiver fixed to a location.
The user of a cell network uses a portable device over a specific set of radio wave frequencies to connect to the cell site and other cellular devices or the internet.
The standard descriptors to differentiate cellular technology refer to the generation when the technology was introduced. This can be confusing.
For instance, 4G and 5G mean fourth-and fifth-generation, respectively. It does not indicate a specific frequency or signal strength.

| GENERATION         | 3G                          | 4G                     | 5G                     |
|--------------------|-----------------------------|------------------------|------------------------|
| Timeline           | 2002 to 2005                | 2010 to present        | 2018 to present        |
| Messaging features | Graphics and formatted text | Full unified messaging | Full unified messaging |
| Data support       | Packet switched             | Native IPv6            | Native IPv6            |
| Target data rate   | 2 Mbps                      | 1 Gbps                 | 20 Gbps                |

#### 4G and 5G

While 4G has been the leading cellular technology available since about 2010, 5G technology made its limited debut in 2018 and has seen dramatic growth since 2020.
The key difference between 4G and 5G is the tenfold increase in speed provided by the latter. This dramatic speed increase brings new applications to cellular technology and is projected to further advance the growth of IoT technologies in the near future.
More internet-connected devices with greater capabilities means greater attack surface and must be a consideration for CISSPs moving forward.

#### Cellular Security

A security professional should keep some important considerations in mind when it comes to supporting and securing information sent and received in a cellular wireless network.
Since 2G, cellular use has been used for much more than just voice. Cell phones today (smartphones) have higher-level computing power to run applications, transmit text, send images, stream video, and store significant amounts of sensitive data.
For these reasons, communications that need to be secured will need additional technical controls in place. Cellular transactions are not inherently secure. There are numerous tools available for attackers to intercept wireless transmissions.

A common attack scenario uses cell base stations to conduct MITM traffic capture. These attacks can take place whether the cellular connections are to the internet or just between two or more mobile devices.

As a CISSP, you should consider these threats when developing or managing your organization’s bring your own device (BYOD) policies.

### Content Distribution Networks

A content distribution network (CDN), also called a content delivery network, is a collection of resource services, proxy servers, and data centers that are geographically distributed.
The nature of the architecture model is to provide the low latency, high performance, and high availability of content, especially multimedia, e-commerce, and social networking sites across a large (often national or continental) area.
Content is acquired as near to the requesting customer as possible, which results in the lower latency and greater throughput.

CDN content is distributed among many data hosts, not centralized in one location.
While this positively affects availability, given that content distribution mitigates the impact of any one location going offline, the distribution of content among many hosts can also negatively affect confidentiality.

Organizations concerned with regulatory compliance must also be mindful of how content distribution affects their compliance requirements.
Many CDNs provide licensed access to content through a variety of subscriptions or fees for service models, and protecting that licensed content as well as ensuring its legal crossing of borders can be an issue.
Naturally, as data is stored or processed across multiple jurisdictions, the CDN and its users must be aware of how local regulations affect their business and their customers.
