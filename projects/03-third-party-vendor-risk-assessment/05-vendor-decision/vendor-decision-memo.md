# Vendor Risk Decision Memo

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Prepared For:** Avenloft Executive Management and CISO  
**Prepared By:** GRC Assessment Function  
**Assessment Type:** Third-Party Vendor Risk and Governance Review  
**Case Reference:** Fictional Avenloft Third-Party Risk Review Case  
**Assessment Date:** November 27, 2026  
**Decision Status:** Proposed Management Recommendation — Not an Approved Decision

---

## 1. Executive Summary

This memo presents the results of the third-party risk assessment of CobaltCedar Analytics, Inc. and its SupportLens SaaS service.

Avenloft uses SupportLens to analyze closed customer-support cases and generate analytics dashboards and account-level reporting. The service processes customer and business contact information, support ticket subjects, free-text descriptions, and related operational metadata.

The assessment identified three principal risk scenarios:

1. Compromise of a customer account and unauthorized export of support information.
2. Potential cross-tenant exposure of Avenloft information.
3. Excessive retention or incomplete deletion of Avenloft data.

All three scenarios currently have a **Moderate residual risk rating** under the case-specific qualitative risk matrix.

The vendor has described several security controls, including workforce authentication, logical tenant isolation, encryption, monitoring, incident response, backups, and data-retention processes. However, important evidence and control limitations remain.

The most significant concerns are:

- MFA is optional on the Standard plan and only five of eight Avenloft users have enrolled in TOTP.
- Four Avenloft users have analytics export permissions.
- The vendor reported a credential-stuffing incident in March 2026 involving customer-account compromise and unauthorized analytics exports.
- Independent evidence specifically validating tenant isolation was not supplied.
- The penetration-test summary identified an open Medium finding involving insufficient rate limiting on a bulk-export endpoint, with an October 30, 2026 target date. Completion and retesting are unverified.
- No sample data-deletion certificate was supplied.
- Contractual incident-notification and subprocessor provisions have limitations.

SupportLens is useful but is not essential to Avenloft's frontline support or core Relay service. Salesforce reporting provides an alternative, although switching would require several weeks of manual effort.

**Recommended management position:** Do not grant unconditional approval for a new or renewed long-term vendor commitment on the basis of the supplied evidence alone. First establish the current contractual position, validate outstanding security remediation, agree proportionate contractual safeguards, and document any authorized acceptance of the remaining Moderate risks.

This is a proposed assessment recommendation, not evidence that management has approved or rejected the vendor.

## 2. Vendor Relationship Overview

| Item | Assessment Detail |
|---|---|
| Vendor | CobaltCedar Analytics, Inc. |
| Product | SupportLens |
| Service type | Multi-tenant SaaS analytics platform |
| Vendor location | United States |
| Hosting | AWS U.S. regions, according to the case |
| Relationship start | February 2026 |
| Annual contract value | $18,600 |
| Stated renewal date | November 1, 2026 |
| Business purpose | Analytics and reporting for closed customer-support cases |
| Avenloft users | 8 Customer Success managers and operations analysts |
| Data transfer | Weekly manual CSV export from Salesforce |
| Direct production access | No direct Avenloft production or endpoint access reported |
| Business criticality | Limited; Salesforce reporting provides an alternative |
| Alternative effort | Several weeks of manual work, according to the case |

### 2.1 Data Processed

The weekly CSV export may contain:

- Customer company names.
- Business contact names and email addresses.
- Ticket subjects and free-text ticket bodies.
- Severity and product area.
- Timestamps, case owner, and resolution code.

The case states that payment-card data, authentication secrets, source code, direct production database records, and attachments are excluded.

Free-text content may still contain logs, hostnames, identifiers, and troubleshooting details. Therefore, the data should not be treated as risk-free simply because certain highly sensitive fields are excluded.

## 3. Risk Assessment Results

### 3.1 Consolidated Risk Summary

| Risk ID | Risk Scenario | Inherent Risk | Residual Risk | Proposed Target |
|---|---|---|---|---|
| TPRM-R01 | Customer-account compromise and unauthorized analytics export | High | Moderate | Low |
| TPRM-R02 | Cross-tenant exposure of Avenloft data | Moderate | Moderate | Moderate |
| TPRM-R03 | Excessive retention and incomplete data deletion | Moderate | Moderate | Low |

The risk ratings are qualitative analyst judgments using the matrix specified for the fictional case. They are not independently validated ratings or formal management decisions.

### 3.2 TPRM-R01 — Customer Account Compromise and Unauthorized Export

**Residual Risk: Moderate**

The vendor's March 14–15, 2026 incident involved nine customer accounts across four organizations. Two compromised accounts had export permissions and exported analytics data.

The incident demonstrates that customer-account compromise and unauthorized export are relevant threats to the service.

Additional concerns include:

- MFA is available but not mandatory on the Standard plan.
- Five of eight Avenloft users have TOTP enabled.
- Four users can export analytics results.
- No formal retained access-certification process was supplied.
- The bulk-export rate-limiting finding requires current remediation-status confirmation and appropriate retesting evidence.

**Management consideration:** Stronger authentication, controlled export permissions, and validated remediation evidence should be treated as important conditions for continued use.

### 3.3 TPRM-R02 — Cross-Tenant Exposure

**Residual Risk: Moderate**

SupportLens is described as a multi-tenant SaaS platform with logical tenant isolation.

However, the supplied case contains an architecture narrative rather than separate independent technical evidence demonstrating effective tenant isolation.

There is no confirmed cross-tenant incident in the case packet. Nevertheless, unauthorized access to Avenloft information by another tenant could have significant consequences.

**Management consideration:** Obtain relevant technical documentation and evidence of cross-tenant authorization testing.

### 3.4 TPRM-R03 — Excessive Retention and Incomplete Deletion

**Residual Risk: Moderate**

The Standard plan has a default retention period of 180 days. The vendor reports that active data deletion begins within 30 days after termination and encrypted backups expire through a further 35-day lifecycle.

However:

- No sample deletion certificate was supplied.
- Backup deletion and retention requirements need clearer documentation.
- The suitability of the Standard plan retention period requires review.
- Contractual data-deletion provisions should be strengthened or clarified.

**Management consideration:** Agree on documented retention and deletion requirements and obtain evidence demonstrating the deletion process.

## 4. Key Control and Contractual Observations

| Area | Current Position in Case | Management Concern |
|---|---|---|
| Customer MFA | Optional on Standard; 5 of 8 Avenloft users enrolled | Incomplete protection against account compromise |
| Export permissions | 4 of 8 users can export analytics | Export access requires documented business justification and periodic review |
| Access certification | Informal quarterly operational review | No formal retained certification evidence |
| Vendor workforce access | 2 of 25 sampled terminated accounts disabled after 36 and 44 hours versus a 24-hour target | July 2026 workflow change not independently tested |
| Tenant isolation | Vendor reports logical isolation | Separate independent test evidence unavailable |
| Penetration testing | One Medium bulk-export rate-limiting finding had an October 30, 2026 target | Current remediation and retesting status unverified |
| Vulnerability scanning | Weekly external and monthly authenticated scans reported | Scan reports not supplied |
| Incident notification | Contract says without undue delay after a confirmed incident affecting customer data | No fixed hour-based contractual deadline; vendor's 72-hour target is internal |
| Subprocessors | May 2026 list identifies AWS, Datadog, and SendGrid | Updated list and stronger change-notification arrangements needed |
| Data retention | 180-day default on Standard | Suitability requires review |
| Data deletion | Active deletion begins within 30 days; backups expire through a further 35-day lifecycle | No sample deletion certificate supplied |
| Audit rights | Annual right to request current security documents; no on-site audit right | Assurance and verification rights are limited |
| SOC 2 obligations | No explicit SOC 2 maintenance clause | Ongoing assurance expectations require clarification |

The SOC 2 Type II summary covers July 1, 2025 through June 30, 2026 and was issued on August 21, 2026. It contains an unmodified opinion but also reports the terminated-account deactivation exception described above.

The summary is not the full underlying SOC 2 report. Its scope and reported exception should be considered when evaluating the level of assurance it provides.

## 5. Business Impact and Alternatives

### 5.1 Business Value

SupportLens provides analytics dashboards and account-level reporting based on closed customer-support cases.

The case identifies eight Avenloft users who use the service.

### 5.2 Business Dependency

The service is not required for:

- Avenloft Relay.
- Frontline customer support.
- Direct production-system operations.

Salesforce reporting provides an alternative. Switching would require several weeks of manual effort, according to the business information supplied in the case.

### 5.3 Business Assessment

The available information indicates that SupportLens provides operational convenience and analytics value but has limited criticality to Avenloft's core operations.

This reduces the business pressure to accept unresolved vendor risks solely to preserve an essential service.

The business owner should nevertheless confirm:

- Whether the current analytics outputs are actively used.
- Whether the Salesforce alternative provides sufficiently useful reporting.
- The actual cost and operational effort of switching.
- Whether the business benefit justifies the annual contract cost.

## 6. Commercial Considerations

| Item | Standard Plan | Enterprise Plan |
|---|---:|---:|
| Annual cost | $18,600 | Approximately $24,600 |
| Additional annual cost | — | Approximately $6,000 |
| TOTP MFA | Available, not mandatory | Plan capabilities should be confirmed with vendor |
| SAML SSO | Not included | Available |
| SCIM | Not included | Available |
| Shorter configurable retention | Not included as stated in the case | Available |

The Enterprise plan may offer capabilities relevant to authentication, user provisioning, and data retention.

However, purchasing a higher plan should not automatically be treated as risk remediation.

Before considering an upgrade, Avenloft should establish:

- Whether the required security settings can actually be enforced.
- Whether all intended users can be governed through SSO and SCIM.
- Whether retention configuration meets Avenloft's documented requirements.
- Whether the additional features are supported by appropriate evidence.
- Whether the annual additional cost is justified by the business and security benefits.

Any commercial decision should be supported by Procurement, the business owner, IT, Legal & Privacy, and the appropriate management authority.

## 7. Recommended Vendor Decision

### 7.1 Proposed Decision

**Recommendation: Conditional continuation only, subject to documented management approval and completion or formal treatment of the priority requirements below.**

An unconditional new long-term renewal should not be recommended solely on the basis of the current case evidence.

The assessment does not establish whether the contract was actually renewed on November 1, 2026. That status must be confirmed before any current vendor decision is recorded.

### 7.2 Conditions for Continued Use

| Condition ID | Required Condition | Proposed Owner | Evidence Required |
|---|---|---|---|
| DEC-01 | Confirm the current contract and service status, including whether the November 1, 2026 renewal occurred. | Noah Grant | Executed agreement, renewal record, or documented contract status. |
| DEC-02 | Confirm the current status of the bulk-export rate-limiting finding and obtain appropriate retesting evidence. | Aaron Bell / CobaltCedar | Updated finding status and relevant retest results. |
| DEC-03 | Require MFA for all active Avenloft users or approve an alternative authentication arrangement with equivalent protection. | Marcus Holloway / CobaltCedar | Configuration and enrollment evidence. |
| DEC-04 | Review export permissions and document the business need for each authorized export user. | Lena Ortiz / Marcus Holloway | Approved access and export-permission review. |
| DEC-05 | Obtain appropriate technical evidence of tenant-isolation controls. | Aaron Bell / CobaltCedar | Architecture documentation and relevant test evidence. |
| DEC-06 | Agree on data-retention, deletion, and backup-expiration requirements. | Hannah Kim / CobaltCedar | Written retention and deletion commitments. |
| DEC-07 | Review incident-notification and subprocessor contractual provisions. | Hannah Kim / Noah Grant | Legal-reviewed contract terms or documented amendments. |
| DEC-08 | Document management's decision to accept or treat the remaining Moderate residual risks. | Maya Chen / Authorized Management | Signed or otherwise formally recorded risk decision. |

These are proposed decision conditions. The case packet does not establish that any of them have been completed.

### 7.3 Conditions Before a Long-Term Renewal

Before entering into or approving a new long-term commitment, management should seek:

1. Current and appropriately scoped vendor security assurance.
2. Verified status of significant outstanding penetration-test findings.
3. Satisfactory authentication and export-access arrangements.
4. Appropriate tenant-isolation validation.
5. Documented retention and deletion obligations.
6. Clearer contractual incident-notification and subprocessor provisions.
7. A documented assessment of the business value and available alternative.
8. Formal acceptance of any residual risk that remains outside normal risk appetite or requires explicit management approval.

Failure to obtain sufficient evidence should result in continued escalation and consideration of the Salesforce reporting alternative or another suitable service.

## 8. Alternative Decision Options

Management may consider the following options.

| Option | Description | Advantages | Considerations |
|---|---|---|---|
| Option A — Conditional Continuation | Continue use subject to defined security, privacy, contractual, and governance conditions. | Preserves analytics capability while requiring risk reduction. | Depends on vendor cooperation, evidence quality, and documented management approval. |
| Option B — Time-Limited Continuation | Allow a limited, explicitly approved continuation period while specific high-priority requirements are addressed. | Avoids an immediate operational transition while keeping unresolved risks under review. | Requires an authorized decision, documented expiry or review point, and clear exit criteria. |
| Option C — Transition to Alternative | Use Salesforce reporting or evaluate another suitable service. | Reduces dependency on the vendor and may avoid accepting unresolved vendor risks. | Requires several weeks of manual effort according to the case and may reduce reporting convenience. |

The assessment recommends considering Option A or Option B only where the conditions, business justification, and residual-risk acceptance are documented.

Option C should remain a credible alternative, particularly if material remediation or assurance requirements cannot be satisfied.

No option is recorded as approved in this memo.

## 9. Proposed Stakeholder Responsibilities

| Stakeholder | Proposed Responsibility |
|---|---|
| Aaron Bell — GRC | Maintain the risk register, coordinate evidence reviews, track remediation, and prepare reassessments. |
| Lena Ortiz — Customer Success | Confirm business value, user requirements, access needs, and alternative operational arrangements. |
| Maya Chen — CISO | Provide security oversight, review escalated risks, and support the management decision within delegated authority. |
| Noah Grant — Procurement | Confirm contract status, manage commercial discussions, and coordinate vendor renewal or exit activities. |
| Hannah Kim — Legal & Privacy | Review contractual, privacy, incident-notification, data-retention, and subprocessor provisions. |
| Marcus Holloway — IT | Validate user access, authentication settings, export permissions, and technical requirements. |
| CobaltCedar Analytics | Provide vendor-side evidence, respond to agreed remediation requirements, and clarify service and security arrangements. |

These responsibilities are proposed for the fictional case. They are not evidence of actual assignments or approvals.

## 10. Management Decision Record

The following section is intentionally left for completion by the authorized decision-makers.

| Decision Field | Record |
|---|---|
| Vendor | CobaltCedar Analytics, Inc. |
| Service | SupportLens |
| Current contract status | To be confirmed |
| Overall residual risk | Moderate |
| Business owner recommendation | Pending |
| GRC recommendation | Conditional continuation, subject to requirements in this memo |
| CISO assessment | Pending |
| Legal & Privacy review | Pending |
| Procurement confirmation | Pending |
| Authorized decision-maker | To be confirmed |
| Decision | Pending |
| Conditions approved | Pending |
| Risk acceptance reference | Not recorded |
| Decision date | Not recorded |
| Next review date | To be agreed |

### Possible Formal Decision Outcomes

The authorized decision-maker should record one of the following, or an appropriately documented alternative:

- Approved for continued use subject to specified conditions.
- Approved for time-limited continuation with an agreed review point.
- Approved for renewal subject to specified contractual and security requirements.
- Not approved; initiate transition to an alternative.
- Deferred pending additional evidence or stakeholder review.

A blank decision field must not be interpreted as an approval.

## 11. Monitoring and Reassessment

If continued use is approved, the following monitoring activities are recommended:

| Monitoring Activity | Proposed Frequency or Trigger | Responsible Function |
|---|---|---|
| Review active users and export permissions | At least quarterly and after material personnel changes | IT / Customer Success |
| Confirm MFA enrollment | At onboarding and during periodic access review | IT |
| Review vendor security assurance | At least annually and when material changes occur | GRC |
| Track open remediation actions | According to agreed action deadlines | GRC |
| Review penetration-test findings and significant vulnerabilities | At assurance review and after material security events | GRC / IT |
| Review subprocessors and relevant changes | At contract review and when vendor changes are announced | Legal & Privacy / Procurement |
| Review retention and deletion requirements | At least annually and on termination or material service changes | Legal & Privacy |
| Reassess vendor risk | Annually, at renewal, or after a material incident or service change | GRC |

These are proposed monitoring intervals, not existing contractual commitments.

## 12. Final Assessment Conclusion

SupportLens provides a useful analytics capability, but the service processes customer-support information and relies on vendor-operated security controls that Avenloft cannot directly administer or independently verify through the supplied case evidence.

The assessment identified three Moderate residual risks, with the greatest immediate management attention required for customer authentication, analytics export permissions, outstanding bulk-export remediation evidence, tenant-isolation validation, and data deletion assurance.

The service's limited business criticality and the availability of Salesforce reporting provide Avenloft with an alternative to indefinite reliance on the vendor.

The appropriate management response is therefore to require evidence-based remediation, strengthen relevant contractual safeguards, maintain an alternative-service option, and formally document the decision to continue, temporarily continue, renew, or exit.

**This memo is a proposed decision recommendation based on a fictional training case. It is not an approved vendor decision, an executed contract amendment, a formal risk acceptance, or evidence that the vendor relationship was renewed.**