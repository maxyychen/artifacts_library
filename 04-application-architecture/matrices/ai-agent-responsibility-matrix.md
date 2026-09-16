---
id: APP-MAT-04
title: AI Agent Responsibility Matrix - Atlas Support Agent
artifact_type: matrix
adm_phase: Application Architecture
status: draft
owner: AI Solutions Architect
version: 0.1
traces_to: []
---

# AI Agent Responsibility Matrix: Atlas Support Agent

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Assigns RACI-style responsibility between Atlas Support Agent (APP-08) and
human roles for each customer-support action it can take, so authorization
thresholds are explicit rather than implicit in the agent's prompt or code.
Referenced by
[[04-application-architecture/diagrams/ai-agent-architecture-diagram]] (the
Planning layer enforces these thresholds) and by
[[04-application-architecture/catalogs/interface-catalog]] (IF-11's
threshold gate).

## Matrix

| | Atlas Support Agent | CS Supervisor | Compliance |
|---|---|---|---|
| **Answer order-status FAQ** | R, A | I | |
| **Look up customer profile (read-only)** | R, A | I | |
| **Issue refund < $50** | R, A | I | |
| **Issue refund >= $50** | R | A | I |
| **Update customer profile (write)** | | R, A | |
| **Escalate complaint / dispute** | R | A | C |
| **Retain conversation transcript** | R | | A |

## Legend

| Symbol | Meaning |
|--------|---------|
| R | Responsible — performs the action |
| A | Accountable — approval required / owns the outcome |
| C | Consulted |
| I | Informed |

## Notes

- Atlas is never sole "A" above the $50 refund threshold or for any
  customer-record write — those remain human-accountable, matching the
  human oversight boundary in
  [[04-application-architecture/diagrams/ai-agent-architecture-diagram]].
- Compliance is Accountable for transcript retention because conversation
  logs are the audit trail for RISK-06 in
  [[11-risk-and-security/risk-register]].
- This matrix is the authorization source of truth; any change to
  thresholds here must be reflected in the agent's Planning-layer policy
  config before deployment.