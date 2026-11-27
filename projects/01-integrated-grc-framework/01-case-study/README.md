# Uber 2016 Data Breach — Case Study

**Portfolio:** Integrated GRC Framework Design & Implementation

**Case type:** Independent research based on public evidence

**Organisation:** Uber Technologies, Inc.

**Incident period:** October–November 2016

**Writing reference:** ASD-STE100 Issue 9

**Status:** In Progress

---

## 1. Purpose

This case study examines the Uber 2016 data breach.

It uses official records from the U.S. Federal Trade Commission (FTC) and the U.S. Department of Justice (DOJ).

The study explains the incident, its technical details, the exposed information, and the response.

It also identifies the Governance, Risk, and Compliance (GRC) topics that require further analysis.

This is an independent portfolio research project. It is not an audit of Uber.

## 2. Scope

This study covers:

- Access to Uber's private GitHub repository.
- Use of stolen credentials.
- Exposure of an AWS access key.
- Access to Amazon S3 data.
- Exposure of personal information.
- Incident discovery and response.
- Delayed disclosure.
- Regulatory and legal outcomes.

The study uses public information only.

It does not claim access to Uber's internal systems, policies, or records.

## 3. Organisation Background

Uber Technologies, Inc. operates a technology platform that connects consumers with independent drivers for ridesharing and delivery services. [Source: [DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)]

Uber collects personal information from riders and drivers. This information includes names, email addresses, phone numbers, and driver's licence information. [Source: [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)]

## 4. Incident Summary

In October and November 2016, attackers accessed Uber's private GitHub repository.

They used stolen credentials to gain access. They found an AWS access key in the source code.

They used this key to access Uber's Amazon S3 datastore and copy personal information. [Sources: [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)]

The FTC complaint reports that the attackers downloaded 16 files between 13 October and 15 November 2016. [Source: [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)]

Uber learned about the breach on or about 14 November 2016.

Uber paid the attackers $100,000 through its bug bounty program in December 2016. [Source: [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)]

Uber notified affected consumers on 21 November 2017, more than one year after discovery. [Source: [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)]

## 5. Verified Incident Timeline

| Date | Documented event | Official evidence |
|---|---|---|
| 13 October–15 November 2016 | Attackers downloaded 16 files from Amazon S3. | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| 14 November 2016 | Uber learned about the breach after an attacker contacted the company. | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| December 2016 | Uber paid the attackers $100,000 in Bitcoin. | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| January 2017 | Uber identified the two attackers. | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| 21 November 2017 | Uber notified affected consumers. | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| 26 October 2018 | The FTC approved a revised settlement with Uber. | [FTC Announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber) |
| 22 July 2022 | Uber entered a non-prosecution agreement with federal prosecutors. | [DOJ Announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) |
| 5 October 2022 | A federal jury convicted Uber's former Chief Security Officer. | [DOJ Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach) |
| 5 May 2023 | The former Chief Security Officer received three years of probation and a $50,000 fine. | [DOJ Sentencing Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data) |

## 6. Documented Technical Findings

The official records describe the following technical issues:

1. Attackers used credentials that had been exposed in earlier data breaches.
2. Uber did not require MFA for access to its GitHub repositories, according to the FTC complaint.
3. The attackers found an AWS access key in plain-text source code.
4. They used the key to access Amazon S3.
5. The downloaded files contained unencrypted personal information.

Source: [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

The DOJ agreement also records the actions taken after discovery.

Uber's security team closed the attackers' access point, started password resets, enabled two-factor authentication for GitHub accounts, and rotated AWS service keys.

Source: [DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

**Important:** The security weaknesses above are described in the FTC complaint. They must be identified as allegations in that complaint.

## 7. Exposed Information

The FTC complaint reported these data categories:

| Information | Reported amount | Official evidence |
|---|---:|---|
| Names and email addresses | Approximately 25.6 million | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Names and mobile phone numbers | Approximately 22.1 million | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Names and driver's licence numbers | Approximately 607,000 | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |

The DOJ later reported approximately 57 million user records and 600,000 driver's licence numbers. [Source: [DOJ Announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)]

These figures use different reporting descriptions. The FTC category counts must not be added to calculate the number of unique affected people.

## 8. Governance Implications

The incident raises important governance questions:

- Who owns access to source-code repositories?
- Who approves and monitors access to cloud credentials?
- Who is responsible for incident escalation?
- Who approves communication with regulators?
- How does senior management monitor security and privacy risks?

These are independent governance questions. They are not claims about Uber's current internal governance structure.

## 9. Risk Implications

The incident provides examples of risks that an organisation should assess.

| Risk area | Potential consequence |
|---|---|
| Credential compromise | Unauthorised system access |
| Exposed cloud keys | Unauthorised cloud data access |
| Weak access controls | Unauthorised access to sensitive information |
| Unencrypted data | Exposure of readable personal information |
| Delayed incident disclosure | Regulatory and legal consequences |
| Weak incident oversight | Poor accountability and incident response |

These are proposed risk scenarios based on the documented incident. They are not a verified assessment of Uber's current risk position.

## 10. Compliance Implications and Proposed GRC Responses

The incident raises questions about privacy obligations, security controls, incident response, and regulatory reporting.

For this portfolio, the proposed GRC framework will examine the following controls:

| Area | Proposed GRC response |
|---|---|
| Identity and access management | Define access rules and require MFA. |
| Credential management | Establish credential reuse and rotation requirements. |
| Secrets management | Prevent access keys from being stored in source code. |
| Cloud security | Restrict and monitor access to cloud storage. |
| Data protection | Define encryption and data classification controls. |
| Incident response | Establish escalation, investigation, and response procedures. |
| Compliance monitoring | Assign control owners and retain evidence. |
| Management oversight | Report significant risks and incidents to management. |

These are proposed controls for an independent GRC framework. They are not controls that we claim to have implemented at Uber.

## 11. Limitations

This is an independent portfolio research project.

It uses public information from official sources.

The project does not represent:

- An audit of Uber.
- A penetration test.
- A legal opinion.
- An assessment of Uber's current security posture.
- An implementation of controls inside Uber.

The study will not make claims that public evidence cannot support.

## 12. Official References

### S1 — FTC Revised Complaint

**Organisation:** U.S. Federal Trade Commission

**Date:** October 2018

**Purpose:** GitHub access, credential reuse, MFA, AWS access key, Amazon S3 access, exposed data, and consumer notification.

[Open the official FTC Revised Complaint (PDF)](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

### S2 — DOJ Executed Non-Prosecution Agreement

**Organisation:** U.S. Department of Justice

**Date:** 22 July 2022

**Purpose:** Attack path, company admissions, response actions, payment, and disclosure.

[Open the official DOJ Agreement (PDF)](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

### S3 — DOJ Non-Prosecution Agreement Announcement

**Organisation:** U.S. Department of Justice

**Date:** 22 July 2022

**Purpose:** Uber's admissions, approximate data exposure, and delayed disclosure.

[Open the official DOJ Announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)

### S4 — FTC Settlement Announcement

**Organisation:** U.S. Federal Trade Commission

**Date:** 26 October 2018

**Purpose:** Regulatory action, privacy program, and independent assessments.

[Open the official FTC Announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber)

### S5 — Former Chief Security Officer Conviction

**Organisation:** U.S. Department of Justice

**Date:** 5 October 2022

**Purpose:** Trial outcome and individual accountability.

[Open the official DOJ Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach)

### S6 — Former Chief Security Officer Sentencing

**Organisation:** U.S. Department of Justice

**Date:** 5 May 2023

**Purpose:** Final sentence and fine.

[Open the official DOJ Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data)

### S7 — ASD-STE100 Issue 9

**Organisation:** ASD Simplified Technical English Maintenance Group

**Issue:** 9

**Date:** 15 January 2025

**Purpose:** Technical writing rules and controlled vocabulary.

[Open the official ASD-STE100 website](https://www.asd-ste100.org/)

[Open the official ASD-STE100 Issue 9 PDF](https://www.asd-ste100.org/assets/files/ASD-STE100_ISSUE9.pdf)

---

**Writing note:** This document uses ASD-STE100 Issue 9 writing principles. Full compliance has not yet been verified against the complete specification.

**Next step:** Review the case study and use its findings in the Problem Analysis section.