# Enterprise Network & Security Lab

A Cisco Packet Tracer project simulating a small enterprise network — built to demonstrate practical skills in network segmentation, routing, security controls, network services, and centralized monitoring.

## Overview

This project models a small enterprise environment with multiple departments, a dedicated server segment, layered security controls, centralized monitoring, and Internet connectivity via a simulated ISP. It reflects a realistic design workflow: segmenting traffic by function, securing access at every layer, and validating the result through structured testing.

## Technologies Used

`Cisco Packet Tracer` · `VLAN` · `Inter-VLAN Routing` · `OSPF` · `DHCP` · `DNS` · `HTTP/Web Server` · `NAT/PAT` · `ACL` · `Port Security` · `STP` · `EtherChannel` · `SSH` · `Syslog` · `NTP`

## Network Segmentation

| VLAN | Purpose    | Network          |
|------|------------|------------------|
| 10   | Staff      | 192.168.10.0/24  |
| 20   | IT         | 192.168.20.0/24  |
| 30   | Servers    | 192.168.30.0/24  |
| 99   | Management | 192.168.99.0/24  |

## Security Features

- VLAN-based network segmentation
- Access Control Lists (ACLs) restricting inter-VLAN traffic
- Port Security on access-layer switches
- SSH-only device management
- Dedicated management VLAN, isolated from user traffic
- NAT/PAT for controlled outbound Internet access

## Network Services

- **DHCP** — automated IP addressing per VLAN
- **DNS** — internal name resolution
- **Web Server** — hosted HTTP service
- **Syslog** — centralized event logging
- **NTP** — synchronized device time

## Routing

OSPF runs between the Layer 3 core switch and the edge router, providing dynamic internal routing. A default route from the edge router provides outbound connectivity toward the simulated ISP.

## Monitoring

A centralized NMS (Network Management Server) aggregates:
- Syslog messages from network devices
- NTP synchronization across the topology

## Testing

The network was validated against the following criteria:

- [x] Inter-VLAN connectivity
- [x] ACL enforcement
- [x] Server accessibility
- [x] Internet connectivity via NAT
- [x] OSPF adjacency and route propagation
- [x] Port Security violation handling
- [x] Syslog message delivery
- [x] NTP synchronization

## Project Status

**Completed** ✅
