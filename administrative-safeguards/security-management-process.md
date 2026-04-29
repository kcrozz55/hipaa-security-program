# Security Management Process
## MedCore Health Systems — Administrative Safeguards
### 45 CFR §164.308(a)(1)

---

**Standard:** Security Management Process — Required
**HIPAA Reference:** 45 CFR §164.308(a)(1)
**Implementation Date:** January 2026
**Document Owner:** Amara Osei, ISSO
**Reviewed By:** Jonathan E. Steele, CISO
**Classification:** INTERNAL / SENSITIVE

---

## Standard Overview

The Security Management Process standard requires covered entities to implement policies and procedures to prevent, detect, contain, and correct security violations. This standard includes four required and addressable implementation specifications.

---

## Implementation Specifications

### §164.308(a)(1)(ii)(A) — Risk Analysis (Required)

**Implementation Status:** IMPLEMENTED

MedCore conducts a formal, comprehensive HIPAA Security Risk Analysis annually and whenever significant changes occur to the organization's ePHI environment, technology, or threat landscape. The Risk Analysis is conducted using the methodology described in NIST SP 800-30 Rev 1, adapted for healthcare per NIST SP 800-66 Rev 2.

**Current Risk Analysis:** Version 3.0, completed February 1, 2026. See: risk-analysis/hipaa-risk-analysis.md

The Risk Analysis encompasses:
- Identification and documentation of all ePHI systems and locations
- Comprehensive threat identification (human-caused deliberate, human-caused unintentional, environmental/natural)
- Vulnerability identification through scanning, architecture review, and workforce interviews
- Assessment of current security controls effectiveness
- Likelihood and impact assessment for each identified risk using a defined risk rating methodology
- Overall risk level determination for each risk scenario
- Documented risk register used to drive the Risk Management Plan

The ISSO is responsible for conducting the Risk Analysis. The CISO reviews the analysis. The CEO approves the Risk Analysis and the resulting Risk Management Plan. The Risk Analysis is retained for a minimum of 6 years from the date of its creation or the date it was last in effect.

### §164.308(a)(1)(ii)(B) — Risk Management (Required)

**Implementation Status:** IMPLEMENTED

MedCore implements a formal Risk Management Plan to reduce risks and vulnerabilities to ePHI to a reasonable and appropriate level. Risk management activities are tracked through:

1. **POA&M (Plan of Action and Milestones):** All identified risks requiring remediation are tracked in the MedCore EHRP POA&M (see nist-rmf-implementation repository). The POA&M includes the risk ID, remediation approach, responsible party, milestone dates, and current status.

2. **Monthly ConMon Reporting:** The ISSO reviews risk management progress monthly and reports status to the CISO and AO. Overdue or at-risk items are escalated immediately.

3. **Risk Acceptance:** Risks that cannot be fully mitigated may be formally accepted by the CISO (for Moderate risks) or the CEO/AO (for High risks), with documented rationale and compensating controls. All risk acceptances are reviewed annually.

4. **Annual Risk Management Review:** The ISSO and CISO review the overall risk posture annually, incorporating Risk Analysis findings, security incident trends, audit results, and changes in the threat environment.

**Current Risk Management Status:**
- 2 HIGH risk items active in POA&M (R-001 Patching, R-002 Training — both with active remediation plans)
- 6 MODERATE risk items with documented management plans
- No risk acceptances in place without compensating controls

### §164.308(a)(1)(ii)(C) — Sanction Policy (Required)

**Implementation Status:** IMPLEMENTED

MedCore has a documented sanction policy that applies appropriate sanctions against workforce members who fail to comply with the security policies and procedures of the covered entity.

**Sanction Policy Summary:**

All workforce members are required to comply with MedCore's information security policies and HIPAA requirements. Violations are subject to sanctions based on severity:

| Violation Category | Examples | Potential Sanctions |
|-------------------|----------|---------------------|
| Minor / Unintentional | Forgetting to lock workstation once; accidental ePHI email to wrong internal recipient | Verbal counseling; required remedial training |
| Moderate / Negligent | Repeated policy violations; accessing ePHI without business need; sharing login credentials | Written warning; suspension of access privileges; mandatory training; documented HR file |
| Serious / Willful | Intentional unauthorized access to ePHI; disclosing ePHI to unauthorized parties; deliberate circumvention of security controls | Termination of employment; referral to law enforcement; civil/criminal liability |

Sanctions are applied consistently regardless of workforce member position or tenure. The HR department maintains records of all sanctions related to HIPAA violations. The ISSO is notified of all HIPAA-related sanctions to assess whether additional security controls are needed.

The Sanction Policy is communicated to all workforce members during onboarding and reinforced through annual security awareness training.

### §164.308(a)(1)(ii)(D) — Information System Activity Review (Required)

**Implementation Status:** IMPLEMENTED

MedCore implements procedures to regularly review records of information system activity — including audit logs, access reports, and security incident tracking reports — to detect and respond to anomalous or suspicious activity.

**Review Procedures:**

- **Daily (Automated):** AWS GuardDuty, Security Hub, and SIEM (Splunk) automatically analyze system activity and generate alerts for anomalous events. SOC analysts review all high-priority alerts daily.

- **Weekly (Manual):** SOC analysts and the ISSO conduct manual review of:
  - Authentication failures and lockout events
  - Privileged access activity logs
  - AWS CloudTrail for unusual API calls
  - ePHI access logs for access outside normal patterns (time of day, volume, user location)
  - Failed security control events

- **Monthly (ISSO):** The ISSO prepares a monthly Continuous Monitoring report that includes system activity review findings, anomaly trends, and any events escalated to security incidents.

- **Quarterly (Access Review):** All user accounts and their associated system access are reviewed by account owners and the IAM Administrator to identify inappropriate or excessive access.

**Trigger-Based Reviews:** The following events trigger immediate out-of-cycle activity review:
- Any security incident declaration
- Discovery of a new critical/high vulnerability in systems handling ePHI
- Any report of potential ePHI breach
- Receipt of threat intelligence indicating active targeting of healthcare systems

---

## Evidence of Implementation

| Artifact | Location | Last Updated |
|----------|----------|-------------|
| HIPAA Risk Analysis v3.0 | risk-analysis/hipaa-risk-analysis.md | February 2026 |
| Risk Register | risk-analysis/risk-register.md | February 2026 |
| Sanction Policy | Referenced in POL-HR-001 Personnel Security Policy | January 2026 |
| Monthly ConMon Reports | Maintained by ISSO; archived in SharePoint/ISSO drive | Monthly |
| POA&M | nist-rmf-implementation/step-6-monitor/poam-tracker.md | Monthly updates |
| SIEM Alert Dashboard | Splunk Enterprise — siem.medcorehealthsystems.internal | Live |

---

*MedCore Health Systems — INTERNAL/SENSITIVE*
*HIPAA §164.308(a)(1) Implementation Documentation | Version 1.0 | January 2026*
