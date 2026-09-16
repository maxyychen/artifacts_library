---
id: APP-CAT-02
title: Interface Catalog
artifact_type: catalog
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.1
---

# Interface Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Inventories the integration interfaces between applications, referenced by
[[04-application-architecture/diagrams/application-communication-diagram]].

## Entries

| ID | Name | Source | Target | Protocol | Description |
|----|------|--------|--------|----------|--------------|
| IF-01 | Order Create | Nova Commerce | Helix ERP | REST/JSON | Submits a new order for fulfillment |
| IF-02 | Order Create (Store) | StoreLine POS | Helix ERP | REST/JSON | Submits an in-store order for fulfillment |
| IF-03 | Order Fulfilled Event | Helix ERP | Beacon CRM | Kafka event | Notifies CRM to update loyalty accrual |
| IF-04 | Customer Lookup | Nova Commerce | Beacon CRM | REST/JSON | Retrieves customer profile at checkout |
| IF-05 | Stock Check | Helix ERP | FlowStock WMS | REST/JSON | Queries real-time inventory position |
| IF-06 | Payment Authorization | Nova Commerce | InsightPay Gateway | REST/JSON (tokenized) | Authorizes and captures payment |
| IF-07 | Legacy Customer Sync | Coastal Legacy ERP | Beacon CRM | Batch file (nightly) | Temporary migration feed, to be decommissioned |
| IF-08 | Legacy Order/Inventory Sync | Coastal Legacy ERP | Helix ERP | Batch file (nightly) | Temporary feed of inherited order/inventory records, to be decommissioned alongside Coastal Legacy ERP retirement |

## Notes

- IF-07 and IF-08 are the interfaces governed by
  [[09-architecture-change-management/architecture-change-request]] and are
  scheduled for decommission alongside Coastal Legacy ERP retirement.
- A directional summary of interaction styles (sync/event/batch) across all
  application pairs is in
  [[04-application-architecture/matrices/application-interaction-matrix]].
