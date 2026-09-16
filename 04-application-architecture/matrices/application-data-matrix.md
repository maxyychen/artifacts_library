---
id: APP-MAT-02
title: Application/Data Matrix
artifact_type: matrix
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.1
---

# Application/Data Matrix

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows which applications create, read, update, or delete each core data
entity, distinct from the function-level view in
[[03-data-architecture/matrices/data-entity-business-function-matrix]].

## Matrix

| | Customer | Order | Product | Inventory Position |
|---|---|---|---|---|
| **Nova Commerce** | R | CRU | R | R |
| **StoreLine POS** | R | CRU | R | R |
| **Helix ERP** | R | CRUD | CRUD | RU |
| **Beacon CRM** | CRUD | R | | |
| **WMS Classic** | | | R | CRUD |
| **Coastal Legacy ERP** | CRUD | R | | |

## Legend

| Symbol | Meaning |
|--------|---------|
| C | Create |
| R | Read |
| U | Update |
| D | Delete |
| CRUD | Full lifecycle ownership |

## Notes

- Baseline state: Beacon CRM and Coastal Legacy ERP both hold full CRUD
  ownership of Customer — the dual system-of-record condition tracked as
  gap G-02 in [[06-opportunities-and-solutions/gap-analysis]]. Target state,
  with Beacon CRM as sole CRUD owner, is defined in
  [[08-implementation-governance/architecture-contract]].
- WMS Classic holds CRUD on Inventory Position today; it is slated for
  replacement by FlowStock WMS (SBB-03) per gap G-04 in
  [[06-opportunities-and-solutions/gap-analysis]].
