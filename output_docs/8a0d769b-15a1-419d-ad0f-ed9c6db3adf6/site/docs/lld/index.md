# canvas-repo-3p2clcww — Low-Level Design

This system comprises six modules across a single Gradle-wrapped Java project, though the flat dependency graph (zero edges, one layer) reflects a gap in the module summarization rather than true architectural independence—Java package imports within `quadtree-graphic/src/main/java/src` are not surfaced. The actual layering flows from `src/quadtree/core` (the pure quadtree library exposing `QuadTree`, `QuadTreeNode`, and `Neighbour` for geospatial indexing) through `src/quadtree` (rendering extensions `DrawableQuadTree` and `DrawableQuadTreeNode`) up to `src` (the Swing shell with `Main`, `CanvasPanel`, `MainScreen`). With zero degraded modules and zero cyclic SCCs, the codebase exhibits clean boundaries at the directory level, though the absence of fan-in and fan-out data means composition roots and leaf modules are not machine-identified here.

The Gradle wrapper configuration sits in `quadtree-graphic` and `quadtree-graphic/gradle/wrapper`, establishing the build envelope but not participating in runtime collaboration. Because no inter-module edges are recorded, readers will need to infer coupling by tracing Java `import` statements manually—expect `src` to depend on both `src/quadtree` and `src/quadtree/core`, and `src/quadtree` to depend on `src/quadtree/core`. For a higher-level view that contextualizes these modules as *Core Library*, *Rendering Adapter*, and *GUI Shell* components, consult the HLD Components page.

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
| [.](modules/root.md) | Root-level repository metadata for a standalone quadtree-based geolocation data structure project. Contains… |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides the Gradle build scaffolding for an isolated `quadtree-graphic` project, including the Java plugin… |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides the Gradle Wrapper configuration for the quadtree-graphic project, pinning the build to Gradle 4.0… |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing application shell and rendering framework for the quadtree graphic visualizer.… |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides graphical/drawable extensions to a core quadtree data structure for visualization purposes. `Drawa… |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides a self-contained quadtree spatial indexing core for geographic data. Defines the `Neighbour` abstr… |


---

**Related surfaces.** [HLD Components](../hld/components.md) · [HLD Architecture](../hld/architecture.md) · [Codebase Guide](../modules/index.md)
