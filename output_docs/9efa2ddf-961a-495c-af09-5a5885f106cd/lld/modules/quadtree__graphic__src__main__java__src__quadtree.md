# Module — `quadtree-graphic/src/main/java/src/quadtree` (LLD)

The module at `quadtree-graphic/src/main/java/src/quadtree` serves as a visualization adapter that wraps the core quadtree spatial index with drawable presentation logic. It exports `DrawableQuadTree` and `DrawableQuadTreeNode`, both of which implement the `src.Drawable` interface and delegate spatial operations to `src.quadtree.core.QuadTree` and `src.quadtree.core.QuadTreeNode` respectively, while adding the capability to render geographic boundaries and neighbour points by projecting latitude/longitude coordinates onto screen space.

This module's public surface couples tightly to four collaborators: the `Drawable` contract it must satisfy, the two core quadtree classes it decorates, and the `Neighbour` type whose geographic coordinates it renders. Despite this coupling, the module exhibits zero fan-in and zero fan-out at the module level, indicating it neither depends on nor is depended upon by other *module directories*—its collaborators all resolve to individual classes rather than sibling module boundaries. This isolation simplifies reasoning about side-effect surface but also signals that the drawable layer may not yet be integrated into a broader rendering pipeline.

For a detailed file-level breakdown of `DrawableQuadTree.java` and `DrawableQuadTreeNode.java`, consult the Codebase Guide entry for this module, which enumerates all source files and their individual responsibilities within the visualization adapter.

_Domain hint: `Geospatial data visualization (quadtree-based spatial indexing rendering)`_

## Responsibility

Provides a graphical/drawable visualization layer over a core QuadTree data structure. It wraps `QuadTree` and `QuadTreeNode` from `src.quadtree.core` with `DrawableQuadTree` and `DrawableQuadTreeNode` classes that implement the `Drawable` interface, rendering quadtree boundaries and neighbour points by scaling latitude/longitude geographic coordinates to screen coordinates.

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
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java` | This file provides a drawable wrapper around the core QuadTree data structure, enabling graphical… | `DrawableQuadTree` |
| `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java` | This file defines a drawable wrapper for quadtree nodes that enables visualization of the quadtre… | `DrawableQuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
