# Business Associate Agreement (BAA) Register
## MedCore Health Systems
### 45 CFR §164.308(b) and §164.314

---

**Register Owner:** Dr. Rachel Feinberg, Privacy Officer
**Co-Owner:** Amara Osei, ISSO
**Last Full Review:** January 2026
**Next Review:** January 2027
**Classification:** CONFIDENTIAL — INTERNAL USE ONLY

---

## Overview

Under 45 CFR §164.308(b), MedCore Health Systems must obtain satisfactory assurances from Business Associates (BAs) that ePHI will be appropriately safeguarded. These assurances must be documented in a written Business Associate Agreement (BAA) that meets the requirements of 45 CFR §164.314 and §164.504(e).

A Business Associate is a person or entity who performs certain functions or activities that involve the use or disclosure of protected health information on behalf of, or provides services to, a covered entity.

This register tracks all active BAAs, upcoming renewals, and terminated agreements.

---

## Active Business Associate Agreements

### Tier 1 — Critical Business Associates (ePHI Access)

| # | Business Associate | Service Description | BAA Version | Execution Date | Renewal Date | ePHI Access Type | BAA Location | Status |
|---|-------------------|--------------------|-----------|--------------|-----------|--------------------|-------------|--------|
| 1 | Amazon Web Services, Inc. | Cloud infrastructure — AWS GovCloud hosting EHRP | AWS BAA v3.1 | March 2021 | Auto-renewal with Master Agreement | Infrastructure hosting; AWS staff have limited access per shared responsibility model | Legal / Contracts folder | ACTIVE |
| 2 | Okta, Inc. | Identity and Access Management — authentication for all EHRP users | Okta BAA v2.0 | January 2024 | January 2027 | Authentication logs may include user identifiers; limited ePHI | Legal / Contracts folder | ACTIVE |
| 3 | CrowdStrike, Inc. | Endpoint Detection and Response (EDR) — security monitoring on EHRP endpoints | CrowdStrike BAA v1.2 | January 2024 | January 2027 | EDR agents may capture system memory/files potentially containing ePHI | Legal / Contracts folder | ACTIVE |
| 4 | Qualys, Inc. | Vulnerability Management — authenticated scanning of EHRP systems | Qualys BAA v1.0 | January 2024 | January 2027 | Network scanning; no direct ePHI access; scan credentials only | Legal / Contracts folder | ACTIVE |
| 5 | Splunk Inc. | SIEM — log aggregation including audit logs that may reference ePHI metadata | Splunk BAA v2.0 | January 2024 | January 2027 | Audit logs; no clinical ePHI stored in SIEM | Legal / Contracts folder | ACTIVE |
| 6 | Surescripts, LLC | Electronic Prescribing (e-Rx) — transmits prescription data on behalf of MedCore | Surescripts BAA v4.2 | July 2022 | July 2025 — **RENEWAL OVERDUE** | Prescription ePHI including medication history | Legal / Contracts folder | **RENEWAL REQUIRED** |
| 7 | Regional Health Information Exchange (HIE) | Health Information Exchange — shares patient records with authorized providers | HIE Participation BAA v3.0 | January 2023 | January 2026 — **DUE FOR RENEWAL** | Full clinical ePHI for participating patients | Legal / Contracts folder | **RENEWAL IN PROGRESS** |
| 8 | IBM Corporation | Legacy HL7 Interface Engine support and maintenance | IBM BAA v1.1 | March 2023 | March 2026 — Due for renewal | Maintenance access may encounter HL7 message data | Legal / Contracts folder | RENEWAL IN PROGRESS |
| 9 | Meridian Security Advisors, LLC | HIPAA Security Assessment / RMF Assessment services | Meridian BAA v1.0 | January 2026 | January 2028 | Assessment activities expose assessors to ePHI system access | Legal / Contracts folder | ACTIVE |
| 10 | LabCorp (Laboratory Corporation of America) | Reference laboratory services — receives lab orders and returns results | LabCorp BAA v5.0 | September 2022 | September 2025 — **RENEWAL OVERDUE** | Lab orders and results containing ePHI | Legal / Contracts folder | **RENEWAL REQUIRED** |

### Tier 2 — Standard Business Associates (Limited ePHI Access)

| # | Business Associate | Service Description | BAA Version | Execution Date | Renewal Date | Status |
|---|-------------------|--------------------|-----------|--------------|-----------|----|
| 11 | MedCore Billing Services, LLC | Third-party billing and claims processing | MBS BAA v2.1 | January 2024 | January 2027 | ACTIVE |
| 12 | AtlantaShred, Inc. | Document and media destruction services | AS BAA v1.0 | January 2025 | January 2028 | ACTIVE |
| 13 | Recall Corporation | Medical records storage and retrieval | Recall BAA v3.0 | March 2022 | March 2025 — **RENEWAL REQUIRED** | **RENEWAL REQUIRED** |
| 14 | DataVault Backup Solutions | Off-site backup verification services | DV BAA v1.0 | January 2024 | January 2027 | ACTIVE |
| 15 | Physician Answering Service of Atlanta | After-hours call service — may receive patient identifying information | PASA BAA v2.0 | July 2023 | July 2026 | ACTIVE |

*(Register continues for all 47 active BAs — abbreviated here for readability. Full register maintained in Privacy Officer's secure document system.)*

---

## BAA Renewal Action Items

The following BAAs require immediate attention:

| Priority | Business Associate | Issue | Action Required | Responsible | Due Date |
|----------|-------------------|-------|----------------|------------|---------|
| HIGH | Surescripts, LLC | BAA expired July 2025 | Execute renewal immediately; interim risk review | Privacy Officer + Legal | April 30, 2026 |
| HIGH | LabCorp | BAA expired September 2025 | Execute renewal immediately | Privacy Officer + Legal | April 30, 2026 |
| HIGH | Recall Corporation | BAA expired March 2025 | Execute renewal or terminate relationship | Privacy Officer + Legal | April 30, 2026 |
| MEDIUM | Regional HIE | BAA expired January 2026 | Renewal in final negotiation | Privacy Officer | May 15, 2026 |
| MEDIUM | IBM Corporation | BAA due March 2026 | Renewal in progress | Privacy Officer | May 31, 2026 |

**Note to Privacy Officer:** The 3 HIGH priority expired BAAs represent a compliance gap. ePHI continues to flow to these BAs without current contractual protections. Interim risk mitigation: ISSO has been notified; enhanced monitoring of these data flows is in place; Legal Counsel is aware. This is tracked as a MODERATE risk in the Risk Register (R-004).

---

## BAA Program Statistics

| Metric | Value | Target |
|--------|-------|--------|
| Total active BAAs | 47 | N/A |
| BAAs current (not expired) | 44 | 100% |
| BAAs expired — renewal pending | 3 | 0 |
| BAAs with annual review completed (2026) | 47 of 47 | 100% |
| Average BAA term | 3 years | N/A |

---

## BAA Termination Register

| Business Associate | Service | Termination Date | ePHI Destruction Confirmed | Destruction Certificate |
|-------------------|---------|-----------------|--------------------------|------------------------|
| PracticeFusion EHR | Legacy EHR (predecessor to EHRP) | June 2022 | Yes | Certificate on file — June 30, 2022 |
| MedQuist Transcription | Medical transcription services | March 2023 | Yes | Certificate on file — March 31, 2023 |
| Legacy Radiology PACS vendor | Imaging system (replaced by EHRP Imaging) | December 2023 | Yes | Certificate on file — January 15, 2024 |

---

*MedCore Health Systems — CONFIDENTIAL / INTERNAL USE ONLY*
*BAA Register | Last Updated: January 2026 | Maintained by: Dr. Rachel Feinberg, Privacy Officer*
