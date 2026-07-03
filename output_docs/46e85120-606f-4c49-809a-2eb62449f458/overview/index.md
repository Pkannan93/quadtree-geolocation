# Geospatial indexing and visualization via quadtrees Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository provides a quadtree-based geospatial indexing library together with an interactive Swing demonstration. The core spatial data structure—`QuadTree`, `QuadTreeNode`, and supporting classes in the `quadtree.core` package—handles latitude/longitude insertion and radius-based neighbor search. A graphical adapter layer (`DrawableQuadTree`, `DrawableQuadTreeNode`) extends these core types with Java2D rendering, and the application shell (`Main`, `CanvasPanel`, `MainScreen`) bootstraps a JFrame that loads a world map, scatters approximately ten million random points into the tree, and supports interactive proximity queries with pan and zoom.

The architecture follows a three-tier pattern: the core indexing logic is independent of rendering concerns, a drawable adapter adds visualization capabilities, and the Swing UI shell wires everything together. Geographic unit conversion utilities translate kilometers to degrees for search operations. The entire codebase lives in a single Gradle project under `quadtree-graphic`, with wrapper configuration in `gradle/wrapper`.

The tables below enumerate modules, classes, and configuration files detected across twenty-one source files. Use them to navigate the layer boundaries and understand how quadtree subdivision, neighbor relationships, and mouse-driven queries combine to visualize spatial indexing over millions of points.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements a quadtree-based geospatial indexing library together with an interactive Swing demo that visualizes it. The core spatial data structure lives in `quadtree-graphic/src/main/java/src/quadtree/core` (`QuadTree`, `QuadTreeNode`, `Neighbour`/`NeighbourImpl`, `QuadTreeConstants`), which provides latitude/longitude insertion and radius-based neighbor search. A graphical adapter layer in `quadtree-graphic/src/main/java/src/quadtree` (`DrawableQuadTree`, `DrawableQuadTreeNode`) extends the core types with Java2D rendering. The application shell in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `MainScreen`, `Screen`, `BaseObject`, `Drawable`) bootstraps a JFrame, loads a world map, scatters ~10 million random points into the quadtree, and performs interactive proximity queries with pan/zoom. Surrounding modules (`quadtree-graphic` root, `gradle/wrapper`) provide Gradle build scaffolding. Note: the dependency graph reports zero edges and a single flat layer, which reflects that module-extraction did not resolve cross-package Java imports rather than true isolation — the code logically layers core → drawable → app shell.

**Architecture style.** layered library with demo application (core data structure → drawable adapter → Swing UI shell), packaged as a single-project Gradle build

**Primary domain.** Geospatial indexing and visualization via quadtrees

## Key capabilities

- Quadtree-based spatial indexing of latitude/longitude points
- Radius-based nearest-neighbor / proximity search
- Geographic unit conversion utilities (e.g., kilometers to degrees)
- Java2D rendering of quadtree subdivisions and neighbor relationships
- Interactive Swing visualization with pan, zoom, and mouse-driven queries over millions of points

## Business capabilities

### `build tooling / gradle wrapper configuration`

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution to version 8.10.2 and defining download URLs, local storage locations, and validation settings so all developers and CI environments build with a consistent Gradle version. This module is isolated in the dependency graph and serves purely as build-tool bootstrapping metadata.

### `build tooling / project scaffolding for a quadtree visualization application`

- **quadtree-graphic** — Provides the Gradle build infrastructure for a standalone `quadtree-graphic` project, including build configuration (Java 8 compatibility, JUnit test dependencies), project settings, and Gradle wrapper scripts for both Unix (`gradlew`) and Windows (`gradlew.bat`) environments. This module is isolated in the dependency graph and contains only build/scaffolding artifacts — no source code is present in this directory.

### `geospatial indexing / quadtree spatial data structures`

- **Top-level project root for a quadtree-based geolocation optimization library** — Top-level project root for a quadtree-based geolocation optimization library. Contains only repository metadata: licensing (Apache 2.0), Git ignore rules, and the README documenting the spatial indexing data structure with usage examples and visualizations. No source code lives directly at this level; this directory frames and documents the library as a whole.

### `geospatial indexing / spatial data structures`

- **core** — Provides the core quadtree spatial index implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` entity contract and its `NeighbourImpl` implementation, the recursive `QuadTreeNode` for spatial partitioning, the top-level `QuadTree` facade exposing insertion and proximity search, and `QuadTreeConstants` utilities for unit conversions (e.g., kilometers to degrees). This module is self-contained (isolated in the dependency graph) and serves as the underlying spatial data structure to be consumed by higher-level graphic/visualization layers.

### `interactive geospatial visualization / quadtree demo ui`

- **src** — Provides the Swing-based graphical application shell for the quadtree visualization demo. It defines the rendering framework (`Drawable` interface, `BaseObject` base class, `Screen` collection manager), the interactive `CanvasPanel` with its dedicated render thread handling pan/zoom and mouse/keyboard input, and the `MainScreen` which loads a world map, scatters 10 million random points into a quadtree, and performs radius-based neighbor searches on mouse interaction. `Main` bootstraps the `JFrame` and wires `CanvasPanel` into it.

### `spatial indexing / 2d graphical visualization of quadtrees`

- **quadtree** — Provides a graphical/drawable layer over the core quadtree data structure by extending `QuadTree` and `QuadTreeNode` with Java2D rendering capabilities. It renders quadtree node boundaries as rectangles and visualizes neighbor relationships with zoom-level-dependent detail, while delegating spatial indexing operations (subdivision, neighbor lookup) to the underlying core quadtree implementation.

## Where to next

- [Architecture diagram](architecture-diagram.md) — the system Mermaid and a module breakdown.
- [Codebase Guide](../guide/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](../quality/index.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
