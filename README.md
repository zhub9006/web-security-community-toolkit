# Web Security Community Toolkit

A collaborative security toolkit bridging compliance insights from clinical-trial data privacy practices with web security resources, community documentation, and Portland-area workshop planning.

---

## 🛡️ Compliance Insights from Clinical Trials

We analysed recent studies on ClinicalTrials.gov related to **patient data privacy** and extracted actionable lessons for web security compliance. Below are findings from our research across clinical trials published 2023–2026, combined with key practices from recent direct analysis (NCT07449429, NCT02795806, NCT07308691, NCT06562491, and more).

### Data Protection Practices Observed

#### 1. Automated PII Detection & Removal (NLM Scrubber — NCT02795806)
The U.S. National Library of Medicine (NIH) developed an automated tool that recognizes and removes all 18 categories of Personally Identifiable Information (PII) defined by HIPAA from clinical text. The system compares computer vs. manual de-identification results and iteratively improves accuracy.

> **Web security lesson:** Automate data scrubbing pipelines; don't rely solely on manual redaction. Build GDPR/CCPA data-minimisation & anonymisation APIs. Audit your redaction against gold-standard annotations.

#### 2. On-Premise / Locally-Deployed Processing (Privacy-Preserving OCR-LLM — NCT07449429)
This study deploys OCR and LLM inference on local servers, so patient HPI images are never sent to external APIs. De-identified text is extracted and processed entirely in-house. Individual participant data is not shared publicly.

> **Web security lesson:** For sensitive user data, keep processing on your own servers or use on-device computation. Avoid sending raw PII to third-party APIs (including AI/ML services) unless properly de-identified first.

#### 3. Layered Data Protection — Technical + Administrative + Physical (Rehab Chatbot — NCT07308691)
The study applied password-protected systems, anonymization of stored data, locked physical storage for records, and secure destruction after the retention period. All processes passed Institutional Review Board (IRB) ethics approval with informed consent.

> **Web security lesson:** Apply defense-in-depth — encrypt data at rest and in transit, enforce access controls (RBAC), audit access logs, and define data retention/deletion policies that are technically enforced. Get independent ethics/security review.

#### 4. Pseudonymisation with Least-Privilege Access & Secure Transfer (EGFR Study — NCT06562491)
Patient data was pseudonymised at each site into centre-specific secure Excel files. Access was restricted to the Principal Investigator + max 2 collaborators. Data was transmitted via France's secure national RENATER platform and governed by CNIL regulations; patients could opt out.

> **Web security lesson:** Use pseudonymous identifiers in your databases, enforce least-privilege access, transmit data over secure channels, and give users meaningful opt-out/consent controls (GDPR/CCPA compliance).

#### 5. Informed Consent & Transparency (All Trials)
Multiple trials mandate detailed informed consent explaining purpose, risks, data handling, and privacy measures before enrollment. Patients can withdraw consent at any time.

> **Web security lesson:** Build transparent user consent flows with clear data-use explanations — not just cookie banners, but granular, purpose-specific controls with easy withdrawal.

#### 6. Data Use Agreements & Access Governance (All Trials)
Several trials require signed DUAs prohibiting re-identification, redistribution, and commercial use. Access is logged and audited.

> **Web security lesson:** Enforce data-sharing agreements with explicit usage boundaries. Apply API access terms, rate limiting, scope restrictions, and audit logging.

#### 7. Independent Oversight (DSMB — Various Trials)
Independent Data Safety Monitoring Boards oversee data handling throughout a trial's lifecycle.

> **Web security lesson:** Establish independent oversight for security audits — third-party audits, bug bounty programs, and penetration testing.

#### 8. Client-Side Encryption at Capture (NCT06489847 — Stanford)
Stanford's SPPB++ mobile app specifies that video recording "will be automatically encrypted and securely uploaded to Stanford privacy-protected computer servers."

> **Web security lesson:** Encrypt sensitive data at capture, not just at rest. Client-side encryption before upload prevents interception during transit.

#### 9. De-identified Secure Computing Environments (NCT07590271 — Taichung)
"All data processing will occur within a de-identified and secure computing environment to ensure data privacy and information security."

> **Web security lesson:** Process data in isolated, hardened environments. Apply the principle of least privilege to compute infrastructure — sandbox AI/ML workloads away from production systems.

#### 10. Configuration Error Awareness (NCT07304908 — Peking University)
A European hospital network "inadvertently leaked partially anonymized but still sensitive patient data during the testing of medical LLMs due to a system configuration error."

> **Web security lesson:** Configuration drift is a top breach vector. Implement automated config validation, infrastructure-as-code audits, and blast-radius containment. Public perception of security failures directly impacts trust and adoption.

#### 11. Privacy as Measurable UX (NCT04930198 — Vanderbilt)
Uses validated instruments (FIM, AIM, IAM) that explicitly measure "privacy/security concerns" alongside usability and adoption.

> **Web security lesson:** Make privacy trust measurable. Include privacy-perception questions in UX surveys. Treat security confidence as a KPI alongside conversion and retention.

#### 12. Decentralised Identity + Data Disposal Lifecycle (NCT06150508 — Seoul National University)
Uses DID (Decentralized Identifier) for third-party data sharing, with "disposal of data containing personal information in accordance with the Personal Information Protection Act after three years of archiving."

> **Web security lesson:** Decentralised identity (DID/DIDComm) can replace centralised auth for cross-org data sharing. Define a data disposal lifecycle — retention limits, secure deletion, and compliance-triggered purge schedules.

#### 13. GDPR Controller/Processor Separation + UUID Anonymisation (NCT05487365)
"All data storages are encrypted on the patients' smartphone and a server located in an ISO-certified data centre… all information exchanges are highly secured." Uses UUID-based anonymisation, QR-code anonymous access cards, and clearly delineates data controller vs. processor roles.

> **Web security lesson:** Encrypt at both device and server level (double encryption). Use UUID/anonymous tokens instead of pseudonymous IDs. Clearly document who is the data controller and who is the processor.

#### 14. Re-identification Risk Awareness (NCT07445152 — Zhejiang University)
Explicitly excludes "data samples with privacy protection or legal risks" and notes "there remains a potential risk of re-identifying individual participants if the data are shared without strict restrictions."

> **Web security lesson:** Even de-identified data carries re-identification risk. Proactively audit datasets for re-identification vectors before sharing or publishing. Exclude high-risk data from public APIs and open datasets.

#### 15. Confidentiality as Default Gatekeeper (NCT07524179 — Erzurum Technical University)
"Individual participant data will not be shared due to confidentiality and privacy concerns. The data contain sensitive patient information and institutional review board approval does not include data sharing."

> **Web security lesson:** Treat data confidentiality as a default gatekeeper, not an opt-in. Make "no sharing unless explicitly approved" your default policy — align with IRB/ethics-board thinking for internal data governance.

### Clinical Trials Referenced

| NCT ID | Title | Key Practice |
|---|---|---|
| NCT02795806 | NLM Scrubber — De-identify Clinical Text (NIH) | Automated PII detection; HIPAA compliance |
| NCT07449429 | Privacy-Preserving OCR-LLM System (China/US) | On-premise processing; de-identified pipelines |
| NCT07308691 | Rehab Chatbot (Hong Kong Polytechnic Univ.) | Password protection; anonymisation; locked storage; secure destruction |
| NCT06562491 | EGFR Pathogenic Variants (APHP, France) | Pseudonymisation; RENATER secure platform; CNIL opt-out |
| NCT06489847 | SPPB++ Mobile App (Stanford) | Client-side encryption at capture |
| NCT07590271 | AI-IBD Study (Taichung) | De-identified secure computing environments |
| NCT07304908 | LLM Acceptance Study (Peking Univ.) | Configuration-error breach awareness |
| NCT04930198 | PeerNaija mHealth Study (Vanderbilt) | Privacy as measurable UX factor |
| NCT06150508 | Smart O2O Digital Health (Seoul Nat'l Univ.) | Blockchain DID; data disposal lifecycle |
| NCT05487365 | BEDICARE-HF Telemonitoring (Comunicare) | GDPR double encryption; UUID anonymisation |
| NCT07445152 | Multimodal Imaging AI (Zhejiang Univ.) | Re-identification risk exclusion |
| NCT07524179 | Palliative Care IT (Erzurum Tech Univ.) | Confidentiality as default gatekeeper |

### Cross-Domain Summary: Clinical Trial → Web Security

| Clinical Practice | Web Security Adaptation |
|---|---|
| HIPAA de-identification (18 PII types) | GDPR/CCPA data minimisation & anonymisation APIs |
| On-premise OCR/LLM processing | Self-hosted services; no raw PII to third parties |
| Password + encryption + physical security | Defense-in-depth: encrypt, RBAC, audit |
| Informed consent protocols | Transparent consent flows with granular controls |
| Data Use Agreements | API access terms, rate limiting, scope restrictions |
| DSMB independent oversight | Third-party security audits & bug bounty programs |
| Auto-encryption at capture | Client-side encryption before server upload |
| De-identified secure compute | Sandboxed AI/ML, least-privilege infra |
| Config-error breach awareness | Automated config validation, IaC audits |
| Privacy as measurable UX | Privacy-perception KPIs in UX surveys |
| Blockchain DID + data disposal | Decentralised identity; retention & purge schedules |
| GDPR controller/processor + UUID | Double encryption; anonymous tokens; clear roles |
| Re-identification risk exclusion | Audit datasets for re-ID vectors before sharing |
| Confidentiality as default gatekeeper | "No sharing unless approved" default policy |

---

## 📍 Portland, Oregon — Workshop & Meetup Venues

All locations are within **~2 km of downtown Portland's central area** (SW Park Ave / SW 6th Ave corridor).

### Community & Workshop Spaces (Best for Events)

| Venue | Address | Type | Distance | Notes |
|---|---|---|---|---|
| **Portland Community College — Downtown Center** | 722 SW 2nd Ave | College / Classroom | ~0.4 km | Purpose-built for training; AV equipment; affordable community rates |
| **Portland State University** | 1825 SW Broadway | University | ~0.3 km | Lecture halls, classrooms; academic partnership potential; SW Broadway |
| **Central Library (Multnomah County)** | 801 SW 10th Ave | Library | ~0.4 km | Meeting rooms for community groups; free booking; excellent WiFi |
| **Portland Center Stage at The Armory** | 128 NW 11th Ave (Pearl District) | Theatre / Event | ~0.9 km | Historic Pearl District building; versatile event spaces |
| **Oregon Convention Center** | 777 NE MLK Jr Blvd (Lloyd District) | Conference Centre | ~2.5 km | Largest venue in OR; breakout rooms; MAX Light Rail accessible |
| **Matt Dishman Community Center** | 77 NE Knott St (Eliot) | Community Centre | ~3 km | Portland Parks & Rec; gym, meeting rooms; affordable |
| **Oregon Historical Society** | 1200 SW Park Ave | Museum / Event | ~0.1 km | Cultural event space in heart of downtown |

### Informal Meetup Spots (Cafés with WiFi)

| Venue | Address | Highlights |
|---|---|---|
| **Portal Tea** | 734 NW 23rd Ave | Indoor seating, **free WiFi**, tea-focused, secluded |
| **Case Study Coffee Roasters** | 1400 NW 23rd Ave | WiFi, outdoor seating, great for 5–15 person groups |
| **Starbucks (23rd & Burnside)** | 2328 W Burnside | WiFi, wheelchair accessible, reliable |
| **Pepino's** | 914 NW 23rd Ave | Mexican restaurant, group-friendly |
| **Papa Haydn** | 635 NW 23rd Ave | Regional American, full-service, **wheelchair accessible** |
| **Jo Bar** | 715 NW 23rd Ave | Pub/gastropub, WiFi, wheelchair accessible |
| **Hop City Tavern** | 921 SW 6th Ave (Hilton) | Hotel restaurant, large groups, accessible |

### Venue Recommendations by Event Type

- **Monthly meetup (10–30 people):** Portal Tea or Case Study Coffee (casual, WiFi, central NW 23rd Ave corridor)
- **Workshop / training (20–60 people):** PCC Downtown Center (classrooms, AV) or PSU lecture halls (academic credibility)
- **Mid-size presentations (50–100 people):** Central Library meeting rooms (free) or The Armory event spaces (professional Pearl District vibe)
- **Annual conference (200+ people):** Oregon Convention Center (full AV, catering, breakout rooms, MAX transit)
- **Community social / networking:** Papa Haydn, Jo Bar, or Matt Dishman Community Center (affordable, flexible hours)

---

## 🔒 Security Resources

- [OWASP Top 10](https://owasp.org/www-project-top-ten/) — Checklists for common web vulnerabilities
- [OWASP Web Security Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [NIST Privacy Framework](https://www.nist.gov/privacy-framework)
- [GDPR Official Text](https://gdpr-info.eu/)
- [CCPA/CPRA California Privacy Rights](https://oag.ca.gov/privacy/ccpa)

---

## 🤝 Contributing

We welcome contributions! Please open issues or submit pull requests. Areas of interest:
- New clinical-trial privacy analyses
- Portland venue reviews and updates
- Workshop curriculum proposals
- Security tool recommendations
- Greyhat / bug bounty resources

---

## 📄 License

MIT License — see LICENSE file for details.

---

## 🔗 Quick Links

- **GitHub:** https://github.com/zhub9006/web-security-community-toolkit
- **Clone:** `git clone https://github.com/zhub9006/web-security-community-toolkit.git`
- **ClinicalTrials.gov:** https://clinicaltrials.gov