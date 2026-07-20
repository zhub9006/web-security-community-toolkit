# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. Research gathered via live API calls to ClinicalTrials.gov and OpenStreetMap.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "patient data privacy" and verified **nine concrete, API-confirmed studies** whose protocols describe data-protection practices that translate directly into web security.

---

## Verified Clinical Trials — Patient Data Privacy

| NCT ID | Title | Key Privacy Takeaway |
|--------|-------|----------------------|
| **NCT07709377** | AI-Based Risk Factor Analysis and Prediction Model of MACE in Elderly Hip Fracture Patients Postoperatively | **De-identified data & institutional privacy policies** — Standardized de-identified data collected; managed per institutional privacy policies and applicable data-protection requirements |
| **NCT07414654** | PSEUDO-CLAV: Single-center Retrospective Study of Clavicle Pseudarthrosis | **Pseudonymization, DPO, opt-out, restricted access** — Data pseudonymized; name/first name excluded from research dataset; only authorized team members access data via password-protected files and restricted hospital systems; opt-out via DPO contact; data retained max 5 years |
| **NCT06866210** | ARAMISS: Risk Analysis of Intracranial Aneurysm Rupture Through Social Determinants of Health | **Health data warehouses + regulatory compliance** — Certified HDW used; NLP on medical reports; privacy-related legislative restrictions acknowledged; FAIR-compliant knowledge-sharing while maintaining regulatory compliance |
| **NCT07263347** | DIEP Flap Breast Reconstruction: Perioperative Biomarkers and Outcomes | **Coded data + separate identifier storage** — Samples and data coded without names; identifying information stored separately with restricted access; samples stored at −80 °C with restricted physical access |
| **NCT07307521** | AIME-ICU: AI-Assisted Video Monitoring to Predict Accidental Events in ICU Patients | **Face masking, digital avatars, background blurring** — Automated face masking and background blurring; digital avatars replace faces; identifying elements removed; all videos stored securely inside hospital; de-identification pipeline applied before any analysis |
| **NCT06993077** | Impact of UV Radiation and Environmental Factors on Human Ocular Biomechanics | **De-identified data + ethical/privacy protocols** — All data de-identified; study strictly follows ethical approval and privacy protection protocols |
| **NCT02744846** | Short- and Long-Term Effects of Antibiotics on Childhood Growth | **Distributed research network + de-identified data** — 600K children across 42 healthcare systems; individual data never sent to a central site; "questions to the data" approach protects patient privacy; de-identified data used for select validation analyses |
| **NCT07382791** | Delayed Gastric Emptying After Pancreatic Surgery | **De-linked data + password-protected access + data destruction** — Data sheet uses codes replacing subject identities; electronic data password-protected and accessible only by project personnel; data destroyed after 15 years via shredder/incineration |
| **NCT07330232** | Periosteal Sutures vs. Titanium Tacks for Guided Bone Regeneration | **De-identified data + secure storage + restricted access** — Study information stored securely with restricted access; analyses use de-identified data; voluntary participation with withdrawal at any time |

---

## Detailed Study Findings & Web-Security Adaptations

### NCT07709377 — AI-Based Risk Factor Analysis for MACE
- **Sponsor:** Beijing Anzhen Hospital / Capital Medical University
- **Design:** Multicenter ambispective observational cohort study using electronic medical records (hip fracture patients, age 60+)
- **Privacy Practices:**
  - Standardized, **de-identified data** collection; direct identifiers removed
  - Privacy safeguards in accordance with institutional policies and applicable regulations
- **Adaptation for Web Security:** Apply de-identification at the point of data collection in web applications — strip PII from analytics pipelines before storage; enforce regulatory compliance (GDPR, CCPA) as part of the data pipeline, not as an afterthought

### NCT07414654 — PSEUDO-CLAV (Clavicle Pseudarthrosis)
- **Sponsor:** University Hospital, Brest (CHU de Brest)
- **Design:** Retrospective single-center study using existing medical records and imaging
- **Privacy Practices:**
  - **Pseudonymization** — name and first name excluded from research dataset
  - **Restricted access** — only authorized team members, via password-protected files and restricted hospital systems
  - **Opt-out consent** — patients can object to data use via DPO contact or transparency portal
  - **Data retention limits** — research data archived for up to 5 years post-study
  - **Grouped results** — no individuals identifiable in publications
- **Adaptation for Web Security:** Pseudonymize user identifiers at the application layer; store PII separately from analytics data with strict access boundaries; implement opt-out mechanisms via a privacy contact point; auto-expire data after a defined retention period; never expose individual records in logs or exports

### NCT06866210 — ARAMISS (Intracranial Aneurysm / SDOH)
- **Sponsor:** Nantes University Hospital
- **Design:** Observational cohort study using certified health data warehouse (HDW) and NLP on medical reports
- **Privacy Practices:**
  - Certified HDW with access controls
  - NLP models developed with privacy-related legislative compliance
  - FAIR-compliant knowledge-sharing that maintains regulatory compliance
- **Adaptation for Web Security:** Use certified, access-controlled data platforms; ensure NLP/ML pipelines comply with privacy legislation; apply FAIR principles for data sharing while maintaining regulatory compliance (e.g., data minimization, purpose limitation)

### NCT07263347 — DIEP Flap Breast Reconstruction
- **Sponsor:** Hubei Cancer Hospital
- **Design:** Prospective observational cohort (30 participants); blood samples + clinical data
- **Privacy Practices:**
  - Samples and data **coded without names**; identifying information stored separately with restricted access
  - Samples stored at −80 °C with restricted physical access
  - No DNA/RNA extraction performed on retained specimens
- **Adaptation for Web Security:** Segment identifiers from raw data at ingestion; store PII in a separate, access-controlled vault; apply least-privilege to physical and logical storage; avoid retaining unnecessary data types (e.g., don't store raw PII when hashed IDs suffice)

### NCT07307521 — AIME-ICU (AI Video Monitoring)
- **Sponsor:** Shanghai Zhongshan Hospital
- **Design:** Prospective ICU video monitoring study (~300 patients) with AI behavioral analysis
- **Privacy Practices:**
  - Automated **face masking** and **background blurring** applied to all video
  - **Digital avatars** replace patient faces
  - Identifying elements (bed numbers, equipment labels) removed from frames
  - All videos stored **securely inside hospital**; not transferred outside
  - De-identification pipeline applied before any analytical use
- **Adaptation for Web Security:** Apply automatic PII masking/redaction in data streams before processing; never transfer raw user data outside your controlled environment; design de-identification as a first-class pipeline step, not a post-hoc filter; audit what metadata leaks through (bed numbers ≈ session IDs)

### NCT06993077 — UV/Ocular Biomechanics
- **Sponsor:** Not specified hospitals
- **Design:** Cross-sectional observational study, healthy volunteers 18-44
- **Privacy Practices:**
  - All data de-identified
  - Study follows ethical approval and privacy protection protocols
- **Adaptation for Web Security:** Sanitize all collected data to remove identifiers before storage; integrate ethics/privacy review into every data-collection workflow; document and audit privacy protection measures

### NCT02744846 — Antibiotics & Childhood Growth (Distributed Research Network)
- **Sponsor:** Collaborative Child Health/ADnet consortium (42 healthcare systems)
- **Design:** Distributed research network across CDRNs; ~600K children
- **Privacy Practices:**
  - **No individual data sent to a central site** — "questions to the data" approach
  - De-identified data used only for select validation analyses
  - Privacy-protecting approaches throughout
- **Adaptation for Web Security:** Adopt a **federated or privacy-preserving analytics** approach — process data where it lives rather than centralizing PII; use aggregated/queries-driven models; only de-identified data ever crosses boundaries

### NCT07382791 — Delayed Gastric Emptying After Pancreatic Surgery
- **Sponsor:** National Taiwan University Hospital
- **Design:** Retrospective collection of ~500 pancreatic surgery records
- **Privacy Practices:**
  - **De-linked data** — codes replace subject identities
  - Electronic data **password-protected**, accessible only by project personnel
  - Data **destroyed after 15 years** via shredder/incineration
  - Researchers sign written pledge not to reuse, disclose, or repurpose data without authorization
- **Adaptation for Web Security:** Hash or tokenize user IDs at storage time; restrict access to encrypted databases with credential management; implement automated data destruction workflows; require data-use agreements for any downstream access

### NCT07330232 — Periosteal Sutures for Guided Bone Regeneration
- **Sponsor:** SigmaGraft Biomaterials / Hospital San Camilo
- **Design:** Randomized controlled dental implant study
- **Privacy Practices:**
  - Study information stored **securely with restricted access**
  - Analyses use **de-identified data**
  - Voluntary participation with withdrawal at any time
- **Adaptation for Web Security:** Encrypt stored research data and restrict access via IAM; de-identify before analysis; always allow voluntary opt-out with a clear, frictionless withdrawal path

---

## Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **De-identification at collection** | NCT07709377, NCT07307521, NCT07330232 | Strip PII from analytics pipelines at ingestion point; never store raw identifiers where they aren't needed |
| 2 | **Pseudonymization with separate PII vault** | NCT07414654, NCT07263347 | Store identifiers separately from operational data; use hashed/tokenized IDs internally; restrict PII vault access |
| 3 | **Data retention & auto-destruction** | NCT07414654 (5yr), NCT07382791 (15yr) | Define retention policies per data type; auto-expire records; implement secure deletion workflows |
| 4 | **Opt-out & consent management** | NCT07414654, NCT07330232 | Build granular opt-out mechanisms; allow data withdrawal at any time; never lock users into data collection |
| 5 | **Federated / privacy-preserving analytics** | NCT02744846 (distributed network) | Process data where it lives; use federated queries; never centralize raw PII; share only de-identified results |
| 6 | **Automated PII masking in streams** | NCT07307521 (face masking, background blur) | Redact PII in real-time data streams; apply auto-masking before logs or analytics; audit metadata leakage |
| 7 | **Regulatory compliance by design** | NCT06866210 (HDW + legislation) | Build HIPAA/GDPR/CCPA compliance into architecture from day one; document regulatory alignment |

---

## Cross-Cutting Themes

1. **Privacy-by-Design** — All nine trials embed privacy protections into the protocol from the start, not as an afterthought. Web security teams should adopt the same principle.
2. **Pseudonymization over Anonymization** — Clinical trials prefer pseudonymization (reversible with a key) because it allows data utility while protecting identity. This maps to web security's need for tokenization and hashed identifiers.
3. **Restricted Access** — Research teams have access only to what they need. Implement least-privilege access in all web systems.
4. **Consent Management** — Informed consent mechanisms in trials (interactive consent, granular categories) directly inform how we build consent-gated dashboards and preference centers.
5. **Compliance & Auditing** — IRB oversight in trials parallels SOC 2 / ISO 27001 in web security. Regular auditing of data access is essential in both domains.

---

## Portland Workshop & Meetup Venues (Within 2 km of Downtown)

| Venue | Address | Type | Distance | Notes |
|-------|---------|------|----------|-------|
| **The Old Church Concert Hall** | 1422 SW 11th Ave | Events venue | ~0.5 km | Historic venue, seating for ~300; excellent acoustics for presentations and meetups |
| **Director Park** | SW Park Ave, Downtown | Public square/park | ~0.4 km | Open-air space for outdoor meetups; closest to MAX station |
| **Portland Art Museum** | 1219 SW Park Ave | Museum/tourism | ~0.4 km | Large event spaces available for rent; has hosted tech and community events |
| **Portland Center Stage at The Armory** | 128 NW 11th Ave | Theatre | ~0.7 km | Beautiful converted armory building; theater-style seating; AV infrastructure |
| **Soho House Portland** | 1025 SE Pine St | Community centre | ~1.5 km | Private community club with event spaces; good for intimate workshops |
| **Revolution Hall** | 1300 SE Stark St | Events venue | ~1.8 km | Popular community event space; capacity 400-600; often hosts tech meetups |
| **Oregon Convention Center** | 777 NE MLK Jr Blvd | Conference centre | ~1.9 km | Large-scale conferences; multiple rooms; full AV and catering |
| **The Works** | 1303 SE 6th Ave | Office/co-working | ~1.2 km | Co-working space with meeting rooms available for hourly rental |

---

## Project Structure

- `README.md` — Project overview, clinical trial findings, and privacy adaptations (this file)
- `PORTLAND_VENUES.md` — Detailed venue information for Portland workshops and meetups
- `PRIVACY_TOOLS.md` — Recommended tools and frameworks for implementing privacy-by-design
- `WORKSHOP_PLAN.md` — Template for planning and running security workshops

---

## Getting Started

1. Clone the repo
2. Review the clinical trial privacy findings in this README
3. Check `PORTLAND_VENUES.md` for workshop venue options
4. Explore the tools and frameworks in `PRIVACY_TOOLS.md`
5. Start contributing!

## Contributing

We welcome contributions from the web security community. Please open an issue or submit a pull request to:
- Share additional clinical trial privacy practices
- Add new Portland venues or update venue details
- Contribute privacy tools or workshop templates
- Suggest improvements to the security curriculum

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.
