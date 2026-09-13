# CRM Reporting Framework

## Purpose

A framework for turning CRM activity into operational, funnel and revenue reporting that teams can trust.

---

## 1. Define Questions Before Dashboards

Examples:

- How many leads arrived?
- Where did they come from?
- How quickly were they assigned?
- How many were contacted?
- How many qualified?
- How many became opportunities?
- How many booked/attended?
- What is pipeline value?
- What was won?
- Why were opportunities lost?

Build reports around decisions, not chart volume.

---

## 2. Metric Dictionary

Every important KPI should define:

- Name
- Formula
- Numerator
- Denominator
- Date basis
- Included statuses
- Exclusions
- Source system
- Owner

Example:

```text
Win Rate =
Won Opportunities /
(Won Opportunities + Lost Opportunities)
```

This is one possible definition; use the business's agreed definition consistently.

---

## 3. Operational Dashboard

Possible metrics:

- New leads
- Unassigned leads
- Assignment time
- Leads awaiting first action
- Overdue tasks
- Workflow errors
- Duplicate records
- Missing required fields
- Stale opportunities

---

## 4. Funnel Dashboard

```text
Lead
↓
Engaged
↓
Qualified
↓
Opportunity
↓
Appointment
↓
Won
```

Track counts and conversion rates between clearly defined stages.

---

## 5. Pipeline Dashboard

Include:

- Open opportunities
- Pipeline value
- Stage distribution
- Aging
- Expected close date
- Owner
- Service/product
- Stale opportunities

---

## 6. Revenue Dashboard

Possible metrics:

- Won revenue
- Revenue by source
- Revenue by campaign
- Revenue by service
- Revenue by owner
- Average deal value
- Sales cycle

Ensure the revenue source is documented.

---

## 7. Attribution Reporting

Label attribution model clearly.

Examples:

- Original source revenue
- Opportunity source revenue
- Latest source revenue

Do not label all of these simply "revenue by source."

---

## 8. Cohorts and Date Logic

Choose the date used for each report:

- Lead created
- Opportunity created
- Appointment date
- Won date
- Revenue date

Mixing date bases can create misleading comparisons.

---

## 9. Owner Reporting

Use owner metrics carefully.

Consider:

- Lead volume
- Lead quality
- Territory
- Assignment method
- Sales cycle
- Existing accounts

Raw win totals may not be directly comparable across unequal portfolios.

---

## 10. Data Quality Dashboard

Track:

- Unknown source
- Missing owner
- Missing lost reason
- Opportunities without value
- Duplicate rate
- Invalid phone/email
- Stale stage
- Missing next action

---

## 11. Reporting Cadence

Possible cadence:

### Daily
Operational exceptions.

### Weekly
Pipeline and activity management.

### Monthly
Funnel, attribution and revenue analysis.

### Quarterly
Trend, process and model review.

---

## 12. Dashboard Design Principles

1. Show decisions, not decoration.
2. Keep definitions visible.
3. Separate leading and lagging indicators.
4. Surface exceptions.
5. Avoid false precision.
6. Make date filters explicit.
7. Label attribution model.
8. Preserve drill-down to records where possible.

---

## Reporting QA

- [ ] Metric dictionary exists
- [ ] Date basis is explicit
- [ ] Funnel definitions match CRM lifecycle
- [ ] Won/lost definitions are consistent
- [ ] Revenue source is known
- [ ] Attribution model is labeled
- [ ] Unknown/missing data is visible
- [ ] Filters are tested
- [ ] Duplicate records do not inflate totals
- [ ] Dashboard values can be reconciled
