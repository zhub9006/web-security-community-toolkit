# Privacy Takeaways from Clinical Trials

> Extracted from live ClinicalTrials.gov API searches (2026-07-13). See README.md for the full table.

## Study 1: NLM Scrubber — HIPAA De-identification (NCT02795806)

- **Sponsor:** National Library of Medicine (NIH)
- **Status:** ENROLLING_BY_INVITATION
- **What it does:** Automated tool that finds and deletes **18 types of personally identifiable information** (names, addresses, dates, SSNs) from clinical text reports. Research conducted per HIPAA Privacy Rule and Privacy Act. Trained and validated on 50k+ clinical reports.
- **Web Adaptation:** Build **automated PII redaction middleware** for community platforms. Scrub emails, IPs, usernames, and API keys from logs before storage. Treat PII like PHI — classify, encrypt, redact at the data-ingestion layer.

## Study 2: Digital Media Privacy Literacy Training (NCT06885580)

- **Sponsor:** Ataturk University
- **Status:** COMPLETED
- **What it does:** 8-session privacy literacy training for students ages 9–12. Used validated **Privacy Consciousness Scale** and **Autonomy Survey** to measure impact. Found that structured privacy education significantly raises awareness and decision-making.
- **Web Adaptation:** Mandate **privacy-awareness training** for all community members before accessing tools or data. Measure training effectiveness with validated assessment tools. Education must be the first onboarding step, not an afterthought.

## Study 3: NLM Scrubber Referenced Studies

- **PII De-identification of Address, Date, and Alphanumeric Identifiers:** Kayaalp et al., AMIA 2014
- **Patient Privacy in the Era of Big Data:** Kayaalp, Balkan Med J 2018
- **Pattern of Name Tokens in Narrative Clinical Text:** Kayaalp et al., JAMIA 2014

## Bonus: Additional Verified Trials from This Session

| NCT ID | Title | Status | Key Privacy Takeaway |
|--------|-------|--------|----------------------|
| NCT01862133 | Aspiring to Awesome — Patient Preference Privacy Selections in EMR (Indiana University) | COMPLETED | Patients choose who sees what (all, none, sensitive-only, time-limited). Web adaptation: **user-controlled data-sharing preferences** with per-field consent and revocation. |
| NCT04910009 | The Effect of Privacy Education on Nursing Students' Privacy Consciousness (Gazi University) | COMPLETED | 6-session program (theoretical + digital storytelling + ethical case analysis) improved privacy awareness scores at 8, 12, and 24 weeks. Web adaptation: **mandatory recurring privacy training** with measurable outcomes. |
| NCT03795090 | Antimicrobial Surface Coating for Patient Privacy Curtains (HKUST) | COMPLETED | Physical privacy barriers need active maintenance; antimicrobial coating + cross-over blind study design ensures data integrity. Web adaptation: **privacy barriers (screens, partitions) in physical workshops** must be evaluated like network segments — layer physical and digital access controls. |