---
id: PW-DATA-MAT-01
title: Data Entity/Business Function Matrix
artifact_type: matrix
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Data Entity/Business Function Matrix

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Cross-references data entities against the business functions that create,
read, update, or delete them (CRUD).

## Matrix

| | Client Onboarding | Financial Planning | Portfolio Management | Reporting & Billing |
|---|---|---|---|---|
| **Household** | CRUD | R | R | R |
| **Account** | CRUD | R | R | R |
| **Holding** | | | CRUD | R |
| **Transaction** | | | CRUD | R |
| **Financial Plan** | | CRUD | | R |
| **Fee Schedule** | R | | | CRUD |

## Legend

| Symbol | Meaning |
|--------|---------|
| C | Create |
| R | Read |
| U | Update |
| D | Delete |
| CRUD | Full lifecycle ownership |

## Notes

- Only Client Onboarding holds full CRUD on Household, confirming it as the
  intended system-of-record owner consistent with
  [[03-data-architecture/catalogs/data-entity-catalog]].
