---
id: BUS-MAT-02
title: Actor/Role Matrix
artifact_type: matrix
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Actor/Role Matrix

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows which roles (defined in
[[02-business-architecture/catalogs/organization-actor-catalog]]) are
Responsible, Accountable, Consulted, or Informed for each business service,
adding role-level RACI detail beneath the org-unit-level view in
[[02-business-architecture/matrices/business-interaction-matrix]].

## Matrix

| | Place Order | Check Stock Availability | Maintain Customer Profile | Process In-Store Payment | Process Return/Refund | Manage Loyalty Rewards |
|---|---|---|---|---|---|---|
| **Store Associate** | RA | C | I | RA | R | I |
| **Customer Service Representative** | I | I | C | | RA | C |

## Legend

| Symbol | Meaning |
|--------|---------|
| R | Responsible - performs the work |
| A | Accountable - owns the outcome |
| C | Consulted - provides input |
| I | Informed - kept up to date |

## Notes

- Customer Service Representative is shown Accountable for Process
  Return/Refund, which formalizes at the role level the ownership change
  that [[07-migration-planning/implementation-and-migration-plan]] WP-01
  ("Define Customer Service ownership model") is chartered to deliver — see
  gap G-01 in [[06-opportunities-and-solutions/gap-analysis]].
- Architecture Review Board (OA-08) is intentionally excluded — it is a
  governance actor, not a service-delivery role, and has no cells in this
  matrix.
