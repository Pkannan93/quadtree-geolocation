# Geospatial indexing and visualization (quadtree-based geographic neighbour search) Documentation — Capability matrix

One row per capability, with its bounded context, the modules that implement it, and the routes it exposes (when an HTTP surface is involved). Routes deep-link into the per-route reference page so readers can pivot from the domain view to the technical contract.

## `build tooling / gradle wrapper configuration`

| Capability | Modules | Routes |
|---|---|---|
| **wrapper** | `quadtree-graphic/gradle/wrapper` | — |


## `build tooling / project infrastructure (graphical quadtree application)`

| Capability | Modules | Routes |
|---|---|---|
| **Provides the Gradle build infrastructure for the `quadtree-graphic` project** | `quadtree-graphic` | — |


## `geospatial data structures (quadtree-based location indexing)`

| Capability | Modules | Routes |
|---|---|---|
| **.** | `.` | — |


## `geospatial indexing / spatial search (quadtree for geographic neighbour lookup)`

| Capability | Modules | Routes |
|---|---|---|
| **core** | `quadtree-graphic/src/main/java/src/quadtree/core` | — |


## `spatial data visualization (quadtree-based geographic rendering)`

| Capability | Modules | Routes |
|---|---|---|
| **quadtree** | `quadtree-graphic/src/main/java/src/quadtree` | — |


## `spatial indexing visualization / interactive geographic data rendering`

| Capability | Modules | Routes |
|---|---|---|
| **src** | `quadtree-graphic/src/main/java/src` | — |

