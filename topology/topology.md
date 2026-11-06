# Network Topology

## Overview

The following diagram illustrates the network topology,
including device connections, switch ports, and VLAN assignments.

<img width="701" height="505" alt="VLAN 10" src="https://github.com/user-attachments/assets/043d2340-0078-4199-93cf-c44387c84e83" />

---

## VLAN Assignments

| VLAN | Department | Network | Gateway |
|---|---|---|---|
| 10 | Sales | 10.10.1.0/24 | 10.10.1.1 |
| 20 | HR | 10.10.2.0/24 | 10.10.2.1 |
| 30 | IT/Admin | 10.10.3.0/24 | 10.10.3.1 |

## Switch Port Assignments

### SW1-SALES-HR

| Interface | Connected Device | Mode | VLAN |
|---|---|---|---|
| Fa0/1 | PC-SALES | Access | 10 |
| Fa0/2 | PC-HR | Access | 20 |
| Fa0/3 | SW3-CORE | Trunk | 10, 20, 30 |

### SW2-IT

| Interface | Connected Device | Mode | VLAN |
|---|---|---|---|
| Fa0/1 | PC-IT/ADMIN | Access | 30 |
| Fa0/2 | SW3-CORE | Trunk | 10, 20, 30 |

### SW3-CORE

| Interface | Connected Device | Mode | VLAN |
|---|---|---|---|
| Fa0/1 | SW2-IT | Trunk | 10, 20, 30 |
| Fa0/2 | SW1-SALES-HR | Trunk | 10, 20, 30 |
| Fa0/3 | Router-CORE | Trunk | 10, 20, 30 |

---

## Router Connections

| Router | Interface | IP Address |
|---|---|---|
| Router-CORE | G0/1 | 10.0.0.2 |
| Router-BRANCH | G0/0 | 10.0.0.1 |
