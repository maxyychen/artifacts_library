---
id: RISK-REG-01
title: Risk Register - Unified Commerce Platform
artifact_type: risk-register
adm_phase: Risk and Security
status: approved
owner: CISO
version: 1.2
---

# Risk Register: Unified Commerce Platform

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Tracks architecture-level risks to the Unified Commerce Platform program.

## Entries

| ID | Risk | Likelihood | Impact | Mitigation | Owner |
|----|------|------------|--------|------------|-------|
| RISK-01 | Customer PII exposed in transit via the temporary Coastal sync adapter | Medium | High | Enforce TLS 1.3 and field-level encryption; time-box adapter lifespan (see CHG-01) | CISO |
| RISK-02 | Manual DR failover misses RTO during a real AWS us-east-1 outage | Medium | High | Automate failover under WP-06 | Technology Architect |
| RISK-03 | Store cutover pace (40/month) slips due to network readiness at older locations | High | Medium | Pre-cutover network audit added to store rollout checklist | PMO |
| RISK-04 | Dual "Primary" ownership of Order Management (Nova Commerce / Helix ERP) causes conflicting order states during transition | Medium | High | Resolve via WP-03 before Phase 2 go-live | Application Architect |
| RISK-05 | Coastal Living Leadership resistance slows data migration cooperation | Low | Medium | Dedicated change-management liaison assigned | PMO |
| RISK-06 | Atlas Support Agent (APP-08) reasoning error or prompt injection causes an unauthorized action (e.g. refund above threshold, incorrect profile disclosure) | Medium | High | Enforce authorization thresholds in [[04-application-architecture/matrices/ai-agent-responsibility-matrix]] at the Planning layer, not in the prompt; sandbox all tool calls per [[04-application-architecture/diagrams/ai-agent-architecture-diagram]]; retain full conversation transcripts for audit | AI Solutions Architect |

## Notes

- RISK-01 and RISK-04 are the highest-priority items and are reviewed
  bi-weekly by the Architecture Review Board alongside
  [[08-implementation-governance/architecture-compliance-assessment]].
- RISK-06 is reviewed as a gating condition before Atlas Support Agent
  (currently "Piloting" in
  [[04-application-architecture/catalogs/application-portfolio-catalog]])
  can move to general availability.
