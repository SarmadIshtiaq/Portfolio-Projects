# Avenloft Systems Group — Security Observation Map

**Project ID:** GRC-RISK-001  
**Document:** Evidence and Observation Analysis  
**Organisation:** Avenloft Systems Group (Fictional)  
**Primary Source:** [Avenloft Cybersecurity Risk Register Case Packet](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf)  
**Source Pages:** 6–9  
**Status:** Evidence documented; risk analysis pending

## 1. Purpose

This document records the 12 security and control observations supplied in the Avenloft case packet.

Its purpose is to:

- Record what the case packet actually says.
- Identify the source of each observation.
- Document existing controls and safeguards.
- Record relevant limitations and uncertainties.
- Connect observations to relevant business objectives.
- Provide a traceable evidence base for later risk-scenario development.

An observation is evidence for analysis. It is not automatically a separate risk or proof of a control failure.

**Source:** [Case Packet — Evidence Set, pages 6–8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

## 2. Observation Index

| Evidence ID | Observation | Evidence Source | Case Page |
|---|---|---|---:|
| OBS-01 | Recovery testing lag | IT Operations interview | 6 |
| OBS-02 | Critical Partner Portal vulnerability | Vulnerability remediation tracker | 6 |
| OBS-03 | Contractor offboarding delay | Quarterly access review | 6 |
| OBS-04 | Legacy administrative gateway without MFA | IT architecture note | 6 |
| OBS-05 | Vendor review classification gap | Procurement process review | 7 |
| OBS-06 | Awareness and phishing results | Security awareness dashboard | 7 |
| OBS-07 | SaaS audit-log retention gap | Logging standard review | 7 |
| OBS-08 | Customer-support download workflow | Customer Success interview | 7 |
| OBS-09 | Incident-response exercise is stale | Incident response program review | 8 |
| OBS-10 | Shared appliance administrator identity | IT control walkthrough | 8 |
| OBS-11 | Asset ownership gaps | Asset inventory review | 8 |
| OBS-12 | Unmanaged AI experimentation | Security Steering Committee notes | 8 |

**Source:** [Case Packet — Evidence Set, pages 6–8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

---

## 3. Detailed Observation Records

### OBS-01 — Recovery Testing Lag

**Evidence source:** IT Operations interview  
**Case page:** 6

**Documented observation**

- Production database backups run daily.
- Protected backup copies are maintained.
- The last documented full application-and-database restore exercise occurred 14 months ago.
- The recovery runbook still refers to the pre-migration network layout.
- Avenloft moved its final production services into its current AWS architecture.

**Existing controls and safeguards**

- Daily production backups.
- Protected backup copies.
- Operations monitoring of backup-job completion.

**Evidence limitations**

- The review identified no evidence of a failed backup.
- The case packet does not provide a recent successful full restoration test.
- The current recovery runbook's accuracy has not been demonstrated by a documented test.

**Business relevance**

Avenloft's service reliability and recovery capability are relevant to this observation.

**Source:** [Case Packet — OBS-01, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

### OBS-02 — Critical Partner Portal Vulnerability

**Evidence source:** Vulnerability remediation tracker  
**Case page:** 6

**Documented observation**

- A critical vulnerability with a CVSS score of 9.1 remains open on the internet-facing Partner Portal.
- It has remained open for 32 days.
- Engineering delayed the vendor patch because regression testing caused partner-session failures.
- A web application firewall (WAF) rule was added as temporary mitigation.
- The formal risk exception expired five days ago.
- The exception has not been renewed.

**Existing controls and safeguards**

- Weekly vulnerability scanning.
- A documented WAF mitigation rule.
- A previous formal risk exception, which is now expired.

**Evidence limitations**

- The case packet does not state that the vulnerability has been exploited.
- It does not provide evidence of a successful attack or compromise.
- The WAF rule is described as temporary mitigation, not a permanent fix.
- The previous exception is no longer current.

**Business relevance**

The Partner Portal is internet-facing. Customer trust, service security, and the stated critical-vulnerability tolerance are relevant to this observation.

**Source:** [Case Packet — OBS-02, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

### OBS-03 — Contractor Offboarding Delay

**Evidence source:** Quarterly access review  
**Case page:** 6

**Documented observation**

- Three engineering contractors retained GitHub access after their contract end dates.
- The access remained active for 4, 6, and 9 days, respectively.
- No unauthorized activity was found in the sampled logs.
- Employee departures are automatically deprovisioned through Workday and Okta.
- Contractor offboarding depends on an engineering sponsor submitting a ticket.

**Existing controls and safeguards**

- All three identified contractor accounts are now disabled.
- GitHub requires SSO for workforce identities.
- Employee offboarding is connected to the identity workflow.

**Evidence limitations**

- No unauthorized activity was found in the sampled logs; this does not establish that no other activity occurred.
- The case does not provide evidence of a fully automated contractor offboarding process.
- The ticket-submission dependency remains relevant.

**Business relevance**

Access governance, software-development assets, and privileged or third-party access are relevant to this observation.

**Source:** [Case Packet — OBS-03, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

### OBS-04 — Legacy Administrative Gateway Without MFA

**Evidence source:** IT architecture note  
**Case page:** 6

**Documented observation**

- Six IT administrators use a legacy remote administration gateway.
- The gateway manages two network appliances.
- It does not support Okta or MFA.
- Authentication uses local usernames and passwords.
- Access is restricted to company VPN source addresses.

**Existing controls and safeguards**

- The gateway is not exposed to arbitrary internet sources.
- Only six administrators are authorised.
- Password rotation is performed through the team vault.

**Evidence limitations**

- The case packet does not provide evidence of compromise.
- It does not identify the gateway's exact software version or vulnerability status.
- VPN restriction and the team vault reduce some exposure but do not provide MFA.

**Business relevance**

Privileged access and network infrastructure security are relevant to this observation.

**Source:** [Case Packet — OBS-04, page 6](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=6).

### OBS-05 — Vendor Review Classification Gap

**Evidence source:** Procurement process review  
**Case page:** 7

**Documented observation**

- Procurement automatically requires security review for vendors above a spend threshold.
- Data sensitivity is not a mandatory vendor-classification field.
- A customer-support analytics vendor receives periodic ticket exports.
- The vendor did not receive a security assessment before onboarding because its annual spend was below the threshold.

**Existing controls and safeguards**

- The vendor contract includes confidentiality language.

**Missing or unavailable evidence**

- No security questionnaire is on file.
- No architecture review is on file.
- No formal vendor risk rating is on file.

**Evidence limitations**

- The packet does not specify every data field contained in the ticket exports.
- The absence of a formal assessment does not prove that the vendor has no security controls.

**Business relevance**

Customer-data confidentiality, third-party risk management, procurement governance, and vendor onboarding are relevant to this observation.

**Source:** [Case Packet — OBS-05, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

### OBS-06 — Awareness and Phishing Results

**Evidence source:** Security awareness dashboard  
**Case page:** 7

**Documented observation**

- Annual security-awareness training completion is 91%.
- 56 employees are overdue.
- The most recent phishing simulation recorded a 6% company-wide click rate.
- Customer Success recorded a 14% click rate.
- Repeat simulation failures do not currently trigger mandatory remedial training.

**Existing controls and safeguards**

- Email filtering.
- Endpoint protection.
- Automated training reminders.

**Evidence limitations**

- The case packet does not identify all repeat simulation failures.
- It does not provide a breakdown of actual security incidents caused by phishing.
- The simulation results are indicators of user behaviour, not proof of a successful compromise.

**Business relevance**

Workforce security awareness and customer-support operations are relevant to this observation.

**Source:** [Case Packet — OBS-06, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

### OBS-07 — SaaS Audit-Log Retention Gap

**Evidence source:** Logging standard review  
**Case page:** 7

**Documented observation**

- Avenloft's security logging standard calls for 180 days of searchable administrative logs for high-value systems.
- AWS production logging meets this standard.
- Detailed administrative exports from Salesforce and GitHub are retained for 30 days.
- Extended retention was not included in the original implementation.

**Existing controls and safeguards**

- Native audit logging is enabled in Salesforce and GitHub.
- Security can retrieve the retained 30-day window when required.
- AWS production logging meets the 180-day standard.

**Evidence limitations**

- The case does not establish whether every relevant event is captured in the retained exports.
- The case does not state that the shorter retention has caused a failed investigation.
- The 180-day standard applies to high-value systems; the assessment should retain this classification context.

**Business relevance**

Security monitoring, administrative accountability, and investigation capability are relevant to this observation.

**Source:** [Case Packet — OBS-07, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

### OBS-08 — Customer-Support Download Workflow

**Evidence source:** Customer Success interview  
**Case page:** 7

**Documented observation**

- Support agents sometimes download customer ticket attachments to local laptops to reproduce product issues.
- Approximately 18 such downloads occur in a typical month.
- Managed laptops use disk encryption and endpoint detection and response (EDR).
- No data loss prevention (DLP) rule prevents local copies or requires deletion after a case closes.

**Existing controls and safeguards**

- Role-based access to customer-support tickets.
- Disk encryption on managed laptops.
- EDR on managed laptops.
- Customer Success managers review unusual export volumes when alerted.

**Evidence limitations**

- The case packet does not identify the exact content of every downloaded attachment.
- It does not establish that all local copies remain after case closure.
- A documented deletion-verification process is not supplied.

**Business relevance**

Customer-data confidentiality, support operations, endpoint security, and data lifecycle management are relevant to this observation.

**Source:** [Case Packet — OBS-08, page 7](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=7).

### OBS-09 — Incident-Response Exercise Is Stale

**Evidence source:** Incident response program review  
**Case page:** 8

**Documented observation**

- The incident-response plan was reviewed six months ago.
- The last ransomware tabletop exercise occurred 22 months ago.
- The exercise took place before the final AWS migration.
- It did not test the loss of the primary identity provider.

**Existing controls and safeguards**

- The incident-response plan contains current contact information.
- An executive escalation tree is available.

**Evidence limitations**

- The case packet does not document a newer ransomware tabletop exercise.
- It does not provide evidence of a completed exercise covering the current AWS environment and identity-provider loss.

**Business relevance**

Incident readiness, recovery, production availability, and management escalation are relevant to this observation.

**Source:** [Case Packet — OBS-09, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

### OBS-10 — Shared Appliance Administrator Identity

**Evidence source:** IT control walkthrough  
**Case page:** 8

**Documented observation**

- Two legacy network appliances use a shared administrator account named `netadmin`.
- The appliances do not support individual administrator identities.
- The password is stored in the privileged credential vault.
- Credential check-out activity is logged.
- Device audit logs record `netadmin` rather than the individual administrator who made a change.

**Existing controls and safeguards**

- The credential is stored in the privileged credential vault.
- Vault check-out activity is logged.
- Only the network administration team can retrieve the credential.
- Vault records provide partial attribution outside the appliance itself.

**Evidence limitations**

- Device-level records do not identify the individual administrator.
- Vault check-out records provide partial attribution, not complete device-level attribution.
- The packet does not provide evidence of an unauthorised administrative change.

**Business relevance**

Privileged access, accountability, and network infrastructure administration are relevant to this observation.

**Source:** [Case Packet — OBS-10, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

### OBS-11 — Asset Ownership Gaps

**Evidence source:** Asset inventory review  
**Case page:** 8

**Documented observation**

- The asset inventory covers approximately 93% of known computing assets.
- Eighteen Linux build servers were discovered during a cloud-cost review.
- These servers do not have a documented business owner in the inventory.
- Engineering states that the servers support non-production software builds.
- Engineering states that the servers are patched through the standard image pipeline.

**Existing controls and safeguards**

- The servers are not customer-facing.
- They are managed through the engineering cloud account.
- Engineering reports that standard image-pipeline patching is used.

**Evidence limitations**

- The packet does not identify the individual technical or business owner of each server.
- It does not report that the servers are unpatched.
- It does not report that the servers are exposed to customers or the public.

**Business relevance**

Asset governance, ownership accountability, and engineering infrastructure management are relevant to this observation.

**Source:** [Case Packet — OBS-11, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

### OBS-12 — Unmanaged AI Experimentation

**Evidence source:** Security Steering Committee notes  
**Case page:** 8

**Documented observation**

- Marketing has permitted employees to use consumer generative-AI accounts for low-sensitivity drafting.
- Customer Success has requested approval for a SaaS AI tool to summarise customer calls and support tickets.
- Avenloft does not maintain a formal AI use-case inventory.
- Avenloft does not have a standard AI-risk intake process.

**Existing controls and safeguards**

- Leadership has told teams not to place customer-confidential information into unapproved AI tools.
- The Customer Success AI request is paused pending GRC review.

**Evidence limitations**

- The packet does not state that customer-confidential information has been entered into an unapproved AI tool.
- It does not provide a complete inventory of consumer AI accounts or actual employee usage.
- The requested Customer Success tool has not been approved.

**Business relevance**

AI governance, customer-data confidentiality, data handling, and responsible technology adoption are relevant to this observation.

**Source:** [Case Packet — OBS-12, page 8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=8).

---

## 4. Supplemental Stakeholder Evidence

The case packet also provides six stakeholder statements. These statements add context to the observations.

| Stakeholder | Role | Documented Statement / Context |
|---|---|---|
| Aaron Bell | Director, GRC | The register must explain business consequences and be usable by leadership. |
| Priya Nair | VP, Engineering | The Partner Portal patch was tested twice but caused partner-session failures; the WAF rule buys time, and the exception should not have lapsed. |
| Marcus Holloway | Director, IT | The old administrative gateway is among the last systems not moved behind modern SSO; replacement of the two appliances is proposed for next fiscal year. |
| Lena Ortiz | VP, Customer Success | Support downloads are usually screenshots, logs, or customer-provided files needed to reproduce problems; there is no good workflow for proving local deletion. |
| Noah Grant | Director, Procurement | Vendor routing is mainly spend-driven and can miss inexpensive services that handle sensitive data. |
| Maya Chen | CISO | Prioritisation should identify the risks that deserve scarce time and budget, account for existing safeguards, and explain material uncertainty. |

**Source:** [Case Packet — Supplemental Stakeholder Notes, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

## 5. Important Assessment Restrictions

The case packet explicitly warns analysts not to make the following assumptions:

1. An observation is not automatically a control failure.
2. A control gap is not automatically a High or Very High risk.
3. The absence of evidence does not prove that a control does not exist.
4. A vulnerability score is not the same as a business risk score.
5. GRC facilitates and monitors the risk; the accountable business or technology leader normally owns it.

**Source:** [Case Packet — Facts You Should Not Assume, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

## 6. Initial Evidence Themes

The observations provide evidence across several areas:

| Evidence Theme | Related Observations |
|---|---|
| Service recovery and incident readiness | OBS-01, OBS-09 |
| Vulnerability and remediation management | OBS-02 |
| Workforce and contractor access | OBS-03 |
| Privileged administration and accountability | OBS-04, OBS-10 |
| Vendor oversight and customer-data handling | OBS-05, OBS-08 |
| Security awareness | OBS-06 |
| Logging and investigation support | OBS-07 |
| Asset inventory and ownership | OBS-11 |
| AI governance and data-use oversight | OBS-12 |

These are initial evidence themes for analysis. They are not final risk entries. Some observations may support more than one risk, and multiple observations may support one risk scenario.

**Source:** [Case Packet — Assignment Brief and Evidence Set, pages 2 and 6–8](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=2).

## 7. Evidence Analysis Status

| Activity | Status |
|---|---|
| Record OBS-01 to OBS-12 | Documented |
| Record stated existing controls | Documented |
| Record stakeholder context | Documented |
| Identify evidence limitations | Documented |
| Group observations into final risk scenarios | Not started |
| Assign inherent risk ratings | Not started |
| Assign residual risk ratings | Not started |
| Select top-five residual risks | Not started |

**Document status:** Evidence mapping prepared for the independent training simulation.

No final risk rating or risk treatment decision is assigned in this document.