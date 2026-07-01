# code-analyser-repo-ihs_qu4m — Low-Level Design

This system comprises six directories reported as isolated modules in a single flat layer, though the source-level reality is a classic three-tier desktop stack: a Swing shell (`quadtree-graphic/src/main/java/src`) consuming drawable adapters (`quadtree-graphic/src/main/java/src/quadtree`) which wrap the core spatial index (`quadtree-graphic/src/main/java/src/quadtree/core`). The absence of recorded edges means fan-in and fan-out metrics are zero across the board, a signal that the module boundaries correspond to filesystem directories rather than meaningful architectural seams—`Main`, `CanvasPanel`, and `MainScreen` call into `DrawableQuadTree` and `DrawableQuadTreeNode`, which delegate to `QuadTree` and `QuadTreeNode`, but those import relationships are invisible to the dependency graph. The root `.`, `quadtree-graphic`, and `quadtree-graphic/gradle/wrapper` directories hold only repository metadata and Gradle wrapper scripts, contributing no production surface.

Because every module shows zero collaborators, the composition root lives implicitly in the Swing shell directory, where `Main` wires the canvas panel to the drawable index and spawns the background insertion thread. The core quadtree directory is effectively a leaf module—it exports `QuadTree`, `QuadTreeNode`, `Neighbour`, and `QuadTreeConstants` but depends on no sibling packages—while the drawable wrappers sit between shell and core, extending node state to carry canvas coordinates. Consult the **HLD Components** page for the logical view that collapses these six filesystem entries into their three functional tiers.

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
| [.](modules/root.md) | Root project directory containing only repository metadata: a `.gitignore` for excluding untracked files, a… |
| [quadtree-graphic](modules/quadtree__graphic.md) | Provides Gradle build infrastructure for the quadtree-graphic project, including the build configuration (`… |
| [quadtree-graphic/gradle/wrapper](modules/quadtree__graphic__gradle__wrapper.md) | Provides Gradle wrapper configuration for the quadtree-graphic subproject, declaring which Gradle distribut… |
| [quadtree-graphic/src/main/java/src](modules/quadtree__graphic__src__main__java__src.md) | Provides the top-level Swing application shell and rendering framework for a quadtree visualization tool. I… |
| [quadtree-graphic/src/main/java/src/quadtree](modules/quadtree__graphic__src__main__java__src__quadtree.md) | Provides drawable/visualization wrappers around the core quadtree data structures, enabling rendering of qu… |
| [quadtree-graphic/src/main/java/src/quadtree/core](modules/quadtree__graphic__src__main__java__src__quadtree__core.md) | Provides the core quadtree spatial-indexing data structure for geographic points (latitude/longitude). It d… |


---

**Related surfaces.** [HLD Components](../hld/components.md) · [HLD Architecture](../hld/architecture.md) · [Codebase Guide](../guide/index.md)
