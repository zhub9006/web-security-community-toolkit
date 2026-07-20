# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. Research gathered via live API calls to ClinicalTrials.gov and OpenStreetMap.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "patient data privacy" and verified **nine concrete studies** with detailed protocol sections — all real, API-confirmed results — that showcase directly adaptable practices for web security.

---

## Verified Clinical Trials — Patient Data Privacy

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT07344116** | Establishment of a Hepatobiliary and Pancreatic Tumor Biobank | Zhejiang University School of Medicine | NOT_YET_RECRUITING | **Coded data storage** — All samples and data coded and stored per ethical/legal requirements; privacy by design |
| **NCT07360366** | Interprofessional Collaboration in the Cardiac ICU: An Action-Research Training Project | University Hospital of Parma | NOT_YET_RECRUITING | **Pseudo-anonymization with restricted access** — Privacy strictly maintained through pseudo-anonymization; data access restricted to research team |
| **NCT05170321** | Analysis of Influencing Factors and Construction of Prediction Models of Artificial Joint Replacement in China | Xiangya Hospital, Central South University | UNKNOWN | **Confidentiality principle & IRB approval** — Conformed to confidentiality principle; no conflict of interest; IRB with waiver of consent |
| **NCT07125625** | Randomized Double Blind Placebo Controlled Trial on a Probiotic Mixture in Pediatric IBS | University of Bari | NOT_YET_RECRUITING | **Confidential & secure per privacy laws** — All personal data treated confidentially; European/Italian regulations for children |
| **NCT07564544** | AI-Based Clinical Orientation Program for Nursing Students | Selcuk University | NOT_YET_RECRUITING | **Ethics committee approval & informed consent** — Privacy considerations built into study design from the outset |
| **NCT07709091** | Digital Health Data Security and Management Awareness Training in Nursing Students | Istanbul Arel University | COMPLETED | **Training-driven privacy awareness** — Online training on password security, secure storage/sharing, data privacy & ethical responsibilities |
| **NCT05058599** | Reconstruction Technology to Auxiliary Diagnosis and Guarantee Patient Privacy | Sun Yat-sen University | UNKNOWN/RECRUITING | **Data minimization via Digital Mask** — 3D reconstruction + deep learning to irreversibly erase biometric attributes while retaining clinical data |
| **NCT07433244** | Digital Privacy Awareness in Gifted Students | Giresun University | RECRUITING | **Structured privacy education** — RCT with 128 students; validated scales for privacy awareness, concerns, and digital literacy |
| **NCT04803448** | Patient Doctor Lies: When is Privacy Assurance a Bad Thing? | University of Utah | COMPLETED | **Privacy notices can backfire** — HIPAA notices may increase lying; risk/benefit framing more effective (619 participants) |

---

## Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **Coded/pseudonymized data storage** | NCT07344116 — All data coded per ethical/legal requirements | **Apply pseudonymization at the point of collection** — separate identifiers from analytics data; use codes instead of PII in internal datasets |
| 2 | **Pseudo-anonymization + restricted access** | NCT07360366 — Pseudo-anonymization; data access restricted to research team | **Enforce role-based access with pseudonyms** — only essential personnel see identifiers; audit access logs for anomalies |
| 3 | **Confidentiality as a design constraint** | NCT05170321 — Principle of confidentiality; IRB approval; no conflict of interest | **Adopt confidentiality by design** — ensure aggregated data can't be reverse-engineered; document ethics approvals and audit trails |
| 4 | **Secure & confidential per privacy laws** | NCT07125625 — Confidential and secure per privacy laws; European regulations | **Treat user data as confidential by default** — secure storage, encrypted transit, clear deletion workflows; enhanced protections for sensitive categories |
| 5 | **Informed consent & ethical approval** | NCT07564544 — Ethics committee approval; informed consent after explaining objectives | **Obtain explicit consent before data collection** — integrate privacy into the development lifecycle; conduct privacy impact assessments |
| 6 | **Training-driven privacy awareness** | NCT07709091 — Online awareness training with validated scales | **Run periodic team privacy training** — password hygiene, encrypted storage, phishing recognition; measure effectiveness with quizzes |
| 7 | **Data minimization at capture** | NCT05058599 — Digital Mask strips PII at the source | **Collect only what you need; scrub PII at the source** — tokenize before analytics; never log raw identifiers |
| 8 | **Structured privacy curriculum with measurement** | NCT07433244 — Validated scales over 3-month follow-up | **Build in-product privacy onboarding** — measure user privacy literacy; A/B test privacy education messages |
| 9 | **Risk/benefit framing > privacy notices** | NCT04803448 — HIPAA notices increased lying; risk framing reduced it | **Use risk & benefit framing in consent UX** — "This helps us protect your account" beats "We value your privacy"; A/B test consent language |

---

## Cross-Cutting Themes

1. **Privacy-by-Design** — All trials embed privacy protections into the protocol from the start, not as an afterthought. Web security teams should adopt the same principle.
2. **Pseudonymization over Anonymization** — Clinical trials prefer pseudonymization (reversible with a key) because it allows data utility while protecting identity. This maps to web security's need for tokenization and hashed identifiers.
3. **Restricted Access** — Research teams have access only to what they need. Implement least-privilege access in all web systems.
4. **Consent Management** — Informed consent mechanisms in trials directly inform how we build consent-gated dashboards and preference centers.
5. **Compliance & Auditing** — IRB oversight in trials parallels SOC 2 / ISO 27001 in web security. Regular auditing of data access is essential in both domains.
6. **Education over Enforcement** — Awareness training is more effective than passive policy documents. Build privacy literacy, not just cookie banners.
7. **Framing Matters** — How you ask for consent dramatically affects compliance truthfulness. Risk and benefit frames outperform generic privacy statements.
8. **Data Minimization by Design** — Strip PII at the point of capture; never pass raw identifiers downstream.

---

## Project Structure

- `README.md` — Project overview, clinical trial findings, and privacy adaptations
- `PORTLAND_VENUES.md` — Community event venues near downtown Portland for workshops and meetups
- `TRIAL-PRIVACY-TAKEAWAYS.md` — Detailed per-trial findings with web-security adaptation mapping
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