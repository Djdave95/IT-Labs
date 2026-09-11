# Mapping My IAM Labs to NIST CSF 2.0

> Labs 1–4 of this portfolio were built to practice hands-on identity and access management skills, not to chase a framework checklist. This document works backward from what was actually built and asks: which NIST Cybersecurity Framework (CSF) 2.0 outcomes does this work actually satisfy — and, just as importantly, which ones does it *not* touch yet? Framework familiarity is easy to claim and hard to demonstrate; this is the difference.

**Framework version:** NIST CSF 2.0 (NIST CSWP 29, February 2024)
**Labs covered:** [01 – AD Domain Setup](./windows-admin-labs/01-ad-domain-setup) · [02 – Windows 11 Domain Client](./windows-admin-labs/02-win11-domain-client) · [03 – Group Policy Management](./windows-admin-labs/03-group-policy) · [04 – IAM / RBAC / NTFS Permissions](./windows-admin-labs/04-rbac-ntfs-permissions)

---

## Why this document exists

CSF 2.0 organizes cybersecurity outcomes into 6 Functions (Govern, Identify, Protect, Detect, Respond, Recover), broken into 22 Categories and further into Subcategories — the framework's actual unit of "did you do the thing." Most portfolios that reference a framework do it as decoration: a logo, a sentence, a vague claim of "framework-aligned." This document instead cites the specific Subcategory codes each lab produces evidence for, and is explicit about the Functions this portfolio doesn't cover yet, since a security professional who only ever shows their strengths hasn't shown they understand the framework.

## Coverage at a glance

| Function | Coverage | Primary lab(s) |
|---|---|---|
| **GV** — Govern | Partial | Lab 3 (policy) |
| **ID** — Identify | Partial | Labs 1–2 (asset/account foundation) |
| **PR** — Protect | Strong | Labs 1–4 (this is the core of the work) |
| **DE** — Detect | Partial | Lab 3, Lab 4 (verification steps) |
| **RS** — Respond | Anecdotal | Lab 4 (the permission-leak investigation) |
| **RC** — Recover | Not covered | — |

## Detailed mapping

### PR.AA — Identity Management, Authentication, and Access Control
*"Access to physical and logical assets is limited to authorized users, services, and hardware and managed commensurate with the assessed risk of unauthorized access."*

This is the category the whole portfolio is built around — every lab contributes evidence here.

- **PR.AA-01** (identities and credentials for authorized users are managed) — Lab 1 established the AD user/OU structure that all identities live in; Lab 2 provisioned a domain-joined client and user accounts against it; Lab 4 created and populated the `HR-ReadWrite`/`IT-ReadWrite` security groups that scope access by role rather than by individual.
- **PR.AA-03** (users are authenticated) — Lab 2's domain join and Lab 3's domain-wide password/lockout policy (12-char minimum, 5-attempt lockout) both directly strengthen how authentication is enforced.
- **PR.AA-05** (access permissions, entitlements, and authorizations are defined in policy, managed, enforced, reviewed, and incorporate least privilege and separation of duties) — **this is the single strongest subcategory in the whole portfolio.** Lab 3's OU-targeted GPO (Control Panel restricted for HR only, proven with a same-machine control test) and Lab 4's NTFS least-privilege design (Modify, not Full Control, scoped to department security groups, verified with Effective Access and `icacls`) are both textbook PR.AA-05 in practice, not theory.

### GV.PO — Policy
*"Organizational cybersecurity policy is established, communicated, and enforced."*

- **GV.PO-01** — Lab 3's domain password and account lockout policy is a real, enforced organizational policy (not just a note in a document) — set at the Default Domain Policy level so it applies universally, then verified by testing an actual password change against it.

### DE.CM — Continuous Monitoring
*"Assets are monitored to find anomalies, indicators of compromise, and other potentially adverse events."*

- **DE.CM-03** (personnel activity and technology usage are monitored) — every lab in this portfolio ends with a verification step rather than trusting configuration alone: `gpresult /r` in Lab 3, and the Effective Access tool plus live `New-Item` write tests as sjohnson/mlopez in Lab 4. The habit of checking *actual* enforced behavior instead of *intended* configuration is exactly what this subcategory is asking for.

### DE.AE — Adverse Event Analysis / RS.MI — Incident Mitigation
*"Anomalies are analyzed" / "Incidents are mitigated."*

- Lab 4 produced a genuine (if small-scale) example of this pair, not a staged one: the Effective Access tool surfaced write access that shouldn't have existed for a user outside the intended security group. That anomaly was investigated methodically (group membership → visible ACL entries → live confirmation) before concluding the GUI-reported permission state didn't match what was actually enforced, then remediated by rebuilding the NTFS ACLs from scratch with `icacls` and re-verified. It's a small incident, but the process — detect, investigate, remediate, verify — is the real shape of DE.AE/RS.MI, and a more credible demonstration of it than a clean, uneventful configuration run would have provided.

### ID.AM — Asset Management
*"Assets... are identified and managed consistent with their relative importance to organizational objectives."*

- **ID.AM-01/02** — Labs 1 and 2 stood up and documented the actual inventory this portfolio runs on: the domain controller (DC01) and a domain-joined client (WIN11-CLIENT), both with defined roles.

## What's not covered — and why that's worth saying

- **GV.RM (Risk Management Strategy) and ID.RA (Risk Assessment)** — nothing in this portfolio formally assesses or prioritizes risk; the labs assume the value of least privilege rather than deriving it from a documented risk analysis. A natural next step would be a short risk register for the lab environment.
- **PR.DS (Data Security)** — no encryption at rest, no data classification. The NTFS work in Lab 4 controls *who* can access files, not how the data itself is protected.
- **PR.PS (Platform Security)** — no OS hardening baseline, patching cadence, or configuration management was part of these labs.
- **RC (Recover)** — no backup, restore, or disaster recovery testing has been done in this environment at all.
- **GV.SC (Supply Chain)** — not applicable; there's no vendor/third-party component to this lab environment.

Naming these gaps isn't a weakness in the portfolio — claiming full framework coverage from four labs in a home environment would be the actual red flag. This list is effectively next steps for extending the portfolio.

## Summary

Across Labs 1–4, this portfolio produces concrete, falsifiable evidence for several NIST CSF 2.0 subcategories — PR.AA-05 in particular, where the OU-targeted GPO from Lab 3 and the NTFS least-privilege design from Lab 4 are both directly observable in the linked lab READMEs rather than merely asserted. It also documents, deliberately, the Functions and Categories this work does not yet reach: formal risk assessment, data protection, platform hardening, and recovery. That combination — specific, evidenced coverage alongside an honest account of the gaps — is the point of this document: framework alignment that can be checked against real, linked work, rather than a claim taken at face value.

---
*Part of the [IT-Labs portfolio](./README.md) · Jose Pesantez*
