# Geospatial indexing and proximity search with interactive visualization Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / gradle wrapper configuration`

Modules participating in the 'build tooling / gradle wrapper configuration' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Provides the Gradle Wrapper configuration for the quadtree-graphic project, pinning the build to Gradle 4.0 via `gradle-wrapper.properties` so that builds run consistently across environments without requiring a locally installed Gradle. This module is isolated in the dependency graph and acts purely as build-tooling configuration.

## `build tooling / quadtree graphics application`

Modules participating in the 'build tooling / quadtree graphics application' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **quadtree-graphic** — Provides the Gradle build scaffolding for an isolated `quadtree-graphic` project, including the Java plugin configuration with JUnit testing (`build.gradle`), the project naming (`settings.gradle`), and the cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) used to bootstrap and execute builds on Unix and Windows. As an isolated module with no fan-in or fan-out dependencies, it stands alone as a self-contained build harness.

## `geospatial indexing / proximity search`

Modules participating in the 'geospatial indexing / proximity search' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (1):**

- **Provides a self-contained quadtree spatial indexing core for geographic data** — Provides a self-contained quadtree spatial indexing core for geographic data. Defines the `Neighbour` abstraction for points with id and lat/lon coordinates (`NeighbourImpl`), recursive node subdivision and search via `QuadTreeNode`, and the public `QuadTree` facade for inserting points and querying neighbors within a kilometer-based radius. `QuadTreeConstants` centralizes minimum node size configuration and km-to-degree conversion. The module is isolated (no internal fan-in/fan-out), making it a standalone library suitable for embedding in spatial-search applications.

## `geospatial indexing / quadtree spatial data structures`

Modules participating in the 'geospatial indexing / quadtree spatial data structures' domain.

**Modules in this context:**

- `.`

**Capabilities (1):**

- **.** — Root-level repository metadata for a standalone quadtree-based geolocation data structure project. Contains the Apache 2.0 `LICENSE`, a `README.md` describing the quadtree implementation and its use for spatial/proximity queries on geographic data, and a `.gitignore` for version-control hygiene. This module is isolated in the dependency graph and provides no runtime code surface.

## `interactive geospatial quadtree visualization (swing gui)`

Modules participating in the 'interactive geospatial quadtree visualization (swing gui)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — Provides the top-level Swing application shell and rendering framework for the quadtree graphic visualizer. It bootstraps the JFrame (`Main`), runs a double-buffered game loop with pan/zoom input handling (`CanvasPanel`), defines the rendering abstractions (`Screen`, `Drawable`, `BaseObject`), and implements the concrete world-map quadtree visualization with random neighbor point generation and interactive search (`MainScreen`). This module is isolated in the dependency graph and serves as the standalone GUI driver layer that consumes the quadtree library internally.

## `spatial data structure visualization (quadtree rendering)`

Modules participating in the 'spatial data structure visualization (quadtree rendering)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **quadtree** — Provides graphical/drawable extensions to a core quadtree data structure for visualization purposes. `DrawableQuadTree` subclasses `QuadTree` and `DrawableQuadTreeNode` subclasses `QuadTreeNode`, both implementing a `Drawable` interface to render node boundaries and contained neighbours as rectangles on a graphics context, with support for coordinate scaling and bounds.
