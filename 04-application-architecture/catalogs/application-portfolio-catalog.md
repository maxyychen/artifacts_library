---
id: APP-CAT-01
title: Application Portfolio Catalog
artifact_type: catalog
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.1
---

# Application Portfolio Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Inventories applications in use across MRG, their vendor, and lifecycle
status.

## Entries

| ID | Name | Description | Owner | Status |
|----|------|--------------|-------|--------|
| APP-01 | Nova Commerce | E-commerce storefront and cart (SaaS, VendorCo) | Commerce Operations | Active |
| APP-02 | StoreLine POS | In-store point-of-sale system | Store Operations | Active |
| APP-03 | Helix ERP | Order, finance, and general ledger backbone | Finance | Active |
| APP-04 | Beacon CRM | Customer profile and loyalty engine | Marketing | Active |
| APP-05 | WMS Classic | Warehouse management for distribution centers | Supply Chain | Deprecating |
| APP-06 | Coastal Legacy ERP | Order/inventory system inherited from Coastal Living acquisition | Supply Chain | Retiring (2027) |
| APP-07 | InsightPay | Payment gateway and PCI tokenization | Finance | Active |
| APP-08 | Atlas Support Agent | LLM-based AI agent handling customer order-support conversations, with tool access to CRM/ERP/payment systems | Customer Service Ops | Piloting |

## Notes

- APP-06 retirement is tracked in
  [[07-migration-planning/implementation-and-migration-plan]].
- APP-05 is being replaced as part of the same program; see gap G-04 in
  [[06-opportunities-and-solutions/gap-analysis]].
- APP-08 is a pilot AI agent component. Its internal architecture is detailed
  in [[04-application-architecture/diagrams/ai-agent-architecture-diagram]]
  and human/agent responsibility boundaries in
  [[04-application-architecture/matrices/ai-agent-responsibility-matrix]].
