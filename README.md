# Multi-VLAN-Network-with-ACL-Enforcement

## Project Overview

This project demonstrates the design and implementation of a segmented multi-VLAN network using Router-on-a-Stick architecture. The lab includes inter-VLAN routing, DHCP configuration, WAN connectivity, and ACL-based access control to enforce network segmentation between departments.

The objective was to simulate a small enterprise network and validate Layer 2 and Layer 3 functionality through structured configuration and troubleshooting.

## Network Design
### VLAN Structure

VLAN | Department | Subnet | Gateway
-------|-------|-------|-------|
| 10 | Sales | 192.168.10.0/24 | 192.168.10.1 |
| 20 | HR | 192.168.20.0/24 | 192.168.20.1 |
| 30 | Guest | 192.168.30.0/24 | 192.168.30.1 |

#### WAN Interface:

- 10.0.0.2/30
- Default Route → 10.0.0.1

### Key Features Implemented
- VLAN creation and trunk configuration (802.1Q)
- Router-on-a-Stick inter-VLAN routing
- DHCP pools per VLAN
- Static default route to WAN
- Extended ACL restricting Guest access to internal VLANs
- Layer 2 and Layer 3 validation testing

## ACL Logic
An extended ACL was applied inbound on the Guest VLAN subinterface (G0/0.30) to prevent traffic from VLAN 30 reaching VLAN 10 and VLAN 20, while permitting outbound WAN access.

## Validation & Testing

### Connectivity Testing

- Verified DHCP address assignment per VLAN
- Confirmed inter-VLAN communication between Sales and HR
- Confirmed Guest VLAN blocked from internal subnets
- Validated WAN reachability from all VLANs
- Used ping, traceroute, show vlan, show ip route, and show access-lists for verification

