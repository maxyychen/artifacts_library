---
id: VISION-DIA-01
title: Value Chain Diagram
artifact_type: diagram
adm_phase: Architecture Vision
status: approved
owner: Chief Architect
version: 1.0
---

# Value Chain Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows MRG's primary and support activities, to identify where the Unified
Commerce Platform creates competitive differentiation.

## Diagram

```mermaid
flowchart TB
  subgraph PRIMARY["Primary Activities"]
    direction LR
    P1[Merchandise Sourcing] --> P2[Inventory & Distribution] --> P3[Store & Online Selling] --> P4[Order Fulfillment] --> P5[Customer Service & Returns]
  end

  subgraph SUPPORT["Support Activities"]
    direction LR
    S1[Technology Infrastructure]
    S2[Human Resources]
    S3[Finance & Procurement]
    S4[Marketing & Loyalty]
  end

  SUPPORT -.-> PRIMARY
```

## Notes

- P3 and P4 are the focus of the Unified Commerce Platform program (see
  [[01-architecture-vision/architecture-vision]]); S4 (Marketing & Loyalty)
  is the secondary focus via customer profile consolidation.
