# Networking Configuration

Open the terminal.
First, we must ensure we have sufficient permission. 
The easiest way is running `sudo -i` in the beginning o the terminal.
The password for the lab image is `net123`.

How to test if we are connected to the internet?
We can ping any domain.

Let's start with the theory. 
Imagine we have one computer, some network connection, some computer network, and some other device at the end. What ping does, is we try to send data to that device on the other end. 
If the data reaches the device, and the device doesn't block the protocol (ISNP) we are using for pinging, it will reply with the data back. If we get the data back, if we receive it, we measure how much time it took between sending the data and between receiving it.
If we received it back, it means the network traffic in both directions works.
The time is the ping we mostly see in games.
If we receive the reply we can see we are connected.
If we don't, either the data got blocked, or there is some disconnection in the network structure.

Ping Pong!

What can we ping?
We could ping `google.com`
Trying it, we get an unknown host error.
We could try the `8.8.8.8` - the google DNS service. Most famous IP in the world lol
If we cannot reach it, it's either we are at fault or google is (quite slim)

So we should try pinging `8.8.8.8
Trying it, we get a network is unreachable error.
Can we ping something closer maybe? Computers next to us?
Let's try pinging them. For now, let's skip ahead and we are told our IP, and then we will explain where we got it from.

The IP address is `10.3.44.1XX` where `XX` is the computer ID (sticker).
We get the same error. Since we are not configured yet.
They make us configure everything from the start.
First, let's configure our IP.
Check if we even have an IP using `ifconfig` command.
It says `lo`, local loopback.
The loopback is a virtual interface - every computer has one. It is used for our computer to communicate with ourselves. If we send any traffic to the loopback/localhost, the data never actually leaves our computer. What happens is that our OS sees our traffic and sees that it is meant for us - why would we need to send it to the internet? And then it sends it for us.
This interface should always work. If it doesn't something is very wrong.

Another interfaces we have here we can see with `ifconfig -a`
We see loopback again, the `eth<number>` (cable hole, for putting the ethernet cable in). Additionally, we also might have wlan. Firstly, we will be configuring on `eth0` - it is the interface we will be using mostly.
The red cable on our patch panel is our connection.
Second part from the left is the PC, leftmost is internet, according to the paper.

Then, configure our IP with `ifconfig` again
Our IP address will be in format `10.3.44.1XX`
In my case, `10.3.44.104`.
If we configure the IP address of our neighbor, it means we have two devices with the same IP in the same network. Effectively, we disconnect our neighbor from the internet. You cannot tell which computer will receive the data. Be extra careful when setting the correct IP.

Another thing, we need to specify a mask.
A mask is a number that tells you how big the network is - how many different devices/ip addresses may be active in the network we are connected to. Let's just go with this for now, and run...
`ifconfig eth0 10.3.44.104 netmask 255.255.255.0`

If we now try to ping our neighbor, we should be able to get a reply.
Now that we are able to communicate in the classroom, can we communicate with the internet?
No, because we tried and it didn't work))
Pinging 8.8.8.8, it is still unreachable!

Right now, the computer has an IP address. It is able to communicate in the network it is connected to, the small classroom network. Communicating outside this network, the computer doesn't know how to get to that network. It is unreachable, it doesn't know where to go. We can communicate with the same segment members.

To fix this, we need to use gateways. Gateways are intermediaries - someone we send the data to, if the data is intended for outside our network. There can be multiple gateways for multiple networks. The one we are interested in for now is called Default Gateway, we have maybe heard of before.
It's the gateway we send data to, in the case we don't know where else to send it.
If we do not know where to send it, it goes to default - make it someone else's problem.

How to set up default gateway?
We will use the command `route`.
The computer has something called a routing table. The routing table determines where we send the data - which gateway. What do we want to do with it? We want to add an entry for the default gateway. We run...
`route add default gw <IP>`
Where the IP will be the same for all of us, being `10.3.44.1` 
It is the default gateway of the classroom, the magical device, router.

Once we add the gateway to the routing table, we are able to finally ping `8.8.8.8`.
Right now, default gateway is where we send the data if we don't know what to do with it, and the router serves as the default gateway.

Trying to ping google.com, we see that we still cannot ping it. We need to configure the DNS - Domain Name Service. `google.com` is simply a domain name, for humans, not the actual IP address. DNS converts domain to IP, and IP to domain. 
With unknown host, the computer tells us it does not know the IP belonging to this domain name. 
We need a DNS server. How?
This command is a bit more tricky. We need to open a configuration file in `/etc/resolv.conf`
Side-note, we should really use the tab-auto-completion tool of the terminal.

Our perfect hint that we are in the correct place is the warning at the very top.
We will ignore the warning, and add a new line, the following:
`nameserver 8.8.8.8`

Now we are able to connect to the internet.

In summary, the golden three, the golden standard:
1. We configure our own IP address
2. We set our default gateway
3. We configure our DNS

We will get taught this later in the subject. It does not tell us the IP address, we ask for the IP, and the google DNS server will say it does not know it, and sends the request to some other DNS.

Networking is a mess... It was created by everyone doing it differently and then they came together, tried to standardize (RFC).
In practical life, real life sometimes doesn't match the theory... 

Since networking is hierarchical, we can trickle down to more categories, for example `.cz` websites we may be redirected to Czech DNS servers.

We made it to half of the lab!

We can go over the WireShark app now.
We will be using this tool to analyze traffic as it is coming in and out of the computer. We will be asked for structures and explanations.

In the beginning, it's mostly gibberish. We can ping something, then stop the wireshark recording, and analyze the packets we sent/received.

The arrows on the leftmost tell us what it is included, single packet / chain. For example, for DHCP there will be several.
We may add filters at the top, for example, `ip.addr == 8.8.8.8` (all DNS queries)
Could also do `udp.port == 53` to listen for the DNS port.
Anything that exists beyond 1024 is non standardized. Before it, it is locked/reserved.

If the source is our computer that's the request.
If the destination is our computer that's the response.

Wireshark is overly smart, it combines the query and response together.

Refresh interval is how often to ask the DNS for a new address.
Retry interval, Expire limit, Minimum TTL are also parameters.

Side-note the HTTP port is 80. HTTPS is 443.

Wireshark is a very detailed tool. When we will be using it during the labs, we will get hints during the labs. Some companies think of it is a harmful, dangerous tool, as it needs admin permissions - but if we really need to debug something on the network level, this is our go-to tool.

...

Opening the CISCO app, select any USB, select the upper number, and a terminal will come up. Press enter a few times, and write `en` to elevate privileges.
It looks identical to the bash terminal, but has different functionality. The yellow lines are the ones responsible for this.
If it writes gibberish, sit elsewhere...

Configuring the router does not go over the normal ethernet cables, it goes over the yellow cable. From port 5, to port 7. It connects the router console to the computer (RS232). It is a serial line, using totally different technology. If take it out, it will stop responding.
We are using this opposed to ethernet cables because if we mess something something in the configuration, we cut ourselves from the router; But we cannot break the serial line no matter the amount of wrong configuration.


The netmask will strongly be represented in the first test.
Basically, the network address has two parts. The IP address itself, and the so called mask. The short version, is adding `/24` at the end for example, but the long way is `255.255.255.0` is the exact same.
The first part is called the ADDR NETWORK, it is the lowest IP address in the network range. The mask tells you what's the size of that range - how many IP addresses there are in the range. `/24` has 256 total IP addresses, minus 2, because two are always reserved (network address, lowest - and address of broadcast, the highest one).
It tells us there is 256 total IPs, with 254 being usable.

Connecting things and the netmask, somewhere in the middle of the semester, is 90% of the first test. Week 5, Lab 3.
There is the proseminar videos, there's videos, and there's plenty of material on the internet. Though, careful with internet materials obviously.

The labs are published. It is good if before the lab we read through it.
We can do the whole lab at home using an emulator, and do the whole lab in 15 minutes.
