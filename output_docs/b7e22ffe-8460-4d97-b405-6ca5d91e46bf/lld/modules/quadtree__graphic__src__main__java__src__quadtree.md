# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module serves as a graphical adapter layer, wrapping the core quadtree data structure (`src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`) to expose a visualization-ready interface through `DrawableQuadTree` and `DrawableQuadTreeNode`. Both classes implement `src.Drawable`, allowing the spatial bounds and neighbour relationships of quadtree nodes to be rendered via `Rectangle2D` primitives without coupling the core spatial logic to any graphics framework. This module's public surface is deliberately narrow—just two exported symbols—reflecting a focused adapter responsibility that bridges domain logic and presentation.

The collaborator set is stable: the module consumes four symbols from the core quadtree package and the `Drawable` abstraction but produces no outbound dependencies on other modules, yielding zero fan-out. Conversely, no other modules depend on `quadtree-graphic/src/main/java/src/quadtree`, resulting in zero fan-in; this isolation suggests the module may be a leaf in a larger visualization pipeline or that consuming modules reside outside the analyzed codebase scope. The absence of degraded files and the clean alignment between public surface and responsibility indicate a well-contained adapter.

For a complete file inventory and per-file purpose statements, consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree`, which documents both `DrawableQuadTree.java` and `DrawableQuadTreeNode.java` in detail.

_Domain hint: `Spatial data structure visualization (quadtree rendering for 2D graphics)`_

## Responsibility

Provides a graphical/drawable adapter layer over a core quadtree data structure, enabling visualization of quadtree nodes, their spatial bounds, and neighbour relationships within a graphics system. `DrawableQuadTree` wraps a `QuadTree` and delegates draw/update calls to a root `DrawableQuadTreeNode`, which extends `QuadTreeNode` to add rendering of boundaries and neighbour links via `Rectangle2D`. The module is isolated in the dependency graph but logically depends on a core quadtree package and a `Drawable` abstraction.

## At a glance

| Dimension | Value |
|---|---|
| Files | 2 |
| Public surface | 2 symbol(s) |
| Collaborators | 4 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `DrawableQuadTree`
- `DrawableQuadTreeNode`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper for a QuadTree data structure, enabling visualization by de… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file implements a drawable visualization layer for quadtree nodes, extending QuadTreeNode wi… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
