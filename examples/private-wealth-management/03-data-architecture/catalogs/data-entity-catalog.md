---
id: PW-DATA-CAT-01
title: Data Entity Catalog
artifact_type: catalog
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Data Entity Catalog

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Inventories the core business data entities, their system of record, and
their classification.

## Entries

| ID | Name | Description | Owner | Status |
|----|------|--------------|-------|--------|
| PW-DE-01 | Household | A family unit and its relationship to SPW, spanning one or more accounts | Advisory Services | Active |
| PW-DE-02 | Account | A specific investment account (IRA, trust, joint, etc.) belonging to a household | Client Reporting & Operations | Active |
| PW-DE-03 | Holding | A position in a security within an account | Client Reporting & Operations | Active |
| PW-DE-04 | Transaction | A trade, deposit, withdrawal, or fee event tied to an account | Portfolio Management & Trading | Active |
| PW-DE-05 | Financial Plan | A goals-based financial plan for a household | Advisory Services | Active |
| PW-DE-06 | Fee Schedule | The advisory fee terms tied to a household or account | Client Reporting & Operations | Active |

## Notes

- PW-DE-01 (Household) is designated the master entity per PW-PRIN-02 in
  [[00-preliminary/architecture-principles-catalog]]; system of record is
  being consolidated per [[01-architecture-vision/architecture-vision]].
