
# Vendor Relationship Profile

## 1. Assessment Information

| Field | Details |
|---|---|
| Case ID | GRC-TPRM-003 |
| Organization | Avenloft Systems Group, Inc. (Fictional) |
| Vendor | CobaltCedar Analytics, Inc. (Fictional) |
| Service | CobaltCedar SupportLens |
| Assessment Type | Third-Party Vendor Risk Assessment |
| Business Owner | Lena Ortiz, VP, Customer Success |
| GRC Assessor | Junior GRC Analyst |
| Annual Contract Value | $18,600 |
| Relationship Start | February 2026 |
| Contract Renewal | November 1, 2026 |
| Assessment Due Date | October 23, 2026 |

## 2. Vendor Overview

CobaltCedar Analytics, Inc. is a fictional U.S.-based SaaS provider with approximately 76 employees and 420 organizational customers.

Avenloft uses the vendor's SupportLens service to analyze closed customer-support cases and generate analytics dashboards and account-level reporting.

The service supports Customer Success reporting and planning. It is not required for the operation of Avenloft Relay or frontline customer support.

## 3. Business Purpose

SupportLens is used to analyze:

- Product-related support themes.
- Customer response trends.
- Escalation patterns.
- Account-level support volumes.
- Trends across closed support cases.

Eight Customer Success managers and operations analysts use the service.

The business owner considers the service useful because it reduces recurring reporting effort. However, the business can continue operating using Salesforce reports if SupportLens becomes unavailable.

## 4. Data Classification and Exposure

Avenloft transfers weekly CSV exports containing closed Salesforce support cases.

| Data element | Current handling |
|---|---|
| Customer company name | Included |
| Business contact name | Included |
| Business contact email | Included |
| Ticket subject | Included |
| Ticket free-text body | Included |
| Severity and product area | Included |
| Timestamps | Included |
| Case owner | Included |
| Resolution code | Included |
| Ticket attachments | Excluded by current process |
| Authentication secrets | Excluded by design |
| Payment-card data | Excluded by design |
| Avenloft source code | Not included |
| Direct production database records | Not included |

**Important exposure consideration:**

Although attachments and certain sensitive data categories are excluded by process, free-text support tickets may contain customer-provided logs, hostnames, identifiers, or troubleshooting details.

Therefore, the assessment should not assume that all exported ticket content is free of sensitive technical information.

## 5. Data Flow

1. Customer support cases are maintained in Salesforce.
2. Customer Success Operations exports the previous week's closed cases every Friday.
3. The export is saved as a CSV file.
4. An authorized user uploads the CSV through the authenticated SupportLens web portal.
5. SupportLens processes the uploaded data and generates analytics dashboards.
6. Customer Success leadership uses the resulting reports.

The vendor does not have a direct Salesforce integration or credentials to Avenloft systems.

## 6. Access and Authentication Profile

| Control area | Current state |
|---|---|
| Vendor access to Avenloft production | None identified |
| Vendor access to Avenloft endpoints | None identified |
| Salesforce integration | None |
| Data transfer method | Weekly manual CSV export and upload |
| Avenloft user accounts | 8 individual accounts |
| Shared accounts | None identified |
| TOTP MFA enrollment | 5 of 8 accounts |
| SAML SSO | Not available on current Standard plan |
| Customer-visible activity history | 30 days |
| Export permissions | 4 of 8 Avenloft accounts |
| Data viewing permissions | All 8 accounts |

## 7. Data Retention and Contractual Context

- SupportLens retains uploaded support-case records for 180 days by default.
- The Standard plan does not provide shorter retention configuration.
- Active customer-data deletion begins within 30 days after contract termination.
- Encrypted backups expire within the vendor's normal 35-day backup lifecycle.
- The current contract does not require customer MFA or SSO.
- The current contract does not specify a fixed hour-based security incident notification deadline.
- The contract does not specify advance notice or objection rights for subprocessor changes.

These terms should be evaluated as part of the evidence review and renewal findings.

## 8. Business Criticality and Dependency

SupportLens provides reporting and analytical value but is not operationally essential.

According to the business owner:

- Avenloft Relay can operate without SupportLens.
- Frontline support can continue without the service.
- Salesforce reports provide an alternative reporting method.
- Replacing the reporting workflow would create several weeks of manual work.

The service therefore represents a useful business dependency rather than a critical operational dependency.

## 9. Preliminary Third-Party Classification

**Recommended review priority: Elevated**

Rationale:

1. The vendor receives customer business contact information and support-case content.
2. Free-text ticket fields may contain sensitive technical details.
3. Uploaded data is retained for 180 days on the current plan.
4. Customer MFA is not enforced on the Standard plan.
5. Only five of eight Avenloft accounts currently have TOTP MFA enabled.
6. A previous credential-stuffing incident affected other vendor customers.
7. An open penetration-test finding concerns insufficient rate limiting on a bulk-export endpoint.
8. The existing procurement workflow did not require formal security review for this low-spend relationship.

**Balancing factors:**

- No direct access to Avenloft production systems was identified.
- Data is transferred through a manual export and upload process.
- The service is not operationally critical.
- Avenloft can use Salesforce reporting as an alternative.

The Elevated classification is a preliminary review-priority judgment based on the relationship's data exposure and evidence gaps. It is not the residual cybersecurity risk rating. Residual risk will be determined separately using Avenloft's qualitative likelihood-and-impact method.

## 10. Key Stakeholders

| Stakeholder | Responsibility |
|---|---|
| Aaron Bell | GRC assessment coordination and risk recommendation |
| Lena Ortiz | Business ownership and service justification |
| Noah Grant | Procurement and contract renewal |
| Hannah Kim | Legal and privacy review |
| Maya Chen | CISO escalation for High or Very High residual risk |

## 11. Assessment Limitations

This profile is based on the fictional GRC-TPRM-003 training case packet.

It is not an independent audit, technical penetration test, legal opinion, or confirmation that vendor controls have been independently tested.

Vendor statements, supplied evidence, current Avenloft configurations, and proposed renewal conditions will be evaluated separately in the following assessment documents.

## 12. Source

Primary source: Avenloft Systems Group, GRC-TPRM-003, Third-Party Vendor Risk Assessment Case File, issued October 12, 2026.

Relevant sections:
- Assignment Brief — Page 2
- Relationship Context — Page 3
- Vendor Classification — Page 4
- Vendor and Service Profile — Page 5
- Vendor Security Overview — Page 6
- Contract and Data-Handling Excerpts — Page 11
- Stakeholder Notes — Page 12
