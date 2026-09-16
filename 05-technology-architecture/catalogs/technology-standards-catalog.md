---
id: TECH-CAT-01
title: Technology Standards Catalog
artifact_type: catalog
adm_phase: Technology Architecture
status: reviewed
owner: Technology Architect
version: 1.1
---

# Technology Standards Catalog

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Inventories approved technology standards and products by category.

## Entries

| ID | Name | Description | Owner | Status |
|----|------|--------------|-------|--------|
| TS-01 | AWS (primary cloud) | Approved public cloud provider for all new workloads | Technology Architect | Approved |
| TS-02 | PostgreSQL 16 | Standard relational database for new services | Technology Architect | Approved |
| TS-03 | Kafka | Standard event streaming backbone | Technology Architect | Approved |
| TS-04 | Kubernetes (EKS) | Standard container orchestration platform | Technology Architect | Approved |
| TS-05 | Oracle Database 11g | Legacy database underlying Coastal Legacy ERP | Technology Architect | Deprecated |
| TS-06 | Okta | Standard identity provider (SSO/MFA) | CISO | Approved |
| TS-07 | On-Prem VMware | Legacy on-prem virtualization platform underlying Coastal Legacy ERP | Technology Architect | Deprecated |

## Notes

- TS-05 is deprecated in favor of TS-02; no new development permitted against
  it. Retirement tied to APP-06 in
  [[04-application-architecture/catalogs/application-portfolio-catalog]].
- TS-07 is deprecated per PRIN-04 (Cloud First) in
  [[00-preliminary/architecture-principles-catalog]]; retirement tied to the
  same APP-06 exit as TS-05.
