
# Step 4 - Access Ports

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
interface Fa0/3
switchport mode trunk
switchport trunk allowed vlan 10,20,30
end
```

## SW2-IT

```cisco
enable
configure terminal
switchport trunk allowed vlan 10,20,30
interface Fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30
end
```

## SW3-CORE

```cisco
enable
configure terminal
interface Fa0/2
switchport mode trunk
switchport trunk allowed vlan 10,20,30
interface Fa0/3
switchport mode trunk
switchport trunk allowed vlan 10,20,30
interface Fa0/1
switchport mode trunk
switchport trunk allowed vlan 10,20,30
end
```

## Verification

We could use the following command to verify that the trunk ports were successfully configured on each switch and to confirm which VLANs are permitted across the trunk links.

```cisco
show interfaces trunk
```
<img width="638" height="194" alt="image" src="https://github.com/user-attachments/assets/1310002c-05f6-4d11-b4ec-286fdee88bbe" />
<img width="638" height="117" alt="image" src="https://github.com/user-attachments/assets/25d136dc-cf31-447f-ae9a-061a6c18eda4" />
<img width="638" height="125" alt="image" src="https://github.com/user-attachments/assets/626a6dd7-6501-4326-ba00-2a2837606676" />

## Summary

Successfully configured trunk links between SW1-SALES-HR, SW2-IT, SW3-CORE, and Router-CORE.

The ```show cdp neighbors``` command was used to identify the connected interfaces before configuration, while ```show interfaces trunk``` was used to verify the trunk configurations.

VLANs 10,20,30 can now travel across the configured trunk links, allowing the network to carry multiple VLANs over shared physical connections.

As shown earlier, using command ```show cdp neighbors``` you're able to see a physical connection between SW3-CORE and Router-CORE

At this stage, Router-CORE is connected through its physical GigabitEthernet interface. Router subinterfaces have not yet been configured, as this will be configured in Step 5 during the implementation of Router-on-a-Stick.

