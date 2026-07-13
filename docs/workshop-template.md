# Workshop Planning Template

Use this template to plan every web-security community workshop. Adapted from clinical-trial informed-consent and data-handling workflows.

## 1. Pre-Event (2–4 weeks out)

- [ ] **Define workshop scope & audience cap** — Match venue size (Central Library cap ~30, PSU rooms ~50–100, OCC ballrooms >200).
- [ ] **Book venue** — Use `docs/portland-venues.md` shelf for distance & booking links.
- [ ] **Create RSVP form** — Collect: name, email, dietary needs, accessibility needs, photo/video consent (opt-in), prior-experience level.
- [ ] **Privacy notice** — Draft one-page privacy statement (what data, why, retention period, how to delete). Publish on event page + link in RSVP confirmation auto-email.
- [ ] **Speaker agreements** — Collect speaker bio, headshot consent, and content-release or NDAs if needed.

## 2. During Event (Day-Of Runbook)

- [ ] **Check-in desk** — Sign-in sheet with name + email (scan or knox-box: use password-protected spreadsheet).
- [ ] **Privacy announcement** — State at T-0: "This event may be photographed / recorded. Opt-in only. Full privacy notice: [link]."
- [ ] **WiFi credentials** — Share via QR code, not verbal broadcast (prevents shoulder-surfing).
- [ ] **Consent tracking** — If recording video or photos, have a visible opt-in list (green sticker / name-tag check).
- [ ] **Emergency contact** — Post event organizer phone on back of name-tags.

## 3. Post-Event (0–7 days)

- [ ] **Delete raw sign-in** — Transcribe to aggregate count; delete raw CSV after 90 days. (Mirrors clinical-trial auto-deletion window.)
- [ ] **Send thank-you + privacy summary** → email with link to photo release form & data-deletion request.
- [ ] **Publish deck/slides** — Redact attendee-specific photos before posting public GitHub repo.
- [ ] **Incident check** — Scan for PII leaks in chat logs, shared drive, or photos before public release.
- [ ] **Retrospective** — Complete internal review: attendance count, privacy complaints, near-miss log. File 1-page post-mortem in `docs/retrospectives/YYYY-MM-DD-workshop.md`.

## 4. Consent Form (Template)

```
Web Security Community Workshop — Privacy Consent

Your data will be collected ONLY to:
  (1) process event RSVP & coordination
  (2) run event WiFi authentication (if required)
  (3) publish anonymized attendance stats for grant reports

We will NOT:
  (1) Sell your email or name to third parties
  (2) Store raw data longer than 3 years
  (3) Record video/audio unless you opt-in

Questions? Email privacy@websecurity.community
I consent to the above. ☐  Name: __________  Email: __________  Date: __________
```

## 5. Checklist Metrics (for quarterly review)

| Metric | Target |
|---|---|
| Attendee consent rate | ≥ 95% |
| Post-event data purge within window | 100% |
| Incidents with PII leak | 0 |
| Average post-event satisfaction (Survey) | ≥ 4.5 / 5 |
| Privacy notice link clicks (RSVP page) | ≥ 90% view rate |