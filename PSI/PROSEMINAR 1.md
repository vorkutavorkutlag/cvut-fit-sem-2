
We will be using the CISCO standard for definitions.
Routers, Switches, End Devices all have special symbols.

The official definition of the network segment is the part of the network in which the devices work with only data link protocol.
The router is the divider between segments. 
Sometimes we put a switch next to another switch in a diagram, to transfer from one LAN to another LAN in order to increase communication distance.

WiFi is also a network segment. It is both a switch and router(?)

Packet is for network layer.
Opposed to frame, which is for linked layer.
In most cases, frame wraps a packet 

Your ISP may be connected to another ISP, and from their perspective, their network is the LAN. Therefore the thought that "anything beyond the router is the internet" is not objective.


Dividing address space!
An address space is a list of identifiers that we can assign on a computer network. The size of the address space is given in bits.
We will focus on IPv4 protocol.

Each network interface has a unique identifier.
Each network segment has a unique identifier.
The network interface identifier makes it clear to which network segment it belongs.

Every identifier inside the IP address (being separated by the decimal), can be divided into the prefix and the "post-ip"(?). We distribute then according to the need, amount of devices.

Each device in the same network segment should share the prefix. When we have this shared prefix, it can be used as an identifier for the entire segment - A subnet.
The definition is: if we have some address space, and this subspace is called a subnet. It is assigned with this prefix to a segment. Network segment mostly == subnet.

Network mask splits IP address into prefix/network address.
Address of end station (is not used alone)
Network mask is a sequence of binary ones followed by a sequence of zeroes:
- 255.168.128.0
- ....................0000

The highest address in rang represents broadcast address. 
CIDR notation includes a slash and a number after an IP address, to denote how many of the first n bits are used as a mask.

The total number of IP addresses in the range:
- $2^n-2$ 
- where $n$ is the total number of zeroes in ask and two addresses are reserved for address of the network and broadcast.

The prefix cannot be finished by 1. Meaning it is always even.

What?

