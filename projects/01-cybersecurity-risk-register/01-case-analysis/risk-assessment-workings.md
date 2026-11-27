# Avenloft Systems Group — Risk Assessment Working Paper

**Project ID:** GRC-RISK-001  
**Document:** Inherent and Residual Risk Assessment  
**Organisation:** Avenloft Systems Group (Fictional)  
**Assessment Basis:** Case packet evidence and Avenloft risk criteria  
**Method:** NIST SP 800-30 Rev. 1, Appendix I, Table I-2  
**Status:** Provisional analyst assessment; validation pending

## 1. Purpose

This document records the proposed inherent and residual risk ratings for the ten candidate cybersecurity risk scenarios.

It explains:

- Why each likelihood rating was selected.
- Why each impact rating was selected.
- Which existing controls were considered.
- Whether current controls reduce likelihood, impact, or both.
- Why the residual risk remains at its proposed level.
- Which assumptions require validation.
- Which risk treatment is recommended.

These are independent analyst judgements based on the fictional case evidence. They are not scores prescribed by the case packet.

**Primary source:** [Avenloft Cybersecurity Risk Register Case Packet — Risk Assessment Method, pages 10–13](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 2. Rating Method

### 2.1 Qualitative levels

Both likelihood and impact use five levels:

- Very Low
- Low
- Moderate
- High
- Very High

### 2.2 Risk determination matrix

| Likelihood / Impact | Very Low | Low | Moderate | High | Very High |
|---|---|---|---|---|---|
| Very High | Very Low | Low | Moderate | High | Very High |
| High | Very Low | Low | Moderate | High | Very High |
| Moderate | Very Low | Low | Moderate | Moderate | High |
| Low | Very Low | Low | Low | Low | Moderate |
| Very Low | Very Low | Very Low | Very Low | Low | Low |

Do not multiply the qualitative values or introduce an invented numerical formula.

**Source:** [Avenloft Case Packet — Risk Determination Matrix, page 11](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11).

### 2.3 Rating sequence

1. Assess inherent likelihood and impact without giving credit to existing controls.
2. Determine the inherent risk level using the matrix.
3. Identify the current safeguards.
4. Assess whether each safeguard reduces likelihood, impact, or both.
5. Assess residual likelihood and impact.
6. Determine residual risk using the same matrix.
7. Compare residual risk with Avenloft's risk appetite and tolerance.
8. Recommend a treatment and identify information requiring validation.

**Source:** [Avenloft Case Packet — Risk Assessment Method, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 3. Proposed Risk Rating Summary

| Risk ID | Risk Title | Inherent Likelihood | Inherent Impact | Inherent Level | Residual Likelihood | Residual Impact | Residual Level |
|---|---|---|---|---|---|---|---|
| R-001 | Production Recovery and Incident Readiness | Moderate | High | Moderate | Moderate | High | Moderate |
| R-002 | Partner Portal Vulnerability Exploitation | Moderate | Moderate | Moderate | Moderate | Moderate | Moderate |
| R-003 | Contractor Access After Contract End | Moderate | Moderate | Moderate | Moderate | Moderate | Moderate |
| R-004 | Legacy Privileged Access and Administrator Accountability | Moderate | Moderate | Moderate | Low | Moderate | Low |
| R-005 | Third-Party Access to Customer Support Data | Moderate | Moderate | Moderate | Moderate | Moderate | Moderate |
| R-006 | Phishing and Workforce Account Compromise | Moderate | Moderate | Moderate | Low | Moderate | Low |
| R-007 | SaaS Administrative Log Retention | Moderate | Moderate | Moderate | Moderate | Moderate | Moderate |
| R-008 | Customer-Support Attachments on Local Devices | Moderate | Moderate | Moderate | Moderate | Moderate | Moderate |
| R-009 | Unassigned Ownership of Engineering Build Servers | Low | Moderate | Low | Low | Moderate | Low |
| R-010 | Unmanaged Consumer Generative-AI Use | Moderate | Moderate | Moderate | Low | Moderate | Low |

The ratings are provisional. The assumptions and validation requirements below must be considered before finalisation.

---

## 4. Individual Risk Assessment Rationales

### R-001 — Production Recovery and Incident Readiness

**Evidence:** OBS-01 and OBS-09.

**Inherent likelihood: Moderate**

A major production disruption is a plausible threat scenario for a cloud-hosted SaaS business. Avenloft has not documented a full application-and-database restore exercise for 14 months, and its recovery runbook refers to the pre-migration network layout. The last ransomware tabletop occurred 22 months ago.

The case does not provide an outage frequency or failed recovery result. Moderate is therefore a working judgement, not a measured probability.

**Inherent impact: High**

Avenloft considers production availability business-critical and has low tolerance for outages exceeding four hours during business operations. Failure to restore Avenloft Relay within the expected recovery period could materially affect customer operations and service commitments.

**Inherent risk: Moderate**

Moderate likelihood combined with High impact produces Moderate under the supplied matrix.

**Existing controls**

- Daily production backups.
- Protected backup copies.
- Backup-job monitoring.
- An incident-response plan.
- Current incident contacts and an executive escalation tree.

**Residual likelihood: Moderate**

The backup and incident-response safeguards exist. However, the available evidence does not demonstrate a recent successful full restore or an exercise covering the current AWS environment and identity-provider loss. The controls therefore do not justify reducing the working likelihood rating.

**Residual impact: High**

The current safeguards do not remove the business impact of a prolonged production outage.

**Residual risk: Moderate**

Moderate likelihood combined with High impact produces Moderate.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Conduct a full application-and-database restore test.
2. Update the recovery runbook to reflect the current AWS architecture.
3. Conduct a ransomware tabletop covering AWS and primary identity-provider loss.
4. Record test outcomes, recovery times, and unresolved dependencies.

**Proposed risk owner:** Priya Nair, VP Engineering.

**Validation required**

- Confirm the last successful full restore.
- Confirm recovery performance against the four-hour tolerance.
- Verify current application, database, and identity-provider dependencies.

**Evidence:** [OBS-01 and OBS-09, pages 6 and 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

### R-002 — Partner Portal Vulnerability Exploitation

**Evidence:** OBS-02.

**Inherent likelihood: Moderate**

The vulnerability is critical, internet-facing, and has remained open for 32 days. These conditions support a credible exploitation scenario. However, the case supplies no evidence of exploitation, attack attempts, or detailed exploitability.

Moderate is a provisional likelihood judgement.

**Inherent impact: Moderate**

The vulnerability affects the Partner Portal and may disrupt partner access or expose information available through the portal. The case does not specify the full data scope or technical privileges available through the affected component.

Moderate is used until that information is validated.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- Weekly vulnerability scanning.
- Temporary WAF mitigation.
- Engineering regression testing of the vendor patch.

**Residual likelihood: Moderate**

The WAF rule may reduce exposure, but the case does not provide evidence of its effectiveness. The permanent patch remains delayed. No reduction in likelihood is therefore credited in this provisional assessment.

**Residual impact: Moderate**

The temporary WAF rule does not establish that the potential business impact has been eliminated.

**Residual risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Recommended treatment:** Mitigate urgently.

**Recommended actions**

1. Complete testing and deployment of a permanent patch.
2. Validate the technical coverage and effectiveness of the WAF rule.
3. Review and document the expired exception.
4. Set a named remediation owner and target date.
5. Escalate the tolerance conflict to the CISO.

**Proposed risk owner:** Priya Nair, VP Engineering.

**Validation required**

- Confirm the vulnerability identifier and affected component.
- Establish affected data and service dependencies.
- Validate the WAF mitigation.
- Confirm whether a current written exception exists.

**Important tolerance consideration**

Avenloft does not accept a known critical internet-facing vulnerability beyond 30 days without a current written exception and compensating controls. The observed 32-day period and expired exception conflict with this direction.

The risk remains Moderate under the matrix, but it requires prompt action because of the tolerance conflict.

**Evidence:** [OBS-02, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6) and [Risk Appetite, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

### R-003 — Contractor Access After Contract End

**Evidence:** OBS-03.

**Inherent likelihood: Moderate**

Three contractors retained GitHub access for 4, 6, and 9 days after their contract end dates. This demonstrates that the contractor offboarding process has failed to remove access promptly in multiple observed cases.

**Inherent impact: Moderate**

Unauthorised access to engineering repositories could expose source code or allow changes to software-development information. The case does not report unauthorised activity in the sampled logs.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- GitHub SSO for workforce identities.
- Automated employee offboarding through Workday and Okta.
- The three identified contractor accounts are now disabled.

**Residual likelihood: Moderate**

The identified accounts have been disabled, but the underlying contractor offboarding process still depends on a sponsor submitting a ticket. The employee automation does not currently cover contractor offboarding. SSO does not automatically remove access when a contract ends.

The recurring process weakness remains.

**Residual impact: Moderate**

The potential impact to engineering repositories remains relevant even after the identified accounts have been disabled.

**Residual risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Define a formal contractor end-date notification process.
2. Require access removal when the contract ends.
3. Introduce automated or tracked contractor deprovisioning.
4. Reconcile contractor records with GitHub access.
5. Review overdue access-removal cases.

**Proposed risk owner:** Priya Nair, VP Engineering, with People Operations and IT support.

**Validation required**

- Confirm the total contractor population.
- Identify systems accessible to contractors.
- Verify whether all contractor access is covered by an end-date process.
- Confirm the adequacy of the sampled activity logs.

**Evidence:** [OBS-03, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

### R-004 — Legacy Privileged Access and Administrator Accountability

**Evidence:** OBS-04 and OBS-10.

**Inherent likelihood: Moderate**

The legacy gateway does not support MFA and uses local credentials. The two appliances also use a shared administrator account. These conditions create a credible opportunity for unauthorised or untraceable administrative activity.

**Inherent impact: Moderate**

Unauthorised appliance changes could affect network administration and infrastructure reliability. The case does not document a compromise or a resulting outage.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- Access restricted to company VPN source addresses.
- Six authorised administrators.
- Password rotation through the team vault.
- Shared credentials stored in the privileged credential vault.
- Vault check-out logging.
- Access limited to the network administration team.

**Residual likelihood: Low**

The restricted VPN access, limited administrator population, and controlled credential retrieval reduce the likelihood of unauthorised access.

These safeguards support a reduction from Moderate to Low. They do not eliminate the authentication and accountability weaknesses.

**Residual impact: Moderate**

The potential business consequences of an unauthorised network-appliance change remain.

**Residual risk: Low**

Low likelihood combined with Moderate impact produces Low.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Move administrative access to an MFA-supported gateway.
2. Replace or upgrade the legacy appliances where technically feasible.
3. Improve individual administrator attribution.
4. Review vault records and appliance activity.
5. Document interim safeguards until replacement is completed.

**Proposed risk owner:** Marcus Holloway, Director IT & Workplace Technology.

**Validation required**

- Confirm whether VPN authentication requires MFA.
- Review appliance and gateway versions.
- Confirm the timeline for appliance replacement.
- Assess how vault logs correlate with device activity.

**Important tolerance consideration**

Avenloft has low tolerance for weak privileged authentication and untraceable administrative activity. The Low residual rating does not remove the need for treatment.

**Evidence:** [OBS-04, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6), [OBS-10, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8), and [Risk Appetite, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

### R-005 — Third-Party Access to Customer Support Data

**Evidence:** OBS-05.

**Inherent likelihood: Moderate**

The vendor receives periodic support-ticket exports, but the onboarding process did not require a security assessment because annual spend was below the threshold. The actual vendor control environment has not been assessed in the supplied evidence.

**Inherent impact: Moderate**

The exports may contain customer information. The exact fields and sensitivity are not supplied, so a higher impact rating cannot be justified without validation.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- Contractual confidentiality language.
- A procurement workflow that requires security review for vendors above a spend threshold.

**Residual likelihood: Moderate**

The confidentiality clause is a safeguard, but the case provides no security questionnaire, architecture review, or formal vendor risk rating. The assessment therefore gives no reduction in likelihood.

**Residual impact: Moderate**

The actual contents of the exports and the vendor's processing arrangements remain unknown.

**Residual risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Identify the exact data fields in support-ticket exports.
2. Perform a vendor security assessment.
3. Review vendor architecture, access, and data-handling safeguards.
4. Confirm retention, deletion, and subcontractor arrangements.
5. Add data sensitivity to vendor classification and review routing.

**Proposed risk owner:** Lena Ortiz, VP Customer Success, with Procurement coordination.

**Validation required**

- Identify the exported data.
- Confirm where data is stored and processed.
- Review the vendor's security evidence.
- Confirm retention and deletion requirements.

**Evidence:** [OBS-05, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7) and [Procurement stakeholder note, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

### R-006 — Phishing and Workforce Account Compromise

**Evidence:** OBS-06.

**Inherent likelihood: Moderate**

The company-wide simulation click rate is 6%, and Customer Success recorded 14%. Fifty-six employees are overdue for training, and repeated simulation failures do not trigger mandatory remedial training.

These observations support a plausible workforce phishing scenario. They do not establish a real compromise.

**Inherent impact: Moderate**

A successful account compromise could provide unauthorised access to workforce systems or information. The case does not establish that a real phishing incident caused material impact.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- Email filtering.
- Endpoint protection.
- Automated training reminders.
- Okta SSO and MFA for standard workforce applications.

**Residual likelihood: Low**

Email filtering, endpoint protection, SSO, and MFA reduce the likelihood that a phishing attempt results in a successful account compromise.

The high Customer Success simulation click rate and absence of mandatory remedial training prevent the risk from being treated as eliminated.

**Residual impact: Moderate**

If an account is successfully compromised, the potential business impact remains.

**Residual risk: Low**

Low likelihood combined with Moderate impact produces Low.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Require remedial training for repeat simulation failures.
2. Review the Customer Success phishing results.
3. Monitor phishing reports and repeat failures.
4. Confirm MFA coverage for relevant workforce applications.
5. Track overdue training to completion.

**Proposed risk owner:** Marcus Holloway, Director IT & Workplace Technology, with Security program support.

**Validation required**

- Identify repeat simulation failures.
- Review actual phishing incident history.
- Confirm MFA coverage and account-protection exceptions.
- Verify remedial training completion.

**Evidence:** [OBS-06, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7) and [Technology and Security Baseline, page 5](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=5).

### R-007 — SaaS Administrative Log Retention

**Evidence:** OBS-07.

**Inherent likelihood: Moderate**

A security incident could require investigation after detailed administrative logs are no longer available. Salesforce and GitHub detailed exports are retained for 30 days, while the standard specifies 180 days for high-value systems.

**Inherent impact: Moderate**

Missing historical logs may limit the ability to reconstruct administrative activity, establish accountability, and determine the scope of an incident.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- Native Salesforce audit logging.
- Native GitHub audit logging.
- Thirty days of detailed administrative exports.
- Centralised AWS production logging.

**Residual likelihood: Moderate**

The 30-day log window provides investigation evidence for recent activity. It does not address the loss of older detailed records if an incident is detected after the retention period.

No reduction is applied in this provisional assessment.

**Residual impact: Moderate**

The potential impact on investigation and accountability remains.

**Residual risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Recommended treatment:** Mitigate, subject to system classification validation.

**Recommended actions**

1. Confirm whether Salesforce and GitHub are classified as high-value systems.
2. Determine which administrative events are included in the detailed exports.
3. Evaluate extended retention or centralised export storage.
4. Establish monitoring and evidence-retrieval requirements.

**Proposed risk owner:** Needs validation. The named Salesforce and GitHub system owners are not identified in the case packet. Aaron Bell owns GRC reporting and register governance, but should not automatically become the operational risk owner.

**Validation required**

- Confirm system classification.
- Identify system owners.
- Review log completeness and retrieval options.
- Confirm whether any longer-term copy already exists.

**Evidence:** [OBS-07, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7) and [Technology Environment, page 5](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=5).

### R-008 — Customer-Support Attachments on Local Devices

**Evidence:** OBS-08.

**Inherent likelihood: Moderate**

Support agents download attachments to local laptops approximately 18 times in a typical month. No DLP rule prevents local copies or requires deletion after case closure. A deletion-verification workflow is not available.

**Inherent impact: Moderate**

Customer attachments may contain information relevant to support cases. Uncontrolled retention or unauthorised access could affect customer confidentiality and trust. The exact content of each attachment is not supplied.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- Role-based access to support tickets.
- Disk encryption on managed laptops.
- Endpoint detection and response.
- Review of unusual export volumes when alerted.

**Residual likelihood: Moderate**

The endpoint safeguards reduce certain device-related exposures. They do not ensure that local attachments are deleted after a case closes. No reduction is applied for the deletion-control gap.

**Residual impact: Moderate**

The customer-data exposure concern remains until attachment contents and retention practices are validated.

**Residual risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Establish an approved attachment-handling process.
2. Define where local copies may be stored.
3. Introduce deletion requirements and verification.
4. Evaluate DLP or other controls for sensitive attachments.
5. Review unusual downloads and retained copies.

**Proposed risk owner:** Lena Ortiz, VP Customer Success.

**Validation required**

- Determine the data types contained in attachments.
- Confirm whether all downloads use managed devices.
- Review local storage and deletion practices.
- Determine whether download activity is recorded.

**Evidence:** [OBS-08, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7) and [Customer Success stakeholder note, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

### R-009 — Unassigned Ownership of Engineering Build Servers

**Evidence:** OBS-11.

**Inherent likelihood: Low**

Eighteen Linux build servers have no documented business owner in the asset inventory. However, Engineering states that the servers are patched through the standard image pipeline. The case does not report a patch failure or compromise.

Low is a cautious judgement based on the ownership gap and available safeguards.

**Inherent impact: Moderate**

An unowned server could delay remediation or accountability if a security or operational issue occurs. The servers support non-production software builds, so the case does not support treating them as direct customer-facing production systems.

**Inherent risk: Low**

Low likelihood combined with Moderate impact produces Low.

**Existing controls**

- Standard image-pipeline patching, as reported by Engineering.
- Management through the engineering cloud account.
- Non-production role.

**Residual likelihood: Low**

The image pipeline and engineering management reduce some exposure. The lack of a documented owner remains and prevents a further reduction.

**Residual impact: Moderate**

The potential effect on engineering build processes remains, but the servers are described as non-production.

**Residual risk: Low**

Low likelihood combined with Moderate impact produces Low.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Assign a documented owner to each server or an accountable service owner.
2. Add ownership and criticality to the asset inventory.
3. Confirm patch-pipeline coverage.
4. Identify dependencies on source-code and deployment workflows.

**Proposed risk owner:** Priya Nair, VP Engineering.

**Validation required**

- Confirm server owners and technical administrators.
- Verify image-pipeline coverage.
- Identify business dependencies.
- Confirm whether the inventory percentage and ownership records are current.

**Evidence:** [OBS-11, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

### R-010 — Unmanaged Consumer Generative-AI Use

**Evidence:** OBS-12.

**Inherent likelihood: Moderate**

Employees have access to consumer generative-AI accounts for low-sensitivity drafting, but Avenloft has no formal AI inventory or standard risk-intake process. The process does not provide complete visibility into actual use or data submitted.

The case does not state that confidential customer information has been entered into an unapproved AI service.

**Inherent impact: Moderate**

If customer-confidential information is submitted to an unapproved service, customer confidentiality and trust could be affected.

**Inherent risk: Moderate**

Moderate likelihood combined with Moderate impact produces Moderate.

**Existing controls**

- Leadership instruction not to enter customer-confidential information into unapproved AI tools.
- The proposed Customer Success AI pilot is paused pending GRC review.

**Residual likelihood: Low**

The explicit instruction and paused pilot reduce the likelihood of unauthorised customer-data use. However, the absence of an AI inventory and intake process leaves uncertainty about actual employee activity.

**Residual impact: Moderate**

The potential customer-confidentiality impact remains if restricted data is submitted.

**Residual risk: Low**

Low likelihood combined with Moderate impact produces Low.

**Recommended treatment:** Mitigate.

**Recommended actions**

1. Establish an AI use-case inventory.
2. Introduce a standard AI-risk intake and review process.
3. Define approved tools and permitted data categories.
4. Communicate data-handling requirements to employees.
5. Review consumer AI usage and reassess the proposed Customer Success pilot separately.

**Proposed risk owner:** Needs validation. The case identifies Maya Chen as the executive owner of the security program and Aaron Bell as owner of GRC governance and reporting, but does not name a formal AI governance owner.

**Validation required**

- Identify consumer AI services used by employees.
- Confirm whether employees submit only low-sensitivity information.
- Review service terms and data handling.
- Appoint an accountable AI governance owner.

**Evidence:** [OBS-12, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8) and [Risk Appetite, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

---

## 5. Consolidated Control Effect Assessment

| Risk ID | Main Existing Safeguards | Proposed Likelihood Change | Reason |
|---|---|---|---|
| R-001 | Daily backups, protected copies, incident contacts | No change | No recent full restore or current-environment exercise demonstrates recovery effectiveness. |
| R-002 | Weekly scanning, temporary WAF rule | No change | WAF effectiveness is not evidenced; patch remains delayed and exception expired. |
| R-003 | SSO, identified accounts disabled | No change | Contractor offboarding still depends on manual sponsor action. |
| R-004 | VPN restriction, six authorised administrators, vault | Moderate to Low | Restricted access and controlled credential retrieval reduce exposure. |
| R-005 | Confidentiality clause | No change | Contract wording does not establish the vendor's technical security effectiveness. |
| R-006 | Email filtering, EDR, SSO/MFA for standard workforce apps | Moderate to Low | Multiple existing safeguards reduce the likelihood of successful account compromise. |
| R-007 | Native audit logs and 30-day exports | No change | The controls do not resolve the short retention concern for older investigations. |
| R-008 | RBAC, disk encryption, EDR, export alerts | No change | These safeguards do not establish deletion of local support attachments. |
| R-009 | Standard image pipeline, non-production servers | No change | Patching safeguards exist, but the documented ownership gap remains. |
| R-010 | Explicit data-use instruction, paused AI pilot | Moderate to Low | Direction and the paused pilot reduce likelihood, but actual use is not inventoried. |

A control's existence does not automatically justify a lower residual rating. The control must address the particular scenario and have supporting evidence.

**Source:** [Avenloft Case Packet — Existing Control Evaluation, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 6. Provisional Treatment Summary

| Risk ID | Residual Risk | Proposed Treatment | Main Action |
|---|---|---|---|
| R-001 | Moderate | Mitigate | Test recovery and update response exercises. |
| R-002 | Moderate | Mitigate | Remediate the critical internet-facing vulnerability and review the expired exception. |
| R-003 | Moderate | Mitigate | Improve contractor offboarding. |
| R-004 | Low | Mitigate | Improve privileged authentication and individual accountability. |
| R-005 | Moderate | Mitigate | Assess vendor data access and security controls. |
| R-006 | Low | Mitigate | Improve phishing remediation and monitor workforce exposure. |
| R-007 | Moderate | Mitigate | Validate system classification and improve log retention where required. |
| R-008 | Moderate | Mitigate | Control local attachment handling and deletion. |
| R-009 | Low | Mitigate | Assign ownership to build servers. |
| R-010 | Low | Mitigate | Establish AI governance inventory and intake. |

The treatment decisions are recommendations. No mitigation is represented as already implemented.

## 7. Important Rating Limitations

The following gaps could change the proposed ratings:

1. Recovery test results and actual recovery-time capability.
2. Partner Portal data access, vulnerability details, and WAF effectiveness.
3. Contractor access population and current deprovisioning workflow.
4. Gateway and appliance security configuration.
5. Customer-ticket export data and vendor security evidence.
6. Phishing incident history and MFA exceptions.
7. Salesforce and GitHub high-value asset classification.
8. Data types and deletion practices for support attachments.
9. Build-server ownership, dependencies, and patch evidence.
10. Actual employee use of consumer AI services and data submitted.

The case packet says that missing information must be recorded rather than invented.

**Source:** [Avenloft Case Packet — Facts You Should Not Assume, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

## 8. Current Assessment Status

| Activity | Status |
|---|---|
| Ten candidate scenarios documented | Complete |
| Inherent likelihood and impact proposed | Provisional |
| Inherent risk levels calculated | Provisional |
| Existing controls reviewed | Provisional |
| Residual likelihood and impact proposed | Provisional |
| Residual risk levels calculated | Provisional |
| Treatment recommendations drafted | Provisional |
| Risk-owner assignments | Provisional / validation required |
| Material unknowns documented | Complete |
| Final register approval | Not started |
| Top-five prioritisation | Not started |
| Executive risk summary | Not started |

## 9. Assessment Disclaimer

This working paper contains independent analyst judgements for a fictional training case. The ratings are not supplied or approved by Avenloft leadership.

Different analysts may produce different defensible ratings. The final assessment must explain the evidence, control effectiveness, assumptions, business impact, and treatment rationale.

No real incident, breach, compromise, audit result, or client engagement is claimed.