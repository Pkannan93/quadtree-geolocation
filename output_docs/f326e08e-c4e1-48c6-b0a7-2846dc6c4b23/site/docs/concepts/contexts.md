# Geospatial indexing and proximity search visualization Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / gradle wrapper configuration`

Modules participating in the 'build tooling / gradle wrapper configuration' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Provides the Gradle wrapper configuration for the `quadtree-graphic` project, specifying which Gradle distribution version to download, where to fetch it from, and where to cache the distribution and wrapper files locally. This module is isolated in the dependency graph and serves purely as build tooling configuration consumed by the Gradle wrapper scripts.

## `build tooling / project scaffolding for a quadtree graphics application`

Modules participating in the 'build tooling / project scaffolding for a quadtree graphics application' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **Gradle-based Java project scaffolding for a `quadtree-graphic` application** — Gradle-based Java project scaffolding for a `quadtree-graphic` application. Provides the build configuration (`build.gradle` with Java 8 compatibility and JUnit test dependency), project naming (`settings.gradle`), and cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) so the project can be built consistently on Unix and Windows without a pre-installed Gradle. This module is isolated in the dependency graph and represents the build/tooling layer rather than runtime source code.

## `geospatial indexing / geolocation (quadtree-based spatial data structures)`

Modules participating in the 'geospatial indexing / geolocation (quadtree-based spatial data structures)' domain.

**Modules in this context:**

- `.`

**Capabilities (1):**

- **Top-level project root containing only meta and documentation files: a `** — Top-level project root containing only meta and documentation files: a `.gitignore` for VCS hygiene, an Apache License 2.0 `LICENSE` file, and a `README.md` describing a quadtree data structure implementation aimed at geolocation optimization. This directory does not contain executable code itself; per the graph it is isolated with no fan-in or fan-out, serving purely as the project's entry-point documentation and licensing layer.

## `geospatial indexing / proximity search`

Modules participating in the 'geospatial indexing / proximity search' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (1):**

- **core** — Provides the core quadtree spatial indexing implementation for geographic point data. Defines a `Neighbour` abstraction (id + latitude/longitude) with a concrete `NeighbourImpl`, recursively subdivides 2D space via `QuadTreeNode`, and exposes a top-level `QuadTree` API for inserting neighbours and performing range queries by lat/lon. `QuadTreeConstants` centralizes tuning parameters and km↔degree conversion utilities used during spatial searches. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial-indexing engine for the surrounding quadtree-graphic application.

## `spatial data structure visualization (quadtree rendering for 2d graphics)`

Modules participating in the 'spatial data structure visualization (quadtree rendering for 2d graphics)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **quadtree** — Provides a graphical/drawable adapter layer over a core quadtree data structure, enabling visualization of quadtree nodes, their spatial bounds, and neighbour relationships within a graphics system. `DrawableQuadTree` wraps a `QuadTree` and delegates draw/update calls to a root `DrawableQuadTreeNode`, which extends `QuadTreeNode` to add rendering of boundaries and neighbour links via `Rectangle2D`. The module is isolated in the dependency graph but logically depends on a core quadtree package and a `Drawable` abstraction.

## `spatial data structure visualization / geographic neighbor search`

Modules participating in the 'spatial data structure visualization / geographic neighbor search' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — Provides the top-level Swing/AWT graphical application for visualizing a quadtree of geographic points on a world map. It defines the application entry point (`Main`), the rendering surface and input loop (`CanvasPanel`), a screen abstraction (`Screen`) with a concrete `MainScreen` that loads the world map image, populates a quadtree, and handles mouse-driven radius neighbor searches with performance display. Also defines core drawable abstractions (`Drawable` interface and `BaseObject` base class) used by visual elements. This module is isolated in the dependency graph but internally relies on a `src.quadtree` package for the quadtree data structure and rendering.
