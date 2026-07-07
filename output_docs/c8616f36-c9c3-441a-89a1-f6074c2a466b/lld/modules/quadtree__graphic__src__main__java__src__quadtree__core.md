# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module implements the foundational spatial-indexing data structure for geographic latitude/longitude queries, exposing a twelve-symbol public surface that includes `QuadTree`, `QuadTreeNode`, `Neighbour`, and operations like `findNeighboursWithinRectangle` and `addNeighbour`. This is a leaf module with zero fan-in and zero fan-out—no collaborators consume its exports, and it pulls in no other application modules—positioning it as a reusable library component that higher-level layers can depend on without introducing coupling. The recursive `QuadTreeNode` subdivides 2D space into quadrants and stores `NeighbourImpl` instances at leaf boundaries, while `QuadTreeConstants` provides shared configuration (maximum depth, capacity thresholds) and coordinate conversion via `kmToDegree`.

Because the module sits entirely disconnected from the rest of the system's dependency graph, it carries no layering obligations and can be composed into any parent without risk of cyclic reference. The public surface cleanly separates the `Neighbour` abstraction from its concrete `NeighbourImpl` data holder, and the `QuadTree` facade encapsulates both insertion (`addNeighbour`) and range-query workflows (`findNeighbours`, `findNeighboursIds`). Developers integrating this module should note that its self-contained design makes it trivial to vendor or extract as a standalone spatial-index library.

For a file-by-file breakdown of `Neighbour.java`, `QuadTree.java`, `QuadTreeNode.java`, `QuadTreeConstants.java`, and `NeighbourImpl.java`, consult the Codebase Guide entry for this module.

_Domain hint: `Geospatial indexing / quadtree spatial data structures`_

## Responsibility

Provides the core quadtree spatial-indexing data structure for geographic points (latitude/longitude). It defines the `Neighbour` abstraction and its `NeighbourImpl` data holder, the top-level `QuadTree` API for adding/removing points and performing radius-based range queries, the recursive `QuadTreeNode` that subdivides 2D space into quadrants and stores neighbors at leaf nodes, and shared configuration plus coordinate-conversion utilities in `QuadTreeConstants`. The module is self-contained (isolated in the dependency graph) and exposes a reusable spatial index intended to be consumed by higher-level quadtree/graphic layers.

## At a glance

| Dimension | Value |
|---|---|
| Files | 5 |
| Public surface | 12 symbol(s) |
| Collaborators | 0 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

## Public surface

- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `QuadTreeNode`
- `QuadTreeConstants`
- `addNeighbour`
- `findNeighbours`
- `findNeighboursIds`
- `getRangeAsRectangle`
- `removeNeighbour`
- `findNeighboursWithinRectangle`
- `kmToDegree`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines an interface for neighbor objects in a quadtree structure, specifying that neighbors must… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | This file implements the Neighbour interface to represent a geographic neighbor entity with an id… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a QuadTree data structure for spatial indexing and querying of geographic neighbors us… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+2) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines constants and utility methods for QuadTree operations, including configuration values for… | `QuadTreeConstants`, `kmToDegree` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTree spatial data structure node that recursively subdivides 2D geographic space… | `QuadTreeNode`, `addNeighbour`, `removeNeighbour`, … (+1) |


---

**Related surfaces.** [Codebase Guide entry](../../guide/modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
