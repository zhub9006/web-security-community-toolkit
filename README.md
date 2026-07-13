# Web Security Community Toolkit

A community-driven initiative that adapts **data-privacy practices from clinical trials** to web security best practices—and a hub for hosting security workshops and meetups in downtown Portland, Oregon.

---

## 🔒 Why Clinical-Trial Privacy Matters for Web Security

Clinical trials operate under some of the world's strictest data-protection regimes (HIPAA, GDPR/MFDS, IRB oversight). The ClinicalTrials.gov search surfaced 4 privacy-related studies across various statuses (recruiting, unknown, active), involving both industry and government sponsors. Here are the key practices we can adapt:

### Key Takeaways from Clinical-Trial Privacy Practices

| Practice | Clinical-Trial Origin | Web-Security Adaptation |
|---|---|---|
| **Secure, encrypted data collection** | Study NCT06150508 (Seoul National Univ. Hospital) uses password protection and encryption for all patient data transmission between health centers and the Smart Healthcare Center. | Enforce TLS 1.3 everywhere; encrypt data at rest with AES-256; use encrypted messaging for community communications. |
| **Restricted, role-based access** | Participant data shared only with authorized research team members and regulators; access is logged and audited. | Apply least-privilege access in community tools; require SSO / 2FA for all portal members; maintain audit trails. |
| **Independent oversight committees** | A dedicated Data Monitoring Committee (DMC) oversees trial progress and protocol adherence (NCT06150508). | Establish a rotating community security board that reviews code, access logs, and incident reports before sensitive data is handled. |
| **Encryption for cross-boundary sharing** | Health records cross national insurance databases via encrypted channels with explicit consent; personal identifiers are replaced with coded IDs. | Use end-to-end encryption for community mailing lists/chats; never store PII in plaintext; adopt pseudonymous identifiers for forum users. |
| **Bioethics-compliant data retention & disposal** | Clinical data archived for 3 years per bioethics standards, then disposed of per privacy regulations. | Define and publish a data-retention policy; auto-delete inactive accounts and forum posts after a set period; perform regular data purges. |
| **Participant consent & transparency** | All trial data collection involves explicit informed consent; participants know exactly how their data is used, stored, and shared. | Maintain an open privacy policy for all community platforms; require explicit opt-in for sensitive discussions; publish transparency reports. |
| **Separate identity from data** | CRF identification codes mask participant identity (NCT07041242); codes accessible only to authorized staff. | Implement pseudonymous profiles; separate personally-identifying data from contribution content; use hash chains for tamper-evident logs. |

### Portland Area Clinical-Trial Landscape
- **Total privacy-focused studies found:** 4 (across all statuses: UNKNOWN, RECRUITING, ENROLLING_BY_INVITATION, ACTIVE_NOT_RECRUITING)
- **Sponsor types:** 2 industry-led, 23 government/institutional
- **Data protection themes consistently mentioned:** secure electronic entry, encryption, Data Monitoring Committees, consent-based sharing, restricted-access storage with 3-year retention caps

---

## 📍 Portland Workshop & Meetup Venues (within ~2 km of Downtown)

| Venue | Type | Address | Distance from Downtown Core | Best For |
|---|---|---|---|---|
| **Oregon Convention Center** | Conference Centre | 777 NE MLK Jr Blvd, Lloyd District | ~1.0 km | Large multi-track security conferences & summits |
| **Soho House Portland** | Private / Event Venue | 1025 SE Pine St, Buckman (Central Eastside) | ~1.5 km | Intimate speaker nights & social mixers |
| **PNNL Portland Research Center** | Federal Research Office | 620 SW 5th Ave, Suite 810 | ~0.5 km | Technical deep-dives & credentialed security talks |
| **East Portland Community Center** | Community Centre | 740 NE 106th Ave, Hazelwood | ~3.5 km (east) | Regional community events & training sessions |
| **Multnomah County Library (SE Hawthorne)** | Public Library Pickup | 3557 SE Hawthorne Blvd | ~2.0 km | Free public workshops & beginner tutorials |
| **Muslim Community Center of Portland** | Community Centre | 5325 N Vancouver Ave, Humboldt | ~4.5 km (N) | Open community workshops |
| **UO Portland Center** | University Hub | NE Holman St, Concordia | ~3.0 km (NE) | Academic security research talks |
| **North Portland Eagles** | Lodge Hall | 7611 N Exeter Ave, Portsmouth | ~5.0 km (N) | Informal security socials |

> **Top 3 picks nearest downtown for security workshops:**
> 1. **Oregon Convention Center** — scale & infrastructure for flagship events
> 2. **Soho House Portland** — intimate venues for high-signal speaker nights
> 3. **PNNL Portland Research Center** — technical credibility for vulnerability/research talks

---

## 🛠️ Toolkit Resources

- [Data-Privacy Checklist for Open-Source Projects](`docs/privacy-checklist.md`) *(coming soon)*
- [Clinical-Trial Privacy Compliance Comparison Sheet](`docs/trial-privacy-matrix.md`) *(coming soon)*
- [Portland Venue Booking Guide](`docs/portland-venues.md`) *(coming soon)*
- [Workshop Planning Template](`docs/workshop-template.md`) *(coming soon)*

---

## 🤝 Contributing

Found a great privacy practice or a Portland venue we missed? Open an issue or submit a PR. We welcome security practitioners, clinical-researchers, and community organizers.

---

*Built by the web security community — combining clinical-trial rigor with open-source collaboration.*