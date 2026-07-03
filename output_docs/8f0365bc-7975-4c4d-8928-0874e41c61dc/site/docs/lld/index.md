# canvas-repo-qdvswexp — Low-Level Design

This system decomposes into six modules arranged in a strict three-tier architecture: a reusable spatial-index core, a presentation adapter that exposes `Drawable` contracts, and a Swing UI shell that wires the demo. The core tier (`quadtree-graphic/src/main/java/src/quadtree/core`) defines `QuadTree`, `QuadTreeNode`, and the `Neighbour`/`NeighbourImpl` proximity-search contracts, constrained by `QuadTreeConstants`; it carries zero outbound dependencies and forms the system's only true leaf module. The adapter tier (`quadtree-graphic/src/main/java/src/quadtree`) wraps those core types as `DrawableQuadTree` and `DrawableQuadTreeNode`, bridging spatial logic to a rendering surface. The application tier (`quadtree-graphic/src/main/java/src`) serves as the composition root, instantiating `Main`, `CanvasPanel`, and `MainScreen` to coordinate world-map loading, quadtree population, and mouse-driven nearest-neighbor queries.

Zero cycles appear in the inter-module dependency graph, and no module exhibits a degraded summary, which signals intentional layering discipline: the core remains ignorant of visualization concerns, and the Swing shell depends inward without leaking UI abstractions downward. The remaining two modules—`quadtree-graphic` and `quadtree-graphic/gradle/wrapper`—supply build and wrapper scaffolding for reproducible Gradle execution but contribute no runtime logic. For the higher-level component view and allocation of these modules to architectural tiers, consult the **HLD Components** page.

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
| [.](modules/root.md) | This is the repository root directory containing only project metadata and documentation files: a `.gitigno… |
| [quadtree-graphic](modules/quadtree__graphic.md) | Build infrastructure scaffolding for the `quadtree-graphic` Java project. Provides the Gradle build configu… |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic project, specifying the Gradle distribution… |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | This module is the top-level application package for a Java Swing/AWT graphical application that visualizes… |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical visualization layer for the quadtree data structure by wrapping core quadtree types wi… |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial indexing implementation for geographic data. Defines the `Neighbour` abs… |


---

**Related surfaces.** [HLD Components](../hld/components.md) · [HLD Architecture](../hld/architecture.md) · [Codebase Guide](../modules/index.md)
