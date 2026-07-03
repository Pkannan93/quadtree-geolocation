# canvas-repo-sbb61m6j — Architecture

This codebase implements a **layered library with demo application**, where a core data structure layer feeds a drawable adapter, which in turn serves a Swing UI shell—all unified within a single-project Gradle build. The architecture is strictly **acyclic** (zero cycles detected across six modules), enforcing unidirectional dependency flow and enabling deterministic build order and safe refactoring. The single-layer classification suggests the modules share a common abstraction level or that deeper layer boundaries have not been formalized; this trades architectural segmentation for reduced coupling surface and simpler onboarding at the cost of weaker compile-time boundaries between domain logic and presentation concerns.

With zero inter-module edges reported, the current decomposition is either **nascent**—modules exist but cross-references have not yet emerged—or the substrate captured only the root composition and not internal package-level dependencies. In a mature layered library, one would expect the Swing shell to depend on the drawable adapter, which in turn depends on the core data structure; the absence of reported edges means module-level dependency enforcement is either premature or adjacency is encoded within packages rather than Gradle subprojects. The `module_count` of six and single Gradle project structure indicate a **modular monolith by convention** rather than by build-tool isolation.

Concrete module names, package layering rules, and dependency relationships live in the **Reference → Codebase Guide**; Gradle subproject topology (if evolved) will appear in **Operations → Build & Release**.

**Architecture style.** layered library with demo application (core data structure → drawable adapter → Swing UI shell), packaged as a single-project Gradle build

## System diagram

_Architecture Mermaid not available — the diagram-generation agent did not run or had no input to emit. See `overview/architecture-diagram.md` for the text breakdown._

## Layers

_Topological layers, leaves first. Modules in layer 0 depend on nothing internal; deeper layers depend on shallower ones. Cyclic SCCs collapse to a single layer._

- **Layer 0** (5 module(s)): `quadtree-graphic`, `quadtree-graphic/gradle/wrapper`, `quadtree-graphic/src/main/java/src`, `quadtree-graphic/src/main/java/src/quadtree`, `quadtree-graphic/src/main/java/src/quadtree/core`


---

**Related surfaces.** [Components](components.md) · [Overview / architecture-diagram](../overview/architecture-diagram.md)
