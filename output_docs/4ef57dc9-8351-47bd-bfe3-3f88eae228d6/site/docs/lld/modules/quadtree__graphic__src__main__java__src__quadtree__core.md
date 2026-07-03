# Module — `quadtree-graphic/src/main/java/src/quadtree/core` (LLD)

The `quadtree-graphic/src/main/java/src/quadtree/core` module provides the foundational spatial indexing implementation for geographic entity storage and proximity queries. Its public surface centers on the `QuadTree` facade—offering `addNeighbour`, `findNeighbours`, and `findNeighboursIds` operations—together with the `Neighbour` interface (and its concrete `NeighbourImpl`) for latitude-longitude entities, plus the recursive `QuadTreeNode` subdivision logic and `QuadTreeConstants` for kilometer-to-degree conversions. With zero fan-in and zero fan-out, this module is a leaf in the dependency graph, making it a reusable component that other layers can consume without coupling concerns.

The isolation is complete: no collaborators appear in the substrate, and no dependent modules yet import the public surface. This pattern is typical of a utility or library module designed to be integrated after initial development; however, readers should verify whether the consuming integration layer exists elsewhere in the codebase or remains unimplemented. The self-contained design allows the quadtree logic to evolve independently, though the lack of dependents at this snapshot suggests the application's higher layers either use an alternative indexing strategy or have not yet landed.

For the full file-level breakdown—including `Neighbour.java`, `QuadTreeNode.java`, and the coordinate-conversion constants—consult the **Codebase Guide** entry for `quadtree-graphic/src/main/java/src/quadtree/core`, which enumerates all five files and their individual purposes within the spatial index.

_Domain hint: `Geospatial indexing / proximity search`_

## Responsibility

Provides the core QuadTree spatial indexing implementation for storing and querying geographic entities by latitude/longitude. Defines the `Neighbour` abstraction (interface plus `NeighbourImpl`) representing points with an ID and coordinates, and exposes a `QuadTree` facade backed by recursive `QuadTreeNode` subdivision to support insertion and radius-based neighbor lookups (in kilometers, converted via `QuadTreeConstants`). This module is self-contained (isolated in the dependency graph) and offers the reusable spatial data structure that other layers of the quadtree-graphic application would build upon.

## At a glance

| Dimension | Value |
|---|---|
| Files | 5 |
| Public surface | 8 symbol(s) |
| Collaborators | 0 |
| Fan-in | 0 module(s) |
| Fan-out | 0 module(s) |

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

**Related surfaces.** [Codebase Guide entry](../../modules/quadtree__graphic__src__main__java__src__quadtree__core.md) · [LLD overview](../index.md) · [HLD Components](../../hld/components.md)
