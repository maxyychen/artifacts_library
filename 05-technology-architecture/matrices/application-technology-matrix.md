---
id: TECH-MAT-01
title: Application/Technology Matrix
artifact_type: matrix
adm_phase: Technology Architecture
status: reviewed
owner: Technology Architect
version: 1.0
---

# Application/Technology Matrix

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows which technology platforms host each application.

## Matrix

| | AWS (EKS) | PostgreSQL | Oracle 11g | On-Prem VMware |
|---|---|---|---|---|
| **Nova Commerce** | X | X | | |
| **StoreLine POS** | X | X | | X |
| **Helix ERP** | X | X | | |
| **Beacon CRM** | X | X | | |
| **Coastal Legacy ERP** | | | X | X |

## Legend

| Symbol | Meaning |
|--------|---------|
| X | Application is hosted on / uses this platform |

## Notes

- Coastal Legacy ERP is the only application still on Oracle 11g and
  on-prem VMware, both flagged Deprecated in
  [[05-technology-architecture/catalogs/technology-standards-catalog]].
