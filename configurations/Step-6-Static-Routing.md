# Step 6 - Static-Routing

## Objective

Configure IP addressing and static routing between Router-CORE and Router-BRANCH to establish communication between both routers and the departmental VLAN networks.

A default route is configured on Router-CORE to forward traffic destined for unknown networks towards Router-BRANCH, allowing it to act as the upstream gateway.

## Identification

## Router-CORE

```cisco
enable
configure terminal
int g0/1
no shutdown
ip address.10.0.0.2 255.255.255.0
end
configure terminal
ip route 0.0.0.0 0.0.0.0 10.0.0.1
```

## Router-BRANCH

```cisco
enable
configure terminal
int g0/0
no shutdown
ip address 10.0.0.1 255.255.255.0
end
configure terminal
ip route 10.10.1.0 255.255.255.0
ip route 10.10.2.0 255.255.255.0
ip route 10.10.3.0 255.255.255.0
```

## Verification

We could use the following command to verify that Router-CORE has a default route pointing towards Router-BRANCH and that Router-BRANCH has the necessary static routes pointing back towards the VLAN networks through Router-CORE.

The show ip interface brief command provides an overview of the router interfaces, including their assigned IP addresses and operational status.

Together, these commands help verify the routing configuration and ensure that both routers have the necessary network paths to facilitate bidirectional communication.

```cisco
show ip route
show ip int brief
```

<img width="780" height="173" alt="image" src="https://github.com/user-attachments/assets/c4b1b748-7203-42bd-b09d-331f2283b501" />
<img width="780" height="402" alt="image" src="https://github.com/user-attachments/assets/344e03d0-00a6-46ff-9c2e-066eed7f6a24" />
<img width="780" height="101" alt="image" src="https://github.com/user-attachments/assets/5f98ed01-fd2c-452c-882c-0619966bcb27" />
<img width="780" height="347" alt="image" src="https://github.com/user-attachments/assets/b2e680e3-e652-4073-a085-350ddcc2d844" />

## Summary

Successfully configured IP addressing and static routing between Router-CORE and Router-BRANCH to establish bidirectional communication between the routers and the departmental VLAN networks.

A default route was configured on Router-CORE to forward traffic destined for unknown networks towards Router-BRANCH, while static routes on Router-BRANCH provide return paths to the three departmental VLANs.

The routing tables and interface configurations were verified to confirm the correct routes, IP addressing, and operational status of both routers.
