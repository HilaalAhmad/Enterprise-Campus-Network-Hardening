# Enterprise Multi-Site Hybrid Infrastructure with Multi-Area OSPF & L2/L3 Hardening

[![Cisco Packet Tracer](https://img.shields.io/badge/Cisco-Packet%20Tracer-1ba0d7?style=flat&logo=cisco)](https://www.netacad.com/)
[![Network Architecture](https://img.shields.io/badge/Architecture-3--Tier%20Campus-blue)](#)
[![Security Hardening](https://img.shields.io/badge/Security-L2%20Port%20Security%20%7C%20ACL-red)](#)

An enterprise-grade hybrid campus network topology designed, deployed, and verified in Cisco Packet Tracer. Features hierarchical 3-tier switching/routing, dynamic multi-area OSPF convergence, inter-VLAN SVI routing, perimeter security filtering via extended ACLs, and dynamic NAT/PAT overload.

---

## Architecture Topology

![Enterprise Network Topology](topology.png)

### Key Network Specifications
- **Hierarchical Layout:** Core Layer 3 Switch (Cisco 3560), Border Gateway (Cisco 2911), Branch Gateway (Cisco 2911), Access Layer (Cisco 2960).
- **Dynamic Routing:** Multi-Area OSPFv2 (Backbone Area 0 & Branch Area 1) with dynamic default-route propagation (\default-information originate\).
- **Layer 3 Switching:** Multi-VLAN SVI termination on Cisco Catalyst 3560 with dedicated routed uplink (\
o switchport\).
- **Perimeter Defense:** Edge Extended Access Control Lists (ACLs) mitigating unauthorized cross-segment lateral movement from branch operations to management domains.
- **Layer 2 Security:** 802.1Q trunking with isolated Native VLAN 99, port security with sticky MAC bindings, and violation restriction modes.
- **WAN & Edge Services:** Dynamic Port Address Translation (PAT) translating RFC 1918 subnets (\10.10.0.0/16\) to public IP space for simulated upstream DNS connectivity (\8.8.8.8\).

---

## IP Addressing Schema

| Device | Interface | IP Address | Subnet Mask | Description / Role |
| :--- | :--- | :--- | :--- | :--- |
| **ISP-DNS** | Fa0/0 | \8.8.8.8\ | \255.255.255.0\ | Upstream Public DNS Gateway |
| **HQ-EDGE-R1** | Gi0/1 | \8.8.8.1\ | \255.255.255.0\ | Edge WAN Interface (NAT Outside) |
| **HQ-EDGE-R1** | Gi0/0 | \172.16.1.1\ | \255.255.255.252\ | HQ Core Transit Link (OSPF Area 0) |
| **HQ-EDGE-R1** | Gi0/2 | \192.168.255.1\ | \255.255.255.252\ | Branch P2P Link (OSPF Area 0) |
| **HQ-CORE-SW1**| Gi0/1 | \172.16.1.2\ | \255.255.255.252\ | Routed Uplink to Border Router |
| **HQ-CORE-SW1**| Vlan10 | \10.10.10.1\ | \255.255.255.0\ | SVI Gateway: Management VLAN |
| **HQ-CORE-SW1**| Vlan20 | \10.10.20.1\ | \255.255.255.0\ | SVI Gateway: IT & Engineering VLAN |
| **BRANCH-R2**  | Gi0/0 | \192.168.255.2\ | \255.255.255.252\ | Branch Uplink to HQ |
| **BRANCH-R2**  | Gi0/1 | \10.10.30.1\ | \255.255.255.0\ | Branch Operations LAN Gateway (OSPF Area 1) |

---

## Verification & Hardening Results

1. **Inter-VLAN SVI Convergence:** Sub-millisecond latency round-trips verified between \10.10.10.0/24\ and \10.10.20.0/24\.
2. **NAT / PAT Translation:** Internal RFC 1918 traffic translated to \8.8.8.1\ verifying complete outbound internet connectivity to \8.8.8.8\.
3. **ACL Isolation Verification:** ICMP/TCP probes originating from Branch VLAN 30 directed at HQ Management VLAN 10 administratively prohibited at the edge boundary.
4. **Port Security:** Unauthorized MAC transitions successfully trigger restrict mode with violation logging.

---

## Lab Artifacts Included
- \Enterprise_Campus_OSPF_Hardening.pkt\ (Fully functional Packet Tracer lab file)
- \configs/\ (Modular running-configs for all routers and switches)
