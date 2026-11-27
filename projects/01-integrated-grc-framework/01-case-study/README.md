
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

- Access to Uber's private GitHub repository using stolen credentials. ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))

- Exposure of an AWS access key in source code stored in the private repository. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

- Access to Uber's Amazon S3 datastore using the AWS key. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

- Download of personal information from Amazon S3. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

- Incident discovery and response. ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))

- Payment to the attackers. ([DOJ Conviction Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach))

- Delayed disclosure to affected consumers and regulators. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

- Regulatory and legal outcomes. ([FTC Settlement Announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber)) ([DOJ Non-Prosecution Agreement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement))

The study uses public information only.

It does not claim access to Uber's internal systems, policies, or records.

## 3. Organisation Background

Uber Technologies, Inc. operates a technology platform that connects consumers with independent drivers for ridesharing and delivery services. ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))

Uber collects personal information from riders and drivers. This information includes names, email addresses, phone numbers, and driver's licence information. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

Uber used Amazon S3 to store files that contained personal information. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

## 4. Incident Summary

In October and November 2016, attackers accessed Uber's private GitHub repository.

They used stolen credentials to gain access. They found an AWS access key in the source code.

They used this key to access Uber's Amazon S3 datastore and download personal information. ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))

The FTC complaint reports that the attackers downloaded 16 files between 13 October and 15 November 2016. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

Uber learned about the breach on or about 14 November 2016. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

Uber paid the attackers $100,000 in Bitcoin in December 2016. ([DOJ Conviction Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach))

Uber notified affected consumers on 21 November 2017, more than one year after discovery. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

**Incident distinction:** The 2014 Uber breach was a separate incident. In 2014, an AWS key was posted to a public GitHub repository. In 2016, attackers used stolen credentials to access a private GitHub repository. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)) ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))

## 5. Verified Incident Timeline

| Date | Documented event | Official evidence |
|---|---|---|
| 13 October–15 November 2016 | Attackers downloaded 16 files from Amazon S3. | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| 14 November 2016 | Uber learned about the breach after an attacker contacted the company. | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| December 2016 | Uber paid the attackers $100,000 in Bitcoin. | [DOJ Conviction Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach) |
| January 2017 | Uber identified the two attackers. | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| 21 November 2017 | Uber notified affected consumers. | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| 26 October 2018 | The FTC approved a revised settlement with Uber. | [FTC Announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber) |
| 22 July 2022 | Uber entered a non-prosecution agreement with federal prosecutors. | [DOJ Announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) |
| 5 October 2022 | A federal jury convicted Uber's former Chief Security Officer. | [DOJ Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach) |
| 5 May 2023 | The former Chief Security Officer received three years of probation and a $50,000 fine. | [DOJ Sentencing Announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data) |

## 6. Documented Technical Findings

The FTC complaint describes the following security weaknesses:

1. Uber did not have a policy that prohibited engineers from reusing credentials. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

2. Uber did not require engineers to enable MFA when they accessed its GitHub repositories. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

3. The attackers found an AWS access key in plain-text source code. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

4. The attackers used the AWS key to access Amazon S3 and download files that contained unencrypted personal information. ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))

The DOJ agreement records the response actions taken after discovery. Uber's security team closed the attackers' access point, started password resets, enabled two-factor authentication for GitHub accounts, and rotated AWS service keys. ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))

**Important:** The security weaknesses in the FTC complaint are allegations in that complaint. The response actions above are recorded in the DOJ agreement's Statement of Facts, which Uber accepted.

## 7. Exposed Information

The FTC complaint reported these data categories:

| Information | Reported amount | Official evidence |
|---|---:|---|
| Names and email addresses | Approximately 25.6 million | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Names and mobile phone numbers | Approximately 22.1 million | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Names and driver's licence numbers | Approximately 607,000 | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |

The DOJ reported approximately 57 million user records and 600,000 driver's licence numbers. ([DOJ Non-Prosecution Agreement Announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement))

These figures use different reporting descriptions. The FTC category counts must not be added to calculate the number of unique affected people.

## 8. Governance Implications

The incident raises important governance questions:

- Who owns access to source-code repositories? ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))
- Who approves and monitors access to cloud credentials? ([FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf))
- Who is responsible for incident escalation and response? ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))
- Who approves communication with regulators? ([DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf))
- How does senior management monitor security and privacy risks? ([FTC Settlement Announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber))

These are questions for independent GRC analysis. They are not claims about Uber's current internal governance structure.

## 9. Risk Implications

The following risk scenarios are based on the documented incident:

| Risk area | Potential consequence | Evidence |
|---|---|---|
| Credential compromise | Unauthorised repository access | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Exposed cloud keys | Unauthorised cloud data access | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| Weak access controls | Unauthorised access to sensitive information | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Unencrypted data | Exposure of readable personal information | [FTC Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Delayed disclosure | Regulatory and legal consequences | [FTC Settlement Announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber) |
| Weak incident oversight | Poor accountability and incident response | [DOJ Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |

These are proposed risk scenarios. They are not a verified assessment of Uber's current risk position.

## 10. Compliance Implications and Proposed GRC Responses

The incident provides a basis for the following proposed GRC controls:

| Area | Proposed GRC response | Evidence or regulatory context |
|---|---|---|
| Identity and access management | Define access rules and require MFA. | [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Credential management | Establish credential reuse and rotation requirements. | [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Secrets management | Prevent access keys from being stored in source code. | [DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| Cloud security | Restrict and monitor access to cloud storage. | [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Data protection | Define encryption and data classification controls. | [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| Incident response | Establish escalation, investigation, and response procedures. | [DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |
| Compliance monitoring | Assign control owners and retain evidence. | [FTC Settlement Announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber) |
| Management oversight | Report significant risks and incidents to management. | [DOJ Non-Prosecution Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf) |

These are proposed controls for this portfolio. They are not controls that we claim to have implemented at Uber.

## 11. Limitations

This is an independent portfolio research project.

It uses public information from official sources.

The project does not represent:

- An audit of Uber.
- A penetration test.
- A legal opinion.
- An assessment of Uber's current security posture.
- An implementation of controls inside Uber.

The study does not make claims that public evidence cannot support.

## 12. Official References

- **FTC Revised Complaint (October 2018):** [Open the official complaint PDF](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

- **DOJ Executed Non-Prosecution Agreement (July 2022):** [Open the official agreement PDF](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

- **DOJ Non-Prosecution Agreement Announcement (22 July 2022):** [Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)

- **FTC Settlement Announcement (26 October 2018):** [Open the official FTC announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber)

- **DOJ Former Chief Security Officer Conviction (5 October 2022):** [Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach)

- **DOJ Former Chief Security Officer Sentencing (5 May 2023):** [Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data)

- **ASD-STE100 Issue 9:** [Open the official ASD-STE100 website](https://www.asd-ste100.org/)

---

**Writing note:** This document uses ASD-STE100 Issue 9 writing principles. Full compliance has not yet been verified against the complete specification.

**Next step:** Review the case study and use its findings in the Problem Analysis section.
