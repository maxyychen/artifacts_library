---
id: BUS-DIA-01
title: Order-to-Fulfillment Process Flow Diagram
artifact_type: diagram
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Order-to-Fulfillment Process Flow Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows the end-to-end flow of a customer order from placement through
fulfillment, across the channels and org units involved.

## Diagram

```mermaid
flowchart TD
  A[Customer places order\nweb, mobile, or in-store] --> B{Stock available\nat nearest location?}
  B -- Yes --> C[Reserve inventory]
  B -- No --> D[Check distribution center stock]
  D --> E{Available at DC?}
  E -- Yes --> C
  E -- No --> F[Backorder & notify customer]
  C --> G[Pick & pack]
  G --> H{Fulfillment channel}
  H -- Ship to home --> I[Hand off to carrier]
  H -- Ship to store / BOPIS --> J[Store associate notifies customer]
  I --> K[Customer receives order]
  J --> K
  K --> L[Order marked complete]
```

## Notes

- "BOPIS" = Buy Online, Pickup In Store.
- Corresponds to services BF-01 through BF-04 in
  [[02-business-architecture/catalogs/business-service-function-catalog]].
