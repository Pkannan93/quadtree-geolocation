# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Spatial indexing / 2D graphical visualization of quadtrees`_

## Responsibility

Provides a graphical/drawable layer over the core quadtree data structure by extending `QuadTree` and `QuadTreeNode` with Java2D rendering capabilities. It renders quadtree node boundaries as rectangles and visualizes neighbor relationships with zoom-level-dependent detail, while delegating spatial indexing operations (subdivision, neighbor lookup) to the underlying core quadtree implementation.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file defines DrawableQuadTree, which extends QuadTree to add graphical rendering capabilitie… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file provides a drawable extension of QuadTreeNode that enables visualization of quadtree st… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
