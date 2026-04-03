# AuthC v0.1 — Authority-First Specification for AuthN and AuthZ
Consent Based Digital-ID Protocol April 3, 2026

## Draft IPR + participation
This initial AuthC v0.1 draft is published under **0PN RF-RAND** and governed by the **OPN Lab General Participation Agreement (GPA)** for work aligned to the **ISO/IEC 27560-1 profile**.

## Table of Contents (draft)
1. Document control
    0.1 Title, version, status, date
    0.2 Editors, contributors, review group
    0.3 Normative language (MUST/SHOULD/MAY)
    0.4 Change log + release policy (consensus-governed)
2. Introduction
    1.1 Purpose (authority-first operational internet privacy)
    1.2 Scope (digital identification management; controller practice transparency)
    1.3 Non-goals / exclusions (v0.1 boundary)
    1.4 Audience and intended use
3. Core principles (normative)
    2.1 Transparency-by-Default (TbD) ordering rule
    2.2 Authority-first rule (scope of authority for surveillance at all times)
    2.3 Macro-data-only raw transfer rule (open internet constraint)
    2.4 Separation: authority/consent vs permission (human vs system act)
    2.5 Evidence is a security property (no post-hoc laundering)
4. Terms, roles, and concepts
5. Normative artifacts (what exists, always)
6. Data classification + transfer rules (normative)
7. Convention 108+ code-of-practice mapping (normative)
8. AuthC 1.2.2 — Order of Operations (Operational Internet Privacy) (normative)
9. AuthC Exchange (authority protocol) (normative)
10. Conformance (normative)
11. Governance: spec evolution by consensus (normative)
12. Security and failure modes (informative)

Appendix A: Minimal field templates
Appendix B: Worked examples
Appendix C: Crosswalk to existing v1.x exchange docs

---

## 1. Introduction

### 1.1 Purpose
AuthC is a form of digital identification management for digital public infrastructure, developed with and for the ISO/IEC 27560-1 profile for notice and consent receipt systems.

AuthC governs authentication (authN) and authorization (authZ) by requiring authority-first disclosure, evidence-grade receipts, and enforceable ordering before any identity verification, identifier binding, or permission enforcement.

AuthC specifies an authority-first, Transparency-by-Default code of practice for Convention 108+ in digital identification management contexts.

The objective is to make controller practice inspectable before any surveillance-relevant act occurs, by requiring controller identification, declared scope of authority for surveillance, and evidence-grade receipt history.

### 1.2 Scope
This specification covers:
- Digital identification management as a surveillance-relevant practice (identifier binding + metadata creation).
- The rule that only macro authority data (controller identification + authority scope disclosure) may travel as raw/open data across the internet.
- Authority evolution through consensus, captured in AuthC Exchange outcomes and receipt history.

### 1.3 Non-goals
- Transport/API protocol details (left to implementation profiles)
- Detailed cryptographic schemes (left to higher-assurance profiles)
- Certification role mechanics (left to later versions)

---

## 2. Core principles (normative)

### 2.1 Controller-ID first
Controller identification MUST be disclosed and retrievable before any identifier binding, tracking, inference, or collection.

### 2.2 Authority-first
Scope of authority for surveillance MUST be disclosed (versioned) and bound to receipts so authority-in-force can be reconstructed at time T.

### 2.3 Macro-data-only raw transfer
Only macro authority data may be transferred as raw/open data across the internet.

Any micro-context data or individual-linked data MUST be authority-scoped, evidence-linked, and proportionate.

### 2.4 Consent (authority) vs permission (enforcement)
Consent (when used) is the human authority act and/or legal-basis condition.

Permission is system enforcement downstream of disclosed authority and proof-of-notice.
