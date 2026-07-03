# Geospatial indexing and visualization (quadtree-based nearest-neighbor search) Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This page catalogs the bounded contexts and capabilities the analysis pipeline identified across the repository. The system centers on a geospatial indexing library built around a quadtree data structure for efficient nearest-neighbor search, paired with an interactive visualization layer that renders the spatial index in real time.

Six distinct capabilities emerge from the substrate. The `core` capability implements the fundamental quadtree spatial indexing logic for geographic proximity queries, while the `quadtree` capability wraps those data structures in drawable adapters for graphical rendering. The `src` capability provides the Swing/AWT application shell that orchestrates the interactive visualization experience. Supporting these are build tooling capabilities—`quadtree-graphic` for the overall Gradle infrastructure and `wrapper` for pinning the Gradle distribution version.

The table below breaks down each capability's context, description, and origin. Use this data to understand how the codebase separates concerns between spatial algorithms, visualization adapters, and application scaffolding.
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
