# Avenloft Systems Group — Risk Scenario Analysis

**Project ID:** GRC-RISK-001  
**Document:** Candidate Cybersecurity Risk Scenarios  
**Organisation:** Avenloft Systems Group (Fictional)  
**Assessment:** FY2027 Cybersecurity Risk Register  
**Source:** [Avenloft Cybersecurity Risk Register Case Packet](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf)  
**Status:** Candidate scenarios documented; risk ratings pending

## 1. Purpose

This document converts the 12 security and control observations in the Avenloft case packet into business-focused candidate risk scenarios.

The objective is to identify approximately 8–12 defensible scenarios for the cybersecurity risk register.

This analysis:

- Groups related observations where they support the same underlying scenario.
- Separates observations that represent different business exposures.
- Connects each scenario to an affected business objective or asset.
- Records the evidence supporting each scenario.
- Identifies existing safeguards.
- Documents assumptions and information requiring validation.
- Avoids assigning risk ratings before the formal assessment.

The case packet explicitly states that observations are evidence, not prewritten risks. Several observations may combine into one scenario, and one observation may support more than one scenario.

**Source:** [Case Packet — Assignment Brief, page 2](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=2) and [Evidence Set, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

## 2. Scenario Development Method

Each candidate risk statement follows the case packet's cause-and-impact structure:

> If [threat event or failure] exploits or occurs alongside [condition or weakness], then [asset, process, or objective] may experience [business impact].

A technical observation is not automatically a business risk.

For example:

**Technical condition:** A full application-and-database restore exercise has not been documented for 14 months.

**Business risk:** A major production disruption may require restoration of services, but recovery procedures may not support restoration within the expected business recovery period.

The second statement connects the condition to a potential business consequence.

**Source:** [Case Packet — Avenloft Risk Assessment Method, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 3. Observation Grouping

The 12 observations are grouped into 10 candidate risk scenarios.

| Candidate ID | Candidate Risk Title | Supporting Evidence | Grouping Decision |
|---|---|---|---|
| R-001 | Production Recovery and Incident Readiness | OBS-01, OBS-09 | Combined because recovery testing and incident exercises support the same service-restoration objective. |
| R-002 | Partner Portal Vulnerability Exploitation | OBS-02 | Separate because it concerns a known critical internet-facing vulnerability and its remediation. |
| R-003 | Contractor Access After Contract End | OBS-03 | Separate because it concerns contractor identity lifecycle and repository access. |
| R-004 | Legacy Privileged Access and Administrator Accountability | OBS-04, OBS-10 | Combined because both observations concern administration of the two legacy network appliances. |
| R-005 | Third-Party Access to Customer Support Data | OBS-05 | Separate because it concerns supplier oversight and customer-ticket exports. |
| R-006 | Phishing and Workforce Account Compromise | OBS-06 | Separate because it concerns workforce susceptibility to phishing and possible account compromise. |
| R-007 | SaaS Administrative Log Retention | OBS-07 | Separate because it concerns the ability to investigate and reconstruct administrative activity. |
| R-008 | Customer-Support Attachments on Local Devices | OBS-08 | Separate because it concerns local copies of customer information and deletion control. |
| R-009 | Unassigned Ownership of Engineering Build Servers | OBS-11 | Separate because it concerns asset ownership and accountability for engineering infrastructure. |
| R-010 | Unmanaged Consumer Generative-AI Use | OBS-12 | Separate because it concerns AI-use governance and possible handling of confidential information. |

**Sources:** [OBS-01–OBS-04, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6), [OBS-05–OBS-08, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7), and [OBS-09–OBS-12, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

## 4. Candidate Risk Scenarios

### R-001 — Production Recovery and Incident Readiness

**Supporting observations:** OBS-01 and OBS-09

**Candidate risk statement**

If a major production disruption requires coordinated incident response and restoration, but Avenloft's recovery procedures and response exercises do not reflect the current AWS environment and supporting identity dependencies, Avenloft Relay may remain unavailable beyond the business recovery tolerance, disrupting customer operations and service commitments.

**Evidence**

- Daily production database backups run and protected copies are maintained. The last documented full application-and-database restore exercise occurred 14 months ago.
- The recovery runbook still refers to the pre-migration network layout.
- The last ransomware tabletop exercise occurred 22 months ago.
- The tabletop took place before the final AWS migration and did not test loss of the primary identity provider.

Sources: [OBS-01, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6) and [OBS-09, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

**Existing safeguards**

- Daily production backups.
- Protected backup copies.
- Backup-job monitoring.
- An incident-response plan with current contact information.
- An executive escalation tree.

**Relevant business objective**

Maintain service reliability and recover quickly from disruptive events.

**Risk appetite connection**

Leadership has low tolerance for production outages exceeding four hours during business operations.

[Source: Case Packet — Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

**Information requiring validation**

- When was the last successful full application-and-database restore?
- Does the current recovery runbook reflect the final AWS environment?
- Are recovery objectives and dependencies documented and tested?
- Can the organisation coordinate response if its primary identity provider is unavailable?
- Do recovery tests demonstrate restoration within the four-hour business tolerance?

**Assessment note**

Daily backups exist. The evidence does not show that a backup has failed. The scenario concerns the ability to restore and coordinate recovery, not an assumed backup failure.

---

### R-002 — Partner Portal Vulnerability Exploitation

**Supporting observation:** OBS-02

**Candidate risk statement**

If an attacker exploits the critical vulnerability on Avenloft's internet-facing Partner Portal before permanent remediation, the portal or associated partner services may be compromised or disrupted, affecting customer trust, partner operations, and service commitments.

**Evidence**

- A critical vulnerability with a CVSS score of 9.1 has remained open for 32 days.
- Engineering delayed the vendor patch because regression testing caused partner-session failures.
- A web application firewall rule was added as temporary mitigation.
- The formal risk exception expired five days ago and has not been renewed.
- Weekly vulnerability scanning is operating.

Sources: [OBS-02, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6) and [Engineering stakeholder note, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

**Existing safeguards**

- Weekly vulnerability scanning.
- A documented WAF mitigation rule.
- Engineering regression testing of the vendor patch.

**Relevant business objectives**

- Protect customer trust.
- Maintain service reliability.
- Preserve contractual security commitments.

**Risk appetite connection**

Leadership does not accept known critical internet-facing vulnerabilities beyond 30 days without a current written exception and compensating controls.

[Source: Case Packet — Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

**Information requiring validation**

- What is the vulnerability identifier and affected software component?
- Has the vendor supplied an updated remediation?
- What attack paths does the vulnerability expose?
- What exactly does the WAF rule block?
- Has the effectiveness of the temporary mitigation been tested?
- Has the expired exception been formally reviewed and escalated?

**Assessment note**

The case packet does not report successful exploitation. A CVSS score is not itself a business risk rating. The risk scenario must be assessed using Avenloft's supplied likelihood-and-impact method.

---

### R-003 — Contractor Access After Contract End

**Supporting observation:** OBS-03

**Candidate risk statement**

If contractor access remains active after a contract ends because access removal depends on manual sponsor requests, a former contractor account may be used to access engineering repositories or related information without current business authorisation, affecting source-code confidentiality and software-delivery integrity.

**Evidence**

- Three engineering contractors retained GitHub access after their contract end dates for 4, 6, and 9 days.
- Employee departures are automatically deprovisioned through Workday and Okta.
- Contractor offboarding depends on the engineering sponsor submitting a ticket.
- No unauthorised activity was found in the sampled logs.
- All three identified accounts are now disabled.

[Source: Case Packet — OBS-03, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

**Existing safeguards**

- Employee offboarding is automated through Workday and Okta.
- GitHub requires SSO for workforce identities.
- The three identified contractor accounts have been disabled.

**Relevant business objectives**

- Protect customer trust and company information.
- Maintain secure engineering and software-delivery processes.
- Reduce friction in access decisions.

**Information requiring validation**

- Does the SSO requirement cover every contractor identity?
- How many active contractor accounts exist across engineering systems?
- Is there a documented deadline for contractor access removal?
- Are contractor end dates recorded in a system that sponsors and IT can use?
- Were the sampled logs sufficient to cover the full access periods?

**Assessment note**

No unauthorised activity was found in the sampled logs. This is not proof that unauthorised activity never occurred. The scenario focuses on the recurring access-lifecycle weakness, not an assumed compromise.

---

### R-004 — Legacy Privileged Access and Administrator Accountability

**Supporting observations:** OBS-04 and OBS-10

**Candidate risk statement**

If legacy administrative credentials are compromised or misused, the absence of MFA on the remote gateway and the use of a shared appliance administrator account may allow unauthorised network-appliance changes, while limited individual attribution may delay investigation and accountability.

**Evidence**

- Six IT administrators use a legacy remote administration gateway.
- The gateway does not support Okta or MFA and uses local username-and-password authentication.
- Access is restricted to company VPN source addresses.
- Two legacy network appliances use the shared `netadmin` account because they do not support individual administrator identities.
- Device audit logs record `netadmin`, not the individual administrator.
- Vault check-out activity is logged.

Sources: [OBS-04, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6) and [OBS-10, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

**Existing safeguards**

- Access is restricted to company VPN source addresses.
- Only six administrators are authorised to use the gateway.
- Password rotation is performed through the team vault.
- The shared appliance credential is stored in the privileged credential vault.
- Vault check-out records provide partial attribution.
- Only the network administration team can retrieve the credential.

**Relevant business objectives**

- Protect privileged access.
- Maintain reliable infrastructure.
- Preserve accountability for administrative changes.

**Risk appetite connection**

Leadership has low tolerance for weak authentication and untraceable administrative activity.

[Source: Case Packet — Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

**Information requiring validation**

- What software and firmware versions run on the gateway and appliances?
- Is access to the VPN itself protected by MFA?
- Can the appliance activity be correlated with vault check-out records?
- How often are privileged access permissions reviewed?
- What compensating monitoring exists for shared-account use?
- What is the approved timeline for replacing the legacy appliances?

**Assessment note**

The gateway is restricted to VPN source addresses and is not exposed to arbitrary internet sources. Vault activity provides partial attribution. These safeguards must receive consideration during the control assessment.

---

### R-005 — Third-Party Access to Customer Support Data

**Supporting observation:** OBS-05

**Candidate risk statement**

If the customer-support analytics vendor or its service environment is compromised, or customer-ticket information is handled outside Avenloft's expected safeguards, customer information contained in periodic ticket exports may be disclosed or used without appropriate oversight, affecting customer trust and contractual commitments.

**Evidence**

- A customer-support analytics vendor receives periodic ticket exports.
- Security review was not completed before onboarding because annual spend was below the procurement threshold.
- Data sensitivity is not a mandatory procurement classification field.
- No security questionnaire, architecture review, or formal vendor risk rating is on file.
- The vendor contract includes confidentiality language.

[Source: Case Packet — OBS-05, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

**Existing safeguards**

- Contractual confidentiality language.
- Existing procurement workflow requires security review for vendors above its spend threshold.

**Relevant business objectives**

- Protect customer trust.
- Preserve contractual security commitments.
- Make vendor onboarding and security reviews more consistent.

**Information requiring validation**

- What data fields are included in the ticket exports?
- Do exports contain customer-confidential information, attachments, or personal data?
- What security controls does the vendor operate?
- Where is the exported data stored and processed?
- Which people or subcontractors can access it?
- What data-retention and deletion arrangements apply?
- Is there any independent assurance evidence available?

**Assessment note**

The absence of a completed assessment does not prove that the vendor has no security controls. The data scope and the vendor's actual control environment require validation.

---

### R-006 — Phishing and Workforce Account Compromise

**Supporting observation:** OBS-06

**Candidate risk statement**

If an employee responds to a phishing attempt and discloses credentials or executes malicious content, an attacker may gain unauthorised access to workforce systems or customer-support information, affecting company operations and customer-data confidentiality.

**Evidence**

- Annual security-awareness training completion is 91%.
- 56 employees are overdue.
- The latest phishing simulation recorded a 6% company-wide click rate.
- Customer Success recorded a 14% click rate.
- Repeat simulation failures do not currently trigger mandatory remedial training.

[Source: Case Packet — OBS-06, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

**Existing safeguards**

- Email filtering.
- Endpoint protection.
- Automated training reminders.
- Okta SSO and MFA for standard workforce applications.

[Source: Case Packet — Technology Environment and Security Baseline, page 5](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=5).

**Relevant business objectives**

- Protect customer trust.
- Maintain service reliability.
- Protect company information and workforce systems.

**Information requiring validation**

- Do repeat simulation failures include users who handle sensitive customer information?
- How many employees have failed multiple simulations?
- Are MFA and conditional-access requirements consistently applied to relevant systems?
- Are phishing reports and real incidents tracked?
- Does the organisation measure completion of remedial training?

**Assessment note**

A phishing simulation click rate is an indicator of susceptibility. It does not establish that credentials were stolen or that an actual compromise occurred.

---

### R-007 — SaaS Administrative Log Retention

**Supporting observation:** OBS-07

**Candidate risk statement**

If an administrative security incident involving Salesforce or GitHub is identified after the available detailed audit-log retention period, Avenloft may not have sufficient historical records to reconstruct activity, establish accountability, or investigate the full scope of the incident.

**Evidence**

- Avenloft's logging standard calls for 180 days of searchable administrative logs for high-value systems.
- AWS production logging meets this standard.
- Detailed administrative exports from Salesforce and GitHub are retained for 30 days.
- Native audit logging is enabled in both services.

[Source: Case Packet — OBS-07, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

**Existing safeguards**

- Native Salesforce audit logging.
- Native GitHub audit logging.
- Security can retrieve the retained 30-day window.
- AWS production security logs are centralised and meet the 180-day standard.

[Source: Case Packet — Logging Baseline, page 5](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=5).

**Relevant business objectives**

- Protect customer trust.
- Demonstrate predictable control operation.
- Maintain investigation and assurance capability.

**Information requiring validation**

- Are Salesforce and GitHub formally classified as high-value systems under the logging standard?
- Which administrative events are included in the detailed exports?
- Are the exports stored elsewhere before the 30-day period expires?
- Are alerts and investigations generated quickly enough to use the available logs?
- Can the company retrieve longer-term audit evidence from either provider?

**Assessment note**

The case packet does not explicitly state whether Salesforce and GitHub are formally classified as high-value systems. Confirm this before concluding that the 30-day retention is a direct breach of the 180-day standard.

---

### R-008 — Customer-Support Attachments on Local Devices

**Supporting observation:** OBS-08

**Candidate risk statement**

If customer-support attachments downloaded to local laptops remain after support cases close, or are accessed by an unauthorised person following device loss or compromise, customer information may be disclosed outside the intended support workflow, affecting customer trust and contractual commitments.

**Evidence**

- Support agents sometimes download ticket attachments to local laptops to reproduce product issues.
- Approximately 18 downloads occur in a typical month.
- There is no DLP rule preventing local copies or requiring deletion after the case closes.
- Customer Success management does not have a reliable workflow for proving local deletion.

Sources: [OBS-08, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7) and [Customer Success stakeholder note, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

**Existing safeguards**

- Role-based access to support tickets.
- Disk encryption on managed laptops.
- Endpoint detection and response.
- Customer Success managers review unusual export volumes when alerted.

[Source: Case Packet — OBS-08, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

**Relevant business objectives**

- Protect customer trust.
- Preserve customer-data confidentiality.
- Maintain reliable customer-support operations.

**Information requiring validation**

- What types of files and data are included in the attachments?
- Are all downloads made to managed devices?
- Are local copies stored in approved locations?
- What happens to downloaded files when devices are reassigned or returned?
- Is deletion technically enforced or only expected from employees?
- Are downloads recorded and reviewed?

**Assessment note**

The case packet does not establish that a local copy has been exposed or that a device has been compromised. The risk concerns uncontrolled retention and limited deletion verification.

---

### R-009 — Unassigned Ownership of Engineering Build Servers

**Supporting observation:** OBS-11

**Candidate risk statement**

If a security issue, configuration weakness, or operational failure affects one of the engineering build servers without a documented business owner, remediation and risk decisions may be delayed, affecting engineering build operations and software-delivery activities.

**Evidence**

- The asset inventory covers approximately 93% of known computing assets.
- Eighteen Linux build servers discovered during a cloud-cost review do not have a documented business owner in the inventory.
- Engineering states that the servers support non-production software builds.
- Engineering states that the servers are patched through the standard image pipeline.

[Source: Case Packet — OBS-11, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

**Existing safeguards**

- The servers are not customer-facing.
- They are managed through the engineering cloud account.
- Engineering reports that standard image-pipeline patching is used.

**Relevant business objectives**

- Scale responsibly.
- Maintain predictable engineering operations.
- Reduce friction in security ownership and accountability.

**Information requiring validation**

- Who is the technical owner of each server?
- Who can approve security changes or risk acceptance?
- Are all 18 servers included in the standard patching pipeline?
- Are asset criticality and recovery requirements documented?
- Are the servers connected to source-code repositories or production deployment workflows?
- Does the cloud inventory identify their current configuration and access?

**Assessment note**

There is no evidence in the case packet that these servers are unpatched or customer-facing. The scenario concerns ownership and accountability, not an assumed vulnerability or compromise.

---

### R-010 — Unmanaged Consumer Generative-AI Use

**Supporting observation:** OBS-12

**Candidate risk statement**

If employees enter customer-confidential or other restricted information into consumer generative-AI services outside Avenloft's approved controls, the information may be exposed to an external service without appropriate organisational oversight, affecting customer confidentiality and responsible technology adoption.

**Evidence**

- Marketing has permitted employees to use consumer generative-AI accounts for low-sensitivity drafting.
- Customer Success has requested approval for a SaaS AI tool to summarise customer calls and support tickets.
- Avenloft does not maintain a formal AI use-case inventory or standard AI-risk intake process.
- The Customer Success request is paused pending GRC review.

[Source: Case Packet — OBS-12, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

**Existing safeguards**

- Leadership has instructed teams not to place customer-confidential information into unapproved AI tools.
- The proposed Customer Success pilot is paused pending review.

[Source: Case Packet — OBS-12, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

**Relevant business objectives**

- Protect customer trust.
- Scale responsibly.
- Avoid unmanaged customer-data or decision risk.

**Risk appetite connection**

Leadership has a moderate appetite for controlled AI pilots and low tolerance for customer or confidential data entering unapproved tools.

[Source: Case Packet — Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

**Information requiring validation**

- Which consumer generative-AI services are being used?
- Are accounts personal or organisation-managed?
- What information do employees actually submit?
- Are there approved usage rules for different data classifications?
- Is there a process to identify and review new AI use cases?
- What data handling and retention terms apply to the services currently used?

**Assessment note**

The case packet does not state that customer-confidential information has been entered into an unapproved AI service. The proposed Customer Success pilot is paused. The scenario is a potential exposure that requires usage and data-flow validation.

---

## 5. Candidate Risk-to-Business Objective Mapping

| Candidate Risk | Primary Business Objective | Additional Business Relevance |
|---|---|---|
| R-001 | Maintain service reliability | Protect customer trust |
| R-002 | Protect customer trust | Maintain service reliability |
| R-003 | Protect customer trust | Reduce friction in access decisions |
| R-004 | Protect customer trust | Maintain infrastructure reliability and accountability |
| R-005 | Protect customer trust | Improve vendor onboarding and assurance |
| R-006 | Protect customer trust | Maintain secure workforce operations |
| R-007 | Win larger enterprise customers | Support investigation and control assurance |
| R-008 | Protect customer trust | Maintain customer-support operations |
| R-009 | Scale responsibly | Maintain engineering operations and accountability |
| R-010 | Scale responsibly | Protect customer trust and confidentiality |

**Source:** [Case Packet — Business Objectives for FY2027, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3).

## 6. Important Grouping Decisions

### Decision 1 — OBS-01 and OBS-09

These observations are combined under R-001 because they concern two connected parts of the same service-restoration capability:

- OBS-01 concerns restoration procedures and restore testing.
- OBS-09 concerns incident response and exercise coverage.

They have a common business outcome: the organisation's ability to restore services after a disruptive event.

### Decision 2 — OBS-04 and OBS-10

These observations are combined under R-004 because they concern the legacy administrative gateway and the two network appliances it manages.

- OBS-04 concerns gateway authentication and remote access.
- OBS-10 concerns the shared administrator identity and device-level attribution.

They are related parts of the privileged-access exposure and should be assessed together to avoid counting the same infrastructure exposure twice.

**Sources:** [OBS-01 and OBS-04, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6), [OBS-09 and OBS-10, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8), and [Technology Environment, page 5](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=5).

### Decision 3 — OBS-05 and OBS-08

These observations are not combined.

- OBS-05 concerns a third-party vendor receiving periodic ticket exports without a documented security assessment.
- OBS-08 concerns support agents downloading attachments to local laptops without a deletion-verification workflow.

Both relate to customer information, but their processes, control owners, and potential treatment actions differ.

### Decision 4 — OBS-03 and OBS-07

These observations are not combined.

- OBS-03 concerns access remaining active after a contractor's contract ends.
- OBS-07 concerns the length of time detailed administrative logs are retained.

The first concerns access authorisation. The second concerns investigation and evidence availability.

---

## 7. Candidate Risk Register Shortlist

| Risk ID | Candidate Risk Title | Evidence IDs | Rating Status |
|---|---|---|---|
| R-001 | Production Recovery and Incident Readiness | OBS-01, OBS-09 | Not assessed |
| R-002 | Partner Portal Vulnerability Exploitation | OBS-02 | Not assessed |
| R-003 | Contractor Access After Contract End | OBS-03 | Not assessed |
| R-004 | Legacy Privileged Access and Administrator Accountability | OBS-04, OBS-10 | Not assessed |
| R-005 | Third-Party Access to Customer Support Data | OBS-05 | Not assessed |
| R-006 | Phishing and Workforce Account Compromise | OBS-06 | Not assessed |
| R-007 | SaaS Administrative Log Retention | OBS-07 | Not assessed |
| R-008 | Customer-Support Attachments on Local Devices | OBS-08 | Not assessed |
| R-009 | Unassigned Ownership of Engineering Build Servers | OBS-11 | Not assessed |
| R-010 | Unmanaged Consumer Generative-AI Use | OBS-12 | Not assessed |

**Total candidate scenarios: 10**

The number is within the case packet's required range of approximately 8–12 risk entries.

[Source: Case Packet — Required Deliverables, page 2](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=2).

## 8. Items Requiring Validation Before Risk Scoring

The following questions should be considered during risk assessment:

| Area | Validation Requirement |
|---|---|
| Recovery | Confirm successful full restoration and current recovery-runbook coverage. |
| Partner Portal | Confirm vulnerability details, exposure, and WAF mitigation effectiveness. |
| Contractor access | Confirm the contractor population, offboarding timing, and SSO coverage. |
| Privileged access | Confirm VPN authentication, device logging, and compensating monitoring. |
| Third-party vendor | Confirm exported data types, vendor controls, processing locations, and retention. |
| Phishing | Confirm repeat failures, actual incidents, and account-protection coverage. |
| Logging | Confirm whether Salesforce and GitHub are classified as high-value systems. |
| Support downloads | Confirm file contents, storage locations, and deletion practices. |
| Build servers | Confirm ownership, patch coverage, and engineering dependencies. |
| AI use | Confirm actual employee use, services, data submitted, and provider terms. |

These items are not additional findings. They are questions whose answers may materially affect the assessment.

## 9. Assessment Rules

Before any candidate becomes a final risk-register entry:

- Confirm that the scenario is supported by the evidence.
- Check whether multiple observations have been grouped correctly.
- Confirm the affected business objective or asset.
- Identify all relevant existing safeguards.
- Record assumptions and missing evidence.
- Confirm the accountable risk owner.
- Assess inherent risk before considering current controls.
- Assess residual risk after considering current controls.
- Use the qualitative matrix defined in `risk-criteria.md`.

The risk assessment must not invent facts, assume control effectiveness, or treat a vulnerability score as the business risk rating.

**Source:** [Case Packet — Facts You Should Not Assume, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9) and [Quality Bar for the Analyst, page 13](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=13).

## 10. Document Status

**Candidate risk scenarios documented:** 10  
**Supporting observations mapped:** OBS-01 to OBS-12  
**Risk statements drafted:** Yes  
**Inherent risk ratings:** Not started  
**Residual risk ratings:** Not started  
**Treatment decisions:** Not started  
**Final risk ownership:** Pending assessment  
**Top-five prioritisation:** Not started

This document is part of an independent training simulation. Avenloft Systems Group and all case observations are fictional.