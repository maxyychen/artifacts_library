---
id: TECH-DIA-01
title: Environments and Locations Diagram
artifact_type: diagram
adm_phase: Technology Architecture
status: reviewed
owner: Technology Architect
version: 1.0
---

# Environments and Locations Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows physical/cloud hosting locations and which applications run where.

## Diagram

```mermaid
flowchart TB
  subgraph AWS_US_EAST["AWS us-east-1 (Primary Cloud Region)"]
    Nova[Nova Commerce]
    Helix[Helix ERP]
    Beacon[Beacon CRM]
  end

  subgraph AWS_US_WEST["AWS us-west-2 (DR Region)"]
    NovaDR[Nova Commerce - standby]
    HelixDR[Helix ERP - standby]
  end

  subgraph ONPREM["On-Prem Data Center - Columbus, OH"]
    Coastal[Coastal Legacy ERP]
    POSHub[StoreLine POS - central hub]
  end

  subgraph STORES["420 Retail Store Locations"]
    POS[StoreLine POS terminals]
  end

  AWS_US_EAST -. async replication .-> AWS_US_WEST
  POSHub --> POS
  POS --> Helix
```

## Notes

- DR region is warm-standby only; failover is manual, tracked as a gap in
  [[06-opportunities-and-solutions/gap-analysis]].
- Columbus on-prem data center is slated for exit per PRIN-04 in
  [[00-preliminary/architecture-principles-catalog]].
