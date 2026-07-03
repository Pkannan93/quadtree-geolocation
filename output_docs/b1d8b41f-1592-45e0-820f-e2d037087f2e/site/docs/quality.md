# Geospatial indexing and proximity search via quadtree, with an interactive Swing visualization Documentation — Quality and coverage

<!-- alpha8-narrative:overview -->
## Overview

This page reports on the documentation pipeline's coverage of the codebase. The analysis processed 307 files and extracted 367 embeddings across 40 modules, providing a quantitative view of how thoroughly the system captured the repository's structure and content. The pipeline ran without degradation, meaning no quality issues or skipped sections compromised the extraction process.

The embedding count reflects the number of semantic chunks the pipeline indexed for search and retrieval. With 367 embeddings distributed across 40 modules, the system has captured a representative cross-section of the codebase's logic and configuration. No routes or route details were detected, which may indicate this repository focuses on library code, tooling, or services that expose APIs through mechanisms not yet instrumented by the pipeline.

The tables below break down coverage by module and file, showing which parts of the codebase contributed to the documentation corpus. Use this data to identify gaps or confirm that critical modules received adequate attention during analysis.
<!-- /alpha8-narrative:overview -->
This page measures how well the codebase **explains itself** to future readers. The signals are derived from facts the upstream agents already extract — no extra LLM calls — so they're stable across re-runs and citation-friendly.

## Documentation coverage

| Signal | Documented | Total | Coverage |
|---|---|---|---|
| Public functions / classes with a docstring | 0 | 0 | — |
| HTTP routes with a handler docstring | 0 | 0 | — |
| Entity fields with a description | 0 | 0 | — |
| Modules with a README | 0 | 39 | 0% |
| Public symbols referenced from a test file | 0 | 76 | 0% |

### Detection notes

Docstring detection currently runs only against languages whose doc-comment lives **inside** the declaration body (Python `"""..."""`). For languages that put the doc-comment **before** the declaration (JSDoc `/** */`, Javadoc, Go `// `, Rust `///`) the parser hands us declaration source that doesn't include the leading comment block, so we can't tell from the artifact alone whether the author wrote one. Those symbols are reported as `undetected`, not as `undocumented`.

| Language | Symbols not yet measurable |
|---|---|
| `java` | 76 |

### Modules with no README

First 12 modules without a `README{.md,.rst,.txt}` file directly inside the module directory.

- `output_docs/0520f421-3584-4a75-8b04-97cbcf45f5f7`
- `output_docs/13d2867e-cc7f-4366-8d7e-a8e36f74a147`
- `output_docs/1b36ab85-b4a9-4da8-9377-b95ee49e2fd7`
- `output_docs/2473916f-59c7-4f88-ae4b-4cc55ec6c04a`
- `output_docs/27c31699-7abf-457b-a087-532f24fa07c1`
- `output_docs/3ce1bc1d-a150-4697-9858-2d0728b2b3ea`
- `output_docs/3cff911f-bcb2-4fe1-87d5-eb050623423f`
- `output_docs/4a66578e-e29c-45b0-a782-5ed801bdc3d1`
- `output_docs/4fa81b64-5268-4b7c-9fb8-3da7b6320406`
- `output_docs/742d0dce-e19d-45fb-9a93-f363ae6b600f`
- `output_docs/81bfea4c-bca4-4354-a6af-42e79ce1d979`
- `output_docs/84013871-aa6e-42b2-8c17-738d2206c7ad`

### Public symbols with no test reference

First 12 of 76 public symbols whose short name doesn't appear in any test file's source. Searched across **0** test file(s) detected by path convention. Substring-based: a comment in a test file that mentions the symbol counts as a reference, so the real number is a lower bound on under-tested code.

| Symbol | Kind | Source |
|---|---|---|
| `quadtree-graphic/src/main/java/src/BaseObject.java::BaseObject` | `class` | `quadtree-graphic/src/main/java/src/BaseObject.java:23` |
| `quadtree-graphic/src/main/java/src/BaseObject.java::BaseObject.getX` | `method` | `quadtree-graphic/src/main/java/src/BaseObject.java:37` |
| `quadtree-graphic/src/main/java/src/BaseObject.java::BaseObject.getY` | `method` | `quadtree-graphic/src/main/java/src/BaseObject.java:41` |
| `quadtree-graphic/src/main/java/src/BaseObject.java::BaseObject.getWidth` | `method` | `quadtree-graphic/src/main/java/src/BaseObject.java:45` |
| `quadtree-graphic/src/main/java/src/BaseObject.java::BaseObject.getHeight` | `method` | `quadtree-graphic/src/main/java/src/BaseObject.java:49` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java::CanvasPanel` | `class` | `quadtree-graphic/src/main/java/src/CanvasPanel.java:30` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java::CanvasPanel.start` | `method` | `quadtree-graphic/src/main/java/src/CanvasPanel.java:43` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java::CanvasPanel.stop` | `method` | `quadtree-graphic/src/main/java/src/CanvasPanel.java:72` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java::CanvasPanel.setupInput` | `method` | `quadtree-graphic/src/main/java/src/CanvasPanel.java:76` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java::CanvasPanel.mouseClicked` | `method` | `quadtree-graphic/src/main/java/src/CanvasPanel.java:78` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java::CanvasPanel.mousePressed` | `method` | `quadtree-graphic/src/main/java/src/CanvasPanel.java:82` |
| `quadtree-graphic/src/main/java/src/CanvasPanel.java::CanvasPanel.mouseReleased` | `method` | `quadtree-graphic/src/main/java/src/CanvasPanel.java:87` |

---

## Pipeline health

These are operational counters — useful for triaging a degraded run, not for measuring the codebase itself.

### Ingestion

| Signal | Count |
|---|---|
| Parsed files | 307 |
| File summaries | 307 |
| Module summaries | 40 |
| Indexable chunks in vector store (Ask coverage) | 367 |
| File summaries that fell back to a degraded summary | 0 |
| Module summaries that fell back to a degraded summary | 0 |

### Static analysis

| Signal | Count |
|---|---|
| HTTP routes detected | 0 |
| Routes with no resolved handler | 0 |
| Entities detected | 0 |
| Entities with no extracted fields | 0 |

### Runtime behaviour

| Signal | Count |
|---|---|
| Sequence flows derived | 0 |
| Flows with zero call-edge steps | 0 |

### Diagrams

| Signal | Count |
|---|---|
| Diagrams rendered | 0 |
| Diagrams skipped (with a reason) | 3 |

**Skip reasons**

- `architecture` x 1 — no inter-module imports
- `er` x 1 — no entities extracted
- `sequence` x 1 — no routes extracted from static analysis
