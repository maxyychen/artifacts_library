---
id: BUS-DIA-02
title: Business Footprint Diagram
artifact_type: diagram
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Business Footprint Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Maps business goals to the functions, organizational units, and applications
that realize them, showing the "footprint" of each goal across the business.

## Diagram

```mermaid
flowchart LR
  subgraph GOALS["Goals"]
    G1[Unify Customer Experience]
    G2[Improve Inventory Accuracy]
  end

  subgraph FUNCTIONS["Business Functions"]
    F1[Customer Management]
    F2[Inventory Management]
  end

  subgraph ORGS["Org Units"]
    O1[Marketing]
    O2[Supply Chain]
  end

  subgraph APPS["Applications"]
    A1[Beacon CRM]
    A2[FlowStock WMS]
  end

  G1 --> F1 --> O1 --> A1
  G2 --> F2 --> O2 --> A2
```

## Notes

- Goals correspond to the drivers listed in
  [[01-architecture-vision/architecture-vision]].
- FlowStock WMS is the SBB-03 selection from
  [[06-opportunities-and-solutions/solution-building-blocks-catalog]].
