# CRM Strategy Framework

## Purpose

A practical framework for designing a CRM as an operational system for managing customer relationships, sales processes, ownership, follow-up, pipeline visibility and revenue measurement.

A CRM should not be treated as a digital address book. It should define how customer information moves through the business.

---

## 1. Start With the Business Process

Before configuring software, document:

- How enquiries enter the business
- What information is captured
- Who owns each lead
- How leads are qualified
- When an opportunity is created
- How follow-up happens
- How appointments are managed
- What causes pipeline stages to change
- How won and lost outcomes are recorded
- Which reports management needs

The CRM should reflect a deliberate operating process rather than compensate for an undefined one.

---

## 2. Define the CRM's Role

Identify which responsibilities belong to the CRM.

Typical responsibilities include:

- Contact system of record
- Lead source tracking
- Ownership and assignment
- Qualification data
- Opportunity management
- Follow-up tasks
- Appointment history
- Communication history
- Pipeline status
- Revenue attribution
- Reporting

Document systems that remain authoritative for other information such as accounting, ecommerce orders, product usage or support tickets.

---

## 3. Core CRM Architecture

```text
Lead Sources
    ↓
Capture + Validation
    ↓
Contact Record
    ↓
Ownership + Qualification
    ↓
Opportunity
    ↓
Pipeline
    ↓
Follow-Up / Appointment / Sales Activity
    ↓
Won / Lost
    ↓
Revenue + Attribution
    ↓
Reporting
```

---

## 4. Separate Contacts, Leads and Opportunities

These concepts should not be used interchangeably.

### Contact
A person or organization represented in the CRM.

### Lead
A contact currently being evaluated or worked as a potential commercial relationship.

### Opportunity
A defined potential transaction or sales outcome.

One contact may have multiple opportunities over time.

---

## 5. Establish a Source of Truth

For every important field, define:

| Data | Source of Truth | Update Owner |
|---|---|---|
| Contact identity | CRM | Sales / Operations |
| Lead source | Tracking + CRM | System |
| Owner | CRM | Routing logic / Manager |
| Qualification | CRM | Sales |
| Pipeline stage | CRM | Sales / Workflow |
| Appointment status | Calendar / CRM | System |
| Revenue | Billing / CRM | Finance / Integration |

Avoid allowing multiple systems to independently overwrite the same business-critical value without defined precedence.

---

## 6. Design Around Lifecycle

The CRM should answer:

1. Where did this contact come from?
2. Who owns the relationship?
3. What is the current status?
4. What should happen next?
5. When should it happen?
6. What happened previously?
7. What commercial outcome resulted?

If the CRM cannot answer these reliably, additional automation will usually amplify the underlying problem.

---

## 7. Ownership

Every actionable lead or opportunity should have an accountable owner.

Define:

- Assignment rules
- Team or territory routing
- Capacity rules if required
- Reassignment rules
- Unassigned fallback queue
- Leave/absence handling
- Escalation
- Ownership transfer logging

Avoid silent ownership changes.

---

## 8. Pipeline Design

Pipeline stages should represent meaningful changes in the sales process.

Good stages have:

- Clear entry criteria
- Clear exit criteria
- Defined owner
- Expected next action
- Allowed transitions
- Required information
- Aging expectations where useful

Avoid stages based only on vague labels such as "Interested" without operational definitions.

---

## 9. Automation Principles

Automate stable, repeatable rules first.

Good candidates:

- Lead acknowledgement
- Assignment
- Task creation
- Reminder scheduling
- Stage-based actions
- Appointment reminders
- No-show recovery
- Inactivity alerts
- Lost-stage cleanup
- Internal notifications

Do not automate a process that the team cannot explain consistently.

---

## 10. Follow-Up Governance

Define:

- Who follows up
- Which channels are permitted
- Cadence
- Business hours
- Stop conditions
- Reply handling
- Appointment handling
- Opt-out handling
- Maximum sequence duration
- Ownership during automation

Automated communication should stop or adapt when the customer responds or the business state changes.

---

## 11. Data Model

Use fields only when they support a decision, workflow, segmentation or report.

Common groups:

### Identity
- Name
- Email
- Phone
- Company
- Location

### Acquisition
- Original source
- Latest source
- Campaign
- Landing page
- Referrer

### Qualification
- Service
- Budget
- Timeline
- Need
- Location
- Fit status

### Sales
- Owner
- Opportunity
- Pipeline
- Stage
- Value
- Expected close date
- Lost reason

### Operational
- Last activity
- Next action
- Appointment status
- Consent / communication eligibility

---

## 12. Integration Architecture

Document every integration:

```text
System A
  ↓ event
Integration / Workflow
  ↓ validation
CRM
  ↓ business rule
System B
```

For each integration define:

- Trigger
- Authentication
- Payload
- Field mapping
- Duplicate behavior
- Retry behavior
- Error logging
- Ownership
- Recovery process

---

## 13. Reliability Controls

Production CRM automation should consider:

- Duplicate events
- Duplicate contacts
- Missing fields
- Invalid values
- API failures
- Rate limits
- Time zones
- Concurrent updates
- Re-entry into workflows
- Infinite loops
- Partial failures
- Manual overrides

Use idempotent design where repeated processing could otherwise create duplicate records, tasks, opportunities or messages.

---

## 14. Measurement

Track both operational and commercial metrics.

### Operational
- Assignment success
- Unassigned leads
- Duplicate rate
- Missing required data
- Workflow failures
- Response time
- Follow-up completion

### Funnel
- Leads
- Qualified leads
- Opportunities
- Appointments
- Won
- Lost
- Stage conversion
- Pipeline aging

### Commercial
- Pipeline value
- Won revenue
- Revenue by source
- Revenue by campaign
- Revenue by owner
- Sales cycle

Metrics should use documented definitions.

---

## 15. Governance

Assign ownership for:

- CRM configuration
- Field definitions
- Pipeline definitions
- Workflow changes
- Integrations
- User permissions
- Reporting
- Data quality
- Incident response

Maintain change history for important production workflows.

---

## 16. Implementation Sequence

```text
Business Process
↓
Lifecycle
↓
Data Model
↓
Pipeline
↓
Ownership
↓
Routing
↓
Follow-Up
↓
Appointments
↓
Integrations
↓
Attribution
↓
Reporting
↓
QA
↓
Deployment
↓
Monitoring
```

---

## Core Principles

1. Process before platform.
2. One accountable source of truth.
3. Clear ownership.
4. Meaningful lifecycle states.
5. Automate rules, not ambiguity.
6. Keep data models purposeful.
7. Design failure paths before launch.
8. Preserve attribution.
9. Measure business outcomes.
10. Make workflows understandable to humans.

---

## Related Resources

- [Lead Lifecycle Framework](lead-lifecycle-framework.md)
- [CRM Data Model Framework](crm-data-model-framework.md)
- [CRM Pipeline Design Framework](crm-pipeline-design-framework.md)
- [CRM Lead Routing Framework](crm-lead-routing-framework.md)
- [CRM Automation QA Checklist](crm-automation-qa-checklist.md)

---

## Important Note

This framework is vendor-neutral. CRM capabilities, APIs, messaging requirements and platform behavior change over time. Validate implementation decisions against current vendor documentation, applicable regulations, security requirements and real-world testing.
