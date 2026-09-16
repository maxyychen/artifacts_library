---
id: SBB-CAT-01
title: Solution Building Blocks Catalog
artifact_type: catalog
adm_phase: Opportunities and Solutions
status: approved
owner: Chief Architect
version: 1.0
---

# Solution Building Blocks Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Lists the concrete Solution Building Blocks (SBBs) selected to realize the
Architecture Building Blocks implied by the target architecture, and which
gap each one closes.

## Entries

| ID | SBB Name | Realizes Capability | Vendor/Product | Closes Gap | Status |
|----|----------|----------------------|------------------|------------|--------|
| SBB-01 | Customer 360 Module | Unified Customer Data | Beacon CRM (existing, extended) | G-02 | Selected |
| SBB-02 | Real-Time Order Orchestration Service | Omnichannel Order Management | Helix ERP Order Hub add-on | G-03 | Selected |
| SBB-03 | Cloud-Native WMS | Real-Time Inventory Visibility | New: FlowStock WMS (SaaS) | G-04 | Selected |
| SBB-04 | Multi-Region Automated Failover | Automated Disaster Recovery | AWS Route 53 + native EKS multi-region | G-05 | Evaluating |
| SBB-05 | Legacy Data Migration Adapter | Coastal Legacy ERP retirement | Custom-built (waiver CHG-01) | G-06 | Selected |

## Notes

- SBB-03 (FlowStock WMS) is a new vendor selection, not yet in
  [[04-application-architecture/catalogs/application-portfolio-catalog]];
  add once contract is signed.
- SBB-05 depends on approval of
  [[09-architecture-change-management/architecture-change-request]].
