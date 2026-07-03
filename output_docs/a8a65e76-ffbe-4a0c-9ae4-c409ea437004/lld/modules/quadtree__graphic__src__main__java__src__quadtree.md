# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module provides a graphical visualization layer for the quadtree data structure by wrapping core quadtree types with rendering capability. Its public surface comprises two classes—`DrawableQuadTree` and `DrawableQuadTreeNode`—that adapt `src.quadtree.core.QuadTree` and `src.quadtree.core.QuadTreeNode` to the `src.Drawable` interface, enabling spatial bounds and neighbor points to be rendered on a graphics canvas with zoom-dependent detail. This module has zero fan-in and zero fan-out at the module level, indicating it occupies a leaf position in the dependency graph yet reaches across to `src.quadtree.core` for the underlying spatial logic and to `src.Drawable` for the rendering contract.

The collaborator list shows four distinct symbols—`src.Drawable`, `src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, and `src.quadtree.core.Neighbour`—confirming that rendering concerns are strictly layered atop the core spatial data structure without introducing bidirectional coupling. `DrawableQuadTree` delegates draw and update calls to a `DrawableQuadTreeNode` root, which extends `QuadTreeNode` to paint spatial regions and neighbor markers. Both files in this module are non-degraded, meaning their purpose and structure remain consistent with the stated responsibility.

For the complete file listing and per-file purpose summaries, consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree`.

_Domain hint: `Spatial data structure visualization / 2D graphics rendering`_

## Responsibility

Provides a graphical visualization layer for the quadtree data structure by wrapping core quadtree types with rendering capability. `DrawableQuadTree` adapts a `QuadTree` to the `Drawable` interface, delegating draw and update calls to a `DrawableQuadTreeNode` root, which extends `QuadTreeNode` to render spatial bounds and neighbor points on a graphics canvas with zoom-dependent detail.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper class for a QuadTree data structure, implementing the Drawa… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | Provides a drawable implementation of a quadtree node that extends QuadTreeNode with visualizatio… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
