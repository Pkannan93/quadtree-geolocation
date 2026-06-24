# Geospatial indexing and visualization (quadtree-based location services) Documentation — Concepts

<!-- alpha8-narrative:overview -->
## Overview

This repository centers on a quadtree-based spatial indexing system for geographic data, organized into distinct bounded contexts that separate core data structures from visualization and tooling concerns. The substrate reveals six capabilities spanning geospatial indexing, interactive visualization, and build infrastructure.

At the heart of the system is a core quadtree implementation that handles spatial indexing for geographic data through structures like `Neighborhood`. This foundation is wrapped by a graphical visualization layer that exposes the quadtree mechanics through a Java Swing/AWT application, providing an interactive demo UI for exploring how the spatial index partitions and queries location-based data. The build context is cleanly separated, with Gradle wrapper configuration managing project infrastructure independently of domain logic.

The breakdown below maps each capability to its bounded context and provides a human-readable description. Use this page to understand which parts of the codebase own which responsibilities, especially when navigating between the core indexing logic, its visual representation, and the surrounding build scaffolding.
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
