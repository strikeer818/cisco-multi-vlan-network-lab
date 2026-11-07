
# Step 4 - Access Ports

## Objective

Configure PC-Connected switch ports in access mode and assign them to their respective VLANs to ensure end devices are connected to the appropriate departmental networks.

## Identification

The ```show interfaces status``` command was used to identify active switch interfaces, their connection status, and their existing VLAN assignments.

The appropriate interfaces had already been identified during the inital network setup, allowing the correct ports to be selected to their respective end devices.

## SW1-SALES-HR

```cisco
enable
configure terminal
interface Fa0/1
switchport mode access
switchport access vlan 10
interface Fa0/2
switchport mode access
switchport access vlan 10
end
```

## SW2-IT

```cisco
enable
configure terminal
interface Fa0/1
switchport mode access
switchport access vlan 30
end
```

## Verification

We could use the following command to verify that the access ports were successfully configured on each switch and to confirm taht the appropriate interfaces were assigned to their respective departmental VLANs.

```cisco
show interfaces status
show vlan brief
```

<img width="768" height="227" alt="image" src="https://github.com/user-attachments/assets/6f6ac245-95a3-4073-a3e9-36640f83659f" />
<img width="768" height="99" alt="image" src="https://github.com/user-attachments/assets/f771e1d6-433a-42a7-955a-a9c187803f1d" />
<img width="768" height="246" alt="image" src="https://github.com/user-attachments/assets/3b7a9aa4-2256-444d-8891-759b900b74b8" />
<img width="768" height="77" alt="image" src="https://github.com/user-attachments/assets/ebfc6e16-3521-4754-ae81-6dd3f73eceb5" />


## Summary

Successfully configured and verified access port assignments across SW1-SALES-HR and SW2-IT.

Each end device was assigned to its respective departmental VLAN to ensure proper network segmentation.

The ```show vlan brief``` and ```show interfaces status``` commands were used to verify VLANs, interface assignments, and connection status.

This configuration establishes the access layer required for end devices to communicate within their designated VLANs.

