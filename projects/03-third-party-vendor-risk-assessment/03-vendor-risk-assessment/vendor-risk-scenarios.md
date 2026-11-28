# Vendor Risk Scenarios and Analysis

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Assessment Type:** Third-Party Vendor Risk Assessment  
**Case:** Fictional Avenloft Third-Party Risk Review

---

## 1. Purpose

This document identifies and analyzes the principal information security and privacy risk scenarios associated with Avenloft's use of CobaltCedar Analytics' SupportLens SaaS platform.

The scenarios are based on the fictional case evidence and use the methodology documented in `risk-assessment-methodology.md`.

The assessment focuses on three areas:

1. Unauthorized access to Avenloft support data through compromised vendor customer accounts.
2. Potential cross-tenant exposure of Avenloft data.
3. Excessive retention or incomplete deletion of Avenloft data.

The risk ratings represent qualitative analyst judgments. They are not confirmed incidents or independently validated findings unless explicitly stated.

## 2. Risk Rating Summary

The assessment uses the case-specific qualitative matrix documented in the methodology.

| Risk ID | Risk Scenario | Inherent Likelihood | Inherent Impact | Inherent Risk | Residual Likelihood | Residual Impact | Residual Risk | Proposed Target |
|---|---|---|---|---|---|---|---|---|
| TPRM-R01 | Compromised account and unauthorized data export | High | High | High | Moderate | Moderate | Moderate | Low |
| TPRM-R02 | Cross-tenant exposure of Avenloft data | Low | High | Moderate | Low | High | Moderate | Moderate |
| TPRM-R03 | Excessive retention and incomplete data deletion | Moderate | Moderate | Moderate | Moderate | Moderate | Moderate | Low |

**Important:** Target residual risk represents a proposed outcome after treatment and validation. It is not the current risk rating and must not be treated as achieved.

## 3. TPRM-R01 — Compromised Account and Unauthorized Data Export

### 3.1 Risk Description

**Risk statement:**

If an attacker compromises a SupportLens customer account, particularly an account with analytics export permissions, the attacker could gain unauthorized access to Avenloft support information and export customer or business-related data. This could result in unauthorized disclosure, privacy concerns, contractual exposure, incident response costs, and reputational damage.

### 3.2 Affected Assets and Information

The information uploaded to SupportLens includes:

- Customer company names.
- Business contact names and email addresses.
- Ticket subjects and free-text ticket bodies.
- Ticket severity and product area.
- Timestamps, case owners, and resolution codes.
- Potential technical details within free-text support content, such as logs, hostnames, identifiers, and troubleshooting information.

The case states that payment-card data, authentication secrets, source code, direct production database records, and attachments are excluded from the weekly uploads.

### 3.3 Threat Event

An attacker obtains valid credentials for an Avenloft SupportLens user account through credential stuffing, password reuse, phishing, or another account-compromise technique.

The attacker then accesses the account and potentially exports analytics results if the compromised account has export permissions.

### 3.4 Relevant Weaknesses and Exposure

- TOTP MFA is available on the Standard plan but is not mandatory.
- Only 5 of the 8 Avenloft user accounts have TOTP enabled.
- All 8 Avenloft users can view uploaded support data.
- 4 users have analytics export permissions.
- The vendor's March 2026 credential-stuffing incident affected 9 customer accounts across 4 organizations.
- Two compromised accounts in that incident had export permissions and exported analytics data.
- The vendor increased MFA enrollment prompts after the incident, but MFA remained optional on the Standard plan.
- Avenloft does not have a formal retained access-certification process.

### 3.5 Existing Controls

| Existing Control | Evidence or Case Detail | Assessment |
|---|---|---|
| TOTP MFA availability | Available on Standard plan | Positive control capability, but optional enrollment limits protection. |
| MFA enrollment | 5 of 8 Avenloft users enrolled | Partially implemented for Avenloft accounts. |
| Export permissions | 4 users have export access | Some separation of viewing and export permissions exists, but permissions require review. |
| Vendor monitoring | Vendor detected unusual login and export activity during the March incident | Detective capability is demonstrated by the reported incident response. |
| Session revocation and account reset | Used during the March incident | Corrective response actions were reported. |
| IP blocking | Used during the March incident | Additional corrective measure reported by the vendor. |
| Avenloft access review | Informal review during quarterly operations review | No formal retained access certification was supplied. |
| Manual data transfer | Weekly CSV upload; no direct Salesforce integration | Limits direct system connectivity but does not prevent misuse of uploaded data. |

### 3.6 Inherent Risk Assessment

| Factor | Rating | Rationale |
|---|---|---|
| Likelihood | High | A credential-stuffing incident involving customer accounts and unauthorized analytics exports has already been reported by the vendor. MFA is not mandatory on the Standard plan. |
| Impact | High | Unauthorized export could expose customer contact information and support content, potentially creating privacy, contractual, reputational, and response consequences. |
| **Inherent Risk** | **High** | High likelihood combined with high impact results in a High rating under the case matrix. |

### 3.7 Residual Risk Assessment

The residual assessment considers the vendor's reported monitoring and incident response capabilities, the partial enrollment of Avenloft users in TOTP MFA, restricted export permissions, and the limited data scope.

These controls reduce some exposure, but they do not eliminate account-compromise risk.

| Factor | Rating | Rationale |
|---|---|---|
| Likelihood | Moderate | Monitoring, partial MFA enrollment, and restricted export permissions provide some protection. However, MFA remains optional and some Avenloft accounts do not have TOTP enabled. |
| Impact | Moderate | The uploaded data remains sensitive business and customer-support information. However, attachments, payment-card data, authentication secrets, source code, and direct production database records are excluded. |
| **Residual Risk** | **Moderate** | Moderate likelihood combined with moderate impact results in a Moderate rating. |

### 3.8 Recommended Treatment

| Action ID | Recommended Action | Proposed Owner | Required Evidence |
|---|---|---|---|
| R01-A1 | Require TOTP MFA for all Avenloft SupportLens users or evaluate an authentication arrangement that enforces MFA. | Marcus Holloway / CobaltCedar | Configuration evidence and confirmation of MFA enrollment for all active users. |
| R01-A2 | Review all active accounts and remove access that is no longer required. | Marcus Holloway / Lena Ortiz | Dated user access review and approved access list. |
| R01-A3 | Review export permissions and restrict them to users with a documented business need. | Lena Ortiz / Marcus Holloway | Approved export-permission matrix and platform configuration evidence. |
| R01-A4 | Establish a periodic, documented access-certification process. | Aaron Bell / Lena Ortiz | Completed access certification records and defined review frequency. |
| R01-A5 | Obtain evidence of vendor incident monitoring, response procedures, and relevant customer-account security improvements. | Aaron Bell / CobaltCedar | Security documentation or appropriate assurance evidence. |

### 3.9 Proposed Target Residual Risk

**Target:** Low

This target assumes mandatory MFA for Avenloft accounts, controlled export permissions, documented access certification, and validated monitoring and response arrangements.

The target should only be accepted after implementation evidence has been reviewed. Until then, the current residual rating remains Moderate.

---

## 4. TPRM-R02 — Cross-Tenant Exposure of Avenloft Data

### 4.1 Risk Description

**Risk statement:**

If SupportLens' logical tenant-isolation controls fail or are incorrectly implemented, another vendor customer or unauthorized party could gain access to Avenloft's uploaded support information. This could result in cross-customer data disclosure, privacy concerns, contractual exposure, and loss of customer trust.

### 4.2 Affected Assets and Information

- Avenloft support-case CSV exports.
- Customer company and business contact information.
- Support ticket subjects and free-text descriptions.
- Analytics dashboards and account-level reporting.
- Related service metadata and customer-specific records.

### 4.3 Threat Event

A technical weakness, configuration error, or application-level authorization failure allows a user from another SupportLens tenant to access Avenloft data.

Potential examples include:

- Incorrect tenant authorization checks.
- Inadequate isolation between customer records.
- Application-level access-control defects.
- Misconfigured data access or reporting functionality.

These are plausible threat scenarios, not confirmed SupportLens vulnerabilities.

### 4.4 Relevant Weaknesses and Exposure

- SupportLens is a multi-tenant SaaS platform hosted on AWS U.S. regions.
- The vendor states that logical tenant isolation is implemented.
- The case provides an architecture narrative but no separate test evidence specifically validating tenant isolation.
- Avenloft uploads customer-support information to the platform.
- The service is not directly integrated with Salesforce and the vendor has no Avenloft credentials or direct production access.

### 4.5 Existing Controls

| Existing Control | Evidence or Case Detail | Assessment |
|---|---|---|
| Logical tenant isolation | Vendor states that customer tenants are logically separated | Relevant control claim, but independent validation was not supplied. |
| AWS hosting | Platform is hosted on AWS U.S. regions | Provides hosting infrastructure; does not independently prove application-level tenant isolation. |
| Encryption | Vendor reports TLS 1.2+ and AES-256 | Supports data protection in transit and at rest, subject to implementation and validation. |
| Manual CSV transfer | Avenloft uploads weekly exports rather than using a direct integration | Reduces direct connectivity and integration exposure. |
| No vendor production access | Vendor has no Avenloft production database or endpoint access | Limits direct access to Avenloft's internal environment. |
| Restricted data scope | Attachments, payment-card data, authentication secrets, source code, and direct production database records are excluded | Reduces the potential scope of exposure. |

### 4.6 Inherent Risk Assessment

| Factor | Rating | Rationale |
|---|---|---|
| Likelihood | Low | Cross-tenant exposure is a plausible SaaS threat scenario, but the case provides no confirmed cross-tenant incident or evidence of a specific isolation vulnerability. |
| Impact | High | Successful cross-tenant access could expose information belonging to Avenloft and its customers, potentially affecting confidentiality, privacy, contractual obligations, and customer trust. |
| **Inherent Risk** | **Moderate** | Low likelihood combined with high impact results in a Moderate rating under the case matrix. |

### 4.7 Residual Risk Assessment

The vendor reports logical tenant isolation, encryption, and a multi-tenant architecture. Avenloft also uses a manual upload process and does not provide direct production access to the vendor.

However, the case packet does not include independent technical validation specifically demonstrating that tenant-isolation controls operate effectively.

| Factor | Rating | Rationale |
|---|---|---|
| Likelihood | Low | No cross-tenant incident or specific isolation weakness is identified in the supplied case. The vendor's architecture and control claims provide some assurance, but their effectiveness is not independently demonstrated. |
| Impact | High | If tenant isolation fails, the potential consequences of unauthorized access to customer-support data remain significant. |
| **Residual Risk** | **Moderate** | Low likelihood combined with high impact results in a Moderate rating. |

### 4.8 Recommended Treatment

| Action ID | Recommended Action | Proposed Owner | Required Evidence |
|---|---|---|---|
| R02-A1 | Obtain technical documentation describing tenant-isolation architecture and authorization boundaries. | Aaron Bell / CobaltCedar | Architecture and access-control documentation. |
| R02-A2 | Request evidence of testing specifically covering cross-tenant access restrictions. | Aaron Bell / CobaltCedar | Relevant penetration-test results, test scope, or independent validation evidence. |
| R02-A3 | Confirm that application authorization controls prevent access to another customer's data through dashboards, APIs, exports, and reporting functions. | CobaltCedar | Test results or other suitable validation evidence. |
| R02-A4 | Continue limiting uploaded information to the minimum data required for the SupportLens business purpose. | Lena Ortiz / Marcus Holloway | Approved export field list and periodic data-scope review. |

### 4.9 Proposed Target Residual Risk

**Target:** Moderate

The potential impact of a successful cross-tenant exposure remains high because the service processes customer-support information.

Even after stronger validation, this scenario may reasonably retain a Moderate rating under the case matrix. The main objective is to increase confidence in the low likelihood assessment through suitable technical evidence and ongoing data minimization.

The target is not considered achieved until appropriate evidence has been reviewed.

---

## 5. TPRM-R03 — Excessive Retention and Incomplete Data Deletion

### 5.1 Risk Description

**Risk statement:**

If Avenloft support data remains stored by CobaltCedar longer than necessary or is not completely deleted after contract termination, the information could remain exposed to unauthorized access, future security incidents, or inappropriate retention. This could result in privacy concerns, contractual issues, and difficulty demonstrating appropriate data disposal.

### 5.2 Affected Assets and Information

- Uploaded customer-support CSV files.
- Customer and business contact information.
- Ticket subjects and free-text descriptions.
- Analytics results derived from support-case information.
- Backup copies containing Avenloft data.

### 5.3 Threat Event

Avenloft's relationship with the vendor ends or the data is no longer required, but data remains in active storage or backups beyond the intended retention period.

Potential consequences include:

- Unnecessary continued retention of customer information.
- Incomplete deletion after termination.
- Inability to demonstrate that deletion was completed.
- Exposure of retained information during a later security incident.

The case does not establish that CobaltCedar has failed to delete Avenloft data. This is a risk scenario based on the documented retention arrangements and evidence gaps.

### 5.4 Relevant Weaknesses and Exposure

- Standard plan data retention is 180 days by default.
- Shorter configurable retention is available on the Enterprise tier.
- Active data deletion begins within 30 days after termination.
- Encrypted backups expire through a further 35-day backup lifecycle.
- No sample deletion certificate was supplied.
- Avenloft's contract does not provide a detailed, independently validated deletion assurance mechanism.
- The case does not establish whether all retained copies and derived analytics data are covered by a documented deletion confirmation.

### 5.5 Existing Controls

| Existing Control | Evidence or Case Detail | Assessment |
|---|---|---|
| Defined retention period | Standard plan retention is 180 days by default | Provides a stated retention period, but may exceed Avenloft's preferred period. |
| Enterprise retention option | Shorter configurable retention is available on Enterprise | Provides a potential control improvement at additional cost. |
| Active data deletion | Deletion begins within 30 days after termination | Defined vendor process, but supporting execution evidence was not supplied. |
| Backup lifecycle | Encrypted backups expire through a further 35-day lifecycle | Provides a stated backup-expiration process. |
| Encryption | Vendor reports AES-256 at rest | Reduces exposure from certain forms of unauthorized access, but does not replace deletion. |
| Deletion evidence | No sample deletion certificate supplied | Evidence gap; Avenloft cannot verify the reported deletion process from the case packet. |

### 5.6 Inherent Risk Assessment

| Factor | Rating | Rationale |
|---|---|---|
| Likelihood | Moderate | The vendor has a defined retention and deletion process, but the default retention period and backup lifecycle create a continuing data-retention window. |
| Impact | Moderate | Retained information includes customer contacts and support content. Unauthorized disclosure or failure to dispose of the data could create privacy, contractual, and reputational consequences. |
| **Inherent Risk** | **Moderate** | Moderate likelihood combined with moderate impact results in a Moderate rating. |

### 5.7 Residual Risk Assessment

The vendor reports defined retention, active deletion after termination, encrypted backups, and a backup-expiration lifecycle.

However, Avenloft has not been provided with a sample deletion certificate or other execution evidence demonstrating how deletion is completed and confirmed.

| Factor | Rating | Rationale |
|---|---|---|
| Likelihood | Moderate | The defined process provides some control, but the absence of deletion evidence and the continued backup lifecycle leave uncertainty about execution and completeness. |
| Impact | Moderate | The types of information and potential privacy and contractual consequences remain relevant after considering the stated controls. |
| **Residual Risk** | **Moderate** | Moderate likelihood combined with moderate impact results in a Moderate rating. |

### 5.8 Recommended Treatment

| Action ID | Recommended Action | Proposed Owner | Required Evidence |
|---|---|---|---|
| R03-A1 | Review whether the 180-day Standard plan retention period is appropriate for Avenloft's business and privacy requirements. | Hannah Kim / Lena Ortiz | Documented retention requirement and business-owner approval. |
| R03-A2 | Agree on a written data-retention and deletion schedule covering active records, analytics outputs, and backups. | Hannah Kim / CobaltCedar | Contractual wording or documented vendor commitment. |
| R03-A3 | Obtain a sample deletion certificate or equivalent evidence explaining how deletion is confirmed after termination. | Aaron Bell / CobaltCedar | Sample deletion confirmation and documented deletion process. |
| R03-A4 | Clarify how the backup-expiration lifecycle is handled after termination and whether any exceptions apply. | CobaltCedar / Hannah Kim | Written backup-deletion and retention explanation. |
| R03-A5 | Evaluate whether the Enterprise retention capability is necessary and proportionate to Avenloft's data-retention requirements and cost considerations. | Noah Grant / Hannah Kim / Lena Ortiz | Documented cost-benefit and privacy assessment. |

### 5.9 Proposed Target Residual Risk

**Target:** Low

This target assumes that Avenloft's retention requirements are documented, the vendor agrees to appropriate retention and deletion terms, and deletion processes can be demonstrated through suitable evidence.

The target should only be recorded as achieved after the agreed controls and evidence have been validated.

---

## 6. Cross-Scenario Observations

The three scenarios share several underlying themes.

### 6.1 Customer Authentication and Access

The March 2026 credential-stuffing incident demonstrates that customer-account compromise is a relevant threat to the vendor service. Optional MFA and incomplete enrollment among Avenloft users warrant additional attention.

### 6.2 Evidence and Assurance

The vendor has supplied assurance summaries and security statements, but some important controls lack specific supporting evidence.

Examples include:

- Independent tenant-isolation validation.
- Evidence of penetration-test remediation and retesting.
- Evidence demonstrating deletion completion.
- Formal retained access-certification records.

### 6.3 Data Minimization

Avenloft's weekly manual export process provides an opportunity to control what information is uploaded. Data minimization should remain part of the ongoing vendor risk-management process.

### 6.4 Contractual Safeguards

Retention, deletion, incident notification, and subprocessor provisions should be reviewed to ensure that contractual requirements match Avenloft's risk and privacy expectations.

## 7. Important Case Timeline and Evidence Limitations

The supplied case packet identifies:

- **October 12, 2026:** Case issue date.
- **October 30, 2026:** Stated target remediation date for the open Medium penetration-test finding concerning bulk-export rate limiting.
- **November 1, 2026:** Contract renewal date.

The case packet does not provide evidence confirming whether the open penetration-test finding was remediated by October 30, 2026, whether an independent retest was completed, or what decision was made at the November 1, 2026 renewal.

These dates have passed. The assessment therefore treats remediation and renewal outcomes as **unverified from the supplied case evidence**. No completion or approval is assumed.

The open bulk-export rate-limiting finding is relevant context for the vendor's security posture and should be considered alongside TPRM-R01. However, the case does not establish that this finding caused the March 2026 credential-stuffing incident.

## 8. Overall Risk Conclusion

Based on the supplied fictional case evidence, SupportLens presents a **Moderate residual risk profile** across the three assessed scenarios.

The main areas requiring management attention are:

- Customer-account authentication and export permissions.
- Independent validation of tenant-isolation controls.
- Evidence of data deletion and backup expiration.
- Completion and validation of outstanding security remediation.
- Contractual clarity around security and privacy obligations.

The service has limited operational dependency because Avenloft can use Salesforce reporting as an alternative, although switching may require several weeks of manual effort. This provides some flexibility when considering risk treatment and vendor decisions.

A continued-use or renewal decision should be based on documented treatment actions, validation evidence, business-owner input, contractual review, and authorized risk acceptance.

**Assessment limitation:** This is a portfolio assessment based on a fictional case packet. It is not a real vendor audit, independent technical assessment, or formal approval to use the service.