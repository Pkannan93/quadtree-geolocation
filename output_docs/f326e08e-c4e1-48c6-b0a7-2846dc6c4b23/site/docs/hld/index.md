# canvas-repo-__67eu4o — High-Level Design

The quadtree-graphic application solves a classic problem: quickly finding nearby points on the surface of the Earth. Given a collection of geographic coordinates—cities, landmarks, or sensor locations—the system organizes them into a quadtree, a spatial data structure that recursively divides the map into four quadrants, enabling fast proximity searches without scanning every point. A user clicks anywhere on a displayed world map, and the application returns the nearest neighbors within a chosen radius in milliseconds, even when thousands of locations are indexed.

The codebase is organized in three layers. At the core, classes like `QuadTree` and `QuadTreeNode` implement the spatial indexing logic: inserting latitude/longitude pairs, traversing the tree, and converting between kilometers and angular degrees. Above that, a drawable adapter layer wraps each tree node so it knows how to paint its bounding box and connections to neighboring nodes. The top layer is a Swing UI shell—`Main`, `CanvasPanel`, and `MainScreen`—that loads the world map background, populates the quadtree with sample data, and listens for mouse clicks to trigger live neighbor lookups. Performance metrics appear on screen so you can see how subdivision depth affects query time.

The entire application lives in a single Gradle module under `quadtree-graphic`. There are no external APIs, no microservices, and no database; everything runs in-process on the desktop. The build is managed by Gradle wrapper scripts in the repository root, so a fresh checkout builds cleanly with `./gradlew run`.

Below you will find deeper pages that document the module structure, the core quadtree algorithms, the rendering strategy, and the Swing event flow. Start with those sections if you need to modify the indexing logic or extend the visualization.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | layered desktop application (core spatial engine, drawable adapter layer, Swing UI shell) built as a single Gradle module |
| Primary domain | Geospatial indexing and proximity search visualization |
| Modules | 6 |
| Parsed files | 21 |
| HTTP routes | 0 |
| Domain entities | 0 |
| Background jobs | 0 |
| Deployment manifests | 0 |
| Bounded contexts | 6 |
| Business capabilities | 6 |

## Dive deeper

- [System context](system-context.md) — what's inside the boundary, what's outside, who talks to it.
- [Components](components.md) — major components, their responsibilities, and the fan-in / fan-out leaders.
- [Architecture](architecture.md) — architectural style, key patterns, layering, and the system diagram.
- [Data flows](data-flows.md) — how requests flow through the system end-to-end for the busiest routes.
- [Integration](integration.md) — external systems this service talks to (DBs, caches, queues, third-party APIs).
- [Deployment](deployment.md) — services, container images, background workers, scaling notes.


---

**Related surfaces.** [Overview](../index.md) · [Codebase Guide](../modules/index.md) · [API Reference](../api/index.md) · [Operations](../operations/index.md)
