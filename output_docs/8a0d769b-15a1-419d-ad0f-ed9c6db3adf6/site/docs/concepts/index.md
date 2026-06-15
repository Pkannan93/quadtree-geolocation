# Geospatial indexing and proximity search with interactive visualization Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This repository centers on a **geospatial quadtree data structure** designed for spatial indexing and proximity search. The codebase defines bounded contexts around both the core indexing logic and an interactive visualization layer, separating concerns between algorithmic primitives and end-user rendering. Key capabilities include a standalone quadtree implementation that supports neighbor queries and a Swing-based graphical application (`quadtree-graphic`) that renders the tree's spatial partitioning interactively.

The most significant domain concept is the **quadtree itself**, a hierarchical spatial index that recursively subdivides geographic regions to enable efficient proximity searches. The visualization context extends this core with drawable components, allowing developers to inspect how the tree partitions space and responds to queries in real time. Build tooling is isolated into its own context, with Gradle Wrapper configuration ensuring reproducible builds across environments.

The tables below catalog each bounded context and capability detected in the repository, linking them to the source files where they are defined. Use this map to understand how spatial indexing logic, graphical extensions, and build infrastructure relate to one another.
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
