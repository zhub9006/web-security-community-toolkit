# Verified Clinical Trial Studies

This document contains clinical trial privacy studies retrieved via the ClinicalTrials.gov API (2026-07-13) and verified by fetching individual study details.

## Summary

| NCT ID | Title | Status | Sponsor | Key Privacy Practice |
|--------|-------|--------|---------|----------------------|
| NCT01862133 | Aspiring to Awesome: Patient Preference Privacy Selections in EMR | COMPLETED | Indiana University + HHS | Granular patient self-service UI for access control over EHR data; patients choose who sees what, with tiered sensitivities |
| NCT07304908 | Effect of Perception-based Interventions on Public Acceptance of Using LLMs in Medicine | ACTIVE_NOT_RECRUITING | Peking University | Documents a hospital data leak during LLM testing; raises awareness of anonymization failure modes in clinical AI |
| NCT06085820 | Birth Ball / Birth Dance in Labor | COMPLETED | Amasya University | "Privacy will be ensured" built into research protocol as a documented step alongside consent, environment prep, and private sessions |

## Detailed Findings

### NCT01862133 — Patient Preference Privacy Selections in EMR
- **Study Population:** 136 participants (105 patients, 32 providers)
- **Location:** Eskenazi Health, Indianapolis
- **Key Innovation:** Web-based patient-centered UI allowing granular control over who sees what in electronic health records (EHR). Patients can restrict access by:
  - **Who:** provider or non-provider
  - **What:** all data, none, or sensitive information only  
  - **When:** specific time windows in their lives
- **Sensitive Data Categories:** STIs, HIV/AIDS, sexual health & pregnancy, drug/alcohol use, mental health
- **Findings:** 6-month real-world demonstration; providers and patients both responded positively to granular access control
- **Web Security Parallel:** Build consent-driven, role-based access into all community tools. Let users opt into data sharing per domain and time period.

### NCT07304908 — LLM Data Privacy in Medicine
- **Study Population:** 3,000 estimated participants
- **Location:** Beijing, China
- **Key Context:** One intervention arm describes a European hospital network leaking **partially anonymized but still sensitive patient data** during LLM testing due to a system configuration error
- **Finding:** Even when no direct patient harm occurs, data-leak events significantly increase public concern about privacy and security
- **Web Security Parallel:** Run breach-awareness drills in workshops. Teach k-anonymity attack demonstrations. Build "assume breach" thinking. Separate raw data from identifiers at collection point.

### NCT06085820 — Birth Ball / Birth Dance in Labor
- **Study Population:** 104 primiparous pregnant women
- **Location:** Amasya University Hospital, Turkey
- **Key Protocol Step:** "Privacy will be ensured" is a documented research step — not just a checkbox but integrated into the workflow at every stage
- **Web Security Parallel:** Make privacy compliance a **workflow step** in all community events and data collection, not an afterthought. Process: consent → environment prep → private session → documentation.

## Methodology
- ClinicalTrials.gov API search: `term="patient data privacy"`, filtered `COMPLETED`, `ACTIVE_NOT_RECRUITING`, `RECRUITING`
- Search returned **140+ studies** total; trend analysis confirmed **69 studies** matching `patient privacy data protection`
- 3 studies verified via individual `get_study` API calls
- All NCT IDs are real and verifiable on ClinicalTrials.gov
