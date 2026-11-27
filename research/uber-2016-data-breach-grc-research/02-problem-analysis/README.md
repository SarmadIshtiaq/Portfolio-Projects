
# Uber 2016 Data Breach — Problem Analysis

**Portfolio:** Integrated GRC Framework Design & Implementation

**Case reference:** [Uber 2016 Data Breach Case Study](../01-case-study/README.md)

**Analysis type:** Independent GRC analysis based on public evidence

**Status:** In Progress

**Writing reference:** ASD-STE100 Issue 9

---

## 1. Purpose

This document analyses the problems identified in the Uber 2016 data breach case study.

The purpose is to convert documented incident facts into structured GRC problem statements.

The analysis examines:

- What security or governance problem is indicated by the evidence.
- Why the problem matters.
- What could happen if the problem remains unresolved.
- What type of control an organisation should consider.

This is an independent analysis. It does not represent an audit of Uber or an assessment of its current security controls.

## 2. Analysis Method

Each problem is analysed in four steps.

| Step | Meaning |
|---|---|
| Documented evidence | What the official source reports. |
| Problem statement | What weakness or management issue the evidence indicates. |
| Potential consequence | What could happen if the problem is not addressed. |
| Proposed direction | What an organisation could do to reduce the problem. |

The analysis separates official facts from independent interpretation.

An official allegation is not presented as a final court finding.

A proposed control is not presented as a control implemented by Uber.

## 3. Identified GRC Problems

### PA-01 — Credential and Authentication Management

**Documented evidence**

The FTC complaint states that Uber did not have a policy that prohibited engineers from reusing credentials. It also states that Uber did not require MFA for access to its GitHub repositories.

The attackers said that they used passwords previously exposed in other data breaches.

Source: [FTC Revised Complaint — 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

**Problem statement**

The authentication controls did not sufficiently reduce the risk of access through compromised credentials.

**Potential consequence**

An unauthorised person could gain access to a private repository.

**Proposed direction**

- Require MFA for developer accounts.
- Establish a unique credential policy.
- Define secure authentication requirements.
- Review access to private repositories.

### PA-02 — Secrets Management

**Documented evidence**

The FTC complaint states that the attackers found an AWS access key in plain-text source code.

They used the key to access Uber's Amazon S3 datastore.

Sources: [FTC Revised Complaint — 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) | [DOJ Non-Prosecution Agreement — 2022](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

**Problem statement**

A sensitive cloud credential was stored in source code.

This created a path from repository access to cloud data access.

**Potential consequence**

An unauthorised person who obtains the credential could use it to access cloud resources.

**Proposed direction**

- Store secrets in a secure secrets manager.
- Prevent credentials from being committed to source code.
- Scan repositories for exposed secrets.
- Rotate credentials after suspected exposure.
- Define ownership of cloud credentials.

### PA-03 — Cloud Access Control

**Documented evidence**

The DOJ agreement records that attackers used a private access key to access and copy data associated with Uber users and drivers from its cloud environment.

Source: [DOJ Non-Prosecution Agreement — 2022](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

**Problem statement**

A compromised AWS credential enabled access to stored data.

The public records used in this study do not provide enough detail to assess the complete permission scope of the key.

**Potential consequence**

A compromised cloud credential could allow unauthorised access to sensitive storage resources.

**Proposed direction**

- Apply least-privilege access.
- Restrict credentials to required resources.
- Review cloud access permissions.
- Monitor unusual access to storage services.
- Rotate exposed credentials.

### PA-04 — Data Protection

**Documented evidence**

The FTC complaint states that the downloaded files contained unencrypted personal information.

The complaint reports approximately 25.6 million names and email addresses, 22.1 million names and mobile phone numbers, and 607,000 names and driver's licence numbers.

Source: [FTC Revised Complaint — 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

**Problem statement**

Personal information was stored in a form that allowed it to be read after unauthorised access.

**Potential consequence**

Unauthorised persons could obtain readable personal information.

This could affect customer privacy and create regulatory and legal consequences.

**Proposed direction**

- Define data classification rules.
- Encrypt sensitive data at rest.
- Protect database backups.
- Limit access to personal information.
- Define data retention and deletion requirements.

### PA-05 — Incident Response and Disclosure

**Documented evidence**

The DOJ agreement records that Uber's security team closed the attackers' access point, started password resets, enabled two-factor authentication for GitHub accounts, and rotated AWS service keys.

Source: [DOJ Non-Prosecution Agreement — 2022](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

The FTC complaint states that Uber notified affected consumers on 21 November 2017. It had learned about the breach on or about 14 November 2016.

Source: [FTC Revised Complaint — 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

**Problem statement**

The records show that containment actions were taken after discovery. However, notification and regulatory disclosure took place much later.

**Potential consequence**

Delayed reporting can increase regulatory, legal, reputational, and customer-trust risks.

**Proposed direction**

- Define incident escalation procedures.
- Assign incident reporting responsibilities.
- Establish a regulatory notification assessment process.
- Record incident decisions and approvals.
- Define communication responsibilities for affected parties.

### PA-06 — Governance and Accountability

**Documented evidence**

The DOJ agreement states that Uber admitted its personnel failed to report the November 2016 breach to the FTC despite a pending FTC investigation into the company's data security.

Source: [DOJ Non-Prosecution Agreement — 2022](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)

**Problem statement**

The case raises questions about executive oversight, incident escalation, and accountability for regulatory reporting decisions.

**Potential consequence**

Unclear responsibilities and weak oversight could delay important decisions and reduce accountability.

**Proposed direction**

- Assign clear incident ownership.
- Define executive escalation responsibilities.
- Establish reporting and approval procedures.
- Maintain records of important incident decisions.
- Include security and compliance reporting in management oversight.

## 4. Consolidated Problem Register

| ID | Problem area | Main concern | Proposed response |
|---|---|---|---|
| PA-01 | Credential management | Compromised credentials could access private repositories. | MFA and unique credentials |
| PA-02 | Secrets management | An AWS key was stored in source code. | Secure secrets management |
| PA-03 | Cloud access control | A compromised key enabled cloud data access. | Least privilege and access monitoring |
| PA-04 | Data protection | Downloaded files contained unencrypted personal information. | Encryption and data protection |
| PA-05 | Incident response and disclosure | Consumer and regulator notification was delayed. | Escalation and reporting procedures |
| PA-06 | Governance and accountability | Incident reporting and oversight decisions require examination. | Clear ownership and executive oversight |

The problem IDs will be used in the later risk management and governance documents.

No likelihood, impact, or risk score is assigned at this stage.

## 5. Analysis Limitations

This analysis uses public FTC and DOJ records.

It does not use Uber's internal policies, security configurations, audit reports, or investigation records.

The analysis does not claim that every identified issue was the sole cause of the breach.

The proposed responses are independent recommendations.

They are not verified controls implemented by Uber.

The full permission scope of the compromised AWS key is not established by the sources used here.

The analysis does not determine whether a particular statutory reporting deadline was breached. That would require a separate legal assessment.

## 6. Next Step

The identified problems provide input to the next project phases.

- Governance Framework: define roles, responsibilities, and oversight.
- Risk Management: convert problem statements into risk statements and assess their likelihood and impact.
- Compliance Management: identify applicable requirements and map them to proposed controls.

The next step is to develop the proposed governance responsibilities and operating model.

## References and Standards

- [FTC — Uber Revised Complaint, October 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)
- [DOJ — Executed Non-Prosecution Agreement, July 2022](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)
- [DOJ — Uber Non-Prosecution Agreement Announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)
- [NIST — Cybersecurity Framework 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20)
- [ASD-STE100 — Official Standard](https://www.asd-ste100.org/)

---

**Writing note:** This document uses ASD-STE100 Issue 9 writing principles. Full compliance has not yet been verified against the complete specification.
