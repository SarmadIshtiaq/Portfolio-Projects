# Evidence Gaps and Validation Plan

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Review type:** Third-party due diligence evidence-gap assessment  
**Assessment basis:** Fictional Avenloft vendor case packet

## 1. Purpose

This document consolidates the evidence gaps identified during the third-party vendor review of CobaltCedar Analytics, Inc.

The objective is to distinguish between:

- Evidence supplied and reasonably supported.
- Vendor statements that remain self-attested.
- Findings for which remediation has not been independently verified.
- Missing evidence requiring follow-up.
- Internal Avenloft controls that require confirmation.

The purpose is not to assume that missing evidence proves a control failure. Instead, evidence gaps are treated as limitations on Avenloft's ability to establish the effectiveness of relevant safeguards.

## 2. Evidence assessment principles

The review uses the following classifications:

| Classification | Meaning |
|---|---|
| Supported | Supplied evidence provides reasonable support for the stated claim within its scope |
| Partially supported | Some evidence exists, but important details or independent validation are missing |
| Self-attested | The statement is primarily based on vendor representation |
| Not sufficiently evidenced | The available material does not adequately establish the claim |
| Internal validation required | Avenloft must verify its own configuration, process or control |

An independent report or certification should not be treated as proof of every security requirement. Its scope, reporting period, exceptions and customer responsibilities must also be considered.

## 3. Consolidated evidence gaps

| ID | Area | Evidence gap | Why it matters | Priority |
|---|---|---|---|---|
| EG-01 | SOC 2 | Full SOC 2 Type II report not supplied | Detailed scope, control testing and exceptions cannot be fully examined | High |
| EG-02 | SOC 2 | July 2026 workforce offboarding workflow change not independently tested | Remediation effectiveness remains unverified | High |
| EG-03 | Penetration testing | Bulk-export rate-limiting finding has no supplied closure or retest evidence | Unauthorized export exposure may remain | High |
| EG-04 | Penetration testing | Two Medium findings marked remediated without independent retest evidence | Closure status relies on vendor reporting | Medium |
| EG-05 | Vulnerability management | Weekly external and monthly authenticated scan reports not supplied | Scan coverage and remediation performance cannot be confirmed | Medium |
| EG-06 | Incident response | Complete March 2026 incident report and root-cause analysis not supplied | Cause, impact and corrective actions cannot be independently assessed | High |
| EG-07 | Customer authentication | Standard-plan MFA is optional | Customer accounts may remain vulnerable to credential-based attacks | High |
| EG-08 | Customer access | Formal retained access certification is not evidenced | Unnecessary access may remain active | Medium |
| EG-09 | Data retention | Standard-plan default retention is 180 days | Customer data remains available longer than may be necessary | Medium |
| EG-10 | Data deletion | No sample deletion certificate supplied | Completion of deletion cannot be independently verified | Medium |
| EG-11 | Contract | No fixed hour-based incident notification deadline identified | Avenloft may receive notification later than operationally necessary | High |
| EG-12 | Subprocessors | No clear advance objection rights established | Avenloft has limited ability to respond to unacceptable changes | Medium |
| EG-13 | Subprocessors | May 2026 list requires confirmation of currency and completeness | Processing arrangements may have changed | Medium |
| EG-14 | Tenant isolation | Architecture narrative supplied without separate test evidence | Effectiveness of logical tenant separation is not independently established | High |
| EG-15 | Logging | Customer-visible history is 30 days while vendor security logs are reportedly retained for 180 days | Avenloft's investigation visibility and evidence access may be limited | Medium |
| EG-16 | Business continuity | Backup and recovery information is supplied, but detailed test evidence is limited | Recovery capability requires further validation | Medium |

Priority represents the analyst's proposed due diligence priority, not a formal vendor risk rating.

## 4. Validation plan

| ID | Validation activity | Requested evidence or action | Responsible function |
|---|---|---|---|
| VAL-01 | Review SOC 2 scope and exceptions | Full report, system description and testing details | GRC |
| VAL-02 | Validate workforce offboarding remediation | Post-July workflow test evidence | GRC / Vendor Security |
| VAL-03 | Validate bulk-export remediation | Closure evidence and independent retest | IT / GRC |
| VAL-04 | Review remaining penetration test findings | Original findings and retest results | GRC |
| VAL-05 | Assess vulnerability management | Recent scan summaries and remediation metrics | GRC / Vendor Security |
| VAL-06 | Review credential-stuffing incident | Incident report and root-cause analysis | GRC / Information Security |
| VAL-07 | Verify Avenloft account MFA | Configuration evidence for all eight accounts | IT |
| VAL-08 | Review Avenloft export permissions | Current user-to-permission listing and business justification | Customer Success / IT |
| VAL-09 | Confirm access review process | Documented access certification and review record | Customer Success |
| VAL-10 | Validate retention and deletion | Retention configuration and deletion documentation | Legal & Privacy / GRC |
| VAL-11 | Review incident notification terms | Executed contract and proposed amendment | Legal & Privacy |
| VAL-12 | Confirm subprocessor governance | Current list and contractual notification provisions | Procurement / Legal |
| VAL-13 | Review tenant isolation assurance | Relevant architecture and independent testing evidence | IT / GRC |
| VAL-14 | Review logging and investigation support | Log access, retention and export capabilities | IT / GRC |
| VAL-15 | Validate recovery capability | Relevant backup restoration and recovery test evidence | IT / Vendor |

The responsible functions are proposed assignments based on the case stakeholders. They are not confirmed approvals or completed actions.

## 5. Evidence that would reduce concern

The following evidence would materially improve Avenloft's confidence:

1. A full current SOC 2 Type II report with relevant scope and exceptions reviewed.
2. Independent evidence confirming the effectiveness of the revised workforce offboarding process.
3. Successful independent retesting of the bulk-export rate-limiting finding.
4. A complete incident report explaining the March credential-stuffing event and corrective actions.
5. Configuration evidence confirming MFA for every Avenloft account.
6. A documented review showing that export privileges are limited to justified users.
7. A current subprocessor list with clear processing purposes.
8. Contractual amendments establishing appropriate notification, deletion and subprocessor requirements.
9. Evidence supporting tenant isolation and backup recovery capabilities.

## 6. Vendor statements requiring validation

The following claims should not be treated as independently established solely because they appear in vendor documentation.

| Vendor statement | Current evidence limitation | Validation approach |
|---|---|---|
| Logical tenant isolation | Architecture narrative without separate test evidence | Obtain independent assurance or relevant technical testing |
| Workforce offboarding workflow improved | July 2026 process change not independently tested | Request post-change test results |
| Two Medium penetration test findings remediated | No independent retest evidence | Review closure records and retest results |
| Weekly and monthly vulnerability scanning | Scan reports not supplied | Request recent scan summaries |
| Incident response actions completed | No complete investigation report supplied | Review incident report and root-cause analysis |
| Data deletion begins within stated timelines | No sample deletion certificate | Request deletion documentation |
| Backup restoration capability | Detailed recovery test evidence limited | Review recent recovery exercise results |

## 7. Internal Avenloft validation requirements

Due diligence must also examine Avenloft's own use of the service.

The case packet identifies several internal validation needs:

- Confirm all eight SupportLens accounts are assigned to current authorized users.
- Enable TOTP MFA for the three accounts that do not currently have it.
- Confirm whether all four export-enabled accounts require that privilege.
- Remove unnecessary export access.
- Establish a documented periodic access review.
- Review the weekly Salesforce CSV export process.
- Ensure credentials and unnecessary sensitive information are excluded from uploaded free-text data.
- Confirm that data retention aligns with the business purpose.

These are proposed actions. They should only be marked complete after evidence is obtained.

## 8. Renewal decision dependencies

The evidence gaps should inform the renewal decision.

The following items should receive particular attention:

### Before renewal approval

- Validate the bulk-export rate-limiting finding's current status.
- Review the full SOC 2 report and relevant exceptions.
- Obtain sufficient information about the March incident and corrective actions.
- Confirm an acceptable MFA and export-access configuration for Avenloft.
- Resolve material contractual concerns through Legal and Privacy review.

### During renewal negotiation

- Establish a defined incident notification deadline.
- Agree appropriate data retention and deletion requirements.
- Obtain current subprocessor information and suitable change-notification rights.
- Clarify ongoing independent assurance expectations.
- Agree evidence access and cooperation requirements for material security concerns.

### During ongoing monitoring

- Review material changes to the vendor's security posture.
- Reassess significant vulnerabilities and incidents.
- Review access and export permissions periodically.
- Track outstanding remediation commitments.
- Reassess the vendor when the service, data scope or business dependency changes.

These are proposed due diligence requirements, not evidence that the vendor has agreed to them.

## 9. Overall evidence assessment

**Overall evidence position: Partially supported; material validation remains necessary.**

CobaltCedar has supplied useful assurance information, including a SOC 2 Type II summary, penetration test summary, security questionnaire responses, incident information, and service documentation.

However, several important areas remain dependent on vendor statements or incomplete evidence.

The most significant validation needs concern:

1. The open or unverified bulk-export rate-limiting finding.
2. Workforce access remediation following SOC 2 exceptions.
3. The March 2026 credential-stuffing incident.
4. Tenant isolation assurance.
5. Avenloft's own MFA and export-access configuration.
6. Contractual notification, retention, deletion and subprocessor provisions.

The absence of evidence should be recorded as an assurance limitation. It should not automatically be described as proof that the vendor has no relevant control.

## 10. Relationship to the overall vendor assessment

This document consolidates evidence limitations identified in:

- Vendor Evidence Register.
- Security Questionnaire Review.
- SOC 2 Report Review.
- Penetration Test Review.
- Security Incident Review.
- Contract and Privacy Review.

Its findings should feed into the vendor risk scenarios, findings and remediation tracker, and final vendor decision memo.

---

**Important:** CobaltCedar Analytics, Inc., SupportLens and all case information in this portfolio project are fictional training materials. Validation activities and ownership assignments are analyst recommendations, not completed vendor actions.