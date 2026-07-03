# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Geospatial data visualization (quadtree-based spatial indexing rendering)`_

## Responsibility

Provides a graphical/drawable visualization layer over a core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` from `src.quadtree.core` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, rendering quadtree boundaries and neighbour points by scaling latitude/longitude geographic coordinates to screen coordinates.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper around the core QuadTree data structure, enabling graphical… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable wrapper for quadtree nodes that enables visualization of the quadtre… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
