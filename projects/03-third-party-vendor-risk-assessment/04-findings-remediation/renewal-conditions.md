# Vendor Renewal and Continued-Use Conditions

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Organization:** Avenloft Systems Group  
**Document Type:** Third-Party Vendor Renewal Conditions  
**Assessment Basis:** Fictional Avenloft Third-Party Risk Review Case  
**Related Documents:**
- `../03-vendor-risk-assessment/vendor-risk-scenarios.md`
- `../03-vendor-risk-assessment/current-controls-and-residual-risk.md`
- `findings-remediation-tracker.md`
- `../05-vendor-decision/vendor-decision-memo.md`

---

## 1. Purpose

This document defines the security, privacy, contractual, operational, and governance conditions that Avenloft should consider before approving continued use, an extension, or a future renewal of CobaltCedar Analytics' SupportLens service.

The conditions are based on the findings and residual risks identified in the fictional third-party risk assessment.

The purpose is to ensure that:

- Important security weaknesses are addressed.
- Vendor security claims are supported by appropriate evidence.
- Avenloft's user access and data-processing arrangements are adequately governed.
- Contractual and privacy obligations are clearly documented.
- Outstanding risks receive appropriate management attention.
- Continued use is supported by a documented business justification and authorized decision.

These are proposed assessment conditions. They are not existing contractual commitments, confirmed vendor agreements, or approved management decisions.

## 2. Current Assessment Position

The assessment identified three principal risk scenarios.

| Risk ID | Risk Scenario | Current Residual Risk |
|---|---|---|
| TPRM-R01 | Customer-account compromise and unauthorized analytics export | Moderate |
| TPRM-R02 | Cross-tenant exposure of Avenloft data | Moderate |
| TPRM-R03 | Excessive retention and incomplete data deletion | Moderate |

The main renewal concerns are:

1. Customer MFA is optional on the Standard plan.
2. Three of eight Avenloft user accounts do not have TOTP enabled.
3. Four users have analytics export permissions.
4. Independent validation of tenant isolation was not supplied.
5. Remediation and independent retesting of the bulk-export rate-limiting finding remain unverified.
6. A sample deletion certificate was not supplied.
7. Contractual incident-notification and subprocessor provisions require improvement.

The case identifies November 1, 2026 as the contract renewal date. As of November 27, 2026, that date has passed. The supplied case evidence does not confirm whether the contract was renewed, extended, amended, or allowed to expire.

Accordingly, this document defines requirements for a prospective decision and does not assume that a renewal has occurred.

## 3. Mandatory Security Conditions

The following conditions are recommended as important requirements for continued use or a new long-term commitment.

### RC-01 — Enforced Customer Authentication

**Related Risk:** TPRM-R01  
**Priority:** High  
**Proposed Owner:** Marcus Holloway / CobaltCedar Analytics

**Condition:**

All active Avenloft SupportLens accounts must use MFA. Optional MFA enrollment should not be treated as sufficient protection for accounts that can access customer-support information.

Avenloft should evaluate whether this requirement can be enforced on the Standard plan or whether a suitable alternative authentication arrangement is required.

**Acceptance Criteria:**

- All active Avenloft accounts are identified.
- MFA is enforced for all active accounts.
- Enrollment status is validated.
- Exceptions are documented and formally approved.
- Authentication configuration is supported by appropriate evidence.

**Required Evidence:**

- Current user and account list.
- MFA configuration evidence.
- Evidence of user enrollment.
- Documented exception approvals, where applicable.

**Completion Rule:**

The condition should not be marked complete merely because the vendor confirms that MFA is available. Evidence must demonstrate that MFA is enforced for the relevant Avenloft accounts.

### RC-02 — Review and Restrict Analytics Export Permissions

**Related Risk:** TPRM-R01  
**Priority:** High  
**Proposed Owner:** Lena Ortiz / Marcus Holloway

**Condition:**

Analytics export permissions must be limited to users with an approved and documented business requirement.

The current arrangement identifies four Avenloft users with export permissions.

**Acceptance Criteria:**

- All current export-enabled accounts are identified.
- Each export permission has a documented business justification.
- Unnecessary permissions are removed.
- Export access is approved by the appropriate business owner.
- Changes are recorded and retained for review.

**Required Evidence:**

- Current user and role listing.
- Approved export-permission matrix.
- Relevant configuration evidence.
- Record of access changes.

### RC-03 — Formal Periodic Access Certification

**Related Risk:** TPRM-R01  
**Priority:** Medium  
**Proposed Owner:** Aaron Bell / Lena Ortiz

**Condition:**

Avenloft must establish a documented process for reviewing and certifying active SupportLens users and permissions.

An informal review during quarterly operations meetings is not a sufficient substitute for retained access-certification evidence.

**Acceptance Criteria:**

- An access-review process is documented.
- A responsible reviewer is identified.
- Active accounts and roles are reviewed.
- Unnecessary access is removed.
- Approval and completion records are retained.

**Required Evidence:**

- Access-review procedure.
- Completed access-certification record.
- Approved user and permission list.
- Record of access removals or changes.

### RC-04 — Validate Bulk-Export Rate-Limiting Remediation

**Related Risk:** TPRM-R01  
**Priority:** High  
**Proposed Owner:** CobaltCedar Analytics / Aaron Bell

**Condition:**

The vendor must provide the current status of the Medium penetration-test finding involving insufficient rate limiting on the bulk-export endpoint.

The case identifies October 30, 2026 as the target remediation date. This date has passed, and the supplied evidence does not establish whether remediation or independent retesting was completed.

**Acceptance Criteria:**

- Current finding status is documented.
- The implemented remediation is described.
- Relevant retesting has been completed.
- Retest results address the original weakness.
- Any remaining limitations or exceptions are documented.

**Required Evidence:**

- Updated penetration-test finding.
- Remediation record.
- Relevant test or retest results.
- Independent validation evidence, where available.

**Completion Rule:**

A vendor statement that the finding was fixed is not sufficient by itself. The condition remains pending until suitable evidence has been reviewed.

## 4. Additional Security Assurance Conditions

### RC-05 — Tenant-Isolation Validation

**Related Risk:** TPRM-R02  
**Priority:** High  
**Proposed Owner:** CobaltCedar Analytics / Aaron Bell

**Condition:**

The vendor must provide appropriate assurance that SupportLens enforces logical separation between customer tenants.

The architecture narrative supplied in the case is useful, but it does not independently demonstrate effective tenant isolation.

**Acceptance Criteria:**

- Tenant-isolation architecture is documented.
- Customer authorization boundaries are explained.
- Controls preventing cross-tenant access are described.
- Relevant testing covers tenant-level access restrictions.
- Any identified exceptions are disclosed and addressed.

**Required Evidence:**

- Current architecture documentation.
- Application authorization-control description.
- Relevant penetration-test or security-test results.
- Independent validation evidence, where available.

### RC-06 — Vulnerability Management Evidence

**Related Risk:** TPRM-R01 / TPRM-R02  
**Priority:** Medium  
**Proposed Owner:** CobaltCedar Analytics / Aaron Bell

**Condition:**

The vendor should provide sufficient evidence of its reported weekly external and monthly authenticated vulnerability-scanning activities and its vulnerability-remediation process.

**Acceptance Criteria:**

- Scan frequency is confirmed.
- Relevant scan summaries are provided.
- Significant findings are tracked.
- Remediation status and exceptions are documented.
- Material outstanding vulnerabilities are communicated through an agreed process.

**Required Evidence:**

- Relevant external scan reports or summaries.
- Relevant authenticated scan reports or summaries.
- Vulnerability-remediation records.
- Evidence of risk-based prioritization.

### RC-07 — Ongoing Security Assurance

**Related Risk:** Cross-cutting  
**Priority:** Medium  
**Proposed Owner:** Aaron Bell / CobaltCedar Analytics

**Condition:**

Avenloft should establish an ongoing process for reviewing relevant vendor security-assurance documentation.

The supplied SOC 2 Type II summary covers July 1, 2025 through June 30, 2026 and identifies the terminated-account deactivation exception.

The reported July 2026 workflow change should be supported by appropriate evidence.

**Acceptance Criteria:**

- Current assurance documentation is obtained.
- Assessment scope and reporting period are reviewed.
- Relevant exceptions are identified.
- Remediation of the terminated-account deactivation issue is supported by evidence.
- Changes after the reporting period are not assumed to have been independently tested unless evidence confirms this.

**Required Evidence:**

- Current SOC 2 report or appropriate assurance documentation.
- Relevant exception details.
- Remediation documentation.
- Evidence of post-change testing, where available.

## 5. Privacy and Data-Protection Conditions

### RC-08 — Documented Data-Minimization Requirements

**Related Risk:** TPRM-R01 / TPRM-R02  
**Priority:** Medium  
**Proposed Owner:** Lena Ortiz / Marcus Holloway / Hannah Kim

**Condition:**

Avenloft should maintain a documented list of the information permitted in weekly Salesforce CSV exports.

Only information necessary for the SupportLens analytics purpose should be uploaded.

**Acceptance Criteria:**

- Approved export fields are documented.
- Business purpose for the fields is recorded.
- Unnecessary fields are excluded.
- Free-text content is reviewed for unnecessary sensitive technical details.
- Export scope is periodically reassessed.

**Required Evidence:**

- Approved export-field inventory.
- Data-flow documentation.
- Relevant CSV configuration or sample structure.
- Documented data-minimization review.

### RC-09 — Defined Retention Requirements

**Related Risk:** TPRM-R03  
**Priority:** Medium  
**Proposed Owner:** Hannah Kim / Lena Ortiz

**Condition:**

Avenloft must determine whether the Standard plan's 180-day default retention period is appropriate for its business and privacy requirements.

**Acceptance Criteria:**

- Business and privacy retention requirements are documented.
- The vendor's available retention capabilities are confirmed.
- The selected retention period is agreed.
- The treatment of analytics outputs and associated copies is clarified.
- Any exception is documented and approved.

**Required Evidence:**

- Documented retention requirement.
- Vendor retention documentation.
- Relevant configuration evidence, where applicable.
- Approved retention decision.

### RC-10 — Data Deletion and Backup Expiration

**Related Risk:** TPRM-R03  
**Priority:** Medium  
**Proposed Owner:** Hannah Kim / CobaltCedar Analytics / Aaron Bell

**Condition:**

The vendor must provide clear documentation covering the deletion of Avenloft data from active storage and the subsequent expiration of backup copies after termination.

The case states that active deletion begins within 30 days after termination and encrypted backups expire through a further 35-day backup lifecycle.

**Acceptance Criteria:**

- Active-data deletion responsibilities are documented.
- Backup expiration arrangements are documented.
- Relevant retention exceptions are identified.
- Deletion timing is clearly described.
- Avenloft receives appropriate confirmation after deletion.

**Required Evidence:**

- Documented deletion procedure.
- Backup-retention and expiration explanation.
- Sample deletion certificate or equivalent evidence.
- Relevant contractual commitment.

**Completion Rule:**

A general statement that the vendor deletes data after termination is not sufficient to demonstrate completion or verification.

## 6. Contractual Conditions

### RC-11 — Incident-Notification Requirements

**Related Risk:** TPRM-R01  
**Priority:** High  
**Proposed Owner:** Hannah Kim / Noah Grant

**Condition:**

Avenloft should negotiate clearer contractual incident-notification requirements.

The supplied case describes notification without undue delay after a confirmed incident affecting customer data. The vendor's internal target is within 72 hours after confirming customer-data impact, but this is not a fixed hour-based contractual deadline.

**Acceptance Criteria:**

- Contractual notification requirements are reviewed by Legal & Privacy.
- The notification trigger is clearly defined.
- A specific notification timeframe is negotiated where appropriate.
- Required notification contents and communication channels are documented.
- The process includes updates as investigation findings develop.

**Required Evidence:**

- Legal-reviewed contract wording.
- Executed contract amendment or other binding agreement, where agreed.
- Documented incident-notification procedure.

This recommendation is a contractual risk-management measure and does not replace independent legal advice on applicable notification obligations.

### RC-12 — Subprocessor Governance

**Related Risk:** TPRM-R03  
**Priority:** Medium  
**Proposed Owner:** Hannah Kim / Noah Grant / CobaltCedar Analytics

**Condition:**

Avenloft should obtain a current subprocessor list and seek appropriate advance notification and review arrangements for material subprocessor changes.

The case identifies AWS, Datadog, and SendGrid in a May 2026 list.

**Acceptance Criteria:**

- Current subprocessors are identified.
- Service or data-processing roles are described where relevant.
- Change-notification arrangements are documented.
- Review or objection procedures are considered.
- Material subprocessor changes are communicated through an agreed process.

**Required Evidence:**

- Updated subprocessor register.
- Relevant data-processing information.
- Contractual subprocessor provisions.
- Documented notification and review procedure.

### RC-13 — Ongoing Security and Audit Rights

**Related Risk:** Cross-cutting  
**Priority:** Medium  
**Proposed Owner:** Hannah Kim / Noah Grant

**Condition:**

Avenloft should review contractual provisions governing ongoing security assurance and access to relevant vendor evidence.

The case identifies an annual right to request current security documentation but no on-site audit right or explicit SOC 2 maintenance clause.

**Acceptance Criteria:**

- Ongoing security documentation requirements are defined.
- Relevant assurance-report availability is addressed.
- Material security-program changes are communicated.
- Appropriate assessment, audit, or independent-assurance rights are considered.
- The contractual approach is proportionate to service criticality and data exposure.

**Required Evidence:**

- Legal-reviewed contract provisions.
- Updated assurance requirements.
- Documented vendor evidence-sharing arrangements.

## 7. Business and Commercial Conditions

### RC-14 — Confirm Business Need and Alternative Capability

**Related Area:** Vendor criticality and dependency  
**Priority:** Medium  
**Proposed Owner:** Lena Ortiz / Noah Grant

**Condition:**

Before approving continued use, Avenloft should confirm the business value of SupportLens and compare it with the available Salesforce reporting alternative.

**Acceptance Criteria:**

- Current service usage is confirmed.
- Business benefits are documented.
- Operational switching effort is assessed.
- Alternative reporting capability is reviewed.
- The decision is proportionate to annual service expenditure and operational value.

**Required Evidence:**

- Business-owner assessment.
- Usage information.
- Alternative-service comparison.
- Documented business recommendation.

### RC-15 — Evaluate Plan Capabilities and Commercial Cost

**Related Area:** Commercial and control suitability  
**Priority:** Medium  
**Proposed Owner:** Noah Grant / Marcus Holloway / Lena Ortiz

**Condition:**

Avenloft should evaluate whether the Enterprise plan is necessary to meet required authentication, provisioning, and retention capabilities.

The case identifies an approximate annual cost of $24,600 for Enterprise compared with $18,600 for Standard, an additional $6,000 annually.

**Acceptance Criteria:**

- Required features are confirmed with the vendor.
- MFA enforcement options are validated.
- SAML SSO and SCIM capabilities are evaluated.
- Configurable retention requirements are assessed.
- Cost and security benefits are documented.
- The final choice receives appropriate commercial and business approval.

**Required Evidence:**

- Vendor feature and configuration documentation.
- Commercial proposal.
- Cost-benefit assessment.
- Approved plan-selection decision.

Purchasing the Enterprise plan must not automatically be treated as proof that all identified risks have been mitigated.

## 8. Management and Governance Conditions

### RC-16 — Formal Residual-Risk Acceptance

**Related Risks:** TPRM-R01, TPRM-R02, TPRM-R03  
**Priority:** High  
**Proposed Owner:** Maya Chen / Authorized Management

**Condition:**

Remaining Moderate residual risks must be documented and considered by authorized management in accordance with Avenloft's risk governance process.

**Acceptance Criteria:**

- The current risk register is reviewed.
- Outstanding findings and evidence gaps are disclosed.
- Business justification is recorded.
- Treatment options are considered.
- The authorized decision-maker is identified.
- Acceptance conditions and review requirements are recorded.

**Required Evidence:**

- Completed risk register.
- Management decision record.
- Documented risk-acceptance rationale, where accepted.
- Conditions and review date.

Acceptance of risk does not mean that the associated finding has been remediated or validated.

### RC-17 — Continued Monitoring and Reassessment

**Related Area:** Ongoing third-party governance  
**Priority:** Medium  
**Proposed Owner:** Aaron Bell / Relevant Business and Control Owners

**Condition:**

If continued use is approved, Avenloft should establish a documented monitoring and reassessment process for SupportLens.

**Acceptance Criteria:**

- A GRC review owner is identified.
- Periodic vendor assurance reviews are scheduled.
- Customer access and export permissions are reviewed.
- Material security events trigger reassessment.
- Changes in vendor service, subprocessors, or data processing are evaluated.
- Outstanding remediation actions remain tracked.

**Required Evidence:**

- Approved monitoring plan.
- Review schedule.
- Access-review records.
- Vendor evidence review records.
- Risk reassessment records.

## 9. Consolidated Renewal Conditions Matrix

| Condition ID | Condition | Priority | Required Decision or Evidence |
|---|---|---|---|
| RC-01 | Enforce MFA for Avenloft users | High | Validated configuration and enrollment |
| RC-02 | Restrict analytics export permissions | High | Approved permission matrix |
| RC-03 | Formalize access certification | Medium | Completed access review process |
| RC-04 | Validate bulk-export remediation | High | Current finding status and retest evidence |
| RC-05 | Validate tenant isolation | High | Architecture and technical test evidence |
| RC-06 | Obtain vulnerability management evidence | Medium | Scan summaries and remediation records |
| RC-07 | Maintain ongoing security assurance | Medium | Current assurance and exception evidence |
| RC-08 | Document data-minimization requirements | Medium | Approved export-field inventory |
| RC-09 | Agree on appropriate retention | Medium | Documented retention requirements |
| RC-10 | Validate deletion and backup expiration | Medium | Deletion process and confirmation evidence |
| RC-11 | Strengthen incident notification terms | High | Legal-reviewed contractual provisions |
| RC-12 | Improve subprocessor governance | Medium | Current list and change-notification process |
| RC-13 | Review assurance and audit rights | Medium | Agreed contractual arrangements |
| RC-14 | Confirm business need and alternatives | Medium | Business assessment |
| RC-15 | Evaluate plan capabilities and cost | Medium | Feature validation and commercial approval |
| RC-16 | Document residual-risk acceptance | High | Authorized management decision |
| RC-17 | Establish ongoing monitoring | Medium | Approved monitoring plan |

## 10. Conditions for Decision Approval

The following decision approach is recommended.

### 10.1 Before Unconditional Long-Term Renewal

The organization should obtain appropriate evidence for all material security and privacy requirements, resolve or formally treat significant findings, negotiate necessary contractual safeguards, and document authorized acceptance of remaining risks.

### 10.2 For Time-Limited Continued Use

Where the business requires temporary continuation while evidence or remediation remains outstanding, management should explicitly document:

- Business justification.
- Current residual risk.
- Outstanding conditions.
- Responsible owners.
- Agreed review or expiry date.
- Required monitoring.
- Exit or transition triggers.

Time-limited continuation is a proposed risk-management option, not an automatic approval.

### 10.3 If Conditions Cannot Be Satisfied

If material requirements remain unresolved or the vendor cannot provide sufficient evidence, Avenloft should consider:

- Restricting the information uploaded to SupportLens.
- Reducing user and export permissions.
- Limiting or suspending affected service functions.
- Seeking additional contractual safeguards.
- Transitioning to Salesforce reporting or another suitable alternative.

Any restrictions, suspension, or termination must be decided by the authorized business and management stakeholders.

## 11. Decision and Approval Record

This section is reserved for the authorized decision-makers.

| Decision Field | Record |
|---|---|
| Vendor | CobaltCedar Analytics, Inc. |
| Service | SupportLens |
| Current contract status | To be confirmed |
| Renewal or extension proposed | Pending confirmation |
| Business owner recommendation | Pending |
| GRC assessment | Conditional continuation subject to requirements |
| Security review | Pending |
| Legal & Privacy review | Pending |
| Procurement review | Pending |
| Authorized decision-maker | To be confirmed |
| Conditions approved | Pending |
| Outstanding exceptions | To be documented |
| Residual-risk acceptance reference | Not recorded |
| Decision date | Not recorded |
| Next review date | To be agreed |

No condition in this document should be treated as approved or completed unless the relevant decision and supporting evidence are recorded.

## 12. Conclusion

The vendor assessment identifies several conditions that should be addressed before approving a new long-term commitment or unconditional continued use of SupportLens.

The highest priorities relate to customer authentication, export permissions, penetration-test remediation evidence, tenant-isolation assurance, and contractual incident-notification requirements.

Additional requirements concern data minimization, retention, deletion, subprocessor governance, ongoing assurance, and management oversight.

Avenloft should make the vendor decision based on documented evidence, business value, contractual protections, available alternatives, and authorized residual-risk acceptance.

**Assessment limitation:** These conditions are analyst recommendations for a fictional training case. They are not executed contractual amendments, actual vendor commitments, confirmed remediation outcomes, or management approvals.