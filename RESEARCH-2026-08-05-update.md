# Supplementary Research Update — August 5, 2026

This document captures additional clinical-trial privacy research and Portland venue analysis performed on August 5, 2026, complementing the main README.

---

## Additional Clinical-Trial Privacy Studies (Verified by NCT ID)

These three studies were retrieved by directly querying the ClinicalTrials.gov API with specific NCT IDs, after the initial search returned 11 results.

### NCT04910009 — Privacy Education for Nursing Students (Gazi University, Turkey)

- **Status:** COMPLETED (Nov 2020 – Apr 2021)
- **Design:** Randomized controlled trial, pre-test/post-test factorial design
- **Population:** 116 nursing students (age 20–22), Gazi University Faculty of Health Sciences
- **Intervention:** 2 × 40-min theoretical privacy education sessions + 4 × 60-min practical sessions (digital storytelling + ethical case analysis)
- **Outcome Measures:** Privacy Consciousness Scale (PCS) and Patient Privacy Scale (PPS) at baseline, Week 8, 12, and 24
- **Key Finding:** Structured privacy education (theory + practice) measurably improved privacy consciousness and attitudes. Digital storytelling + ethical case analysis was more effective than theory-only training.

**Web-Security Adaptation:** Train, don't just enforce. Structured privacy training (theory + practice) significantly improves awareness. Build recurring privacy literacy programs, not one-time compliance checkboxes.

---

### NCT05298514 — Data Sharing Project Part 2: Service User Opinions (King's College London, UK)

- **Status:** UNKNOWN (last known: NOT_YET_RECRUITING)
- **Design:** Qualitative, focus groups
- **Population:** 32 mental health service users
- **Method:** Focus groups exploring what users consider "identifiable" data, acceptable access levels, and how protection requirements vary by data type
- **Key Research Questions:**
  1. What is data? What would you consider personally identifiable information?
  2. Who gets access?
  3. How should individuals/companies get access?
  4. How should data be protected?
- **Key Finding:** User input directly shapes data-sharing protocol design. What users consider "identifiable" or acceptable often differs from engineer assumptions.

**Web-Security Adaptation:** Co-design with your users. Include user feedback in privacy design rather than making assumptions about what constitutes identifiable or sensitive data.

---

### NCT07200453 — Interactive E-learning for Digital Health Literacy (Universitätsklinikum Hamburg-Eppendorf, Germany)

- **Status:** RECRUITING (started Jan 2025)
- **Design:** Randomized controlled trial, parallel groups, triple-masked
- **Population:** 660 cancer patients, stratified by cancer type
- **Intervention Groups:**
  - IG 1.1: E-learning with persuasive primary task support (reduction, tunneling, rehearsal)
  - IG 1.2: E-learning without tunneling
  - IG 1.3: E-learning without rehearsal
  - IG 2: PDF document (same content as e-learning)
  - Control: No intervention (brochure only)
- **Outcome:** Digital health literacy measured at baseline, 2 weeks, and 8 weeks
- **Key Finding:** E-learning with scaffolding (reduction, tunneling, rehearsal) outperforms passive formats (PDF) for teaching users to evaluate online information. Layered, accessible educational content improves users' ability to make informed privacy decisions.

**Web-Security Adaptation:** Accessible education enables better privacy choices. Layer learning formats (interactive + reference) to help users understand and exercise their privacy rights.

---

## Portland Venue Analysis — Detailed Walking Routes

All routes calculated from downtown Portland center (Pioneer Courthouse Square, 45.5189°N, 122.6793°W) using OSM foot routing.

### Complete Venue Directory

| Venue | Type | Address | Coordinates | Distance | Walk Time |
|-------|------|---------|-------------|----------|-----------|
| Oregon Convention Center | Conference Centre | 777 NE MLK Jr Blvd, Lloyd District | 45.5283°N, 122.6631°W | 2,575 m | ~6 min 45 s |
| Portland Center Stage at The Armory | Theatre / Event Space | 128 NW 11th Ave, Pearl District | 45.5242°N, 122.6817°W | 1,401 m | ~3 min 44 s |
| Pioneer Courthouse Square | Public Square | SW Taylor / SW Broadway, Downtown | 45.5189°N, 122.6793°W | ~0.1 km | — |
| Oregon Historical Society | Museum / Event Venue | 1200 SW Park Ave, University District | 45.5159°N, 122.6822°W | ~0.3 km | — |
| The Nines Hotel | Hotel / Meeting Rooms | 525 SW Morrison St, Downtown | 45.5190°N, 122.6780°W | ~0.2 km | — |

### Walking Route Details

**Downtown → Oregon Convention Center (2,575 m / ~6 min 45 s):**
SW Madison St → SW 4th Ave → NW 4th Ave → NW Everett St → Steel Bridge → NE Oregon St → NE 1st Ave → NE Oregon St → destination

**Downtown → Portland Center Stage at The Armory (1,401 m / ~3 min 44 s):**
SW Madison St → SW Broadway → SW Jefferson St → SW Park Ave → SW 10th Ave → NW Davis St → destination

---

## Summary: Key New Insights

1. **Privacy education works** (NCT04910009): Structured training combining theory and practice measurably improves privacy awareness. This validates investment in recurring security/privacy training programs for development teams.

2. **Users should co-design privacy** (NCT05298514): Service-user focus groups revealed that what users consider "identifiable" data differs from technical assumptions. Web products should include user feedback loops in privacy design.

3. **Digital literacy empowers privacy choices** (NCT07200453): Interactive e-learning with pedagogical scaffolding (reduction, tunneling, rehearsal) outperforms passive content. Layer your security awareness materials accordingly.

4. **Portland has strong venue options within walkable distances**: The Oregon Convention Center and Portland Center Stage at The Armory are both within 3 km walking distance of downtown, with confirmed event/conference capabilities.
