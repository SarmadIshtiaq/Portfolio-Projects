# Project 02 — References and Source Register

**Project ID:** GRC-AI-002  
**Project:** Evaluate a New AI Use Case  
**Organisation:** Avenloft Systems Group (Fictional)  
**Use Case:** LumenFerry Resolve — Customer Support Summarisation  
**Reference Review Basis:** Supplied GRC-AI-002 Case Packet  
**Document Status:** References Recorded

## 1. Purpose

This document records the primary case material and authoritative guidance used to assess Avenloft's proposed AI-enabled customer-support summarisation pilot.

The references support:

- AI use-case identification and inventory.
- Business purpose and stakeholder analysis.
- Data-flow and third-party dependency review.
- Generative AI risk assessment.
- Human oversight and output-quality evaluation.
- Qualitative likelihood-and-impact assessment.
- Risk treatment, monitoring, and governance decisions.

The fictional case packet is the controlling source for Avenloft-specific facts, vendor responses, stakeholder statements, test results, and proposed pilot boundaries.

NIST publications provide supporting risk-management guidance. They do not establish fictional vendor facts or automatically certify the proposed service.

## 2. Primary Case Source

### REF-01 — Avenloft AI Use-Case Review Case Packet

**Case ID:** GRC-AI-002  
**Publisher / Source:** LabList training case  
**Issue date:** September 22, 2026  
**Document type:** Fictional AI governance training case  
**Length:** 15 pages

[Download Avenloft AI Use-Case Review Case Packet (PDF)](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf)

**Purpose in this project**

This is the primary source for the proposed use case and all company-specific evidence.

| Case Packet Page | Information Used |
|---|---|
| Page 1 | Case identification, assignment ownership, fictional-entity notice |
| Page 2 | Assignment brief, required deliverables, assessment boundaries |
| Page 3 | Business context, risk appetite, governance roles, interim AI direction |
| Page 4 | AI use-case intake, business purpose, intended users, pilot proposal |
| Page 5 | Proposed workflow, data flow, human review, explicit exclusions |
| Page 6 | LumenFerry vendor fact sheet, hosting, encryption, SSO, audit logs, SOC 2, continuity |
| Page 7 | Vendor data-handling responses, retention, subprocessor, telemetry, deletion, model changes |
| Page 8 | Support-data profile, customer-data categories, historical secret examples |
| Page 9 | Pre-pilot evaluation results, examples of omissions and unsupported output, test limitations |
| Page 10 | Stakeholder notes from Customer Success, CISO, Legal & Privacy, Procurement, IT, and GRC |
| Page 11 | NIST AI RMF working lens and relevant generative AI risk areas |
| Page 12 | Qualitative likelihood-and-impact methodology and risk determination matrix |
| Page 13 | Required AI use-case inventory and AI risk assessment fields |
| Page 14 | Decision memo requirements and governance questions |
| Page 15 | Analyst quality expectations, authoritative reference list, version note, fiction notice |

**Important evidence rule**

The packet explicitly states that vendor information must be treated as vendor-supplied evidence, not independently verified fact.

The assessment must distinguish case facts, vendor statements, synthetic test results, stakeholder statements, existing safeguards, and proposed approval conditions.

## 3. NIST AI Risk Management Framework

### REF-02 — NIST AI 100-1: Artificial Intelligence Risk Management Framework (AI RMF 1.0)

**Publisher:** National Institute of Standards and Technology (NIST)  
**Publication:** AI RMF 1.0  
**Document identifier:** NIST AI 100-1

[Official NIST AI RMF 1.0 Publication](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-ai-rmf-10)

**How this source is used**

The framework organises AI risk management into four functions:

| Function | Application in Project 2 |
|---|---|
| Govern | Accountability, ownership, policies, inventory, third-party oversight, and review processes |
| Map | Intended purpose, users, input data, outputs, stakeholders, human role, system boundaries, and dependencies |
| Measure | Evaluation results, reliability, limitations, privacy, security, and traceability |
| Manage | Risk treatment, approval conditions, monitoring, reassessment, and shutdown decisions |

**Project application**

Used to organise the AI use-case inventory, risk scenarios, governance responsibilities, risk treatment, and final decision.

The case packet states that the four functions are not a rigid sequence or a checklist.

It also identifies AI RMF 1.0 as a voluntary governance reference for this exercise, not a compliance certification.

[Case reference: page 11](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=11).

### REF-03 — NIST AI RMF Playbook

**Publisher:** National Institute of Standards and Technology (NIST)  
**Resource type:** Practical AI RMF implementation resource

[Official NIST AI RMF Playbook](https://airc.nist.gov/airmf-resources/playbook/)

**How this source is used**

- Provides practical suggestions for applying AI RMF functions.
- Supports the identification of governance activities.
- Helps translate framework concepts into assessment and management actions.
- Provides additional context when documenting AI governance responsibilities and monitoring.

**Project application**

Used as supplementary guidance rather than a mandatory checklist or a substitute for evidence-based analysis.

## 4. Generative Artificial Intelligence Guidance

### REF-04 — NIST AI 600-1: Artificial Intelligence Risk Management Framework — Generative Artificial Intelligence Profile

**Publisher:** National Institute of Standards and Technology (NIST)  
**Document identifier:** NIST AI 600-1  
**Publication:** Generative Artificial Intelligence Profile

[Official NIST AI 600-1 Publication](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence)

**How this source is used**

The project uses relevant generative AI risk areas identified in the Avenloft case packet.

| Risk Area | Application to LumenFerry Resolve |
|---|---|
| Confabulation | Generated summaries may contain unsupported or incorrect statements. |
| Data Privacy | Customer information may be retained, disclosed, reused, or processed beyond the intended purpose. |
| Human-AI Configuration | Agents may over-rely on summaries or fail to review them adequately. |
| Information Integrity | Generated case notes may omit or distort important source information. |
| Information Security | Service identities, integrations, logs, and customer content require appropriate protection. |
| Value Chain / Component Integration | The foundation-model subprocessor and future model changes introduce additional dependencies. |

**Project application**

Used to connect generative AI risks to the actual support-summarisation workflow rather than listing unrelated AI risks.

[Case reference: page 11](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=11).

## 5. Cybersecurity Risk Assessment Method

### REF-05 — NIST SP 800-30 Rev. 1: Guide for Conducting Risk Assessments

**Publisher:** National Institute of Standards and Technology (NIST)  
**Publication:** September 2012  
**Revision:** 1  
**Relevant section:** Appendix I, Table I-2

[Official NIST SP 800-30 Rev. 1 Publication](https://csrc.nist.gov/pubs/sp/800/30/r1/final)

**How this source is used**

- Supports structured risk assessment.
- Provides likelihood and impact assessment guidance.
- Provides the qualitative risk determination matrix referenced by the Avenloft case.
- Supports the distinction between risk before safeguards and risk remaining after safeguards.

**Project application**

Avenloft requires the same qualitative likelihood-and-impact method used in Project 1.

The risk levels are:

- Very Low
- Low
- Moderate
- High
- Very High

The case packet provides working interpretations of likelihood and impact and the corresponding determination matrix.

The assessment must rate inherent risk before giving credit to current or proposed safeguards. Proposed approval conditions must be distinguished from controls that already operate.

[Case reference: page 12](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=12).

## 6. Source-to-Deliverable Mapping

| Project Document | Primary Case Evidence | Supporting Reference |
|---|---|---|
| `README.md` | REF-01, pages 1–2 | REF-02, REF-04 |
| `use-case-overview.md` | REF-01, pages 3–5 | REF-02 |
| `data-flow-and-scope.md` | REF-01, pages 4–8 | REF-02, REF-04 |
| `evidence-register.md` | REF-01, pages 5–10 | REF-02, REF-04, REF-05 |
| `stakeholder-and-governance.md` | REF-01, pages 3 and 10–11 | REF-02, REF-03 |
| `ai-use-case-inventory.md` | REF-01, pages 3–5 and 13 | REF-02 |
| `ai-risk-assessment.xlsx` | REF-01, pages 5–12 | REF-02, REF-04, REF-05 |
| `risk-treatment-and-monitoring.md` | REF-01, pages 6–14 | REF-02, REF-03, REF-04, REF-05 |
| `ai-governance-decision-memo.md` | REF-01, pages 2–14 | REF-02, REF-03, REF-04, REF-05 |

## 7. Evidence Classification

The project uses the following evidence classifications:

| Classification | Meaning |
|---|---|
| Case Fact | Information explicitly provided as a fact in the fictional case. |
| Vendor-Stated | Information supplied by LumenFerry that has not been independently verified. |
| Synthetic Test Result | Result from the 50-case synthetic pre-pilot evaluation. |
| Stakeholder Statement | Position or proposal expressed by an Avenloft stakeholder. |
| Proposed Control | A safeguard recommended for the pilot but not yet demonstrated as implemented. |
| Independently Validated | Evidence checked through an appropriate independent method. |
| Needs Validation | Information requiring clarification or additional evidence. |

These categories must remain separate in the risk assessment and decision memo.

## 8. Publication and Version Notes

The case packet's page 15 version note states that, as of September 2026:

- NIST AI RMF 1.0 remained the published framework used in the case, with a revision in progress.
- NIST AI 600-1 had been updated on April 8, 2026.

The project uses the versions and references specified by the supplied case packet.

For any later formal assessment, the official NIST publication pages should be checked again before relying on publication status or revised guidance.

[Source: GRC-AI-002 Case Packet, page 15](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=15).

## 9. Source Use and Evidence Integrity

The following rules apply:

1. Avenloft-specific facts must be supported by the supplied case packet.
2. Vendor claims must be identified as vendor-stated until verified.
3. Synthetic test results must not be represented as real-customer performance.
4. Proposed conditions must not be described as implemented controls.
5. Unknown contractual or privacy obligations must be referred to Legal and Privacy.
6. NIST guidance must not be described as proof of compliance or certification.
7. Risk ratings must include evidence-based reasoning.
8. The final decision must state the approved scope and prohibited uses.
9. Material assumptions and evidence gaps must remain visible.
10. Fictional organisations, vendors, employees, records, and events must remain clearly identified as fictional.

## 10. Assessment Limitations

This reference register supports an independent training simulation.

It is not a legal opinion, formal audit, certification assessment, or real organisational approval.

The assessment is limited to the fictional case evidence and the cited public guidance.

The final governance decision would require approval by the authorised Avenloft decision-maker and completion of the required specialist reviews.

## 11. Reference Review Status

| Activity | Status |
|---|---|
| Primary case packet identified | Complete |
| NIST AI RMF 1.0 recorded | Complete |
| NIST AI RMF Playbook recorded | Complete |
| NIST AI 600-1 recorded | Complete |
| NIST SP 800-30 Rev. 1 recorded | Complete |
| Source-to-deliverable mapping | Complete |
| Vendor evidence independently validated | Not claimed |
| Legal and Privacy review | Pending |
| Authorised governance decision | Pending |

**Document status:** Reference register prepared for Project 2.

Avenloft Systems Group, LumenFerry AI, LumenFerry Resolve, all employees, vendors, records, test results, and events in the case are fictional. This is an independent portfolio simulation, not a real client engagement.