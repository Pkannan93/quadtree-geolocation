# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module delivers a self-contained spatial index for geographic entities, exposing a public surface of twelve symbols anchored by the `QuadTree` facade, the `Neighbour` interface, and its concrete `NeighbourImpl`. With zero fan-in and zero fan-out, this is a leaf module in the strictest sense: no collaborators consume it within the scanned codebase, and it depends on no other application modules. That isolation signals either an early-stage implementation awaiting integration or a library component intended for reuse but not yet wired into any visualization or application layer.

The public surface centers on insertion (`addNeighbour`) and proximity search (`findNeighbours`, `findNeighboursIds`), with `QuadTreeNode` managing recursive spatial partitioning and `QuadTreeConstants` supplying unit-conversion helpers like `kmToDegree`. The interface-implementation pair (`Neighbour`, `NeighbourImpl`) abstracts the entity contract to getters for `getId`, `getLatitude`, and `getLongitude`, keeping the quadtree logic decoupled from concrete data models. Callers outside this module—once they exist—will depend on `QuadTree` as the entry point and `Neighbour` as the entity protocol, while `QuadTreeNode` remains an internal recursive workhorse.

For a walkthrough of the five files implementing this spatial index—including `QuadTree.java`, `QuadTreeNode.java`, and the constants utility—consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src/quadtree/core`.

_Domain hint: `Geospatial indexing / spatial data structures`_

## Responsibility

Provides the core quadtree spatial index implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` entity contract and its `NeighbourImpl` implementation, the recursive `QuadTreeNode` for spatial partitioning, the top-level `QuadTree` facade exposing insertion and proximity search, and `QuadTreeConstants` utilities for unit conversions (e.g., kilometers to degrees). This module is self-contained (isolated in the dependency graph) and serves as the underlying spatial data structure to be consumed by higher-level graphic/visualization layers.

## At a glance

| Dimension | Value |
|---|---|
| Files | 5 |
| Public surface | 12 symbol(s) |
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

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
