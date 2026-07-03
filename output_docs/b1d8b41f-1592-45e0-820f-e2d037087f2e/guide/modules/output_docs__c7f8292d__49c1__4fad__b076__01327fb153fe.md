# Module — `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe`

_Domain hint: `Code analysis / documentation generation output artifacts`_

## Responsibility

This module is an output artifact directory containing the generated documentation deliverables for a single repository analysis run (identified by UUID c7f8292d-49c1-4fad-b076-01327fb153fe). It collects sequentially numbered markdown reports covering the full analysis pipeline: run metadata (00), selected results (01), repository ingestion (02), static analysis (03), runtime inference (04), business semantics (05), functional specification documentation (06), diagram generation outcomes (07), and critic verification (08). The module is isolated in the dependency graph, serving purely as terminal output rather than consumed code.

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
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/00-run-summary.md` | This file serves as a metadata summary document for a code analysis run. It records the run ident… | — |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/01-selected-result.md` | This file is a comprehensive analysis report document that presents repository intelligence resul… | — |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/02-ingestion.md` | This markdown file documents the results of a repository ingestion process, presenting a comprehe… | — |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/03-static-analysis.md` | This file is a comprehensive static analysis report that documents code structure, dependencies,… | — |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/04-runtime-inference.md` | This file documents inferred runtime behavior and analysis for a system, including technical sequ… | — |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/05-business-semantics.md` | This markdown file documents the business semantics analysis of a codebase, presenting business c… | — |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/06-documentation.md` | This markdown file serves as a functional specification document for a web application. It includ… | `functional specification document`, `gap analysis report`, `technical appendix sections` |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/07-diagrams.md` | This file documents the results of diagram generation for a codebase analysis, specifically listi… | — |
| `output_docs/c7f8292d-49c1-4fad-b076-01327fb153fe/08-critic.md` | This file documents the verification criticism process for generated documentation. It provides a… | `confidence score`, `issues list`, `unsupported claims list`, … (+7) |

---

See also: [Modules index](index.md) — every module in this run.
