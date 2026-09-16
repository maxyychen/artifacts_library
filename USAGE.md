# How to Use This Library

Two things people actually do with this library: **add a new artifact**, and
**trace a requirement through to delivery**. This doc walks through both
with real examples from the repo, plus a cheat sheet at the end.

If you just want to know what folder holds what, see [README.md](README.md)
instead — this doc is about workflow, not structure.

---

## 1. Adding a new artifact

Say a Technology Architect needs to document a new Network Diagram that
doesn't exist yet. Here's the flow:

1. **Pick the template.** Every artifact is one of three shapes — catalog,
   matrix, or diagram. Copy the matching file from
   [`_templates/`](_templates/).
2. **Drop it in the right ADM-phase folder.** A diagram in the Technology
   Architecture phase goes in `05-technology-architecture/diagrams/`.
3. **Assign an ID.** Follow the domain prefix already in use in that folder
   (e.g. `TECH-DIA-03` — see the [ID prefix table](#id-prefixes) below).
   Check `INDEX.md` first so you don't collide with an existing ID.
4. **Fill in the frontmatter** — `id`, `title`, `artifact_type`,
   `adm_phase`, `status: draft`, `owner`, `version: 0.1`. Leave
   `traces_to: []` empty unless this artifact directly satisfies a specific
   requirement ID.
5. **Write the content.** Purpose (1-2 sentences), the actual
   catalog/matrix/diagram, then a Notes section. In Notes, cross-link
   related artifacts with `[[path/without/extension]]` — e.g.
   `[[06-opportunities-and-solutions/gap-analysis]]`. This is what makes the
   library navigable instead of just a pile of files.
6. **Register it in `INDEX.md`.** One row, same columns as the others.
7. **Move `status` forward as it matures** — `draft` → `reviewed` →
   `approved` — and bump `version` when the content changes materially.

That's the whole loop. Nothing here is automated yet (see the open item on
an index-generator/link-validator script), so steps 3 and 6 are on you to
get right by hand for now.

---

## 2. Tracing a requirement end to end

This is the exercise that catches orphaned work — a requirement nobody is
actually building toward. Walk it using
[`10-requirements-management/requirements-traceability-matrix.md`](10-requirements-management/requirements-traceability-matrix.md)
in the Meridian Retail Group scenario:

```
REQ-01 "Inventory position visible within 5s"
  ← driven by:     Inventory inaccuracy (a driver in architecture-vision.md)
  → gap:           G-04 (WMS lacks real-time sync)
  → solution:      SBB-03 (Cloud-Native WMS)
  → work package:  WP-04 (Select and deploy new WMS)
  → verified by:   (not yet — WMS isn't deployed)
```

Every requirement in the catalog should resolve to a chain like this. When
one doesn't — like **REQ-06** ("3,000 concurrent checkout transactions"),
which the matrix marks **Untraced** because no gap, SBB, or work package
claims it — that's a real finding, not a formatting gap. It means either a
work package is missing, or the requirement needs to be re-scoped or
dropped. Re-run this walk whenever the gap analysis or migration plan
changes, since new gaps/work packages can silently leave old requirements
behind.

---

## 3. Learning by comparing the two scenarios

The fastest way to see how a template *adapts* to a different industry is
to open the same artifact side by side in both scenarios:

| Look at... | Meridian Retail Group (root) | Silverline Private Wealth (`examples/`) |
|---|---|---|
| Vision | `01-architecture-vision/architecture-vision.md` | `examples/private-wealth-management/01-architecture-vision/architecture-vision.md` |
| Data entities | `03-data-architecture/catalogs/data-entity-catalog.md` | `examples/private-wealth-management/03-data-architecture/catalogs/data-entity-catalog.md` |
| Gap analysis | `06-opportunities-and-solutions/gap-analysis.md` | `examples/private-wealth-management/06-opportunities-and-solutions/gap-analysis.md` |

Same table structure, same frontmatter fields, same `[[cross-link]]`
convention — completely different business. That's the point: the
templates carry the method, not the content.

The two scenarios differ in *depth*, not *convention* — Meridian Retail
Group has extra catalogs/diagrams per domain where Silverline keeps to one
of each. If you're starting a third scenario, the Silverline scope (one
catalog + one matrix + one diagram per domain; one artifact each for
Migration Planning, Implementation Governance, Change Management,
Requirements Management, and Risk & Security; two apiece for Preliminary,
Vision, and Opportunities & Solutions) is the leaner template to copy.

---

## Cheat sheet

### ID prefixes

| Domain | Prefix | Example |
|---|---|---|
| Preliminary | `PRIN-`, `CAP-` | `PRIN-CAT-01` |
| Architecture Vision | `VISION-` | `VISION-01` |
| Business Architecture | `BUS-` | `BUS-CAT-01` |
| Data Architecture | `DATA-` | `DATA-CAT-01` |
| Application Architecture | `APP-` | `APP-CAT-01` |
| Technology Architecture | `TECH-` | `TECH-CAT-01` |
| Opportunities & Solutions | `GAP-`, `SBB-` | `GAP-01` |
| Migration Planning | `MIG-`, `TRANS-ARCH-` | `MIG-01` |
| Implementation Governance | `GOV-` | `GOV-01` |
| Change Management | `CHG-` | `CHG-01` |
| Requirements | `REQ-` | `REQ-01` |
| Risk & Security | `RISK-` | `RISK-REG-01` |

A second scenario just adds its own short prefix on top (Silverline uses
`PW-`, e.g. `PW-BUS-CAT-01`) so IDs stay visually distinct even though
they live in separate folders and never actually collide.

### Frontmatter fields

| Field | Required? | Notes |
|---|---|---|
| `id` | Yes | Unique across the whole repo (including `examples/`) |
| `title` | Yes | |
| `artifact_type` | Yes | `catalog` \| `matrix` \| `diagram` \| a specific type like `gap-analysis` |
| `adm_phase` | Yes | Human-readable phase name, e.g. `Business Architecture` |
| `status` | Yes | `draft` → `reviewed` → `approved` (→ `deprecated`) |
| `owner` | Yes | A role, not a person's name |
| `version` | Yes | Start at `0.1`, bump on material change |
| `traces_to` | No | Array of requirement/artifact IDs this one satisfies |

### Diagram rule

Mermaid only, fenced with ` ```mermaid `. No PNG/JPG/SVG/Visio exports —
if a diagram type genuinely can't be expressed in Mermaid, use PlantUML
text syntax instead. Still plain text either way.
