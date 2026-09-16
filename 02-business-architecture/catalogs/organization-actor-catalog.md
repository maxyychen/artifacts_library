---
id: BUS-CAT-02
title: Organization/Actor Catalog
artifact_type: catalog
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Organization/Actor Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Inventories the organizational units, roles, and actors referenced across
MRG's business architecture.

## Entries

| ID | Name | Type | Description | Reports To |
|----|------|------|--------------|------------|
| OA-01 | Store Operations | Org Unit | Runs the 420 physical retail locations | COO |
| OA-02 | Commerce Operations | Org Unit | Owns order management and returns processes | COO |
| OA-03 | Supply Chain | Org Unit | Owns inventory, distribution, and replenishment | COO |
| OA-04 | Marketing | Org Unit | Owns customer profile, loyalty, and campaigns | CMO |
| OA-05 | Customer Service | Org Unit | Handles post-purchase support across channels | CMO |
| OA-06 | Store Associate | Role | Front-line staff operating POS and assisting customers | Store Operations |
| OA-07 | Customer Service Representative | Role | Handles inbound support requests and returns | Customer Service |
| OA-08 | Architecture Review Board | Actor (Governance Body) | Approves architecture contracts and compliance decisions | Chief Architect |

## Notes

- OA-05 (Customer Service) currently has no direct service ownership per
  [[02-business-architecture/matrices/business-interaction-matrix]]; tracked
  as gap G-01.
