# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Graphical visualization of spatial quadtree data structures`_

## Responsibility

Provides drawable wrapper classes that adapt the core QuadTree data structures for graphical rendering. `DrawableQuadTree` wraps `QuadTree` and `DrawableQuadTreeNode` wraps `QuadTreeNode`, delegating draw and update operations to render node boundaries, child nodes, and neighbor points with coordinate scaling and translation support.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper class for QuadTree that enables the quadtree data structure… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable wrapper for QuadTreeNode that adds graphical rendering capabilities.… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
