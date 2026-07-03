# canvas-repo-3p2clcww — High-Level Design

This repository solves the problem of finding nearby geographic locations quickly. Given millions of latitude-longitude points scattered across the planet, a linear scan is too slow; instead, the system uses a quadtree—a tree that recursively divides the world into four quadrants—to index points and answer "which points lie within *x* kilometers of this spot?" in logarithmic time.

The codebase is organized as a single Gradle project with three conceptual layers. At the bottom, `quadtree-graphic/src/main/java/src/quadtree/core` supplies the core data structures: `QuadTree`, `QuadTreeNode`, and proximity-search logic that converts kilometer radii into degree deltas and walks the tree. A middle drawable layer in `quadtree-graphic/src/main/java/src/quadtree` wraps those nodes with rendering metadata—bounding boxes, colors—so each quadrant and point can paint itself onto a canvas. Finally, the application shell in `quadtree-graphic/src/main/java/src` ties everything together in a Swing GUI (`Main`, `CanvasPanel`, `MainScreen`) that displays a world map, lets you pan and zoom with the mouse, and click any location to highlight neighbors within a configurable radius.

The build runs through the Gradle 4.0 wrapper checked into `quadtree-graphic/gradle/wrapper`, giving you a single `./gradlew build` command to compile the Java sources and execute JUnit tests. Because the project is small, all modules live in one flat Gradle subproject rather than a multi-module hierarchy.

The pages that follow break down the core quadtree algorithms, the drawable adapter contracts, the Swing event-handling loop, and the Gradle configuration in detail.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | layered modular Java application (core library + drawable adapter + Swing GUI shell) packaged as a single Gradle project |
| Primary domain | Geospatial indexing and proximity search with interactive visualization |
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
