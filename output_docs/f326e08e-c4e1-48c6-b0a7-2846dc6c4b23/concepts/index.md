# Geospatial indexing and proximity search visualization Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This page catalogs the bounded contexts and capabilities detected across the codebase. The analysis identified six distinct capabilities organized around quadtree-based spatial indexing and visualization, ranging from build infrastructure to core geospatial data structures.

The repository centers on a `quadtree-graphic` Java application that visualizes geographic point data through a Swing/AWT interface. Two capabilities stand out: the `core` capability implements the fundamental quadtree spatial indexing for proximity search operations, while the `quadtree` capability provides a drawable adapter layer that bridges the core data structure to 2D graphics rendering. The project uses Gradle for build orchestration, with dedicated capabilities handling project scaffolding and wrapper configuration.

The table below enumerates each capability with its bounded context and a brief description. Use this inventory to understand how spatial indexing concerns are separated from visualization logic, and how build tooling supports the application's runtime features.
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
