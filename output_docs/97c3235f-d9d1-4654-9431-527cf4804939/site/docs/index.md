# Geospatial indexing and visualization (quadtree-based geographic neighbour search) Documentation

<!-- alpha8-narrative:overview -->
## Overview

This repository delivers a quadtree-based spatial indexing engine for geographic coordinates, paired with a Swing desktop application that visualizes partitions and neighbour searches across large datasets. The architecture follows a layered model: the `quadtree.core` package provides the reusable indexing primitives—`QuadTree`, `QuadTreeNode`, and kilometre-radius lookup logic that partitions Earth's latitude and longitude space—while the `quadtree` drawable extension layer wraps those types with AWT rendering capabilities, and a thin Swing shell in `Main` and `CanvasPanel` composes the interactive demo.

At the heart of the system is kilometre-radius neighbour lookup, which converts physical distance into degree-based bounding boxes and queries the quadtree for nearby points. The demo scenario loads roughly 10 million geographic neighbours, exercising the index at scale and demonstrating both the spatial partitioning and the rendering pipeline. The core library remains independent of UI concerns, making it straightforward to extract for server-side or batch use cases.

The tables and lists below enumerate the detected modules, key classes, and capabilities. Use them to identify entry points—`QuadTree` for indexing logic, `DrawableQuadTree` for visualization—and understand which files correspond to core algorithms versus application scaffolding.
<!-- /alpha8-narrative:overview -->
_Source: `https://github.com/Pkannan93/quadtree-geolocation.git` @ `a1b444ae134e`_

**Purpose.** This repository implements a quadtree-based geospatial indexing system with an interactive graphical visualization. The core spatial engine lives in `quadtree-graphic/src/main/java/src/quadtree/core`, which provides `QuadTree`, `QuadTreeNode`, `Neighbour`, and `QuadTreeConstants` to partition the Earth's latitude/longitude space and answer kilometre-radius neighbour queries. The `quadtree-graphic/src/main/java/src/quadtree` module extends those core types with AWT-drawable variants (`DrawableQuadTree`, `DrawableQuadTreeNode`) that map geographic coordinates to screen space. The Swing application shell in `quadtree-graphic/src/main/java/src` (`Main`, `CanvasPanel`, `MainScreen`) composes these pieces into a demo that loads 10M geographic neighbours and runs interactive radius searches. Build tooling in `quadtree-graphic` and `quadtree-graphic/gradle/wrapper` provides Gradle-based project scaffolding. The graph block reports no detected edges (top_fan_in and top_fan_out are empty and all modules sit in a single layer), so the architectural spine is inferred from package conventions rather than measured imports.

**Architecture style.** layered (core → drawable extension → application shell), packaged as a single Gradle-built desktop application

**Primary domain.** Geospatial indexing and visualization (quadtree-based geographic neighbour search)

## Key capabilities

- Quadtree spatial partitioning over global latitude/longitude coordinates
- Kilometre-radius neighbour lookup with km-to-degree conversion
- Interactive Swing/AWT visualization of the quadtree and its contents
- Large-scale demo handling on the order of 10M geographic points
- Reusable core spatial-search library independent of rendering

## Business capabilities

### `build tooling / gradle wrapper configuration`

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and specifying where the wrapper downloads and stores the Gradle distribution. This ensures all developers and CI environments build the project with a consistent Gradle version without requiring a pre-installed Gradle binary. The module is isolated with no inter-module dependencies.

### `build tooling / project infrastructure (graphical quadtree application)`

- **Provides the Gradle build infrastructure for the `quadtree-graphic` project** — Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) for Unix and Windows that bootstrap the Gradle build tool, along with `build.gradle` defining project metadata, Java source compatibility, repositories, and dependencies, and `settings.gradle` declaring the root project name. This module is isolated in the dependency graph — it does not import from or get imported by other code modules; it exists purely as build/tooling scaffolding.

### `geospatial data structures (quadtree-based location indexing)`

- **.** — Top-level repository root containing project metadata, licensing, and documentation for a quadtree data structure implementation aimed at geolocation optimization. It hosts the Apache License 2.0 (`LICENSE`), Git ignore rules (`.gitignore`), and the `README.md` which explains quadtree theory and demonstrates spatial partitioning usage for geographical queries. This directory itself contains no source code and has no module dependencies.

### `geospatial indexing / spatial search (quadtree for geographic neighbour lookup)`

- **core** — Provides the core quadtree spatial indexing engine: defines the `Neighbour` abstraction for geo-located entities (id, latitude, longitude), a concrete `NeighbourImpl` data holder, and the recursive `QuadTreeNode` that partitions latitude/longitude space and stores neighbours at leaves. The top-level `QuadTree` covers the full Earth coordinate range and exposes operations to add neighbours and query them within a kilometre-based range (`addNeighbour`, `findNeighbours`, `findNeighboursIds`, `getRangeAsRectangle`), relying on `QuadTreeConstants` for km-to-degree conversions and coordinate normalization. The module is self-contained (isolated in the dependency graph) and acts as the reusable spatial-search backbone for the quadtree-graphic application.

### `spatial data visualization (quadtree-based geographic rendering)`

- **quadtree** — Provides graphical/visual rendering capabilities for quadtree data structures by extending the core quadtree types (`QuadTree`, `QuadTreeNode`) with `Drawable`-compatible subclasses. `DrawableQuadTree` wraps a `DrawableQuadTreeNode` root with scaling parameters and delegates draw/update operations, while `DrawableQuadTreeNode` maps geographic longitude/latitude coordinates to screen coordinates and recursively renders nodes and their neighbours using Java AWT graphics.

### `spatial indexing visualization / interactive geographic data rendering`

- **src** — Provides the Swing/AWT-based graphical application shell for visualizing a quadtree spatial index. It defines the window entry point (`Main`), the rendering surface and input handling (`CanvasPanel`), the scene composition and demo logic that populates 10M geographic neighbors and runs interactive radius searches (`MainScreen`), and base abstractions for drawable entities (`Drawable`, `BaseObject`, `Screen`). The module is isolated in the dependency graph but internally depends on a `src.quadtree` package for the underlying quadtree data structure (`QuadTree`, `Neighbour`, `DrawableQuadTree`).

## Where to next

- [Architecture](architecture.md) — the system Mermaid diagram and a module breakdown.
- [Modules](modules/index.md) — every directory the ingestion agent treated as a unit, with its responsibility and public surface.
- [Quality](quality.md) — observability into what the run captured (routes, entities, embeddings) and what it skipped.
