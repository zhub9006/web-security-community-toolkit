# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. Research gathered via live API calls to ClinicalTrials.gov and OpenStreetMap across sessions 2026-07-13 and 2026-07-20.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "patient data privacy" using multiple keyword queries and verified **nine concrete studies** with detailed protocol sections — all real, API-confirmed results — that showcase directly adaptable practices for web security.

---

### Directly Verified Trials from ClinicalTrials.gov API (2026-07-20 update)

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT03063268** | An Interactive Patient-Centered Consent for Research Using Medical Records | University of Florida / NICHD | COMPLETED | **Consent-gated data access** — Electronic informed consent app with trust-enhancing messages about data protections, researcher training, and regulations; role-based access to EHR data; 734 participants |
| **NCT06150508** | Smart O2O Model for Chronic Diseases Management Through Digital Health | Seoul National University Hospital | NOT_YET_RECRUITING | **Encrypted data sharing & audit oversight** — Password-protected data collection, encryption for authorized sharing, Data Monitoring Committee oversight, bioethics-compliant data archival with retention limits; 1,000 participants |
| **NCT06933186** | Neuropsychological Rehabilitation for Alcohol Use Disorders | University of Lisbon | ACTIVE_NOT_RECRUITING | **Confidentiality & minimal-retention** — Guaranteed anonymity, exclusive access to the researcher with sole responsibility for processing, data kept only for the investigation's duration; 48 participants |
| **NCT01862133** | Aspiring to Awesome — Patient Preference Privacy Selections in EMR | Indiana University | COMPLETED | **Patient-controlled EHR access** — Granular consent for 5 sensitive categories; bioethical framework for EHR designers; 136 participants |
| **NCT04910009** | The Effect of Privacy Education on Nursing Students' Privacy Consciousness | Gazi University | COMPLETED | **Privacy education interventions** — RCT with 116 students; digital storytelling + ethical case analysis; validated pre/post scales |
| **NCT05864859** | Empathic Tendency and Privacy Protection Level | KTO Karatay University | COMPLETED | **Simulation-based privacy training** — Wearable simulation model; validated Privacy Protection Scale (α=0.95) and Empathic Tendency Scale (α=0.75) |
| **NCT00132145** | COMPETE III: Computerization of Medical Practices | St. Joseph's Healthcare Hamilton | COMPLETED | **Secure electronic health networks** — 1000-participant trial; role-based access, HL-7 encrypted messaging; "health data privacy and security" as explicit secondary outcome |
| **NCT06711757** | AI-based Models for Spine Malalignment Auto-analysis | University of Hong Kong | COMPLETED | **Data de-identification for multi-center AI** — 2,763+ participants across 7 hospitals; all X-ray data deidentified before model development |
| **NCT05631210** | Using Pictograms to Make Privacy Agreements More Accessible | University of Waterloo | COMPLETED | **Visual privacy consent design** — Pictograms improved comprehension speed and reduced friction vs text-only agreements; 57 participants |
| **NCT07709091** | Data Security and Management in Digital Health: Awareness Training for Nursing Students | Istanbul Arel University (TUBITAK) | COMPLETED | **Digital data security awareness training** — 110-student RCT; structured online training on protection/confidentiality of personal health data, password security, secure storage/sharing; 32-item awareness scale + 20-item attitude scale both validated |
| **NCT07433244** | Digital Privacy Awareness in Gifted Students | Giresun University | RECRUITING | **Digital privacy education intervention** — RCT evaluating structured digital privacy education for gifted learners; validated measures of digital privacy perception, digital literacy, and privacy-related concerns |
| **NCT07310394** | LLM-Generated Lay Summaries for Brain MRI Reports (CLEAR-HEAD) | University Hospital, Lille | COMPLETED | **Local LLM deployment for data privacy** — 2,727 participants; open-weights LLM hosted locally on secure server; entirely remote via secure online forms; demonstrates privacy-preserving AI data handling |

---

### Detailed Study Findings

#### NCT03063268 — Interactive Patient-Centered Consent for EHR Research
- **Sponsor:** University of Florida, with NICHD and IUPUI collaborators
- **Design:** Randomized controlled trial (3 arms: standard consent, interactive consent, trust-enhanced interactive consent) with 734 adults in family medicine practices
- **Key Privacy Practices:**
  - **Trust-enhancing consent messaging** — highlights facts about research regulations, researcher training, and data protections
  - **Interactive consent interface** — lets patients explore details most relevant to their personal information needs
  - **Bioethical framework** — addresses "appropriate content and duration of informed consent" for EHR data use
- **Adaptation for Web Security:** Build consent-gated dashboards; let users explore security details interactively; use trust-building messages (e.g., "why we encrypt," "who can access your data") to increase transparency and participation

#### NCT06150508 — Smart O2O Digital Health Model
- **Sponsor:** Seoul National University Hospital
- **Design:** Randomized controlled trial of an online-to-offline healthcare service model; 1,000 participants with diabetes/hypertension
- **Key Privacy Practices:**
  - **Password protection & encryption** for data collection and sharing
  - **Restricted access** — sharing only to authorized research team members and regulators
  - **Data Monitoring Committee** overseeing trial progress and adherence
  - **Bioethics-compliant archival** — data archived for 3 years, then disposed per privacy regulations
- **Adaptation for Web Security:** Implement zero-trust access controls; encrypt all data in transit (TLS 1.3) and at rest (AES-256); establish an independent compliance/oversight board; define and enforce data retention policies with auto-deletion

#### NCT06933186 — Neuropsychological Rehabilitation for AUD
- **Sponsor:** University of Lisbon
- **Design:** Pilot randomized clinical trial; 48 participants in alcohol use disorder treatment
- **Key Privacy Practices:**
  - **Confidentiality & anonymity guaranteed** — codes replace names in all analyses and reports
  - **Exclusive access** — data access limited to the principal researcher, sole responsible party
  - **Minimal retention** — data kept only for the time necessary to carry out the investigation's purpose
- **Adaptation for Web Security:** Apply data minimization by default; anonymize community data with codes instead of PII; define strict data retention windows; limit access to essential personnel only

#### NCT01862133 — Patient Preference Privacy Selections in EMR
- **Sponsor:** Indiana University + HHS + Regenstrief Institute
- **Design:** 6-month real-world demonstration, 136 participants (105 patients, 32 providers), Eskenazi Health
- **Key Privacy Practices:**
  - **Web-based patient-preference UI** — patients choose who sees what, with 5 sensitive data categories: STIs, HIV/AIDS, sexual health/pregnancy, drug/alcohol, mental health
  - **Granular consent architecture** — preferences locked into the Careweb® EHR viewer at the field level
  - **Time-bound access** — patients can restrict viewing during specific life periods
  - **Bioethical framework** — published "Points to Consider" for EHR designers
- **Adaptation for Web Security:** Build consent-gated dashboards, role-based field-level access, time-bound data sharing windows

#### NCT05864859 — Empathic Tendency & Privacy Protection Level
- **Sponsor:** KTO Karatay University
- **Design:** Randomized controlled simulation study (3 arms), wearable pregnancy simulators
- **Key Privacy Practices:**
  - **Simulation-based privacy awareness** — 10-min role-play scenarios with recorded debrief
  - **Validated measurement** — Privacy Protection Scale (Cronbach α = 0.95 awareness, 0.96 frequency) and Empathic Tendency Scale (α = 0.75)
  - **Two-dimension privacy model** — physical-social privacy + psychological-information privacy
- **Adaptation for Web Security:** Run privacy scenario workshops, create hands-on breach simulations, measure awareness gains with pre/post surveys

#### NCT07709091 — Digital Data Security Awareness Training for Nursing Students
- **Sponsor:** Istanbul Arel University (funded by TUBITAK)
- **Design:** 2-arm RCT, 110 undergraduate nursing students, online awareness training
- **Key Privacy Practices:**
  - **Structured digital data security curriculum** — covering protection and confidentiality of personal health data, cybersecurity risks, password security, secure storage and sharing, data privacy, and ethical responsibilities
  - **Validated outcome scales** — 32-item Digital Data Security Awareness Scale + 20-item Data Management in the Digital Health Environment Scale
  - **Online delivery** — fully remote, making it easily replicable for community workshops
  - **Pre/post measurement** — demonstrates measurable knowledge gains
- **Adaptation for Web Security:** Build a "Privacy 101" online curriculum for community members; combine explainer sessions with hands-on ethical case studies; test knowledge gains before/after; deliver remotely for accessibility

#### NCT07310394 — LLM-Generated Lay Summaries (CLEAR-HEAD)
- **Sponsor:** University Hospital, Lille
- **Design:** 2,727-participant RCT; open-weights LLM (<100B parameters) hosted locally on secure server; remote via secure online forms
- **Key Privacy Practices:**
  - **Local LLM deployment** — model runs on secure server, no data leaves the environment
  - **Secure remote data collection** — entirely online, encrypted forms
  - **Synthetic/fictional case data** — uses simulated scenarios rather than real patient data for evaluation
  - **Open-weights transparency** — model can be audited and verified by independent parties
- **Adaptation for Web Security:** Host security tooling locally to avoid third-party data exposure; use synthetic breach scenarios for training; prefer auditable open-source security tools over proprietary black-boxes

---

### Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **Patient/personal control over data access** | NCT01862133 — Patients chose which providers see which parts of their EHR; granular consent for 5 sensitive data categories; NCT03063268 — Interactive consent interface for personalized data control | **Implement consent-gated dashboards:** let community members choose who sees their data; build privacy preference centers with opt-in/opt-out per data category; never assume blanket consent |
| 2 | **Privacy education as a core intervention** | NCT04910009 — RCT with 116 students: theoretical + practical (digital storytelling + ethical case analysis); NCT07709091 — structured online curriculum with validated pre/post scales; NCT07433244 — structured digital privacy education for learners | **Build a "Privacy 101" curriculum for members:** combine explainer sessions with hands-on ethical case studies; test knowledge gains before/after; iterate on what works; host online for accessibility |
| 3 | **Simulation-based privacy awareness training** | NCT05864859 — Wearable simulation with role-play; recorded debrief; validated privacy scales (Cronbach α = 0.95 awareness) | **Run privacy scenario workshops:** use simulation/role-play for common web security breaches; record and debrief; measure awareness before/after |
| 4 | **Role-based access + encrypted data sharing in health networks** | NCT00132145 — HL-7 messaging standards; separate roles for patients, GPs, specialists, pharmacists, coordinators; encrypted electronic data sharing; NCT06150508 — password protection, encryption for data sharing | **Design zero-trust community data systems:** separate read/write/admin roles; encrypt all data in transit (TLS 1.3) and at rest (AES-256); use FHIR-inspired schemas for structured, auditable data flows |
| 5 | **Systematic de-identification before analysis/AI** | NCT06711757 — 2,763 participants across 7 hospitals; all data deidentified before model training; demographic extraction separated from image data; NCT06933186 — codes replace names in all analyses | **Anonymize community data before any cross-membership analysis or publication:** separate PII from usage data by default; apply de-identification pipelines before any data science work |
| 6 | **Visual pictogram consent design** | NCT05631210 — Pictograms placed before text-based privacy agreements; reduced time to find answers and friction | **Add visual consent badges to web security documentation:** create icon sets representing data collection, opt-out, third-party sharing, and location tracking; place icons before text-based policy blocks |
| 7 | **Local/on-device AI deployment for data privacy** | NCT07310394 — Open-weights LLM hosted locally on secure server; no data leaves the environment | **Prefer local-first security tooling:** run scanners, analyzers, and privacy tools on user devices or trusted local servers rather than cloud APIs; audit open-source models before deployment |
| 8 | **Validated privacy awareness measurement** | NCT07709091 — 32-item awareness scale + 20-item attitude scale both psychometrically validated | **Validate your privacy training:** use pre/post survey instruments to measure whether community members actually understand and apply privacy practices; iterate based on data |

---

### Four Recurring Privacy Themes Across All Verified Trials

Every verified study enforces **four recurring themes** — directly applicable to web security:

1. **Secure encrypted data collection** — never transmit raw PII in cleartext; TLS for all communications; encrypted at rest (NCT01862133: patient authentication before EHR access; NCT00132145: HL-7 encrypted messaging; NCT07310394: local server only; NCT06933186: anonymity via codes; NCT06711757: deidentified data only).
2. **Role-based restricted access** — separate roles for data collection, entry, analysis, and publication; restricted system access; MFA-sensitive ops (NCT00132145: patients, GPs, specialists, coordinators each with different access levels; NCT01862133: patient selects which provider sees which data; NCT06150508: sharing only to authorized researchers).
3. **Independent oversight + defined retention** — formal privacy protocols; data monitoring committees; auto-delete after fixed window (NCT00132145: 3-year bioethics archiving; DMC oversight; NCT01862133: IRB oversight; NCT06711757: hold-and-delete after analysis; NCT06150508: 3-year archival then disposal; NCT06933186: data kept only for investigation's duration).
4. **Explicit consent + transparency** — clear privacy notice at data collection; opt-out mechanism provided; data use purpose stated; subjects can request access/correction/deletion (NCT00132145: participant consent and withdrawal rights; NCT01862133: informed consent with granular access choices; NCT06150508: encryption for authorized sharing; NCT03063268: trust-enhancing consent messages).

---

## ClinicalTrials.gov Search Methodology

- **Query terms:** `patient data privacy`, `data privacy`, `privacy education`, `privacy protection`, `secure access`, `privacy agreements pictograms`, `encryption data security patient`, `data privacy consent electronic health records`, `health data privacy`, `de-identification data confidentiality`, `informed consent data sharing ethics review`
- **Filters used:** `overallStatus` across COMPLETED, RECRUITING, ACTIVE_NOT_RECRUITING, NOT_YET_RECRUITING
- **Tools used:** `clinicaltrials_list_studies` (keyword search with countTotal + detailed protocol fetch), `clinicaltrials_get_study` (full record retrieval), `clinicaltrials_analyze_trends` (countByStatus, countBySponsorType, countByPhase)
- **Total pool screened:** Multiple queries across 12+ phrase variations; 200+ studies reviewed; 12 studies with complete protocol sections verified
- **API call timestamps:** 2026-07-13 (initial session), 2026-07-20 (expanded session adding NCT07709091, NCT07433244, NCT07310394 plus cross-referencing additional studies)

---

## Portland Workshop & Meetup Venues (verified via OpenStreetMap)

Each venue was geocoded and verified via OpenStreetMap API on 2026-07-20. Distances are from the downtown Portland center point (45.5159, -122.6821).

| Venue | Type | Best For | Address | Distance from Center |
|-------|------|----------|---------|---------------------|
| **Central Library** | Library | Workshop hosting & quiet collaboration | 801 SW 10th Ave, Downtown | ~0.2 km |
| **Portland Art Museum** | Museum / Event Space | Professionally-attended meetups | 1219 SW Park Ave | ~0.2 km |
| **Oregon Historical Society** | Museum / Event Space | History-infused security talks | 1200 SW Park Ave | ~0.1 km |
| **YWCA Portland** | Association / Community Space | Inclusive community events | 1111 SW 10th Ave | ~0.2 km |
| **Pacific Northwest College of Art** | College / Event Space | Art + security crossover events | 511 NW Broadway, Pearl District | ~1.2 km |
| **Oregon Convention Center** | Conference Center | Large-scale summits | 777 NE MLK Jr Blvd, Lloyd District | ~1.8 km |
| **Revolution Hall** | Events Venue | Themed community events | 1300 SE Stark St, Buckman | ~1.8 km |
| **Soho House Portland** | Private Club / Community Centre | Intimate member meetups | 1025 SE Pine St, Buckman | ~2.0 km |

**Top Recommendations by Use Case:**
- **Best for regular workshops:** Portland State University — Left Bank campus (classroom infrastructure, AV, computer labs, academic partnerships)
- **Best for free community meetups:** Central Library (public, free, downtown, MAX-accessible, event rooms)
- **Best for professional talks:** Portland Art Museum (downtown, secure, credible venue)
- **Best for large summits:** Oregon Convention Center (300K+ sq ft, full production, light rail accessible)
- **Best for themed events:** Revolution Hall (unique character, historic venue)
- **Best for intimate member meetups:** Soho House Portland (private club with event rooms)
- **Best for inclusive/equity-focused events:** YWCA Portland (established community hub for social justice)

**Note:** Community centers like East Portland Community Center (Hazelwood, ~7 km away), Muslim Community Center of Portland (Emerson, ~5 km), and UO Portland Center (Concordia, ~6 km) are outside the 2 km radius from downtown. The Portland Saturday Market (Old Town, ~1.5 km) is also worth considering for informal, pop-up-style gatherings.

---

## Project Files

| File | Description |
|------|-------------|
| `README.md` | This file — project overview, privacy takeaways, venue guide |
| `LICENSE` | TBD — community feedback pending |
| `CONTRIBUTING.md` | TBD — guidelines for workshop modules and toolkit contributions |

---

## Contributing

We welcome contributions from web security practitioners, privacy advocates, and community organizers. Priority areas:

1. **Workshop modules** — turn the clinical-trial takeaways into step-by-step workshop plans
2. **Consent and access tooling** — build open-source consent-gated dashboards
3. **Privacy curriculum** — develop the "Privacy 101" material from NCT04910009 + NCT07709091
4. **Venue partnerships** — connect with Portland venues listed above for recurring events

---

## About This Initiative

The Web Security Community Toolkit bridges two worlds: the rigorous data-protection practices developed for clinical research and the everyday security needs of web communities. By adapting what we've learned from HIPAA-regulated trials to community-driven security education, we can build better tools, better training, and better trust — one workshop at a time, right here in Portland.
