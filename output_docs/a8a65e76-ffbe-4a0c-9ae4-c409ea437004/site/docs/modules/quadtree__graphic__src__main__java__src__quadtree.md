# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Spatial data structure visualization / 2D graphics rendering`_

## Responsibility

Provides a graphical visualization layer for the quadtree data structure by wrapping core quadtree types with rendering capability. `DrawableQuadTree` adapts a `QuadTree` to the `Drawable` interface, delegating draw and update calls to a `DrawableQuadTreeNode` root, which extends `QuadTreeNode` to render spatial bounds and neighbor points on a graphics canvas with zoom-dependent detail.

## Public surface

- `DrawableQuadTree`
- `DrawableQuadTreeNode`

## Collaborators

- `src.Drawable`
- `src.quadtree.core.QuadTree`
- `src.quadtree.core.QuadTreeNode`
- `src.quadtree.core.Neighbour`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper class for a QuadTree data structure, implementing the Drawa… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | Provides a drawable implementation of a quadtree node that extends QuadTreeNode with visualizatio… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
