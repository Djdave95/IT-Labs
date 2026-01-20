# 🧪 Lab 01 – Active Directory Domain Setup & User Provisioning

## 📌 Overview
This lab demonstrates the deployment of a Windows Server Domain Controller and the foundational configuration of an Active Directory environment. The objective was to install Active Directory Domain Services (AD DS), validate default domain containers, design a logical Organizational Unit (OU) structure, and provision domain user accounts following best practices.

This lab simulates a real-world enterprise identity environment used in IT operations, cybersecurity, and Identity & Access Management (IAM).

---

## 🎯 Objectives
- Install and configure Windows Server as a Domain Controller
- Deploy Active Directory Domain Services (AD DS)
- Validate default Active Directory containers
- Design and implement a scalable Organizational Unit (OU) structure
- Create and manage domain user accounts
- Verify successful domain functionality

---

## 🛠️ Tools & Technologies
- Windows Server (Domain Controller)
- Active Directory Users and Computers (ADUC)
- VMware / VirtualBox
- Windows Client VM
- NTFS File System
- Networking Fundamentals (DNS, Domain Services)

---

## 🧱 Lab Architecture
Client VM → Domain Controller (Windows Server)
            │
            ├── Active Directory Domain
            ├── Organizational Units (OUs)
            └── User Accounts

---

## ✅ Lab Steps & Validation

### 🔹 Step 1 – Active Directory Console & Default Containers
Verified the Active Directory Users and Computers console and validated default domain containers created automatically after domain promotion.

Validated Items:
- Builtin
- Computers
- Domain Controllers
- Users
- ForeignSecurityPrincipals
- Managed Service Accounts

Evidence:
![Default Containers](screenshots/01-aduc-default-containers-view.png)
![Expanded Containers](screenshots/02-default-ad-containers-expanded.png)

---

### 🔹 Step 2 – Organizational Unit (OU) Design
Created a structured OU hierarchy to simulate enterprise identity organization and delegation readiness.

OU Structure Created:
- Corp_Users
- Corp_Computers
- Corp_Groups
- IT_Admin

Evidence:
![OU Structure](screenshots/03-custom-ou-structure-created.png)

---

### 🔹 Step 3 – Domain User Provisioning
Provisioned a domain user account and verified placement inside the correct Organizational Unit.

User Created:
- Username: Jose User
- Location: Corp_Users OU

Evidence:
![User Created](screenshots/04-domain-user-created-jose.png)

---

## 🧠 Skills Demonstrated
- Windows Server Administration
- Active Directory Deployment
- Organizational Unit Design
- Identity Lifecycle Management
- User Provisioning
- Access Control Foundations
- Virtualization Management
- Documentation & Evidence Collection

---

## 🔐 Security & Best Practices Applied
- Logical OU separation for scalable management
- Principle of Least Privilege preparation
- Clean naming conventions
- Separation of administrative objects
- Documentation for auditability

---

## 🚀 Next Steps
Future labs will expand this environment with:
- Group Policy Management
- NTFS Permissions
- Role-Based Access Control (RBAC)
- Azure Active Directory / Entra ID integration
- Identity security hardening
