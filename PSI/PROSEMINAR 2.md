New territory, kinda.
Premier for this networking class.
Configuration of all devices in GNS3.

We usually use `ip` instead of `ifconfig`, but the old images do not support that command, so in the labs we use the latter.

They want us to remember concepts rather than commands mostly.
It will not be on the exam. The theory mostly will.

`ifconfig -a` will show all the interfaces in the system, though most of them might be turned off by default. Without the flag, it shows only UP interfaces.

`ifconfig`, followed by the name of the interface, say `eth0`, then the IP address (given by the administrator of the lab), followed by the mask.
For example, we could write.
`ifconfig eth0 10.3.44.101 netmask 255.255.255.0`
This is long-hand for `ifconfig eth0 10.3.44.101/24`

`ifconfig` also shows us other details like MTU - Maximum Transition Unit, which is the maximum size of a packet. It shows us information about the link layer, IPv4, IPv6, 

Let's take a look at the routing table. Through command `route -n`
In the beginning, it contains only one line.
Reminder, it will compare the first bytes with respect to the subnet mask in the routing table when we do the ping.

The wire was the problem. Need to connect it before doing the whole ifconfig and pinging shit. The rest of the proseminar is lost in time. Eat shit.

CISCO's ping is different. Dots mean timeout, exclamation means proper ping.
For CISCO routers they have very tight timeout. The first ping usually fails.

DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH DEATH 