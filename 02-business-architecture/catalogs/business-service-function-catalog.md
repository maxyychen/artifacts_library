---
id: BUS-CAT-01
title: Business Service/Function Catalog
artifact_type: catalog
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Business Service/Function Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Inventories MRG's business functions and the services each one exposes to
customers or to other parts of the business.

## Entries

| ID | Function | Business Service | Description | Owning Org Unit | Status |
|----|----------|-------------------|--------------|------------------|--------|
| BF-01 | Order Management | Place Order | Capture and confirm a customer order across any channel | Commerce Operations | Active |
| BF-02 | Order Management | Track Order Status | Provide real-time order/shipment status to the customer | Commerce Operations | Active |
| BF-03 | Inventory Management | Check Stock Availability | Return real-time stock levels by SKU and location | Supply Chain | Active |
| BF-04 | Inventory Management | Replenish Stock | Trigger reorder from distribution center or supplier | Supply Chain | Active |
| BF-05 | Customer Management | Maintain Customer Profile | Create/update a single customer profile shared across channels | Marketing | In Transition |
| BF-06 | Customer Management | Manage Loyalty Rewards | Accrue and redeem loyalty points | Marketing | Active |
| BF-07 | Store Operations | Process In-Store Payment | Authorize and capture payment at POS | Store Operations | Active |
| BF-08 | Returns Management | Process Return/Refund | Handle merchandise returns across channels | Commerce Operations | Active |

## Notes

- BF-05 is "In Transition" pending the customer profile consolidation
  described in [[01-architecture-vision/architecture-vision]].
- Cross-referenced with [[02-business-architecture/matrices/business-interaction-matrix]].
- The processes, events, controls, and products realizing these functions
  are detailed in
  [[02-business-architecture/catalogs/process-event-control-product-catalog]].
