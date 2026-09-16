---
id: PW-TECH-MAT-01
title: Application/Technology Matrix
artifact_type: matrix
adm_phase: Technology Architecture
status: reviewed
owner: Technology Architect
version: 1.0
---

# Application/Technology Matrix

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Shows which technology platforms host each application.

## Matrix

| | AWS (EKS) | PostgreSQL | SQL Server 2014 | On-Prem Windows Server |
|---|---|---|---|---|
| **Ledgerline** | X | X | | |
| **AdvisorHub CRM** | X | X | | |
| **PlanForward** | X | X | | |
| **BillRight** | X | X | | |
| **ComplyWatch** | X | X | | |
| **ClientPortal** | X | | | |
| **Foxglove PMS** | | | X | X |

## Legend

| Symbol | Meaning |
|--------|---------|
| X | Application is hosted on / uses this platform |

## Notes

- Foxglove PMS is the only application still on SQL Server 2014 and on-prem
  Windows Server, both flagged Deprecated in
  [[05-technology-architecture/catalogs/technology-standards-catalog]].
