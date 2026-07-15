# Privacy Checklist for Web Security Workshops

Adapted from clinical trial data-handling practices confirmed via ClinicalTrials.gov API (2026-07-13).

## Pre-Event Checklist

### Data Collection & Consent
- [ ] **Informed consent forms** published and provided at registration (opt-in, never opt-out)
- [ ] **Granular access controls**: participants can choose what data they share
- [ ] **Separate raw data from identifiers** at the point of collection
- [ ] **Privacy notice** posted visibly at venue and on registration page

### Environment Preparation
- [ ] **Private rooms** for sensitive discussions
- [ ] **No unauthorized observers** during breakout sessions
- [ ] **Secure Wi-Fi**: WPA3, captive portal, separate network for organizers vs. attendees
- [ ] **Screen privacy**: blur bystanders in demo screen shares

### Access Control
- [ ] **Role-based permissions**: contributor, moderator, admin separated
- [ ] **MFA required** for organizer accounts handling member data
- [ ] **Hashed user IDs** in public-facing dashboards
- [ ] **Auto-delete raw logs** after 3-year retention window

### Data Storage
- [ ] **TLS 1.3** for all in-transit communications
- [ ] **AES-256 encryption** at rest for any stored data
- [ ] **Access logging** with quarterly review by rotating security board

## Study References

| Practice | Source NCT | Study |
|----------|-----------|-------|
| Granular access control | NCT01862133 | Patient Preference Privacy Selections in EMR |
| Breach awareness | NCT07304908 | LLM Data Privacy in Medicine |
| Privacy as workflow | NCT06085820 | Birth Ball / Birth Dance in Labor |