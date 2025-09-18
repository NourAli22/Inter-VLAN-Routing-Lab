# 🚀 Inter-VLAN Routing Lab

## 📄 Description
A hands-on lab demonstrating Inter-VLAN Routing using Router-on-a-Stick in Cisco Packet Tracer.  
This setup enables communication between segmented VLANs using sub-interfaces and DHCP services on a router.

---

## 🧪 Lab Overview
In this lab, a Cisco router and switch are used to implement Inter-VLAN Routing.  
Three VLANs are configured to simulate departmental segmentation:

- VLAN 10 – IT  
- VLAN 20 – SALES  
- VLAN 30 – HR  

Each VLAN receives IP addresses via DHCP, and routing is handled through router sub-interfaces.

---

## 📊 VLANs Used

| VLAN ID | Department |
|---------|------------|
| 10      | IT         |
| 20      | SALES      |
| 30      | HR         |

---

## ⚙️ Key Configurations

### 🔹 Router Sub-Interfaces
```bash
interface Gig0/2
no shutdown

interface Gig0/2.10
encapsulation dot1Q 10
ip address [Hidden]

interface Gig0/2.20
encapsulation dot1Q 20
ip address [Hidden]

interface Gig0/2.30
encapsulation dot1Q 30
ip address [Hidden]
```
### 🔹 DHCP Pools
```bash
ip dhcp pool IT
network [Hidden]
default-router [Hidden]

ip dhcp pool SALES
network [Hidden]
default-router [Hidden]

ip dhcp pool HR
network [Hidden]
default-router [Hidden]
```
### 🔹 Switch Port Configuration
```bash
interface fa0/1 - 4
switchport access vlan 10

interface fa0/5 - 8
switchport access vlan 20

interface fa0/9 - 12
switchport access vlan 30

interface fa0/24
switchport mode trunk
```
---
### 🧩 Troubleshooting Experience
Initially, devices were receiving APIPA addresses and couldn’t communicate across VLANs.
The issue was traced to a missing trunk configuration on the switch port connected to the router.
Once the trunk was properly configured, DHCP worked and inter-VLAN communication was successful.

### ✅ Final Results
- Devices received IPs via DHCP.
- VLANs communicated successfully through the router.
- Real-world troubleshooting skills were applied and resolved.

### 💡 This lab is part of my journey into Network Engineering.
Full configuration and screenshots available in this repository.
![2](https://github.com/user-attachments/assets/a61ec578-a70b-4088-b699-3af964512a31)

