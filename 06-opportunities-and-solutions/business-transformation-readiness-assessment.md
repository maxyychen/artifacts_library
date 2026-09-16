---
id: BTRA-01
title: Business Transformation Readiness Assessment - Unified Commerce Platform
artifact_type: readiness-assessment
adm_phase: Opportunities and Solutions
status: approved
owner: Chief Architect
version: 1.0
---

# Business Transformation Readiness Assessment: Unified Commerce Platform

*Demo data for Meridian Retail Group (fictitious company).*

## Purpose

Assesses MRG's organizational readiness to absorb the change implied by the
target architecture in [[01-architecture-vision/architecture-vision]], per
TOGAF Phase E guidance, ahead of finalizing the roadmap in
[[07-migration-planning/implementation-and-migration-plan]].

## Assessment

| Readiness Factor | Current (1-5) | Target (1-5) | Risk if Unaddressed | Mitigating Action | Owner |
|-------------------|----------------|----------------|----------------------|---------------------|-------|
| Vision & Strategic Alignment | 4 | 5 | Store-level teams haven't seen the vision translated into day-to-day impact | Roadshow + FAQ before Phase 1 cutover | CMO |
| Sponsorship & Leadership | 5 | 5 | None — COO and CMO are visible, engaged sponsors | n/a | Chief Architect |
| Desire, Willingness, and Consensus | 3 | 4 | Coastal Living leadership resistance to losing their legacy ERP | Dedicated change-management liaison (RISK-05 mitigation) | PMO |
| Business Case & Funding | 4 | 4 | Funded through Q4 2027; payback period tracked | Quarterly funding review | CFO |
| Governance Capability | 4 | 4 | Architecture Review Board and compliance gates already operating | n/a | Architecture Review Board |
| IT Capacity to Execute | 3 | 4 | Engineering teams concurrently support BAU plus WP-02, WP-03, WP-04 | Backfill hiring for Marketing Engineering and Supply Chain Engineering | PMO |
| Enterprise Capacity to Absorb Change | 2 | 4 | Store Associates face new POS behavior; 40 stores/month pace leaves little training slack | Phased store-readiness checklist + train-the-trainer program per cutover wave | COO |
| Skills to Sustain Post-Go-Live | 3 | 4 | No in-house FlowStock WMS support skillset yet | Managed-service contract through year 1, transition in-house by Phase 3 | Supply Chain |

## Overall Readiness

**Ready to proceed to Phase 1.** The largest readiness gap is Enterprise
Capacity to Absorb Change (store associate training bandwidth) — this is
already factored into the 40 stores/month cutover cap reflected in the
roadmap, not a reason to delay.

## Notes

- Ties to RISK-03 (store cutover pace) and RISK-05 (Coastal Living
  resistance) in [[11-risk-and-security/risk-register]].
- The lowest-rated factor is the basis for the 40 stores/month constraint in
  [[01-architecture-vision/architecture-vision]] and REQ-04 in
  [[10-requirements-management/requirements-catalog]].
