# Web-Security Community Toolkit — Prototype Reference Architecture

A minimal reference architecture that adapts the 8 verified clinical trials privacy practices for a community web-security product.

```
              ┌──────────────────────────────────────────────────────────────┐
              │  User Device (browser / mobile web)                        │
              │  – React/Vue app runs decision support or curriculum UI      │
              │  – PII stripped at the edge (behaviour split)                │
              └────────┬──────────────────────────────────────────┬─────────┘
                       │                                          │
                   HTTPS│               HTTPS + Bearer token       │
                       │   (session only, short-lived JWT)        │
              ─────────┼──────────────────────────────────────────┼─────────
              │   ┌─────│─────────────────────────────────────────────│───────┐
              │   │AUTH ││ API Gateway                               ││STATIC│
              │   │(MFA)││ – Auth0 / OAuth2 (PKCE) with MFA        ││S3/ │
              │   │     ││ – Per-tenant rate limits                 ││CF  │
              │   │     ││ – Audit log (WORM) ingested here         ││    │
              │   └─────┘└─────────────┬───────────────────────────┘└──────┘
              │                        │
              │      ┌─────────────────┼──────────────────┐
              │      │                 │                  │
              │      ▼                 ▼                  ▼
              │ ┌──────────────┐ ┌──────────────────┐ ┌─────────────────────┐
              │ │ User POD     │ │ Analytics Switch │ │ Workspace Service   │
              │ │ (Self-Sov)   │ │ (pseudonymised   │ │ (workshop sessions,
              │ │ * PII only   │ │  session-ID ⨯    │ │  resource booking) │
              │ │   there, no  │ │  pseudo-ID)      │ │                     │
              │ │   raw token  │ │ ⨯ Vital/Event    │ │ Data Use Agreement  │
              │ │ maps to live │ │   → S3-lake      │ │ metadata for each   │
              │ │ identity ↔ any││   aggregated ── ┘│ │ partner             │
              │ │ partner      │ │   numbers only   │ │                     │
              │ └──────────────┘ │ (C-K→ Kafka→DuckDB) │ ┌───────────────────┘
              │                  └──────────────────┘ ││
              │                                         │││
              │       ┌─────────────────────────────────┘││
              │       ▼                                   ▼│
              │ ┌──────────────────────────────────────────┐│
              │ │ DMC Review Board (Data Monitoring         ││
              │ │   Committee equivalent – monthly, cross-   ││
              │ │   eng + legal + UX review)                 ││
              │ │   Veto over dataset/partner opens.         ││
              │ └────────────────────────────────────────────┘│
              │
              ▼
  [Compliance Layer]
  – Breach notification pre-drafted, test quarterly
  – Immutable WORM audit logs with per-endpoint metrics
  – Status-page + 24h SLA to regulator for EU/GDPR users
```

## Practice-to-component mapping (by study)

| Practice  #  |  Referred study  | Component |
|---------|----|----------|
| A 18-category PII taxonomy | NCT02795806 (NLM Scrubber) | Workspace Service + User POD (every write-through record gets `pii_category: list<>`) |
| B Dual-method verification | NCT02795806 | Analytics Switch: offline rule-engine sampler + periodically dropped human audit |
| C Anonymize at the edge | NCT05487365, NCT07269964 | User POD hashes/salts PII before transit; analytics Switch never raw identity |
| D Zero personal-device linkage | NCT07269964 | User POD + Live ID held as separate services, cross-link time-boxed |
| E RBAC + internal dashboards | NCT07700199, NCT07269964 | Auth (MFA everywhere) + per-endpoint access log; Owner/Analyst/Viewer roles|
| F Data Use Agreements | NCT07269964, NCT05487365, NCT02795806 | Workspace Service: signed DUA per partner, scoped + expirable token |
| G User-held datastores | NCT06150508 | User POD (sinos, OAuth-scoped, time-expirable grants) |
| H Privacy-as-primary-endpoint | NCT04568317 | Analytics: DSAR MTTFR, Break-glass Correlation in Workspace cross-t |
