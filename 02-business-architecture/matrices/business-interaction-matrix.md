---
id: BUS-MAT-01
title: Business Interaction Matrix
artifact_type: matrix
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Business Interaction Matrix

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows which organizational units interact with which business services, and
the nature of the interaction (I = Initiates, P = Participates, C = Consulted).

## Matrix

| | Place Order | Check Stock | Maintain Customer Profile | Process In-Store Payment | Process Return |
|---|---|---|---|---|---|
| **Store Operations** | P | P | C | I | I |
| **Commerce Operations** | I | C | P | | P |
| **Supply Chain** | | I | | | C |
| **Marketing** | | | I | | |
| **Customer Service** | C | C | P | | P |

## Legend

| Symbol | Meaning |
|--------|---------|
| I | Initiates the service |
| P | Participates in fulfilling the service |
| C | Consulted / receives information |

## Notes

- Highlights that Customer Service has no direct ownership of any service,
  flagged as a gap in [[06-opportunities-and-solutions/gap-analysis]].
- Role-level RACI detail beneath this org-unit view is in
  [[02-business-architecture/matrices/actor-role-matrix]].
