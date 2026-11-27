# Project 01 — References and Source Register

**Project ID:** GRC-RISK-001  
**Project:** Cybersecurity Risk Register  
**Organisation:** Avenloft Systems Group (Fictional)  
**Document Owner:** Independent Portfolio Project  
**Last Reference Review:** 27 November 2026

## 1. Purpose

This document records the primary case material and authoritative publications used to develop the Avenloft cybersecurity risk assessment.

It identifies:

- The source of organisation-specific facts.
- The source of the risk assessment methodology.
- Supporting guidance for cybersecurity risk registers.
- Supporting guidance for risk prioritisation and response.
- The purpose for which each source is used.

The Avenloft case packet is the primary source for all fictional company facts, observations, stakeholder statements, risk appetite, and assignment requirements.

NIST publications provide supporting methodology and guidance. They do not establish fictional Avenloft company facts or automatically impose Avenloft's internal risk rules.

---

## 2. Primary Case Source

### REF-01 — Avenloft Cybersecurity Risk Register Case Packet

**Project code:** GRC-RISK-001  
**Publisher / Source:** LabList  
**Document type:** Fictional cybersecurity risk assessment training case

[Download Avenloft Cybersecurity Risk Register Case Packet (PDF)](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf)

**How this source is used**

This is the primary source for the complete assessment.

| Case Packet Pages | Information Used |
|---|---|
| Page 1 | Fictional case notice and assignment context |
| Page 2 | Assignment objective and required deliverables |
| Page 3 | Company profile, business objectives, risk appetite and tolerance |
| Page 4 | Organisation structure, governance roles and reporting cadence |
| Page 5 | Technology environment and security baseline |
| Page 6 | OBS-01 to OBS-04 |
| Page 7 | OBS-05 to OBS-08 |
| Page 8 | OBS-09 to OBS-12 |
| Page 9 | Stakeholder notes and facts analysts should not assume |
| Page 10 | Inherent risk, existing controls, residual risk, likelihood and impact |
| Page 11 | Qualitative risk determination matrix, risk response options and escalation |
| Page 12 | Required risk register fields and executive summary structure |
| Page 13 | Analyst quality expectations and methodology note |

**Important source rule:** Case-specific facts and observations are taken from this packet. Missing information is recorded as requiring validation instead of being invented.

---

## 3. Primary Risk Assessment Method

### REF-02 — NIST SP 800-30 Rev. 1

**Title:** Guide for Conducting Risk Assessments  
**Publisher:** National Institute of Standards and Technology (NIST)  
**Publication date:** September 2012  
**Revision:** 1  
**Relevant section:** Appendix I, Table I-2

[Official NIST Publication Page — SP 800-30 Rev. 1](https://csrc.nist.gov/pubs/sp/800/30/r1/final)

[Official NIST Publication DOI](https://doi.org/10.6028/NIST.SP.800-30r1)

**How this source is used**

- Supports the structured risk assessment approach.
- Provides guidance for assessing likelihood and impact.
- Provides the qualitative risk-level determination matrix referenced by the Avenloft case packet.
- Supports assessment of inherent and residual risk.

**Project application**

Avenloft uses the qualitative matrix in Appendix I, Table I-2, as specified by the case packet.

The qualitative ratings are:

- Very Low
- Low
- Moderate
- High
- Very High

The workbook does not multiply these labels or represent an invented numerical formula as a NIST requirement.

---

## 4. Cybersecurity Risk Management and Enterprise Risk Management

### REF-03 — NIST IR 8286 Rev. 1

**Title:** Integrating Cybersecurity and Enterprise Risk Management (ERM)  
**Publisher:** National Institute of Standards and Technology (NIST)  
**Publication date:** December 2025  
**Revision:** 1

[Official NIST Publication Page — IR 8286 Rev. 1](https://csrc.nist.gov/pubs/ir/8286/r1/final)

[Official NIST Publication DOI](https://doi.org/10.6028/NIST.IR.8286r1)

**How this source is used**

- Connects cybersecurity risk management with enterprise risk management.
- Supports the use of cybersecurity risk registers.
- Helps connect cybersecurity risks to business objectives.
- Supports communication of the organisation's cybersecurity risk posture to leadership.
- Provides context for risk appetite, risk tolerance, and enterprise-level decisions.

**Project application**

Used as supporting guidance for connecting the candidate risk scenarios to Avenloft's business objectives and preparing management-facing reporting.

### REF-04 — NIST IR 8286A Rev. 1

**Title:** Identifying and Estimating Cybersecurity Risk for Enterprise Risk Management  
**Publisher:** National Institute of Standards and Technology (NIST)  
**Publication date:** December 2025  
**Revision:** 1

[Official NIST Publication Page — IR 8286A Rev. 1](https://csrc.nist.gov/pubs/ir/8286/a/r1/final)

[Official NIST Publication DOI](https://doi.org/10.6028/NIST.IR.8286Ar1)

**How this source is used**

- Supports cybersecurity risk identification.
- Provides guidance for documenting risk scenarios.
- Supports likelihood and impact estimation.
- Connects threat events and vulnerabilities to potential enterprise consequences.
- Supports the development of cybersecurity risk registers.

**Project application**

Used as supporting guidance for developing the ten candidate risk scenarios and connecting technical observations to business impact.

---

## 5. Risk Prioritisation and Response

### REF-05 — NIST IR 8286B — Updated 1

**Title:** Prioritizing Cybersecurity Risk for Enterprise Risk Management  
**Publisher:** National Institute of Standards and Technology (NIST)  
**Publication date:** February 2025  
**Update:** Updated 1

[Official NIST Publication Page — IR 8286B Updated 1](https://csrc.nist.gov/pubs/ir/8286/b/upd1/final)

[Official NIST Publication DOI](https://doi.org/10.6028/NIST.IR.8286B-upd1)

**How this source is used**

- Supports prioritisation of cybersecurity risks in the context of enterprise objectives.
- Provides guidance on risk response and treatment.
- Supports adding risk priorities and response information to a cybersecurity risk register.
- Helps explain how management decisions can consider enterprise impact.

**Project application**

Used as supplemental guidance for the Top-Five Residual-Risk Prioritization document.

It does not replace the risk-level matrix specified by the Avenloft case packet.

---

## 6. Source-to-Deliverable Mapping

| Project Document | Primary Source | Supporting Reference |
|---|---|---|
| `company-profile.md` | REF-01, pages 3–5 | REF-03 |
| `observation-map.md` | REF-01, pages 6–9 | REF-03 |
| `risk-criteria.md` | REF-01, pages 10–13 | REF-02, REF-03 |
| `risk-scenario-analysis.md` | REF-01, pages 2 and 6–9 | REF-02, REF-04 |
| `risk-assessment-workings.md` | REF-01, pages 9–11 | REF-02, REF-04 |
| `cybersecurity-risk-register.xlsx` | REF-01, pages 6–12 | REF-02, REF-03, REF-04 |
| `top-five-residual-risks.md` | REF-01, pages 3, 9, 11 and 13 | REF-03, REF-05 |
| `executive-risk-summary.md` | REF-01, pages 3, 4, 11 and 12 | REF-03, REF-05 |

---

## 7. Publication Version Notes

The following versions are used to avoid relying on superseded editions:

| Publication | Version Used | Version Information |
|---|---|---|
| NIST SP 800-30 | Rev. 1 | Final publication dated September 2012 |
| NIST IR 8286 | Rev. 1 | December 2025; supersedes the October 2020 edition |
| NIST IR 8286A | Rev. 1 | December 2025; supersedes the November 2021 edition |
| NIST IR 8286B | Updated 1 | February 2025; supersedes the February 2022 edition |

Official publication histories:

- [NIST IR 8286 Rev. 1](https://csrc.nist.gov/pubs/ir/8286/r1/final).
- [NIST IR 8286A Rev. 1](https://csrc.nist.gov/pubs/ir/8286/a/r1/final).
- [NIST IR 8286B Updated 1](https://csrc.nist.gov/pubs/ir/8286/b/upd1/final).

---

## 8. Source Use and Evidence Integrity

The following rules apply to this project:

1. Avenloft-specific facts must be supported by the supplied case packet.
2. NIST guidance must not be presented as a fictional Avenloft policy or company requirement.
3. A recommended control must not be described as an existing control.
4. A missing document or evidence item must not automatically be described as proof that a control does not exist.
5. An observation must not automatically be treated as a separate risk.
6. A CVSS score must not be presented as the business risk rating.
7. Risk ratings must include analyst reasoning.
8. Material unknowns must be recorded as requiring validation.
9. Proposed treatment actions must not be represented as completed remediation.
10. Fictional organisations, employees, vendors, and events must remain clearly identified as fictional.

## 9. Limitations

This reference register supports an independent portfolio simulation.

It is not a legal opinion, formal audit, certification assessment, or real organisational risk assessment.

The assessment is limited to the evidence included in the supplied fictional case packet and the cited public guidance.

A final risk decision would require confirmation from the relevant risk owners and authorised management.

## 10. Reference Review

**Reference review date:** 27 November 2026

The official NIST publication pages listed above were checked for their publication titles and revision information.

The Avenloft case packet remains the controlling source for the fictional organisation's facts, evidence, risk appetite, and assignment requirements.