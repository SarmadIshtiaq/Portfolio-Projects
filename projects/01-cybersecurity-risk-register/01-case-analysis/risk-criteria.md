# Avenloft Systems Group — Risk Criteria and Rating Methodology

**Project ID:** GRC-RISK-001  
**Document:** Risk Assessment Criteria  
**Organisation:** Avenloft Systems Group (Fictional)  
**Assessment Period:** FY2027 Planning  
**Primary Method:** NIST SP 800-30 Rev. 1, Appendix I, Table I-2  
**Status:** Assessment criteria documented

## 1. Purpose

This document defines the criteria and method for assessing cybersecurity risk in the Avenloft Systems Group training case.

It establishes a consistent approach for:

- Writing business-focused risk scenarios.
- Assessing inherent likelihood and impact.
- Evaluating existing controls.
- Assessing residual likelihood and impact.
- Determining qualitative risk levels.
- Comparing residual risks with management's stated risk appetite.
- Recommending risk treatment.
- Supporting risk prioritisation and escalation.

**Primary case reference:** [Avenloft Cybersecurity Risk Register Case Packet — Avenloft Risk Assessment Method, pages 10–12](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 2. Authoritative Methodology

For this exercise, Avenloft uses the qualitative risk-level matrix published in:

[NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments](https://csrc.nist.gov/pubs/sp/800/30/r1/final), Appendix I, Table I-2.

NIST presents the assessment scale as an example that organisations can tailor. Avenloft uses the published five-level matrix directly for this training exercise.

The following are fictional Avenloft-specific rules:

- The organisation's risk appetite and tolerance.
- Its use of the matrix for inherent and residual risk.
- Its escalation and approval requirements.
- Its governance and risk-review arrangements.

These company rules must not be represented as NIST requirements.

**Sources:** [Avenloft Case Packet — Methodology Note, page 13](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=13) and [NIST SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final).

## 3. Risk Scenario Construction

Every risk statement must connect a plausible threat event or failure condition to a business consequence.

### Required structure

> If [threat event or failure] exploits / occurs alongside [condition or weakness], then [asset, process, or objective] may experience [business impact].

### Risk statement requirements

A good risk statement must:

- Describe a plausible event or failure.
- Identify the condition or weakness that may contribute to the event.
- Identify the affected asset, service, business process, or objective.
- Explain the potential business impact.
- Use clear language that management can understand.

### Example

**Technical observation:**

The full application and database restore exercise has not been performed for 14 months.

**Business-focused risk scenario:**

If a production disruption requires restoration of the application and database, but the recovery procedures or backups cannot restore services successfully within the expected recovery period, Avenloft Relay may remain unavailable beyond the business tolerance, affecting customer operations and contractual commitments.

This is an illustrative transformation of the case observation, not a final risk assessment or assigned rating.

**Source:** [Avenloft Case Packet — Risk Scenario Guidance, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 4. Inherent Risk Assessment

**Definition:** Inherent risk is the estimated risk before giving credit to the existing controls listed in the case.

For every risk scenario:

1. Understand the threat event or failure.
2. Identify the affected business objective, asset, or process.
3. Assess the overall likelihood of the scenario occurring and resulting in adverse impact.
4. Assess the level of business impact.
5. Use the qualitative matrix to determine the inherent risk level.

Inherent likelihood and impact are analytical estimates based on available evidence. They are not predictions.

**Source:** [Avenloft Case Packet — Rate Inherent Risk, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 5. Existing Control Assessment

Before assigning residual risk, identify the safeguards that are already operating.

For every relevant control, assess whether it materially reduces:

- The likelihood of the risk scenario.
- The impact if the scenario occurs.
- Both likelihood and impact.
- Neither, where the control does not address the particular scenario.

### Control assessment principles

- A control must actually exist or be operating before it receives credit.
- A proposed recommendation is not an existing control.
- A temporary safeguard must be identified as temporary.
- Control effectiveness must be considered using the available evidence.
- A control should not receive full credit simply because it exists.
- Missing evidence should be documented as an uncertainty.

**Source:** [Avenloft Case Packet — Evaluate Existing Controls, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 6. Residual Risk Assessment

**Definition:** Residual risk is the risk that remains after considering the existing controls.

For every risk scenario:

1. Review the inherent likelihood and impact.
2. Identify relevant current controls.
3. Determine how those controls affect the scenario.
4. Reassess overall likelihood.
5. Reassess impact.
6. Use the same qualitative matrix to determine residual risk.

Residual risk is the primary rating used for prioritisation in this exercise.

A recommended control must not be included as an existing control. Its expected effect should be discussed under treatment recommendations instead.

**Source:** [Avenloft Case Packet — Rate Residual Risk, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 7. Overall Likelihood Scale

Use the following five qualitative likelihood levels.

| Rating | Working Guidance for This Case |
|---|---|
| Very Low | The threat event occurring and resulting in adverse impact is highly unlikely based on the available evidence. |
| Low | The scenario is unlikely to produce adverse impact, although it remains plausible. |
| Moderate | The scenario is somewhat likely to occur and result in adverse impact. |
| High | The scenario is highly likely to occur and result in adverse impact. |
| Very High | The scenario is almost certain to occur and result in adverse impact. |

The likelihood assessment must consider the complete risk scenario rather than the existence of a technical weakness alone.

**Source:** [Avenloft Case Packet — Overall Likelihood Scale, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 8. Impact Scale

Use the following impact definitions as applied to Avenloft.

| Rating | Impact Definition |
|---|---|
| Very Low | Negligible adverse effect; little meaningful effect on operations, assets, customers, or objectives. |
| Low | Limited adverse effect that can be handled through normal operations. |
| Moderate | Serious adverse effect requiring management attention, such as meaningful service, customer, financial, or assurance impact. |
| High | Severe or catastrophic adverse effect, such as major service loss, customer harm, or significant contractual or financial consequence. |
| Very High | Multiple severe or catastrophic adverse effects with broad or sustained consequences for Avenloft and its stakeholders. |

Impact must be connected to the business consequences of the risk scenario.

**Source:** [Avenloft Case Packet — Impact Scale, page 10](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=10).

## 9. Qualitative Risk-Level Matrix

Use this matrix to determine the risk level from overall likelihood and impact.

### Risk determination matrix

| Likelihood / Impact | Very Low | Low | Moderate | High | Very High |
|---|---|---|---|---|---|
| Very High | Very Low | Low | Moderate | High | Very High |
| High | Very Low | Low | Moderate | High | Very High |
| Moderate | Very Low | Low | Moderate | Moderate | High |
| Low | Very Low | Low | Low | Low | Moderate |
| Very Low | Very Low | Very Low | Very Low | Low | Low |

### Important scoring rule

Do not multiply ordinal labels or assign invented numerical values to them.

For example:

- High likelihood + Moderate impact = Moderate risk.
- Moderate likelihood + High impact = Moderate risk.
- Low likelihood + Very High impact = Moderate risk.
- Very High likelihood + Very High impact = Very High risk.

These results must come directly from the published matrix.

The same matrix is used for inherent and residual risk.

**Sources:** [Avenloft Case Packet — Risk Determination Matrix, page 11](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11) and [NIST SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final).

## 10. Avenloft Risk Appetite and Tolerance

Leadership has provided directional risk appetite guidance.

These statements influence treatment decisions. They do not automatically determine a risk's qualitative rating.

| Risk Area | Leadership Direction | Assessment Consideration |
|---|---|---|
| Customer Data Confidentiality | Low tolerance for unauthorised disclosure or uncontrolled third-party use of customer information. | Evaluate exposure of customer information and safeguards against unauthorised access or disclosure. |
| Privileged Access | Low tolerance for weak authentication, stale privileged accounts, or untraceable administrative activity. | Evaluate privileged access, authentication, account lifecycle, and accountability. |
| Production Availability | Low tolerance for outages exceeding four hours during business operations. Recovery capability is business-critical. | Consider service disruption and recovery capability. |
| Critical Vulnerabilities | No acceptance of known critical internet-facing vulnerabilities beyond 30 days without a current written exception and compensating controls. | Review vulnerability age, remediation status, and the validity of exceptions and safeguards. |
| Internal Productivity | Moderate tolerance for short, reversible productivity interruptions that do not affect customers or material financial reporting. | Distinguish internal inconvenience from material business impact. |
| Experimentation and AI | Moderate appetite for controlled pilots; low tolerance for customer or confidential data entering unapproved tools. | Consider approved scope, data handling, governance, and safeguards. |

### How to use risk appetite

Risk appetite must be considered alongside the calculated residual risk.

A Moderate residual risk may still require prompt treatment if it conflicts with a stated tolerance or strategic objective.

**Source:** [Avenloft Case Packet — Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3), and [Risk Determination, page 11](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11).

## 11. Residual Risk Handling and Escalation

Avenloft uses the following expectations for residual risk.

| Residual Risk | Expected Handling |
|---|---|
| Very Low | Monitor through normal control ownership. |
| Low | Monitor; treatment may still be appropriate when the risk conflicts with a stated tolerance. |
| Moderate | Assign an accountable owner and document a treatment decision or rationale. |
| High | Document a treatment plan and target date; escalate to the CISO for review. |
| Very High | Provide immediate executive visibility and formal treatment; acceptance requires executive leadership approval. |

### Governance requirements

- High and above residual risks must have a named owner and treatment plan.
- High and Very High residual risks require CISO review.
- Acceptance of Very High residual risk requires executive leadership approval.
- The risk register is reviewed quarterly and before major executive planning cycles.
- The Security Steering Committee meets monthly.

These are Avenloft case-specific governance requirements.

**Sources:** [Avenloft Case Packet — Organization and Governance Context, page 4](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=4) and [Residual Risk Handling, page 11](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11).

## 12. Risk Response Options

Each risk must have a recommended response.

| Response | When to Use It |
|---|---|
| Mitigate | Additional controls or process changes can reduce likelihood and/or impact. |
| Avoid | The activity creating the risk can be stopped or redesigned so the scenario no longer exists. |
| Transfer / Share | A contract, insurance arrangement, service provider, or another mechanism shifts or shares part of the consequence. Accountability is not eliminated. |
| Accept | The accountable authority explicitly agrees to retain the residual risk within delegated tolerance, with a rationale and review date. |

### Treatment recommendation requirements

Each treatment recommendation should explain:

- What action should be taken.
- Why the action is appropriate.
- Which control or process change is required.
- Who should be accountable.
- The proposed target date.
- Whether management approval or escalation is required.

**Source:** [Avenloft Case Packet — Risk Response Options, page 11](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11).

## 13. Risk Ownership Rules

The risk owner should normally be the accountable business or technology leader responsible for the affected outcome.

Examples of case-defined accountability:

| Area | Relevant Accountable Role |
|---|---|
| Product engineering and cloud production | Priya Nair — VP, Engineering |
| Workforce identity, endpoints, and corporate infrastructure | Marcus Holloway — Director, IT & Workplace Technology |
| Customer support and customer-data workflows | Lena Ortiz — VP, Customer Success |
| Procurement and vendor onboarding | Noah Grant — Director, Procurement |
| Business continuity and financial operations | Elena Ruiz — VP, Finance & Operations |
| Employee lifecycle processes | Jared Cole — Head of People Operations |

The final owner must be selected according to the actual risk scenario.

GRC facilitates and monitors risk management. It does not automatically own every risk.

**Sources:** [Avenloft Case Packet — Governance Roles, page 4](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=4) and [Facts You Should Not Assume, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

## 14. Risk Register Documentation Requirements

Every risk record must contain the following information.

| Field | Required Information |
|---|---|
| Risk ID | Unique identifier such as R-001 |
| Risk Title | Short, business-readable name |
| Risk Statement | Scenario connecting a threat or failure, condition, affected asset/process, and business impact |
| Business Objective / Asset | Exposed business objective, process, data, system, or service |
| Evidence / Source | Observation IDs or stakeholder notes supporting the scenario |
| Inherent Likelihood | Qualitative likelihood before existing controls |
| Inherent Impact | Qualitative impact before existing controls |
| Inherent Risk Level | Result from the qualitative matrix |
| Existing Controls | Safeguards already operating or temporarily mitigating the condition |
| Residual Likelihood | Qualitative likelihood after considering current controls |
| Residual Impact | Qualitative impact after considering current controls |
| Residual Risk Level | Result from the same qualitative matrix |
| Treatment Recommendation | Mitigate, Avoid, Transfer/Share, or Accept with rationale |
| Risk Owner | Accountable business or technology leader |
| Target Action / Due Date | Practical next step and proposed timing |
| Status / Uncertainty | Open, In Treatment, Accepted, Needs Validation, or another suitable status; include material unknowns |

**Source:** [Avenloft Case Packet — Required Risk Register Fields, page 12](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=12).

## 15. Risk Prioritisation Rules

The top-five prioritisation must focus on residual risk.

The selection should consider:

- Residual risk level.
- The business objective affected.
- Avenloft's stated risk appetite and tolerance.
- Existing safeguards.
- The practical urgency of treatment.
- Important uncertainty that could change the decision.

The five risks must be listed in priority order with a clear explanation of why each matters to Avenloft.

Do not rank every observation as High or Very High.

A Moderate risk may still deserve urgent attention when it conflicts with a stated tolerance or strategic objective.

**Sources:** [Avenloft Case Packet — Risk Determination, page 11](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=11) and [Quality Bar for the Analyst, page 13](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=13).

## 16. Executive Risk Summary Requirements

The executive risk summary must remain one page and include:

1. **Overall risk posture:** Two to four sentences describing the dominant risk themes.
2. **Top-five residual risks:** List risks in priority order and explain why each matters.
3. **Immediate actions:** Identify three to five actions leadership should fund, assign, or escalate first.
4. **Important unknowns:** Identify missing information that could materially change a rating or treatment decision.
5. **Management message:** Explain the assessment in language that non-technical leaders can understand.

**Source:** [Avenloft Case Packet — Executive Summary Structure, page 12](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=12).

## 17. Assessment Restrictions

The following restrictions apply to this project:

- An observation is not automatically a control failure.
- A control gap is not automatically a High or Very High risk.
- The absence of evidence does not prove that a control does not exist.
- A vulnerability score is not the same as a business risk score.
- Do not invent facts, control effectiveness, or missing evidence.
- Record assumptions and mark material unknowns as Needs Validation.
- Do not treat recommended safeguards as existing controls.
- Do not assign every risk to GRC or simply to IT.
- Keep the risk assessment connected to Avenloft's stated business objectives.

**Source:** [Avenloft Case Packet — Facts You Should Not Assume, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9).

## 18. Reference List

1. [Avenloft Cybersecurity Risk Register Case Packet — GRC-RISK-001](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf).
2. [NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments](https://csrc.nist.gov/pubs/sp/800/30/r1/final).
3. [NIST IR 8286 Rev. 1 — Integrating Cybersecurity and Enterprise Risk Management](https://csrc.nist.gov/pubs/ir/8286/r1/final).
4. [NIST IR 8286A Rev. 1 — Identifying and Estimating Cybersecurity Risk for Enterprise Risk Management](https://csrc.nist.gov/pubs/ir/8286/a/r1/final).
5. [NIST IR 8286B — Prioritizing Cybersecurity Risk for Enterprise Risk Management](https://csrc.nist.gov/pubs/ir/8286/b/final).
6. [NIST Cybersecurity Framework 2.0 Resource Center](https://www.nist.gov/cyberframework).

## 19. Methodology Limitations

This methodology is designed for the fictional Avenloft training case.

The qualitative ratings depend on the evidence supplied and the analyst's reasoned judgement. Different analysts may reach different ratings where they have different defensible interpretations.

The matrix does not replace management judgement, risk ownership, or approval authority.

A final risk decision must explain the evidence, rating rationale, existing controls, remaining uncertainty, and recommended response.

## 20. Document Status

**Status:** Criteria documented.

Risk scenarios, inherent ratings, residual ratings, treatment decisions, and prioritisation have not yet been completed.