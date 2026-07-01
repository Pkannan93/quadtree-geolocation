# Module — `quadtree-graphic/src/main/java/src/quadtree`

_Domain hint: `Geospatial data visualization / quadtree spatial indexing`_

## Responsibility

Provides drawable/visualization wrappers around the core quadtree data structures, enabling rendering of quadtree spatial subdivisions and neighbor relationships onto a graphics canvas. `DrawableQuadTree` delegates drawing operations to its root `DrawableQuadTreeNode`, which extends `QuadTreeNode` with rendering logic for geographic spatial data and neighbor points. This module is currently isolated in the dependency graph (no internal fan-in or fan-out), bridging the core quadtree implementation with a `Drawable` rendering interface.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper for QuadTree that implements the Drawable interface, enabli… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable quadtree node that extends QuadTreeNode with rendering capabilities… | `DrawableQuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
