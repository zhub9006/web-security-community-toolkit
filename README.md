# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. All research was gathered via live API calls to ClinicalTrials.gov and OpenStreetMap.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "patient data privacy" using multiple keyword queries and verified studies with detailed protocol sections — all real, API-confirmed results — that showcase directly adaptable practices for web security.

---

### Verified Trials from ClinicalTrials.gov API

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT01862133** | Aspiring to Awesome — Patient Preference Privacy Selections in EMR | Indiana University | COMPLETED | Patient-controlled EHR access — Granular consent for 5 sensitive data categories; time-bound access; bioethical framework |
| **NCT04910009** | Privacy Education on Nursing Students' Privacy Consciousness | Gazi University | COMPLETED | Privacy education RCT with 116 students; theoretical + practical (digital storytelling + ethical case analysis); validated scales |
| **NCT05864859** | Empathic Tendency and Privacy Protection Level | KTO Karatay University | COMPLETED | Simulation-based privacy training; wearable simulation + role-play; Privacy Protection Scale (α=0.95) |
| **NCT00132145** | COMPETE III: Secure Electronic Health Networks | St. Joseph's Healthcare Hamilton | COMPLETED | 1,000-participant RCT; role-based access; encrypted HL-7 data sharing; "Health data privacy and security" as secondary outcome |
| **NCT06711757** | AI-based Models for Spine Malalignment (Multi-Center) | University of Hong Kong | COMPLETED | 2,763+ participants across 7 hospitals; systematic de-identification before AI model development |
| **NCT05631210** | Pictograms for Privacy Agreements | University of Waterloo | COMPLETED | Visual consent design — pictograms improved comprehension speed and reduced friction vs. text-only |
| **NCT07709091** | Digital Health Data Security Awareness Training | Istanbul Arel University | COMPLETED | RCT with 110 nursing students; training on data security, cybersecurity risks, password security, secure storage/sharing |
| **NCT07307521** | AIME-ICU: AI-Assisted Video Monitoring with Privacy Protections | Shanghai Zhongshan Hospital | NOT_YET_RECRUITING | Face masking, background blurring, secure local storage, de-identification pipeline, informed consent with opt-out |

---

### Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | Patient/personal control over data access | NCT01862133 — Granular consent for 5 sensitive EHR categories | Implement consent-gated dashboards; privacy preference centers with opt-in/opt-out per category |
| 2 | Privacy education as a core intervention | NCT04910009 — RCT: theoretical + practical education; pre/post scales | Build "Privacy 101" curriculum with hands-on ethical case studies; measure knowledge gains |
| 3 | Simulation-based privacy awareness training | NCT05864859 — Role-play + recorded debrief; validated scales | Run privacy scenario workshops; measure awareness before/after with validated scales |
| 4 | Role-based access + encrypted data sharing | NCT00132145 — HL-7 standards; separate patient/GP/specialist/coordinator roles | Design zero-trust community data systems; TLS 1.3 + AES-256; separate read/write/admin roles |
| 5 | Systematic de-identification before analysis/AI | NCT06711757 — 2,763 participants; all data deidentified before model training | Anonymize community data before cross-membership analysis; separate PII from usage data by default |
| 6 | Visual pictogram consent design | NCT05631210 — Pictograms improved comprehension speed | Add visual consent badges to documentation; icon sets for data collection, opt-out, sharing |
| 7 | Structured data security awareness training | NCT07709091 — 110 students; cybersecurity, password security, encrypted storage | Run data-security bootcamps; issue certificates; cover phishing, secure storage, encrypted communication |
| 8 | Privacy-by-design AI with de-identification pipelines | NCT07307521 — Face masking, blurring, offline-only storage, compliance | Integrate privacy into dev pipeline; automated PII scrubbing; offline-first processing |

---

### Four Recurring Privacy Themes

1. **Secure encrypted data collection** — TLS for all comms; encrypted at rest; never transmit raw PII in cleartext
2. **Role-based restricted access** — separate read/write/admin roles; MFA-sensitive ops; granular field-level consent
3. **Independent oversight + defined retention** — formal privacy protocols; data monitoring committees; auto-delete after fixed window
4. **Explicit consent + transparency** — clear privacy notice; opt-out mechanism; subjects can request access/correction/deletion

---

## ClinicalTrials.gov Search Methodology

- **Query terms:** `patient data privacy`, `data privacy`, `privacy education`, `privacy protection`, `de-identification`, `data security management`
- **Filters:** `overallStatus` across COMPLETED, NOT_YET_RECRUITING, RECRUITING
- **Tools:** `clinicaltrials_list_studies`, `clinicaltrials_get_study`, `clinicaltrials_analyze_trends`
- **Verified:** 8 studies with complete protocol sections; all NCT IDs confirmed real

---

## Portland Workshop & Meetup Venues (verified via OpenStreetMap)

All venues within ~2 km of downtown Portland city center.

| Venue | Type | Best For | Address |
|-------|------|----------|---------|
| **Central Library** | Library | Free workshops & quiet collaboration | 801 SW 10th Ave, Downtown |
| **Portland Art Museum** | Museum / Event Space | Professional meetups | 1219 SW Park Ave, University District |
| **Oregon Convention Center** | Conference Center | Large-scale summits | 777 NE MLK Jr Blvd, Lloyd District |
| **Revolution Hall** | Events Venue | Themed community events | 1300 SE Stark St, Buckman |
| **Soho House Portland** | Private Club / Community Centre | Intimate member meetups | 1025 SE Pine St, Buckman |
| **Pacific Northwest College of Art** | College / Event Space | Art + security crossover events | 511 NW Broadway, Pearl District |
| **Oregon Historical Society** | Museum / Event Space | History-infused security talks | 1200 SW Park Ave, University District |
| **YWCA Portland** | Association / Community Space | Inclusive community events | 1111 SW 10th Ave, Downtown |

**Top Recommendations:**
- **Regular workshops:** Central Library (public, free, MAX-accessible, event rooms)
- **Professional talks:** Portland Art Museum (downtown, secure, credible)
- **Large summits:** Oregon Convention Center (300K+ sq ft, light rail accessible)
- **Themed events:** Revolution Hall (historic venue, ~600 capacity)
- **Intimate meetups:** Soho House Portland (private club, event rooms)
- **Inclusive/equity events:** YWCA Portland (established social justice hub)

---

## Getting Started

1. Clone the repo and review the Privacy Takeaways
2. Pick a Portland venue from the recommendations
3. Plan your first workshop using the agenda template
4. Contribute case studies, templates, or venue reviews

---

## License

Open-source project. Check individual file licenses.
