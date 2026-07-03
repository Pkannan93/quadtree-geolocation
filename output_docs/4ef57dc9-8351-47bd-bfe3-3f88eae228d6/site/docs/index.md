# Geospatial indexing and proximity search with interactive visualization Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository implements a quadtree spatial index for geolocation queries and provides an interactive Swing desktop application to visualize it. The architecture follows a three-layer design: a core spatial-indexing module (`quadtree.core`) that handles latitude-longitude insertion and radius-based neighbour lookups, a drawable adapter layer that wraps `QuadTree` and `QuadTreeNode` with rendering contracts, and a Swing UI shell that hosts a zoomable canvas over a world-map backdrop. The system supports mouse-driven proximity searches measured in kilometers and renders both quadtree node boundaries and the resulting neighbour points in real time.

The core capability is efficient nearest-neighbour lookup using a recursive quadtree decomposition of geographic space. `DrawableQuadTree` and `DrawableQuadTreeNode` bridge the gap between the raw data structure and the AWT graphics pipeline, while `Main`, `CanvasPanel`, and `MainScreen` orchestrate user interaction—generating random points, dispatching queries on clicks, and managing pan and zoom gestures. The build is anchored by a Gradle wrapper configuration under `quadtree-graphic/gradle/wrapper`, ensuring reproducible JUnit 5 test runs and consistent toolchain versions.

The tables and lists below enumerate modules, key classes, and test coverage. Use them to locate specific entry points or to trace how a query flows from mouse event through the drawable layer into the core quadtree logic.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements a quadtree spatial index for geolocation queries and provides an interactive Swing/AWT visualization of it. The core data structure lives in `quadtree-graphic/src/main/java/src/quadtree/core`, exposing `QuadTree`, `QuadTreeNode`, and the `Neighbour`/`NeighbourImpl` abstractions for inserting geographic points and performing radius-based neighbour lookups in kilometers. A rendering layer in `quadtree-graphic/src/main/java/src/quadtree` wraps these with `DrawableQuadTree` and `DrawableQuadTreeNode` that implement a `Drawable` contract. The top-level application shell in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `MainScreen`, `Screen`, `BaseObject`) hosts a JFrame with a zoom/pan canvas over a world-map background, generates random points, and dispatches mouse-driven neighbour queries against the quadtree. Build and wrapper tooling under `quadtree-graphic` and `quadtree-graphic/gradle/wrapper` provides reproducible Gradle 11/JUnit 5 builds.

**Architecture style.** layered desktop application (spatial-core → drawable adapter → Swing UI shell) with separate Gradle build-tooling roots

**Primary domain.** Geospatial indexing and proximity search with interactive visualization

## Key capabilities

- Quadtree-based spatial indexing of geographic points by latitude/longitude
- Radius-based nearest-neighbour lookups in kilometers
- Interactive Swing/AWT visualization with zoom, pan, and mouse-driven queries
- Rendering of quadtree node boundaries and neighbour points over a world-map backdrop
- Reproducible Gradle wrapper build with JUnit 5 test support

## Business capabilities

### `build tooling / gradle configuration`

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL and version along with file system paths for the wrapper's base directory, zip storage, and JAR location. This enables reproducible Gradle builds across environments without requiring a pre-installed Gradle distribution.

### `build tooling / project scaffolding for a quadtree graphics application`

- **quadtree-graphic** — Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the root project settings, Java 11 compilation configuration, JUnit 5 test dependency wiring, and the cross-platform Gradle wrapper scripts (`gradlew` for Unix, `gradlew.bat` for Windows) used to bootstrap builds. This module is an isolated build-tooling root with no runtime code dependencies on or from other modules in the graph.

### `geospatial indexing / geolocation optimization via quadtree data structures`

- **.** — Top-level project metadata for a quadtree data structure implementation aimed at geolocation optimization. Contains only repository-level artifacts (`.gitignore`, `LICENSE` under Apache 2.0, and `README.md` describing the quadtree's purpose and usage) with no source code or runtime dependencies. Serves as the documentation and licensing entry point for the project.

### `geospatial indexing / proximity search`

- **core** — Provides the core QuadTree spatial indexing implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` abstraction (interface plus `NeighbourImpl`) representing points with an ID and coordinates, and exposes a `QuadTree` facade backed by recursive `QuadTreeNode` subdivision to support insertion and radius-based neighbor lookups (in kilometers, converted via `QuadTreeConstants`). This module is self-contained (isolated in the dependency graph) and offers the reusable spatial data structure that other layers of the quadtree-graphic application would build upon.

### `interactive graphical visualization of a quadtree spatial index over geographic points`

- **src** — Provides the top-level Swing/AWT application shell for the quadtree visualization: bootstraps the JFrame (`Main`), hosts a game-loop rendering canvas with zoom/pan and input handling (`CanvasPanel`), and defines the `Screen`/`Drawable`/`BaseObject` abstractions that structure renderable entities. Its concrete `MainScreen` composes a `DrawableQuadTree` over a world-map background, generates random points, and dispatches mouse-driven neighbour queries against the underlying `QuadTree`.

### `spatial data structure visualization / graphics rendering`

- **Provides drawable/visualizable extensions of the core quadtree data structure** — Provides drawable/visualizable extensions of the core quadtree data structure. `DrawableQuadTree` extends the base `QuadTree` and delegates rendering to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` and implements `Drawable` to render node boundaries and neighbor points on screen (with zoom-dependent detail). This module is isolated in the dependency graph and serves as a visualization layer over an external quadtree core.

## Where to next

- [Architecture](architecture.md) — the system Mermaid diagram and a module breakdown.
- [Modules](modules/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](quality.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
