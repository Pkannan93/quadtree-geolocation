# canvas-repo-nkwtyu9g — Low-Level Design

This system comprises six modules arranged in a single-layer graph with zero recorded edges, a structural artifact of tracking directories as independent units rather than capturing import relationships within the Java monolith. Despite the flat topology reported here, the codebase itself implements a classic three-tier architecture: `quadtree-graphic/src/main/java/src/quadtree/core` holds the core spatial-indexing engine (`QuadTree`, `QuadTreeNode`, `Neighbour`, `NeighbourImpl`), `quadtree-graphic/src/main/java/src/quadtree` provides the drawable adapter (`DrawableQuadTree`, `DrawableQuadTreeNode`), and `quadtree-graphic/src/main/java/src` supplies the Swing UI shell (`Main`, `CanvasPanel`, `Screen`, `MainScreen`). The remaining three modules—`quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, and the repository root—contain Gradle build configuration, license files, and documentation, none exposing a public surface for runtime composition.

With zero degraded modules and an acyclic structure at the directory level, the design is clean in the nominal sense, though the absence of inter-module edges means fan-in and fan-out metrics are uninformative. The composition root resides in `Main`, which instantiates the canvas and wires the drawable layer to the core engine. Readers seeking to understand how classes collaborate should consult the HLD Components page, which reconstructs the logical layering from source imports rather than module boundaries, and provides the call-graph context that this directory-based view elides.

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
| [.](modules/root.md) | This top-level directory contains repository-level metadata and documentation for a quadtree data structure… |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides the Gradle build infrastructure for the `quadtree-graphic` project. Contains the build configurati… |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Holds the Gradle Wrapper configuration that pins the Gradle distribution version and download/cache locatio… |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing/AWT application shell and rendering loop for the quadtree graphic visualizatio… |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides a graphical/drawable visualization layer over a core QuadTree data structure. It wraps `QuadTree`… |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial-indexing data structure for storing and querying geographic neighbours b… |


---

**Related surfaces.** [HLD Components](../hld/components.md) · [HLD Architecture](../hld/architecture.md) · [Codebase Guide](../guide/index.md)
