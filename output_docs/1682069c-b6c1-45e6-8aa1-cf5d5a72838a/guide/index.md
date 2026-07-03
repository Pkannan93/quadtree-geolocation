# Geospatial indexing and proximity search visualization Documentation — Modules

<!-- alpha8-narrative:overview -->
## Overview

This repository implements a geographic quadtree data structure with an interactive Swing-based visualization layer. The codebase is organized as a single Gradle project named `quadtree-graphic`, containing both the spatial indexing logic and the graphical interface that renders it on a world map.

The core quadtree implementation lives in `quadtree-graphic/src/main/java/src/quadtree/core`, defining a `Neighbour` abstraction and the foundational tree algorithms for partitioning geographic points. A separate adapter layer at `quadtree-graphic/src/main/java/src/quadtree` wraps these core structures with drawable hooks, bridging the data structure to the AWT canvas. The top-level `src` package hosts the Swing application that orchestrates the UI and coordinates user interaction with the quadtree visualization.

The tables below detail each module's public surface and internal dependencies. Use them to trace how geographic data flows from the core tree through the drawable adapters to the canvas, or to identify which files to modify when extending search radius logic or changing map projection behavior.
<!-- /alpha8-narrative:overview -->
6 module(s) detected by the ingestion agent. Each row links to a per-module page with its responsibility, public surface, collaborators, and the files inside it.

| Module | Responsibility | Files | Domain hint |
|---|---|---|---|
| [.](root.md) | Top-level project root containing only meta and documentation files: a `.gitignore` for VCS hygiene, an Apache Licens… | 0 | `Geospatial indexing / geolocation (quadtree-based spatial data structures)` |
| [quadtree-graphic](quadtree__graphic.md) | Gradle-based Java project scaffolding for a `quadtree-graphic` application. Provides the build configuration (`build.… | 4 | `Build tooling / project scaffolding for a quadtree graphics application` |
| [quadtree-graphic/gradle/wrapper](quadtree__graphic__gradle__wrapper.md) | Provides the Gradle wrapper configuration for the `quadtree-graphic` project, specifying which Gradle distribution ve… | 1 | `build tooling / Gradle wrapper configuration` |
| [quadtree-graphic/src/main/java/src](quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT graphical application for visualizing a quadtree of geographic points on a world map… | 6 | `Spatial data structure visualization / geographic neighbor search` |
| [quadtree-graphic/src/main/java/src/quadtree](quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical/drawable adapter layer over a core quadtree data structure, enabling visualization of quadtree n… | 2 | `Spatial data structure visualization (quadtree rendering for 2D graphics)` |
| [quadtree-graphic/src/main/java/src/quadtree/core](quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial indexing implementation for geographic point data. Defines a `Neighbour` abstracti… | 5 | `Geospatial indexing / proximity search` |
