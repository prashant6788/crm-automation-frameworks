# CRM Workflow Specification Template

Use this template to document a CRM workflow before production implementation.

---

# 1. Workflow Metadata

**Workflow name:**  
**Version:**  
**Owner:**  
**Status:** Draft / Testing / Production / Retired  
**Last updated:**  
**Related process:**  

---

# 2. Objective

Business problem:

`________________________________________`

Expected outcome:

`________________________________________`

Out of scope:

`________________________________________`

---

# 3. Trigger

**Trigger event:**  
`________________________________________`

**Trigger source:**  
`________________________________________`

**Re-entry allowed?** Yes / No / Conditional

**Frequency:**  
`________________________________________`

---

# 4. Entry Conditions

```text
Condition 1:
Condition 2:
Condition 3:
```

Exclusions:

```text
1.
2.
3.
```

---

# 5. Systems

| System | Role | Source of Truth? |
|---|---|---|
| CRM | | |
| | | |
| | | |

---

# 6. Required Data

| Field | Entity | Source | Required | Validation |
|---|---|---|---|---|
| | | | | |
| | | | | |

Missing-data behavior:

`________________________________________`

---

# 7. Duplicate / Idempotency Logic

Duplicate key:

`________________________________________`

If the same event is processed twice:

`________________________________________`

If contact already exists:

`________________________________________`

If opportunity already exists:

`________________________________________`

---

# 8. Workflow Steps

| # | Action | System | Condition | Success Result | Failure Result |
|---:|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |

---

# 9. Business Rules

```text
IF ______________________
THEN ____________________

IF ______________________
THEN ____________________

ELSE ____________________
```

Rule precedence:

```text
1.
2.
3.
```

---

# 10. Ownership / Routing

Existing owner check:

`________________________________________`

Assignment method:

`________________________________________`

Fallback owner/queue:

`________________________________________`

Reassignment rules:

`________________________________________`

---

# 11. CRM Updates

### Contact

```text
Field → Value / Logic
```

### Opportunity

```text
Field → Value / Logic
```

### Pipeline

```text
Pipeline:
Stage:
Movement rule:
```

### Tasks

```text
Task:
Owner:
Due date logic:
```

---

# 12. Communication

Channel:

`________________________________________`

Eligibility:

`________________________________________`

Timing:

`________________________________________`

Stop conditions:

`________________________________________`

Reply behavior:

`________________________________________`

---

# 13. Appointment Logic

If applicable:

- Calendar:
- Appointment type:
- Time zone:
- Booking behavior:
- Reschedule behavior:
- Cancellation behavior:
- No-show behavior:

---

# 14. Error Handling

| Failure | Retry? | Fallback | Alert |
|---|---|---|---|
| CRM API | | | |
| Missing data | | | |
| Routing failure | | | |
| Communication failure | | | |

---

# 15. Loop Prevention

How is repeated workflow entry prevented?

`________________________________________`

How are automation-to-automation loops prevented?

`________________________________________`

---

# 16. Logging

Log:

- [ ] Workflow start
- [ ] Workflow completion
- [ ] Record IDs
- [ ] Routing result
- [ ] Important field changes
- [ ] External API result
- [ ] Error
- [ ] Retry
- [ ] Manual override

Log location:

`________________________________________`

---

# 17. Monitoring

Success signal:

`________________________________________`

Failure signal:

`________________________________________`

Alert owner:

`________________________________________`

Review cadence:

`________________________________________`

---

# 18. Security and Privacy

Permissions required:

`________________________________________`

Sensitive data:

`________________________________________`

Secrets storage:

`________________________________________`

Retention considerations:

`________________________________________`

---

# 19. Test Cases

| Test | Expected Result | Status |
|---|---|---|
| Normal record | | |
| Existing contact | | |
| Existing opportunity | | |
| Missing field | | |
| Duplicate event | | |
| No eligible owner | | |
| API timeout | | |
| Manual override | | |

---

# 20. Deployment

Pilot group:

`________________________________________`

Deployment date:

`________________________________________`

Rollback method:

`________________________________________`

Post-launch owner:

`________________________________________`

---

# 21. Measurement

Baseline:

`________________________________________`

Primary KPI:

`________________________________________`

Reliability KPI:

`________________________________________`

Review date:

`________________________________________`

---

# 22. Change Log

| Version | Date | Change | Owner |
|---|---|---|---|
| | | | |
