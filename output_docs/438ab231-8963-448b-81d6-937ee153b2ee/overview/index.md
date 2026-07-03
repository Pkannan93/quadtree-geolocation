# Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository provides a quadtree-based spatial index for latitude/longitude points and an interactive Swing application that visualizes how the structure partitions a world map. The core engine in `quadtree/core` offers `QuadTree`, `QuadTreeNode`, and neighbour-search classes that recursively subdivide geographic coordinates and answer radius-based proximity queries with kilometre-to-degree conversion. A drawable adapter layer wraps these structures so they can render their bounding boxes and query results on screen, and a Swing canvas shell supplies mouse-driven zoom, pan, and double-buffered drawing.

The architecture is a layered Java monolith: data structure → drawable adapter → UI shell, built as a single Gradle artifact via the checked-in wrapper. Because the module graph treats directories as independent units without cross-references, the codebase appears flat rather than hierarchical, though the package layout and class dependencies establish the layering at runtime.

The tables and lists below catalogue every Java source file, configuration, and build artifact detected in the repository. Use them to trace how `QuadTreeConstants` defines subdivision thresholds, how `CanvasPanel` wires keyboard listeners, or how the Gradle wrapper pins the build to a reproducible tool version.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements a quadtree spatial-indexing data structure and an interactive Swing/AWT visualization of it for geolocation neighbour queries. The core engine lives in `quadtree-graphic/src/main/java/src/quadtree/core`, where `QuadTree`, `QuadTreeNode`, `Neighbour`/`NeighbourImpl`, and `QuadTreeConstants` provide a reusable engine for adding latitude/longitude points and finding neighbours within a radius. A drawable adapter layer in `quadtree-graphic/src/main/java/src/quadtree` (`DrawableQuadTree`, `DrawableQuadTreeNode`) renders the tree on screen, and the application shell in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `Screen`, `MainScreen`, `BaseObject`, `Drawable`) hosts a zoom/pan-enabled canvas that overlays the quadtree on a world map. The remaining modules (`quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, and the repo root) supply Gradle build tooling, licensing, and documentation. The module graph is reported as edge-less and flat (a single layer), reflecting that the directories are tracked as independent units rather than via cross-module imports.

**Architecture style.** layered (Java application: core data structure → drawable adapter → Swing UI shell), packaged as a single Gradle-built modular monolith

**Primary domain.** Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points

## Key capabilities

- Quadtree construction and recursive spatial subdivision of geographic coordinates
- Radius-based neighbour search by latitude/longitude (with km-to-degree conversion)
- Interactive 2D visualization of quadtree structure and neighbour queries over a world map
- Zoom, pan, and mouse/keyboard interaction in a double-buffered Swing canvas
- Reproducible Gradle build via wrapper for the visualization application

## Business capabilities

### `build tooling / project infrastructure`

- **wrapper** — Holds the Gradle Wrapper configuration that pins the Gradle distribution version and download/cache locations for the `quadtree-graphic` build, allowing the project to be built reproducibly without a pre-installed Gradle. This module is isolated in the dependency graph and is consumed only by the Gradle build tooling itself.

### `build tooling / project scaffolding for a quadtree-based graphics application`

- **Provides the Gradle build infrastructure for the `quadtree-graphic` project** — Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the build configuration (`build.gradle`) targeting Java 8 with JUnit test dependencies, the project settings file (`settings.gradle`), and cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) that bootstrap the build system on Unix and Windows. This module is isolated in the dependency graph — it contains no application source code, only the tooling required to compile, test, and package the quadtree graphic implementation.

### `geospatial data visualization (quadtree-based spatial indexing rendering)`

- **quadtree** — Provides a graphical/drawable visualization layer over a core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` from `src.quadtree.core` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, rendering quadtree boundaries and neighbour points by scaling latitude/longitude geographic coordinates to screen coordinates.

### `geospatial indexing / proximity search`

- **core** — Provides the core quadtree spatial-indexing data structure for storing and querying geographic neighbours by latitude/longitude. Defines the `Neighbour` contract and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that subdivides space into quadrants, the top-level `QuadTree` facade for adding points and finding neighbours within a radius, and `QuadTreeConstants` for node sizing and km-to-degree conversions. This module is self-contained (isolated in the dependency graph) and serves as a reusable spatial-query engine.

### `geospatial indexing / quadtree data structures for geolocation queries`

- **.** — This top-level directory contains repository-level metadata and documentation for a quadtree data structure project optimized for geolocation queries. It holds the `.gitignore` for version control exclusions, the Apache License 2.0 (`LICENSE`) governing usage terms, and a `README.md` documenting the quadtree implementation with explanations and examples of 2D spatial partitioning for efficient geographic searches. As an isolated module with no code dependencies, it serves purely as the project's entry-point documentation and licensing layer.

### `interactive 2d graphics / spatial-index visualization (quadtree neighbor search on a world map)`

- **src** — Provides the top-level Swing/AWT application shell and rendering loop for the quadtree graphic visualization. It defines the drawable abstractions (`BaseObject`, `Drawable`), a `Screen` container that aggregates and dispatches draw/update calls, a double-buffered `CanvasPanel` that handles the render loop and mouse/keyboard interaction (zoom/pan), the `Main` entry point that boots a `JFrame`, and `MainScreen` which loads a world map image and drives an interactive quadtree neighbor-search visualization.

## Where to next

- [Architecture diagram](architecture-diagram.md) — the system Mermaid and a module breakdown.
- [Codebase Guide](../guide/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](../quality/index.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
