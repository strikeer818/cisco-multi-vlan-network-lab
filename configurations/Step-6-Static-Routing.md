# Step 6 - Static-Routing

## Objective

Creating a static route and giving ip address for both Routers so traffic can smoothly pass through as well as creating a default gateway as if anything goes wrong it’ll send traffic directly to Router-BRANCH

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

## Summary




