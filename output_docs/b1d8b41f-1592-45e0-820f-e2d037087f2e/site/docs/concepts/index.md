# Geospatial indexing and proximity search via quadtree, with an interactive Swing visualization Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This page catalogs the conceptual domains and capabilities detected across the repository. The analysis identified 40 distinct contexts, each representing a bounded area of concern or technical capability that the codebase addresses.

The dominant context is geospatial indexing built on quadtree spatial data structures, which forms the foundational domain for the project. A significant portion of the detected capabilities relate to automated documentation generation pipeline output and artifact storage, reflecting the repository's dual nature as both a quadtree implementation and a documentation generation target. Multiple capability entries reference isolated output artifact directories identified by UUID, such as `0520f421-3584-4a75-8b04-97cbcf45f5f7` and `13d2867e-cc7f-4366-8d7e-a8e36f74a147`, which house complete sets of generated documentation deliverables.

The tables below enumerate all 40 contexts with their associated capabilities. Use this glossary to understand the vocabulary and conceptual boundaries that structure the system, particularly when exploring the relationships between spatial indexing logic and the documentation tooling that captures it.
<!-- /alpha8-narrative:overview -->
Domain-level view of the system: bounded contexts, business capabilities, the actors who use them, and a narrative data model. Companion to the technical Reference surface — same source data, different framing for a non-technical reader.

| Area | Count | Page |
|---|---|---|
| Bounded contexts | 40 | [contexts.md](contexts.md) |
| Business capabilities | 40 | [capability-matrix.md](capability-matrix.md) |
| Actors | 0 | [actors.md](actors.md) |
| Domain entities | 0 | [data-model.md](data-model.md), [terms.md](terms.md) |

Pages:

- [Bounded contexts](contexts.md) — independent areas of the domain, each with its own language and rules.
- [Actors](actors.md) — who interacts with the system, and which capabilities they use.
- [Capability matrix](capability-matrix.md) — capability × bounded-context × code (modules + routes) join.
- [Glossary](terms.md) — alphabetical reference for every entity and capability name.
- [Data model](data-model.md) — narrative ER with the top-20 most central entities.
