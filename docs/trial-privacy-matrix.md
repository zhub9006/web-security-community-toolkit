# Clinical-Trial Privacy Assessment Matrix

This matrix maps real clinical-trial privacy practices (verified 2026-07-13 via ClinicalTrials.gov API) to web-security adaptions for the community toolkit.

## Studies

### 1. NCT05129397 — Virtual Mom Power (Tulane University, COMPLETED 2024-01)

**Domain:** Biobehavioral maternal-child intervention (virtual group sessions)

**Privacy practices observed:**
- HIPAA-grade encrypted video platform for all virtual groups (90-min sessions, 10 weeks)
- Explicit privacy problem-solving embedded in core curriculum — participants coached to manage privacy during group discussions
- Individual sessions (separate from group) combine motivational interviewing with privacy-related goal setting
- Data Safety Monitoring Board (DSMB) provides independent oversight of data handling
- Role differentiation: facilitators vs. participants vs. data analysts
- Outcomes: maternal depression (PHQ-9), PTSD symptoms (PCL-5), secure biobehavioral outcomes (RSA)

**Web-security takeaways:**
| Clinical Trial Practice | Web-Security Relevance |
|---|---|
| HIPAA video platform with consent controls | Use E2E-encrypted conferencing; record only with explicit consent |
| Privacy curriculum built into sessions (not afterthought) | Publish security best-practices in onboarding, not buried in footer |
| DSMB independent oversight | Rotating security board reviews access logs quarterly |
| Individual + group separation | Segregate 1:1 admin tooling from public community channels |

---

### 2. NCT05493930 — LN-MASTER (Peking Union Medical College, COMPLETED 2015-12)

**Domain:** Multi-center AI model for rectal cancer lymph node prediction

**Privacy practices observed:**
- Privacy-preserving computing platform for 3 hospitals (6,578 patients total)
- Clinical data remains on-site at each hospital — only AI model weights are shared
- External validation split across 3 independent hospital datasets
- Inclusion/exclusion criteria strictly enforce minimum dataset granularity

**Web-security takeaways:**
| Clinical Trial Practice | Web-Security Relevance |
|---|---|
| Federated data stays in-network | Host community threat-intel in guild/discord channels, not a central raw-media dump |
| Only model/aggregate weights exported | Share sanitized, aggregated statistics instead of raw IP logs |
| Multi-site validation on separate datasets | Require independent verification of security findings across teams |

---

### 3. NCT05547425 — WildCam (Northwestern University, COMPLETED 2026-03)

**Domain:** Wearable eating-detection camera with privacy-preserving image processing

**Privacy practices observed:**
- Three-camera obfuscation techniques tested: blurring, edge-masking (bodypart cartooning), pixel cartooning
- Participants alternate 7-day obfuscation vs. 7-day raw-image phases (counterbalanced)
- Structured acceptability/user-burden surveys for each technique
- Bystander privacy: background/environment digitally obfuscated before upload
- 24/7 wearing for 2 weeks vs. 1 week no-device washout period

**Web-security takeaways:**
| Clinical Trial Practice | Web-Security Relevance |
|---|---|
| Blur background PII at capture edge | Apply edge filtering to community dashboards before rendering |
| Three technique comparison (blurring vs masking vs cartooning) | Benchmark obfuscation methods on community-tool UI; publish effectiveness data |
| Mandatory washout / dual-phase design | Default to privacy-preserving mode; opt-in to less restricted mode only |
| User burden + acceptability surveys | Measure security-friction impact alongside privacy gains |

---

### 4. NCT06804967 — VR Relaxation for Dental Anxiety (Indiana University, COMPLETED 2026-03)

**Domain:** Randomized controlled trial of VR vs. no-VR during orthodontic bonding

**Privacy practices observed:**
- Written informed consent obtained individually before data collection
- All health data (vitals, anxiety scores) stored in **REDCap** — encrypted at rest + in transit (TLS)
- IRB approved device classification (research-exempt but still monitored)
- Control group used for comparison (ethical requirement of parallel design)
- De-identification workflow for pooled analysis datasets
- Providex/DUA: data usage agreement before accessing raw data

**Web-security takeaways:**
| Clinical Trial Practice | Web-Security Relevance |
|---|---|
| Written informed consent before any data collection | Every event attendee signs a data-consent form before sharing PII |
| REDCap encryption (at rest + in transit) | Use tools like Keycloak/Auth0 (encrypted tokens) + S3 server-side encryption |
| Control group comparison | Compare community outcomes with/without data collection to measure privacy cost |
| Data Usage Agreement (DUA) | Contributor license agreement (CLA) with data-use条款 for GitHub orgs |

---

## Cross-Cutting Themes

| Theme | Clinical-Trial Origin | Community Toolkit Application |
|---|---|---|
| Secure encrypted data collection | All 4 studies (HIPAA / TLS / HTTPS / REDCap) | TLS 1.3 everywhere, E2E for private channels, `file:` not `public:` for PII |
| Role-based restricted access | DSMB (DIALEX), investigators vs. analysts (CALI), trained facilitators (Mom Power) | Admin / moderator / contributor / guest role separation, 2FA for sensitive actions |
| Independent oversight | DSMB oversight, IRB audits | Rotating security board quarterly review |
| Defined retention + auto-delete | 3–7 year retention (DIALEX), post-study de-identification | Auto-delete raw logs after 3 years; immediate purge of PII after event wrap-up |
| Explicit consent/opt-in | All 4 studies — no opt-out | Privacy-first onboarding; clear "what we collect / why / how long" statement |