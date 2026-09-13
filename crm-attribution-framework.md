# CRM Attribution Framework

## Purpose

A practical framework for preserving acquisition information from first contact through opportunity and revenue.

Attribution is a measurement model, not perfect proof of causality.

---

## 1. Separate Attribution Concepts

### Original Source
How the relationship was first acquired.

### Latest Source
Most recent known acquisition/engagement source.

### Campaign
Specific campaign metadata.

### Conversion Event
The event that created a lead/opportunity/customer.

### Revenue Attribution
The rule used to associate commercial value with acquisition data.

---

## 2. Preserve Original Source

Original source should normally be immutable after it is established, except through controlled correction.

Do not overwrite it every time a customer returns through another channel.

---

## 3. Track Latest Source Separately

Latest source can update as new meaningful acquisition events occur.

This allows the CRM to answer both:

- Where did this relationship begin?
- What most recently brought the person back?

---

## 4. Recommended Data

Where available and appropriate:

- Original source
- Original medium
- Original campaign
- Original landing page
- Original referrer
- Latest source
- Latest medium
- Latest campaign
- Latest landing page
- UTM parameters
- Ad/click identifiers where supported
- Lead created date
- Opportunity created date
- Won date

---

## 5. Normalize Sources

Create a controlled source taxonomy.

Example:

```text
Paid Search
Paid Social
Organic Search
Organic Social
Referral
Direct
Email
Partner
Offline
Other
Unknown
```

Store detailed platform/campaign values separately.

---

## 6. Contact vs Opportunity Attribution

A returning contact may create a new opportunity from a different campaign.

Consider preserving:

- Contact-level original acquisition
- Opportunity-level acquisition context

This prevents new commercial events from destroying relationship history.

---

## 7. Revenue Mapping

Define:

```text
Revenue Transaction
↓
Customer / Account
↓
Opportunity
↓
Acquisition Fields
↓
Reporting Model
```

Ensure identifiers can connect systems reliably.

---

## 8. Attribution Models

Possible reporting models:

- First touch
- Last touch
- Opportunity creation source
- Campaign-associated
- Multi-touch analysis

Document which model a dashboard uses.

Do not compare numbers from different models as if they represent the same concept.

---

## 9. Unknown Attribution

Unknown is a valid data state.

Track unknown attribution rate and investigate causes such as:

- Missing tracking
- Cross-device journeys
- Offline interactions
- Privacy restrictions
- Manual imports
- Broken integrations

Do not invent a source to make reports look complete.

---

## 10. Offline and Manual Leads

Define source capture for:

- Phone calls
- Walk-ins
- Referrals
- Events
- Partners
- Manual sales entries

Use controlled values.

---

## 11. Attribution QA

Test:

- First visit
- Returning visit
- Multiple campaigns
- Duplicate contact
- New opportunity for existing contact
- Manual lead
- Missing UTMs
- Won revenue sync
- Refund/cancellation if relevant

---

## 12. Metrics

- Leads by source
- Qualified leads by source
- Opportunities by source
- Won revenue by source
- Cost per lead where spend is available
- Cost per opportunity
- Customer acquisition cost where definitions/data support it
- Unknown attribution rate

---

## Attribution Checklist

- [ ] Original and latest source are separate
- [ ] Source taxonomy is controlled
- [ ] Original source is preserved
- [ ] Opportunity attribution is considered
- [ ] Revenue can map to opportunity/customer
- [ ] Reporting model is labeled
- [ ] Unknown source is allowed
- [ ] Manual/offline source capture exists
- [ ] Multi-touch claims are not overstated
