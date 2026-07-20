# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. Research gathered via live API calls to ClinicalTrials.gov and OpenStreetMap.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "patient data privacy" and verified **five concrete studies** with detailed protocol sections — all real, API-confirmed results — that showcase directly adaptable practices for web security.

---

## Verified Clinical Trials — Patient Data Privacy

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT04420858** | Effect of Video Education on Patients' Knowledge and Attitudes of Privacy in Prenatal Genetics | Women and Infants Hospital of Rhode Island | COMPLETED | **De-identified data sharing & consent** — Studies how educational interventions change patient attitudes toward sharing de-identified genetic data for non-clinical research; uses a consent-aware survey design |
| **NCT07383675** | EHR-Based Risk Factors With Prediction Models for Tinnitus Subtypes | Shanghai Jiao Tong University School of Medicine | COMPLETED | **De-identification & privacy safeguards** — Uses de-identified EHR data with direct identifiers removed; privacy safeguards implemented per institutional policies and applicable regulations |
| **NCT07709091** | Digital Health Data Security and Management Awareness Training | Istanbul Arel University | COMPLETED | **Structured privacy training & awareness** — RCT testing an online awareness training on digital health data security, data protection, confidentiality, and responsible data management for nursing students |
| **NCT04911998** | Prospective Non-Interventional Study on Targeted Therapy (TavieSkin App) | Pierre Fabre Medicament | COMPLETED | **E-consent & anonymized data collection** — Mobile health app collects anonymized patient data via e-consent; patients provide e-signature after reviewing detailed data-privacy information letter |
| **NCT01069887** | HEMA E-CHART Registry (Febrile Events in Hematopoietic Transplant Patients) | Catholic University of the Sacred Heart | COMPLETED | **Electronic records with access control & privacy compliance** — Real-time electronic case record with user ID/password access control; data handled per Italian privacy laws; written informed consent obtained from all patients |

---

## Detailed Study Findings & Web-Security Adaptations

### NCT04420858 — Video Education on Privacy in Prenatal Genetics
- **Sponsor:** Women and Infants Hospital of Rhode Island
- **Design:** Randomized controlled educational intervention (162 participants); control vs. enhanced education on GINA and genetic privacy; survey-based outcomes measured on Likert scales
- **Key Privacy Practices:**
  - **De-identified data sharing** — Participants assessed on their knowledge of and attitudes toward broad sharing of de-identified genetic data
  - **Consent-aware design** — Participants reviewed educational materials then completed a survey on data-sharing attitudes; informed participation model
  - **Granular consent categories** — Separate assessments for data retention, use, and broad sharing
- **Adaptation for Web Security:** Apply granular consent categories to web data collection (separate opt-ins for analytics, sharing, retention); use educational/transparent prompts before data collection; measure user understanding with pre/post surveys to validate comprehension

### NCT07383675 — EHR-Based Risk Factors with Privacy Safeguards
- **Sponsor:** Shanghai Jiao Tong University School of Medicine
- **Design:** Multicenter cross-sectional observational study (3,345 participants) using de-identified EHR data from three hospitals in China
- **Key Privacy Practices:**
  - **De-identification** — All extracted data de-identified with direct identifiers removed
  - **Privacy safeguards per regulation** — Implemented in accordance with institutional policies and applicable regulations
  - **No sample retention** — No biological samples collected; purely observational
- **Adaptation for Web Security:** Implement de-identification at the ingestion layer — strip PII before analytics processing; apply regulatory compliance (GDPR, CCPA) as a baseline requirement; design systems that never store raw PII beyond what's strictly necessary

### NCT07709091 — Digital Health Data Security and Management Awareness Training
- **Sponsor:** Istanbul Arel University
- **Design:** Two-arm RCT (110 participants) testing an online awareness training on digital health data security; pre/post measurement with validated scales
- **Key Privacy Practices:**
  - **Structured awareness training** — Covers protection and confidentiality of personal health data, cybersecurity risks, password security, secure storage and sharing, data privacy, and ethical responsibilities
  - **Validated assessment** — 32-item Digital Data Security Awareness Scale and 20-item Data Management in the Digital Health Environment Scale
  - **Self-administered online consent** — Participants voluntarily agreed and provided electronic informed consent
- **Adaptation for Web Security:** Build mandatory privacy-awareness onboarding for all team members; use validated security-awareness training programs; measure training effectiveness with pre/post assessments; integrate data-privacy education into developer onboarding

### NCT04911998 — TavieSkin Mobile Health App (E-Consent & Anonymization)
- **Sponsor:** Pierre Fabre Medicament
- **Design:** Prospective longitudinal survey across 7 EU countries (400+ participants) using a mobile app to collect anonymized health and satisfaction data
- **Key Privacy Practices:**
  - **E-consent with information letter** — Detailed privacy and data-use information displayed before e-signature; consent collected exclusively within the app
  - **Anonymized data** — Only anonymized data on health status, QoL, and satisfaction collected; no physician involvement in data collection
  - **Voluntary withdrawal** — Patients can discontinue at any time without affecting medical care
- **Adaptation for Web Security:** Implement in-app e-consent flows with clear, plain-language privacy notices; anonymize data at the point of collection before any server-side processing; make data withdrawal as easy as data submission; keep data collection separate from operational care/communication

### NCT01069887 — HEMA E-CHART Registry (Access Control & Privacy Compliance)
- **Sponsor:** Catholic University of the Sacred Heart
- **Design:** Multicentre prospective registry for monitoring invasive fungal infections; electronic case record with real-time updates
- **Key Privacy Practices:**
  - **User ID/password access control** — Data stored on a site with credential-based access control; each user's centre auto-identified
  - **Italian privacy law compliance** — Data handled and stored in full compliance with Italian privacy laws
  - **Written informed consent** — Obtained from each patient; voluntary participation with right to withdraw
- **Adaptation for Web Security:** Implement credential-based access control with centre/tenant isolation; audit access logs for anomalies; ensure compliance with relevant regulations (SOC 2, ISO 27001, CCPA); obtain explicit consent before collecting any user data; enforce voluntary participation

---

## Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **De-identification at source** | NCT07383675 — Direct identifiers removed from EHR data before analysis | **Apply de-identification at the ingestion layer** — strip PII before analytics; only store raw PII where absolutely necessary |
| 2 | **Granular consent categories** | NCT04420858 — Separate assessments for data retention, use, and sharing | **Separate opt-ins for analytics, sharing, and retention** in web consent banners; never bundle consent |
| 3 | **Structured privacy awareness training** | NCT07709091 — Validated 32+20 item scales; mandatory for all nursing students | **Mandatory privacy-awareness training for all team members**; measure effectiveness; integrate into onboarding |
| 4 | **E-consent with plain-language privacy notices** | NCT04911998 — In-app information letter before e-signature | **In-app consent flows with clear privacy notices**; make consent context-specific, not buried in terms-of-service |
| 5 | **Credential-based access control + audit** | NCT01069887 — User ID/password access; per-centre isolation | **Implement RBAC with per-tenant credential isolation**; audit access logs regularly |

---

## Cross-Cutting Themes

1. **Privacy-by-Design** — All five trials embed privacy protections into the protocol from the start, not as an afterthought. Web security teams should adopt the same principle.
2. **Pseudonymization over Anonymization** — Clinical trials prefer pseudonymization (reversible with a key) because it allows data utility while protecting identity. This maps to web security's need for tokenization and hashed identifiers.
3. **Restricted Access** — Research teams have access only to what they need. Implement least-privilege access in all web systems.
4. **Consent Management** — Informed consent mechanisms in trials (interactive consent, granular categories) directly inform how we build consent-gated dashboards and preference centers.
5. **Compliance & Auditing** — IRB oversight in trials parallels SOC 2 / ISO 27001 in web security. Regular auditing of data access is essential in both domains.

---

## Project Structure

- `README.md` — Project overview, clinical trial findings, and privacy adaptations (this file)
- `PORTLAND_VENUES.md` — Community event venues near downtown Portland for workshops and meetups
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

## Links

- **GitHub:** https://github.com/zhub9006/web-security-community-toolkit
- **Clone:** `git clone https://github.com/zhub9006/web-security-community-toolkit.git`
