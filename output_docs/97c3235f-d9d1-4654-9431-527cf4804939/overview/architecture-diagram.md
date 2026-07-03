# Geospatial indexing and visualization (quadtree-based geographic neighbour search) Documentation — Architecture

**Architecture style.** layered (core → drawable extension → application shell), packaged as a single Gradle-built desktop application

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](../guide/modules/root.md) | Top-level repository root containing project metadata, licensing, and documentation for a quadtree data structure implementation aimed at… | — |
| [quadtree-graphic](../guide/modules/quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the Gradle wrapper scripts (`gradlew`, `gradlew.bat… | — |
| [quadtree-graphic/gradle/wrapper](../guide/modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and specifying wher… | — |
| [quadtree-graphic/src/main/java/src](../guide/modules/quadtree__graphic__src__main__java__src.md) | Provides the Swing/AWT-based graphical application shell for visualizing a quadtree spatial index. It defines the window entry point (`Ma… | `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)` |
| [quadtree-graphic/src/main/java/src/quadtree](../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides graphical/visual rendering capabilities for quadtree data structures by extending the core quadtree types (`QuadTree`, `QuadTree… | `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour`, `src.Drawable` |
| [quadtree-graphic/src/main/java/src/quadtree/core](../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial indexing engine: defines the `Neighbour` abstraction for geo-located entities (id, latitude, longitude… | — |

The full per-module deep dives live under [Codebase Guide](../guide/index.md).
