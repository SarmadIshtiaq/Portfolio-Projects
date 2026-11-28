# Current Controls and Residual Risk Assessment

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Assessment Basis:** Fictional Avenloft Third-Party Risk Review Case  
**Related Documents:**
- `risk-assessment-methodology.md`
- `vendor-risk-scenarios.md`
- `../02-evidence-review/vendor-evidence-register.md`
- `../02-evidence-review/evidence-gaps-and-validation.md`

---

## 1. Purpose

This document consolidates the existing security and privacy controls relevant to Avenloft's use of CobaltCedar Analytics' SupportLens SaaS platform.

It evaluates:

- Which controls are described in the available case evidence.
- Whether controls are vendor-owned or Avenloft-owned.
- The quality and limitations of supporting evidence.
- Whether controls reduce the likelihood or impact of the identified risk scenarios.
- The residual risks that remain after considering existing controls.

The assessment distinguishes existing controls from proposed improvements. Recommendations are not treated as implemented controls, and vendor statements are not automatically treated as independently verified evidence.

## 2. Overall Control Assessment

The case packet describes several security and operational controls. However, the strength of assurance varies.

| Control Area | Existing Control or Arrangement | Evidence Assessment | Overall Assessment |
|---|---|---|---|
| Security governance | Vendor reports an annually approved security program and supplies a security policy index. | Policy index supplied; full policies not provided. | Partially supported |
| Workforce authentication | Vendor workforce uses central SSO and MFA. | Described in the supplied security information and assurance summary. | Partially supported |
| Privileged access | Vendor reports privileged roles and separate approvals. | Control description available, but detailed operating evidence is limited. | Partially supported |
| Customer authentication | TOTP MFA is available on Standard but not mandatory. | Avenloft has enrolled 5 of 8 users. | Partially implemented |
| Customer SSO | SAML SSO is available only on Enterprise. | Standard plan does not include this feature. | Not available on current plan |
| Customer provisioning | SCIM is available only on Enterprise. | Standard plan does not include this feature. | Not available on current plan |
| Customer access reviews | Customer Success manager informally reviews active users during quarterly operations reviews. | No formal retained access certification supplied. | Weakly evidenced |
| Export permissions | Four of eight Avenloft users can export analytics results. | User and permission information supplied in the case. | Implemented, but requires periodic validation |
| Vendor tenant isolation | Vendor states that logical tenant isolation is implemented. | Architecture narrative supplied; separate independent test evidence not provided. | Partially supported |
| Encryption | Vendor reports TLS 1.2+ and AES-256. | Vendor-provided security information. | Reported; implementation evidence limited |
| Vulnerability management | Weekly external and monthly authenticated vulnerability scans are reported. | Scan reports not supplied. | Not sufficiently evidenced |
| Penetration testing | May 2026 test summary reports zero Critical/High findings, two Medium findings marked remediated, and one open Medium finding. | Summary supplied; remediation and independent retest evidence not supplied. | Partially supported |
| Security monitoring | Vendor reports security monitoring and 180-day security log retention. | Vendor description and incident-response information. | Partially supported |
| Incident response | March 2026 credential-stuffing event was detected and handled through session revocation, account resets, IP blocking, and customer notification. | Incident summary supplied. | Response actions reported; independent validation not supplied |
| Customer-visible activity history | Activity history is available for 30 days. | Product information supplied. | Documented capability |
| Backup and recovery | Nightly backups; stated RPO of 24 hours and RTO of 8 hours; restore exercise reported in February 2026. | Vendor-provided information. | Partially supported |
| Data retention | Standard plan retains data for 180 days by default. | Product and vendor information supplied. | Defined arrangement; suitability requires review |
| Data deletion | Active deletion begins within 30 days after termination; backups expire through a further 35-day lifecycle. | Process description supplied; no sample deletion certificate. | Partially supported |
| Subprocessor management | May 2026 list identifies AWS, Datadog, and SendGrid. | List supplied, but update and change-notification provisions require review. | Partially supported |
| Contractual security obligations | Contract includes confidentiality and reasonable safeguards, plus incident notification without undue delay after a confirmed incident affecting customer data. | Contract information supplied. | Some safeguards present; material gaps remain |

## 3. Control Ownership

Control responsibilities are divided between CobaltCedar and Avenloft.

### 3.1 Vendor-Owned Controls

The following controls are primarily the vendor's responsibility:

- Vendor workforce authentication and access management.
- Privileged access administration.
- SaaS application security.
- Tenant-isolation architecture.
- Infrastructure and application monitoring.
- Vulnerability management and penetration testing.
- Vendor incident detection and response.
- Backup and disaster recovery arrangements.
- Vendor-side data retention and deletion.
- Subprocessor oversight.

Avenloft should request appropriate evidence to evaluate these controls because they operate within the vendor's environment.

### 3.2 Avenloft-Owned Controls

The following controls remain Avenloft's responsibility:

- Selecting which support information is uploaded.
- Reviewing and minimizing the CSV export fields.
- Managing SupportLens user accounts.
- Enabling available MFA capabilities.
- Limiting export permissions.
- Reviewing active users and access rights.
- Monitoring business use of the service.
- Reviewing vendor security evidence.
- Managing contractual and privacy requirements.
- Making and documenting vendor risk-acceptance decisions.

The vendor's security assurances do not replace Avenloft's responsibility for its own users, information, and configuration.

## 4. Key Control Observations

### 4.1 Authentication and Customer Access

The Standard plan makes TOTP MFA available but does not enforce it.

Five of Avenloft's eight accounts have TOTP enabled, leaving three accounts without this additional authentication control.

All eight accounts can view uploaded support information, while four can export analytics results.

The case also identifies an informal quarterly user review but no formal retained access certification.

**Assessment:** Customer authentication and access governance require improvement. The March 2026 credential-stuffing incident makes the lack of mandatory MFA particularly relevant.

### 4.2 Vendor Workforce Access

The SOC 2 Type II summary identifies two of 25 sampled terminated workforce accounts that were disabled after 36 and 44 hours, compared with a 24-hour target.

The vendor reports that its HR-to-identity workflow was changed in July 2026. However, this change occurred after the SOC 2 reporting period and was not independently tested in the supplied evidence.

**Assessment:** The reported remediation is relevant, but the operating effectiveness of the updated process remains unverified.

### 4.3 Tenant Isolation

The vendor describes SupportLens as a multi-tenant SaaS platform hosted on AWS U.S. regions and states that logical tenant isolation is implemented.

However, the case packet contains an architecture narrative rather than separate technical test evidence demonstrating that one customer's data cannot be accessed by another tenant.

**Assessment:** Tenant isolation remains an important assurance gap. Avenloft should seek evidence of application-level authorization and cross-tenant testing.

### 4.4 Vulnerability Management and Penetration Testing

The vendor reports weekly external and monthly authenticated vulnerability scans, but the scan reports were not supplied.

The May 11–22, 2026 penetration-test summary reports:

- Zero Critical or High findings.
- Two Medium findings marked remediated in July 2026.
- One remaining Medium finding involving insufficient rate limiting on the bulk-export endpoint, with an October 30, 2026 target date.

The case packet does not include independent retest evidence confirming the remediation of the findings.

**Assessment:** The supplied summary provides some assurance, but the outstanding finding and absent validation evidence require follow-up.

### 4.5 Incident Detection and Response

The March 14–15, 2026 credential-stuffing incident affected nine customer accounts across four organizations.

Two compromised accounts had export permissions and exported analytics data.

The vendor reports that it detected unusual login and export activity, revoked sessions, reset accounts, blocked IP addresses, and notified affected customers. Avenloft was not identified as affected.

The vendor increased MFA enrollment prompts after the incident, but MFA remained optional on the Standard plan.

**Assessment:** The vendor demonstrated reported incident-response activity, but the event also highlights the risk of customer-account compromise and unauthorized data export.

The case does not establish that the open penetration-test finding caused this incident.

### 4.6 Data Retention and Deletion

The Standard plan has a default retention period of 180 days. Active deletion begins within 30 days after termination, and encrypted backups expire through a further 35-day lifecycle.

No sample deletion certificate was provided.

**Assessment:** A retention and deletion process is described, but Avenloft does not have sufficient evidence to confirm how deletion is completed and demonstrated.

### 4.7 Contractual and Privacy Safeguards

The contract contains confidentiality and reasonable-safeguard provisions. It also requires notification without undue delay after a confirmed incident affecting customer data.

However, the vendor's internal 72-hour target after confirming customer-data impact is not a fixed hour-based contractual deadline.

Other limitations include:

- No explicit SOC 2 maintenance clause.
- No advance notice or objection rights for subprocessor changes.
- No on-site audit right.
- Annual right to request current security documentation.
- The supplied subprocessor list is dated May 2026 and requires confirmation that it remains current.

**Assessment:** Some contractual safeguards are present, but the agreement should be reviewed for stronger and clearer security, incident-notification, subprocessor, and data-deletion provisions.

## 5. Residual Risk Assessment

Residual risk is assessed after considering the existing controls described in the case packet.

### 5.1 Summary

| Risk ID | Risk Scenario | Existing Controls Considered | Residual Likelihood | Residual Impact | Residual Risk |
|---|---|---|---|---|---|
| TPRM-R01 | Compromised account and unauthorized analytics export | Partial MFA enrollment, restricted export permissions, vendor monitoring and reported incident response, limited uploaded data scope. | Moderate | Moderate | Moderate |
| TPRM-R02 | Cross-tenant exposure of Avenloft data | Vendor-reported logical tenant isolation, encryption, AWS hosting, manual CSV transfer, no direct production access. | Low | High | Moderate |
| TPRM-R03 | Excessive retention and incomplete data deletion | Defined retention period, active deletion process, encrypted backup lifecycle. | Moderate | Moderate | Moderate |

### 5.2 TPRM-R01 — Residual Risk: Moderate

**Why the risk remains Moderate:**

- MFA is not mandatory on the Standard plan.
- Three of eight Avenloft users have not enrolled in TOTP MFA.
- Four users have analytics export permissions.
- The vendor has reported a real credential-stuffing incident affecting customer accounts.
- The case does not provide evidence of a formal Avenloft access-certification process.

Partial MFA, restricted export permissions, and reported monitoring reduce some exposure, but they do not remove the risk.

**Recommended risk treatment:** Enforce MFA for all Avenloft users, review access and export permissions, and establish formal access certification.

### 5.3 TPRM-R02 — Residual Risk: Moderate

**Why the risk remains Moderate:**

- The vendor reports logical tenant isolation.
- The case does not provide separate independent testing evidence for tenant isolation.
- Customer-support information is uploaded to the vendor's multi-tenant SaaS environment.
- The potential impact of unauthorized cross-tenant access remains high.

The likelihood remains assessed as Low because the supplied case does not identify a confirmed cross-tenant incident or a specific tenant-isolation vulnerability. The high potential impact means the resulting residual risk remains Moderate.

**Recommended risk treatment:** Obtain relevant architecture documentation and technical validation of tenant-level access restrictions.

### 5.4 TPRM-R03 — Residual Risk: Moderate

**Why the risk remains Moderate:**

- Standard plan data retention is 180 days by default.
- Active deletion begins within 30 days after termination.
- Encrypted backups expire through a further 35-day lifecycle.
- No sample deletion certificate was supplied.
- The contract does not provide sufficiently detailed evidence of deletion validation in the supplied case.

The stated processes reduce uncertainty about how retention and deletion are intended to work, but the lack of execution evidence leaves residual risk.

**Recommended risk treatment:** Document an agreed retention and deletion schedule, clarify backup deletion, and obtain suitable deletion confirmation evidence.

## 6. Control Improvements and Priority

The following actions are proposed based on their relevance to the identified scenarios.

| Priority | Action | Related Risk | Proposed Owner |
|---|---|---|---|
| High | Require MFA for all Avenloft SupportLens accounts. | TPRM-R01 | Marcus Holloway / CobaltCedar |
| High | Review export permissions and restrict them to users with an approved business need. | TPRM-R01 | Lena Ortiz / Marcus Holloway |
| High | Obtain evidence of remediation and retesting for the open bulk-export rate-limiting finding. | TPRM-R01 | Aaron Bell / CobaltCedar |
| High | Obtain evidence of tenant-isolation testing. | TPRM-R02 | Aaron Bell / CobaltCedar |
| Medium | Establish formal periodic access certification. | TPRM-R01 | Aaron Bell / Lena Ortiz |
| Medium | Review the retention period and agree documented deletion requirements. | TPRM-R03 | Hannah Kim / Lena Ortiz |
| Medium | Obtain a sample deletion certificate or equivalent validation evidence. | TPRM-R03 | Aaron Bell / CobaltCedar |
| Medium | Review incident-notification and subprocessor contractual provisions. | TPRM-R01, TPRM-R03 | Hannah Kim / Noah Grant |
| Medium | Obtain vendor vulnerability-scan evidence and relevant security documentation. | TPRM-R01, TPRM-R02 | Aaron Bell / CobaltCedar |

Priority labels are proposed analyst recommendations, not vendor-assigned priorities or evidence of approved remediation deadlines.

## 7. Evidence Required to Reassess Residual Risk

The following evidence would help determine whether the current ratings can be reduced or whether additional treatment is necessary.

| Evidence ID | Evidence Required | Related Control | Related Risk |
|---|---|---|---|
| E-01 | Current list of active Avenloft users and their roles. | Customer access management | TPRM-R01 |
| E-02 | Evidence that all active Avenloft users have MFA enabled or an enforced equivalent. | Customer authentication | TPRM-R01 |
| E-03 | Approved list of users permitted to export analytics. | Export authorization | TPRM-R01 |
| E-04 | Completed access-certification record. | Periodic access review | TPRM-R01 |
| E-05 | Evidence of remediation and independent retesting of the bulk-export rate-limiting finding. | Vulnerability remediation | TPRM-R01 |
| E-06 | Tenant-isolation architecture and cross-tenant security test evidence. | Tenant isolation | TPRM-R02 |
| E-07 | Current retention and deletion documentation, including backup lifecycle details. | Data lifecycle management | TPRM-R03 |
| E-08 | Sample deletion certificate or equivalent proof of deletion process. | Data deletion | TPRM-R03 |
| E-09 | Current subprocessor list and change-notification process. | Subprocessor governance | TPRM-R03 |
| E-10 | Updated contractual incident-notification and data-deletion terms. | Contractual safeguards | TPRM-R01, TPRM-R03 |

These evidence requests are proposed validation requirements. They are not evidence that the vendor has already supplied or completed the requested material.

## 8. Overall Assessment Conclusion

The available case evidence indicates that CobaltCedar has several reported security and operational controls, including workforce authentication, encryption, logical tenant isolation, monitoring, incident response, backups, and defined data-retention processes.

However, important limitations remain:

- Customer MFA is optional on the Standard plan.
- Avenloft's MFA enrollment is incomplete.
- Formal access certification is not evidenced.
- The tenant-isolation claim lacks separate test evidence.
- Vulnerability scan reports and penetration-test remediation validation were not supplied.
- Data deletion has not been supported by a sample deletion certificate.
- Contractual notification and subprocessor provisions need further review.

The three assessed scenarios currently have Moderate residual risk ratings under the case-specific matrix.

Given the service's limited operational dependency and the availability of Salesforce reporting as an alternative, Avenloft has some flexibility to require additional safeguards before making a continued-use or renewal decision.

The assessment recommends documented remediation, evidence validation, legal and privacy review, business-owner input, and formal risk acceptance by an authorized decision-maker.

**Assessment limitation:** This is a fictional portfolio assessment based on the supplied case packet. It is not a real vendor audit, independent technical validation, or formal approval of the vendor relationship.