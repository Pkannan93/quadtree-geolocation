# Geospatial indexing and proximity search visualization Documentation — Quality and coverage

<!-- alpha8-narrative:overview -->
## Overview

This page reports how thoroughly the documentation pipeline analyzed the repository. The system processed 21 files and generated 81 embeddings across 6 modules, indicating solid coverage of the codebase structure. No routes were detected, which suggests this project may be a library, CLI tool, or backend service without HTTP endpoints rather than a web application.

The pipeline completed without degradation, meaning all targeted files were successfully analyzed and no analysis stages failed or timed out. This clean run provides confidence that the documentation below represents the full picture of what the system could extract from the source code.

Use the metrics below to assess whether critical parts of your codebase are represented in the generated documentation and to identify any gaps that might require manual documentation effort.
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
