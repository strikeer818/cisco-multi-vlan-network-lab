
# Step 3 - Trunk Ports

## Objective

Configure trunk ports across all switches to allow traffic from multiple VLANs to travel across shared physical connections using IEEE 802.1Q encapsulation

## Identification

<img width="709" height="98" alt="image" src="https://github.com/user-attachments/assets/f00cf5d4-5ca1-462f-82f9-d0647dc87689" />
<img width="709" height="212" alt="image" src="https://github.com/user-attachments/assets/b3f8d43c-b6eb-4f62-b885-193669adffc6" />
<img width="709" height="98" alt="image" src="https://github.com/user-attachments/assets/a79fe322-11d4-4d11-86f6-768d497846a5" />

Before configuring trunk ports, the ```show cdp neighbors``` command was used to identify neighboring Cisco devices and determine which local switch interfaces were connected to other switches and Router-CORE.

This helped identify the correct interfaces that needed to be configured as trunk ports

## SW1-SALES-HR

```cisco
enable
configure terminal
interface 
switchport mode trunk
switchport trunk allowed vlan 10,20,30
end
```

## SW2-IT

```cisco
enable
configure terminal
vlan 10
name SALES
vlan 20
name HR
vlan 30
name IT-ADMIN
end
```

## SW3-CORE

```cisco
enable
configure terminal
vlan 10
name SALES
vlan 20
name HR
vlan 30
name IT-ADMIN
end
```

## Verification

We could use the following command to verify that the VLANs were successfully created on each switch.

```cisco
show vlan brief
```


<img width="765" height="245" alt="image" src="https://github.com/user-attachments/assets/32eed2c3-4a84-40df-b683-4d7f79737676" />

<img width="765" height="245" alt="image" src="https://github.com/user-attachments/assets/62c43c25-3ab0-4a03-bd90-b4710d9bf767" />

<img width="765" height="245" alt="image" src="https://github.com/user-attachments/assets/2a78c8e5-cf59-4aa0-a2ee-297178293391" />

## Summary

As shown in the screenshots above, the ```show vlan brief``` command confirms that VLANs 10,20, and 30 have been successfully created on the switches. 

At this stage, the VLANs have been created, but access ports have not yet been assigned. This will be configured in Step 4, where end devices will be allocated to their respective departmental VLANs.

These VLANs provide the logical network segmentation required for separating departmental traffic throughout the network.

