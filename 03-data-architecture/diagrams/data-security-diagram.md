---
id: DATA-DIA-03
title: Data Security Diagram
artifact_type: diagram
adm_phase: Data Architecture
status: reviewed
owner: Data Architect
version: 1.0
---

# Data Security Diagram

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows the classification and protection requirement for each core data
entity in [[03-data-architecture/catalogs/data-entity-catalog]], distinct
from the network trust-zone view in
[[11-risk-and-security/security-architecture-diagram]].

## Diagram

```mermaid
flowchart TB
  subgraph RESTRICTED["Restricted - PCI cardholder data"]
    PT[Payment Transaction\ntokenized only, never stored in plaintext]
  end

  subgraph CONFIDENTIAL["Confidential - PII, encrypted at rest + in transit"]
    CUST[Customer]
    LOY[Loyalty Account]
  end

  subgraph INTERNAL["Internal - standard access controls"]
    ORD[Order]
    PROD[Product]
    INV[Inventory Position]
    LOC[Location]
  end

  CUST -- 1:N --> ORD
  ORD -- 1:N --> PT
  CUST -- 1:1 --> LOY
  ORD -- N:M --> PROD
  INV -- N:1 --> LOC
  INV -- N:1 --> PROD
```

## Notes

- Payment Transaction is tokenized at capture by InsightPay Gateway per
  PRIN-05 in [[00-preliminary/architecture-principles-catalog]]; the
  Restricted zone here is a data-classification scope, narrower than the
  PCI-DSS Scoped Zone network boundary in
  [[11-risk-and-security/security-architecture-diagram]].
- Customer and Loyalty Account classification as Confidential is the basis
  for the encryption requirement called out against RISK-01 in
  [[11-risk-and-security/risk-register]] during the Coastal Legacy ERP sync.
