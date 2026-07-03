# Geospatial indexing and proximity search visualization Documentation — Architecture

**Architecture style.** layered desktop application (core spatial engine, drawable adapter layer, Swing UI shell) built as a single Gradle module

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](modules/root.md) | Top-level project root containing only meta and documentation files: a `.gitignore` for VCS hygiene, an Apache License 2.0 `LICENSE` file… | — |
| [quadtree-graphic](modules/quadtree__graphic.md) | Gradle-based Java project scaffolding for a `quadtree-graphic` application. Provides the build configuration (`build.gradle` with Java 8… | — |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides the Gradle wrapper configuration for the `quadtree-graphic` project, specifying which Gradle distribution version to download, w… | — |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT graphical application for visualizing a quadtree of geographic points on a world map. It defines the app… | `src.quadtree (DrawableQuadTree, QuadTree, Neighbour)` |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical/drawable adapter layer over a core quadtree data structure, enabling visualization of quadtree nodes, their spatial… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial indexing implementation for geographic point data. Defines a `Neighbour` abstraction (id + latitude/lo… | — |

The full per-module deep dives live under [Modules](modules/index.md).
