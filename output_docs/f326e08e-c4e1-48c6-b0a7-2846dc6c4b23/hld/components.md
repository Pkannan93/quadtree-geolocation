# canvas-repo-__67eu4o — Components

The system comprises six modules organized in a single architectural layer with no inter-module dependencies, resulting in zero cyclic coupling and zero edges in the dependency graph. This flat topology indicates that each module operates as an independent unit—no composition root aggregates them, and no fan-in or fan-out leaders emerge because the modules do not reference one another at all. The absence of coupling reflects either a microservices boundary where orchestration lives outside the codebase, a collection of independent command-line tools sharing a repository, or a project in its earliest scaffolding phase where integration points have not yet materialized.

The architectural trade-off is clarity versus integration cost: zero dependencies eliminate cycle risk and simplify reasoning about each module in isolation, but the lack of shared abstractions or a unifying entry point suggests that cross-cutting concerns—logging, configuration injection, shared domain logic—are either duplicated in each module or externalized to runtime infrastructure. Without fan-out data, we cannot identify where instantiation or dependency resolution occurs, so the system's composition strategy remains opaque from static analysis alone.

Concrete module names, their internal structure, and any runtime wiring mechanisms appear in the **Reference > Codebase Guide**, while deployment and orchestration context that may bind these modules at runtime is documented under **Operations**.

## Most depended-on components

_Module dependency graph not available — falling back to a flat module list under Codebase Guide._


---

**Related surfaces.** [Codebase Guide (per-module pages)](../guide/index.md) · [Architecture](architecture.md)
