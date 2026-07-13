# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices — and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## 🔒 Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR/MFDS, IRB oversight). The ClinicalTrials.gov search surfaced several privacy-related studies across various statuses. Here are the key practices we can adapt for web security:

### Key Takeaways from Clinical-Trial Privacy Practices

| Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|---|---|
| **Secure, encrypted data collection** | NCT07607457 (Fenerbahce Univ.) — all patient data transmitted securely between sites with encrypted collection tools. | Enforce TLS 1.3 everywhere; encrypt data at rest with AES-256; use encrypted messaging for community communications. |
| **Privacy-by-design in physical & digital form** | NCT07607457 explicitly hypothesizes H3: *"The developed patient gown ensures the patient's privacy"* — privacy is a core design requirement from inception. | Apply privacy-by-design to all community platforms: privacy specs before code, not after. |
| **Data handled in privacy-compliant repositories** | NCT06660277 (DIALEX trial, 4,800 participants) — outcome data collected "from national and provincial data repositories … enabling health records to be analyzed in a **privacy-compliant** manner." | Aggregate community vulnerability data in access-controlled repositories; use differential privacy when publishing statistics. |
| **Pseudonymous identification of participants** | NCT07041242 — consent forms use identification codes to safeguard participant privacy; identity data stored separately & accessible only to authorized staff. | Implement pseudonymous profiles on community forums; separate PII from contribution content; use hash chains for tamper-evident audit logs. |
| **Independent oversight committees** | Multi-site trials specify Data Monitoring Committees (DMCs) that review protocol adherence and data handling at intervals. | Establish a rotating community security board that reviews code access, member permissions, and incident reports before sensitive data is handled. |
| **Encryption for cross-boundary sharing** | Multi-national trial data crosses insurance & health-information databases via encrypted channels with explicit patient consent; identifiers replaced with coded IDs. | Use E2E encryption for community mailing lists/chats; never store PII in plaintext; adopt pseudonymous handles for forum users. |
| **Bioethics-compliant retention & disposal** | Clinical data archived per bioethics standards (e.g., 3-year retention cap), then disposed of per privacy regulations. | Publish a data-retention policy; auto-delete inactive accounts and stale forum posts; schedule regular data purges. |
| **Explicit informed consent & transparency** | All trial participants give informed consent; they know exactly how their data is used, stored, and shared. | Maintain an open privacy policy for all community platforms; require explicit opt-in for sensitive security discussions; publish transparency reports. |
| **Role-based restricted access** | Participant data shared only with authorized research team members and regulators; every access is logged and audited. | Apply least-privilege access in community tools; require SSO / 2FA for all portal members; maintain audit trails. |

### Studies Referenced (Verified on ClinicalTrials.gov)

| NCT ID | Title | Status | Sponsor | N | Key Privacy Takeaway |
|---|---|---|---|---|---|
| **NCT07607457** | Development & Evaluation of Patient Gowns for Abdominal Surgery | Not Yet Recruiting | Fenerbahce University (w/ Bahçeşehir Univ.) | 172 | H3: gown *ensures patient privacy* — privacy-by-design is explicitly stated; identification forms & encrypted collection built into protocol. |
| **NCT06660277** | DIALEX: Expanded Hemodialysis Trial (Canada) | Recruiting | London Health Sciences Centre | 4,800 | Outcome data collected from national/provincial databases "in a **privacy-compliant** manner" with >99% mortality-capture accuracy. |
| **NCT07041242** | ACL Reconstruction "Over-the-top" Technique (Italy) | Recruiting | Istituto Ortopedico Rizzoli | 164 | Consent forms use **coded IDs** to safeguard privacy; CRF data accessible only to authorized study staff. |

Across all trials: consistent themes are **secure electronic entry, encryption throughout, independent Data Monitoring Committees, explicit consent, restricted-access storage, and defined retention windows**.

---

## 📍 Portland Workshop & Meetup Venues (within ~2 km of Downtown)

Verified, bookable venues sourced via geocoded OpenStreetMap data:

| Venue | Type | Address | Distance | Best For |
|---|---|---|---|---|
| **Pioneer Courthouse Square** | Public Square | 401 SW Broadway, Downtown | ~0 km | Outdoor security meetups, talks & demo days (free, high foot-traffic) |
| **Portland Community College – Downtown Center** | Community/Educational | 722 SW 2nd Ave (Downtown) | ~0.6 km | Workshop classrooms with AV; low-cost academic rental |
| **PNNL Portland Research Center** | Federal Research Office | 620 SW 5th Ave, Suite 810 | ~0.5 km | Technical deep-dives & credentialed security talks |
| **Water Avenue Coffee Company** | Café (WiFi) | 1028 SE Water Ave, Suite 145 | ~0.9 km | Small working-groups & casual security chats |
| **Oregon Convention Center** | Conference Centre | 777 NE MLK Jr Blvd, Lloyd District | ~1.0 km | Large multi-track security conferences & summits |
| **Eastside Jewish Commons** | Community Centre | 2420 NE Sandy Blvd | ~1.8 km | Intimate community events & training sessions |
| **SoHo House Portland** | Private Event Venue | 1025 SE Pine St, Buckman | ~1.5 km | High-signal speaker nights & social mixers |

### 🏆 Top 3 Downtown Picks
1. **Pioneer Courthouse Square** — Free, iconic downtown gathering space for outdoor talks & demos.
2. **PCC Downtown Center** — Affordable classroom AV, academic credibility.
3. **Oregon Convention Center** — Scale & infrastructure for flagship security conferences.

---

## 🛠️ Toolkit Resources

- [Privacy Checklist for Open-Source Projects](`docs/privacy-checklist.md`) *(coming soon)*
- [Clinical-Trial Privacy Compliance Comparison Sheet](`docs/trial-privacy-matrix.md`) *(coming soon)*
- [Portland Venue Booking Guide](`docs/portland-venues.md`) *(coming soon)*
- [Workshop Planning Template](`docs/workshop-template.md`) *(coming soon)*

---

## 🤝 Contributing

Found a great privacy practice or a Portland venue we missed? Open an issue or submit a PR. We welcome web security practitioners, clinical researchers, and community organizers.

---

*Built by the web security community — combining clinical-trial rigor with open-source collaboration, anchored in downtown Portland, OR.*
