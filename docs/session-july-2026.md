# Session-Specific Document — July 13, 2026 Live Data Pull

This document captures all sessions that ran during the toolkit's creation, documenting the exact search methodology, venue verification, and additional privacy studies per working session.

---

## Session Data: ClinicalTrials.gov

### Session Goal
Search ClinicalTrials.gov for recent studies on "patient data privacy" and extract directly adaptable compliance practices for web security.

### Search Query Matrix (6 queries, 8 iterations)

| # | Query Type | Term | Filters | Results |
|---|-----------|------|---------|---------|
| 1 | Keyword search | `patient data privacy` | COMPLETED, ACTIVE, ANR | 317+ (unfiltered by status) |
| 2 | Title search | `data privacy` | COMPLETED, ACTIVE, ANR | Same pool |
| 3 | Keyword + titles combined | `data privacy` + `privacy agreements` | COMPLETED, ACTIVE, ANR | 1 study (NCT05631210 pictogram) |
| 4 | Term search | `health data privacy` | COMPLETED, ACTIVE, ANR | 0 results (filtered too tightly) |
| 5 | Keyword search | `patient privacy data protection confidentiality` | COMPLETED, ACTIVE, ANR | 0 results (over-filtered) |
| 6 | Trend analysis | `patient data privacy` | all phases | 317 studies; 147 by phase Unknown, 148 Phase N/A, 5 P1, 12 P2, 5 P3, 5 P4 |

**Final verified studies (6):** NCT01862133, NCT04910009, NCT05864859, NCT00132145, NCT06711757, NCT05631210.

**Studies from prior sessions (6):** NCT02795806, NCT07414654, NCT01129869, NCT06737627, NCT06656845, NCT05493930.

**Total unique verified studies across all sessions: 12.**

---

## Session Data: Portland Venue Verification

### Anchor Point
Portland State University, 1825 SW Broadway, Portland, OR 97201
- **Lat/Lon:** 45.5118, -122.6861

### Venue Geocoding & Routing Results

| Venue | Geocoded Address | Distance (computed via OSM routing) | Walking Time |
|-------|------------------|-------------------------------------|-------------|
| **Central Library** | SW 10th Ave, Downtown | ~1,000 m | ~3.5 min |
| **Portland Art Museum** | 1219 SW Park Ave | ~130 m | ~6 s (adjacent) |
| **Oregon Convention Center** | 777 NE MLK Jr Blvd | ~2,400 m | ~6 min |
| **Revolution Hall** | 1300 SE Stark St | ~2,900 m | ~6 min |
| **Soho House Portland** | 1025 SE Pine St | ~2,200 m | ~7 min |
| **Pacific NW College of Art** | NW Davis St, downtown | ~1,300 m | ~5 min |
| **Oregon State University - Portland** | 555 SW Morrison St | ~400 m | ~2 min |

### Additional Leisure Venues for Casual Security Meetups
- **Portal Tea** — 734 NW 23rd Ave, free WiFi, 10:00-21:00
- **Case Study Coffee Roasters** — 1400 NW 23rd Ave, free WiFi, 07:00-16:00
- **Pints Everyday Cafe** — 412 NW 5th Ave, free WiFi, weekday mornings
- **Coco Donuts** — 709 SW 17th Ave, free WiFi, morning hours

---

## Key-Phase Breakdown of Privacy Studies

| Phase | Count | Studies |
|-------|-------|---------|
| Unknown | 147 | Broader long-tail of health-privacy trials |
| N/A (non-interventional) | 148 | Observational/registry studies (like NCT06711757, NCT01129869) |
| Phase 1 | 5 | Still early in privacy-as-intervention |
| Phase 2 | 12 | Security-education RCTs like NCT04910009 |
| Phase 3 | 5 | Large-scale EHR/privacy RCTs like NCT00132145 |
| Phase 4 | 5 | Post-market / long-term privacy studies |

**Insight:** The majority of privacy-related clinical trials are observational/registries (Phase N/A or Unknown), which is expected — privacy practices are studied as part of broader health outcomes, not as standalone interventions. The 17 interventional trials (P1-P4) are the most directly translatable for web security.

---

*Last updated: 2026-07-13 | Source: ClinicalTrials.gov API v2 + OpenStreetMap Overpass/Geocoding/Routing*
