---
id: DATA-DIA-01
title: Core Data Entity Relationship Diagram
artifact_type: diagram
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Core Data Entity Relationship Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows the relationships between MRG's core data entities.

## Diagram

```mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  CUSTOMER ||--o| LOYALTY_ACCOUNT : holds
  ORDER ||--|{ ORDER_LINE : contains
  ORDER_LINE }o--|| PRODUCT : references
  ORDER ||--|| PAYMENT_TRANSACTION : "paid by"
  PRODUCT ||--o{ INVENTORY_POSITION : "stocked as"
  LOCATION ||--o{ INVENTORY_POSITION : holds
```

## Notes

- Matches entities defined in [[03-data-architecture/catalogs/data-entity-catalog]].
- ORDER_LINE is a decomposition of Order (DE-02) not separately catalogued.
