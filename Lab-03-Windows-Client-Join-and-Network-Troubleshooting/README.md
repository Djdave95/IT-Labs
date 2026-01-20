# Lab 03 – Windows Client Join & Network Troubleshooting

## 🎯 Objective
Demonstrate the ability to troubleshoot virtual network connectivity, configure DNS correctly, and successfully join a Windows client to an Active Directory domain.

## 🧩 Environment
- VMware Workstation
- Windows Server (Domain Controller: DC01)
- Windows 11 Client
- Host-Only Virtual Network (VMnet1)

## 🛠️ Tasks Performed
- Validated virtual network configuration across multiple VMs
- Identified subnet mismatch between domain controller and client
- Corrected virtual network configuration using Host-Only networking (VMnet1)
- Configured client DNS to point to the domain controller
- Verified connectivity using ping and name resolution
- Confirmed domain join and validated domain authentication

---

## 📸 Evidence

### 1) DC01 IP Configuration
![DC01 IP](screenshots/lab03_01_dc01_ipconfig.png)

### 2) Windows Client IP Configuration
![Client IP](screenshots/lab03_02_win11_ipconfig.png)

### 3) DNS Configuration on Client
![DNS Configuration](screenshots/lab03_03_dns_configuration.png)

### 4) Connectivity Validation (Ping DC01)
![Ping Test](screenshots/lab03_04_ping_dc01.png)

### 5) Domain Join Confirmation
![Domain Joined](screenshots/lab03_05_domain_joined.png)

### 6) Domain Login Validation
![Domain Login](screenshots/lab03_06_domain_login_validation.png)

---

## ✅ Validation Commands
```bash
ipconfig
ping DC01
nslookup lab.local
whoami

🧠 What I Learned

How VMware virtual networking works (NAT vs Host-Only)

How subnet mismatches prevent machines from communicating

Why Active Directory clients must use the Domain Controller as their DNS server

How to validate connectivity using ping, ipconfig, and nslookup

How to confirm domain authentication using whoami

How troubleshooting methodology applies to real-world IT environments

✅ Outcome

Successfully configured a Windows 11 client to communicate with a domain controller, resolved DNS and network issues, and validated domain authentication.
