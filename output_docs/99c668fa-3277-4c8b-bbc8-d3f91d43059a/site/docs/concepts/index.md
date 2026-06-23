# Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This repository centers on a quadtree-based geospatial indexing system with an accompanying interactive visualization layer. The core capability provides spatial data structures for indexing and querying geographic entities, while the `quadtree-graphic` build configuration supports a Swing/AWT application that renders neighbor-search operations over a map. Together, these components demonstrate how hierarchical spatial partitioning can accelerate queries in two-dimensional coordinate spaces.

The substrate reveals six capabilities spanning three main concerns: the foundational quadtree implementation in the `core` module, Gradle-based build tooling that packages the visualization project, and graphical rendering logic under `src` and `quadtree` that wraps the core data structure for on-screen display. The visualization component is particularly notable—it provides a drawable adapter layer that lets users see quadtree subdivision and neighbor-search behavior in real time, bridging algorithmic structure and human understanding.

Five bounded contexts emerge from the analysis, ranging from low-level spatial data structures through build configuration to interactive 2D graphics. The tables below enumerate each capability and context in detail, offering concrete entry points into the codebase's architectural boundaries.
<!-- /alpha8-narrative:overview -->
Domain-level view of the system: bounded contexts, business capabilities, the actors who use them, and a narrative data model. Companion to the technical Reference surface — same source data, different framing for a non-technical reader.

| Area | Count | Page |
|---|---|---|
| Bounded contexts | 5 | [contexts.md](contexts.md) |
| Business capabilities | 6 | [capability-matrix.md](capability-matrix.md) |
| Actors | 0 | [actors.md](actors.md) |
| Domain entities | 0 | [data-model.md](data-model.md), [terms.md](terms.md) |

Pages:

- [Bounded contexts](contexts.md) — independent areas of the domain, each with its own language and rules.
- [Actors](actors.md) — who interacts with the system, and which capabilities they use.
- [Capability matrix](capability-matrix.md) — capability × bounded-context × code (modules + routes) join.
- [Glossary](terms.md) — alphabetical reference for every entity and capability name.
- [Data model](data-model.md) — narrative ER with the top-20 most central entities.
