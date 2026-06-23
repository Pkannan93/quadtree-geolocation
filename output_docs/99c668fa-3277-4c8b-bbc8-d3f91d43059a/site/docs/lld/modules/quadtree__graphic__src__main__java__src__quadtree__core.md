# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module implements a self-contained spatial indexing library, offering a quadtree data structure for partitioning two-dimensional geographic space and supporting efficient range queries over entities identified by latitude and longitude. Its public surface exposes the `Neighbour` abstraction and `NeighbourImpl` value type, the recursive `QuadTreeNode` that subdivides regions and maintains capacity thresholds, the `QuadTree` facade with methods like `addNeighbour`, `findNeighboursWithinRectangle`, and `getRangeAsRectangle` (which converts kilometer radii to degree-based bounding boxes), and `QuadTreeConstants` holding tuning parameters such as max node capacity and km-to-degree conversion factors. The design treats neighbours as immutable point entities, each carrying an `getId` property, and enforces spatial partitioning rules at the node level to balance insertion cost against query speed.

With zero fan-in and zero fan-out, this module is a leaf in the dependency graph and has no collaborators—no other module depends on it, and it depends on no other module within the codebase. This isolation signals that `core` was intended as a reusable library component, possibly shared across multiple applications or held in reserve for future composition, but currently remains uncoupled from the rest of the system. The absence of downstream consumers means changes to its public surface carry no ripple risk, though it also suggests the module may not yet be integrated into the application's runtime pathways.

For the five files implementing this functionality—`Neighbour.java`, `NeighbourImpl.java`, `QuadTree.java`, `QuadTreeNode.java`, and `QuadTreeConstants.java`—see the Codebase Guide entry for `quadtree-graphic/src/main/java/src/quadtree/core`.

_Domain hint: `Geospatial indexing / spatial data structures`_

## Responsibility

Provides the core quadtree spatial data structure for indexing and querying geographic entities (neighbours) by latitude/longitude. Defines the `Neighbour` abstraction and its `NeighbourImpl` value type, the recursive `QuadTreeNode` that partitions space and supports add/remove/range-search, the top-level `QuadTree` facade that exposes add and range-query operations (including km-based range conversion), and `QuadTreeConstants` holding tuning parameters such as max node capacity and km-to-degree conversion factors. The module is self-contained (isolated in the dependency graph) and serves as a reusable spatial index library.

## At a glance

| Dimension | Value |
|---|---|
| Files | 5 |
| Public surface | 14 symbol(s) |
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

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
