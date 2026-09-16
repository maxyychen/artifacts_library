---
id: APP-MAT-01
title: Application/Function Matrix
artifact_type: matrix
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.2
---

# Application/Function Matrix

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows which applications support which business functions, and the degree of
support (P = Primary system, S = Secondary/partial support).

## Matrix

| | Order Management | Inventory Management | Customer Management | Store Operations |
|---|---|---|---|---|
| **Nova Commerce** | P | S | S | |
| **StoreLine POS** | S | | S | P |
| **Helix ERP** | P | P | | S |
| **Beacon CRM** | | | P | S |
| **WMS Classic** | | S | | |
| **Coastal Legacy ERP** | S | S | | |
| **Atlas Support Agent** | | | S | |

## Legend

| Symbol | Meaning |
|--------|---------|
| P | Primary system of support |
| S | Secondary / partial support |

## Notes

- Two applications (Nova Commerce, Helix ERP) both show "P" for Order
  Management — flagged as functional overlap in
  [[06-opportunities-and-solutions/gap-analysis]].
- WMS Classic is Secondary for Inventory Management pending real-time stock
  sync; it is slated for replacement by FlowStock WMS (SBB-03) per gap G-04
  in [[06-opportunities-and-solutions/gap-analysis]].
- Atlas Support Agent is Secondary for Customer Management: it assists with
  order-support conversations under human oversight but does not own the
  customer record (Beacon CRM remains Primary). See
  [[04-application-architecture/matrices/ai-agent-responsibility-matrix]] for
  the action-level breakdown.
