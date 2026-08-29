HEAD
# Enterprise Network Design Lab

A small enterprise network built and verified in Cisco Packet Tracer, covering VLAN segmentation, inter-VLAN routing, centralized DHCP/DNS, and secure remote management. Built as a hands-on lab to practice enterprise network design and configuration.

## Topology
                     R1-EDGE
                        |
                   SW1-CORE
                 /     |      \
                /      |       \
           VLAN 10  VLAN 20   VLAN 30
            STAFF      IT     SERVERS
              |         |        |
            PCs       PCs    DNS + WEB
              \         |        /
               \________|_______/
                     |
                DHCP + DNS

## Progress

| Phase                | Status |
|-----------------------|--------|
| VLANs                 | ✅ |
| Trunking               | ✅ |
| Inter-VLAN Routing     | ✅ |
| DHCP                   | ✅ |
| DNS                    | ✅ |
| Web Server             | ✅ |
| DNS Resolution         | ✅ |
| SSH Management         | ⬜ |
| ACL Security           | ⬜ |
| OSPF                   | ⬜ |
| STP                    | ⬜ |
| EtherChannel           | ⬜ |
| Port Security          | ⬜ |
| Firewall               | ⬜ |
| Monitoring             | ⬜ |
| Wireshark              | ⬜ |
| Security Testing       | ⬜ |

## Documentation

- [Network Design](docs/01-network-design.md) — topology, VLAN table, IP addressing scheme
- [Phase Log](docs/02-phase-log.md) — detailed build log per phase, with config, verification, and notes
- [Screenshots](docs/screenshots/) — numbered evidence for each build step

## Tools
- Cisco Packet Tracer

## Author
Pawan Sirimanna — [slapy2-0](https://github.com/slapy2-0)

# \# Enterprise Network \& Security Lab

# 

# A Cisco Packet Tracer enterprise network designed and implemented

# to demonstrate networking, security, routing, network services,

# and monitoring concepts.

# 

# \## Project Overview

# 

# This project simulates a small enterprise network with multiple

# departments, servers, network security controls, centralized

# monitoring, and Internet connectivity.

# 

# \## Technologies Used

# 

# \- Cisco Packet Tracer

# \- VLAN

# \- Inter-VLAN Routing

# \- OSPF

# \- DHCP

# \- DNS

# \- HTTP/Web Server

# \- NAT/PAT

# \- ACL

# \- Port Security

# \- STP

# \- EtherChannel

# \- SSH

# \- Syslog

# \- NTP

# 

# \## Network Segmentation

# 

# | VLAN | Purpose | Network |

# |------|---------|---------|

# | 10 | STAFF | 192.168.10.0/24 |

# | 20 | IT | 192.168.20.0/24 |

# | 30 | SERVERS | 192.168.30.0/24 |

# | 99 | MANAGEMENT | 192.168.99.0/24 |

# 

# \## Security Features

# 

# \- VLAN-based network segmentation

# \- Access Control Lists

# \- Port Security

# \- SSH management

# \- Restricted inter-VLAN communication

# \- NAT/PAT

# \- Dedicated management VLAN

# 

# \## Network Services

# 

# \- DHCP

# \- DNS

# \- Web Server

# \- Syslog

# \- NTP

# 

# \## Routing

# 

# OSPF is used between the Layer 3 core switch and the edge router.

# 

# A default route provides connectivity toward the simulated ISP.

# 

# \## Monitoring

# 

# A centralized NMS server is used for:

# 

# \- Syslog collection

# \- NTP synchronization

# 

# \## Testing

# 

# The network was tested for:

# 

# \- Inter-VLAN connectivity

# \- ACL restrictions

# \- Server accessibility

# \- Internet connectivity

# \- NAT translation

# \- OSPF adjacency

# \- Port Security

# \- Syslog

# \- NTP synchronization

# 

# \## Project Status

# 

# Completed

 266c731 (Initial enterprise network lab)
