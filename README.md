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
