# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / spatial data structures`_

## Responsibility

Provides the core quadtree spatial index implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` entity contract and its `NeighbourImpl` implementation, the recursive `QuadTreeNode` for spatial partitioning, the top-level `QuadTree` facade exposing insertion and proximity search, and `QuadTreeConstants` utilities for unit conversions (e.g., kilometers to degrees). This module is self-contained (isolated in the dependency graph) and serves as the underlying spatial data structure to be consumed by higher-level graphic/visualization layers.

## Public surface

- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `QuadTreeNode`
- `QuadTreeConstants`
- `addNeighbour`
- `findNeighbours`
- `findNeighboursIds`
- `kmToDegree`
- `getId`
- `getLatitude`
- `getLongitude`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines an interface contract for objects representing a neighbour entity with an ID and geograph… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | Implements the Neighbour interface to represent a geographical entity with an ID and coordinates… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a QuadTree spatial index data structure for efficiently storing and querying geographi… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines constants and utility methods for quadtree operations. Provides conversion functionality… | `QuadTreeConstants`, `kmToDegree` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTreeNode class that represents nodes in a quadtree spatial data structure for pa… | `QuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
