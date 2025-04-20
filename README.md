# 💼 Network Infrastructure Design and Implementation for a Small Business

📅 **Jan 2025 – Present**  
🔧 **Freelance Network & IT Support**  
🏷️ *Simulated Real-World Project Based on Freelance Experience*

---

## 📘 Project Overview

This project showcases the complete design and implementation of a **secure, scalable network infrastructure** for a small business using **Cisco networking technologies**. 

> ⚠️ *Note: IPs and topology have been modified to maintain privacy while keeping the configurations and challenges realistic.*

---

## 🏢 Business Snapshot

- **Employees**: 8  
- **Departments**: Sales, Inventory, Management, Owner  
- **Additional Systems**: 1 DVR for CCTV, 1 shared printer

---

## 🛠️ Project Requirements

- Enable inter-department communication
- Provide internet access to all users
- VLAN-based departmental segmentation
- Secure access to CCTV system
- Future scalability for additional devices

---

## 🖥️ Devices Overview

| Department   | Devices                  |
|-------------|--------------------------|
| Sales       | 2 PCs                    |
| Inventory   | 1 PC                     |
| Management  | 2 PCs + 1 shared printer |
| Owner       | 1 PC                     |
| Network     | 1 Router, 1 Switch       |
| CCTV        | 1 DVR                    |

---

## 🌐 IP Addressing and Subnetting

- **Public IP**: `74.125.50.10/30`
- **Private IPs**: Subnetted per VLAN to optimize usage
- **Router**: Router-on-a-stick setup with sub-interfaces for inter-VLAN routing
- **DHCP**: Centralized on router, with excluded ranges for static IPs

| VLAN | Department | Subnet              | Usable IPs     | Gateway         |
|------|------------|---------------------|----------------|-----------------|
| 10   | Sales      | 192.168.10.0/29     | .1 – .6        | 192.168.10.1    |
| 20   | Inventory  | 192.168.10.8/29     | .9 – .14       | 192.168.10.9    |
| 30   | Management | 192.168.10.16/28    | .17 – .30      | 192.168.10.17   |
| 40   | Owner      | 192.168.10.32/29    | .33 – .38      | 192.168.10.33   |

---

## 🔁 NAT & Internet Connectivity

- **PAT** (Port Address Translation) configured due to limited public IP
- `ip nat inside` applied on sub-interfaces
- `ip nat outside` configured on interface `Gig0/1`
- **ACL** defined to include inside users for NAT
- Default route to ISP added for full internet access

---

## 🔒 Network Security

### 🔐 ACLs
- Only **Owner VLAN** and **Admin's IP** allowed Telnet access to router
- Restricted access to **Inventory VLAN** (only Sales and Owner can access)

### 🛡️ Port Security
- Enabled per interface based on the number of authorized devices
- Unauthorized MAC addresses cause port shutdown for protection

---

## ⚙️ Features Implemented

- VLAN segmentation for logical separation
- Router-based DHCP server with per-VLAN IP pools
- NAT & PAT setup for internet access
- ACLs for router access and sensitive VLANs
- Port Security to prevent unauthorized device connections

---

## ✅ Testing & Verification

- Successful ping tests across allowed VLANs
- Access blocks confirmed via ACLs
- NAT and DHCP functionality verified
- Port Security behavior tested per interface

---

## 📌 Conclusion

This project simulates a **production-ready network model** for small businesses, built around:

- Security  
- Simplicity  
- Scalability  

It demonstrates a practical approach to small office networking and serves as a personal proof-of-capability in **secure network design and implementation**.

> Future enhancements: IDS/IPS, SIEM logging, cloud-based services, and failover/redundancy.

---

## 📂 Files Included

This repository contains all relevant files for reviewing and reproducing the project:

- `Network Infrastructure Design and Implementation.docx` – Full technical documentation including:
  - Business requirements
  - IP addressing and subnetting
  - VLAN setup
  - NAT and DHCP configurations
  - ACLs and security settings
  - Configuration walkthroughs and verification tests
  - Conclusion and future improvements

- `network topology.pkt` – Cisco Packet Tracer simulation file for hands-on interaction with the network setup.

> Use the `.pkt` file to explore the complete working network, including devices, configurations, and connectivity tests.

---
