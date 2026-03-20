We will be doing a bit of IPv6 and then the routing sample test.

IPv6
Larger address space, $2^{128}$, eliminating scarcity.
Internet users are assigned blocks of addresses ($2^{64}$).
...as opposed to at most one unique address per user.
Header is of constant size.
Encrypted.
Header does not contain the checksum.
Syntax of address notation.
Communication in LAN segment and from the local network segment.

The idea was there will be the top level authority, and then the sub-level authorities.
There are almost no free IPv4 addresses now. Unique public addresses need to be paid for.

Other than that, there were some known problems with IPv4 and the creators of IPv6 wanted to fix those.

What remained:
There is still automatic configuration by DHCP.
What changed:
Network interfaces have more than one IPv6 address assigned. Broadcast is replaced by multicast. Protocol ARP disappeared. Stateless configuration.

Syntax.
Hexadecimal notation, pairs of bytes separated by colon.
Maximal prefix. The network prefix, mask size, should not exceed 64 bits. For clients of one network, 64 bits of IPv6 are always available.
`2001:0db8:000:0000:0000:0000:0000:0000:0001/64`
`2001:db8:0:0:0:0:0:1/64`
`2001:db8::1/64`
Information is very concentrated.

Remember hex to binary transcription.

Every 16 bits are separated by a column. There is no mask anymore, there is only the length of the prefix. It can be from `64-48`.

A sequence of zeros can be simplified into a single zero.
If values start with zeros, they can be skipped.
If we have multiple sections of zeros, we can have double column to skip them all.

There is a special IP address, `::`, which means all zeros. 
You already saw the routing table on IPv4. It contained multiple zero IP addresses for a specific reason. If there is no gateway, then there is an IPv4 containing all zeros. The same notation is used for IPv6, but instead of writing the entire notation, we write double column.

We don't lose any information with the skipping as we can always reconstruct it.

Another big change in IPv6 is that each interface can have multiple IP addresses.
- `::1/128` - loopback
- `fe80::/10` - link local range
- `fc00::/7` - unique local address (local network range)
- `ff00::/8` - multicast
- `2000::/3` - global addresses
- `2001:db8::/32` - used for documentation and illustration purposes.

In IPv4, multicast was used only in particular cases. It's a big thing in IPv6.
All devices inside of a network, should be part of a group, which corresponds to the multicast address.
Broadcast is technically back but it works only in local network segments. 

Link local range `fe80::/10`
- Every interface has address from this range
- Allows to communicate in the local network segment without explicit config.
- Address is valid only in LAN
- Address is created automatically from MAC
`00:1e:65:3f:fd:8c` $\rightarrow$ `fe80::21e::65ff:fe3f:fd8c/64`
We can ping this IP address if we are in the same segment.
We should also provide which interface to use for the ping.

Multicast `ff00::/8`
- Special addresses, which allows to reach specific group of interfaces in the same network.
- `ff01:1` - only own interface.
- `ff02::1` - all interfaces in local segment.
- `ff02::2` - all routers in segment.
- `ff02::9` - all routers with dynamic routing.
- `ff02::f` - UPnP servers
- `ff02::fb` - multicast DNS (mDNS)
- `ff02::1:ffXX:XXXX` - solicitation address - for all devices starting with the same bytes.

The multicast should be deliberate to all devices in the segment, and only those who are registered to that group should receive this group.
The entire MAC address range is reserved for multicast addresses `33:33:XX:XX:XX:XX` where `XX:XX:XX:XX` is replaced by the last 4 octets of IPv6 multicast address. Switch send such frame in the same way as broadcast.
Network interface accepts frames, which have destination MAC address. The same as interface MAC address, broadcast, the same as one of the multicast MAC addresses that belong to that interface.

The interface MAC address `00:11:22:33:44:55`
IPv6, link local:
- `fe80::21122ff:fe33:4455`
IPv6 multicast:
- `ff01::1`
- `ff02::1`
- `ff02::1:ff33:4455` - attached to the link local address

This is for neighbor discovery process which replaces ARP.

Accepted MAC addresses (besides own and broadcast):
- `33:33:00:00:00:01`
- `33:33:ff:33:44:55`

ARP was le bad because all devices had to process the message.
Now we process it only with those who are interested/relevant.
That is neighbor discovery, ensuring address uniqueness.

...

ROUTING TABLE

We are working with range `92.144.32.0/20`
Number of network interfaces include: 27, 1394, 42, 165, 2 respectively in all these 5 different networks. We don't care whether it's device/router, etc.

It's /20. it means we have 12 bits to work with for our network. 
To make it interesting, let's see how it looks graphically.
The graphical representation of the space division...

`0|........................................................|2^12`
                         `2^11`
            `2^10`
	`2^9`
In the first network we have 27 devices. We are searching for the first exponent of 2 which is bigger than that. 32, so we need 5 bits.
Then, the prefix is 32-5 = 27.

Let's zoom in.
`0|........................................................|2^9`
	                    `2^8`
	         `2^7`
	  `2^6`
   `2^5`

That little `2^5` is the part we just assigned.
Then the network IP address / mask for the first network is `92.144.32.0/27`
Then the broadcast is `92.144.32.31` ((WHY??))
Highest assignable, but then again, why is it 31?

Then for the big one, we need 1394 devices. Then, the closest exponent of 2 is 2048, so we need 11 bits.
Then, the prefix/mask is 32-11 = /21 

We have to start in the middle of the range now, we will assign `2^11 <-> 2^12`
It then has to be a multiple. So, let's look at the binary. `00100|000`
So that is 32, but it already occupied by the first network. Then, let's change it to `00101|000` which is 40, which we can use. 
Then, the network IP address is `92.144.40.0/21`
Then, the broadcast is... Last three bits need to be flipped to the ones, so it will actually be `92.144.47.255` (all binary ones at the end).

Now, for the third network with 42 devices, the prefix is 6 bits. 
Then, the mask is /26.
That first area is still occupied by the first network, so we will take the place from 
`2^6 <-> 2^7`. Note we still have the `2^5 <-> 2^6` address space free
The first two bytes are the same everywhere, so it's
`922.144. ... . ... / 26`

How do we find the rest of the address?
It starts with 32, because we are back in the first half.
Look at the bit representation.
`92.144.32.64/26`

We cannot have a 1 after the prefix. It has to start on the multiple of the power

In multicast, we don't change anything before the prefix, we only flip everything after the prefix to 1's.

Then, the broadcast is `92.144.32.127/26`

Network 4 has 165 devices, so we need 8 bits to represent it. Then the mask is /24.

The problem is now the first block is occupied, so we need to take the other block `2^8<->2^9` instead of `0<->2^8` 

Then, the last is all zeros, and we have to flip the next bit after the prefix, and we get `92.144.33.0/24` 

Then the broadcast is the same with all the bits after the prefix flipped to 1.
`92.144.33.255`

Now for Network 5 we only need 2 bits. We could start it after `2^5` 
It is placed directly after the first address. 
Then we can take the final address of network 1 and increment by one, and that's where we start, that being `92.144.33.32/30`
Then the broadcast is `92.144.33.35`

xxxxxxxx.xxxxxxxx.xxxxxxxx.xxxxxxxx / 21
xxxxxxxx.xxxxxxxx.xxxxx | xxx . xxxxxxxx / 21

Lowest assignable and highest assignable are network IP address + 1 and broadcast - 1 respectively.

