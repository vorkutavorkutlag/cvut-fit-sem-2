Communication inside segment - learning of the switch.
Something about how a switch remembers the MAC address.

Every switch has a CAM table, with the destination MAC and the port (in this case, port is related to which device/computer has sent the message(?) (or received?)).

Conflict of MAC addresses.
Each MAC address should be unique from the manufacturing process, but if we want, we can tell the OS when we are sending data outside this card, ignore the MAC address, and use a different one, pretty simply.
For example, if we want to convince the DHCP service to give us more IP addresses, we may use a different MAC address from a virtual machine. 
MAC spoofing in general is pretty useful.

Prevention from checking our device can include swapping our MAC addresses per every connection, so we don't map our movement throughout the networks.

Routing table is the information of each device using the IP address.
Which devices use the routing tables? "Routers, obviously!" And, what else? Every device which uses IP address. Every OS, communicating over the network, has the routing table. It is information not only for the router, for resending messages between segments, but also gives us the information whether the destination address we want to communicate with is placed in our local network segment or somewhere else. Every time we configure the IP address, the OS fills the routing table with info about the local segment.

The default gateway is denoted as both its destination and mask being `0.0.0.0` and then its gateway is the IP address of the router.

The different between MAC and IP addresses is:
MAC is not a logical, it is the address of the physical device. IP is a logical address, configurable, and its meaning is usually given by the position in the network (hierarchy).
Note also MAC is in the link layer.
MAC is called flat, since two addresses that are almost the same, can be very different. So the numbers don't really denote any structure(?).

IP has to be known in order to initiate communication, but not MAC.

We also use ARP, address resolution protocol, which maps IP addresses to MAC addresses. It sends an ARP query, a question that is sent to the network, needs to be delivered to all devices in the network, "Who has {IP}?" The device that has it should answer, and the rest should ignore it.
We need to define the concept of broadcast MAC address. It is the mac address consisting of all binary ones. Meaning, `ff:ff:ff:ff:ff:ff` 
Each switch in the world is implemented like this - when this MAC address arrives on the port, it sends it to all of its ports.

The network adapter accepts only its own MAC address.

When is the time when the OS sends the ARP query, systematically? When this information is not in the ARP table. As in, there is no mapping from the IP to MAC.
We need to update the table.


OS uses IP for end to end communication.
MAC is used to deliver inside a single segment.

The "second one" is not answer for the query, it was already answered.

"Convincing sending information to the internet through your computer"

The command is called `arping`

The ping is the command that sends a message toward a destination, and then the answer is sent back, and the device that sent the message knows that the target device is alive and it can measure the time of the reaction, so you know how much time it takes to communicate.
This command takes IP addresses.

On the contrary, arping uses the ARP protocol to measure that elapsed time and checking if the device is alive. ICMP protocol can sometimes be ignored for security or performance reasons. arping is always answered, since ARP has always to be answered to communicate with any other devices.
Disadvantage is it works only inside the network segment.
Receives IP as argument and sends the ARP query.

Something something DHCP PCX.

