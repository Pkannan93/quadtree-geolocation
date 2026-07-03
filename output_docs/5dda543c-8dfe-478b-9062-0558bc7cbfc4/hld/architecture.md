# canvas-repo-hnnu2hd_ — Architecture

This codebase adopts a **layered modular monolith** composed of a core spatial library, a visualization adapter, and a Swing UI shell, with build scaffolding isolated in separate modules. The substrate reports six modules with zero dependencies captured between them—likely because the six units represent horizontally partitioned slices (distinct library, adapter, and UI JARs) rather than vertically composed layers inside a single deployment artifact. The absence of cycles and the single-layer classification confirm that no cross-cutting fan-in or layering violations exist at the module boundary; each top-level unit respects its architectural role.

The pattern is characteristic of **capability-oriented decomposition**: spatial computation lives in one module, rendering concerns in another, user interaction in a third. This structure affords independent versioning and testability but trades off the in-process composition root that would surface in a more tightly coupled monolith. The zero edge count implies either that inter-module wiring happens via reflection, service-loader manifests, or runtime plugin discovery, or that dependency edges were filtered from the analysis scope.

Concrete module names, layer assignments, and dependency edges—if present—appear in the **Reference → Codebase Guide** and **Configuration** pages below. If runtime wiring uses `ServiceLoader` or OSGi-style registries, those manifests will clarify the invariant that static analysis cannot infer.

**Architecture style.** layered modular monolith (core spatial library + visualization adapter + Swing UI shell, with separate build scaffolding)

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
