# Geospatial indexing and proximity search with interactive visualization Documentation — Modules

<!-- alpha8-narrative:overview -->
## Overview

This codebase implements a quadtree spatial index optimized for geolocation queries, packaged as a Swing/AWT visualization application. The project is organized into six modules, with the core data structure living in `quadtree-graphic/src/main/java/src/quadtree/core` and a drawable extension layer in the adjacent `quadtree` package. The Gradle-based build is rooted in `quadtree-graphic`, which wraps both the indexing logic and the GUI shell.

The heart of the system is the `QuadTree` class in the core module, which stores and queries geographic entities by latitude and longitude. This base implementation is extended by `DrawableQuadTree`, adding rendering capabilities so the tree structure can be visualized in real time. The Swing application entry point (`Main`) bootstraps a JFrame that hosts this visualization, making it straightforward to observe how the spatial partitioning behaves under different data sets.

The tables below break down each module's responsibilities, public interfaces, and dependencies. Use them to identify which parts of the codebase you need to modify for indexing logic versus rendering concerns, and to trace how the visualization layer consumes the core data structure.
<!-- /alpha8-narrative:overview -->
6 module(s) detected by the ingestion agent. Each row links to a per-module page with its responsibility, public surface, collaborators, and the files inside it.

| Module | Responsibility | Files | Domain hint |
|---|---|---|---|
| [.](root.md) | Top-level project metadata for a quadtree data structure implementation aimed at geolocation optimization. Contains o… | 0 | `Geospatial indexing / geolocation optimization via quadtree data structures` |
| [quadtree-graphic](quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the root project settings, Jav… | 4 | `Build tooling / project scaffolding for a quadtree graphics application` |
| [quadtree-graphic/gradle/wrapper](quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL and ve… | 1 | `build tooling / Gradle configuration` |
| [quadtree-graphic/src/main/java/src](quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application shell for the quadtree visualization: bootstraps the JFrame (`Main`), ho… | 6 | `Interactive graphical visualization of a quadtree spatial index over geographic points` |
| [quadtree-graphic/src/main/java/src/quadtree](quadtree__graphic__src__main__java__src__quadtree.md) | Provides drawable/visualizable extensions of the core quadtree data structure. `DrawableQuadTree` extends the base `Q… | 2 | `Spatial data structure visualization / graphics rendering` |
| [quadtree-graphic/src/main/java/src/quadtree/core](quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core QuadTree spatial indexing implementation for storing and querying geographic entities by latitude/l… | 5 | `Geospatial indexing / proximity search` |
