# Geospatial indexing and visualization (quadtree-based location services) Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / project infrastructure`

Modules participating in the 'build tooling / project infrastructure' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL, version, and local cache/distribution paths. This enables reproducible Gradle builds across environments without requiring developers to pre-install Gradle. The module is isolated with no inter-module dependencies.

## `build tooling / project scaffolding`

Modules participating in the 'build tooling / project scaffolding' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **Build infrastructure scaffolding for the `quadtree-graphic` Java project** — Build infrastructure scaffolding for the `quadtree-graphic` Java project. Provides the Gradle build configuration (`build.gradle`, `settings.gradle`) declaring the Java plugin and JUnit 5 test dependency, plus the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) that bootstrap Gradle on Unix and Windows without a pre-installed distribution. This module is isolated in the dependency graph and serves purely as the build entry point for the project.

## `geospatial data structures / location-based services (quadtree-based spatial indexing)`

Modules participating in the 'geospatial data structures / location-based services (quadtree-based spatial indexing)' domain.

**Modules in this context:**

- `.`

**Capabilities (1):**

- **.** — This is the repository root directory containing only project metadata and documentation files: a `.gitignore` for version control hygiene, an Apache 2.0 `LICENSE`, and a `README.md` that documents a quadtree data structure implementation for geolocation optimization. The module itself contains no executable code; it provides the project-level context, licensing, and developer-facing documentation for a spatial data partitioning library.

## `geospatial indexing / spatial data structures`

Modules participating in the 'geospatial indexing / spatial data structures' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (1):**

- **Provides the core quadtree spatial indexing implementation for geographic data** — Provides the core quadtree spatial indexing implementation for geographic data. Defines the `Neighbour` abstraction (with a concrete `NeighbourImpl`) representing identifiable points by latitude/longitude, and exposes a `QuadTree` that recursively subdivides space via `QuadTreeNode` to support insertion (`addNeighbour`) and radius-based proximity queries (`findNeighbours`, `findNeighboursIds`). `QuadTreeConstants` centralizes configuration such as the minimum node size and degree-to-kilometer conversion. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial indexing engine for the broader quadtree-graphic application.

## `interactive visualization / demo ui for a quadtree spatial-indexing data structure`

Modules participating in the 'interactive visualization / demo ui for a quadtree spatial-indexing data structure' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — This module is the top-level application package for a Java Swing/AWT graphical application that visualizes a quadtree spatial data structure over a world map. It bootstraps the JFrame window (`Main`), runs a custom render-loop canvas with zoom/pan and input handling (`CanvasPanel`), and provides the abstract scene-graph primitives (`Drawable` interface, `BaseObject` abstract class, `Screen` container) on top of which `MainScreen` builds an interactive demo that loads a map image, populates a `DrawableQuadTree`, and performs mouse-driven nearest-neighbor queries while reporting performance.

## `spatial data structure visualization / 2d graphics rendering`

Modules participating in the 'spatial data structure visualization / 2d graphics rendering' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **quadtree** — Provides a graphical visualization layer for the quadtree data structure by wrapping core quadtree types with rendering capability. `DrawableQuadTree` adapts a `QuadTree` to the `Drawable` interface, delegating draw and update calls to a `DrawableQuadTreeNode` root, which extends `QuadTreeNode` to render spatial bounds and neighbor points on a graphics canvas with zoom-dependent detail.
