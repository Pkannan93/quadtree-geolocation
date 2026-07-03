# Geospatial indexing and proximity search visualization Documentation — Dead-code candidates

Exported symbols (functions, methods, classes, interfaces) with **zero internal callers** *and* **zero references from any test file**. Conservative: we only flag symbols where both signals agree; a single test reference or single intra-module call removes the candidate.

Test files are detected by path pattern: anything under `tests/` or `test/`, anything ending in `_test.py`, `.test.{js,jsx,ts,tsx}`, or `Test.{js,jsx,ts,tsx}`, plus files starting with `test_`.

False positives are common for: framework entry points (FastAPI / Flask handlers — they're called by the framework, not by user code), ORM models (SQLAlchemy `declarative_base` registers them implicitly), and anything imported via reflection. Skim before deleting.

3 candidate(s) across 2 module(s).

## `quadtree-graphic/src/main/java/src`

| Kind | Symbol | Source |
|---|---|---|
| `interface` | `Drawable` | `quadtree-graphic/src/main/java/src/Drawable.java:23` |

## `quadtree-graphic/src/main/java/src/quadtree/core`

| Kind | Symbol | Source |
|---|---|---|
| `interface` | `Neighbour` | `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java:22` |
| `class` | `QuadTreeConstants` | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java:22` |
