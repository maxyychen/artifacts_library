# TOGAF Artifact Library

A text-only library of TOGAF (The Open Group Architecture Framework) artifacts.
Every artifact is Markdown (+ YAML frontmatter for metadata); diagrams are
[Mermaid](https://mermaid.js.org/) code blocks, not binary images, so
everything stays plain-text, diffable, and greppable.

New here? See [USAGE.md](USAGE.md) for a walkthrough of adding an artifact
and tracing a requirement end to end, or
[TUTORIAL.md](TUTORIAL.md) for how to run an actual EA modernization
program phase by phase using this library.

## Structure

Folders follow the TOGAF ADM phases, with the three phases that share the
Catalog / Matrix / Diagram content-metamodel split into subfolders:

```
00-preliminary/                    Principles, frameworks, tailoring decisions
01-architecture-vision/            Vision, stakeholder map, value chain, drivers/goals
02-business-architecture/
  catalogs/                        e.g. Organization/Actor, Business Service, Process catalogs
  matrices/                        e.g. Business Interaction, Actor/Role matrices
  diagrams/                        e.g. Business Footprint, Process Flow (Mermaid)
03-data-architecture/
  catalogs/                        e.g. Data Entity, Data Component catalogs
  matrices/                        e.g. Data Entity/Business Function matrix
  diagrams/                        e.g. Data Dissemination, Data Security, Class diagrams (Mermaid)
04-application-architecture/
  catalogs/                        e.g. Application Portfolio catalog
  matrices/                        e.g. Application/Function, App Interaction matrices
  diagrams/                        e.g. Application Communication diagram (Mermaid)
05-technology-architecture/
  catalogs/                        e.g. Technology Standards, Platform catalogs
  matrices/                        e.g. App/Technology matrix
  diagrams/                        e.g. Environments & Locations, Network diagrams (Mermaid)
06-opportunities-and-solutions/    Gap analysis, solution building blocks, work packages,
                                    business transformation readiness assessment
07-migration-planning/             Implementation and migration plan, roadmap, transition architecture
08-implementation-governance/      Architecture contracts, compliance assessments
09-architecture-change-management/ Change requests, impact analyses
10-requirements-management/        Requirements catalog and traceability matrix (cross-cutting,
                                    per TOGAF's central circle)
11-risk-and-security/              Risk register, security architecture diagrams
_templates/                        Starting point for each artifact type
examples/                          Additional self-contained worked scenarios
```

## Worked scenarios

The numbered folders above are the primary worked scenario: **Meridian
Retail Group**, a fictitious retail company, run through the full breadth
of TOGAF artifacts (`INDEX.md` at the repository root indexes it).

`examples/` holds additional, self-contained worked scenarios in a
different industry, each with the same folder-per-ADM-phase layout and its
own local `README.md` and `INDEX.md`:

- [`examples/private-wealth-management/`](examples/private-wealth-management/) —
  **Silverline Private Wealth**, a fictitious multi-family office /
  registered investment advisor. Lighter than the primary scenario (one
  catalog/matrix/diagram per architecture domain rather than several), to
  show the same templates generalizing to a different industry without
  duplicating the primary scenario's full depth.

## Conventions

- **One artifact per file**, named `<domain-prefix>-<kebab-case-name>.md`
  (e.g. `02-business-service-catalog.md`).
- **Frontmatter on every file** — see `_templates/` for the fields
  (id, title, artifact_type, adm_phase, status, owner, version).
- **Diagrams as Mermaid**, fenced with ` ```mermaid `, embedded directly in
  the artifact's Markdown file (or in `diagrams/` as standalone files
  referenced from a catalog/matrix when reused across artifacts).
- **No binary images** (no PNG/JPG/SVG/Visio/PDF exports). If a diagram type
  genuinely can't be expressed in Mermaid, use PlantUML text syntax instead —
  still plain text.
- **Index**: `INDEX.md` at the root lists every artifact with its metadata for
  quick lookup; regenerate it whenever artifacts are added or changed.
- **Traceability**: frontmatter may include an optional `traces_to` array
  (IDs of requirements or other artifacts this one helps satisfy) for
  lightweight point-to-point linking. The authoritative end-to-end view —
  driver → requirement → gap → SBB → work package → verification — lives in
  `10-requirements-management/requirements-traceability-matrix.md`.
