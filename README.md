# Web Security Community Toolkit

A collaborative security toolkit bridging compliance insights from clinical-trial data privacy practices with web security resources, community documentation, and workshop planning.

## 📁 Repository Structure

```
web-security-community-toolkit/
├── compliance-insights/     # Lessons from clinical-trial data privacy
├── security-resources/      # Web security tools, checklists, guides
├── community-docs/          # Workshop planning, meetup logistics, venue info
└── README.md
```

---

## 🔒 Compliance Insights from Clinical Trials

We analysed recent studies on ClinicalTrials.gov related to **patient data privacy** and extracted actionable lessons for web security compliance. Below is an expanded set of findings combining our original research with new 2024–2026 trials.

### Data Protection Practices Observed

#### 1. De-identification & Pseudonymization
The NLM Scrubber trial (NCT02795806) developed a HIPAA-compliant automated tool that removes 18 types of PII from clinical text.
> **Web security lesson:** Automate data scrubbing pipelines; don't rely solely on manual redaction. Build GDPR/CCPA data-minimisation & anonymisation APIs.

#### 2. Polymorphic Encryption & Pseudonymization (PEP)
The Personalized Parkinson Project (NCT03364894) pioneered PEP methodology combining advanced encryption with distributed pseudonymization and data access management.
> **Web security lesson:** Layer encryption with access controls for shared datasets. Adopt zero-knowledge proofs & encrypted user data stores.

#### 3. Federated Learning / Data Stays at Source
The EURACAN Rare Cancer Registry (NCT05483374) uses federated learning via Vantage6 so identifiable data never leaves its originating institution.
> **Web security lesson:** Minimize data movement; compute where data resides. Embrace edge computing / local-first web architectures.

#### 4. Informed Consent & Transparency
Multiple trials mandate detailed informed consent explaining purpose, risks, and privacy measures before enrollment.
> **Web security lesson:** Build transparent user consent flows with clear data-use explanations — not just cookie banners, but granular, purpose-specific controls.

#### 5. Data Use Agreements & Access Governance
Several trials require signed DUAs prohibiting re-identification, redistribution, and commercial use.
> **Web security lesson:** Enforce data-sharing agreements with explicit usage boundaries. Apply API access terms, rate limiting, and scope restrictions.

#### 6. Independent Data Safety Monitoring
Trials like NCT07378683 use independent Data Safety Monitoring Boards (DSMBs) to oversee data handling throughout.
> **Web security lesson:** Establish independent oversight for security audits — third-party audits & bug bounty programs.

#### 7. Automatic Encryption & Secure Upload (NEW — NCT06489847)
Stanford University's SPPB++ mobile app study specifies that *"video recording will be automatically encrypted and securely uploaded to Stanford privacy-protected computer servers."*
> **Web security lesson:** Encrypt sensitive data **at capture**, not just at rest. Client-side encryption before upload prevents interception during transit.

#### 8. De-identified Secure Computing Environments (NEW — NCT07590271)
Taichung Veterans General Hospital's AI-IBD study mandates that *"all data processing will occur within a de-identified and secure computing environment to ensure data privacy and information security."*
> **Web security lesson:** Process data in isolated, hardened environments. Apply the principle of least privilege to compute infrastructure — sandbox AI/ML workloads away from production systems.

#### 9. Configuration Errors as a Breach Vector (NEW — NCT07304908)
Peking University's LLM acceptance study highlights a real incident where *"a major European hospital network inadvertently leaked partially anonymized but still sensitive patient data during the testing of medical LLMs due to a system configuration error."* This arm explicitly tests whether public perception of such privacy failures reduces adoption.
> **Web security lesson:** Configuration drift is a top breach vector. Implement automated config validation, infrastructure-as-code audits, and blast-radius containment. Also: public perception of security failures directly impacts user trust and adoption.

#### 10. Privacy Concerns as a Measurable UX Factor (NEW — NCT04930198)
Vanderbilt's PeerNaija mHealth app study uses validated instruments (FIM, AIM, IAM) that explicitly measure *"privacy/security concerns"* alongside usability and adoption.
> **Web security lesson:** Make privacy trust measurable. Include privacy-perception questions in UX surveys. Treat security confidence as a KPI alongside conversion and retention.

#### 11. Blockchain Identity + Regulated Data Disposal Lifecycle (NEW — NCT06150508)
Seoul National University's Smart O2O digital health trial uses *"DID (Decentralized Identifier, a distributed identification technology based on blockchain technology)"* for third-party data sharing, and mandates *"disposal of data containing personal information in accordance with the Personal Information Protection Act after three years of archiving."*
> **Web security lesson:** Decentralised identity (DID/DIDComm) can replace centralised auth for cross-org data sharing. Define a **data disposal lifecycle** — retention limits, secure deletion, and compliance-triggered purge schedules.

#### 12. GDPR Compliance, Controller/Processor Separation, UUID Anonymization (NEW — NCT05487365)
Comunicare Solutions' BEDICARE-HF telemonitoring study implements a full GDPR framework: *"All data storages are encrypted on the patients' smartphone and a server located in an ISO-certified data centre… all information exchanges are highly secured."* It uses UUID-based anonymisation, QR-code anonymous access cards, and clearly delineates data controller vs. processor roles.
> **Web security lesson:** Encrypt at both **device and server** level (double encryption). Use UUID/anonymous tokens instead of pseudonymous IDs. Clearly document who is the data controller and who is the processor in your privacy policy.

#### 13. Re-identification Risk Awareness & Proactive Exclusion (NEW — NCT07445152)
Zhejiang University's multimodal medical imaging AI study explicitly excludes *"data samples with privacy protection or legal risks"* and states IPD will not be shared because *"there remains a potential risk of re-identifying individual participants if the data are shared without strict restrictions."*
> **Web security lesson:** Even de-identified data carries re-identification risk. Proactively audit datasets for re-identification vectors before sharing or publishing. Exclude high-risk data from public APIs and open datasets.

#### 14. Data Confidentiality as a Gatekeeper (NEW — NCT07524179)
Erzurum Technical University's palliative care study refuses IPD sharing with the rationale: *"Individual participant data will not be shared due to confidentiality and privacy concerns. The data contain sensitive patient information and institutional review board approval does not include data sharing."*
> **Web security lesson:** Treat data confidentiality as a default gatekeeper, not an opt-in. Make "no sharing unless explicitly approved" your default policy — align with IRB/ethics-board thinking for internal data governance.

---

### Cross-Domain Lessons for Web Security

| Clinical Trial Practice | Web Security Adaptation |
|---|---|
| HIPAA de-identification (18 PII types) | GDPR/CCPA data minimisation & anonymisation APIs |
| Polymorphic encryption (PEP) | Zero-knowledge proofs & encrypted user data stores |
| Federated learning (data-at-source) | Edge computing / local-first web architectures |
| Informed consent protocols | Transparent cookie/consent banners with granular controls |
| Data Use Agreements (DUAs) | API access terms, rate limiting, scope restrictions |
| DSMB independent oversight | Third-party security audits & bug bounty programs |
| Automatic encryption at capture (NCT06489847) | Client-side encryption before server upload |
| De-identified secure compute (NCT07590271) | Sandboxed AI/ML workloads, least-privilege infrastructure |
| Config-error breach awareness (NCT07304908) | Automated config validation, IaC audits, blast-radius containment |
| Privacy as measurable UX (NCT04930198) | Privacy-perception KPIs in UX surveys |
| Blockchain DID + data disposal (NCT06150508) | Decentralised identity for cross-org auth; data retention & purge schedules |
| GDPR controller/processor + UUID (NCT05487365) | Double encryption (device+server); anonymous tokens; clear controller/processor roles |
| Re-identification risk exclusion (NCT07445152) | Audit datasets for re-ID vectors before sharing |
| Confidentiality as default gatekeeper (NCT07524179) | "No sharing unless approved" default policy |

---

## 📍 Portland, Oregon — Workshop & Meetup Venues

We identified community-friendly venues near downtown Portland (within ~2 km of SW Park Ave & SW 6th Ave) suitable for security workshops and meetups:

| Venue | Type | Address | Distance from Downtown Core | Notes |
|---|---|---|---|---|
| **Central Library** | Library | 801 SW 10th Ave, Portland 97205 | ~0.4 km | Multnomah County's flagship library; meeting rooms available for community groups; free booking |
| **Portland State University** | University | 1825 SW Broadway, Portland 97201 | ~0.3 km | Lecture halls, classrooms, and event spaces; academic partnership potential |
| **Portland Center Stage at The Armory** | Theatre / Event venue | 128 NW 11th Ave, Pearl District 97209 | ~0.9 km | Historic Pearl District building; versatile event spaces; rentable for community events |
| **Oregon Convention Center** | Conference centre | 777 NE MLK Jr Blvd, Lloyd District 97204 | ~2.6 km | Largest venue in OR; ideal for large conferences (500+); MAX Light Rail accessible |
| **Matt Dishman Community Center** | Community centre | 77 NE Knott St, Eliot 97212 | ~3 km | Portland Parks & Rec facility; gym, meeting rooms, classrooms; affordable community rates |

### Venue Recommendations by Event Type

- **Monthly meetup (20–50 people):** Central Library meeting rooms (free, central, WiFi) or Matt Dishman Community Center (affordable, flexible hours)
- **Hands-on workshop (30–80 people):** Portland State University classrooms (AV equipment, academic credibility) or The Armory event spaces (professional setting, Pearl District vibe)
- **Annual conference (200+ people):** Oregon Convention Center (full AV, catering, breakout rooms, transit access)

---

## 🛡️ Security Resources

See `security-resources/` for:
- OWASP Top 10 checklists
- Secure coding guidelines
- Incident response templates
- Authentication best practices

---

## 🤝 Contributing

We welcome contributions! Please open issues or submit pull requests. Areas of interest:
- New clinical-trial privacy analyses
- Portland venue reviews and updates
- Workshop curriculum proposals
- Security tool recommendations

---

## 📜 License

MIT License — see LICENSE file for details.
