# SOC 2 Type II Report Review

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Review type:** Third-party assurance review  
**Assessment basis:** Fictional Avenloft vendor case packet

## 1. Review objective

This review evaluates the SOC 2 Type II assurance information supplied by CobaltCedar Analytics, Inc. for its SupportLens service.

The purpose is to determine what the supplied report summary supports, identify exceptions and evidence limitations, and establish what Avenloft should validate before making a vendor renewal decision.

This is a review of the evidence described in the fictional case packet. The underlying full SOC 2 report was not provided or independently examined.

## 2. Evidence reviewed

| Attribute | Case information |
|---|---|
| Evidence | SOC 2 Type II report summary |
| Reporting period | July 1, 2025 – June 30, 2026 |
| Report issue date | August 21, 2026 |
| Opinion | Unmodified opinion |
| Control areas described | Logical access, change management, monitoring, incident response, availability and selected data protection |
| Evidence limitation | Summary supplied; full report and detailed testing schedules not provided |

## 3. What the evidence supports

The supplied summary provides evidence that an independent SOC 2 Type II examination was performed for a defined reporting period.

The described examination covered several relevant control areas:

- Logical access management.
- Change management.
- Security monitoring.
- Incident response.
- Availability.
- Selected data protection controls.

The unmodified opinion is a positive assurance indicator within the scope of the examination.

However, it does not establish that every relevant control operated without exception, nor does it automatically demonstrate that every control is suitable for Avenloft's specific use of SupportLens.

## 4. Identified control exception

The case packet identifies an exception involving terminated vendor workforce accounts.

| Attribute | Observation |
|---|---|
| Sample | 25 terminated workforce accounts |
| Exception count | 2 accounts |
| Deactivation times | 36 hours and 44 hours |
| Vendor target | 24 hours |
| Result | Two sampled accounts were disabled later than the stated target |

### Risk significance

Delayed deactivation of terminated workforce accounts can leave access active longer than intended.

Depending on the access privileges involved, this could increase the opportunity for unauthorized access to vendor systems or customer information.

The case packet states that the vendor changed its HR-to-identity workflow in July 2026.

However:

- The workflow change occurred after the SOC 2 reporting period.
- No independent post-change test evidence was supplied.
- The effectiveness of the corrective action therefore remains unverified for this assessment.

The exception should not be treated as resolved solely because the vendor reports that a process change was implemented.

## 5. Customer-side responsibility

The case packet states that customers remain responsible for their own user access and authentication settings.

This distinction matters because the vendor's workforce controls do not replace Avenloft's responsibility to manage its eight SupportLens accounts.

Avenloft should separately review:

- Whether all eight accounts belong to current authorized personnel.
- Whether MFA is enabled for every account.
- Whether export permissions are limited to business need.
- Whether access reviews are formally documented.
- Whether access is removed promptly when a user changes role or leaves.

The current case information states that five of eight Avenloft accounts have TOTP MFA enabled, while three do not.

## 6. Assurance limitations

The supplied summary does not provide enough detail to independently evaluate every control relevant to Avenloft.

The following limitations remain:

1. The full SOC 2 report was not supplied.
2. Detailed control descriptions and test procedures were not available.
3. The complete auditor testing results were not available.
4. The vendor's July 2026 corrective-action workflow change was not independently tested in the supplied evidence.
5. The report's coverage of the specific SupportLens service, infrastructure and relevant subservice organizations requires confirmation.
6. The report period ended June 30, 2026; it does not by itself establish the status of controls after that date.

An unmodified opinion should therefore be considered positive but not conclusive evidence for the renewal decision.

## 7. Required follow-up evidence

Avenloft should request:

| ID | Evidence request | Purpose |
|---|---|---|
| SOC-01 | Full current SOC 2 Type II report under NDA | Review scope, system description, controls and testing |
| SOC-02 | Complementary User Entity Controls (CUECs) | Identify controls Avenloft must operate |
| SOC-03 | Subservice organization and carve-out details | Understand reliance on AWS and other providers |
| SOC-04 | Management response to the two termination-access exceptions | Understand root cause and corrective action |
| SOC-05 | Post-July 2026 test evidence for the revised offboarding workflow | Validate remediation effectiveness |
| SOC-06 | Bridge letter or equivalent period update, if available | Understand material changes since June 30, 2026 |
| SOC-07 | Confirmation of SupportLens service and infrastructure coverage | Confirm the reviewed system matches Avenloft's service |

## 8. Assessment conclusion

**Evidence assessment: Partially supported; follow-up required.**

The unmodified SOC 2 Type II opinion and coverage of relevant security control areas provide useful assurance.

However, the two sampled termination-access exceptions, absence of independent post-remediation testing, and lack of the full report limit the strength of the evidence available to Avenloft.

The SOC 2 summary should not be treated as proof that all vendor risks are adequately controlled.

Avenloft should obtain and review the full report, validate corrective actions, and assess the customer responsibilities identified in the report before relying on it for renewal approval.

## 9. Relationship to the overall vendor assessment

This review contributes to:

- Vendor evidence assessment.
- Workforce logical-access risk analysis.
- Findings and remediation tracking.
- Renewal conditions and decision-making.
- Ongoing vendor monitoring.

The findings should be considered alongside the penetration test review, security incident review, contract review, and Avenloft's own SupportLens account configuration.

---

**Important:** CobaltCedar Analytics, Inc., SupportLens and all case evidence in this portfolio project are fictional training materials. This document does not represent an actual SOC 2 audit or independent vendor examination.
