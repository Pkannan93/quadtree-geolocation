# Geospatial indexing and visualization (quadtree-based nearest-neighbor search) Documentation — Modules

<!-- alpha8-narrative:overview -->
## Overview

This codebase implements a geographic point search engine using a quadtree spatial index, paired with a Swing-based visualization tool. The repository is structured around two primary concerns: the core quadtree algorithm in `quadtree-graphic/src/main/java/src/quadtree/core` and the graphical frontend in `quadtree-graphic/src/main/java/src` that renders the tree's structure and queries in real time.

The six modules reflect a typical Java project layout, with Gradle wrapper configuration pinning the build to version 8.5 and the `quadtree-graphic` directory housing all application code. The `DrawableQuadTree` adapters in `quadtree-graphic/src/main/java/src/quadtree` bridge the core data structures to the AWT rendering pipeline, enabling visual debugging of spatial partitions and neighbor searches. The root module provides licensing and top-level documentation.

The tables below break down each module's public surface and internal collaborators, helping you trace how the quadtree core feeds the visualization layer and where to extend functionality.
<!-- /alpha8-narrative:overview -->
6 module(s) detected by the ingestion agent. Each row links to a per-module page with its responsibility, public surface, collaborators, and the files inside it.

| Module | Responsibility | Files | Domain hint |
|---|---|---|---|
| [.](root.md) | This top-level module serves as the project's root metadata and documentation layer. It contains the Apache 2.0 LICEN… | 0 | `geolocation / spatial data structures (quadtree)` |
| [quadtree-graphic](quadtree__graphic.md) | Provides Gradle build infrastructure for the quadtree-graphic Java project, including build configuration (`build.gra… | 4 | `Build tooling / project scaffolding for a quadtree graphics application` |
| [quadtree-graphic/gradle/wrapper](quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5)… | 1 | `build tooling / Gradle wrapper configuration` |
| [quadtree-graphic/src/main/java/src](quadtree__graphic__src__main__java__src.md) | Provides the Swing/AWT-based graphical application shell for visualizing a quadtree-driven geographic point search. I… | 6 | `Interactive 2D visualization of a quadtree spatial index for geographic nearest-neighbor search` |
| [quadtree-graphic/src/main/java/src/quadtree](quadtree__graphic__src__main__java__src__quadtree.md) | Provides drawable wrapper classes that adapt the core QuadTree data structures for graphical rendering. `DrawableQuad… | 2 | `Graphical visualization of spatial quadtree data structures` |
| [quadtree-graphic/src/main/java/src/quadtree/core](quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core QuadTree spatial indexing implementation for geographic neighbor lookup. Defines the `Neighbour` ab… | 5 | `Geospatial indexing / proximity search` |
