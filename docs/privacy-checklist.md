# Privacy Checklist for Community Projects

Derived from clinical-trial data-privacy practices (see [Clinical-Trial Privacy Comparison Matrix](./trial-privacy-matrix.md)).

## 1. Data Collection
- [ ] **Encrypt in-transit**: TLS 1.3 for all outgoing connections; no cleartext PII.
- [ ] **Encrypt at rest**: AES-256 for any stored sensitive data.
- [ ] **De-identify at the edge**: Process sensitive telemetry locally; export only sanitised metadata.
- [ ] **Blur / obfuscate PII**: Never transmit raw screenshots, camera feeds, or session recordings without consent layers.

## 2. Access Control
- [ ] **Role-based access**: Separate contributor / moderator / admin permissions.
- [ ] **Multi-factor authentication (MFA)**: Required for sensitive operations (exporting rosters, accessing keys).
- [ ] **Principle of least privilege**: Each role gets only the data it needs.
- [ ] **Access logging**: Every data read/write is logged with user ID + timestamp.

## 3. Data Retention & Disposal
- [ ] **Define retention window**: Community data → auto-delete after 3 years (clinical trials use 3–7 years).
- [ ] **Controlled disposal**: Secure deletion (not just file removal); document disposal in audit trail.
- [ ] **Separate data from identities**: Store identifiers in a different location from operational data; link via token.

## 4. Oversight & Transparency
- [ ] **Independent review**: Rotating security board reviews practices quarterly.
- [ ] **Explicit consent**: Opt-in for every new data stream; never opt-out.
- [ ] **Privacy notice**: Plain-language notice at point of collection (see [Consent Form Template](./consent-template.md)).
- [ ] **Publish audit results**: Share anonymised audit findings with the community.

## 5. Distributed Data
- [ ] **Federated model**: Raw records never leave home institutions; only aggregated queries or model weights are shared.
- [ ] **Secure aggregation**: Use cryptographic techniques for community metrics.
- [ ] **"Questions to the data"**: Statistical queries only — no raw record exports.

---

*This checklist is adapted from HIPAA, IRB standards, and GDPR principles observed in clinical trials on ClinicalTrials.gov.*
