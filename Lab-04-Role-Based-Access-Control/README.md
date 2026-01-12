# Lab 04 – Role-Based Access Control (RBAC) & NTFS Permissions

## 🎯 Objective
Design and enforce role-based access control using Active Directory security groups and NTFS permissions to protect shared resources.

## 🛠️ Tools Used
- Windows Server (Domain Controller / File Server)
- Active Directory Users & Computers
- NTFS Permissions
- Windows Client VM

## 🧪 Lab Overview

This lab demonstrates how enterprise environments control access using security groups rather than assigning permissions directly to users.

Users are mapped to roles, roles are mapped to permissions, and access is validated from a domain-joined client machine.

---

## 🧪 Lab Steps

### ✅ Step 1 – User & Group Creation
- Create domain users for HR, Finance, and IT roles
- Create security groups for each department
- Assign users to their respective groups

📸 Screenshot: Users and group membership

---

### ✅ Step 2 – Shared Folder Setup
- Create departmental shared folders on the file server
- Configure network sharing

📸 Screenshot: Folder structure and sharing configuration

---

### ✅ Step 3 – NTFS Permission Enforcement
- Disable inherited permissions
- Assign least-privilege access using security groups
- Remove unnecessary permissions

📸 Screenshot: NTFS permissions configuration

---

### ✅ Step 4 – Access Validation
- Login as each user from client machine
- Validate authorized access
- Validate denied access

📸 Screenshot: Successful access and access denied

---

## 📸 Evidence
Screenshots will be uploaded to:
