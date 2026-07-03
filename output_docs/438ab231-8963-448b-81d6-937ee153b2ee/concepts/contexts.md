# Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / project infrastructure`

Modules participating in the 'build tooling / project infrastructure' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Holds the Gradle Wrapper configuration that pins the Gradle distribution version and download/cache locations for the `quadtree-graphic` build, allowing the project to be built reproducibly without a pre-installed Gradle. This module is isolated in the dependency graph and is consumed only by the Gradle build tooling itself.

## `build tooling / project scaffolding for a quadtree-based graphics application`

Modules participating in the 'build tooling / project scaffolding for a quadtree-based graphics application' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **Provides the Gradle build infrastructure for the `quadtree-graphic` project** — Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the build configuration (`build.gradle`) targeting Java 8 with JUnit test dependencies, the project settings file (`settings.gradle`), and cross-platform Gradle wrapper scripts (`gradlew`, `gradlew.bat`) that bootstrap the build system on Unix and Windows. This module is isolated in the dependency graph — it contains no application source code, only the tooling required to compile, test, and package the quadtree graphic implementation.

## `geospatial data visualization (quadtree-based spatial indexing rendering)`

Modules participating in the 'geospatial data visualization (quadtree-based spatial indexing rendering)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **quadtree** — Provides a graphical/drawable visualization layer over a core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` from `src.quadtree.core` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, rendering quadtree boundaries and neighbour points by scaling latitude/longitude geographic coordinates to screen coordinates.

## `geospatial indexing / proximity search`

Modules participating in the 'geospatial indexing / proximity search' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (1):**

- **core** — Provides the core quadtree spatial-indexing data structure for storing and querying geographic neighbours by latitude/longitude. Defines the `Neighbour` contract and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that subdivides space into quadrants, the top-level `QuadTree` facade for adding points and finding neighbours within a radius, and `QuadTreeConstants` for node sizing and km-to-degree conversions. This module is self-contained (isolated in the dependency graph) and serves as a reusable spatial-query engine.

## `geospatial indexing / quadtree data structures for geolocation queries`

Modules participating in the 'geospatial indexing / quadtree data structures for geolocation queries' domain.

**Modules in this context:**

- `.`

**Capabilities (1):**

- **.** — This top-level directory contains repository-level metadata and documentation for a quadtree data structure project optimized for geolocation queries. It holds the `.gitignore` for version control exclusions, the Apache License 2.0 (`LICENSE`) governing usage terms, and a `README.md` documenting the quadtree implementation with explanations and examples of 2D spatial partitioning for efficient geographic searches. As an isolated module with no code dependencies, it serves purely as the project's entry-point documentation and licensing layer.

## `interactive 2d graphics / spatial-index visualization (quadtree neighbor search on a world map)`

Modules participating in the 'interactive 2d graphics / spatial-index visualization (quadtree neighbor search on a world map)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — Provides the top-level Swing/AWT application shell and rendering loop for the quadtree graphic visualization. It defines the drawable abstractions (`BaseObject`, `Drawable`), a `Screen` container that aggregates and dispatches draw/update calls, a double-buffered `CanvasPanel` that handles the render loop and mouse/keyboard interaction (zoom/pan), the `Main` entry point that boots a `JFrame`, and `MainScreen` which loads a world map image and drives an interactive quadtree neighbor-search visualization.
