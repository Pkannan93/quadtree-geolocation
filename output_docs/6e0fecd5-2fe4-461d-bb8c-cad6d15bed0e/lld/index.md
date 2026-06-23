# canvas-repo-95z65xwi — Low-Level Design

This codebase partitions into six modules arranged in a single reported layer, though the source-level intent describes a three-tier stack: `quadtree-graphic/src/main/java/src/quadtree/core` holds the core spatial indexing logic (`QuadTree`, `QuadTreeNode`, `Neighbour`, `QuadTreeConstants`), `quadtree-graphic/src/main/java/src/quadtree` provides drawable wrappers (`DrawableQuadTree`, `DrawableQuadTreeNode`), and `quadtree-graphic/src/main/java/src` implements the Swing UI shell (`Main`, `CanvasPanel`, `MainScreen`). The remaining two modules—`quadtree-graphic` and `quadtree-graphic/gradle/wrapper`—contain build and tooling configuration. The graph reports zero edges and no fan-in or fan-out, which means either the module boundaries were drawn too coarsely to capture the intended layering or the dependency extraction did not reach inside Java package structure; the result is that every module appears isolated, making it impossible to verify composition roots or detect cyclic coupling from the substrate alone.

Because the graph shows no degraded modules and is trivially acyclic (cycle count zero), there are no structural smells at the module level, but the absence of edges also means the data cannot confirm which module serves as the composition root or which are leaf nodes. A reader seeking to understand call flow or side-effect surface will need to consult the individual module pages and the HLD Components view, where the higher-level architecture and the rationale for the core → drawable → UI layering are documented.

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
| [.](modules/root.md) | This top-level module serves as the project's root metadata and documentation layer. It contains the Apache… |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides Gradle build infrastructure for the quadtree-graphic Java project, including build configuration (… |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, pinning the Gradle distribution ver… |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the Swing/AWT-based graphical application shell for visualizing a quadtree-driven geographic point… |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides drawable wrapper classes that adapt the core QuadTree data structures for graphical rendering. `Dr… |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core QuadTree spatial indexing implementation for geographic neighbor lookup. Defines the `Nei… |


---

**Related surfaces.** [HLD Components](../hld/components.md) · [HLD Architecture](../hld/architecture.md) · [Codebase Guide](../guide/index.md)
