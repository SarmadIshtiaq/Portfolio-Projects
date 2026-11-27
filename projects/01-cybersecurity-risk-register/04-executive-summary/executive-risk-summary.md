# Avenloft Systems Group
# Executive Cybersecurity Risk Summary

**Project ID:** GRC-RISK-001  
**Assessment Period:** FY2027  
**Prepared For:** Executive Leadership and Security Steering Committee  
**Prepared By:** Junior GRC Analyst — Independent Portfolio Simulation  
**Assessment Status:** Draft — Provisional Analyst Assessment

## 1. Executive Assessment

The assessment identifies ten candidate cybersecurity risk scenarios affecting Avenloft's service reliability, customer information, privileged access, workforce security, third-party relationships, and technology governance.

The provisional assessment identifies **six Moderate and four Low residual risks**. No risk is currently rated High or Very High. However, several Moderate risks require management attention because they conflict with stated risk tolerances or involve important control and evidence gaps.

The most immediate concerns are the overdue critical Partner Portal vulnerability, unverified production recovery capability, insufficient third-party security assessment, uncontrolled local copies of support attachments, and delayed contractor access removal.

The assessment uses the qualitative likelihood-and-impact matrix in [NIST SP 800-30 Rev. 1, Appendix I, Table I-2](https://csrc.nist.gov/pubs/sp/800/30/r1/final), as specified in the [Avenloft case packet](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11).

All ratings and priorities remain provisional and require validation and management review.

## 2. Top-Five Residual Risks

| Priority | Risk ID | Risk | Residual Level | Management Concern |
|---:|---|---|---|---|
| 1 | R-002 | Partner Portal Vulnerability Exploitation | Moderate | Critical internet-facing vulnerability remains open for 32 days and its formal exception has expired. |
| 2 | R-001 | Production Recovery and Incident Readiness | Moderate | Current-environment recovery capability has not been demonstrated through a recent full restore exercise. |
| 3 | R-005 | Third-Party Access to Customer Support Data | Moderate | Vendor receives periodic ticket exports without a documented security assessment. |
| 4 | R-008 | Customer-Support Attachments on Local Devices | Moderate | Local customer-data copies are created without a verified deletion process. |
| 5 | R-003 | Contractor Access After Contract End | Moderate | Three contractor accounts remained active after contract end dates. |

The priority order represents proposed management attention, not a separate numerical risk score.

## 3. Immediate Management Actions

| Action | Recommended Management Response | Proposed Accountability |
|---|---|---|
| Critical vulnerability | Prioritise permanent remediation, validate WAF protection, and resolve the expired exception. | Priya Nair — VP Engineering |
| Recovery capability | Fund and schedule a full application-and-database restore test and an updated incident exercise. | Priya Nair — VP Engineering |
| Third-party oversight | Complete the vendor security assessment and confirm the customer-data scope and handling arrangements. | Lena Ortiz — VP Customer Success; Noah Grant — Procurement |
| Customer attachments | Establish approved local storage, retention, and deletion-verification procedures. | Lena Ortiz — VP Customer Success |
| Contractor access | Establish reliable contractor offboarding and periodic access reconciliation. | Priya Nair — VP Engineering, with IT and People Operations |

These are proposed management actions, not completed remediation activities.

## 4. Important Uncertainties Requiring Validation

Before final approval of the risk register, management and control owners should confirm:

- Whether the WAF mitigation adequately protects the Partner Portal until permanent patching is completed.
- Whether a full restore can meet the four-hour production availability tolerance.
- What customer information is included in vendor ticket exports and which security controls the vendor operates.
- Whether customer-support attachments are stored only on managed devices and deleted after case closure.
- Whether contractor access removal is consistently completed across engineering systems.
- Whether Salesforce and GitHub are formally classified as high-value systems under the 180-day logging standard.

**Additional watch item:** R-007, SaaS Administrative Log Retention, has a provisional Moderate residual rating. Its priority should be reconsidered after confirming whether Salesforce and GitHub are classified as high-value systems. [Case evidence: OBS-07](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

## 5. Management Decisions Requested

The Security Steering Committee and relevant executives should:

1. Confirm ownership and remediation commitments for the five prioritised risks.
2. Require CISO review of the critical Partner Portal exposure and its expired exception.
3. Approve resources for current-environment recovery testing.
4. Require formal security due diligence for vendors handling customer information.
5. Require evidence of contractor access removal and customer-attachment handling controls.
6. Confirm the system classification and logging-retention requirements for Salesforce and GitHub.

## 6. Overall Management Message

Avenloft has several useful safeguards, including protected backups, workforce MFA, endpoint protection, access restrictions, and native audit logging. However, the existence of a safeguard does not prove that it adequately reduces the relevant business risk.

Management attention should focus on closing known exposure gaps, demonstrating that important controls work in the current environment, assigning clear accountability, and validating the information that could materially change the risk assessment.

**Assessment limitation:** This is an independent assessment of a fictional training case. Ratings are provisional analyst judgements, not findings approved by Avenloft management. No actual incident, compromise, client engagement, or remediation outcome is claimed.