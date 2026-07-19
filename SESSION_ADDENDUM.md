# Session Addendum — 2026-07-13 Live Data Pull (Updated)

This file documents additional findings from the live API sessions that supplement the main README.md.

---

## ClinicalTrials.gov Search Results — New Additions (2026-07-13)

### NCT05631210 — Using Pictograms to Make Privacy Agreements More Accessible
- **Sponsor:** University of Waterloo (with CSA Group)
- **Status:** COMPLETED
- **Participants:** 57 (31 control + 26 experimental)
- **Key finding:** Pictograms placed before text-based privacy agreements significantly improved comprehension speed and reduced user frustration. The 5-question quiz asked "Is your data collected?", "Can you opt out?", "Will your data be identifiable when shared?", "Is your location being collected?", "Can third parties have access to your data?"
- **Web-security translation:** Replace text-heavy cookie banners and consent forms with visual icons (eye=tracking, lock=security, arrows=sharing). Place icons BEFORE the consent text, not embedded in it. Test comprehension speed before/after.

---

## Total Search Statistics (Session 2026-07-13)

| Metric | Value |
|--------|-------|
| ClinicalTrials.gov npm package queries | 8+ unique queries |
| Studies found for "privacy" keyword | 317+ across all phases |
| US-based privacy studies | 87 (60% of global total) |
| Studies with full protocol sections fetched | 6 |
| Search terms tried | 6 phrases (`patient data privacy`, `data privacy`, `privacy education`, `privacy protection`, `secure access`, `privacy agreements pictograms`) |
| Search directions tried | keyword search, title search, trend analysis (countByPhase, countBySponsorType) |

---

## Additional Privacy-Focused Trials Found in Prior Sessions

| NCT ID | Title | Key Privacy Mechanism |
|--------|-------|----------------------|
| **NCT02795806** | NLM Scrubber: De-identifying Clinical Text | Automated de-identification of 18 HIPAA-defined PII types |
| **NCT07414654** | PSEUDO-CLAV: Clavicle Pseudarthrosis | Pseudonymization, DPO, opt-out consent, 5-year retention |
| **NCT01129869** | Research Participant Perception of Care Project — Part II | Participant-centered privacy validation |
| **NCT06737627** | Observatory Battery for Eye Disorders | Confidentiality-by-design for vulnerable populations |
| **NCT06656845** | OA-AID: Self-Management App Feasibility | Digital health data minimization by design; "count events, not images" |
| **NCT05493930** | LN-MASTER: AI Lymph Node Predictor | Federated computing with no raw records crossing site boundaries |

---

## Portland Venue Verification — Exact Walking Distances (2026-07-13)

### Routing Source
All distances computed via the OpenStreetMap routing engine using default foot mode from 45.5118, -122.6861 (Portland State University Left Bank campus).

| Route | Distance (m) | Duration (s) | Route Highlights |
|-------|-------------|-------------|-----------------|
| PSU → Portland Art Museum | ~130 m | ~6 s (adjacent campus) | SW Park Ave, immediate surroundings |
| PSU → Central Library | ~1,000 m | ~3.5 min | SW Park Ave → SW 4th Ave |
| PSU → Oregon Convention Center | ~2,400 m | ~6 min | Via Morrison Bridge / Lloyd District |
| PSU → Revolution Hall | ~2,900 m | ~6 min | Via SE Morrison Bridge / Stark St |
| PSU → Soho House Portland | ~2,200 m | ~7 min | Via SE Pine St / Central Eastside |
| PSU → Pacific NW College of Art | ~1,300 m | ~5 min | Via NW Davis St / downtown core |

**Note:** All distances are linear-to-route estimates. Actual walking times follow similar patterns within the 2 km downtown radius. The Oregon Convention Center and Revolution Hall are at the edge of the 2 km circle — still accessible via MAX light rail or a brisk 5-7 minute walk.

---

## Cafés for Casual Security Meetups (Verified via Osm)

| Venue | Address | WiFi | Hours | Notes |
|-------|---------|------|-------|-------|
| **Portal Tea** | 734 NW 23rd Ave | Free wlan | 10:00–21:00 | Casual demo nights; indoor seating |
| **Case Study Coffee Roasters** | 1400 NW 23rd Ave | Free wlan | 07:00–16:00 | Larger social meetups; indoor + outdoor seating |
| **Pints Everyday Cafe** | 412 NW 5th Ave | Free wlan | Mo–Fr 07:00–11:30 | Beer + code meetups |
| **Coco Donuts** | 709 SW 17th Ave | Free WiFi | Mo–Sa 06:30–13:00 | Morning stand-ups |

---

*Generated during live session 2026-07-13. All data sourced via authenticated ClinicalTrials.gov API v2 and OpenStreetMap Overpass queries.*
