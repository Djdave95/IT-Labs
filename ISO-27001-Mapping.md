# Mapping My IAM Labs to ISO/IEC 27001:2022

> Labs 1–4 of this portfolio were built to practice hands-on identity and access management skills, not to chase a certification checklist. This document works backward from what was actually built and asks: which ISO/IEC 27001:2022 Annex A controls does this work actually produce evidence for — and, just as importantly, which parts of the standard does it not touch at all? A full ISO 27001 Information Security Management System (ISMS) requires far more than technical controls, and this document is scoped honestly to what four home-lab projects can actually demonstrate.

**Framework version:** ISO/IEC 27001:2022, Annex A (93 controls across 4 themes: Organizational, People, Physical, Technological). Annex A lists control titles; ISO/IEC 27002:2022 provides the corresponding implementation guidance under identical clause numbers.
**Labs covered:** [01 – AD Domain Setup](./windows-admin-labs/01-ad-domain-setup) · [02 – Windows 11 Domain Client](./windows-admin-labs/02-win11-domain-client) · [03 – Group Policy Management](./windows-admin-labs/03-group-policy) · [04 – IAM / RBAC / NTFS Permissions](./windows-admin-labs/04-rbac-ntfs-permissions)

---

## Why this document exists

ISO/IEC 27001:2022 is a certifiable management-system standard, not a purely technical checklist — most of it (Clauses 4–10: context, leadership, planning, support, operation, evaluation, improvement) concerns organizational governance that a set of home-lab projects cannot demonstrate on its own. Annex A, the 93-control reference used to build an organization's Statement of Applicability, is the part most directly testable through hands-on technical work. This document maps Labs 1–4 against the Annex A controls in the Identity and Access Management cluster (Clauses 5.15–5.18, 5.3, and 8.2–8.5) and is explicit about the much larger portion of the standard — People, Physical, and most of the Organizational and Technological themes — that this portfolio does not address.

## Coverage at a glance

| Theme | Coverage | Primary lab(s) |
|---|---|---|
| **Organizational (A.5)** | Strong | Labs 1, 3, 4 — access control policy, identity management, access rights |
| **People (A.6)** | Not covered | — |
| **Physical (A.7)** | Not covered | — |
| **Technological (A.8)** | Partial | Labs 2, 3, 4 — authentication, information access restriction |

## Detailed mapping

### A.5.15 — Access control
*"Rules to control physical and logical access to information and other associated assets are established and implemented based on business and information security requirements."*

Every lab in this portfolio is, at bottom, an implementation of this control. Lab 3's Group Policy work (domain password/lockout baseline plus an OU-targeted restriction) and Lab 4's NTFS/share design (security-group-scoped Modify permissions in place of broad access) are both concrete, enforced access control rules — not policy statements, but configurations that were tested and shown to work.

### A.5.16 — Identity management
*"The full life cycle of identities is managed."*

Lab 1 established the Active Directory OU structure and initial user accounts that every subsequent identity in this environment lives in. Lab 2 extended that lifecycle by provisioning a domain-joined client and managing accounts against it — including password resets and enable/disable actions, which are identity lifecycle events, not just troubleshooting.

### A.5.17 — Authentication information
*"Allocation and management of authentication information is controlled by a management process."*

Lab 3's domain-wide password policy (12-character minimum, complexity enabled, password history, account lockout after 5 attempts) is a direct, enforced implementation of this control — set once at the Default Domain Policy level so it governs authentication information for every account in the domain, then verified by testing an actual password change against it.

### A.5.18 — Access rights
*"Access rights to information and other associated assets are provisioned, reviewed, modified, and removed in accordance with the organization's topic-specific policy on and rules for access control."*

This is the single strongest control in the portfolio. Lab 4 provisioned access rights through role-based security groups (`HR-ReadWrite`, `IT-ReadWrite`) rather than per-user grants, scoped each to Modify (not Full Control) on its matching department folder, and — critically — reviewed and corrected those rights after the Effective Access tool and a live write test surfaced a permission that had been granted more broadly than intended. Provisioning, review, and correction all happened in this one lab, which is the complete lifecycle A.5.18 describes.

### A.5.3 — Segregation of duties
*"Conflicting duties and conflicting areas of responsibility are segregated."*

Lab 4's department-scoped access model — HR staff can write to the HR share and nowhere else, IT staff the reverse — is a working example of segregating access by role so that one identity's legitimate access in one area doesn't extend into another's.

### A.8.3 — Information access restriction
*"Access to information and other associated assets is restricted in accordance with the established topic-specific policy on access control."*

The NTFS permission design in Lab 4 is a direct technical implementation of this control: department folders restricted at the file-system layer to the matching security group, verified with the Effective Access tool and confirmed with live read/write tests from both an authorized and an unauthorized account.

### A.8.5 — Secure authentication
*"Secure authentication technologies and procedures are implemented based on information access restrictions and the topic-specific policy on access control."*

Lab 2's domain join and Lab 3's account lockout policy (protecting against repeated failed authentication attempts) both contribute here, though this portfolio does not implement multi-factor authentication, so coverage of this control is partial rather than complete.

### A.8.2 — Privileged access rights
*"The allocation and use of privileged access rights are restricted and managed."*

Touched only incidentally: Domain Admin credentials were used to recover DC01 and WIN11-CLIENT administrator access, and Domain Admins inherit local admin rights on domain-joined machines by default. Neither lab formally designs or audits a privileged-access tier the way Labs 1 and 4 do for standard department access, so this is listed as a partial touchpoint, not a demonstrated control.

## What's not covered — and why that's worth saying

- **People (A.6, all 8 controls)** — screening, terms and conditions of employment, security awareness training, disciplinary process, and remote working controls are organizational/HR processes with no equivalent in a technical home lab.
- **Physical (A.7, all 14 controls)** — physical security perimeters, equipment siting, clear desk/clear screen, and similar controls don't apply to a virtualized lab environment with no physical facility to secure.
- **Most of Technological (A.8)** — cryptography (A.8.24), backup (A.8.13), logging and monitoring (A.8.15, A.8.16), malware defenses (A.8.7), vulnerability management (A.8.8), and secure development controls are all untouched by these labs.
- **The ISMS itself (main Clauses 4–10)** — risk assessment methodology, a defined ISMS scope, management review, internal audit, and the Statement of Applicability process that Annex A actually supports are organizational activities this portfolio does not attempt to demonstrate.

Naming these gaps isn't a weakness in the portfolio — a home lab claiming full ISO 27001 coverage would be the actual red flag, since the standard is fundamentally a management-system certification, not a technical control list. This is an honest account of where four hands-on labs land within a much larger standard.

## Summary

Across Labs 1–4, this portfolio produces concrete, verifiable evidence for the Annex A controls that govern identity and access — A.5.16, A.5.17, A.5.18, A.5.3, and A.8.3 in particular, where the OU-targeted GPO from Lab 3 and the NTFS least-privilege design from Lab 4 are directly observable in the linked lab READMEs rather than asserted. It documents, just as deliberately, the much larger portion of ISO/IEC 27001:2022 — the People and Physical themes, most of Technological, and the ISMS governance clauses outside Annex A — that this work does not reach. That combination is the point of this document: specific, evidenced control coverage, paired with an honest account of scope, rather than a blanket claim of framework alignment.

---
*Part of the [IT-Labs portfolio](./README.md) · Jose Pesantez*
