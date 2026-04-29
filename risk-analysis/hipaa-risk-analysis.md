# HIPAA Security Risk Analysis
## MedCore Health Systems
### 45 CFR §164.308(a)(1)(ii)(A)

---

**Organization:** MedCore Health Systems
**Covered Entity Type:** Healthcare Provider
**Risk Analysis Version:** 3.0
**Date Completed:** February 1, 2026
**Conducted By:** Amara Osei, ISSO
**Reviewed By:** Jonathan E. Steele, CISO
**Approved By:** Marcus T. Hargrove, CEO
**Methodology:** NIST SP 800-30 Rev 1 / NIST SP 800-66 Rev 2
**Classification:** RESTRICTED — FOR AUTHORIZED PERSONNEL ONLY

---

## 1. Purpose and Legal Basis

The HIPAA Security Rule at 45 CFR §164.308(a)(1)(ii)(A) requires covered entities to conduct an accurate and thorough assessment of the potential risks and vulnerabilities to the confidentiality, integrity, and availability of electronic protected health information (ePHI) held by the covered entity.

This Risk Analysis is MedCore Health Systems' annual assessment, completed as required by the Security Rule. It documents the scope of ePHI in the organization, identifies threats and vulnerabilities, assesses current controls, determines the likelihood and impact of potential risk events, and establishes the prioritized risk register that drives MedCore's risk management program.

---

## 2. Scope — ePHI Systems and Locations

### 2.1 Electronic Systems Containing ePHI

| System | ePHI Type | Location | Approximate Record Count |
|--------|----------|----------|------------------------|
| MedCore EHRP — Clinical Database | Patient records, diagnoses, medications, lab results, clinical notes | AWS GovCloud (Primary) | ~340,000 patient records |
| MedCore EHRP — Medical Imaging | DICOM images, radiology reports | AWS GovCloud (S3) | ~2.1 million imaging files |
| EHRP Backup Storage | All EHRP ePHI categories | AWS S3 Glacier (GovCloud) | Full backup copy |
| Legacy HL7 Interface Engine | In-transit HL7 messages (transient) | On-premises, Atlanta data center | Transient only (< 15 min retention) |
| Lab Information System Interface | Laboratory orders and results | On-premises integration point | Interface data only |
| Email System (Microsoft 365) | Incidental ePHI in clinical emails | Microsoft GCC High cloud | Variable |
| Workstations (clinical) | Cached session data only; no persistent ePHI storage | On-premises, all facilities | Session only |
| Mobile Devices (MDM-managed) | Email access; no ePHI downloaded per policy | User devices with MDM | None (per policy) |

### 2.2 ePHI Categories Present

Based on the system inventory, MedCore EHRP stores and processes the following categories of ePHI:
- Patient demographics (name, DOB, address, contact information)
- Clinical diagnoses and ICD-10 codes
- Medication records and prescription history
- Laboratory orders and results
- Medical imaging data (radiology, pathology)
- Surgical and procedure records
- Mental health and behavioral health records
- Substance abuse treatment records (also subject to 42 CFR Part 2)
- Billing and claims data
- Insurance and authorization information
- Appointment and scheduling data

---

## 3. Threat Identification

Threats are categorized as environmental, natural, or human-caused. The following threats are applicable to MedCore's ePHI environment:

### 3.1 Human-Caused Threats — Deliberate

| Threat ID | Threat | Source | Target |
|-----------|--------|--------|--------|
| T-H-001 | Unauthorized access / insider threat — workforce member accessing ePHI without need | Internal workforce | EHRP clinical data |
| T-H-002 | Ransomware / malware attack | External threat actor | EHRP servers, workstations |
| T-H-003 | Phishing / social engineering attack targeting credentials | External threat actor | Workforce credentials |
| T-H-004 | External network attack / exploitation of vulnerabilities | External threat actor | EHRP web services, APIs |
| T-H-005 | Theft of device containing ePHI | External / opportunistic | Workstations, mobile devices |
| T-H-006 | Supply chain attack through compromised vendor | External / sophisticated | EHRP software, cloud services |
| T-H-007 | Unauthorized physical access to server room | Internal or external | On-premises servers |
| T-H-008 | Improper disposal of media containing ePHI | Internal (negligent) | Retired hardware |
| T-H-009 | ePHI disclosure via unsecured email / messaging | Internal (negligent) | ePHI in email |
| T-H-010 | Unauthorized modification of clinical data | Internal (malicious) | EHRP clinical database |

### 3.2 Human-Caused Threats — Unintentional

| Threat ID | Threat | Source | Target |
|-----------|--------|--------|--------|
| T-U-001 | Misconfiguration of cloud resources exposing ePHI | IT staff error | S3 buckets, databases |
| T-U-002 | Accidental disclosure of ePHI to wrong recipient | Clinical staff error | Email, fax, verbal |
| T-U-003 | Unintentional deletion of ePHI | IT staff / user | EHRP database, backups |
| T-U-004 | Failure to apply critical security patch | IT staff oversight | Servers, workstations |
| T-U-005 | Inadequate access removal for terminated employee | HR/IT coordination failure | All ePHI systems |

### 3.3 Environmental and Natural Threats

| Threat ID | Threat | Likelihood (Atlanta, GA) |
|-----------|--------|------------------------|
| T-E-001 | Power failure / utility outage | Moderate (summer storms) |
| T-E-002 | Severe weather (tornado, ice storm) impacting facilities | Low-Moderate |
| T-E-003 | Fire at primary data center or facility | Low |
| T-E-004 | AWS GovCloud regional outage | Very Low |
| T-E-005 | Network connectivity loss (ISP outage) | Low-Moderate |

---

## 4. Vulnerability Identification

The following vulnerabilities were identified through review of vulnerability scan results, prior assessment findings, system documentation, and interviews:

| Vuln ID | Vulnerability Description | Affected System(s) | Discovery Method |
|---------|--------------------------|-------------------|-----------------|
| V-001 | Legacy HL7 Interface Engine cannot encrypt message queues at rest | On-premises HL7 engine | Architecture review |
| V-002 | Lab equipment interfaces use proprietary protocols without FIPS cryptography | Lab integration points | Vendor documentation review |
| V-003 | 14 read-only billing analytics accounts use software TOTP MFA (not hardware keys) | EHRP analytics access | IAM review |
| V-004 | Residual unpatched MODERATE vulnerabilities on 3 legacy on-premises servers (Moderate CVSS 5.x) | On-premises servers | Qualys scan Jan 2026 |
| V-005 | Two staff members have not completed annual security awareness training (compliance: 98.4%) | Workforce | Training completion report |
| V-006 | PHI-containing email sent via standard email by 1 clinical user in Q4 2025 (addressed via training) | Email system | SIEM detection |
| V-007 | Emergency break-glass accounts have longer than ideal password rotation (quarterly vs. monthly) | Break-glass accounts | Access review |

---

## 5. Risk Assessment

### 5.1 Risk Rating Methodology

Risk is calculated as: **Risk Level = Likelihood x Impact**

**Likelihood Scale:**
- High (3): Threat is likely to occur; known active exploitation or frequent occurrence in healthcare
- Moderate (2): Threat may occur; occasional occurrence in healthcare sector
- Low (1): Threat is unlikely; rare occurrence or significant barriers exist

**Impact Scale:**
- High (3): Severe harm — large ePHI breach (500+ patients), patient safety impact, regulatory action, significant financial penalty
- Moderate (2): Moderate harm — limited ePHI breach (<500 patients), operational disruption, reputational damage
- Low (1): Minor harm — minimal ePHI exposure, brief operational disruption, no regulatory action expected

**Risk Levels:**
- HIGH (7-9): Immediate management attention required; must be prioritized in Risk Management Plan
- MODERATE (4-6): Management attention required; addressed in near-term Risk Management Plan
- LOW (1-3): Monitor; address through routine operations

### 5.2 Risk Assessment Results

| Risk ID | Threat | Vulnerability | Likelihood | Impact | Risk Score | Risk Level | Current Controls |
|---------|--------|--------------|-----------|--------|------------|------------|-----------------|
| R-001 | T-H-002 Ransomware attack | V-004 Unpatched servers | 3 | 3 | 9 | HIGH | CrowdStrike EDR, network segmentation, backups; see POA&M |
| R-002 | T-H-003 Phishing / credential theft | V-005 Training gap | 3 | 3 | 9 | HIGH | MFA required; phishing simulation program; SIEM monitoring |
| R-003 | T-H-001 Insider threat ePHI access | V-003 Weak MFA for analytics accounts | 2 | 3 | 6 | MODERATE | RBAC enforced; SIEM monitoring; quarterly access review |
| R-004 | T-H-006 Supply chain attack | General third-party risk | 2 | 3 | 6 | MODERATE | TPRM program; BAAs; annual vendor assessments |
| R-005 | T-H-004 External network attack | V-004 Unpatched vulnerabilities | 2 | 3 | 6 | MODERATE | WAF, firewall, IDS/IPS; weekly vulnerability scanning |
| R-006 | T-U-001 Cloud misconfiguration | General cloud complexity | 2 | 3 | 6 | MODERATE | AWS Config, Macie, Security Hub; infrastructure-as-code |
| R-007 | T-H-005 Device theft | V-001 Legacy system encryption gap | 2 | 2 | 4 | MODERATE | Full-disk encryption on all endpoints; data minimization on legacy |
| R-008 | T-U-002 Accidental ePHI disclosure | V-006 Email policy compliance | 2 | 2 | 4 | MODERATE | DLP controls; training; SIEM detection |
| R-009 | T-H-008 Improper media disposal | General risk | 1 | 3 | 3 | LOW | NIST 800-88 disposal procedures; certificate of destruction required |
| R-010 | T-E-001 Power failure | General infrastructure | 2 | 2 | 4 | MODERATE | UPS, AWS multi-AZ, backup power; BCP tested Nov 2025 |
| R-011 | T-U-005 Terminated employee retains access | General process risk | 1 | 3 | 3 | LOW | 24-hr (1-hr high-risk) disablement policy; HR/ISSO SLA |
| R-012 | T-U-004 Patch management gap | V-004 | 2 | 2 | 4 | MODERATE | Formal patch policy; AWS Systems Manager automation; weekly scans |

---

## 6. Current Security Controls Assessment

MedCore's current security controls were assessed for effectiveness against the identified risks. The assessment finds:

**Effective Controls (providing significant risk reduction):**
- Multi-Factor Authentication (MFA) mandatory for all users — significantly reduces credential theft risk
- AWS KMS encryption for all cloud ePHI at rest — eliminates data exposure from storage-layer breaches
- CrowdStrike Falcon EDR on all endpoints — significantly reduces ransomware and malware impact
- SIEM-based monitoring and SOC analyst review — provides early detection capability
- Formal TPRM program with BAAs — addresses supply chain and vendor risk
- Automated backup to immutable S3 storage — limits ransomware impact on data availability
- AWS Config and Macie continuous monitoring — reduces cloud misconfiguration risk

**Controls Requiring Improvement (partially effective):**
- Patch management — SLA met for most assets but 3 legacy servers have moderate unpatched vulnerabilities (POA&M tracked)
- Security awareness training — 98.4% completion; remaining 2 users must complete by April 30, 2026
- Analytics account MFA — software TOTP vs. hardware keys (compensating controls in place; upgrade planned Q2 2026)

---

## 7. Risk Management Plan Summary

Based on this risk analysis, the following prioritized risk responses are planned:

| Risk ID | Risk Level | Response Strategy | Responsible | Target Date |
|---------|-----------|-------------------|------------|------------|
| R-001 | HIGH | Mitigate — complete patch remediation for legacy servers; see POA&M | Systems Admin | May 31, 2026 |
| R-002 | HIGH | Mitigate — complete security awareness training for remaining users; continue phishing simulations | ISSO | April 30, 2026 |
| R-003 | MODERATE | Mitigate — upgrade analytics accounts to hardware MFA (POA-2026-M09) | IAM Admin | June 30, 2026 |
| R-004 | MODERATE | Mitigate — maintain TPRM program; annual vendor reviews completed | ISSO | Ongoing |
| R-005 | MODERATE | Mitigate — continued patching; quarterly penetration testing | Systems Admin / Security Ops | Ongoing |
| R-006 | MODERATE | Mitigate — AWS Config rules; Infrastructure-as-Code; quarterly cloud security review | Cloud Security Engineer | Ongoing |
| R-007 | MODERATE | Accept (with compensating controls) — legacy system replacement in FY2027 CapEx plan | CIO | FY2027 |
| R-008 | MODERATE | Mitigate — enhanced DLP controls; targeted training for clinical users | ISSO | June 30, 2026 |

---

## 8. Certification

This Risk Analysis was conducted using recognized methodology (NIST SP 800-30 Rev 1 as adapted for HIPAA in NIST SP 800-66 Rev 2) and represents an accurate and thorough assessment of risks to MedCore ePHI as of the date completed.

| Role | Name | Signature | Date |
|------|------|-----------|------|
| ISSO | Amara Osei | [Signed] | February 1, 2026 |
| CISO | Jonathan E. Steele | [Signed] | February 3, 2026 |
| CEO / AO | Marcus T. Hargrove | [Signed] | February 5, 2026 |

---

*MedCore Health Systems — RESTRICTED / FOR AUTHORIZED PERSONNEL ONLY*
*HIPAA Risk Analysis v3.0 | February 2026 | Next review: February 2027*
