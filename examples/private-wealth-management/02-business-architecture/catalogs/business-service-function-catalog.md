---
id: PW-BUS-CAT-01
title: Business Service/Function Catalog
artifact_type: catalog
adm_phase: Business Architecture
status: reviewed
owner: Business Architect
version: 1.0
---

# Business Service/Function Catalog

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Inventories SPW's business functions and the services each one exposes to
clients or to other parts of the firm.

## Entries

| ID | Function | Business Service | Description | Owning Org Unit | Status |
|----|----------|-------------------|--------------|------------------|--------|
| PW-BF-01 | Client Onboarding | Onboard New Household | Capture KYC/AML and open accounts for a new household | Client Onboarding & Compliance | Active |
| PW-BF-02 | Financial Planning | Create Financial Plan | Build a goals-based financial plan for a household | Advisory Services | Active |
| PW-BF-03 | Portfolio Management | Manage Model Portfolio | Construct and rebalance model portfolios | Portfolio Management & Trading | Active |
| PW-BF-04 | Portfolio Management | Execute Trade | Place and confirm trades across custodians | Portfolio Management & Trading | Active |
| PW-BF-05 | Reporting & Billing | Generate Performance Report | Produce consolidated household performance reporting | Client Reporting & Operations | In Transition |
| PW-BF-06 | Reporting & Billing | Calculate Advisory Fee | Compute and invoice advisory fees per household fee schedule | Client Reporting & Operations | Active |
| PW-BF-07 | Compliance | Monitor Trade Surveillance | Screen trades for suitability and conflicts of interest | Client Onboarding & Compliance | Active |
| PW-BF-08 | Client Servicing | Respond to Client Inquiry | Handle inbound client service and reporting requests | Advisory Services | Active |

## Notes

- PW-BF-05 is "In Transition" pending the household consolidation described
  in [[01-architecture-vision/architecture-vision]].
- Cross-referenced with
  [[02-business-architecture/matrices/business-interaction-matrix]].
