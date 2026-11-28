
# Vendor Evidence Register

## 1. Assessment Information

| Field | Details |
|---|---|
| Case ID | GRC-TPRM-003 |
| Organization | Avenloft Systems Group, Inc. (Fictional) |
| Vendor | CobaltCedar Analytics, Inc. (Fictional) |
| Service | SupportLens |
| Assessment Type | Third-Party Security Due Diligence |
| Evidence Review Period | October 2026 |
| Assessment Owner | GRC |
| Primary Business Owner | Lena Ortiz, VP, Customer Success |

## 2. Purpose

This register records the security, privacy-related, operational, and contractual evidence supplied for the CobaltCedar SupportLens relationship.

Its purpose is to:

- Maintain traceability between vendor claims and supporting evidence.
- Distinguish self-attested statements from documentary and independent assurance evidence.
- Record exceptions and unresolved findings.
- Identify missing, outdated, or incomplete evidence.
- Support relationship-specific risk scenarios and renewal decisions.

This register does not represent an independent audit of CobaltCedar.

## 3. Evidence Classification Method

Evidence is classified using the following categories:

| Classification | Meaning |
|---|---|
| Independent assurance | Evidence originating from an independent assessment or assurance activity, as described in the case packet. |
| Documentary evidence | A supplied document, report summary, contract excerpt, product guide, or other recorded artifact. |
| Vendor self-attestation | A statement or questionnaire response made by the vendor without sufficient independent corroboration in the supplied packet. |
| Exception / finding | A documented control exception, penetration-test finding, incident, or other identified weakness. |
| Evidence gap | Information that is missing, incomplete, outdated, or not independently validated. |
| Internal Avenloft evidence | Information about Avenloft's own account configuration, processes, or access practices. |

**Evidence limitation:** The SOC 2 and penetration-test materials in this training case are summaries. They are not complete underlying reports. The case packet is fictional and does not represent a real audit or vendor engagement.

## 4. Evidence Inventory

| Evidence ID | Evidence item | Date / period | Classification | Review status |
|---|---|---|---|---|
| EV-01 | Vendor security questionnaire, Part 1 | October 2026 case packet | Vendor self-attestation / documentary responses | Reviewed |
| EV-02 | Vendor security questionnaire, Part 2 | October 2026 case packet | Vendor self-attestation / documentary responses | Reviewed |
| EV-03 | Vendor security overview | Current case information | Documentary evidence / vendor statements | Reviewed |
| EV-04 | Synthetic SOC 2 Type II summary | Report period: Jul 2025–Jun 2026; issued Aug 21, 2026 | Independent assurance summary / exception | Reviewed |
| EV-05 | Synthetic penetration-test summary | May 11–22, 2026 | Independent testing summary / findings | Reviewed |
| EV-06 | March 2026 account incident summary | Mar 14–15, 2026 | Vendor incident disclosure / incident evidence | Reviewed |
| EV-07 | Contract and data-handling excerpts | Current agreement in case packet | Contractual documentary evidence | Reviewed |
| EV-08 | Product administration guide excerpt | Current case packet | Product documentation | Reviewed |
| EV-09 | Subprocessor list | May 2026 | Vendor-provided documentary evidence | Reviewed; currency needs validation |
| EV-10 | Business continuity summary | February 2026 exercise | Documentary evidence / vendor statement | Reviewed |
| EV-11 | Avenloft account configuration | Current case packet | Internal relationship evidence | Reviewed |
| EV-12 | Supplemental stakeholder notes | October 2026 case packet | Internal stakeholder evidence | Reviewed |
| EV-13 | Vendor remediation tracker | Current case packet | Vendor-provided remediation evidence | Reviewed; supporting validation required |

## 5. Detailed Evidence Review

### 5.1 Security Program and Governance

| ID | Vendor claim / observation | Supporting evidence | Evidence assessment | Follow-up |
|---|---|---|---|---|
| EV-14 | Security program is approved annually by executive management. | Q-01; policy index supplied. | Policy index is available, but full policies are not supplied. | Request relevant security policies and approval dates. |
| EV-15 | Vendor workforce users authenticate with SSO and MFA. | Q-02; SOC 2 summary. | Supported at summary level, subject to the SOC 2 exception and scope limitations. | Request current workforce identity-control evidence. |
| EV-16 | Privileged access uses separate roles, MFA, approvals, and quarterly review. | Q-06; SOC 2 summary. | Documentary support exists, but one access-review exception is noted. | Obtain remediation and current privileged-access review evidence. |
| EV-17 | Vendor operates a secure development lifecycle. | Q-08; SOC 2 summary. | Questionnaire claim and summary support exist; detailed SDLC procedure is not supplied. | Request secure development and change-management procedure. |

### 5.2 Infrastructure and Data Protection

| ID | Vendor claim / observation | Supporting evidence | Evidence assessment | Follow-up |
|---|---|---|---|---|
| EV-18 | Service is hosted in AWS U.S. regions. | Vendor security overview. | Vendor statement supplied; infrastructure evidence is not independently detailed. | Confirm current hosting and data-location arrangements. |
| EV-19 | Multi-tenant logical isolation is implemented. | Q-05; architecture narrative. | Architecture narrative only; no specific test evidence supplied. | Request tenant-isolation test evidence. |
| EV-20 | TLS 1.2 or higher protects data in transit. | Q-04; architecture statement; SOC 2 summary. | Supported by vendor documentation and assurance summary at a high level. | Request current technical configuration evidence if needed. |
| EV-21 | AES-256 protects application databases, object storage, and backups at rest. | Q-04; architecture statement; SOC 2 summary. | Supported at summary level; detailed implementation evidence not supplied. | Validate scope and current encryption configuration. |
| EV-22 | Uploaded customer data is retained for 180 days by default. | Q-11; contract and product guide excerpts. | Documentary evidence supplied. | Determine whether shorter retention can be negotiated or configured. |
| EV-23 | Active data deletion begins within 30 days after termination; backups expire within a further 35-day cycle. | Q-12; contract excerpt. | Contractual timeline supplied; no deletion certificate example provided. | Request deletion process and sample deletion confirmation. |

### 5.3 Authentication, Access and Logging

| ID | Vendor claim / observation | Supporting evidence | Evidence assessment | Follow-up |
|---|---|---|---|---|
| EV-24 | TOTP MFA is available to customers. | Q-03; product administration guide. | Product documentation supplied. MFA is not mandatory on Standard plan. | Confirm whether MFA can be enforced for every Avenloft user. |
| EV-25 | SAML SSO is available on Enterprise tier. | Q-03; contract and product information. | Documented plan limitation. | Evaluate commercial and security implications of Enterprise tier. |
| EV-26 | Administrative actions and data-export events are logged. | Vendor security overview; Q-09. | Vendor statement and questionnaire support. | Request representative log fields and event coverage. |
| EV-27 | Standard customers can view 30 days of activity history. | Q-09; Q-19; product guide. | Product documentation supplied. | Determine whether 30 days is sufficient for Avenloft investigations. |
| EV-28 | Vendor retains security logs for 180 days. | Q-09; vendor questionnaire and overview. | Vendor statement; detailed retention configuration evidence not supplied. | Confirm log retention and availability for customer investigations. |
| EV-29 | Eight Avenloft accounts exist; five have TOTP enabled. | Current Avenloft account-state table. | Relationship-specific configuration evidence. | Enable MFA for all active accounts. |
| EV-30 | Four Avenloft accounts can export analytics results; all eight can view uploaded support data. | Current Avenloft account-state table. | Relationship-specific configuration evidence. | Validate business need and least-privilege permissions. |
| EV-31 | Quarterly access reviews are performed informally. | Current Avenloft account-state table; stakeholder notes. | Process described, but no retained certification evidence supplied. | Establish and retain formal quarterly access reviews. |

### 5.4 Vulnerability Management and Independent Testing

| ID | Vendor claim / observation | Supporting evidence | Evidence assessment | Follow-up |
|---|---|---|---|---|
| EV-32 | Weekly external and monthly authenticated vulnerability scans are performed. | Q-07; vendor security overview. | Vendor statement; detailed scan reports not supplied. | Request a recent vulnerability-management summary. |
| EV-33 | Annual independent penetration testing is performed. | Q-07; Q-18; penetration-test summary. | Test summary supplied for May 2026. | Confirm test scope and remediation evidence. |
| EV-34 | Two Medium findings were marked remediated in July 2026. | Penetration-test summary and remediation tracker. | Vendor-reported remediation status. | Request retest evidence for the remediated findings. |
| EV-35 | One Medium finding remains open on a bulk-export endpoint. | Penetration-test summary. | Documented open finding. | Obtain remediation evidence and independent retest confirmation. |
| EV-36 | Target remediation date for the open finding is October 30, 2026. | Penetration-test summary. | Vendor-stated target date, not proof of closure. | Confirm actual status after the target date. |

### 5.5 SOC 2 Type II Assurance

| ID | Evidence / observation | Assessment |
|---|---|---|
| EV-37 | Report period: July 1, 2025 to June 30, 2026. | Relevant historical assurance period; it does not cover later corrective actions. |
| EV-38 | Report issued August 21, 2026. | Report is recent relative to the October 2026 case assessment. |
| EV-39 | Unmodified opinion in the synthetic case report. | Positive assurance indicator, but not blanket approval of this specific relationship. |
| EV-40 | Logical access, change management, security monitoring, incident response, availability, and selected data-protection controls described as in scope. | Scope summary is available; detailed underlying control testing is not supplied. |
| EV-41 | Two of 25 sampled terminated workforce accounts were disabled after 36 and 44 hours. | Documented exception against the vendor's 24-hour target. |
| EV-42 | Vendor changed its HR-to-identity workflow in July 2026. | Management response; post-report-period action not independently tested in supplied summary. |
| EV-43 | Customers remain responsible for their own SupportLens user access and authentication settings. | Important customer responsibility relevant to Avenloft's account configuration. |

**SOC 2 assessment conclusion:**

The supplied summary provides useful independent assurance information and identifies an unmodified opinion.

However, the two delayed workforce account deactivations, the untested July remediation, and the customer responsibility note must be considered in the relationship-specific assessment.

The summary does not establish that every Avenloft-specific risk is adequately controlled.

### 5.6 March 2026 Account Incident

| ID | Incident evidence | Assessment |
|---|---|---|
| EV-44 | Credential-stuffing activity occurred March 14–15, 2026. | Relevant threat evidence for customer account authentication. |
| EV-45 | Nine customer user accounts across four organizations authenticated successfully. | Confirms successful account compromise in the vendor environment. |
| EV-46 | Two compromised accounts had export permissions and exported analytics data. | Demonstrates potential consequences of compromised export-enabled accounts. |
| EV-47 | Vendor reported no administrative or production infrastructure access. | Limits the reported scope; does not eliminate customer-data exposure. |
| EV-48 | Vendor detected abnormal login volume and export activity. | Positive evidence of monitoring and detection. |
| EV-49 | Sessions were revoked, users reset, IP ranges blocked, and affected customers notified. | Reported response actions. |
| EV-50 | Vendor increased MFA enrollment prompts but did not make TOTP mandatory on Standard plan. | Remaining customer authentication concern. |
| EV-51 | Avenloft was not identified as an affected customer. | No direct Avenloft impact reported in the case. |

**Incident assessment conclusion:**

The incident is relevant to Avenloft's account configuration and the vendor's export controls.

It does not establish that Avenloft was compromised or that the open penetration-test finding caused the incident.

MFA availability, optional enrollment, export permissions, and the open rate-limiting finding should be considered together within a consolidated risk scenario.

### 5.7 Contract, Privacy-Related and Subprocessor Evidence

| ID | Evidence / observation | Assessment | Follow-up |
|---|---|---|---|
| EV-52 | Confidentiality clause requires reasonable administrative, technical, and physical safeguards. | General contractual protection exists. | Legal review of adequacy for the relationship. |
| EV-53 | Incident notification is required without undue delay after confirmation. | No fixed hour-based contractual deadline. | Negotiate a defined notification period. |
| EV-54 | No explicit SOC 2 maintenance obligation in current order form. | Assurance expectations are not contractually specific. | Consider annual assurance delivery requirement. |
| EV-55 | No advance notice or objection rights for subprocessor changes. | Contractual oversight gap. | Negotiate advance notice and review rights. |
| EV-56 | Subprocessor list includes AWS, Datadog, and SendGrid. | Vendor-provided list dated May 2026. | Confirm list is current before renewal. |
| EV-57 | Standard plan retains data for 180 days. | Longer default retention than may be necessary for Avenloft's purpose. | Assess shorter retention options. |
| EV-58 | Active-data deletion begins within 30 days after termination; backup copies expire within a further 35 days. | Contractual timeline exists; deletion evidence is not supplied. | Obtain deletion confirmation and backup lifecycle details. |
| EV-59 | Annual right to request current security documentation; no on-site audit right. | Limited assurance and assessment rights. | Consider stronger documentation and cooperation clauses. |
| EV-60 | Enterprise tier costs approximately $24,600 annually compared with $18,600 for Standard. | Additional cost of approximately $6,000 per year. | Evaluate whether added SSO, configurable retention, and longer customer-visible history are justified. |

### 5.8 Business Continuity Evidence

| ID | Vendor statement | Supporting evidence | Assessment |
|---|---|---|---|
| EV-61 | Nightly backups are performed. | Vendor security overview and BCP summary. | Vendor-reported control. |
| EV-62 | Recovery Point Objective is 24 hours. | BCP summary. | Documented recovery objective. |
| EV-63 | Recovery Time Objective is 8 hours. | BCP summary. | Documented recovery objective. |
| EV-64 | Restore exercise completed in February 2026. | Exercise summary. | Evidence of a completed exercise; detailed results and remediation actions should be reviewed if material. |

### 5.9 Security Program Change Notifications

| ID | Vendor claim | Supporting evidence | Assessment |
|---|---|---|---|
| EV-65 | Material changes to the security program are communicated through customer notices when they affect contracted services. | Q-20 response. | Self-attestation only; no corresponding contract clause located. |

## 6. Evidence Quality Summary

| Evidence area | Evidence strength | Main limitation |
|---|---|---|
| Security program | Partial | Full policies not supplied. |
| Encryption | Moderate | Architecture statement and SOC 2 summary; detailed technical evidence not supplied. |
| Tenant isolation | Weak / incomplete | Architecture narrative only; no test evidence. |
| Workforce identity | Moderate | SOC 2 exception and untested remediation. |
| Customer authentication | Documentary | MFA optional on Standard plan; three Avenloft accounts not enrolled. |
| Vulnerability management | Partial | Test summary supplied; one Medium finding remains open. |
| Incident response | Moderate | Incident summary supplied; underlying detailed investigation report not included. |
| Logging | Partial | Retention and customer-visible history differ; detailed log samples not supplied. |
| Data retention and deletion | Documentary | No deletion certificate example supplied. |
| Subprocessors | Partial | List dated May 2026; current status unconfirmed. |
| Business continuity | Partial | Exercise summary supplied; detailed recovery results not included. |
| Contractual security obligations | Partial | Notification, subprocessor, assurance, and assessment terms need review. |
| Avenloft user access | Relationship-specific | Informal reviews with no retained certification evidence. |

## 7. Priority Evidence Gaps

| Gap ID | Evidence gap | Why it matters | Required evidence |
|---|---|---|---|
| GAP-01 | No tenant-isolation test evidence. | A multi-tenant service processes multiple customers' information. | Independent tenant-isolation test or relevant security assessment. |
| GAP-02 | July 2026 workforce offboarding remediation not independently tested. | The SOC 2 summary records delayed deactivation of sampled terminated accounts. | Post-remediation test results or independent validation. |
| GAP-03 | Open bulk-export rate-limiting finding lacks independent retest evidence. | An authenticated export-enabled account may be able to exploit the weakness. | Closure evidence and independent retest letter. |
| GAP-04 | Three Avenloft accounts lack TOTP MFA. | Customer account compromise could expose uploaded support information. | Evidence of MFA enrollment or enforceable MFA configuration. |
| GAP-05 | Avenloft access reviews lack retained certification. | Excessive or outdated permissions may persist. | Completed and approved user-access certification. |
| GAP-06 | Current subprocessor list is unconfirmed. | Avenloft needs visibility into parties processing its information. | Updated dated subprocessor list and change process. |
| GAP-07 | No fixed contractual incident-notification deadline. | Delayed notification may impair Avenloft's response. | Proposed contractual notification clause. |
| GAP-08 | No deletion certificate example. | Avenloft needs confidence that data is deleted at termination. | Sample deletion certificate or documented deletion procedure. |
| GAP-09 | Data-field minimization capability is unconfirmed. | Unnecessary support information may be transferred. | Vendor confirmation and test of reduced-field export. |
| GAP-10 | No documented proof of quarterly Avenloft access review. | Informal review may not demonstrate control operation. | Dated review records and approval evidence. |

## 8. Evidence That Reduces Concern

The following evidence provides positive indicators and should be recognized in the assessment:

1. The synthetic SOC 2 Type II summary reports an unmodified opinion.
2. The report describes logical access, change management, security monitoring, incident response, availability, and selected data-protection controls as in scope.
3. The penetration-test summary reports zero Critical and zero High findings.
4. The vendor reports encryption in transit and at rest.
5. The vendor reports administrative-action and data-export logging.
6. The March incident was detected and responded to, and affected customers were notified.
7. No direct Salesforce integration or vendor credentials into Avenloft systems are identified.
8. SupportLens is not operationally essential to Avenloft Relay or frontline support.

These positive indicators do not automatically close the identified gaps.

## 9. Vendor Statements Requiring Validation

The following statements should not be treated as independently established facts without supporting evidence:

- Tenant isolation is enforced at the application and database access layers.
- The July 2026 workforce offboarding change corrected the SOC 2 exception.
- The remaining bulk-export finding will be remediated by October 30, 2026.
- Weekly and monthly vulnerability scans operate as described.
- Material security-program changes are communicated to customers.
- The May 2026 subprocessor list remains current.
- Reduced-field exports can or cannot be supported without affecting reporting.

## 10. Evidence Review Conclusion

The evidence package provides a useful basis for assessing CobaltCedar SupportLens.

It includes a synthetic SOC 2 Type II summary, penetration-test summary, vendor security questionnaire, incident summary, contractual excerpts, product documentation, and business continuity information.

However, the evidence also identifies unresolved concerns:

- Delayed vendor workforce account deactivation.
- Untested post-report-period remediation.
- An open Medium bulk-export rate-limiting finding.
- Incomplete customer MFA enrollment.
- Limited evidence of tenant-isolation testing.
- Contractual gaps concerning notification and subprocessor changes.
- Incomplete proof of Avenloft's periodic access reviews.

The assessment should proceed using the evidence currently supplied while recording these limitations as validation requirements.

No proposed control or remediation should be treated as implemented until supporting evidence confirms it.

## 11. Source

Primary source: Avenloft Systems Group, GRC-TPRM-003, Third-Party Vendor Risk Assessment Case File, October 12, 2026.

Relevant sections:

- Vendor Security Overview and Avenloft Account State — Page 6
- Vendor Security Questionnaire, Part 1 — Page 7
- Vendor Security Questionnaire, Part 2 — Page 8
- Synthetic SOC 2 Type II and Penetration-Test Summaries — Page 9
- March 2026 Account Incident — Page 10
- Contract and Data-Handling Excerpts — Page 11
- Supplemental Stakeholder Notes and Open Questions — Page 12
