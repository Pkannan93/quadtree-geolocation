# Geospatial indexing and proximity search visualization Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository is a small Java desktop application that demonstrates quadtree-based spatial indexing for geographic point data. The architecture follows a three-layer pattern: a core spatial engine in `quadtree.core` implements the tree data structure and distance calculations, a drawable adapter layer wraps tree nodes with rendering logic, and a Swing UI shell presents an interactive world map canvas where users can click to trigger proximity searches.

The core engine offers insertion of lat/lon coordinates and radius-based neighbor lookup with automatic kilometer-to-degree conversion, backed by classes like `QuadTree`, `QuadTreeNode`, and `NeighbourImpl`. The visualization layer—`DrawableQuadTree` and `DrawableQuadTreeNode`—renders quadrant boundaries and highlights matching neighbors on screen, while the top-level `Main`, `CanvasPanel`, and `MainScreen` classes manage the Swing window, load the background map, and wire mouse events to the search API.

The tables and dependency data below detail the twenty-one files, six modules, and key classes that support interactive geospatial queries. Use them to trace how a mouse click flows from the UI through the drawable adapters into the core indexing logic, or to understand how quadrant subdivision accelerates neighbor lookup.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements a quadtree-based spatial indexing system for geolocation optimization, packaged as a small Java Swing desktop application that visualizes geographic neighbor searches on a world map. The core spatial engine lives in `quadtree-graphic/src/main/java/src/quadtree/core` (`QuadTree`, `QuadTreeNode`, `Neighbour`/`NeighbourImpl`, `QuadTreeConstants`) and provides insertion and radius-based lookup of lat/lon points. A drawable adapter layer in `quadtree-graphic/src/main/java/src/quadtree` (`DrawableQuadTree`, `DrawableQuadTreeNode`) wraps the core nodes to render their boundaries and neighbour links, while the top-level Swing application in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `MainScreen`, `Drawable`, `BaseObject`) hosts the canvas, loads the world map, populates the quadtree, and handles interactive mouse-driven proximity queries. The `quadtree-graphic` and `quadtree-graphic/gradle/wrapper` directories supply the Gradle build tooling, and the root directory holds licensing and documentation. The dependency graph reports no captured edges, but the intended layering is clear: core engine → drawable adapter → Swing UI shell.

**Architecture style.** layered desktop application (core spatial engine, drawable adapter layer, Swing UI shell) built as a single Gradle module

**Primary domain.** Geospatial indexing and proximity search visualization

## Key capabilities

- Quadtree-based spatial indexing of geographic (lat/lon) points
- Radius / nearest-neighbour search over indexed points with km↔degree conversion
- Interactive Swing/AWT visualization of quadtree subdivisions and query results on a world map
- Mouse-driven neighbor lookup with on-screen performance feedback
- Reusable Drawable abstraction for rendering quadtree nodes and their boundaries

## Business capabilities

### `build tooling / gradle wrapper configuration`

- **wrapper** — Provides the Gradle wrapper configuration for the `quadtree-graphic` project, specifying which Gradle distribution version to download, where to fetch it from, and where to cache the distribution and wrapper files locally. This module is isolated in the dependency graph and serves purely as build tooling configuration consumed by the Gradle wrapper scripts.

### `build tooling / project scaffolding for a quadtree graphics application`

- **Gradle-based Java project scaffolding for a `quadtree-graphic` application** — Gradle-based Java project scaffolding for a `quadtree-graphic` application. Provides the build configuration (`build.gradle` with Java 8 compatibility and JUnit test dependency), project naming (`settings.gradle`), and cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) so the project can be built consistently on Unix and Windows without a pre-installed Gradle. This module is isolated in the dependency graph and represents the build/tooling layer rather than runtime source code.

### `geospatial indexing / geolocation (quadtree-based spatial data structures)`

- **Top-level project root containing only meta and documentation files: a `** — Top-level project root containing only meta and documentation files: a `.gitignore` for VCS hygiene, an Apache License 2.0 `LICENSE` file, and a `README.md` describing a quadtree data structure implementation aimed at geolocation optimization. This directory does not contain executable code itself; per the graph it is isolated with no fan-in or fan-out, serving purely as the project's entry-point documentation and licensing layer.

### `geospatial indexing / proximity search`

- **core** — Provides the core quadtree spatial indexing implementation for geographic point data. Defines a `Neighbour` abstraction (id + latitude/longitude) with a concrete `NeighbourImpl`, recursively subdivides 2D space via `QuadTreeNode`, and exposes a top-level `QuadTree` API for inserting neighbours and performing range queries by lat/lon. `QuadTreeConstants` centralizes tuning parameters and km↔degree conversion utilities used during spatial searches. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial-indexing engine for the surrounding quadtree-graphic application.

### `spatial data structure visualization (quadtree rendering for 2d graphics)`

- **quadtree** — Provides a graphical/drawable adapter layer over a core quadtree data structure, enabling visualization of quadtree nodes, their spatial bounds, and neighbour relationships within a graphics system. `DrawableQuadTree` wraps a `QuadTree` and delegates draw/update calls to a root `DrawableQuadTreeNode`, which extends `QuadTreeNode` to add rendering of boundaries and neighbour links via `Rectangle2D`. The module is isolated in the dependency graph but logically depends on a core quadtree package and a `Drawable` abstraction.

### `spatial data structure visualization / geographic neighbor search`

- **src** — Provides the top-level Swing/AWT graphical application for visualizing a quadtree of geographic points on a world map. It defines the application entry point (`Main`), the rendering surface and input loop (`CanvasPanel`), a screen abstraction (`Screen`) with a concrete `MainScreen` that loads the world map image, populates a quadtree, and handles mouse-driven radius neighbor searches with performance display. Also defines core drawable abstractions (`Drawable` interface and `BaseObject` base class) used by visual elements. This module is isolated in the dependency graph but internally relies on a `src.quadtree` package for the quadtree data structure and rendering.

## Where to next

- [Architecture](architecture.md) — the system Mermaid diagram and a module breakdown.
- [Modules](modules/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](quality.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
