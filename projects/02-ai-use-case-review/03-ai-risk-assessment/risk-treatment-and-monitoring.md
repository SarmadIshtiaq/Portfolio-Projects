# Avenloft Systems Group — AI Risk Treatment and Monitoring Plan

**Project ID:** GRC-AI-002  
**Use Case:** LumenFerry Resolve — Customer Support Summarisation  
**Business Owner:** Lena Ortiz, VP Customer Success  
**GRC Coordinator:** Aaron Bell, Director GRC  
**Document Status:** Proposed Conditions — Approval Pending  
**Assessment Type:** Independent Portfolio Simulation

## 1. Purpose

This document defines the proposed risk treatments, approval conditions, monitoring measures, and reassessment triggers for the LumenFerry Resolve pilot.

The proposed service would summarise Salesforce ticket text and support-call transcripts, extract issue themes, and draft action items for internal case notes.

The purpose is to ensure that the proposed use remains within its approved business purpose and that customer information is protected throughout the processing workflow.

This document separates:

- Existing safeguards supported by the case evidence.
- Vendor statements that have not been independently verified.
- Controls proposed as conditions of pilot approval.
- Monitoring responsibilities after the pilot begins.

**Primary source:** [GRC-AI-002 Case Packet, pages 3–10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf).

## 2. Assessment Basis

### 2.1 Pre-pilot evaluation

Customer Success evaluated LumenFerry Resolve using 50 synthetic support cases. No real customer content was used. Two Customer Success supervisors compared the outputs with source records.

| Evaluation Measure | Result | Assessment |
|---|---:|---|
| Fully accurate and materially complete summaries | 42 / 50 (84%) | Most summaries met the stated evaluation outcome. |
| Material omissions | 5 / 50 (10%) | Important troubleshooting steps or limitations were omitted. |
| Unsupported factual details | 3 / 50 (6%) | The service introduced information not supported by the source. |
| Correct case identifier extraction | 50 / 50 (100%) | Case identifier extraction was correct in this test. |
| External sends or autonomous actions | 0 / 50 | The tested configuration had no customer-send or action permission. |
| Median internal note preparation time | 6.8 to 3.1 minutes | The test workflow reduced median preparation time. |

**Source:** [GRC-AI-002 Case Packet, page 9 — Pre-Pilot Evaluation Results](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=9).

### 2.2 Important test limitations

The supplied test does not establish:

- Performance with real customer information.
- Performance across every support category and uncommon edge case.
- Stability after a model or product update.
- Whether busy agents will detect subtle errors consistently.

The 84% result must not be represented as a guaranteed real-world accuracy rate.

The 10% omission rate and 6% unsupported-detail rate are important findings for the pilot design.

### 2.3 Data-handling context

The support-data sample identifies business contact information, operational customer data, and product or technical data as common categories.

Three support tickets in the prior 12 months contained a pasted API key or secret before the value was removed and the customer was instructed to rotate it.

Attachments are outside the proposed AI pilot.

**Source:** [GRC-AI-002 Case Packet, page 8 — Support Data Profile](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=8).

## 3. Existing Safeguards and Vendor Claims

The following items are present in the case evidence, but their status must be described accurately.

| Item | Evidence Classification | Assessment |
|---|---|---|
| AI Draft field in Salesforce | Proposed pilot workflow | Preserves the original ticket and transcript; actual configuration must be verified. |
| Agent Accept/Edit/Reject | Proposed pilot workflow | Provides a human review step; enforcement must be tested. |
| No automatic customer messages in tested configuration | Synthetic test configuration | Supports the proposed boundary; production integration permissions still require verification. |
| Enterprise SAML SSO and SCIM | Vendor-stated feature availability | Available on Enterprise; not evidence that Avenloft has configured them. |
| TLS 1.2 or later and AES-256 encryption | Vendor-stated | Technical configuration and supporting evidence require review. |
| 180 days of administrative audit-log export | Vendor-stated | Export capability should be confirmed during vendor review. |
| SOC 2 Type II report | Vendor-stated availability | Avenloft has not reviewed the report. |
| No shared or foundation-model training under Enterprise terms | Vendor-stated contractual response | Exact Enterprise contract wording must be reviewed. |
| 90-day default application retention; 30 days configurable on Enterprise | Vendor-stated | Enterprise setting must be configured and verified. |
| Foundation-model subprocessor retention up to 30 days | Vendor-stated | Subprocessor terms and processing details require review. |
| Case deletion within seven days, subject to backup rotation | Vendor-stated | Backup rotation and deletion evidence require clarification. |

**Source:** [GRC-AI-002 Case Packet, pages 6–7](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=6).

A vendor statement is not independent proof that a control is effective.

## 4. Candidate Risk Treatment Plan

### AI-R01 — Confabulation and Unsupported Statements

**Risk:** The AI may generate facts or actions that are not present in the source, and an agent may accept them into an internal case note.

**Evidence:** Three of 50 synthetic summaries contained at least one unsupported factual detail. In test case T-42, the tool suggested restarting a warehouse connector even though the source did not contain that recommendation.

[Source: Case Packet, page 9](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=9).

**Treatment:** Mitigate.

**Proposed approval conditions:**

- Require source-based human review before acceptance into the final case note.
- Keep the original ticket and transcript available.
- Allow the agent to edit or reject unsupported output.
- Record corrections and rejection reasons.
- Train agents to identify unsupported statements.

**Proposed owner:** Lena Ortiz.

**Monitoring:**

- Unsupported-statement rate.
- Agent correction and rejection rate.
- Sampled source-to-summary comparison.
- Material errors accepted into final notes.

**Stop or reassessment trigger:**

Any material unsupported statement that reaches a final case note, repeated output-quality failures, or inability to verify generated content.

### AI-R02 — Omission or Distortion of Source Information

**Risk:** The summary may omit a material troubleshooting step or remove uncertainty from the original information.

**Evidence:**

- Five of 50 synthetic summaries omitted a material troubleshooting step or limitation.
- T-17 changed “intermittently after 14:00 UTC” into a statement that the issue began at 14:00 UTC.
- T-31 omitted that the customer had already rotated the service-account secret.

[Source: Case Packet, page 9](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=9).

**Treatment:** Mitigate.

**Proposed approval conditions:**

- Require comparison against the original source.
- Preserve uncertainty, dates, and prior remediation details.
- Include a review procedure for security-related and troubleshooting statements.
- Allow correction or rejection before final case-note approval.

**Proposed owner:** Lena Ortiz.

**Monitoring:**

- Material omission rate.
- Correction and rejection reasons.
- Source-review sampling.
- Repeated omission patterns by support category.

**Stop or reassessment trigger:**

A material omission that changes the meaning of a customer event, security action, prior remediation, or troubleshooting instruction.

### AI-R03 — Customer Secrets Submitted to the AI Service

**Risk:** A support ticket or transcript containing an API key, token, or other secret may be submitted to LumenFerry and its foundation-model subprocessor.

**Evidence:** Three support tickets during the prior 12 months contained a pasted API key or secret before removal and customer rotation.

[Source: Case Packet, page 8](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=8).

**Treatment:** Mitigate — mandatory pre-pilot condition.

**Proposed approval conditions:**

- Implement pre-submission secret detection.
- Block or redact suspected credentials and secrets.
- Apply detection to both ticket text and call transcripts.
- Test detection against representative synthetic examples.
- Define an escalation process for suspected secret exposure.
- Keep attachments excluded from the pilot.

**Proposed owner:** Lena Ortiz, with Maya Chen providing security escalation.

**Monitoring:**

- Detected secrets.
- Blocked or redacted submissions.
- False-negative test results.
- Security exceptions and credential-rotation events.

**Stop or reassessment trigger:**

Any confirmed API key, token, or other secret transmitted to LumenFerry or its subprocessor, or failure of the approved detection process.

### AI-R04 — Retention, Deletion, and Telemetry Ambiguity

**Risk:** Customer content may remain in the vendor or subprocessor environment longer than Avenloft permits, or transformed customer-content excerpts may enter telemetry.

**Evidence and vendor responses:**

- Default application retention is 90 days.
- Enterprise retention can be configured to 30 days.
- Zero-retention processing is unavailable.
- The foundation-model subprocessor may retain inputs and outputs for up to 30 days.
- Telemetry is described as aggregated and de-identified, but the standard response does not define whether transformed content excerpts can be included.
- Case deletion is stated to complete within seven days, subject to backup rotation.

[Source: Case Packet, page 7](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=7).

**Treatment:** Mitigate — mandatory pre-pilot condition.

**Proposed approval conditions:**

- Purchase the Enterprise plan.
- Configure application retention to 30 days.
- Obtain written clarification about telemetry.
- Obtain contractual confirmation that customer-content excerpts will not be included in telemetry without approved terms.
- Confirm subprocessor retention and deletion arrangements.
- Document how backup rotation affects final deletion.
- Retain deletion-request evidence.

**Proposed owners:** Lena Ortiz and Hannah Kim.

**Monitoring:**

- Configured retention period.
- Deletion completion time.
- Outstanding deletion requests.
- Telemetry exceptions.
- Subprocessor retention changes.

**Stop or reassessment trigger:**

Retention configuration changes, deletion failure, undeclared customer-content use in telemetry, or a material change to retention terms.

### AI-R05 — Foundation-Model Subprocessor and Customer-Contract Conflict

**Risk:** Customer content may be processed by an additional AI provider without the required contractual oversight or customer approval.

**Evidence:**

- LumenFerry uses a third-party foundation-model subprocessor.
- Subprocessor changes receive at least 30 days' notice under Enterprise terms.
- Hannah Kim states that several enterprise customer agreements have different requirements for new subprocessors and use of customer data.

[Sources: Case Packet, pages 7 and 10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=7).

**Treatment:** Mitigate — mandatory pre-pilot condition.

**Proposed approval conditions:**

- Identify the foundation-model subprocessor.
- Document its processing role and locations.
- Review its data-handling and security commitments.
- Map the relevant customer agreements.
- Obtain any required customer notice or approval before affected data is processed.
- Include subprocessor-change notification and review arrangements in the contract or order form.

**Proposed owners:** Noah Grant and Hannah Kim.

**Monitoring:**

- Current subprocessor inventory.
- Subprocessor change notices.
- Outstanding customer-contract reviews.
- Open vendor due-diligence findings.

**Stop or reassessment trigger:**

An unapproved subprocessor, unreviewed model-provider change, or an unresolved customer-contract requirement.

### AI-R06 — Identity and Access Control

**Risk:** Unrestricted or poorly managed user access may expose customer-support content or allow access beyond the approved pilot group.

**Evidence:**

- SAML SSO and SCIM are available on the Enterprise plan.
- Local password accounts can be disabled after SSO configuration.
- Marcus Holloway proposes disabling local logins and restricting access to the Customer Success pilot group.

[Sources: Case Packet, pages 6 and 10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=6).

**Treatment:** Mitigate — mandatory pre-pilot condition.

**Proposed approval conditions:**

- Purchase the Enterprise plan.
- Configure SAML SSO and SCIM.
- Disable local password logins.
- Restrict access to the 25 approved pilot agents.
- Test onboarding, role changes, and offboarding.
- Review the Salesforce integration permissions.

**Proposed owner:** Marcus Holloway.

**Monitoring:**

- Pilot group membership.
- Local-login status.
- Access-review exceptions.
- Deprovisioning results.

**Stop or reassessment trigger:**

Any local login remains enabled contrary to the approved design, access is granted outside the pilot group, or an access-removal failure occurs.

### AI-R07 — Human Oversight and Automation Bias

**Risk:** Agents may rely on generated summaries without adequate source review, allowing inaccurate or incomplete content to become part of the final internal case note.

**Evidence:**

- The proposed workflow places the summary in an AI Draft field.
- The assigned agent compares the draft with the source and chooses Accept, Edit, or Reject.
- The synthetic evaluation does not establish whether agents will detect subtle errors when busy.

[Sources: Case Packet, pages 5 and 9](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=5).

**Treatment:** Mitigate.

**Proposed approval conditions:**

- Keep human review mandatory.
- Ensure source content remains available.
- Require agents to verify material statements.
- Record accept, edit, and reject actions.
- Provide user training.
- Do not treat generated summaries as authoritative without human approval.

**Proposed owner:** Lena Ortiz.

**Monitoring:**

- Review completion.
- Acceptance, correction, and rejection rates.
- Review exceptions.
- Quality samples from participating agents.

**Stop or reassessment trigger:**

Review bypass, loss of source visibility, or repeated material errors being accepted into final case notes.

### AI-R08 — Performance Representativeness and Model Change

**Risk:** Results from the synthetic test may not reflect real customer-data performance, and model changes may reduce summary quality without adequate reassessment.

**Evidence:**

- The pre-pilot evaluation used 50 synthetic cases.
- The vendor manages underlying model selection.
- Material platform changes are documented in release notes.
- Generation records identify the user, source case ID, timestamp, product release, and internal model-version identifier.
- The product does not expose calibrated confidence scores for individual summaries.

[Sources: Case Packet, pages 7 and 9](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=7).

**Treatment:** Mitigate.

**Proposed approval conditions:**

- Define business-approved quality acceptance criteria before the pilot.
- Use representative support categories in testing.
- Establish a baseline for omissions and unsupported facts.
- Review the output by source category.
- Repeat evaluation after material model or product changes.
- Record product release and model-version identifiers.

**Proposed owner:** Lena Ortiz, with Aaron Bell coordinating GRC review.

**Monitoring:**

- Accuracy and completeness results.
- Omission and unsupported-detail rates.
- Performance by support category.
- Model and product release information.

**Stop or reassessment trigger:**

Material deterioration, an unreviewed model change, breached acceptance criteria, or loss of traceability.

### AI-R09 — Vendor Assurance and Incident Response

**Risk:** Avenloft may rely on the service without sufficient assurance evidence or clear contractual incident and recovery commitments.

**Evidence:**

- LumenFerry states that a current SOC 2 Type II report is available under NDA.
- Avenloft has not yet reviewed the report.
- The vendor states that production backups are maintained and recovery procedures are tested annually.
- Detailed recovery results were not supplied.
- Standard terms refer to customer notification without undue delay after the vendor confirms an incident involving customer content.

[Source: Case Packet, page 6](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=6).

**Treatment:** Mitigate — mandatory pre-pilot condition.

**Proposed approval conditions:**

- Review the SOC 2 Type II report under NDA.
- Check its scope, examination period, exceptions, and relevant subservice dependencies.
- Obtain available business-continuity and recovery-test evidence.
- Ask the vendor to clarify incident notification and cooperation requirements.
- Obtain Legal review of the final terms.

**Proposed owners:** Maya Chen, Hannah Kim, and Noah Grant.

**Monitoring:**

- Open SOC 2 exceptions.
- Unresolved contractual gaps.
- Vendor incident notifications.
- Recovery-assurance evidence.

**Stop or reassessment trigger:**

An unacceptable assurance exception, unresolved contractual requirement, material vendor incident, or inability to support required incident response.

### AI-R10 — Expansion Beyond Approved Pilot Scope

**Risk:** Integration permissions or business use may expand beyond internal summaries and draft action items, enabling autonomous or unauthorised customer-facing or account actions.

**Evidence:**

The proposed pilot excludes:

- Automated customer replies.
- Entitlement decisions.
- Refunds.
- Account actions.
- Case closure.
- Autonomous prioritisation.
- Employee or customer scoring.

The tested configuration had no customer-send or autonomous-action permission.

[Sources: Case Packet, pages 4–5 and 9](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=page=5).

**Treatment:** Mitigate.

**Proposed approval conditions:**

- Enforce least-privilege integration permissions.
- Technically prevent excluded actions.
- Keep the pilot limited to the approved 25-agent group.
- Require a new governance review before scope expansion.
- Maintain a rapid integration-disable process.

**Proposed owners:** Lena Ortiz and Marcus Holloway.

**Monitoring:**

- Integration permission review.
- Scope-change requests.
- Excluded-action test results.
- Pilot user membership.

**Stop or reassessment trigger:**

Any automated customer message, refund, entitlement change, account action, case closure, autonomous prioritisation, or unapproved expansion.

## 5. Pre-Pilot Approval Conditions

The following conditions should be completed and verified before customer data is submitted to LumenFerry.

| Condition ID | Required Condition | Proposed Owner | Required Evidence |
|---|---|---|---|
| C-01 | Enforce mandatory human source review and Accept/Edit/Reject recording. | Lena Ortiz | Demonstrated workflow and audit trail. |
| C-02 | Implement secret detection and redaction for ticket text and transcripts. | Lena Ortiz / Maya Chen | Successful detection and false-negative tests. |
| C-03 | Configure Enterprise retention to 30 days and resolve telemetry, subprocessor, backup, and deletion terms. | Lena Ortiz / Hannah Kim | Configuration evidence and written contractual clarification. |
| C-04 | Identify and review the foundation-model subprocessor and customer agreement requirements. | Noah Grant / Hannah Kim | Subprocessor inventory and customer-contract review. |
| C-05 | Configure SAML SSO/SCIM, disable local accounts, and restrict access to the pilot group. | Marcus Holloway | Configuration and access-lifecycle test evidence. |
| C-06 | Train agents on source verification, unsupported statements, and omissions. | Lena Ortiz | Approved procedure and training records. |
| C-07 | Define quality thresholds and a model-change regression process. | Lena Ortiz / Aaron Bell | Approved test protocol and acceptance criteria. |
| C-08 | Review the SOC 2 Type II report and available continuity evidence. | Maya Chen / Hannah Kim / Noah Grant | Review record and documented exceptions. |
| C-09 | Enforce all prohibited-use and integration permission boundaries. | Lena Ortiz / Marcus Holloway | Permission test results and approved scope. |
| C-10 | Establish and test a rapid method to disable the integration. | Maya Chen / Marcus Holloway | Stop procedure and successful disablement test. |
| C-11 | Determine whether customer notices or additional approvals are required. | Hannah Kim | Documented customer-contract and privacy review. |
| C-12 | Use source-based quality monitoring because calibrated per-summary confidence scores are not available. | Lena Ortiz / Aaron Bell | Approved monitoring design and review records. |

These are proposed conditions. They must not be described as completed controls until evidence confirms implementation.

## 6. Pilot Monitoring Plan

The pilot is proposed for 25 Customer Success agents over eight weeks.

The following monitoring plan is recommended.

| Monitoring Area | Metric or Evidence | Proposed Review |
|---|---|---|
| Summary accuracy | Accuracy and material completeness in sampled outputs | Weekly during pilot |
| Confabulation | Unsupported factual details and their severity | Weekly and immediate review of material incidents |
| Information integrity | Material omissions, changed meaning, and lost uncertainty | Weekly |
| Human oversight | Review completion, corrections, rejections, and bypasses | Weekly |
| Secret handling | Secret detection, blocked submissions, and suspected transmission | Immediate security escalation |
| Data minimisation | Input-field and excluded-data exceptions | Weekly |
| Access management | Pilot group membership and access-removal exceptions | At onboarding/offboarding and periodic review |
| Retention and deletion | Configured retention and deletion evidence | Before pilot and periodic review |
| Vendor chain | Subprocessor and model-provider notices | On every material notice |
| Security events | Vendor or Avenloft incidents involving the service or data | Immediate escalation |
| Model changes | Release notes, model identifiers, and regression results | On material change |
| Scope compliance | Use outside the approved purpose or prohibited actions | Continuous operational control, reviewed weekly |

The weekly cadence is a proposed monitoring arrangement for this eight-week pilot, not an existing Avenloft requirement.

## 7. Reassessment and Shutdown Triggers

The following events should trigger immediate review and, where appropriate, suspension of the affected integration or pilot.

1. A secret or credential is submitted to LumenFerry or its foundation-model subprocessor.
2. Customer information is processed outside the approved data scope.
3. A material unsupported statement enters a final case note.
4. Repeated material omissions occur.
5. Human review is bypassed or source information is unavailable.
6. An unapproved model or subprocessor change occurs.
7. A material security or privacy incident affects customer information.
8. A retention, deletion, or telemetry commitment is breached.
9. Required customer notice or approval is missing.
10. An excluded autonomous action becomes available or is performed.
11. The service cannot be disabled promptly when required.
12. Model or product changes cause quality to fall below the approved threshold.

Maya Chen, as CISO, has identified the need for a quick way to stop the integration if quality or security becomes unacceptable.

[Source: Case Packet, page 10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=10).

## 8. Ownership and Escalation

| Role | Responsibility |
|---|---|
| Lena Ortiz — VP Customer Success | Business owner, pilot accountability, output quality, and agent oversight. |
| Aaron Bell — Director GRC | Coordinates the assessment, maintains inventory and risk records, and prepares the governance recommendation. |
| Maya Chen — CISO | Security escalation and material customer-data or AI risk oversight. |
| Hannah Kim — General Counsel & Privacy Lead | Reviews customer agreements, privacy, and contractual issues. |
| Noah Grant — Director Procurement | Vendor onboarding, due diligence, contracting, and order-form conditions. |
| Marcus Holloway — Director IT & Workplace Technology | SSO, SCIM, local login disablement, and workforce access controls. |

**Source:** [Case Packet, pages 3 and 10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=3).

## 9. Final Treatment Position

The recommended treatment is to pursue a narrow, controlled pilot only after all mandatory pre-pilot conditions are implemented and verified.

The pilot should remain limited to internal support summarisation and draft case notes.

The 50-case synthetic evaluation provides useful evidence of potential productivity benefit, but it also identifies material omissions and unsupported output. It does not establish real-customer performance or consistent detection by busy agents.

The data-handling and third-party terms require further review, especially retention, telemetry, subprocessor processing, customer-contract requirements, and deletion.

The final governance decision must be documented in the AI Governance Decision Memo.

## 10. Document Status

| Activity | Status |
|---|---|
| Candidate AI risks documented | Complete |
| Case evidence mapped | Complete |
| Proposed treatments documented | Complete |
| Pre-pilot conditions defined | Proposed |
| Monitoring measures defined | Proposed |
| Stop and reassessment triggers defined | Proposed |
| Condition implementation | Not verified |
| Pilot approval | Pending authorised decision |
| Customer data processing | Not approved by this document |

This document is part of an independent portfolio simulation. Avenloft Systems Group, LumenFerry AI, LumenFerry Resolve, and all people, records, vendor terms, test results, and events are fictional.