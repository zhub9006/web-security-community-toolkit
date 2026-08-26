# NLM Scrubber — Supplementary Privacy Study

> **NCT02795806** · *NLM Scrubber: NLM's Software Application to De-identify Clinical Text Documents*
> **Sponsor:** National Library of Medicine (NLM) / NIH Clinical Center (CC)
> **Collaborators:** National Cancer Institute (NCI), NIH Clinical Center
> **PI:** Mehmet M. Kayaalp, Ph.D. — National Library of Medicine
> **Status:** ENROLLING BY INVITATION (started 2016-05-25; estimated completion 2027-01-31)
> **Study type:** OBSERVATIONAL — Retrospective · **Estimated enrollment:** 50,000 records
> **Condition:** Personally Identifiable Information (PII)
> **Location:** National Library of Medicine, Bethesda, MD

*Retrieved from ClinicalTrials.gov live API on August 5, 2026.*

---

## Why This Study Matters for Web Security

This is one of the very few clinical trials whose **primary goal is building privacy-preserving software**. The NLM Scrubber is a production-grade de-identification tool used across the U.S. federal government and academic medical centers. Its design principles directly mirror what web-security practitioners need.

---

## Study Design at a Glance

| Step | What happens | Web-security analogue |
|------|--------------|-----------------------|
| **1. Data collection** | Research collects a random sample of clinical narrative reports from many doctors and specialties | Automated security logging: collect samples of user data flowing through your systems |
| **2. Manual redaction (gold standard)** | Expert human annotators manually strip all PII from each report | Manual security audits and penetration tests against automated tools |
| **3. Automated redaction** | NLM Scrubber automatically removes PII from the same reports | Automated DLP (Data Loss Prevention), regex-based PII stripping, tokenization |
| **4. Comparison & calibration** | Researchers compare manual vs. automated results, identify failures, iterate | Purple-team exercises: compare manual vs. automated detections, tune rules |
| **5. Continuous improvement** | Loop repeats until the de-identification is as close to 100% as practically possible | Continuous compliance monitoring, regression testing, automated policy evaluation |

---

## Privacy Practices Extracted — Mapped to Web Security

### 1. 🏷️ HIPAA Privacy Rule-Compliant PII Taxonomy (18 Identifiers)

> *"HIPAA Privacy Rule defines 18 types of personally identifying information that need to be de-identified, which include personal names, addresses, significant dates, numeric identifiers (such as social security number)."*

**Web adaptation:** Build an equivalent PII taxonomy for your product. Map out all 18 HIPAA PII categories + additional categories relevant to your domain (browser fingerprints, IP addresses, device identifiers, behavioral IDs, email, phone, geolocation, biometric data). Encode this taxonomy into your automated scanners.

### 2. 🧪 Gold-Standard Annotation + Automated Comparison

The study uses expert human annotators to create a **gold standard** of what correct PII removal looks like. Automated NLM Scrubber results are compared against this gold standard to measure precision, recall, and false-positive/false-negative rates.

**Web adaptation:** Establish a human-reviewed ground-truth set of sensitive-data samples for your product. Run automated scanners against it. Measure:
- **Precision** — Did we flag only real sensitive data?
- **Recall** — Did we catch all of it?
- **False positives** — Did we break working code by over-redacting?

### 3. 🔒 Access Control via Formal Agreements

> *"We receive patient data, protected health information (PHI), from our collaborating data sources with the promise that we would protect PHI to the full extent and not share it with third parties."*

**Web adaptation:** Every external data integration should be governed by a **Data Use Agreement (DUA)** that explicitly states: no re-identification, no third-party sharing, limited purpose, data destruction at end of use. Adopt NIST SP 800-53 AC-3 (Access Enforcement) and AC-4 (Information Flow Enforcement) controls.

### 4. 🪣 Data Minimization by Design

NLM Scrubber strips identifiers *before* the data enters any secondary analysis pipeline. The source and destination systems are never exposed to others' PHI.

**Web adaptation:** Treat privacy as a pipeline concern:
- **HALT** Personally Identifiable Data at ingestion — replace with opaque tokens.
- Keep the token↔PII mapping in a separate, access-scoped vault.
- Raw PII should *never* flow through analytics databases, logging systems, or CDPs in cleartext.

### 5. 📋 Retrospective Observational Model

Because the study uses historical data, IRB and HIPAA Privacy Rule Section 164.512(i) allow secondary use **only** after de-identification to a "safe harbor" standard (all 18 identifiers removed, no re-identification risk remaining).

**Web adaptation:** Before any secondary analytics, tracking, or ML pipeline:
- Verify whether your data qualifies as "de-identified" under your jurisdiction's safe-harbor standard.
- Document a **Data Protection Impact Assessment (DPIA)** or equivalent privacy-risk review.
- Confirm internal control baselines before forwarding data to any downstream system.

### 6. 🔁 Closed-Loop Quality Assurance

The entire methodology is a closed loop: collect → redact → compare → correct → repeat. The NLM Scrubber is *not* considered finished; it is continuously refined.

**Web adaptation:** Treat your privacy controls as **continuously-operated infrastructure**, not one-off audits:
- Schedule regular token-type regression tests.
- Automate sensitive-data scanners in CI / pre-commit hooks.
- Census / count how many PII categories leak into log lines, error reports, 3rd-party beacons.

---

## Practical Implementation Checklist

Use this checklist when building a "Privacy Scrubber" layer for your web product:

- [ ] **PII taxonomy defined** — enumerate all PII categories your product processes (≥ the 18 HIPAA categories)
- [ ] **Gold-standard test set created** — 1,000+ labeled samples covering all PII categories
- [ ] **Automated PII scanner** — a regex + ML scanner that matches or beats your gold standard on a defined F1 threshold
- [ ] **False-positive review process** — humans audit scanner over-redactions weekly
- [ ] **De-identification at ingress** — PII stripped before stored in logs, databases, analytics
- [ ] **Opaque token IDs** issued — raw PII stored in a separate, access-scoped vault only
- [ ] **Data Use Agreements** in place for every downstream data recipient
- [ ] **DPIA / Privacy Risk Assessment** completed before new analytics pipelines are approved
- [ ] **Audit log** — every access to the mapping vault is logged with actor, timestamp, justification
- [ ] **Re-identification risk test** — quarterly simulation where engineers try to re-identify "de-identified" datasets; if any can, tighten the rules
- [ ] **Continuous regression** — PII scanner results tracked as an automated quality gate in CI; fails build on degradation

---

## Relevant References From the Study Record

1. **Kayaalp M.** *Patient Privacy in the Era of Big Data.* Balkan Med J. 2018 Jan 20;35(1):8-17. doi:[10.4274/balkanmedj.2017.0966](https://doi.org/10.4274/balkanmedj.2017.0966)
2. **Kayaalp M, Browne AC, Dodd ZA, Sagan P, McDonald CJ.** *De-identification of Address, Date, and Alphanumeric Identifiers in Narrative Clinical Reports.* AMIA Annu Symp Proc. 2014 Nov 14;2014:767-76.
3. **Kayaalp M, Browne AC, Callaghan FM, Dodd ZA, Divita G, Ozturk S, McDonald CJ.** *The pattern of name tokens in narrative clinical text and a comparison of five systems for redacting them.* J Am Med Inform Assoc. 2014 May-Jun;21(3):423-31.

---

## See Also

- [Main README](../blob/main/README.md) — All verified trials and privacy takeaways
- [PORTLAND_VENUES.md](../blob/main/PORTLAND_VENUES.md) — Venue options for security workshops & meetups in Portland, OR
- ClinicalTrials.gov study page — [NCT02795806](https://clinicaltrials.gov/study/NCT02795806)
