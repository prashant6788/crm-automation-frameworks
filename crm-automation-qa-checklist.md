# CRM Automation QA Checklist

Use before deploying or materially changing a production CRM workflow.

---

## Workflow Definition

- [ ] Business objective is documented
- [ ] Workflow owner is assigned
- [ ] Trigger is explicit
- [ ] Entry conditions are documented
- [ ] Exclusions are documented
- [ ] Re-entry behavior is defined
- [ ] Stop conditions are defined

## Data

- [ ] Required fields are known
- [ ] Missing-data behavior is tested
- [ ] Field types are correct
- [ ] Controlled values match CRM configuration
- [ ] Phone/email normalization is tested
- [ ] Source of truth is documented

## Duplicate Control

- [ ] Existing contact is tested
- [ ] Existing opportunity is tested
- [ ] Duplicate submission is tested
- [ ] Duplicate webhook/event is tested
- [ ] Idempotency control exists where needed
- [ ] Merge behavior is understood

## Routing

- [ ] Existing ownership is preserved where required
- [ ] Rule precedence is correct
- [ ] Eligible users are validated
- [ ] Round robin/territory behavior is tested
- [ ] No-owner scenario is tested
- [ ] Fallback works
- [ ] Reassignment is tested
- [ ] Ownership changes are traceable

## Pipeline

- [ ] Correct pipeline is selected
- [ ] Correct stage is selected
- [ ] Stage entry requirements are met
- [ ] Stage automation does not create loops
- [ ] Won behavior is tested
- [ ] Lost behavior is tested
- [ ] Lost reason requirement is tested
- [ ] Manual stage changes are handled

## Follow-Up

- [ ] Sequence entry is correct
- [ ] Timing is correct
- [ ] Time zone is correct
- [ ] Reply stops/pauses automation
- [ ] Appointment stops conflicting follow-up
- [ ] Won stops sales follow-up
- [ ] Lost/disqualified behavior is correct
- [ ] Opt-out is respected
- [ ] Collision with human communication is considered

## Appointments

- [ ] Booking sync works
- [ ] Duplicate booking is tested
- [ ] Reschedule cancels obsolete reminders
- [ ] Cancellation stops reminders
- [ ] No-show flow works
- [ ] Rebooking works
- [ ] Attendance is recorded correctly
- [ ] Pipeline update is correct

## Attribution

- [ ] Original source is preserved
- [ ] Latest source updates correctly
- [ ] Campaign fields map correctly
- [ ] Existing contacts are tested
- [ ] New opportunities for existing contacts are tested
- [ ] Unknown source is allowed
- [ ] Revenue mapping is tested if applicable

## Integrations

- [ ] Authentication is valid
- [ ] Secrets are stored securely
- [ ] Request payload is validated
- [ ] Response handling is tested
- [ ] Timeout is tested
- [ ] Retry behavior is tested
- [ ] Rate-limit behavior is understood
- [ ] Partial failure is tested
- [ ] External IDs are stored where required

## Reliability

- [ ] Workflow cannot loop indefinitely
- [ ] Duplicate actions are prevented
- [ ] Concurrent update risk is considered
- [ ] Manual override exists where needed
- [ ] Failed records are discoverable
- [ ] Recovery process is documented
- [ ] Rollback is possible

## Logging

- [ ] Start/completion can be traced
- [ ] Record IDs are logged
- [ ] Errors are logged
- [ ] Retries are logged
- [ ] Routing result is logged
- [ ] Important updates are traceable
- [ ] Logs do not expose secrets

## Security & Privacy

- [ ] Least-necessary permissions are used
- [ ] Sensitive fields are minimized
- [ ] Credentials are not stored in CRM fields
- [ ] Export permissions are appropriate
- [ ] Communication eligibility is respected
- [ ] Applicable retention/deletion requirements are considered

## Reporting

- [ ] Workflow success is measurable
- [ ] Failure rate is measurable
- [ ] Assignment metrics are accurate
- [ ] Pipeline metrics are unaffected by duplicates
- [ ] Attribution model is labeled
- [ ] Test records are excluded where appropriate

---

# Required Test Scenarios

At minimum test:

```text
1. Normal happy path
2. Existing contact
3. Existing opportunity
4. Missing required data
5. Duplicate event
6. Invalid data
7. No eligible owner
8. External API failure
9. Timeout / retry
10. Manual CRM change during workflow
11. Customer reply
12. Appointment booked
13. Opt-out
14. Won / Lost state
15. Workflow re-entry
```

---

# Release Decision

**Workflow:**  
**Version:**  
**Tester:**  
**Date:**  

- [ ] Approved for pilot
- [ ] Approved for production
- [ ] Blocked

Blocking issues:

`________________________________________`

Rollback plan confirmed:

- [ ] Yes
- [ ] No
