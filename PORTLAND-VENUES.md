---

## 🔍 Additional Clinical Trial Findings (Direct Analysis)

The following studies were directly sourced from ClinicalTrials.gov and provide additional privacy/compliance practices relevant to web security:

### NCT07310394 — CLEAR-HEAD: LLM-Generated Lay Summaries for Brain MRI Reports

- **Sponsor:** University Hospital, Lille (France)
- **Status:** COMPLETED (March–April 2026)
- **Key Privacy Practice:** Uses an **open-weights LLM hosted locally on a secure server** to ensure data privacy. Patient medical data is never sent to external APIs. The model generates plain-language summaries entirely on-premise.
- **Why It Matters for Web Security:** Demonstrates that sensitive user data (medical records in this case) can be processed by AI/ML tools without exposing raw data to third parties — a core principle for zero-trust architectures and edge computing in web applications.

### NCT06786247 — ActivaTeen (University of Washington)

- **Sponsor:** University of Washington / NIMH
- **Status:** NOT YET RECRUITING (starting April 2025)
- **Key Privacy Practice:** The ActivaTeen app is built on a **HIPAA-compliant instance** of a popular messaging platform. Patient data stays within the encrypted app environment with moderated peer support and therapist controls.
- **Why It Matters for Web Security:** Shows how HIPAA-compliant infrastructure can serve as a model for secure messaging and data handling in web applications, especially for community platforms handling sensitive user data.

### NCT07171892 — Ischemic Stroke Risk Prediction Model (Ningbo University)

- **Sponsor:** First Affiliated Hospital of Ningbo University
- **Status:** NOT YET RECRUITING
- **Key Privacy Practice:** All personal identity information is **permanently removed** to protect privacy. Data is stored securely on the hospital's protected network with strict access controls. All patient identity information is anonymized and imaging data has personal identifiers removed.
- **Why It Matters for Web Security:** Reinforces the principle of data anonymization at the source — don't just pseudonymize, but strip identifiers before processing or storing.

---

## 📊 ClinicalTrials.gov Search Summary: "Patient Data Privacy"

A search on ClinicalTrials.gov for "patient data privacy" returned **314 studies** spanning multiple statuses:

- **COMPLETED:** 114 studies
- **RECRUITING:** 64 studies
- **NOT_YET_RECRUITING:** 59 studies
- **ACTIVE_NOT_RECRUITING:** 25 studies
- **UNKNOWN:** 32 studies
- **TERMINATED:** 10 studies

Key compliance themes identified across the search results:
1. **On-premise/edge processing** — Keep sensitive data local, never send to external APIs
2. **Automated PII detection & removal** — Build scrubbing pipelines, not just manual redaction
3. **Layered defense-in-depth** — Technical + administrative + physical controls
4. **Pseudonymisation + least-privilege** — Restrict access and use tokenized identifiers
5. **Transparent consent** — Granular, purpose-specific user controls with easy withdrawal
6. **Data Use Agreements** — Explicit usage boundaries with audit logging
7. **Independent oversight** — Third-party audits, DSMBs, and penetration testing
8. **Encryption at capture** — Encrypt sensitive data at the source, not just at rest
9. **Secure computing environments** — Sandbox AI/ML workloads away from production
10. **Configuration management** — Automated config validation to prevent drift-based breaches
11. **Privacy as measurable UX** — Track privacy confidence as a KPI
12. **Decentralized identity** — DID/DIDComm for cross-org data sharing
13. **GDPR controller/processor separation** — Double encryption + clear role delineation
14. **Re-identification risk audit** — Audit datasets for re-ID vectors before sharing
15. **Confidentiality as default** — "No sharing unless approved" default policy

---

## 🗺️ Portland Area Clinical Research Hubs (For Future Partnership)

Hospitals and research institutions in the Portland area that conduct privacy-focused clinical research and may be potential partners:

| Institution | Location | Relevant Focus |
|-------------|----------|----------------|
| **Oregon Health & Science University (OHSU)** | Portland, OR | Major research hospital; HIPAA-compliant data handling |
| **Portland State University** | 1825 SW Broadway | Public health research; community health data studies |
| **VA Portland Health Care System** | Portland, OR | VA-affiliated research; TBI and mental health privacy |

These local institutions often IRB-approved data handling processes that align with the compliance practices documented in this toolkit.
