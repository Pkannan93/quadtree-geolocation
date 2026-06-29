# Geospatial indexing and visualization (quadtree-based geographic neighbour search) Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / gradle wrapper configuration`

Modules participating in the 'build tooling / gradle wrapper configuration' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and specifying where the wrapper downloads and stores the Gradle distribution. This ensures all developers and CI environments build the project with a consistent Gradle version without requiring a pre-installed Gradle binary. The module is isolated with no inter-module dependencies.

## `build tooling / project infrastructure (graphical quadtree application)`

Modules participating in the 'build tooling / project infrastructure (graphical quadtree application)' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **Provides the Gradle build infrastructure for the `quadtree-graphic` project** — Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) for Unix and Windows that bootstrap the Gradle build tool, along with `build.gradle` defining project metadata, Java source compatibility, repositories, and dependencies, and `settings.gradle` declaring the root project name. This module is isolated in the dependency graph — it does not import from or get imported by other code modules; it exists purely as build/tooling scaffolding.

## `geospatial data structures (quadtree-based location indexing)`

Modules participating in the 'geospatial data structures (quadtree-based location indexing)' domain.

**Modules in this context:**

- `.`

**Capabilities (1):**

- **.** — Top-level repository root containing project metadata, licensing, and documentation for a quadtree data structure implementation aimed at geolocation optimization. It hosts the Apache License 2.0 (`LICENSE`), Git ignore rules (`.gitignore`), and the `README.md` which explains quadtree theory and demonstrates spatial partitioning usage for geographical queries. This directory itself contains no source code and has no module dependencies.

## `geospatial indexing / spatial search (quadtree for geographic neighbour lookup)`

Modules participating in the 'geospatial indexing / spatial search (quadtree for geographic neighbour lookup)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (1):**

- **core** — Provides the core quadtree spatial indexing engine: defines the `Neighbour` abstraction for geo-located entities (id, latitude, longitude), a concrete `NeighbourImpl` data holder, and the recursive `QuadTreeNode` that partitions latitude/longitude space and stores neighbours at leaves. The top-level `QuadTree` covers the full Earth coordinate range and exposes operations to add neighbours and query them within a kilometre-based range (`addNeighbour`, `findNeighbours`, `findNeighboursIds`, `getRangeAsRectangle`), relying on `QuadTreeConstants` for km-to-degree conversions and coordinate normalization. The module is self-contained (isolated in the dependency graph) and acts as the reusable spatial-search backbone for the quadtree-graphic application.

## `spatial data visualization (quadtree-based geographic rendering)`

Modules participating in the 'spatial data visualization (quadtree-based geographic rendering)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **quadtree** — Provides graphical/visual rendering capabilities for quadtree data structures by extending the core quadtree types (`QuadTree`, `QuadTreeNode`) with `Drawable`-compatible subclasses. `DrawableQuadTree` wraps a `DrawableQuadTreeNode` root with scaling parameters and delegates draw/update operations, while `DrawableQuadTreeNode` maps geographic longitude/latitude coordinates to screen coordinates and recursively renders nodes and their neighbours using Java AWT graphics.

## `spatial indexing visualization / interactive geographic data rendering`

Modules participating in the 'spatial indexing visualization / interactive geographic data rendering' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — Provides the Swing/AWT-based graphical application shell for visualizing a quadtree spatial index. It defines the window entry point (`Main`), the rendering surface and input handling (`CanvasPanel`), the scene composition and demo logic that populates 10M geographic neighbors and runs interactive radius searches (`MainScreen`), and base abstractions for drawable entities (`Drawable`, `BaseObject`, `Screen`). The module is isolated in the dependency graph but internally depends on a `src.quadtree` package for the underlying quadtree data structure (`QuadTree`, `Neighbour`, `DrawableQuadTree`).
