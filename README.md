# Cisco NetAcad Essentials

## Getting Online

### Cables/ Physical Mediums

There are three commonly used cables in IT. 

The first are Copper Twisted Pair cables. They can be classified by their shielding, number of pins, and wiring standards.

UTP - Unshielded Twister Pair. They are flexible without any metal shielding to prevent interference. They are primarly used in North America
STP - Shielded Twister Pair. They are more rigid but defend against interference. They are primarly used in Europe or anywhere with lots of interference.

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/UTP_STP.jpeg)

RJ-45 have 8 pins while RJ-11 only have 4 pins. RJ-45 are more common now; RJ-11 are a legacy of the old telephone systems.

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

That's where a switch's MAC Address Table comes into play. Before the advent of switches, a hub would connect LANs that would merely transmit all frames to all interfaces. A NIC would then simply drop all the frames not meant for them; however with many frames being sent at once, NICs would have to individually sort many frames to know which one was meant for them. Now the filtering is done with switches. Switches use MAC tables to record the MAC address of each interface. Once a frame is send to the switch, the switch reads the source MAC and associates it with the interface it came from. Then is reads the frame's destination MAC address and sends the frame only to the corresponding NIC. The switch would only broadcast a frame if it couldn't find an associated MAC address. This device greatly reduced the amount of frames that individual NICs had to sort.

A similar concept is used when routers distribute packets. A router uses Routing Table to determine which interface it should send packet to in order to reach the destination Network. It re-encapsulates an ethernet frame with the source MAC for its own interface and the destination MAC to either another router interface or to the destinations MAC if the interface matches the NID associated with the IP destination. A router can use ARP to find the MAC within a network if it doesn't know the MAC. 

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

Remember the acronym DORA

### VLSM (Variable Length Subnet Mask)

## Home Network Basics

IEEE 802.3 is Ethernet

## Introduction to Cisco Networking

1.Place Devices. Connect unlike devices with copper-straight through and similar devices with Cross-over.
2. Configure basic device settings (assume global configuration mode)
2.1 Configure computers by using IP configuration and inputing IP, SM and DG
2.2 Configure Router using console cable
a. Device name 
> blockcode?
