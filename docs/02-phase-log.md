# Phase Log

Running log of each build phase, in order completed. Each entry links to the relevant screenshot(s) in `/docs/screenshots/`.

---

## Phase 1: VLAN Creation ✅
**Goal:** Segment the network into STAFF (10), IT (20), and SERVERS (30) VLANs.
**Config:** Created VLANs 10, 20, 30 on SW1-CORE, SW2, and SW3 using `vlan <id>` / `name <name>`.
**Verification:** `show vlan brief` confirms all three VLANs exist with correct names.
**Screenshots:** 02-sw1-vlans.png, 03-sw2-vlans.png, 04-sw3-vlans.png
**Notes:** —

---

## Phase 2: Access Port Assignment ✅
**Goal:** Assign access switch ports to their correct VLANs.
**Config:** `switchport mode access` + `switchport access vlan <id>` on SW2 (STAFF ports) and SW3 (IT ports).
**Verification:** `show vlan brief` on each switch shows ports correctly grouped under their VLAN.
**Screenshots:** 05-sw2-staff-ports.png, 06-sw3-it-ports.png
**Notes:** —

---

## Phase 3: Trunking ✅
**Goal:** Carry all VLAN traffic between SW1-CORE and the access switches.
**Config:** `switchport mode trunk` + `switchport trunk allowed vlan all` (or explicit VLAN list) on the links between SW1-CORE ↔ SW2 and SW1-CORE ↔ SW3.
**Verification:** `show interfaces trunk` confirms trunk status and allowed VLANs on each link.
**Screenshots:** 07-sw1-trunks.png, 08-sw2-trunk.png, 09-sw3-trunk.png
**Notes:** —

---

## Phase 4: Inter-VLAN Routing ✅
**Goal:** Enable routing between VLAN 10, 20, and 30 so devices in different VLANs can reach each other.
**Config:** Created SVIs on SW1-CORE (`interface vlan 10/20/30`, assigned gateway IPs, `no shutdown`).
**Verification:** `show ip interface brief` shows all VLAN SVIs up/up with correct gateway IPs; successful ping across VLANs.
**Screenshots:** 10-server-vlan.png, 11-router-interface.png, 12-inter-vlan-gateways.png, 13-vlan10-verification.png, 14-all-vlan-gateways.png, 15-server-ip.png, 16-inter-vlan-ping.png
**Notes:** —

---

## Phase 5: DHCP ✅
**Goal:** Automatically assign IP addresses to STAFF and IT VLAN devices.
**Config:** DHCP pools configured for VLAN 10 and VLAN 20 (either on SW1-CORE or a dedicated DHCP server in the SERVERS VLAN), with correct network, default-router, and DNS server options.
**Verification:** PCs in VLAN 10/20 receive IPs automatically via `ipconfig`; `show ip dhcp binding` confirms active leases.
**Screenshots:** 17-staff-dhcp.png, 18-it-dhcp.png, 19-dhcp-bindings.png
**Notes:** —

---

## Phase 6: DNS ✅
**Goal:** Provide internal name resolution for hosts on the network.
**Config:** DNS server configured in the SERVERS VLAN with A records for internal hosts (e.g. web server).
**Verification:** DNS records visible on the server; test resolution confirmed working from a client.
**Screenshots:** 20-dns-records.png
**Notes:** —

---

## Phase 7: Web Server + DNS Resolution ✅
**Goal:** Host an internal website and confirm it's reachable by hostname (not just IP).
**Config:** Web server configured in the SERVERS VLAN; DNS A record points hostname to server's IP.
**Verification:** Website loads in browser by hostname; DNS resolution confirmed successful.
**Screenshots:** 21-web-server.png, 22-dns-resolution.png, 23-website.png
**Notes:** —

---

## Phase 8: SSH Management ⬜
*(next — in progress)*

---

## Phase 9: ACL Security ⬜
*(planned)*