# Software Stuff

## Virtualization

A sandbox enviromenet is used for testing. A virtual Machine Monitor VMM or Hypervisort is used for virutalization. Type 1 hypervisors AKA Bare Metal, are installed directly on hardware. Type 2 AKA Hosted, are installed on top of a already existing OS (Virtual Box).

Virtual Applience: VM with dedicated purpose. Specialized. Datastore: VM Storage device. [See the Manual for all the rest of the VMWare terms and architcture.](https://github.com/Cham0i/Netacad/blob/main/vi_architecture_wp.pdf)

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

The second are Coxial Cables. These cables were primarly used for TV and satellite connections, but now also serve the additional purpose of providing internet connections. They come in the following types:
- BNC
- F-Type
- N-Type

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/Coaxial.jpg)

Lastly, optic fiber cables are the most modern and fastest type of medium. They use light to transfer signals between interfaces. 

Fiber optic cables come in either single mode/laser mode or multimode/LED. Single mode cable cores are 9 microns thick whilst multimode cable cores are around 50 microns thick. Both are coated by 125 micron cladding. Single mode lasers only use one laser and therefore experience less signal loss; they can transmit up to 100Km. Multimode uses multiple lasers and can only transmit up to 500m. Single mode cables will be yellow, while multimode cables can be either orange or aqua color.

Fiber optic cables have multiple connections including:
- Staight Tip (ST) You stick-n-twist this connector
- Lucent Connector (LC) These can some in [simplex or dublex versions](https://community.fs.com/article/simplex-vs-duplex-fiber-optic-cables.html).
- Subscriber Connector (SC)

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/Fiber.jpg)

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

Goodput is almost like throughput, except it excludes useless traffic overhead. It's essentially only the usefull data going to your interface.

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

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/RoutingEntry.png)

Common Codes
- L Local LAN
- C Directly Connected via Interface
- S Static Route
- O Dynamically created using OSPF
- * Default Route

Common Adminstrative Distances (The value is used in routers to rank routes from most preferred to least preferred.)
0. Direct
1. Static
5. EIGRP Summary Route
90. EIGRP Internal
110. OSPF
120. RIP  
170. EIGRP External

The default static route is where packages are automatically routed in case the router doesn't recognize the IP. The default setting is usually to drop the packet.
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

IANA (Internet Assigned Numbers Authority) manages all IPs and allocates to RIR (Reginal Internet Registries). RIR allocates public IPs to ISP (Internet Service Providers) who provide Ipv4 blocks to organizations or other smaller ISPs.

IETF (Internet Engineering Task Force) Documents proposition to Internet rules using RFC (Request for Comment) documents

EIA/TIA establised the T658A and T658B wiring standards.

IEEE (Institute of Electrical and Electronics Engineers) Is in charge of for the LAN standards.
- IEEE 802.11 Concerns Wireless LAN
  - 802.11b AKA WiFi 1, 2.4Ghz, 11mps
  - 802.11a AKA WiFi 2, 5Ghz, 52mps
  - 802.11g AKA WiFi 3, 2.4 Ghz, 54mps
  - 802.11n AKA WiFi 4 or Wireless N, Uses multiple signals and antenas, 600mps
  - 802.11ac AKA WiFi 5, 2.4 and 5Ghz, 1300mps
 
*Although WiFi 1 and 2 were developed at the same time, WiFi 2 was more popular due to its affordability.
    
- IEEE 802.15 Concerns Wireless PAN (Personal Area Network). This has low range, but also low power use. Associate this with Bluetooth
  - IEEE 802.15.4 Concerns [Zigbee](https://www.techradar.com/news/what-is-zigbee-and-why-its-a-must-have-for-your-smart-home)
- IEEE 802.16 Concerns [WiMAX](https://www.lifewire.com/wimax-wireless-networking-818321)

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

Shell is CLI or GUI requests from user to computer. Kernal communicates hardware and software; manages how resources meet software requirements. Terminal Emulation; Putty.

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


### Fucking Fundamenetals

To require a 'long' password
<pre>security passwords min-length (length of characters)</pre>

To deter brute force attacks.
<pre>login block-for (seconds blocked) attempts (max number of attempts) within (period of seconds that trigger the block)</pre>

To edit how long a session lasts before reverting to user EXEC mode
<pre>exec-timeout (min) (sec)</pre>
(Psst. 'exec-timeout 0 0' is how you disable timeouts. This is done under console or VTY)

Stops the annoying cable messages from appearing
<pre>logging synchronous</pre>
(This is done under console or VTY)

### Inter-VLAN routing

Create vlans in your switch
<pre>vlan ()
name ()</pre>

Assign IP to VLAN
<pre>(Nah you should know this by now. Scroll up nerd)</pre>

To make interfaces into access (only between end-devices and switches). Remember to use "int range" if you need to edit multiple interfaces. 
<pre>int (f0/1,2,3,etc.)
switchport mode access
switchport access vlan (the vlan number this int belongs to)</pre>

To make interfaces into trunks. Only use for interfaces between switches, on VOIP, or switch to Router when sub-interfaces are involved.
<pre>switchport mode trunk
switchport trunk allowed vlan (VLAN numbers here "10,20,999" etc.)
switchport native vlan (NativeVLAN Number here)</pre>
The "native VLAN mismatch discovered" error happens when the native VLANs are not the same between interfaces. You might not even have to use the last command if no Native VLAN is present

Troubleshooting *Check yourself before yo wreck yourself*
<pre>show vlan
show int trunk
show int (f0/x) switchport
</pre>

To make the VLANs talk amongst each other, configure the router using sub interfaces
<pre>int (f0/1.X  X is typically the vlan number)
encapsulation dot1q (vlan number)
ip add (IP) (SM)</pre>
Remember to "no shut" the phyiscal interfaces that supports the sub interfaces. (f0/1 or f0/2 or whatever)

Lastly, remember to use the Management VLAN sub interface as the "ip default-gateway"

### Port Security

ALWAYS SHUT BEFORE YOU ENABLE PORT SEC!!!!!
<pre>int ()
shut</pre>

Now we may begin. Do this to enable port security
<pre>switchport port-security</pre>
If the port is dynamic and you can't enable port security, that means the port hasn't been configured to access mode. See above.

If you need a different maximum amount of MAC addresses
<pre>switch port-security maximum (max number of MACs recorded) </pre>

To actually add MACs you can either do it manually...
<pre>switchport port-security mac-address (MAC of int)</pre>
Use "ipconfig /all" to find the MAC address of a PC int or "ip int ()" for cisco device int

or have it read automatically
<pre>switchport port-security mac-address sticky</pre>

Use whichever method is instructed. Remember adding "no" before any command, erases that command from the run.conf. Example "no switchport port-security mac-address x.x.x" deletes x.x.x from the MAC list

Troubleshooting
<pre>show port-security
show port-security address
show port-security int ()</pre>

### DHCP
Configure the IP,SM, DG as if the DHCP server was actually part of that VLAN. Yet for the IP address of the physical server, configure it based on the network its actually in.

***There are two types of servers in this world, ones that ping and ones that don't. You ping.***

Remember how routers halt broadcasts? So how will your screaming computer infant find its DHCP mother on the other side of the router? Tell your interface to make an exception using this command:
<pre>ip helper-address (IP of the DHCP server)</pre>
This command is done on the int/sub-int of the router facing the LAN that needs DHCP services.

### Routing

Turn the thing off, install the HWICK2T on the right slot, and turn it back on.

There are two ends to the red lightning! The CDE end and the DCT end. The CDE end, which has a clock, is the end where you need to set the clock rate. Clicking on the CDE cable means that it will connect the cable as a CDE end for the first connection and DCT to the second connection. Vise versa.
<pre>int (s0/0/X)
clock rate (usually "128000")</pre>

Getting into routing configuration
<pre>router ospf (ProcessID)</pre>
Set your router's ID
<pre>router-id (IP)</pre>
Use this command if it doesn't let you change the router ID. (This only happens if you advertise your networks first. Which is why you wanna set the router ID first)
<pre>do clear ip ospf process</pre>
Advertise your adjecent networks
<pre>network (ip) (wc) area (AreaID)</pre>

Disable OSPF updates to the interfaces which don't face other routers. This is to prevent OSPF from needlessly searching for other routers past that interface.
<pre>passive-interface (int/sub-int)</pre>

Configure a default static route using this command
<pre>ip route 0.0.0.0 0.0.0.0 (int. Usually a loopback)</pre>
This is making a static route with an IP whos subnet mask makes the entire IP a Host IP (and thus cannot discriminate based on Network ID). In essence, saying "send every fucken IP you don't recognize to this interface."

To share this default route to your other router friends! The router will take the other router's unknown packets and deal with them...(using the above command)
<pre>default-information originate</pre>

All my homies hate Cisco Discovery Protocol (CDP) (because it broadcasts information to other Cisco products, which is a security concern)
<pre>no cdp run</pre>
That one disables it globally. If you only need to do it on a specific interfaces use the following:
<pre>int ()
no cdp enable</pre>

Troubleshooting
<pre>show ip route
show ip route static
show ip ospf neighbor
show cdp neighbors</pre>
You can also try "ping" or "tracert" on PCs to find out which router is the OP.

### Access Control List (ACL)

To add things to an access list. Running this command the first time will automatically create the access list if not created previously.
<pre>access-list (ListNumber) (permit/deny) (IP) (WC)</pre>
Remember that every access list implicitly ends with a "deny any", which is fine if you're making a white list (permit access to certain IPs). However, be sure to add the following command if you are making a black list (deny access to certain IPs)
<pre>access-list (ListNumber) permit any</pre>

Apply the ACL to the interface. On the test, this will mean having the ACL outbound from the sub-interface you are tring to protect. (You might wanna ping from the IP getting #cancelled to the one filing a restraining order before adding this command.)
<pre>int ()
ip access-group (ListNumber) (outbound/inbound)</pre>
If you try the same ping again after using this command and you get hit with a "Reply from Router: Destination host unreachable." Congrats! The restraining order works.

troubleshooting
<pre>show access-list (ListNumber)
show ip int ()</pre>
Look on the 9th line down titled: "Outgoing access list is X"

### Network Address Translation (NAT)

A Inside local IP turns into a Inside Global IP, which communicates with a Outside Global and potentially to a Outside Local. Another way to look at it is that Local means Private and Global means Public; whilst Inside means your LAN and Outside means someone else's LAN. There are three types of ways to translate a Inside Local IP to a Inside Global IP: Static NAT, Dynamic NAT, and PAT/NAT Overload. 

*Configuring a Static NAT*

With Static NAT, every local IP is manually configured to use a certain global IP. 

*Configuring a Dynamic NAT*

Global IPs are randomly assigned to Local IPs inside your network based on a preconfigured list/pool of Global addresses. Almost like DCHP, but for addresses outside your LAN

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/NAT.jpg)

Create the access list that will allow the private IPs to dance around
<pre>access-list (ListNumber) permit (PrivateIP) (WC)</pre>

Find the Private IPs an extroverted partner (Public IP). The Public IPs will do all the talking if the Private IPs need something beyond the LAN (or past the router).
<pre>ip nat pool (PoolName) (PublicIPMin) (PublicIPMax) netmask (SM)</pre>
Basically the router will choose a Public IP within this Pool, from the ranges of X to Y, and use it to represent a specific Private IP when packets are sent past the router. Remember that the PoolName is case sensitive, capitalization matters.

Determine which interfaces face the Private IP LAN and which ones face the scary outside world. For the LAN use:
<pre>int (sub-int most likely)
ip nat in</pre>
For the horrors of the outside world ("WAN") use:
<pre>int ()
ip nat out</pre>

*Configuring PAT/ NAT Overload*

Port Address Translation/ NAT Overload uses sockets to differentiate between multiple Local addresses using the same Global address. Port numbers (just like in minecraft.)

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/Minecraft.jpg)

(If you and your brother hosted Minecraft servers at the same time, using PAT, both of your servers would have the SAME global IP. However your friends would use one port number and your brother's friends would connect using another port number)

It is the same way as Dynamic NAT except you add "overload" to this command:
<pre>ip nat pool (PoolName) (PublicIPMin) (PublicIPMax) netmask (SM) overload</pre>

Troubleshooting:
Ping the loopback located outside the LAN and the use this command to verify:
<pre>show ip nat translations</pre>

To be continued...
