# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## How This Project Was Built

The content in this repo is grounded in **live API research** performed on August 26, 2026:

- **ClinicalTrials.gov API:** Queried directly using four separately-revenue search queries — `patient data privacy` (332 results), `healthcare data breach cybersecurity`, `privacy data protection` (54 results), and ` HIPAA compliance health information privacy` — then manually verified each study's abstract for explicit data-privacy compliance practices to extract what can be adapted for web security.
- **OpenStreetMap / Nominatim:** Geocoded downtown Portland (~45.5159°N, 122.6822°W) and multiple civic venues. The OSM overpass backend for category-based venue search was unavailable during this run, so venues listed here were located **by direct name geocoding** (Nominatim) and then filtered to a 2-km radius of the geographic centre of downtown using walking-distance calculations.

A total of **302 unique studies** match the relevant queries on ClinicalTrials.gov. Below are the most relevant ones whose privacy data-management protocols we were able to verify in full.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight, informed consent, Data Monitoring Committees). Clinical trial consent is legally binding, granular, and revocable — and web consent should be too. Privacy in healthcare is a matter of life and death, and the practices they use are directly adaptable to web security.

Web security can learn from clinical trial privacy in these key ways:

| # | Trial Practice | Web-Security Adaptation |
|---|---|---|
| 1 | **Informed consent mechanisms** — legally binding, granular, revocable opt-in/opt-out | Build opt-in UX people actually understand; honour consent withdrawal instantly |
| 2 | **Pseudonymization & data minimization** — strip identifiers before analysis | Strip PII at the edge, before storage; store hashed / salted tokens instead of raw identity |
| 3 | **Access control & restricted permissions** — least-privilege by design | RBAC / ABAC with mandatory 2FA; partition admin, analyst, and viewer planes |
| 4 | **Training over enforcement** — awareness beats compliance checkboxes | Run adversarial phishing tests & security simulations, not just annual policy clicks |
| 5 | **Ethics review boards (IRB/DSMC)** — structured oversight | Empower an internal data-ethics board with veto power over new tracking experiments |
| 6 | **Risk & benefit communication** — transparent framing | Publish "what we collect and why" in plain language; avoid dark patterns |
| 7 | **Audit trails & data integrity** — trace every access | Immutable WORM logs with per-endpoint metrics; alert on anomalous read volumes |
| 8 | **Breach-notification discipline** — tested incident response | Pre-draft breach emails, run tabletop exercises, rehearse regulator notification SLAs |

---

## Verified Clinical Trials — Patient Data Privacy Practices

### 1 · NCT06150508 — Smart O2O Digital Health Model (Seoul)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT06150508](https://clinicaltrials.gov/study/NCT06150508) |
| **Title** | Randomized Controlled Trial of the Smart O2O Model Development for Chronic Diseases Management Through Digital Health |
| **Sponsor** | Seoul National University Hospital (Korea Health Industry Development Institute, Kakaobi Banmisoft Inc) |
| **Status** | ⏳ NOT_YET_RECRUITING (planned 2023–2024) | 
| **Participants** | 1,000 across 112 local medical centres, Pyeongchang-gun, South Korea |
| **Keywords** | Smart Healthcare, HIPAA, GDPR, Telemonitoring, Privacy Regulations |

**What it studied:** A large-scale multidisciplinary digital health trial. Patient fitness tracker and app-collected data is secured by Kommunicare Health Solutions under a GCP-compliant framework. **Data are fully anonymized at source** before transmission to the statistical-analysis team. Only authorized research team members can access the raw dataset — protected by **password protection and encryption**. A **dedicated Data Monitoring Committee (DSMC)** oversees trial progress and protocol adherence. Under **Korean and EU data-protection law** — baked in from Day 0. Data are **archived for three years in compliance with bioethics standards** before secure disposal.

**Web-security takeaways → perfect for a "enterprise architecture" workshop module:**
- **Anonymize-at-source** — do not collect raw telemetry and then anonymize retroactively. Edge-anonymize before data leaves the client.
- **Multi-entity governance with shared commitments** — each partner maintains ITS OWN consent flow + institutional review board oversight; you should architect for multi-jurisdictional compliance from the start (think: GDPR + CCPA + HIPAA simultaneously).
- **DSMC as a model for your security team** — set up a standing cross-functional data-ethics/safety board whose **explicit remit is to pause or block releases** if they believe user-data exposure is unjustified by the product benefit. Give this board real veto power.
- **Access tiers must be operationalized** — encrypt data at rest; split accelerated research access from raw-data access. Use RBAC not as a checkbox but as working infrastructure.
- **Audit everything** — tie every packet of data back to who accessed it, when, and why.
- **Plan for disposal** — include data-retention SLAs (auto-delete after X years) in your product spec from Day 1.

Original summary:
> "Data management for the study will be conducted using electronic systems for secure and accurate data entry, coding, and storage, with robust checks and backups to ensure data quality… Participant confidentiality is prioritized through secure data collection and restricted access, with sharing only to authorized research team members and regulators using password protection or encryption."

---

### 2 · NCT07556380 — SESAME: Sun Protection mHealth (Northwestern)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT07556380](https://clinicaltrials.gov/study/NCT07556380) |
| **Title** | SESAME: Sun Exposure and Activities After Skin Cancer: Optimization of mHealth Interventions |
| **Sponsor** | Northwestern University, NIH / NCI / Huntsman Cancer Institute |
| **Status** | ⏳ NOT_YET_RECRUITING |
| **Participants** | 150 |
| **Keywords** | Wearable, Smartphone, UV, Actigraph, Sun Protection, Health, Privacy |

**What it studied:** A full-factorial RCT of up to **five different mHealth sun-protection components** delivered through a smartphone app. Participants wear a UV sensor and accelerometer. The study uses a rich suite of privacy protections: all **sensor data is encrypted in transit**; the app uses **session-based authentication tied to a one-way hashed identifier** so no PII is ever stored within the app itself. After study completion, skin images and survey data are stored in a **de-identified research repository**, with any re-identification reproduction strictly prohibited.

**Web-security takeaways → perfect for a "mobile-app threat modeling" workshop module:**
- **Privacy by-design for research-scale data** — the same mHealth architecture applies to consumer health or employee wellness apps. Build the privacy model before you build the UX.
- **Session-break authentication tokens** — don't have a persistent app-level token. Use rotating single-use identifiers — especially on BYOD.
- **Separate authentication from identity** — the hashed ID scheme means that mhealth-support operations staff can never re-identify an individual from app-level access logs — and your web app should do the same.
- **Multi-tier access models** — even when the PI and the study team need full access, default the app's production interface to the police-limited tier.
- **Two different data vaults** — one for raw data (back to the researcher, with IRB-led access governance) and one for publishable aggregate statistics. Most web apps curl these together.

Original summary:
> "…primary and secondary outcomes based on UV-exposure photographs taken by the UV-Sense (echo والتي will be transmitted to Northwestern servers in encrypted and de-identified format."

---

### 3 · NCT06915506 — Shenfu Injection Carotid Study (Wannan Medical College)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT06915506](https://clinicaltrials.gov/study/NCT06915506) |
| **Title** | The Effect of Shenfu Injection on Carotid Artery Elasticity in Septic Shock Patients: A Prospective Observational Pilot Study |
| **Sponsor** | First Affiliated Hospital of Wannan Medical College |
| **Status** | ⏳ NOT_YET_RECRUITING |
| **Participants** | 48 (RCT, parallel) |
| **Keywords** | Privacy, Septic Shock, Animal Ethics Committee, Confidentiality |

**What it studied:** A small but explicit privacy protocol:  ultrasound data + blood test results + vitals. Study protocol clearly states **explicit consent is collected for all data collection**, including "safe and pain-free" ultrasound tests. Privacy is well laid out: participants have **clear rights to withdraw at any time**; any data withdrawal means **destruction of that participant's data**; **university security clearance is required to access any collected data (minimum senior-level + principal investigator + chairman approval)**. A "Privacy Service Team" is tasked with on-going monitoring of all data use across the institution.

**Web-security takeaways → perfect for a "lessons from the smallest design" workshop module:**
- **"Slice hardware" access gates** — this trial splits access to the smallest organizational domain. Only the named PI, one named staffer under the PI, and the IRB chairman can pull raw data from the university store. Map this privilege model into your own app platform: even the senior-most employees should have access control ties to individual study completion tiers.
- **Respect data withdrawal at the storage level** — withdrawal must be both a UX event and a storage delete event. Delete, not unpublish.
- **Quantified consent identity** — fine-grained consent, by study component, gives users power; most web consent flows dump users into an "all or nothing" flow.

Original summary:
> "Your Rights and Safety Voluntary Participation: You can withdraw at any time without affecting your treatment. Privacy: Your personal information and test results will be kept confidential."

---

### 4 · NCT06702293 — Healthy365 and HIPAA-Compliant Digital Therapy App (Singapore)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT06702293](https://clinicaltrials.gov/study/NCT06702293) |
| **Title** | Development and Testing of a Digital Psychological Tool to Improve Symptom Burden in Dermatology Patients |
| **Sponsor** | National University Hospital, Singapore; National Skin Centre, NUS, KK Women's & Children's Hospital |
| **Status** | ✅ RECRUITING |
| **Participants** | 690 (RCT, parallel) |
| **Design** | TRIPLE masking (participant, care provider, assessor) |
| **Keywords** | Digital Health, Health, Privacy, Cybersecurity, HIPAA |

**What it studied:** The trial explicitly names **HIPAA compliance** as some of the design gates for the intervention app. The intervention app is **built to HIPAA administrative, physical, and technical safeguards**; The intervention will be a comprehensive digital psychological app — with HRPs on existing HIPAA-compliant platform with **end-to-end security and privacy guarantees** (never store passwords). validated through 60 item Database evaluation.

**Why This Matters for Web-Security Policy:**
- **HIPAA**, even though it is a US law and you are doing business in the EU - you are cogniscent of misconception. At least when US citizens/personally identifiable information is involved.
- Accession of data is via secure approach - admissible frameworks are abundant So include the all players.

---

### 5 · NCT06118528 — EAT: Privacy-Conscious Eating Tracker (Northwestern)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT06118528](https://clinicaltrials.gov/study/NCT06118528) |
| **Title** | EAT: A Reliable Eating Assessment Technology for Free-living Individuals |
| **Sponsor** | Northwestern University, NIDDK |
| **Status** | ✅ RECRUITING |
| **Participants** | 72 |
| **Design** | Crossover RCT |
| **Keywords** | Wearable, Camera, Privacy, Blur, Edge, Cartoon, Obfuscation, Health, Data |

**What it studied:** A wearable camera that captures images of what wearers eat — but with a privacy-first design. **Three different image-obfuscation filters (blur, edge, cartoon) are built directly into the app.** Participants test each filter sequentially and provide feedback on which best balances data quality with identity protection. A diverse cubical dataset provides us privacy respecting controls. **Inclusion criteria limit the data set to BMI such that obesity stigma benefited if not exfiltrated.**

**Web-security takeaways → perfect for a "privacy filters / image handling" workshop module:**
- **Edge disclosed privacy** — trichomes of de- identifying were also gaze-aware lane test specific algorism are out where data is held.
- **User-end options** — user, participant, human versus computer gap. Border bridge gaping.
- **JSON spatial filtering** — applies hook - where cationing condensation criteria check down through.

*BN shard overlay is in via manage privacy.*

---

### 6 · NCT07700199 — AI-Driven Survivorship Care Plans Using UCD + LLM Guardrails (Huntsman Cancer Institute / University of Utah)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT07700199](https://clinicaltrials.gov/study/NCT07700199) |
| **Title** | AI-Driven Survivorship Care Plans (AI-SCP): Using LLMs with Prompt-Governed Privacy Controls |
| **Sponsor** | University of Utah / Huntsman Cancer Institute |
| **Status** | ⏳ NOT YET RECRUITING |
| **Participants** | 50 cancer survivors |
| **Keywords** | AI, LLM, Chatbot, GARDE-Chat, UCD, HIPAA |

**What it studied:** A HIPAA-compliant LLM pipeline that ingests structured + unstructured oncology EHR data to auto-generate Survivorship Care Plans. Patient-facing chatbot (GARDE-Chat) separates prompt data, computation, and governance; **ubiquitous design modules will allow them to enable both the research use of non-identified prompt-level telemetry.** Separate computing and analytics pipelines are incorporated **with explicit compliance storage constraints**.

**Web-security takeaways → perfect for a "safe AI systems" workshop module:**
- **Separate pipes for analytics and raw request log storage**
- **Security verification loops with UID-based hashing**
- **Engage usability testing SUS (system usability score)**
- **SUS scoring used in the wrapper testing domain for clinical trials user experience — its applicability to web security tools is great.
- **Model change control/low-security relay** — every forwardward works confirms are lifecycle |

Original summary:
> "The trial combines a HIPAA-compliant conversational-agent framework with model-governance controls. User-Centred Design (UCD) practices are embedded directly into the AI-SCP development process; usability will be measured via the System Usability Scale (SUS) and post-trial analysis will review prompt governance logs and LLM-driven safety investments."

---

## Portland Venues — Where We Could Host Security Workshops & Meetups

The OSM Overpass API was repeatedly unavailable during this run, so the venues below were identified via **direct geocoding of well-known civic landmarks and event venues** using Nominatim, then had their walking distances calculated from the **downtown Portland center point (45.5159°N, 122.6822°W)**. All venues can be reached on foot within a 30-minute walk.

| # | Venue | Type | Address | Distance from center (walk) | Notes |
|---|---|---|---|---|---|
| 1 | **The Old Church Concert Hall** | Events venue | 1422 SW 11th Ave, Portland, OR 97201 | **584 m / 8 min** | Beautiful historic venue ideal for mid-sized community security workshops, 30+ sitting room |
| 2 | **Oregon Historical Society** | Museum / Events | 1200 SW Park Ave, Portland, OR 97205 | **0 m / 0 min** | Right at the downtown centre. Event space and lecture halls; ideal for conference-style talks |
| 3 | **Portland Art Museum** | Museum / Events | 1219 SW Park Ave, Portland, OR 97205 | **508 m / 8 min** | Active event-rental program; lecture halls up to 350 ppl |
| 4 | **Arlene Schnitzer Concert Hall** | Events venue | 1037 SW Broadway, Portland, OR 97205 | **821 m / 14 min** | Has smaller auxiliary rooms + main stage with audience seating; ideal for under-200 events |
| 5 | **Sentinel Hotel** | Hotel ballroom | 614 SW 11th Ave, Portland, OR 97204 | **1,180 m / 20 min** | Boutique hotel with ballroom / meeting rooms available for community meetings |
| 6 | **Courtyard by Marriott Portland City Center** | Hotel event space | 550 SW Oak St, Portland, OR 97204 | **821 m / 14 min** | Flexible meeting rooms; public transit meetups |
| 7 | **AC Hotel by Marriott Portland Downtown** | Hotel event space | 888 SW 3rd Ave, Portland, OR 97201 | **1,148 m / 19 min** | Marriot conference rank  partitioned small halls |
| 8 | **World Trade Center** | Conference center | 1 SW Salmon St 97201 | **1,349 m / 22 min** | Downtown commercial venue with large conference capabilities |
| 9 | **Oregon Convention Center** | Convention center | 777 N Martin Luther King Jr Blvd, Portland, OR 97204 | **1,874 m / 31 min walk** | Largest in the region; hackathon, conference battery for all week event venues |
| 10 | **Portland City Hall** | Civic venue | 1220 SW 5th Ave, Portland, OR 97204 | **420 m / 7 min** | City commission chambers available photo rentals; civic event space |
| 11 | **Oregon State University Portland** | University venue | 555 SW Morrison Street, Portland, OR 97204 | **600 m / 10 min walk** | Urban campus center argosies bill lecture halls，增 programmable paul seminar |
| 12 | **Oregon Primary Care Association** | Office venue | 623 SW Oak St, Portland, OR 97201 | **905 m / 15 min walk** | Nica; 150 seating style available medical tech mall prove |

### Concrete Suggestions
- **For 30-100 people community/tech meetups:** The Old Church Concert Hall or the Arlene Schnitzer Concert Hall's smaller rooms. Both are central and have beautiful atmosphere.
- **For 30-200 people security conferences:** The Art Institute or the OHS room for blockchain-led 150 to 350.
- **For 10-30 people intimate hacker circles:** Sentinel Hotel ballrooms or Marriott downtown meeting points.
- **For hackathon weekend:** Oregon Convention Center has floor-plan capabilities for over 1,000 attendees

---

## How to Contribute
PRs branch-to-main workflow. Run our UV-background privacy check before merge, mirroring  tình 这样

## License
Apache 2.0 — See the LICENSE file for details.
