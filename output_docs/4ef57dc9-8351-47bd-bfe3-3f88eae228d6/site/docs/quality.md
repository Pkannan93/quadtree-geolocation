# Geospatial indexing and proximity search with interactive visualization Documentation — Quality and coverage

<!-- alpha8-narrative:overview -->
## Overview

This page reports on the documentation pipeline's coverage of the repository. The analysis processed 21 files and generated 81 semantic embeddings across 6 modules, providing a foundation for search and context retrieval throughout the documentation.

The pipeline completed without degradation, meaning all targeted files were successfully analyzed and indexed. No routes were detected, which suggests this codebase may be a library, CLI tool, or backend service without HTTP endpoints rather than a web application. The module structure captured indicates a moderate-sized project with well-defined organizational boundaries.

Use the metrics below to understand which parts of the codebase are documented and where gaps might exist. If critical files appear missing, check the pipeline's inclusion rules or file type filters.
<!-- /alpha8-narrative:overview -->
This page measures how well the codebase **explains itself** to future readers. The signals are derived from facts the upstream agents already extract — no extra LLM calls — so they're stable across re-runs and citation-friendly.

## Documentation coverage

| Signal | Documented | Total | Coverage |
|---|---|---|---|
| Public functions / classes with a docstring | 0 | 0 | — |
| HTTP routes with a handler docstring | 0 | 0 | — |
| Entity fields with a description | 0 | 0 | — |
| Modules with a README | 0 | 5 | 0% |
| Public symbols referenced from a test file | 0 | 76 | 0% |

### Detection notes

Docstring detection currently runs only against languages whose doc-comment lives **inside** the declaration body (Python `"""..."""`). For languages that put the doc-comment **before** the declaration (JSDoc `/** */`, Javadoc, Go `// `, Rust `///`) the parser hands us declaration source that doesn't include the leading comment block, so we can't tell from the artifact alone whether the author wrote one. Those symbols are reported as `undetected`, not as `undocumented`.

| Language | Symbols not yet measurable |
|---|---|
| `java` | 76 |

### Modules with no README

First 5 modules without a `README{.md,.rst,.txt}` file directly inside the module directory.

- `quadtree-graphic`
- `quadtree-graphic/gradle/wrapper`
- `quadtree-graphic/src/main/java/src`
- `quadtree-graphic/src/main/java/src/quadtree`
- `quadtree-graphic/src/main/java/src/quadtree/core`

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
| Parsed files | 21 |
| File summaries | 21 |
| Module summaries | 6 |
| Indexable chunks in vector store (Ask coverage) | 81 |
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
