
# Integrated GRC Framework — Risk Management

**Portfolio:** Integrated GRC Framework Design & Implementation

**Case reference:** [Uber 2016 Data Breach Case Study](../01-case-study/README.md)

**Problem reference:** [Part 02 — Problem Analysis](../02-problem-analysis/README.md)

**Governance reference:** [Part 03 — Governance Framework](../03-governance-framework/README.md)

**Risk assessment reference:** [NIST SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final)

**Status:** In Progress

**Writing reference:** ASD-STE100 Issue 9

---

## 1. Purpose

This document defines a proposed risk management methodology.

It converts the problems identified in the Uber 2016 case study into structured risk statements.

It also defines how an organisation can assess, prioritise, treat, and monitor these risks.

This is an independent portfolio exercise.

It does not represent Uber's actual risk register or risk ratings.

## 2. Risk Management Objectives

The proposed methodology has six objectives:

1. Identify relevant security risks.
2. Define clear risk statements.
3. Assess likelihood and impact.
4. Prioritise risks.
5. Assign risk owners and treatment actions.
6. Monitor risks and review treatment results.

## 3. Risk Assessment Methodology

This methodology uses guidance from [NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments](https://csrc.nist.gov/pubs/sp/800/30/r1/final).

NIST describes risk assessment as an activity that considers threat events, vulnerabilities, likelihood, and impact.

This portfolio uses a simplified 5 × 5 qualitative scoring model.

The model is a proposed assessment method. It is not a scoring formula prescribed by NIST.

### 3.1 Risk Statement Format

Each risk statement follows this structure:

**Because [cause], [risk event] may occur, resulting in [business impact].**

Example:

Because an AWS access key may be exposed in source code, an unauthorised person may use the key to access cloud data, resulting in exposure of personal information.

The example is based on the documented Uber incident. [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

### 3.2 Likelihood Scale

Likelihood measures how probable a risk event is within the defined assessment scenario.

| Score | Level | Meaning |
|---|---|---|
| 1 | Rare | Very unlikely to occur. |
| 2 | Unlikely | Could occur, but is not expected. |
| 3 | Possible | Could occur under some conditions. |
| 4 | Likely | Expected to occur in relevant conditions. |
| 5 | Almost Certain | Expected to occur frequently or repeatedly. |

### 3.3 Impact Scale

Impact measures the possible consequence if the risk event occurs.

Consider:

- Confidentiality of information.
- Operational disruption.
- Financial loss.
- Legal or regulatory consequences.
- Customer trust and reputation.

| Score | Level | Meaning |
|---|---|---|
| 1 | Insignificant | Minimal business effect. |
| 2 | Minor | Limited effect that requires routine action. |
| 3 | Moderate | Noticeable effect that requires management attention. |
| 4 | Major | Significant business, financial, or security effect. |
| 5 | Severe | Critical effect on business operations, sensitive data, or regulatory responsibilities. |

### 3.4 Risk Score Calculation

The proposed calculation is:

**Risk Score = Likelihood × Impact**

Example:

- Likelihood = 4
- Impact = 5
- Risk Score = 20

### 3.5 Risk Rating

| Score | Rating | Proposed response |
|---|---|---|
| 1–4 | Low | Record and monitor the risk. |
| 5–9 | Moderate | Assign an owner and review the risk. |
| 10–16 | High | Establish a formal treatment plan and report to management. |
| 17–25 | Critical | Escalate to executive management and prioritise treatment. |

These thresholds are proposed for this portfolio methodology.

An organisation must approve its own risk appetite and acceptance authority.

## 4. Inherent and Residual Risk

Risk assessment uses two important concepts.

### 4.1 Inherent Risk

Inherent risk is the risk before considering the effect of controls.

It helps identify the level of exposure without relying on control protection.

### 4.2 Residual Risk

Residual risk is the risk that remains after controls have been implemented and their effectiveness has been assessed.

A proposed control does not automatically reduce residual risk.

The organisation must review evidence and test the control before assigning a residual rating.

**For this portfolio:** Residual risk is marked as Not Assessed because the proposed controls have not been implemented and tested in a real organisation.

## 5. Risk Assessment Register

The following register contains six illustrative risks.

Each risk maps to a problem identified in [Part 02 — Problem Analysis](../02-problem-analysis/README.md).

The initial scores are proposed ratings for the portfolio reference scenario.

They are not Uber's historical risk scores.

| Risk ID | Related problem | Risk statement | Likelihood | Impact | Score | Rating |
|---|---|---|---:|---:|---:|---|
| R-01 | PA-01 | Compromised credentials may allow unauthorised access to private repositories, resulting in source-code exposure. | 4 | 4 | 16 | High |
| R-02 | PA-02 | An exposed cloud credential may allow unauthorised access to cloud resources, resulting in sensitive data exposure. | 4 | 5 | 20 | Critical |
| R-03 | PA-03 | A compromised cloud credential may enable unauthorised access to stored data, resulting in data loss or disclosure. | 3 | 5 | 15 | High |
| R-04 | PA-04 | Unencrypted personal information may be read after unauthorised access, resulting in privacy harm. | 3 | 5 | 15 | High |
| R-05 | PA-05 | Delayed incident escalation or notification may result in regulatory, legal, and reputational consequences. | 3 | 4 | 12 | High |
| R-06 | PA-06 | Unclear accountability for incident decisions may delay escalation and weaken management oversight. | 3 | 5 | 15 | High |

### Risk Evidence

**R-01 — Credential compromise**

The FTC complaint states that attackers used credentials exposed in earlier data breaches to access Uber's private GitHub repositories. It also describes the MFA and credential reuse policy issues. [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

**R-02 — Exposed cloud credentials**

The FTC complaint and DOJ agreement describe the AWS access key found in source code and its use to access cloud data. [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf) [DOJ Executed Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

**R-03 — Cloud data access**

The DOJ agreement describes the attackers' access to Uber's cloud environment and the data they obtained. [DOJ Executed Agreement](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)

**R-04 — Personal data protection**

The FTC complaint states that the downloaded files contained unencrypted personal information. [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

**R-05 — Incident disclosure**

The FTC complaint records that Uber notified affected consumers on 21 November 2017 after learning about the breach in November 2016. [FTC Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)

**R-06 — Governance and accountability**

Uber's DOJ non-prosecution agreement records its admission and acceptance of responsibility for the concealment of the incident from the FTC. [DOJ Non-Prosecution Agreement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)

## 6. Risk Treatment Plan

Risk treatment defines actions that an organisation can take to manage identified risks.

This portfolio uses four treatment options:

| Treatment | Meaning |
|---|---|
| Mitigate | Reduce likelihood or impact through controls. |
| Avoid | Stop the activity that creates the risk. |
| Transfer or Share | Transfer or share some financial or operational exposure through an appropriate arrangement. |
| Accept | Retain the risk with approval from an authorised owner. |

### Proposed Treatment Actions

| Risk ID | Proposed treatment | Main actions | Proposed owner |
|---|---|---|---|
| R-01 | Mitigate | Require MFA, prohibit credential reuse, and review repository access. | Security Lead |
| R-02 | Mitigate | Use a secrets manager, scan source code, and rotate exposed keys. | Cloud / IT Control Owner |
| R-03 | Mitigate | Restrict cloud permissions, apply least privilege, and monitor storage access. | Cloud / IT Control Owner |
| R-04 | Mitigate | Classify personal data, encrypt sensitive information, and protect backups. | Security Lead |
| R-05 | Mitigate | Define incident escalation procedures and assess notification duties. | Security Lead and Privacy / Legal |
| R-06 | Mitigate | Define executive accountability, approval procedures, and incident reporting lines. | Executive Sponsor and GRC Lead |

These are proposed actions.

They are not verified controls implemented by Uber.

The proposed owners follow the roles defined in [Part 03 — Governance Framework](../03-governance-framework/README.md).

## 7. Risk Ownership and Monitoring

Each risk requires an accountable owner.

The owner must:

- Review the assigned risk.
- Maintain supporting evidence.
- Coordinate treatment actions.
- Report delays and control failures.
- Request approval for risk acceptance where required.

The GRC Lead coordinates risk monitoring.

The Security Lead monitors security-related treatment actions.

The Executive Sponsor reviews risks that require management decisions.

These assignments follow the proposed governance model in [Part 03 — Governance Framework](../03-governance-framework/README.md).

### Proposed Monitoring Frequency

| Risk level | Proposed review frequency |
|---|---|
| Critical | Monthly or after a significant change |
| High | Monthly |
| Moderate | Quarterly |
| Low | Quarterly or during scheduled review |

These are proposed review intervals, not NIST-mandated frequencies.

## 8. Residual Risk Assessment

Residual risk will be assessed after the proposed controls have been implemented and tested.

| Risk ID | Proposed controls implemented? | Control evidence reviewed? | Residual risk |
|---|---|---|---|
| R-01 | No | No | Not Assessed |
| R-02 | No | No | Not Assessed |
| R-03 | No | No | Not Assessed |
| R-04 | No | No | Not Assessed |
| R-05 | No | No | Not Assessed |
| R-06 | No | No | Not Assessed |

The portfolio does not claim that these controls have been implemented in Uber or another organisation.

## 9. Risk Reporting

The proposed GRC dashboard will report:

- Total identified risks.
- Risks by rating.
- Risks by owner.
- Open treatment actions.
- Overdue actions.
- Risks with no assigned owner.
- Risks awaiting acceptance.
- Residual risks after control assessment.

The dashboard will be developed in the later Google Sheets and Power BI project sections.

## 10. Limitations

This is an independent risk management framework design.

It uses public incident information and published NIST guidance.

The project does not represent:

- Uber's actual risk register.
- Uber's internal risk ratings.
- A real organisational risk assessment.
- An implementation of security controls at Uber.
- A legal or regulatory compliance opinion.

The likelihood and impact scores are illustrative.

They require validation against an organisation's business context, risk appetite, control environment, and available evidence before operational use.

## 11. Next Step

The next project phase is Compliance Management.

It will identify relevant obligations and map them to proposed security controls.

The compliance work will use official regulatory and framework sources.

## 12. Official References

- [NIST SP 800-30 Rev. 1 — Guide for Conducting Risk Assessments](https://csrc.nist.gov/pubs/sp/800/30/r1/final)
- [NIST SP 800-30 Rev. 1 — Full Publication (PDF)](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-30r1.pdf)
- [NIST Cybersecurity Framework 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20)
- [NIST SP 800-53 Rev. 5 — Security and Privacy Controls](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)
- [FTC — Uber Revised Complaint](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)
- [DOJ — Uber Non-Prosecution Agreement](https://www.justice.gov/usao-ndca/pr/uber-enters-non-prosecution-agreement)
- [DOJ — Executed Non-Prosecution Agreement (PDF)](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)
- [ASD-STE100 — Official Standard](https://www.asd-ste100.org/)

---

**Writing note:** This document uses ASD-STE100 Issue 9 writing principles. Full compliance has not yet been verified against the complete specification.
