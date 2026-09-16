---
id: GOV-CONTRACT-01
title: Architecture Contract - WP-02 Customer Profile Consolidation
artifact_type: architecture-contract
adm_phase: Implementation Governance
status: approved
owner: Architecture Review Board
version: 1.0
---

# Architecture Contract: WP-02 Customer Profile Consolidation

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Formal agreement between the Architecture Review Board and the delivery team
for WP-02, binding the project to the architecture defined for it.

## Parties

| Role | Party |
|------|-------|
| Architecture Sponsor | Chief Architect |
| Delivery Owner | Marketing Engineering Team Lead |
| Governance Body | Architecture Review Board |

## Scope

Consolidate Customer entity into Beacon CRM as sole system of record,
including migration of records from Coastal Legacy ERP via the adapter
described in [[09-architecture-change-management/architecture-change-request]].

## Deliverables

| Deliverable | Due Date |
|-------------|----------|
| Data mapping specification (Coastal → Beacon) | 2026-10-30 |
| Sync adapter deployed to staging | 2026-12-15 |
| Production cutover | 2027-02-28 |

## Compliance Requirements

- Must pass the criteria in [[08-implementation-governance/architecture-compliance-assessment]].
- Must not introduce a second system of record for Customer (PRIN-02).
- Adapter must be decommissioned within 30 days of Coastal Legacy ERP
  retirement (WP-05).

## Acceptance Criteria

- Zero customer records lost or duplicated during migration (validated by
  reconciliation report).
- Beacon CRM API becomes the only integration point for Customer data across
  Nova Commerce and StoreLine POS.

## Signatures

*Pending — contract enters effect upon Architecture Review Board sign-off.*

## Notes

- Breach of the compliance requirements triggers a mandatory entry in
  [[09-architecture-change-management/architecture-change-request]].
