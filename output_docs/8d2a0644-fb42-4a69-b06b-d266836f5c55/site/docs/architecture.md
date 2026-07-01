# Geospatial indexing and visualization using quadtrees (geolocation optimization / efficient spatial queries) Documentation — Architecture

**Architecture style.** layered desktop application (Swing UI shell over a drawable adapter over a core spatial-index library), packaged as a single Gradle module

_The diagram-agent did not emit an architecture block this run. The module breakdown below carries the same information in textual form (each module's responsibility + collaborators)._

## Modules at a glance

| Module | Responsibility | Collaborators |
|---|---|---|
| [.](modules/root.md) | Root project directory containing only repository metadata: a `.gitignore` for excluding untracked files, an Apache License 2.0 `LICENSE`… | — |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides Gradle build infrastructure for the quadtree-graphic project, including the build configuration (`build.gradle`), project settin… | — |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic subproject, declaring which Gradle distribution version to download and wh… | — |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing application shell and rendering framework for a quadtree visualization tool. It defines the application entr… | `src.quadtree.DrawableQuadTree`, `src.quadtree.core.QuadTree`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides drawable/visualization wrappers around the core quadtree data structures, enabling rendering of quadtree spatial subdivisions an… | `src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour` |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial-indexing data structure for geographic points (latitude/longitude). It defines the `Neighbour` abstrac… | — |

The full per-module deep dives live under [Modules](modules/index.md).
