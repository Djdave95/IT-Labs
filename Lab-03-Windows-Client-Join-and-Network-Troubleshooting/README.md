# Lab 03 – Windows Client Join & Network Troubleshooting

## 🎯 Objective
Demonstrate the ability to troubleshoot virtual network connectivity, configure DNS correctly, and successfully join a Windows client to an Active Directory domain.

## 🧪 Environment
- VMware Workstation
- Windows Server (Domain Controller)
- Windows 11 Client
- Host-Only Virtual Network (VMnet1)

## ✅ Tasks Performed
- Validated virtual network configuration across multiple VMs
- Identified subnet mismatch between domain controller and client
- Corrected virtual network configuration using Host-Only networking (VMnet1)
- Configured client DNS to point to the domain controller
- Verified connectivity using ping and name resolution
- Joined Windows client to Active Directory domain
- Validated domain authentication

## 📸 Evidence

### 1) DC01 IP Configuration
![DC01 IP](screenshots/lab03_01_dc01_ipconfig.png)  
**DC01 showing static IP configuration and network settings.**

---

### 2) Windows Client IP Configuration
![Client IP](screenshots/lab03_02_win11_ipconfig.png)  
**Windows 11 client receiving IP address from the Host-Only network.**

---

### 3) DNS Configuration on Client
![DNS Configuration](screenshots/lab03_03_dns_configuration.png)  
**Client DNS manually configured to point to the Domain Controller (DC01).**

---

### 4) Connectivity Validation (Ping DC01)
![Ping Test](screenshots/lab03_04_ping_dc01.png)  
**Successful network connectivity validation between client and DC01 using ping.**

---

### 5) Domain Join Confirmation
![Domain Joined](screenshots/lab03_05_domain_joined.png)  
**Windows client successfully joined to the Active Directory domain.**

---

### 6) Domain Login Validation
![Domain Login](screenshots/lab03_06_domain_login_validation.png)  
**Domain user successfully authenticated on the Windows client.**



## 🧪 Validation Commands
ipconfig  
ping DC01  
nslookup lab.local  
whoami  

## 🧠 What I Learned
- How VMware virtual networking works (NAT vs Host-Only) and how it impacts VM connectivity
- How subnet mismatches prevent machines from communicating properly
- Why Active Directory clients must use the Domain Controller as their primary DNS server
- How to validate DNS and network connectivity using ipconfig, ping, and nslookup
- How to confirm domain authentication using whoami
- How to document troubleshooting work clearly using GitHub and screenshots
- How structured troubleshooting mirrors real-world IT support workflows

## ✅ Outcome
Successfully configured a Windows 11 client to communicate with a domain controller, resolved DNS and network issues, joined the client to the Active Directory domain, and validated domain authentication.
