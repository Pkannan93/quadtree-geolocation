# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core QuadTree spatial indexing implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` abstraction (interface plus `NeighbourImpl`) representing points with an ID and coordinates, and exposes a `QuadTree` facade backed by recursive `QuadTreeNode` subdivision to support insertion and radius-based neighbor lookups (in kilometers, converted via `QuadTreeConstants`). This module is self-contained (isolated in the dependency graph) and offers the reusable spatial data structure that other layers of the quadtree-graphic application would build upon.

## Public surface

- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `addNeighbour`
- `findNeighbours`
- `findNeighboursIds`
- `QuadTreeNode`
- `QuadTreeConstants`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines an interface for representing geographic neighbors in the quadtree system. Provides a con… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | This file implements the Neighbour interface to represent a neighbor entity with an ID and geogra… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | This file implements a QuadTree data structure for efficiently storing and querying geographic ne… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines constants for QuadTree operations, specifically providing conversion factors between kilo… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTreeNode class that represents nodes in a spatial indexing QuadTree structure fo… | `QuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
