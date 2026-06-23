# Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository provides a quadtree spatial index for geographic point data, packaged with an interactive visualization that demonstrates proximity search over latitude and longitude coordinates. The core data structure in `quadtree/core` implements `QuadTree` and `QuadTreeNode` for efficient insertion and radius-based neighbor queries, converting kilometer distances to degree thresholds for geographic search. The architecture follows a three-layer pattern: a self-contained spatial index, a drawable adapter (`DrawableQuadTree` and `DrawableQuadTreeNode`) that renders the tree structure, and a Swing-based presentation shell (`Main`, `CanvasPanel`, `MainScreen`) that overlays the quadtree on a world map and responds to mouse-driven queries.

The system's key capability is real-time proximity search: users click the map canvas to trigger neighbor lookups within a configurable radius, and the application renders both the underlying quadtree structure and the resulting neighbor set. The `quadtree-graphic` module bundles this functionality with Gradle tooling for cross-platform builds and distribution.

The tables below catalog the concrete classes, configurations, and build artifacts that compose each layer, offering drill-down paths into the spatial index, the drawable adapters, and the interactive application shell.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements and visualizes a quadtree spatial index for geolocation queries. The core data structure lives in `quadtree-graphic/src/main/java/src/quadtree/core`, which provides `QuadTree`, `QuadTreeNode`, `Neighbour`/`NeighbourImpl`, and `QuadTreeConstants` for inserting geographic points and performing range/radius searches in kilometers. The `quadtree-graphic/src/main/java/src/quadtree` module adapts these core types into `DrawableQuadTree`/`DrawableQuadTreeNode` renderers, and the top-level Swing application in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `MainScreen`) composes them into an interactive demo that overlays a quadtree on a world map and runs neighbor searches in response to mouse input. The `quadtree-graphic` root and its `gradle/wrapper` subdirectory provide Gradle build tooling, while the repository root holds only project metadata (README, LICENSE). The supplied graph reports no extracted edges, but the directory structure implies a clean unidirectional flow from core → drawable adapter → application shell.

**Architecture style.** layered application with a reusable core library (presentation shell over a drawable adapter over a self-contained spatial-index core)

**Primary domain.** Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points)

## Key capabilities

- Quadtree-based spatial indexing of geographic points (latitude/longitude)
- Radius/range neighbor search with kilometer-to-degree conversion
- Interactive 2D visualization of the quadtree and query results over a world map
- Mouse-driven proximity queries in a Swing/AWT canvas application
- Gradle-based build and distribution tooling for cross-platform execution

## Business capabilities

### `build tooling / gradle configuration`

- **wrapper** — Configures the Gradle wrapper for the quadtree-graphic project, specifying which Gradle distribution version and download source to use so that builds run consistently across developer machines without requiring a pre-installed Gradle. This module is isolated and has no inter-module dependencies — it is purely build tooling configuration.

### `build tooling / project configuration for a quadtree graphics application`

- **quadtree-graphic** — Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the project settings, build script targeting Java 1.8 with JUnit testing, and the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) for executing builds on Unix and Windows without a pre-installed Gradle. This module is isolated in the dependency graph and serves purely as the build/tooling configuration layer.

### `geospatial indexing / spatial data structures`

- **.** — This is the root module of a standalone repository containing a quadtree data structure implementation for geolocation optimization and spatial indexing. It currently holds only project-level metadata files: a `.gitignore` for version control exclusions, an Apache 2.0 `LICENSE`, and a `README.md` documenting the quadtree concept, algorithm, and usage examples for proximity queries. The module is isolated with no inter-module dependencies in the supplied graph, suggesting actual implementation code resides elsewhere or has yet to be added.
- **core** — Provides the core quadtree spatial data structure for indexing and querying geographic entities (neighbours) by latitude/longitude. Defines the `Neighbour` abstraction and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that partitions space and supports add/remove/range-search, the top-level `QuadTree` facade that exposes add and range-query operations (including km-based range conversion), and `QuadTreeConstants` holding tuning parameters such as max node capacity and km-to-degree conversion factors. The module is self-contained (isolated in the dependency graph) and serves as a reusable spatial index library.

### `interactive 2d graphics / spatial data-structure visualization (quadtree neighbor search over a geographic map)`

- **src** — Provides the top-level Swing/AWT application scaffolding for the quadtree visualization: bootstraps the window (`Main`), hosts a double-buffered rendering canvas with input handling (`CanvasPanel`), defines base abstractions for drawable scene objects (`BaseObject`, `Drawable`, `Screen`), and implements `MainScreen` which renders a world map, overlays an interactive quadtree, and performs radius-based neighbor searches in response to mouse input. This module is the application's entry layer and presentation shell, composing lower-level quadtree data structures into a visual demo.

### `spatial data structure visualization / graphical rendering of quadtrees`

- **quadtree** — Provides a drawable/visualizable adapter layer over the core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, enabling rendering of quadtree boundaries and neighbor points on a graphical canvas with configurable scale factors.

## Where to next

- [Architecture diagram](architecture-diagram.md) — the system Mermaid and a module breakdown.
- [Codebase Guide](../guide/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](../quality/index.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
