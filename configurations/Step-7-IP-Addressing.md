
# Step 7 - IP Addressing

## Objective

Manually configure the IP addresses and default gateways of end devices since a DHCP server has not yet been implemented to automatically assign IP addresses.

## SALES

<img width="680" height="443" alt="Algorithm Settings" src="https://github.com/user-attachments/assets/533abeba-87ee-4c8d-b442-3c1246d9bd21" />
<img width="680" height="410" alt="Settings" src="https://github.com/user-attachments/assets/17176f40-f565-4433-87e4-eab8f22dc8b3" />

## HR

<img width="680" height="451" alt="Settings" src="https://github.com/user-attachments/assets/abf9871a-c3c5-4401-ac52-23bcb31371f2" />
<img width="680" height="414" alt="Settings" src="https://github.com/user-attachments/assets/94e82525-e2df-4409-aabc-81cb75e031ea" />

## IT/ADMIN

<img width="680" height="449" alt="Settings" src="https://github.com/user-attachments/assets/7bbf98a5-061b-4b4b-8b88-2b82c227de93" />
<img width="680" height="419" alt="GLOBAL" src="https://github.com/user-attachments/assets/751e0914-80a2-41bb-81d2-525b0446f968" />

## Summary

static IP addressing was manually configured for all end devices in the SALES, HR, and IT/ADMIN departments because a DHCP server has not yet been implemented.

Each end device was assigned the following network settings:

- **IP Address**: A unique IP address within its department's designated subnet.

- **Subnet Mask**: The appropriate subnet mask to identify the network portion and host portion of the IP address.

- **Default Gateway**: The IP address of the router interface assigned to the respective department's network.

This configuration ensures that each device can communicate with other devices within its subnet and access devices on different networks through the router.

By manually assigning IP addresses and default gateways, the network is prepared for communication between the different departments. These settings will also serve as a foundation for implementing DHCP in a future configuration step, which will automate IP address assignment and simplify network administration.


