# Geospatial indexing and proximity search with interactive visualization Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository delivers a quadtree-based geospatial indexing engine with an interactive Swing visualizer for exploring spatial queries over geographic coordinates. The core library in `quadtree-graphic/src/main/java/src/quadtree/core` provides `QuadTree` and `QuadTreeNode` classes that partition latitude-longitude points and execute radius-based neighbor searches in kilometers, while a drawable adapter layer extends these structures for rendering. The system is packaged as a single Gradle project with reproducible builds via the bundled wrapper.

At the heart of the implementation lies `QuadTreeConstants`, which defines the km-to-degree conversion and maximum tree depth, and `NeighbourImpl`, which encapsulates the results of proximity queries. The Swing shell—`Main`, `CanvasPanel`, and `MainScreen`—layers an interactive world map canvas on top, supporting pan, zoom, and click-to-search workflows that visualize both the quadtree's hierarchical decomposition and the nearest points to a query location.

The tables and module list below catalog the twenty-one files, six recognized modules, and key class definitions that compose the system. Use them to navigate into the spatial indexing logic, the drawable extensions, or the GUI components as needed.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements a quadtree-based geospatial indexing data structure together with an interactive Swing visualizer. The core library lives in `quadtree-graphic/src/main/java/src/quadtree/core`, which provides `QuadTree`, `QuadTreeNode`, `Neighbour`/`NeighbourImpl`, and `QuadTreeConstants` for inserting geographic points and performing radius-based proximity queries (in kilometers, with km-to-degree conversion). On top of this, `quadtree-graphic/src/main/java/src/quadtree` adds `DrawableQuadTree` and `DrawableQuadTreeNode` rendering extensions, and `quadtree-graphic/src/main/java/src` supplies the application shell (`Main`, `CanvasPanel`, `MainScreen`) implementing a double-buffered, pan/zoom Swing canvas that visualizes the quadtree over a world map and supports interactive neighbor search. The build is driven by a standalone Gradle 4.0 wrapper setup in `quadtree-graphic` and `quadtree-graphic/gradle/wrapper`. The dependency graph is flat (a single layer, no edges), reflecting that module summarization did not capture intra-package Java imports rather than true architectural independence.

**Architecture style.** layered modular Java application (core library + drawable adapter + Swing GUI shell) packaged as a single Gradle project

**Primary domain.** Geospatial indexing and proximity search with interactive visualization

## Key capabilities

- Quadtree-based spatial indexing of geographic points (lat/lon)
- Radius-based nearest-neighbor / proximity search in kilometers
- Drawable adapter layer for rendering quadtree nodes and points
- Interactive Swing visualizer with pan, zoom, and click-to-search over a world map
- Self-contained Gradle wrapper build for reproducible compilation and JUnit testing

## Business capabilities

### `build tooling / gradle wrapper configuration`

- **wrapper** — Provides the Gradle Wrapper configuration for the quadtree-graphic project, pinning the build to Gradle 4.0 via `gradle-wrapper.properties` so that builds run consistently across environments without requiring a locally installed Gradle. This module is isolated in the dependency graph and acts purely as build-tooling configuration.

### `build tooling / quadtree graphics application`

- **quadtree-graphic** — Provides the Gradle build scaffolding for an isolated `quadtree-graphic` project, including the Java plugin configuration with JUnit testing (`build.gradle`), the project naming (`settings.gradle`), and the cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) used to bootstrap and execute builds on Unix and Windows. As an isolated module with no fan-in or fan-out dependencies, it stands alone as a self-contained build harness.

### `geospatial indexing / proximity search`

- **Provides a self-contained quadtree spatial indexing core for geographic data** — Provides a self-contained quadtree spatial indexing core for geographic data. Defines the `Neighbour` abstraction for points with id and lat/lon coordinates (`NeighbourImpl`), recursive node subdivision and search via `QuadTreeNode`, and the public `QuadTree` facade for inserting points and querying neighbors within a kilometer-based radius. `QuadTreeConstants` centralizes minimum node size configuration and km-to-degree conversion. The module is isolated (no internal fan-in/fan-out), making it a standalone library suitable for embedding in spatial-search applications.

### `geospatial indexing / quadtree spatial data structures`

- **.** — Root-level repository metadata for a standalone quadtree-based geolocation data structure project. Contains the Apache 2.0 `LICENSE`, a `README.md` describing the quadtree implementation and its use for spatial/proximity queries on geographic data, and a `.gitignore` for version-control hygiene. This module is isolated in the dependency graph and provides no runtime code surface.

### `interactive geospatial quadtree visualization (swing gui)`

- **src** — Provides the top-level Swing application shell and rendering framework for the quadtree graphic visualizer. It bootstraps the JFrame (`Main`), runs a double-buffered game loop with pan/zoom input handling (`CanvasPanel`), defines the rendering abstractions (`Screen`, `Drawable`, `BaseObject`), and implements the concrete world-map quadtree visualization with random neighbor point generation and interactive search (`MainScreen`). This module is isolated in the dependency graph and serves as the standalone GUI driver layer that consumes the quadtree library internally.

### `spatial data structure visualization (quadtree rendering)`

- **quadtree** — Provides graphical/drawable extensions to a core quadtree data structure for visualization purposes. `DrawableQuadTree` subclasses `QuadTree` and `DrawableQuadTreeNode` subclasses `QuadTreeNode`, both implementing a `Drawable` interface to render node boundaries and contained neighbours as rectangles on a graphics context, with support for coordinate scaling and bounds.

## Where to next

- [Architecture](architecture.md) — the system Mermaid diagram and a module breakdown.
- [Modules](modules/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](quality.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
