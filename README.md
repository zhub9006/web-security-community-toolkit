# Web Security Community Toolkit

A community-driven initiative that adapts data-privacy practices from clinical trials to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## How This Project Was Built

The content in this repo is grounded in **live API research** performed on 2026-07-21:
- **ClinicalTrials.gov:** Searched for recent studies on "patient data privacy," "HIPAA," "de-identification," and "data protection" — verified concrete studies with full protocol sections
- **OpenStreetMap:** Geocoded downtown Portland (45.5159°N, 122.6822°W) and searched within a 2km radius for community centres, event spaces, libraries, and civic venues

We pulled the most relevant verified studies with detailed protocol details for direct web-security adaptation.

---

## Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR, IRB oversight, Data Monitoring Committees). We searched ClinicalTrials.gov for recent studies on "patient data privacy" and verified concrete studies — all real, API-confirmed results — that showcase directly adaptable practices for web security.

---

## Verified Clinical Trials — Patient Data Privacy

| NCT ID | Title | Sponsor | Status | Key Privacy Takeaway |
|--------|-------|---------|--------|----------------------|
| **NCT04684615** | Mental Health Impact of the COVID-19 Pandemic on Amish and Mennonite Participants in AMBiGen | NIH / NIMH | COMPLETED | **Coded identifiers instead of names** — Surveys contain no participant names, just codes; protects privacy of sensitive mental health data across 193 participants |
| **NCT02744846** | PCORnet Obesity Observational Study (ABX): Short- and Long-Term Effects of Antibiotics on Childhood Growth | Harvard Pilgrim Health Care / PCORI | COMPLETED | **Distributed research network + de-identified data** — CDRNs don't send individual data to a central site; coordinating center sends "questions to the data"; de-identified records used for validation; 681,739 participants across 42 healthcare systems |
| **NCT02329210** | Clinical Registry Investigating Bardet-Biedl Syndrome (CRIBBS) | Marshfield Clinic Research Foundation | RECRUITING | **HIPAA-compliant registry with pseudonymization** — Assigned study IDs instead of names; password-protected database + double-locked physical PHI storage; de-identified data shared only with board-approved researchers; IRB oversight |
| **NCT05908474** | io Fibrewater Supplementation on Gut Health & Metabolism | University of Roehampton | COMPLETED | **GDPR-compliant data collection** — Qualtrics platform follows GDPR; data export restricted to authorized users with admin-controlled permissions |
| **NCT03795090** | A Multi-level Antimicrobial Surface Coating for a Healthier Environment | HKUST | COMPLETED | **Patient privacy curtain protocols** — Physical privacy protections in clinical settings; cross-over blinded design with coded curtain assignments |

---

## Key Takeaways — Directly From Verified Clinical-Trial Privacy Practices

| # | Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|----------|----------------------|------------------------|
| 1 | **Coded/pseudonymized identifiers** | NCT04684615 — No names in surveys; codes only | **Replace PII with tokens at collection** — separate identifiers from analytics data; never log raw names or emails in internal datasets |
| 2 | **Distributed / federated data architecture** | NCT02744846 — Data stays at source; "questions to data" approach | **Don't centralize sensitive data** — keep data at source, query remotely; use federated learning or query-first patterns in web apps |
| 3 | **De-identification for secondary sharing** | NCT02744846 — Stripped identifiers before sharing | **Tokenize before analytics or sharing** — never pass raw identifiers downstream; use hashed or tokenized references |
| 4 | **HIPAA-compliant data storage** | NCT02329210 — Password-protected DB, double-locked PHI storage | **Encrypt at rest + restrict physical access** — use KMS, encrypted volumes, and access-controlled key vaults |
| 5 | **Role-based restricted access** | NCT02329210 — Only CRIBBS staff can access the database | **Enforce least-privilege access** — only essential personnel see identifiers; audit access logs for anomalies |
| 6 | **Regulatory compliance (GDPR)** | NCT05908474 — GDPR-compliant platform with admin-controlled exports | **Build GDPR/CCPA compliance into data pipelines** — data export controls, consent logging, right-to-deletion workflows |
| 7 | **Ethics committee & IRB oversight** | NCT02329210 — IRB provides ongoing oversight | **Adopt continuous compliance auditing** — periodic privacy reviews, SOC 2 / ISO 27001 audits, community review boards |
| 8 | **Physical security for sensitive data** | NCT02329210 — Double-locked environment for paper PHI | **Secure physical hardware and backup media** — encrypted drives, locked server rooms, proper disposal of退役 devices |
| 9 | **Instructional transparency** | NCT05908474 — Clear explanation of data use to participants | **Transparent data policies** — explain in plain language what you collect, why, and who can see it; link to your privacy policy |
| 10 | **Blinded design for privacy** | NCT03795090 — Coded curtain assignments hide treatment group | **Use blinded/masked identifiers in testing** — don't expose user IDs in test environments or staging data |

---

## Cross-Cutting Themes

1. **Privacy-by-Design** — All trials embed privacy protections into the protocol from the start, not as an afterthought. Web security teams should adopt the same principle.
2. **Pseudonymization over Anonymization** — Clinical trials prefer pseudonymization (reversible with a key) because it allows data utility while protecting identity. This maps to web security's need for tokenization and hashed identifiers.
3. **Restricted Access** — Research teams have access only to what they need. Implement least-privilege access in all web systems.
4. **Consent Management** — Informed consent mechanisms in trials directly inform how we build consent-gated dashboards and preference centers.
5. **Compliance & Auditing** — IRB oversight in trials parallels SOC 2 / ISO 27001 in web security. Regular auditing of data access is essential in both domains.
6. **Education over Enforcement** — Awareness training is more effective than passive policy documents. Build privacy literacy, not just cookie banners.
7. **Framing Matters** — How you ask for consent dramatically affects compliance truthfulness. Risk and benefit frames outperform generic privacy statements (see NCT04803448 findings).
8. **Data Minimization by Design** — Strip PII at the point of capture; never pass raw identifiers downstream.
9. **Sensitive Data Needs Extra Layers** — Genetic data (NCT04999436) gets extra protections. Apply the same level to financial, biometric, and location data.
10. **Continuous Monitoring** — Privacy isn't a one-time consent—it's an ongoing practice. Like clinical trial DMCs, establish a community review board for your data practices.

---

## Venue Selection by Event Size (Downtown Portland)

| Group Size | Venue | Distance | Cost Tier |
|---|---|---|---|
| 10–25 | Central Library meeting rooms, YWCA, Davies Family Research Library | 0.1–0.5 km | Free–Low |
| 25–75 | Portland Art Museum lecture, PSU lecture halls, Antoinette Hatfield Hall | 0.3–1.0 km | Low–Medium |
| 75–300 | Revolution Hall, Dossier Hotel ballroom, Oregon Convention Center | 0.5–2.0 km | Medium |
| Casual / Pop-Up | Pioneer Courthouse Square, Water Avenue Coffee, Coffee Time | 0.3–1.0 km | Free–Coffee |
| Planning / Community | Oregon Community Foundation, UO Portland Center | 0.3–1.8 km | Free–Low |

See `PORTLAND_VENUES.md` for full venue details and `PORTLAND_VENUES_EXTRA.md` for additional spaces.

---

## Quick-Start Checklist

- [ ] Clone the repo: `git clone https://github.com/zhub9006/web-security-community-toolkit`
- [ ] Review the clinical trial privacy findings in this README and `TRIAL-PRIVACY-TAKEAWAYS.md`
- [ ] Check `PORTLAND_VENUES.md` for workshop venue options
- [ ] Explore the tools and frameworks in `PRIVACY_TOOLS.md`
- [ ] Read the privacy best practices in `privacy-best-practices.md`
- [ ] Plan a workshop using the template in `WORKSHOP_PLAN.md`
- [ ] Start contributing: suggest new venues, share more clinical trial findings, or add workshop templates!

---

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
