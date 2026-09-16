---
id: PW-CHG-01
title: Architecture Change Request - Custom Cost-Basis Migration Adapter Waiver (PW-PRIN-03)
artifact_type: change-request
adm_phase: Architecture Change Management
status: draft
owner: Application Architect
version: 0.1
---

# Architecture Change Request: Custom Cost-Basis Migration Adapter Waiver

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Requests a waiver against PW-PRIN-03 (Buy Before Build) to build a custom
cost-basis migration adapter, as flagged in
[[08-implementation-governance/architecture-compliance-assessment]].

## Request Detail

| Field | Value |
|-------|-------|
| Requestor | Application Architect |
| Date Submitted | 2026-09-16 |
| Related Work Package | WP-02 |
| Principle Affected | PW-PRIN-03 - Buy Before Build |
| Description | Foxglove PMS exports tax lot and cost-basis history in a proprietary flat-file format that Ledgerline's standard import connectors do not support. A custom adapter is needed to migrate historical cost-basis records without loss of tax-lot detail. |
| Business Impact if Denied | WP-02 delayed by an estimated 3 months pending a commercial alternative, pushing Phase 1 completion past the Q1 2027 target |
| Proposed Mitigation | Adapter is scoped as one-time and migration-only, decommissioned immediately after the Foxglove PMS cutover under WP-05 |

## Impact Analysis

| Area | Impact |
|------|--------|
| Data Architecture | No new entity introduced; adapter maps existing Holding/Transaction fields only |
| Technology Architecture | Adapter deployed as a containerized job on the existing AWS EKS cluster (PW-TS-03), no new platform |
| Compliance | Adapter output must reconcile 1:1 with Foxglove PMS records before cutover, reviewed by CCO |
| Cost | Estimated 5 person-weeks of development effort |

## Decision

*Pending Architecture Review Board vote, due 2026-10-15.*

## Notes

- If approved, update
  [[08-implementation-governance/architecture-compliance-assessment]] status
  from "Conditionally Approved" to "Approved."
