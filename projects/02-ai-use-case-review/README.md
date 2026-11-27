# AI Use-Case Review and Governance Assessment

**Project ID:** GRC-AI-002  
**Organisation:** Avenloft Systems Group (fictional case study)  
**AI Service:** LumenFerry Resolve  
**Assessment Type:** AI Governance, Risk Assessment and Third-Party AI Review  
**Status:** Portfolio assessment — analyst recommendation documented; approval conditions remain proposed

## 1. Project Overview

This project evaluates a proposed AI-enabled customer-support summarisation service for Avenloft Systems Group, a fictional B2B logistics SaaS company.

The proposed service, LumenFerry Resolve, summarises customer-support tickets and call transcripts, extracts issue themes, and drafts internal case notes for Customer Success agents.

The objective is to determine whether the proposed AI use case can be introduced responsibly, with appropriate controls for data protection, information security, human oversight, third-party risk and AI output reliability.

The assessment uses the supplied fictional case packet and recognised NIST guidance. It does not represent an actual vendor deployment, production implementation or formal approval by a real organisation.

## 2. Business Context and Proposed Use

The case describes:

- 25 Customer Success agents participating in a proposed eight-week pilot.
- Approximately 58,000 support case notes generated annually.
- A proposed annual service cost of $46,000 if the service moves into production.
- AI-generated summaries and draft action items based on support tickets and call transcripts.
- Human review by the assigned agent before any generated text becomes a final internal case note.

The proposed workflow does not authorise autonomous customer communications, refunds, entitlement decisions, account actions or case closure.

## 3. Assessment Scope

This portfolio project covers:

1. Business and AI use-case analysis.
2. Data-flow mapping and scope definition.
3. Evidence collection and classification.
4. Stakeholder responsibilities and governance.
5. AI use-case inventory.
6. AI risk identification and assessment.
7. Risk treatment and monitoring recommendations.
8. Governance decision memo.
9. Reference and source register.

## 4. Key Assessment Findings

The case packet describes a pre-pilot evaluation of 50 synthetic support cases:

| Evaluation result | Cases | Percentage |
|---|---:|---:|
| Fully accurate and materially complete | 42 | 84% |
| Material troubleshooting step or limitation omitted | 5 | 10% |
| Unsupported factual detail introduced | 3 | 6% |
| **Total** | **50** | **100%** |

The evaluation indicates that human review is important. The assessment also identifies issues requiring further review, including:

- Potential exposure of API keys or secrets in support content.
- Vendor application and foundation-model subprocessor retention.
- Customer contractual restrictions and subprocessor approval requirements.
- Identity and access-management configuration.
- Vendor assurance, incident notification and recovery evidence.
- Output omissions, unsupported facts and performance changes after model updates.
- Risk of the pilot expanding beyond its approved purpose.

These findings are based on the fictional case packet, not independent testing of a live service.

## 5. Governance Recommendation

**Analyst recommendation: Conditionally Approve — subject to completion of mandatory pre-pilot conditions.**

This is a proposed assessment outcome, not an actual organisational approval.

The recommendation is conditional on matters such as:

- Completing security, privacy, procurement and contractual review.
- Confirming customer agreement requirements for the proposed data flow and subprocessors.
- Configuring enterprise SSO and restricting access to authorised pilot users.
- Confirming retention, deletion, telemetry and foundation-model data-handling terms.
- Implementing controls to prevent secrets from being submitted.
- Establishing documented human-review procedures.
- Completing pilot testing, monitoring and escalation arrangements.
- Defining stop, reassessment and shutdown triggers.

Customer data should not be processed through the proposed service until the required conditions have been completed and the authorised decision-makers have approved the pilot.

## 6. Repository Structure

```text
02-ai-use-case-review/
│
├── README.md
│
├── 01-case-analysis/
│   ├── use-case-overview.md
│   ├── data-flow-and-scope.md
│   ├── evidence-register.md
│   └── stakeholder-and-governance.md
│
├── 02-ai-use-case-inventory/
│   └── ai-use-case-inventory.md
│
├── 03-ai-risk-assessment/
│   ├── ai-risk-assessment.xlsx
│   └── risk-treatment-and-monitoring.md
│
├── 04-governance-decision/
│   └── ai-governance-decision-memo.md
│
└── 05-references/
    └── references.md
```

## 7. Risk Assessment Workbook

The Excel workbook contains:

- AI Risk Assessment
- Evidence Register
- Conditions & Monitoring
- Rating Matrix
- Use-Case Snapshot
- Dashboard

The assessment records inherent risk separately from target residual risk. Target residual ratings are provisional analyst estimates that assume the proposed conditions are implemented; they must not be interpreted as evidence that those controls are already operating.

## 8. Frameworks and References

The assessment draws on the following published NIST resources:

- [NIST AI Risk Management Framework (AI RMF 1.0)](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10)
- [NIST AI RMF Playbook](https://airc.nist.gov/airmf-resources/playbook/)
- [NIST AI 600-1: Generative AI Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence)
- [NIST SP 800-30 Rev. 1: Guide for Conducting Risk Assessments](https://csrc.nist.gov/pubs/sp/800/30/r1/final)

See [`05-references/references.md`](05-references/references.md) for the source register and source-to-deliverable mapping.

**Original case packet:** [Avenloft AI Use-Case Review Case Packet (PDF)](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf)

## 9. Important Limitations

- Avenloft Systems Group, LumenFerry AI and LumenFerry Resolve are fictional entities in the supplied case study.
- Vendor security, privacy and operational claims are treated as case-packet statements unless independently verified.
- The assessment is an educational portfolio exercise, not legal advice, an audit opinion, a certification or a production security assessment.
- Proposed controls and recommendations are not represented as implemented controls.
- Final risk acceptance and pilot approval belong to the organisation's authorised decision-makers.

## 10. Portfolio Objective

This project demonstrates a structured approach to reviewing an AI use case before deployment: understanding the business purpose, mapping data flows, evaluating AI-specific risks, assessing third-party dependencies, documenting governance responsibilities and presenting a conditional decision recommendation.

The emphasis is on evidence-based GRC analysis and practical governance documentation rather than claiming a real-world AI deployment.