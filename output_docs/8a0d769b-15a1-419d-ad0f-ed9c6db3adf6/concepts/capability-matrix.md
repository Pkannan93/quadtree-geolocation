# Geospatial indexing and proximity search with interactive visualization Documentation — Capability matrix

One row per capability, with its bounded context, the modules that implement it, and the routes it exposes (when an HTTP surface is involved). Routes deep-link into the per-route reference page so readers can pivot from the domain view to the technical contract.

## `build tooling / gradle wrapper configuration`

| Capability | Modules | Routes |
|---|---|---|
| **wrapper** | `quadtree-graphic/gradle/wrapper` | — |


## `build tooling / quadtree graphics application`

| Capability | Modules | Routes |
|---|---|---|
| **quadtree-graphic** | `quadtree-graphic` | — |


## `geospatial indexing / proximity search`

| Capability | Modules | Routes |
|---|---|---|
| **Provides a self-contained quadtree spatial indexing core for geographic data** | `quadtree-graphic/src/main/java/src/quadtree/core` | — |


## `geospatial indexing / quadtree spatial data structures`

| Capability | Modules | Routes |
|---|---|---|
| **.** | `.` | — |


## `interactive geospatial quadtree visualization (swing gui)`

| Capability | Modules | Routes |
|---|---|---|
| **src** | `quadtree-graphic/src/main/java/src` | — |


## `spatial data structure visualization (quadtree rendering)`

| Capability | Modules | Routes |
|---|---|---|
| **quadtree** | `quadtree-graphic/src/main/java/src/quadtree` | — |

