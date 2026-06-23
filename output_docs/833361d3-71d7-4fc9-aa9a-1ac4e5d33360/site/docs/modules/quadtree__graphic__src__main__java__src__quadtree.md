# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Spatial data structure visualization (quadtree rendering for 2D graphics)`_

## Responsibility

Provides a graphical/drawable adapter layer over a core quadtree data structure, enabling visualization of quadtree nodes, their spatial bounds, and neighbour relationships within a graphics system. `DrawableQuadTree` wraps a `QuadTree` and delegates draw/update calls to a root `DrawableQuadTreeNode`, which extends `QuadTreeNode` to add rendering of boundaries and neighbour links via `Rectangle2D`. The module is isolated in the dependency graph but logically depends on a core quadtree package and a `Drawable` abstraction.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper for a QuadTree data structure, enabling visualization by de… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file implements a drawable visualization layer for quadtree nodes, extending QuadTreeNode wi… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
