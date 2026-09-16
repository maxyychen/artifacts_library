---
id: DATA-MAT-01
title: Data Entity/Business Function Matrix
artifact_type: matrix
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Data Entity/Business Function Matrix

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Cross-references data entities against the business functions that create,
read, update, or delete them (CRUD).

## Matrix

| | Order Management | Inventory Management | Customer Management | Store Operations |
|---|---|---|---|---|
| **Customer** | R | | CRUD | R |
| **Order** | CRUD | R | R | CRU |
| **Product** | R | R | | R |
| **Inventory Position** | RU | CRUD | | RU |
| **Loyalty Account** | R | | CRUD | RU |

## Legend

| Symbol | Meaning |
|--------|---------|
| C | Create |
| R | Read |
| U | Update |
| D | Delete |
| CRUD | Full lifecycle ownership |

## Notes

- Only Customer Management holds full CRUD on Customer, confirming it as
  system-of-record owner consistent with [[03-data-architecture/catalogs/data-entity-catalog]].
