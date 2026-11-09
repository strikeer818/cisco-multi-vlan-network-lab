# Network Connectivity Testing

## 1. Inter-VLAN Connectivity

Testing communication between Sales, HR and IT/Admin.

### Sales to HR
<img width="692" height="359" alt="image" src="https://github.com/user-attachments/assets/37d8a13d-254c-4096-9ef9-32069cc04ec2" />

### Sales to IT/Admin
<img width="692" height="645" alt="image" src="https://github.com/user-attachments/assets/79c19eda-7f02-47ce-95fe-b165464bc9d9" />

### HR to IT/Admin
<img width="692" height="358" alt="image" src="https://github.com/user-attachments/assets/3c0ace0a-f944-444d-9921-c2cf1017db1d" />

<p>&nbsp;</p>

During the initial connectivity test, the first ping request timed out, while the subsequent requests were successful. This may be due to ARP (Address Resolution Protocol) resolving the MAC address of the default gateway before the packet can be forwarded to another subnet. Once the MAC address is learned and stored in the ARP cache, subsequent packets can be transmitted without repeating the same address resolution process.

## 2. Router Connectivity

Testing communication between Router-CORE and Router-BRANCH.

<img width="645" height="124" alt="image" src="https://github.com/user-attachments/assets/4fa18c6f-5ef4-40c9-b8ba-4c7185afa49a" />
<img width="645" height="102" alt="image" src="https://github.com/user-attachments/assets/cd691067-7bcc-4128-a93a-9b8c5e776cb3" />

Similar to the initial connectivity test involving the end devices, the ping test between Router-CORE and Router-BRANCH resulted in one timeout, followed by four successful replies. This may be attributed to initial ARP resolution, where the router needs to discover the MAC address of its neighbouring device. Subsequent packets were successfully transmitted, demonstrating connectivity between the two routers.

<img width="645" height="273" alt="image" src="https://github.com/user-attachments/assets/debcb81e-f25b-4ed7-89d0-7587e238b44d" />

To further verify ARP resolution, the show ```show ip arp``` command was executed on Router-CORE. This displays the ARP table, which contains the IPv4 addresses and corresponding MAC addresses of devices that the router has learned. The output confirms that Router-CORE has successfully learned the MAC addresses of Router-BRANCH and the end devices within the SALES, HR, and IT/ADMIN networks.

## 3. Traceroute Testing

Verifying the network path to remote VLAN destinations.

<img width="475" height="117" alt="image" src="https://github.com/user-attachments/assets/f48a0c27-0006-47c6-9afd-521f4b891745" />
<img width="475" height="117" alt="image" src="https://github.com/user-attachments/assets/7c44c855-7f1e-4cb4-9603-ac03fbbafb71" />
<img width="475" height="113" alt="image" src="https://github.com/user-attachments/assets/8f20d83b-5741-4a44-a0c8-45a13e9fe3fa" />


The ```traceroute``` command was used on Router-BRANCH to identify the Layer 3 path taken by packets travelling towards the SALES end device (10.10.1.10).

Traceroute operates at Layer 3 of the OSI model by using IP packets with varying Time to Live (TTL) values to identify the intermediate routers along the path to the destination. The output shows that traffic passes through the neighbouring router (10.0.0.2) before reaching the destination device (10.10.1.10).

## 4. Results

| Test | Expected Result |
|---|---|
| Sales → HR | Successful |
| Sales → IT/Admin | Successful |
| HR → IT/Admin | Successful |
| Sales → Router-CORE | Successful |
| Router-CORE → Router-BRANCH | Successful |
| Router-BRANCH → VLAN Networks | Successful |
