# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / spatial data structures`_

## Responsibility

Provides the core quadtree spatial indexing implementation for geographic data. Defines the `Neighbour` abstraction (with a concrete `NeighbourImpl`) representing identifiable points by latitude/longitude, and exposes a `QuadTree` that recursively subdivides space via `QuadTreeNode` to support insertion (`addNeighbour`) and radius-based proximity queries (`findNeighbours`, `findNeighboursIds`). `QuadTreeConstants` centralizes configuration such as the minimum node size and degree-to-kilometer conversion. This module is self-contained (isolated in the dependency graph) and serves as the reusable spatial indexing engine for the broader quadtree-graphic application.

## Public surface

- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `QuadTreeNode`
- `QuadTreeConstants`
- `addNeighbour`
- `findNeighbours`
- `findNeighboursIds`
- `QUADTREE_LAST_NODE_SIZE_IN_KM`
- `QUADTREE_LAST_NODE_SIZE_IN_DEGREE`
- `ONE_DEGREE_IN_KM`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines the Neighbour interface, which represents a spatial object with an identifier and geograp… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | Implements the Neighbour interface to provide a concrete representation of a geographical neighbo… | `NeighbourImpl`, `getId`, `getLatitude`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a quadtree data structure for efficient spatial indexing and querying of neighbors bas… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines global constants for quadtree configuration, including the minimum node size in both kilo… | `QuadTreeConstants`, `QUADTREE_LAST_NODE_SIZE_IN_KM`, `QUADTREE_LAST_NODE_SIZE_IN_DEGREE`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTreeNode that represents a node in a quadtree spatial data structure for efficie… | `QuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
