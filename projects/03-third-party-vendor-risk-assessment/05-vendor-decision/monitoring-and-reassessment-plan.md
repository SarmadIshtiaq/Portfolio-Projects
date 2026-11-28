# Vendor Monitoring and Reassessment Plan

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Organization:** Avenloft Systems Group  
**Document Type:** Third-Party Vendor Monitoring and Reassessment Plan  
**Assessment Basis:** Fictional Avenloft Third-Party Risk Review Case  
**Plan Status:** Proposed Governance Plan — Pending Approval

---

## 1. Purpose

This document defines a proposed ongoing monitoring and reassessment process for CobaltCedar Analytics, Inc. and its SupportLens SaaS service.

The objective is to ensure that vendor risks do not remain static after the initial assessment and that changes in the vendor's security posture, service arrangements, data processing, and business relationship are identified and evaluated.

The monitoring plan aims to:

- Maintain visibility of the vendor's security and privacy posture.
- Track outstanding findings and remediation commitments.
- Monitor customer access and authentication arrangements.
- Review vendor assurance evidence and security testing.
- Identify material security incidents and changes.
- Monitor data retention, deletion, and subprocessor arrangements.
- Reassess residual risks when relevant information changes.
- Support future contract, renewal, and continued-use decisions.

This is a proposed monitoring framework for the fictional case. It does not imply that Avenloft currently operates these monitoring activities.

## 2. Monitoring Scope

The monitoring process covers the following areas:

| Monitoring Area | Scope |
|---|---|
| Vendor relationship | Business purpose, service use, annual spend, contract status, and service changes |
| Customer access | Active user accounts, authentication, MFA, roles, and permissions |
| Analytics exports | Export permissions, approved users, and data access |
| Vendor workforce security | Workforce authentication, privileged access, and access deprovisioning |
| Security assurance | SOC 2 reports, security documentation, and independent assessments |
| Vulnerability management | Vulnerability scanning, penetration testing, and remediation |
| Security incidents | Customer-account compromise, data exposure, and incident response |
| Tenant isolation | Logical separation and application-level authorization |
| Data protection | Data minimization, encryption, and information handling |
| Data lifecycle | Retention, deletion, and backup expiration |
| Subprocessors | Subprocessor list, material changes, and relevant assurance |
| Contractual governance | Security obligations, incident notification, audit rights, and renewal provisions |
| Business dependency | Business value, operational usage, and alternative-service availability |

## 3. Monitoring Governance and Responsibilities

Monitoring requires coordination between GRC, IT, Customer Success, Procurement, Legal & Privacy, management, and the vendor.

The following responsibilities are proposed based on the stakeholders identified in the case packet.

| Stakeholder | Proposed Monitoring Responsibility |
|---|---|
| Aaron Bell — GRC | Coordinate the vendor monitoring process, maintain the risk register, review evidence, track remediation, and initiate reassessments. |
| Lena Ortiz — Customer Success | Confirm business usage, active users, reporting requirements, export needs, and business dependency. |
| Maya Chen — CISO | Provide security oversight, review escalated risks, and support management risk decisions within delegated authority. |
| Noah Grant — Procurement | Monitor contract status, commercial changes, renewal requirements, and vendor relationship changes. |
| Hannah Kim — Legal & Privacy | Review privacy, retention, deletion, subprocessor, incident-notification, and contractual requirements. |
| Marcus Holloway — IT | Review customer accounts, MFA, user permissions, export access, and relevant technical configuration. |
| CobaltCedar Analytics | Provide vendor security evidence, communicate relevant changes and incidents, and implement agreed vendor-side actions. |

These are proposed governance responsibilities rather than confirmed formal assignments.

## 4. Monitoring Frequency

The following schedule is recommended, subject to management approval and the organization's risk-management requirements.

| Monitoring Activity | Proposed Frequency | Responsible Function |
|---|---|---|
| Review active Avenloft users | Quarterly | IT / Customer Success |
| Review analytics export permissions | Quarterly and after relevant role changes | IT / Customer Success |
| Confirm MFA enrollment | At onboarding and quarterly | IT |
| Review data-export scope | Quarterly | Customer Success / IT |
| Review open findings and remediation actions | Monthly | GRC |
| Review outstanding evidence requests | Monthly until closure | GRC |
| Review relevant vendor security assurance | Annually and when material changes occur | GRC |
| Review penetration-test and vulnerability information | At least annually and after significant security developments | GRC / IT |
| Review incident history and material security events | As incidents occur and during periodic vendor reviews | GRC / CISO |
| Review subprocessor information | At least annually and when changes are notified | Legal & Privacy / Procurement |
| Review data-retention and deletion arrangements | Annually and before contract exit or material changes | Legal & Privacy |
| Review business need and service dependency | Annually and before renewal | Customer Success / Procurement |
| Complete overall vendor risk reassessment | Annually, before renewal, or after a material trigger | GRC |

These are proposed monitoring intervals, not existing contractual service levels or vendor commitments.

## 5. Customer Access and Authentication Monitoring

### 5.1 Active User Review

Avenloft should maintain an approved record of all active SupportLens accounts.

The review should verify:

- Whether each account belongs to an authorized user.
- Whether the user still requires access.
- Whether the assigned role matches the business requirement.
- Whether the account has appropriate authentication protection.
- Whether unnecessary or inactive accounts have been removed.

### 5.2 MFA Monitoring

The case identifies eight Avenloft accounts, of which five have TOTP enabled.

The recommended control objective is MFA enforcement for every active Avenloft account.

**Monitoring evidence:**

- Current user list.
- MFA configuration.
- User enrollment status.
- Documented exceptions.
- Evidence of access removal when users leave or no longer need the service.

A general vendor statement that MFA is available should not be treated as proof that all Avenloft users are protected.

### 5.3 Export Permission Monitoring

Four of eight Avenloft users have analytics export permissions according to the case.

The review should confirm:

- Which users can export analytics.
- Whether each user has a documented business need.
- Whether permission changes have appropriate approval.
- Whether users with no export requirement have been restricted.
- Whether export permissions remain appropriate following personnel or role changes.

### 5.4 Access Review Records

Each periodic review should record:

| Field | Description |
|---|---|
| Review Date | Date the review was performed |
| Reviewer | Person conducting the review |
| User Account | Account being assessed |
| Assigned Role | Current platform role |
| MFA Status | Whether MFA is enabled and enforced |
| Export Permission | Whether export access is assigned |
| Business Justification | Reason access is required |
| Review Decision | Retain, modify, or remove access |
| Approval | Relevant reviewer or approver |
| Evidence Reference | Supporting record or configuration evidence |

Completed reviews should be retained according to Avenloft's internal governance and record-retention requirements.

## 6. Vendor Security Assurance Monitoring

### 6.1 SOC 2 Assurance

Avenloft should periodically obtain and review relevant SOC 2 assurance documentation.

The review should consider:

- Reporting period.
- Report issue date.
- Scope and services covered.
- Relevant control areas.
- Opinion and exceptions.
- Complementary user-entity controls.
- Subservice organization considerations, where applicable.
- Remediation of identified exceptions.
- Changes to the vendor's security environment after the reporting period.

The supplied case includes a SOC 2 Type II summary covering July 1, 2025 through June 30, 2026, issued August 21, 2026.

The summary identifies two of 25 sampled terminated vendor workforce accounts that were disabled after 36 and 44 hours, against a 24-hour target.

The vendor reports that its HR-to-identity workflow was changed in July 2026, but independent post-change testing was not supplied.

**Monitoring requirement:** The next review should seek appropriate evidence showing whether the revised process operates effectively.

A summary or management statement should not automatically be treated as a substitute for the complete assurance report where the full report is reasonably required for the assessment.

### 6.2 Penetration Testing

Avenloft should request relevant penetration-test summaries or reports according to the agreed assurance arrangements.

The review should examine:

- Date and scope of testing.
- Tested applications and service components.
- Critical and High findings.
- Relevant Medium findings.
- Remediation status.
- Independent retest evidence.
- Outstanding vulnerabilities.
- Material changes since the previous testing period.

The case identifies an open Medium bulk-export rate-limiting finding with an October 30, 2026 target date.

Because the target date has passed, its current status must be confirmed rather than assumed to be complete.

### 6.3 Vulnerability Management

The vendor reports:

- Weekly external vulnerability scanning.
- Monthly authenticated vulnerability scanning.

However, the scan reports were not supplied in the case.

Avenloft should seek evidence of:

- Scanning frequency.
- Scope and coverage.
- Significant identified vulnerabilities.
- Remediation prioritization.
- Exceptions and accepted risks.
- Evidence that important remediation activities were completed.

## 7. Security Incident Monitoring

The vendor should communicate material security incidents affecting the service, Avenloft information, or relevant vendor infrastructure according to agreed contractual and operational requirements.

### 7.1 Relevant Incident History

The case reports a credential-stuffing incident on March 14–15, 2026.

The incident affected nine customer accounts across four organizations. Two compromised accounts had export permissions and exported analytics data.

The vendor reports:

- Detection of unusual login and export activity.
- Session revocation.
- Account resets.
- IP blocking.
- Customer notification.
- Increased MFA enrollment prompts.

Avenloft was not identified as affected.

### 7.2 Incident Monitoring Requirements

For future incidents, Avenloft should seek sufficient information to evaluate:

- Incident date and detection time.
- Affected service components.
- Whether Avenloft data was involved.
- Types of information potentially exposed.
- Whether unauthorized access or exports occurred.
- Containment and recovery actions.
- Root-cause analysis, where available.
- Corrective measures.
- Potential impact on Avenloft's obligations and customers.

### 7.3 Incident Escalation

Material vendor security incidents should be escalated to the appropriate Avenloft GRC, IT, CISO, and Legal & Privacy stakeholders.

An incident should trigger reassessment when it:

- Involves Avenloft information.
- Demonstrates failure of an important vendor control.
- Introduces a new relevant threat.
- Reveals a previously unidentified vulnerability.
- Significantly changes the likelihood or impact of an existing risk scenario.

The process should follow applicable legal and contractual obligations. The monitoring plan does not independently establish legal notification deadlines.

## 8. Tenant-Isolation Monitoring

SupportLens is described as a multi-tenant SaaS platform using logical tenant isolation.

Because separate independent tenant-isolation test evidence was not supplied, Avenloft should seek appropriate assurance covering customer-level authorization.

Monitoring should consider:

- Changes to the service's tenant architecture.
- Relevant access-control changes.
- Independent testing of cross-tenant authorization.
- Significant application security findings.
- Material security incidents involving customer data separation.

Any identified weakness affecting tenant boundaries should trigger an immediate risk review.

## 9. Data Protection and Data-Minimization Monitoring

Avenloft transfers support data through weekly manual Salesforce CSV exports.

The export scope should remain limited to the information required for SupportLens reporting.

Periodic reviews should examine:

- Customer and business contact information included.
- Ticket subjects and free-text bodies.
- Severity and product-area fields.
- Timestamps, case owner, and resolution-code fields.
- Unnecessary technical or sensitive details in free-text content.
- Whether the purpose of each exported field remains valid.

The review should also confirm that attachments, payment-card data, authentication secrets, source code, and direct production database records remain excluded, as specified in the fictional case.

The review should be documented through an approved export-field inventory and supporting data-flow documentation.

## 10. Data Retention and Deletion Monitoring

The case identifies the following vendor arrangements:

| Data Lifecycle Item | Case Information |
|---|---|
| Standard plan retention | 180 days by default |
| Active data deletion after termination | Begins within 30 days |
| Encrypted backup lifecycle | Further 35-day expiration lifecycle |
| Sample deletion certificate | Not supplied |
| Shorter configurable retention | Available on Enterprise plan |

Monitoring should confirm:

- The agreed retention period remains appropriate.
- The vendor's actual configuration matches the agreed requirement.
- Retention arrangements cover relevant records and analytics outputs.
- Backup expiration arrangements are understood.
- Data-deletion obligations are documented.
- Suitable evidence of deletion can be obtained upon termination.

Avenloft should request a deletion certificate or equivalent confirmation where appropriate after an actual deletion event.

An absence of a deletion certificate in the original case packet is an evidence gap, not proof that deletion has failed.

## 11. Subprocessor Monitoring

The supplied May 2026 subprocessor list identifies:

- AWS.
- Datadog.
- SendGrid.

The list should be checked for currency and completeness according to agreed vendor assurance arrangements.

Monitoring should consider:

- Current subprocessor identities.
- Relevant services or processing activities.
- Material changes in subprocessors.
- Data-location or processing changes.
- Available security and privacy assurance.
- Contractual notification and review arrangements.

Material changes should be referred to Legal & Privacy and Procurement for assessment.

## 12. Contractual and Commercial Monitoring

Procurement and Legal & Privacy should periodically review the vendor relationship and relevant contractual obligations.

The review should consider:

- Current contract and service status.
- Annual contract cost.
- Renewal and termination terms.
- Incident-notification commitments.
- Confidentiality and security safeguards.
- Subprocessor provisions.
- Data-retention and deletion requirements.
- Assurance documentation obligations.
- Audit or independent-assessment rights.
- Material service or pricing changes.

The case identifies annual Standard plan expenditure of $18,600 and an approximate Enterprise plan cost of $24,600.

Any plan upgrade should be evaluated against the actual business requirements and validated technical capabilities rather than assumed to provide automatic risk remediation.

## 13. Business Dependency Monitoring

SupportLens is used for analytics and reporting rather than frontline support or core Relay operations.

Salesforce reporting is identified as an alternative, requiring several weeks of manual work according to the case.

The business owner should periodically confirm:

- Whether the service continues to provide measurable value.
- Number and roles of active users.
- Reporting activities that depend on SupportLens.
- Whether the Salesforce alternative remains viable.
- Whether manual transition effort has changed.
- Whether annual expenditure remains justified.

A material reduction in business value or increase in vendor risk may support a decision to reduce or discontinue service use.

## 14. Risk Reassessment Triggers

A formal vendor risk reassessment should be initiated when a material change or event affects the vendor relationship or its risk profile.

| Trigger ID | Reassessment Trigger | Required Response |
|---|---|---|
| TRG-01 | Material security incident involving the service or relevant vendor environment | Review affected risks and reassess likelihood and impact. |
| TRG-02 | Confirmed unauthorized access or export of Avenloft data | Escalate immediately and perform a focused risk reassessment. |
| TRG-03 | New Critical or High vulnerability relevant to SupportLens | Obtain vendor response and evaluate exposure and treatment. |
| TRG-04 | Failure or regression in MFA or customer-access controls | Review customer access risk and required restrictions. |
| TRG-05 | Failure of tenant-isolation controls or relevant test evidence | Escalate and reassess cross-tenant exposure. |
| TRG-06 | Significant change to hosting, architecture, or service delivery | Review the effect on information security, privacy, and supplier dependency. |
| TRG-07 | New or materially changed subprocessor | Obtain relevant information and perform privacy and security review. |
| TRG-08 | Change to the information being uploaded | Reassess data sensitivity and exposure. |
| TRG-09 | Change in retention or deletion arrangements | Review privacy and data-lifecycle risks. |
| TRG-10 | Significant unresolved remediation commitment | Escalate and evaluate residual risk and continued-use conditions. |
| TRG-11 | Material vendor ownership or financial change | Review service continuity and supplier dependency. |
| TRG-12 | Business dependency or available alternatives change | Reevaluate the business justification and vendor criticality. |
| TRG-13 | Contract renewal or major amendment | Complete a vendor review before the relevant management decision. |
| TRG-14 | Annual scheduled reassessment | Review the overall relationship and current risk register. |

The table describes proposed trigger events. It does not imply that any such future event has already occurred.

## 15. Risk and Remediation Reporting

The GRC function should maintain a periodic vendor-monitoring report.

The report should include:

| Reporting Metric | Purpose |
|---|---|
| Current residual risk by scenario | Shows the current assessed vendor risk position. |
| Open High-priority findings | Identifies material issues requiring management attention. |
| Total open remediation actions | Tracks the remediation workload. |
| Overdue actions | Identifies actions beyond formally agreed due dates. |
| Actions pending evidence | Highlights unverified remediation. |
| Actions pending validation | Shows evidence awaiting review. |
| Closed and validated actions | Records confirmed remediation outcomes. |
| Outstanding evidence gaps | Identifies unresolved assurance limitations. |
| Recent security incidents | Provides visibility of relevant events. |
| Customer access-review results | Monitors authentication and permission governance. |
| Contract and privacy exceptions | Tracks unresolved contractual requirements. |
| Risk acceptance decisions | Shows formally accepted residual risks. |

The report should distinguish between:

- Vendor-reported completion.
- Evidence received.
- Evidence reviewed.
- Independently validated remediation.
- Formally accepted residual risk.

These are different stages and should not be presented as equivalent.

## 16. Escalation Matrix

| Situation | Proposed Escalation | Recommended Response |
|---|---|---|
| High-priority finding remains unresolved | Aaron Bell and Maya Chen | Review exposure, request an updated remediation plan, and consider restrictions or management escalation. |
| Vendor does not supply required assurance evidence | Aaron Bell / CobaltCedar | Record the evidence gap and reassess the relevant residual risk. |
| Authentication or export permissions are inadequate | Marcus Holloway / Lena Ortiz | Review access and consider restricting affected permissions. |
| Significant privacy or deletion concern arises | Hannah Kim / Maya Chen | Review privacy implications and contractual obligations. |
| Subprocessor or material contract change occurs | Hannah Kim / Noah Grant | Review and obtain appropriate approval before relying on the changed arrangement. |
| Remediation deadline is missed | Aaron Bell / Relevant action owner | Record the missed deadline, request an updated plan, and escalate according to risk severity. |
| Residual risk is outside organizational appetite | Maya Chen / Authorized Management | Obtain a formal risk decision and document conditions. |
| Vendor is unable to satisfy material requirements | Relevant management stakeholders | Evaluate time-limited continuation or transition to an alternative. |

Any service restriction, suspension, renewal, or termination decision requires appropriate management authorization.

## 17. Annual Vendor Reassessment Procedure

The annual reassessment should follow a structured process:

1. Confirm the current vendor relationship and contract status.
2. Validate the business need and service usage.
3. Review the latest user accounts, MFA settings, and export permissions.
4. Review current vendor security assurance.
5. Assess penetration-test and vulnerability-management evidence.
6. Review security incidents and material service changes.
7. Confirm data-processing scope and export minimization.
8. Review data retention, deletion, and backup arrangements.
9. Review subprocessors and contractual protections.
10. Examine outstanding findings and remediation evidence.
11. Reassess inherent and residual risk scenarios.
12. Update the risk register and management reporting.
13. Obtain business-owner, IT, Legal & Privacy, and Procurement input.
14. Obtain authorized management approval or risk acceptance where required.
15. Record the next review date and outstanding monitoring actions.

An annual review does not replace immediate reassessment following a material risk event.

## 18. Monitoring Record Template

The following template can be used to record individual monitoring activities.

| Field | Description |
|---|---|
| Monitoring Reference | Unique monitoring record identifier |
| Review Date | Date the activity was completed |
| Monitoring Area | Access, assurance, incident, privacy, contract, or other area |
| Activity | Specific review or verification performed |
| Responsible Person | Person performing the review |
| Evidence Reference | Supporting document or configuration record |
| Observation | Result or issue identified |
| Related Risk ID | Associated vendor risk |
| Action Required | Follow-up requirement, if any |
| Action Owner | Proposed responsible person or function |
| Status | Open, In Progress, Pending Evidence, Pending Validation, or Closed — Validated |
| Escalation Required | Whether management attention is required |
| Next Review | Agreed next review date |

Records should be maintained in the approved GRC or vendor-management repository.

## 19. Monitoring Plan Approval

The proposed monitoring plan requires review and approval by the relevant Avenloft stakeholders.

| Approval Field | Record |
|---|---|
| GRC Review | Pending |
| IT Review | Pending |
| Business Owner Review | Pending |
| Legal & Privacy Review | Pending |
| Procurement Review | Pending |
| CISO Approval | Pending |
| Effective Date | Not recorded |
| Next Scheduled Review | To be agreed |

No approval or implementation is assumed.

## 20. Conclusion

SupportLens should be subject to ongoing third-party monitoring if Avenloft authorizes continued use.

The most important monitoring priorities are:

1. Customer MFA and export-permission governance.
2. Validation of penetration-test remediation.
3. Ongoing assurance of tenant-isolation controls.
4. Vendor security assurance and vulnerability management.
5. Incident notification and response.
6. Data minimization, retention, and deletion.
7. Subprocessor and contractual changes.
8. Formal reassessment of residual risks.

The proposed process ensures that vendor risk is reviewed throughout the relationship rather than only during initial due diligence or contract renewal.

**Assessment limitation:** This is a proposed monitoring and reassessment plan for a fictional third-party risk case. It does not establish that any monitoring activity has been implemented, approved, or completed by Avenloft.