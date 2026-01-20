# 📄 Lab 03 – Windows Client Domain Join & Network Troubleshooting

## 🎯 Objective
Join a Windows client machine to an Active Directory domain, validate network connectivity and DNS resolution, and troubleshoot common domain join issues in an enterprise environment.

This lab demonstrates practical troubleshooting, system configuration, and validation techniques used in IT operations and security environments.

---

## 🖥️ Environment
- Windows Server (Domain Controller – DC01)
- Windows 11 Client
- Active Directory Domain Services (AD DS)
- DNS Services
- VMware / VirtualBox Lab Environment

---

## ✅ Tasks Performed
- Verified IP configuration on Domain Controller and client machine
- Validated DNS configuration and name resolution
- Tested network connectivity between client and domain controller
- Joined Windows client to Active Directory domain
- Authenticated using domain credentials
- Validated successful domain membership

---

## 📸 Evidence

### ✅ Step 1 — Domain Controller IP Configuration
Validated IP addressing and network configuration on the domain controller.

![DC01 IP Configuration](screenshots/lab03_01_dc01_ipconfig.png)

---

### ✅ Step 2 — Windows Client IP Configuration
Confirmed correct IP address, subnet, gateway, and DNS settings on the Windows 11 client.

![Windows Client IP Configuration](screenshots/lab03_02_win11_ipconfig.png)

---

### ✅ Step 3 — DNS Configuration Validation
Verified DNS server assignment and name resolution configuration.

![DNS Configuration](screenshots/lab03_03_dns_configuration.png)

---

### ✅ Step 4 — Network Connectivity Test (Ping DC01)
Validated network connectivity between the client and the domain controller using ICMP ping.

![Ping DC01](screenshots/lab03_04_ping_dc01.png)

---

### ✅ Step 5 — Client Successfully Joined to Domain
Confirmed successful domain join operation.

![Domain Joined](screenshots/lab03_05_domain_joined.png)

---

### ✅ Step 6 — Domain Login Validation
Authenticated using domain credentials on the Windows client.

![Domain Login Validation](screenshots/lab03_06_domain_login_validation.png)

---

## 🔍 Validation Performed
- Confirmed correct IP addressing on both systems
- Verified DNS server configuration points to Domain Controller
- Tested connectivity using ICMP ping
- Validated domain join status
- Successfully logged in using domain credentials

---

## 🧠 What I Learned
- How DNS configuration impacts domain join success
- How to validate network configuration using ipconfig and ping
- How Active Directory authentication relies on DNS and connectivity
- How to troubleshoot common domain join and connectivity issues
- How to document technical labs clearly using structured evidence

---

## ✅ Outcome
Successfully joined a Windows client to the Active Directory domain, validated network connectivity and DNS configuration, and confirmed domain authentication functionality.

This lab demonstrates foundational enterprise troubleshooting and identity infrastructure skills.

---
