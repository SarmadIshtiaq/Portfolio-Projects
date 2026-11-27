
# Integrated GRC Governance Framework

**Portfolio:** Integrated GRC Framework Design & Implementation

**Case reference:** [Uber 2016 Data Breach Case Study](../01-case-study/README.md)

**Problem reference:** [Part 02 — Problem Analysis](../02-problem-analysis/README.md)

**Framework reference:** NIST Cybersecurity Framework (CSF) 2.0

**Document type:** Proposed Governance Framework

**Status:** In Progress

**Writing reference:** ASD-STE100 Issue 9

---

## 1. Purpose

This document defines a proposed GRC governance framework.

It explains how an organisation should assign security and compliance responsibilities.

It also defines reporting lines, decision authority, and management oversight.

The framework uses the problems identified in the Uber 2016 case study as a design reference.

This is an independent framework design. It does not describe Uber's actual internal governance structure.

## 2. Governance Framework Objectives

The proposed framework has six objectives:

1. Assign clear ownership of security and compliance responsibilities.
2. Define approval and decision-making authority.
3. Establish accountability for security controls.
4. Connect risk management with business decisions.
5. Define incident escalation and reporting procedures.
6. Provide regular oversight of risks and corrective actions.

The framework addresses the problems identified in [Part 02 — Problem Analysis](../02-problem-analysis/README.md).

## 3. Governance Design Basis

This framework uses the Govern function of NIST CSF 2.0.

NIST defines six categories under this function:

| NIST category | Governance focus |
|---|---|
| GV.OC — Organizational Context | Understand the organisation and its stakeholders. |
| GV.RM — Risk Management Strategy | Establish risk priorities and risk appetite. |
| GV.RR — Roles, Responsibilities, and Authorities | Define ownership and decision authority. |
| GV.PO — Policy | Establish and maintain security policies. |
| GV.OV — Oversight | Monitor governance and risk performance. |
| GV.SC — Cybersecurity Supply Chain Risk Management | Manage cybersecurity risks from suppliers and third parties. |

**Official reference:** [NIST Cybersecurity Framework 2.0 — Govern Function](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf)

NIST CSF 2.0 provides cybersecurity outcomes. It does not prescribe one organisational structure for every organisation.

This portfolio uses the framework to design a proposed governance model.

## 4. Proposed GRC Governance Structure

The following structure defines the proposed reporting and oversight model.

```text
             Board / Risk Committee
                       |
                       v
               Executive Sponsor
                       |
                       v
              GRC Steering Committee
                       |
          +------------+------------+
          |            |            |
          v            v            v
       GRC Lead    Security Lead   Privacy / Legal
          |            |
          |            v
          |       IT / Engineering
          |       Control Owners
          |
          v
     Risk and Compliance
     Monitoring and Reporting


     Internal Audit
     Independent assurance function
```

### 4.1 Board or Risk Committee

The Board or Risk Committee provides strategic oversight.

Its proposed responsibilities include:

- Approve the organisation's risk appetite.
- Review significant security risks.
- Review major risk exceptions.
- Monitor important incidents.
- Oversee management's response to significant risks.

### 4.2 Executive Sponsor

The Executive Sponsor provides management support.

Its proposed responsibilities include:

- Approve the GRC framework.
- Assign resources.
- Support policy implementation.
- Resolve major ownership issues.
- Escalate significant risks to the Board or Risk Committee.

### 4.3 GRC Steering Committee

The GRC Steering Committee coordinates governance activities.

Its proposed responsibilities include:

- Review the enterprise risk register.
- Review compliance status.
- Monitor corrective actions.
- Review important security incidents.
- Coordinate departments and control owners.
- Report significant issues to executive management.

### 4.4 GRC Lead

The GRC Lead coordinates the GRC programme.

Its proposed responsibilities include:

- Maintain the GRC framework.
- Coordinate risk assessments.
- Maintain the compliance register.
- Track control ownership.
- Monitor corrective actions.
- Prepare management reports.

The GRC Lead coordinates the programme. Control owners remain responsible for implementing their assigned controls.

### 4.5 Security Lead

The Security Lead manages security operations and control requirements.

Its proposed responsibilities include:

- Define security requirements.
- Monitor identity and access controls.
- Oversee security incident response.
- Review cloud security risks.
- Coordinate security remediation.
- Report significant security issues.

### 4.6 Control Owners

Control Owners implement and maintain assigned controls.

Examples include:

- IT administrators.
- Cloud engineers.
- Software development teams.
- System administrators.

Their proposed responsibilities include:

- Implement assigned controls.
- Maintain control evidence.
- Review access permissions.
- Report control failures.
- Complete corrective actions.

### 4.7 Privacy and Legal

Privacy and Legal provide advice on legal and regulatory obligations.

Their proposed responsibilities include:

- Identify applicable privacy obligations.
- Review incident disclosure requirements.
- Advise on regulatory notification.
- Review privacy-related policies.
- Support communication with regulators.

### 4.8 Internal Audit

Internal Audit provides independent assurance.

Its proposed responsibilities include:

- Review the design of governance processes.
- Assess control effectiveness independently.
- Report findings.
- Monitor agreed audit actions.

Internal Audit should not operate the controls that it independently reviews.

## 5. Roles and Responsibilities

| Activity | Main responsible role |
|---|---|
| Risk appetite | Board or Risk Committee |
| GRC framework approval | Executive Sponsor |
| GRC programme coordination | GRC Lead |
| Security policy ownership | Security Lead |
| Technical control implementation | Control Owner |
| Risk and compliance monitoring | GRC Lead |
| Incident response | Security Lead |
| Regulatory notification assessment | Privacy and Legal |
| Independent assurance | Internal Audit |

These are proposed responsibilities for this portfolio framework.

Actual assignments should reflect the size and structure of the organisation.

## 6. RACI Matrix

RACI defines participation in each activity.

- **R — Responsible:** Performs the work.
- **A — Accountable:** Owns the final result.
- **C — Consulted:** Provides advice or input.
- **I — Informed:** Receives updates.

The following matrix is a proposed responsibility model.

| Activity | Board / Risk Committee | Executive Sponsor | GRC Lead | Security Lead | Control Owner | Privacy / Legal | Internal Audit |
|---|---|---|---|---|---|---|---|
| Approve risk appetite | A | R | C | C | C | C | I |
| Approve GRC framework | I | A | R | C | C | C | I |
| Maintain risk register | I | I | A | C | R | C | I |
| Approve security policies | I | A | C | R | C | C | I |
| Implement GitHub MFA | I | I | C | C | A/R | I | I |
| Manage cloud secrets | I | I | C | C | A/R | I | I |
| Monitor controls | I | I | A | C | R | C | I |
| Coordinate incident response | I | I | C | A | R | C | I |
| Assess regulatory notification | I | A | C | C | I | R | I |
| Track corrective actions | I | I | A | C | R | C | I |
| Perform independent assurance | I | I | C | I | I | I | A/R |

Each activity has one accountable role.

The matrix is a proposed design. An organisation should approve the final assignments.

## 7. Decision Authority and Escalation

The framework uses defined escalation levels.

| Level | Responsible role | Action |
|---|---|---|
| Level 1 | Control Owner | Report and address a control issue. |
| Level 2 | Security Lead | Assess security impact and coordinate response. |
| Level 3 | GRC Lead | Record the risk and monitor corrective action. |
| Level 4 | Executive Sponsor | Approve major decisions and resources. |
| Level 5 | Board or Risk Committee | Review significant risks and exceptions. |

### Escalation examples

- A suspected cloud credential exposure must be reported to the Security Lead.
- A high-risk control failure must be recorded and assigned to an owner.
- A risk that exceeds approved risk appetite must be escalated to management.
- A possible personal data breach must be referred to Privacy and Legal for reporting assessment.

Applicable notification duties and deadlines require a separate legal assessment.

## 8. Governance Reporting and Oversight

The proposed framework uses regular management reviews.

| Review | Frequency | Main purpose |
|---|---|---|
| Control Owner review | Monthly | Review control operation and evidence. |
| GRC Steering Committee | Monthly | Review risks, compliance gaps, and corrective actions. |
| Executive review | Quarterly | Review significant risks and management decisions. |
| Board or Risk Committee | Quarterly | Review risk exposure and major exceptions. |
| Incident review | After a significant incident | Review response and identify improvements. |

These are proposed reporting intervals, not requirements imposed by NIST.

### Proposed Governance Metrics

The organisation can monitor:

- Percentage of high risks with assigned owners.
- Number of overdue corrective actions.
- Percentage of critical accounts protected by MFA.
- Number of open security policy exceptions.
- Number of incidents escalated within the defined process.
- Number of unresolved high-priority control findings.

The metrics must use defined owners, reporting periods, and calculation rules.

## 9. Governance Documents and Records

The proposed framework requires the following records:

| Document or record | Purpose |
|---|---|
| GRC Charter | Defines the purpose and authority of the GRC programme. |
| Roles and Responsibilities | Defines ownership and duties. |
| RACI Matrix | Defines participation in key activities. |
| Risk Appetite Statement | Defines acceptable risk boundaries. |
| Policy Register | Tracks approved policies and owners. |
| Risk Register | Records identified risks and treatments. |
| Governance Meeting Minutes | Records decisions and discussions. |
| Exception Register | Records approved control exceptions. |
| Corrective Action Tracker | Tracks gaps and assigned actions. |
| Governance Dashboard | Reports governance performance. |

The risk register and corrective action tracker will be developed in later project sections.

## 10. Alignment with Problem Analysis

The governance model responds to the problems identified in [Part 02 — Problem Analysis](../02-problem-analysis/README.md).

| Problem ID | Problem area | Governance response |
|---|---|---|
| PA-01 | Credential and authentication management | Assign identity and access control ownership. |
| PA-02 | Secrets management | Assign ownership of cloud credentials and secrets policies. |
| PA-03 | Cloud access control | Assign cloud control owners and review responsibilities. |
| PA-04 | Data protection | Define security and privacy responsibilities. |
| PA-05 | Incident response and disclosure | Define escalation and notification responsibilities. |
| PA-06 | Governance and accountability | Establish executive oversight and decision authority. |

These are proposed governance responses. They are not descriptions of Uber's internal governance arrangements.

## 11. Limitations

This is an independent portfolio framework design.

It uses public incident information and the NIST CSF 2.0 as a design reference.

It does not represent:

- An actual governance structure at Uber.
- A governance implementation at a real organisation.
- An internal or external audit.
- A legal compliance opinion.
- An approved organisational policy.

The proposed roles and reporting structure must be adapted to the organisation that uses them.

## 12. Official References

- [NIST — Cybersecurity Framework 2.0 (2024)](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20)
- [NIST — Cybersecurity Framework 2.0 Full Publication (PDF)](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf)
- [FTC — Uber Revised Complaint (2018)](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)
- [DOJ — Uber Non-Prosecution Agreement (2022)](https://www.justice.gov/d9/press-releases/attachments/2022/07/22/executed_uber_npa.pdf)
- [ASD-STE100 — Official Standard](https://www.asd-ste100.org/)

---

**Writing note:** This document uses ASD-STE100 Issue 9 writing principles. Full compliance has not yet been verified against the complete specification.

**Next step:** Develop the Risk Management Methodology and Risk Register.
