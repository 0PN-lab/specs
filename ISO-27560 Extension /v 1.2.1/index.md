# ISO/IEC 27560-1 v1.2 — Digital Consent (Consolidated)
**Code of Conduct Profile packaging built on the Universal Notice Receipt (UNR) profile lineage**

> **Status:** Consolidated draft (v1.2)  
> **Prerequisite:** UNR (v1 / v1.01) is required to interpret and apply this package correctly.

## Start here
- **v1.2 Consolidated specification (Digital Consent):**  
  https://github.com/0PN-lab/specs/blob/bd54d86fe8d063b6f935f1adf5cadb6adf85f928/27560%20profile%20/v%201.2%20-%20Digital%20Notice%20%26%20Consent%20Profile%20/v1.2%20-%20Digital%20Consent%20(consolidated).md

## What this is
This page introduces the **v1.2 consolidated packaging** that frames the 0PN Lab ISO/IEC 27560 profile work as a **Digital Consent Code of Conduct Profile**.

**Core idea:** ISO/IEC TS 27560:2023 defines a consent record information structure. The UNR profile lineage extends it into **Transparency-by-Default** infrastructure by requiring **Controller Identification disclosure before personal data processing begins** (Controller-ID first), with **bilateral proof-of-notice** and supporting auditability.

## Foundation (base standard)
ISO/IEC TS 27560:2023 — *Privacy technologies — Consent record information structure*  
ISO catalogue page: https://www.iso.org/standard/80392.html

## Reading path (UNR → consolidated Digital Consent)
This v1.2 package assumes the UNR profile lineage. Recommended reading order:

1) **v1 (UNR) — Universal Notice Receipt (submission draft PDF)**  
   https://github.com/0PN-lab/specs/blob/e19ad403f5ee6a200ff65d02913fd854243b356f/27560%20profile%20/v%201%20-%20UNR%20-%20Notice%20Receipt/27560-1%20Universal%20Notice%20Receipt%20v1%20(Draft%20for%20Submission)141225.pdf

2) **v1.01 (UNR) — baseline internal draft (best implementer reference)**  
   https://github.com/0PN-lab/specs/blob/e19ad403f5ee6a200ff65d02913fd854243b356f/27560%20profile%20/v%201.01%20-%20UNR%20-%20Notice%20Receipt/ISO-IEC-27560-1-v1.01.md

3) **v1.1 — working draft enhancement set (pilot only)**  
   https://github.com/0PN-lab/specs/blob/bd54d86fe8d063b6f935f1adf5cadb6adf85f928/27560%20profile%20/v1.1/v1.1%20UNRP.md

4) **v1.2 — Digital Consent (consolidated)**  
   Start with the v1.2 consolidated doc link above.

## What “Digital Consent” means here
“Digital Consent” in this consolidated package is not a UI click-through pattern. It is a **governance-grade, inspectable record of meaningful choice** built on:

- **Controller-ID first disclosure** before collection or inference
- **Bilateral notice receipts** held by both controller and individual
- **Notice event logs** that track state changes and material updates
- **Portability** patterns (where applicable) that avoid surveillance intermediaries

This is **privacy-enabling** infrastructure: transparency comes first, enabling an individual to decide what architecture to trust.

## Who this is for
- Standards participants reviewing the profile lineage and the consolidated packaging
- Implementers who need the consolidated framing, but should start from v1.01 for baseline stability
- Regulators and policy stakeholders assessing “Code of Conduct Profile” positioning and auditability requirements

## Conformance / implementation guidance
- For the most stable implementer reference, start from **v1.01** (linked above).
- Treat v1.1 and v1.2 as draft/consolidation materials unless a specific pilot or review process requires otherwise.

## License
Repository license:  
https://github.com/0PN-lab/specs/blob/main/LICENSE
