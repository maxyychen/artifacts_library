---
id: SEC-DIA-01
title: Security Architecture Diagram - Payment & Customer Data Zones
artifact_type: diagram
adm_phase: Risk and Security
status: approved
owner: CISO
version: 1.2
---

# Security Architecture Diagram: Payment & Customer Data Zones

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Shows the trust zones and controls protecting cardholder and customer data
across the commerce platform.

## Diagram

```mermaid
flowchart TB
  subgraph PUBLIC["Public Zone"]
    Customer((Customer Browser/App))
  end

  subgraph DMZ["DMZ - WAF + CDN"]
    WAF[Web Application Firewall]
  end

  subgraph APPZONE["Application Zone - mTLS between services"]
    Nova[Nova Commerce]
    Beacon["Beacon CRM\nPII encrypted at rest"]
    Helix[Helix ERP]
  end

  subgraph PCIZONE["PCI-DSS Scoped Zone - Tokenization Boundary"]
    InsightPay[InsightPay Gateway]
  end

  subgraph IDP["Identity Zone"]
    Okta[Okta SSO/MFA]
  end

  Customer --> WAF --> Nova
  Nova --> Okta
  Nova -- tokenized reference only --> InsightPay
  Nova --> Beacon
  Nova --> Helix
```

## Notes

- No raw cardholder data crosses out of the PCI-DSS Scoped Zone, satisfying
  PRIN-05 in [[00-preliminary/architecture-principles-catalog]].
- RISK-01 in [[11-risk-and-security/risk-register]] concerns a temporary
  exception to this boundary during the Coastal Legacy ERP migration.
