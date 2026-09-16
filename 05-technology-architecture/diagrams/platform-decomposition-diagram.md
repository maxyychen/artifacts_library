---
id: TECH-DIA-02
title: Platform Decomposition Diagram
artifact_type: diagram
adm_phase: Technology Architecture
status: reviewed
owner: Technology Architect
version: 1.0
---

# Platform Decomposition Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Breaks down the technology platform supporting Nova Commerce into its
constituent layers.

## Diagram

```mermaid
flowchart TB
  subgraph PRESENTATION["Presentation Layer"]
    CDN[CloudFront CDN]
    WAF[Web Application Firewall]
  end

  subgraph COMPUTE["Compute Layer"]
    EKS[EKS Cluster - Nova Commerce services]
  end

  subgraph MIDDLEWARE["Middleware Layer"]
    Kafka[Kafka - event streaming]
    APIGW[API Gateway]
  end

  subgraph DATA["Data Layer"]
    PG[(PostgreSQL 16)]
    Redis[(Redis - session cache)]
  end

  CDN --> WAF --> APIGW --> EKS
  EKS --> Kafka
  EKS --> PG
  EKS --> Redis
```

## Notes

- All layers run on TS-01/TS-02/TS-03/TS-04 standards from
  [[05-technology-architecture/catalogs/technology-standards-catalog]].
