
We will finish network communication stuff and then move onto proper lectures.

The device passes the data to the closest router, and then the router is meant to know how to deliver it.

The routing algorithm can detect malfunctions or other issues in the network and choose a better path to traverse.

The routing table is filled with the destination, gateway, and mask.
When we see the internet symbol (cloud) it implies there is at least one more router in the end somewhere there.

Each router has a rule - don't send the message to the same interface it was sent from. Which means, don't send it back.

The IP protocol header has TTL - Time To Live - which is decreased per every transmission between routers. When it reaches zero, the message is finally dropped. Meant to avoid infinite loops.

Note that the communication of routing tables should be bidirectional. If we send something to a destination, it should also be reachable from the destination back to us.

To limit ourselves to only a few devices, we would think to enlarge the mask so our destinations become smaller. However, CISCO routers do not allow that. What we can do, is change the record on the OTHER router. We make the mask larger, and put the IP address directly to the target device(s).
If the mask is all binary ones, then all bits will be compared with the target device.

If we want to allow more than one device, we have to set the mask to allow some wiggle room. We could also add them manually one after the other with a full mask, but we can change the mask to be `255.255.255.254` instead of `255.255.255.255`

The records in the routing table does not need to necessarily reflect our network. If some subnet is not shown, there may be a reason. Maybe they used aggregation, a clever trick to optimize the routing table by merging destinations.

...

IPs were hierarchical. The most significant bits account for broader regions, and the least significant ones are more specific (geographically). Though, it isn't like this now, and now it is way more random.

...

Switch works according to MAC, we need it, not just IP.

...

The exponent of IPv6 is 4 times bigger than IPv4.
128 as opposed to 32.

IPv6 is entirely unique, but IPv4 can be shared by several users on the internet.
It is returned in hexadecimal values.
