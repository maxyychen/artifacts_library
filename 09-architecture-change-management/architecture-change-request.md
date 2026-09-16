---
id: CHG-01
title: Architecture Change Request - Custom Sync Adapter Waiver (PRIN-03)
artifact_type: change-request
adm_phase: Architecture Change Management
status: draft
owner: Application Architect
version: 0.1
---

# Architecture Change Request: Custom Sync Adapter Waiver

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Requests a waiver against PRIN-03 (Buy Before Build) to build a custom sync
adapter, as flagged in
[[08-implementation-governance/architecture-compliance-assessment]].

## Request Detail

| Field | Value |
|-------|-------|
| Requestor | Application Architect |
| Date Submitted | 2026-09-16 |
| Related Work Package | WP-02 |
| Principle Affected | PRIN-03 - Buy Before Build |
| Description | Coastal Legacy ERP exposes no standard API; no COTS connector exists for its proprietary flat-file export. A custom adapter is needed to sync customer records into Beacon CRM during the transition window. |
| Business Impact if Denied | WP-02 delayed by an estimated 3 months pending a commercial alternative, pushing Phase 1 completion past the Q1 2027 target |
| Proposed Mitigation | Adapter is scoped as temporary, decommissioned automatically when Coastal Legacy ERP retires under WP-05 |

## Impact Analysis

| Area | Impact |
|------|--------|
| Data Architecture | No new entity introduced; adapter maps existing Customer fields only |
| Technology Architecture | Adapter deployed as a containerized job on existing AWS EKS cluster (TS-04), no new platform |
| Security | Adapter handles PII in transit; requires encryption in transit and at rest, reviewed by CISO |
| Cost | Estimated 6 person-weeks of development effort |

## Decision

*Pending Architecture Review Board vote, due 2026-10-15.*

## Notes

- If approved, update
  [[08-implementation-governance/architecture-compliance-assessment]] status
  from "Conditionally Approved" to "Approved."
