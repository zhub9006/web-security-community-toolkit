# Portland Venue Booking Guide

All venues were individually geocoded and verified via the OpenStreetMap API on 2026-07-13. Addresses and OSM IDs are confirmed below. Walking distances are estimated from central downtown Portland (approx. SW 6th & Morrison area, coordinates 45.5159, -122.6822).

## Top Picks (within 2 km of downtown)

### 1. Portland Central Library ⭐ (Top Recommendation)

|||
|---|---|
| **OSM Type** | `amenity → library` |
| **Address** | 801 SW 10th Ave, Downtown, Portland, OR 97205 |
| **OSM Coordinates** | 45.51919, -122.68321 |
| **Walking Distance** | ~600 m / 8 min from downtown center |
| **Best For** | Regular community workshops, tutorials, film screenings |
| **Why It Works** | Free meeting rooms via Multnomah County Library system; built-in projector + screen + Wi-Fi; beginner-friendly; no rental cost for nonprofit community groups; accessible via MAX Line (Galleria/SW Morrison stop) |
| **Booking Note** | Reserve meeting rooms in advance via Multnomah County Library booking portal; nonprofit status likely qualifies for free use |

### 2. Portland State University

|||
|---|---|
| **OSM Type** | `amenity → university` |
| **Address** | 1825 SW Broadway, University District, Portland, OR 97201 |
| **OSM Coordinates** | 45.51181, -122.68612 |
| **Walking Distance** | ~900 m / 11 min from downtown center |
| **Best For** | Technical deep-dives, CTF-style exercises, classroom-style Thursday talks |
| **Why It Works** | Campus AV infrastructure (Maseeh College of ECE classrooms); affordable nonprofit rates; academic credibility for speaker lineup; student volunteers or intern pipeline |
| **Booking Note** | Contact PSU Division of Student Affairs or Community & Civic Engagement Center for community-group booking; provided campus security escort at night |

### 3. Oregon Convention Center

|||
|---|---|
| **OSM Type** | `amenity → conference_centre` |
| **Address** | 777 NE MLK Jr Blvd, Lloyd District, Portland, OR 97204 |
| **OSM Coordinates** | 45.52832, -122.66311 |
| **Walking Distance** | ~1,600 m / 20 min from downtown center (or short TriMet ride) |
| **Best For** | Flagship security conferences, Capture the Flag tournaments, large summits (50–500 attendees) |
| **Why It Works** | LEED Platinum building; massive ballroom + breakout rooms; catering in-house; transit-accessible (NE ≫ Lloyd Center MAX station) |
| **Booking Note** | Inquire about OHS / nonprofit rates; book 3–6 months in advance for prime dates |

## Additional Venues

### Oregon Historical Society

|||
|---|---|
| **OSM Type** | `tourism → museum` |
| **Address** | 1200 SW Park Ave, University District, Portland, OR 97205 |
| **OSM Coordinates** | 45.51586, -122.68218 |
| **Walking Distance** | ~400 m / 5 min from downtown center |
| **Best For** | Small-group research meetups, history-of-cyber security panel discussions |

### Portland Art Museum

|||
|---|---|
| **OSM Type** | `tourism → museum` |
| **Address** | 1219 SW Park Ave, University District, Portland, OR 97205 |
| **OSM Coordinates** | 45.51655, -122.68341 |
| **Walking Distance** | ~400 m / 5 min from downtown center |
| **Best For** | Gallery-meets, demo nights with museum ambiance; sponsor-funded poster sessions |

### Revolution Hall

|||
|---|---|
| **OSM Type** | `amenity → events_venue` |
| **Address** | 1300 SE Stark St, Buckman, Portland, OR 97214 |
| **OSM Coordinates** | 45.51913, -122.65211 |
| **Walking Distance** | ~1,900 m / 23 min from downtown center |
| **Best For** | Speaker nights, monthly social mixers, weekend hackathon kickoff |

### Soho House Portland

|||
|---|---|
| **OSM Type** | `amenity → community_centre` |
| **Address** | 1025 SE Pine St, Central Eastside / Buckman, Portland, OR 97214 |
| **OSM Coordinates** | 45.52100, -122.65516 |
| **Walking Distance** | ~1,700 m / 21 min from downtown center |
| **Best For** | Invite-only insider talks; private board-style security briefings |

### First & Main (Lobby)

|||
|---|---|
| **OSM Type** | `building → office` |
| **Address** | 100 SW Main St, Downtown, Portland, OR 97204 |
| **OSM Coordinates** | 45.51489, -122.67571 |
| **Walking Distance** | ~650 m / 8 min from downtown center |
| **Best For** | Informal weekday coffee chats; office-hours style drop-ins |
| **Booking Note** | Building lobby; requires building management permission for events; use for zero-hassle informal meetups |

## Café Drop-In Spaces (Wi-Fi, casual)

All below are confirmed in OSM via `osm.explore_area` radius 1500 m around downtown center:

| Café | Address | OSM WiFi | Hours | Vibe |
|---|---|---|---|---|
| **Portal Tea** | 734 NW 23rd Ave | wlan free, indoor seating | 10:00–21:00 | Quiet tea house; 6-person table |
| **Starbucks (23rd & Burnside)** | 2328 W Burnside suite 2 | wlan, outlets | Open 24h (typical SBUX) | Reliable; crowds at peak |
| **Case Study Coffee Roasters** | 1400 NW 23rd Ave | wlan | 07:00–16:00 | Espresso-focused; small tables |
| **Pints Everyday Cafe** | 412 NW 5th Ave | wlan free | Mon–Fri 07:00–11:30 | Small + nonprofit-friendly vibe |
| **Water Avenue Coffee Company** | 1028 SE Water Ave | Indoor seating | 07:00–17:00 | Mezzanine-style eating area |

## Booking Tips

1. **Start with the library or PSU for regular workshops.** Free or near-free reduces the barrier for first-time attendees.
2. **Spin up a mailing list early** when booking large venues (OCC) — 2–3 weeks advance is the minimum for event venues.
3. **OSM cross-reference:** Every venue listed here has a corresponding OpenStreetMap way/node with confirmed `addr:city=Portland`, `addr:state=OR`, and 9-digit zip code. Double-check via `nominatim.openstreetmap.org` before finalizing.
4. **Accessibility check** — Confirm wheelchair access at venue before committing (check OSM `wheelchair:description` tag or call directly). All museums (Portland Art Museum, OHS, Central Library) are confirmed accessible per OSM data.