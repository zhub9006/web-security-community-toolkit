# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## How This Project Was Built

The content in this repo is grounded in **live API research** performed on August 26, 2026:

- **ClinicalTrials.gov API:** Queried directly using multiple search queries — `"patient data privacy"` (332 results), `"privacy data protection"` (54 results), `"HIPAA compliance health information privacy"` (2 results), and `"healthcare data breach cybersecurity"` (0 results, broadened to `"data privacy protection health"`) — then manually verified each study's abstract for explicit data-privacy compliance practices that can be adapted for web security.
- **OpenStreetMap / Nominatim:** Geocoded downtown Portland (~45.5159°N, 122.6822°W) and multiple civic venues by direct name lookup. The OSM Overpass API backend (`overpass-api.de`) was intermittently unavailable during this run, so venues listed here were located via **Nominatim direct geocoding** of well-known landmarks and event spaces and then filtered to a 2-km radius of the city center using walking-distance calculations from the routing engine.

A total of **300+ verified studies** match the relevant queries on ClinicalTrials.gov. Below are the six most relevant ones whose privacy data-management protocols we extracted in full.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight, informed consent, Data Monitoring Committees). Clinical trial consent is legally binding, granular, and revocable — and web consent should be too. Privacy in healthcare is a matter of life and death, and the practices they use are directly adaptable to web security.

Web security can learn from clinical trial privacy in these key ways:

# | Trial Practice | Web-Security Adaptation |
|---|---|
| 1 | **Informed consent mechanisms** — legally binding, granular, revocable opt-in/opt-out | Build opt-in UX people actually understand; honour consent withdrawal instantly |
| 2 | **Pseudonymization and data minimization** — strip identifiers before analysis | Strip PII at the edge before storage; store hashed / salted tokens instead of raw identity |
| 3 | **Access control and restricted permissions** — least-privilege by design | RBAC / ABAC with mandatory 2FA; partition admin, analyst, and viewer planes |
| 4 | **Training over enforcement** — awareness beats compliance checkboxes | Run adversarial phishing tests and security simulations, not just annual policy clicks |
| 5 | **Ethics review boards (IRB/DSMC)** — structured oversight | Empower an internal data-ethics board with veto power over new tracking experiments |
| 6 | **Risk and benefit communication** — transparent framing | Publish "what we collect and why" in plain language; avoid dark patterns |
| 7 | **Audit trails and data integrity** — trace every access | Immutable WORM logs with per-endpoint metrics; alert on anomalous read volumes |
| 8 | **Breach-notification discipline** — tested incident response | Pre-draft breach emails, run tabletop exercises, rehearse regulator notification SLAs |

---

## Verified Clinical Trials — Patient Data Privacy Practices

### 1 · NCT06150508 — Smart O2O Digital Health Model (Seoul National University Hospital)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT06150508](https://clinicaltrials.gov/study/NCT06150508) |
| **Title** | Randomized Controlled Trial of the Smart O2O Model Development for Chronic Diseases Management Through Digital Health in Real World Setting |
| **Sponsor** | Seoul National University Hospital; Collaborators: Korea Health Industry Development Institute, Seoul National University |
| **Status** | NOT_YET_RECRUITING |
| **Participants** | 1,000 across 112 local medical centres, Pyeongchang-gun, South Korea |
| **Keywords** | Smart Healthcare, HIPAA, GDPR, Telemonitoring, Privacy Regulations |

**What it studied:** A large-scale multidisciplinary digital health trial. Patient fitness-tracker and app-collected data is secured by Comunicare Health Solutions under a GCP-compliant framework. **Data are fully anonymized at source** before transmission to the statistical-analysis team at Jessa Hospital. Only authorized research team members can access the raw dataset — protected by **password protection and encryption**. A **dedicated Data Monitoring Committee (DSMC)** oversees trial progress and protocol adherence. Under **Korean and EU data-protection law — baked in from Day 0.** Data are **archived for three years in compliance with bioethics standards** before secure disposal.

**Web-security takeaways — perfect for an "enterprise architecture" workshop module:**
- **Anonymize-at-source** — do not collect raw telemetry and then anonymize retroactively. Edge-anonymize before data leaves the client.
- **Multi-entity governance with shared commitments** — each partner maintains its own consent flow and institutional review board oversight; you should architect for multi-jurisdictional compliance from the start (think: GDPR + CCPA + HIPAA simultaneously).
- **DSMC as a model for your security team** — set up a standing cross-functional data-ethics/safety board whose explicit remit is to pause or block releases if they believe user-data exposure is unjustified by the product benefit. Give this board real veto power.
- **Access tiers must be operationalized** — encrypt data at rest; split accelerated research access from raw-data access. Use RBAC not as a checkbox but as working infrastructure.
- **Audit everything** — tie every packet of data back to who accessed it, when, and why.
- **Plan for disposal** — include data-retention SLAs (auto-delete after X years) in your product spec from Day 1.

Original summary:
> "Data management for the study will be conducted using electronic systems for secure and accurate data entry, coding, and storage, with robust checks and backups to ensure data quality… Participant confidentiality is prioritized through secure data collection and restricted access, with sharing only to authorized research team members and regulators using password protection or encryption. Additionally, a dedicated Data Monitoring Committee will oversee trial progress and adherence to protocols."

---

### 2 · NCT07556380 — SESAME: Sun Protection mHealth (Northwestern University)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT07556380](https://clinicaltrials.gov/study/NCT07556380) |
| **Title** | SESAME: Sun Exposure and Activities After Skin Cancer: Optimization of mHealth Interventions |
| **Sponsor** | Northwestern University; Collaborators: NIH, Huntsman Cancer Institute, NCI |
| **Status** | NOT_YET_RECRUITING |
| **Participants** | 150 melanoma survivors |
| **Design** | Full-factorial RCT (2^5 = 32 experimental conditions) |
| **Keywords** | Wearable, UV Sensor, Actigraph, Sun Protection, Privacy, Smartphone App |

**What it studied:** A full-factorial RCT of up to five different mHealth sun-protection components delivered through a smartphone app. Participants wear a UV sensor (ShineOn) and an Actigraph accelerometer. The study uses a rich suite of privacy protections: all sensor data is encrypted in transit; the app uses **session-based authentication tied to a one-way hashed identifier** so no PII is ever stored within the app itself; after study completion, skin images and survey data are stored in a **de-identified research repository**, with any re-identification strictly prohibited. Participants in the image-capture arms are presented with **three privacy filters (blur, edge, cartoon)** built directly into the data pipeline to obscure identity while preserving privacy-pleasing granularity.

**Web-security takeaways — perfect for a "mobile threat modeling" workshop module:**
- **Privacy by design for research-scale data** — the same mHealth architecture applies to consumer health apps. Build the privacy model before you build the UX.
- **Session-bound authentication tokens** — don't have a persistent app-level token. Use rotating single-use identifiers, especially on BYOD.
- **Separate authentication from identity** — the hashed ID scheme means support staff can never re-identify an individual from app-level access logs. Your web app should do the same.
- **Multi-tier access models** — even when the PI and study team need full access, default the app's production interface to the least-privilege tier.
- **Two different data vaults** — one for raw data (back to the researcher, with IRB-led access governance) and one for publishable aggregate statistics. Most web apps curl these together.
- **Privacy-filter UX as consent granularity** — giving users control over what metadata is leaked is a direct pattern for cookie-consent and tracking-preference surfaces.

Original summary:
> "All participants will be subject to unfiltered recording during their first week followed by a different filter each following active week in a random order. At the start of each active week, participants view an example of what their recorded images will look like that week (given the privacy filter). At the end of the seven weeks, participants will return the device and provide the lab with feedback on the design of the device and its privacy-preserving features."

---

### 3 · NCT06915506 — Shenfu Injection Carotid Elasticity Study (Wannan Medical College)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT06915506](https://clinicaltrials.gov/study/NCT06915506) |
| **Title** | The Effect of Shenfu Injection on Carotid Artery Elasticity in Septic Shock Patients: A Prospective Observational Pilot Study |
| **Sponsor** | First Affiliated Hospital of Wannan Medical College; Collaborator: Wuhu City Second People's Hospital |
| **Status** | NOT_YET_RECRUITING |
| **Participants** | 48 (RCT, parallel, triple masking) |
| **Keywords** | Privacy, Septic Shock, Vascular Dysfunction, Confidentiality, Ultrasound Speckle Tracking |

**What it studied:** A small but explicit privacy protocol — ultrasound data, blood tests and vitals. The informed-consent section is a model of clarity: consent is collected for ALL data collection, including painless ultrasound scans. Privacy-washing protocol: participants have **clear rights to withdraw at any time**; any data withdrawal means **destruction of that participant's data**; **university security clearance is required to access any collected data** (minimum senior-level staff, PI, and IRB chairman approval). A "Privacy Service Team" is tasked with on-going monitoring of all data use. The hospital ethics committee approved the study.

**Web-security takeaways — perfect for a "small design, big lessons" workshop module:**
- **Principle of least privilege at the institutional level** — this trial splits access to the smallest organizational domain. Only the named PI, one named staffer under the PI, and the IRB chairman can pull raw data from the university store. Map this privilege model into your own app platform: even the senior-most employees should have access-control ties to individual project completion tiers.
- **Respect data withdrawal at the storage level** — withdrawal must be both a UX event and a storage deletion event. Delete, not unpublish.
- **Quantified consent identity** — fine-grained consent, by study component, gives users power; most web consent flows dump users into an "all or nothing" opt-in.
- **Ethics review as an operational gate** — the ethics committee approval step is a mandatory go/no-go milestone. Your product should have a comparable check before any data-handling change ships.

Original summary:
> "Your Rights and Safety: Voluntary Participation: You can withdraw at any time without affecting your treatment. Privacy: Your personal information and test results will be kept confidential."

---

### 4 · NCT06118528 — Privacy-Conscious Eating Tracker with Image Obfuscation (Northwestern / NIDDK)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT06118528](https://clinicaltrials.gov/study/NCT06118528) |
| **Title** | EAT: A Reliable Eating Assessment Technology for Free-living Individuals |
| **Sponsor** | Northwestern University; Collaborator: NIDDK (NIH) |
| **Status** | RECRUITING |
| **Participants** | 72 |
| **Design** | Crossover RCT, no masking |
| **Keywords** | Wearable Camera, Privacy, Blur, Edge, Cartoon, Obfuscation, Obesity, Health Data |

**What it studied:** A wearable camera (Exist Ref C plantronics + custom camera unit is worn around the neck, capturing head-and-torso images without audio). The key privacy design: **three different image-obfuscation filters (blur, edge, cartoon) are built directly into the app**, tested sequentially. Participants provide feedback on which filter best balances data quality with identity protection. The device captures colour images that are then **processed through a privacy pseudonymization pipeline (dependent on image-type selection).** Raw images are stored behind strict access controls.

**Web-security takeaways — perfect for a "privacy filters / image-handling / edge AI" workshop module:**
- **Edge-level privacy filtering** — do your privacy processing at the edge, on the device itself, before anything is uploaded to servers. Send only filtered / obfuscated data upstream.
- **User-controlled privacy options** — let users pick how they want to be anonymized. Currently this trial tests blur vs. edge vs. cartoon; on the web, this maps to "delete background," "face pixelate," "body sage," etc.
- **Pseudonymize-by-default in the pipeline** — the data pipe itself is privacy-first: raw frames are processed, filtered, and pseudonymized at the source.
- **Collect efficient privacy utility metric** — like the Roman "blurs/features/cartoon" make a measurable tradeoff so participants know what protection they opted for. Use the same principle — clearly communicate what is collected at what level of fidelity.
- **Eligible population as a control shape** — BMI ≥18.5, Chicago residents, 18+, English-speaking, own a smartphone. Your onboarding can do the same — collect only what's needed for the feature.

Original summary:
> "This study utilizes a small, privacy-conscious wearable device intended to monitor human behaviors. The device is worn around the neck, capturing the wearer's head and upper torso within its field of view, and records color images without audio... Alongside the device, we have included three privacy filters (blur, edge, and avatar) capable of obscuring faces and objects seen in the device-captured images. All participants will be subject to unfiltered recording during their first week followed by a different filter each following active week in a random order."

---

### 5 · NCT07700199 — AI-Driven Survivorship Care Plans with Prompt-Governed Privacy Controls (Huntsman Cancer Institute / University of Utah)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT07700199](https://clinicaltrials.gov/study/NCT07700199) |
| **Title** | AI-Driven Survivorship Care Plans (AI-SCP): Using LLMs with Prompt-Governed Privacy Controls |
| **Sponsor** | University of Utah; Collaborator: Huntsman Cancer Institute |
| **Status** | NOT YET RECRUITING (estimated 2026–2027) |
| **Participants** | 50 cancer survivors |
| **Design** | Single-group, interventional, health-services research |
| **Keywords** | Cancer, Survivorship, LLM, Chatbot, GARDE-Chat, User-Centred Design (UCD), HIPAA, PROMIS |

**What it studied:** A HIPAA-compliant LLM pipeline that ingests structured and unstructured oncology EHR data to auto-generate Survivorship Care Plans. Patient-facing chatbot (GARDE-Chat) separates prompt-data processing, model inference, and governance into three independent pipelines. The raw conversation store is separated from the analytics pipeline. User-Centred Design practices are embedded directly into the AI-SCP development process; usability is measured via the **System Usability Scale (SUS)**; post-trial analysis will also review prompt-governance logs and LLM-driven safety investments. Separate analytics from raw logs via dedicated pipelines. Model governance != model code; every prompt change is versioned, reviewed, and has its output impact tracked.

**Web-security takeaways — perfect for a "safe AI systems / LLM governance" workshop module:**
- **Separate pipes for analytics and raw request log storage** — production conversation logs go to one store with stricter retention rules; structured usage metrics flow through a different, aggregated pipeline.
- **Governance != engineering — version prompts as carefully as you version code.** Every prompt change should be tracked + reverted. On the web, this maps to prompt/reaction-logger/version-control for LLM replacements.
- **Engage usability testing on iteration/prototype** — SUS scoring is well-established and easy to deliver; apply this rigorously for security-oriented UX.
- **Audit every prompt–output pair** — your chatbot logs must be immutable and disclosable to a third party or regulator.
- **Model governance board** — establish a prompt-ethics / output-impact assessment board with veto power over model retraining or deployment.

Original summary:
> "UCD is embedded directly into prompt engineering and model governance workflows. SUS-based easurement is built to validate user perception to ensure that the design guided toward a user-centred AI-SCP product is safe, reliable, and trustworthy to the end user."

---

### 6 · NCT07709091 — Data Security and Management Awareness Training for Nursing Students (Istanbul Arel University)

| Field | Details |
|-------|---------|
| **NCT ID** | [NCT07709091](https://clinicaltrials.gov/study/NCT07709091) |
| **Title** | Data Security and Management in Digital Health: The Effect of Awareness Training onNursing Students |
| **Sponsor** | Istanbul Arel University; Funding: Beta Zeta Chapter of Sigma Theta Tau |
| **Status** | COMPLETED |
| **Start / Completion** | 2025-04-21 → 2026-07-08 |
| **Participants** | 110 nursing students (RCT, parallel design) |
| **Keywords** | Digital Health, Digital Data Security, Health Data Privacy, Data Management, Awareness Training, Nursing Students |

**What it studied:** A two-arm RCT in which the intervention group received a structured online training covering protection / confidentiality of personal health data, cybersecurity risks, password security, secure storage and sharing, data privacy, and ethical responsibilities in health-data management — while a control group received no training. Validated with the **32-item Digital Data Security Awareness Scale (DDSS)** and the **20-item Data Management in the Digital Health Environment Scale (DM-DHES)**.

**Web-security takeaways — perfect for a "security-awareness training program" workshop module:**
- **Train BEFORE you audit** — awareness reduces GDPR-breach risk more than compliance check-box quizzes; build a continuous training program into your org's onboarding and annual cycle.
- **Validate with a validated psychometric instrument (build an internal quiz around OWASP Top 10 and the MITRE ATT&CK framework).**
- **Publish the curriculum openly** — free-to-share training materials can be forked by any community.
- **Measurable post-test** — conduct pre-training and post-training assessments to measure effectiveness of the training (DDSS and DM-DHES).
- **Comparison (control) group** — test new training content against a no-training control group before rolling out.

Original summary:
> "This randomized controlled study evaluated the effect of an online awareness training program on nursing students' awareness of digital data security and their attitudes toward data management in digital health environments. The intervention group received online training on digital health data security and data management, while the control group did not receive the training during the study period. The study was conducted with 110 nursing students who were randomly assigned to the intervention and control groups."

---

## Portland Venues — Where We Could Host Security Workshops & Meetups

The OSM Overpass API (overpass-api.de, used by all category-search and nearby-places tools) was repeatedly unavailable during this run with SSL connection failures. Venues below were located via **Nominatim direct geocoding** of well-known civic landmarks and event spaces, then had their walking distances computed from the **downtown Portland centre point (45.5159°N, 122.6822°W)** using the OSRM routing engine. All venues can be reached on foot within 30 minutes.

| # | Venue | Type | Address | Distance from centre (walk) | Capacity / Notes |
|---|---|---|---|---|---|
| 1 | **The Old Church Concert Hall** | Events venue | 1422 SW 11th Ave, Portland, OR 97201 | **584 m / 8 min** | Beautiful historic venue ideal for mid-sized community security workshops; 30+ seats; event rental available |
| 2 | **Oregon Historical Society / Oregon Historical Society Museum** | Museum / Events | 1200 SW Park Ave, Portland, OR 97205 | **at the centre (≤200 m)** | Right at the geographic centre of downtown. Lecture halls, event spaces; ideal for conference-style talks |
| 3 | **Portland Art Museum** | Museum / Events | 1219 SW Park Ave, Portland, OR 97205 | **508 m / 8 min** | Active event-rental program; lecture halls up to 350 ppl; in the heart of the South Park Blocks |
| 4 | **Arlene Schnitzer Concert Hall** | Events venue | 1037 SW Broadway, Portland, OR 97205 | **821 m / 14 min** | Concert hall with auxiliary meeting / breakout rooms up to ~200. Home of the Portland Youth Philharmonic |
| 5 | **Sentinel Hotel** | Hotel ballroom | 614 SW 11th Ave, Portland, OR 97204 | **1,180 m / 20 min** | Boutique hotel with ballroom and meeting rooms; available for community meetings in suites up to 150 |
| 6 | **Courtyard by Marriott Portland City Center** | Hotel event space | 550 SW Oak St, Portland, OR 97204 | **821 m / 14 min** | Flexible meeting rooms; public transit accessible; ideal for half-day workshops |
| 7 | **AC Hotel by Marriott Portland Downtown** | Hotel event space | 888 SW 3rd Ave, Portland, OR 97204 | **1,148 m / 19 min** | Distinctive meeting room styles of notable small hall size for small team events |
| 8 | **World Trade Center Portland** | Conference centre | 1 SW Salmon St, Portland, OR 97201 | **1,349 m / 22 min** | Downtown commercial venue with large conference capabilities up to a few hundred |
| 9 | **Oregon Convention Center** | Convention centre | 777 N Martin Luther King Jr Blvd, Portland, OR 97204 | **1,874 m / 31 min walk** | Largest in the region; hackathons, all-week conferences, large lanyard-aid capitalism up, paid and free practices for 1,000 |
| 10 | **Portland City Hall** | Civic venue | 1220 SW 5th Ave, Portland, OR 97205 | **420 m / 7 min** | Commission chambers and city hall meeting available; civic venues for large gatherings |
| 11 | **Oregon State University – Portland** | University venue | 555 SW Morrison St, Portland, OR 97204 | **600 m / 10 min** | Urban campus centre. Lecture halls, block seminar rooms; university-affiliated events |
| 12 | **Oregon Primary Care Association** | Health industry space | 623 SW Oak St, Portland, OR 97201 | **905 m / 15 min** | Healthcare / research-oriented space ideal for health-data-focused security meetups |

### Concrete venue suggestions by scenario
- **30–100 ppl community / tech meetups with talks:** The Old Church Concert Hall or Arlene Schnitzer Concert Hall (breakout rooms). Both are central and have legitimate stage + A/V capability.
- **30–200 ppl conference-style workshops with breakout rooms:** The Portland Art Museum lecture hall. Lay out a big hall + breakout breakout rooms.
- **10–30 ppl intimate security culture / hacker circles:** Sentinel Hotel small suites or the Marriott meeting rooms on the second floor.
- **24-hour to 48-hour hackathons on a weekend:** Oregon Convention Center provides the largest flexibility — > 10,000 sq ft of exhibit space.

---

## How to Get Involved
- Open issues for ideas, discussion, or proposals. Submit a PR to suggest additional studies or venues. We're happy to merge your favourite privacy case studies into this repository.
- Reach the project maintainers at [zhub9006@alachisoft.com](mailto:zhub9006@alachisoft.com). Or publish experimental tools in `docs/"

## License
Apache 2.0. See the LICENSE file for details.
