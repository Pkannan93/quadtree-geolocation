# canvas-repo-3yaruvsz — Low-Level Design

This system comprises six modules organized into a clean three-layer architecture: a core spatial engine, a drawable adapter layer that bridges the engine to visualization, and a Swing UI shell. The dependency graph is acyclic with zero detected edges—an artifact of the single-Gradle-module build structure—yet the intended layering is evident in the package hierarchy. The core engine in `quadtree-graphic/src/main/java/src/quadtree/core` (`QuadTree`, `QuadTreeNode`, `Neighbour`, `NeighbourImpl`) owns insertion and radius-based lookup semantics for lat/lon points, while `quadtree-graphic/src/main/java/src/quadtree` wraps those nodes with `DrawableQuadTree` and `DrawableQuadTreeNode` to expose boundary and neighbour-link rendering. The top-level module at `quadtree-graphic/src/main/java/src` serves as the composition root, hosting `Main`, `CanvasPanel`, and `MainScreen` to wire the canvas, load the world map, populate the quadtree, and dispatch interactive proximity queries.

No cyclic SCCs or degraded modules appear, and the absence of fan-in/fan-out data reflects the monolithic Gradle packaging rather than a loose dependency discipline. The `quadtree-graphic` and `quadtree-graphic/gradle/wrapper` modules supply build tooling, while the root module holds licensing and documentation. For a higher-level view of the system's responsibilities and component boundaries, see the HLD Components page.

## Modular structure at a glance

| Dimension | Value |
|---|---|
| Modules | 6 |
| Degraded summaries | 0 |
| Dependency edges | 0 |
| Acyclic | yes |
| Topological layers | 1 |
| Cycles | 0 |
| Per-module pages emitted | 6 |

## All modules

| Module | Responsibility |
|---|---|
| [.](modules/root.md) | Top-level project root containing only meta and documentation files: a `.gitignore` for VCS hygiene, an Apa… |
| [quadtree-graphic](modules/quadtree__graphic.md) | Gradle-based Java project scaffolding for a `quadtree-graphic` application. Provides the build configuratio… |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides the Gradle wrapper configuration for the `quadtree-graphic` project, specifying which Gradle distr… |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT graphical application for visualizing a quadtree of geographic points on a… |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical/drawable adapter layer over a core quadtree data structure, enabling visualization of… |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial indexing implementation for geographic point data. Defines a `Neighbour`… |


---

**Related surfaces.** [HLD Components](../hld/components.md) · [HLD Architecture](../hld/architecture.md) · [Codebase Guide](../modules/index.md)
