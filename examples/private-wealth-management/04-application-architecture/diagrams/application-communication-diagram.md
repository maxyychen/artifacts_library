---
id: PW-APP-DIA-01
title: Application Communication Diagram
artifact_type: diagram
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.0
---

# Application Communication Diagram

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Shows the integration interfaces between SPW's core applications and
external custodians.

## Diagram

```mermaid
flowchart LR
  Harborstone[Harborstone Custody] -- Batch file, nightly --> Ledgerline[Ledgerline]
  Falcon[Falcon Trust Co] -- Batch file, nightly --> Ledgerline
  Ledgerline -- REST: holdings/performance --> Portal[ClientPortal]
  Ledgerline -- REST: holdings/performance --> CRM[AdvisorHub CRM]
  CRM -- REST: household lookup --> Plan[PlanForward]
  Ledgerline -- REST: trade activity --> Comply[ComplyWatch]
  Ledgerline -- REST: billable AUM --> Bill[BillRight]
  Foxglove[Foxglove PMS] -. Manual export/import .-> Ledgerline
```

## Notes

- Dashed edge indicates the temporary, manual migration path for Birchwood
  households, slated for decommission alongside Foxglove PMS retirement.
- Corresponds to relationships implied in
  [[04-application-architecture/matrices/application-function-matrix]].
