---
id: APP-CAT-02
title: Interface Catalog
artifact_type: catalog
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.2
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
| IF-09 | Order Status Query (Agent Tool Call) | Atlas Support Agent | Helix ERP | REST/JSON (read-only, sandboxed) | Agent tool call to retrieve order status while assisting a customer |
| IF-10 | Customer Lookup (Agent Tool Call) | Atlas Support Agent | Beacon CRM | REST/JSON (read-only, sandboxed) | Agent tool call to retrieve customer profile and loyalty status |
| IF-11 | Refund Issuance (Agent Tool Call) | Atlas Support Agent | InsightPay Gateway | REST/JSON (tokenized, threshold-gated) | Agent-initiated refund; auto-approved under $50 per APP-MAT-04, else routed to human approval |

## Notes

- IF-07 and IF-08 are the interfaces governed by
  [[09-architecture-change-management/architecture-change-request]] and are
  scheduled for decommission alongside Coastal Legacy ERP retirement.
- IF-09 through IF-11 are Atlas Support Agent tool calls, not human-initiated
  interfaces; each is sandboxed to read-only or threshold-gated write access.
  See [[04-application-architecture/diagrams/ai-agent-architecture-diagram]]
  for the layered agent architecture and
  [[04-application-architecture/matrices/ai-agent-responsibility-matrix]] for
  the human/agent authorization boundary on IF-11.
- A directional summary of interaction styles (sync/event/batch) across all
  application pairs is in
  [[04-application-architecture/matrices/application-interaction-matrix]].
