# Geospatial indexing and visualization — quadtree-based proximity search over latitude/longitude points Documentation — Capability matrix

One row per capability, with its bounded context, the modules that implement it, and the routes it exposes (when an HTTP surface is involved). Routes deep-link into the per-route reference page so readers can pivot from the domain view to the technical contract.

## `build tooling / project infrastructure`

| Capability | Modules | Routes |
|---|---|---|
| **wrapper** | `quadtree-graphic/gradle/wrapper` | — |


## `build tooling / project scaffolding for a quadtree-based graphics application`

| Capability | Modules | Routes |
|---|---|---|
| **Provides the Gradle build infrastructure for the `quadtree-graphic` project** | `quadtree-graphic` | — |


## `geospatial data visualization (quadtree-based spatial indexing rendering)`

| Capability | Modules | Routes |
|---|---|---|
| **quadtree** | `quadtree-graphic/src/main/java/src/quadtree` | — |


## `geospatial indexing / proximity search`

| Capability | Modules | Routes |
|---|---|---|
| **core** | `quadtree-graphic/src/main/java/src/quadtree/core` | — |


## `geospatial indexing / quadtree data structures for geolocation queries`

| Capability | Modules | Routes |
|---|---|---|
| **.** | `.` | — |


## `interactive 2d graphics / spatial-index visualization (quadtree neighbor search on a world map)`

| Capability | Modules | Routes |
|---|---|---|
| **src** | `quadtree-graphic/src/main/java/src` | — |

