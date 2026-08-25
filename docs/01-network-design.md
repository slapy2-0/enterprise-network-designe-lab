# Network Design Document

## Project Overview
This project implements a small enterprise network with segmented VLANs, inter-VLAN routing, centralized DHCP/DNS, and a web server — built and verified in Cisco Packet Tracer.

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



- **R1-EDGE** — edge router, handles inter-VLAN routing (router-on-a-stick or via SW1-CORE SVIs) and external connectivity.
- **SW1-CORE** — core/distribution switch, trunks to access switches, hosts VLAN gateways (SVIs).
- **SW2 / SW3** — access layer switches for STAFF and IT VLANs.
- **Server VLAN** — hosts DHCP, DNS, and the web server.

## VLAN Table

| VLAN ID | Name    | Subnet             | Gateway        | Purpose                          |
|---------|---------|---------------------|-----------------|-----------------------------------|
| 10      | STAFF   | 192.168.10.0/24     | 192.168.10.1    | Staff workstations                |
| 20      | IT      | 192.168.20.0/24     | 192.168.20.1    | IT department workstations        |
| 30      | SERVERS | 192.168.30.0/24     | 192.168.30.1    | DNS, Web server, infrastructure   |

## IP Addressing Scheme

| Device            | Interface        | IP Address        | Notes                        |
|--------------------|-------------------|--------------------|-------------------------------|
| SW1-CORE           | Vlan10            | 192.168.10.1/24    | STAFF gateway (SVI)           |
| SW1-CORE           | Vlan20            | 192.168.20.1/24    | IT gateway (SVI)              |
| SW1-CORE           | Vlan30            | 192.168.30.1/24    | SERVERS gateway (SVI)         |
| DHCP Pool (VLAN10) | —                 | 192.168.10.20 | Assigned to STAFF PCs         |
| DHCP Pool (VLAN20) | —                 | 192.168.20.20 | Assigned to IT PCs            |
| DNS Server         | VLAN30            | 192.168.30.10       | Resolves internal hostnames   |
| Web Server         | VLAN30            | 192.168.30.20       | Hosts internal website        |

*(Fill in the exact DHCP ranges and server IPs from your Packet Tracer config — check screenshots 15, 17–20 for the real values.)*

## Design Notes
- Trunk links carry all VLANs between SW1-CORE and access switches (SW2, SW3).
- Inter-VLAN routing is handled at Layer 3 via SVIs on SW1-CORE.
- DHCP and DNS are centralized in the SERVERS VLAN to simplify management and reflect a typical small-enterprise design.