---
id: PW-GAP-01
title: Gap Analysis - Baseline to Target Household Platform Architecture
artifact_type: gap-analysis
adm_phase: Opportunities and Solutions
status: approved
owner: Chief Architect
version: 1.0
---

# Gap Analysis: Baseline to Target Household Platform Architecture

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Identifies gaps between the baseline and target architecture defined in
[[01-architecture-vision/architecture-vision]], and their disposition.

## Gaps

| ID | Architecture Area | Baseline | Target | Gap | Disposition |
|----|--------------------|----------|--------|-----|--------------|
| G-01 | Business | Birchwood households have no assigned Client Reporting & Operations ownership post-acquisition | Full ownership assigned per SPW's standard org model | New responsibility assignment | Address in phase 1 |
| G-02 | Data | Household data duplicated across AdvisorHub CRM and Foxglove PMS for Birchwood households | Single Household entity, AdvisorHub CRM as system of record | Data consolidation needed | Address in phase 1 |
| G-03 | Application | Ledgerline and Foxglove PMS both support Portfolio Management/Reporting for Birchwood households | Ledgerline is sole owner of portfolio accounting and reporting | Functional overlap / unclear ownership | Address in phase 1 |
| G-04 | Data/Application | Custodian reconciliation runs nightly batch, causing a one-day lag in reported values | Same-day (T+0) reconciliation across all custodians | Real-time reconciliation capability required | Address in phase 2 |
| G-05 | Technology | Foxglove PMS runs on deprecated on-prem SQL Server 2014 | Fully retired, replaced by Ledgerline | Legacy retirement | Retire by 2027 (phase 2) |
| G-06 | Business/Application | Trade surveillance in ComplyWatch runs as an overnight batch, so alerts land the next day | Same-day trade surveillance alerting | Automation gap | Address in phase 2 |

## Notes

- Gaps are sequenced into the roadmap in
  [[07-migration-planning/implementation-and-migration-plan]].
