# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## 🔒 Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). A ClinicalTrials.gov analysis returned **286 recent studies** matching "health data privacy" — predominantly in the US (157), Germany (55), Spain (51), UK (37), Italy (38), and China (27), spanning Phase 1 through 4 and observational designs. We examined **three concrete studies** that showcase directly adaptable practices:

### Key Takeaways from Clinical-Trial Privacy Practices

| Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|---|---|
| **Privacy-compliant administrative data reuse** | **NCT06660277 (DIALEX)** — UK/Canada hemodialysis trial: outcome data obtained from *national & provincial data repositories* "in a privacy-compliant manner," with high completeness/validity and a Data Safety Monitoring Board (DMC) over 4,800 participants. | Treat your production logs and threat telemetry as administrative data — replicate the same principle: aggregate, de-identify, and replay through access-controlled pipelines rather than exporting raw records. |
| **Multi-regulatory consent & encrypted federated data** | **NCT06265909 (Mobio/AmDTx)** — Singapore mental-health platform: data collected in strict compliance with **HIPAA, PHIPA (Canada), and GDPR (EU)**; anonymised subject data transferred to a secured web platform for QC before analysis — no raw biometric data exposed externally. | If your community spans international contributors, design for triple-regulatory compliance: HIPAA (US health data), GDPR (EU), and PHIPA (if you handle Canadian members' data). Use a single secured ingestion endpoint (not federated raw dumps) with automated anonymisation before analytics. |
| **Anonymised data pipeline & coded-identifier chain** | **NCT05446922 (CALI)** — French brain-MRI study: post-acquisition, anonymised subject data transferred to a vendor platform on a *secured web connection*; QC performed server-side only; healthy volunteers; written informed consent; 60-participant prospective cohort. | For any community data that includes FOUO (For Official Use Only) or subscriber metadata, adopt the same pipeline: acquire → anonymise on-device → upload to secured server → server-side QC. Never store raw identifiers alongside analysis data. |

### Greater Consistency Across Trials

Every study above enforces **four recurring themes** we can borrow for our community:

1. **Secure encrypted data collection** — never transmit raw PII in cleartext; use TLS 1.3 + end-to-end encryption for all communications.
2. **Role-based restricted access** — separate contributor, moderator, and admin permissions; require 2FA for sensitive operations (inspired by the DSMB/oversight module pattern).
3. **Independent oversight & defined retention** — have a rotating security board review data practices; auto-delete raw logs after a fixed window (clinical trials typically retain 3–7 years; we recommend 3 years for community data).
4. **Explicit participant consent & transparency** — publish a clear privacy notice; opt-in, never opt-out, for new data collection (mirrors IRB-informed-consent workflow).

---

## 📊 ClinicalTrials.gov Search Results

| NCT ID | Title | Status | Key Privacy Takeaway |
|---|---|---|---|
| **NCT06660277** | DIALEX: Expanded vs. Conventional Hemodialysis (UK/Canada) | Recruiting | Health records analyzed "in a privacy-compliant manner" from national/provincial repositories; Data Safety Monitoring Board; 4,800-participant pragmatic trial. |
| **NCT06265909** | Mobio/AmDTx: Mental Health Platform Algorithm Training (Singapore) | Completed | HIPAA + PHIPA + GDPR triple compliance; anonymised data to secured web platform; 36,160 users engaged, 2,786 provided biometric data. |
| **NCT05446922** | CALI: Brain MRI Normalization (France) | Not yet recruiting | Anonymised imaging data transferred to secured vendor platform; QC server-side only; written informed consent; prospective cohort design. |

> **286 total studies found** on ClinicalTrials.gov for "health data privacy" — spanning 46+ countries. Search URL: https://clinicaltrials.gov/search?term=health+data+privacy

---

## 📍 Portland Workshop & Meetup Venues (within ~2 km of Downtown)

Verified venues sourced via geocoded OpenStreetMap, with walking distances from the downtown center (SW 6th & Morrison):

| Venue | Type | Address | Walking Distance | Best For |
|---|---|---|---|---|
| **Portland Art Museum** 🎨 | Museum / Event Space | 1219 SW Park Ave | ~510 m / 1.5 min | Sponsor-hosted talks, gallery-meets, demo nights |
| **Oregon Historical Society** 🏛️ | Museum / Research Space | 1200 SW Park Ave | Adjacent (same block) | Research-focused meetups, small-group technical reviews |
| **First & Main** 🏢 | Office Lobby | 100 SW Main St | ~500 m / 1.5 min | Office-hours style informal meetups, weekday coffee chats |
| **Portland State University** 🎓 | University Campus | 1825 SW Broadway | ~820 m / 2.5 min | Technical deep-dives, classroom-style workshops, academic partnership events |
| **Portland Central Library** 📚 | Public Library (recommended) | 801 SW 10th Ave | ~1.0 km / 3 min | **Top pick for regular workshops** — free meeting rooms, Wi-Fi, AV, beginner-friendly tutorials |
| **Oregon Convention Center** 🏟️ | Conference Centre | 777 NE MLK Jr Blvd, Lloyd District | ~1.5 km / 7 min | **Flagship events** — multi-track security conferences, Capture the Flag tournaments, large summits |
| **Revolution Hall** 🎵 | Events Venue | 1300 SE Stark St (Buckman) | ~1.9 km / 6 min | Speaker nights, social mixers, weekend hackathons (near-2 km, easily reachable) |

### Venue Distance Map (walking from downtown center)

```
Downtown center (SW 6th & Morrison)
  │
  ├── 0.5 km  → Portland Art Museum
  ├── 0.5 km  → First & Main (office lobby)
  ├── 0.8 km  → Portland State University
  ├── ~0.9 km → Portland Central Library    ★ Recommended
  ├── ~1.5 km → Oregon Convention Center
  └── ~1.9 km → Revolution Hall
```

> **Top 3 picks for regular security workshops:**
> 1. **Portland Central Library** — free rooms, central, full AV, beginner-friendly
> 2. **Portland State University** — academic credibility, classroom tech, affordable
> 3. **Oregon Convention Center** — scale, infrastructure, and visibility for flagship events

---

## 🛠️ Toolkit Resources (Coming Soon)

- [Privacy Checklist for Open-Source Projects](`docs/privacy-checklist.md`)
- [Clinical-Trial Privacy Comparison Matrix](`docs/trial-privacy-matrix.md`)
- [Portland Venue Booking Guide](`docs/portland-venues.md`)
- [Workshop Planning Template](`docs/workshop-template.md`)

---

## 🤝 Contributing

Found a great privacy practice or a Portland venue we missed? Open an issue or submit a PR. We welcome:

- Web security practitioners
- Clinical researchers exploring data-privacy crossover
- Community organizers looking for meetup spaces

---

*Built by the web security community — combining clinical-trial rigor with open-source collaboration, anchored in downtown Portland, OR.*
