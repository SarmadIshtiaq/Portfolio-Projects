
# Vendor Criticality Assessment

## 1. Assessment Information

| Field | Details |
|---|---|
| Case ID | GRC-TPRM-003 |
| Organization | Avenloft Systems Group, Inc. (Fictional) |
| Vendor | CobaltCedar Analytics, Inc. (Fictional) |
| Service | SupportLens |
| Business Owner | Lena Ortiz, VP, Customer Success |
| Annual Contract Value | $18,600 |
| Relationship Start | February 2026 |
| Renewal Date | November 1, 2026 |
| Assessment Type | Third-Party Criticality Classification |

## 2. Assessment Objective

The purpose of this assessment is to classify CobaltCedar SupportLens according to the information exposure, access, business criticality, dependency, security evidence, and contractual considerations associated with the relationship.

The assessment follows Avenloft's risk-based third-party classification approach.

Annual contract value is not used as the primary determinant of criticality.

The classification is intended to establish the appropriate level of due diligence and review priority. It is not a substitute for the separate cybersecurity risk assessment.

## 3. Classification Method

Avenloft's case-specific classification approach considers six factors:

1. Data sensitivity and exposure.
2. Vendor access to Avenloft systems.
3. Business criticality.
4. Concentration and operational dependency.
5. Security evidence quality.
6. Contract and relationship lifecycle requirements.

The case requires a Low, Moderate, or Elevated review-priority classification.

The following assessment uses documented case facts and identifies material uncertainties separately.

## 4. Criticality Factor Assessment

### 4.1 Data Sensitivity and Exposure

**Assessment: Elevated**

Evidence and observations:

- SupportLens receives weekly CSV exports of closed Salesforce support cases.
- Exports include customer company names, business contact names, and email addresses.
- Ticket subjects and free-text bodies are included.
- Severity, product area, timestamps, case owner, and resolution code are also included.
- Attachments, payment-card data, authentication secrets, and source code are excluded by the current process.
- Free-text ticket content may nevertheless contain customer-provided logs, hostnames, identifiers, or troubleshooting details.

Risk considerations:

The vendor receives identifiable customer business information and support-case content that may contain sensitive technical details.

The data is transferred outside Avenloft's Salesforce environment and stored in a multi-tenant SaaS service.

The current process does not establish that every free-text field has been screened for sensitive information before upload.

**Conclusion:**

The information exposure is material enough to require an Elevated review priority, even though certain sensitive data categories are excluded by process.

### 4.2 Vendor Access to Avenloft Systems

**Assessment: Low direct system access; material data-processing exposure**

Evidence and observations:

- No direct Salesforce integration exists.
- The vendor has no credentials into Avenloft systems.
- No direct access to Avenloft production systems or endpoints is identified.
- Data is transferred through a weekly manual CSV export and authenticated portal upload.
- Eight Avenloft accounts use SupportLens.
- Five of eight accounts have TOTP MFA enabled.
- All eight accounts can view uploaded support data.
- Four accounts can export vendor analytics results.

Risk considerations:

The absence of direct system access reduces the vendor's direct connectivity and credential-based exposure to Avenloft's environment.

However, this does not remove the risk created by the information already transferred to and processed by the vendor.

The authentication posture of Avenloft's own SupportLens accounts also requires attention.

**Conclusion:**

Direct system access is limited, but third-party data-processing exposure remains material.

### 4.3 Business Criticality

**Assessment: Low**

Evidence and observations:

- SupportLens provides support analytics and trend reporting.
- Customer Success uses it for product themes, response trends, escalation patterns, and account-level reporting.
- Avenloft Relay can operate without SupportLens.
- Frontline customer support can continue without the service.
- Salesforce reports provide an alternative reporting method.

Risk considerations:

Loss of the service would create additional manual reporting work, but the case does not identify an immediate interruption to Avenloft's core service delivery.

**Conclusion:**

SupportLens is useful to business operations but is not identified as an operationally critical service.

### 4.4 Concentration and Operational Dependency

**Assessment: Low to Moderate**

Evidence and observations:

- The service supports Customer Success reporting.
- Avenloft has eight users.
- Salesforce reporting is available as an alternative.
- The business owner confirms that the organization can return to Salesforce reports if SupportLens becomes unavailable.

Risk considerations:

The alternative reporting process reduces dependency on the vendor.

However, the case does not provide a detailed migration plan, replacement-provider assessment, or quantified cost of changing services.

These details should not be assumed.

**Conclusion:**

Current evidence indicates limited operational dependency. Replacement effort and migration requirements remain areas for validation if the relationship is exited.

### 4.5 Security Evidence Quality

**Assessment: Elevated**

Evidence supplied in the case includes:

- Vendor security questionnaire.
- SOC 2 Type II report summary issued August 2026.
- Independent penetration-test summary.
- Vendor security overview.
- Business continuity summary.
- Security incident summary.
- Product and contract excerpts.

Material limitations and concerns:

- The SOC 2 material is a summary rather than a full report in the supplied case.
- The penetration-test summary includes a remaining Medium finding involving insufficient rate limiting on a bulk-export endpoint.
- The case does not show independent retesting of that remaining finding.
- A July 2026 vendor workforce offboarding fix has not been independently tested in the supplied evidence.
- The tenant-isolation explanation is an architecture narrative; separate test evidence is not supplied.
- The vendor questionnaire contains self-attested statements that should not automatically be treated as independently verified controls.

**Conclusion:**

The evidence set is useful but contains unresolved findings and verification gaps. Further due diligence is required before renewal.

### 4.6 Contract and Relationship Lifecycle

**Assessment: Elevated**

Evidence and observations:

- Standard-plan customer data retention is 180 days by default.
- Shorter retention is available on the Enterprise tier.
- Active-data deletion begins within 30 days after contract termination.
- Encrypted backups expire through a further 35-day lifecycle.
- The contract requires incident notification without undue delay after confirmation of a security incident affecting customer data.
- The vendor's internal notification target is within 72 hours after confirming customer-data impact.
- The contract does not define a specific fixed notification deadline.
- The current contract does not specify advance notice for subprocessor changes.
- The subprocessor list supplied is dated May 2026.

Risk considerations:

The current contractual terms do not fully establish Avenloft's desired incident-notification, retention, deletion, and subprocessor oversight expectations.

**Conclusion:**

Contractual and lifecycle gaps require prioritized review and negotiation before renewal.

## 5. Consolidated Criticality Assessment

| Factor | Assessment | Main rationale |
|---|---|---|
| Data sensitivity and exposure | Elevated | Customer contact details and support-ticket free text are transferred to the vendor. |
| Direct system access | Low | No direct Salesforce integration or Avenloft system credentials. |
| Business criticality | Low | Core operations and frontline support can continue without SupportLens. |
| Concentration / dependency | Low to Moderate | Salesforce reporting provides an alternative; migration effort is not quantified. |
| Security evidence quality | Elevated | Open penetration-test finding and unresolved evidence-validation gaps. |
| Contract / lifecycle | Elevated | Retention, incident notification, deletion, and subprocessor terms need review. |

## 6. Overall Classification

**Final review-priority classification: ELEVATED**

### Rationale

The relationship is classified as Elevated because of the combined information exposure, vendor-side processing, security evidence limitations, and contractual gaps.

The principal drivers are:

1. Customer business contact information and support-case content are transferred to the vendor.
2. Free-text ticket content may contain technical identifiers or troubleshooting details.
3. The vendor retains support-case records for 180 days by default.
4. Customer MFA is not enforced on the Standard plan, and only five of eight Avenloft accounts have TOTP enabled.
5. The supplied penetration-test summary identifies a remaining Medium bulk-export rate-limiting finding.
6. Independent evidence is not supplied for certain important remediation and architecture claims.
7. Incident notification and subprocessor change requirements need stronger contractual definition.

### Factors that reduce criticality

- No direct Salesforce integration.
- No vendor credentials into Avenloft systems.
- No direct access to Avenloft production systems identified.
- Frontline support and Avenloft Relay can continue without SupportLens.
- Salesforce reporting provides an alternative business process.

These mitigating factors are relevant, but they do not eliminate the data exposure or the need for stronger vendor oversight.

## 7. Review Priority Versus Cybersecurity Risk Rating

The Elevated classification is a third-party review-priority decision.

It must not be interpreted as a High or Very High residual cybersecurity risk rating.

The separate vendor risk assessment will:

1. Define relationship-specific risk scenarios.
2. Estimate inherent likelihood and impact.
3. Identify controls that exist today.
4. Assess the effectiveness and evidence supporting those controls.
5. Determine residual likelihood, impact, and risk using Avenloft's qualitative matrix.
6. Record required remediation and renewal conditions separately.

Proposed contractual or technical improvements will not be counted as current controls.

## 8. Required Follow-up

| ID | Follow-up question | Responsible function |
|---|---|---|
| CF-01 | Can unnecessary fields be removed from weekly CSV exports without affecting SupportLens reporting? | Customer Success |
| CF-02 | Can MFA be enabled for all eight Avenloft accounts? | Customer Success / Vendor |
| CF-03 | Can Avenloft obtain stronger evidence of tenant-isolation testing? | GRC / Vendor |
| CF-04 | Has the remaining Medium bulk-export rate-limiting finding been independently retested? | GRC / Vendor |
| CF-05 | Has the July 2026 workforce offboarding fix been independently validated? | GRC / Vendor |
| CF-06 | Can retention be reduced and deletion evidence be provided? | Procurement / Legal / Vendor |
| CF-07 | Can the contract define a fixed incident-notification deadline? | Legal / Procurement |
| CF-08 | Is the May 2026 subprocessor list still current? | GRC / Vendor |
| CF-09 | Is the quarterly Avenloft user-access review performed and documented? | Customer Success |

These items are validation requirements. They are not assumed to be completed.

## 9. Recommendation for the Next Assessment Stage

Proceed with a detailed vendor cybersecurity risk assessment using Avenloft's qualitative likelihood-and-impact methodology.

Prioritize the following areas:

- Unauthorized access to customer-support data.
- Compromise of vendor customer accounts.
- Bulk export and data-exposure weaknesses.
- Data retention and deletion.
- Incident notification and response coordination.
- Evidence quality and unresolved remediation items.

The final renewal decision should be based on residual risk, evidence quality, and the completion of defined requirements.

## 10. Source

Primary source: Avenloft Systems Group, GRC-TPRM-003, Third-Party Vendor Risk Assessment Case File, October 12, 2026.

Relevant sections:

- Third-Party Classification Factors — Page 4
- Vendor and Service Profile — Page 5
- Vendor Security Overview and Avenloft Account State — Page 6
- Vendor Questionnaire — Pages 7–8
- Supplemental Stakeholder Notes and Open Questions — Page 12
- Avenloft Vendor Risk Assessment Method — Page 13
- Required Vendor Assessment Fields — Page 14
