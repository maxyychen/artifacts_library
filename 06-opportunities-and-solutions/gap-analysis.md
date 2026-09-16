---
id: GAP-01
title: Gap Analysis - Baseline to Target Commerce Architecture
artifact_type: gap-analysis
adm_phase: Opportunities and Solutions
status: approved
owner: Chief Architect
version: 1.0
---

# Gap Analysis: Baseline to Target Commerce Architecture

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Identifies gaps between the baseline and target architecture defined in
[[01-architecture-vision/architecture-vision]], and their disposition.

## Gaps

| ID | Architecture Area | Baseline | Target | Gap | Disposition |
|----|--------------------|----------|--------|-----|--------------|
| G-01 | Business | Customer Service has no direct service ownership | Customer Service co-owns Returns and Order Support | New responsibility assignment | Address in phase 1 |
| G-02 | Data | Customer profile duplicated across Beacon CRM and Coastal Legacy ERP | Single Customer entity, Beacon CRM as system of record | Data consolidation needed | Address in phase 1 |
| G-03 | Application | Nova Commerce and Helix ERP both "Primary" for Order Management | Nova Commerce owns capture, Helix ERP owns fulfillment only | Functional overlap / unclear ownership | Address in phase 2 |
| G-04 | Application | WMS Classic lacks real-time stock sync | Real-time inventory position across all locations | New WMS capability required | Replace with new WMS (phase 2) |
| G-05 | Technology | DR failover for AWS us-east-1 is manual | Automated failover within 15 min RTO | Automation gap | Address in phase 3 |
| G-06 | Technology | Coastal Legacy ERP runs on deprecated Oracle 11g / on-prem | Fully retired, replaced by Helix ERP | Legacy retirement | Retire by 2027 (phase 2) |

## Notes

- Gaps are sequenced into the roadmap in
  [[07-migration-planning/implementation-and-migration-plan]].
- Organizational readiness to absorb this change is assessed in
  [[06-opportunities-and-solutions/business-transformation-readiness-assessment]].
