# Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points Documentation — Architecture

**Architecture style.** layered (Java application: core data structure → drawable adapter → Swing UI shell), packaged as a single Gradle-built modular monolith

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](modules/root.md) | This top-level directory contains repository-level metadata and documentation for a quadtree data structure project optimized for geoloca… | — |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the build configuration (`build.gradle`) targeting… | — |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Holds the Gradle Wrapper configuration that pins the Gradle distribution version and download/cache locations for the `quadtree-graphic`… | — |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application shell and rendering loop for the quadtree graphic visualization. It defines the drawable abs… | `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)` |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical/drawable visualization layer over a core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` from `src.q… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial-indexing data structure for storing and querying geographic neighbours by latitude/longitude. Defines… | — |

The full per-module deep dives live under [Modules](modules/index.md).
