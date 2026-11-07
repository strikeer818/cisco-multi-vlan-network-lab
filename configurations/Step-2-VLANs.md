# Step 2 - VLANs

## Objective

Configuring VLANs for all switches to separate the network into different departments

## SW1-SALES-HR

```cisco
enable
configure terminal
vlan 10
name SALES
vlan 20
name HR
vlan 30
name IT/ADMIN
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
name IT/ADMIN
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
name IT/ADMIN
end
```

## Verification

We could use the following command to verify that the VLANs were successfully created on each switch

```cisco
show vlan brief
```

