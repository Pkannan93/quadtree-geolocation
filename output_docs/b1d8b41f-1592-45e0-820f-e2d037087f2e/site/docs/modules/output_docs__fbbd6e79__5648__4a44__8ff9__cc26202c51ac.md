# Module — `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac`

_Domain hint: `Automated code analysis and functional documentation generation`_

## Responsibility

This module is an isolated documentation output directory for a single documentation-generation run (identified by UUID `fbbd6e79-5648-4a44-8ff9-cc26202c51ac`). It aggregates the full pipeline artifacts produced when analyzing a target repository: run metadata (`00-run-summary.md`), the finalized selected result (`01-selected-result.md`), repository ingestion profiling (`02-ingestion.md`), static code analysis (`03-static-analysis.md`), runtime behavior inference (`04-runtime-inference.md`), business semantics interpretation (`05-business-semantics.md`), the consolidated functional specification (`06-documentation.md`), and a verification critic report (`07-critic.md`). Together these files represent the staged, traceable outputs of an automated codebase-to-functional-documentation workflow. The module has no inbound or outbound code dependencies — it is a terminal data/artifact directory consumed by humans or downstream documentation tooling.

## Public surface

- `00-run-summary.md`
- `01-selected-result.md`
- `02-ingestion.md`
- `03-static-analysis.md`
- `04-runtime-inference.md`
- `05-business-semantics.md`
- `06-documentation.md`
- `07-critic.md`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/00-run-summary.md` | This file serves as a metadata summary for a documentation generation run. It records key informa… | `run metadata`, `run ID`, `repository URL`, … (+3) |
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/01-selected-result.md` | This file contains the complete functional documentation result for a specific repository analysi… | `functional specification document`, `documentation markdown`, `static analysis summary`, … (+3) |
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/02-ingestion.md` | This documentation file describes the repository ingestion and analysis process, detailing how th… | `tech stack profile`, `module map`, `entry points`, … (+4) |
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/03-static-analysis.md` | This file documents comprehensive static analysis results for a codebase, including symbol relati… | `symbol graph`, `dependency graph`, `API catalog`, … (+11) |
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/04-runtime-inference.md` | This documentation file presents runtime behavior inference results, capturing technical sequence… | `technical sequence flows`, `state transitions`, `end-to-end transaction paths`, … (+6) |
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/05-business-semantics.md` | This documentation file captures the business semantics analysis of a system, defining its purpos… | `system purpose`, `business capabilities by domain`, `business capabilities list`, … (+5) |
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/06-documentation.md` | This file serves as the comprehensive functional specification document for the system. It docume… | `functional specification`, `executive summary`, `actors`, … (+6) |
| `output_docs/fbbd6e79-5648-4a44-8ff9-cc26202c51ac/07-critic.md` | This file contains verification critic analysis results for a document, providing a confidence sc… | `confidence score`, `issues list`, `unsupported claims`, … (+2) |

---

See also: [Modules index](index.md) — every module in this run.
