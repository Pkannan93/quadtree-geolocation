# code-analyser-repo-7irj4_tm — Architecture

This system implements a classic layered desktop architecture where a Swing UI shell delegates to a drawable adapter, which in turn leverages a core spatial-index library for geometric queries and rendering. The entire stack is packaged as a single Gradle module, avoiding the coordination overhead of a multi-module build while maintaining logical layering through package structure and interface boundaries. With six modules and zero detected cycles, the codebase enforces acyclicity at the component level—each layer depends only on contracts defined below it, preventing the coupling erosion that typically accompanies monolithic growth.

The architecture trades multi-module isolation for build simplicity and rapid iteration: a single compilation unit means no version drift between layers, but also no compile-time firewall against accidental cross-layer references. The spatial-index core remains the invariant anchor—UI and adapter layers must never leak domain assumptions upward, and the drawable adapter exists specifically to translate core geometric primitives into Swing rendering calls without polluting the index algorithms. This boundary is critical: violations would couple pure spatial logic to GUI lifecycle concerns, undermining testability and future adapter swaps.

Concrete module boundaries, package conventions, and the Gradle build definition live in the **Reference > Codebase Guide** section. Runtime configuration—if the spatial index or UI expose tuning parameters—is detailed under **Configuration**.

**Architecture style.** layered desktop application (Swing UI shell over a drawable adapter over a core spatial-index library), packaged as a single Gradle module

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../architecture.md)
