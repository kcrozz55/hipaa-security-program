# Breach Notification Procedures
## MedCore Health Systems
### 45 CFR §§164.400 – 164.414 — HIPAA Breach Notification Rule

---

**Standard:** Breach Notification Rule
**HIPAA Reference:** 45 CFR Part 164, Subpart D (§§164.400 – 164.414)
**Document Version:** 2.3
**Effective Date:** January 15, 2026
**Document Owner:** Dr. Rachel Feinberg, Privacy Officer
**Co-Owner:** Amara Osei, ISSO
**Approved By:** Marcus T. Hargrove, CEO
**Classification:** INTERNAL / SENSITIVE

---

## 1. Overview

Under the HIPAA Breach Notification Rule, MedCore Health Systems must provide notification following a breach of unsecured protected health information. A "breach" is defined as the acquisition, access, use, or disclosure of protected health information (PHI) in a manner not permitted under the HIPAA Privacy Rule which compromises the security or privacy of the PHI.

The Breach Notification Rule establishes three categories of required notifications:
1. Notification to affected individuals
2. Notification to the Secretary of HHS (OCR)
3. Notification to media (for breaches affecting 500+ individuals in a single state)

---

## 2. Definitions

**Breach:** An impermissible use or disclosure under the Privacy Rule that compromises the security or privacy of the PHI. Per §164.402, a breach is presumed unless the covered entity demonstrates that there is a low probability that the PHI has been compromised based on a risk assessment of at least:
- The nature and extent of the PHI involved (including types of identifiers and likelihood of re-identification)
- The unauthorized person who used the PHI or to whom the disclosure was made
- Whether the PHI was actually acquired or viewed
- The extent to which the risk has been mitigated

**Unsecured PHI:** PHI that is not rendered unusable, unreadable, or indecipherable to unauthorized persons through the use of an approved technology or methodology (specifically encryption meeting HHS guidance or destruction meeting NIST 800-88).

**Impermissible Disclosure:** A use or disclosure of PHI that is not permitted by the HIPAA Privacy Rule.

**Discovery Date:** The first day on which a breach is known (or by exercising reasonable diligence should have been known) to any workforce member of the covered entity, other than the person committing the breach.

---

## 3. Breach Risk Assessment (4-Factor Test)

Whenever a potential breach event is identified, the Privacy Officer and ISSO conduct a risk assessment using the HHS four-factor test to determine the probability that PHI has been compromised:

### Factor 1: Nature and Extent of PHI Involved
- What types of PHI were involved? (diagnoses, SSN, financial, mental health, etc.)
- How many individuals are affected?
- Could the PHI be used to identify specific individuals?
- Does it include special categories (mental health, substance abuse, HIV status)?

### Factor 2: Who Accessed or Could Have Accessed the PHI
- Was the unauthorized person an insider with some legitimate access (error) or a complete outsider (intrusion)?
- What is their identity? Are they another covered entity?
- Did they have any obligation to protect PHI?
- Is there any indication they actually accessed, viewed, or used the PHI?

### Factor 3: Whether PHI Was Actually Acquired or Viewed
- Is there evidence the data was accessed, exfiltrated, or used?
- Are there logs indicating access to the data?
- Was the exposure very brief with no indication of download/viewing?

### Factor 4: Extent to Which Risk Has Been Mitigated
- Were notification/remediation steps taken to mitigate risk to affected individuals?
- Was the disclosure to a trustworthy entity that signed a BAA?
- Can MedCore confirm the PHI was destroyed or not accessed?

**Outcome:** If the four-factor assessment demonstrates a low probability of compromise, MedCore may determine that no notification is required (no breach), but must document the assessment. If the assessment cannot establish low probability, notification is required.

**Default Rule:** If there is any doubt, MedCore treats the event as a reportable breach and proceeds with notifications. Notification is preferable to under-reporting.

---

## 4. Breach Discovery and Initial Response

### 4.1 Identification and Reporting

Security incidents that may constitute breaches are initially identified through:
- SOC monitoring and SIEM alerts
- Workforce member reports to the ISSO or Privacy Officer
- Reports from patients or external parties
- Vendor breach notifications
- Routine access log review

Any workforce member who suspects a breach must immediately report it to the ISSO (aosei@medcorehealthsystems.org / ext. 5912) or Privacy Officer (rfeinberg@medcorehealthsystems.org / ext. 5910).

### 4.2 Initial Assessment (Within 24 Hours of Discovery)

Upon receiving a report of potential breach, the ISSO and Privacy Officer must within 24 hours:
1. Secure the PHI or system involved to prevent further unauthorized access
2. Document the Discovery Date
3. Conduct an initial assessment to determine the scope and severity
4. Initiate the Incident Response process (MedCore-IRP-001) if not already active
5. Notify the CISO
6. Begin the four-factor risk assessment

### 4.3 Escalation

| Time from Discovery | Escalation Required |
|--------------------|---------------------|
| Immediately | ISSO and Privacy Officer notified by workforce member |
| Within 24 hours | CISO notified by ISSO; Legal Counsel notified if breach suspected |
| Within 24 hours | AO/CEO notified if breach affecting ePHI of 10 or more individuals is confirmed |
| Ongoing | Breach response team assembled; notifications timeline tracked |

---

## 5. Notification Requirements and Timelines

### 5.1 Notification to Affected Individuals (§164.404)

**Required when:** MedCore determines that a breach of unsecured PHI has occurred.

**Timeline:** Without unreasonable delay and in no case later than **60 calendar days** after the Discovery Date.

**Content of Individual Notice (§164.404(b)):**
1. A brief description of what happened, including the date of the breach and the date of discovery (if known)
2. The types of unsecured PHI involved (e.g., name, SSN, date of birth, diagnoses, medical record numbers)
3. Steps individuals should take to protect themselves from potential harm
4. A brief description of what MedCore is doing to investigate, mitigate harm, and protect against further breaches
5. Contact procedures for individuals to ask questions or learn additional information (toll-free number, email address, website, or postal address)

**Method of Individual Notice (§164.404(c)):**
- First class mail to last known address on file
- Email if the individual has agreed to email notice
- If contact information is insufficient or out-of-date (10 or more individuals): substitute notice on MedCore website homepage for 90 days AND conspicuous posting in print or broadcast media

### 5.2 Notification to HHS Secretary / OCR (§164.408)

**Timeline for breaches affecting 500+ individuals:** Within **60 calendar days** of Discovery Date — submitted via HHS Breach Portal (ocrportal.hhs.gov)

**Timeline for breaches affecting fewer than 500 individuals:** Within **60 days after the end of the calendar year** in which the breaches were discovered (annual log submitted to HHS)

**Required Information for HHS Notification:**
- Name and contact info of covered entity
- Location of breach
- Nature of breach
- PHI involved
- Number of individuals affected
- Safeguards in place
- Actions taken in response

**MedCore Small Breach Log:** The Privacy Officer maintains a log of all breaches affecting fewer than 500 individuals. The log is submitted to HHS OCR annually by January 31 for the preceding calendar year.

### 5.3 Media Notification (§164.406)

**Required when:** A breach affects 500 or more residents of a state or jurisdiction.

**Timeline:** Without unreasonable delay and in no case later than **60 calendar days** after Discovery Date.

**Method:** Prominent media outlets serving the affected state (press release to major Atlanta-area media outlets for events affecting Georgia residents).

**Note:** Media notification must be coordinated with MedCore's Public Relations team, CEO, and Legal Counsel before any public statement is made.

---

## 6. Breach Response Team

| Role | Name | Primary Responsibility |
|------|------|----------------------|
| Privacy Officer (Lead) | Dr. Rachel Feinberg | Four-factor assessment; individual and HHS notifications; BAA breach provisions |
| ISSO | Amara Osei | Incident response; forensic investigation; technical containment |
| CISO | Jonathan E. Steele | Executive oversight; media strategy support; AO communication |
| Legal Counsel | MedCore General Counsel | Legal privilege over investigation; regulatory filing review; law enforcement liaison |
| CEO/AO | Marcus T. Hargrove | Ultimate decision authority; approves notifications; AO acceptance |
| Public Relations | MedCore PR Manager | Media statement drafting and release coordination |
| Human Resources | MedCore HR Director | Workforce discipline if breach involves employee misconduct |

---

## 7. Business Associate Breach Obligations

Business Associates must notify MedCore without unreasonable delay and within **60 calendar days** of discovering a breach of unsecured PHI (per BAA terms). Upon receiving BA breach notification:

1. Privacy Officer documents receipt date as potential MedCore Discovery Date
2. ISSO initiates incident response and investigates scope
3. Four-factor assessment conducted using information from BA
4. MedCore notification obligations apply from the date MedCore was notified
5. BA must cooperate with MedCore's investigation and notification activities

---

## 8. Documentation and Record Retention

All breach-related documentation must be retained for **6 years** from the date of creation or the date it was last in effect:
- Breach risk assessment documents
- Individual notification records (proof of mailing, email delivery)
- HHS OCR notification confirmations
- Media notices
- Investigation reports
- BA breach notification correspondence
- Legal privilege review records

Documentation is maintained by the Privacy Officer in the MedCore Breach Log (breach-notification/breach-log.md) and in the secure Legal/Compliance document system.

---

*MedCore Health Systems — INTERNAL/SENSITIVE*
*HIPAA Breach Notification Procedures v2.3 | January 2026 | Dr. Rachel Feinberg, Privacy Officer*
