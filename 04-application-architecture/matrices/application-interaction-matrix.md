---
id: APP-MAT-03
title: Application Interaction Matrix
artifact_type: matrix
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.0
---

# Application Interaction Matrix

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Summarizes the interaction style between application pairs (directional:
row = initiator, column = receiver), independent of the individual
interfaces enumerated in
[[04-application-architecture/catalogs/interface-catalog]] and the flow view
in
[[04-application-architecture/diagrams/application-communication-diagram]].

## Matrix

| From \ To | Nova Commerce | StoreLine POS | Helix ERP | Beacon CRM | WMS Classic | InsightPay Gateway | Coastal Legacy ERP |
|---|---|---|---|---|---|---|---|
| **Nova Commerce** | | | S | S | | S | |
| **StoreLine POS** | | | S | S | | S | |
| **Helix ERP** | | | | E | S | | |
| **Beacon CRM** | | | | | | | |
| **WMS Classic** | | | | | | | |
| **InsightPay Gateway** | | | | | | | |
| **Coastal Legacy ERP** | | | B | B | | | |

## Legend

| Symbol | Meaning |
|--------|---------|
| S | Synchronous API call |
| E | Asynchronous event |
| B | Batch file interchange |
| (blank) | No direct interaction |

## Notes

- WMS Classic's only inbound interaction (synchronous stock check from Helix
  ERP) is not real-time-guaranteed, which is the mechanism behind gap G-04 in
  [[06-opportunities-and-solutions/gap-analysis]]. Once SBB-03 replaces it
  with FlowStock WMS, this cell becomes event-driven (E) per IF-05 in
  [[04-application-architecture/catalogs/interface-catalog]].
- Coastal Legacy ERP has exclusively outbound batch interactions and no
  synchronous interfaces, consistent with its planned retirement (APP-06 in
  [[04-application-architecture/catalogs/application-portfolio-catalog]]).
