# Privacy Self-Assessment Checklist

Use this checklist before publishing any community data. Based on clinical trial privacy practices adapted for web security.

## Data Collection & Consent
- [ ] Informed consent collected from all participants (signed/electronic)
- [ ] Consent specifies: what data, who sees it, for how long, opt-out mechanism
- [ ] No bundled consent — each purpose stated separately
- [ ] Minors' consent has parental/guardian co-signature
- [ ] Participants can withdraw consent at any time

## Encryption & Transmission
- [ ] All data in transit encrypted (TLS 1.3 minimum)
- [ ] All data at rest encrypted (AES-256)
- [ ] No raw PII sent in cleartext in any system
- [ ] Certificate pinning enabled for mobile/web apps
- [ ] API endpoints use authentication tokens, not basic auth

## Access Control
- [ ] Role-based access: separate roles for entry, analysis, publication
- [ ] MFA required for all sensitive operations
- [ ] Access logged with audit trail (who accessed what, when)
- [ ] Principle of least privilege enforced for all accounts
- [ ] Access reviews conducted quarterly

## Data Minimization & De-identification
- [ ] PII stripped from reports/dashboards before publishing
- [ ] Automated scrubbing of usernames, emails, locations, device fingerprints
- [ ] Aggregated/grouped statistics only for public release
- [ ] Identity data stored separately from operational data
- [ ] Pseudonymous/hashed user IDs used in analysis

## Oversight & Retention
- [ ] Data Protection Officer (DPO) or privacy contact published
- [ ] Formal privacy protocols documented
- [ ] Data Monitoring Committee or equivalent oversight in place
- [ ] Retention policy set (3 years recommended for community data)
- [ ] Auto-delete after retention window
- [ ] Periodic privacy audits scheduled

## Venue/Event Security
- [ ] Workshop venue has visual privacy (no bystander screens)
- [ ] Whiteboards/notes collected and securely disposed after events
- [ ] Room access restricted (check-in desk or badge system)
- [ ] Physical side-channel leaks addressed (screen filters, no public whiteboards)
- [ ] Antimicrobial cleaning for shared devices

## Consent UI (Adapted from NCT01862133 Granular Consent Pattern)
- [ ] Category-level opt-in (e.g., "share posts but not profile info")
- [ ] Time-limited consent options
- [ ] No pre-ticked consent boxes
- [ ] Consent changeable via account settings
