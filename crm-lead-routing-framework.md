# CRM Lead Routing Framework

## Purpose

A practical framework for assigning leads to the right owner while preserving accountability, speed, fairness and recoverability.

---

## Routing Architecture

```text
New Lead
↓
Validate
↓
Check Duplicate / Existing Owner
↓
Apply Eligibility Rules
↓
Apply Routing Rules
↓
Assign Owner
↓
Create Task / Notify
↓
Verify Assignment
↓
Fallback if Failed
```

---

## 1. Preserve Existing Ownership

Before assigning a new owner, check:

- Existing contact owner
- Existing open opportunity
- Active customer relationship
- Account owner
- Territory rules

Avoid routing the same customer to multiple representatives without a deliberate rule.

---

## 2. Routing Inputs

Possible inputs:

- Geography
- Service/product
- Language
- Business segment
- Account
- Lead source
- Existing relationship
- Sales territory
- Team
- Capacity
- Working hours

Only use data reliable enough to support the decision.

---

## 3. Routing Methods

### Fixed Ownership
Specific category → specific owner.

### Round Robin
Distribute eligible leads across a team.

### Territory
Route based on geography/account.

### Skill-Based
Route based on service/language/expertise.

### Capacity-Aware
Consider workload or availability.

### Account-Based
Preserve named account ownership.

---

## 4. Routing Priority

When multiple rules apply, define precedence.

Example:

```text
Existing Customer Owner
↓
Existing Open Opportunity Owner
↓
Named Account Owner
↓
Service Specialist
↓
Territory
↓
Round Robin
↓
Fallback Queue
```

---

## 5. Eligibility

Before including a representative in routing, check relevant conditions:

- Active user
- Correct team
- Available for assignment
- Required skill
- Territory eligibility

Do not rely on informal manual knowledge.

---

## 6. Assignment Verification

After routing, verify:

- Owner field updated
- Task created if required
- Notification delivered/queued
- Opportunity ownership aligned
- Lead did not remain unassigned

Routing success should be observable.

---

## 7. Fallback

Every routing system needs a fallback.

Examples:

- Central queue
- Sales manager
- Operations owner
- Retry
- Manual review task

Never silently discard a lead because no rule matched.

---

## 8. Reassignment

Define reassignment triggers:

- Employee unavailable
- SLA missed
- Wrong territory
- Wrong service
- Existing relationship discovered
- Manager override

Log important ownership changes.

---

## 9. Duplicate Leads

A duplicate submission should not automatically create:

- New contact
- New opportunity
- New owner
- Duplicate follow-up

Define whether the event updates an existing record or creates a new opportunity.

---

## 10. SLA

If response-time SLAs are used, define:

- Start event
- Working-hours behavior
- Pause conditions
- Completion event
- Escalation
- Reporting calculation

---

## 11. Routing Metrics

- Assignment success rate
- Unassigned lead count
- Time to assignment
- Time to first meaningful response
- Reassignment rate
- Fallback rate
- Leads per owner
- Qualification by routing group
- Opportunity conversion by group

Distribution alone does not prove routing quality.

---

## Routing QA Checklist

- [ ] Existing ownership is checked
- [ ] Rule precedence is documented
- [ ] Eligibility is verified
- [ ] Duplicate behavior is defined
- [ ] Assignment is verified
- [ ] Fallback exists
- [ ] Reassignment is controlled
- [ ] SLA definitions are documented
- [ ] Ownership changes are traceable
- [ ] No lead can disappear silently
