# Contract and Privacy Review

**Project ID:** GRC-TPRM-003  
**Vendor:** CobaltCedar Analytics, Inc.  
**Service:** SupportLens  
**Review type:** Contractual, data protection and privacy review  
**Assessment basis:** Fictional Avenloft vendor case packet

## 1. Review objective

This review evaluates the contractual and privacy-related terms governing Avenloft's use of SupportLens.

The objective is to identify contractual weaknesses, assess data retention and deletion arrangements, review incident notification and subprocessor provisions, and recommend improvements before contract renewal.

This assessment is based on the fictional case packet. The executed contract and complete data processing agreement were not independently examined.

## 2. Contract overview

| Attribute | Case information |
|---|---|
| Vendor | CobaltCedar Analytics, Inc. |
| Service | SupportLens |
| Relationship start | February 2026 |
| Annual spend | $18,600 |
| Contract renewal | November 1, 2026 |
| Service plan | Standard |
| Enterprise alternative | Approximately $24,600 annually |
| Price difference | Approximately $6,000 annually |

The contract includes confidentiality and reasonable safeguards obligations. However, several important security and privacy requirements are not sufficiently specific in the supplied case information.

## 3. Data processing and privacy exposure

Avenloft uploads weekly CSV exports from Salesforce containing:

- Customer company names.
- Business contact names and email addresses.
- Ticket subjects and free-text descriptions.
- Severity and product-area information.
- Timestamps, case owners and resolution codes.

Attachments are excluded. Payment-card data, authentication secrets, source code and direct production database records are not included in the intended data scope.

However, free-text support cases may contain logs, hostnames, identifiers and troubleshooting details.

### Privacy and confidentiality considerations

The data includes identifiable business contact information and potentially sensitive operational details.

Avenloft should therefore ensure that:

- The permitted processing purposes are clearly documented.
- Data collection is limited to what is necessary.
- Users avoid uploading credentials and unnecessary sensitive information.
- Vendor access is restricted to authorized personnel.
- Retention and deletion requirements are contractually defined.
- Subprocessor processing is transparent and controlled.

## 4. Data retention and deletion review

| Area | Current case information | Assessment |
|---|---|---|
| Standard-plan retention | 180 days by default | Longer than necessary may increase exposure |
| Enterprise retention | Shorter configurable retention available | Requires cost and necessity assessment |
| Active data deletion | Begins within 30 days after termination | Deletion is not immediate |
| Backup deletion | Further 35-day backup lifecycle | Data may remain in backups after active deletion |
| Deletion certificate | No sample supplied | Completion cannot be independently verified |

### Risk implications

The 180-day default retention period increases the amount of time Avenloft's support data remains within the vendor environment.

Following termination, active deletion begins within 30 days, while encrypted backups expire through a further 35-day lifecycle.

This creates a potential period during which data remains in vendor-controlled backup systems.

The case packet does not provide a sample deletion certificate or independent evidence demonstrating the complete deletion process.

### Recommended requirements

Avenloft should:

1. Confirm whether a shorter retention period can be configured on the Standard plan.
2. Establish a retention period based on documented business need.
3. Require deletion of active customer data within a clearly defined contractual period.
4. Define backup deletion timelines and exceptions.
5. Require written deletion confirmation after termination.
6. Clarify how legal holds and backup restoration affect deletion obligations.

## 5. Security incident notification

The contract requires notification without undue delay after a confirmed incident affecting customer data.

The vendor's internal target is notification within 72 hours after confirming customer-data impact.

However, the contract does not establish a fixed hour-based notification deadline.

### Assessment

An internal target is not equivalent to a binding contractual obligation.

The absence of a defined deadline may create uncertainty about when Avenloft will receive notification and how quickly it can assess the impact.

### Recommended requirement

Avenloft should negotiate:

- A defined initial notification deadline after the vendor becomes aware of a security incident affecting Avenloft data.
- Prompt updates as material facts become available.
- Cooperation with investigation and containment.
- Access to a post-incident report, where appropriate.
- Preservation of relevant evidence.
- Clear responsibilities for regulatory and customer communications.

The exact contractual deadline should be agreed with Legal and Privacy stakeholders.

## 6. Subprocessor management

The vendor's May 2026 subprocessor list identifies:

- AWS.
- Datadog.
- SendGrid.

The supplied contract information does not establish advance notification or customer objection rights for subprocessor changes.

The vendor also provides a 30-day notice of subprocessor changes under its described service terms, but the case information does not establish a contractual right for Avenloft to object or terminate based on an unacceptable change.

### Assessment

Subprocessors may participate in hosting, monitoring, communications or other service operations.

Avenloft needs sufficient visibility into which organizations process its information and under what safeguards.

The May 2026 list should also be checked for completeness and currency before renewal.

### Recommended requirements

Avenloft should request:

1. A current and complete subprocessor list.
2. The processing purpose and data categories for each subprocessor.
3. Processing locations and relevant transfer arrangements.
4. Advance notice of material subprocessor changes.
5. A reasonable objection process.
6. Contractual confirmation that the vendor remains responsible for its subprocessors.

## 7. Audit and assurance rights

The supplied case information indicates:

- Avenloft may request current security documentation annually.
- No on-site audit right is included.
- No explicit SOC 2 maintenance clause is identified.

The annual documentation request is useful but may not provide sufficient assurance if a material security concern arises between annual reviews.

### Recommended requirements

Avenloft should seek:

- Continued availability of current independent