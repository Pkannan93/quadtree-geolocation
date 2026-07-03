# Geospatial indexing and visualization (quadtree-based proximity search over latitude/longitude points) Documentation — Architecture

**Architecture style.** layered application with a reusable core library (presentation shell over a drawable adapter over a self-contained spatial-index core)

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](../guide/modules/root.md) | This is the root module of a standalone repository containing a quadtree data structure implementation for geolocation optimization and s… | — |
| [quadtree-graphic](../guide/modules/quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the project settings, build script targeting Java… | — |
| [quadtree-graphic/gradle/wrapper](../guide/modules/quadtree__graphic__gradle__wrapper.md) | Configures the Gradle wrapper for the quadtree-graphic project, specifying which Gradle distribution version and download source to use s… | — |
| [quadtree-graphic/src/main/java/src](../guide/modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application scaffolding for the quadtree visualization: bootstraps the window (`Main`), hosts a double-b… | `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree](../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a drawable/visualizable adapter layer over the core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` with `Drawab… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial data structure for indexing and querying geographic entities (neighbours) by latitude/longitude. Defin… | — |

The full per-module deep dives live under [Codebase Guide](../guide/index.md).
