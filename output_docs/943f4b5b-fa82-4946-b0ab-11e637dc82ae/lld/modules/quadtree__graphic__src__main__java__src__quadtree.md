# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree` module exposes two wrappers—`DrawableQuadTree` and `DrawableQuadTreeNode`—that adapt the core quadtree spatial index for rendering onto a graphics canvas. Both classes compose instances from `src.quadtree.core` (specifically `QuadTree`, `QuadTreeNode`, and `Neighbour`) and implement the `src.Drawable` interface, allowing geographic subdivisions and neighbor points to be visualized without modifying the core data structures. `DrawableQuadTree` acts as the entry point, delegating draw calls to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` to add rendering logic for boundaries and neighbor markers. This composition approach keeps the core quadtree implementation decoupled from presentation concerns.

Despite a well-defined public surface, the module currently shows zero fan-in and zero fan-out within the internal dependency graph, suggesting it is either freshly introduced or rendered temporarily unreachable by recent refactoring. No other modules in the codebase consume `DrawableQuadTree` or `DrawableQuadTreeNode` at this snapshot, which may indicate an integration seam still under construction or a layer violation if calling code resides outside the scanned source tree. The module depends on four collaborators but contributes to no downstream consumers, making it effectively a leaf in its current state.

For the two files implementing these wrappers and their internal delegation strategy, refer to the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src/quadtree`.

_Domain hint: `Geospatial data visualization / quadtree spatial indexing`_

## Responsibility

Provides drawable/visualization wrappers around the core quadtree data structures, enabling rendering of quadtree spatial subdivisions and neighbor relationships onto a graphics canvas. `DrawableQuadTree` delegates drawing operations to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` with rendering logic for geographic spatial data and neighbor points. This module is currently isolated in the dependency graph (no internal fan-in or fan-out), bridging the core quadtree implementation with a `Drawable` rendering interface.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper for QuadTree that implements the Drawable interface, enabli… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable quadtree node that extends QuadTreeNode with rendering capabilities… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
