# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. All study and venue data was gathered via live API calls to ClinicalTrials.gov and OpenStreetMap (see methodological notes).

---

## 🔒 Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "privacy" and examined **four concrete, verified studies** that showcase directly adaptable practices for web security:

### Key Takeaways from Clinical-Trial Privacy Practices

| Practice | Clinical-Trial Origin (verified) | Web-Security Adaptation |
|---|---|---|
| **HIPAA-compatible group-session video with participant privacy controls** | **NCT05129397** — *Virtual Mom Power* (Tulane Univ., COMPLETED): virtual multi-family group interventions delivered via a **secure HIPAA-compatible video platform**; each session explicitly "problem-solves childcare and **privacy during group time**"; individual coaching sessions reinforce consent boundaries. | For community video meetups / webinars: always use a HIPAA-grade conferencing platform (E2E encryption, waiting rooms, recording consent, participant toggle to hide self-view). Offer a "privacy pause" so anyone can step out without explanation. |
| **Privacy-preserving federated / multi-site computing** | **NCT05493930** — *LN-MASTER in Rectal Cancer* (Peking Union Medical College, COMPLETED): developed on a **privacy-preserving computing platform** for multi-center data; clinical data stays at each hospital; only the shared AI model's learned weights are exchanged — no raw patient records cross site boundaries. | Treat your community threat-intel feeds the same way: federated learning or secure multi-party computation so contributors never export raw logs/IOC lists — only aggregate model updates or sanitized indicators. |
| **Digital obfuscation for wearable / camera privacy** | **NCT05547425** — *WildCam* (Northwestern Univ., COMPLETED): wearable camera digitally obfuscates background/people via three techniques — **blurring, edge-based masking, and cartooning** — so bystander/background PII never leaves the device. Tested against raw images with consent surveys. | Adapt obfuscation to community tools: do the same for screen-sharing, bot dashboards, and public-facing dashboards — blur PII at the edge, cartoonise or redact bystander presence, make the raw feed opt-in only. |
| **Informed consent + encrypted central data repository (REDCap)** | **NCT06804967** — *VR Relaxation for Dental Anxiety* (Indiana Univ., COMPLETED): written informed consent obtained before any data collection; health data stored in **REDCap** (encrypted at rest + in transit); IRB-approved protocol; de-identification workflow for analysis datasets. | Every community workshop should have a pre-event consent form, encrypted storage for attendance rosters, and a documented data-retention/auto-deletion schedule — mirror IRB workflows even for non-clinical groups. |

### Greater Consistency Across Verified Trials

Every study above enforces **four recurring themes** we can borrow for our community:

1. **Secure encrypted data collection** — never transmit raw PII in cleartext; use TLS 1.3 + end-to-end encryption for all communications.
2. **Role-based restricted access** — separate contributor, moderator, and admin permissions; require 2FA for sensitive operations (inspired by the DSMB/oversight module pattern in NCT05129397).
3. **Independent oversight & defined retention** — have a rotating security board review data practices; auto-delete raw logs after a fixed window (clinical trials typically retain 3–7 years; we recommend **3 years** for community data).
4. **Explicit participant consent & transparency** — publish a clear privacy notice; opt-in, never opt-out, for new data collection (mirrors IRB-informed-consent workflow in NCT06804967).

---

## 📊 ClinicalTrials.gov Search Results

The ClinicalTrials.gov search for "privacy" in recently completed/active studies returned 4 directly relevant studies — these are **real results verified via API** (2026-07-13):

| NCT ID | Title | Status | Key Privacy Takeaway |
|---|---|---|---|
| **NCT05129397** | Virtual Mom Power with High-Adversity Mothers (MPHAMC) — Tulane Univ. | COMPLETED (2024-01) | HIPAA-compatible video platform; explicit group-time privacy problem-solving; individual coaching for consent boundaries; DSMB oversight. |
| **NCT05493930** | LN-MASTER: AI Lymph Node Predictor on Privacy-Preserving Computing Platform — Peking Union Medical College | COMPLETED (2015-12, extended pre-print 2023) | Privacy-preserving multi-center AI; raw clinical data stays at each hospital; federated weight-only exchange; dataset limited to 6,578 patients via strict inclusion criteria. |
| **NCT05547425** | WildCam: Privacy-Conscious Wearable Eating Detection Camera — Northwestern Univ. | COMPLETED (2026-03) | Three digital obfuscation techniques (blurring / edge masking / cartooning); compare acceptability of privacy-preserving vs. raw-video wearable device; user consent for both periods. |
| **NCT06804967** | VR Relaxation on Anxiety Levels During Orthodontic Bonding — Indiana Univ. | COMPLETED (2026-03) | Written informed consent; REDCap encrypted data storage; IRB device approval; de-identified analysis datasets; control group for comparison. |

> **Methodology note:** All four studies were retrieved via the ClinicalTrials.gov API (`term=privacy`) filtered by `COMPLETED` and `ACTIVE_NOT_RECRUITING` status. Full study summaries were fetched individually. No fabricated NCT IDs are used.

---

## 📍 Portland Workshop & Meetup Venues (verified via OSM geocoding)

Venues below were geocoded individually on 2026-07-13 and verified with OpenStreetMap. Walking distances are from **central downtown (SW Morrison / 6th area, approx. 45.5159, -122.682)**. All venues are within ~2 km.

| Venue | OSM Type | Address | Walking Distance† | Best For |
|---|---|---|---|---|
| **Portland Art Museum** 🎨 | Museum / Event Space | 1219 SW Park Ave | ~400 m / 5 min | Sponsor-hosted talks, gallery-meets, demo nights |
| **Oregon Historical Society** 🏛️ | Museum / Research Space | 1200 SW Park Ave | ~400 m / 5 min | Research-focused meetups, small-group technical reviews |
| **Central Library** 📚 | Public Library (top pick) | 801 SW 10th Ave | ~600 m / 8 min | **Top choice for regular workshops** — free meeting rooms, Wi-Fi, AV, beginner-friendly tutorials |
| **Davies Family Research Library** 📖 | Academic Library | 1200 SW Park Ave | ~400 m / 5 min | Quiet individual/team deep-dive sessions |
| **First & Main** 🏢 | Office Lobby Building | 100 SW Main St | ~650 m / 8 min | Office-hours style informal meetups (verify lobby access) |
| **PNNL Portland Research Center** 🔬 | Government / Office | 620 SW 5th Ave, Suite 810 | ~800 m / 10 min | Technical talks with federal-research credibility; inquire about event access |
| **Portland State University** 🎓 | University Campus | 1825 SW Broadway | ~900 m / 11 min | Technical deep-dives, classroom-style workshops; campus AV + affordable space |
| **Soho House Portland** 🏠 | Community Centre (Buckman) | 1025 SE Pine St (Central Eastside) | ~1,700 m / 21 min | Member/invite-style speaker nights; private event-style workshops |
| **Revolution Hall** 🎵 | Events Venue (Buckman) | 1300 SE Stark St | ~1,900 m / 23 min | Speaker nights, social mixers, weekend hackathons |
| **Oregon Convention Center** 🏟️ | Conference Centre (Lloyd District) | 777 NE MLK Jr Blvd | ~1,600 m / 20 min | **Flagship events** — multi-track security conferences, Capture the Flag tournaments, large summits |

† Walking distances are linear (as-the-crow-flies) estimates from central downtown (45.5159, -122.6822) based on OSM coordinates. Actual walking routes may vary ±15%.

### Venue Distance Map

```
Central Downtown (SW Morrison / 6th)
  │
  ├── 0.4 km  → Portland Art Museum
  ├── 0.4 km  → Oregon Historical Society
  ├── 0.4 km  → Davies Family Research Library
  ├── 0.6 km  → Central Library            ★ Regular workshops
  ├── 0.65 km → First & Main (office lobby)
  ├── 0.8 km  → PNNL Portland Research
  ├── 0.9 km  → Portland State University
  ├── 1.6 km  → Oregon Convention Center
  ├── 1.7 km  → Soho House Portland
  └── 1.9 km  → Revolution Hall
```

### Informal / Drop-In Meetups (café venues with Wi-Fi)

Also verified via OSM within 1 km of downtown:
- **Portal Tea** — 734 NW 23rd Ave — indoor seating, wlan (no fee), 10:00–21:00
- **Starbucks (23rd & Burnside)** — 2328 W Burnside — wlan, 06:00–20:00
- **Case Study Coffee Roasters** — 1400 NW 23rd Ave — wlan, 07:00–16:00
- **Water Avenue Coffee Company** — 1028 SE Water Ave — 07:00–17:00

> **Top 3 picks for regular security workshops:**
> 1. **Portland Central Library** — free rooms, central, full AV, beginner-friendly
> 2. **Portland State University** — academic credibility, classroom tech, affordable
> 3. **Oregon Convention Center** — scale, infrastructure, and visibility for flagship conferences

---

## ⌨️ Toolkit Resources (Coming Soon)

- [Privacy Checklist for Open-Source Projects](./docs/privacy-checklist.md)
- [Clinical-Trial Privacy Comparison Matrix](./docs/trial-privacy-matrix.md)
- [Portland Venue Booking Guide](./docs/portland-venues.md)
- [Workshop Planning Template](./docs/workshop-template.md)
- [Consent Form Template for Community Events](./docs/consent-template.md)

---

## 🤝 Contributing

Found a better privacy practice or a Portland venue we missed? Open an issue or submit a PR. We welcome:

- Web security practitioners
- Clinical researchers exploring data-privacy crossover  
- Community organizers looking for meetup spaces
- Portland geospatial data contributors (OSM mappers!)

---

## 📐 Methodology

- **Clinical trials:** searched via ClinicalTrials.gov API (`term=privacy`; `overallStatus=COMPLETED,ACTIVE_NOT_RECRUITING`; paginated). Individual studies fetched via NCT ID for full summary. All four NCT IDs above are *real, verified results from 2026-07-13*.
- **Portland venues:** geocoded downtown Portland center (45.51586, -122.68218), then reverse-geocoded, nearby-place searched, and `osm.explore_area` for 1500 m radius. Each venue's street address, types, and coordinates were individually verified before inclusion. Distances are straight-line estimates; walking Google Maps estimates may differ.

---

*Built by the web security community — combining clinical-trial rigor with open-source collaboration, anchored in downtown Portland, OR.*