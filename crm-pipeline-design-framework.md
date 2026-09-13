# CRM Pipeline Design Framework

## Purpose

A framework for designing sales pipelines that reflect meaningful commercial progress and produce reliable operational reporting.

---

## 1. Pipeline Principle

A pipeline is not a to-do list.

Stages should represent changes in the commercial state of an opportunity.

Example:

```text
New Opportunity
↓
Qualified
↓
Meeting / Discovery
↓
Proposal / Commercial
↓
Decision
↓
Won / Lost
```

Use stages appropriate to the actual sales process.

---

## 2. Stage Definition Template

For every stage define:

- Purpose
- Entry criteria
- Exit criteria
- Required fields
- Owner
- Expected next action
- Maximum expected aging
- Allowed transitions
- Automation
- Reporting meaning

---

## 3. Avoid Excessive Stages

Do not create a new stage for every activity.

Usually poor stage names:

- Called Once
- WhatsApp Sent
- Follow-Up Tomorrow
- Email Sent

These are activities or tasks, not necessarily changes in opportunity state.

---

## 4. Entry and Exit Criteria

Example:

### Qualified

Entry:
- Requirement confirmed
- Service fit established

Exit:
- Discovery/meeting scheduled or opportunity disqualified

Required:
- Service
- Owner
- Qualification status

This makes reporting more consistent across users.

---

## 5. Stage Movement

Decide which movements are:

- Manual
- Automated
- Conditional
- Prohibited

Example:

```text
Appointment Booked
→ move to Meeting Scheduled

Appointment Cancelled
→ do not automatically mark Lost

Payment Received
→ mark Won
```

---

## 6. Backward Movement

Define whether opportunities may move backward.

If allowed, preserve stage history and reason where useful.

Do not destroy historical reporting by simply overwriting every state without timestamps.

---

## 7. Won and Lost

Treat Won and Lost as outcomes, not ordinary intermediate stages.

### Won
Use one consistent business definition.

### Lost
Capture structured reason.

Possible reasons:

- Price
- Competitor
- No decision
- Timing
- Not qualified
- Unresponsive
- Requirement changed

Adapt to the business.

---

## 8. Multiple Pipelines

Use separate pipelines when processes materially differ.

Examples:

- New sales vs renewals
- Different business units
- Recruitment vs sales
- Customer onboarding vs acquisition

Do not create separate pipelines solely for individual salespeople if the underlying process is identical.

---

## 9. Pipeline Aging

Track:

- Time in current stage
- Total opportunity age
- Stale opportunities
- Expected close date
- Last meaningful activity

Use aging thresholds as operational signals, not automatic evidence that an opportunity is lost.

---

## 10. Pipeline Automation

Potential automations:

- Create task on stage entry
- Request missing data
- Notify owner
- Schedule reminder
- Trigger appointment sequence
- Stop previous follow-up
- Alert manager on aging
- Create onboarding process on Won
- Capture reason on Lost

---

## 11. Forecasting

Forecasting may use:

- Opportunity value
- Expected close date
- Stage
- Explicit forecast category
- Probability

Do not present arbitrary stage probabilities as precise predictions unless they are calibrated from reliable historical data.

---

## 12. Pipeline Metrics

- Opportunities created
- Stage conversion
- Win rate
- Loss rate
- Lost reasons
- Stage aging
- Sales cycle
- Pipeline value
- Won value
- Owner performance
- Source-to-opportunity conversion

---

## Pipeline QA

- [ ] Stages represent commercial states
- [ ] Entry/exit criteria exist
- [ ] Required fields are defined
- [ ] Allowed transitions are documented
- [ ] Won has one definition
- [ ] Lost reasons are structured
- [ ] Stage history is available where required
- [ ] Aging is monitored
- [ ] Automations respect manual overrides
- [ ] Reports use documented definitions
