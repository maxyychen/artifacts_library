---
id: PW-BUS-MAT-01
title: Business Interaction Matrix
artifact_type: matrix
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Business Interaction Matrix

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Shows which organizational units interact with which business services, and
the nature of the interaction (I = Initiates, P = Participates, C =
Consulted).

## Matrix

| | Onboard New Household | Create Financial Plan | Execute Trade | Generate Performance Report | Calculate Advisory Fee | Monitor Trade Surveillance |
|---|---|---|---|---|---|---|
| **Advisory Services** | I | I | C | C | | |
| **Portfolio Management & Trading** | | C | I | P | | C |
| **Client Onboarding & Compliance** | P | | | | | I |
| **Client Reporting & Operations** | C | | | I | I | C |

## Legend

| Symbol | Meaning |
|--------|---------|
| I | Initiates the service |
| P | Participates in fulfilling the service |
| C | Consulted / receives information |

## Notes

- No org unit is shown as sole owner ("I") of Generate Performance Report
  for Birchwood households, since Portfolio Management & Trading still
  participates via the legacy Foxglove PMS — flagged as gap G-03 in
  [[06-opportunities-and-solutions/gap-analysis]].
