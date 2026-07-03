# Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This page documents the bounded contexts and capabilities that structure the repository, which centers on a quadtree-based geospatial indexing system with an interactive visualization layer. The codebase separates concerns between a `core` spatial-indexing library that handles geographic proximity queries and a `quadtree` graphics module that renders those structures in a Swing/AWT application.

The domain splits into two primary contexts: geospatial indexing logic (quadtree data structures, neighbor search algorithms) and interactive 2D graphics (world map visualization, spatial-index rendering). The `core` capability implements the underlying quadtree for storing and querying geographic neighbors, while the `src` capability provides the top-level application shell and rendering loop. Build tooling through Gradle scaffolds the `quadtree-graphic` project and pins distribution versions via the wrapper configuration.

The tables below enumerate each capability and context detected in the repository, showing how responsibilities distribute across modules and where key abstractions live.
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
