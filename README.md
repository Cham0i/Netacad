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


Application -Basically the Upper Layer of the OSI model

Internet - The transport layer of the OSI

Network Access - The lower layer of OSI excluding Transport



IEEE 802.3 is Ethernet

A NIC drops any frames not meant for them. Switches gives frames to all ports except the input port. 

A Ethernet frame consists of Destination MAC, Source MAC


Switches communicate via MAC Addresses. All ports have a MAC Address

IEEE (pronounce I triple E)

IANA

IETF (Internet Engineering Task Force) Documents proposition to Internet rules using RFC (Request for Comment) documents

EIA/TIA


- Volunteered data - This is created and explicitly shared by individuals, such as social network profiles. This type of data might include video files, pictures, text or audio files.
- Observed data - This is captured by recording the actions of individuals, such as location data when using cell phones.
- Inferred data - This is data such as a credit score, which is based on analysis of volunteered or observed data.

## Data Communications and Network Services

Hexadecimals -_-
Are written with 0x to indicate hexidecimal. Represents values from 0-15 with 16 characters (0-9, A-F) called hextets. Each hextet represents 4 hexidecimal values. (8,4,2,1)

Ipv6 uses hexadecimals to represent their huge numbers. 
AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA
AAAA:AAAA:AAAA:AAAA:AAAA:AAAA:AAAA:AAAA

Encapsulation is when data is joined with a destination and source address.

Preamble + Start Frame Delimiter + Destination MAC + Source MAC + Length Type + Data +Frame Check Sequence

7 + 1 + 6 + 6 + 2 + 46-1500 + 4

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/EthernetFrame.png)

Hierarchial Network (specificallt distribution layer)

Core;Network's backbone. Highspeed interconnectivity.Examples: Distribution modules, service modules, data centers, and WAN edge

Distribution; Policy-based connectivity and controls

Access; End devices and printers

Routers can divide and contain networks. Segmentation security, location, and logical grouping. Connects layer 3 nets. Routes based on IP's (layer 3).

Routing Table Entry

Type...Network...Port
C, L S, 0, D, Candidate default, 10.0.0.0/8 insert photo here

![alt text](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/RoutingTable.jpg)

The static default route is where packages are automatically routed in case the router doesn't recognize the IP. The default setting is usually to drop the packet.

If host A and B are not in the same Net. Host A will encapsulate the frame with the router's MAC

Router uses Routing Table to determine which interface it should send packet to inorder to reach destination Net (packet) Rebuilds ethernet frame to have source MAC as arouters and detinations IP either to another router interface or to destinations IP MAC (which is found using ARP Address Resolution Protocal table)

RIR allocates public IPs to ISP who provide Ipv4 block to organizations or other smaller ISPS

IANA (Internet Assigned Numbers Authority) manages all IPs and allocates to RIR (Reginal Internet Registries)

Unicast; 0.0.0.0 - 223.255.255.255
Multicast; To specific Pcs. 224.0.0.0 - 239.255.255.255 (Remember PC can have more than one IP address) Video streams RIPv2 (Routing Internet Protocol)
Broadcast; To everyone 255.255.255.255

Default Subnet Classes

Class A; 0.0.0.0/8 - 127.0.0.0/8
16 million host addresses or 50%

Class B; 128.0.0.0/16 - 191.0.0.0/16
65K host addresses or 25%

Class C; 192.0.0.0/24 - 223.255.255.0/24
254 Host addresses or 12.5%

DHCP(Dynamic Host Configuration Protocol)
PC sends Discover (HELP I NEED AN IP!!)
Server responds with IP Address Offer (Do you want this one?)
PC responds with a Request (Yes) Which is done in a broadcast to inform other DHCP that their offers were rejected
Server Acknowledges PC as having an assigned IP

VLSM (Variable Length Subnet Mask)

## Home Network Basics



## Introduction to Cisco Networking

1.Place Devices. Connect unlike devices with copper-straight through and similar devices with Cross-over.
2. Configure basic device settings (assume global configuration mode)
2.1 Configure computers by using IP configuration and inputing IP, SM and DG
2.2 Configure Router using console cable
a. Device name 
> blockcode?
