---
id: PW-BUS-DIA-01
title: Business Footprint Diagram
artifact_type: diagram
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Business Footprint Diagram

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Maps business goals to the functions, organizational units, and
applications that realize them, showing the "footprint" of each goal across
the firm.

## Diagram

```mermaid
flowchart LR
  subgraph GOALS["Goals"]
    G1[Unify Household View]
    G2[Real-Time Custodian Reconciliation]
  end

  subgraph FUNCTIONS["Business Functions"]
    F1[Client Onboarding]
    F2[Reporting & Billing]
  end

  subgraph ORGS["Org Units"]
    O1[Client Onboarding & Compliance]
    O2[Client Reporting & Operations]
  end

  subgraph APPS["Applications"]
    A1[AdvisorHub CRM]
    A2[Ledgerline]
  end

  G1 --> F1 --> O1 --> A1
  G2 --> F2 --> O2 --> A2
```

## Notes

- Goals correspond to the drivers listed in
  [[01-architecture-vision/architecture-vision]].
- Ledgerline's reconciliation module is the PW-SBB-03 selection from
  [[06-opportunities-and-solutions/solution-building-blocks-catalog]].
