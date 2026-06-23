# Geospatial indexing and visualization (quadtree-based nearest-neighbor search) Documentation — Architecture

**Architecture style.** layered desktop application (core data-structure library wrapped by drawable adapters and a Swing UI shell)

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](modules/root.md) | This top-level module serves as the project's root metadata and documentation layer. It contains the Apache 2.0 LICENSE governing distrib… | — |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides Gradle build infrastructure for the quadtree-graphic Java project, including build configuration (`build.gradle`), project setti… | — |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution version (8.5) and defining where… | — |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the Swing/AWT-based graphical application shell for visualizing a quadtree-driven geographic point search. It defines the render… | `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)`, `javax.swing/java.awt (JFrame, Canvas, BufferStrategy, Graphics2D)` |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides drawable wrapper classes that adapt the core QuadTree data structures for graphical rendering. `DrawableQuadTree` wraps `QuadTre… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core QuadTree spatial indexing implementation for geographic neighbor lookup. Defines the `Neighbour` abstraction (id + lat/… | — |

The full per-module deep dives live under [Modules](modules/index.md).
