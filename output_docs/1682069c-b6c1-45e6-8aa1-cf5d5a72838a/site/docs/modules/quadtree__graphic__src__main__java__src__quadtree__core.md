# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core quadtree spatial indexing implementation for geographic point data. Defines a `Neighbour` abstraction (id + latitude/longitude) with a concrete `NeighbourImpl`, recursively subdivides 2D space via `QuadTreeNode`, and exposes a top-level `QuadTree` API for inserting neighbours and performing range queries by lat/lon. `QuadTreeConstants` centralizes tuning parameters and km↔degree conversion utilities used during spatial searches. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial-indexing engine for the surrounding quadtree-graphic application.

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

See also: [Modules index](index.md) — every module in this run.
