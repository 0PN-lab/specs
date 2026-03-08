# ISO/IEC 27560:2025-1 Universal Notice Receipt Profile v1.02

## Appendices (GitHub split file)

This file is the appendices container for the v1.02 baseline.

---

## Appendix A — Field mapping to ISO/IEC 27560-1:2025

Source page: [Appendix A — Field Mapping](https://www.notion.so/Appendix-A-Field-Mapping-115f9ba65ff24c45b0f1bbebe1dc82b4?pvs=21)

Note: the full mapping tables (one row per field, with clause refs, cardinality, and types) still need to be completed. Until then, this appendix carries a minimum viable mapping set sufficient for implementer alignment.

### A.1 Minimum viable mapping table (selected)

| Base standard (27560) | Profile field (UNRP) | Clause ref (if known) | Change type | Notes |
| --- | --- | --- | --- | --- |
| record_id | receipt_id | 6.3.3.2 | Renamed | Semantic clarity: "receipt" instance tracking |
| pii_principal_id | pii_principal_id | 6.3.3.1 | Constrained | Removed from Stage 1 (anonymous-by-default); optional Stage 2+ |
| party_id (Controller role) | controller_identity_record_id | 6.3.6.* | Extended | Used as CIR-ID; supports registry verification |
| (none) | cir_publication_url | N/A | New | Public CIR location (e.g., /.well-known/transparency/notice.txt) |
| (none) | notice_receipt_type | N/A | New | Stage 1–4 progression indicator |
| (none) | notice_type | N/A | New | notification/disclosure/policy/signal/statement |
| (none) | context_category | N/A | New | privacy/safety/security/environment/ai_system |
| (none) | two_factor_notice_indicator | N/A | New | 2FN pattern flag |
| (none) | scope_of_disclosure | N/A | New | Risk-proportionate disclosure scope |
| (none) | permissions_bundle | N/A | New | Granular permissions; requested Stage 1, granted Stage 2+ |
| (none) | authorization_type | N/A | New | Stage 2+ basis/context semantics |
| event_time | event_time | 6.3.1.1 | Unchanged | Also used for Notice Event Log entries |
| event_type | event_type | 6.3.1.2 | Extended | Adds profile event types; delegation-related when used |

### A.2 Next step (to fully complete Appendix A)

Expand to a full inventory including:

- base field name
- profile field name
- 27560 clause refs (where available)
- requirement level per stage (Stage 1 vs Stage 2+)
- data type + allowed values
- change rationale

---

## Appendix G — Backward compatibility with ISO/IEC TS 27560:2023

### G.1 Terminology evolution

Universal Notice Receipt term → 2025 WD term → 2023 TS term (notes)

- Notice receipt (universal) → Privacy receipt → Consent receipt (2023 scope limited to consent only)
- Notice record (universal) → PII processing record → Consent record (2023 scope limited to consent only)
- authorization_type (implicit in lawful_basis) → N/A → New field for multi-basis and multi-context
- notice_type → N/A → New field for context categorization
- context_category → N/A → New field for domain categorization
- Controller-ID Notice Receipt → N/A → Completes original MVCR purpose
- Co-regulated infrastructure → N/A → Independent receipt generation capability

### G.2 Field migration

2023 TS field → 2023 clause → Universal Notice Receipt field → Migration action

- record_id → 6.3.3.2 → receipt_id → Rename for semantic clarity
- pii_principal_id → 6.3.3.1 → pii_principal_id → Make optional in Stage 1
- party_id (Controller) → 6.3.6.2 → controller_identity_record_id → Enhance with public registry verification
- (none) → N/A → cir_publication_url → Add public CIR location
- (none) → N/A → notice_type → Add for context categorization
- (none) → N/A → context_category → Add for domain categorization
- (none) → N/A → authorization_type → Add for Stage 2 multi-basis/context support
- (none) → N/A → scope_of_disclosure → Add for risk-proportionate transparency
- (none) → N/A → two_factor_notice_indicator → Add for 2FN pattern

### G.3 Migration strategy

For ISO/IEC TS 27560:2023 implementers:

- Current 2023 TS consent record implementations remain valid.
- Adopt ANCR Exchange Stage 1 (Notice Receipt) as an enhancement.
- Publish CIR at a public location (/.well-known/transparency).
- Maintain 2023 field compatibility while adding universal extensions.
- When the 2025 International Standard publishes, adopt full multi-basis and multi-context support.

Interoperability bridge notes:

- schema_version enables version detection.
- 2023 systems can interpret Universal Notice Receipts as consent receipts (ignore unknown/new fields).
- Universal systems can read 2023 receipts and map them to Stage 2 consent context.

---

## Appendix H — Profile types for ISO/IEC 27560:2025

### H.1 Overview of profile types

- Profile Type 1: Data Protection Privacy Receipt Profile
    - Control model: Controller-centric (Individual-ID first)
    - Receipt timing: After individual creates account and provides PII
    - Trust model: Individual depends on controller promises
    - Architecture: Centralized
- Profile Type 2: Co-Regulated Digital Privacy Profile (this document)
    - Control model: Co-regulated transparency (Controller-ID first)
    - Receipt timing: Before any processing/collection begins
    - Trust model: Verifiable through cryptographic receipts and public registries
    - Architecture: Distributed
- Profile Type 3: Personal Data Control Profile
    - Control model: Individual-controlled (SSI/DID anchored)
    - Receipt timing: Individual presents verifiable credentials on demand
    - Trust model: Individual controls authorization distribution
    - Architecture: Decentralized

### H.2 Architectural comparison (summary)

- Primary identifier:
    - Type 1: pii_principal_id (required)
    - Type 2: controller_identity_record_id (CIR-ID first; pii_principal_id optional Stage 2+)
    - Type 3: principal_anchor (DID/public key)
- Notice timing:
    - Type 1: After individual provides PII
    - Type 2: Before any PII collection (Controller-ID first)
    - Type 3: Individual controls timing
- Violation detection:
    - Type 1: Manual after harm
    - Type 2: Automated verification through receipt validation
    - Type 3: Individual-initiated verification

---

## Other appendices (v1.02 baseline set)

The following appendices exist as part of the baseline set; include them here (or split into separate files) as needed:

- Appendix B — Legal Bases and Context Implementation (draft scaffold: [Appendix B — Legal Bases and Context Implementation](https://www.notion.so/Appendix-B-Legal-Bases-and-Context-Implementation-23c3d9ff70d1460cbfbd99537bbf3728?pvs=21))

### Appendix B — Legal Bases and Context Implementation (Draft)

Status: Draft placeholder.

Purpose: Provide implementable guidance for how lawful basis and context interact with authorization_type, notice_type, and Notice Event Log events.

B.1 Legal bases (Convention 108+)

- consent
- contract
- legal_obligation
- legitimate_interest
- vital_interest
- public_interest

B.2 Context categories

- privacy
- safety
- security
- environment
- ai_system (informative extension; see Appendix J)

B.3 Stage 2 authorization_type by legal basis (baseline mapping)

Privacy context authorizations:

- consent → authorization_type = consent_granted
- contract → authorization_type = contract_accepted
- legal_obligation → authorization_type = legal_access_acknowledged
- legitimate_interest → authorization_type = legitimate_interest_objection (or legitimate_interest_acknowledged where high-risk acknowledgement is required but not permission-gating)
- vital_interest → authorization_type = emergency_notified
- public_interest → authorization_type = public_interest_participation

Non-privacy context authorizations:

- safety → authorization_type = safety_acknowledgment
- security → authorization_type = security_policy_acceptance
- environment → authorization_type = environmental_disclosure_acknowledgment

B.4 Minimum Notice Event Log event taxonomy (by basis)

Stage 1 (notice): notice_issued, material_change

Stage 2 (authorization/ack): consent_granted / contract_accepted / legal_access_acknowledged / objection_received / emergency_notified / public_interest_participation

Termination + updates: consent_withdrawn (or authorization_terminated), permission_changed

Delegation (when used): delegation_granted, delegation_revoked, delegation_expired, delegation_superseded

B.5 Implementation rules (normative-style guidance)

- Stage 1 applies to all lawful bases: it is a scope rule, not a consent rule.
- Stage 2 semantics MUST match lawful basis (MUST NOT represent Stage 2 as consent unless lawful_basis is consent).
- Legitimate interest is notify-by-default + objection-capable (not permission-gated).
- Appendix D — Emergency Protocols (currently empty in Notion)
- Appendix E — Open Questions for Reviewers (currently empty in Notion)
- Appendix F — (Reserved)
- Appendix I — (Reserved)
- Appendix J — AI System Context Implementation (Informative)
- Appendix K — Enhanced Transparency Features for v1.1 (Informative)

### Appendix J — AI System Context Implementation (Informative)

Source page: [Appendix J — AI System Context Implementation (Informative)](https://www.notion.so/Appendix-J-AI-System-Context-Implementation-Informative-cefc87412dcc40b4890dfb455b801055?pvs=21)

Status: INFORMATIVE — Optional extension.

Key elements:

- AI-specific notice types (e.g., automated decision disclosure)
- AI-specific authorization types (Stage 2)
- AI Notice Event Log requirements (mandatory AI events + example log entries)
- High-risk AI enhanced transparency via CIR ai_system_documentation
- Cross-border AI deployment disclosure

### Appendix K — Enhanced Transparency Features for v1.1 (Informative)

Source page: [Appendix K — Enhanced Transparency Features for v1.1 (Informative)](https://www.notion.so/Appendix-K-Enhanced-Transparency-Features-for-v1-1-Informative-e312202351cf4d01870c83569720b8b8?pvs=21)

Status: INFORMATIVE — Deferred features for v1.1.

Key elements:

- Privacy preference signals (GPC/DNT) fields + Notice Event Log event types
- Transparency assurance levels (TATA) + trustmarks + visual indicators
- Global Privacy Rights Controls (GPRC) framework (72 contexts)
- v1.1 implementation timeline

---

## Completeness note

This file exists to avoid Notion export/render limits. As appendices are extracted from the canonical baseline, replace each TODO section with the complete appendix text.