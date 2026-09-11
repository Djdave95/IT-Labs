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

- **GV.PO-01** — Lab 3's domain password and account lockout
