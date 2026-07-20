# Clinical Trial Privacy Practices — Adapted for Web Security

> Generated 2025-07-13 from ClinicalTrials.gov API and OpenStreetMap queries.

## Eight Verified Studies with Directly Adaptable Privacy Practices

### 1. NCT01862133 — Patient Preference Privacy Selections in EMR
- **Sponsor:** Indiana University + HHS + Regenstrief Institute
- **Status:** COMPLETED | **Participants:** 136
- **Key Practice:** Patient-controlled EHR access with granular consent for 5 sensitive categories (STIs, HIV/AIDS, sexual health, drug/alcohol, mental health)
- **Web-Security Adaptation:** Consent-gated dashboards; role-based field-level access; time-bound data sharing windows

### 2. NCT04910009 — Privacy Education on Nursing Students' Privacy Consciousness
- **Sponsor:** Gazi University
- **Status:** COMPLETED | **Participants:** 116
- **Key Practice:** RCT combining theoretical + practical (digital storytelling + ethical case analysis) privacy education
- **Web-Security Adaptation:** "Privacy 101" curriculum with hands-on ethical case studies; pre/post knowledge assessments

### 3. NCT05864859 — Empathic Tendency and Privacy Protection Level
- **Sponsor:** KTO Karatay University
- **Status:** COMPLETED | **Participants:** Simulation-based
- **Key Practice:** Wearable simulation + role-play for midwifery privacy; validated Privacy Protection Scale (α=0.95) and Empathic Tendency Scale (α=0.75)
- **Web-Security Adaptation:** Privacy scenario workshops with role-play; measure awareness gains with validated scales

### 4. NCT00132145 — COMPETE III: Secure Electronic Health Networks
- **Sponsor:** St. Joseph's Healthcare Hamilton
- **Status:** COMPLETED | **Participants:** 1,000
- **Key Practice:** Role-based access + encrypted data sharing (HL-7); "Health data privacy and security" as explicit secondary outcome
- **Web-Security Adaptation:** Zero-trust community data systems; TLS 1.3 + AES-256; FHIR-inspired schemas; separate read/write/admin roles

### 5. NCT06711757 — AI-based Models for Spine Malalignment (Multi-Center)
- **Sponsor:** University of Hong Kong
- **Status:** COMPLETED | **Participants:** 2,763 across 7 hospitals
- **Key Practice:** Systematic de-identification before AI model training; demographic extraction separated from image data
- **Web-Security Adaptation:** Anonymize community data before cross-membership analysis; separate PII from usage data by default

### 6. NCT05631210 — Pictograms for Privacy Agreements
- **Sponsor:** University of Waterloo
- **Status:** COMPLETED | **Participants:** 57
- **Key Practice:** Pictogram-enhanced privacy agreements improved comprehension speed and reduced friction
- **Web-Security Adaptation:** Visual consent badges in documentation; icon sets for data collection, opt-out, third-party sharing, location tracking

### 7. NCT07709091 — Digital Health Data Security Awareness Training
- **Sponsor:** Istanbul Arel University
- **Status:** COMPLETED | **Participants:** 110
- **Key Practice:** Online awareness training on digital data security, cybersecurity risks, password security, secure storage/sharing, data privacy, ethical responsibilities
- **Web-Security Adaptation:** Regular data-security bootcamps; cover password hygiene, encrypted communication, phishing awareness; issue certificates

### 8. NCT07307521 — AIME-ICU: AI-Assisted Video Monitoring with Privacy Protections
- **Sponsor:** Shanghai Zhongshan Hospital
- **Status:** NOT_YET_RECRUITING | **Participants:** 300 (estimated)
- **Key Practice:** Face masking, background blurring, offline-only storage, de-identification pipeline before AI training, national law compliance
- **Web-Security Adaptation:** Integrate privacy into dev pipeline; automated PII scrubbing; background blurring for screenshots; offline-first data processing

## Four Recurring Privacy Themes

1. **Secure encrypted data collection** — TLS for all communications; encrypted at rest
2. **Role-based restricted access** — separate read/write/admin roles; MFA-sensitive ops
3. **Independent oversight + defined retention** — formal privacy protocols; auto-delete after fixed window
4. **Explicit consent + transparency** — clear privacy notice; opt-out mechanism; subjects can request access/correction/deletion
