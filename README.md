# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. Research gathered via live API calls to ClinicalTrials.gov and OpenStreetMap.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "patient data privacy" and verified **five concrete studies** with detailed protocol sections — all real, API-confirmed results — that showcase directly adaptable practices for web security.

---

## Verified Clinical Trials — Patient Data Privacy

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT07344116** | Establishment of a Hepatobiliary and Pancreatic Tumor Biobank | Zhejiang University School of Medicine | NOT_YET_RECRUITING | **Coded data storage** — All samples and data coded and stored per ethical and legal requirements to protect participants' privacy; long-term research resource with privacy by design |
| **NCT07360366** | Interprofessional Collaboration in the Cardiac ICU: An Action-Research Training Project | University Hospital of Parma | NOT_YET_RECRUITING | **Pseudo-anonymization with restricted access** — Privacy strictly maintained through pseudo-anonymization; data access restricted to the research team |
| **NCT05170321** | Analysis of Influencing Factors and Construction of Prediction Models of Artificial Joint Replacement in China | Xiangya Hospital, Central South University | UNKNOWN | **Confidentiality principle & IRB approval** — Data analysis conformed to the principle of confidentiality; won't reveal patient privacy; authorized by HQMS Committee Board and institutional IRB with waiver of informed consent |
| **NCT07125625** | Randomized Double Blind Placebo Controlled Trial on a Probiotic Mixture in Pediatric IBS | University of Bari | NOT_YET_RECRUITING | **Confidential and secure per privacy laws** — All personal data and medical information treated confidentially and securely in accordance with privacy laws; European and Italian regulations for children |
| **NCT07564544** | AI-Based Clinical Orientation Program for Nursing Students | Selcuk University | NOT_YET_RECRUITING | **Ethics committee approval & informed consent** — Ethical committee approval obtained; informed consent collected after explaining study objectives; keys to privacy in research |

---

## Detailed Study Findings & Web-Security Adaptations

### NCT07344116 — Hepatobiliary and Pancreatic Tumor Biobank
- **Sponsor:** Zhejiang University School of Medicine
- **Design:** Biobank collecting blood, tissue, bile, and body fluids with clinical data; no experimental treatment or additional invasive procedures
- **Key Privacy Practices:**
  - **Coded data storage** — All samples and data coded and stored per ethical and legal requirements
  - **Privacy by design** — Purpose-built as a long-term research resource with privacy protections
- **Adaptation for Web Security:** Apply data coding/pseudonymization to user data at the point of collection; design systems with privacy-by-design principles from the start, not as an afterthought; separate identifiable data from research/analytics data with strict access boundaries

### NCT07360366 — Interprofessional Collaboration in CICU
- **Sponsor:** University Hospital of Parma
- **Design:** Scenario-based training program for physicians, nurses, healthcare assistants using Moodle-based simulations; 24-month project with 53 total participants
- **Key Privacy Practices:**
  - **Pseudo-anonymization** — Privacy strictly maintained through pseudo-anonymization, not just anonymization
  - **Restricted access** — Data access restricted to the research team only
- **Adaptation for Web Security:** Implement pseudo-anonymization for community data (codes replace identifiers); enforce strict role-based access controls limiting data access to essential personnel only; audit access logs regularly

### NCT05170321 — Joint Replacement Prediction Models in China
- **Sponsor:** Xiangya Hospital, Central South University
- **Design:** Analysis of 230M+ standardized inpatient discharge records across 31 provincial regions using HQMS database; includes knee/hip/shoulder/ankle/elbow arthroplasty
- **Key Privacy Practices:**
  - **Confidentiality principle** — Data analysis conformed to the principle of confidentiality; will not reveal patient privacy
  - **IRB approval with waiver of informed consent** — Authorized by HQMS Committee Board and institutional IRB
  - **No conflict of interest** — Applies to principles of ethics, harmlessness, and fairness
- **Adaptation for Web Security:** Adopt the "principle of confidentiality" as a core design constraint; ensure aggregated/analytics data cannot be reverse-engineered to leak PII; document IRB/ethics approvals and audit trails; define and communicate data use boundaries clearly to users

### NCT07125625 — Probiotic Mixture for Pediatric IBS
- **Sponsor:** University of Bari
- **Design:** Randomized, double-blind, placebo-controlled trial; 14-week study with 2-week run-in, 8-week treatment, 4-week follow-up; children aged 4-18 with IBS
- **Key Privacy Practices:**
  - **Confidential and secure** — All personal data and medical information treated confidentially and securely in accordance with privacy laws
  - **European/Italian regulations for children** — Additional protections for minor participants
  - **Informed consent with voluntary participation** — Families can withdraw at any time without affecting medical care
- **Adaptation for Web Security:** Treat all user data as confidential and secure by default; apply enhanced protections for sensitive data categories (health, financial, etc.); ensure users can withdraw their data as easily as they consented; implement clear data deletion workflows

### NCT07564544 — AI-Based Clinical Orientation Program
- **Sponsor:** Selcuk University
- **Design:** Experimental study with 186 nursing students (90 intervention, 45 control); pre-test/post-test design; AI-based clinical orientation program
- **Key Privacy Practices:**
  - **Ethical committee approval** — Obtained before study begins
  - **Informed consent** — Collected from all participants after explaining objectives
  - **Data protection integration** — Privacy considerations built into study design from the outset
- **Adaptation for Web Security:** Obtain explicit consent before collecting user data; integrate privacy considerations into product development from the start (not retroactively); conduct privacy impact assessments alongside security assessments; evaluate effectiveness with pre/post measurements

---

## Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **Coded/pseudonymized data storage** | NCT07344116 — All data coded per ethical/legal requirements | **Apply pseudonymization at the point of collection** — separate identifiers from analytics data; use codes instead of PII in all internal datasets |
| 2 | **Pseudo-anonymization + restricted access** | NCT07360366 — Pseudo-anonymization; data access restricted to the research team | **Enforce role-based access with pseudonyms** — only essential personnel see identifiers; audit access logs for anomalies |
| 3 | **Confidentiality as a design constraint** | NCT05170321 — Principle of confidentiality; IRB approval; no conflict of interest | **Adopt confidentiality by design** — ensure aggregated data can't be reverse-engineered; document ethics approvals and audit trails |
| 4 | **Secure & confidential per privacy laws** | NCT07125625 — Confidential and secure per privacy laws; European regulations | **Treat user data as confidential by default** — secure storage, encrypted transit, clear deletion workflows; enhanced protections for sensitive categories |
| 5 | **Informed consent & ethical approval** | NCT07564544 — Ethics committee approval; informed consent after explaining objectives | **Obtain explicit consent before data collection** — integrate privacy into the development lifecycle; conduct privacy impact assessments |

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
