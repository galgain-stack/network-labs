# Packet Tracer Labs

This folder contains Cisco Packet Tracer networking labs.

Each lab is used to practice building, testing, and troubleshooting network configurations.

## Labs


### Network Foundations Lab

Version 1  
`network-foundations-v1.pkt`

VLAN 40 restricted from communicating with other VLANs using ACL 100.

Version 2  
`network-foundations-v2.pkt`

ACL removed from interface g0/1.40 allowing VLAN 40 to communicate with other VLANs.

## Version 3 - DHCP Enablement
`network-foundations-v2.pkt`

### Summary
This version adds DHCP services for VLAN10, VLAN20, VLAN30, and VLAN40 using router-based DHCP pools.

### Changes Made
- Added excluded gateway addresses for each VLAN
- Configured DHCP pools for all four VLANs
- Changed client hosts from static addressing to DHCP

### Validation
- Verified DHCP lease assignment for all VLANs
- Verified default gateway reachability
- Verified inter-VLAN connectivity
- Verified leases with `show ip dhcp binding`

### Rollback
If DHCP configuration fails or causes incorrect addressing behavior, revert to `network-foundations-v2.pkt`.
Skills practiced:

- IP addressing
- Gateway configuration
- Connectivity testing
- Basic troubleshooting
