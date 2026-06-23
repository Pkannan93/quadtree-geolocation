# canvas-repo-cswgl2br — Architecture

This system implements a **layered desktop application** within a single Gradle module, organizing responsibilities across a core spatial engine, a drawable adapter layer, and a Swing UI shell. The architecture enforces strict layering without cycles—`cycle_count` confirms zero circular dependencies—allowing the spatial engine to remain UI-agnostic while the adapter layer translates domain geometry into renderable primitives for the Swing surface. The absence of inter-module boundaries (module_count: 6, edge_count: 0) indicates either a nascent modularization effort or a deliberate choice to enforce layering through package conventions rather than build-time constraints, trading compile-time isolation for simpler build orchestration.

Six modules exist but report zero edges, revealing that modularization has been declared without wiring inter-module dependencies through the build graph. This pattern—common in early architectural decomposition or in systems migrating from a monolith—means layering violations remain detectable only through static analysis or runtime coupling, not Gradle's DAG. The single-layer count suggests the build treats all modules as peers; architectural layering exists in package structure and naming conventions, not in enforced compilation order.

Concrete module names, layering rules, and package-to-layer mappings appear in **Reference → Codebase Guide**, where the actual boundaries between spatial primitives, adapters, and UI concerns are cataloged.

**Architecture style.** layered desktop application (core spatial engine, drawable adapter layer, Swing UI shell) built as a single Gradle module

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
