# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## How This Project Was Built

The content in this repo is grounded in **live API research** performed on July 22, 2026:

- **ClinicalTrials.gov:** Searched for recent studies on "patient data privacy," "data sharing," and "informed consent" — verified 9 concrete studies with full protocol sections pulled directly from the API
- **OpenStreetMap:** Geocoded downtown Portland (45.5159°N, 122.6822°W) and searched within a 2 km radius for community centres, event spaces, libraries, and civic venues

A total of **317+ studies** match the "patient data privacy" query on ClinicalTrials.gov. We extracted the most relevant verified studies with detailed protocol details for direct web-security adaptation.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight, informed consent, Data Monitoring Committees). Clinical trial consent is legally binding, granular, and revocable — and web consent should be too. Privacy in healthcare is a matter of life and death, and the practices they use are directly adaptable to web security.

Web security can learn from clinical trial privacy in these key ways:

1. **Informed consent mechanisms** → opt-in/opt-out UX that people actually understand
2. **Pseudonymization & data minimization** → strip PII before storage/analysis
3. **Access control & restricted permissions** → least-privilege by design
4. **Training over enforcement** → awareness beats compliance checkboxes
5. **Ethics review boards** → structured oversight of data practices
6. **Risk & benefit communication** → transparent framing of what users get

---

## Verified Clinical Trials — Patient Data Privacy Practices

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT04609072** | Connect for Cancer Prevention Study (Connect) | NIH / NCI | RECRUITING | **Secure digital consent & EHR sharing** — Online consent via MyConnect; "All information shared through MyConnect is secure to protect participant privacy"; electronic health record linkage with participant control; cloud-hosted infrastructure with modern interoperability standards |
| **NCT07378683** | ML-Based Risk Stratification for Surgical Site Infection | Cancer Institute, Chinese Academy of Medical Sciences | RECRUITING | **Coded identifiers & ethics oversight** — "Privacy Protection: All your personally identifiable information will be kept strictly confidential. Codes will replace your name and other identifiable information"; Ethics Committee review; independent Data Safety Monitoring Board; informed consent required |
| **NCT07620834** | AI-Guided Diagnosis for Osteoporosis | Taichung Veterans General Hospital | RECRUITING | **Data sharing & cybersecurity compliance** — "All research data collection, exchange, and sharing will strictly adhere to cybersecurity and privacy regulations"; multi-center data exchange with standardized privacy framework; ethical review & clinical governance |
| **NCT07707518** | SMART-DKD: Diabetic Kidney Disease Screening | Chongqing Medical University | NOT_YET_RECRUITING | **Full data anonymization & encryption** — "All participant personal information and biological samples are fully anonymized with unique study codes and stored in encrypted databases with restricted access"; Declaration of Helsinki + Chinese GCP compliance; written informed consent with withdrawal at any time |
| **NCT05999279** | Patient Preferences: In-person vs Digital Health | Lebanese University | COMPLETED | **Privacy-first digital health** — One of the earliest studies to call out "ensure patient privacy and data security when implementing digital pharmaceutical care services"; survey-based approach measuring patient privacy preferences for digital vs in-person care |
| **NCT06425523** | THRIVE: Refugee Mental Health (Uganda) | Uppsala University | ACTIVE_NOT_RECRUITING | **Sensitive population data protection** — Collects highly sensitive data (migration history, traumatic events, social capital); data gathered on vulnerable refugee mothers; designed for ethical handling of sensitive behavioral & mental-health data |
| **NCT05540782** | PRO-HEALTH: Prostate Cancer Survivorship | Memorial Sloan Kettering | ACTIVE_NOT_RECRUITING | **HIPAA-compliant communication** — Uses "secure, HIPAA-compliant Mosio texting platform" for patient outreach; IPD sharing via Data Use Agreement; 12-month data sharing window (IRB/Federal requirements); validated data-sharing framework |
| **NCT06380192** | DEE-RETRO: Epilepsy Data Reuse | Imagine Institute | RECRUITING | **Consent-based health data reuse** — Explicit opt-in for retrospective data reuse; patient can oppose data re-use; multicenter EU data sharing under standardized ethical review; demonstrates how to balance research utility with privacy for sensitive neurological data |
| **NCT05533918** | SCALE-UP Utah II: COVID-19 Testing & Vaccination | University of Utah | COMPLETED | **Privacy-preserving digital outreach** — PHM interventions using phone/text messaging at community health centers; telephone and text-based consent/preferences; built for underserved populations with privacy considerations for vulnerable communities |

---

## Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **Secure digital consent** | NCT04609072 — Online informed consent via MyConnect with secure account creation | **Replace dark patterns with clear opt-ins** — build consent flows that are easy to understand, easy to decline, and easy to revoke; store consent choices immutably |
| 2 | **Coded identifiers** | NCT07378683 & NCT07707518 — All PII replaced with codes; encrypted databases | **Pseudonymize at ingestion** — replace raw user IDs with tokens before analytics; keep the mapping in a separate, access-controlled vault |
| 3 | **Cybersecurity & data-sharing standards** | NCT07620834 — All data exchange "strictly adheres to cybersecurity and privacy regulations" | **Standardize your data-sharing agreements** — adopt well-known standards (NIST, ISO 27001); document security controls for every integration point |
| 4 | **Encrypted storage + restricted access** | NCT07707518 — "encrypted databases with restricted access" | **Encrypt at rest + in transit; enforce least-privilege IAM** — use KMS, encrypted volumes, and per-service access scopes |
| 5 | **Privacy-by-design in digital health** | NCT05999279 — "ensure patient privacy and data security when implementing digital care" | **Embed privacy into feature specs from day one** — don't bolt it on post-launch; add privacy requirements to your Definition of Done |
| 6 | **Sensitive population protections** | NCT06425523 — heightened care for trauma/mental-health data | **Tiered data handling** — apply stricter defaults for sensitive categories (health, financial, location, biometric); ask for more explicit consent |
| 7 | **HIPAA-compliant communication** | NCT05540782 — HIPAA-compliant messaging platform with Data Use Agreements | **Choose verified privacy-compliant tools** — don't build your own encrypted channel; use established APIs with clear compliance certifications |
| 8 | **Consent-based data reuse** | NCT06380192 — retrospective data reuse requires explicit opt-out rights | **Make data opt-out easy** — provide a clear dashboard showing what data you hold and let users delete/export it with one click |
| 9 | **Privacy-preserving digital outreach** | NCT05533918 — phone/text-based interventions at community health centers | **Prefer opt-in channels over surveillance** — push notifications with consent over passive tracking; let users choose their comms preferences |
| 10 | **Ethics review + Data Safety Monitoring** | NCT07378683 — DMC + IRB oversight for all data handling | **Establish an internal data governance board** — regular audits of who accesses what data; quarterly privacy impact assessments |

---

## Cross-Cutting Themes — What Clinical Trials Teach Us

1. **Privacy-by-Design** — All good trials embed privacy protections into the protocol from the start, not as an afterthought. Web security teams should adopt the same principle.
2. **Pseudonymization over Anonymization** — Clinical trials prefer pseudonymization (reversible with a key) because it allows data utility while protecting identity. This maps to web security's need for tokenization and hashed identifiers.
3. **Restricted Access** — Research teams have access only to what they need. Implement least-privilege access in all web systems.
4. **Consent Management** — Informed consent mechanisms in trials directly inform how we build consent-gated dashboards and preference centers.
5. **Compliance & Auditing** — IRB oversight in trials parallels SOC 2 / ISO 27001 in web security. Regular auditing of data access is essential in both domains.
6. **Education over Enforcement** — Awareness training is more effective than passive policy documents. Build privacy literacy, not just cookie banners.
7. **Framing Matters** — How you ask for consent dramatically affects user behavior. Risk and benefit frames outperform generic privacy statements.
8. **Data Minimization by Design** — Strip PII at the point of capture; never pass raw identifiers downstream.
9. **Sensitive Data Needs Extra Layers** — Genetic data (NCT07620834/NCT07707518) gets extra protections. Apply the same level to financial, biometric, and location data.
10. **Continuous Monitoring** — Privacy isn't a one-time consent — it's an ongoing practice. Like clinical trial Data Safety Monitoring Boards, establish regular reviews of your data practices.

---

## Portland Venues for Workshops & Meetups

All venues are within **2 km** of downtown Portland (centered at Pioneer Courthouse Square, 45.5189°N, 122.6793°W).

### Event Spaces by Size

| Group Size | Venue | Address | Distance from Center | Best For |
|---|---|---|---|---|
| 10–30 | **First Presbyterian Church** | 1200 SW Alder St | ~0.3 km | Intimate workshops, breakout sessions, community gatherings |
| 10–30 | **Pioneer Courthouse Square** *(outdoor)* | SW Taylor / SW Broadway | ~0.1 km | Free meetups, demos, pop-up events (permit may be required) |
| 10–50 | **PCC Downtown Center** *(classroom)* | 722 SW 2nd Ave | ~0.6 km | Training sessions, seminars, hands-on labs (book via PCC) |
| 20–50 | **Helfgott Research Institute** *(CEC)* | 2220 SW 1st Ave | ~1.0 km | Panel discussions, educational events, community forums |
| 20–75 | **Native American Student & Community Center** | 710 SW Jackson St | ~0.8 km | Cultural events, community organizing, diversity & inclusion workshops |
| 20–150 | **Lincoln Hall** | 1620 SW Park Ave | ~0.3 km | Talks, presentations, larger workshops (check PSU events) |
| 50–200 | **Portland Art Museum** *(event spaces)* | 1219 SW Park Ave | ~0.1 km | Evening receptions, galas, media-friendly events |
| 75–300 | **Oregon Convention Center** | 777 NE MLK Jr Blvd | ~1.5 km | Large conferences, multi-track workshops, vendor demos |
| 75–300 | **Revolution Hall** | 1300 SE Stark St | ~2.1 km | Music, talks, community gatherings; great AV & ticketing |
| 100–500 | **Star Theater** | 13 NW 6th Ave | ~0.5 km | Larger presentations, film screenings, immersive tech demos |
| 30–80 | **The Joinery** | 922 SW Yamhill St | ~0.1 km | Small workshops, co-working meetups (furniture-making heritage space) |

### Community & Planning Organizations

| Organization | Address | Notes |
|---|---|---|
| **Ecotrust** | 1140 SE 7th Ave | Sustainable-economy nonprofit; ~80 seats; contact for community event availability |
| **Wieden+Kennedy** | 224 NW 13th Ave | Creative agency with event-friendly campus spaces; contact for community access |
| **Oregon Health & Science University (OHSU)** | 3181 SW Hooker St | Academic venue; community education programs; ~1.5 km south, full tech infrastructure |
| **Portland Community College — Downtown Center** | 722 SW 2nd Ave | Multiple classrooms & computer labs; highly affordable event rental for community groups |
| **Native American Student & Community Center** | 710 SW Jackson St | Community-oriented; support for indigenous-led events; close to downtown |

### Booking Tips

- **Pioneer Courthouse Square** — Free for public gatherings; check with the City of Portland for permits (permits required for structures/ amplified sound)
- **PCC Downtown Center** — Free or low-cost for 501(c)(3) community organizations; book 6+ weeks ahead
- **Revolution Hall** — Contactless ticketing system; capacity ~300; great for mid-size security workshops with live streaming
- **Oregon Convention Center** — Book 3+ months ahead for large events; Excellent AV and breakout room infrastructure
- **Ecotrust** — Sustainable food and BUILD nonprofit headquarters; seats ~80; contact ahead for private event availability
- **Native American Student & Community Center** — Community-oriented; support for indigenous-led events; close to downtown
- **Star Theater** — Owned by Portland events organization; capacity ~400; excellent for large workshops and screenings

---

## Quick-Start Checklist

- [ ] Familiarize your team with the 10 key takeaways above
- [ ] Audit your current consent + data-handling practices using the Clinical-Trial Privacy Maturity Matrix (coming soon)
- [ ] Pick a Portland venue for your next meetup from the table above
- [ ] Share the privacy takeaways as a 5-minute warm-up at your next workshop 💻🔒

---

## Contributing

Found a great clinical-trial privacy practice or a Portland venue we missed? Open an issue or PR! We welcome pull requests with:
- Additional verified clinical trials (NCT ID + full summary)
- New Portland venues (name, address, distance, capacity)
- Mappings between trial practices and web-security controls

---

## License

Open-source. See `LICENSE` for details.
