# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module provides graphical rendering capabilities for the core spatial data structures by extending `QuadTree` and `QuadTreeNode` with drawable subclasses. Its public surface exposes two symbols—`DrawableQuadTree` and `DrawableQuadTreeNode`—that wrap the core quadtree types with AWT-based coordinate mapping and recursive rendering logic. This module collaborates exclusively with `src.quadtree.core` (pulling in `QuadTree`, `QuadTreeNode`, and `Neighbour`) and the `src.Drawable` interface, establishing a clean separation between geometric logic and visualization concerns.

The module exhibits zero fan-in and zero fan-out at the module level, positioning it as a leaf in the dependency graph with no other modules consuming its drawable types. `DrawableQuadTree` acts as a thin adapter: it holds scaling parameters and delegates draw/update operations to a `DrawableQuadTreeNode` root, which performs the geographic-to-screen coordinate transformation and invokes AWT graphics primitives. Both files in the module remain undegraded, keeping the rendering surface tightly scoped.

For the file-level inventory and per-file purpose statements within this module, consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src/quadtree`.

_Domain hint: `Spatial data visualization (quadtree-based geographic rendering)`_

## Responsibility

Provides graphical/visual rendering capabilities for quadtree data structures by extending the core quadtree types (`QuadTree`, `QuadTreeNode`) with `Drawable`-compatible subclasses. `DrawableQuadTree` wraps a `DrawableQuadTreeNode` root with scaling parameters and delegates draw/update operations, while `DrawableQuadTreeNode` maps geographic longitude/latitude coordinates to screen coordinates and recursively renders nodes and their neighbours using Java AWT graphics.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file extends QuadTree to provide drawable/visual functionality by wrapping a DrawableQuadTre… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file extends QuadTreeNode to provide visualization capabilities for quadtree structures. It… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
