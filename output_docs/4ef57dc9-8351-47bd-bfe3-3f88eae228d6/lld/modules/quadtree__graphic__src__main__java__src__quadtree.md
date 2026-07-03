# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module provides drawable extensions of a core quadtree data structure, wrapping `src.quadtree.core.QuadTree` and `src.quadtree.core.QuadTreeNode` with rendering capabilities. Its public surface consists of `DrawableQuadTree` and `DrawableQuadTreeNode`, both of which implement the `src.Drawable` contract to enable on-screen visualization of node boundaries and neighbor points with zoom-dependent detail. This module functions as a visualization layer, delegating spatial logic to the core quadtree types while adding graphics-specific responsibilities.

The module exhibits zero fan-in and zero fan-out, indicating that no other module in the codebase depends on it and it does not transitively pull in any sibling modules—only the core quadtree collaborators (`src.quadtree.core.QuadTree`, `src.quadtree.core.QuadTreeNode`, `src.quadtree.core.Neighbour`) and the `src.Drawable` interface. This isolation makes it a leaf in the dependency graph, narrowing its side-effect surface to pure rendering concerns. The absence of dependent modules suggests the visualization layer is either used only at a composition root outside the analyzed scope or remains an extension point not yet wired into the runtime.

For file-level details—including the two implementations that comprise this module—consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src/quadtree`.

_Domain hint: `Spatial data structure visualization / graphics rendering`_

## Responsibility

Provides drawable/visualizable extensions of the core quadtree data structure. `DrawableQuadTree` extends the base `QuadTree` and delegates rendering to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` and implements `Drawable` to render node boundaries and neighbor points on screen (with zoom-dependent detail). This module is isolated in the dependency graph and serves as a visualization layer over an external quadtree core.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file defines a drawable quadtree data structure that extends the core QuadTree with renderin… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a DrawableQuadTreeNode class that extends QuadTreeNode and implements Drawable,… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
