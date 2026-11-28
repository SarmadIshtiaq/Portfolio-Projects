# Vendor Risk Assessment Methodology

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Assessment Type:** Third-Party Vendor Security and Privacy Risk Assessment  
**Assessment Basis:** Fictional Avenloft Third-Party Risk Review Case  
**Framework References:** NIST SP 800-30 Rev. 1, NIST CSF 2.0 GV.SC, NIST SP 1305, NIST SP 1326, and NIST SP 800-161

---

## 1. Purpose

This document explains the methodology used to assess information security, privacy, operational, and third-party risks associated with CobaltCedar Analytics, Inc. and its SupportLens SaaS service.

The assessment is intended to:

- Understand the vendor relationship, business purpose, and data-processing activities.
- Identify threats, vulnerabilities, and potential adverse impacts.
- Evaluate the vendor's existing security and privacy controls.
- Determine inherent and residual risk levels.
- Identify evidence gaps and control weaknesses.
- Recommend proportionate risk treatments and conditions for continued use or renewal.

This is a risk-based assessment. It does not represent a formal audit, certification, penetration test, or independent validation of the vendor's security environment.

## 2. Assessment Scope

The assessment covers the following areas:

| Assessment Area | Scope |
|---|---|
| Vendor relationship | Business purpose, service dependency, annual spend, and contract lifecycle |
| Data processing | Support-case exports, personal and business contact information, and free-text support content |
| Access management | Avenloft user access, MFA enrollment, export permissions, and access reviews |
| Vendor security | Workforce access controls, security program, encryption, logging, and vulnerability management |
| Independent assurance | Available SOC 2 Type II report summary and penetration-test summary |
| Security incidents | March 2026 credential-stuffing incident and its relevance to the service |
| Privacy and retention | Data retention, deletion, backups, and subprocessors |
| Contractual safeguards | Incident notification, audit rights, security documentation, and subprocessor provisions |
| Business continuity | Backup arrangements, recovery objectives, and service dependency |

The assessment is limited to the information supplied in the fictional case packet. It does not assume access to the vendor's production environment, full SOC 2 report, complete penetration-test report, internal policies, or technical configuration.

## 3. Assessment Approach

The assessment follows a structured risk-assessment process informed by NIST SP 800-30 Rev. 1.

The process consists of the following activities:

1. **Establish context:** Understand the business relationship, service purpose, data types, stakeholders, and organizational requirements.
2. **Review evidence:** Examine the available questionnaire responses, security documentation, assurance summaries, incident information, contract terms, and internal stakeholder input.
3. **Identify risk scenarios:** Describe plausible events involving threats, vulnerabilities or control weaknesses, affected assets, and potential consequences.
4. **Assess likelihood:** Estimate the possibility of each scenario occurring, considering the threat activity, exposure, weaknesses, and existing controls.
5. **Assess impact:** Estimate the potential business, security, privacy, legal, contractual, and operational consequences.
6. **Determine inherent risk:** Rate the scenario before considering the effectiveness of existing controls.
7. **Evaluate existing controls:** Assess whether relevant controls are implemented and whether the available evidence supports their effectiveness.
8. **Determine residual risk:** Reassess the scenario after considering supported existing controls.
9. **Recommend treatment:** Define practical actions, proposed owners, validation evidence, and target risk levels.
10. **Support the vendor decision:** Present the remaining risks and recommended conditions for continued use or renewal.

## 4. Risk Scenario Structure

Each risk scenario is documented using a consistent structure:

- **Risk ID:** Unique identifier assigned for tracking.
- **Risk title:** Short description of the risk.
- **Risk statement:** Description of the threat event, relevant weakness or exposure, and potential consequence.
- **Affected assets or information:** Systems, services, records, or business processes exposed.
- **Threat source or event:** The event or actor that could trigger the scenario.
- **Vulnerability or control weakness:** The condition that could allow the event to occur or increase its consequences.
- **Existing controls:** Controls already described in the case evidence.
- **Evidence quality:** Whether the control is supported by independent assurance, documentary evidence, or vendor statements.
- **Inherent likelihood and impact:** Ratings before existing controls are considered.
- **Inherent risk:** Risk level derived from the assessment matrix.
- **Residual likelihood and impact:** Ratings after considering supported existing controls.
- **Residual risk:** Remaining risk after existing controls.
- **Recommended treatment:** Additional actions proposed to reduce, transfer, avoid, or formally accept the risk.
- **Target residual risk:** Proposed risk level after successful implementation and validation of the recommended actions.

A risk scenario is not treated as a confirmed incident or control failure unless the case evidence supports that conclusion. Plausible scenarios and analyst judgments are identified as assessments rather than established facts.

## 5. Likelihood Assessment

Likelihood represents the estimated possibility that a risk scenario will occur within the context of the vendor relationship.

The assessment uses three qualitative levels: Low, Moderate, and High.

| Rating | General Interpretation |
|---|---|
| Low | The scenario is considered less likely based on the available information. Relevant controls appear to reduce exposure, and there is limited evidence of the scenario or comparable events. |
| Moderate | The scenario is plausible. Some exposure, control weaknesses, prior events, or evidence gaps increase uncertainty or the possibility of occurrence. |
| High | The scenario is considered likely or has strong supporting indicators, such as significant unresolved weaknesses, repeated events, or inadequate controls in an exposed area. |

Likelihood is assessed using relevant factors, including:

- Nature and sensitivity of the information processed.
- Exposure of the service and its user accounts.
- Existing authentication and access controls.
- Known security incidents or threat activity.
- Identified vulnerabilities and outstanding remediation.
- Vendor and customer responsibilities.
- Reliability and completeness of the available evidence.

The ratings are qualitative analyst judgments based on the case information. They are not numerical probabilities.

## 6. Impact Assessment

Impact represents the potential consequences if a risk scenario occurs.

The assessment considers the possible effect on:

- **Confidentiality:** Unauthorized disclosure or access to Avenloft or customer information.
- **Integrity:** Unauthorized alteration, manipulation, or loss of trust in information.
- **Availability:** Disruption or loss of access to the vendor service or related business processes.
- **Privacy:** Exposure or misuse of personal information contained in support records.
- **Legal and contractual obligations:** Potential breach of applicable requirements or contractual commitments.
- **Financial impact:** Incident response costs, remediation costs, contractual exposure, or business losses.
- **Reputation and customer trust:** Loss of confidence among customers, partners, or other stakeholders.
- **Operational impact:** Disruption to Customer Success, reporting, or support-related activities.

The assessment uses three qualitative levels: Low, Moderate, and High.

| Rating | General Interpretation |
|---|---|
| Low | Limited and manageable consequences, with little expected disruption or exposure. |
| Moderate | Meaningful consequences that may require management attention, remediation, customer communication, or additional operational effort. |
| High | Serious consequences, potentially involving significant sensitive-data exposure, major operational disruption, substantial legal or contractual concerns, or material damage to customer trust. |

Impact ratings consider the reasonably foreseeable consequences of the scenario. They do not assume that every possible consequence will occur.

## 7. Risk Rating Matrix

The assessment uses the qualitative likelihood-and-impact matrix specified for the supplied case study and aligned with the qualitative approach referenced in NIST SP 800-30 Rev. 1.

The matrix is case-specific. It should not be interpreted as a universal risk matrix prescribed by NIST.

| Likelihood \ Impact | Low | Moderate | High |
|---|---|---|---|
| **Low** | Low | Low | Moderate |
| **Moderate** | Low | Moderate | High |
| **High** | Moderate | High | High |

The resulting rating is recorded as Low, Moderate, or High.

### 7.1 Rating Interpretation

| Risk Level | General Meaning |
|---|---|
| Low | Risk is comparatively limited. Existing controls and routine monitoring may be sufficient, subject to normal oversight. |
| Moderate | Risk requires documented treatment, monitoring, and management oversight. Additional controls may be appropriate. |
| High | Risk requires prompt management attention and stronger treatment measures. Continued use may need explicit approval and conditions. |

A risk level is not, by itself, an approval or rejection decision. The business owner and authorized management must consider the risk in the context of business need, contractual obligations, available alternatives, and organizational risk appetite.

## 8. Inherent Risk Assessment

Inherent risk is the level of risk before considering the effectiveness of existing controls.

For each scenario:

1. Identify the threat event and the relevant exposure.
2. Consider the sensitivity and importance of the affected information or service.
3. Assess the likelihood without giving credit to existing controls.
4. Assess the potential impact.
5. Apply the risk matrix to determine the inherent risk level.

The inherent assessment provides a view of the exposure that exists because of the nature of the vendor relationship and the scenario itself.

## 9. Existing Control Evaluation

Existing controls are evaluated based on their relevance, implementation, and supporting evidence.

The assessment distinguishes between the following evidence categories:

| Evidence Category | Treatment in Assessment |
|---|---|
| Independent assurance | Evidence from an independent assessment or assurance activity, subject to its scope, period, exceptions, and limitations. |
| Documentary evidence | Written policies, reports, contractual documents, configuration records, or other supplied documentation. |
| Vendor statements | Vendor-provided explanations or claims that have not been independently validated. |
| Internal evidence | Information about Avenloft's own configuration, users, processes, or decisions. |
| Evidence gap | Information or validation needed to determine whether a control is implemented or effective. |

A control is not automatically considered effective merely because the vendor states that it exists.

The following principles apply:

- A control supported by evidence receives more confidence than an unsupported statement.
- A control with an identified exception is not treated as fully effective without considering that exception.
- A remediation claim is not treated as verified without appropriate supporting evidence.
- A control implemented after an assurance period is identified separately from controls tested during that period.
- Avenloft-owned controls are distinguished from vendor-owned controls.
- Proposed recommendations are not counted as existing controls.

## 10. Residual Risk Assessment

Residual risk is the risk remaining after considering the supported effectiveness of existing controls.

For each scenario:

1. Review the inherent likelihood and impact.
2. Identify relevant existing preventive, detective, and corrective controls.
3. Evaluate the evidence supporting each control.
4. Consider known exceptions, weaknesses, incidents, and evidence gaps.
5. Reassess likelihood and impact after taking supported controls into account.
6. Apply the risk matrix again to determine residual risk.

The assessment does not reduce a rating simply because a control is claimed to exist. The reduction must be reasonable in light of the control's relevance and available evidence.

Where evidence is incomplete, the assessment records the uncertainty and avoids assuming that the control is fully effective.

## 11. Risk Treatment

Risk treatment recommendations are designed to address the scenario's underlying causes and reduce its likelihood, impact, or both.

The assessment considers four broad treatment approaches:

| Treatment | Description |
|---|---|
| Mitigate | Introduce or improve controls to reduce likelihood or impact. |
| Avoid | Stop or change the activity that creates the risk. |
| Transfer or Share | Allocate some financial or contractual consequences through appropriate agreements or insurance, where suitable. |
| Accept | Formally retain the risk through an authorized decision based on risk appetite and business context. |

For this assessment, recommendations may include:

- Requiring stronger authentication for all Avenloft users.
- Reviewing and limiting export permissions.
- Establishing a documented access-certification process.
- Obtaining evidence of penetration-test remediation and retesting.
- Reviewing the vendor's vulnerability-management evidence.
- Obtaining validation of tenant-isolation controls.
- Clarifying incident notification requirements in the contract.
- Reviewing and updating the subprocessor list.
- Defining data-retention and deletion requirements.
- Obtaining appropriate deletion evidence when the relationship ends.

These are proposed treatments, not controls confirmed as implemented.

## 12. Target Residual Risk

Target residual risk is the proposed level of risk after recommended treatment actions have been implemented and their effectiveness has been validated.

A target rating is not a statement of the vendor's current security posture.

A target rating should only be considered achieved when:

- The responsible party has implemented the agreed action.
- Appropriate evidence has been provided.
- Any required independent validation or retesting has been completed.
- The assessment has been updated to reflect the validated control state.

Until then, the current residual risk remains the operative assessment.

## 13. Risk Ownership and Accountability

Risk management activities involve both Avenloft and the vendor.

The following ownership roles are proposed based on the stakeholder responsibilities identified in the case packet.

| Stakeholder | Proposed Responsibility |
|---|---|
| Aaron Bell — GRC | Coordinate the assessment, maintain the risk register, track evidence, and monitor remediation. |
| Lena Ortiz — Customer Success | Confirm business usage, user needs, operational dependency, and business impact. |
| Maya Chen — CISO | Provide security oversight and support risk acceptance or escalation decisions within delegated authority. |
| Noah Grant — Procurement | Coordinate vendor relationship and renewal-related requirements. |
| Hannah Kim — Legal & Privacy | Review contractual, privacy, notification, retention, and subprocessor requirements. |
| Marcus Holloway — IT | Validate internal access settings, user permissions, authentication, and technical requirements. |
| CobaltCedar Analytics | Provide vendor-side evidence, implement agreed vendor controls, and communicate relevant security changes. |

These are proposed working responsibilities for the case study. They should not be interpreted as confirmed formal assignments or evidence of approvals.

## 14. Risk Acceptance and Escalation

Risk acceptance must be made by an authorized Avenloft decision-maker in accordance with the organization's risk governance process.

A risk should not be considered accepted solely because:

- The business uses the service.
- The vendor provides a written assurance.
- A remediation date has been proposed.
- A risk has been recorded in a spreadsheet.
- The contract is approaching renewal.

A documented acceptance decision should identify:

- The risk being accepted.
- The current residual risk rating.
- The business rationale.
- Relevant limitations and outstanding evidence gaps.
- The accepting authority.
- Any conditions, monitoring requirements, or review date.

High risks should be escalated for management review. Moderate risks should have documented treatment and monitoring. Low risks should remain subject to normal oversight.

## 15. Assessment Limitations and Assumptions

The assessment is subject to the following limitations:

1. The Avenloft, CobaltCedar Analytics, and SupportLens scenario is fictional and is used for portfolio and learning purposes.
2. The assessment is based on the supplied case packet and does not represent a real vendor investigation.
3. The SOC 2 Type II material is a synthetic report summary rather than the complete underlying report.
4. The penetration-test material is a summary; complete technical findings and independent retest evidence were not supplied.
5. Some security and architecture statements are vendor-provided claims rather than independently verified facts.
6. The assessment does not include direct technical testing of the vendor environment.
7. The assessment does not establish that the open penetration-test finding caused the March 2026 credential-stuffing incident.
8. The assessment does not assume that remediation was completed merely because a target date was stated.
9. Risk ratings are qualitative analyst judgments based on the supplied case information and the case-specific rating matrix.
10. Proposed control improvements and target ratings remain recommendations until implementation and validation are evidenced.

## 16. Reference Frameworks

The methodology is informed by the following publications and guidance:

- **NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments:** Provides guidance for preparing, conducting, communicating, and maintaining information security risk assessments.
- **NIST Cybersecurity Framework 2.0 — GV.SC:** Provides governance outcomes for establishing and managing cybersecurity supply-chain risk.
- **NIST SP 1305 — Integrating Cybersecurity Supply Chain Risk Management into the NIST Cybersecurity Framework:** Explains how organizations can use CSF 2.0 to establish and operate a cybersecurity supply-chain risk management program.
- **NIST SP 1326 — Cybersecurity Supply Chain Risk Management (C-SCRM) Due Diligence Assessment Quick-Start Guide:** Provides guidance for performing C-SCRM due diligence.
- **NIST SP 800-161 Rev. 1 — Cybersecurity Supply Chain Risk Management Practices for Systems and Organizations:** Provides practices for identifying, assessing, and mitigating cybersecurity supply-chain risks.

See `06-references/references.md` for the project reference list and source links.

---

## 17. Methodology Governance

This methodology should be applied consistently across the vendor risk scenarios in this project.

Any change to a risk rating should be supported by a documented reason, such as:

- New evidence becoming available.
- A control being implemented and validated.
- A control exception being identified.
- A material change in the vendor relationship.
- A new incident or threat.
- A change in the data processed or the service's business use.

The risk register should preserve the distinction between the original assessment, current residual risk, recommended treatment, and validated target risk.