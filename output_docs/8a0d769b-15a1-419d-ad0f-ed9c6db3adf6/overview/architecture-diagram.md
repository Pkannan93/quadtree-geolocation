# Geospatial indexing and proximity search with interactive visualization Documentation — Architecture

**Architecture style.** layered modular Java application (core library + drawable adapter + Swing GUI shell) packaged as a single Gradle project

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](../guide/modules/root.md) | Root-level repository metadata for a standalone quadtree-based geolocation data structure project. Contains the Apache 2.0 `LICENSE`, a `… | — |
| [quadtree-graphic](../guide/modules/quadtree__graphic.md) | Provides the Gradle build scaffolding for an isolated `quadtree-graphic` project, including the Java plugin configuration with JUnit test… | — |
| [quadtree-graphic/gradle/wrapper](../guide/modules/quadtree__graphic__gradle__wrapper.md) | Provides the Gradle Wrapper configuration for the quadtree-graphic project, pinning the build to Gradle 4.0 via `gradle-wrapper.propertie… | — |
| [quadtree-graphic/src/main/java/src](../guide/modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing application shell and rendering framework for the quadtree graphic visualizer. It bootstraps the JFrame (`Ma… | `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree](../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides graphical/drawable extensions to a core quadtree data structure for visualization purposes. `DrawableQuadTree` subclasses `QuadT… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides a self-contained quadtree spatial indexing core for geographic data. Defines the `Neighbour` abstraction for points with id and… | — |

The full per-module deep dives live under [Codebase Guide](../guide/index.md).
