---
id: PW-GOV-01
title: Architecture Compliance Assessment - WP-02 Foxglove to Ledgerline Migration
artifact_type: compliance-assessment
adm_phase: Implementation Governance
status: approved
owner: Architecture Review Board
version: 1.0
---

# Architecture Compliance Assessment: WP-02 Foxglove to Ledgerline Migration

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Assesses whether the WP-02 project (from
[[07-migration-planning/implementation-and-migration-plan]]) complies with
approved architecture principles and standards before proceeding past
design gate.

## Assessment

| Criteria | Reference | Compliant? | Finding |
|----------|-----------|------------|---------|
| Uses approved cloud platform | PW-TS-01 (AWS) | Yes | Ledgerline already runs on AWS us-east-1 |
| Single system of record for Household | PW-PRIN-02 | Yes | AdvisorHub CRM confirmed as sole system of record post-migration |
| Compliance review completed | PW-PRIN-05 | Yes | CCO sign-off obtained 2026-09-12 |
| Uses approved database standard | PW-TS-02 (PostgreSQL) | Yes | Ledgerline's PostgreSQL 16 instance is in scope, no new DB introduced |
| No new custom-built components without waiver | PW-PRIN-03 | Partial | A custom cost-basis migration script is required for Foxglove PMS; waiver requested |

## Decision

**Conditionally Approved** — proceed to build, contingent on Architecture
Review Board approving the PW-PRIN-03 waiver for the custom cost-basis
migration script by 2026-10-15.

## Notes

- Waiver request logged as a linked architecture change; see
  [[09-architecture-change-management/architecture-change-request]].
