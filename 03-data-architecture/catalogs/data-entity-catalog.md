---
id: DATA-CAT-01
title: Data Entity Catalog
artifact_type: catalog
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Data Entity Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Inventories the core business data entities, their system of record, and
their classification.

## Entries

| ID | Name | Description | Owner | Status |
|----|------|--------------|-------|--------|
| DE-01 | Customer | Individual who purchases from MRG across any channel | Marketing | Active |
| DE-02 | Order | A confirmed purchase transaction, one or more line items | Commerce Operations | Active |
| DE-03 | Product | A sellable item, including SKU-level attributes | Merchandising | Active |
| DE-04 | Inventory Position | Quantity on hand of a Product at a Location | Supply Chain | Active |
| DE-05 | Location | A store, distribution center, or fulfillment node | Supply Chain | Active |
| DE-06 | Loyalty Account | A customer's accrued points and tier | Marketing | Active |
| DE-07 | Payment Transaction | An authorization/capture/refund event tied to an Order | Finance | Active |

## Notes

- DE-01 (Customer) is designated the master entity per PRIN-02 in
  [[00-preliminary/architecture-principles-catalog]]; system of record is
  being consolidated per [[01-architecture-vision/architecture-vision]].
- Classification and protection requirements per entity are detailed in
  [[03-data-architecture/diagrams/data-security-diagram]].
