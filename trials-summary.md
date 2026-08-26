# Clinical Trial Privacy Findings — Cross-Trial Synthesis

This file holds a compact digest of the 8 key trials retrieved from ClinicalTrials.gov on 2026-08-26. It's designed to be linked from the `README.md` and consumed by curriculum designers.

```
Study ID │ Status        │ Sponsor / Origin               │ Participants │ Privacy Feature
─────────┼───────────────┼────────────────────────────────┼──────────────┼──────────────────────────────────────────────────────────
NCT07709091 │ COMPLETED    │ Istanbul Arel University       │ 110          │ RCT of digital data-security awareness training curriculum
NCT07219862 │ Not yet rec. │ Keck School of Medicine, USC  │ 250          │ smART decision-support tool runs locally, stores NO patient data
NCT07700199 │ Not yet rec. │ University of Utah / Huntsman │ 50           │ HIPAA-compliant LLM pipeline; UCD built into prompt & governance
NCT07269964 │ Recruiting   │ Technical Univ. of Munich     │ 30           │ Zero personal-data device linkage; anonymized session telemetry only
NCT05487365 │ Unknown      │ Comunicare Solutions (Belgium)│ 330          │ Anonymized-at-source telemetry; GDPR-by-design; multi-center DUA
NCT04568317 │ COMPLETED    │ Silver Cloud Health           │ (feasibility)│ Privacy metrics captured as primary endpoints, alongside CBT outcomes
NCT02795806 │ Enrolling    │ NLM / NIH                     │ 50,000       │ 18-category HIPAA PII taxonomy; auto vs. expert dual-method verification
NCT06150508 │ Not yet rec. │ Seoul National Univ. Hospital │ 1,000        │ User-held Pod datastores; revocable OAuth-style grants; DMC oversight
```

## Reading order for curriculum designers

1. Start with NCT02795806 (NLM Scrubber) — makes the core PII-taxonomy and dual-method verification practices concrete.
2. Move to NCT07709091 — gives a direct "how to teach privacy awareness" framework you can re-use for a community course.
3. Then pair NCT07269964 + NCT05487365 — give you the anonymize-at-edge architecture lessons.
4. Add NCT07219862 as the "edge-compute" case study and NCT07700199 as the LLM-governance case.
5. NCT06150508 shows the user-held-POD / decentralized-identity pattern.
6. NCT04568317 shows how to measure privacy-as-a-primary-endpoint.

For full extracted protocol text, see the `README.md` file in this repository.
