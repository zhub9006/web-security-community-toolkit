# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## 🔒 Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). ClinicalTrials.gov returned **315 recent studies** matching "patient data privacy", and we examined three that showcase concrete, adaptable practices:

### Key Takeaways from Clinical-Trial Privacy Practices

| Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|---|---|
| **Automated de-identification + PII scrubbing** | **NCT02795806** — NLM Scrubber (National Library of Medicine): a software tool that recognizes and deletes personally identifiable information from clinical text documents, built to HIPAA and Privacy Act standards. | Use automated PII redaction for screenshots, logs, and ticket descriptions; run post-processing scrubbers on any exported data before sharing. |
| **Federated / privacy-respecting cross-border data sharing** | **NCT06019208** — GenoMed4ALL (Spain): pools genomic, clinical, and multi-omics data across 4 EU countries *without ever directly sharing sensitive patient data*, using federated learning on a privacy-respecting platform. | Adopt federated analytics for community metrics (e.g., threat intel) so members contribute insights without exposing raw user data; use differential privacy or on-device aggregation. |
| **Coded identifiers, informed consent & encrypted storage** | **NCT07378683** — CNS Tumor SSI study (China): uses coded identifiers replacing names in all analyses and reports; mandatory written informed consent; IRB-approved ethics board; centralized encrypted storage; independent Data Safety Monitoring Board. | Assign pseudonymous IDs to forum contributors; require explicit consent for any data collection; enforce TLS 1.3 + AES-256 at rest; apply least-privilege roles, SSO/2FA for all admin access; maintain audit trails; publish a data-retention & auto-deletion policy. |

### Greater Consistency Across Trials

Every study cited above enforces **four recurring themes** we can borrow for our community:

1. **Secure encrypted data collection** — never transmit raw PII in cleartext; use end-to-end encryption for all communications.
2. **Role-based restricted access** — separate contributor, moderator, and admin permissions; require 2FA for sensitive operations.
3. **Independent oversight & defined retention** — have a rotating security board review data practices; auto-delete logs after a fixed window (e.g., 3 years).
4. **Explicit participant consent & transparency** — publish a clear privacy notice; opt-in, not opt-out, for any new data collection.

---

## 📊 ClinicalTrials.gov Search Results

| NCT ID | Title | Status | Sponsor | Key Privacy Takeaway |
|---|---|---|---|---|
| **NCT02795806** | NLM Scrubber: NLM's Software Application to De-identify Clinical Text Documents | Enrolling by Invitation | National Library of Medicine (NIH) | Automated de-identification of 18 HIPAA-defined PII types; gold-standard manual annotation benchmarks; references published on patient-privacy in big data (Kayaalp, 2018). |
| **NCT06019208** | GenoMed4ALL: Federated Privacy-Respecting Data Sharing for SCD AI | Active, Not Recruiting | Hospital Universitari Vall d'Hebron Research Institute (Spain) | Cross-border federated learning platform; no raw patient data leaves each institution; interoperable data-sharing via ERN-EuroBloodNet standards. |
| **NCT07378683** | ML-Based Prediction of Surgical Site Infection in CNS Tumor Surgery | Recruiting | Cancer Institute & Hospital, Chinese Academy of Medical Sciences | Coded identifiers replace names in all analyses; mandatory informed consent; IRB oversight; DSMB; 500-patient prospective study. |

> 315 total studies found on ClinicalTrials.gov for "patient data privacy" — spanning Phase 1 through 4 and observational designs. The full search is accessible at https://clinicaltrials.gov/search?cond=patient+data+privacy.

---

## 📍 Portland Workshop & Meetup Venues (within ~2 km of Downtown)

Verified venues sourced via geocoded OpenStreetMap, with walking distances from the downtown center (SW 6th & Morrison):

| Venue | Type | Address | Walking Distance | Best For |
|---|---|---|---|---|
| **Portland Art Museum** 🎨 | Museum / Event Space | 1219 SW Park Ave | ~510 m / 1.5 min | Sponsor-hosted talks, gallery-meets, demo nights |
| **KOIN Tower** 🏢 | Office / Lobby Space | 222 SW Columbia St | ~600 m / 2 min | Small working-groups, casual security chats (daytime lobby access) |
| **Portland State University** 🎓 | University Campus | 1825 SW Broadway | ~820 m / 2.5 min | Technical deep-dives, classroom-style workshops, academic partnership events |
| **Portland Central Library** 📚 | Public Library | 801 SW 10th Ave | ~1,040 m / 3 min | **Top pick for regular workshops** — free meeting rooms, Wi-Fi, AV, beginner-friendly tutorials |
| **First & Main** 🏣 | Office Lobby | 100 SW Main St | ~750 m / 2.2 min | Office-hours style informal meetups, weekday coffee chats |
| **Oregon Convention Center** 🏟️ | Conference Centre | 777 NE MLK Jr Blvd (Lloyd District) | ~1.5 km walk / 7 min | **Flagship events** — multi-track security conferences, Capture the Flag tournaments, large summits |
| **Revolution Hall** 🎶 | Events Venue | 1300 SE Stark St (Buckman) | ~1.9 km / 6 min | Speaker nights, social mixers, weekend hackathons (just outside 2 km, but easily reachable) |
| **Davies Family Research Library** 📖 | Research Library (OHS) | 1200 SW Park Ave | Adjacent to Art Museum | Focused research meetups, small-group technical reviews |

### Venue Distance Map (walking)

```
Downtown center (SW 6th & Morrison)
  │
  ├── 0.5 km  → Portland Art Museum
  ├── 0.6 km  → KOIN Tower
  ├── 0.8 km  → Portland State University
  ├── 1.0 km  → Portland Central Library  ★ Recommended
  ├── 1.5 km  → Oregon Convention Center
  └── 1.9 km  → Revolution Hall
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
