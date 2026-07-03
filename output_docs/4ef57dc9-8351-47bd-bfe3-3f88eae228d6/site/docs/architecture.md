# Geospatial indexing and proximity search with interactive visualization Documentation — Architecture

**Architecture style.** layered desktop application (spatial-core → drawable adapter → Swing UI shell) with separate Gradle build-tooling roots

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](modules/root.md) | Top-level project metadata for a quadtree data structure implementation aimed at geolocation optimization. Contains only repository-level… | — |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the root project settings, Java 11 compilation con… | — |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL and version along with fil… | — |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application shell for the quadtree visualization: bootstraps the JFrame (`Main`), hosts a game-loop rend… | `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides drawable/visualizable extensions of the core quadtree data structure. `DrawableQuadTree` extends the base `QuadTree` and delegat… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core QuadTree spatial indexing implementation for storing and querying geographic entities by latitude/longitude. Defines th… | — |

The full per-module deep dives live under [Modules](modules/index.md).
