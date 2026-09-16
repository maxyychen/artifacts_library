---
id: BUS-CAT-03
title: Process/Event/Control/Product Catalog
artifact_type: catalog
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.1
---

# Process/Event/Control/Product Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Inventories the business processes, triggering events, controls, and
customer-facing products that realize the functions/services in
[[02-business-architecture/catalogs/business-service-function-catalog]].

## Entries

| ID | Type | Name | Description | Related Function | Owner |
|----|------|------|--------------|-------------------|-------|
| PECP-01 | Process | Order Capture and Confirmation | Captures and confirms a customer order across any channel | Order Management (BF-01) | Commerce Operations |
| PECP-02 | Event | Order Placed | Fired when a customer completes checkout | Order Management (BF-01) | Commerce Operations |
| PECP-03 | Control | Payment Authorization Control | Ensures cardholder data is tokenized before storage or transmission | Process In-Store Payment (BF-07) | CISO |
| PECP-04 | Process | Stock Replenishment | Reorders from a distribution center or supplier when triggered | Inventory Management (BF-04) | Supply Chain |
| PECP-05 | Event | Stock Below Threshold | Fired when on-hand quantity drops below reorder point | Inventory Management (BF-04) | Supply Chain |
| PECP-06 | Product | Loyalty Tier Reward | Customer-facing tiered loyalty benefit | Manage Loyalty Rewards (BF-06) | Marketing |
| PECP-07 | Control | Return Authorization Control | Validates return eligibility before a refund is issued | Process Return/Refund (BF-08) | Commerce Operations |
| PECP-08 | Event | Return Initiated | Fired when a customer requests a return, any channel | Process Return/Refund (BF-08) | Customer Service |

## Notes

- PECP-05 (Stock Below Threshold) is the event that should drive real-time
  replenishment; today it fires with unreliable latency from WMS Classic,
  part of the case for gap G-04 in
  [[06-opportunities-and-solutions/gap-analysis]] and SBB-03 in
  [[06-opportunities-and-solutions/solution-building-blocks-catalog]].
- Cross-referenced with
  [[02-business-architecture/catalogs/business-service-function-catalog]]
  via the Related Function column.
