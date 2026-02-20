Network taxonomy.

###### Switching
...how data spreads between two stations.
Circuits (Connection-Oriented) - ATM, Frame-Relay
Circuit = assembled route, 
Packets (Connectionless) - Ethernet (almost everywhere)
Packet = package of sent data.

###### Architecture
Peer-To-Peer (P2P) : decentralized!
Client-Sever : centralized!

###### Use
Public, Private, Hybird

###### According to size
Personal Area Network (PAN) (1m)
Local Area (LAN) (100m)
Urban - Metropolitan Area Network (MAN) (10 km)
Wide Area (WAN) (1000km)

##### Basic Network Topologies
Not too relevant. Star is used most of the time today, centralized. Full connection is too expensive and not worth it most of the time.

###### Types of Links
Simplex: Single-sided send -> receiver.
Full duplex: send1 -> receive1 and send2 -> receive2
Import distinction from half duplex: send1, receive1 -> node1, send2, receive2 -> node2. 
The distinction is, only one transmitter can communicate at a time. Full duplex means both can be sending and receiving bidirectionally all the time, but in half-duplex, the communication, the "right to speak", gets switched between the two transmitters. Sort of like multithreading?

Side-note: ISP = Internet Service Provider

###### Casts
Unicast - communicating with a single server, communication between two devices.
Broadcast - communicating with every device independently.
Mutlicast - Something between broadcast and unicast. Transferring data only to some subset group of receivers. We will see in IPv6. Used in streaming sometimes (switching channel would be subscribing to a different multicast)
Anycast - Several services which offer the same service. They are identical. We don't care which one we use. For example, watching a YouTube video. We send a request for the video. We don't care whether it came from server A, B, C, D... Something in the middle decides which server gets "chosen".

Side-note: Alex Mouka has classes for CISCO, ST1, ST2, teaches modern technologies.

#### Computer Networking Concept Design
The proposal contains 7 hierarchical functionally disjunction levels (layers) that cooperate with each other. Each later has its own specific functions. Each layer provides a different set of protocols for communication, independent from other layers. We may combine different protocols without breaking.

Host Layers:
Application - Data; Network Process to Applications -> HTTP/FTP
Presentation - Presentation; Data representation and encryption -> TLS/XML
Session - Data; Interhost Communication -> RPC, NFS, NETBIOS
Transport - Segments; End-to-End connections and reliability -> TCP/UDP

Media Layers:
Network - Packets; Path Determination and IP (Logical Addressing) -> IP/Internet
Data Link - Frames; MAC and LLC (Physical Addressing) -> Ethernet/LAN
Physical - Bits; Media, Signal and Transmission -> Optic, Metallic, Antennas

Open System Interconnection (OSI) Model, standardized by ISO.

Network layer is responsible for delivering, Transport layer responsible for making sure delivery was correct and uncorrupted. UDP doesn't do confirmations, though..
The transport layer also gives us the context, coming in form of a listening port.

We will be focusing mostly on Data Link, Network, and Transport layers.
The rest are not as important.

#### Encapsulation and Decapsulation of data
Going down the network layers, data becomes encapsulated with more headers/encoding/encryption. It is wrapped in more layers, until it reaches the bottom, Physical, at which point it is transported with bits. Receiving the bits, the other machine begins removing the layers one by one, decapsulating it from the bottom up, until we will have completely unwrapped it.

The switch is the device that works with Data Link and Physical, it is the device which allows to connect multiple devices together into a single LAN network. The Segment is managed by the switch.
The router is the device operating on the network layer, operating with IP addresses. It is responsible for exchanging data between these segments, and also for sending data to other routers.
Each router has a list, routing table, of different destinations. It should know the "path" to the destination. It doesn't know exactly where the goal destination is, but it knows what other devices know where it is.


##### TCP/IP model and addressing

Internet Protocol (IP) is a basic communication protocol that allows data to be delivered between stations (nodes). The IP protocol uses a unique identifier (IP address) assigned to a specific station. The address always belongs to a specific Network Interface Controller (NIC).
IP is hierarchical, has a logical structure.

The TCP/IP model is more compacted than the OSI model. 
Application - Data
Transport - Segments
Internet - Packets
Network Interface - Bits and Frames

IP addressing concept.
The main motivation for addressing is the assignment of names for all computers in the network according to some scheme.
