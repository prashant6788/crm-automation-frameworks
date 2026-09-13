# CRM Automation Implementation Example

> **Illustrative example only.** This is a fictional, sanitized scenario created to demonstrate CRM architecture. It does not represent a specific Touchstone Infotech client, and the example does not claim real-world performance results.

---

## Scenario

A fictional B2B services company receives enquiries through:

- Website forms
- Paid advertising
- Referral forms
- Direct sales entry

The company wants one CRM process for lead capture, ownership, qualification, appointments, pipeline and reporting.

---

## Business Problem

The existing process has:

- Manual lead assignment
- Inconsistent source tracking
- Duplicate contacts
- Follow-up dependent on individual memory
- Opportunities created inconsistently
- Limited pipeline visibility

---

## Desired Outcome

Create a workflow that:

1. Captures enquiries
2. Validates basic data
3. Checks duplicates
4. Preserves source
5. Routes the lead
6. Creates an accountable next action
7. Tracks qualification
8. Creates an opportunity at the correct milestone
9. Connects appointments
10. Records won/lost outcomes
11. Supports reporting

---

# Architecture

```text
Lead Source
↓
Capture
↓
Validation
↓
Duplicate Check
↓
CRM Contact
↓
Ownership
↓
Acknowledgement + Sales Task
↓
Qualification
↓
Opportunity
↓
Appointment / Discovery
↓
Proposal / Decision
↓
Won / Lost
↓
Attribution + Reporting
```

---

# 1. Lead Capture

Example input:

```text
Name: Arjun Mehta
Email: arjun@example.com
Phone: +91-XXXXXXXXXX
Service: CRM Automation
Source: Paid Search
Campaign: crm-demo
```

The values are fictional.

---

# 2. Validation

Rules:

```text
IF no usable email AND no usable phone
→ manual review / reject based on business policy

IF service value is not recognized
→ map to "Other" and flag for review

IF source is missing
→ use "Unknown"
```

The system does not invent missing source or qualification data.

---

# 3. Duplicate Check

Check normalized:

1. Phone
2. Email

If existing contact found:

- Update appropriate latest-source fields
- Preserve original source
- Preserve existing owner where business rules require
- Check for open opportunity

If no contact exists:

- Create contact

---

# 4. Attribution

Contact fields:

```text
Original Source = Paid Search
Original Campaign = crm-demo
Latest Source = Paid Search
Latest Campaign = crm-demo
```

If Arjun returns later through another campaign:

```text
Original Source remains Paid Search
Latest Source may update
```

---

# 5. Routing

Example precedence:

```text
Existing Account Owner
↓
Existing Open Opportunity Owner
↓
Service Specialist
↓
Round Robin
↓
Sales Manager Fallback
```

If no representative is eligible, the record enters a visible fallback queue.

---

# 6. Assignment Actions

On successful assignment:

- Set contact owner
- Create first-response task
- Send internal notification
- Record assignment timestamp
- Send eligible acknowledgement

The acknowledgement does not imply that qualification has been completed.

---

# 7. Qualification

Example fields:

```text
Service = CRM Automation
Company Type = B2B Services
Current CRM = Unknown
Requirement = Lead Management + Follow-Up
Timeline = 1–3 Months
Budget = Not Provided
Qualification Status = In Progress
```

Unknown information remains unknown.

---

# 8. Opportunity Creation

Business rule:

```text
IF requirement is confirmed
AND service fit is established
AND sales engagement exists
THEN create opportunity
```

The business intentionally does not create an opportunity for every raw form submission.

---

# 9. Pipeline

Example:

```text
New Opportunity
↓
Qualified
↓
Discovery Scheduled
↓
Discovery Completed
↓
Proposal
↓
Decision
↓
Won / Lost
```

Activities such as "Email Sent" remain activities rather than pipeline stages.

---

# 10. Appointment

When discovery is booked:

- Create/update appointment
- Update related opportunity to Discovery Scheduled
- Schedule reminders
- Stop incompatible lead-chasing sequence
- Preserve owner

If rescheduled:

- Cancel obsolete reminders
- Create reminders for new time
- Keep same opportunity

If no-show:

- Mark explicit no-show
- Notify owner
- Create rebooking task
- Send eligible rebooking communication

---

# 11. Follow-Up

If no reply:

```text
Assignment
↓
Sales Task
↓
Defined Follow-Up
↓
Defined Follow-Up
↓
Manual Review / Nurture
```

Stop if:

- Reply received
- Appointment booked
- Disqualified
- Won
- Lost
- Opted out
- Owner manually stops sequence

---

# 12. Won

Example business definition:

```text
Payment confirmed
→ Opportunity = Won
```

Actions:

- Record won date/value
- Stop acquisition follow-up
- Trigger onboarding process
- Preserve attribution
- Update customer lifecycle

---

# 13. Lost

Required:

- Lost reason
- Lost date
- Owner

Example reasons:

```text
Timing
Price
Competitor
No Decision
Not Qualified
Unresponsive
```

---

# 14. Failure Paths

### CRM API unavailable

```text
Retry according to policy
↓
If still failed
Log
↓
Alert operations
↓
Preserve payload for recovery
```

### No eligible owner

```text
Fallback Queue
↓
Notify Manager
```

### Duplicate webhook

```text
Idempotency Check
↓
Do Not Duplicate Contact / Opportunity / Task
```

---

# 15. Reporting

Operational:

- Assignment time
- Unassigned leads
- Follow-up completion
- Workflow errors

Funnel:

- Leads
- Qualified
- Opportunities
- Appointments
- Won/lost

Commercial:

- Pipeline value
- Won value
- Source
- Campaign
- Sales cycle

No performance figures are included because this example is illustrative.

---

# 16. QA Cases

Test:

- New contact
- Existing contact
- Existing opportunity
- Missing source
- Missing phone
- Duplicate event
- No eligible owner
- Reply during follow-up
- Appointment reschedule
- Appointment cancellation
- No-show
- Won
- Lost
- API failure
- Manual override

---

# 17. Key Lessons

1. Preserve original acquisition data.
2. Do not create opportunities indiscriminately.
3. Check existing ownership before routing.
4. Use explicit stop conditions.
5. Treat appointments as stateful records.
6. Design fallback paths.
7. Prevent duplicate processing.
8. Keep pipeline stages commercially meaningful.
9. Measure both reliability and business outcomes.
10. Keep humans accountable for judgment and exceptions.

---

## Related Resources

- [CRM Strategy Framework](crm-strategy-framework.md)
- [Lead Lifecycle Framework](lead-lifecycle-framework.md)
- [CRM Lead Routing Framework](crm-lead-routing-framework.md)
- [CRM Workflow Specification Template](crm-workflow-specification-template.md)
- [CRM Automation QA Checklist](crm-automation-qa-checklist.md)
