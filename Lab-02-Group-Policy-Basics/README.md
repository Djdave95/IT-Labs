# 📄 Lab 02 – Group Policy Configuration & Management

## 🎯 Objective
Configure and validate Group Policy Objects (GPOs) in an Active Directory environment to centrally manage user settings, drive mappings, security policies, and shared resource access.

This lab demonstrates practical experience using Group Policy Management to automate configuration and enforce consistent policies across domain-joined systems.

---

## 🖥️ Environment
- Windows Server 2022 (Domain Controller)
- Active Directory Domain Services (AD DS)
- Group Policy Management Console (GPMC)
- Windows Client (Domain Joined)
- VMware / VirtualBox Lab Environment

---

## ✅ Tasks Performed
- Created and linked a new Group Policy Object (GPO)
- Configured automatic drive mapping using Group Policy Preferences
- Applied a security banner logon policy
- Created and secured a shared folder using group permissions
- Verified policy deployment and access control

---

## 📸 Evidence

### ✅ Step 1 — Drive Mapping via Group Policy
Mapped a network drive (`S:`) to a shared folder hosted on the domain controller using Group Policy Preferences.

![Drive Mapping](screenshots/01-drive-mapping-gpo.png)

---

### ✅ Step 2 — GPO Created and Linked
Created the GPO and linked it to the appropriate Organizational Unit for policy application.

![GPO Created](screenshots/02-gpo-created-linked.png)

---

### ✅ Step 3 — Security Banner Policy Applied
Configured an interactive logon message to display a security notice before user login.

![Security Banner](screenshots/03-security-banner-policy.png)

---

### ✅ Step 4 — Shared Folder Permissions Configured
Configured share-level permissions using security groups to control access to the shared folder.

![Shared Permissions](screenshots/04-shared-folder-permissions.png)

---

## 🔍 Validation Performed
- Forced policy refresh using **gpupdate /force**
- Verified applied policies using **gpresult /r**
- Confirmed drive mapping using **net use**
- Validated user access to shared resources

---

## 🧠 What I Learned
- How Group Policy Objects are created, linked, and scoped within Active Directory
- How to automate drive mappings using Group Policy Preferences
- How to enforce security banners for compliance and user awareness
- How NTFS and share permissions work together for access control
- How centralized policy management improves security and operational efficiency
- How to document enterprise-style configurations using screenshots and GitHub

---

## ✅ Outcome
Successfully deployed and validated Group Policy configurations that automated drive mapping, enforced security policies, and secured shared resources within a domain environment.

This lab demonstrates hands-on experience with enterprise Windows administration and policy management.
