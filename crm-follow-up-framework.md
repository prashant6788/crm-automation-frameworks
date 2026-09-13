# CRM Follow-Up Framework

## Purpose

A framework for designing structured follow-up that combines automation with clear human ownership and stop conditions.

---

## 1. Define the Follow-Up Objective

Examples:

- Establish first contact
- Complete qualification
- Book appointment
- Obtain proposal decision
- Recover no-show
- Re-engage inactive lead

A sequence should have one primary purpose.

---

## 2. Entry Conditions

Examples:

- New eligible lead
- Assigned owner
- No active customer status
- Communication permitted
- No appointment already booked
- No conflicting sequence

---

## 3. Sequence Design

Document each step:

| Step | Delay | Channel | Owner | Condition | Action |
|---|---|---|---|---|---|
| 1 | Immediate | Internal | System | New lead | Assign + task |
| 2 | Immediate | Message | System | Eligible | Acknowledge |
| 3 | Defined | Call/task | Sales | No reply | Follow up |
| 4 | Defined | Message | System/Sales | Still active | Follow up |

Cadence should reflect business context and applicable communication rules.

---

## 4. Human vs Automated Follow-Up

Automation can:

- Acknowledge
- Remind
- Create tasks
- Send approved communication
- Detect state changes
- Stop sequences

Humans should retain ownership where judgment, negotiation or sensitive communication is required.

---

## 5. Stop Conditions

Critical stop conditions may include:

- Customer replied
- Appointment booked
- Opportunity won
- Opportunity lost
- Disqualified
- Opted out
- Owner manually stopped sequence
- Customer already active
- Record merged/deleted

Do not continue sending messages because a workflow failed to notice the state change.

---

## 6. Collision Prevention

Prevent:

- Two sequences messaging simultaneously
- Salesperson and automation sending contradictory messages
- Follow-up after booking
- Follow-up after opt-out
- Multiple owners contacting the same lead

---

## 7. Time Logic

Define:

- Business hours
- Time zone
- Weekend behavior
- Holiday behavior if relevant
- Minimum delay
- Maximum sequence duration

---

## 8. Reply Handling

When a reply arrives:

```text
Reply
↓
Stop / Pause Automated Sequence
↓
Notify Owner
↓
Create/Update Task
↓
Record Activity
↓
Human or Defined Workflow Continues
```

---

## 9. No Response

No response should not automatically imply lack of interest.

Define what happens after the sequence:

- Nurture
- Manual review
- Close as unresponsive
- Re-engagement later

Use business-specific rules.

---

## 10. Follow-Up Metrics

- First-response time
- Contact rate
- Reply rate
- Appointment rate
- Qualification rate
- Sequence completion
- Opt-out rate
- Human takeover rate
- Opportunity conversion
- Errors/collisions

---

## Follow-Up QA

- [ ] Entry conditions are explicit
- [ ] Owner is defined
- [ ] Cadence is documented
- [ ] Stop conditions are complete
- [ ] Replies pause/stop automation correctly
- [ ] Appointments stop conflicting follow-up
- [ ] Opt-outs are respected
- [ ] Time zones are handled
- [ ] Collision prevention exists
- [ ] Final no-response outcome is defined
