---
id: PW-TECH-DIA-01
title: Environments and Locations Diagram
artifact_type: diagram
adm_phase: Technology Architecture
status: reviewed
owner: Technology Architect
version: 1.0
---

# Environments and Locations Diagram

*Demo data for Silverline Private Wealth (fictitious company).*

## Purpose

Shows physical/cloud hosting locations and which applications run where.

## Diagram

```mermaid
flowchart TB
  subgraph AWS_US_EAST["AWS us-east-1 (Primary Cloud Region)"]
    Ledgerline[Ledgerline]
    CRM[AdvisorHub CRM]
    Bill[BillRight]
    Comply[ComplyWatch]
    Portal[ClientPortal]
  end

  subgraph AWS_US_WEST["AWS us-west-2 (DR Region)"]
    LedgerlineDR[Ledgerline - standby]
    CRMDR[AdvisorHub CRM - standby]
  end

  subgraph ONPREM["On-Prem Server Room - Boston, MA HQ"]
    Foxglove[Foxglove PMS]
  end

  subgraph CUSTODIANS["External Custodian Networks"]
    Harborstone[Harborstone Custody]
    Falcon[Falcon Trust Co]
  end

  AWS_US_EAST -. async replication .-> AWS_US_WEST
  CUSTODIANS -. nightly batch feed .-> Ledgerline
  Foxglove -. manual export, migration only .-> Ledgerline
```

## Notes

- DR region is warm-standby only; failover is manual, tracked as an accepted
  risk in [[11-risk-and-security/risk-register]].
- The Boston on-prem server room is slated for exit per PW-PRIN-04 in
  [[00-preliminary/architecture-principles-catalog]], once Foxglove PMS
  retires.
