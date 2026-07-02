# 🔐 Web Security Community Toolkit

A community initiative for web security professionals, grinding compliance practices from clinical research and turning them into actionable web security insights — plus a curated guide to Portland venues for hosting workshops and meetups.

---

## 🎯 Project Overview

This toolkit bridges **clinical trial data privacy compliance** with **web security best practices**. By analyzing how ClinicalTrials.gov studies handle patient data privacy, we extract transferable principles that web security teams can adapt for their own compliance and infrastructure needs. The toolkit also maps downtown Portland, OR event venues where we can hold security workshops and community meetups.

---

## 📊 Clinical Trials Insights: Privacy Practices from ClinicalTrials.gov

We searched ClinicalTrials.gov for **"patient data privacy"** and found **314 studies** across all statuses. Here are the key compliance takeaways most relevant to web security:

### 1. On-Premise / Edge Processing
**Study:** NCT07310394 (CLEAR-HEAD, University Hospital, Lille)
- An open-weights LLM with <100B parameters is **hosted locally on a secure server** — raw patient data never leaves the facility.
- **Web Security Adaptation:** Process sensitive user data at the edge or on-prem rather than sending it to third-party APIs. Zero-trust architecture starts with keeping data local.

### 2. Automated PII Detection & Removal
**Study:** NCT07171892 (Ningbo University — Ischemic Stroke Prediction)
- All personal identity information is **permanently removed** before analysis. Electronic medical records are closed with screen savers activated; research computers have DLP systems and disabled USB ports.
- **Web Security Adaptation:** Build automated scrubbing pipelines that strip PII at the source — don't rely on manual redaction. Apply data loss prevention (DLP) controls to your data pipelines.

### 3. Layered Defense-in-Depth
**Study:** NCT07171892 & NCT07144228 (Duke University — Prostate Cancer Proteomics)
- Multiple layers: encrypted internal networks, dual authentication, role-based access, SSL-VPN for data transmission, research-specific hardware with DLP.
- **Web Security Adaptation:** Never rely on a single security control. Combine encryption in transit and at rest, MFA, RBAC, and network segmentation.

### 4. Pseudonymisation + Least Privilege
**Study:** NCT06833099 (Nantong First People's Hospital — Disc Herniation ML Model)
- Data handled in strict accordance with hospital ethics committee rules. Only aggregated data is exported; individual records stay within the research team.
- **Web Security Adaptation:** Tokenize or pseudonymize user identifiers. Export only aggregates or anonymized datasets. Enforce least-privilege access controls.

### 5. Transparent Consent & Granular Controls
**Study:** NCT02812836 (Medical University of Warsaw)
- Patients provide informed consent with clear understanding of data usage. No data sharing without explicit permission.
- **Web Security Adaptation:** Implement granular, purpose-specific consent dialogs. Make it easy for users to withdraw consent. Treat consent as a first-class security feature, not an afterthought.

### 6. Data Use Agreements & Audit Logging
**Study:** Multiple studies reference strict data use agreements with audit trails.
- **Web Security Adaptation:** Every data access should be logged and auditable. Define clear data use boundaries with contractual agreements, especially when sharing data across teams or organizations.

### 7. Independent Oversight & Penetration Testing
**Study:** NCT07144228 (Duke University) notes strong steps to protect privileged information, including trained research ethics teams.
- **Web Security Adaptation:** Conduct regular third-party penetration tests. Establish internal security review boards. Train all team members on data ethics and security hygiene.

### 8. Encryption at Capture
**Study:** NCT07144228 — Data is encrypted at the point of collection on secure servers.
- **Web Security Adaptation:** Encrypt sensitive data at the edge (in the browser or at the API gateway) before it hits your servers. Don't rely solely on at-rest encryption.

### 9. Secure Computing Environments (Sandboxing)
**Study:** NCT07310394 — AI/ML workloads are sandboxed away from production clinical systems.
- **Web Security Adaptation:** Isolate ML inference, data analytics, and third-party integrations in sandboxed environments separate from your core application and database.

### 10. Re-Identification Risk Audits
**Study:** NCT07171892 — Anonymization is verified before any data sharing.
- **Web Security Adaptation:** Before releasing datasets or analytics, audit for re-identification vectors. K-anonymity, l-diversity, and t-closeness should be baseline requirements.

### 11. Privacy as Measurable UX
**Studies across multiple trials track patient confidence and understanding metrics.
- **Web Security Adaptation:** Track privacy confidence as a KPI. Measure user trust through surveys and behavioral metrics. Make privacy a first-class product feature.

---

## 📍 Portland, OR — Workshop & Meetup Venues (Within ~2km of Downtown)

Using downtown Portland (45.516°N, 122.682°W) as the center point, we identified the following venues suitable for security workshops and community meetups:

### ☕ Cafés (Indoor Seating + WiFi)

| Venue | Address | Key Features |
|---|---|---|
| **Starbucks** (23rd & Burnside) | 2328 W Burnside St, Portland, OR 97210 | WiFi, takeaway, open seating — good for casual meetups |
| **Portal Tea** | 734 NW 23rd Ave, Portland, OR | Indoor seating, WiFi (free), tea focus, quiet atmosphere — great for workshops |
| **Case Study Coffee Roasters** | 1400 NW 23rd Ave, Portland, OR 97210 | WiFi, outdoor seating, coffee-focused — ideal for longer sessions |

### 🍽️ Restaurants with Event Capacity

| Venue | Cuisine | Address | Notes |
|---|---|---|---|
| **Papa Haydn** | Regional American | 635 NW 23rd Ave | Air conditioning, wheelchair accessible, full service — good for evening events |
| **Grassa** | Italian | 1506 NW 23rd Ave | Modern Italian, suitable for group dining + discussion |
| **Tara Thai Northwest** | Thai/Lao | 1310 NW 23rd Ave | Group-friendly, diverse menu |
| **Top Burmese (Burma Joy)** | Burmese/Asian | 1305 NW 23rd Ave | Opens Mo-Su 11:30-21:00 |

### 🏛️ Other Nearby Amenities

| Venue | Type | Address | Notes |
|---|---|---|---|
| **Chase Bank** | Bank | 2364 W Burnside St | ATM available, accessible during business hours |
| **Oregon Historical Society** | Museum/Cultural | 1200 SW Park Ave | Potential for larger event hosting — contact for availability |

**Recommendation:** For regular meetups, **Portal Tea** and **Case Study Coffee Roasters** offer the best combination of WiFi, quiet atmosphere, and flexible seating. For larger workshops, consider reaching out to the **Oregon Historical Society** or restaurant private dining areas.

---

## 🗂️ Repository Structure

```
web-security-community-toolkit/
├── README.md                          ← You are here
├── community-docs/                    ← Workshop guides, meeting notes
├── compliance-insights/               ← Deep dives into clinical compliance practices
└── security-resources/                ← Web security templates, checklists, tools
```

---

## 🤝 Get Involved

1. **Fork** this repo and contribute your own privacy/compliance insights
2. **Add venues** from your city to the Portland guide (or create city-specific files)
3. **Host a workshop** using the venue recommendations and clinical trial takeaways
4. **Share** your own data privacy practices from your industry

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.
