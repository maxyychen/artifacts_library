---
id: APP-DIA-01
title: Application Communication Diagram
artifact_type: diagram
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.0
---

# Application Communication Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows the integration interfaces between MRG's core applications.

## Diagram

```mermaid
flowchart LR
  Nova[Nova Commerce] -- REST: order create --> Helix[Helix ERP]
  StoreLine[StoreLine POS] -- REST: order create --> Helix
  Helix -- Event: order.fulfilled --> Beacon[Beacon CRM]
  Nova -- REST: customer lookup --> Beacon
  StoreLine -- REST: customer lookup --> Beacon
  Helix -- REST: stock check --> WMS[WMS Classic]
  Nova -- REST: payment auth --> InsightPay[InsightPay Gateway]
  StoreLine -- REST: payment auth --> InsightPay
  Coastal[Coastal Legacy ERP] -. Batch file, nightly .-> Helix
```

## Notes

- Dashed edge indicates a legacy batch interface slated for decommission
  alongside Coastal Legacy ERP retirement.
- Corresponds to relationships implied in
  [[04-application-architecture/matrices/application-function-matrix]].
