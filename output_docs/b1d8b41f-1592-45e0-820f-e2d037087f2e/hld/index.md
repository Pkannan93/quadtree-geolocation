# canvas-repo-ywrcy9mc — High-Level Design

This repository houses a Java application that solves geographic proximity search—finding all points within a given radius of a target location—using a quadtree spatial index. The core library lives in `quadtree-graphic/src/main/java/src/quadtree/core`, where classes like `QuadTree` and `QuadTreeNode` recursively subdivide the world map into smaller regions and answer "show me all neighbors within X kilometers" queries in logarithmic time. A Swing GUI (`Main`, `CanvasPanel`, `MainScreen`) wraps this library in an interactive visualizer: you can pan and zoom a world map, click to insert points, and see the quadtree's bounding boxes drawn over a geographic backdrop.

The repository's structure is unusual. Alongside the dozen or so Java source files and Gradle build scripts, you will find 35 sibling directories under `output_docs/`, each named with a UUID. Every directory is a self-contained snapshot from an automated documentation pipeline that ingested this quadtree project, ran static analysis, inferred runtime behavior, extracted business semantics, generated diagrams, and produced a critic report. The pipeline has run dozens of times against the same subject code, so the repository doubles as an archive of those analysis artifacts—stage-by-stage Markdown reports numbered `00-run-summary` through `07-critic` or `08-critic`.

In practice, the 40 top-level modules form a flat layer with no import edges between them: the quadtree application is one isolated island, the Gradle wrapper is another, and each `output_docs/<uuid>` folder is its own island of generated documentation. The application itself is built with Gradle 4.0 (wrapper scripts in `quadtree-graphic/gradle/wrapper`) and depends only on the Java standard library and Swing.

The pages that follow drill into module groups, the application's class hierarchy, and the documentation-pipeline artifact schema. If you want to understand the quadtree algorithm or modify the visualizer, start with the Modules page; if you are exploring the pipeline's output format, begin with the generated-documentation sections.

## System at a glance

| Dimension | Value |
|---|---|
| Architecture style | library + GUI application coexisting with a flat archive of generated documentation runs (no internal import edges; graph is a single layer of 39 isolated modules) |
| Primary domain | Geospatial indexing and proximity search via quadtree, with an interactive Swing visualization |
| Modules | 40 |
| Parsed files | 307 |
| HTTP routes | 0 |
| Domain entities | 0 |
| Background jobs | 0 |
| Deployment manifests | 0 |
| Bounded contexts | 40 |
| Business capabilities | 40 |

## Dive deeper

- [System context](system-context.md) — what's inside the boundary, what's outside, who talks to it.
- [Components](components.md) — major components, their responsibilities, and the fan-in / fan-out leaders.
- [Architecture](architecture.md) — architectural style, key patterns, layering, and the system diagram.
- [Data flows](data-flows.md) — how requests flow through the system end-to-end for the busiest routes.
- [Integration](integration.md) — external systems this service talks to (DBs, caches, queues, third-party APIs).
- [Deployment](deployment.md) — services, container images, background workers, scaling notes.


---

**Related surfaces.** [Overview](../overview/index.md) · [Codebase Guide](../guide/index.md) · [API Reference](../reference/index.md) · [Operations](../operations/index.md)
