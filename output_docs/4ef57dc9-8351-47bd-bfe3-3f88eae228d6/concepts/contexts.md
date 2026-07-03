# Geospatial indexing and proximity search with interactive visualization Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / gradle configuration`

Modules participating in the 'build tooling / gradle configuration' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL and version along with file system paths for the wrapper's base directory, zip storage, and JAR location. This enables reproducible Gradle builds across environments without requiring a pre-installed Gradle distribution.

## `build tooling / project scaffolding for a quadtree graphics application`

Modules participating in the 'build tooling / project scaffolding for a quadtree graphics application' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **quadtree-graphic** — Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the root project settings, Java 11 compilation configuration, JUnit 5 test dependency wiring, and the cross-platform Gradle wrapper scripts (`gradlew` for Unix, `gradlew.bat` for Windows) used to bootstrap builds. This module is an isolated build-tooling root with no runtime code dependencies on or from other modules in the graph.

## `geospatial indexing / geolocation optimization via quadtree data structures`

Modules participating in the 'geospatial indexing / geolocation optimization via quadtree data structures' domain.

**Modules in this context:**

- `.`

**Capabilities (1):**

- **.** — Top-level project metadata for a quadtree data structure implementation aimed at geolocation optimization. Contains only repository-level artifacts (`.gitignore`, `LICENSE` under Apache 2.0, and `README.md` describing the quadtree's purpose and usage) with no source code or runtime dependencies. Serves as the documentation and licensing entry point for the project.

## `geospatial indexing / proximity search`

Modules participating in the 'geospatial indexing / proximity search' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (1):**

- **core** — Provides the core QuadTree spatial indexing implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` abstraction (interface plus `NeighbourImpl`) representing points with an ID and coordinates, and exposes a `QuadTree` facade backed by recursive `QuadTreeNode` subdivision to support insertion and radius-based neighbor lookups (in kilometers, converted via `QuadTreeConstants`). This module is self-contained (isolated in the dependency graph) and offers the reusable spatial data structure that other layers of the quadtree-graphic application would build upon.

## `interactive graphical visualization of a quadtree spatial index over geographic points`

Modules participating in the 'interactive graphical visualization of a quadtree spatial index over geographic points' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — Provides the top-level Swing/AWT application shell for the quadtree visualization: bootstraps the JFrame (`Main`), hosts a game-loop rendering canvas with zoom/pan and input handling (`CanvasPanel`), and defines the `Screen`/`Drawable`/`BaseObject` abstractions that structure renderable entities. Its concrete `MainScreen` composes a `DrawableQuadTree` over a world-map background, generates random points, and dispatches mouse-driven neighbour queries against the underlying `QuadTree`.

## `spatial data structure visualization / graphics rendering`

Modules participating in the 'spatial data structure visualization / graphics rendering' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **Provides drawable/visualizable extensions of the core quadtree data structure** — Provides drawable/visualizable extensions of the core quadtree data structure. `DrawableQuadTree` extends the base `QuadTree` and delegates rendering to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` and implements `Drawable` to render node boundaries and neighbor points on screen (with zoom-dependent detail). This module is isolated in the dependency graph and serves as a visualization layer over an external quadtree core.
