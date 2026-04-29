# HIPAA Security Program
## MedCore Health Systems — Complete HIPAA Security Rule Implementation

---

**Organization:** MedCore Health Systems
**Covered Entity Type:** Healthcare Provider
**Program Owner:** Jonathan E. Steele, Chief Information Security Officer (CISO)
**Privacy Officer:** Dr. Rachel Feinberg
**HIPAA Security Official:** Amara Osei, ISSO
**Governing Regulation:** HIPAA Security Rule — 45 CFR Parts 160 and 164, Subparts A and C
**Last Full Program Review:** January 2026
**Next Scheduled Review:** January 2027

---

## Overview

This repository documents MedCore Health Systems' comprehensive HIPAA Security Rule compliance program. MedCore is a HIPAA Covered Entity as a healthcare provider that transmits health information in electronic form in connection with transactions for which HHS has adopted standards.

The HIPAA Security Rule requires covered entities to implement administrative, physical, and technical safeguards to protect the confidentiality, integrity, and availability of electronic Protected Health Information (ePHI). This program documents how MedCore satisfies each of those requirements across its operations and information systems.

---

## Repository Structure

```
hipaa-security-program/
├── README.md                                    ← This file — Program Overview
├── risk-analysis/
│   ├── hipaa-risk-analysis.md                   ← Full HIPAA Risk Analysis (164.308(a)(1)(ii)(A))
│   └── risk-register.md                         ← Active risk register with ratings
├── administrative-safeguards/
│   ├── security-management-process.md           ← 164.308(a)(1) — Security Management Process
│   ├── assigned-security-responsibility.md      ← 164.308(a)(2) — Assigned Responsibility
│   ├── workforce-security.md                    ← 164.308(a)(3) — Workforce Security
│   ├── information-access-management.md         ← 164.308(a)(4) — Information Access Management
│   ├── security-awareness-training.md           ← 164.308(a)(5) — Security Awareness & Training
│   ├── security-incident-procedures.md          ← 164.308(a)(6) — Security Incident Procedures
│   ├── contingency-plan.md                      ← 164.308(a)(7) — Contingency Plan
│   └── evaluation.md                            ← 164.308(a)(8) — Evaluation
├── physical-safeguards/
│   ├── facility-access-controls.md              ← 164.310(a) — Facility Access Controls
│   ├── workstation-use.md                       ← 164.310(b) — Workstation Use
│   ├── workstation-security.md                  ← 164.310(c) — Workstation Security
│   └── device-and-media-controls.md             ← 164.310(d) — Device and Media Controls
├── technical-safeguards/
│   ├── access-controls.md                       ← 164.312(a) — Access Controls
│   ├── audit-controls.md                        ← 164.312(b) — Audit Controls
│   ├── integrity.md                             ← 164.312(c) — Integrity
│   ├── person-authentication.md                 ← 164.312(d) — Person Authentication
│   └── transmission-security.md                ← 164.312(e) — Transmission Security
├── organizational-requirements/
│   ├── business-associate-agreements.md         ← 164.308(b) and 164.314 — BAA Program
│   └── baa-register.md                          ← Active BAA tracking register
└── breach-notification/
    ├── breach-notification-procedures.md        ← 164.400–164.414 — Breach Notification Rule
    └── breach-log.md                            ← Breach assessment and notification log
```

---

## HIPAA Security Rule Requirements — Compliance Summary

### Administrative Safeguards (45 CFR §164.308)

| Standard | Specification | Required/Addressable | MedCore Status |
|----------|--------------|---------------------|---------------|
| §164.308(a)(1) | Security Management Process | Required | Implemented |
| §164.308(a)(1)(ii)(A) | Risk Analysis | Required | Implemented |
| §164.308(a)(1)(ii)(B) | Risk Management | Required | Implemented |
| §164.308(a)(1)(ii)(C) | Sanction Policy | Required | Implemented |
| §164.308(a)(1)(ii)(D) | Information System Activity Review | Required | Implemented |
| §164.308(a)(2) | Assigned Security Responsibility | Required | Implemented — Amara Osei, ISSO |
| §164.308(a)(3) | Workforce Security | Required | Implemented |
| §164.308(a)(3)(ii)(A) | Authorization and/or Supervision | Addressable | Implemented |
| §164.308(a)(3)(ii)(B) | Workforce Clearance Procedure | Addressable | Implemented |
| §164.308(a)(3)(ii)(C) | Termination Procedures | Addressable | Implemented |
| §164.308(a)(4) | Information Access Management | Required | Implemented |
| §164.308(a)(4)(ii)(A) | Isolating Healthcare Clearinghouse Functions | Addressable | Not Applicable |
| §164.308(a)(4)(ii)(B) | Access Authorization | Addressable | Implemented |
| §164.308(a)(4)(ii)(C) | Access Establishment and Modification | Addressable | Implemented |
| §164.308(a)(5) | Security Awareness and Training | Required | Implemented |
| §164.308(a)(5)(ii)(A) | Security Reminders | Addressable | Implemented |
| §164.308(a)(5)(ii)(B) | Protection from Malicious Software | Addressable | Implemented |
| §164.308(a)(5)(ii)(C) | Log-in Monitoring | Addressable | Implemented |
| §164.308(a)(5)(ii)(D) | Password Management | Addressable | Implemented |
| §164.308(a)(6) | Security Incident Procedures | Required | Implemented |
| §164.308(a)(6)(ii) | Response and Reporting | Required | Implemented |
| §164.308(a)(7) | Contingency Plan | Required | Implemented |
| §164.308(a)(7)(ii)(A) | Data Backup Plan | Required | Implemented |
| §164.308(a)(7)(ii)(B) | Disaster Recovery Plan | Required | Implemented |
| §164.308(a)(7)(ii)(C) | Emergency Mode Operation Plan | Required | Implemented |
| §164.308(a)(7)(ii)(D) | Testing and Revision Procedures | Addressable | Implemented |
| §164.308(a)(7)(ii)(E) | Applications and Data Criticality Analysis | Addressable | Implemented |
| §164.308(a)(8) | Evaluation | Required | Implemented |
| §164.308(b) | Business Associate Contracts | Required | Implemented |

### Physical Safeguards (45 CFR §164.310)

| Standard | Specification | Required/Addressable | MedCore Status |
|----------|--------------|---------------------|---------------|
| §164.310(a)(1) | Facility Access Controls | Required | Implemented |
| §164.310(a)(2)(i) | Contingency Operations | Addressable | Implemented |
| §164.310(a)(2)(ii) | Facility Security Plan | Addressable | Implemented |
| §164.310(a)(2)(iii) | Access Control and Validation Procedures | Addressable | Implemented |
| §164.310(a)(2)(iv) | Maintenance Records | Addressable | Implemented |
| §164.310(b) | Workstation Use | Required | Implemented |
| §164.310(c) | Workstation Security | Required | Implemented |
| §164.310(d)(1) | Device and Media Controls | Required | Implemented |
| §164.310(d)(2)(i) | Disposal | Required | Implemented |
| §164.310(d)(2)(ii) | Media Re-use | Required | Implemented |
| §164.310(d)(2)(iii) | Accountability | Addressable | Implemented |
| §164.310(d)(2)(iv) | Data Backup and Storage | Addressable | Implemented |

### Technical Safeguards (45 CFR §164.312)

| Standard | Specification | Required/Addressable | MedCore Status |
|----------|--------------|---------------------|---------------|
| §164.312(a)(1) | Access Controls | Required | Implemented |
| §164.312(a)(2)(i) | Unique User Identification | Required | Implemented |
| §164.312(a)(2)(ii) | Emergency Access Procedure | Required | Implemented |
| §164.312(a)(2)(iii) | Automatic Logoff | Addressable | Implemented |
| §164.312(a)(2)(iv) | Encryption and Decryption | Addressable | Implemented |
| §164.312(b) | Audit Controls | Required | Implemented |
| §164.312(c)(1) | Integrity | Required | Implemented |
| §164.312(c)(2) | Mechanism to Authenticate ePHI | Addressable | Implemented |
| §164.312(d) | Person or Entity Authentication | Required | Implemented |
| §164.312(e)(1) | Transmission Security | Required | Implemented |
| §164.312(e)(2)(i) | Integrity Controls | Addressable | Implemented |
| §164.312(e)(2)(ii) | Encryption | Addressable | Implemented |

---

## Key Program Metrics

| Metric | Current Status | Target | Last Verified |
|--------|---------------|--------|--------------|
| HIPAA Security Risk Analysis — completed and current | Yes | Annual | February 2026 |
| Security awareness training completion | 98.4% | 100% | March 2026 |
| Business Associate Agreements — all current | 100% (47 of 47) | 100% | January 2026 |
| ePHI breach incidents reported to HHS OCR | 0 (current ATO period) | 0 | April 2026 |
| Annual HIPAA Security Rule evaluation — completed | Yes | Annual | January 2026 |
| Workforce sanctions policy — in place | Yes | Yes | January 2026 |
| Contingency plan tested | Yes — Nov 2025 | Annual | November 2025 |

---

## Regulatory References

| Reference | Description |
|-----------|-------------|
| 45 CFR Part 160 | General Administrative Requirements |
| 45 CFR Part 164, Subpart A | General Provisions |
| 45 CFR Part 164, Subpart C | Security Standards |
| 45 CFR Part 164, Subpart D | Notification in Case of Breach |
| HITECH Act §13401 | Application of Security Provisions to Business Associates |
| HHS OCR Guidance on HIPAA Security Rule | Interpretive guidance |
| NIST SP 800-66 Rev 2 | Implementing the HIPAA Security Rule |

---

*MedCore Health Systems — INTERNAL / SENSITIVE*
*HIPAA Security Program Documentation | Maintained by: Amara Osei, ISSO*
*Do not share externally without CISO and Privacy Officer approval*
