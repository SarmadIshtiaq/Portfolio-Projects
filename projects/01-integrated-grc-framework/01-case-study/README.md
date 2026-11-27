# Uber 2016 Data Breach — Case Study

**Portfolio:** Integrated GRC Framework Design & Implementation

**Case type:** Independent research based on public evidence

**Case period:** October–November 2016

**Writing standard:** ASD-STE100 Issue 9

**Status:** In Progress — Research draft prepared

---

## 1. Purpose

This case study examines the 2016 Uber data breach.

It uses official public records from the U.S. Federal Trade Commission (FTC) and the U.S. Department of Justice (DOJ).

The study explains:

- What happened.
- How the attackers gained access.
- How they accessed cloud data.
- What information they obtained.
- How Uber responded.
- When Uber disclosed the breach.
- What regulatory and legal actions followed.

The study provides a factual basis for an independent Governance, Risk, and Compliance (GRC) framework design.

This is an independent portfolio project.

It is not an audit of Uber.

It does not claim access to Uber's internal systems, policies, or records.

## 2. Scope

This study focuses on the Uber data breach that occurred in October and November 2016.

It covers:

1. Access to a private GitHub repository.
2. Stolen credentials.
3. Exposure of an AWS access key.
4. Access to the Amazon S3 datastore.
5. Download of personal information.
6. Discovery and containment.
7. Payment to the attackers.
8. Delayed disclosure.
9. Regulatory and legal outcomes.

The study also describes the separate 2014 Uber data breach.

This comparison helps explain the difference between the two incidents.

The study uses public information only.

It does not make claims about controls that the public sources do not support.

## 3. Research Methodology

This case study uses primary sources from U.S. government agencies.

The main sources are:

- Federal Trade Commission (FTC).
- U.S. Department of Justice (DOJ).

The research process follows these steps:

1. Identify official source documents.
2. Extract relevant facts.
3. Record dates and events.
4. Compare information across sources.
5. Identify differences in source descriptions.
6. Link each fact to its source.
7. Separate documented facts from independent analysis.

Each source has a reference ID.

The IDs appear in the text as clickable links, such as [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf).

A reader can select a reference ID to open the original source.

## 4. Organisation Background

Uber Technologies, Inc. operates a technology platform.

The platform connects consumers with independent drivers for rideshare and delivery services. [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

Uber collects personal information from riders and drivers.

This information can include:

- Names.
- Email addresses.
- Phone numbers.
- Postal addresses.
- Driver's licence information.
- Bank account information.
- Trip records.
- Geolocation information.

The FTC complaint describes the types of personal information that Uber collected from riders and drivers. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

This list describes information collected by Uber.

It does not mean that every data type was exposed in the 2016 incident.

## 5. Incident Summary

In October and November 2016, attackers accessed Uber's private GitHub repository.

They used stolen credentials to gain access.

They found an AWS access key in plain-text code.

They used this key to access Uber's Amazon S3 datastore.

They downloaded personal information about Uber riders and drivers. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

The FTC complaint reports that the attackers downloaded 16 files between 13 October and 15 November 2016.

The files contained unencrypted personal information. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

Uber learned about the breach on or about 14 November 2016.

The attackers demanded a six-figure payment.

Uber paid them $100,000 in Bitcoin in December 2016. [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

Uber did not notify affected consumers until 21 November 2017.

Uber also disclosed the breach to the FTC in November 2017. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)

## 6. Difference Between the 2014 and 2016 Breaches

Uber experienced two separate data breaches.

Both incidents involved AWS credentials and access to the Amazon S3 datastore.

However, the attackers used different access paths.

### 6.1 The 2014 Data Breach

In May 2014, an AWS access key was posted to a public GitHub repository.

An intruder used the key to access Uber's Amazon S3 datastore.

The key gave access to data and documents in the datastore.

Uber discovered the incident in September 2014. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 6.2 The 2016 Data Breach

In 2016, attackers used stolen credentials to access Uber's private GitHub repository.

They found an AWS access key in the source code.

They used the key to access Uber's Amazon S3 datastore and download personal information. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 6.3 Comparison

| Area | 2014 incident | 2016 incident |
|---|---|---|
| GitHub repository | Public repository | Private repository |
| Initial access | Publicly exposed AWS key | Stolen credentials |
| AWS key | Posted publicly | Found in source code |
| Cloud service | Amazon S3 | Amazon S3 |
| Main data affected | Driver information | Rider and driver information |
| Discovery | September 2014 | November 2016 |

The two incidents must not be described as one event.

The 2016 incident used stolen credentials to reach a private repository.

The FTC complaint and DOJ agreement describe the different access paths. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

## 7. Technical Attack Path

The following sequence shows the attack path described in the public records.

```text
Previously exposed credentials
             |
             v
Access to private GitHub repository
             |
             v
AWS access key found in source code
             |
             v
Access to Amazon S3 datastore
             |
             v
Download of personal information
             |
             v
Exposure of rider and driver data
```

The FTC complaint and DOJ agreement support this sequence. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 7.1 Access to GitHub

The attackers used credentials that had been exposed in other data breaches.

They used these credentials to access Uber's private GitHub repository. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

### 7.2 Credential Management

The FTC complaint reported two weaknesses:

- Uber did not have a policy that prohibited engineers from reusing credentials.
- Uber did not require engineers to enable multi-factor authentication (MFA) when accessing its GitHub repositories. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

These statements appear in the FTC complaint.

They must be identified as allegations in that complaint.

### 7.3 AWS Access Key

The attackers found an AWS access key in plain-text code.

They used this key to access the Amazon S3 datastore. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 7.4 Amazon S3 Access

Amazon S3 is a cloud storage service.

Uber used this service to store data.

The attackers used the AWS credential to access the datastore.

The FTC complaint reports that the attackers downloaded 16 files between 13 October and 15 November 2016. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

### 7.5 Unencrypted Information

The FTC complaint states that the downloaded files contained unencrypted personal information.

It also states that nearly all the exposed information was collected before July 2015.

The information was stored in unencrypted database backup files. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

### 7.6 Other Access-Control Allegations

The FTC complaint also described a failure to require MFA for programmatic service account access to the Amazon S3 datastore until at least November 2016.

This is separate from the MFA issue for GitHub user accounts. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

## 8. Exposed Data

The FTC complaint reported the following data categories for U.S. riders and drivers:

| Data category | Reported amount |
|---|---:|
| Names and email addresses | Approximately 25.6 million |
| Names and mobile phone numbers | Approximately 22.1 million |
| Names and driver's licence numbers | Approximately 607,000 |

Source: FTC Revised Complaint. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

The DOJ's 2022 announcement reported approximately 57 million user records and 600,000 driver's licence numbers. [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)

### Important Note About the Figures

These figures come from different descriptions in official records.

The FTC figures describe specific data categories.

The DOJ figure describes approximately 57 million user records.

The category counts must not be added to calculate the number of unique affected people.

The term "records" must not be changed to "unique people" without supporting evidence.

## 9. Discovery and Incident Response

### 9.1 Discovery

On 14 November 2016, Uber's Chief Security Officer received an email from an attacker.

The attacker claimed to have accessed Uber's data and demanded a payment.

Uber's security team started an investigation. [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 9.2 Verification

Within approximately one day, Uber's security team learned that the attackers had:

- Accessed Uber's AWS environment.
- Accessed source code in GitHub.
- Found an AWS credential.
- Downloaded Uber data.
- Obtained information that included approximately 600,000 driver's licence numbers. [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 9.3 Containment

The DOJ agreement records that Uber's security team took several actions within hours of contact from the attackers.

The team:

- Sealed off the attackers' access point.
- Started a password reset.
- Established two-factor authentication for GitHub accounts.
- Rotated AWS service keys. [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

These actions took place after Uber learned about the breach.

They must not be described as preventive controls that were already active before the breach.

### 9.4 Payment

The attackers demanded a six-figure payment.

Uber paid them $100,000 in Bitcoin in December 2016.

The payment was made through the company's bug bounty program.

The DOJ agreement records that the attackers had taken and stored personal information. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 9.5 Non-Disclosure Agreements

The DOJ agreement records that the attackers signed non-disclosure agreements.

The agreements stated that the attackers had not taken or stored data.

The DOJ agreement also records that the attackers had, in fact, taken and stored large quantities of data. [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 9.6 Identification of the Attackers

Uber identified the two attackers in January 2017.

The attackers then signed new copies of the agreements in their real names.

The DOJ agreement records these events. [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

## 10. Disclosure and Notification

Uber learned about the breach on or about 14 November 2016.

The FTC complaint states that Uber did not notify affected consumers until 21 November 2017.

This was more than one year after discovery. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

The DOJ agreement records that Uber did not report the breach to the FTC until November 2017.

Uber's new management investigated the incident and disclosed it to affected drivers, the public, law enforcement, and regulators. [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

## 11. Verified Incident Timeline

| Date | Documented event | Source |
|---|---|---|
| 12 May 2014 | An intruder accessed Uber data with an AWS key posted to a public GitHub repository. | [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| September 2014 | Uber discovered the 2014 data breach. | [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| 21 May 2015 | The FTC issued a Civil Investigative Demand to Uber. | [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=) |
| 4 November 2016 | Uber's Chief Security Officer gave sworn testimony to the FTC about data security practices. | [S5](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach) |
| 13 October–15 November 2016 | The FTC complaint reports that attackers downloaded 16 files from Amazon S3 during this period. | [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| 14 November 2016 | An attacker contacted Uber and reported access to its data. | [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=) |
| November 2016 | Uber's security team investigated and took containment actions. | [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=) |
| December 2016 | Uber paid the attackers $100,000 in Bitcoin. | [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=) |
| January 2017 | Uber identified the two attackers. | [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=) |
| Fall 2017 | Uber's new management investigated the 2016 breach. | [S6](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data) |
| 21 November 2017 | Uber notified affected consumers. | [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) |
| November 2017 | Uber disclosed the breach to the FTC and other authorities. | [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) |
| 26 October 2018 | The FTC gave final approval to its settlement with Uber. | [S2](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber) |
| 22 July 2022 | Uber entered a non-prosecution agreement with federal prosecutors. | [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) |
| 5 October 2022 | A federal jury convicted Uber's former Chief Security Officer. | [S5](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach) |
| 5 May 2023 | The former Chief Security Officer received a sentence of three years' probation and a $50,000 fine. | [S6](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data) |

### Timeline Note

The FTC complaint reports a download period that ended on 15 November 2016.

The DOJ agreement states that Uber learned about the breach on 14 November 2016. It also states that the security team sealed off the attackers' access point within hours.

This study reports both source statements.

It does not infer an exact time for each file download.

## 12. Regulatory and Legal Outcomes

### 12.1 Federal Trade Commission Settlement — 2018

On 26 October 2018, the FTC gave final approval to a settlement with Uber.

The FTC press release describes the settlement as a response to allegations about Uber's privacy and data security practices.

The settlement required Uber to:

- Maintain a comprehensive privacy program.
- Obtain independent third-party assessments every two years.
- Continue these assessments for 20 years.
- Report certain future incidents involving unauthorized access to consumer information. [S2](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber)

### 12.2 State Attorneys General Settlement

The DOJ agreement records a civil settlement with the attorneys general of all 50 U.S. states and the District of Columbia.

Uber agreed to pay $148 million.

The agreement also required a corporate integrity program, data security safeguards, an incident response plan, data breach notification plans, and independent assessments. [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 12.3 Non-Prosecution Agreement — 2022

On 22 July 2022, Uber entered a non-prosecution agreement with the U.S. Attorney's Office for the Northern District of California.

Uber admitted and accepted responsibility for the acts of its officers, directors, employees, and agents in concealing the 2016 breach from the FTC. [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

A non-prosecution agreement is not the same as a criminal conviction.

This agreement resolved the federal criminal investigation of Uber on the terms stated in the agreement.

### 12.4 Former Chief Security Officer — Criminal Case

On 5 October 2022, a federal jury found Uber's former Chief Security Officer, Joseph Sullivan, guilty of two federal charges:

- Obstruction of Federal Trade Commission proceedings.
- Misprision of a felony. [S5](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach)

On 5 May 2023, the court sentenced him to three years of probation and ordered him to pay a $50,000 fine. [S6](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data)

This was an individual criminal case.

It must not be described as a criminal conviction of Uber.

## 13. Preliminary GRC Relevance

The incident provides a basis for further GRC analysis.

The following topics will be examined in later project sections.

| Area | Question for GRC analysis |
|---|---|
| Governance | Who owns security decisions and incident reporting? |
| Identity and access management | How should organisations control access to private repositories? |
| Credential management | How should organisations prevent credential reuse? |
| Multi-factor authentication | Which systems and accounts must use MFA? |
| Secrets management | How should organisations store and rotate cloud access keys? |
| Cloud security | How should organisations restrict access to cloud storage? |
| Data protection | How should organisations protect stored personal information? |
| Monitoring | How should organisations detect unusual access and data downloads? |
| Incident response | Who must investigate, contain, and report a security incident? |
| Regulatory reporting | Who must assess reporting duties and manage regulator communication? |
| Third-party programs | How should an organisation verify and manage bug bounty reports? |
| Accountability | How should senior management oversee incident decisions and records? |

These questions are topics for independent analysis.

They are not findings about Uber's current internal systems.

The next project sections will convert relevant findings into risk statements, control objectives, responsibilities, and proposed actions.

## 14. Evidence Classification

This portfolio separates information into four categories.

### 14.1 Documented Allegation

A documented allegation is a claim made by a regulator in a complaint.

Example:

The FTC complaint states that Uber did not require engineers to enable MFA when they accessed its GitHub repositories. [S1](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

This statement must be described as an allegation in the FTC complaint.

### 14.2 Company Admission

A company admission is a fact that the company accepted in a formal agreement.

Example:

Uber admitted and accepted responsibility for the acts of its officers, directors, employees, and agents in concealing the 2016 breach from the FTC. [S3](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement) [S4](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### 14.3 Court Finding

A court finding is an outcome decided by a court or jury.

Example:

A federal jury found Uber's former Chief Security Officer guilty of two federal charges in October 2022. [S5](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach)

### 14.4 Independent Analysis

Independent analysis is an interpretation of public facts.

Example:

A GRC framework should define ownership of credentials and access controls.

This is a proposed design choice.

It is not a claim about a control that Uber had or did not have.

## 15. Limitations

This is an independent portfolio research project.

It uses public information from official sources.

The author has no access to Uber's internal systems, records, policies, or employees.

The study does not represent:

- An internal audit.
- An external audit.
- A penetration test.
- A legal opinion.
- A review of Uber's current security posture.
- A verified GRC implementation at Uber.

The study does not claim that every cause of the breach is known.

It will state the limits of public evidence where needed.

## 16. Official References

The following sources support this case study.

### S1 — FTC Revised Complaint

**Organisation:** U.S. Federal Trade Commission

**Document:** Uber Technologies, Inc. — Revised Complaint

**Date:** October 2018

**Purpose:** GitHub access, credential reuse, MFA, AWS access key, Amazon S3 access, exposed data, and consumer notification.

[Open the official FTC Revised Complaint (PDF)](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

### S2 — FTC Final Settlement Announcement

**Organisation:** U.S. Federal Trade Commission

**Date:** 26 October 2018

**Document:** Federal Trade Commission Gives Final Approval to Settlement with Uber

**Purpose:** Regulatory action, privacy program, and independent assessments.

[Open the official FTC announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber)

### S3 — DOJ Non-Prosecution Agreement Announcement

**Organisation:** U.S. Department of Justice

**Date:** 22 July 2022

**Document:** Uber Enters Non-Prosecution Agreement Related to 2016 Data Breach

**Purpose:** Uber's admissions, approximate data exposure, and delayed disclosure.

[Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)

### S4 — Executed Non-Prosecution Agreement

**Organisation:** U.S. Department of Justice

**Date:** 22 July 2022

**Document:** Executed Non-Prosecution Agreement and Statement of Facts

**Purpose:** Detailed incident facts, attack path, response actions, payment, and company admissions.

[Open the official DOJ agreement (PDF)](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### S5 — Former Chief Security Officer Conviction

**Organisation:** U.S. Department of Justice

**Date:** 5 October 2022

**Document:** Former Chief Security Officer of Uber Convicted of Federal Charges for Covering Up Data Breach

**Purpose:** Trial outcome and individual accountability.

[Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach)

### S6 — Former Chief Security Officer Sentencing

**Organisation:** U.S. Department of Justice

**Date:** 5 May 2023

**Document:** Former Chief Security Officer of Uber Sentenced to Three Years' Probation

**Purpose:** Final reported sentence and fine.

[Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data)

### S7 — FTC Case Record

**Organisation:** U.S. Federal Trade Commission

**Document:** In the Matter of Uber Technologies, Inc.

**Purpose:** Official case record and related documents.

[Open the FTC case page](https://www.ftc.gov/legal-library/browse/cases-proceedings/152-3054-c-4662-uber-technologies-inc-matter)

### S8 — ASD-STE100 Issue 9

**Organisation:** ASD Simplified Technical English Maintenance Group

**Issue:** 9

**Date:** 15 January 2025

**Document:** ASD-STE100 Simplified Technical English — Standard for Technical Documentation

**Purpose:** Writing rules and controlled vocabulary reference.

[Open the official ASD-STE100 Issue 9 PDF](https://www.asd-ste100.org/assets/files/ASD-STE100_ISSUE9.pdf)

[Open the official ASD-STE100 website](https://www.asd-ste100.org/)

## 17. Writing Standard

This document uses ASD-STE100 Issue 9 as its technical writing reference. [S8](https://www.asd-ste100.org/assets/files/ASD-STE100_ISSUE9.pdf)

The writing approach aims to:

- Use clear and direct sentences.
- Keep one main idea in each sentence.
- Use consistent technical terms.
- Use approved words with their approved meanings.
- Avoid unclear or unnecessary wording.
- Keep headings and tables consistent.
- Separate facts from analysis.

A full ASD-STE100 compliance review has not yet been completed.

The document must not be described as fully compliant until its vocabulary and applicable rules have been checked against the complete official standard.

## 18. Current Status and Next Step

**Current status:** Research draft prepared. Review in progress.

This document establishes the public evidence and incident timeline.

The next stage is Problem Analysis.

That stage will examine the documented findings and identify their possible GRC implications.

The next stage will separate:

1. Confirmed technical facts.
2. Source allegations.
3. Company admissions.
4. Court findings.
5. Risk scenarios.
6. Proposed control objectives.

No proposed control will be presented as an actual Uber control.