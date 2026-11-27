# Avenloft Systems Group — AI Use-Case Evidence Register

**Project ID:** GRC-AI-002  
**Organisation:** Avenloft Systems Group (Fictional)  
**Business Function:** Customer Success  
**Use Case:** AI-Assisted Customer Support Summarisation  
**Document:** Evidence Register  
**Status:** Initial evidence inventory; case-packet validation pending

## 1. Purpose

This document records the evidence required to evaluate the proposed AI-enabled SaaS tool for summarising customer support calls and tickets.

The evidence register will help the analyst:

- Identify information supplied in the assignment brief.
- Record evidence from the complete case packet.
- Distinguish vendor statements from independently supported evidence.
- Identify missing or incomplete information.
- Record evidence limitations.
- Connect evidence to AI risks and governance decisions.
- Maintain traceability between the evidence and the final assessment.

The presence of a vendor statement does not automatically establish that a control operates effectively.

## 2. Evidence Sources

The following sources are expected to support the assessment.

| Source ID | Source | Expected Information |
|---|---|---|
| SRC-01 | GRC-AI-002 Case Packet | Business context, proposed use case, data flow, stakeholder information, and assignment requirements |
| SRC-02 | Vendor Responses | Vendor statements about AI functionality, security, privacy, and service operation |
| SRC-03 | Data Flow Information | Data sources, transmission, processing, storage, and outputs |
| SRC-04 | Retention Information | Retention periods for inputs, outputs, logs, and backups |
| SRC-05 | Subprocessor Information | External AI providers, hosting providers, and other subprocessors |
| SRC-06 | Pre-Pilot Test Results | AI summarisation accuracy, unsupported outputs, and other test findings |
| SRC-07 | Stakeholder Notes | Business requirements, responsibilities, human oversight, and concerns |
| SRC-08 | Contractual Information | Vendor commitments, data processing terms, security requirements, and deletion obligations |
| SRC-09 | NIST AI RMF | Framework guidance for AI risk management |
| SRC-10 | NIST AI 600-1 | Generative AI risk guidance |

The actual documents, evidence identifiers, and page references must be recorded after reviewing the complete case packet.

## 3. Evidence Available from the Assignment Brief

The following information is directly established by the project brief shared for this assignment.

| Evidence ID | Evidence Description | Source | Evidence Status |
|---|---|---|---|
| AI-EV-01 | Customer Success has requested approval to pilot an AI-enabled SaaS tool. | Project 2 assignment brief | Confirmed from brief |
| AI-EV-02 | The proposed purpose is summarising customer support calls and tickets. | Project 2 assignment brief | Confirmed from brief |
| AI-EV-03 | The proposed system uses generative AI. | Project 2 assignment brief | Confirmed from brief |
| AI-EV-04 | The case packet contains vendor responses and subprocessor information. | Project 2 assignment brief | Existence stated; contents not reviewed |
| AI-EV-05 | The case packet contains data-retention information. | Project 2 assignment brief | Existence stated; actual terms not reviewed |
| AI-EV-06 | The case packet contains pre-pilot test results. | Project 2 assignment brief | Existence stated; actual results not reviewed |
| AI-EV-07 | The proposed use case requires a governance decision before the pilot. | Project 2 assignment brief | Confirmed from brief |
| AI-EV-08 | The decision options are Approve, Conditionally Approve, Defer, and Reject. | Project 2 assignment brief | Confirmed from brief |

**Primary assignment reference:** [Avenloft AI Use-Case Review Case Packet](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf).

The actual case packet must be reviewed before AI-EV-04, AI-EV-05, and AI-EV-06 can be treated as evidence of specific vendor practices or test results.

## 4. Evidence Collection Register

The following register identifies the evidence required for the assessment.

| Evidence ID | Evidence Required | Why It Matters | Current Status |
|---|---|---|---|
| AI-EV-09 | Detailed business justification | Establishes the problem the business wants to solve. | Needs case-packet review |
| AI-EV-10 | Named business owner | Establishes accountability for the use case. | Needs case-packet review |
| AI-EV-11 | List of intended users | Establishes who may access the service and its outputs. | Needs case-packet review |
| AI-EV-12 | Detailed data-flow diagram | Identifies data sources, processing, transmission, storage, and outputs. | Needs case-packet review |
| AI-EV-13 | Input-data profile | Establishes which customer information enters the service. | Needs case-packet review |
| AI-EV-14 | AI system and model details | Identifies the AI capability and technical dependencies. | Needs case-packet review |
| AI-EV-15 | Vendor security responses | Provides the vendor's statements about its security practices. | Needs case-packet review |
| AI-EV-16 | Subprocessor list | Identifies other organisations involved in processing information. | Needs case-packet review |
| AI-EV-17 | Data-retention terms | Establishes how long information is retained. | Needs case-packet review |
| AI-EV-18 | Data deletion terms | Establishes how inputs and outputs are deleted. | Needs case-packet review |
| AI-EV-19 | Model-training and data-use terms | Establishes whether submitted information may be used for model training or improvement. | Needs case-packet review |
| AI-EV-20 | Pre-pilot performance results | Provides evidence about summarisation quality and limitations. | Needs case-packet review |
| AI-EV-21 | Unsupported-output test results | Helps evaluate confabulation and information integrity. | Needs case-packet review |
| AI-EV-22 | Human-review workflow | Establishes whether employees verify generated summaries. | Needs case-packet review |
| AI-EV-23 | Vendor contract and data-processing terms | Helps establish formal service-provider obligations. | Needs case-packet review |
| AI-EV-24 | Security architecture information | Supports assessment of access, transmission, and storage controls. | Needs case-packet review |
| AI-EV-25 | Incident-notification terms | Establishes how security or privacy incidents are reported. | Needs case-packet review |
| AI-EV-26 | Monitoring and change information | Supports ongoing assessment of model, vendor, and service changes. | Needs case-packet review |

## 5. Vendor Claim Assessment

Vendor statements must be recorded separately from evidence that independently supports those statements.

Use the following classifications:

| Classification | Meaning |
|---|---|
| Vendor-Stated | The vendor has made the statement, but supporting evidence has not yet been reviewed. |
| Document-Supported | A supplied document supports the statement. |
| Independently Validated | Evidence has been checked through an appropriate independent method. |
| Partially Supported | Some parts of the statement are supported, but important limitations remain. |
| Not Supported | Available evidence does not support the statement. |
| Not Provided | The requested evidence was not supplied. |
| Needs Clarification | The statement is incomplete, ambiguous, or requires further explanation. |

A vendor assurance statement must not be treated as independent validation merely because it appears in a questionnaire or presentation.

## 6. Pre-Pilot Testing Evidence

The case packet is expected to include pre-pilot test results.

These results must be reviewed before making a decision about the reliability of generated summaries.

### Required test information

| Assessment Area | Evidence to Review |
|---|---|
| Test population | Number and type of test calls and tickets |
| Test method | How test inputs and outputs were evaluated |
| Summary accuracy | Whether summaries preserve the meaning of source interactions |
| Unsupported statements | Whether generated outputs contain facts not supported by the source |
| Omitted information | Whether important customer statements or troubleshooting steps are missing |
| Human correction | Whether reviewers identify and correct inaccurate outputs |
| Test limitations | What the test did not cover |
| Acceptance criteria | Whether formal approval thresholds exist |

### Example of an unsupported output

The project brief describes an example in which an AI-generated summary states that a customer restarted a system even though the source transcript does not contain that information.

This illustrates a potential confabulation risk.

It is an example from the assignment brief, not evidence that the proposed vendor actually produced that result during testing.

## 7. Data Privacy and Retention Evidence

The following information must be collected and reviewed.

| Assessment Area | Evidence Required |
|---|---|
| Data categories | Exact customer information submitted |
| Data minimisation | Whether every submitted field is necessary |
| Data transmission | How information is transferred to the service |
| Storage location | Where inputs and outputs are stored |
| Processing locations | Countries or regions where data is processed |
| Access | Vendor and subprocessor access arrangements |
| Retention | Retention periods for each data category |
| Deletion | Deletion process and verification |
| Backup copies | Treatment of data in backups |
| Model training | Whether submitted data is used to train or improve models |
| Contractual terms | Data-use restrictions and processing obligations |

Actual values must be taken from the supplied case evidence.

## 8. Human Oversight Evidence

The assessment must identify whether human review is meaningful and appropriate for the intended use.

| Review Requirement | Evidence Needed |
|---|---|
| Reviewer identity | Which employee or role reviews outputs? |
| Review timing | Before or after a summary becomes part of a support record? |
| Source access | Can the reviewer compare the output with its source? |
| Correction | Can inaccurate or incomplete summaries be corrected? |
| Accountability | Who remains responsible for the final support record? |
| Audit trail | Are corrections and review decisions recorded? |
| Escalation | What happens when an output cannot be verified? |

A statement that employees are expected to review summaries is not enough by itself. The actual review process must be documented.

## 9. Evidence Limitation Register

| Limitation ID | Missing or Uncertain Information | Potential Assessment Effect | Required Action |
|---|---|---|---|
| EL-01 | Complete case packet not yet reviewed | Vendor and technical details remain unknown. | Review original PDF. |
| EL-02 | Actual retention terms unavailable | Data lifecycle risk cannot be fully assessed. | Review vendor retention evidence. |
| EL-03 | Subprocessor details unavailable | External processing dependencies remain unknown. | Review subprocessor information. |
| EL-04 | Pre-pilot test results unavailable | AI reliability cannot be assessed. | Review the test report. |
| EL-05 | Human-review process not established | Oversight effectiveness remains unknown. | Confirm the actual workflow. |
| EL-06 | Contract terms not reviewed | Formal vendor commitments remain unverified. | Review contractual evidence. |
| EL-07 | Exact input-data fields unknown | Data minimisation cannot be completed. | Review the data profile. |
| EL-08 | Model and service details unknown | Technical dependencies and model limitations remain unclear. | Review vendor technical responses. |

## 10. Evidence Traceability Requirements

Every material AI risk should link to one or more evidence records.

The AI Risk Assessment should identify:

- The evidence ID supporting the risk.
- The source document or stakeholder.
- Whether the evidence is vendor-stated or independently supported.
- Any limitations affecting confidence.
- Whether additional validation is required.

The Governance Decision Memo should identify material evidence gaps that could change the final decision.

## 11. Reference Guidance

### NIST AI Risk Management Framework

[Official NIST AI RMF 1.0](https://www.nist.gov/itl/ai-risk-management-framework)

The framework organises AI risk management into Govern, Map, Measure, and Manage.

### NIST Generative AI Profile

[Official NIST AI 600-1 — Generative Artificial Intelligence Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence)

The profile provides supporting guidance for generative AI risks, including confabulation, data privacy, information integrity, information security, human-AI configuration, and third-party integration.

## 12. Evidence Status Summary

| Evidence Category | Current Position |
|---|---|
| Assignment purpose | Established from brief |
| Business function | Established from brief |
| Proposed AI capability | Established at high level |
| Vendor-specific responses | Awaiting case-packet review |
| Data-flow details | Awaiting case-packet review |
| Retention periods | Awaiting case-packet review |
| Subprocessor details | Awaiting case-packet review |
| Pre-pilot testing | Awaiting case-packet review |
| Human oversight | Awaiting case-packet review |
| Contractual commitments | Awaiting case-packet review |
| Independent validation | Not yet performed |

## 13. Document Status

**Status:** Initial evidence register prepared.

The actual vendor evidence, retention terms, subprocessor information, and pre-pilot test results must be entered after reviewing the complete GRC-AI-002 case packet.

No vendor control, test result, or contractual commitment is claimed as verified in this initial document.

This is an independent portfolio simulation. Avenloft Systems Group and all associated case employees, vendors, systems, and events are fictional.