
# Step 5 - InterVLAN-Routing

## Objective

Performing inter-VLAN routing which allows traffic to run smoothly across the network using encapsulation dot1q that would allow us to create sub interfaces so that we would be used to read VLAN tags through the port, this could be known as router on a stick

## Identification



## Router-CORE

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

## Verification

We could use the following command to verify that 

```cisco
show vlan brief
show interfaces status
```

## Summary



