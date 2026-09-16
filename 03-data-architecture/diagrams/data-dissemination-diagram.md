---
id: DATA-DIA-02
title: Data Dissemination Diagram
artifact_type: diagram
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Data Dissemination Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows how the Customer entity is distributed and replicated across
applications and locations.

## Diagram

```mermaid
flowchart LR
  Beacon[Beacon CRM\nsystem of record] -- event: customer.updated --> NovaCache[Nova Commerce\nread-through cache]
  Beacon -- event: customer.updated --> StoreLineCache[StoreLine POS\nread-through cache]
  Beacon -- nightly extract --> Helix[Helix ERP\nread-only replica]
  Coastal[Coastal Legacy ERP] -. temporary sync adapter .-> Beacon
```

## Notes

- Nova Commerce and StoreLine POS hold no independent copy of Customer data;
  they cache reads only, consistent with
  [[04-application-architecture/matrices/application-data-matrix]].
- The Coastal Legacy ERP feed is temporary; see RISK-01 in
  [[11-risk-and-security/risk-register]].
