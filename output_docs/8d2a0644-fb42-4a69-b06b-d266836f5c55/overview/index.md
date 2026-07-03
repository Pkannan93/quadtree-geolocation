# Geospatial indexing and visualization using quadtrees (geolocation optimization / efficient spatial queries) Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository demonstrates a quadtree spatial index through an interactive Java/Swing visualization layered over a world map. The core `QuadTree` and `QuadTreeNode` classes provide efficient geographic point insertion and queries—radius searches, rectangle ranges, and nearest-neighbor lookups—while drawable adapter classes (`DrawableQuadTree`, `DrawableQuadTreeNode`) translate the index structure into on-screen subdivisions. A Swing shell (`Main`, `CanvasPanel`, `MainScreen`) hosts the canvas with zoom, pan, and mouse-driven nearest-neighbor queries, and a background thread continuously inserts random lat/lon points to illustrate the tree subdividing in real time.

The system is organized as a single Gradle module with distinct package layers: `quadtree/core` holds the spatial-index primitives, `quadtree` wraps them for rendering, and `src` contains the UI shell. Build automation relies on the bundled Gradle wrapper to ensure reproducible cross-platform compilation.

The tables below catalog 21 tracked files across six logical modules (including repository metadata, wrapper configuration, and source packages) and enumerate the key classes that drive indexing, visualization, and user interaction. Use them to navigate the codebase and understand how the layers fit together.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** An interactive Java/Swing demonstration application for visualizing a quadtree spatial index over a world map. The core spatial data structure lives in `quadtree-graphic/src/main/java/src/quadtree/core` (exposing `QuadTree`, `QuadTreeNode`, `Neighbour`, and `QuadTreeConstants` for adding geographic points and performing radius/rectangle range queries), and is wrapped for rendering by `quadtree-graphic/src/main/java/src/quadtree` (`DrawableQuadTree`, `DrawableQuadTreeNode`). The Swing shell in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `MainScreen`, `Screen`, `Drawable`, `BaseObject`) hosts the canvas, drives zoom/pan and mouse-based nearest-neighbor queries, and runs a background thread that continuously inserts random points to illustrate the index growing in real time. Although the dependency-graph block records no edges (each directory is reported as isolated, yielding a single flat layer), at the source level the rendering shell consumes the drawable wrappers, which in turn consume the core quadtree package. The remaining directories (`.`, `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`) supply only repository metadata and Gradle build/wrapper infrastructure.

**Architecture style.** layered desktop application (Swing UI shell over a drawable adapter over a core spatial-index library), packaged as a single Gradle module

**Primary domain.** Geospatial indexing and visualization using quadtrees (geolocation optimization / efficient spatial queries)

## Key capabilities

- Quadtree-based spatial indexing of geographic (lat/lon) points
- Radius and rectangle range queries plus nearest-neighbor lookup
- Interactive 2D visualization of the quadtree subdivision over a world map with zoom, pan, and mouse interaction
- Live insertion of random points via a background thread to demonstrate index behavior
- Reproducible cross-platform build via the bundled Gradle wrapper

## Business capabilities

### `build tooling / gradle wrapper configuration`

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic subproject, declaring which Gradle distribution version to download and where to cache it locally so the project can be built reproducibly without a pre-installed Gradle. This module is isolated with no inter-module dependencies.

### `build tooling / project infrastructure for a quadtree graphics application`

- **quadtree-graphic** — Provides Gradle build infrastructure for the quadtree-graphic project, including the build configuration (`build.gradle`), project settings (`settings.gradle`), and cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) that allow bootstrapping the build on Unix and Windows without a pre-installed Gradle. Targets Java 1.8 with JUnit for testing. This module is isolated in the dependency graph and serves purely as the build harness for the quadtree-graphic codebase.

### `geospatial data visualization / quadtree spatial indexing`

- **quadtree** — Provides drawable/visualization wrappers around the core quadtree data structures, enabling rendering of quadtree spatial subdivisions and neighbor relationships onto a graphics canvas. `DrawableQuadTree` delegates drawing operations to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` with rendering logic for geographic spatial data and neighbor points. This module is currently isolated in the dependency graph (no internal fan-in or fan-out), bridging the core quadtree implementation with a `Drawable` rendering interface.

### `geospatial indexing / quadtree spatial data structures`

- **core** — Provides the core quadtree spatial-indexing data structure for geographic points (latitude/longitude). It defines the `Neighbour` abstraction and its `NeighbourImpl` data holder, the top-level `QuadTree` API for adding/removing points and performing radius-based range queries, the recursive `QuadTreeNode` that subdivides 2D space into quadrants and stores neighbors at leaf nodes, and shared configuration plus coordinate-conversion utilities in `QuadTreeConstants`. The module is self-contained (isolated in the dependency graph) and exposes a reusable spatial index intended to be consumed by higher-level quadtree/graphic layers.

### `geospatial indexing / quadtree-based geolocation optimization`

- **Root project directory containing only repository metadata: a `** — Root project directory containing only repository metadata: a `.gitignore` for excluding untracked files, an Apache License 2.0 `LICENSE` file, and a `README.md` documenting a quadtree implementation intended for geolocation optimization and efficient spatial queries. No source code resides at this level, and the module is isolated in the dependency graph.

### `interactive 2d spatial-data (quadtree) visualization / geographic point indexing demo`

- **src** — Provides the top-level Swing application shell and rendering framework for a quadtree visualization tool. It defines the application entry point (`Main`), a double-buffered interactive `CanvasPanel` with zoom/pan and input handling, a generic `Screen` container of `Drawable` objects, and the concrete `MainScreen` which renders a quadtree over a world map image, supports mouse-driven nearest-neighbor queries, and runs a background thread that continuously inserts random points. `BaseObject` and the `Drawable` interface provide the abstract primitives that all rendered elements build on. This module is isolated in the dependency graph (no fan-in/fan-out recorded), though at the source level `MainScreen` consumes `src.quadtree.DrawableQuadTree`, `QuadTree`, and `Neighbour` from a sibling quadtree package.

## Where to next

- [Architecture diagram](architecture-diagram.md) — the system Mermaid and a module breakdown.
- [Codebase Guide](../guide/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](../quality/index.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
