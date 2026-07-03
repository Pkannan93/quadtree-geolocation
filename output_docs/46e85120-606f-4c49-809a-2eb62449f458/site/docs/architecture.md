# Geospatial indexing and visualization via quadtrees Documentation — Architecture

**Architecture style.** layered library with demo application (core data structure → drawable adapter → Swing UI shell), packaged as a single-project Gradle build

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](modules/root.md) | Top-level project root for a quadtree-based geolocation optimization library. Contains only repository metadata: licensing (Apache 2.0),… | — |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides the Gradle build infrastructure for a standalone `quadtree-graphic` project, including build configuration (Java 8 compatibility… | — |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution to version 8.10.2 and defining do… | — |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the Swing-based graphical application shell for the quadtree visualization demo. It defines the rendering framework (`Drawable`… | `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical/drawable layer over the core quadtree data structure by extending `QuadTree` and `QuadTreeNode` with Java2D renderin… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial index implementation for storing and querying geographic entities by latitude/longitude. Defines the `… | — |

The full per-module deep dives live under [Modules](modules/index.md).
