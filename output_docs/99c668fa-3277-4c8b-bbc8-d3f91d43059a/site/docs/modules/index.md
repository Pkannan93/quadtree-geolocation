# Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) Documentation — Modules

<!-- alpha8-narrative:overview -->
## Overview

This codebase implements a quadtree spatial index for geolocation queries, organized across six modules that separate core data structure logic from visualization concerns. The root module anchors the repository, while `quadtree-graphic` supplies a Gradle-based Swing/AWT application for rendering and interacting with the quadtree.

The most consequential separation lives between `quadtree-graphic/src/main/java/src/quadtree/core`, which houses the underlying quadtree implementation for indexing geographic entities by latitude and longitude, and `quadtree-graphic/src/main/java/src/quadtree`, which wraps those core primitives in a drawable adapter layer. The `src` module at `quadtree-graphic/src/main/java/src` ties everything together by bootstrapping the application window through its `Main` entry point. Gradle wrapper configuration resides in `quadtree-graphic/gradle/wrapper`, pinning the build toolchain to a specific distribution.

The tables below enumerate each module's files, public interfaces, and dependency relationships, helping you trace how query logic in core propagates through the drawable layer to the GUI.
<!-- /alpha8-narrative:overview -->
6 module(s) detected by the ingestion agent. Each row links to a per-module page with its responsibility, public surface, collaborators, and the files inside it.

| Module | Responsibility | Files | Domain hint |
|---|---|---|---|
| [.](root.md) | This is the root module of a standalone repository containing a quadtree data structure implementation for geolocatio… | 0 | `Geospatial indexing / spatial data structures` |
| [quadtree-graphic](quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the project settings, build sc… | 4 | `Build tooling / project configuration for a quadtree graphics application` |
| [quadtree-graphic/gradle/wrapper](quadtree__graphic__gradle__wrapper.md) | Configures the Gradle wrapper for the quadtree-graphic project, specifying which Gradle distribution version and down… | 1 | `build tooling / Gradle configuration` |
| [quadtree-graphic/src/main/java/src](quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application scaffolding for the quadtree visualization: bootstraps the window (`Main… | 6 | `Interactive 2D graphics / spatial data-structure visualization (quadtree neighbor search over a geographic map)` |
| [quadtree-graphic/src/main/java/src/quadtree](quadtree__graphic__src__main__java__src__quadtree.md) | Provides a drawable/visualizable adapter layer over the core QuadTree data structure. It wraps `QuadTree` and `QuadTr… | 2 | `Spatial data structure visualization / graphical rendering of quadtrees` |
| [quadtree-graphic/src/main/java/src/quadtree/core](quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial data structure for indexing and querying geographic entities (neighbours) by latit… | 5 | `Geospatial indexing / spatial data structures` |
