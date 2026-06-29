# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Spatial data visualization (quadtree-based geographic rendering)`_

## Responsibility

Provides graphical/visual rendering capabilities for quadtree data structures by extending the core quadtree types (`QuadTree`, `QuadTreeNode`) with `Drawable`-compatible subclasses. `DrawableQuadTree` wraps a `DrawableQuadTreeNode` root with scaling parameters and delegates draw/update operations, while `DrawableQuadTreeNode` maps geographic longitude/latitude coordinates to screen coordinates and recursively renders nodes and their neighbours using Java AWT graphics.

## Public surface

- `DrawableQuadTree`
- `DrawableQuadTreeNode`

## Collaborators

- `src.quadtree.core.QuadTree`
- `src.quadtree.core.QuadTreeNode`
- `src.quadtree.core.Neighbour`
- `src.Drawable`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file extends QuadTree to provide drawable/visual functionality by wrapping a DrawableQuadTre… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file extends QuadTreeNode to provide visualization capabilities for quadtree structures. It… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
