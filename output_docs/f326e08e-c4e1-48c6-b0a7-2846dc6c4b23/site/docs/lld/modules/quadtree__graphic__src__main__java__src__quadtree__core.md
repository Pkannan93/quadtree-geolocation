# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module carries sole responsibility for spatial indexing of geographic point data, offering a classic quadtree implementation with no dependencies on other modules in the codebase. It defines a `Neighbour` abstraction for lat/lon entities alongside a concrete `NeighbourImpl`, then recursively partitions 2D space through `QuadTreeNode` to support efficient proximity search via the top-level `QuadTree` façade. `QuadTreeConstants` centralizes tuning parameters and kilometre-to-degree conversions that govern range-query precision.

With zero fan-in and zero fan-out this module is a leaf in the dependency graph—it neither depends on nor is depended upon by any collaborators visible at module granularity, making it a self-contained spatial-indexing engine ready to be wired into the surrounding quadtree-graphic application. The public surface exports eleven symbols: the four core types (`Neighbour`, `NeighbourImpl`, `QuadTree`, `QuadTreeNode`), the constants holder, and six methods (`addNeighbour`, `findNeighbours`, `findNeighboursIds`, `getId`, `getLatitude`, `getLongitude`) that together expose insertion, query, and accessor operations. Because the module is isolated it offers a clean integration point for any consumer that needs geospatial indexing without pulling in transitive dependencies.

For the complete file listing and individual file purposes within `quadtree-graphic/src/main/java/src/quadtree/core`, see the corresponding entry in the Codebase Guide.

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core quadtree spatial indexing implementation for geographic point data. Defines a `Neighbour` abstraction (id + latitude/longitude) with a concrete `NeighbourImpl`, recursively subdivides 2D space via `QuadTreeNode`, and exposes a top-level `QuadTree` API for inserting neighbours and performing range queries by lat/lon. `QuadTreeConstants` centralizes tuning parameters and km↔degree conversion utilities used during spatial searches. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial-indexing engine for the surrounding quadtree-graphic application.

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
- `findNeighbours`
- `findNeighboursIds`
- `getId`
- `getLatitude`
- `getLongitude`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines an interface for representing a neighbour entity in a quadtree structure, requiring imple… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | Implements the Neighbour interface to represent a geographic point with an identifier and coordin… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a quadtree data structure for spatial indexing and efficient querying of geographic ne… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines constants and utility methods for QuadTree operations, including conversions between kilo… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | This file implements a QuadTreeNode class representing a node in a spatial quadtree data structur… | `QuadTreeNode` |


---

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
