Last time we talked about communication inside segment.
We will talk about ethernet protocol separately.
We will start with the big picture of how things are connected and then zoom in.

Last time we talked about automatic DHCP configuration, service that is running in the network, **usually** runs on the router, most responsible network device.
However, DHCP can run practically anywhere in the segment.

It automatically assigns IP addresses, subnet masks, default gateways, and DNS server details to devices.

There are 4 messages that have to be exchanged between client and server.
**Discover**: discover where the DHCP service is. We call so everybody can hear us, we broadcast, and then server answers us.
**Offer** - offers us the IP addresses, gateways, etc.
**Request**: In general, anything we send over the network, we don't know whether it reaches the destination or not, so we need to have a confirmation. We see that the person isn't paying attention, but we need to provide some reaction, confirmation. We don't know whether the offer was delivered correctly, so we send the request back, "here is the message you sent, right?". Also, we can ask for a different IP address here. We need to keep the prefix, but we can request some different things than the gateway.
**Acknowledge (ACK)**: Same philosophy as before, sending us back the request we sent and acknowledging that they saved us.

If something fails, after some timeout, we start over from discover.

How do we even discover if we don't have an IP address yet?
We will be broadcasting the discover message. 
The special MAC address for broadcast on the switch is all `f`'s. (`ff:ff:ff:...`)
That's the link layer, what's with the network layer?
DHCP is implemented on 5th layer of ISO. It requires IP header! It needs to have destination IP and source IP. What is the source IP of the discover message? We don't know our IP address yet... It will be filled with all zeros, placeholder. Destination is IP address `255.255.255.255.255` the limited broadcast address. Limited to current segment, accepted by any device in the network.

The network adapter is made to drop automatically message which are not designated to it, as well as some special addresses. Broadcast is one of these addresses. The network adapters accept these messages, and pass this to the OS.
The OS then decides it is not running DHCP, so then it drops it.

Offer, request, and acknowledgement are also sent with broadcast. Why not send unicast toward the MAC address we received? Modern DHCP clients are setting a special flag inside the discover message, saying "send me the answer in broadcast". But, why would we want that? All the devices need to process it and find out it is not designated for them.
Someone could impersonate DHCP and it could be dangerous, and this would mean they cannot hide it from the administrator.
Also, could have a  some other DHCP service that should get the information..

DHCP chooses from a pool of IP addresses, and assigns it to the device.

If a device sets the IP address on his own, and that IP is in the DHCP pool, there could be an issue. Since DHCP sends $3 \times$ ARP pings and if there is no response, then it considers the IP free, and is ready to grant it to some device. However, if we already assign ourselves the IP, we will answer the pings, and then the problem arises.

We cannot two duplicate IP address in the network? Wrong, we can.
It results in undefined behavior, but it can be done locally and cannot be prevented.

Say we have a range (subnet mask of 16) of $2^{16}$. Some range is reserved for static IP addresses. If we have some services, that don't support DHCP, we can reserve a few addresses, and we are not offering or considering them for DHCP.

Anytime we get two discover requests, we only answer one of them at a time, using the transaction ID. The communication will always be unique.


Without the physical connection to the router for DHCP, devices are still capable to communicate with one another within the network segment (around switch). 
There is no DHCP service so there is no authority to provide IP addresses.
After several failed attempts, we randomly choose IP with prefix `169.254.   /16`
Note that these are public IP addresses but it isn't relevant since we are already disconnected from the DHCP service.
We arp-ping the IP addresses to see if they are occupied or not, and we needn't worry about our own address as ARP protocol does not require a source IP.
This is the **link local** backup configuration.

Network adapters' glowing lights indicating there are glowing lights are the first things you check with a faulty network. Then we check the configuration, the IP address with prefix `169.254` is a good indicator that the computer is connected to the network, but DHCP is not reachable.


Communication between segments! Routing!
Our task is to fill out the routing tables of all devices. Remember that they are not only for routers, but also for personal devices. 

Anytime we set an IP address on the network interface, the routing table is filled out, the subnet of that IP address is always filled, and the gateway is the IP address of the device through which the destination is reachable.
For example, `172.22.0.0/16` for dest and all zeros for the gateway, since all devices are able to communicate with it.

The default gateway has destination `0.0.0.0/0`, and its gateway is the closest router. It is used for all messages which do not belong to the same subnet.
If a device wants to communicate with a 'foreign' IP adders, it sends it to the router and hopes it will reach the other router, and then the destination device.

There is always at least one default gateway to reach the rest of the internet.
Most routing tables have gateway of default gateway.
The algorithm handling the routing table...
The destination is what segment we want to actually reach.
The gateway is the halfway zone between these. It is where we have to stop to reach the destination. (?)
The mask is the information - how much bits are considered to be matched with the destination.
Flags tell us the type of a record, not too interesting.
Metric is the information telling us what is the quality of that record/destination. The table is very strange, and can have alternative routes. The same destination can be in the same table several times, though with a different metric. It tells us how fast that route is. The faster routes have a smaller metric.
The routing protocol fills out the metric, they are set externally, maybe by admin.
Maybe the faster path is now slower or unreachable, in which case, we can update it automatically, and the other path may be more convenient.
The other two are pretty much not that useful...
The last one is the interface on which the message is sent out of. `eth0, eth1, eth2...`

You can go from junction to junction, from router to router, it provides the direction of where to go to, in order to reach your final destination.

Most with the biggest prefix mean the network is smaller, and more specific.
First three bytes of the target IP address are compared with the record. If they don't match, we use another record. If they do, we can use this one.

Then, if all records fail, we go to the default gateway, with the smallest mask, the all zeros, the default gateway!!.. It is an automatic match.

When a router does not know what the destination is, it drops the message and sends a message toward the sender, sends ICMP (Internet Control Message Protocol), saying "hey, I don't know where this is."

We finish filling the routing table once everybody can communicate with anybody.

