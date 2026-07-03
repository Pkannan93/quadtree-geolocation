# Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points Documentation — Modules

<!-- alpha8-narrative:overview -->
## Overview

This page walks through the six modules that together implement a geographic quadtree data structure with an interactive Swing visualization. The codebase is organized as a Gradle project under `quadtree-graphic`, with source modules split between core spatial indexing logic and a graphical rendering layer.

At the heart of the system sits `quadtree-graphic/src/main/java/src/quadtree/core`, which provides the fundamental quadtree data structure for storing and querying geographic neighbors by latitude and longitude. This core is wrapped by `quadtree-graphic/src/main/java/src/quadtree`, which adds drawable visualization primitives on top of the underlying `QuadTree` and `QuadTreeNode` classes. The top-level application shell in `quadtree-graphic/src/main/java/src` ties these layers together into a Swing/AWT rendering loop that drives the interactive graphic.

The tables below detail each module's public interface, internal components, and dependencies. Use them to trace data flow from the Swing event loop down through the drawable wrappers into the core spatial index, or to understand how the Gradle wrapper in `quadtree-graphic/gradle/wrapper` pins the build environment.
<!-- /alpha8-narrative:overview -->
6 module(s) detected by the ingestion agent. Each row links to a per-module page with its responsibility, public surface, collaborators, and the files inside it.

| Module | Responsibility | Files | Domain hint |
|---|---|---|---|
| [.](root.md) | This top-level directory contains repository-level metadata and documentation for a quadtree data structure project o… | 0 | `Geospatial indexing / quadtree data structures for geolocation queries` |
| [quadtree-graphic](quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the build configuration (`build… | 4 | `build tooling / project scaffolding for a quadtree-based graphics application` |
| [quadtree-graphic/gradle/wrapper](quadtree__graphic__gradle__wrapper.md) | Holds the Gradle Wrapper configuration that pins the Gradle distribution version and download/cache locations for the… | 1 | `Build tooling / project infrastructure` |
| [quadtree-graphic/src/main/java/src](quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application shell and rendering loop for the quadtree graphic visualization. It defi… | 6 | `Interactive 2D graphics / spatial-index visualization (quadtree neighbor search on a world map)` |
| [quadtree-graphic/src/main/java/src/quadtree](quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical/drawable visualization layer over a core QuadTree data structure. It wraps `QuadTree` and `QuadT… | 2 | `Geospatial data visualization (quadtree-based spatial indexing rendering)` |
| [quadtree-graphic/src/main/java/src/quadtree/core](quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial-indexing data structure for storing and querying geographic neighbours by latitude… | 5 | `Geospatial indexing / proximity search` |
