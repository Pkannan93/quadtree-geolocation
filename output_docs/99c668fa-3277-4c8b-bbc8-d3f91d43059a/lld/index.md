# canvas-repo-whq499lb — Low-Level Design

This system comprises six modules organized into a three-layer architecture: a self-contained spatial-index core (`quadtree-graphic/src/main/java/src/quadtree/core`), a drawable adapter layer (`quadtree-graphic/src/main/java/src/quadtree`), and a Swing presentation shell (`quadtree-graphic/src/main/java/src`). The extracted graph shows zero edges because the dependency relationships—while evident from directory structure—were not captured during module boundary detection; the intended flow runs unidirectionally from `QuadTree` and `QuadTreeNode` in the core, through `DrawableQuadTree` renderers in the adapter, to `Main` and `CanvasPanel` in the composition root. Two additional modules (`quadtree-graphic` root and `gradle/wrapper`) supply build tooling but carry no runtime responsibility.

The architecture exhibits zero cycles and zero degraded modules, reflecting clean layering and well-separated concerns. The `quadtree-graphic/src/main/java/src` module serves as the sole composition root, wiring the drawable adapters into a Swing `MainScreen` that overlays a world map with interactive range queries. The core module is a leaf—it exports `Neighbour`, `NeighbourImpl`, and `QuadTreeConstants` but depends on no sibling—making it trivially reusable outside this demo application. The absence of extracted fan-in and fan-out data means you will rely on file-level imports to trace collaborations when reviewing individual modules.

For the higher-level view of how these modules map to logical components (Core Spatial Index, Drawable Adapter, Interactive Visualization), consult the **HLD Components** page.

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
| [.](modules/root.md) | This is the root module of a standalone repository containing a quadtree data structure implementation for… |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project, including the project settings… |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Configures the Gradle wrapper for the quadtree-graphic project, specifying which Gradle distribution versio… |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application scaffolding for the quadtree visualization: bootstraps the win… |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a drawable/visualizable adapter layer over the core QuadTree data structure. It wraps `QuadTree` a… |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial data structure for indexing and querying geographic entities (neighbours… |


---

**Related surfaces.** [HLD Components](../hld/components.md) · [HLD Architecture](../hld/architecture.md) · [Codebase Guide](../guide/index.md)
