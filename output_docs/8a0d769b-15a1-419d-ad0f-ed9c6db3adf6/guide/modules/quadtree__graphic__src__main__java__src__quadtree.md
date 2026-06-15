# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Spatial data structure visualization (quadtree rendering)`_

## Responsibility

Provides graphical/drawable extensions to a core quadtree data structure for visualization purposes. `DrawableQuadTree` subclasses `QuadTree` and `DrawableQuadTreeNode` subclasses `QuadTreeNode`, both implementing a `Drawable` interface to render node boundaries and contained neighbours as rectangles on a graphics context, with support for coordinate scaling and bounds.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | Extends QuadTree to provide drawable/graphical capabilities for visualization, implementing the D… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file extends QuadTreeNode to provide drawable/renderable capabilities for visualization. It… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
