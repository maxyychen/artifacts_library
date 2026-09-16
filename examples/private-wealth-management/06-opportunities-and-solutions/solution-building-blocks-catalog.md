---
id: PW-SBB-CAT-01
title: Solution Building Blocks Catalog
artifact_type: catalog
adm_phase: Opportunities and Solutions
status: approved
owner: Chief Architect
version: 1.0
---

# Solution Building Blocks Catalog

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Lists the concrete Solution Building Blocks (SBBs) selected to realize the
Architecture Building Blocks implied by the target architecture, and which
gap each one closes.

## Entries

| ID | SBB Name | Realizes Capability | Vendor/Product | Closes Gap | Status |
|----|----------|----------------------|------------------|------------|--------|
| PW-SBB-01 | Household Consolidation Module | Unified Household Data | AdvisorHub CRM (existing, extended with a Birchwood migration toolkit) | G-02 | Selected |
| PW-SBB-02 | Portfolio Migration & Reconciliation Service | Single Portfolio Accounting System of Record | Ledgerline Data Migration Add-on | G-03 | Selected |
| PW-SBB-03 | Real-Time Custodian Reconciliation Engine | Same-Day Custodian Reconciliation | New: Ledgerline "RecondaSync" module (SaaS add-on) | G-04 | Evaluating |
| PW-SBB-04 | Automated Trade Surveillance Alerts | Real-Time Compliance Monitoring | ComplyWatch AI Alerts add-on | G-06 | Selected |
| PW-SBB-05 | Legacy Cost-Basis Migration Adapter | Foxglove PMS retirement | Custom-built (waiver PW-CHG-01) | G-05 | Selected |

## Notes

- PW-SBB-03 (RecondaSync) is a new module purchase, not yet in
  [[04-application-architecture/catalogs/application-portfolio-catalog]];
  add once contract is signed.
- PW-SBB-05 depends on approval of
  [[09-architecture-change-management/architecture-change-request]].
