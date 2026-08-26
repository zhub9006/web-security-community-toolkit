# August 2026 — Fresh Clinical-Trial Findings & Portland Venue Notes

This file captures additional research performed on **August 26, 2026** to supplement the main README. It includes newly identified clinical trials on patient-data privacy and notes on venues near downtown Portland, Oregon for community security workshops.

---

## New Clinical-Trial Privacy Cases (August 2026 batch)

These studies were surfaced by re-running ClinicalTrials.gov searches for "patient data privacy," "data privacy health," and "HIPAA health data privacy security." They are **not yet** in the main README's 12-study table but offer valuable additional compliance patterns.

---

### 1. NCT06702293 — HIPAA-Compliant Digital Psychotherapeutic App

| Field | Detail |
|-------|--------|
| **Title** | Use of a Digital Psychotherapeutic App to Reduce Symptom Burden in Dermatology Patients |
| **Sponsor** | National University Hospital, Singapore (+ National Skin Centre, NUS, KK Women's & Children's Hospital) |
| **Status** | Recruiting (Feb 2026 → estimated Jul 2029) |
| **Design** | Randomized, parallel-group, triple-blinded RCT; 690 participants |

**Privacy Practice:**
> "This fully automated and self-administered intervention will be delivered via a **Health Insurance Portability and Accountability Act (HIPAA) compliant mobile app** developed in collaboration with Intellect Inc."
> — The intervention description explicitly cites HIPAA compliance and notes that a detailed discussion of the app's **user interface, data acquisition and curation technology, security and privacy assurance** is available.

**Web-Security Adaptation:**
- When building privacy-facing web apps, explicitly document your security and privacy architecture in the product description (builds user trust and audit trail).
- Choose third-party SDKs and platforms that carry recognized compliance certifications — don't build your own encryption layer.
- Triple-blind trial design (participant + care provider + outcomes assessor all blinded) maps to **role-based access separation** in web systems: the team that builds a feature shouldn't also be the team that audits its privacy controls.

---

### 2. NCT07759193 — Coded Identifiers + Strict Access Control

| Field | Detail |
|-------|--------|
| **Title** | Indirect Calorimetry Profile for Surgically Free Flap Treated Head and Neck Oncologic Patients |
| **Sponsor** | Tel-Aviv Sourasky Medical Center (Ichilov Hospital, Israel) |
| **Status** | Recruiting (started Jan 2025, estimated completion Sep 2026) |
| **Design** | Interventional, single-group; 19 participants |

**Privacy Practice:**
> "Study data will be stored in a **coded form**, and **access will be limited to authorized study personnel**. **Personal identifying information will be kept separate** from the research database."
> — IPD Sharing Statement: **NO** (no individual-level data sharing).

**Web-Security Adaptation:**
- **Tokenize user identifiers at the application layer** — store randomly generated codes, not raw usernames or emails, in analytics and reporting databases.
- **Segregate PII stores** — keep identity data in a separate, more heavily guarded database from operational/analytics data. Cross-reference via codes, not direct links.
- **Zero data sharing by default** — the IPD: NO setting is a strong stance. Default to no third-party data sharing; build explicit opt-in flows if sharing is ever needed.

---

### 3. Bonus: NCT05116020 — Data Privacy as a Non-Participation Barrier

| Field | Detail |
|-------|--------|
| **Title** | Swiss Chiropractic Cohort (Swiss ChiCo) Study: Patient Cohort |
| **Sponsor** | Balgrist University Hospital (+ University of Zurich, University of Southern Denmark, ChiroSuisse) |
| **Status** | Completed (568 participants enrolled) |

**Privacy Insight:**
This study lists **"data privacy concerns"** as one of the measured reasons for invited participant non-participation (alongside "no email address," "unfamiliar with electronic tools," "lack of time," "lack of interest"). Privacy concerns directly reduced the dataset — a quantifiable UX problem.

**Web-Security Adaptation:**
- **Privacy friction has a measurable cost.** If your consent flows or privacy notices feel unclear or intimidating, users won't just skip your terms — they'll bounce your product entirely. Test consent UX for comprehension, not just legal compliance.
- Treat **privacy confidence as a product metric** (like conversion or retention). If it drops, your data-handling communication needs work.