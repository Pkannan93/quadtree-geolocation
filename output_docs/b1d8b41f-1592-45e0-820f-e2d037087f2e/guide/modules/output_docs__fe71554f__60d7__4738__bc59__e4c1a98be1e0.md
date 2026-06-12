# Module — `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0`

_Domain hint: `Code analysis / automated documentation generation pipeline output (analyzed subject domain: quadtree-based geolocation)`_

## Responsibility

This module is an output artifact directory containing the complete generated analysis report for a single code analysis run (run ID `fe71554f-60d7-4738-bc59-e4c1a98be1e0`) targeting a quadtree geolocation repository. It aggregates the staged outputs of a multi-phase documentation pipeline — run metadata (`00-run-summary`), consolidated results (`01-selected-result`), repository ingestion and tech-stack profiling (`02-ingestion`), static analysis with symbol/dependency graphs and API catalog (`03-static-analysis`), runtime behavior inference including sequence flows and state transitions (`04-runtime-inference`), business semantics and actor mapping (`05-business-semantics`), the final functional specification documentation (`06-documentation`), diagram generation log (`07-diagrams`), and a critic-style quality assessment (`08-critic`). As an isolated leaf in the dependency graph, it produces no code and is consumed by human readers rather than other modules.

## Public surface

- `00-run-summary.md`
- `01-selected-result.md`
- `02-ingestion.md`
- `03-static-analysis.md`
- `04-runtime-inference.md`
- `05-business-semantics.md`
- `06-documentation.md`
- `07-diagrams.md`
- `08-critic.md`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/00-run-summary.md` | This file serves as a metadata summary document for a code analysis run, capturing key informatio… | — |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/01-selected-result.md` | This file consolidates all analysis results for a quadtree geolocation repository, including inge… | `Tech Stack Profile`, `Module Map`, `Entry Points`, … (+27) |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/02-ingestion.md` | This documentation file describes the repository ingestion phase of a codebase analysis system. I… | `Tech Stack Profile`, `Module Map`, `Entry Points`, … (+9) |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/03-static-analysis.md` | This file presents comprehensive static code analysis results for a codebase, including symbol gr… | `Symbol Graph`, `Dependency Graph`, `Api Catalog`, … (+17) |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/04-runtime-inference.md` | This documentation file describes runtime behavior inference for a system, detailing technical se… | `Technical Sequence Flows`, `State Transitions`, `End To End Transaction Paths`, … (+7) |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/05-business-semantics.md` | This file documents the business semantics analysis of a software system, capturing its purpose,… | `System Purpose`, `Business Capabilities By Domain`, `Business Capabilities`, … (+8) |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/06-documentation.md` | This file is a comprehensive functional specification documentation template that structures the… | `Executive Summary`, `Actors`, `Business Capabilities`, … (+6) |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/07-diagrams.md` | This file documents the diagram generation process for a codebase analysis, including attempts ma… | `Diagrams`, `Skipped Diagrams with reasons` |
| `output_docs/fe71554f-60d7-4738-bc59-e4c1a98be1e0/08-critic.md` | This file serves as a documentation quality assessment report, identifying verification issues, c… | — |

---

See also: [Modules index](index.md) — every module in this run.
