# Lab 03 – Windows Client Join & Network Troubleshooting

## 🎯 Objective
Demonstrate the ability to troubleshoot virtual network connectivity, configure DNS correctly, and successfully join a Windows client to an Active Directory domain.

## 🧩 Environment
- VMware Workstation
- Windows Server (Domain Controller)
- Windows 11 Client
- Host-Only Virtual Network (VMnet1)

## 🔧 Tasks Performed
- Validated virtual network configuration across multiple VMs
- Identified subnet mismatch between domain controller and client
- Corrected virtual network configuration using Host-Only networking
- Configured client DNS to point to the domain controller
- Verified connectivity using ping and name resolution
- Joined Windows client to Active Directory domain
- Validated domain authentication

## 📸 Evidence

### DC01 IP Configuration
![DC01 IP](screenshots/lab03_01_dc01_ipconfig.png)

---

### Windows Client IP Configuration
![Client IP](screenshots/lab03_02_win11_ipconfig.png)

---

### DNS Configuration on Client
![DNS Configuration](screenshots/lab03_03_dns_configuration.png)

---

### Connectivity Validation (Ping DC01)
![Ping Test](screenshots/lab03_04_ping_dc01.png)

---

### Domain Join Confirmation
![Domain Joined](screenshots/lab03_05_domain_joined.png)

---

### Domain Login Validation
![Domain Login](screenshots/lab03_06_domain_login_validation.png)

---

## ✅ Validation Commands

```bash
ipconfig
ping DC01
nslookup lab.local
whoami

---

## 🧠 What I Learned

- How virtual networking works in VMware (NAT vs Host-Only)
- How to troubleshoot connectivity issues using tools such as ping, ipconfig, and nslookup
- How DNS configuration impacts Active Directory domain joins
- How to manually configure a Windows client to point to a domain controller
- How to validate successful domain joins and domain authentication
- How to document technical work clearly using screenshots and GitHub
- Improved confidence troubleshooting real-world network issues

This lab strengthened my understanding of Windows networking fundamentals and domain infrastructure.
