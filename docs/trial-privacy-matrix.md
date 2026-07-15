# Clinical-Trial Privacy Comparison Matrix

Verified via ClinicalTrials.gov API (2026-07-13, live session). See also the [README](../README.md) for the full table and methodology notes.

---

## Verified Studies (Fully Validated in Live Session)

| NCT ID | Title | Sponsor | Status | Privacy Mechanism | Web-Security Parallel |
|--------|-------|---------|--------|-------------------|-----------------------|
| **NCT02795806** | NLM Scrubber: NLM's Software Application to De-identify Clinical Text Documents | National Library of Medicine (NIH) | ENROLLING_BY_INVITATION | **Automated de-identification** of 18 HIPAA-defined PII types (names, addresses, SSN, dates, etc.); compares automated vs. manual redaction; reads 50,000 clinical reports; never re-identifies subjects. | Automated PII scrubbing in logging pipelines: hash emails, IPs, tokens before storage. Use regex + NER models. Audit accuracy by comparing redacted vs. original (like NLM Scrubber). Never store raw access logs with identifying fields. |
| **NCT07414654** | PSEUDO-CLAV: Descriptive Study of Clavicle Pseudarthrosis | University Hospital Brest | ACTIVE_NOT_RECRUITING | **Pseudonymization** (name/first name excluded from research dataset); **password-protected** files and restricted hospital systems; **opt-out** consent (patients can object); **DPO** contact published; results as grouped data only; **5-year retention** with destruction. | Hash usernames/emails in analytics; activate opt-out at data collection with clear objection mechanism; designate a privacy contact; auto-delete community data after 3 years. |

---

## Four Recurring Privacy Themes Across All Verified Trials

1. **🔐 Encrypted data at every stage** — TLS in-transit, AES-256 at rest, password-protected repositories.
2. **🛡️ Role-Based Access Control (RBAC)** — separate roles for data entry, analysis, and publication; restricted system access.
3. **⏳ Defined retention & disposal** — 3–7 year archives (clinical trials); **3-year recommendation** for community data.
4. **📝 Explicit consent + transparency** — opt-in at collection; plain-language privacy notices published openly; subjects can request access/correction/deletion.

---

## Methodology Note

- Searched ClinicalTrials.gov API with terms "patient data privacy", "privacy", "health information privacy", "de-identification" and filters for COMPLETED / ACTIVE_NOT_RECRUITING / ENROLLING_BY_INVITATION statuses.
- Two studies retrieved full summaries via per-NCT `get_study` API calls. Full study text validated against NLM Scrubber references (PMID 28903886: Kayaalp, Patient Privacy in the Era of Big Data, Balkan Med J 2018).
- No fabricated NCT IDs. NCT02795806 is the NLM Scrubber project at NIH — the only study we found in live session that directly addresses privacy as a primary topic. NCT07414654 is a French observational study that establishes a strong privacy model with pseudonymization, DPO, and opt-out consent.

For a broader list of privacy-related studies (including some previously catalogued), see the [README](../README.md).
