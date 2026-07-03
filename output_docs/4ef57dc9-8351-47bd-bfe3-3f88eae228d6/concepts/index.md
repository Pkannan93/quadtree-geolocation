# Geospatial indexing and proximity search with interactive visualization Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This page maps the primary bounded contexts and capabilities discovered in the codebase. The repository centers on a quadtree spatial indexing implementation designed for geolocation optimization and proximity search. Six distinct capabilities span from core data structures through build tooling to interactive visualization.

The `core` capability delivers the foundational `QuadTree` implementation for storing and querying geographic entities, while drawable extensions layer visualization support on top of that structure. The `quadtree-graphic` build tooling and `src` capability together bootstrap a Swing/AWT application shell that renders the spatial index over geographic points. Build configuration lives in the `wrapper` and `quadtree-graphic` contexts, orchestrating Gradle distribution and project dependencies.

The table below enumerates all contexts and capabilities with their descriptions. Use this inventory to understand how the system partitions responsibility and where to locate logic for specific geographic indexing or rendering concerns.
<!-- /alpha8-narrative:overview -->
Domain-level view of the system: bounded contexts, business capabilities, the actors who use them, and a narrative data model. Companion to the technical Reference surface — same source data, different framing for a non-technical reader.

| Area | Count | Page |
|---|---|---|
| Bounded contexts | 6 | [contexts.md](contexts.md) |
| Business capabilities | 6 | [capability-matrix.md](capability-matrix.md) |
| Actors | 0 | [actors.md](actors.md) |
| Domain entities | 0 | [data-model.md](data-model.md), [terms.md](terms.md) |

Pages:

- [Bounded contexts](contexts.md) — independent areas of the domain, each with its own language and rules.
- [Actors](actors.md) — who interacts with the system, and which capabilities they use.
- [Capability matrix](capability-matrix.md) — capability × bounded-context × code (modules + routes) join.
- [Glossary](terms.md) — alphabetical reference for every entity and capability name.
- [Data model](data-model.md) — narrative ER with the top-20 most central entities.
