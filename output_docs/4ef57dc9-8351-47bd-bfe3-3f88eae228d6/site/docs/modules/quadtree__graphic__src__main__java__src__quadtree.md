# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Spatial data structure visualization / graphics rendering`_

## Responsibility

Provides drawable/visualizable extensions of the core quadtree data structure. `DrawableQuadTree` extends the base `QuadTree` and delegates rendering to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` and implements `Drawable` to render node boundaries and neighbor points on screen (with zoom-dependent detail). This module is isolated in the dependency graph and serves as a visualization layer over an external quadtree core.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file defines a drawable quadtree data structure that extends the core QuadTree with renderin… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a DrawableQuadTreeNode class that extends QuadTreeNode and implements Drawable,… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
