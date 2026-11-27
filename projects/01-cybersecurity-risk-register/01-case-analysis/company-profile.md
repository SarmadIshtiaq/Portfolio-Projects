# Avenloft Systems Group — Company Profile

**Project ID:** GRC-RISK-001  
**Organisation:** Avenloft Systems Group, Inc.  
**Organisation Type:** Fictional U.S.-based B2B software company  
**Primary Service:** Avenloft Relay  
**Assessment Context:** FY2027 Cybersecurity Risk Register  
**Source:** [Avenloft Cybersecurity Risk Register Case Packet — Company Profile, pages 3–5](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3)

## 1. Organisation Overview

Avenloft Systems Group, Inc. is a fictional U.S.-based business-to-business (B2B) software company.

Its flagship Software-as-a-Service (SaaS) platform, **Avenloft Relay**, helps mid-market manufacturers and distributors coordinate:

- Warehouse scheduling.
- Supplier handoffs.
- Inventory workflows.
- Shipment status.

**Source:** [Case Packet — Company Profile, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3)

## 2. Company Information

| Attribute | Case Information |
|---|---|
| Employees | Approximately 640 employees |
| Workforce | Hybrid and remote workforce across the United States |
| Business Customers | 185 |
| Customer User Accounts | Approximately 22,000 |
| Annual Recurring Revenue | Approximately USD 84 million |
| Primary Service | Avenloft Relay, a cloud-hosted logistics and warehouse workflow SaaS platform |
| Operating Model | Cloud-first |
| Production Environment | No customer-facing on-premises production environment |
| Assurance Posture | Current SOC 2 Type II report; next examination period begins in Q4 2026 |

**Source:** [Case Packet — Company Profile, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3)

## 3. Customer Data Profile

Avenloft Relay processes the following customer information:

- Business contact information.
- Warehouse locations.
- Purchase-order identifiers.
- Inventory quantities.
- Shipment schedules.
- Customer support attachments.

The case packet states that Avenloft does not intentionally process payment-card Primary Account Number (PAN) data or Protected Health Information (PHI) in Relay.

These data categories are relevant to the risk assessment because unauthorized disclosure, loss of availability, or inappropriate third-party access may affect customer trust and business operations.

**Source:** [Case Packet — Customer Data and Excluded Data, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3)

## 4. Business Objectives for FY2027

The case packet identifies five business objectives.

| ID | Business Objective | Description |
|---|---|---|
| BO-01 | Protect Customer Trust | Avoid unauthorized disclosure of customer data and preserve contractual security commitments. |
| BO-02 | Maintain Service Reliability | Keep Avenloft Relay available and recover quickly from disruptive events. |
| BO-03 | Win Larger Enterprise Customers | Demonstrate mature risk management, audit readiness, and predictable control operation. |
| BO-04 | Scale Responsibly | Adopt automation and AI where they improve productivity without creating unmanaged customer-data or decision risk. |
| BO-05 | Reduce Friction | Make security reviews, access decisions, and vendor onboarding more consistent as the company grows. |

**Source:** [Case Packet — Business Objectives for FY2027, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3)

## 5. Risk Appetite and Tolerance

Leadership has provided directional risk appetite guidance. These statements should influence treatment recommendations but do not replace the assessment of individual risk scenarios.

| Risk Area | Leadership Direction |
|---|---|
| Customer Data Confidentiality | Low tolerance for unauthorized disclosure or uncontrolled third-party use of customer information. |
| Privileged Access | Low tolerance for weak authentication, stale privileged accounts, or untraceable administrative activity. |
| Production Availability | Low tolerance for outages exceeding four hours during business operations. Recovery capability is business-critical. |
| Critical Vulnerabilities | No acceptance of known critical internet-facing vulnerabilities beyond 30 days without a current written exception and compensating controls. |
| Internal Productivity | Moderate tolerance for short, reversible productivity interruptions that do not affect customers or material financial reporting. |
| Experimentation and AI | Moderate appetite for controlled pilots; low tolerance for customer or confidential data entering unapproved tools. |

**Source:** [Case Packet — Risk Appetite and Tolerance, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3)

These statements will be used as decision context when assessing residual risk and recommending treatment. They will not be treated as automatic risk ratings.

## 6. Organisation and Governance Roles

The following roles are identified in the case packet.

| Person | Role | Responsibility Relevant to This Assessment |
|---|---|---|
| Maya Chen | Chief Information Security Officer (CISO) | Executive owner for the security program and escalation point for High and Very High cyber risks. |
| Aaron Bell | Director, Governance, Risk & Compliance | Owns the cybersecurity risk register, policy governance, assurance coordination, and GRC reporting. |
| Priya Nair | VP, Engineering | Accountable for product engineering, cloud production, software delivery, and remediation of engineering-owned risks. |
| Marcus Holloway | Director, IT & Workplace Technology | Owns workforce identity, endpoints, corporate infrastructure, and administrative access. |
| Elena Ruiz | VP, Finance & Operations | Executive stakeholder for business continuity, financial operations, and enterprise risk reporting. |
| Lena Ortiz | VP, Customer Success | Owns customer support operations and several customer-data workflows. |
| Hannah Kim | General Counsel & Privacy Lead | Advises on contracts, privacy, and data-handling obligations. |
| Noah Grant | Director, Procurement | Owns procurement workflow and coordinates vendor onboarding. |
| Jared Cole | Head of People Operations | Owns employee lifecycle data; employee offboarding integrates with IT, while contractor offboarding does not. |

**Source:** [Case Packet — Organization and Governance Context, page 4](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=4)

Risk ownership in the register should normally be assigned to the person accountable for the affected business or technology outcome. GRC facilitates and monitors the risk; it does not automatically own every risk.

**Source:** [Case Packet — Facts You Should Not Assume, page 9](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=9)

## 7. Governance and Risk Reporting Cadence

Avenloft currently follows these governance arrangements:

1. The Security Steering Committee meets monthly.
2. High and above residual risks are expected to have a named owner and a treatment plan.
3. The GRC team maintains policies, customer assurance responses, the risk register, audit evidence coordination, and third-party security review.
4. Security risks may be accepted by the accountable business owner only within delegated authority.
5. High and Very High residual risks require CISO review.
6. Acceptance of Very High residual risk requires executive leadership approval.
7. The risk register is reviewed quarterly and before major executive planning cycles.

**Source:** [Case Packet — Current Governance Cadence, page 4](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=4)

## 8. Business and Risk Assessment Implications

The company profile provides context for interpreting the security observations.

The following relationships are relevant to the assessment:

| Business Context | Why It Matters to the Risk Assessment |
|---|---|
| Avenloft Relay is a customer-facing SaaS platform. | Availability and security of production services are important to customer operations. |
| The platform handles customer and logistics information. | Confidentiality and appropriate data handling are important business concerns. |
| The company has approximately 640 employees and a hybrid workforce. | Workforce identity, endpoint security, and access governance are relevant to the environment. |
| Avenloft depends on cloud-hosted production services. | Cloud recovery, resilience, and incident response should be considered. |
| The company serves 185 business customers. | Customer trust and contractual security commitments are relevant business objectives. |
| The company wants to expand its enterprise customer base. | Risk management, audit readiness, and predictable control operation support this objective. |
| Leadership permits controlled AI experimentation. | AI use and customer-data handling require governance boundaries. |

These are assessment considerations derived from the company profile and stated business objectives. They are not additional findings or confirmed control failures.

**Sources:** [Case Packet — Company Profile and Business Objectives, page 3](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=3) and [Organization and Governance Context, page 4](https://www.lablist.io/downloads/avenloft-risk-register-case.pdf#page=4).

## 9. Assessment Scope and Limitations

This project assesses cybersecurity risk to the fictional Avenloft Systems Group and its stated business objectives.

The assessment will:

- Use the supplied case packet and its linked authoritative references.
- Separate documented observations from risk scenarios and recommendations.
- Avoid inventing missing company facts or control evidence.
