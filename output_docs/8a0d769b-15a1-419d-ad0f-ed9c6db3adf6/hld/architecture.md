# canvas-repo-3p2clcww — Architecture

This architecture embodies a strict layered modular monolith within a single Gradle project, expressed as three distinct tiers: a domain core library, a drawable adapter layer, and a Swing GUI shell that composes them. The substrate reveals zero cyclic dependencies across six modules—a clean acyclic graph that enforces unidirectional coupling from UI down through adapters into core logic. The absence of top dependency targets and the single-layer classification suggest either minimal inter-module wiring or that composition happens late at the application boundary, likely within the Swing shell module serving as the composition root.

The zero-cycle invariant is the design's most significant constraint: no module may depend on a peer or ancestor, preventing the layering violations common in GUI-heavy Java applications where presentation concerns leak into domain model classes. One module count and one layer count imply either a flat namespace with informal boundaries or that the build tooling doesn't surface finer-grained submodule structure; architects onboarding should verify whether package conventions enforce the core/adapter/shell separation when module boundaries do not.

Concrete module names, dependency fan-out metrics, and package-level layering rules appear in the **Reference > Codebase Guide**, while the Gradle configuration surfacing build-time enforcement of acyclicity lives under **Configuration > Build System**.

**Architecture style.** layered modular Java application (core library + drawable adapter + Swing GUI shell) packaged as a single Gradle project

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
