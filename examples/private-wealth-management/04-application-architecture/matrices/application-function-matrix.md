---
id: PW-APP-MAT-01
title: Application/Function Matrix
artifact_type: matrix
adm_phase: Application Architecture
status: reviewed
owner: Application Architect
version: 1.0
---

# Application/Function Matrix

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Shows which applications support which business functions, and the degree
of support (P = Primary system, S = Secondary/partial support).

## Matrix

| | Client Onboarding | Financial Planning | Portfolio Management | Reporting & Billing | Compliance |
|---|---|---|---|---|---|
| **Ledgerline** | S | | P | P | S |
| **AdvisorHub CRM** | P | S | | | |
| **PlanForward** | | P | | | |
| **BillRight** | | | | P | |
| **ComplyWatch** | S | | S | | P |
| **ClientPortal** | | S | | S | |
| **Foxglove PMS** | | | S | S | |

## Legend

| Symbol | Meaning |
|--------|---------|
| P | Primary system of support |
| S | Secondary / partial support |

## Notes

- Ledgerline and Foxglove PMS both show support for Portfolio Management and
  Reporting & Billing for Birchwood households — flagged as functional
  overlap in [[06-opportunities-and-solutions/gap-analysis]] (gap G-03).
