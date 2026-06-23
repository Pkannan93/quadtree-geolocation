# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Spatial data structure visualization / graphical rendering of quadtrees`_

## Responsibility

Provides a drawable/visualizable adapter layer over the core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, enabling rendering of quadtree boundaries and neighbor points on a graphical canvas with configurable scale factors.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file defines a drawable variant of a QuadTree that implements the Drawable interface, allowi… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable quadtree node that extends QuadTreeNode and implements Drawable, ena… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
