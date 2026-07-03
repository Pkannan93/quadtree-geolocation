# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / spatial data structures`_

## Responsibility

Provides the core quadtree spatial data structure for indexing and querying geographic entities (neighbours) by latitude/longitude. Defines the `Neighbour` abstraction and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that partitions space and supports add/remove/range-search, the top-level `QuadTree` facade that exposes add and range-query operations (including km-based range conversion), and `QuadTreeConstants` holding tuning parameters such as max node capacity and km-to-degree conversion factors. The module is self-contained (isolated in the dependency graph) and serves as a reusable spatial index library.

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
- `findNeighboursWithinRectangle`
- `removeNeighbour`
- `getId`
- `getLatitude`
- `getLongitude`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines an interface for representing a neighbor entity in a quadtree system. The interface speci… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | Implements the Neighbour interface to represent a geographic neighbor with an identifier and coor… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a quadtree data structure for efficiently storing and querying geographic neighbors ba… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+2) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | This file defines configuration constants for quadtree operations, specifically the maximum node… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTreeNode class representing nodes in a quadtree spatial data structure for effic… | `QuadTreeNode`, `addNeighbour`, `removeNeighbour`, … (+1) |

---

See also: [Modules index](index.md) — every module in this run.
