
# Access and Dependency Analysis

## 1. Assessment Information

| Field | Details |
|---|---|
| Case ID | GRC-TPRM-003 |
| Organization | Avenloft Systems Group, Inc. (Fictional) |
| Vendor | CobaltCedar Analytics, Inc. (Fictional) |
| Service | SupportLens |
| Assessment Area | Access Management and Business Dependency |
| Business Owner | Lena Ortiz, VP, Customer Success |
| Assessment Type | Third-Party Risk Assessment |

## 2. Purpose

This document evaluates the access relationship between Avenloft and CobaltCedar SupportLens.

The assessment considers:

- Vendor access to Avenloft systems.
- Avenloft user access to SupportLens.
- Authentication and MFA configuration.
- User permissions and export capabilities.
- Access review practices.
- Potential account-compromise exposure.
- Operational dependency and alternative arrangements.

The objective is to distinguish direct system access from access to information transferred to a third-party service.

## 3. Vendor Access to Avenloft Systems

### 3.1 Current Access Model

The case packet establishes the following:

| Access area | Current state |
|---|---|
| Direct Salesforce integration | None |
| Vendor credentials into Avenloft systems | None identified |
| Direct Avenloft production access | None identified |
| Direct Avenloft endpoint access | None identified |
| Data transfer | Weekly manual CSV export and upload |
| Upload destination | Authenticated SupportLens web portal |

### 3.2 Assessment

CobaltCedar does not have direct connectivity or credentials into Avenloft's Salesforce or production environment under the described service arrangement.

This reduces the direct attack paths through vendor-held credentials or system integrations.

However, Avenloft transfers customer-support information to SupportLens. Once uploaded, the vendor processes and retains that information within its own SaaS environment.

Therefore:

**No direct system access does not mean no third-party security exposure.**

The primary exposure is the vendor's possession and processing of Avenloft customer-support data.

## 4. Avenloft User Access to SupportLens

### 4.1 Account Inventory

The case packet identifies eight individual Avenloft user accounts.

| Account attribute | Observed state |
|---|---|
| Total named accounts | 8 |
| Shared accounts identified | None |
| TOTP MFA enabled | 5 |
| TOTP MFA not enabled | 3 |
| Accounts with data-view access | 8 |
| Accounts with analytics-export permission | 4 |
| SAML SSO | Not available on current Standard plan |
| SCIM provisioning | Not available on current Standard plan |

### 4.2 Access Model

All eight Avenloft users can view uploaded support data.

Four of the eight accounts can export SupportLens analytics results.

This creates two different permission levels:

1. General viewing access.
2. Analytics export access.

The case packet does not establish whether the four export-enabled accounts have a documented business justification or whether export permissions are reviewed individually.

This should be validated with the business owner.

### 4.3 Access Governance

The Customer Success manager informally reviews active users during quarterly operations reviews.

However:

- No formal access certification is supplied.
- No retained evidence of completed quarterly reviews is supplied.
- The case does not establish whether every user's current business need is documented.
- The case does not establish whether access is promptly removed when a user changes responsibilities or leaves the organization.

**Assessment:**

The existence of individual named accounts is a positive access-management feature.

However, the current review process lacks documented evidence of periodic access certification.

## 5. Authentication and MFA Assessment

### 5.1 Current Authentication Configuration

SupportLens uses local username and password authentication for Avenloft customer accounts.

TOTP MFA is available but is not mandatory on the Standard plan.

SAML SSO is available only on the Enterprise tier.

| Authentication control | Current state | Assessment |
|---|---|---|
| Individual user accounts | 8 named accounts | Positive |
| Shared accounts | None identified | Positive |
| TOTP MFA | 5 of 8 accounts | Incomplete enrollment |
| Mandatory customer MFA | Not enforced on Standard plan | Gap |
| SAML SSO | Enterprise tier only | Not available under current plan |
| SCIM | Not available under current plan | Manual access lifecycle dependency |

### 5.2 Assessment

Three Avenloft accounts do not currently have TOTP MFA enabled.

Because SupportLens contains uploaded customer-support information, an account compromise could expose information accessible to that account.

The risk is particularly relevant because the vendor previously experienced a credential-stuffing incident involving customer accounts.

The current configuration does not provide mandatory MFA for Standard-plan customer accounts.

**Assessment conclusion:**

Avenloft should require MFA enrollment for all active SupportLens accounts as a priority. The available authentication options and enforceability should be confirmed with CobaltCedar.

## 6. Account Compromise and Data Exposure

### 6.1 March 2026 Credential-Stuffing Incident

The vendor's incident summary describes the following event:

| Incident attribute | Case fact |
|---|---|
| Date | March 14–15, 2026 |
| Attack type | Credential stuffing |
| Affected accounts | 9 customer user accounts |
| Affected organizations | 4 customer organizations |
| Successful authentication | Yes |
| Accounts with export permissions | 2 compromised accounts |
| Data activity | SupportLens analytics data was exported |
| Administrative or production infrastructure access | Vendor reported none |
| Avenloft affected | No |
| Root cause statement | Vendor found no evidence that its systems were the source of stolen credentials |

### 6.2 Vendor Response

The vendor reported that it:

- Revoked affected sessions.
- Reset impacted user accounts.
- Blocked identified IP ranges.
- Notified affected customers.
- Enabled additional impossible-travel alerts.
- Enabled high-volume export alerts.
- Increased MFA enrollment prompts.

The vendor did not make TOTP mandatory for Standard-plan customer accounts.

### 6.3 Relationship-Specific Exposure

The incident is relevant to Avenloft because:

- Avenloft has eight SupportLens accounts.
- Three accounts do not have TOTP MFA enabled.
- All eight accounts can view uploaded support data.
- Four accounts can export analytics results.
- The vendor has an open Medium penetration-test finding concerning insufficient rate limiting on a bulk-export endpoint.

The case does not establish that the open penetration-test finding caused or contributed to the March incident.

These facts should be evaluated together as a potential account-compromise and data-exposure scenario, not presented as proof of a single confirmed attack path.

## 7. Vendor Workforce Access

The vendor states that:

- Central SSO and MFA are required for vendor workforce users.
- Production administrative access is restricted to approved engineering and operations personnel.
- Privileged access uses separate elevated roles.

The synthetic SOC 2 Type II summary identifies an exception:

Two of 25 sampled terminated vendor workforce accounts were disabled after 36 and 44 hours, compared with the vendor's stated 24-hour target.

The vendor states that it changed its HR-to-identity workflow in July 2026.

However, the supplied SOC 2 summary does not independently test this corrective action because it occurred after the report period.

**Assessment:**

The reported workforce access controls provide useful evidence, but the offboarding remediation requires independent validation.

This is a vendor internal access-management concern. It should not be confused with Avenloft's own eight customer accounts.

## 8. Access Risk Summary

| ID | Access-related concern | Existing evidence | Required validation |
|---|---|---|---|
| AC-01 | Three Avenloft accounts lack TOTP MFA | Account-state summary | Confirm MFA enrollment for all eight accounts |
| AC-02 | All eight accounts can view uploaded support data | Vendor account-state summary | Validate individual business need |
| AC-03 | Four accounts can export analytics | Vendor account-state summary | Confirm export permissions are necessary and restricted |
| AC-04 | Quarterly access review is informal | Stakeholder and evidence notes | Obtain documented access certification |
| AC-05 | Vendor workforce offboarding delay | SOC 2 exception | Obtain evidence of July remediation and independent validation |
| AC-06 | Standard-plan customer MFA is optional | Product and questionnaire evidence | Confirm enforceable MFA configuration |
| AC-07 | Bulk-export rate limiting finding remains open | Penetration-test summary | Obtain remediation evidence and independent retest |

## 9. Business Dependency Assessment

### 9.1 Service Dependency

SupportLens provides analytics and reporting to Customer Success.

The business owner states that the service saves time every week but is not required to operate Avenloft Relay or frontline support.

Salesforce reports are available as an alternative.

### 9.2 Dependency Factors

| Factor | Assessment | Rationale |
|---|---|---|
| Core service dependency | Low | Avenloft Relay can operate without SupportLens. |
| Frontline support dependency | Low | Customer support can continue without the vendor. |
| Reporting dependency | Moderate | SupportLens provides recurring analytics and trend reporting. |
| Availability of alternative | Positive | Salesforce reporting is available. |
| Replacement effort | Not fully quantified | Business owner expects several weeks of additional manual work. |
| Data migration complexity | Unknown | No detailed migration or exit test is supplied. |

### 9.3 Business Impact of Vendor Unavailability

If SupportLens becomes unavailable:

- Customer Success reporting may become slower.
- Staff may need to return to Salesforce reports.
- Manual analysis effort may increase.
- Q4 planning may require additional work.
- The case does not indicate that core product operations or frontline customer support would stop.

**Conclusion:**

The relationship has a manageable operational dependency, but it still requires appropriate data protection and vendor security oversight.

## 10. Alternative and Exit Considerations

The current alternative identified in the case is Salesforce reporting.

Before an exit decision, Avenloft should validate:

1. Whether historical reports can be exported and retained.
2. Whether uploaded data can be retrieved in a usable format.
3. Whether active customer data can be deleted within agreed timelines.
4. Whether backup deletion can be evidenced.
5. Whether the Customer Success team can return to Salesforce reporting without material disruption.
6. Whether any operational or contractual dependencies have been omitted from the current case evidence.

These are proposed validation activities, not confirmed existing capabilities.

## 11. Overall Assessment

### Access posture

**Assessment: Improvement required**

The absence of direct Avenloft system access is a positive factor. However, optional MFA, incomplete MFA enrollment, broad viewing access, export permissions, and informal access reviews create weaknesses in customer-account governance.

### Vendor access posture

**Assessment: Evidence follow-up required**

The vendor reports centralized workforce SSO and MFA, but the SOC 2 summary identifies delayed termination of two sampled workforce accounts. The reported July remediation has not been independently validated in the supplied evidence.

### Business dependency

**Assessment: Low operational dependency**

SupportLens supports reporting efficiency but is not essential to Avenloft Relay or frontline support. Salesforce reporting provides an alternative.

### Overall implication

Limited direct system access and manageable business dependency reduce some dimensions of the relationship's exposure.

They do not eliminate the need to protect customer-support information stored in SupportLens.

Avenloft should prioritize MFA enforcement, least-privilege access, documented access reviews, and validation of the vendor's outstanding security findings.

## 12. Recommended Follow-up Actions

| ID | Action | Proposed owner |
|---|---|---|
| ACT-01 | Enable TOTP MFA for all eight Avenloft accounts. | Customer Success |
| ACT-02 | Review and justify all eight data-view permissions. | Business Owner |
| ACT-03 | Validate the business need for four export-enabled accounts. | Business Owner |
| ACT-04 | Establish and retain quarterly access certification. | Customer Success |
| ACT-05 | Obtain evidence of vendor workforce offboarding remediation. | GRC / Vendor |
| ACT-06 | Obtain independent retest evidence for the open bulk-export finding. | GRC / Vendor |
| ACT-07 | Confirm whether MFA can be enforced on the current Standard plan. | Procurement / Vendor |
| ACT-08 | Document a practical reporting fallback and exit approach. | Customer Success |

These are recommended actions. They are not represented as completed.

## 13. Source

Primary source: Avenloft Systems Group, GRC-TPRM-003, Third-Party Vendor Risk Assessment Case File, October 12, 2026.

Relevant sections:

- Vendor and Service Profile and Data Flow — Page 5
- Vendor Security Overview and Avenloft Account State — Page 6
- SOC 2 Type II Summary and Penetration-Test Summary — Page 9
- March 2026 Account Incident — Page 10
- Contract and Data-Handling Excerpts — Page 11
- Supplemental Stakeholder Notes and Open Questions — Page 12
