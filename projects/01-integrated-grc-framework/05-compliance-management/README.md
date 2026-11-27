
# Integrated GRC Framework — Compliance Management

**Portfolio:** Integrated GRC Framework Design & Implementation

**Case reference:** [Uber 2016 Data Breach Case Study](../01-case-study/README.md)

**Problem reference:** [Part 02 — Problem Analysis](../02-problem-analysis/README.md)

**Governance reference:** [Part 03 — Governance Framework](../03-governance-framework/README.md)

**Risk reference:** [Part 04 — Risk Management](../04-risk-management/README.md)

**Primary framework:** [NIST Cybersecurity Framework 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20)

**Status:** In Progress

**Writing reference:** ASD-STE100 Issue 9

---

## 1. Purpose

This document defines a proposed compliance management process.

It explains how an organisation can identify, record, assess, and monitor compliance obligations.

It also explains how requirements can be mapped to controls and supporting evidence.

The Uber 2016 data breach provides the case-study context.

This is an independent portfolio project. It is not a legal compliance assessment of Uber.

## 2. Understanding Compliance Management

Compliance management helps an organisation identify and manage requirements that apply to its activities.

These requirements can come from different sources.

| Source type | Meaning | Example |
|---|---|---|
| Law or regulation | A legal requirement that applies to an organisation. | Applicable privacy or data protection law. |
| Regulatory order | A binding order issued to a named organisation. | [FTC Decision and Order for Uber (2018)](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |
| Contract | A requirement agreed with a customer or business partner. | A contractual security obligation. |
| Standard | A published set of requirements or practices. | [ISO/IEC 27001:2022](https://www.iso.org/standard/27001) |
| Framework | Guidance that helps an organisation manage risk. | [NIST CSF 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20) |
| Internal policy | A requirement approved by the organisation. | An information security policy. |

**Important distinction:** A framework or standard is not automatically a law.

The [NIST CSF FAQ](https://www.nist.gov/cyberframework/faqs) explains that most organisations use CSF on a voluntary basis.

An organisation may also make a standard or framework binding through a contract, policy, regulatory requirement, or formal adoption.

## 3. Scope and Boundaries

This project examines compliance topics related to:

- Identity and access management.
- Credential and secrets management.
- Cloud security.
- Protection of personal information.
- Security monitoring.
- Incident response and reporting.
- Privacy governance.
- Independent assessment and evidence management.

The project uses the Uber case study and selected official frameworks as design references.

The FTC issued a specific Decision and Order to Uber in October 2018. Its requirements apply to the respondent named in that order. They are not automatically legal obligations for every organisation. [FTC Decision and Order](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf)

This portfolio does not determine whether Uber met every requirement of that order.

It does not provide a legal opinion or a statutory compliance assessment.

## 4. Compliance References and Applicability

The following sources support the proposed compliance framework.

| Source | Type | Use in this project | Applicability |
|---|---|---|---|
| [FTC Decision and Order, 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) | Regulatory order | Study privacy programme, risk assessment, testing, reporting, and assessment requirements. | Specific to Uber and the order's respondent. |
| [NIST CSF 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20) | Cybersecurity framework | Organise cybersecurity outcomes and compliance-related activities. | Voluntary guidance unless adopted or required. |
| [NIST SP 800-53 Rev. 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) | Security and privacy control catalogue | Select and map proposed security controls. | Use depends on the organisation's requirements and adoption. |
| [ISO/IEC 27001:2022](https://www.iso.org/standard/27001) | International standard | Use as a reference for an Information Security Management System (ISMS). | Applies through adoption or other binding arrangements where relevant. |

NIST describes CSF 2.0 as guidance for managing cybersecurity risks. It provides outcomes but does not prescribe one method for achieving them. [NIST CSF 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20)

NIST SP 800-53 provides a flexible and customisable catalogue of security and privacy controls. Its controls address requirements that can come from business needs, laws, regulations, policies, standards, and guidelines. [NIST SP 800-53 Rev. 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)

ISO/IEC 27001:2022 defines requirements for establishing, implementing, maintaining, and continually improving an ISMS. [Official ISO standard page](https://www.iso.org/standard/27001)

## 5. Case-Specific Regulatory Requirements

The FTC's October 2018 Decision and Order established requirements for Uber.

The following table summarises selected provisions from that order.

These requirements are presented as case-study evidence. They are not general requirements for every organisation.

| Reference | Requirement in the FTC Order | Official evidence |
|---|---|---|
| FTC-II-A | Designate employee(s) responsible for coordinating the privacy programme. | [FTC Order — Section II](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |
| FTC-II-B | Identify foreseeable privacy risks and assess the safeguards used to manage them. | [FTC Order — Section II](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |
| FTC-II-B(3) | Include secure software design and testing, access key and secret key management, and secure cloud storage in the risk assessment. | [FTC Order — Section II](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |
| FTC-II-C | Design reasonable controls and test or monitor their effectiveness on a regular basis. | [FTC Order — Section II](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |
| FTC-II-D | Take reasonable steps to select service providers and require appropriate privacy protections by contract. | [FTC Order — Section II](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |
| FTC-III | Obtain initial and biennial independent privacy assessments under the terms of the order. | [FTC Order — Section III](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |
| FTC-IV | Submit covered incident reports to the FTC within the time limits stated in the order. | [FTC Order — Section IV](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) |

### Important note on the FTC reporting requirement

Section IV applies to a defined Covered Incident.

Under the order, Uber must report a covered incident within a reasonable time after discovery, and no later than 10 days after it first notifies a U.S. federal, state, or local government entity about that incident. [FTC Decision and Order — Section IV](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf)

This is a condition in Uber's specific order.

It must not be presented as a general 10-day notification deadline for every organisation.

## 6. Proposed Compliance Control Mapping

This section maps selected requirement areas to proposed control objectives.

The NIST CSF 2.0 includes GV.OC-03. This outcome states that legal, regulatory, and contractual cybersecurity requirements, including privacy obligations, are understood and managed. [NIST CSF 2.0 — GV.OC-03](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf)

| ID | Requirement area | Framework or source reference | Proposed control objective |
|---|---|---|---|
| CM-01 | Legal and regulatory obligations | [NIST CSF 2.0 — GV.OC-03](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf) | Identify applicable legal, regulatory, and contractual requirements. |
| CM-02 | Identity and access | [NIST CSF 2.0 — PR.AA](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf) | Restrict access to authorised users and services. |
| CM-03 | Secrets and cloud security | [FTC Order — Section II-B](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) | Protect access keys, secret keys, and cloud storage. |
| CM-04 | Personal information | [FTC Order — Section II](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) | Identify privacy risks and maintain suitable safeguards. |
| CM-05 | Control testing and monitoring | [FTC Order — Section II-C](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) | Test and monitor control effectiveness. |
| CM-06 | Service providers | [FTC Order — Section II-D](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) | Assess service providers and define security obligations in contracts. |
| CM-07 | Incident reporting | [NIST CSF 2.0 — RS.CO](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf) | Define internal and external incident communication procedures. |
| CM-08 | Independent assessment | [FTC Order — Section III](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) | Define independent assessment processes where required. |

These mappings are proposed design relationships.

They do not establish that an organisation is legally compliant.

A mapping does not mean that two frameworks have identical requirements.

## 7. Compliance Assessment Methodology

The proposed assessment process has seven steps.

### Step 1 — Identify the organisation

Record the following information:

- Legal entity.
- Country and operating locations.
- Products and services.
- Customer types.
- Personal information handled.
- Suppliers and service providers.

These facts help determine which requirements may apply.

### Step 2 — Identify requirements

Find requirements from:

- Laws and regulations.
- Regulatory orders.
- Customer and supplier contracts.
- Adopted standards.
- Internal policies.

Use official sources to verify each requirement.

### Step 3 — Assess applicability

Apply one of the following decisions:

| Decision | Meaning |
|---|---|
| Applicable | The requirement applies to the defined organisation or activity. |
| Conditionally Applicable | The requirement applies when a stated condition is met. |
| Not Applicable | The requirement does not apply, based on a recorded reason. |
| Under Review | More information or legal review is needed. |

Do not mark a requirement as Not Applicable without a reason.

### Step 4 — Map the requirement

Link the requirement to one or more control objectives.

Record the control ID, control description, and owner.

### Step 5 — Identify evidence

Decide what evidence can demonstrate that the control operates.

### Step 6 — Assess compliance

Compare the requirement with the control and available evidence.

### Step 7 — Record gaps and actions

Record the gap, assign an owner, define a corrective action, and set a review date.

## 8. Compliance Status Method

The project uses five proposed assessment statuses.

| Status | Meaning |
|---|---|
| Compliant | Available evidence supports that the requirement is met. |
| Partially Compliant | Some parts are met, but gaps remain. |
| Non-Compliant | Evidence shows that the requirement is not met. |
| Not Assessed | No assessment has been completed. |
| Not Applicable | The requirement does not apply and the reason is recorded. |

The status must be based on evidence.

A planned control must not receive a Compliant status.

**Portfolio status:** Proposed controls have not been tested in a real organisation. Actual compliance results are Not Assessed.

## 9. Sample Compliance Obligations Register

The following table demonstrates how requirements can be recorded.

It is a portfolio example. It is not an assessment of Uber's current compliance.

| Obligation ID | Source | Requirement summary | Applicability to this portfolio | Status |
|---|---|---|---|---|
| OBL-01 | [FTC Decision and Order](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf) | Uber-specific privacy programme and control requirements. | Reference only; the order names Uber as respondent. | Not Assessed |
| OBL-02 | [NIST CSF 2.0 — GV.OC-03](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf) | Understand and manage legal, regulatory, and contractual cybersecurity requirements. | Voluntary framework reference. | Not Assessed |
| OBL-03 | [NIST SP 800-53 Rev. 5](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final) | Select suitable security and privacy controls. | Control catalogue reference. | Not Assessed |
| OBL-04 | [ISO/IEC 27001:2022](https://www.iso.org/standard/27001) | Establish and maintain an ISMS when the standard is adopted. | Optional standard reference for this portfolio design. | Not Assessed |

This example does not identify every law that could apply to Uber or to another organisation.

A real compliance assessment must consider its operating jurisdictions, legal entities, services, customers, contracts, and data types.

## 10. Compliance Evidence and Gap Management

### 10.1 Evidence Register

Evidence supports compliance assessment.

Examples include:

| Evidence type | Example | Related area |
|---|---|---|
| Approved policy | Access control policy | Identity and access |
| Configuration record | MFA configuration | Authentication |
| Access review | Approved account review | Access management |
| Technical record | Secrets scanning report | Secrets management |
| Test report | Control effectiveness test | Control monitoring |
| Incident record | Incident response report | Incident management |
| Contract | Supplier security clauses | Third-party compliance |
| Assessment report | Independent privacy assessment | Assurance |

These are examples of proposed evidence. They are not evidence collected from Uber.

### 10.2 Gap Assessment

When evidence does not show that a requirement is met, the assessor records a gap.

A gap record should include:

- Gap ID.
- Requirement ID.
- Control ID.
- Gap description.
- Risk rating.
- Corrective action.
- Responsible owner.
- Target date.
- Closure evidence.

### 10.3 Remediation Process

The proposed process is:

1. Identify the compliance gap.
2. Record its supporting evidence.
3. Assess the related risk.
4. Assign an action owner.
5. Define the corrective action.
6. Set a target date.
7. Review the completed work.
8. Record closure evidence.

## 11. Limitations

This is an independent compliance framework design.

It uses public incident records and official standards.

It does not represent:

- A legal review of Uber.
- An assessment of Uber's compliance with every applicable law.
- A certification audit.
- A verified control assessment.
- A completed compliance programme at a real organisation.

The FTC Decision and Order is specific to Uber. It is not a universal privacy regulation.

NIST CSF and NIST SP 800-53 provide cybersecurity guidance and control references. They are not automatically binding legal requirements for every private organisation.

The applicability of privacy and breach notification laws must be assessed for each jurisdiction and business activity.

Legal conclusions require qualified legal review.

## 12. Official References

- [FTC — Uber Revised Decision and Order, October 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_decision_and_order.pdf)
- [FTC — Final Approval of Settlement with Uber, October 2018](https://www.ftc.gov/news-events/news/press-releases/2018/10/federal-trade-commission-gives-final-approval-settlement-uber)
- [FTC — Uber Revised Complaint, October 2018](https://www.ftc.gov/system/files/documents/cases/152_3054_c-4662_uber_technologies_revised_complaint.pdf)
- [NIST — Cybersecurity Framework 2.0](https://www.nist.gov/publications/nist-cybersecurity-framework-csf-20)
- [NIST — Cybersecurity Framework FAQ](https://www.nist.gov/cyberframework/faqs)
- [NIST — CSF 2.0 Full Publication (PDF)](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.29.pdf)
- [NIST — SP 800-53 Rev. 5, Updated Publication](https://csrc.nist.gov/pubs/sp/800/53/r5/upd1/final)
- [ISO — ISO/IEC 27001:2022](https://www.iso.org/standard/27001)
- [ASD-STE100 — Official Standard](https://www.asd-ste100.org/)

---

**Writing note:** This document uses ASD-STE100 Issue 9 writing principles. Full compliance has not yet been verified against the complete specification.

**Next step:** Develop the GRC platform implementation plan and demonstrate the proposed compliance records in the selected tools.