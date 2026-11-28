cat > projects/03-third-party-vendor-risk-assessment/02-evidence-review/security-questionnaire-review.md <<'EOF'
# Security Questionnaire Review

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Assessment Type:** Third-Party Security Due Diligence  
**Case Environment:** Fictional Avenloft Systems Group training case

---

## 1. Purpose

This document evaluates CobaltCedar's responses to Avenloft's 20-question vendor security questionnaire.

The objective is not simply to record whether the vendor answered "Yes" or "No." Each response is compared with the evidence supplied in the case packet to determine:

- What the vendor claims.
- What evidence supports the claim.
- Whether the evidence is independent, documentary, self-attested, or incomplete.
- What remains unverified.
- What follow-up action is appropriate for Avenloft.

A questionnaire response is not automatically proof that a security control is operating effectively.

## 2. Assessment Method

Each response is assigned one of the following evidence assessments:

| Assessment | Meaning |
|---|---|
| Supported | Supplied evidence provides meaningful support for the response, although it may not prove every aspect of control effectiveness. |
| Partially supported | Some evidence exists, but important details, scope, or operating effectiveness remain uncertain. |
| Not sufficiently evidenced | The response is primarily self-attested or supported by insufficient documentation. |
| Gap identified | Evidence identifies a weakness, exception, missing requirement, or control limitation. |

These assessments describe evidence sufficiency, not a formal audit opinion or certification status.

## 3. Questionnaire Response Review

### Q-01 — Documented Information-Security Program

**Vendor response:** Security program approved annually by executive management.

**Evidence supplied:** Policy index and security program information. Full security policies were not provided.

**Analyst assessment:** Partially supported.

**Analysis:**
The annual executive approval statement indicates management-level oversight. However, the policy index does not establish the actual content, implementation, ownership, or review history of individual security policies.

**Follow-up required:**
- Obtain the current information-security policy.
- Request the policy review and approval date.
- Confirm policy ownership and review frequency.
- Obtain relevant policy excerpts covering access control, incident response, vulnerability management, and data protection.

### Q-02 — Workforce Multi-Factor Authentication

**Vendor response:** Workforce SSO and MFA are mandatory for CobaltCedar workforce users.

**Evidence supplied:** SOC 2 Type II summary referencing identity and access controls.

**Analyst assessment:** Partially supported.

**Analysis:**
The SOC 2 summary provides independent assurance over selected control areas during the stated examination period. However, the summary does not independently demonstrate the current MFA configuration for every workforce account.

The report also identifies an exception: two of 25 sampled terminated workforce accounts were disabled after 36 and 44 hours, exceeding the stated 24-hour target. The vendor reports a workflow change in July 2026, but no independent post-change testing was supplied.

**Follow-up required:**
- Obtain current workforce MFA enforcement evidence.
- Request evidence of the July 2026 identity-workflow remediation.
- Request post-remediation testing or a subsequent access-review result.
- Confirm how exceptions are identified and escalated.

### Q-03 — Customer MFA and SSO Enforcement

**Vendor response:** TOTP MFA is available. SAML SSO is available only on the Enterprise tier.

**Evidence supplied:** Product administration guide and Avenloft account configuration information.

**Analyst assessment:** Supported, with a material configuration gap.

**Analysis:**
The product documentation supports the availability of TOTP MFA and the Enterprise-only SAML SSO feature.

However, MFA is not mandatory for Standard-plan customers. Five of Avenloft's eight accounts have TOTP enabled, while three do not. All eight accounts can view uploaded support data, and four can export analytics results.

The March 2026 credential-stuffing incident further demonstrates why optional customer MFA is relevant to this relationship.

**Follow-up required:**
- Require MFA for all Avenloft accounts.
- Review whether the Standard plan can enforce MFA through an administrative setting.
- Evaluate Enterprise SSO against the additional annual cost.
- Review export permissions and remove unnecessary access.

### Q-04 — Encryption of Avenloft Data

**Vendor response:** TLS 1.2+ in transit and AES-256 at rest.

**Evidence supplied:** Vendor architecture statement and SOC 2 summary.

**Analyst assessment:** Partially supported.

**Analysis:**
The architecture statement describes encryption in transit and at rest. The SOC 2 summary provides additional assurance that selected data-protection controls were within the examination scope.

However, the supplied summary does not provide detailed technical configuration, key-management procedures, or evidence of encryption settings for every relevant data store and backup.

**Follow-up required:**
- Request current encryption configuration documentation.
- Confirm encryption coverage for production databases, backups, and exported data.
- Request a summary of encryption key-management responsibilities.
- Confirm whether the same protections apply to all relevant subprocessors.

### Q-05 — Tenant Separation

**Vendor response:** Tenant ID is enforced in the application and database access layer, with access testing performed during the SDLC.

**Evidence supplied:** Architecture narrative. No separate tenant-isolation test evidence was supplied.

**Analyst assessment:** Not sufficiently evidenced.

**Analysis:**
The architecture description explains the vendor's stated approach to logical tenant separation. However, a design statement does not establish that tenant isolation has been independently tested or that cross-tenant access paths have been effectively prevented.

This matters because SupportLens is a multi-tenant SaaS service processing Avenloft customer-support data.

**Follow-up required:**
- Obtain a recent tenant-isolation testing summary.
- Request evidence of cross-tenant authorization testing.
- Confirm whether tenant-isolation tests are included in penetration testing or secure development reviews.
- Request remediation evidence for any relevant findings.

### Q-06 — Privileged Access Management

**Vendor response:** Separate privileged roles, MFA, approval, and quarterly review.

**Evidence supplied:** SOC 2 Type II summary and access-review exception.

**Analyst assessment:** Partially supported, with an identified exception.

**Analysis:**
The SOC 2 summary provides assurance over selected logical-access controls. However, the report records two sampled terminated accounts that were disabled after the stated 24-hour target.

The vendor reports a July 2026 workflow change, but the supplied case evidence does not independently verify the effectiveness of that change.

**Follow-up required:**
- Obtain the privileged-access policy.
- Request a recent privileged-access review record.
- Obtain evidence supporting the July 2026 remediation.
- Confirm timely removal of access after workforce termination.
- Request details of privileged activity monitoring and approval records.

### Q-07 — Vulnerability Identification and Remediation

**Vendor response:** Weekly scanning, monthly authenticated scanning, annual penetration testing, and severity-based remediation SLAs.

**Evidence supplied:** May 2026 penetration-test summary and remediation tracker.

**Analyst assessment:** Partially supported, with an open finding and remediation evidence gaps.

**Analysis:**
The penetration-test summary reports no Critical or High findings. Two Medium findings were marked remediated in July 2026, but independent retest evidence was not supplied.

One Medium finding involving insufficient rate limiting on the bulk-export endpoint remained open, with an original target date of October 30, 2026.

The case packet does not establish that this finding was subsequently remediated. Its status must therefore remain unverified.

The vendor also reports weekly external and monthly authenticated vulnerability scans, but the underlying scan reports were not supplied.

**Follow-up required:**
- Obtain evidence of remediation for the open bulk-export rate-limiting finding.
- Request independent retest results.
- Obtain evidence supporting closure of the two previously remediated Medium findings.
- Request recent vulnerability scan summaries.
- Confirm remediation SLAs and overdue-finding escalation.

### Q-08 — Secure Development Lifecycle

**Vendor response:** Peer review, automated dependency scanning, SAST in CI, and production change approval.

**Evidence supplied:** SOC 2 summary. No detailed SDLC procedure was supplied.

**Analyst assessment:** Partially supported.

**Analysis:**
The response describes several reasonable secure-development practices. The SOC 2 summary provides limited assurance over selected change-management controls.

However, the supplied evidence does not establish the detailed operation of peer review, SAST, dependency scanning, or security testing across the development lifecycle.

**Follow-up required:**
- Request the secure SDLC policy or procedure.
- Obtain evidence of code-review and production-change approval requirements.
- Request a summary of SAST and dependency-scanning coverage.
- Confirm how security findings are tracked through remediation.

### Q-09 — Security Logging and Retention

**Vendor response:** Security logs are retained for 180 days; Standard-plan customers can view 30 days of activity.

**Evidence supplied:** Questionnaire response and product documentation.

**Analyst assessment:** Partially supported.

**Analysis:**
The product documentation supports the 30-day customer-visible activity-history limitation. The vendor also states that security logs are retained for 180 days.

The distinction matters: customer-visible activity history is not necessarily the same as the vendor's internal security-log retention.

The supplied evidence does not fully establish the contents, completeness, protection, or retrieval process for all security logs.

**Follow-up required:**
- Obtain documentation confirming 180-day security-log retention.
- Confirm which events are logged, particularly authentication, administrative actions, and data exports.
- Confirm log access restrictions and protection against alteration.
- Establish how Avenloft can request relevant logs during an investigation.

### Q-10 — Security Incidents Affecting Customer Accounts

**Vendor response:** Yes. A March 2026 credential-stuffing incident affected several customer accounts.

**Evidence supplied:** Vendor incident summary.

**Analyst assessment:** Gap identified; incident disclosure is useful evidence.

**Analysis:**
The incident occurred on March 14–15, 2026. Nine customer accounts across four customer organizations authenticated successfully. Two compromised accounts had export permissions and exported SupportLens analytics data.

The vendor reports detecting unusual login and export activity, revoking sessions, resetting accounts, blocking IP ranges, and notifying affected customers. It also reports that Avenloft was not affected and that no administrative or production infrastructure access occurred.

The incident does not prove that Avenloft data was compromised. However, it demonstrates a relevant threat scenario involving customer-account compromise and data export.

The vendor increased MFA enrollment prompts but did not make TOTP mandatory for Standard-plan customers.

**Follow-up required:**
- Obtain the incident root-cause and lessons-learned report.
- Confirm corrective actions and their implementation status.
- Require MFA for Avenloft users.
- Review export permissions and bulk-export safeguards.
- Request evidence of monitoring and alerting improvements.

### Q-11 — Customer-Data Retention

**Vendor response:** 180 days by default. Shorter retention is configurable on the Enterprise tier.

**Evidence supplied:** Contract excerpt and product guide.

**Analyst assessment:** Supported, with a data-minimisation concern.

**Analysis:**
The supplied documentation supports the stated Standard-plan retention period and the availability of shorter retention on Enterprise.

A 180-day default means Avenloft support-ticket data remains with the vendor beyond the period potentially needed for analytics. The case does not establish that all uploaded records require this full retention period.

**Follow-up required:**
- Determine the minimum retention period needed for the business purpose.
- Request available retention configuration options.
- Assess whether Enterprise retention is justified by the data exposure reduction.
- Document the approved retention period in the relationship requirements.

### Q-12 — Data Deletion After Contract Termination

**Vendor response:** Active data deletion begins within 30 days after termination; encrypted backups expire within 35 additional days.

**Evidence supplied:** Contract excerpt. No sample deletion certificate supplied.

**Analyst assessment:** Partially supported.

**Analysis:**
The contract describes a deletion process, but the supplied evidence does not include a completed deletion certificate or an example demonstrating how deletion is verified.

The process also means that data may remain in encrypted backups after active-data deletion begins.

**Follow-up required:**
- Request the deletion procedure and a sample deletion certificate.
- Confirm the meaning of the 30-day deletion commencement period.
- Confirm the backup-expiration process and final deletion timeline.
- Agree on written deletion confirmation at contract termination.

### Q-13 — Subprocessor Use

**Vendor response:** AWS, Datadog, and SendGrid are listed as subprocessors.

**Evidence supplied:** Subprocessor list dated May 2026.

**Analyst assessment:** Partially supported.

**Analysis:**
The supplied list identifies three subprocessors. However, the list is dated May 2026 and may not represent the current processing chain.

The case does not provide a complete mapping of which subprocessor receives which categories of Avenloft data.

**Follow-up required:**
- Obtain the current subprocessor list.
- Confirm each subprocessor's processing purpose and data access.
- Identify relevant hosting, monitoring, communications, and support functions.
- Request the vendor's process for assessing subprocessor security.

### Q-14 — Subprocessor Change Notification

**Vendor response:** Customers may subscribe to Trust Center updates. The contract does not specify advance notice.

**Evidence supplied:** Trust Center excerpt and contract.

**Analyst assessment:** Gap identified.

**Analysis:**
The Trust Center provides a communication mechanism, but the contract does not establish an advance-notice period or a clear objection process for subprocessor changes.

This creates uncertainty about Avenloft's ability to review material changes before they affect its data.

**Follow-up required:**
- Request advance written notification of material subprocessor changes.
- Seek a contractual review and objection mechanism.
- Confirm how existing customers are notified.
- Refer proposed contractual wording to Legal and Privacy.

### Q-15 — Incident Notification Commitment

**Vendor response:** The contract requires notification without undue delay after confirmation. The vendor's internal target is within 72 hours after confirming customer-data impact.

**Evidence supplied:** Incident-response summary and contract excerpt.

**Analyst assessment:** Gap identified.

**Analysis:**
The contractual wording does not establish a fixed hour-based notification deadline. The 72-hour target is an internal vendor target, not a contractual commitment.

The distinction is important because Avenloft should not treat an internal target as an enforceable contractual requirement.

**Follow-up required:**
- Request a defined contractual notification deadline.
- Clarify the notification trigger and required information.
- Confirm escalation contacts and communication channels.
- Refer the proposed contractual requirement to Legal and Privacy.

### Q-16 — Business Continuity and Restoration Testing

**Vendor response:** A restore test was completed in February 2026.

**Evidence supplied:** Business-continuity exercise summary.

**Analyst assessment:** Partially supported.

**Analysis:**
The exercise summary provides evidence that a restoration exercise took place. However, the supplied information does not fully establish the exercise scope, success criteria, identified issues, or remediation of any weaknesses.

**Follow-up required:**
- Request the latest restoration exercise report.
- Confirm which systems and data stores were included.
- Review test results and unresolved findings.
- Confirm the frequency of future restoration exercises.

### Q-17 — Recovery Time and Recovery Point Objectives

**Vendor response:** RTO is 8 hours and RPO is 24 hours.

**Evidence supplied:** Business-continuity summary.

**Analyst assessment:** Supported as a documented vendor commitment, subject to validation.

**Analysis:**
The supplied summary records an eight-hour Recovery Time Objective and a 24-hour Recovery Point Objective.

These objectives describe the vendor's stated recovery targets. They do not independently prove that the service can consistently meet them during an actual disruption.

Given that SupportLens is not critical to frontline support and Salesforce reporting is an alternative, these recovery objectives should be evaluated against Avenloft's actual business dependency.

**Follow-up required:**
- Confirm that the objectives cover the SupportLens service and relevant customer data.
- Request restoration exercise results demonstrating performance against the objectives.
- Confirm how Avenloft would be notified of a prolonged service interruption.

### Q-18 — Independent Assurance

**Vendor response:** SOC 2 Type II report issued in August 2026 and annual external penetration testing.

**Evidence supplied:** SOC 2 Type II report summary and penetration-test summary.

**Analyst assessment:** Partially supported.

**Analysis:**
The SOC 2 summary reports an unmodified opinion for the examination period July 1, 2025 to June 30, 2026, and was issued on August 21, 2026.

The report covers selected areas, including logical access, change management, monitoring, incident response, availability, and selected data-protection controls.

However:
- The supplied artifact is a summary, not the complete underlying report.
- The report contains an access-removal exception involving two sampled terminated workforce accounts.
- The reported July 2026 workflow change occurred after the examination period and was not independently tested in the supplied evidence.
- A penetration-test summary does not establish that all identified findings have been independently retested and closed.

**Follow-up required:**
- Request the full SOC 2 Type II report under the vendor's NDA process.
- Review scope, examination period, exceptions, and complementary user-entity controls.
- Request evidence supporting post-period corrective actions.
- Obtain penetration-test remediation and retest evidence.

### Q-19 — Customer Access to Audit Activity

**Vendor response:** Standard-plan customers can retrieve 30 days of user and administrator activity through SupportLens.

**Evidence supplied:** Product guide excerpt.

**Analyst assessment:** Supported, with a monitoring limitation.

**Analysis:**
The product guide supports the stated 30-day customer-visible activity history.

This provides some visibility into user and administrator activity. However, it is shorter than the vendor's stated 180-day internal security-log retention period.

Avenloft should not assume that it can independently retrieve all relevant historical security events for the full 180-day period.

**Follow-up required:**
- Confirm which events are visible to Avenloft.
- Confirm whether data-export events are included.
- Establish how older logs can be requested.
- Determine whether 30 days is sufficient for Avenloft's monitoring and investigation needs.

### Q-20 — Notification of Material Security-Program Changes

**Vendor response:** Material changes are communicated through customer notices when they affect contracted services.

**Evidence supplied:** Self-attested questionnaire response. No corresponding contract clause was located.

**Analyst assessment:** Not sufficiently evidenced.

**Analysis:**
The response describes a notification practice, but no contractual provision or other supplied evidence establishes a defined notification obligation.

Avenloft should not treat this response as a contractual right.

**Follow-up required:**
- Request the written policy or procedure governing material security-change notifications.
- Request an example of a relevant customer notification.
- Seek a contractual notification requirement for material changes affecting the service or Avenloft data.
- Refer proposed wording to Legal and Privacy.

## 4. Consolidated Questionnaire Results

| Evidence assessment | Questions | Count |
|---|---|---:|
| Supported | Q-17, Q-19 | 2 |
| Partially supported | Q-01, Q-02, Q-04, Q-06, Q-08, Q-09, Q-11, Q-12, Q-13, Q-16, Q-18 | 11 |
| Not sufficiently evidenced | Q-05, Q-20 | 2 |
| Gap identified | Q-03, Q-07, Q-10, Q-14, Q-15 | 5 |
| **Total** | **Q-01 to Q-20** | **20** |

These classifications are analyst judgments based on the supplied case evidence. They are not vendor audit ratings.

## 5. Most Material Findings

### Finding 1 — Customer Account Security

**Related questions:** Q-03, Q-10

Standard-plan MFA is optional, and three of Avenloft's eight accounts do not have TOTP enabled. The March 2026 incident demonstrates that compromised customer accounts with export permissions can expose analytics data.

**Required response:** Enforce MFA for all Avenloft users, review export permissions, and validate the vendor's account-security improvements.

### Finding 2 — Bulk-Export Protection

**Related questions:** Q-07, Q-10

The penetration-test summary identifies an insufficient rate-limiting issue on the bulk-export endpoint. The supplied case evidence does not confirm that this finding was remediated after its original October 30, 2026 target date.

**Required response:** Obtain remediation evidence and independent retest results before treating the finding as closed.

### Finding 3 — Tenant Isolation Assurance

**Related question:** Q-05

The vendor describes logical tenant separation, but no separate tenant-isolation testing evidence was supplied.

**Required response:** Obtain a recent test summary demonstrating cross-tenant access-control validation.

### Finding 4 — Contractual Incident Notification

**Related question:** Q-15

The contract uses "without undue delay" after confirmation, while the 72-hour period is only an internal target.

**Required response:** Seek a defined contractual notification deadline, subject to Legal and Privacy review.

### Finding 5 — Data Retention and Deletion

**Related questions:** Q-11, Q-12

Standard-plan retention is 180 days. Active deletion begins within 30 days after termination, with encrypted backups expiring within a further 35 days. No sample deletion certificate was supplied.

**Required response:** Agree on an appropriate retention period and obtain written deletion evidence at termination.

### Finding 6 — Subprocessor Transparency

**Related questions:** Q-13, Q-14

The supplied list is dated May 2026. The contract does not specify advance notice or an objection process for subprocessor changes.

**Required response:** Obtain a current list and seek appropriate contractual notification and review rights.

## 6. Evidence That Reduces Concern

The following evidence provides meaningful assurance or context:

- The SOC 2 Type II summary reports an unmodified opinion for its stated examination period.
- The penetration-test summary reports no Critical or High findings.
- The vendor supplied an incident summary describing detection, containment, and customer notification actions.
- Avenloft was not identified as an affected customer in the March 2026 incident.
- The vendor supplied a business-continuity exercise summary and documented RTO/RPO targets.
- SupportLens does not have direct Salesforce credentials, production-system access, or endpoint access in the assessed relationship.
- The business owner identified Salesforce reporting as an alternative to SupportLens.

These points reduce some concerns but do not eliminate the identified gaps or establish that every vendor control is effective.

## 7. Vendor Statements Requiring Validation

The following claims should not be treated as fully verified solely from the questionnaire:

| Vendor statement | Why validation is needed |
|---|---|
| All workforce users use mandatory MFA | SOC 2 summary provides limited assurance; current configuration evidence is still needed. |
| Tenant separation is enforced | Architecture narrative supplied, but separate testing evidence is absent. |
| Vulnerability scans occur weekly and monthly | Underlying scan reports were not supplied. |
| Two Medium penetration-test findings were remediated | Independent retest evidence was not supplied. |
| The bulk-export rate-limiting finding is resolved | No post-target remediation evidence was supplied. |
| Material security changes are communicated | Self-attested response; no contractual clause was located. |
| Internal incident-notification target is 72 hours | This is not the same as a fixed contractual notification obligation. |
| July 2026 workforce access workflow resolved the SOC 2 exception | Post-period independent validation was not supplied. |

## 8. Recommended Due-Diligence Actions

Before relying on the questionnaire as evidence of acceptable vendor security, Avenloft should:

1. Obtain the full SOC 2 Type II report and review its scope, exceptions, and complementary user-entity controls.
2. Obtain current evidence of workforce MFA and the July 2026 access-removal remediation.
3. Require MFA for every Avenloft SupportLens account.
4. Obtain independent remediation and retest evidence for the bulk-export rate-limiting finding.
5. Obtain tenant-isolation testing evidence.
6. Review the current subprocessor list and processing purposes.
7. Agree on an appropriate customer-data retention period and deletion confirmation process.
8. Refer incident-notification and subprocessor-notification contract changes to Legal and Privacy.
9. Confirm the available security-log retrieval process and retention.
10. Record all unresolved items in the Findings and Remediation Tracker.

## 9. Overall Analyst Conclusion

CobaltCedar has supplied several useful security artifacts, including a SOC 2 Type II summary, penetration-test summary, incident summary, product documentation, contract excerpts, and business-continuity information.

The evidence provides a basis for due diligence, but it does not establish that every relevant control is operating effectively or that all identified weaknesses have been remediated.

The most important relationship-specific concerns are:

- Optional customer MFA on the Standard plan.
- The March 2026 credential-stuffing incident involving customer accounts and data exports.
- The unverified status of the bulk-export rate-limiting finding.
- Missing tenant-isolation test evidence.
- Contractual limitations concerning incident notification and subprocessor changes.
- Retention and deletion evidence gaps.

The relationship should therefore be evaluated using the actual Avenloft data exposure, limited operational dependency, existing safeguards, and unresolved evidence gaps—not the questionnaire's overall response tone or the SOC 2 opinion alone.

The final renewal decision and residual risk ratings should be documented in the Vendor Risk Assessment and Vendor Decision Memo.

---

## 10. Related Project Documents

- [Vendor Relationship Profile](../01-relationship-understanding/vendor-relationship-profile.md)
- [Business Process and Data Flow](../01-relationship-understanding/business-process-and-data-flow.md)
- [Vendor Criticality Assessment](../01-relationship-understanding/vendor-criticality-assessment.md)
- [Access and Dependency Analysis](../01-relationship-understanding/access-and-dependency-analysis.md)
- [Vendor Evidence Register](vendor-evidence-register.md)
- [Findings and Remediation Tracker](../04-findings-remediation/findings-remediation-tracker.md)
- [References](../06-references/references.md)

## 11. Important Limitations

This assessment is based exclusively on the fictional GRC-TPRM-003 training case and its supplied artifacts. No real-world audit, penetration test, vendor interview, independent technical test, or legal review was performed.

All conclusions are analyst judgments for portfolio demonstration and must not be represented as findings about a real vendor.