### Cisco NetAcad Essentials

## Getting Online

# Cables/ Physical Mediums

UTP - Unshielded Twister Pair. Primarly used in USA
STP - Shielfed Twister Pair primarly used in EU
Coxial Cables - The TV/ Satellite cables

[!alttext](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/UTP_STP.jpeg)

RJ-45 have 8 pins while RJ-11 only have 4 pins. RJ-45 are more common now, RJ-11 are a legacy of the old telephone systems.

RJ-45 have two different wiring standards. T-658A and T-658B

[!alttext](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/Rjs.jpg)

IEEE (Pronounced I triple E) sets networking standards.

IETF (Internet Engineering Task Force) Documents proposition to Internet rules using RFC (Request for Comment) documents

EIA/TIA


## Network Protocol and Architecture

# OSI Model

{APP                #Known as the upper layer. Which includes Email, browser, file transfer, DNS, etc
PRESENTATION

SESSION}

{TRANSPORT         #Known as the lower layer. Which includes Firewall, video and voice streams, IP Addressing routing, NICS, Drivers, WAN connectivity frame, Physical mediums, hubs, repeaters, etc

NETWORK

DATA LINK

PHYSICAL}

[!alttext](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/OSI_TCP_Layers.png)

# TCP/IP Model

Application -Basically the Upper Layer of the OSI model

Internet - The transport layer of the OSI

Network Access - The lower layer of OSI excluding Transport

IEEE 802.3 is Ethernet

A NIC drops any frames not meant for them. Switches gives frames to all ports except the input port. 

A Ethernet frame consists of Destination MAC, Source MAC


Switches communicate via MAC Addresses. All ports have a MAC Address

## Data Communications and Network Services

Hexadecimals -_-
Are written with 0x to indicate hexidecimal. Represents values from 0-15 with 16 characters (0-9, A-F) called hextets. Each hextet represents 4 hexidecimal values. (8,4,2,1)

Ipv6 uses hexadecimals to represent their huge numbers. 
AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA-AA
AAAA:AAAA:AAAA:AAAA:AAAA:AAAA:AAAA:AAAA

Encapsulation is when data is joined with a destination and source address.

Preamble + Start Frame Delimiter + Destination MAC + Source MAC + Length Type + Data +Frame Check Sequence

7 + 1 + 6 + 6 + 2 + 46-1500 + 4

[!alttext](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/EthernetFrame.png)

Hierarchial Network (specificallt distribution layer)

Core;Network's backbone. Highspeed interconnectivity.Examples: Distribution modules, service modules, data centers, and WAN edge

Distribution; Policy-based connectivity and controls

Access; End devices and printers

Routers can divide and contain networks. Segmentation security, location, and logical grouping. Connects layer 3 nets. Routes based on IP's (layer 3).

Routing Table Entry

Type...Network...Port
C, L S, 0, D, Candidate default, 10.0.0.0/8 insert photo here

[!alttext](https://github.com/Cham0i/Netacad/blob/main/Netacad_Pics/RoutingTable.jpg)

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
