# Module — `quadtree-graphic/src/main/java/src/quadtree/core`

_Domain hint: `Geospatial indexing / quadtree spatial data structures`_

## Responsibility

Provides the core quadtree spatial-indexing data structure for geographic points (latitude/longitude). It defines the `Neighbour` abstraction and its `NeighbourImpl` data holder, the top-level `QuadTree` API for adding/removing points and performing radius-based range queries, the recursive `QuadTreeNode` that subdivides 2D space into quadrants and stores neighbors at leaf nodes, and shared configuration plus coordinate-conversion utilities in `QuadTreeConstants`. The module is self-contained (isolated in the dependency graph) and exposes a reusable spatial index intended to be consumed by higher-level quadtree/graphic layers.

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

See also: [Modules index](index.md) — every module in this run.
