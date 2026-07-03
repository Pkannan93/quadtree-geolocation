# Geospatial indexing and visualization via quadtrees Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This page catalogs the bounded contexts and capabilities detected across the repository, which centers on a quadtree-based geolocation optimization library. The codebase separates concerns into distinct layers: a `core` capability handling the fundamental spatial index implementation for storing and querying geographic entities, and a `quadtree-graphic` capability providing Swing-based visualization tooling. Build scaffolding is managed through Gradle wrapper configuration that pins the distribution version and supplies the necessary build infrastructure.

The architecture reflects a classic separation between algorithmic primitives and their visual representation. The core spatial indexing logic operates independently, while the graphical layer extends the base `QuadTree` implementation with drawable components for interactive demos. This structure allows the underlying quadtree data structures to remain decoupled from UI concerns, making the index suitable for headless server use or alternative front-end integrations.

The tables below enumerate all detected contexts and capabilities, each linked to the directories and files where they manifest. Use this data to understand which parts of the system own specific responsibilities and how domain boundaries align with the physical module structure.
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
