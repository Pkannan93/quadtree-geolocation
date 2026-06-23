# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core QuadTree spatial indexing implementation for geographic neighbor lookup. Defines the `Neighbour` abstraction (id + lat/long), a recursive `QuadTreeNode` that subdivides space into quadrants, and a top-level `QuadTree` facade supporting insertion, removal, and range-based proximity queries. Geographic-distance-to-degree conversions and tuning parameters are centralized in `QuadTreeConstants`. The module is self-contained (isolated in the dependency graph) and intended to be consumed by higher-level visualization or query layers.

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

See also: [Modules index](index.md) — every module in this run.
