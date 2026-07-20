# Workshop Planning Guide

Template and best practices for planning and running web security workshops, privacy-focused meetups, and community events — inspired by clinical trial data governance practices.

---

## Workshop Planning Template

### 1. Define the Workshop Objective
- **Topic:** e.g., "Privacy-by-Design for Web Applications", "Implementing Pseudonymization", "Consent UX Best Practices"
- **Duration:** 2 hours (short), Half-day (full), Full day (intensive)
- **Audience:** Developers, security engineers, product managers, or general public
- **Format:** Hands-on lab, presentation + discussion, or panel

### 2. Venue & Logistics
- **Venue:** See `PORTLAND_VENUES.md` for recommended spaces near downtown Portland
- **Date & Time:** Confirm with venue availability; aim for consistent monthly meetups (e.g., 2nd Saturday)
- **Capacity:** Match venue size to expected attendance
- **Equipment:** Projector, Wi-Fi, power strips, whiteboards, name tags
- **Food/Drink:** Potluck, sponsored catering, or nearby restaurant recommendations

### 3. Pre-Workshop Preparation
- [ ] Send registration form with consent checkbox (inspired by clinical trial informed consent)
- [ ] Prepare pre-workshop knowledge survey (baseline measurement)
- [ ] Create workshop materials (slides, hands-on exercises, datasets for sandboxed practice)
- [ ] Set up anonymized/usernames for any exercises requiring data
- [ ] Prepare a privacy notice: what data you collect, how it's used, how it's stored

### 4. Workshop Structure

#### Opening (15 min)
- Welcome & introductions
- Icebreaker: "What's your biggest privacy concern?"
- Overview of workshop goals and agenda

#### Core Session (60–90 min)
- **Presentation** (20 min): Key privacy concepts with real-world examples from clinical trials
- **Hands-on Exercise** (40–60 min): Practical application (e.g., pseudonymize a dataset, configure RBAC, build a consent flow)
- **Group Discussion** (15–20 min): Share approaches, debug problems, discuss trade-offs

#### Closing (15 min)
- Debrief & key takeaways
- Post-workshop knowledge survey
- Resource list & next steps
- Announcements for next meetup

### 5. Post-Workshop Follow-Up
- [ ] Send thank-you emails with slides and resources
- [ ] Publish anonymized workshop feedback (like clinical trial results)
- [ ] Track attendance trends over time
- [ ] Schedule next workshop (aim for monthly cadence)

---

## Privacy-First Workshop Policies

Borrowed directly from clinical trial practices:

| Policy | Clinical-Trial Origin | Workshop Application |
|--------|----------------------|---------------------|
| **Informed consent** | NCT07564544 — Ethics committee approval; informed consent after explaining objectives | Ask participants to consent before recording; explain what data (if any) is collected |
| **Pseudonymized participation** | NCT04568317 — Privacy-protected data collection; code names used | Use participant codes instead of real names for any exercises involving data |
| **Confidentiality by design** | NCT05170321 — Principle of confidentiality | Don't capture or store participant data unless necessary; delete after the event |
| **Right to withdraw** | NCT07125625 — Families can withdraw without affecting care | Let participants skip any exercise or leave at any time without explanation |
| **Data minimization** | NCT07344116 — Only collect data essential to the study | Only collect what's needed for the workshop (name, email for follow-up — no more) |

---

## Example Workshop Curriculum

### Workshop 1: "Privacy-by-Design Sprint"
**Inspired by:** NCT07564544 (Ethics committee approval; informed consent; privacy built into design)
- Build a simple web form with consent controls
- Pseudonymize user input before storage
- Audit what data leaves the browser

### Workshop 2: "Breach Simulation Lab"
**Inspired by:** NCT05864859 (Breach response; real-time simulations)
- Simulate a data breach scenario
- Response playbook: identify, contain, notify, remediate
- Lessons learned discussion

### Workshop 3: "Consent UX Workshop"
**Inspired by:** NCT04568317 (Privacy-protective consent mechanisms)
- Design and test consent interfaces
- A/B test different consent wording
- Measure user trust and comprehension

### Workshop 4: "Data Retention Audit"
**Inspired by:** NCT07360366 (Restricted access; data minimization)
- Audit your project's data retention
- Identify what should be deleted
- Build automated deletion workflows

### Workshop 5: "Privacy 101"
**Inspired by:** NCT07709091 (Education-first approach; pre/post knowledge measurement)
- Intro to privacy concepts: pseudonymization, encryption, access control
- Why clinical trial privacy practices apply to web security
- Hands-on: implement basic protections in a sample app

---

## Sponsorship & Partnerships

Potential partners for Portland workshops:
- **Portland State University** — Student Event Center, AV, academic support
- **Portland Art Museum** — Elegant venue for sponsor-branded events
- **Hilton Portland / Marriott** — On-site catering, meeting rooms, accommodation for out-of-town participants
- **Revolution Hall** — High-capacity theatre for conferences
- **Multnomah County Library** — Free rooms for community workshops

---

## Contributing

Help improve this guide:
- Add new workshop templates
- Share feedback from past workshops
- Suggest guest speakers or presenters
- Contribute Portland venue updates

---

*Last updated: July 2026*
