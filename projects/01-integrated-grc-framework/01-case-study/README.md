# Uber 2016 Data Breach — Case Study

**Portfolio:** Integrated GRC Framework Design & Implementation

**Case type:** Independent research based on public evidence

**Case period:** October–November 2016

**Documentation standard:** ASD-STE100 Issue 9 writing principles

**Status:** completed

---

## 1. Purpose

This case study examines the 2016 Uber data breach.

It uses public records from the U.S. Federal Trade Commission (FTC) and the U.S. Department of Justice (DOJ).

The study explains:

- What happened.
- How the attackers accessed the data.
- What information they obtained.
- When Uber discovered the incident.
- How Uber responded.
- What happened after the incident.

The study will provide a factual basis for an independent Governance, Risk, and Compliance (GRC) framework design.

The case study does not represent an audit of Uber.

It does not claim access to Uber's internal systems, policies, or records.

## 2. Scope

This study focuses on the Uber data breach that occurred in October and November 2016.

It covers the following areas:

1. Private GitHub repository access.
2. Stolen credentials.
3. AWS access key exposure.
4. Amazon S3 datastore access.
5. Download of personal information.
6. Incident discovery and containment.
7. Payment to the attackers.
8. Delayed disclosure.
9. Regulatory and legal outcomes.

The study also describes the separate 2014 Uber data breach.

This comparison helps explain the difference between the two incidents.

The study uses public information only.

It does not make claims about controls that are not supported by public evidence.

## 3. Research Methodology

This case study uses primary sources from U.S. government agencies.

The main sources are:

- Federal Trade Commission (FTC).
- U.S. Department of Justice (DOJ).

The research process follows these steps:

1. Identify official source documents.
2. Extract the facts from each source.
3. Record dates and events.
4. Compare information across sources.
5. identify differences in source descriptions.
6. Link each finding to its source.
7. Separate documented facts from independent analysis.

Each source has a reference ID.

The IDs appear in the text as `[S1]`, `[S2]`, and so on.

A reader can use these IDs to find the original source in Section 15.

## 4. Organisation Background

Uber Technologies, Inc. operates a technology platform.

The platform connects consumers with independent drivers.

It supports ride-sharing and delivery services. [S4][S5]

Uber collects personal information from riders and drivers.

This information can include:

- Names.
- Email addresses.
- Mobile phone numbers.
- Driver's licence information.
- Bank account information.
- Trip records.
- Location information.

This list describes information collected by Uber.

It does not mean that every data type was exposed in the 2016 incident.

The reported data categories for the 2016 incident appear in Section 8.

## 5. Incident Summary

In October and November 2016, attackers accessed Uber's private GitHub repository.

They used stolen credentials to gain access.

They found an AWS access key in the repository.

They used the key to access Uber's Amazon S3 datastore.

They downloaded personal information about Uber riders and drivers. [S1][S5]

The FTC complaint reports that the attackers downloaded 16 files between 13 October and 15 November 2016.

The files contained unencrypted personal information. [S1]

Uber learned about the breach on 14 November 2016.

The attackers demanded a payment.

Uber paid them $100,000 in Bitcoin in December 2016. [S5]

Uber did not disclose the breach to the FTC until November 2017.

It also notified affected consumers in November 2017. [S1][S4]

## 6. Difference Between the 2014 and 2016 Breaches

Uber suffered two separate data breaches.

The incidents had a similar security issue. Both involved AWS access credentials and access to data in Amazon S3.

However, the attack paths were different.

### 6.1 The 2014 Data Breach

In 2014, an AWS access key was posted to a public GitHub repository.

An unauthorized person used the key to access Uber's Amazon S3 datastore.

The accessed file contained personal information about Uber drivers.

Uber discovered the incident in September 2014. [S5]

### 6.2 The 2016 Data Breach

In 2016, attackers used stolen credentials to access a private GitHub repository.

They found an AWS access key in the source code.

They used the key to access Uber's Amazon S3 datastore and download personal information. [S1][S5]

### 6.3 Comparison

| Area | 2014 incident | 2016 incident |
|---|---|---|
| GitHub repository | Public repository | Private repository |
| Access method | Publicly exposed AWS key | Stolen credentials |
| AWS key | Posted publicly | Found in source code |
| Cloud service | Amazon S3 | Amazon S3 |
| Data exposure | Driver information | Rider and driver information |
| Discovery | September 2014 | November 2016 |

The two incidents must not be described as one event.

The 2016 incident used a different method to access the private repository.

The comparison is based on DOJ records. [S5]

## 7. Technical Findings

### 7.1 Access to the Private GitHub Repository

The attackers used stolen credentials to access Uber's private source-code repository.

The DOJ agreement records that the attackers used stolen credentials.

The FTC complaint states that the passwords had been exposed in other large data breaches. [S1][S5]

### 7.2 Credential Management

The FTC complaint reported two security weaknesses:

- Uber did not have a policy that prohibited engineers from reusing credentials.
- Uber did not require multi-factor authentication (MFA) for access to its GitHub repositories. [S1]

These statements are allegations described in the FTC complaint.

They must not be presented as a separate final court finding.

### 7.3 AWS Access Key Exposure

The attackers found an AWS access key in the source code.

The FTC complaint describes the key as plain-text code.

The attackers used the key to access Uber's Amazon S3 datastore. [S1][S5]

### 7.4 Access to Amazon S3

Amazon S3 is a cloud storage service.

Uber used this service to store data.

The attackers used the AWS credential to access the datastore.

They downloaded 16 files between 13 October and 15 November 2016, according to the FTC complaint. [S1]

### 7.5 Unencrypted Personal Information

The FTC complaint states that the downloaded files contained unencrypted personal information.

It also states that nearly all of the exposed information had been collected before July 2015.

The information was stored in unencrypted database backup files. [S1]

### 7.6 Security Actions After Discovery

The DOJ agreement records that Uber's security team took several actions after it learned about the incident.

The team:

- Sealed off the attackers' access point.
- Started a password reset.
- Established two-factor authentication for GitHub accounts.
- Rotated AWS service keys. [S5]

These actions took place after the incident came to light.

They must not be described as preventive controls that were already active before the breach.

## 8. Exposed Data

The FTC complaint reported the following data categories for U.S. riders and drivers:

| Data category | Reported amount |
|---|---:|
| Names and email addresses | Approximately 25.6 million |
| Names and mobile phone numbers | Approximately 22.1 million |
| Names and driver's licence numbers | Approximately 607,000 |

Source: FTC Revised Complaint. [S1]

The DOJ's 2022 announcement reported approximately 57 million user records and 600,000 driver's licence numbers. [S4]

### Important note about the figures

These figures come from different descriptions in official records.

The FTC figures describe specific data categories.

The DOJ figure describes approximately 57 million user records.

The category counts must not be added to calculate the number of unique affected people.

The term "records" must also not be changed to "unique people" without supporting evidence.

## 9. Incident Discovery and Response

### 9.1 Discovery

On 14 November 2016, an attacker contacted Uber's Chief Security Officer.

The attacker claimed to have accessed Uber's data.

The attacker demanded a large payment. [S5]

Uber's security team started an investigation.

The team confirmed that the attackers had accessed AWS and obtained personal information.

The team learned that the stolen data included approximately 600,000 driver's licence numbers. [S5]

### 9.2 Containment

The security team closed the attackers' access point.

It also initiated password resets, enabled two-factor authentication for GitHub accounts, and rotated AWS service keys. [S5]

### 9.3 Payment

The attackers demanded a payment in the six-figure range.

Uber paid them $100,000 in Bitcoin in December 2016.

The payment was handled under the company's bug bounty program.

The DOJ agreement records that the attackers withdrew the payment before Uber identified them and before the security team received assurances that the data had been deleted. [S5]

### 9.4 Non-Disclosure Agreements

The DOJ records state that the attackers signed non-disclosure agreements.

These agreements included statements that the attackers had not taken or stored data.

The DOJ record states that the attackers had, in fact, obtained and stored personal information. [S5]

### 9.5 Notification

The FTC complaint records that Uber notified affected consumers on 21 November 2017.

The DOJ records state that Uber disclosed the breach to the FTC and other authorities in November 2017, under new executive leadership. [S1][S4]

The time between discovery and disclosure was more than one year.

## 10. Verified Incident Timeline

| Date | Event | Evidence |
|---|---|---|
| May 2014 | A separate breach involved an AWS key posted to a public GitHub repository. | [S5] |
| September 2014 | Uber discovered the 2014 breach. | [S5] |
| 21 May 2015 | The FTC issued a Civil Investigative Demand to Uber. | [S5] |
| 4 November 2016 | Uber's Chief Security Officer gave sworn testimony to the FTC about security practices. | [S6] |
| 13 October–15 November 2016 | The FTC complaint reports that attackers downloaded 16 files from Amazon S3 during this period. | [S1] |
| 14 November 2016 | An attacker contacted Uber and reported access to its data. | [S5] |
| November 2016 | Uber's security team investigated and took containment actions. | [S5] |
| December 2016 | Uber paid the attackers $100,000 in Bitcoin. | [S5][S6] |
| January 2017 | Uber identified the attackers. | [S5] |
| Fall 2017 | New management investigated the 2016 breach. | [S6] |
| 21 November 2017 | Uber notified affected consumers, according to the FTC complaint. | [S1] |
| November 2017 | Uber disclosed the breach to the FTC and other authorities. | [S4] |
| 26 October 2018 | The FTC gave final approval to its revised settlement with Uber. | [S2] |
| 22 July 2022 | Uber entered a non-prosecution agreement with federal prosecutors. | [S4][S5] |
| 5 October 2022 | A federal jury convicted Uber's former Chief Security Officer of two federal charges. | [S6] |
| 5 May 2023 | The former Chief Security Officer received a sentence of three years' probation and a $50,000 fine. | [S7] |

### Timeline note

The FTC complaint reports a download period that ended on 15 November 2016.

The DOJ agreement records that Uber learned about the breach on 14 November 2016 and that its security team then closed the attackers' access point.

This study reports both source descriptions.

It does not assume an exact time for the final data download.

## 11. Regulatory and Legal Outcomes

### 11.1 Federal Trade Commission Settlement — 2018

On 26 October 2018, the FTC gave final approval to a revised settlement with Uber.

The settlement required Uber to:

- Maintain a comprehensive privacy program.
- Obtain independent third-party assessments every two years.
- Continue these assessments for 20 years.
- Report certain future incidents involving unauthorized access to consumer information. [S2]

The FTC press release describes the settlement as a response to allegations about Uber's privacy and data security practices.

### 11.2 State Attorneys General Settlement

The DOJ agreement records a civil settlement with the attorneys general of all 50 U.S. states and the District of Columbia.

Uber agreed to pay $148 million.

The agreement also required a corporate integrity program, data security safeguards, an incident response plan, and independent assessments over a ten-year period. [S5]

### 11.3 Non-Prosecution Agreement — 2022

On 22 July 2022, Uber entered a non-prosecution agreement with the U.S. Attorney's Office for the Northern District of California.

Uber admitted and accepted responsibility for the acts of its officers, directors, employees, and agents in concealing the 2016 breach from the FTC. [S4][S5]

A non-prosecution agreement is not the same as a criminal conviction.

This agreement resolved the federal criminal investigation of Uber on the terms stated in the agreement.

### 11.4 Former Chief Security Officer — Criminal Case

On 5 October 2022, a federal jury found Joseph Sullivan, Uber's former Chief Security Officer, guilty of:

- Obstruction of FTC proceedings.
- Misprision of a felony. [S6]

On 5 May 2023, the court sentenced him to three years of probation and ordered him to pay a $50,000 fine. [S7]

This was an individual criminal case.

It must not be described as a criminal conviction of Uber.

## 12. Preliminary GRC Relevance

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
| Incident response | Who must investigate, contain, and escalate a security incident? |
| Regulatory reporting | Who must assess reporting duties and manage regulator communication? |
| Third-party programs | How should a bug bounty program verify and manage security reports? |
| Accountability | How should senior management oversee incident decisions and records? |

These questions are topics for independent analysis.

They are not additional findings about Uber's internal systems.

The next project sections will convert relevant findings into risk statements, control objectives, responsibilities, and proposed actions.

## 13. Evidence and Analysis Rules

This portfolio separates information into three categories.

### 13.1 Documented Fact

A documented fact is supported by an official source.

Example:

The DOJ agreement states that attackers used stolen credentials to access a private source-code repository. [S5]

### 13.2 Source Allegation or Claim

A source allegation is a statement made in a complaint or other legal document.

Example:

The FTC complaint states that Uber did not require MFA for access to its GitHub repositories at the time. [S1]

This statement must be identified as an allegation in the complaint.

### 13.3 Independent Analysis

Independent analysis is an interpretation of the available facts.

Example:

A GRC framework should define ownership of credentials and access controls.

This is a proposed design choice.

It is not a claim about a control that Uber had or did not have.

## 14. Limitations

This is an independent portfolio research project.

It uses public information from official sources.

The author has no access to Uber's internal systems, records, policies, or employees.

The study does not represent:

- An internal audit.
- An external audit.
- A penetration test.
- A legal opinion.
- A review of Uber's current security posture.
- A verified implementation at Uber.

The study does not claim that every possible cause of the breach is known.

The project will identify limits when public evidence does not support a conclusion.

## 15. Official References

The following sources support this case study.

### S1 — FTC Revised Complaint

**Organisation:** U.S. Federal Trade Commission

**Date:** 26 October 2018

**Document:** Uber Technologies — Revised Complaint

**Purpose:** Technical details, GitHub access, credential reuse, MFA, AWS access key, downloaded files, exposed data, and consumer notification.

[Open the official FTC Revised Complaint (PDF)](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

### S2 — FTC Final Settlement Announcement

**Organisation:** U.S. Federal Trade Commission

**Date:** 26 October 2018

**Document:** Federal Trade Commission Gives Final Approval to Settlement with Uber

**Purpose:** Regulatory settlement, privacy program, and independent assessments.

[Open the official FTC announcement](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber)

### S3 — FTC Case Record

**Organisation:** U.S. Federal Trade Commission

**Document:** In the Matter of Uber Technologies, Inc.

**Purpose:** Official case record and related documents.

[Open the FTC case page](https://www.ftc.gov/legal-library/browse/cases-proceedings/152-3054-c-4662-uber-technologies-inc-matter)

### S4 — DOJ Non-Prosecution Agreement Announcement

**Organisation:** U.S. Department of Justice

**Date:** 22 July 2022

**Document:** Uber Enters Non-Prosecution Agreement Related to 2016 Data Breach

**Purpose:** Uber's admissions, approximate data exposure, and delayed disclosure.

[Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement-related-2016-data-breach)

### S5 — Executed Non-Prosecution Agreement

**Organisation:** U.S. Department of Justice

**Date:** 22 July 2022

**Document:** Executed Non-Prosecution Agreement and Statement of Facts

**Purpose:** Detailed incident facts, attack path, response actions, payment, and company admissions.

[Open the official DOJ agreement (PDF)](https://www.justice.gov/usao-ndca/press-release/file/1521546/dl?inline=)

### S6 — Former Chief Security Officer Conviction

**Organisation:** U.S. Department of Justice

**Date:** 5 October 2022

**Document:** Former Chief Security Officer of Uber Convicted of Federal Charges for Covering Up Data Breach

**Purpose:** Trial outcome and individual accountability.

[Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-convicted-federal-charges-covering-data-breach)

### S7 — Former Chief Security Officer Sentencing

**Organisation:** U.S. Department of Justice

**Date:** 5 May 2023

**Document:** Former Chief Security Officer of Uber Sentenced to Three Years' Probation

**Purpose:** Final reported sentence and fine.

[Open the official DOJ announcement](https://www.justice.gov/usao-ndca/pr/former-chief-security-officer-uber-sentenced-three-years-probation-covering-data)

### S8 — ASD-STE100 Official Standard

**Organisation:** ASD Simplified Technical English Maintenance Group

**Current edition:** Issue 9, 15 January 2025

**Purpose:** Technical writing rules and controlled vocabulary reference.

[Open the official ASD-STE100 website](https://www.asd-ste100.org/)

[Open the official ASD-STE100 downloads page](https://asd-ste100.org/STE_downloads.html)

---

## 16. Writing Standard

This document uses ASD-STE100 Issue 9 as its technical writing reference.

The writing approach aims to:

- Use clear and direct sentences.
- Keep one main idea in each sentence.
- Use consistent technical terms.
- Use approved words with their approved meanings.
- Avoid unclear or unnecessary wording.
- Keep headings and tables consistent.
- Separate facts from analysis.

A full ASD-STE100 compliance review has not yet been completed.

The document must not be described as fully compliant until its vocabulary and applicable rules have been checked against the complete official specification.

## 17. Current Status and Next Step

**Current status:** Factual case study draft.

The current work establishes the public evidence and incident timeline.

The next stage is Problem Analysis.

That stage will examine the documented findings and identify their possible GRC implications.

The next stage will also separate:

1. Confirmed technical facts.
2. Governance concerns.
3. Risk scenarios.
4. Compliance questions.
5. Proposed control objectives.

No proposed control will be presented as an actual Uber control.
