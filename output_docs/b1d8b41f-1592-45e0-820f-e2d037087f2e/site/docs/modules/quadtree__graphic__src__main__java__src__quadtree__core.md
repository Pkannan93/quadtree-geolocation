# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides a self-contained quadtree spatial indexing core for geographic data. Defines the `Neighbour` abstraction for points with id and lat/lon coordinates (`NeighbourImpl`), recursive node subdivision and search via `QuadTreeNode`, and the public `QuadTree` facade for inserting points and querying neighbors within a kilometer-based radius. `QuadTreeConstants` centralizes minimum node size configuration and km-to-degree conversion. The module is isolated (no internal fan-in/fan-out), making it a standalone library suitable for embedding in spatial-search applications.

## Public surface

- `Neighbour`
- `NeighbourImpl`
- `QuadTree`
- `QuadTreeNode`
- `QuadTreeConstants`
- `addNeighbour`
- `findNeighbours`
- `findNeighboursIds`

## Files in this module

| File | Purpose | Exports |
|---|---|---|
| `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java` | Defines the Neighbour interface for objects that represent spatial neighbors in a quadtree struct… | `Neighbour` |
| `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java` | This file provides a concrete implementation of the Neighbour interface, representing a geographi… | `NeighbourImpl` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java` | Implements a QuadTree data structure for efficient spatial indexing and querying of geographic ne… | `QuadTree`, `addNeighbour`, `findNeighbours`, … (+1) |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java` | Defines configuration constants for quadtree data structures, including minimum node sizes in bot… | `QuadTreeConstants` |
| `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java` | Implements a QuadTreeNode class for spatial indexing, managing geographic bounds divided into fou… | `QuadTreeNode` |

---

See also: [Modules index](index.md) — every module in this run.
