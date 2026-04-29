# Technical Safeguards — Access Controls
## MedCore Health Systems
### 45 CFR §164.312(a)

---

**Standard:** Access Controls — Required
**HIPAA Reference:** 45 CFR §164.312(a)(1) and (2)
**Implementation Date:** January 2026
**Document Owner:** Amara Osei, ISSO
**Classification:** INTERNAL / SENSITIVE

---

## Standard Overview

The Access Controls standard requires covered entities to implement technical policies and procedures for electronic information systems that maintain ePHI to allow access only to those persons or software programs that have been granted access rights per §164.308(a)(4).

---

## Implementation Specifications

### §164.312(a)(2)(i) — Unique User Identification (Required)

**Implementation Status:** IMPLEMENTED

MedCore assigns a unique identifier to each authorized user of ePHI systems. No shared accounts are permitted for human users of any system containing ePHI.

**Implementation Details:**
- All users are provisioned a unique username in the format: [firstname].[lastname]@medcorehealthsystems.org
- Usernames are tied to a single named individual and never reused after account termination
- Usernames are the same across all integrated systems (Okta SSO ensures single identity across EHRP, AWS, and on-premises systems)
- Service accounts use a separate naming convention (svc-[function]-[system]) and are never shared among multiple services
- The 4 emergency break-glass accounts have unique, documented identifiers and are subject to strict procedural controls

**Technical Enforcement:** Okta Identity Cloud serves as the Identity Provider (IdP) for all EHRP user authentication. Active Directory manages on-premises identities with Okta sync. No system accepts generic or shared accounts.

### §164.312(a)(2)(ii) — Emergency Access Procedure (Required)

**Implementation Status:** IMPLEMENTED

MedCore maintains documented procedures for obtaining necessary ePHI during an emergency. This addresses scenarios where standard authentication systems may be unavailable while patient care must continue.

**Emergency Access Procedure:**

1. **Break-Glass Account Activation:** Four emergency break-glass accounts (BGA-001 through BGA-004) are maintained for emergency use. Account credentials are stored in a physical safe in the IT Operations Manager's office, accessible by: CISO, CIO, and designated alternates.

2. **Activation Conditions:** Break-glass accounts may be used only when: Active Directory or Okta is unavailable and patient care is being directly impacted, OR a senior clinician attests in writing that ePHI access is immediately required for patient safety.

3. **Authorization:** Authorization to use break-glass accounts requires approval from the On-Call Clinical Administrator (OCCA) and notification to the ISSO within 30 minutes.

4. **Monitoring:** All break-glass account usage automatically generates a SIEM alert to the ISSO and CISO. Sessions are fully logged.

5. **Post-Use Review:** The ISSO reviews all break-glass account usage within 24 hours. Passwords are rotated immediately after use.

6. **Documentation:** All break-glass access events are documented in the Break-Glass Access Log maintained by the ISSO.

### §164.312(a)(2)(iii) — Automatic Logoff (Addressable)

**Implementation Status:** IMPLEMENTED

**Rationale for Implementation:** Patient-facing workstations in shared clinical environments present a high risk of unauthorized ePHI access if sessions are left open. MedCore has implemented automatic logoff as a critical control.

**Implementation Details:**
- All EHRP workstations are configured with a 10-minute screen lock inactivity timer via Group Policy
- Workstations in patient care areas (exam rooms, nursing stations, hallways) are configured with a 3-minute screen lock inactivity timer
- After the screen lock period, the user must re-authenticate with username and password (MFA session remains active for 8 hours)
- AWS Console and cloud resource sessions time out after 1 hour of inactivity
- VPN sessions disconnect after 30 minutes of inactivity

### §164.312(a)(2)(iv) — Encryption and Decryption (Addressable)

**Implementation Status:** IMPLEMENTED

**Rationale for Implementation:** Given the HIGH confidentiality impact level of EHRP ePHI and the regulatory requirements under HIPAA, encryption is implemented as a required control.

**Implementation Details:**
- All ePHI at rest is encrypted using AES-256 via AWS KMS customer-managed keys (see POL-SC-002 and EHRP SSP SC-28 implementation)
- All ePHI in transit is encrypted using TLS 1.3 (TLS 1.2 minimum for legacy integrations)
- Encryption keys are managed through AWS KMS with annual automatic rotation
- On-premises ePHI storage uses BitLocker AES-256 with TPM 2.0
- No ePHI may be stored on unencrypted media or devices

Encryption renders ePHI unusable, unreadable, or indecipherable to unauthorized individuals, which under HIPAA Breach Notification Rule means that breaches of properly encrypted ePHI may not require notification.

---

## Access Control Architecture

### Role-Based Access Control (RBAC)

MedCore EHRP uses RBAC to enforce minimum necessary access to ePHI:

| Role | ePHI Access Level | Examples |
|------|------------------|---------|
| Treating Physician | Full access to assigned patient panel; all ePHI types | Attending physicians, specialists |
| Registered Nurse | Full access to assigned patient panel; clinical ePHI | Floor nurses, charge nurses |
| Medical Assistant | Demographic, scheduling, vital signs; limited clinical | MA/CNA role |
| Scheduling Staff | Demographics and scheduling data only | Front desk, scheduling team |
| Billing Specialist | Billing, claims, and diagnosis codes; no clinical notes | Revenue cycle team |
| IT Administrator | Metadata and system data; no ePHI without break-glass | IT Operations |
| ISSO | Audit logs and access reports; specific ePHI only for investigation | ISSO role |
| Read-Only Auditor | Audit logs only; no ePHI | Compliance team |
| Break-Glass Emergency | All ePHI — emergency only; fully logged | Emergency accounts |

### Minimum Necessary Standard

All EHRP access controls are designed to enforce the HIPAA minimum necessary standard:
- Treating providers may access only the records of patients in their assigned care panel
- Administrative staff see only the ePHI required for their specific function
- Role definitions are reviewed by the Privacy Officer annually to ensure minimum necessary compliance

---

*MedCore Health Systems — INTERNAL/SENSITIVE*
*HIPAA §164.312(a) Implementation Documentation | Version 1.0 | January 2026*
