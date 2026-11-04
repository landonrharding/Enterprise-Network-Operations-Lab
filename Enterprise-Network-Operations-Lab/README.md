
# Enterprise Network Operations & Troubleshooting Lab

## Project Objective

Design, configure, and troubleshoot a simulated multi-site enterprise network using Cisco Packet Tracer. The goal is to demonstrate practical networking skills and develop a structured troubleshooting approach for entry-level NOC Analyst and Network Technician roles.

## Network Design Summary

The network consists of a headquarters (HQ), a branch office, and a simulated Internet connection.

The HQ network is divided into departmental VLANs to separate network traffic. Inter-VLAN routing allows communication between departments, while OSPF provides dynamic routing between HQ and Branch.

DHCP provides automatic IP addressing, NAT/PAT supports external connectivity, and ACLs control access between network segments.

## Network Topology

The diagram below shows the HQ network, Branch network, routers, switches, VLANs, and simulated Internet connection.

![Enterprise Network Topology](01-Network%20Diagram/Network-Topology.png)


### VLAN Configuration

| VLAN | Department |
|------|------------|
| 10 | HR |
| 20 | Sales |
| 30 | IT |
| 40 | Guest |
| 99 | Management |

Branch LAN: 10.20.10.0/24

## Technologies Used

- Cisco Packet Tracer
- VLANs and 802.1Q Trunking
- Inter-VLAN Routing
- DHCP
- OSPF
- NAT/PAT
- Access Control Lists (ACLs)
- Spanning Tree Protocol (STP)
- EtherChannel
- SSH Remote Management

## Network Troubleshooting

Five simulated network incidents were investigated and documented:

1. **VLAN Trunk Failure:** Restored Sales connectivity by correcting the trunk's allowed VLAN list.
2. **DHCP Failure:** Recreated a missing DHCP pool to restore automatic IP addressing.
3. **OSPF Failure:** Corrected a passive-interface configuration to restore OSPF adjacency and learned routes.
4. **NAT Failure:** Restored the NAT outside interface configuration. Internet connectivity was restored, verified through successful ICMP tests and confirmed NAT/PAT translations.
5. **ACL Misconfiguration:** Removed an incorrect ACL to restore Sales-to-HR communication.


### Detailed Incident Reports

- [Incident 1 — Sales VLAN Connectivity Outage](05-Incident-Reports/Incident-1.md)
- [Incident 2 — DHCP Addressing Failure](05-Incident-Reports/Incident-2.md)
- [Incident 3 — OSPF Routing Failure](05-Incident-Reports/Incident-3.md)
- [Incident 4 — Internet Connectivity Failure](05-Incident-Reports/Incident-4.md)
- [Incident 5 — ACL Misconfiguration](05-Incident-Reports/Incident-5.md)

## Project Documentation

- **01-Network Diagram:** Network topology
- **02-IP Addressing:** VLAN, subnet, and addressing plans
- **03-Configurations:** Cisco device configurations
- **04-Screenshots:** Configuration and troubleshooting evidence
- **05-Incident-Reports:** Five documented troubleshooting incidents
- **06-Final-Lab:** Final Cisco Packet Tracer project

### Project Files

- [VLAN and Branch LAN Plan](02-IP-Addressing/VLAN_and_Branch_LAN.pdf)
- [Transit and Overall IP Plan](02-IP-Addressing/Transit_and_Overall_IP_Plan.pdf)
- [Final Packet Tracer Lab](06-Final-Lab/Final-Lab.pkt)

## Final Network Verification

After resolving all five simulated incidents, I performed a final network health check to verify that the network was functioning correctly.

| Technology | Verification | Result |
|---|---|---|
| VLANs | Sales-to-IT connectivity | Passed |
| DHCP | Correct IP configuration assigned | Passed |
| OSPF | FULL adjacency and learned routes | Passed |
| NAT/PAT | Internet ping and NAT translations | Passed |
| ACLs | Guest blocked from HR and Branch; Internet allowed | Passed |
| SSH | Successful remote login | Passed |
| EtherChannel | Port-channel operational (SU) | Passed |
| STP | SW3 confirmed as root bridge | Passed |

**Final Result:** All eight network verification checks passed.

## Lessons Learned

This project strengthened my ability to troubleshoot network connectivity systematically. I practiced identifying affected network segments, testing connectivity, examining device configurations, identifying root causes, implementing fixes, and verifying service restoration.
