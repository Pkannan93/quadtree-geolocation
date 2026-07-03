# Geospatial indexing and visualization via quadtrees Documentation — Doc coverage (per-symbol)

Every public, documentable symbol in non-test files, with a 'Has docstring?' verdict. Languages whose docstrings live **before** the declaration (JSDoc, Javadoc, Rustdoc, Go doc) aren't detectable from the chunk text alone — the parser hands us the declaration without the preceding comment block. Those rows are reported as **undetected**, never as undocumented, so the page never lies about coverage.

| Signal | Value |
|---|---|
| Public documentable symbols | 76 |
| Detection-supported (Python today) | 0 |
| Documented | 0 |
| Undocumented | 0 |
| Undetected (language-limited) | 76 |
| Coverage ratio (over detected) | — |

## Undetected by language

These languages need a doc-detector plugin before we can score their symbols. Until then their symbols don't drag the coverage ratio down — they sit in the 'undetected' bucket.

| Language | Undetected symbols |
|---|---|
| `java` | 76 |

_No symbols in detection-supported languages. Add Python files to populate the per-module table below._