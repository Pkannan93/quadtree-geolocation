# Geospatial indexing and proximity search with interactive visualization Documentation — Modules

<!-- alpha8-narrative:overview -->
## Overview

This repository implements a quadtree-based geolocation data structure with a standalone graphical visualizer. The codebase is organized into six modules spanning build configuration, application scaffolding, and the core spatial indexing logic. The project uses Gradle 4.0 and ships with a Swing-based UI for interacting with the quadtree.

Two modules form the functional heart of the system. The `quadtree-graphic/src/main/java/src/quadtree/core` module delivers the spatial indexing engine itself, defining primitives like `Neighbour` for point-based queries and proximity operations. One layer up, `quadtree-graphic/src/main/java/src/quadtree` extends that core with drawable wrappers—`DrawableQuadTree` and related types—that adapt the data structure for rendering. The top-level `quadtree-graphic/src/main/java/src` module ties these together in a Swing application shell, bootstrapping the visualizer window and wiring user interactions to the rendering framework.

The tables below break down each module's files, public exports, and inbound references, giving you a map of responsibilities and collaboration patterns across the repository.
<!-- /alpha8-narrative:overview -->
6 module(s) detected by the ingestion agent. Each row links to a per-module page with its responsibility, public surface, collaborators, and the files inside it.

| Module | Responsibility | Files | Domain hint |
|---|---|---|---|
| [.](root.md) | Root-level repository metadata for a standalone quadtree-based geolocation data structure project. Contains the Apach… | 0 | `Geospatial indexing / quadtree spatial data structures` |
| [quadtree-graphic](quadtree__graphic.md) | Provides the Gradle build scaffolding for an isolated `quadtree-graphic` project, including the Java plugin configura… | 4 | `build tooling / quadtree graphics application` |
| [quadtree-graphic/gradle/wrapper](quadtree__graphic__gradle__wrapper.md) | Provides the Gradle Wrapper configuration for the quadtree-graphic project, pinning the build to Gradle 4.0 via `grad… | 1 | `build tooling / Gradle wrapper configuration` |
| [quadtree-graphic/src/main/java/src](quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing application shell and rendering framework for the quadtree graphic visualizer. It bootst… | 6 | `Interactive geospatial quadtree visualization (Swing GUI)` |
| [quadtree-graphic/src/main/java/src/quadtree](quadtree__graphic__src__main__java__src__quadtree.md) | Provides graphical/drawable extensions to a core quadtree data structure for visualization purposes. `DrawableQuadTre… | 2 | `Spatial data structure visualization (quadtree rendering)` |
| [quadtree-graphic/src/main/java/src/quadtree/core](quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides a self-contained quadtree spatial indexing core for geographic data. Defines the `Neighbour` abstraction for… | 5 | `Geospatial indexing / proximity search` |
