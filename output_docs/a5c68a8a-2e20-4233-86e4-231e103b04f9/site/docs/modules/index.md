# Geospatial indexing and visualization (quadtree-based geographic neighbour search) Documentation — Modules

<!-- alpha8-narrative:overview -->
## Overview

This repository implements a quadtree spatial indexing data structure with both a core algorithmic engine and a graphical visualization layer. The codebase is organized into six modules, split between top-level project scaffolding and the `quadtree-graphic` application that demonstrates the structure in action.

The core logic lives in `quadtree-graphic/src/main/java/src/quadtree/core`, which defines the `Neighbour` abstraction for geo-located entities and provides the fundamental indexing operations. A parallel module at `quadtree-graphic/src/main/java/src/quadtree` extends these core types with rendering capabilities, while `quadtree-graphic/src/main/java/src` supplies the Swing/AWT window shell that ties everything together. Build infrastructure is handled through standard Gradle wrapper modules pinned to version 8.5.

The modules below show zero inter-module fan-in, indicating a relatively flat dependency structure where the graphical layers depend on core types but modules do not reference each other horizontally. Use the responsibility summaries and public surface details in the tables below to understand each module's contract and identify which files to examine first when tracing feature implementations or debugging spatial queries.
<!-- /alpha8-narrative:overview -->
6 module(s) detected by the ingestion agent. Each row links to a per-module page with its responsibility, public surface, collaborators, and the files inside it.

| Module | Responsibility | Files | Domain hint |
|---|---|---|---|
| [.](root.md) | Top-level repository root containing project metadata, licensing, and documentation for a quadtree data structure imp… | 0 | `Geospatial data structures (quadtree-based location indexing)` |
| [quadtree-graphic](quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the Gradle wrapper scripts (`gr… | 4 | `build tooling / project infrastructure (graphical quadtree application)` |
| [quadtree-graphic/gradle/wrapper](quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5)… | 1 | `build tooling / Gradle wrapper configuration` |
| [quadtree-graphic/src/main/java/src](quadtree__graphic__src__main__java__src.md) | Provides the Swing/AWT-based graphical application shell for visualizing a quadtree spatial index. It defines the win… | 6 | `Spatial indexing visualization / interactive geographic data rendering` |
| [quadtree-graphic/src/main/java/src/quadtree](quadtree__graphic__src__main__java__src__quadtree.md) | Provides graphical/visual rendering capabilities for quadtree data structures by extending the core quadtree types (`… | 2 | `Spatial data visualization (quadtree-based geographic rendering)` |
| [quadtree-graphic/src/main/java/src/quadtree/core](quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial indexing engine: defines the `Neighbour` abstraction for geo-located entities (id,… | 5 | `Geospatial indexing / spatial search (quadtree for geographic neighbour lookup)` |
