# Step 2 - VLANs

## Objective

Configuring VLANs for all switches to separate the network into different departments.

## SW1-SALES-HR

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

As shown in the screenshots above, the ```show vlan brief``` command confirms that VLANs 10,20, and 30 have been successfully created on the switches. At this stage, the VLANs have been created, but access ports have not yet been assigned. This will be configured in Step 4, where end devices will be allocated to their respective departmental VLANs.



