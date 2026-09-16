---
id: PW-PRIN-CAT-01
title: Architecture Principles Catalog
artifact_type: catalog
adm_phase: Preliminary
status: approved
owner: Chief Architect
version: 1.0
---

# Architecture Principles Catalog

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Establishes the architecture principles that guide all Silverline Private
Wealth (SPW) architecture decisions across the ADM cycle.

## Entries

| ID | Name | Statement | Rationale | Implications |
|----|------|-----------|-----------|---------------|
| PW-PRIN-01 | Fiduciary Data Integrity First | Household and portfolio data must be complete, accurate, and auditable at all times | Fiduciary duty and SEC examination risk depend on demonstrably correct records | Reconciliation controls required before any new integration goes live |
| PW-PRIN-02 | Household Is a Shared Asset | The Household entity is defined once and shared across CRM, portfolio accounting, planning, and the client portal, not duplicated per system | Duplicated household data causes conflicting views between advisors and clients | Requires a master data management capability and single system-of-record designation |
| PW-PRIN-03 | Buy Before Build | Commercial off-the-shelf software is preferred over custom development unless it delivers competitive differentiation | SPW is a wealth manager, not a software company; custom code carries maintenance risk | Custom builds require an explicit business-case waiver |
| PW-PRIN-04 | Cloud First, Recordkeeping Aware | New workloads default to public cloud unless SEC recordkeeping rules dictate otherwise | Supports infrastructure modernization while respecting SEC 17a-4 constraints | Legacy on-prem systems require a migration or retirement plan that preserves records retention |
| PW-PRIN-05 | Compliance by Design | Every client-facing or trade-related system change requires Chief Compliance Officer (CCO) sign-off and a full audit trail | Regulatory exposure under SEC Reg BI and books-and-records rules | Every project requires a compliance review gate before go-live |

## Notes

- Principles are reviewed annually by the Architecture Review Board (see
  [[08-implementation-governance/architecture-compliance-assessment]]).
- PW-PRIN-03 is the principle most often in tension with PW-PRIN-01 when a
  legacy data format has no COTS migration path; see
  [[09-architecture-change-management/architecture-change-request]].
