---
id: PW-RISK-REG-01
title: Risk Register - Unified Household Platform
artifact_type: risk-register
adm_phase: Risk and Security
status: approved
owner: CCO
version: 1.1
---

# Risk Register: Unified Household Platform

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Tracks architecture-level risks to the Unified Household Platform program.

## Entries

| ID | Risk | Likelihood | Impact | Mitigation | Owner |
|----|------|------------|--------|------------|-------|
| RISK-01 | Client PII/financial data exposed during the manual Foxglove-to-Ledgerline export/import step | Medium | High | Enforce encryption in transit and at rest; time-box the migration window (see PW-CHG-01) | CTO |
| RISK-02 | Manual DR failover for Ledgerline misses recovery objective during a real outage | Medium | High | Accepted risk pending a future automation phase; reviewed quarterly | Technology Architect |
| RISK-03 | Advisor productivity dips or client dissatisfaction from running Foxglove PMS and Ledgerline in parallel for Birchwood households | Medium | Medium | Dedicated transition support team assigned for the parallel-run period | COO |
| RISK-04 | An SEC examination during the migration window finds a books-and-records gap if WORM retention lapses even briefly | Low | High | WORM retention enabled on the target system before any record is migrated | CCO |
| RISK-05 | The custom cost-basis migration script (PW-CHG-01) contains defects causing incorrect tax-lot reporting | Medium | High | Full parallel-run reconciliation against Foxglove PMS before cutover | Portfolio Management & Trading |

## Notes

- RISK-01 and RISK-05 are the highest-priority items and are reviewed
  bi-weekly by the Architecture Review Board alongside
  [[08-implementation-governance/architecture-compliance-assessment]].
