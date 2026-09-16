---
id: PW-TECH-CAT-01
title: Technology Standards Catalog
artifact_type: catalog
adm_phase: Technology Architecture
status: reviewed
owner: Technology Architect
version: 1.1
---

# Technology Standards Catalog

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Inventories approved technology standards and products by category.

## Entries

| ID | Name | Description | Owner | Status |
|----|------|--------------|-------|--------|
| PW-TS-01 | AWS (primary cloud) | Approved public cloud provider for all new workloads | Technology Architect | Approved |
| PW-TS-02 | PostgreSQL 16 | Standard relational database for new services | Technology Architect | Approved |
| PW-TS-03 | Kubernetes (EKS) | Standard container orchestration platform | Technology Architect | Approved |
| PW-TS-04 | Amazon S3 Object Lock (WORM) | Required storage standard for SEC 17a-4 books-and-records retention | Technology Architect | Approved |
| PW-TS-05 | Microsoft SQL Server 2014 | Legacy database underlying Foxglove PMS | Technology Architect | Deprecated |
| PW-TS-06 | Okta | Standard identity provider (SSO/MFA) | CCO | Approved |
| PW-TS-07 | On-Prem Windows Server | Legacy on-prem server room hosting Foxglove PMS | Technology Architect | Deprecated |

## Notes

- PW-TS-05 is deprecated in favor of PW-TS-02; no new development permitted
  against it. Retirement tied to PW-APP-07 in
  [[04-application-architecture/catalogs/application-portfolio-catalog]].
- PW-TS-07 is deprecated per PW-PRIN-04 (Cloud First, Recordkeeping Aware) in
  [[00-preliminary/architecture-principles-catalog]]; retirement tied to the
  same PW-APP-07 exit as PW-TS-05.
