# Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / gradle configuration`

Modules participating in the 'build tooling / gradle configuration' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Configures the Gradle wrapper for the quadtree-graphic project, specifying which Gradle distribution version and download source to use so that builds run consistently across developer machines without requiring a pre-installed Gradle. This module is isolated and has no inter-module dependencies — it is purely build tooling configuration.

## `build tooling / project configuration for a quadtree graphics application`

Modules participating in the 'build tooling / project configuration for a quadtree graphics application' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **quadtree-graphic** — Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the project settings, build script targeting Java 1.8 with JUnit testing, and the Gradle wrapper scripts (`gradlew`, `gradlew.bat`) for executing builds on Unix and Windows without a pre-installed Gradle. This module is isolated in the dependency graph and serves purely as the build/tooling configuration layer.

## `geospatial indexing / spatial data structures`

Modules participating in the 'geospatial indexing / spatial data structures' domain.

**Modules in this context:**

- `.`
- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (2):**

- **.** — This is the root module of a standalone repository containing a quadtree data structure implementation for geolocation optimization and spatial indexing. It currently holds only project-level metadata files: a `.gitignore` for version control exclusions, an Apache 2.0 `LICENSE`, and a `README.md` documenting the quadtree concept, algorithm, and usage examples for proximity queries. The module is isolated with no inter-module dependencies in the supplied graph, suggesting actual implementation code resides elsewhere or has yet to be added.
- **core** — Provides the core quadtree spatial data structure for indexing and querying geographic entities (neighbours) by latitude/longitude. Defines the `Neighbour` abstraction and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that partitions space and supports add/remove/range-search, the top-level `QuadTree` facade that exposes add and range-query operations (including km-based range conversion), and `QuadTreeConstants` holding tuning parameters such as max node capacity and km-to-degree conversion factors. The module is self-contained (isolated in the dependency graph) and serves as a reusable spatial index library.

## `interactive 2d graphics / spatial data-structure visualization (quadtree neighbor search over a geographic map)`

Modules participating in the 'interactive 2d graphics / spatial data-structure visualization (quadtree neighbor search over a geographic map)' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — Provides the top-level Swing/AWT application scaffolding for the quadtree visualization: bootstraps the window (`Main`), hosts a double-buffered rendering canvas with input handling (`CanvasPanel`), defines base abstractions for drawable scene objects (`BaseObject`, `Drawable`, `Screen`), and implements `MainScreen` which renders a world map, overlays an interactive quadtree, and performs radius-based neighbor searches in response to mouse input. This module is the application's entry layer and presentation shell, composing lower-level quadtree data structures into a visual demo.

## `spatial data structure visualization / graphical rendering of quadtrees`

Modules participating in the 'spatial data structure visualization / graphical rendering of quadtrees' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **quadtree** — Provides a drawable/visualizable adapter layer over the core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, enabling rendering of quadtree boundaries and neighbor points on a graphical canvas with configurable scale factors.
