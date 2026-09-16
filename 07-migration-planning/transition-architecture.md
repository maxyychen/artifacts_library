---
id: TRANS-ARCH-01
title: Transition Architecture - Unified Commerce Platform
artifact_type: transition-architecture
adm_phase: Migration Planning
status: approved
owner: Chief Architect
version: 1.0
---

# Transition Architecture: Unified Commerce Platform

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Describes the state of the architecture at the end of each roadmap phase in
[[07-migration-planning/implementation-and-migration-plan]], as a stable,
deployable increment between the baseline and the target architecture in
[[01-architecture-vision/architecture-vision]].

## Increments

| Increment | Target Date | Business Architecture | Data Architecture | Application Architecture | Technology Architecture | Gaps Closed |
|-----------|-------------|-------------------------|----------------------|-----------------------------|----------------------------|-------------|
| Baseline | Current | Customer Service has no direct service ownership | Customer duplicated across Beacon CRM / Coastal Legacy ERP | Nova Commerce and Helix ERP both "Primary" for Order Management; WMS Classic lacks real-time sync | DR failover manual; Coastal Legacy ERP on Oracle 11g | — |
| Transition 1 (end of Phase 1) | 2027-02-28 | Customer Service co-owns Returns & Order Support | Beacon CRM is sole system of record for Customer; Coastal sync adapter still active (temporary) | No change | No change | G-01, G-02 |
| Transition 2 (end of Phase 2) | 2027-09-30 | No change | Coastal Legacy ERP retired; sync adapter decommissioned | Nova Commerce owns capture, Helix ERP owns fulfillment only; FlowStock WMS replaces WMS Classic | Oracle 11g retired | G-03, G-04, G-06 |
| Target (end of Phase 3) | 2027-12-15 | No change | No change | No change | Automated multi-region DR failover live | G-05 |

## Notes

- Each transition increment must pass the compliance gate pattern shown in
  [[08-implementation-governance/architecture-compliance-assessment]] before
  its successor work packages start.
- Transition 1's temporary Coastal sync adapter is the subject of
  [[09-architecture-change-management/architecture-change-request]] and
  RISK-01 in [[11-risk-and-security/risk-register]]; it must not persist
  past Transition 2.
