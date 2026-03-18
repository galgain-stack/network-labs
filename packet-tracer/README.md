# Packet Tracer Labs

This folder contains Cisco Packet Tracer networking labs.

Each lab is used to practice building, testing, and troubleshooting network configurations.

---

## Labs

### Network Foundations Lab

---

### Version 1  
`network-foundations-v1.pkt`

VLAN 40 restricted from communicating with other VLANs using ACL 100.

---

### Version 2  
`network-foundations-v2.pkt`

ACL removed from interface g0/1.40 allowing VLAN 40 to communicate with other VLANs.

---

### Version 3 - DHCP Enablement  
`network-foundations-v3.pkt`

#### Summary  
This version adds DHCP services for VLAN10, VLAN20, VLAN30, and VLAN40 using router-based DHCP pools.

#### Changes Made
- Added excluded gateway addresses for each VLAN  
- Configured DHCP pools for all four VLANs  
- Changed client hosts from static addressing to DHCP  

#### Validation
- Verified DHCP lease assignment for all VLANs  
- Verified default gateway reachability  
- Verified inter-VLAN connectivity  
- Verified leases with `show ip dhcp binding`  

---

### Version 3.2 - VLAN Expansion  
`network-foundations-v3.2.pkt`

#### Summary  
This version expands the topology by adding an additional host to each VLAN to simulate multi-device environments.

#### Changes Made
- Added one additional endpoint to each VLAN (10, 20, 30, 40)  
- Verified switch port assignments for correct VLAN membership  
- Ensured DHCP assigns IP addresses to new hosts  

#### Validation
- Verified communication between hosts within the same VLAN  
- Verified DHCP leases assigned to all new devices  
- Confirmed inter-VLAN routing is still functional  

---

### Version 4 - Inter-VLAN Isolation (ACL Implementation)  
`network-foundations-v4.pkt`

#### Summary  
This version implements an extended ACL to block all inter-VLAN communication while preserving intra-VLAN connectivity.

#### Changes Made
- Created extended ACL 100:  
  `deny ip any any`  
- Applied ACL inbound on all router subinterfaces:  
  - g0/0.10  
  - g0/0.20  
  - g0/1.30  
  - g0/1.40  

#### Validation
- Verified hosts within the same VLAN can communicate  
- Verified inter-VLAN communication is blocked  
- Verified ACL hit counts increase using `show access-lists`  
- Observed "Destination host unreachable" when attempting blocked traffic  

---

## Rollback

If ACL configuration or DHCP behavior causes issues, revert to a previous stable version:

- Use **v3.2** for full connectivity with DHCP  
- Use **v2** for static addressing baseline  

---

## Skills Practiced

- VLAN configuration  
- Inter-VLAN routing (router-on-a-stick)  
- DHCP configuration and validation  
- Access Control Lists (ACLs)  
- Network segmentation and isolation  
- Troubleshooting connectivity issues  
