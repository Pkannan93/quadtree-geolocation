# Geospatial indexing and visualization (quadtree-based location services) Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository delivers a quadtree-based spatial index for geolocation queries, organized as a layered modular monolith with a reusable core engine, a visualization adapter, and a Swing-based demonstration UI. The architecture separates concerns cleanly: the `quadtree-graphic/src/main/java/src/quadtree/core` package houses the engine—`QuadTree`, `QuadTreeNode`, and the `Neighbour` types—that insert latitude/longitude points and execute radius-based proximity searches, while the `quadtree-graphic/src/main/java/src/quadtree` adapter (`DrawableQuadTree`, `DrawableQuadTreeNode`) wraps these structures for rendering. A standalone Swing application in `quadtree-graphic/src/main/java/src` ties everything together, loading a world map and enabling mouse-driven nearest-neighbor queries with performance reporting.

The quadtree engine uses parameters in `QuadTreeConstants` to control tree depth and subdivision thresholds, making it straightforward to tune for different datasets. The interactive demo visualizes both the spatial subdivisions and the query results in real time, offering zoom, pan, and click-to-query interaction that surfaces how the index partitions geographic space. Gradle wrapper scripts ensure reproducible builds across environments.

The tables and references below catalogue the twenty-one files, six modules, and five key capabilities detected in the repository, organized by layer and role within the system.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements and visually demonstrates a quadtree-based spatial index for geolocation queries. The reusable engine lives in `quadtree-graphic/src/main/java/src/quadtree/core`, where `QuadTree`, `QuadTreeNode`, and the `Neighbour`/`NeighbourImpl` types provide insertion and radius-based proximity search over latitude/longitude points, parameterized by `QuadTreeConstants`. A thin rendering adapter in `quadtree-graphic/src/main/java/src/quadtree` (`DrawableQuadTree`, `DrawableQuadTreeNode`) wraps the core types as `Drawable`s, and the top-level application package `quadtree-graphic/src/main/java/src` bootstraps a Swing/AWT demo (`Main`, `CanvasPanel`, `MainScreen`) that loads a world map, populates the quadtree, and performs mouse-driven nearest-neighbor queries. Build and wrapper scaffolding under `quadtree-graphic` and `quadtree-graphic/gradle/wrapper` provide reproducible Gradle builds.

**Architecture style.** layered modular monolith (core spatial library + visualization adapter + Swing UI shell, with separate build scaffolding)

**Primary domain.** Geospatial indexing and visualization (quadtree-based location services)

## Key capabilities

- Quadtree-based spatial indexing of geographic points by latitude/longitude
- Radius-based nearest-neighbor / proximity queries
- Interactive 2D visualization of the quadtree and its subdivisions over a map
- Zoom, pan, and mouse-driven query interaction with performance reporting
- Reproducible Gradle build via wrapper scripts

## Business capabilities

### `build tooling / project infrastructure`

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL, version, and local cache/distribution paths. This enables reproducible Gradle builds across environments without requiring developers to pre-install Gradle. The module is isolated with no inter-module dependencies.

### `build tooling / project scaffolding`

- **Build infrastructure scaffolding for the `quadtree-graphic` Java project** — Build infrastructure scaffolding for the `quadtree-graphic` Java project. Provides the Gradle build configuration (`build.gradle`, `settings.gradle`) declaring the Java plugin and JUnit 5 test dependency, plus the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) that bootstrap Gradle on Unix and Windows without a pre-installed distribution. This module is isolated in the dependency graph and serves purely as the build entry point for the project.

### `geospatial data structures / location-based services (quadtree-based spatial indexing)`

- **.** — This is the repository root directory containing only project metadata and documentation files: a `.gitignore` for version control hygiene, an Apache 2.0 `LICENSE`, and a `README.md` that documents a quadtree data structure implementation for geolocation optimization. The module itself contains no executable code; it provides the project-level context, licensing, and developer-facing documentation for a spatial data partitioning library.

### `geospatial indexing / spatial data structures`

- **Provides the core quadtree spatial indexing implementation for geographic data** — Provides the core quadtree spatial indexing implementation for geographic data. Defines the `Neighbour` abstraction (with a concrete `NeighbourImpl`) representing identifiable points by latitude/longitude, and exposes a `QuadTree` that recursively subdivides space via `QuadTreeNode` to support insertion (`addNeighbour`) and radius-based proximity queries (`findNeighbours`, `findNeighboursIds`). `QuadTreeConstants` centralizes configuration such as the minimum node size and degree-to-kilometer conversion. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial indexing engine for the broader quadtree-graphic application.

### `interactive visualization / demo ui for a quadtree spatial-indexing data structure`

- **src** — This module is the top-level application package for a Java Swing/AWT graphical application that visualizes a quadtree spatial data structure over a world map. It bootstraps the JFrame window (`Main`), runs a custom render-loop canvas with zoom/pan and input handling (`CanvasPanel`), and provides the abstract scene-graph primitives (`Drawable` interface, `BaseObject` abstract class, `Screen` container) on top of which `MainScreen` builds an interactive demo that loads a map image, populates a `DrawableQuadTree`, and performs mouse-driven nearest-neighbor queries while reporting performance.

### `spatial data structure visualization / 2d graphics rendering`

- **quadtree** — Provides a graphical visualization layer for the quadtree data structure by wrapping core quadtree types with rendering capability. `DrawableQuadTree` adapts a `QuadTree` to the `Drawable` interface, delegating draw and update calls to a `DrawableQuadTreeNode` root, which extends `QuadTreeNode` to render spatial bounds and neighbor points on a graphics canvas with zoom-dependent detail.

## Where to next

- [Architecture](architecture.md) — the system Mermaid diagram and a module breakdown.
- [Modules](modules/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](quality.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
