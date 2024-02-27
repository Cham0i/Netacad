# Software Stuff

## Virtualization

A sandbox enviromenet is used for testing. A virtual Machine Monitor VMM or Hypervisort is used for virutalization. Type 1 hypervisors AKA Bare Metal, are installed directly on hardware. Type 2 AKA Hosted, are installed on top of a already existing OS (Virtual Box).

Virtual Applience: VM with dedicated purpose. Specialized. Datastore: VM Storage device. [See the Manual for all the rest of the VMWare terms and architcture.]()

virtual center(VC): Server that manages hosts, datastore, and VMS w/GUI

5 types of virtualization are; Hardware, Software, Storage (multiple physical hdd apearing as one), Network (Vlans), desktop (virtual desktops)

VMs increase avalibility (always up), management (tracks changes and status of VMs), scalability (ability to quickly grow/ the limit of an infastructure), optimization (effecient use of resources)

BCCS Battle Command Common Services, Tactical Army Command Post. UPS are there to do a successful shutdown, not to keep operating. (Storage + ESXI + UPS)

### RAIDS
0. Stripping (superior i/o performance, diversified across disks)
1. mirroring (copy, costly, fast)
5. stripping w/parity
6. stripping w/ double parity
10. mirroring and stripping 

## VOIP

Cisco Unified Communications Manager (CUCM)/ Call Manager is the software used to manage VOIP. 

# Cisco NetAcad Essentials

## Getting Online

### Cables/ Physical Mediums

There are three commonly used cables in IT. 

The first are Copper Twisted Pair cables. They can be classified by their shielding, number of pins, and wiring standards.

UTP - Unshielded Twister Pair. They are flexible without any metal shielding to prevent interference. They are primarly used in North America
STP - Shielded Twister Pair. They are more rigid but defend against interference. They are primarly used in Europe or anywhere with lots of interference.

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/UTP_STP.jpeg)

RJ-45 have 8 pins while RJ-11 only have 4 pins. RJ-45 are more common now; RJ-11 are a legacy of the old telephone systems

The EIA/TIA established two different wiring standards for the RJ-45s. T-658A and T-658B

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/RJs.jpg)

The second are Coxial Cables. These cables were primarly used for TV and satellite connections, but now also serve the additional purpose of providing internet connections. 

Lastly, optic fiber cables are the most modern and fastest type of medium. They use light to transfer signals between interfaces. 

These mediums have a certain bandwidth. The bandwidth is the maximum amount of data that can be transfered within a second. Higher Categories have higher data transfer rates and more twists per foot (twisted pair cables only) to prevent external electromagnetic interference and radio frequency interference.

- Cat 3 - 10mps/16MHz
- Cat 5 - 100mps/100MHz
- Cat 5e - 1kps/100Mhz
- Cat 6 - 1kps/250MHzro
- Cat 6a - 1kps/500MHz
- Cat 7 - 10Gps/600Mhz
- Coaxial Cable - 100mps
- Fiber Optic - 100Gps

This doesn't mean that data will always transfer at this given rate. Throughput is the actual measure of bits transfered per second. It can be affected by a number of factors including:

- The amount of data being sent and received over the connection
- The types of data being transmitted
- The *latency* (or the amount of time it takes for data to travel) created by the number of network devices encountered between source and destination

### Types of Networks

The most common type of network is a Server-Client network. These networks are centralized and require a group of computers called servers to provide information to client computers. The client computers are usually what we associate computers to be; a client could be a PC (personal computer), a workstation, a phone, a gaming console, etc. The server would be the one to provide services to these client computers such as Netflix streaming servers, Google search servers, school district active directory servers, email servers, multiplayer gaming servers, etc.

Another type of network is a P2P (Peer-to-Peer) network. These networks are decentralized because each computer is simultaneously a server and client. Unfortunately this means there is no central administration to keep the network safe, and its also slower because each computer must actively download and upload files from and to other computers. 

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/p2p.jpg)

### Network Medias

These networks can be connected with different medias.

- Metal wires within cables - Data is encoded into electrical impulses. These include twisted pair and coaxial cables.
- Glass or plastic fibers within cables (fiber-optic cable) - Data is encoded into pulses of light.
- Wireless transmission - Data is encoded via modulation of specific frequencies of electromagnetic waves.

To determine which network media is most apporpriate ask yourself these questions:

- What is the maximum distance that the media can successfully carry a signal?
- What is the enviroment in which the media will be installed?
- What is the amount of data and at what speed must it be transmitted?
- What is the cost of the media and installation?


## Network Protocol and Architecture

### OSI Model and TCP/IP Model

The App, Presentation and Session layers are known as the upper layer. Processes in this layer include email, browser, file transfer, DNS, etc.

The Transport, Data Link, and Physical layers are known as the lower layer. Processes and devices in this layer include Firewall, video and voice streams, IP Addressing routing, NICS, Drivers, WAN connectivity frame, physical mediums, hubs, repeaters, etc

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/OSI_TCP_Layers.png)


Application - Basically the Upper Layer of the OSI model

Internet - The transport layer of the OSI

Network Access - The lower layer of OSI excluding Transport

### Hierarchical Designs

The most effecient way to design a network is to design it as a hierarchy. This way the most local communications are done localy, and only communications that are remote move up the hierarchy. This design has 3 layers:

- Access Layer - This includes multiple end devices connected to a switch. If the switch fails, only the end devices connected to the switch will be affected.
- Distribution Layer - This layer connects multiple LANs in the access layer together. This could mean that they are all a bigger LAN connected by a more powerful switch or simply many LANs together connect by a router. This layer usually deals with policy-based connectivity and controls.
- Core Layer - This layer is the network's backbone. It's essentially a step-up from the distribution layer that provides highspeed interconnectivity, except that there is no other redundancy after it. If this layer fails, the rest of the network will fall. This layer contains the best and fastest switches and routers. Examples: Distribution modules, service modules, data centers, and WAN edge

### Using Routers

Routers can be placed to divide networks for a variety of reasons. A router could be placed to restrict the scope of a broadcast and slowing down a network with excessive broadcasting. A router could also segregate LANS for security reasons, where one LAN has information that is restricted to only certain computers or to hide the IP address of those sensitive devices. A common use of a router is simply to connect LANs that are geographically seperated from each other (AKA the internet). Finally, a router may logically group computers to that each LAN may only access certain printers, servers, resources, etc.

### Encapsulation, Address Resolution Protocol (ARP), MAC Address Table, and Routing Tables 

Encapsulation is when data is joined with a destination and source address. Since every Network Interface Card has a MAC, data can be transported to a specific interface via a switch.

Preamble + Start Frame Delimiter + Destination MAC + Source MAC + Length Type + Data + Frame Check Sequence

7 + 1 + 6 + 6 + 2 + 46-1500 + 4

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/EthernetFrame.png)

Within a LAN, the ethernet frame is distributed by a switch which uses the MAC address to figure out where to send the frame. 

If the MAC address is unknown, but the IP address is known, an interface can use Address Resolution Protocol (ARP) to broadcast a signal to every interface in the LAN looking to match the IP. If one of the interfaces matches the IP, that interface will respond with its MAC address. The original sender can then receive the MAC address and use it to send its packets to that specific MAC.

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/ARP.jpg)

That's where a switch's MAC Address Table comes into play. Before the advent of switches, a hub would connect LANs that would merely transmit all frames to all interfaces. A NIC would then simply drop all the frames not meant for them; however with many frames being sent at once, NICs would have to individually sort many frames to know which one was meant for them. Now the filtering is done with switches. Switches use MAC tables to record the MAC address of each interface. Once a frame is send to the switch, the switch reads the source MAC and associates it with the interface it came from. Then is reads the frame's destination MAC address and sends the frame only to the corresponding NIC. The switch would only broadcast a frame if it couldn't find an associated MAC address. This device greatly reduced the amount of frames that individual NICs had to sort.

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/hubs.png)

A similar concept is used when routers distribute packets. A router uses Routing Table to determine which interface it should send packet to in order to reach the destination Network. It re-encapsulates an ethernet frame with the source MAC for its own interface and the destination MAC to either another router interface or to the destinations MAC if the interface matches the NID associated with the IP destination. A router can use ARP to find the MAC within a network if it doesn't know the MAC.

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/Routing.jpg)

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/RoutingTable.jpg)

The static default route is where packages are automatically routed in case the router doesn't recognize the IP. The default setting is usually to drop the packet.
[You can find additional information about routing protocols here](https://community.cisco.com/t5/networking-knowledge-base/dynamic-routing-protocols-ospf-eigrp-ripv2-is-is-bgp/ta-p/4511577)

### Types of Data
- Volunteered data - This is created and explicitly shared by individuals, such as social network profiles. This type of data might include video files, pictures, text or audio files.
- Observed data - This is captured by recording the actions of individuals, such as location data when using cell phones.
- Inferred data - This is data such as a credit score, which is based on analysis of volunteered or observed data.

### Hexadecimals -_-
Are written with 0x to indicate hexidecimal. Represents values from 0-15 with 16 characters (0-9, A-F) called hextets. Each hextet represents 4 hexidecimal values. (8,4,2,1)

Ipv6 uses hexadecimals to represent their huge numbers. 
AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA
AAAA:AAAA:AAAA:AAAA:AAAA:AAAA:AAAA:AAAA


### Who controls the internet?

IANA

IETF (Internet Engineering Task Force) Documents proposition to Internet rules using RFC (Request for Comment) documents

EIA/TIA

RIR allocates public IPs to ISP who provide Ipv4 block to organizations or other smaller ISPS

IANA (Internet Assigned Numbers Authority) manages all IPs and allocates to RIR (Reginal Internet Registries)

### Classfull, Unicast, Multicast, Broadcast Addressing and Private IPs

These are the default subnet classes. It was orginally the way the internet was supposed to be distributed before it became more dynamic. If you had a specific IP within a class, you would have a certain subnet mask.

- Class A; 0.0.0.0/8 - 127.0.0.0/8 Which contained 16 million host addresses or 50% of the internet
- Class B; 128.0.0.0/16 - 191.0.0.0/16 Which contained 65K host addresses or 25% of the internet
- Class C; 192.0.0.0/24 - 223.255.255.0/24 Which contained 254 Host addresses or 12.5% of the internet

Similarly, certain IPs were reserved for certain types of transmitions.

- Unicast; 0.0.0.0 - 223.255.255.255 or any specific IP in within classes A, B or C
- Multicast; 224.0.0.0 - 239.255.255.255 or to specific computers within a group. (Remember that computers can have more than one IP address) Video streams RIPv2 (Routing Internet Protocol)
- Broadcast; To everyone 255.255.255.255

Lastly, because Ipv4 quickly ran out of usable IPs, private IP addresses were reserved to identify computers within a LAN.

- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

## Data Communications and Network Services

### DHCP(Dynamic Host Configuration Protocol)

- PC sends a Discover message using broadcast IP and MAC addresses (HELP I NEED AN IP!!) 
- Server responds with IP Address Offer message (Do you want to use this IP address?)
- PC responds with a Request message (Yes) Which is also done with a broadcast in order to inform other DHCP servers that their offers were rejected
- Server sends Acknowledgement message to PC for having the assigned IP

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/DHCP.jpg)

Remember the acronym DORA

### VLSM (Variable Length Subnet Mask)

This is where subnets are created around the necessity of any given subnet. Remember to feed the fattest network first, and 2 IPs will always be unusable.
NID1 + 128, 64, 32, 16, 8, 4, 2, or 1 (depending on the amount of IPs needed in a network) = NID2. Subtract 1 from the NID2 to get NID1s broadcast. Subtract another to get the last usable IP. And of course, add 1 to NID1 to get the first usable IP.


### TCP vs UDP

The Transport Control Protocol ensures that all packets are transfered. Services like HTML make use of TCP to ensure that all aspects of a website are transferred accurately.

on the other hand, simply transfers all packets as quickly as possible without regard for packet-loss. It its more suitable for video streaming, and gaming, where missing one frame is acceptable.

### Ports

Well-known ports:

TCP Ports:

- 20 FTP - Used in File Transfering for Data
- 21 FTP - Used in File Transfering for control
- 22 SSH - Secure Shell used for encrypted remote access
- 23 Telnet - Unencrypted remote access
- 25 SMTP - Sends email/attachment from client or server to server
- 53 DNS - Domain Name System finds IP for domain name
- 80 HTTP - HyperTextTransferProtocol webpages without encryption
- 110 POP3 - Retrieves email by downloading and then deletes email off server
- 143 IMAP - Retrieves email but keeps email in server
- 443 HTTPS - webpages with encryption

UDP Ports:

- 53 DNS
- 67 DHCP (server)
- 68 DHCP (client)
- 69 TFTP
- 161 SNMP

URL (Uniform Resource Locator) URN (name) URI (identifier)

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/URL.png)

Registered Ports 1024-49151 are reserved for certain applications. Private Ports 49152-65535 are open for any application to use.

## Home Network Basics

IEEE 802.3 is Ethernet

bluetooth uses 2.4 GHz over short range, low-speed connections

5G uses small cell towers hooked up to wired infastracture. Its 10x faster than DSL (Digital Subscriber Line)

### Wireless Router

Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA) is how devices on routers communicate whilst sharing the wifi channels.
[Read more here](https://www.geeksforgeeks.org/carrier-sense-multiple-access-csma/)

WEP (Wired Equivalent Privacy) uses pre-configured keys for encryption. The problem was that it used the same key across all connections without change. 
In contrast WPA (Wifi Protected Access) uses new keys for each client session. WPA2-PSK doesn't use pre-configured keys and instead generates its keys based on the passphrase.

The default option of any router is to not have any passphrase (AKA Open).
MAC filtering is when an access point uses a predetermined list of MAC addresses to block connection to it.

### Port Fowarding and Triggering

Port fowarding allows a traffic from a port to transmit to a certain NIC. It is static. Uses Sockets (IP; Port#)
Port Triggering does the same, except that incoming ports are only opened once outbound/triggered range are used. It is dynamic.

### Services

Software as a Service (SaaS)

Plataform as a Service (PaaS)

Infastructure as a Service (IaaS)

IT as a Service (ITS)

### Choosing and Starting-up a Switch

- Types of Ports (Will it support twisted pair, fiber optic, coaxial?)
- Speed Requirement (Which type of uplink ports will it have? 10/100 Ethernet? 10/100/1000 Gigabit Ethernet?)
- Expandability (Is the switch modular or fixed?)
- Manageability (Is the switch configurable? Cheap, non-cisco switches are usually plug-n-play)

1. POST (Power On Self Test)
2. Rapid green flashing (good) SYST LED Red (fucked)
3. Loads IOS image unto RAM from in flash memory. IOS image facilitates basic operations
4. Loads Startup-config file unto RAM from NVRAM.

### Parts of a router

Router's NIM (Network Interface Modules) allow routing capabilities to serial, DSL, switch ports, wireless, etc.

Management Interface and AUX ports are simply RJ-45 and USB Console cable connections. They are out-of-band connections. Using SSH or Telnet is considered an in-band connection.

LAN Interfaces are where the Networks or LANS are connected to the router

### Malware

adware is spyware?

## Introduction to Cisco Networking

A keyword is a specific parameter defined by the OS. A arguement is a variable that can be inputed by the user.
Hostname (keyword) TheBestRouterInDaWorld (argument)

- Place Devices. Connect unlike devices with copper-straight through and similar devices with Cross-over.
- Configure basic device settings
- Configure computers by using IP configuration and inputing IP, SM and DG
- Configure Router using console cable (assume global configuration mode)

For clarification () means your input

<pre>enable
config t</pre>
  
a. Device name
<pre>hostname ()</pre>
b. Configure Domain
<pre>ip domain-name (.com,.net,etc.)</pre>
c. Priviledge EXEC password
<pre>enable secret ()</pre>
d. Console and Virtual Terminal passwords
<pre>line Con 0
Password ()
login
exit</pre>

<pre>line vty 0 15
password ()
login
exit</pre>

e. Encrypt login passwords
<pre>service password-encryption</pre>
f.Create local database account 
<pre>username () Secret ()</pre>
g. Configure RSA Key (Use 1024 bits when prompted)
<pre>crypto key generate rsa</pre>
h.Virtual terminal enable ssh and login with local database account
<pre>line vty 0 15
transport input ssh
login local
exit</pre>
i.Switch to SSH version 2
<pre>ip ssh version 2</pre>
j.Configure banner
<pre>banner motd "()"</pre>
k.Configure time
<pre>do clock set hh:mm:ss 2 Jan 2024</pre>
l. Set up interfaces. use "shut" instead of "no shut" if you want the int administratively down
<pre>int (g0/1, f0/1, vlan1, etc.)
ip add (ip) (sm)
description ()
no shut
exit</pre>
Alternatively if you want to configure multiple interfaces (for example Fast ethernet 1-24 and Gigabit ethernet 1)
<pre>int range (f0/1-24,g0/1)</pre>
m. Save running-conf
<pre>exit
copy run start</pre>

For a switch to define a default gateway
<pre>ip default-gateway</pre>
v
