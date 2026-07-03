# Geospatial indexing and visualization using quadtrees (geolocation optimization / efficient spatial queries) Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This page maps the project's six bounded contexts and their core capabilities, revealing how a geospatial indexing system built around quadtree data structures organizes its concerns. The substrate spans build infrastructure, core spatial algorithms, visualization layers, and an interactive demonstration application.

The most significant capability is the `core` context, which provides quadtree spatial-indexing data structures for geographic points using latitude and longitude coordinates. This foundation supports a `quadtree` visualization context that wraps these data structures with drawable components, enabling rendering operations. The `src` context ties these together in a Swing application shell that demonstrates interactive 2D spatial-data visualization. Build concerns are isolated in a `quadtree-graphic` context with standard Gradle wrapper configuration.

The tables below detail each context's scope and the specific capabilities that define its boundaries. Use this inventory to understand what responsibilities live where and how the system partitions its spatial indexing work from its rendering and tooling concerns.
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
