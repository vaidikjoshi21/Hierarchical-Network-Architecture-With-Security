# **Hierarchical Network Architecture With Security (HNAS)**

## 📁 Project Overview
The **Hierarchical Network Architecture With Security (HNAS)** project showcases the design and implementation of a **multi-layered enterprise network** with an emphasis on **security, scalability, and efficient communication**.  
Using **Cisco Packet Tracer**, this project integrates **VLAN segmentation**, **OSPF dynamic routing**, **DHCP-based IP allocation**, and **secure remote access (SSH and Port Security)** to ensure reliable and secure operations across all departments.

---

## 🧱 **Network Topology Summary**
- **3 Routers** (one per floor, interconnected with Serial DCE cables).
- **3 Switches** (one per floor for VLAN connections).
- **9 VLANs** (one for each department).
- **Wi-Fi Access Points** and **Printers** for every floor.
- **OSPF Dynamic Routing** between routers.
- **DHCP Servers** (configured on routers).
- **Port Security** on IT switch (`fa0/5`) for **Test-PC**.
- **SSH for Secure Remote Management**.

---

## 🧩 **VLAN & Subnet Details**
| Floor      | Department        | VLAN ID | Network         | Gateway         |
| ---------- | ----------------- | ------- | --------------- | --------------- |
| **1st**    | Reception         | 80      | 192.168.8.0/24  | 192.168.8.1     |
|            | Store             | 70      | 192.168.7.0/24  | 192.168.7.1     |
|            | Logistics         | 60      | 192.168.6.0/24  | 192.168.6.1     |
| **2nd**    | Finance           | 50      | 192.168.5.0/24  | 192.168.5.1     |
|            | HR                | 40      | 192.168.4.0/24  | 192.168.4.1     |
|            | Sales/Marketing   | 30      | 192.168.3.0/24  | 192.168.3.1     |
| **3rd**    | Admin             | 20      | 192.168.2.0/24  | 192.168.2.1     |
|            | IT                | 10      | 192.168.1.0/24  | 192.168.1.1     |

---

## 🌐 **IP Addressing Scheme (Routers)**

| Device    | Interface | IP Address  | Subnet |
| --------- | --------- | ----------- | ------ |
| **F1-R1** | S0/3/0    | 10.10.10.5  | /30    |
|           | S0/3/1    | 10.10.10.9  | /30    |
| **F2-R2** | S0/3/0    | 10.10.10.1  | /30    |
|           | S0/3/1    | 10.10.10.10 | /30    |
| **F3-R3** | S0/3/0    | 10.10.10.6  | /30    |
|           | S0/3/1    | 10.10.10.2  | /30    |

**Router Interconnections:**  
- **F2-R2 ↔ F3-R3:** `10.10.10.0/30`  
- **F2-R2 ↔ F1-R1:** `10.10.10.8/30`  
- **F3-R3 ↔ F1-R1:** `10.10.10.4/30`  

---

## 🔄 **Dynamic Routing - OSPF**
- Configured under **Area 0 (Backbone)**.
- Advertises all VLAN subnets and inter-router links.
- Enables **fast convergence** and **automatic routing updates**.

---

## 🔐 **Security Measures**
- **SSH Access:** Encrypted remote login on all routers.  
- **Port Security:** Sticky MAC binding with violation mode `shutdown` on IT switch `fa0/5`.  
- **DHCP Pools:** Configured for each VLAN for automatic IP distribution.  

---

## 🧠 **Key Features**
- **VLAN Segmentation:** Logical separation of departments.
- **Inter-VLAN Routing:** Enabled via router-on-a-stick approach.
- **Dynamic IP Allocation:** DHCP eliminates manual IP assignments.
- **Secure Access:** SSH and Port Security safeguard the network.
- **Scalability:** Hierarchical design supports future expansion.

---

## ⚙️ **Configuration Highlights**
- **VLAN Creation & Trunking** between switches.
- **Serial Links (/30 subnets)** for router interconnections.
- **OSPF Routing** to share routes dynamically.
- **DHCP Pools** for each VLAN.
- **SSH Setup** with RSA key authentication.
- **Port Security** restricting unauthorized devices.

---

## 🧪 **Testing & Validation**
1. **Ping Tests** across VLANs and floors.  
2. **SSH Login** from Test-PC to routers.  
3. **DHCP Testing** for dynamic IP assignments.  
4. **Security Testing** by connecting unauthorized devices to restricted ports.

---

## 👤 **Author**
**Designed by:** Vaidik Joshi  
**Date:** July 2025  
**Tool:** Cisco Packet Tracer  

---

## 📝 **License**
Free to use for **educational purposes**. Not intended for commercial deployment.
