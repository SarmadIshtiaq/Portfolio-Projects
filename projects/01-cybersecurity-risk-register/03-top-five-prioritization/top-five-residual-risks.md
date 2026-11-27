# Avenloft Systems Group — Top-Five Residual-Risk Prioritization

**Project ID:** GRC-RISK-001  
**Document:** Management Risk Prioritization  
**Organisation:** Avenloft Systems Group (Fictional)  
**Assessment:** FY2027 Cybersecurity Risk Register  
**Assessment Basis:** Provisional residual-risk assessment  
**Status:** Proposed prioritization; management review pending

## 1. Purpose

This document identifies five residual risks that should receive priority management attention.

The selection is based on the evidence in the Avenloft case packet and the provisional risk assessments documented in:

- `01-case-analysis/risk-scenario-analysis.md`
- `01-case-analysis/risk-assessment-workings.md`
- `02-risk-register/cybersecurity-risk-register.xlsx`

The objective is not simply to select the risks with the highest qualitative labels. Several risks have the same residual rating. The analyst must explain why some risks need attention before others.

**Primary source:** [Avenloft Cybersecurity Risk Register Case Packet — GRC-RISK-001](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf).

## 2. Prioritization Method

The top-five selection considers the following factors.

| Selection Factor | How It Is Used |
|---|---|
| Residual Risk Level | Provides the starting point for comparing the risks that remain after existing controls. |
| Risk Appetite and Tolerance | Identifies risks that conflict with leadership's stated tolerance. |
| Current Exposure | Considers whether the condition remains open or whether an issue has already been contained. |
| Business Consequence | Considers potential effects on customer trust, service reliability, data confidentiality, and business objectives. |
| Existing Safeguards | Considers whether current controls reduce exposure or whether evidence of effectiveness is missing. |
| Evidence and Uncertainty | Considers how strongly the case evidence supports the scenario and what information remains unknown. |
| Management Action | Considers whether a decision, escalation, resource allocation, or remediation commitment is needed. |

**Source:** [Case Packet — Quality Bar for the Analyst, page 13](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=13).

### Important scoring limitation

This prioritization does not introduce another numerical score or ranking formula.

The qualitative residual-risk rating remains the rating calculated through Avenloft's NIST SP 800-30 Rev. 1 matrix.

The priority number below is a management-attention order. It is not a new NIST risk level.

**Source:** [Case Packet — Risk Determination Matrix, page 11](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11).

## 3. Executive Priority Summary

| Priority | Risk ID | Risk Title | Provisional Residual Level | Main Reason for Attention |
|---:|---|---|---|---|
| 1 | R-002 | Partner Portal Vulnerability Exploitation | Moderate | Critical internet-facing vulnerability remains open beyond the stated 30-day tolerance and its exception has expired. |
| 2 | R-001 | Production Recovery and Incident Readiness | Moderate | Recovery capability has not been demonstrated through a recent full restore and current-environment exercise. |
| 3 | R-005 | Third-Party Access to Customer Support Data | Moderate | Customer-ticket exports are sent to a vendor without a documented security assessment or confirmed data scope. |
| 4 | R-008 | Customer-Support Attachments on Local Devices | Moderate | Local copies of customer attachments are created regularly without a verified deletion process. |
| 5 | R-003 | Contractor Access After Contract End | Moderate | Three contractor accounts remained active after contract end dates, showing a recurring offboarding process weakness. |

All five ratings are provisional analyst assessments. They have not been approved by Avenloft management.

---

## 4. Priority 1 — R-002: Partner Portal Vulnerability Exploitation

**Residual risk level:** Moderate  
**Supporting evidence:** OBS-02  
**Proposed risk owner:** Priya Nair, VP Engineering  
**Escalation:** CISO review

### Why this risk is first

The case identifies a critical vulnerability with a CVSS score of 9.1 on the internet-facing Partner Portal.

The vulnerability remained open for 32 days. A WAF rule was added as temporary mitigation, but the permanent patch was delayed because regression testing caused partner-session failures. The formal risk exception expired five days before the case observation and had not been renewed.

Avenloft's leadership states that known critical internet-facing vulnerabilities are not accepted beyond 30 days without a current written exception and compensating controls.

The observed condition therefore conflicts directly with the stated tolerance.

Sources: [OBS-02 — Vulnerability Remediation Tracker, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6) and [Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

### Existing safeguards

- Weekly vulnerability scanning.
- Temporary WAF mitigation.
- Engineering regression testing.

### Main uncertainty

The case does not identify the vulnerability by CVE, provide the complete attack path, or demonstrate the effectiveness of the WAF rule. It also does not report successful exploitation.

### Recommended management actions

1. Require Engineering to complete permanent remediation.
2. Obtain evidence that the WAF mitigation addresses the relevant attack path.
3. Review and formally resolve the expired exception.
4. Assign a remediation owner and documented target date.
5. Require CISO review of the current exposure and treatment plan.

### Management decision required

Confirm that permanent remediation is prioritised and that the expired exception is not treated as continuing approval.

---

## 5. Priority 2 — R-001: Production Recovery and Incident Readiness

**Residual risk level:** Moderate  
**Supporting evidence:** OBS-01 and OBS-09  
**Proposed risk owner:** Priya Nair, VP Engineering  
**Relevant executive stakeholder:** Elena Ruiz, VP Finance & Operations

### Why this risk is second

Avenloft provides a customer-facing SaaS service. Leadership has low tolerance for production outages exceeding four hours during business operations.

The last documented full application-and-database restore exercise occurred 14 months before the case review. The recovery runbook still refers to the pre-migration network layout. The last ransomware tabletop exercise occurred 22 months before the review and did not test the final AWS environment or loss of the primary identity provider.

The company has backups and an incident-response plan, but the case does not demonstrate current end-to-end recovery capability.

Sources: [OBS-01 — Recovery Testing, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6), [OBS-09 — Incident Response Exercise, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8), and [Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

### Existing safeguards

- Daily production backups.
- Protected backup copies.
- Backup-job monitoring.
- Incident-response plan.
- Current incident contact information.
- Executive escalation tree.

### Main uncertainty

The case does not provide a recent successful full restore result or evidence that the current environment can meet the four-hour business tolerance.

### Recommended management actions

1. Conduct a full application-and-database restore exercise.
2. Update recovery procedures to reflect the current AWS architecture.
3. Test ransomware response and identity-provider loss scenarios.
4. Document recovery results, actual restoration times, and unresolved dependencies.
5. Review whether recovery objectives and responsibilities remain appropriate.

### Management decision required

Assign resources for an end-to-end recovery test and require the results to be reviewed by the relevant business and technology owners.

---

## 6. Priority 3 — R-005: Third-Party Access to Customer Support Data

**Residual risk level:** Moderate  
**Supporting evidence:** OBS-05  
**Proposed risk owner:** Lena Ortiz, VP Customer Success  
**Supporting function:** Noah Grant, Director Procurement

### Why this risk is third

A customer-support analytics vendor receives periodic ticket exports.

The procurement process requires security review above a spending threshold, but data sensitivity is not a mandatory vendor-classification field. This vendor received no formal security review because its annual spend fell below the threshold.

The case reports no security questionnaire, architecture review, or formal vendor risk rating.

A confidentiality clause exists, but the case does not provide evidence of the vendor's technical and operational security controls.

Source: [OBS-05 — Procurement Process Review, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

### Existing safeguards

- Contractual confidentiality language.
- Procurement security review for vendors above the existing spend threshold.

### Main uncertainty

The exact data fields in the ticket exports are not supplied. The vendor's processing locations, access controls, retention, deletion, and independent assurance evidence are also not documented in the case.

### Recommended management actions

1. Identify exactly what information is sent in the ticket exports.
2. Perform a vendor security assessment.
3. Review the vendor's security architecture and access controls.
4. Confirm storage, processing, retention, deletion, and subcontractor arrangements.
5. Add data sensitivity and service criticality to vendor classification.
6. Review whether the existing contract provides sufficient security and incident-notification commitments.

### Management decision required

Require a documented security assessment of the vendor relationship and review the procurement classification process so low spend does not automatically exclude vendors that handle sensitive information.

---

## 7. Priority 4 — R-008: Customer-Support Attachments on Local Devices

**Residual risk level:** Moderate  
**Supporting evidence:** OBS-08  
**Proposed risk owner:** Lena Ortiz, VP Customer Success

### Why this risk is fourth

Support agents sometimes download customer-ticket attachments to local laptops to reproduce product issues. The case reports approximately 18 such downloads in a typical month.

Managed laptops have disk encryption and EDR. However, there is no DLP rule preventing local copies or requiring deletion after case closure. Customer Success also does not have a reliable process for proving that local copies have been deleted.

This creates a continuing data-handling concern even though endpoint safeguards exist.

Sources: [OBS-08 — Customer Success Interview, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7) and [Customer Success Stakeholder Note, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

### Existing safeguards

- Role-based access to customer-support tickets.
- Disk encryption on managed laptops.
- Endpoint detection and response.
- Review of unusual export volumes when alerted.

### Main uncertainty

The case does not identify the exact content of every attachment, confirm that all downloads occur on managed devices, or provide evidence of local-copy deletion.

### Recommended management actions

1. Define approved handling procedures for customer attachments.
2. Identify where support files may be stored.
3. Define when local copies must be deleted.
4. Introduce a process to verify deletion after case closure.
5. Evaluate whether DLP or other controls are required.
6. Review download activity and unusual file-handling patterns.

### Management decision required

Require Customer Success to document and implement a controlled attachment-handling and deletion process.

---

## 8. Priority 5 — R-003: Contractor Access After Contract End

**Residual risk level:** Moderate  
**Supporting evidence:** OBS-03  
**Proposed risk owner:** Priya Nair, VP Engineering  
**Supporting functions:** Marcus Holloway, Director IT & Workplace Technology, and People Operations

### Why this risk is fifth

The access review identified three engineering contractors whose GitHub access remained active after contract end dates for 4, 6, and 9 days.

All three identified accounts are now disabled, and no unauthorised activity was found in the sampled logs. However, employee departures are automatically handled through Workday and Okta, while contractor offboarding depends on the engineering sponsor submitting a ticket.

The observed access delays indicate that the contractor process needs improvement.

Source: [OBS-03 — Quarterly Access Review, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

### Existing safeguards

- Employee offboarding is automated through Workday and Okta.
- GitHub uses SSO for workforce identities.
- The three identified contractor accounts have been disabled.

### Main uncertainty

The case does not provide a complete contractor population, a complete review of all contractor-accessible systems, or an automated contractor deprovisioning process.

### Recommended management actions

1. Define contractor access end dates in an accountable process.
2. Require timely sponsor notification when a contract ends.
3. Implement tracked or automated contractor access removal.
4. Reconcile contractor records against GitHub access.
5. Review contractor access across other engineering systems.

### Management decision required

Assign clear accountability for contractor offboarding and require periodic evidence that access is removed when contracts end.

---

## 9. Risks Not Selected in the Top Five

Not selecting a risk does not mean that it is unimportant or accepted. The remaining risks continue to require appropriate ownership, monitoring, treatment, or validation.

| Risk ID | Risk Title | Provisional Residual Level | Why It Is Not in the Initial Top Five |
|---|---|---|---|
| R-004 | Legacy Privileged Access and Administrator Accountability | Low | VPN restriction, limited authorised administrators, and controlled vault access reduce exposure. The weak-authentication and attribution concerns still require treatment because leadership has low tolerance for them. |
| R-006 | Phishing and Workforce Account Compromise | Low | Email filtering, endpoint protection, and workforce SSO/MFA reduce likelihood. Repeat training failures still require attention. |
| R-007 | SaaS Administrative Log Retention | Moderate | The applicability of the 180-day standard depends on whether Salesforce and GitHub are classified as high-value systems. This classification must be confirmed promptly. |
| R-009 | Unassigned Ownership of Engineering Build Servers | Low | The servers are reported as non-production and patched through the standard image pipeline. Ownership must still be assigned and verified. |
| R-010 | Unmanaged Consumer Generative-AI Use | Low | Leadership has instructed employees not to submit customer-confidential information to unapproved tools, and the proposed Customer Success pilot is paused. Actual usage and data submission still require validation. |

Sources: [OBS-04 and OBS-06, page 6–7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6), [OBS-07 and OBS-08, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7), and [OBS-09–OBS-12, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

### Specific watch item — R-007

R-007 deserves prompt validation.

Avenloft's logging standard specifies 180 days of searchable administrative logs for high-value systems, while Salesforce and GitHub detailed exports are retained for 30 days.

The case does not confirm whether these two systems are formally classified as high-value. If they are, the risk may warrant inclusion in the top five following reassessment.

[Source: OBS-07 — Logging Standard Review, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

## 10. Immediate Management Action Summary

| Action ID | Management Action | Related Risk | Proposed Accountability |
|---|---|---|---|
| MA-01 | Resolve the critical Partner Portal vulnerability and expired exception. | R-002 | Priya Nair; CISO review |
| MA-02 | Validate recovery capability through a current full restore and response exercise. | R-001 | Priya Nair |
| MA-03 | Complete the customer-support analytics vendor security assessment. | R-005 | Lena Ortiz and Noah Grant |
| MA-04 | Establish a controlled customer-attachment download and deletion process. | R-008 | Lena Ortiz |
| MA-05 | Establish reliable contractor offboarding and access reconciliation. | R-003 | Priya Nair, with IT and People Operations |

These are proposed actions, not completed remediation activities.

## 11. Important Management Decisions

The following decisions should be recorded by the relevant Avenloft authorities:

1. Confirm priority remediation and CISO oversight for R-002.
2. Assign resources and an accountable executive for recovery testing under R-001.
3. Require vendor due diligence for the customer-support analytics relationship under R-005.
4. Approve a controlled customer-attachment handling process under R-008.
5. Confirm accountability for contractor offboarding under R-003.
6. Confirm Salesforce and GitHub asset classification to determine the applicability of the 180-day logging standard under R-007.

## 12. Prioritization Limitations

This prioritization has the following limitations:

- The risk ratings are provisional analyst assessments, not management-approved ratings.
- The case packet does not provide measured event probabilities for the scenarios.
- Several conclusions depend on evidence that requires validation.
- The top-five order is a management-attention recommendation, not a new numerical risk score.
- A risk outside the top five remains in the full risk register and retains its treatment requirements.
- Risk appetite conflicts may require attention even when the residual matrix rating is Low or Moderate.

**Source:** [Case Packet — Facts You Should Not Assume and Quality Bar for the Analyst, pages 9 and 13](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

## 13. Document Status

| Activity | Status |
|---|---|
| Ten candidate risks reviewed | Complete |
| Provisional residual ratings considered | Complete |
| Top-five risks selected | Proposed |
| Priority order justified | Proposed |
| Management actions documented | Proposed |
| Risk owner confirmation | Pending |
| Material unknowns documented | Complete |
| Management approval | Not started |

**Document status:** Proposed management prioritization.

This document is part of an independent portfolio simulation. Avenloft Systems Group and all case events are fictional. No real management approval or remediation is claimed.