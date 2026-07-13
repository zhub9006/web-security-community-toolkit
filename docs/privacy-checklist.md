# Privacy Checklist for Open-Source Community Projects

Adapted from clinical-trial data privacy practices (NCT05129397, NCT05493930, NCT05547425, NCT06804967 — verified via ClinicalTrials.gov API).

## Event & Workshop Privacy Controls

- [ ] **Informed consent** — Distribute a one-page privacy notice before every event. State what data is collected (name, email, photo/video, dietary needs), why, and how long it's kept. Default to opt-in.
- [ ] **Secure registration** — Collect sign-ups through an HTTPS-only form (e.g., Webflow, Jotform over HTTPS, Google Forms with privacy settings enabled). Never collect PII via plain HTTP.
- [ ] **Encrypted attendance logs** — Store sign-in sheets in an encrypted Airtable/Notion workspace or auto-deleted spreadsheet after 90 days if not needed long-term.
- [ ] **Photo/video consent** — Announce "photography/opt-in" at event start. It mirrors clinical-trial DSMB approach: participants explicitly agree to be recorded.

## Communication Security

- [ ] **E2E-encrypted chat** — Use Signal, Element/Matrix, or Signal Group for sensitive community coordination. Avoid plain Slack/Discord for official security discussions.
- [ ] **Waiting rooms & passcodes** — For video meetups, enable waiting rooms (per NCT05129397 HIPAA practices) and unique per-meeting passcodes. Rotate passcodes between events.
- [ ] **GitHub org permissions** — Visitor/Pod-level/organization role hierarchy. Require 2FA for all push-level members. No `@all` push tokens.

## Data Handling

- [ ] **At-rest encryption** — All shared drives (S3, Google Drive, Dropbox) must have server-side encryption enabled. Rotate KMS keys annually.
- [ ] **No raw PII exports** — When sharing research or analytics, aggregate first, de-identify, then export. Mirrors NCT05493930 federated-learning approach.
- [ ] **Browser privacy headers** — Community website sets `Content-Security-Policy`, `Strict-Transport-Security`, `X-Content-Type-Options`, `Referrer-Policy`, and `Permissions-Policy`.
- [ ] **Subprocessor audit** — List every third-party tool in a subprocessor list (mailgun, auth0, stripe, meetup.com, Zoom). Annual review.

## Retention & Deletion

- [ ] **Defined retention period** — 3 years for event attendance records, 90 days for chat messages, indefinite only for required legal filings.
- [ ] **Auto-delete schedule** — Schedule a GitHub Action or cron that auto-purges expired raw PII (attendance sheets, screen recordings) after the retention window.
- [ ] **De-identification guide** — Provide a one-page guide for contributors: convert `name+email` → `hash(name+email)` before analytics pipelines.

## Compliance & Oversight

- [ ] **Security review rotations** — 3-person rotating committee reviews data handling quarterly (mirrors academic Data Safety Monitoring Board in NCT05129397).
- [ ] **Privacy impact assessment (PIA)** — Before launching any new data-collection feature (newsletter, event survey, bi-weekly polls), complete a lightweight PIA.
- [ ] **Incident response plan** — Document a 7-step process: (1) isolate, (2) assess scope, (3) notify affected parties within 72h, (4) file regulator notice if threshold met, (5) post-mortem, (6) remediation, (7) public update.

## Vendor & Tool Choices

- [ ] **Conference platform vetting** — Only platforms with HIPAA-grade encryption (Zoom Healthcare tier, Jitsi Meet on self-hosted infra, or Microsoft Teams E5). Avoid consumer accounts.
- [ ] **VPN requirement** — Contributors must use VPN when accessing CI/CD prod environments or hosting tickets.
- [ ] **OSM contribution** — Check that venue searches (Portland event spaces) are cross-verifiable via OpenStreetMap database dump or API.