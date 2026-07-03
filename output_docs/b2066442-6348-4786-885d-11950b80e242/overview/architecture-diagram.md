# Geospatial indexing and visualization (quadtree-based location services) Documentation — Architecture

**Architecture style.** layered modular monolith (core spatial library + visualization adapter + Swing UI shell, with separate build scaffolding)

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](../guide/modules/root.md) | This is the repository root directory containing only project metadata and documentation files: a `.gitignore` for version control hygien… | — |
| [quadtree-graphic](../guide/modules/quadtree__graphic.md) | Build infrastructure scaffolding for the `quadtree-graphic` Java project. Provides the Gradle build configuration (`build.gradle`, `setti… | — |
| [quadtree-graphic/gradle/wrapper](../guide/modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution URL, version, and local cache/… | — |
| [quadtree-graphic/src/main/java/src](../guide/modules/quadtree__graphic__src__main__java__src.md) | This module is the top-level application package for a Java Swing/AWT graphical application that visualizes a quadtree spatial data struc… | `src.quadtree (DrawableQuadTree)`, `src.quadtree.core (QuadTree, Neighbour)`, `javax.swing (JFrame)`, `java.awt (Canvas, BufferStrategy)` |
| [quadtree-graphic/src/main/java/src/quadtree](../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical visualization layer for the quadtree data structure by wrapping core quadtree types with rendering capability. `Draw… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial indexing implementation for geographic data. Defines the `Neighbour` abstraction (with a concrete `Nei… | — |

The full per-module deep dives live under [Codebase Guide](../guide/index.md).
