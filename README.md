# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## 🔒 Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). A search of ClinicalTrials.gov for recent privacy-focused studies returned three strong examples — across completed, recruiting, and not-yet-recruiting statuses — with concrete practices we can adapt for our web community.

### Key Takeaways from Clinical-Trial Privacy Practices

| Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|---|---|
| **Face masking, background blurring & encrypted intra-hospital storage** | **NCT07307521** (Shanghai Zhongshan Hospital, ICU-AI study) — automated face masking & background blurring before any video is used; raw video never leaves hospital, processed only after privacy protection. | Blur PII in community content by default; automate redaction for screenshots/videos; never expose raw logs externally. |
| **Mandatory de-identification before any analysis** | **NCT07267819** (Uniformed Services Univ., migraine trial) — *"All data will be de-identified to protect patient privacy."* Replaced identifiers enable analysis without exposing patients. | Assign pseudonymous IDs to forum contributors; batch analytics on de-identified logs only; never link usernames to operational telemetry. |
| **Electronic informed consent, encrypted storage & role-based access** | **NCT04990570** (Al-Azhar Univ., telemedicine study, completed) — electronic written consent required before every video consultation; data stored with encryption & shared only with authorized clinical staff. | Require explicit opt-in for any data collection; enforce TLS 1.3 + AES-256 at rest; apply least-privilege roles, SSO/2FA for all moderator/admin access; maintain audit trails. |
| **Independent oversight & defined retention** | NCT07307521 included an IRB-approved protocol, centralized hospital-side encrypted storage, trained annotators under unified privacy guidelines, and a defined retention window. | Establish a rotating community security board; keep hashed audit trails for sensitive data access; publish & enforce a 3-year data-retention & auto-deletion policy. |

### Studies Referenced (Verified on ClinicalTrials.gov)

| NCT ID | Title | Status | Sponsor | Key Privacy Takeaway |
|---|---|---|---|---|
| **NCT07307521** | Exploring AI-Assisted Video Monitoring to Predict Accidental Events in ICU Patients | Not Yet Recruiting | Shanghai Zhongshan Hospital | Automated face masking, background blurring, encrypted intra-hospital storage, IRB oversight, consent-based participation |
| **NCT07267819** | Xeomin Efficacy for Migraine in TBI vs. AHI Patients | Recruiting | Uniformed Services Univ. of the Hlth Sciences | Mandatory de-identification of all datasets before any analysis |
| **NCT04990570** | Telemedicine Virtual Clinic for Pediatric Day-case Surgery (COVID era) | Completed | Al-Azhar University | Electronic informed consent, encrypted storage, access restricted to authorized personnel |

> Consistent cross-trial themes: **secure encrypted data collection, role-based restricted access, independent oversight committees, encryption for cross-boundary sharing, bioethics-compliant retention & disposal, explicit participant consent & transparency, and separation of participant identity from data.**

---

## 📍 Portland Workshop & Meetup Venues (within ~2 km of Downtown)

Verified, bookable venues sourced via geocoded OpenStreetMap data:

| Venue | Type | Address | Best For |
|---|---|---|---|
| **Pioneer Courthouse Square** 🏛️ | Public Square | 401 SW Broadway, Downtown | Outdoor security meetups, talks & demo days (free, high foot-traffic) |
| **Portland Community College – Downtown Center** 🏫 | Community/Educational | 722 SW 2nd Ave, Downtown | Workshop classrooms with AV, low-cost academic rental |
| **PNNL Portland Research Center** 🔬 | Federal Research Office | 620 SW 5th Ave, Suite 810, Downtown | Technical deep-dives & credentialed security talks |
| **Water Avenue Coffee Company** ☕ | Café (WiFi) | 1028 SE Water Ave, SE Water | Small working-groups & casual security chats (indoor, Wi-Fi) |
| **Oregon Convention Center** 🏟️ | Conference Centre | 777 NE MLK Jr Blvd, Lloyd District (~1 km NE) | Large multi-track security conferences & summits |
| **Eastside Jewish Commons** 🏘️ | Community Centre | 2420 NE Sandy Blvd (~1.8 km E) | Intimate community events, training sessions, workshops |
| **SoHo House Portland** 🏠 | Private Event Venue | 1025 SE Pine St, Buckman/Central Eastside (~1.5 km) | High-signal speaker nights & social mixers |
| **Portland City Hall** 🏢 | Civic Town Hall | 1220 SW 5th Ave, Downtown | Formal presentations, city-security partnerships, large public meetings |
| **Central Library (Multnomah)** 📚 | Public Library | 801 SW 10th Ave, Downtown | Free public workshop rooms, beginner security tutorials |
| **Davies Family Research Library** 📖 | Research Library | 1200 SW Park Ave, OHS (4th Fl., Downtown) | Focused research meetups, small group technical reviews (by appt.) |

> **Top 3 picks nearest downtown for regular security workshops:**
> 1. **Pioneer Courthouse Square** — free, iconic downtown gathering space for outdoor talks & demos
> 2. **PCC Downtown Center** — affordable classroom AV, academic credibility, easy access
> 3. **Oregon Convention Center** — scale & infrastructure for flagship security conferences

---

## 🛠️ Toolkit Resources

- [Privacy Checklist for Open-Source Projects](`docs/privacy-checklist.md`) *(coming soon)*
- [Clinical-Trial Privacy Comparison Matrix](`docs/trial-privacy-matrix.md`) *(coming soon)*
- [Portland Venue Booking Guide](`docs/portland-venues.md`) *(coming soon)*
- [Workshop Planning Template](`docs/workshop-template.md`) *(coming soon)*

---

## 🤝 Contributing

Found a great privacy practice or a Portland venue we missed? Open an issue or submit a PR. We welcome web security practitioners, clinical researchers, and community organizers.

---

*Built by the web security community — combining clinical-trial rigor with open-source collaboration, anchored in downtown Portland, OR.*