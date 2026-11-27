# Avenloft Systems Group — AI Data Flow and Assessment Scope

**Project ID:** GRC-AI-002  
**Organisation:** Avenloft Systems Group (Fictional)  
**Business Function:** Customer Success  
**Use Case:** AI-Assisted Customer Support Summarisation  
**Document:** Data Flow and Scope Analysis  
**Status:** Initial Analysis — Validation Pending

## 1. Purpose

This document describes the proposed information flow and assessment boundaries for Avenloft's AI-assisted customer support summarisation use case.

Customer Success wants to pilot an AI-enabled SaaS tool that summarises customer support calls and tickets.

The purpose of this analysis is to identify:

- Information entering the AI service.
- The source of the information.
- The intended processing activity.
- The expected AI-generated outputs.
- External service dependencies.
- Human review responsibilities.
- Data storage, retention, and deletion requirements.
- Approved and prohibited use-case boundaries.

The exact architecture and vendor arrangements must be confirmed from the complete GRC-AI-002 case packet.

**Primary assignment source:** [Avenloft AI Use-Case Review Case Packet](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf).

## 2. Proposed Business Process

The proposed business process is customer-support interaction summarisation.

The assignment brief establishes the following:

| Attribute | Description |
|---|---|
| Business Function | Customer Success |
| Information Sources | Customer support calls and tickets |
| Proposed Technology | AI-enabled SaaS tool |
| Processing Activity | Summarisation |
| Expected Output | Summaries of support calls and tickets |
| Business Purpose | Support Customer Success activities |
| Deployment Status | Proposed pilot |
| Governance Status | Approval pending |

The brief does not establish the exact technical workflow, data fields, or storage arrangements.

## 3. Initial High-Level Data Flow

The following diagram represents only the high-level process supported by the assignment brief.

```text
Customer Support Interaction
          |
          v
  Support Calls and Tickets
          |
          v
  Information Selected
  for AI Processing
          |
          v
  AI-Enabled SaaS Service
          |
          v
  AI Summarisation Process
          |
          v
  Generated Support Summary
          |
          v
  Human Review by Customer
  Success Personnel
          |
          v
  Use in Support Workflow
```

**Important:** The human-review stage is a process area that must be investigated. The supplied assignment brief does not establish the actual reviewer, review requirement, or point at which the summary enters the support record.

The diagram does not claim that a specific integration, API, storage location, or review mechanism has already been implemented.

## 4. Data Sources

The assignment brief identifies two initial information sources.

### 4.1 Customer Support Calls

Customer support calls may be used as source material for generated summaries.

The following details require confirmation:

- Whether the service receives audio recordings or transcripts.
- Whether call transcription occurs before summarisation.
- Whether both customer and employee voices are processed.
- Whether recordings contain personal or confidential information.
- Whether metadata is included.
- Whether the entire call or only selected sections are submitted.

The case packet must be reviewed before these details can be recorded as facts.

### 4.2 Customer Support Tickets

Customer support tickets are also identified as an input source.

The following details require confirmation:

- Ticket descriptions.
- Customer messages and agent responses.
- Customer identifiers.
- Contact information.
- Product or account identifiers.
- Technical logs and troubleshooting details.
- Attachments.
- Any sensitive or restricted information.

These are data categories to investigate, not confirmed contents of every ticket.

## 5. Data Classification and Minimisation

Before information is submitted to the AI service, Avenloft should understand what information is necessary for the summarisation purpose.

| Data Category | Identified in Brief | Data Minimisation Question |
|---|---|---|
| Customer support calls | Yes | Is complete audio necessary, or would a transcript be sufficient? |
| Customer support tickets | Yes | Which ticket fields are necessary for a useful summary? |
| Customer identifiers | Not specified | Can direct identifiers be removed or masked? |
| Contact information | Not specified | Is contact information required for summarisation? |
| Customer attachments | Not specified | Are attachments processed by the proposed tool? |
| Technical troubleshooting information | Not specified | Which technical details must be retained in a summary? |
| Call metadata | Not specified | Is metadata necessary for the business purpose? |
| Personal or sensitive information | Not specified | Can unnecessary sensitive information be excluded? |

**Assessment requirement:** The business owner must explain why each data category is needed.

Information that is not necessary for summarisation should be considered for exclusion, masking, or minimisation.

## 6. Processing Activities

The confirmed high-level processing activity is AI summarisation of customer support calls and tickets.

The following technical processing details require validation:

| Processing Stage | Question to Resolve |
|---|---|
| Collection | How are calls and tickets selected? |
| Preparation | Are recordings transcribed or ticket fields transformed before submission? |
| Transmission | How does information reach the SaaS provider? |
| AI Processing | Which AI model and service components process the information? |
| Generation | What summary structure and content are generated? |
| Review | Who checks the output against the original interaction? |
| Storage | Where are inputs and generated summaries stored? |
| Retention | How long are inputs, outputs, and related logs retained? |
| Deletion | How are records deleted after the approved retention period? |

No specific implementation method is assumed until supported by case evidence.

## 7. Expected AI Outputs

The assignment brief establishes that the AI service generates summaries of customer support calls and tickets.

The following output characteristics require confirmation:

- Summary format.
- Summary length.
- Whether action items are generated.
- Whether customer issues and troubleshooting steps are extracted.
- Whether the output includes confidence indicators or source references.
- Whether users can correct generated statements.
- Whether generated summaries are written to the official support record.
- Whether original source information remains available for comparison.

An AI-generated statement must not automatically be treated as an accurate record of the original customer interaction.

## 8. Human Review and Accountability

Human oversight is a central requirement of this assessment.

The review must determine:

1. Who is responsible for reviewing generated summaries?
2. Is review required before a summary is used?
3. Can a reviewer compare the summary with the original call or ticket?
4. Can an employee correct unsupported or inaccurate information?
5. Are corrections recorded?
6. Can a summary be rejected?
7. Who remains accountable for the final support record?

### Example of an AI output concern

The assignment brief describes a scenario in which an AI-generated summary states that a customer restarted a system even though the original transcript does not contain that information.

This illustrates the risk of confabulation and the need for source verification.

The review should establish whether the pilot provides meaningful human oversight rather than relying only on employees to trust generated content.

## 9. External Service and Third-Party Dependencies

The proposed technology is an AI-enabled SaaS service.

Its external dependencies must be understood before approval.

| Dependency | Information Required |
|---|---|
| AI SaaS Provider | Legal name, service responsibility, and contractual relationship |
| AI Model Provider | Model name, provider, and role in processing |
| Subprocessors | Names, services, and data access |
| Hosting Provider | Processing and storage infrastructure |
| Processing Locations | Countries or regions where information is processed |
| Vendor Personnel | Circumstances under which personnel can access information |
| External Integrations | Systems connected to the service |
| Contractual Dependencies | Security, privacy, retention, deletion, and incident terms |

The actual vendor and subprocessor details must be extracted from the case packet.

The assignment brief indicates that vendor responses and subprocessor information are supplied in the training case, but it does not provide the underlying details.

## 10. Data Storage, Retention, and Deletion

Retention and deletion are important parts of the proposed information lifecycle.

The assessment must distinguish between:

- Original call recordings.
- Call transcripts.
- Customer support tickets.
- Submitted input information.
- AI-generated summaries.
- Application logs.
- Security logs.
- Backup copies.
- Information held by subprocessors.

For each category, the assessment must establish:

| Requirement | Question |
|---|---|
| Storage | Where is the information stored? |
| Encryption | What protection is applied at rest and in transit? |
| Access | Which people and service components can access it? |
| Retention | How long is the information retained? |
| Deletion | How is information deleted? |
| Deletion Verification | Can Avenloft obtain evidence of deletion? |
| Subprocessor Handling | Do the same requirements apply to subprocessors? |
| Model Training | Is customer information used to train or improve AI models? |

All actual retention periods and vendor commitments must be taken from the case evidence.

## 11. Proposed Pilot Scope

The assignment currently identifies the following proposed scope:

| Scope Attribute | Initial Position |
|---|---|
| Business Function | Customer Success |
| Intended Activity | Summarisation of customer support calls and tickets |
| Technology | AI-enabled SaaS service |
| Deployment | Proposed pilot |
| Business Approval | Pending |
| Governance Review | Required |

The exact pilot population, duration, data categories, and technical access boundaries remain to be established.

### Scope items requiring explicit decisions

Before approval, Avenloft should document whether the pilot will permit:

- Processing live customer calls.
- Processing recorded calls.
- Processing call transcripts.
- Processing support-ticket attachments.
- Processing tickets containing sensitive information.
- Automatic insertion of summaries into support records.
- Use of summaries without human review.
- Use outside the Customer Success function.
- Use of customer information for model training.

These decisions must be established from the case evidence and governance assessment.

## 12. Out-of-Scope Activities

The supplied assignment brief does not provide a complete list of formally prohibited activities or approved pilot exclusions.

The following are therefore **scope decisions requiring explicit confirmation**, not established vendor or company restrictions:

- Using AI-generated summaries as autonomous decisions about customer accounts.
- Sending customer information to unapproved AI services.
- Expanding the pilot beyond the approved Customer Success group.
- Processing data categories not approved by the relevant business and governance owners.
- Allowing generated outputs to become authoritative records without the required review.
- Using customer information for model training without explicit approval and an appropriate contractual basis.

The final governance memo must distinguish formal prohibitions from recommended restrictions.

## 13. Initial Data-Flow Risk Considerations

| Data-Flow Stage | Potential Concern | Required Evidence |
|---|---|---|
| Source selection | Unnecessary customer information may be selected. | Input-field inventory and data-minimisation review. |
| Transmission | Information may be exposed during transfer. | Technical architecture and encryption evidence. |
| Vendor processing | Information may be accessed or processed beyond the approved purpose. | Vendor responses and contractual terms. |
| Subprocessor handling | Additional organisations may receive or process information. | Subprocessor list and processing descriptions. |
| AI generation | Incorrect statements may be produced. | Pre-pilot testing and quality evidence. |
| Human review | Unsupported summaries may be used without adequate verification. | Review workflow and accountability evidence. |
| Storage | Inputs and outputs may be retained longer than intended. | Retention and deletion terms. |
| Reassessment | Changes to models, services, or data flows may alter risks. | Change-notification and monitoring arrangements. |

These are assessment concerns, not confirmed findings.

## 14. Information Required for the Final Data-Flow Diagram

The following evidence is needed to convert the high-level diagram into a verified data-flow diagram:

1. Source systems for support calls and tickets.
2. Exact information fields sent to the service.
3. Whether calls are submitted as audio or transcripts.
4. Integration and transmission method.
5. AI SaaS provider and model provider.
6. Subprocessor names and processing functions.
7. Processing and storage locations.
8. Retention periods for inputs and outputs.
9. Human-review stage and responsible personnel.
10. Final destination of generated summaries.
11. Deletion and verification process.

Until these details are confirmed, the high-level diagram must remain labelled as conceptual.

## 15. Document Status

| Activity | Status |
|---|---|
| Identify proposed business purpose | Documented from brief |
| Identify input categories | Partially documented |
| Identify expected output | Documented from brief |
| Establish complete data flow | Needs validation |
| Identify service provider | Needs validation |
| Identify model provider and subprocessors | Needs validation |
| Establish processing locations | Needs validation |
| Establish retention and deletion | Needs validation |
| Confirm human oversight | Needs validation |
| Define formal pilot boundaries | Needs validation |

**Document status:** Initial data-flow and scope analysis.

This is an independent assessment of a fictional training scenario. It does not represent an implemented AI service or a real client engagement.