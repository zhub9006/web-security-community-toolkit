# Clinical-Trial Data Privacy Research

## Overview

This document captures our research into how clinical trials handle patient data privacy, with the goal of extracting compliance lessons adaptable to web security.

## Key Trials Analyzed

### 1. NLM Scrubber — Automated De-identification (NCT02795806)

- **Sponsor**: National Library of Medicine (NIH)
- **Focus**: Automated removal of 18 HIPAA-defined PII types from clinical text
- **Method**: Natural language processing to detect and redact names, addresses, dates, numeric identifiers
- **Key metric**: PII de-identification rate vs. rate of erroneously redacted clinical info
- **Web security lesson**: Build automated, auditable data scrubbing pipelines; validate with gold-standard comparisons

### 2. Personalized Parkinson Project (NCT03364894)

- **Sponsor**: Radboud University Medical Center + Verily Life Sciences
- **Focus**: Longitudinal dataset of clinical, molecular, imaging, and wearable sensor data
- **Privacy method**: Polymorphic Encryption and Pseudonymization (PEP)
- **IPD sharing**: Controlled access via Research & Data Sharing Review Committee
- **Web security lesson**: Layer encryption + pseudonymization + access governance for shared/sensitive datasets

### 3. EURACAN Rare Cancer Registry (NCT05483374)

- **Sponsor**: Fondazione IRCCS Istituto Nazionale dei Tumori, Milano
- **Focus**: Federated registry for rare head & neck cancers across European centers
- **Privacy method**: Federated learning via Vantage6 — data stays at source institutions
- **GDPR compliance**: Explicitly compliant with GDPR 2016/679
- **Web security lesson**: Minimize data movement; use federated/edge computation so identifiable data never leaves its origin

### 4. CNS Tumor Surgery ML Prediction (NCT07378683)

- **Sponsor**: Chinese Academy of Medical Sciences
- **Focus**: ML-based risk stratification for surgical site infection
- **Privacy method**: Codes replace names in research; independent DSMB oversight; clinical trial liability insurance
- **IPD sharing**: YES — de-identified data shared via controlled-access repository with DUA
- **Web security lesson**: Replace identifiers with codes; independent oversight boards; formal data use agreements

### 5. LLMs in Medicine — Public Acceptance & Privacy (NCT07304908)

- **Sponsor**: Peking University
- **Focus**: How perception of data leaks affects public acceptance of medical AI
- **Intervention arm**: Reading about a real European hospital data leak from LLM testing
- **Web security lesson**: Data breach incidents directly erode user trust — proactive breach disclosure and remediation plans are essential

## Trend Analysis

### By Phase
- NA (observational/non-drug): 19 studies
- Unknown/unspecified: 20 studies

### By Sponsor Type
- OTHER (academic/institutional): 36
- INDUSTRY: 2
- NETWORK: 1

### Common Privacy Patterns

1. **De-identification / pseudonymization** — Standard across nearly all trials
2. **Informed consent** — Mandatory before any data collection
3. **Restricted IPD sharing** — Most trials either don't share IPD or require controlled access
4. **Ethics committee / IRB oversight** — Universal requirement
5. **Secure data storage** — Encrypted servers, restricted access
6. **Data disposal policies** — Retention for 3+ years then compliant disposal

## Adaptation Framework for Web Security

### Principle 1: Data Minimization
- Clinical trials collect only necessary data → Web apps should minimize data collection and retention
- Implement automated scrubbing/deletion pipelines

### Principle 2: Consent & Transparency
- Trials require informed consent → Web services need granular, transparent consent mechanisms
- Move beyond cookie banners to explain data use clearly

### Principle 3: Access Governance
- Trials use DSMBs and review committees → Web platforms need independent security oversight
- Bug bounty programs and third-party audits serve this role

### Principle 4: Encryption & Pseudonymization
- PEP and federated learning keep data protected at source → Web architectures should encrypt at rest and in transit
- Consider zero-knowledge architectures for sensitive user data

### Principle 5: Data Sharing Controls
- DUAs with explicit boundaries → API access should be scoped, rate-limited, and governed by clear terms
- Prevent unauthorized redistribution and re-identification

### Principle 6: Breach Response & Trust
- Data leak incidents destroy public trust → Proactive breach disclosure and remediation preserves it
- Build incident response plans before you need them