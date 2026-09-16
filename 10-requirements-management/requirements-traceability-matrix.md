---
id: REQ-TRACE-01
title: Requirements Traceability Matrix - Unified Commerce Platform
artifact_type: matrix
adm_phase: Requirements Management
status: reviewed
owner: Chief Architect
version: 1.0
---

# Requirements Traceability Matrix: Unified Commerce Platform

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Traces each requirement in [[10-requirements-management/requirements-catalog]]
back to the driver/principle that motivated it and forward through the gap,
solution building block, work package, and verification artifact that
satisfies it. This is the authoritative end-to-end lineage; individual
artifacts only carry point-to-point links.

## Matrix

| Req ID | Requirement | Traces From | Gap | SBB | Work Package | Verified By | Trace Status |
|--------|-------------|-------------|-----|-----|---------------|--------------|---------------|
| REQ-01 | Inventory position visible across channels within 5s | Driver: Inventory inaccuracy | G-04 | SBB-03 | WP-04 | — | Partially Traced (WMS not yet deployed) |
| REQ-02 | Customer profile/loyalty balance identical in-store/online | Driver: Customer fragmentation | G-02 | SBB-01 | WP-02 | GOV-01, GOV-CONTRACT-01 | Traced |
| REQ-03 | PCI-DSS Level 1 maintained throughout migration | PRIN-05 (Security by Design) | — (cross-cutting) | InsightPay Gateway (existing PCI scope) | All work packages | RISK-01 | Traced (cross-cutting, not gap-driven) |
| REQ-04 | Store cutover ≤ 40 stores/month | Constraint: Architecture Vision | — | — | WP-02, WP-04 (paced by this constraint) | RISK-03, BTRA-01 | Traced (constraint, not gap-driven) |
| REQ-05 | Loyalty sync across channels within 1 minute | Driver: Customer fragmentation | G-02 | SBB-01 | WP-02 | — | Partially Traced |
| REQ-06 | 3,000 concurrent checkout transactions at peak | Driver: CFO (peak demand) | *unmapped* | *unmapped* | *unmapped* | — | **Untraced** |
| REQ-07 | Returns acceptable at any store regardless of channel | (Draft, not yet ratified) | G-01 (proposed) | — | WP-01 (proposed) | — | **Untraced** (draft requirement) |

## Legend

| Status | Meaning |
|--------|---------|
| Traced | Full chain from driver to verification artifact exists |
| Partially Traced | Chain exists to a work package but no verification artifact yet |
| Untraced | No gap, SBB, or work package currently claims this requirement |

## Notes

- REQ-06 is the one fully untraced *approved* requirement — no gap, SBB, or
  work package currently addresses 3,000 concurrent checkout transactions.
  This was flagged informally in
  [[10-requirements-management/requirements-catalog]]; this matrix makes it a
  visible open item for the next planning cycle rather than a buried note.
- REQ-07 is still in Draft status; its tentative trace to G-01/WP-01 should
  be confirmed (or the requirement re-scoped) before it is promoted to
  Approved.
- REQ-03 and REQ-04 are cross-cutting constraints rather than
  capability gaps, so they trace to risk and readiness artifacts
  ([[11-risk-and-security/risk-register]],
  [[06-opportunities-and-solutions/business-transformation-readiness-assessment]])
  instead of a single gap/SBB pair.
