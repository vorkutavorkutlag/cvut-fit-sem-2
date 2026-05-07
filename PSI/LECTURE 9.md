
# VPN
Encapsulation of data in a VPN tunnel.
Carrier protocol, VPN protocol, Encapsulated data.
Carrier protocol is a lower layer protocol that ensures the delivery of VPN protocol packet data.
VPN protocol is the protocol responsible for creating a tunnel.
Encapsulated data is the packets or frames of the original protocol that are transmitted through the tunnel. Encapsulation can be multiple.

This obscures our initial packet's source and destination from ISP & others.
It is encapsulated, then encrypted.

The tunneling protocol does not know what data is sent through the packet. It already has its own TCP-like confirmation measures. So, if there is an inner TCP protocol, there is collision/duplication. 
If we are using TCP for the VPN we are confirming all data twice and all acknowledging the acknowledgements. That's why UDP is usually enough.
If data is lost, then the outer encapsulation saves it.

Privacy is maintained with ISP and similar. Also helps reach blocked services.
Helps bypass geolocks.

Sometimes a web browser keeps the same finger print from in-before the VPN so it is identified the same.

The problem is having to trust a VPN provider.
// In case it will leak data about customers, they are out of business...

ISP will not be able to look inside since we have **asymmetric cryptography**.
Private, Public keys. The trick is, the VPN can provide a public Key to everybody, and everybody can use it to encrypt it, but only one can decrypt it.

We have two keys, if we encrypt it with one key, it can only be encrypted with the other key and vice versa.

We can make a secure connection without compromising the key itself.
Look into certificate authorities.

Quantum computers' computational power may be able to brute-force it, but nothing else.

Point-To-Point Protocol (PPP) data link layer (Layer 2) protocol that establishes a direct connection between two networking nodes, often used for ISP dial-up or router-to-router links

### IPSec Protocol
IP-Secured, works on the network layer.
Strong encryption, good functionality tunneling protocol. Two modes.
To be maximally compatible with IPv6.
It is a sequence of there important phases.
internet Key Exchange (IKE), Authentication Header (AH), Encapsulation Security Payload (ESP).

Tunneling mode = the original IP header is kept and only the data part of the packet is encrypted. The advantage of the transport mode is lower demands on the capacity of the transmission link. This is when we're greedy with bandwidth.
Tunneling mode = the original IP packet is packed and protected in the newly created IP packet. The new packet contains the IP address of the routers between which the tunnel is built. This mode is more demanding the transmission link capacity. It can hide the IP address of the source and destination stations.

### Open VPN Protocol
Application layer protocol that can transmit link frames or packets of the network layer.
VPN is implemented in the operating system through a virtual network interface.
Virtual network interfaces are referred to in the OS as TAP (for link layer) or TUN (for network layer)
Can also make a certificate with a password.
OpenVPN packets are transmitted as UDP or TCP data according to the admin's settings. (don't use TCP if possible. slow!)
OpenVPN can operate in point-to-point or point-to-multi-point mode.
OpenVPN includes implementations for almost all commonly available operating systems and is popular.

Only problem is performance.

### WireGuard

Today's standard, sponsored by Mullvad.
Not used by companies, but good for individuals.
Fastest, but privacy concerns.

...

# The internet is not anonymous.
The browser during interactions on the internet leaves a specific fingerprint.
Browser fingerprint (BF) is a set of specific attributes sent within an HTTP(S) connection by a web browser. These attributes can be used for device identification.
Many services purposefully use BF to customize the content provided.
The partial protection against BF misuse is the use of VPN and PROXY servers but both change only IP, the BF remains the same.
The solution can be VPN + suitable anonymiser or the use of anonymous mode in browser (limitations, e.g. reloading cookies)
Cookies are used to "remember", i.e. make sure you don't have to log in again and again and again. The tokes you are given are stored in the cookie file and are valid for one week. If your web browser remembers it, then you can move it between places, and you will always be logged in.

# Tor and DarkNet

Good service for anonymizing your presence on the internet, but not for everyday use.
Not that secure nowadays, compromised slop.

Uses onion routing. Going through random path over the nodes, several layers of encryption that takes time. Depends how connection between the nods is. If we want, we can check our computer as a node. Interesting swarm-like capabilities.

Changing the source IP address... skipped

# Application Layer...

### Accessing Remote Device.

Telnet. Only use if you know what you're doing. There is no excuse, since TELNET can always be replaced by SSH in every circumstance, which is secure.
There are not known vulnerabilities today. It can be considered as safe.

We can also access the graphical interface with RDP. Though, useless on server side, no need to. 

### File Transfer Protocol - FTP

The original version, without encryption, is pretty much dead today.
Transmitted in TCP. 
Encrypted variant is Secured FTP (SFTP) (not to be confused with FTPS)

Given two Linux devices, use SSH for transmitting files.