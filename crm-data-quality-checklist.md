# CRM Data Quality Checklist

Use this checklist before launch and during recurring CRM audits.

---

## Contact Data

- [ ] Required identity fields are defined
- [ ] Email format is validated where appropriate
- [ ] Phone numbers are normalized
- [ ] Country/region values are standardized
- [ ] Test/spam contacts are identifiable
- [ ] Contact type is available where required

## Duplicate Control

- [ ] Duplicate matching rules are documented
- [ ] Email matching is normalized
- [ ] Phone matching is normalized
- [ ] Name alone is not used as a strong duplicate key
- [ ] Merge process is defined
- [ ] Duplicate submissions do not automatically create duplicate opportunities

## Ownership

- [ ] Actionable leads have owners
- [ ] Unassigned records are visible
- [ ] Inactive users cannot continue receiving assignments
- [ ] Reassignment is traceable
- [ ] Existing customer/account ownership is preserved where required

## Lifecycle

- [ ] Lifecycle states use controlled values
- [ ] State definitions are documented
- [ ] Disqualified is distinct from Lost
- [ ] Won definition is consistent
- [ ] Nurture state is defined where used

## Pipeline

- [ ] Opportunities use the correct pipeline
- [ ] Stages use controlled values
- [ ] Required stage data is present
- [ ] Lost reason is captured
- [ ] Opportunity value format is valid
- [ ] Expected close date is used consistently if enabled
- [ ] Stale opportunities can be identified

## Acquisition

- [ ] Original source is preserved
- [ ] Latest source is separate
- [ ] Source taxonomy is standardized
- [ ] Campaign data is stored consistently
- [ ] Unknown attribution is measurable
- [ ] Manual/offline source values are controlled

## Appointments

- [ ] Appointment status is synchronized
- [ ] Reschedules do not create misleading duplicates
- [ ] Cancellations stop obsolete reminders
- [ ] No-shows are explicitly recorded
- [ ] Attendance is not inferred merely from elapsed time

## Activities

- [ ] Meaningful activity definitions are documented
- [ ] Automated activity is distinguishable where necessary
- [ ] Last activity is reliable
- [ ] Next action can be identified

## Integrations

- [ ] Field mappings are documented
- [ ] Source of truth is defined
- [ ] Conflicting writers are controlled
- [ ] Failed syncs are logged
- [ ] Retry behavior is defined
- [ ] Duplicate webhook/event processing is controlled

## Privacy & Security

- [ ] Sensitive data collection is minimized
- [ ] Permissions follow business need
- [ ] Credentials are not stored in CRM fields
- [ ] Export access is controlled
- [ ] Retention requirements are documented
- [ ] Deletion/correction process exists

## Reporting

- [ ] Metric definitions are documented
- [ ] Missing data is not silently excluded
- [ ] Date basis is clear
- [ ] Attribution model is labeled
- [ ] Reports reconcile with underlying records

---

## Suggested Recurring Audit

Review at least:

```text
Duplicates
+
Unassigned Leads
+
Unknown Source
+
Missing Lost Reasons
+
Stale Opportunities
+
Failed Workflows
+
Invalid Contact Data
+
Missing Next Actions
```

The appropriate frequency depends on CRM volume and business risk.
