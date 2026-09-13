# CRM Data Model Framework

## Purpose

A framework for deciding what data a CRM should store, where it belongs, how it is validated and which system is authoritative.

---

## 1. Model Business Entities First

Common entities include:

- Contact
- Company / Account
- Lead
- Opportunity
- Appointment
- Activity
- Product / Service
- Campaign
- Order / Transaction

Do not force every type of information into contact-level custom fields.

---

## 2. Contact Data

Typical fields:

### Identity
- First name
- Last name
- Email
- Phone
- Company
- City / region / country

### Relationship
- Contact type
- Lifecycle status
- Owner
- Customer status

### Acquisition
- Original source
- Latest source
- First campaign
- Latest campaign
- Landing page

### Communication
- Consent / eligibility
- Preferred channel
- Language
- Time zone where relevant

---

## 3. Opportunity Data

Typical opportunity fields:

- Opportunity name
- Contact/account
- Owner
- Pipeline
- Stage
- Value
- Service/product
- Expected close date
- Created date
- Won/lost date
- Lost reason

Opportunity-specific commercial data should usually not overwrite contact-level historical information.

---

## 4. Field Design Rules

Every custom field should answer at least one of these:

- Does it affect a decision?
- Does it drive a workflow?
- Does it support segmentation?
- Is it required for reporting?
- Is it necessary for service delivery?

If not, reconsider whether it belongs in the CRM.

---

## 5. Field Dictionary

Maintain a field dictionary.

| Field | Entity | Type | Allowed Values | Source | Required | Used By |
|---|---|---|---|---|---|---|
| Service Interested In | Contact | Select | Defined list | Form/Sales | Yes | Routing |
| Opportunity Value | Opportunity | Currency | Numeric | Sales | Conditional | Forecast |
| Lost Reason | Opportunity | Select | Defined list | Sales | On Lost | Reporting |

---

## 6. Controlled Values

Prefer controlled values for fields used in:

- Routing
- Reporting
- Workflow conditions
- Segmentation

Example:

Bad:

```text
Google
google ads
Google Ads
PPC Google
Adwords
```

Better:

```text
Paid Search
```

Preserve detailed campaign data separately when needed.

---

## 7. Unknown vs Empty

Define the meaning of blank values.

Do not treat:

```text
Unknown
Not Applicable
Not Asked
Not Provided
```

as the same state unless intentionally designed that way.

---

## 8. Data Validation

Validate:

- Email format
- Phone normalization
- Country/region
- Numeric values
- Dates
- Required selections
- Enumerated values
- Relationships between fields

Validation should not unnecessarily block lead capture.

---

## 9. Duplicate Management

Define duplicate keys and merge policy.

Possible matching inputs:

- Normalized email
- Normalized phone
- External customer ID
- Account/domain

Avoid automatic merges based on weak identifiers such as name alone.

---

## 10. Source of Truth

For each important field define:

```text
Field
↓
Authoritative System
↓
Allowed Writers
↓
Conflict Rule
↓
Audit / History
```

Example:

| Field | Authority |
|---|---|
| CRM owner | CRM |
| Invoice status | Billing |
| Ecommerce order | Commerce platform |
| Appointment time | Calendar |
| Ad campaign metadata | Tracking/CRM |

---

## 11. Historical Data

Some fields should preserve history instead of being overwritten.

Examples:

- Original source
- First conversion date
- Previous owners
- Stage history
- Lost reasons
- Previous opportunities
- Communication events

---

## 12. Sensitive Data

Minimize collection of sensitive information.

Define:

- Business purpose
- Access control
- Retention
- Export permissions
- Deletion process
- Audit requirements

Never store credentials, passwords, API keys or secrets in ordinary CRM fields.

---

## 13. Data Retention

Document:

- What is retained
- For how long
- Why
- Who can delete/export
- Legal/business requirements
- Backup behavior

---

## 14. Data Quality Metrics

Track:

- Duplicate rate
- Missing required data
- Invalid contact data
- Unassigned records
- Unknown source rate
- Opportunities without value
- Lost opportunities without reason
- Stale records

---

## Data Model Checklist

- [ ] Entities are defined
- [ ] Contact and opportunity data are separated
- [ ] Field dictionary exists
- [ ] Controlled values are standardized
- [ ] Blank/unknown meanings are defined
- [ ] Duplicate policy exists
- [ ] Sources of truth are documented
- [ ] Historical fields are preserved
- [ ] Sensitive data is minimized
- [ ] Data quality is measured
