
# Step 5 - Inter-VLAN-Routing

## Objective

Performing inter-VLAN routing which allows traffic to run smoothly across the network using encapsulation dot1q that would allow us to create sub interfaces so that we would be used to read VLAN tags through the port, this could be known as router on a stick

## Identification

Using command ```show cdp neighbors``` was executed on SW3-CORE to identify the interface connected to Router-CORE. The output displays the neighboring device's hostname, the local interface, and the remote port ID, allowing the correct physical connection to be identified before configuring Router-on-a-Stick.

In this case, the Router-CORE connection was identified on interface GigabitEthernet0/0(g0/0)

## Router-CORE

```cisco
enable
configure terminal
int g0/0
not shutdown
int g0/0.10
encapsulation dot1q 10
ip address 10.10.1.1 255.255.255.0
exit
int g0/0.20
encapsulation dot1q 20
ip address 10.10.2.1 255.255.255.0
exit
int g0/0.30
encapsulation dot1q 30
ip address 10.10.3.1 255.255.255.0
end
```

## Verification

We could use the following command was used to verify that the router sub interfaces were successfully created and to check their IP addresses and operational status.

```cisco
show ip int brief
```

<img width="771" height="155" alt="image" src="https://github.com/user-attachments/assets/209ec1f2-8e36-4ca1-867f-01fc830ce22f" />

## Summary

Successfully configured three router sub interfaces on Router-CORE using IEEE 802.1Q encapsulation to support inter-VLAN routing.

Each subinterface was assigned a VLAN ID and an IP address to serve as the default gateway for its respective departmental network. Each VLAN operates within its own unique IP subnet to maintain logical network separation.

By configuring these subinterfaces with IEEE 802.1Q encapsulation, Router-CORE can identify and route traffic between all three VLANs, enabling inter-VLAN communication.

This implementation uses Router-on-a-Stick, allowing multiple VLANs to communicate through a single physical router interface while maintaining logical network seperation.

