
# Security of Computer Networks

...later, anynonymization in the networks.

...

The system security is only as strong as the weakest point - the user.
There are a lot of techniques which allow to hide communication, identity, and prevention methods against people getting in to your systems.

#### Firewall
A device that controls: passes, filters (sometimes modifies network traffic.) The specific firewall activity for a specific type of network traffic is defined by firewall rules.

The firewall acts as a barrier that separates the trusted network traffic of the internal network from the untrusted network traffic originating from the external network or the internet.
The ultimate goal is to allow some traffic, and deny other traffic, as set by the administrator or software.

Does not need to be between internal and external, could be in-between segments.

#### Common corporate network architecture

includes DMZ, the demilitarized zone, a part of the computer that is partially or fully accessible from the external network. It hosts servers that make a certain  service available to any users, such as websites or mail forwarding. 
Intranet is an internal part of the network that is accessible only to authorized users, e.g. file sharing server, non-public websites, etc.

Don't think the private network is secure. Don't rely on it being secure. 
Should put a firewall between internal segments too.

Doubling everything is a measure taking when ensuring the logistics never stop, even if a component ceases to work for a while. For example, using two ISP's instead of a single one - big companies may use more than one ISP to ensure they are not bottlenecked in case of outage.
The disadvantage is cost.

You technically could toggle between them to save the cost, but it takes time and generally awkward. If you need to make sure everything is available, then you need them both to be turned on. Depends on the situation and how critical it is.

// Contact Alex Mouxa for more details and recommendations. ST1 !!

#### Firewall Types

**Stateless (Packet filter)**
- Work with network and transport layer information
- Evaluate network traffic based on the source and destination IP/port and other field
- Maintains an access-control list of properties and actions to be applied.
- Most basic type. Does not remember, just filters.
**Stateful**
- Work with transport layer information
- The configuration is more complex, requires knowledge of specific transport layer protocols.
- Keeps track of TCP streams, UDP datagrams and ICMP messages.
- Needs to remember the state. If the connection is not closed properly, it should handle it respectively. Becomes complex.
**Application / Proxy**
- Devices or programs that control and forward traffic between the source station and the destination server.
- All communication takes place via the application layer protocols (e.g. HTTP/S)
- Never communicates with the destination directly, has a proxy in the middle. It is combined with a stateless firewall too.
- The source station (SS) passes the request to the application firewall (AF) via the application protocol. AF copies the request, sets up itself as the originator of the request, and contacts the destination server (DS). DS returns a response to AF. AF forwards the response to SS.

The latter can be used to block access to websites, for example.
It is also capable of caching. The answer from the server can be kept in the cache, and if the client asks the same thing twice, we don't need to resend it, we can simply provide it. This advantage isn't used much anymore, as everything on the website is dynamic mostly. This was for old HTML pages for the most part.

A packet firewall analyzes all packets and come to or leave a particular network interface on a given device. Firewalls perform specific actions on packets based on predefined rules, such as enabling, disabling, modifying items in the packet header, or logging. Firewalls on different operating systems work on similar principles, but the way they are configured differs fundamentally.

Allow the essentials and disable the rest is the general rule.
Favor blacklisting over whitelisting.

The well known Linux packet firewall is called `iptables` or `nftables` 

###### DEEP Packet Inspection (DPI)
Part of the stateful firewall. 
Analyzes the packets, the logical communication.
It is not applicable for encrypted protocols such as HTTPS (99% of traffic).

###### Intrusion Detection System (IDS)
An addition to the firewall, between the user and firewall.
Traffic analysis in the IDS detects threats. It does not analyze the communication, like DEEP. However, if there is suspicious traffic, say, suspiciously big, then it may eliminate it.
Stealing mass data from the database, DDOS, etc.
It is the place where we can usually apply machine learning algorithms to try to detect these threats; especially because it's hard to tell what is a threat or what is not.
It usually does not do anything on its own, rather, informs the administrator.

###### Intrusion Prevention System (IPS)
... Missed. I'm assuming it's a more aggressive IDS, communicating and instructing the firewall to block some traffic.

#### Honeypot
Device that serves as bait for an attacker in order to obtain information about him. 
1. A honeypot is placed in the DMZ. Honeypot gives the impression of running a specific network service, such as emails or the web.
2. The attacker who discovers the honeypot tries to attack it.
3. The honeypot records information (e.g. the source IP) about the attacker.
4. The recorded information from the honeypot will then be used by the firewall to create rules that prevent future attacks

For example, port `22` is the secure shell port - the most attacked port in the internet.
If you log into it, you can gain access to the terminal. Depending on the permissions, you can do pretty much anything.

The attacker may install its own software, executables. It can turn the device into a bot, and make it part of the botnet, the set of the devices which were infected.
Additionally, then, that is useful for DDOS attacks.

The graph is INTERNET -> FIREWALL -> DMZ -> FIREWALL -> INTRANET

The vector of attack can be usually infecting one of the DMZ servers. Therefore, the honeypot is not ruined by being placed in the DMZ. i.e. it won't stop.
Most attacks of the intranet are not exploiting firewalls, rather, exploiting humans.

The preparation for the attack is infecting as many devices and placing them in the botnet. Companies could be targeted by some automated scripts, but, they are secured enough to prevent scripted attack.
Scripted as in: "Go through this set of IP addresses, and try to connect to the shell port. If the port is open, try to authenticate as this list of predefined users, and for every user try every password from this list of passwords."
Dictionary attack, essentially.
The webcameras are exploited most of the time. See the `insecam` website.

// The Japanese are very hackable.

Scrubbing center mentioned.

#### Typical Attacks
**Port Scanning** is the discovery of services running on a given computer, useful for launching another specifically targeted attack.
Port scanning is performed by establishing a connection (TCP) or sending groups of packets (UDP) to the select destination port of the station with a suitable IP address. If the station responds to the request, we speak of an open port, otherwise closed.
Horizontal: Attacker scans a specific port on a computer with different IP addresses.
Vertical: Attacker scans multiple ports on a computer with a single IP address.
Not illegal, perfectly fine to do that.
It's like taking a picture in a public space.

**Password Cracking** takes place via terminal services, `SSH`, `RDP`, `TELNET`.
*Brute Force Attack* : Attacker tries all possible combinations of characters for the given alphabet.
*Dictionary Attack*: Attacker uses predefined list of passwords that users use frequently.
Firewalls with blacklists and IPS are effective defenses.

For brute force, could use hardware acceleration, run these crackings on the GPU.
It is not efficient at all on SSH and RDP since there is a several second delay.
Not feasible.
Dictionary is more feasible, this is mostly used.
Given a database of leaked passwords, someone made analysis, and made a statistic list of most frequent passwords.

If you write your password down somewhere, write some variation of it, not entirely exact. For example, swap all E's with 3's.
In a server, always hash them and use SALT - never plain text!
Take the password, attach the constant word, and then hash it.
It should be placed in the same database as the password themselves.

The hashing algorithm is well known, so it will locally brute force to see what matches.
If the hash matches, then we found the password (even with a different password as long as there's a hash collision). Though, with salt, it adds another layer of obfuscation.

**Denial of Service (DOS)** is an attack implemented to prevent access to the service. Realized by sending a large number of ICMP echo queries, of a large number of TCP-SYN connections (SYN FLOOD).
*Distributed (DDOS)*: DOS versions run simultaneously.
*Reflected/Spoofed (DRDOS)*: combining **IP spoofing** with "reflective" third-party services, turning innocent servers into tools that flood the victim with massive amounts of traffic

Buffer overflow. Sending more information than expected.
If the next part in the memory contains some specific data, we can convince the system to overwrite that data which is placed after us - therefore changing the behavior. It requires a lot of luck and a lot of low level understanding.

Sending *spam* is when the user receives a message from the attacker containing malicious content. The most common type of attack is **Phishing** - an attack to capture a user's identity, e.g. opening a link to a fake login page.
For example, `fit.сvut.cz`. The first `c` is actually cyrillic.
Though, not allowed anymore.

**Malware** is an application that the user downloads or gets uploaded to his device.
The application then performs specific actions without the user's knowledge.
- *Trojan Horse*: malware that most of the time behaves like a normal legitimate application, but also contains irregularly running malicious code.
- *Ransomware*: Malware that encrypts the contents of the hard disk.
- *Spyware*: Malware that tries to read various user information (login/bank details)
- *Adware*: malware that displays advertising offers

Most of them can be detected by antivirus. These are more or less a thing of the past, apparently? 
Antivirus programs and email blacklists are an effective defense.
Looks at the signature of the malware and compares it with virustotal databases.
Have to exploit the time between the malware being new and it being flagged and disabled.

Infecting user stations with malware is an effective mechanism for the possibility of controlling stations in order to carry out a DDOS attack.

The most used type of attacking today is DOS.
The classical, not distributed, is not used at all. It is very hard to generate enough traffic with a single device to interrupt the communication of a server.
Also, if there is only one source, then it's very easy to block.

The original attacker does not perform the attack directly in DDOS.
It uses a Control Master (CM) to infect and control other groups of devices (botnets/zombies). The attacker sends an attack command on the targeted victims via botnets.
Legitimate user does not receive a response from a service running on a destination station due to its network congestion.

An application layer attack is, instead of uploading some pictures, we can send a request to a really complex service. Find the URL containing the biggest data, and then attack over and over. The botnet will try to download that page. Creates most load.

The SYN flood is used a lot, too. The bot only tries to open the connection, sends a TCP SYN request through a fake source. The servers will wait for an ACK which will never come. Additionally, combined with other DDOS methods, we can overwhelm it on several vectors.

The amplification DDOS target servers similar to DNS. Nothing stops us from sending it with a source IP of our victim. Then, the victim gets blamed, and they are sending the answers to the victim, overwhelming him.
This is a particular example of the reflected/spoofed attack.

The prevention is rather hard.
All the techniques work only partially. e.g. blocking ranges
