# Clinical-Trial Privacy Comparison Matrix

Verified via ClinicalTrials.gov API (2026-07-13). See also the [README](../README.md) for the full table.

| NCT ID | Title | Status | Study Size | Privacy Mechanism | Web-Security Parallel |
|--------|-------|--------|------------|-------------------|-----------------------|
| **NCT05493930** | LN-MASTER (Lymph Node Metastasis Predictor) — Peking Union Medical College | COMPLETED | 6,578 patients across 3 hospitals | **Privacy-preserving computing platform**: raw clinical data stays at each hospital; only learned model weights exchanged | Federated threat-intel feeds; secure multi-party computation for community metrics |
| **NCT02744846** | PCORnet ABX (Antibiotics & Childhood Growth) — Harvard Pilgrim Health Care | COMPLETED | ~681,739 children across 42 healthcare systems | **"Questions to the data" distributed model**: raw records never centralised; only statistical queries sent centrally | Distributed threat intelligence; query sources without centralising logs |
| **NCT07457489** | VICTORY (Integrated Community TMS for Opioid Recovery) — Vanderbilt University Medical Center | RECRUITING | ~15–30 participants per cohort | **Number-coded subjects + de-identified server storage**: numeric codes label all data; only PI and approved staff have access; video-calls in private locations; locked cabinets for consent docs | Role-restricted access; numeric/hashed user IDs for community dashboards; private breakout rooms for sensitive discussions |
| **NCT07593560** | ScoliRadar-AI (mmWave Radar for Scoliosis Detection) — Gebze Technical University | RECRUITING | Repository-based pilot | **Non-identifiable gait signatures via mmWave**: no images captured; data de-identified on collection per Turkish KVKK; biological signals are non-reversible | Edge-level obfuscation; process sensor data locally; never transmit raw biometric streams |
| **NCT03382951** | FLASH (Family Level Assessment of Screen use in the Home) — Baylor College of Medicine | COMPLETED | Home-study families | **On-device signal processing instead of identifiable images**: no photos stored, no faces captured; only timing/duration metadata exported | Local CV processing in community tools; aggregate metrics not screenshots; immediate frame discard after feature extraction |

### Four Recurring Privacy Themes

1. **🔐 Encrypted data at every stage** — TLS in-transit, AES-256 at rest, password-protected repositories
2. **🏛️ Role-Based Access Control (RBAC)** — contributor / moderator / admin separation; MFA for sensitive ops
3. **⏳ Defined retention & disposal** — 3–7 year archives (clinical trials); 3-year recommendation for community data
4. **📝 Explicit consent + transparency** — opt-in at collection; plain-language privacy notices published openly
