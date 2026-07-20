# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon. Research gathered via live API calls to ClinicalTrials.gov and OpenStreetMap.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight). We searched ClinicalTrials.gov for recent studies on "patient data privacy" and verified **five concrete studies** with detailed protocol sections — all real, API-confirmed results — that showcase directly adaptable practices for web security.

---

## Verified Clinical Trials — Patient Data Privacy

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT04875260** | Taiwan Center of Outcome and Resource Evaluation Adult ICU Database | National Taiwan University Hospital | RECRUITING | **HIPAA-compliant de-identification** — Multi-center de-identified ICU database built per HIPAA regulations; Joint Data Management Committee enforces privacy safeguards across all participating hospitals |
| **NCT06011356** | SWIPER-MOVES: Smart Watch Insights for Prevention of Exacerbations | Imperial College London | ACTIVE_NOT_RECRUITING | **Secure login & encrypted data transmission** — Connected Life app uses secure login credentials for data privacy; digital health data transmitted only to authorized research team |
| **NCT03849846** | NutriQuébec: Focus Groups on Data Security Concerns | Laval University | COMPLETED | **Data security as a research outcome** — Investigated participant concerns about the security, use, and sharing of health data; conducted in community centres with consent protocols |
| **NCT06474429** | FMS as Physical Therapy Discharge Criteria | Texas Back Institute | RECRUITING | **Encryption & secure storage** — Data managed per Good Clinical Practice and HIPAA guidelines with encryption and secure storage; real-time monitoring for participant safety |
| **NCT00132145** | COMPETE III: Electronic Integration of Care | St. Joseph's Healthcare Hamilton | COMPLETED | **EHR network with privacy/security as a measured outcome** — HL-7 messaging standards per Canada Health Infoway guidelines; "Health data privacy and security" tracked as a formal outcome measure alongside clinical results |

---

## Detailed Study Findings & Web-Security Adaptations

### NCT04875260 — Taiwan ICU Database
- **Sponsor:** National Taiwan University Hospital
- **Design:** Multi-center de-identification adult ICU database with 600,000 estimated participants across hospitals in Taiwan
- **Key Privacy Practices:**
  - **HIPAA-compliant de-identification** — All data de-identified per HIPAA regulations before entering the shared database
  - **Joint Data Management Committee** — Central governance body oversees data access, quality, and privacy
  - **Multi-center access controls** — Participating hospitals contribute and access data under unified privacy policies
- **Adaptation for Web Security:** Apply data de-identification at the point of collection; establish a central data governance committee for privacy oversight; implement unified access policies across all API endpoints and microservices

### NCT06011356 — SWIPER-MOVES (Imperial College London)
- **Sponsor:** Imperial College London
- **Design:** Observational cohort study using smartwatches to track movement and health metrics in 1,000 participants via the NHS Care Information Exchange
- **Key Privacy Practices:**
  - **Secure login credentials** — Each participant receives unique, secure login details for the Connected Life app
  - **Tiered data access** — Only the research team sees linked clinical data; participants see only their own dashboard
  - **Encrypted data pipeline** — Data from wearable device to research backend is encrypted in transit
- **Adaptation for Web Security:** Implement per-user authenticated sessions with strong credential practices; apply least-privilege access so users see only their own data; encrypt all data in transit between client and server

### NCT03849846 — NutriQuébec Focus Groups
- **Sponsor:** Laval University
- **Design:** Cross-sectional study using focus groups (n=28) in community centres to explore data security concerns among low-SES populations
- **Key Privacy Practices:**
  - **Consent before participation** — All participants signed consent forms before focus groups began
  - **Sociodemographic screening** — Participants completed questionnaires separately from discussion content
  - **Data security explored as a core topic** — The study itself investigated what people fear about data sharing, informing better consent design
- **Adaptation for Web Security:** Design consent flows that address real user concerns (not just legal checkboxes); separate sensitive user data from analytics data by design; use community-based feedback to iterate on privacy features

### NCT06474429 — Texas Back Institute (FMS Study)
- **Sponsor:** Texas Back Institute
- **Design:** Prospective cohort study of 50 patients with 6-month follow-up, tracking physical therapy outcomes
- **Key Privacy Practices:**
  - **HIPAA-compliant data management** — All data handled per HIPAA guidelines with encryption and secure storage
  - **Good Clinical Practice adherence** — Procedures follow GCP standards including privacy protections
  - **Termination for safety** — Trained personnel can terminate participation at any point for safety reasons
- **Adaptation for Web Security:** Encrypt data at rest and in transit per regulatory requirements; follow GCP/ISO 27001 frameworks for data handling; implement user-initiated data deletion with clear workflows

### NCT00132145 — COMPETE III
- **Sponsor:** St. Joseph's Healthcare Hamilton
- **Design:** Randomized controlled trial with 1,000 participants, evaluating an electronic vascular tracking system shared between patients and physicians
- **Key Privacy Practices:**
  - **HL-7 messaging standards** — Data exchange follows Canada Health Infoway interoperability and privacy standards
  - **Health data privacy & security as a formal outcome** — Privacy is measured alongside clinical effectiveness, not treated as an afterthought
  - **Electronic health record network** — Built on a patient-facing EHR with pre-authorized research consent
- **Adaptation for Web Security:** Adopt industry-standard encryption and interoperability protocols (like TLS 1.3, RFC standards); track privacy metrics as first-class KPIs alongside performance and uptime; leverage existing trusted platforms for identity and consent management

---

## Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **HIPAA-compliant de-identification** | NCT04875260 — Multi-center ICU database with de-identification | **Pseudonymize PII at collection** — Separate identifiers from analytics data; use reversible codes instead of raw PII in internal datasets |
| 2 | **Secure login + tiered access** | NCT06011356 — Unique credentials; only research team sees linked data | **Authenticate with least-privilege** — Per-user sessions; users see only their own data; role-based access for staff |
| 3 | **Consent addressing real concerns** | NCT03849846 — Focus groups on data security fears; consent before participation | **Design consent for user trust** — Explain data use in plain language; let users opt into granular data-sharing categories |
| 4 | **Encryption at rest and in transit** | NCT06474429 — HIPAA data management with encryption and secure storage | **Encrypt everything** — TLS for transit; AES-256 for at-rest; key rotation policies; audit access logs |
| 5 | **Privacy as a measured outcome** | NCT00132145 — Privacy & security tracked alongside clinical results | **Treat privacy as a KPI** — Monitor access anomalies, consent rates, data-deletion requests; report privacy metrics publicly |

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

---

## Research Methodology

- **ClinicalTrials.gov API:** Searched for "patient data privacy", "HIPAA de-identification", "secure data sharing clinical research", and related terms. Filtered for recent studies (2020–2025) with statuses RECRUITING, ACTIVE_NOT_RECRUITING, or COMPLETED. Retrieved NCT IDs and full protocol sections via `get_study()`.
- **OpenStreetMap API:** Geocoded "Downtown Portland, Oregon" (45.5159°N, 122.6822°W), then used `find_nearby_places()` and `geocode_address()` within a 2km radius to identify community centres, event venues, libraries, and civic buildings.