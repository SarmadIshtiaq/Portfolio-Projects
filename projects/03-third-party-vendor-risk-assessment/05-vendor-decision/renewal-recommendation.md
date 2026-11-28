# Vendor Renewal Recommendation

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Organization:** Avenloft Systems Group  
**Document Type:** Vendor Renewal and Continued-Use Recommendation  
**Assessment Basis:** Fictional Avenloft Third-Party Risk Review Case  
**Recommendation Date:** November 27, 2026  
**Decision Status:** Proposed Recommendation — Pending Management Approval

---

## 1. Purpose

This document provides a focused recommendation on whether Avenloft Systems Group should continue using or enter into a new renewal arrangement with CobaltCedar Analytics, Inc. for its SupportLens SaaS platform.

The recommendation considers:

- The vendor's business value and operational dependency.
- The information processed by SupportLens.
- The current inherent and residual risk assessments.
- The vendor's security controls and assurance evidence.
- Identified security, privacy, and contractual gaps.
- Proposed remediation and renewal conditions.
- Available alternatives and commercial considerations.

This document supports management decision-making. It does not represent an approved renewal, contract amendment, formal risk acceptance, or actual vendor-management decision.

## 2. Executive Recommendation

**Recommendation: Conditional continuation only, subject to documented management approval, evidence-based security requirements, and defined review conditions.**

An unconditional new long-term renewal is not recommended on the basis of the supplied case evidence alone.

The assessment identified three principal risk scenarios, each currently rated Moderate residual risk:

| Risk ID | Risk Scenario | Current Residual Risk |
|---|---|---|
| TPRM-R01 | Customer-account compromise and unauthorized analytics export | Moderate |
| TPRM-R02 | Cross-tenant exposure of Avenloft data | Moderate |
| TPRM-R03 | Excessive retention and incomplete data deletion | Moderate |

The vendor has reported several relevant security controls, including workforce authentication, encryption, logical tenant isolation, monitoring, incident response, backups, and data-retention processes.

However, important weaknesses and evidence limitations remain. The most significant concerns are customer MFA, export permissions, bulk-export remediation evidence, independent tenant-isolation validation, deletion assurance, and contractual incident-notification provisions.

SupportLens provides reporting and analytics value but is not essential to Avenloft's frontline support or core Relay service. Salesforce reporting offers an alternative, although switching is expected to require several weeks of manual effort according to the fictional case.

This limited business dependency gives Avenloft some flexibility to require additional safeguards rather than accepting unresolved risks solely to preserve the service.

## 3. Renewal and Contract Status

The case packet identifies:

- Relationship commencement: February 2026.
- Annual contract value: $18,600.
- Stated renewal date: November 1, 2026.

The renewal date has passed as of November 27, 2026.

The supplied case evidence does not establish whether the contract was:

- Renewed on November 1, 2026.
- Extended under an existing agreement.
- Amended.
- Allowed to expire.
- Replaced by another contractual arrangement.

**Required action:** Procurement should confirm the current executed contract and service status before recording or acting on any renewal recommendation.

If the contract has already been renewed, this recommendation should be treated as a continued-use and remediation review rather than evidence that a new renewal is still pending.

No renewal outcome is assumed in this assessment.

## 4. Business and Service Assessment

### 4.1 Business Purpose

Avenloft uses SupportLens to analyze closed customer-support cases and generate analytics dashboards and account-level reports.

Eight Customer Success managers and operations analysts use the service.

### 4.2 Business Dependency

The case states that SupportLens is not required for:

- Avenloft Relay.
- Frontline customer support.
- Direct production-system operations.

Salesforce reporting provides an alternative. Transitioning to that alternative would require several weeks of manual effort.

### 4.3 Data Exposure

The service processes:

- Customer company names.
- Business contact names and email addresses.
- Ticket subjects and free-text ticket bodies.
- Severity and product area.
- Timestamps, case owners, and resolution codes.

The case states that payment-card data, authentication secrets, source code, direct production database records, and attachments are excluded.

Free-text support content may still contain logs, hostnames, identifiers, and troubleshooting details. The information therefore remains relevant to confidentiality and privacy risk.

### 4.4 Business Conclusion

SupportLens provides operational convenience and reporting value, but the supplied information indicates limited dependency on the service for core business operations.

The business owner should confirm that the benefits justify the annual expenditure and the security and contractual requirements associated with the relationship.

## 5. Key Risk and Control Considerations

### 5.1 Customer Authentication and Unauthorized Export

**Related Risk:** TPRM-R01  
**Residual Risk:** Moderate

The vendor's March 14–15, 2026 credential-stuffing incident affected nine customer accounts across four organizations. Two compromised accounts had export permissions and exported analytics data. Avenloft was not identified as affected.

Avenloft's current access arrangement has the following characteristics:

- TOTP MFA is available but not mandatory on the Standard plan.
- Five of eight Avenloft users have TOTP enabled.
- Four users can export analytics results.
- No formal retained access-certification record was supplied.

**Recommendation:**

Require MFA for all active Avenloft users, review export permissions, and establish formal periodic access certification.

### 5.2 Penetration-Test Remediation

**Related Risk:** TPRM-R01  
**Priority:** High

The May 11–22, 2026 penetration-test summary reports:

- Zero Critical or High findings.
- Two Medium findings marked remediated in July 2026.
- One open Medium finding involving insufficient rate limiting on a bulk-export endpoint.

The stated target date for the open finding was October 30, 2026.

The supplied case does not confirm whether remediation or independent retesting was completed.

**Recommendation:**

Obtain the current finding status, remediation record, and suitable retesting evidence before treating the issue as closed.

The case does not establish that this finding caused the March 2026 credential-stuffing incident.

### 5.3 Tenant Isolation

**Related Risk:** TPRM-R02  
**Residual Risk:** Moderate

The vendor describes SupportLens as a multi-tenant SaaS platform with logical tenant isolation.

An architecture narrative was supplied, but separate independent test evidence demonstrating effective tenant isolation was not included.

**Recommendation:**

Obtain appropriate architecture documentation and technical validation evidence covering customer-level authorization and cross-tenant access restrictions.

### 5.4 Data Retention and Deletion

**Related Risk:** TPRM-R03  
**Residual Risk:** Moderate

The Standard plan has a default retention period of 180 days. Active deletion begins within 30 days after termination, and encrypted backups expire through a further 35-day backup lifecycle.

No sample deletion certificate was supplied.

**Recommendation:**

Agree on documented retention and deletion requirements, clarify backup expiration, and obtain suitable evidence demonstrating the vendor's deletion process.

### 5.5 Contractual Safeguards

The contract contains confidentiality and reasonable-safeguard provisions. However:

- Incident notification is described as occurring without undue delay after a confirmed incident affecting customer data.
- The vendor's internal 72-hour target is not a fixed hour-based contractual deadline.
- No explicit SOC 2 maintenance clause was identified.
- No advance notice or objection rights for subprocessor changes were identified.
- No on-site audit right was identified.
- The latest supplied subprocessor list is dated May 2026.

**Recommendation:**

Legal & Privacy and Procurement should review incident notification, assurance obligations, subprocessor governance, audit or independent-assessment rights, and data-deletion terms.

## 6. Commercial Considerations

The case provides the following annual plan costs:

| Plan | Annual Cost | Relevant Capabilities Identified in the Case |
|---|---:|---|
| Standard | $18,600 | TOTP MFA available but not mandatory |
| Enterprise | Approximately $24,600 | SAML SSO and SCIM available; shorter configurable retention |

The Enterprise option represents approximately $6,000 additional annual expenditure.

The higher-tier plan may provide capabilities relevant to authentication, provisioning, and data retention. However, purchasing it should not automatically be considered remediation.

Before approving an upgrade, Avenloft should confirm:

- Which security features can actually be enforced.
- Whether the features meet Avenloft's requirements.
- Whether user provisioning and deprovisioning are adequately supported.
- Whether configurable retention meets documented requirements.
- Whether the added cost is justified by the business and risk-reduction benefits.

Procurement, IT, Customer Success, and Legal & Privacy should participate in the commercial evaluation.

## 7. Available Decision Options

### Option A — Conditional Continuation

**Description:** Continue using SupportLens subject to documented security, privacy, contractual, and governance requirements.

**Advantages:**

- Preserves existing reporting capability.
- Allows remediation and evidence validation to take place.
- Avoids an immediate operational transition.
- Maintains a documented mechanism for managing residual risks.

**Considerations:**

- Requires vendor cooperation.
- Requires formal ownership and monitoring of outstanding findings.
- Does not eliminate risk until controls are implemented and validated.
- Requires authorized management approval.

**Assessment:** Preferred option where the required safeguards can be agreed and supported by sufficient evidence.

### Option B — Time-Limited Continuation

**Description:** Permit a defined period of continued use while specified high-priority conditions are addressed.

**Advantages:**

- Provides time to obtain outstanding evidence.
- May avoid an immediate operational disruption.
- Allows management to reassess the relationship after agreed conditions are reviewed.

**Considerations:**

- Requires explicit authorization.
- Requires documented expiry or review date.
- Requires a clear list of outstanding conditions.
- Requires monitoring and exit triggers.
- Must not become an indefinite continuation without reassessment.

**Assessment:** Appropriate only where management documents the business justification and formally accepts the temporary residual risk.

### Option C — Transition to an Alternative

**Description:** Transition from SupportLens to Salesforce reporting or another suitable service.

**Advantages:**

- Reduces reliance on the current vendor.
- Provides an alternative where security or contractual requirements cannot be satisfied.
- Avoids continuing a relationship solely because of existing operational convenience.

**Considerations:**

- The case estimates several weeks of manual effort for transition to Salesforce reporting.
- Reporting capabilities and business needs must be validated.
- Operational planning and stakeholder communication would be required.

**Assessment:** Appropriate if material requirements cannot be satisfied, the vendor does not provide sufficient evidence, or the service no longer provides adequate business value.

## 8. Conditions Recommended Before Long-Term Renewal

The following requirements should be treated as key decision conditions.

| Condition ID | Requirement | Priority | Proposed Owner |
|---|---|---|---|
| RC-01 | Enforce MFA for all active Avenloft users. | High | Marcus Holloway / CobaltCedar |
| RC-02 | Review and restrict analytics export permissions. | High | Lena Ortiz / Marcus Holloway |
| RC-04 | Verify remediation and retesting of the bulk-export rate-limiting finding. | High | Aaron Bell / CobaltCedar |
| RC-05 | Obtain appropriate tenant-isolation validation evidence. | High | Aaron Bell / CobaltCedar |
| RC-10 | Agree on data deletion and backup-expiration requirements. | Medium | Hannah Kim / CobaltCedar |
| RC-11 | Strengthen contractual incident-notification requirements. | High | Hannah Kim / Noah Grant |
| RC-12 | Obtain an updated subprocessor list and improve change notification. | Medium | Hannah Kim / Noah Grant |
| RC-16 | Document authorized acceptance or treatment of residual risks. | High | Maya Chen / Authorized Management |
| RC-17 | Establish ongoing monitoring and reassessment. | Medium | Aaron Bell / Relevant stakeholders |

The detailed acceptance criteria and evidence requirements are documented in `../04-findings-remediation/renewal-conditions.md`.

## 9. Recommendation by Decision Scenario

### If the Contract Has Not Been Renewed

Avenloft should avoid an unconditional long-term renewal based solely on the current evidence.

Management should consider conditional continuation only where the business justification is documented, required safeguards are agreed, and the remaining risks receive authorized treatment.

If material conditions cannot be satisfied, the Salesforce reporting alternative should be evaluated.

### If the Contract Has Already Been Renewed

Avenloft should treat this assessment as a continued-use review.

Procurement should confirm the executed contractual position, and the relevant stakeholders should:

- Review existing contractual protections.
- Agree on outstanding remediation conditions.
- Obtain evidence of security improvements.
- Consider contract amendments where appropriate.
- Document residual-risk acceptance.
- Set a management review date.

A completed renewal must not be interpreted as proof that identified risk findings have been resolved.

### If the Vendor Cannot Satisfy Material Requirements

Avenloft should consider restricting the data or access provided to the service, negotiating additional safeguards, or transitioning to an alternative.

Any suspension, restriction, or termination decision should be made by authorized business, legal, procurement, and management stakeholders.

## 10. Proposed Approval Responsibilities

| Stakeholder | Proposed Responsibility |
|---|---|
| Aaron Bell — GRC | Maintain the assessment, validate evidence, and track findings. |
| Lena Ortiz — Customer Success | Confirm business value, usage requirements, and operational alternatives. |
| Maya Chen — CISO | Review security risks and provide oversight of management decisions within delegated authority. |
| Noah Grant — Procurement | Confirm contract status, evaluate commercial terms, and coordinate vendor negotiations. |
| Hannah Kim — Legal & Privacy | Review contractual, privacy, retention, deletion, and subprocessor requirements. |
| Marcus Holloway — IT | Validate authentication, user access, export permissions, and technical requirements. |
| CobaltCedar Analytics | Supply vendor evidence and implement agreed vendor-side remediation. |

These are proposed responsibilities drawn from the fictional case. They are not confirmation of formal assignments or actual approvals.

## 11. Proposed Management Decision Record

| Decision Field | Record |
|---|---|
| Vendor | CobaltCedar Analytics, Inc. |
| Service | SupportLens |
| Current contract status | To be confirmed |
| Overall residual risk | Moderate |
| Business owner recommendation | Pending |
| GRC recommendation | Conditional continuation only |
| CISO review | Pending |
| Legal & Privacy review | Pending |
| Procurement confirmation | Pending |
| Authorized decision-maker | To be confirmed |
| Selected option | Pending |
| Approved conditions | Pending |
| Risk acceptance reference | Not recorded |
| Decision date | Not recorded |
| Review date | To be agreed |

No approval should be inferred from an incomplete decision record.

## 12. Review and Reassessment Requirements

If continued use is approved, the vendor relationship should be reassessed:

- At least annually.
- Before a future renewal.
- After a material security incident.
- Following significant changes to vendor ownership, service, hosting, or subprocessors.
- When the data-processing scope changes.
- When important vendor controls fail or remediation commitments are not met.
- When the business dependency or available alternatives change.

The monitoring schedule and escalation process are detailed in `monitoring-and-reassessment-plan.md`.

## 13. Final Recommendation

Based on the supplied fictional case evidence, SupportLens provides useful reporting functionality but has unresolved security-assurance, customer-access, data-retention, and contractual governance concerns.

All three assessed risk scenarios currently have Moderate residual risk ratings.

The service is not essential to Avenloft's core support operations, and Salesforce reporting provides an alternative, although switching is expected to require several weeks of manual effort.

The recommended approach is therefore **conditional continuation only, subject to documented management approval and evidence-based risk treatment**.

An unconditional new long-term renewal should not be recommended without confirmation of the current contract status, satisfactory treatment of priority security concerns, appropriate contractual protections, and formal consideration of remaining residual risks.

If the vendor cannot satisfy material requirements, Avenloft should evaluate a transition to an alternative service.

---

**Assessment Limitation:** This recommendation is based on a fictional case packet and qualitative analyst judgments. It is not an actual procurement recommendation, legal opinion, executed renewal decision, or formal management approval.