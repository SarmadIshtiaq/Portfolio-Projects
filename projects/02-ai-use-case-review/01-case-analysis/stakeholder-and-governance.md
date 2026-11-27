# Avenloft Systems Group — Stakeholder and AI Governance Analysis

**Project ID:** GRC-AI-002  
**Organisation:** Avenloft Systems Group (Fictional)  
**Business Function:** Customer Success  
**Use Case:** AI-Assisted Customer Support Summarisation  
**Document:** Stakeholder and Governance Analysis  
**Status:** Proposed Governance Model — Validation Pending

## 1. Purpose

This document identifies the stakeholders and governance responsibilities relevant to the proposed AI-enabled SaaS tool for summarising customer support calls and tickets.

The purpose is to establish:

- Who requests and owns the business use case.
- Who is responsible for the customer-support process.
- Who owns the information being processed.
- Who reviews AI-generated summaries.
- Who assesses security, privacy, and third-party risks.
- Who has authority to approve or reject the pilot.
- Who monitors the service after approval.
- Who is responsible for reassessment when material changes occur.

The assignment brief establishes Customer Success as the requesting business function. The exact named stakeholders and approval authorities must be confirmed from the complete GRC-AI-002 case packet.

## 2. Stakeholder Identification

The following roles are relevant to the assessment.

| Stakeholder Role | Relationship to the Use Case | Responsibility to Confirm |
|---|---|---|
| Customer Success Business Owner | Requests the AI pilot and defines the business purpose. | Business justification, pilot scope, expected benefits, and business accountability. |
| Customer Success Manager | Oversees the support workflow and participating employees. | User selection, operating procedures, and human review. |
| Customer Support Employees | Use the service or review generated summaries. | Follow approved procedures, verify outputs, report errors, and protect customer information. |
| Data Owner | Accountable for the customer information used in the process. | Approve data categories, permitted processing, minimisation, and handling requirements. |
| AI Use-Case Owner | Coordinates the AI use case throughout its lifecycle. | Inventory, review, monitoring, and change management. |
| GRC Analyst | Facilitates governance and risk assessment. | Evidence collection, risk documentation, control assessment, and reporting. |
| Information Security | Reviews security risks and technical safeguards. | Identity, access, encryption, security monitoring, and incident response. |
| Legal and Privacy | Reviews data processing and privacy concerns. | Applicable obligations, contract terms, privacy review, and data-processing conditions. |
| Procurement | Coordinates the vendor relationship. | Vendor onboarding, due diligence, contractual coordination, and renewal requirements. |
| AI SaaS Provider | Supplies the proposed service. | Service operation, technical information, contractual commitments, and incident notification. |
| Model Provider / Subprocessors | May support AI processing or service delivery. | Processing activities, security responsibilities, and data-handling commitments. |
| Executive Approver | Makes or authorises the final governance decision. | Approval, conditional approval, deferral, rejection, or risk acceptance within delegated authority. |

These are roles required for the proposed governance analysis. They are not a claim that every role has already been formally assigned.

## 3. Proposed Accountability Model

The following model is proposed for this portfolio assessment.

| Governance Activity | Accountable Role | Supporting Roles |
|---|---|---|
| Define business purpose | Customer Success Business Owner | Customer Success Management |
| Define intended use and scope | AI Use-Case Owner | Customer Success, GRC |
| Approve input data | Data Owner | Privacy, Customer Success |
| Maintain AI use-case inventory | AI Governance Owner | GRC, Business Owner |
| Assess AI risks | Relevant Risk Owner | GRC, Security, Privacy |
| Review vendor evidence | Procurement / Vendor Relationship Owner | Security, Privacy, GRC |
| Validate AI performance | Business Owner | Customer Success Users, AI Provider |
| Define human review | Customer Success Business Owner | Customer Success Management |
| Review security safeguards | Information Security | Vendor, IT |
| Review privacy and contract terms | Legal and Privacy | Procurement, Vendor |
| Make governance decision | Authorised Executive Approver | Business Owner, GRC, Security, Privacy |
| Monitor pilot operation | AI Use-Case Owner | Customer Success, Security, GRC |
| Reassess material changes | AI Governance Owner | Business Owner, Security, Privacy, GRC |

**Governance principle:** The person facilitating a risk assessment is not automatically the owner of the business risk. The accountable business or technology owner must be identified.

## 4. Proposed Responsibility Assignment (RACI)

RACI definitions:

- **R — Responsible:** Performs the activity.
- **A — Accountable:** Owns the outcome and decision.
- **C — Consulted:** Provides input before the decision.
- **I — Informed:** Receives relevant updates.

The following matrix is a proposed allocation for review, not an approved Avenloft RACI.

| Activity | Business Owner | AI Use-Case Owner | GRC | Security | Privacy / Legal | Customer Success Users | Executive Approver |
|---|---|---|---|---|---|---|---|
| Define business purpose | A | R | C | I | I | C | I |
| Document use case | C | A/R | C | C | C | C | I |
| Approve data categories | A | R | C | C | C | I | I |
| Complete AI risk assessment | C | C | A/R | C | C | I | I |
| Review security controls | I | C | C | A/R | C | I | I |
| Review privacy and terms | C | C | C | C | A/R | I | I |
| Review AI output quality | A | R | C | C | I | R | I |
| Define pilot conditions | A | R | C | C | C | C | I |
| Approve pilot | C | C | C | C | C | I | A |
| Monitor pilot | A | R | C | R | C | R | I |
| Reassess material changes | A | R | R | C | C | C | I |

The exact names and approval authority must be confirmed before this model is adopted.

## 5. Human Oversight Responsibilities

Human oversight is important because an AI-generated summary may contain inaccurate or unsupported statements.

The proposed responsibility model is:

### Customer Success Users

- Review generated summaries according to the approved procedure.
- Compare important statements with the original call or ticket.
- Correct inaccurate or incomplete information.
- Avoid treating unsupported AI-generated statements as verified facts.
- Escalate summaries that cannot be validated.

### Customer Success Management

- Define review requirements.
- Ensure users receive appropriate instructions.
- Monitor review quality and recurring errors.
- Identify whether summaries are suitable for the intended business process.

### Business Owner

- Remain accountable for the business use of the AI service.
- Decide how generated outputs may be used.
- Approve the operating procedure and pilot boundaries.
- Escalate material concerns.

Human review must be meaningful. A process that only asks employees to approve AI outputs without source verification may not provide adequate oversight.

The exact review workflow must be confirmed from the case packet.

## 6. AI Governance Responsibilities

The proposed governance model should cover the four functions of the [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework).

| AI RMF Function | Governance Application | Relevant Responsibility |
|---|---|---|
| Govern | Accountability, inventory, policies, oversight, and risk ownership. | AI Governance Owner, Business Owner, GRC |
| Map | Business purpose, users, data, context, dependencies, and potential impacts. | AI Use-Case Owner, Business Owner, Privacy |
| Measure | Performance, limitations, risk evidence, testing, and validation. | Business Owner, Security, Technical Stakeholders |
| Manage | Risk treatment, approval conditions, monitoring, and reassessment. | Risk Owners, AI Governance Owner, Executive Approver |

Governance applies across the lifecycle. It is not limited to completing an approval form.

## 7. Approval Authority

The final pilot decision should be made by an authorised person or committee within Avenloft's delegated governance authority.

The assessment will consider four possible outcomes:

| Decision | Required Governance Position |
|---|---|
| Approve | Evidence supports the proposed use within the defined scope and existing safeguards. |
| Conditionally Approve | The pilot may proceed only after specified conditions are completed and verified. |
| Defer | Material evidence, safeguards, or approvals are not yet available. |
| Reject | The use case cannot be justified or the remaining risks cannot be addressed acceptably. |

A GRC analyst may recommend an outcome but should not claim approval authority unless formally delegated.

The named approving authority for GRC-AI-002 requires confirmation.

## 8. Proposed Governance Gates

The following gates are proposed to prevent the pilot from starting before key governance questions are addressed.

| Gate | Required Review | Expected Evidence |
|---|---|---|
| Gate 1 — Business Definition | Purpose, users, intended outputs, and scope. | Approved use-case description. |
| Gate 2 — Data Review | Input information, data minimisation, and permitted use. | Data inventory and owner approval. |
| Gate 3 — Vendor Review | Service provider, subprocessors, contractual terms, and data handling. | Due diligence evidence and reviewed terms. |
| Gate 4 — AI Risk Review | Accuracy, confabulation, privacy, security, and human oversight. | AI risk assessment and test evidence. |
| Gate 5 — Pilot Approval | Residual risks, required safeguards, and decision authority. | Signed or documented governance decision. |
| Gate 6 — Pilot Monitoring | Performance, incidents, changes, and compliance with conditions. | Monitoring records and review reports. |

These gates are recommendations for this portfolio exercise. They must not be described as an existing Avenloft approval process without supporting evidence.

## 9. Monitoring Responsibilities

The proposed operating model should assign responsibility for monitoring:

| Monitoring Area | Proposed Owner | Evidence to Maintain |
|---|---|---|
| Summary accuracy | Customer Success Business Owner | Quality reviews and correction records |
| Unsupported output | Customer Success Management | Error and escalation records |
| Human review | Customer Success Management | Review completion and exception records |
| Data handling | Data Owner | Approved data scope and handling records |
| Security events | Information Security | Security alerts and incident records |
| Vendor changes | Vendor Relationship Owner | Vendor notices and subprocessor updates |
| Retention and deletion | Data Owner / Vendor Relationship Owner | Retention configuration and deletion evidence |
| AI use-case status | AI Governance Owner | Inventory and periodic review records |
| Risk treatment | Assigned Risk Owners | Remediation and risk review records |

The final monitoring frequency must be determined using the pilot design, vendor terms, and risk assessment.

## 10. Reassessment and Escalation Triggers

The following proposed events should trigger review or escalation:

- Material change in the approved business purpose.
- Addition of new data categories.
- Processing of attachments or more sensitive information.
- Change of AI model or model provider.
- Addition or replacement of subprocessors.
- Change in data storage or processing location.
- Change in retention or model-training terms.
- Repeated unsupported or materially inaccurate summaries.
- Failure of required human review.
- Security or privacy incident.
- Breach of an approval condition.
- Expansion beyond the approved pilot population or use case.

A material issue may require suspension of the affected functionality or the pilot, subject to the approved response procedure.

## 11. Governance Information Requiring Validation

| Information | Required Confirmation |
|---|---|
| Named business owner | Confirm the accountable Customer Success executive or manager. |
| AI Use-Case Owner | Confirm who maintains the use case throughout its lifecycle. |
| Data Owner | Confirm who approves customer-support data use. |
| Review Owner | Confirm who is responsible for checking generated summaries. |
| Security Authority | Confirm the individual or team responsible for technical approval. |
| Privacy Authority | Confirm the legal and privacy review owner. |
| Vendor Relationship Owner | Confirm who manages the SaaS provider relationship. |
| Executive Approver | Confirm delegated authority for the pilot decision. |
| Risk Owners | Confirm ownership of each material AI risk. |
| Monitoring Owner | Confirm who maintains pilot performance and control evidence. |

No named owner is assigned in this document without case evidence or formal confirmation.

## 12. References

- [NIST AI Risk Management Framework 1.0](https://www.nist.gov/itl/ai-risk-management-framework).
- [NIST AI 600-1 — Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence).
- [Avenloft AI Use-Case Review Case Packet](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf).

## 13. Document Status

| Activity | Status |
|---|---|
| Stakeholder roles identified | Proposed |
| Governance responsibilities mapped | Proposed |
| RACI model prepared | Proposed |
| Approval authority confirmed | Needs validation |
| Named role owners confirmed | Needs case-packet review |
| Human-review workflow confirmed | Needs case-packet review |
| Monitoring responsibilities confirmed | Proposed |
| Governance model approved | Not started |

**Document status:** Proposed stakeholder and governance analysis.

This document is part of an independent training simulation. Avenloft Systems Group and all case-related employees, vendors, systems, and events are fictional.