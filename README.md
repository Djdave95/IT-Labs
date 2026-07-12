# IT-Labs: Identity & Access Management Portfolio

Hands-on labs demonstrating hybrid identity skills — on-premises Active Directory administration and cloud identity with Microsoft Entra ID — built and documented the way I'd document them on the job.

**Author:** Jose Pesantez · M.S. Cybersecurity, Fordham University
**Focus:** Identity & Access Management · Microsoft Entra ID · Active Directory

---

## ☁️ Section 1: Identity & Access Management — Cloud (Microsoft Entra ID)

Labs built in a free Microsoft Entra ID tenant, covering the core responsibilities of a cloud IAM analyst.

| # | Lab | Status | Skills |
|---|---|---|---|
| 1 | [Entra ID Tenant Setup & User Lifecycle](./cloud-iam-labs/01-entra-tenant-setup) | 🚧 In progress | Tenant config · users & groups · joiner/mover/leaver |
| 2 | [MFA & Security Defaults](./cloud-iam-labs/02-mfa-security-defaults) | 📋 Planned | MFA enforcement · authentication methods |
| 3 | [Conditional Access Policies](./cloud-iam-labs/03-conditional-access) | 📋 Planned | CA policy design · blocking legacy auth · report-only mode |
| 4 | [SSO App Registration](./cloud-iam-labs/04-sso-app-registration) | 📋 Planned | Enterprise apps · SSO · app assignment |

---

## 🖥️ Section 2: Windows Administration & Endpoint Labs (On-Prem AD)

Foundation labs in a virtualized Windows Server environment — the on-premises half of hybrid identity.

| # | Lab | Skills |
|---|---|---|
| 1 | [Active Directory Domain Setup](./windows-admin-labs/01-ad-domain-setup) | AD DS · DNS · OU design |
| 2 | [Windows 11 Domain Client](./windows-admin-labs/02-win11-domain-client) | Domain join · user provisioning |
| 3 | [Group Policy Management](./windows-admin-labs/03-group-policy) | Security baselines · GPO troubleshooting |
| 4 | [IAM / RBAC / NTFS Permissions](./windows-admin-labs/04-rbac-ntfs-permissions) | Least privilege · RBAC · effective access |

---

## 🧪 Lab Environments

- **Cloud:** Microsoft Entra ID free tenant (+ Entra ID P2 30-day trial for Conditional Access)
- **On-prem:** VMware Workstation · DC01 (Windows Server domain controller) · WIN11-CLIENT (Windows 11 Pro) · host-only lab network

## 🗺️ Why this portfolio

Junior IAM roles live in both worlds: legacy Active Directory and cloud Entra ID. These labs cover the daily work — provisioning identities, enforcing authentication policy, controlling access with least privilege — across both. Every lab includes objectives, step-by-step configuration with screenshots, verification tests, and a "what broke / what I learned" section.

## 📬 Contact

[LinkedIn](https://www.linkedin.com/in/jdp95) · j.d.pesantez09@gmail.com
