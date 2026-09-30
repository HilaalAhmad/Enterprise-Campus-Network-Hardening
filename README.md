Enterprise Multi-Site Hybrid Infrastructure with Multi-Area OSPF & L2/L3 Hardening

Project Overview

Designed, deployed, configured, and verified an enterprise-grade multi-site hybrid network infrastructure in Cisco Packet Tracer. The project implements a hierarchical 3-Tier Campus Architecture with Layer 3 switching, Inter-VLAN routing, Multi-Area OSPF, NAT/PAT, Extended ACLs, and Layer 2 security hardening.

Network Architecture

* 3-Tier Enterprise Campus Architecture
* Cisco Catalyst 3560 Layer 3 Core Switch
* Cisco Catalyst 2960 Access Switches
* Cisco 2911 Edge and Branch Routers
* Multi-site HQ and Branch network connectivity
* Routed Layer 3 uplinks between core and edge devices
* 802.1Q VLAN trunking

Routing & Layer 3 Technologies

* Multi-Area OSPFv2
* OSPF Backbone Area 0
* OSPF Branch Area 1
* Inter-VLAN routing using SVIs
* Dynamic default-route propagation using default-information originate
* Point-to-Point routed links
* Layer 3 switching using no switchport

Network Security & Hardening

* Extended ACLs for inter-segment traffic filtering
* Branch-to-HQ Management VLAN isolation
* Layer 2 port security
* Sticky MAC address learning
* Port-security violation restrict mode
* Isolated Native VLAN 99
* 802.1Q trunk security
* L2/L3 security hardening

WAN, NAT & Edge Services

* Dynamic NAT/PAT overload
* RFC 1918 private address translation
* Simulated public network connectivity
* NAT Outside interface configuration
* Upstream DNS connectivity using 8.8.8.8
* Perimeter traffic filtering at the network edge

IP Addressing

* Management VLAN: 10.10.10.0/24
* IT & Engineering VLAN: 10.10.20.0/24
* Branch Operations VLAN: 10.10.30.0/24
* HQ Core Transit: 172.16.1.0/30
* Branch Point-to-Point Link: 192.168.255.0/30
* Simulated Public Network: 8.8.8.0/24

Verification & Testing

* Verified Inter-VLAN connectivity through SVI gateways
* Verified Multi-Area OSPF neighbor formation and route propagation
* Verified dynamic NAT/PAT translations
* Verified outbound connectivity to the simulated upstream network
* Tested ACL-based isolation between Branch Operations and HQ Management networks
* Verified Layer 2 Port Security violation handling
* Verified restricted unauthorized MAC address behavior

Tools & Technologies

Cisco Packet Tracer
Cisco IOS
OSPFv2
VLANs
802.1Q Trunking
SVI
Inter-VLAN Routing
NAT/PAT
Extended ACL
Port Security
Layer 2 Security
Layer 3 Switching
IPv4 Subnetting
Network Troubleshooting

Project Artifacts

* Enterprise_Campus_OSPF_Hardening.pkt — Fully functional Cisco Packet Tracer lab
* configs/ — Modular running configurations for routers and switches
* topology.png — Enterprise network architecture diagram