---
id: PW-DATA-DIA-01
title: Core Data Entity Relationship Diagram
artifact_type: diagram
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Core Data Entity Relationship Diagram

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Shows the relationships between SPW's core data entities.

## Diagram

```mermaid
erDiagram
  HOUSEHOLD ||--o{ ACCOUNT : holds
  HOUSEHOLD ||--o| FINANCIAL_PLAN : has
  HOUSEHOLD ||--|| FEE_SCHEDULE : "billed under"
  ACCOUNT ||--o{ HOLDING : contains
  ACCOUNT ||--o{ TRANSACTION : records
  HOLDING }o--|| TRANSACTION : "adjusted by"
```

## Notes

- Matches entities defined in
  [[03-data-architecture/catalogs/data-entity-catalog]].
- Every Account belongs to exactly one Household, the basis for
  [[06-opportunities-and-solutions/gap-analysis]] gap G-02 (households
  currently split across two systems have two conflicting Account sets).
