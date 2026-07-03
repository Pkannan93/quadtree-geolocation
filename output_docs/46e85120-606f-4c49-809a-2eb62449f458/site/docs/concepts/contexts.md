# Geospatial indexing and visualization via quadtrees Documentation — Bounded contexts

A bounded context is a self-consistent area of the domain — its own language, its own rules, its own model boundaries. Modules within a context speak the same dialect; modules across contexts may use the same word for different concepts (e.g. `Customer` in Billing vs Support). Sourced from the business-semantics agent's domain rollup; descriptions are LLM-derived against the modules it groups.

## `build tooling / gradle wrapper configuration`

Modules participating in the 'build tooling / gradle wrapper configuration' domain.

**Modules in this context:**

- `quadtree-graphic/gradle/wrapper`

**Capabilities (1):**

- **wrapper** — Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution to version 8.10.2 and defining download URLs, local storage locations, and validation settings so all developers and CI environments build with a consistent Gradle version. This module is isolated in the dependency graph and serves purely as build-tool bootstrapping metadata.

## `build tooling / project scaffolding for a quadtree visualization application`

Modules participating in the 'build tooling / project scaffolding for a quadtree visualization application' domain.

**Modules in this context:**

- `quadtree-graphic`

**Capabilities (1):**

- **quadtree-graphic** — Provides the Gradle build infrastructure for a standalone `quadtree-graphic` project, including build configuration (Java 8 compatibility, JUnit test dependencies), project settings, and Gradle wrapper scripts for both Unix (`gradlew`) and Windows (`gradlew.bat`) environments. This module is isolated in the dependency graph and contains only build/scaffolding artifacts — no source code is present in this directory.

## `geospatial indexing / quadtree spatial data structures`

Modules participating in the 'geospatial indexing / quadtree spatial data structures' domain.

**Modules in this context:**

- `.`

**Capabilities (1):**

- **Top-level project root for a quadtree-based geolocation optimization library** — Top-level project root for a quadtree-based geolocation optimization library. Contains only repository metadata: licensing (Apache 2.0), Git ignore rules, and the README documenting the spatial indexing data structure with usage examples and visualizations. No source code lives directly at this level; this directory frames and documents the library as a whole.

## `geospatial indexing / spatial data structures`

Modules participating in the 'geospatial indexing / spatial data structures' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree/core`

**Capabilities (1):**

- **core** — Provides the core quadtree spatial index implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` entity contract and its `NeighbourImpl` implementation, the recursive `QuadTreeNode` for spatial partitioning, the top-level `QuadTree` facade exposing insertion and proximity search, and `QuadTreeConstants` utilities for unit conversions (e.g., kilometers to degrees). This module is self-contained (isolated in the dependency graph) and serves as the underlying spatial data structure to be consumed by higher-level graphic/visualization layers.

## `interactive geospatial visualization / quadtree demo ui`

Modules participating in the 'interactive geospatial visualization / quadtree demo ui' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src`

**Capabilities (1):**

- **src** — Provides the Swing-based graphical application shell for the quadtree visualization demo. It defines the rendering framework (`Drawable` interface, `BaseObject` base class, `Screen` collection manager), the interactive `CanvasPanel` with its dedicated render thread handling pan/zoom and mouse/keyboard input, and the `MainScreen` which loads a world map, scatters 10 million random points into a quadtree, and performs radius-based neighbor searches on mouse interaction. `Main` bootstraps the `JFrame` and wires `CanvasPanel` into it.

## `spatial indexing / 2d graphical visualization of quadtrees`

Modules participating in the 'spatial indexing / 2d graphical visualization of quadtrees' domain.

**Modules in this context:**

- `quadtree-graphic/src/main/java/src/quadtree`

**Capabilities (1):**

- **quadtree** — Provides a graphical/drawable layer over the core quadtree data structure by extending `QuadTree` and `QuadTreeNode` with Java2D rendering capabilities. It renders quadtree node boundaries as rectangles and visualizes neighbor relationships with zoom-level-dependent detail, while delegating spatial indexing operations (subdivision, neighbor lookup) to the underlying core quadtree implementation.
