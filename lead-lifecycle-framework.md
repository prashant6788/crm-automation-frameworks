# Lead Lifecycle Framework

## Purpose

A practical framework for defining how a person or organization moves from initial enquiry through qualification, opportunity, customer outcome and future re-engagement.

---

## Lifecycle Model

```text
New Contact
↓
New Lead
↓
Attempting Contact
↓
Engaged
↓
Qualified / Disqualified
↓
Opportunity
↓
Sales Process
↓
Won / Lost
↓
Customer / Nurture / Re-engagement
```

Your actual lifecycle may differ. The important requirement is that every state has an operational meaning.

---

## 1. Define Lifecycle States

For each state document:

| Item | Definition |
|---|---|
| Entry criteria | What must be true to enter |
| Exit criteria | What causes movement |
| Owner | Who is accountable |
| Required data | Information needed |
| Next action | Expected activity |
| Automation | System actions |
| SLA | Expected timing if applicable |

---

## 2. New Contact vs New Lead

Not every contact should automatically become an active sales lead.

Examples of contacts that may not be active leads:

- Existing customers
- Vendors
- Partners
- Job applicants
- Newsletter subscribers
- Test records
- Spam

Use explicit classification where the CRM contains multiple relationship types.

---

## 3. Lead Creation

At creation, capture the minimum information necessary to:

- Identify the contact
- Preserve acquisition source
- Prevent duplicates
- Route correctly
- Start appropriate follow-up

Do not block legitimate enquiries merely because optional enrichment data is missing.

---

## 4. Contact Attempt

Define what counts as a contact attempt.

Possible events:

- Call
- Email
- WhatsApp/message
- SMS
- Manual outreach
- Automated acknowledgement

Separate automated delivery from meaningful human engagement when reporting.

---

## 5. Engagement

Define engagement using observable events.

Examples:

- Replied
- Answered call
- Submitted additional information
- Booked appointment
- Requested proposal
- Attended consultation

Avoid assuming that an opened email equals genuine sales engagement.

---

## 6. Qualification

Qualification criteria should be documented.

Typical dimensions:

- Need
- Service fit
- Geography
- Budget
- Timeline
- Authority
- Business type
- Eligibility

Missing information should remain unknown rather than being guessed.

---

## 7. Disqualification

Use structured reasons.

Examples:

- Outside service area
- Wrong service
- Insufficient budget
- Duplicate
- Spam
- Student/job enquiry
- Existing customer
- No current requirement

Disqualification is different from losing an opportunity.

---

## 8. Opportunity Creation

Define the event that creates an opportunity.

Possible rules:

- Qualification completed
- Sales conversation established
- Appointment booked
- Proposal requested
- Commercial requirement confirmed

Avoid creating opportunities for every raw contact if doing so makes pipeline reporting meaningless.

---

## 9. Sales Lifecycle

Once an opportunity exists, track commercial progression through a defined pipeline.

Each stage should reflect a meaningful sales milestone rather than communication activity alone.

---

## 10. Won

Define exactly what "Won" means.

Examples:

- Contract signed
- Payment received
- Order confirmed

Choose one definition and use it consistently.

If contract signature and payment are separate milestones, model them separately.

---

## 11. Lost

A lost opportunity should include:

- Lost date
- Lost reason
- Owner
- Last stage
- Relevant notes

Do not use "Lost" simply because a lead has not replied for a few days unless that is a deliberate business rule.

---

## 12. Nurture and Re-engagement

Not-ready prospects may move to nurture rather than lost.

Define:

- Eligibility
- Cadence
- Content
- Duration
- Re-entry trigger
- Opt-out
- Ownership

Re-engagement should not create duplicate opportunities without checking current state.

---

## 13. Customer Lifecycle

Sales lifecycle and customer lifecycle may be different.

Possible post-sale states:

```text
Won
↓
Onboarding
↓
Active Customer
↓
Renewal / Repeat Purchase
↓
Expanded / Renewed / Churned
```

Use separate pipelines or lifecycle fields when this improves clarity.

---

## 14. Lifecycle Automation

Useful automations:

- New-lead acknowledgement
- Assignment
- First-response task
- Qualification reminders
- Appointment workflows
- Inactivity alerts
- Opportunity creation
- Won/lost actions
- Nurture enrollment
- Re-engagement

Every automation should have exit conditions.

---

## 15. Lifecycle Reporting

Track:

- New leads
- Contact rate
- Engagement rate
- Qualification rate
- Opportunity creation rate
- Appointment rate
- Win rate
- Lost reasons
- Stage aging
- Sales cycle
- Re-engagement conversion

Document denominator definitions before comparing rates.

---

## Lifecycle QA Checklist

- [ ] Every state has a definition
- [ ] Entry and exit criteria are documented
- [ ] Owners are defined
- [ ] Qualification is structured
- [ ] Disqualification and lost are separate
- [ ] Opportunity creation is explicit
- [ ] Won definition is consistent
- [ ] Lost reasons are structured
- [ ] Nurture has re-entry rules
- [ ] Automations have stop conditions
- [ ] Reports use the same lifecycle definitions

---

## Related Resources

- [CRM Strategy Framework](crm-strategy-framework.md)
- [CRM Pipeline Design Framework](crm-pipeline-design-framework.md)
- [CRM Follow-Up Framework](crm-follow-up-framework.md)
