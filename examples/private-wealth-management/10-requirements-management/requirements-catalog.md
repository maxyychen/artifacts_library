---
id: PW-REQ-CAT-01
title: Requirements Catalog - Unified Household Platform
artifact_type: catalog
adm_phase: Requirements Management
status: approved
owner: Chief Architect
version: 1.1
---

# Requirements Catalog: Unified Household Platform

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Central repository of functional and non-functional requirements feeding
every ADM phase, per TOGAF's Requirements Management discipline. Requirements
here trace back to [[01-architecture-vision/architecture-vision]] and
forward into gaps and work packages.

## Entries

| ID | Requirement | Type | Priority | Source | Status |
|----|-------------|------|----------|--------|--------|
| REQ-01 | Household aggregated view must reconcile with custodian data within 1 business day (T+1) | Non-Functional | Must | Architecture Vision | Approved |
| REQ-02 | A household's holdings and financial plan must be identical whether viewed by an advisor in AdvisorHub CRM or by the client in ClientPortal | Functional | Must | Architecture Vision | Approved |
| REQ-03 | SEC 17a-4 books-and-records (WORM) retention must be maintained without lapse throughout migration | Non-Functional | Must | CCO | Approved |
| REQ-04 | Advisor-facing systems must have zero downtime during trading hours (9:30am-4:00pm ET) | Non-Functional | Must | COO | Approved |
| REQ-05 | Advisory fee calculations must match the household's contracted fee schedule with zero calculation errors | Functional | Must | CFO | Approved |
| REQ-06 | Trade surveillance alerts must be generated within the same business day of the trade | Non-Functional | Should | CCO | Draft |
| REQ-07 | New household onboarding (KYC/AML) must complete within 5 business days | Functional | Should | Advisory Services | Draft |

## Notes

- REQ-01 (custodian reconciliation timeliness) directly informed gap G-04 in
  [[06-opportunities-and-solutions/gap-analysis]]; REQ-02 (identical
  household view) directly informed gaps G-02 and G-03.
- REQ-06 and REQ-07 are not yet mapped to a work package; flagged for
  scoping in the next planning cycle.
