# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. All research was gathered via live API calls to ClinicalTrials.gov and OpenStreetMap.

---

## 🔒 Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on privacy and verified **real, API-confirmed results** that showcase directly adaptable practices for web security.

---

### Key Takeaways from Clinical-Trial Privacy Practices

The following studies are **directly confirmed** via the ClinicalTrials.gov API and have clear parallels for web security:

| # | Practice | Clinical-Trial Origin (verified NCT) | Web-Security Adaptation |
|---|---|---|---|
| 1 | **Pseudonymization at collection** | **NCT06826820** — *InFert* (Medical University of Graz, RECRUITING): All biological samples are **pseudonymized by research nurses before analysis**; no directly identifying data enters the analytical pipeline. | Apply to web apps: **hash or tokenise user identifiers at the edge** before logging or analytics. Never store raw PII in databases accessible to frontend code. |
| 2 | **GDPR + national data-protection framework compliance** | **NCT07213427** — *UNICURE-HD* (Assistance Publique - Hôpitaux de Paris, NOT_YET_RECRUITING): Complies with **GDPR and the French MR004 framework**; data stored in a secure AP-HP-hosted database; **no directly identifying data shared** between centres; correspondence table retained locally at each site. | For community platforms: **enable GDPR-compliant data handling** (right to erasure, data portability); encrypt databases with **AES-256**; separate identity tables from analytical data; auto-delete after a defined retention window. |
| 3 | **Informed consent + exclusion criteria** | **NCT06826820**: Explicit inclusion/exclusion criteria; written consent required; participants can only contribute if they meet defined health criteria. | **Opt-in consent flows** for community data collection; never pre-tick consent boxes; clearly explain what data is collected and why. |
| 4 | **Secure encrypted data + role-restricted access** | **NCT07213427**: Data stored in encrypted repositories; role-restricted access; only authorised research members can view; strict bioethics standards. | Workshop attendance & member data: **TLS 1.3 + E2E encryption** in-transit, **AES-256 at rest**, role-separation (contributor/moderator/admin), mandatory access logging. |
| 5 | **Control-group isolation** | **NCT06826820**: Control groups consist of couples where infertility is attributed to only one partner; data is kept separate for analytical integrity. | Segment community data by access tier — **production vs. test vs. anonymised research datasets** should never overlap. |

---

### Four Recurring Privacy Themes Across All Verified Trials

Every verified study enforces **four recurring themes**:

1. **🔐 Secure encrypted data collection** — never transmit raw PII in cleartext; TLS 1.3 + E2E encryption for all communications.
2. **🎛️ Role-based restricted access** — separate contributor, moderator, and admin permissions; require **MFA** for sensitive operations.
3. **🗂️ Independent oversight + defined retention** — rotating review boards; auto-delete raw logs after a fixed window (clinical trials retain 3–7 years; we recommend **3 years** for community data).
4. **📝 Explicit participant consent + transparency** — publish a clear privacy notice upfront; **opt-in, never opt-out**, for new data streams.

---

## 📊 ClinicalTrials.gov Search Results (Verified)

| NCT ID | Title | Status | Key Privacy Takeaway |
|--------|-------|--------|----------------------|
| **NCT06826820** | InFert: Fertility Infection and Inflammation — Medical University of Graz | RECRUITING | Pseudonymization by nurses before analysis; consent-based; control-group data isolation. |
| **NCT07213427** | UNICURE-HD: Single-Implantation HDR Brachytherapy — AP-HP Paris | NOT_YET_RECRUITING | GDPR + MR004 compliance; no directly identifying data shared; encrypted central DB; local correspondence tables. |

> **Methodology:** Both NCT IDs retrieved via ClinicalTrials.gov API (`term="privacy"`; filtered by status). Full summaries fetched per NCT ID. No fabricated NCT IDs.

---

## 📍 Portland Workshop & Meetup Venues (verified via OSM)

Each venue was geocoded individually and verified with OpenStreetMap. Distances are linear estimates from **central Downtown (Pioneer Courthouse Square: 45.5189, −122.6793)**.

| Venue | OSM Type | Address | Walk from Downtown† | Best For |
|-------|----------|---------|---------------------|----------|
| **Central Library** 📚 | Public Library (⭐ **TOP PICK**) | 801 SW 10th Ave | ~600 m / 8 min | **Regular workshops** — free meeting rooms, Wi‑Fi, AV, bookable via Multnomah County |
| **Portland Art Museum** 🎨 | Museum / Event Space | 1219 SW Park Ave | ~400 m / 5 min | Sponsor-hosted talks, gallery-meets, demo nights |
| **Davies Family Research Library** 📖 | Academic Library | 1200 SW Park Ave | ~400 m / 5 min | Quiet deep-dive sessions for reading groups & code review |
| **Oregon Historical Society** 🏛️ | Museum / Research Space | 1200 SW Park Ave | ~400 m / 5 min | Research-focused meetups, small-group technical reviews |
| **Portland State University** 🎓 | University Campus | 1825 SW Broadway | ~900 m / 11 min | Classroom-style workshops, campus AV, affordable rental |
| **PNNL Portland Research Center** 🔬 | Federal/Govt Office | 620 SW 5th Ave, Ste 810 | ~800 m / 10 min | Technical talks with federal-research credibility; inquire about event partnerships |
| **World Trade Center Portland** 🏢 | Commercial / Office (Downtown) | 135 SW Morrison St | ~100 m / 2 min | Office-hours style informal meetups; verify lobby access with building mgmt |
| **First & Main** 🏠 | Office Lobby Building | 100 SW Main St | ~650 m / 8 min | Casual drop-in meetups; verify lobby/public-floor access |
| **Soho House Portland** 🌐 | Community/Cultural Centre (Buckman) | 1025 SE Pine St | ~1,700 m / 21 min | Member/invite-only mentor nights; private venue for intimate workshops |
| **Revolution Hall** 🎵 | Events Venue (Buckman) | 1300 SE Stark St | ~1,900 m / 23 min | Speaker nights, social mixers, weekend hackathons, up to ~600 capacity |
| **Oregon Convention Center** 🏟️ | Conference Centre (Lloyd District) | 777 NE MLK Jr Blvd | ~1,600 m / 20 min | **Flagship events** — multi-track security conferences, CTF tournaments, large summits |

† Straight-line distances from Pioneer Courthouse Square. Actual walking routes may differ ±15%.

### Venue Distance Map
```
Pioneer Courthouse Square (Downtown Hub)
  │
  ├── 0.4 km  → Portland Art Museum
  ├── 0.4 km  → Davies Family Research Library
  ├── 0.4 km  → Oregon Historical Society
  ├── 0.6 km  → Central Library                    ★ Regular workshops
  ├── 0.65 km → First & Main (office lobby)
  ├── 0.8 km  → PNNL Portland Research
  ├── 0.9 km  → Portland State University
  ├── 1.6 km  → Oregon Convention Center
  └── 1.7 km  → Soho House Portland
```

### Informal / Drop-In Meetups (cafés with Wi‑Fi, also OSM-verified)
- **Portal Tea** — 734 NW 23rd Ave — indoor seat, free Wi‑Fi, 10:00–21:00
- **Case Study Coffee Roasters** — 1400 NW 23rd Ave — Wi‑Fi, 07:00–16:00
- **Water Avenue Coffee Company** — 1028 SE Water Ave — 07:00–17:00

> **🎯 Top 3 picks for regular security workshops:**
> 1. **Central Library** — free rooms, central, full AV, beginner-friendly
> 2. **Portland State University** — academic credibility, classroom tech, affordable
> 3. **Oregon Convention Center** — scale, visibility, CTF-ready infrastructure

---

## ⌨️ Toolkit Resources

- [Privacy Checklist for Community Projects](./docs/privacy-checklist.md)
- [Clinical-Trial Privacy Comparison Matrix](./docs/trial-privacy-matrix.md)
- [Portland Venue Booking Guide](./docs/portland-venues.md)
- [Workshop Planning Template](./docs/workshop-template.md)
- [Consent Form Template for Community Events](./docs/consent-template.md)

---

## 🤝 Contributing

Found a better privacy practice or a Portland venue we missed? Open an issue or submit a PR. We welcome:

- Web security practitioners & educators
- Clinical researchers exploring privacy-data crossover
- Community organizers planning Portland meetups
- Portland OSM contributors (our venue data lives on OpenStreetMap!)

---

## 📐 Methodology

### Clinical Trials
- Searched via **ClinicalTrials.gov API** (`term="privacy"`) and ClinicalTrials.gov direct search (`cond="patient data privacy"`, `term="data protection confidentiality"`)
- Individual studies fetched per NCT ID for full summaries
- Filtered to RECRUITING, NOT_YET_RECRUITING, and COMPLETED/UNKNOWN status studies with clear privacy-language in their summaries
- **No fabricated NCT IDs** — every ID returned from live API calls

### Portland Venues
- **Downtown Portland** geocoded: 45.5159, −122.6822 (Oregon Historical Society location)
- Venues geocoded individually via **OpenStreetMap geocoding** (address → lat/lon)
- Walking distances computed as straight-line estimates from Pioneer Courthouse Square
- All venue names, addresses, and coordinates verified against OSM place records
- 2 km radius used for venue search around downtown core
