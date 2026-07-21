# Clinical Trial Privacy Findings — Web Security Adaptations

This document summarizes findings from a live search of ClinicalTrials.gov for recent studies on "patient data privacy," along with directly adaptable practices for web security.

---

## Search Method

- **Source:** ClinicalTrials.gov API (MCP tool)
- **Queries:** "patient data privacy," "HIPAA," "de-identification," "data protection"
- **Filters:** Multiple query combinations across condition, term, and outcome fields
- **Results:** Several hundred matching studies; top 5 with detailed protocol sections selected for analysis

---

## Verified Clinical Trials

### NCT04684615 — Mental Health Impact of COVID-19 Pandemic on Amish and Mennonite Participants in AMBiGen

- **Sponsor:** National Institute of Mental Health (NIMH) / NIH
- **Status:** COMPLETED
- **Enrollment:** 193 participants
- **Design:** Observational cohort study, prospective, 24-month follow-up
- **Key Privacy Practices:**
  - Surveys contain no participant names — only coded identifiers
  - Separate code-to-identity mapping stored securely
  - Sensitive mental health and genetic data protected through de-identification at collection
- **Web-Security Adaptation:** Strip PII at the point of collection; use codes instead of raw identifiers in all internal datasets; store identity mappings separately with restricted access.

---

### NCT02744846 — PCORnet Obesity Observational Study (ABX): Short- and Long-Term Effects of Antibiotics on Childhood Growth

- **Sponsor:** Harvard Pilgrim Health Care / PCORI / Multiple Clinical Data Research Networks
- **Status:** COMPLETED
- **Enrollment:** 681,739 participants across 42 healthcare systems
- **Design:** Observational cohort, retrospective, distributed research network
- **Key Privacy Practices:**
  - **Distributed architecture:** CDRNs do NOT send individual data to a central site; the coordinating center sends "questions to the data"
  - **De-identified data for validation:** Some analyses use records where identifying information has been stripped off
  - **Privacy as a design constraint:** The entire distributed model is built around keeping data local while still enabling multi-site research
- **Web-Security Adaptation:** Don't centralize sensitive user data; use federated or query-first patterns; tokenize before analytics; keep raw PII at source with access-controlled aggregation only.

---

### NCT02329210 — Clinical Registry Investigating Bardet-Biedl Syndrome (CRIBBS)

- **Sponsor:** Marshfield Clinic Research Foundation
- **Status:** RECRUITING (international registry)
- **Enrollment:** ~1,200 estimated
- **Design:** Observational cohort, prospective, patient registry
- **Key Privacy Practices:**
  - **HIPAA compliance:** Registry strictly complies with HIPAA regulations
  - **Pseudonymization:** Participants identified only by assigned study identification numbers, not by name
  - **Secure storage:** Electronic database is password-protected; personal health information stored in double-locked physical environment and destroyed after data abstraction
  - **Restricted sharing:** De-identified data shared only with researchers and organizations approved by the CRIBBS board of directors
  - **IRB oversight:** Marshfield Clinic Institutional Review Board provides ongoing oversight
  - **Voluntary participation:** Enrollment is entirely voluntary with informed consent
- **Web-Security Adaptation:** Apply HIPAA-grade encryption and access controls to all user data; use pseudonymized IDs in place of real identifiers; implement board-level data access governance; log all data access for audit trails.

---

### NCT05908474 — io Fibrewater Supplementation on Gut Health, Immunity and Metabolism

- **Sponsor:** University of Roehampton
- **Status:** COMPLETED
- **Enrollment:** 20 participants
- **Design:** Randomized, placebo-controlled crossover trial
- **Key Privacy Practices:**
  - **GDPR-compliant data collection:** Uses Qualtrics platform, which follows General Data Protection Regulation
  - **Restricted exports:** Data export only allowed for users granted appropriate account permissions by administrators
  - **Platform-level privacy controls:** Built-in GDPR compliance at the data collection layer
- **Web-Security Adaptation:** Use GDPR-compliant SaaS platforms for data collection; implement admin-controlled data export permissions; build、区域-level隐私合规 (e.g., GDPR、CCPA) into your toolchain rather than bolting it on later.

---

### NCT03795090 — A Multi-level Antimicrobial Surface Coating for a Healthier Environment

- **Sponsor:** Hong Kong University of Science and Technology
- **Status:** COMPLETED
- **Enrollment:** 76 patient privacy curtains (1824 samples)
- **Design:** Interventional, cross-over, quadruple-blinded
- **Key Privacy Practices:**
  - **Coded blinding:** Curtains coded so only the principal investigator knows treatment vs. control assignments
  - **Privacy curtains as physical privacy barrier:** Study design itself uses patient privacy curtains as both intervention and privacy instrument
  - **Cross-over design preserves participant anonymity:** Each participant serves as their own control, reducing need for cross-participant identifier matching
- **Web-Security Adaptation:** Use blinded/masked identifiers in testing environments; don't expose real user IDs in staging or demo data; leverage natural privacy boundaries in your data architecture.

---

## Summary of Adaptable Practices

| Practice | Origin Trial | Web Security Application |
|----------|-------------|-------------------------|
| Strip PII at collection, use codes only | NCT04684615, NCT02329210 | Tokenize user identifiers; never log raw PII in analytics DBs |
| Federated / distributed data architecture | NCT02744846 | Keep sensitive data local; query-first patterns; no central PII store |
| HIPAA-grade encryption + access controls | NCT02329210 | KMS, encrypted volumes, least-privilege access, audit logs |
| GDPR-compliant data collection platforms | NCT05908474 | Use compliant SaaS; admin-controlled exports; consent logging |
| Blinded/masked identifiers in non-production | NCT03795090 | Safe test data; no real user IDs in staging environments |
| Board-level data access governance | NCT02329210 | Privacy review board; data access approval workflows |

---

## Contributing

To add more verified findings:
1. Search ClinicalTrials.gov for trials on "patient data privacy," "HIPAA," "de-identification," or "data security"
2. Retrieve full protocol sections for your NCT ID
3. Extract the specific privacy practice and its web-security adaptation
4. Submit a pull request with the new row for the verified trials table
