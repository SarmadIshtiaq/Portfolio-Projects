# Findings and Remediation Tracker

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Assessment:** Third-Party Vendor Risk Assessment  
**Assessment Basis:** Fictional Avenloft Third-Party Risk Review Case

---

## 1. Purpose

This tracker records the security, privacy, operational, and contractual findings identified during the assessment of CobaltCedar Analytics and its SupportLens service.

It provides a structured way to:

- Record identified findings and associated risks.
- Assign proposed remediation ownership.
- Define remediation and validation requirements.
- Track evidence needed to demonstrate completion.
- Distinguish vendor remediation from Avenloft-owned actions.
- Support risk reassessment and vendor governance decisions.

The findings and actions in this document are based on the fictional case packet. Proposed owners, priorities, and actions are analyst recommendations, not confirmed assignments or vendor commitments.

## 2. Status Definitions

| Status | Meaning |
|---|---|
| Open — Proposed | An action has been recommended but no implementation or completion evidence is recorded. |
| In Progress | The responsible party has confirmed that work is underway and supporting information is available. |
| Pending Evidence | Remediation is reported or believed to be completed, but supporting evidence has not yet been validated. |
| Pending Validation | Evidence has been received and requires review or independent validation. |
| Closed — Validated | The action has been completed and sufficient evidence has been reviewed and accepted. |
| Risk Accepted | An authorized decision-maker has formally accepted the remaining risk. This does not mean the underlying control weakness has been remediated. |

**Initial tracker rule:** Unless the supplied case packet provides evidence of verified completion, actions are recorded as `Open — Proposed` or `Pending Evidence`. No action is marked `Closed — Validated` by assumption.

## 3. Priority Definitions

| Priority | Interpretation |
|---|---|
| High | Addresses a material weakness or exposure that warrants prompt attention and management oversight. |
| Medium | Addresses an important control or assurance gap requiring documented remediation. |
| Low | Improves governance, documentation, or routine monitoring where the immediate exposure is comparatively limited. |

Priorities are proposed assessment judgments. They should be confirmed by the responsible Avenloft stakeholders.

---

## 4. Consolidated Findings Register

| Finding ID | Finding | Related Risk | Priority | Proposed Owner |
|---|---|---|---|---|
| TPRM-F01 | Customer MFA is optional on the Standard plan and enrollment is incomplete. | TPRM-R01 | High | Marcus Holloway / CobaltCedar |
| TPRM-F02 | Analytics export permissions require stronger governance and periodic review. | TPRM-R01 | High | Lena Ortiz / Marcus Holloway |
| TPRM-F03 | Formal retained customer access certification is not evidenced. | TPRM-R01 | Medium | Aaron Bell / Lena Ortiz |
| TPRM-F04 | Bulk-export rate-limiting finding requires remediation-status confirmation and retesting evidence. | TPRM-R01 | High | CobaltCedar / Aaron Bell |
| TPRM-F05 | Vendor vulnerability scanning evidence was not supplied. | TPRM-R01 / R02 | Medium | CobaltCedar |
| TPRM-F06 | Independent evidence specifically validating logical tenant isolation was not supplied. | TPRM-R02 | High | CobaltCedar / Aaron Bell |
| TPRM-F07 | Cross-tenant authorization testing should be evidenced. | TPRM-R02 | Medium | CobaltCedar |
| TPRM-F08 | Data minimization and exported-field scope need documented periodic review. | TPRM-R01 / R02 | Medium | Lena Ortiz / Marcus Holloway |
| TPRM-F09 | Standard plan retention is 180 days by default and requires suitability review. | TPRM-R03 | Medium | Hannah Kim / Lena Ortiz |
| TPRM-F10 | Data deletion and backup-expiration requirements need clearer documented agreement. | TPRM-R03 | Medium | Hannah Kim / CobaltCedar |
| TPRM-F11 | No sample deletion certificate or equivalent deletion evidence was supplied. | TPRM-R03 | Medium | Aaron Bell / CobaltCedar |
| TPRM-F12 | Subprocessor list and change-notification arrangements require review. | TPRM-R03 | Medium | Hannah Kim / Noah Grant |
| TPRM-F13 | Contractual incident-notification wording does not specify a fixed hour-based deadline. | TPRM-R01 | High | Hannah Kim / Noah Grant |
| TPRM-F14 | Contract does not contain an explicit SOC 2 maintenance clause or on-site audit right. | Cross-cutting | Medium | Hannah Kim / Noah Grant |
| TPRM-F15 | Updated vendor security assurance and remediation evidence should be maintained before continued-use decisions. | Cross-cutting | Medium | Aaron Bell / CobaltCedar |

---

## 5. Detailed Remediation Action Tracker

### 5.1 TPRM-R01 — Customer Account Compromise and Unauthorized Export

| Action ID | Related Finding | Remediation Action | Proposed Owner | Required Evidence | Proposed Priority |
|---|---|---|---|---|---|
| R01-A1 | TPRM-F01 | Require MFA for all active Avenloft SupportLens accounts or agree on an authentication arrangement that enforces MFA. | Marcus Holloway / CobaltCedar | Configuration evidence and confirmation of MFA enrollment for all active users. | High |
| R01-A2 | TPRM-F02 | Review analytics export permissions and restrict them to users with an approved business need. | Lena Ortiz / Marcus Holloway | Approved export-permission list and platform configuration evidence. | High |
| R01-A3 | TPRM-F03 | Establish a documented periodic user access-certification process, including approval and removal of unnecessary access. | Aaron Bell / Lena Ortiz | Dated access review records, approved user list, and review procedure. | Medium |
| R01-A4 | TPRM-F04 | Obtain the current remediation status for the bulk-export rate-limiting finding and request appropriate retesting evidence. | CobaltCedar / Aaron Bell | Updated penetration-test finding, remediation record, and independent retest evidence where available. | High |
| R01-A5 | TPRM-F05 | Obtain vulnerability-scanning evidence and clarify remediation tracking for identified vulnerabilities. | CobaltCedar | Relevant external and authenticated scan reports, findings summary, and remediation records. | Medium |

### 5.2 TPRM-R02 — Cross-Tenant Exposure of Avenloft Data

| Action ID | Related Finding | Remediation Action | Proposed Owner | Required Evidence | Proposed Priority |
|---|---|---|---|---|---|
| R02-A1 | TPRM-F06 | Obtain documentation explaining the SupportLens tenant-isolation architecture and authorization boundaries. | CobaltCedar / Aaron Bell | Current architecture documentation and tenant-access-control description. | High |
| R02-A2 | TPRM-F07 | Request evidence of technical testing covering cross-tenant access restrictions. | CobaltCedar | Relevant test results, penetration-test coverage, or independent validation evidence. | Medium |
| R02-A3 | TPRM-F06 | Confirm that customer-specific authorization is enforced across dashboards, APIs, reporting, and analytics exports. | CobaltCedar | Technical validation results or suitable independent assurance evidence. | High |
| R02-A4 | TPRM-F08 | Review and minimize the information included in weekly Salesforce CSV exports. | Lena Ortiz / Marcus Holloway | Approved export-field inventory and documented data-minimization review. | Medium |

### 5.3 TPRM-R03 — Excessive Retention and Incomplete Deletion

| Action ID | Related Finding | Remediation Action | Proposed Owner | Required Evidence | Proposed Priority |
|---|---|---|---|---|---|
| R03-A1 | TPRM-F09 | Assess whether the 180-day Standard plan retention period is appropriate for Avenloft's business and privacy requirements. | Hannah Kim / Lena Ortiz | Documented retention assessment and approved requirement. | Medium |
| R03-A2 | TPRM-F10 | Agree on a documented retention and deletion schedule covering active records, analytics outputs, and backups. | Hannah Kim / CobaltCedar | Written vendor commitment or updated contractual provision. | Medium |
| R03-A3 | TPRM-F11 | Obtain a sample deletion certificate or equivalent evidence explaining how data deletion is confirmed. | Aaron Bell / CobaltCedar | Sample deletion confirmation and documented deletion process. | Medium |
| R03-A4 | TPRM-F12 | Obtain an updated subprocessor list and clarify the notification process for subprocessor changes. | Hannah Kim / Noah Grant | Current subprocessor register and written change-notification process. | Medium |

### 5.4 Cross-Cutting Contract and Governance Actions

| Action ID | Related Finding | Remediation Action | Proposed Owner | Required Evidence | Proposed Priority |
|---|---|---|---|---|---|
| GOV-A1 | TPRM-F13 | Review and negotiate clearer contractual incident-notification timing and escalation requirements. | Hannah Kim / Noah Grant | Legal-reviewed contractual wording or an approved amendment. | High |
| GOV-A2 | TPRM-F14 / F15 | Define ongoing security-assurance requirements, including periodic security documentation, assurance-report review, and appropriate audit or independent-assessment provisions. | Aaron Bell / Hannah Kim / Noah Grant | Approved vendor-assurance requirements and agreed contractual or governance documentation. | Medium |

**Tracker count note:** This section contains 15 remediation actions: five for TPRM-R01, four for TPRM-R02, four for TPRM-R03, and two cross-cutting governance actions.

---

## 6. Remediation Tracking Fields

The following fields should be maintained for every action during actual remediation tracking.

| Field | Description |
|---|---|
| Action ID | Unique action reference. |
| Finding ID | Related finding reference. |
| Responsible Party | Vendor or Avenloft stakeholder responsible for the action. |
| Accountable Approver | Person or function responsible for approving the outcome. |
| Priority | High, Medium, or Low. |
| Agreed Due Date | Date formally agreed by the responsible party. |
| Current Status | Current remediation status using the definitions in Section 2. |
| Evidence Received | Name or reference of evidence received. |
| Evidence Review Date | Date evidence was reviewed. |
| Validation Result | Accepted, rejected, or further evidence required. |
| Closure Date | Date the action is formally closed, if validated. |
| Residual Risk Impact | Whether the action changes likelihood, impact, or both. |
| Reviewer Notes | Explanation of the review outcome or remaining limitations. |

No due dates are assumed in this case-study tracker. Due dates should be agreed and recorded by the responsible parties during remediation planning.

## 7. Evidence Validation and Closure Criteria

An action should not be marked `Closed — Validated` solely because a vendor states that remediation is complete.

The reviewer should confirm:

1. The evidence relates to the correct vendor, service, control, and finding.
2. The evidence is current and sufficiently detailed.
3. The evidence demonstrates that the agreed remediation was implemented.
4. Any required test or retest has been completed.
5. Exceptions or limitations are documented.
6. The relevant risk scenario has been reassessed if the control change affects likelihood or impact.
7. The closure decision and reviewer are recorded.

### Example: MFA Remediation

**Action:** R01-A1 — Require MFA for all Avenloft SupportLens accounts.

**Insufficient closure evidence:**
- Vendor email stating that MFA is available.
- Screenshot showing an MFA feature without proof of enrollment.
- General statement that MFA is encouraged.

**More appropriate closure evidence:**
- Current account list.
- Authentication configuration showing the requirement.
- Evidence that all active Avenloft users are enrolled.
- Confirmation that exceptions are documented and approved.

### Example: Penetration-Test Remediation

**Action:** R01-A4 — Validate bulk-export rate-limiting remediation.

**Insufficient closure evidence:**
- Vendor statement that the finding has been fixed.
- A proposed remediation date without a completion record.

**More appropriate closure evidence:**
- Updated finding status.
- Description of the implemented fix.
- Relevant retest results.
- Evidence showing that the original issue no longer exists, subject to test scope and limitations.

### Example: Data Deletion

**Action:** R03-A3 — Obtain deletion confirmation evidence.

**Insufficient closure evidence:**
- General statement that data is deleted after termination.

**More appropriate closure evidence:**
- Documented deletion procedure.
- Example deletion certificate or equivalent confirmation.
- Explanation of active-storage and backup deletion timelines.
- Documented treatment of any deletion exceptions.

## 8. Timeline and Unverified Historical Commitments

The supplied case identifies two significant dates:

| Date | Case Event | Assessment Treatment |
|---|---|---|
| October 30, 2026 | Target date for remediation of the open Medium bulk-export rate-limiting finding. | The supplied packet does not establish whether remediation or independent retesting was completed. |
| November 1, 2026 | Contract renewal date. | The supplied packet does not confirm whether the contract was renewed, amended, or allowed to expire. |

Both dates have passed as of November 27, 2026.

The tracker therefore does not treat either event as completed. The responsible stakeholders would need to obtain current confirmation and supporting documentation.

No new deadlines are invented in this tracker. Any revised deadlines should be formally agreed and recorded.

## 9. Escalation and Governance

The following escalation approach is recommended:

| Situation | Recommended Escalation |
|---|---|
| High-priority action remains unaddressed | Escalate to the CISO and relevant business owner for review. |
| Vendor does not provide required evidence | Record the evidence gap and reassess the associated residual risk. |
| Remediation deadline is missed | Request an updated plan, document the reason, and escalate according to risk severity. |
| Evidence does not demonstrate successful remediation | Keep the action open or pending validation. |
| Residual risk remains above organizational appetite | Obtain a formal risk decision from an authorized management representative. |
| Material security incident or new control failure occurs | Reassess relevant risk scenarios and consider whether continued use remains appropriate. |

Risk acceptance is separate from remediation closure. An authorized management decision may accept a residual risk, but the underlying finding must remain visible in the record unless it has actually been remediated and validated.

## 10. Management Reporting

A periodic remediation report should summarize:

- Total number of open findings.
- Number of High, Medium, and Low priority findings.
- Actions completed and independently validated.
- Actions awaiting evidence or validation.
- Overdue actions, based on agreed due dates.
- Findings with rejected or insufficient evidence.
- Residual risks requiring management attention.
- Risks formally accepted by authorized management.

For the accompanying Excel workbook, the Treatment Tracker worksheet should be used as the operational action-tracking view. This Markdown document provides the narrative findings, ownership rationale, and closure criteria.

## 11. Overall Conclusion

The assessment identified issues requiring attention across customer authentication, access governance, vulnerability management, tenant isolation, data retention, deletion assurance, and contractual safeguards.

The most immediate priorities are:

1. Confirm the current status and validation evidence for the bulk-export rate-limiting finding.
2. Require stronger authentication and review export permissions for Avenloft users.
3. Obtain appropriate evidence of tenant-isolation controls.
4. Agree on documented retention and deletion requirements.
5. Strengthen contractual incident-notification and vendor-assurance provisions.

The three assessed risk scenarios currently retain Moderate residual risk ratings. Recommended actions should be tracked until implementation and evidence validation are complete.

No remediation, contract renewal, or formal risk acceptance is assumed to have occurred unless supported by additional evidence.

**Assessment limitation:** This is a fictional third-party risk assessment exercise based on the supplied case packet. It is not a real vendor remediation plan, audit report, or record of actual management approvals.