# Module — `output_docs/81bfea4c-bca4-4354-a6af-42e79ce1d979`

_Domain hint: `Code analysis / repository documentation generation pipeline output`_

## Responsibility

This module is an isolated documentation output directory for a single analysis run (ID 81bfea4c-bca4-4354-a6af-42e79ce1d979) targeting the quadtree-geolocation Java repository. It aggregates the artifacts produced by a documentation/analysis pipeline: a run summary with metadata, the selected analysis result, the ingestion-phase findings (tech stack, module map, entry points, bounded contexts, architecture style, domain groups), and an error log capturing failures from the static-code-analysis-agent and verification-critic-agent stages.

## Public surface

- `00-run-summary.md`
- `01-selected-result.md`
- `02-ingestion.md`
- `03-errors.md`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `output_docs/81bfea4c-bca4-4354-a6af-42e79ce1d979/00-run-summary.md` | This file provides a summary of a documentation analysis run, including metadata such as run ID,… | — |
| `output_docs/81bfea4c-bca4-4354-a6af-42e79ce1d979/01-selected-result.md` | This file documents the comprehensive analysis results of a quadtree-geolocation Java repository,… | `Tech Stack Profile`, `Module Map`, `Entry Points`, … (+8) |
| `output_docs/81bfea4c-bca4-4354-a6af-42e79ce1d979/02-ingestion.md` | This documentation file describes the ingestion phase results for the quadtree-geolocation projec… | `Tech Stack Profile`, `Module Map`, `Entry Points`, … (+8) |
| `output_docs/81bfea4c-bca4-4354-a6af-42e79ce1d979/03-errors.md` | This file records errors that occurred during the static code analysis pipeline execution, docume… | `static-code-analysis-agent failure`, `verification-critic-agent failure` |

---

See also: [Modules index](index.md) — every module in this run.
