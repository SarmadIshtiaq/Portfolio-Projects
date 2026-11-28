# Third-Party Vendor Risk Assessment

**Project ID:** GRC-TPRM-003  
**Domain:** Governance, Risk & Compliance (GRC)  
**Focus:** Third-Party Risk Management (TPRM), Vendor Due Diligence, Cybersecurity Risk, Privacy, and Contractual Governance  
**Assessment Frameworks:** NIST CSF 2.0, NIST SP 800-30 Rev. 1, NIST SP 1305, NIST SP 1326, and NIST SP 800-161 Rev. 1

---

## 1. Project Overview

This project demonstrates a structured third-party vendor risk assessment for a fictional organization, Avenloft Systems Group, evaluating its use of a fictional SaaS provider, CobaltCedar Analytics, Inc., and its SupportLens analytics platform.

The assessment examines the vendor relationship, business dependency, data-processing activities, security controls, assurance evidence, security incidents, contractual safeguards, and data-retention arrangements.

The objective is to evaluate the vendor's security and privacy posture, identify inherent and residual risks, assess the quality of available evidence, recommend proportionate remediation, and support an informed vendor-management decision.

The project follows a practical GRC assessment lifecycle, from relationship understanding and due diligence through risk analysis, remediation planning, ongoing monitoring, and executive decision-making.

**Case disclaimer:** Avenloft, CobaltCedar Analytics, SupportLens, and all individuals and events described in this assessment are fictional. This is an independent portfolio and learning exercise, not a real vendor audit or investigation.

## 2. Business Scenario

Avenloft uses SupportLens to analyze closed customer-support cases and generate analytics dashboards and account-level reporting.

| Attribute | Case Information |
|---|---|
| Vendor | CobaltCedar Analytics, Inc. |
| Service | SupportLens |
| Service type | Multi-tenant SaaS analytics platform |
| Relationship start | February 2026 |
| Annual spend | $18,600 |
| Stated renewal date | November 1, 2026 |
| Avenloft users | 8 Customer Success managers and operations analysts |
| Data transfer | Weekly manual CSV exports from Salesforce |
| Hosting | AWS U.S. regions, according to the case |
| Direct production access | No direct Avenloft production or endpoint access reported |
| Business dependency | Limited; Salesforce reporting provides an alternative |

The weekly exports may contain customer company names, business contact names and email addresses, ticket subjects, free-text ticket bodies, severity, product area, timestamps, case owner, and resolution codes.

The case states that payment-card data, authentication secrets, source code, direct production database records, and attachments are excluded.

Free-text content may still contain logs, hostnames, identifiers, and troubleshooting details. Therefore, the information remains relevant to confidentiality and privacy risk assessment.

## 3. Project Objectives

The assessment aims to:

1. Understand the vendor relationship, service purpose, and business dependency.
2. Map business processes and data flows.
3. Identify information exposure and access risks.
4. Review vendor security questionnaires and supplied assurance evidence.
5. Evaluate the SOC 2 Type II and penetration-test summaries.
6. Analyze the reported March 2026 credential-stuffing incident.
7. Assess authentication, user access, and analytics export permissions.
8. Review privacy, data retention, deletion, and subprocessor arrangements.
9. Identify and rate inherent and residual vendor risks.
10. Define remediation actions, proposed owners, and evidence requirements.
11. Establish vendor monitoring and reassessment activities.
12. Prepare a structured renewal recommendation and executive decision memo.

## 4. Assessment Methodology

The assessment uses a risk-based approach informed by NIST publications.

| Stage | Activity | Deliverables |
|---|---|---|
| 1 | Understand the vendor relationship | Vendor relationship profile |
| 2 | Map business processes and information flows | Business process and data-flow analysis |
| 3 | Evaluate service criticality and dependency | Vendor criticality assessment |
| 4 | Examine customer and vendor access arrangements | Access and dependency analysis |
| 5 | Review supplied vendor evidence | Vendor evidence register |
| 6 | Evaluate vendor questionnaire responses | Security questionnaire review |
| 7 | Assess independent assurance and testing summaries | SOC 2 and penetration-test reviews |
| 8 | Evaluate reported security incidents | Security incident review |
| 9 | Review contractual and privacy safeguards | Contract and privacy review |
| 10 | Identify missing or insufficient evidence | Evidence gaps and validation |
| 11 | Assess risk scenarios and existing controls | Risk methodology, scenarios, and control assessment |
| 12 | Define remediation actions | Findings and remediation tracker |
| 13 | Establish ongoing oversight | Monitoring and reassessment plan |
| 14 | Evaluate renewal requirements | Renewal conditions and recommendation |
| 15 | Support management decision-making | Vendor decision memo |

The assessment distinguishes vendor statements, documentary evidence, independent assurance, Avenloft-owned controls, analyst judgments, evidence gaps, and proposed recommendations.

## 5. Key Risk Assessment Results

Three principal risk scenarios were assessed.

| Risk ID | Risk Scenario | Inherent Risk | Residual Risk | Proposed Target |
|---|---|---|---|---|
| TPRM-R01 | Customer-account compromise and unauthorized analytics export | High | Moderate | Low |
| TPRM-R02 | Cross-tenant exposure of Avenloft data | Moderate | Moderate | Moderate |
| TPRM-R03 | Excessive retention and incomplete data deletion | Moderate | Moderate | Low |

**Overall assessment:** All three scenarios currently have Moderate residual risk ratings under the qualitative matrix specified in the fictional case.

The main areas requiring management attention are:

- Customer authentication and export permissions.
- Formal access certification.
- Bulk-export penetration-test remediation evidence.
- Independent validation of tenant-isolation controls.
- Data-retention and deletion assurance.
- Contractual incident-notification and subprocessor provisions.

Proposed target ratings are not achieved ratings. They require appropriate treatment and supporting validation evidence.

## 6. Notable Assessment Observations

### 6.1 Authentication and Customer Access

- TOTP MFA is available but not mandatory on the Standard plan.
- Five of eight Avenloft accounts have TOTP enabled.
- Four users have analytics export permissions.
- No formal retained access-certification record was supplied.

### 6.2 Security Assurance and Vulnerability Management

- The supplied SOC 2 Type II summary identifies two of 25 sampled terminated workforce accounts disabled after 36 and 44 hours, compared with a 24-hour target.
- The vendor reports a July 2026 workflow change, but independent post-change testing was not supplied.
- The May 2026 penetration-test summary reports zero Critical or High findings, two Medium findings marked remediated, and one open Medium finding involving insufficient rate limiting on a bulk-export endpoint.
- Independent retest evidence and vulnerability-scan reports were not supplied.

### 6.3 Security Incident

The fictional vendor reported a credential-stuffing incident on March 14–15, 2026, affecting nine customer accounts across four organizations.

Two compromised accounts had export permissions and exported analytics data. Avenloft was not identified as affected.

The incident demonstrates the relevance of customer-account security and analytics export governance. The case does not establish that the open penetration-test finding caused this incident.

### 6.4 Data Retention and Deletion

- Standard plan retention is 180 days by default.
- Active deletion begins within 30 days after termination.
- Encrypted backups expire through a further 35-day backup lifecycle.
- No sample deletion certificate was supplied.

### 6.5 Contractual Safeguards

The contract includes confidentiality and reasonable-safeguard provisions. Further review is recommended for:

- Fixed incident-notification timelines.
- Subprocessor change notification.
- Ongoing security assurance obligations.
- Appropriate audit and verification rights.
- Data-retention and deletion commitments.

## 7. Repository Structure

```text
03-third-party-vendor-risk-assessment/
│
├── README.md
│
├── 01-relationship-understanding/
│   ├── vendor-relationship-profile.md
│   ├── business-process-and-data-flow.md
│   ├── vendor-criticality-assessment.md
│   └── access-and-dependency-analysis.md
│
├── 02-evidence-review/
│   ├── vendor-evidence-register.md
│   ├── security-questionnaire-review.md
│   ├── soc2-report-review.md
│   ├── penetration-test-review.md
│   ├── security-incident-review.md
│   ├── contract-and-privacy-review.md
│   └── evidence-gaps-and-validation.md
│
├── 03-vendor-risk-assessment/
│   ├── risk-assessment-methodology.md
│   ├── vendor-risk-scenarios.md
│   ├── current-controls-and-residual-risk.md
│   └── vendor-risk-assessment.xlsx
│
├── 04-findings-remediation/
│   ├── findings-remediation-tracker.md
│   ├── findings-remediation-tracker.xlsx
│   └── renewal-conditions.md
│
├── 05-vendor-decision/
│   ├── vendor-decision-memo.md
│   ├── renewal-recommendation.md
│   └── monitoring-and-reassessment-plan.md
│
└── 06-references/
    └── references.md
```

The original fictional case PDF is treated as local source material and is not included in the public repository.

## 8. Project Deliverables

### Relationship Understanding

Documents the vendor relationship, business purpose, information flows, service criticality, access arrangements, and business dependency.

### Evidence Review

Provides a structured review of vendor evidence, questionnaire responses, SOC 2 summary, penetration-test summary, security incident information, contract terms, privacy considerations, and evidence gaps.

### Vendor Risk Assessment

Contains the qualitative risk-assessment methodology, three risk scenarios, existing control evaluation, residual-risk justifications, and an Excel risk assessment workbook.

### Findings and Remediation

Contains the consolidated findings, recommended remediation actions, proposed ownership, evidence requirements, closure criteria, and a dedicated Excel remediation tracker.

### Vendor Decision and Renewal

Provides the executive decision memo, detailed renewal recommendation, renewal conditions, and monitoring and reassessment plan.

### References

Documents the official frameworks and publications, fictional case evidence, and internal assessment documents used in the project.

## 9. Excel Workbooks

### Vendor Risk Assessment

**File:** `03-vendor-risk-assessment/vendor-risk-assessment.xlsx`

The workbook includes:

- Executive dashboard.
- Formula-driven risk register.
- Inherent and residual risk ratings.
- Control assessment.
- Findings and treatment tracking.
- Evidence-gap register.
- Qualitative rating matrix.
- Framework references.

### Findings and Remediation Tracker

**File:** `04-findings-remediation/findings-remediation-tracker.xlsx`

This is a separate operational workbook intended for tracking:

- Findings and remediation actions.
- Proposed action owners.
- Priority and status.
- Agreed due dates.
- Evidence received.
- Validation results.
- Closure decisions.
- Outstanding actions.

The two Excel workbooks serve different purposes: one focuses on risk assessment, while the other focuses on remediation execution and follow-up.

## 10. Recommended Vendor Decision

The assessment recommends **conditional continuation only**, subject to authorized management approval and appropriate security, privacy, contractual, and governance conditions.

Before an unconditional renewal or new long-term commitment, Avenloft should:

1. Confirm the current contract and service status.
2. Verify remediation and retesting of the bulk-export rate-limiting finding.
3. Require stronger authentication for Avenloft users.
4. Review export permissions and formalize access certification.
5. Obtain appropriate tenant-isolation validation.
6. Agree on documented retention, deletion, and backup-expiration requirements.
7. Review incident-notification and subprocessor provisions.
8. Document formal management acceptance or treatment of the remaining residual risks.

Salesforce reporting remains an alternative. The case estimates that switching would require several weeks of manual effort.

The supplied case does not confirm whether the November 1, 2026 renewal occurred. No renewal, approval, remediation completion, or management risk acceptance is assumed.

## 11. Framework References

The assessment is informed by the following publications:

| Framework / Publication | Application |
|---|---|
| NIST Cybersecurity Framework 2.0 | Cybersecurity governance and supply-chain risk management, particularly GV.SC |
| NIST SP 800-30 Rev. 1 | Qualitative information-security risk assessment |
| NIST SP 1305 | Applying CSF 2.0 to cybersecurity supply-chain risk management |
| NIST SP 1326 | Cybersecurity supply-chain due diligence |
| NIST SP 800-161 Rev. 1, Update 1 | Cybersecurity supply-chain risk-management practices |

Detailed source information and official publication links are available in [`06-references/references.md`](06-references/references.md).

## 12. Skills Demonstrated

This project demonstrates practical work in:

- Third-Party Risk Management (TPRM).
- Vendor due diligence and security assessments.
- GRC documentation and risk registers.
- Qualitative cybersecurity risk assessment.
- NIST framework application.
- Security questionnaire review.
- SOC 2 report-summary analysis.
- Penetration-test evidence review.
- Security incident analysis.
- Identity and access management assessment.
- Data-flow and information-exposure analysis.
- Privacy and data-retention review.
- Contractual security and supplier governance.
- Remediation planning and evidence validation.
- Vendor renewal and risk-decision support.
- Ongoing monitoring and reassessment planning.
- Executive risk communication.

## 13. Limitations and Disclaimer

This is a fictional portfolio and learning project based on a supplied training case.

It is not:

- A real vendor assessment.
- An independent security audit.
- A SOC 2 examination.
- A penetration test.
- A legal opinion or formal privacy compliance determination.
- An approved vendor renewal decision.
- Evidence of actual control implementation or management approval.

Risk ratings are qualitative analyst judgments based on the fictional evidence and the case-specific assessment matrix.

The project distinguishes documented case facts from analyst judgments, evidence gaps, and proposed recommendations.

---

**Project ID:** GRC-TPRM-003  
**Project:** Third-Party Vendor Risk Assessment  
**Portfolio Area:** Governance, Risk & Compliance (GRC)  
**Assessment Status:** Portfolio case study; management decision and remediation outcomes remain unverified in the supplied case evidence.