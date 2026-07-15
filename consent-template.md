# Consent Form Template (for Web Security Community Events)

Derived from clinical trial data-privacy practices (see [Clinical-Trial Privacy Comparison Matrix](./docs/trial-privacy-matrix.md)).

---

**Why this matters:** Clinical trials (e.g., NCT07457489 VICTORY, NCT03382951 FLASH) use explicit, tiered consent with clear separation of operational and identity data. We adapt these principles for community workshops.

---

## Event Data Collection Consent

**Event Name:** \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
**Date:** \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_
**Organizer:** Web Security Community Toolkit (zhub9006/web-security-community-toolkit)

### What we collect
- [ ] Name (for name badges & follow-up)
- [ ] Email (for newsletter & resources)
- [ ] Photo consent (for event documentation)
- [ ] Recording consent (for session replay)
- [ ] Emergent contact info (for safety)

### How we protect it (adapted from HIPAA / IRB / GDPR clinical-trial standards)
- [ ] **TLS 1.3** in transit for all online forms
- [ ] **AES-256 encryption** at rest for any stored data
- [ ] **Separated storage**: Identity data (names/emails) stored separately from event analytics
- [ ] **Access logging**: Every read/write is logged with user ID + timestamp
- [ ] **Role-based access**: Only organizers and designated moderators can view full rosters
- [ ] **Auto-delete**: Raw data deleted after **3 years**; aggregated analytics retained optionally

### Your rights (opt-in, never opt-out)
1. **Right to decline** any field — skip it and still attend
2. **Right to access** your data (email organizer)
3. **Right to withdraw consent** — email removal request; deletes within 48 hours
4. **Right to know** who can see your data (listed in this form)
5. **Right to opt out of photos/recordings** — attend without being captured

### Disclosures are NOT protected
*(Modeled on NCT07457489 VICTORY: disclosures consented in this document are not protected under research confidentiality.)*
- Legal requirements may require disclosure of registration name/email
- Venue security may require photo ID at entry
- Incident reports may include attendee information

### Tiered Consent (powered by Clinical-Trial principles)

| Data Type | Required to Attend? | Used For | Retention |
|-----------|---------------------|----------|-----------|
| Name | Yes (badge) | Identification | 3 years |
| Email | No (optional) | Newsletter | Until unsubscribed |
| Photo consent | No (optional) | Event photos/social | 1 year |
| Recording consent | No (optional) | Session replay | 1 year |
| Emergent contact | Yes (safety) | Emergency use only | 3 years |

---

## Organizer Checklist
- [ ] Explain each consent tier verbally at event start
- [ ] Post privacy notice visibly at registration desk
- [ ] Use encrypted forms (TLS 1.3) — no cleartext Google Forms for PII
- [ ] Separate the identity spreadsheet from the attendance analytics sheet
- [ ] Log who accesses the roster (monthly audit)
- [ ] Delete name plates after 3 years; shred immediately after
- [ ] Offer a plain-language summary (not just legal text)

---

*This template is adapted from HIPAA, IRB standards, and GDPR principles observed in clinical trials on ClinicalTrials.gov.*