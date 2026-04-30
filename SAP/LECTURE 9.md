Logical Link Layer sublayer is specified in IEEE.
It allows the existence of different protocols, IP, IPX, etc. over a common MAC layer.
It has the task of flow control and error control (using detection and self correcting codes for this.)

Security codes are used for these purposes, e.g. Hamming codes are common. The main idea of these codes is that redundant bits are added to the data bits carrying the information, which allow the transmission error to be detected later or repair.

We are working with frames, not packets, as this is the link layer, not transport layer.
The general frame format includes header, data, and trailer (error detection).
The header initially has a specific sequence of bits according to which the frame is recognized (preamble and start frame delimiter(SFD)).
The end of the frame (interframe gap(IFG)) indicates that the whole frame has arrived.
The end of the frame also contains information for detecting possible errors (checksum).

Devices that work on the link layer are referred to as switches or bridges. The principle of operation of both types is similar.

Something about MTU almost always being "this value".

Two dominant protocols on link layer include Ethernet and WiFi.

### Link (MAC) addresses in Ethernet.
You can identify the type of device/manufacturer in MAC address.
They are defined within MAC layer, commonly called MAC addresses.
The default address size is 48 bits (6 bytes) (MAC 48).
The first three bytes of the address are unique, assigned to a specific manufacturer and can be used to identify a specific device. (OUI)
The remaining three bytes indicate the specific serial number of the device.
Over time, 48 bits of address may not be enough, however depletion of 48 bit MAC addresses is not expected until 2100.
Broadcast address: `FFFFFF FFFFFF`

It is completely flat, there is no hierarchy, the OUI is for identification purposes only.
Ethernet frame format is not needed.
The notation of ethernet technologies is not needed.

UTP is an unshielded Twister Pair. Each pair is carrying the information for one line.
Used with telecommunication cables.

### WiFi
Still link layer, just wireless that uses radio waves.
An electromagnetic (EM) wave is a propagation of electromagnetic field through space at a certain time. The EM wave propagates spatially in two mutually perpendicular planes, we refer to these as the electric and magnetic component of EM waves.
They are useful for carrying data. 
If we have an antenna, it is the source and it is hard to imagine how it works. Imagine water, and imagine slapping the water to create waves, and the intensity and frequency is reflected by the waves that are created. The picture that we can see is a representation/visualization.

Gain is how good an antenna is at transferring information in a certain direction.

Antenna radiation pattern... Read about antennas, good for $A$ students apparently.

Antenna array looks cool.


