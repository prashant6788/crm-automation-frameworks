# CRM Appointment Automation Framework

## Purpose

A framework for connecting appointment booking, CRM records, reminders, rescheduling, cancellations and no-show recovery.

---

## Appointment Lifecycle

```text
Appointment Requested
↓
Booked
↓
Confirmed / Reminder
↓
Attended
   ↘ Cancelled
   ↘ No-Show
↓
Next Sales / Service Action
```

---

## 1. Booking

At booking, confirm:

- Contact identity
- Appointment type
- Date/time
- Time zone
- Assigned calendar/user
- CRM owner
- Related opportunity
- Source where needed

---

## 2. Duplicate Booking

Define behavior if:

- Same contact books twice
- Existing appointment already exists
- Appointment is rescheduled
- Different services are booked

Avoid creating unnecessary duplicate opportunities.

---

## 3. CRM Synchronization

Booking may update:

- Appointment status
- Contact activity
- Opportunity stage
- Owner
- Next action
- Last/next appointment date

Document which system is authoritative for appointment time/status.

---

## 4. Reminders

Reminder design should specify:

- Channel
- Timing
- Appointment details
- Reschedule/cancel path
- Eligibility
- Time zone

Avoid sending stale reminders after cancellation or rescheduling.

---

## 5. Rescheduling

A reschedule should:

1. Update authoritative calendar record
2. Cancel obsolete reminders
3. Create new reminders
4. Preserve appointment history where needed
5. Update CRM
6. Avoid duplicate opportunities

---

## 6. Cancellation

Define:

- Customer cancellation
- Staff cancellation
- Reason if needed
- CRM status
- Opportunity behavior
- Rebooking path
- Notification

Cancellation should not automatically equal lost opportunity.

---

## 7. No-Show

Possible workflow:

```text
Marked No-Show
↓
Update CRM
↓
Notify Owner
↓
Send Eligible Rebooking Communication
↓
Create Follow-Up Task
↓
Track Rebooked / Not Rebooked
```

---

## 8. Attendance

Define how attendance is recorded:

- Manual
- Calendar event
- Meeting integration
- Check-in
- Service system

Do not infer attendance solely because the scheduled time passed.

---

## 9. Pipeline Integration

Possible stage events:

- Booked → Meeting Scheduled
- Attended → Discovery Completed
- No-show → remain active / dedicated state
- Cancelled → review
- Won → stop appointment sales sequence

Use stages that reflect the actual sales process.

---

## 10. Metrics

- Booking rate
- Confirmation rate
- Attendance rate
- Cancellation rate
- No-show rate
- Rebooking rate
- Appointment-to-opportunity conversion
- Appointment-to-win conversion
- Time from lead to appointment

---

## Appointment QA

- [ ] Time zone is correct
- [ ] Duplicate booking behavior exists
- [ ] CRM sync is tested
- [ ] Old reminders stop after reschedule
- [ ] Cancelled appointments do not receive reminders
- [ ] No-show is explicitly recorded
- [ ] Rebooking path works
- [ ] Pipeline updates are correct
- [ ] Attendance is not guessed
- [ ] Communication eligibility is respected
