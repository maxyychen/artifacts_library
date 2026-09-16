---
id: REQ-CAT-01
title: Requirements Catalog - Unified Commerce Platform
artifact_type: catalog
adm_phase: Requirements Management
status: approved
owner: Chief Architect
version: 1.1
---

# Requirements Catalog: Unified Commerce Platform

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Central repository of functional and non-functional requirements feeding
every ADM phase, per TOGAF's Requirements Management discipline. Requirements
here trace back to [[01-architecture-vision/architecture-vision]] and forward
into gaps and work packages.

## Entries

| ID | Requirement | Type | Priority | Source | Status |
|----|-------------|------|----------|--------|--------|
| REQ-01 | Inventory position must be visible across channels within 5 seconds of a change | Non-Functional | Must | Architecture Vision | Approved |
| REQ-02 | A customer's profile and loyalty balance must be identical whether viewed in-store or online | Functional | Must | Architecture Vision | Approved |
| REQ-03 | PCI-DSS Level 1 compliance must be maintained throughout migration, with no lapse in scope | Non-Functional | Must | CISO | Approved |
| REQ-04 | Store cutover to the new platform must not exceed 40 stores/month | Non-Functional | Must | COO | Approved |
| REQ-05 | Loyalty point accrual/redemption must sync across channels within 1 minute | Functional | Should | CMO | Approved |
| REQ-06 | System must support at least 3,000 concurrent checkout transactions during peak (Black Friday) | Non-Functional | Must | CFO | Approved |
| REQ-07 | Returns must be acceptable at any store regardless of original purchase channel | Functional | Should | Customer Service | Draft |

## Notes

- REQ-01 (inventory visibility) directly informed gap G-04, and REQ-02
  (customer profile consistency) directly informed gap G-02, in
  [[06-opportunities-and-solutions/gap-analysis]].
- REQ-06 is not yet mapped to a work package; flagged for scoping in the next
  planning cycle.
- Full requirement-to-architecture-to-delivery lineage is maintained in
  [[10-requirements-management/requirements-traceability-matrix]].
