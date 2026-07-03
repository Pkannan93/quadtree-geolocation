# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module exposes `DrawableQuadTree` and `DrawableQuadTreeNode`, both subclassing their counterparts in `src.quadtree.core` and implementing the `src.Drawable` interface to render spatial partition boundaries and contained `Neighbour` objects onto a graphics context. This module has zero fan-in and zero fan-out, indicating that no other module in the system depends on it and it depends on no peer modules—only on the core quadtree types and the `Drawable` contract. The design trades generality for a targeted visualization capability: by extending `QuadTree` and `QuadTreeNode` rather than composing them, the drawable variants inherit the entire spatial indexing surface but couple tightly to the core implementation hierarchy.

The public surface comprises only the two drawable subclasses; both implement coordinate scaling and bounds-aware rectangle rendering for nodes and their contained neighbours. The collaborator set is minimal—`src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour`, and `src.Drawable`—reflecting the module's role as a leaf adapter that bridges spatial data structures to a rendering pipeline. With no dependents, changes to this module's rendering logic remain isolated, though any breaking change to the `QuadTree` or `QuadTreeNode` base classes will cascade here.

For the complete file listing and per-file responsibilities within this module, consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree`.

_Domain hint: `Spatial data structure visualization (quadtree rendering)`_

## Responsibility

Provides graphical/drawable extensions to a core quadtree data structure for visualization purposes. `DrawableQuadTree` subclasses `QuadTree` and `DrawableQuadTreeNode` subclasses `QuadTreeNode`, both implementing a `Drawable` interface to render node boundaries and contained neighbours as rectangles on a graphics context, with support for coordinate scaling and bounds.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | Extends QuadTree to provide drawable/graphical capabilities for visualization, implementing the D… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file extends QuadTreeNode to provide drawable/renderable capabilities for visualization. It… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
