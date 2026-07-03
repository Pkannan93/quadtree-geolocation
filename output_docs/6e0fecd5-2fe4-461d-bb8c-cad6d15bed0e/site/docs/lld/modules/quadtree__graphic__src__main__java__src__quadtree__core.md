# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The module at `quadtree-graphic/src/main/java/src/quadtree/core` provides a self-contained spatial indexing engine for geographic neighbor lookup, exposing `QuadTree` as its primary facade alongside the `Neighbour` abstraction and recursive `QuadTreeNode` for quadrant subdivision. With zero fan-in and zero fan-out, this module is a true leaf: it neither imports collaborators from other modules nor is consumed by any dependent within the current codebase, suggesting it may serve as a standalone library or remains unintegrated into higher visualization or query layers. The public surface of eleven exports includes insertion operations (`addNeighbour`, `removeNeighbour`), proximity queries (`findNeighbours`, `findNeighboursIds`, `findNeighboursWithinRectangle`), and `QuadTreeConstants` for geographic-to-degree conversion tuning.

The isolation signals an opportunity and a risk: as a leaf module it carries no transitive coupling, but the absence of dependents means its runtime behaviour and query correctness may not yet be exercised by production code paths. The five files—`Neighbour.java`, `NeighbourImpl.java`, `QuadTree.java`, `QuadTreeNode.java`, and `QuadTreeConstants.java`—form a cohesive unit with no degraded symbols, and the recursive node structure hints at standard quadtree decomposition semantics. For implementers integrating this module or validating its spatial partitioning logic, the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree/core` enumerates all five files and their individual purposes.

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core QuadTree spatial indexing implementation for geographic neighbor lookup. Defines the `Neighbour` abstraction (id + lat/long), a recursive `QuadTreeNode` that subdivides space into quadrants, and a top-level `QuadTree` facade supporting insertion, removal, and range-based proximity queries. Geographic-distance-to-degree conversions and tuning parameters are centralized in `QuadTreeConstants`. The module is self-contained (isolated in the dependency graph) and intended to be consumed by higher-level visualization or query layers.

## At a glance

| Dimension | Value |
|---|---|
| Files | 5 |
| Public surface | 11 symbol(s) |
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
- `removeNeighbour`
- `findNeighbours`
- `findNeighboursIds`
- `findNeighboursWithinRectangle`
- `getRangeAsRectangle`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines the interface for representing a geographic neighbor entity in the quadtree system. This… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | Implements the Neighbour interface to represent a geographic point with an id and latitude/longit… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | This file implements a QuadTree data structure for efficient spatial indexing and querying of geo… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+2) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | This file defines constants and utility methods for QuadTree operations, particularly for convert… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a spatial QuadTree node for efficient spatial indexing and querying of Neighbour objec… | `QuadTreeNode`, `addNeighbour`, `removeNeighbour`, … (+1) |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
