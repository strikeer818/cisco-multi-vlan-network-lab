# Cisco Multi-VLAN Network Configuration and Inter-VLAN Routing

## Project Overview

This project demonstrates the configuration of a small enterprise network using Cisco Packet Tracer.

The network consists of two routers, three switches, and three end devices. Multiple VLANs are used to separate departments, while Router-on-a-Stick enables communication between VLANs.

Static routing is configured between Router-BRANCH and Router-CORE to allow communication between the central network and the upstream router.

---

## Network Topology

### Devices
- 2 Cisco Routers
- 3 Cisco Switches
- 3 End Devices (PCs)

### Network Departments
- **VLAN 10** - Sales
- **VLAN 20** - HR
- **VLAN 30** - IT/Admin

---

## IP Addressing Scheme

| VLAN / Link | Network | Default Gateway |
|---|---|---|
| Sales (VLAN 10) | `10.10.1.0/24` | `10.10.1.1` |
| HR (VLAN 20) | `10.10.2.0/24` | `10.10.2.1` |
| IT/Admin (VLAN 30) | `10.10.3.0/24` | `10.10.3.1` |
| Router-CORE | `10.0.0.2/24` | `10.0.0.1` |
| Router-BRANCH | `10.0.0.1/24` | N/A |

---

## Technologies and Concepts

- VLAN Configuration and Network Segmentation
- Access Ports and Trunk Ports
- IEEE 802.1Q Encapsulation
- Router-on-a-Stick
- Inter-VLAN Routing
- Static Routing
- Default Route Configuration
- IP Addressing and Subnetting
- DHCP Configuration (Planned/In Progress)
- Network Troubleshooting using Ping and Traceroute

---

## Project Implementation

1. Configured device hostnames.
2. Created VLANs 10, 20, and 30.
3. Configured trunk links between switches and Router-CORE.
4. Assigned access ports to the appropriate VLANs.
5. Configured router subinterfaces for inter-VLAN routing.
6. Configured static routes between Router-BRANCH and Router-CORE.
7. Assigned IP addresses and default gateways to end devices.
8. Prepared DHCP configuration to automate IP address assignment.

---

## Testing and Verification

The following tests are used to verify network connectivity:

| Test | Expected Result |
|---|---|
| Sales → HR | Successful |
| Sales → IT/Admin | Successful |
| HR → IT/Admin | Successful |
| Sales → Router-CORE | Successful |
| Router-CORE → Router-BRANCH | Successful |
| Router-BRANCH → VLAN Networks | Successful |

### Troubleshooting Commands Used

```cisco
show vlan brief
show interfaces trunk
show ip interface brief
show ip route
show running-config
show cdp neighbors
ping
traceroute
```
## Project Files

- multi-vlan-network.pkt – Cisco Packet Tracer project file.
- configurations/ – Device configuration files.
- topology/ – Network topology diagram.
- screenshots/ – Configuration and connectivity evidence.

## Learning Outcomes

Through this project, I developed practical experience with Cisco networking, VLAN segmentation, inter-VLAN communication, static routing, and network troubleshooting.

The project helped me understand how multiple departments can communicate across separate VLANs while maintaining logical network segmentation.

## Future Improvements

- Implement DHCP pools for automatic IP assignment.
- Replace static routing with OSPF dynamic routing.
- Add additional routers to explore redundant paths.
- Explore network redundancy and failover.
- Implement access control lists (ACLs) to control inter-VLAN traffic.


