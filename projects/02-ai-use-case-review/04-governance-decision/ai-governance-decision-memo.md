# Avenloft Systems Group — AI Governance Decision Memo

**Case ID:** GRC-AI-002  
**Subject:** Governance Decision — LumenFerry Resolve Customer Success Pilot  
**To:** Security Steering Committee  
**From:** Aaron Bell, Director — Governance, Risk & Compliance  
**Business Owner:** Lena Ortiz, VP — Customer Success  
**Decision Recommended:** CONDITIONALLY APPROVE  
**Decision Status:** Proposed — Authorised Approval Pending  
**Assessment Type:** Independent Portfolio Simulation

---

## 1. Executive Decision

**Recommendation: CONDITIONALLY APPROVE the proposed eight-week Customer Success pilot, subject to completion and verification of the mandatory conditions in this memo.**

The proposed use case is narrow and has a defined business purpose. LumenFerry Resolve would summarise selected Salesforce ticket content and support-call transcripts, extract issue themes, and prepare draft internal case notes for review by Customer Success agents.

The proposed workflow preserves the original ticket and transcript. The assigned agent can compare the draft with source material and choose Accept, Edit, or Reject. The pilot excludes automated customer replies and autonomous account or case actions.

The proposed use is consistent with Avenloft's objective to improve productivity without creating unmanaged customer-data or decision risk. However, the current evidence does not justify processing customer information until the required security, privacy, vendor, data-handling, and human-oversight conditions are completed.

[Source: GRC-AI-002 Case Packet, pages 3–5](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=3).

**This memo does not authorise customer-data processing.** The pilot may begin only after the mandatory pre-pilot conditions have been implemented, tested, documented, and approved by the authorised decision-maker.

## 2. Business Rationale

Customer Success estimates that agents create approximately 58,000 internal case notes each year.

The business reports that agents spend significant time converting call transcripts and long ticket histories into internal notes before handoff or closure.

In the supplied pre-pilot evaluation:

- 50 synthetic support cases were tested.
- 42 summaries were fully accurate and materially complete.
- 5 summaries omitted a material troubleshooting step or limitation.
- 3 summaries introduced at least one unsupported factual detail.
- All 50 case identifiers were extracted correctly.
- Median note-preparation time decreased from 6.8 minutes to 3.1 minutes in the test workflow.

The test results indicate potential productivity value. They also demonstrate that summaries can omit or introduce material information.

The results do not establish performance with real customer information, all support categories, uncommon cases, or future model versions.

[Source: GRC-AI-002 Case Packet, page 9](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=9).

The productivity benefit is therefore promising but must be validated during a controlled pilot.

## 3. Approved Pilot Scope

The following is the proposed scope if all required conditions are satisfied.

| Scope Item | Approved Boundary |
|---|---|
| Business function | Customer Success |
| Business owner | Lena Ortiz, VP Customer Success |
| Users | 25 named Customer Success agents |
| Pilot duration | Eight weeks |
| AI service | LumenFerry Resolve |
| Primary purpose | Internal support summarisation |
| Input data | Ticket body, case ID, product area, selected necessary metadata, and transcript text for calls linked to a case |
| Processing | Summarisation, issue-theme extraction, and draft action-item generation |
| Integration | Salesforce and the existing call-transcription platform through the proposed integration |
| Output destination | Salesforce AI Draft field |
| Human review | Assigned agent compares the draft with source material and selects Accept, Edit, or Reject |
| Final record | Only accepted or edited text may become the final internal case note |
| Original source | Original ticket and transcript must remain unchanged and available |

Customer contact name and business email may appear in ticket text. Avenloft must review which selected metadata is necessary before processing begins.

No attachment is required for the proposed pilot.

[Source: GRC-AI-002 Case Packet, pages 4–5 and 8](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=4).

## 4. Prohibited Uses and Data Boundaries

The following uses remain outside the proposed approval.

1. Sending AI-generated text automatically to customers.
2. Automated customer replies.
3. Refund decisions or issuance.
4. Entitlement decisions or changes.
5. Account actions.
6. Automated case closure.
7. Autonomous prioritisation.
8. Employee or customer scoring.
9. Submission of support attachments.
10. Use outside the approved Customer Success pilot without a new governance review.

Customer credentials and secrets must not be submitted to the service. The business must implement and test a suitable pre-submission detection and blocking or redaction process.

The vendor's Enterprise terms must also clearly prohibit unapproved use of customer content for model training or other secondary purposes.

[Sources: GRC-AI-002 Case Packet, pages 5, 7–8](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=5).

## 5. Mandatory Pre-Pilot Conditions

No customer data may be processed until all mandatory conditions below have been completed and verified.

| ID | Required Condition | Accountable Owner | Required Evidence |
|---|---|---|---|
| C-01 | Configure Enterprise SAML SSO and SCIM, disable local password accounts, and restrict access to the 25 approved pilot agents. | Marcus Holloway | Configuration evidence and access-lifecycle test results. |
| C-02 | Implement and test detection and blocking or redaction of API keys, tokens, and other secrets in ticket text and call transcripts. | Lena Ortiz, with Maya Chen | Successful detection tests and documented exception handling. |
| C-03 | Configure LumenFerry application retention to 30 days under Enterprise terms. | Lena Ortiz | Verified retention configuration. |
| C-04 | Obtain written clarification on telemetry, transformed customer-content excerpts, subprocessor retention, deletion, and backup rotation. | Hannah Kim | Reviewed contractual terms and written vendor clarification. |
| C-05 | Identify the foundation-model subprocessor and complete its security, privacy, and data-processing review. | Noah Grant and Hannah Kim | Subprocessor inventory and due-diligence evidence. |
| C-06 | Review applicable customer agreements and determine whether any customer notice or approval is required before processing. | Hannah Kim | Documented customer-contract and privacy review. |
| C-07 | Review the vendor's SOC 2 Type II report under NDA, including scope, examination period, exceptions, and relevant subservice dependencies. | Maya Chen | Completed review and documented exceptions. |
| C-08 | Review business-continuity evidence and clarify contractual incident-notification and cooperation requirements. | Maya Chen and Hannah Kim | Reviewed continuity evidence and approved contract terms. |
| C-09 | Demonstrate that the Salesforce draft workflow requires source-based human review and preserves Accept/Edit/Reject records. | Lena Ortiz and Marcus Holloway | Tested workflow and audit evidence. |
| C-10 | Establish and test quality acceptance criteria for material omissions and unsupported factual statements. | Lena Ortiz, with Aaron Bell | Approved test protocol and evaluation record. |
| C-11 | Technically enforce all prohibited uses and verify that the integration cannot send customer messages or perform autonomous account and case actions. | Marcus Holloway | Integration permission review and exclusion test results. |
| C-12 | Establish a rapid integration-disable procedure and confirm who may activate it. | Maya Chen and Marcus Holloway | Approved runbook and successful disablement test. |

Conditions C-01 to C-12 are proposed controls. They are not represented as implemented or operating.

[Sources: GRC-AI-002 Case Packet, pages 6–10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=6).

## 6. Data Handling and Vendor Requirements

The vendor currently states the following:

- Primary application and customer-content storage are hosted in a U.S. cloud region.
- Data is encrypted in transit using TLS 1.2 or later.
- Stored customer content is encrypted at rest using AES-256.
- Enterprise SAML SSO and SCIM are available.
- Enterprise customers can export 180 days of administrative audit activity.
- Submitted content and generated outputs are not used to train shared or underlying foundation models under Enterprise terms.
- Application retention is 90 days by default and configurable to 30 days for Enterprise customers.
- The foundation-model subprocessor may retain API inputs and outputs for up to 30 days.
- Single-case deletion is stated to complete within seven days, subject to backup rotation.
- LumenFerry may use aggregated and de-identified telemetry, but its standard response does not clearly define whether transformed customer-content excerpts may be included.

These are vendor-provided statements. They are not independent verification of control effectiveness.

[Source: GRC-AI-002 Case Packet, pages 6–7](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=6).

**Required position before the pilot:**

- Use Enterprise retention configured to 30 days.
- Obtain clear contractual restrictions on customer-content use.
- Resolve telemetry wording.
- Document foundation-model subprocessor retention and processing.
- Confirm deletion and backup-rotation arrangements.
- Complete applicable customer-contract review.
- Ensure the vendor and its subprocessor obligations are understood and documented.

Zero-retention processing is not available for Resolve. The pilot must not proceed if applicable customer commitments or approved data-handling requirements cannot be met through the proposed terms.

## 7. Human Oversight and Output Quality

Human review is a required part of the proposed workflow.

Every generated summary must remain a draft until an assigned agent has compared it with the original source and selected Accept, Edit, or Reject.

Agents must be trained to identify:

- Unsupported factual statements.
- Omitted troubleshooting steps.
- Changed dates or uncertainty qualifiers.
- Incorrect descriptions of security actions.
- Unsupported recommendations or action items.

The synthetic evaluation demonstrated three unsupported-output cases and five material-omission cases.

There is no calibrated per-summary confidence score in LumenFerry Resolve. The business must therefore rely on source verification, documented review, quality sampling, and escalation rather than an unavailable confidence indicator.

[Sources: GRC-AI-002 Case Packet, pages 7 and 9](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=7).

## 8. Monitoring During the Eight-Week Pilot

The following monitoring programme is recommended.

| Area | Evidence to Review | Review Frequency |
|---|---|---|
| Summary quality | Accuracy, completeness, omissions, unsupported statements | Weekly |
| Human review | Accept/Edit/Reject, review completion, source verification | Weekly |
| Secret prevention | Detection hits, blocked submissions, suspected false negatives | Continuous alerting; weekly review |
| Data minimisation | Submitted fields and excluded-data exceptions | Weekly |
| Access | Pilot membership, local-login status, offboarding | At onboarding/offboarding and periodic review |
| Retention and deletion | Retention configuration and deletion evidence | Before pilot and periodic review |
| Vendor chain | Subprocessor changes and model-provider notices | On every material notice |
| Security | Security and privacy incidents | Immediate escalation |
| Model changes | Product release, model version, regression results | After each material change |
| Scope compliance | Prohibited actions and permission changes | Continuous control; weekly review |

The business owner must approve acceptable quality thresholds before the first customer-data record is processed.

The pilot must not treat the 84% synthetic test result as a guaranteed production accuracy rate.

## 9. Stop and Reassessment Triggers

The following events require immediate escalation and may require suspension of the integration or the pilot:

1. A secret or credential is submitted to LumenFerry or its foundation-model subprocessor.
2. Customer information is processed outside the approved data scope.
3. A material unsupported statement or omission enters a final case note.
4. Human review is bypassed.
5. Required source material is not available for verification.
6. A material security or privacy incident occurs.
7. Retention, deletion, telemetry, or model-training terms are breached.
8. An unapproved subprocessor or model-provider change occurs.
9. A material model or product change causes unacceptable output quality.
10. A prohibited autonomous action becomes available or is performed.
11. The integration cannot be disabled when required.
12. Required customer notice or approval has not been obtained.

Maya Chen, as CISO, is the security escalation point. Lena Ortiz remains accountable for the Customer Success workflow.

[Source: GRC-AI-002 Case Packet, pages 3 and 10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=3).

## 10. Open Items and Required Specialist Review

| Open Item | Required Reviewer | Required Outcome |
|---|---|---|
| Telemetry and possible customer-content excerpts | Hannah Kim | Written privacy and contractual clarification. |
| Customer agreement requirements for subprocessors | Hannah Kim | Determine customer notice or approval requirements. |
| SOC 2 report and security exceptions | Maya Chen | Review report and document relevant findings. |
| Incident-notification wording | Hannah Kim | Review and approve contractual position. |
| SSO, SCIM, local accounts, and integration permissions | Marcus Holloway | Demonstrate the approved identity and access configuration. |
| Vendor and subprocessor review | Noah Grant | Complete procurement and third-party review. |
| Quality acceptance criteria | Lena Ortiz | Approve the output-quality thresholds and review process. |
| Risk record and decision documentation | Aaron Bell | Maintain the inventory, risk assessment, and decision record. |

This memo does not provide legal advice. Legal and Privacy must determine customer-specific contractual and privacy requirements.

## 11. Decision Rationale

Conditional approval is recommended because:

- The proposed business purpose is defined and limited to internal support documentation.
- The pilot has a named business owner and a defined group of 25 users.
- The original ticket and transcript remain available in the proposed workflow.
- Human review and rejection of drafts are part of the proposed design.
- The tested configuration did not send customer messages or take autonomous actions.
- The synthetic evaluation indicates possible productivity value.
- The identified output-quality, data-handling, vendor, and access risks can be addressed through specific pre-pilot conditions and ongoing monitoring.

Approval is not unconditional because:

- The test evidence identifies material omissions and unsupported outputs.
- The test used synthetic information only.
- Credentials and secrets have appeared in historical support records.
- Application and subprocessor retention remain relevant.
- Telemetry wording requires clarification.
- The underlying foundation-model provider is an additional processing dependency.
- The SOC 2 report has not been reviewed.
- SSO, SCIM, access restrictions, and the rapid stop procedure require implementation and testing.

The recommendation is consistent with Avenloft's moderate appetite for controlled pilots and its low tolerance for customer or confidential data entering unapproved services.

[Source: GRC-AI-002 Case Packet, pages 3, 6–10](https://www.lablist.io/downloads/avenloft-ai-use-case-review.pdf#page=3).

## 12. Timeline and Decision Record

The case lists **12 October 2026** as the requested pilot start date. That date has passed. The case packet does not confirm whether the pilot subsequently began.

Before operational reliance on this memo, the organisation would need to confirm the actual service status. This assessment does not claim that the pilot started, was approved, or processed customer data.

| Decision Record Field | Entry |
|---|---|
| Recommended decision | Conditionally Approve |
| Actual authorised decision | Pending |
| Decision authority | Authorised executive / Security Steering Committee |
| Mandatory conditions | C-01 through C-12 |
| Pilot scope | 25 Customer Success agents, eight weeks, internal draft summaries only |
| Customer-data processing permission | Not granted by this memo |
| Review owner | Aaron Bell, Director GRC |
| Business owner | Lena Ortiz, VP Customer Success |
| Reassessment | Before pilot start and after material changes or triggers |

## 13. Final Recommendation

**CONDITIONALLY APPROVE — subject to completion and verification of all mandatory pre-pilot conditions.**

The pilot must remain limited to internal support summarisation and draft case notes. Customer data must not be processed until the identity, secret-handling, retention, telemetry, subprocessor, contractual, assurance, human-review, quality, and shutdown requirements have been satisfied and recorded.

The decision must be revisited if the evidence changes, a material condition cannot be met, or a stop trigger occurs.

---

## 14. Document Status and Disclaimer

| Activity | Status |
|---|---|
| Business purpose and scope reviewed | Complete |
| Vendor and data-handling evidence reviewed | Complete at case-packet level |
| Synthetic test results reviewed | Complete |
| Material risks documented | Complete in working risk assessment |
| Decision recommendation prepared | Proposed |
| Mandatory conditions implemented | Not verified |
| Legal and privacy review | Pending |
| Security and vendor assurance review | Pending |
| Authorised decision | Pending |
| Pilot approval | Not granted by this memo |

This is an independent portfolio simulation using a fictional training case. Avenloft Systems Group, LumenFerry AI, LumenFerry Resolve, all employees, customer records, vendor terms, test results, metrics, and events are fictional.

No real client engagement, AI deployment, management approval, or completed remediation is claimed.