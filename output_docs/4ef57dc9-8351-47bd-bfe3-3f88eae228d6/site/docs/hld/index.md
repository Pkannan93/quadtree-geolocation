# code-analyser-repo-a6roce0k — High-Level Design

This system helps answer "which points are near me?" questions for geographic data scattered across the world. It builds a quadtree—a tree structure that recursively divides a map into four smaller rectangles—so you can quickly find all locations within a given radius of any latitude and longitude, without checking every point one by one.

The implementation separates concerns into three layers. At the bottom, `quadtree-core` holds the pure data-structure logic: `QuadTree` and `QuadTreeNode` classes that insert points and run radius-based neighbor lookups measured in kilometers. Above that, a rendering adapter in `quadtree` wraps each core class with a `Drawable` counterpart so the tree can paint itself. At the top, a Swing desktop shell in `src` (`Main`, `CanvasPanel`, `MainScreen`) opens a window with a world-map backdrop, scatters random points across it, and lets you click anywhere to highlight neighbors within your chosen radius. Zoom and pan controls make it easy to explore dense clusters or sparse regions.

The repository uses Gradle with a reproducible wrapper and JUnit 5 for tests. Everything lives under `quadtree-graphic`, with build configuration in the root and the wrapper binaries in `gradle/wrapper`.

The pages below dive deeper: one explains the core quadtree indexing algorithms and neighbor-search mechanics, another covers the drawable adapters and how the tree renders itself, and a third walks through the Swing UI event handling and canvas painting. Together they show how raw spatial indexing turns into an interactive map tool.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | layered desktop application (spatial-core → drawable adapter → Swing UI shell) with separate Gradle build-tooling roots |
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
