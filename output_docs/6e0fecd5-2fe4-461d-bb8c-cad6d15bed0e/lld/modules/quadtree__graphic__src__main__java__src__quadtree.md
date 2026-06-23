# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module serves as the presentation adapter layer, wrapping core spatial data structures with drawable capabilities for graphical rendering. Its public surface exposes `DrawableQuadTree` and `DrawableQuadTreeNode`, both of which delegate to `src.quadtree.core.QuadTree` and `src.quadtree.core.QuadTreeNode` while adding coordinate scaling, translation, and boundary visualization. With zero fan-in and zero fan-out at the module level, this sits as a leaf module in the dependency graph—it pulls in core collaborators (`src.Drawable`, `src.quadtree.core.Neighbour`) but no other modules depend on it, indicating it's a terminal consumer in the composition.

The module's coupling is narrow: four collaborators total, all originating from the `src` package hierarchy. `DrawableQuadTree` and `DrawableQuadTreeNode` inherit the tree traversal semantics of their wrapped counterparts while implementing the `src.Drawable` contract, allowing the rendering pipeline to treat quadtree nodes uniformly. The absence of dependent modules suggests this adapter is consumed directly by a composition root or main entry point elsewhere in the codebase, rather than being layered beneath other abstractions.

For the two files that implement this responsibility—`DrawableQuadTree.java` and `DrawableQuadTreeNode.java`—refer to the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree`, which enumerates each file's purpose and internal structure.

_Domain hint: `Graphical visualization of spatial quadtree data structures`_

## Responsibility

Provides drawable wrapper classes that adapt the core QuadTree data structures for graphical rendering. `DrawableQuadTree` wraps `QuadTree` and `DrawableQuadTreeNode` wraps `QuadTreeNode`, delegating draw and update operations to render node boundaries, child nodes, and neighbor points with coordinate scaling and translation support.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper class for QuadTree that enables the quadtree data structure… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable wrapper for QuadTreeNode that adds graphical rendering capabilities.… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
