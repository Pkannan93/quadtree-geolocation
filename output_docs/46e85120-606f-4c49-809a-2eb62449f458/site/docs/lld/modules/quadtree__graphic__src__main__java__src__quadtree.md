# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module supplies a rendering façade over the core spatial index by subclassing `src.quadtree.core.QuadTree` and `src.quadtree.core.QuadTreeNode` to expose `DrawableQuadTree` and `DrawableQuadTreeNode`. Both classes implement `src.Drawable` and use Java2D primitives to draw node boundaries as rectangles and to visualize neighbor relationships returned by `src.quadtree.core.Neighbour` queries, adjusting detail by zoom level. This composition-via-inheritance allows the graphical layer to reuse subdivision logic and neighbor lookup without duplicating the spatial indexing code. The public surface of two classes keeps the module tightly scoped to rendering concerns while delegating all quadtree operations—insert, query, neighbor discovery—to the core types.

With zero fan-in and zero fan-out at the module level, this module currently sits isolated in the dependency graph, suggesting either it is consumed by code outside the analyzed scope or the system has not yet wired the drawable quadtree into a higher-level coordinator. The collaborator count of four confirms the module's single responsibility: it bridges the gap between the core spatial index and any visualization layer that depends on `src.Drawable`. Developers seeking to understand how quadtree nodes are rendered or how neighbor relationships appear on-screen should start here, then trace calls back to the core for the underlying spatial logic.

For the complete file listing and line-level purpose statements, refer to the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree`.

_Domain hint: `Spatial indexing / 2D graphical visualization of quadtrees`_

## Responsibility

Provides a graphical/drawable layer over the core quadtree data structure by extending `QuadTree` and `QuadTreeNode` with Java2D rendering capabilities. It renders quadtree node boundaries as rectangles and visualizes neighbor relationships with zoom-level-dependent detail, while delegating spatial indexing operations (subdivision, neighbor lookup) to the underlying core quadtree implementation.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file defines DrawableQuadTree, which extends QuadTree to add graphical rendering capabilitie… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file provides a drawable extension of QuadTreeNode that enables visualization of quadtree st… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
