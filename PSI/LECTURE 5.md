
IP - Internet Protocol. 
IPv4 is 32 bits long.
The goal is the distinguish stations - source, destination.
IP addresses are organized hierarchically, clustered into groups (segments).
Network addresses are used both within a network segment and between different networks.
The unicast, broadcast, and multicast are types of traffic taken into account.
There exists also the anycast, with the previous example in Lecture 1.
Broadcast is usually used with the highest, last one from the range.
It is not really used with IPv4, even banned in some OS's.

The private IP addresses, on local networks only, include:
- `10.0.0.0/8`
- `172.16.0.0/12`
- `192.168.0.0/16`
Link-Local:
- `169.254.0.0/16`
Loopback, networking layer testing:
- `127.0.0.0/8`
Multicast:
- `244.0.0.0/4`

There is not enough unique IPv4 addresses for all global devices obviously. On the internet, the public ones are unique, and then the private ones are unique only locally.

The most used IP address, usually for routers, comes in the form of `192.168.1.1` .

Class A address = 8 bit mask
Class B address = 16 bit mask
Class C address = 24 bit mask

An IPv4 packet.
The fields which we should remember,
- TTL (Time To Live): represents loop protection. 0 = discard
- Protocol: specifies which upper layer protocol the data should be passed to.
- Header checksum: used to verify whether corruption occurred. Dropped if mismatch
- Source IP Address: The IP address of the network interface that sent the packet.
- Destination IP Address: Address of the interface to which the packet is destined.

The header length (IHL) is counted in the Total Length.
There are some fields for fragmentation.

The checksum is bad design. 
Since TTL is part of the header, it gets recalculated, each decrement.

Without any other tools it's not possible to send a message directly to a device in a private network from the internet. We may send it to its segment and then use other tools to bring it to the specific device in the segment.

The purpose of the router is to forward data between subnets/segments.

It is mandatory to understand the routing table for the exam.

IPv4 supports fragmentation. If we create a communication between two devices, the information needs to be passed between routers. The standard transmission unit (STU), is usually 1,5 KB, 1500 Bytes. 
Though, it can sometimes be smaller. In the case the packet is too big for the STU, the router can fragment the packet. It will split the packet into multiple packets. It preserves the header.
It will have almost an identical header, differing only in the fields regarding the fragmentation.

In general, we don't want routers to waste time with fragmentation. Nowadays, it is mostly turned off, and we should send the packets while keeping in mind the size.
Instead of fragmenting, the routers usually send back the information to the ICMP, saying "decrease the size, please."

It is just me, or is this entire course explaining complex topics, and then dropping the "It is actually entirely useless nowadays and it was a stupid idea to begin with, never do something like this." ? Seriously, I don't get why we do this.

Meaning of private IP addresses, address translation (NAT)
We are skipping it for the class apparently? LOL? WHAT ARE YOU DOING! MAKE UP YOUR MIND! BECAUSE I AM LOSING MINE!

Internet Control Message Protocol (ICMP)
Simple protocol as support for IPv4. It is the protocol for wrapping data of higher levels and it is responsible of delivery of data between endpoints. If the packet is dropped by the router for some reason, or we want to diagnose the network, we have also the diagnostic tools of ICMP.

For example, messages `ICMP REQUEST` and `ICMP REPLY` are used by `ping`.  
ICMP is a sort of debug protocol.

Address Resolution Portal (ARP)
important for the delivery of IP addresses. It gets the MAC address for a specific IP address.

ARP spoofing is a phenomenon that exists due to the simplicity of ARP, and it wasn't made to be very attack-proof. This type of attack can be easily detected and prevented by the switch, as well as sending information to the administrator.
It is a MITM (man in the middle) attack, meaning attacker has access to complete communication between two devices. 
The attacker sends the wrong, hazardous MAC address in response to a request, and the victim proceeds with it thinking it is the MAC address of the IP it inquired for.

Usually it is done by spamming the response constantly, and hoping it catches one time.

// Diffie-Hellman ?

Proxy ARP.
A mechanism that makes the router act like a switch for the source station.
The name is self-explanatory, a proxy for the ARP.
Kind of like ARP spoofing, answering in someone else's name, but le good.
Used for devices that don't have a routing table

