# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module acts as an adapter layer that wraps the core quadtree data structure with visualization capabilities. Its public surface exports `DrawableQuadTree` and `DrawableQuadTreeNode`, both implementing `src.Drawable` to provide a rendering contract for the spatial partitioning logic. This design isolates graphical concerns from the core `src.quadtree.core.QuadTree` and `src.quadtree.core.QuadTreeNode` types, allowing the underlying data structure to remain presentation-agnostic while enabling canvas-based rendering with configurable scale factors.

Despite sitting alongside the core package, this module exhibits zero fan-in and zero fan-out, indicating it is neither depended upon by other modules nor does it depend on any sibling modules at the architectural level. The four collaborators—`src.Drawable`, the two core quadtree types, and `src.quadtree.core.Neighbour`—are all intra-package references. This isolation suggests the drawable variants are consumed directly by application-level or UI-layer code rather than flowing through intermediate architectural layers, a pattern consistent with leaf presentation adapters.

For the two source files and their internal structure, consult the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree`, which enumerates `DrawableQuadTree.java` and `DrawableQuadTreeNode.java` with per-file purpose summaries and implementation details.

_Domain hint: `Spatial data structure visualization / graphical rendering of quadtrees`_

## Responsibility

Provides a drawable/visualizable adapter layer over the core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, enabling rendering of quadtree boundaries and neighbor points on a graphical canvas with configurable scale factors.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file defines a drawable variant of a QuadTree that implements the Drawable interface, allowi… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable quadtree node that extends QuadTreeNode and implements Drawable, ena… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
