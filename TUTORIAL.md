# Tutorial: Running an EA Modernization Program with This Library

This is for an organization that wants to use this library as scaffolding
for an actual enterprise architecture modernization effort — not just as a
reference. It lays out a phase-by-phase sequence, what to produce at each
phase, and the pitfalls that derail most first attempts.

For artifact-level mechanics (how to add a file, how to trace a
requirement), see [USAGE.md](USAGE.md) instead. This doc is about
sequencing the program; USAGE.md is about using the pieces.

---

## The methodology at a glance

```
0. Preliminary        — agree principles before documenting anything
1. Vision              — engage stakeholders, set scope
2. Domain Architecture — baseline + target together, one domain at a time
3. Opportunities       — gap analysis, solutions
4. Migration Planning  — sequence gaps into a roadmap
5. Governance          — keep delivery honest to the target
6. Change Management   — handle drift, then loop back to 1
```

This is TOGAF's ADM. The one habit it breaks that most first-timers fall
into: **don't document current-state for every domain, then design
target-state for every domain.** Do current + target *together*, domain by
domain, in the order your vision's drivers say matters most (usually
Business → Data → Application → Technology). Business Architecture's
target state should shape what you need from Data; Data's target state
shapes Application; and so on. Two big global passes disconnects target
design from the vision that's supposed to drive it.

| Phase | Folder | Produces |
|---|---|---|
| 0. Preliminary | `00-preliminary/` | Principles, capability assessment |
| 1. Vision | `01-architecture-vision/` | Vision statement, stakeholder map |
| 2. Domain Architecture | `02-` through `05-` | Catalogs, matrices, diagrams per domain |
| — (continuous) | `10-requirements-management/` | Requirements catalog, traceability matrix |
| 3. Opportunities & Solutions | `06-opportunities-and-solutions/` | Gap analysis, solution building blocks |
| 4. Migration Planning | `07-migration-planning/` | Work packages, roadmap, transition architecture |
| 5. Governance | `08-implementation-governance/` | Compliance assessments, architecture contracts |
| 6. Change Management | `09-architecture-change-management/` | Change requests |
| — (continuous) | `11-risk-and-security/` | Risk register |

---

## Phase 0 — Preliminary: agree principles before documenting anything

**Why first:** without agreed principles, "document the current state" has
no filter. You'll either try to document everything, or every reviewer will
argue from a different unstated assumption about what matters.

**Do:**
- Run a short workshop with leadership to produce 5-8 principles — no more.
  Each needs a statement, a rationale, and a concrete implication (see
  `00-preliminary/architecture-principles-catalog.md` for the pattern:
  statement → why it matters → what it forces you to do differently).
- Do a lightweight capability assessment: list the 5-6 capabilities the
  modernization is really about, rate current vs. target maturity 1-5.
  This becomes your priority list for Phase 2.

**Exit criteria:** principles and capability assessment are sponsor-approved
(`status: approved`).

**Pitfall:** skipping straight to "let's document our systems." You'll
produce a large, unfiltered inventory that nobody can use to make a
decision.

---

## Phase 1 — Vision: engage stakeholders and set scope

**Why here:** the vision's drivers determine which domains and which
artifacts are worth your time in Phase 2. Deciding scope *before* you know
the drivers means guessing.

**Do:**
- Interview or workshop the real stakeholders (executives, the teams who'll
  live with the new architecture, whoever owns the budget) to surface
  drivers and pain points — see the Drivers table pattern in
  `01-architecture-vision/architecture-vision.md`.
- Write a one-paragraph vision statement with a date and a measurable value
  proposition, not just an aspiration.
- Build a stakeholder map (power/interest grid) to decide who gets
  "manage closely" engagement vs. "keep informed."
- Explicitly record constraints (compliance requirements, blackout windows,
  contract end dates) — these become real scheduling constraints in Phase 4,
  not afterthoughts.

**This is also where you decide *how much* of the library to use.** Don't
aim to fill in every artifact type on day one. Match the
`examples/private-wealth-management/` scenario's scope (one catalog, one
matrix, one diagram per domain) for a first pass; grow toward the full
`02-`–`05-` depth in the primary scenario only where a specific decision
later demands it.

**Exit criteria:** vision and stakeholder map approved; scope for Phase 2
agreed (which domains, how deep).

**Pitfall:** treating stakeholder engagement as a single kickoff meeting.
Re-engage at every phase gate — that's what `status: draft → reviewed →
approved` is for on every artifact, not just Phase 1's.

---

## Phase 2 — Domain Architecture: baseline and target, together, one domain at a time

**Do, per domain (Business → Data → Application → Technology, or whatever
order your vision's drivers set):**
1. Build the catalog, matrix, and diagram for **current state**.
2. Immediately build the same three for **target state** — while the
   current-state picture and the vision's drivers are both fresh. Don't
   move to the next domain until both are drafted.
3. Capture any requirement that surfaces along the way in
   `10-requirements-management/requirements-catalog.md` right away. Don't
   wait until "requirements management" feels like its own phase — it runs
   underneath all of Phase 2.

**Timebox the current-state work.** TOGAF calls this "boiling the ocean" —
documenting the as-is exhaustively because it feels like due diligence. Go
only deep enough to see the gaps that matter for *this cycle's* drivers. A
system nobody plans to touch this cycle doesn't need a full catalog entry.

**Exit criteria:** for each in-scope domain, catalog/matrix/diagram are
`reviewed`, and any requirement they surfaced is in the requirements
catalog.

**Pitfall (the big one):** current-state for all four domains, then
target-state for all four domains, as two separate global passes. By the
time you get to target-state Technology Architecture, the Business
Architecture target you designed weeks earlier has drifted out of your
head, and target-state ends up shaped by today's technology constraints
instead of the vision.

---

## Phase 3 — Opportunities & Solutions: gap analysis and solutions

**Do:**
- For each domain, compare baseline vs. target and log the differences in
  `06-opportunities-and-solutions/gap-analysis.md` — see the pattern:
  Architecture Area, Baseline, Target, Gap, Disposition.
- For each gap you're addressing this cycle, name a concrete Solution
  Building Block in `solution-building-blocks-catalog.md` — a real
  product/vendor/build decision, not just "fix this."
- If organizational change (not just system change) is a real risk, add a
  Business Transformation Readiness Assessment (see the pattern in the
  primary scenario) rating factors like sponsorship, funding, and the
  organization's capacity to absorb the change.

**Exit criteria:** every gap has a disposition (address now / later / accept)
and, if "address now," a named solution.

**Pitfall:** logging gaps without a disposition. A gap analysis that's just
a list of problems isn't architecture — it's a complaint log.

---

## Phase 4 — Migration Planning: sequence into a roadmap

**Do:**
- Turn each "address now" gap into a work package in
  `07-migration-planning/implementation-and-migration-plan.md`, with real
  dependencies and dates.
- Respect the constraints you captured in Phase 1 (a cutover-pace cap, a
  no-downtime trading window, a legacy contract end date) — these are what
  actually determine sequencing, not just gap severity.
- If the program spans multiple discrete increments, describe the
  architecture state at the end of each one in a Transition Architecture —
  it prevents "target state" from being the only state anyone can picture.

**Exit criteria:** roadmap approved by the same stakeholders from Phase 1.

**Pitfall:** sequencing purely by gap severity. The highest-severity gap is
often *not* first if it depends on something else, or collides with a
constraint like a seasonal freeze.

---

## Phase 5 — Governance: keep delivery honest to the target

**Do:**
- Before a work package starts significant build, run an Architecture
  Compliance Assessment against it (`08-implementation-governance/`) —
  check it against your Phase 0 principles and technology standards, not
  just "does it work."
- For anything binding (a vendor, a delivery team), use an Architecture
  Contract to make the target explicit and attach acceptance criteria.

**Exit criteria:** no work package proceeds past its design gate without a
compliance assessment on file.

**Pitfall:** writing a beautiful target architecture and never checking
delivery against it. Compliance assessments are the only thing standing
between "the architecture we designed" and "the architecture we actually
got."

---

## Phase 6 — Change Management: handle drift, then loop back

**Do:**
- When delivery hits something the target architecture didn't anticipate
  (a legacy format with no COTS path, a principle that doesn't fit a
  specific case), log an Architecture Change Request
  (`09-architecture-change-management/`) rather than quietly deviating.
  This is normal — it happens on every real program.
- Keep a running Risk Register (`11-risk-and-security/`) throughout the
  whole effort, not just at the end — update it every time a new risk
  surfaces in any phase above.
- When a work package or major milestone lands, treat it as a trigger to
  revisit Phase 1: has the vision changed? Do drivers need updating? This
  is a loop, not a project with a finish line.

**Exit criteria:** none — this is the ongoing operating rhythm once the
program is live.

---

## Anti-patterns

The per-phase pitfalls above are execution mistakes within a phase. Below
are two more layers: failure modes that only show up at the program level
months in, and content-level anti-patterns specific to each architecture
domain — the ones that make a Business, Data, or Application artifact look
complete while quietly being useless.

### Program-level

| Anti-pattern | Symptom | Fix |
|---|---|---|
| **EA as shelf-ware** | Artifacts hit `status: approved` and are never opened again, while the systems they describe keep changing underneath them | Schedule a periodic re-review per artifact. A stale `version` on a live system is itself a finding, not a neutral fact |
| **No real sponsor** | Gap dispositions and roadmap priorities get quietly overridden by whoever complains loudest this week | Name a sponsor in Phase 1 who actually approves the vision and is the standing tie-breaker on scope fights |
| **Completeness for its own sake** | Every artifact type in this library gets filled in, but nobody can say what decision most of them supported | Before creating an artifact, name the decision or stakeholder question it answers. If you can't, don't create it — see [minimum viable loop](#where-to-start-the-minimum-viable-loop) |
| **One-way governance** | Compliance assessments get filed, but change requests never do — delivery quietly diverges from the target instead of logging why | Track change-request volume across the program. Zero change requests over a long program is a red flag, not a clean bill of health |
| **Big-bang cycle** | One Phase 0→6 pass is planned to span a year or more before anything reaches production | Run the minimum viable loop first, ship it, then loop back — iterate in cycles, not one exhaustive pass |
| **Toothless principles** | Principles are phrased so blandly ("we value quality and innovation") that no real decision ever gets traced back to one | Every principle needs a concrete implication. If it wouldn't change a real decision, it isn't a principle — rewrite or drop it |

### Business Architecture

| Anti-pattern | Symptom | Fix |
|---|---|---|
| **Org chart wearing a business-architecture costume** | The Business Service/Function Catalog is just the org chart relabeled — rows are departments, not capabilities or services | Keep function/service (what the business does) and org unit/actor (who does it) as separate catalogs, the way `business-service-function-catalog` and `organization-actor-catalog` are split in this library, and cross-reference them, don't merge them |
| **A service with no accountable owner** | The Business Interaction Matrix shows a service with only "C" (consulted) cells — everyone participates, nobody is accountable | Force an explicit Accountable role using an Actor/Role Matrix (RACI). This is exactly what gap G-01 in the primary scenario is — a service with participants but no owner |
| **Vision with no footprint** | The vision names a goal ("unify customer experience") but no function, org unit, or application in the Business Architecture actually changes because of it | Trace every vision goal through a Business Footprint Diagram to a function → org unit → application. A goal with no footprint isn't architecture yet, it's a slogan |

### Data / Information Architecture

| Anti-pattern | Symptom | Fix |
|---|---|---|
| **Two systems of record for one entity** | The Application/Data Matrix (or, where duplication is application-specific rather than function-specific, the gap analysis and entity-relationship diagram) shows full CRUD ownership for the same entity in more than one application | Treat a second CRUD owner as a gap requiring disposition, never as "shared ownership" — this is precisely gap G-02 (Customer split across Beacon CRM and Coastal Legacy ERP; Household split across AdvisorHub CRM and Foxglove PMS) in both scenarios |
| **Entities named after screens, not the business** | Data Entity Catalog entries are really application table/screen names (e.g. "NovaOrderRecord") rather than business concepts, so the model breaks the moment the application is replaced | Ask whether an entity name would still make sense after the owning application is swapped out. If not, rename it to the business concept, not the system artifact |
| **Classification bolted on after an incident** | A Data Security / classification diagram gets created only after an audit finding or breach, rather than alongside the entity catalog from the start | Classify every entity (Restricted/Confidential/Internal, or your own scheme) the same day it's added to the Data Entity Catalog — see `data-security-diagram.md` for the pattern |
| **No lineage, only snapshots** | Nobody can say where a piece of data originated, how it propagated, or when it's meant to be purged — only current-state entity lists exist | Maintain a Data Dissemination Diagram showing actual flow and lifecycle, not just a static catalog of entities at rest |

### Application Architecture

| Anti-pattern | Symptom | Fix |
|---|---|---|
| **Permanent "dual primary"** | The Application/Function Matrix shows two applications both marked "P" (Primary), or one "P" and one lingering "S" that never gets retired, for the same function — and it's been true for over a year | An unresolved second owner is a gap with a clock on it, not a steady state — give it a disposition and a work package the same way gap G-03 does in both scenarios (Nova Commerce / Helix ERP marked P/P in the primary scenario; Ledgerline / Foxglove PMS marked P/S in the second scenario) |
| **Interface catalog that lags reality** | New integrations get built, but the Interface Catalog and Application Communication/Interaction diagrams aren't updated, so nobody can answer "what actually talks to what" without asking an engineer | Make updating the Interface Catalog and Application Interaction Matrix part of the definition of done for any work package that adds or changes an integration |
| **"Deprecating" with no exit plan** | An application sits at `status: Deprecating` in the Application Portfolio Catalog for years with no work package targeting its retirement | Any application marked Deprecating/Retiring needs a named work package with a date in the migration plan the same quarter it's marked, not "eventually" |

### Technology Architecture

| Anti-pattern | Symptom | Fix |
|---|---|---|
| **Standards nobody enforces** | The Technology Standards Catalog lists "Approved" platforms, but new projects still pick whatever's convenient because nothing checks against it | Every Architecture Compliance Assessment must explicitly check the proposed technology against the Technology Standards Catalog by ID, the way `PRIN-01`/`TS-01`/`TS-02` are checked line by line in this library's compliance assessments |
| **"We're on the cloud" mistaken for resilience** | Nobody has actually documented failover behavior; the assumption is that migrating to AWS/Azure/GCP made disaster recovery automatic | Document the real DR posture in an Environments and Locations Diagram (primary region, DR region, and whether failover is automated or manual) — a warm-standby-only DR region is a gap, not a feature, as the Environments and Locations Diagram and RISK-02's manual-failover entry capture together in both scenarios |
| **Shadow platforms** | Teams provision SaaS/cloud services outside the Technology Standards Catalog, so the Application/Technology Matrix is quietly incomplete | Periodically reconcile the Application/Technology Matrix against actual cloud billing/inventory, not just what teams reported when the catalog was last built |

---

## Keeping it honest: re-walk the traceability matrix

Periodically re-walk
`10-requirements-management/requirements-traceability-matrix.md` end to
end — driver → requirement → gap → solution → work package → verification.
An untraced requirement is an early warning that delivery has drifted from
what stakeholders actually asked for. See [USAGE.md](USAGE.md#2-tracing-a-requirement-end-to-end)
for a worked example of exactly this walk.

---

## Where to start: the minimum viable loop

You don't need every artifact type to run one full cycle. The smallest
complete loop is:

1. Principles catalog (Phase 0)
2. Vision + stakeholder map (Phase 1)
3. One catalog + one matrix for whichever domain your vision says matters
   most (Phase 2)
4. Gap analysis + solution building blocks (Phase 3)
5. Migration plan (Phase 4)
6. Requirements catalog, kept up to date throughout

That's it — that's a real, defensible ADM cycle. Everything else (extra
domains, diagrams, governance artifacts, change requests) gets added when a
specific decision actually needs it. The
`examples/private-wealth-management/` scenario is built at roughly this
scope; the primary Meridian Retail Group scenario at the repository root
shows what it looks like once a program has matured past its first cycle.

---

## Checklist

- [ ] Principles agreed and approved (Phase 0)
- [ ] Vision written, stakeholders mapped, scope for Phase 2 agreed (Phase 1)
- [ ] For each in-scope domain: current *and* target catalog/matrix/diagram
      drafted before moving to the next domain (Phase 2)
- [ ] Requirements captured continuously, not batched at the end
- [ ] Every gap has a disposition and, where addressed, a named solution
      (Phase 3)
- [ ] Roadmap respects real constraints, not just gap severity (Phase 4)
- [ ] No work package passes its design gate without a compliance
      assessment (Phase 5)
- [ ] Deviations logged as change requests, not silently absorbed (Phase 6)
- [ ] Risk register updated continuously, not just at kickoff
- [ ] Traceability matrix re-walked periodically for orphaned requirements
