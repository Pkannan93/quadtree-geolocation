# Geospatial indexing and visualization (quadtree-based geographic neighbour search) Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This repository implements a quadtree-based spatial indexing system for geographic data, organized into distinct layers that separate core indexing logic from visualization concerns. The architecture spans from foundational data structures through build tooling to an interactive graphical application for exploring spatial relationships.

At the heart of the system is the `core` capability, which defines the `Neighbour` abstraction for geo-location entities and implements quadtree algorithms for efficient neighbour lookup and spatial search. The `quadtree` capability extends this foundation with graphical rendering, while the `src` capability delivers a Swing/AWT-based visualization shell that brings the spatial index to life on screen. Build infrastructure is managed through standard Gradle wrapper configuration, pinning distribution versions and providing reproducible builds across environments.

The bounded contexts below detail how spatial indexing, visualization, and project infrastructure responsibilities are separated, with each capability contributing to either data structure implementation, rendering, or tooling. Review the context mappings to understand how geographic indexing concerns flow from core abstractions through graphical extensions to the interactive application layer.
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
