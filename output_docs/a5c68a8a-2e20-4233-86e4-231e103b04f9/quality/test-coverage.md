# Geospatial indexing and visualization (quadtree-based geographic neighbour search) Documentation — Test coverage (per-symbol)

Every public, documentable symbol declared in **non-test** files, grouped by module. The 'Referenced by tests?' column is a token-grep of the symbol's short name across every test file's chunk text — honest on the over-count side (a comment that mentions the symbol name will count as a reference; we'd rather over-count than miss real coverage).

| Signal | Value |
|---|---|
| Public documentable symbols (non-test files) | 76 |
| Referenced by at least one test file | 0 |
| Untested | 76 |
| Test files scanned | 0 |
| Coverage ratio | 0% (0/76) |

## Symbols by module

Untested symbols within each module render first (audit priority). Tested rows follow.

### `quadtree-graphic/src/main/java/src`

_39 symbol(s); 0 referenced (0% (0/39))._

| Symbol | Kind | Referenced? | Source |
|---|---|---|---|
| `BaseObject` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/BaseObject.java:23` |
| `CanvasPanel` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:30` |
| `Drawable` | `interface` | ❌ no | `quadtree-graphic/src/main/java/src/Drawable.java:23` |
| `Main` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/Main.java:6` |
| `MainScreen` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/MainScreen.java:35` |
| `Screen` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/Screen.java:25` |
| `addDrawable` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Screen.java:47` |
| `draw` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Drawable.java:25` |
| `draw` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/MainScreen.java:92` |
| `draw` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Screen.java:33` |
| `getHeight` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/BaseObject.java:49` |
| `getWidth` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/BaseObject.java:45` |
| `getX` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/BaseObject.java:37` |
| `getY` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/BaseObject.java:41` |
| `handleKeyEvent` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:138` |
| `keyPressed` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:126` |
| `keyReleased` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:131` |
| `keyTyped` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:121` |
| `main` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Main.java:24` |
| `mouseClicked` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:78` |
| `mouseDragged` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:104` |
| `mouseEntered` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:92` |
| `mouseExited` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:97` |
| `mouseMoved` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:112` |
| `mousePressed` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:82` |
| `mouseReleased` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:87` |
| `onMouseClick` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/MainScreen.java:154` |
| `onMouseClick` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Screen.java:59` |
| `onMouseMoved` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/MainScreen.java:132` |
| `onMouseMoved` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Screen.java:55` |
| `removeDrawable` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Screen.java:51` |
| `run` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:166` |
| `setupInput` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:76` |
| `start` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:43` |
| `start` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Main.java:11` |
| `stop` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/CanvasPanel.java:72` |
| `update` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Drawable.java:34` |
| `update` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/MainScreen.java:126` |
| `update` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/Screen.java:40` |

### `quadtree-graphic/src/main/java/src/quadtree`

_7 symbol(s); 0 referenced (0% (0/7))._

| Symbol | Kind | Referenced? | Source |
|---|---|---|---|
| `DrawableQuadTree` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java:26` |
| `DrawableQuadTreeNode` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java:28` |
| `draw` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java:38` |
| `draw` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java:54` |
| `locateAndCreateNodeForPoint` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java:91` |
| `update` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java:43` |
| `update` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java:86` |

### `quadtree-graphic/src/main/java/src/quadtree/core`

_30 symbol(s); 0 referenced (0% (0/30))._

| Symbol | Kind | Referenced? | Source |
|---|---|---|---|
| `Neighbour` | `interface` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java:22` |
| `NeighbourImpl` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java:22` |
| `QuadTree` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:41` |
| `QuadTreeConstants` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java:22` |
| `QuadTreeNode` | `class` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:27` |
| `addNeighbors` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:228` |
| `addNeighbour` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:58` |
| `addNeighbour` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:101` |
| `findAll` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:243` |
| `findNeighbours` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:68` |
| `findNeighboursIds` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:76` |
| `findNeighboursWithinRectangle` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:153` |
| `getHeight` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:287` |
| `getId` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java:24` |
| `getId` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java:34` |
| `getLatitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java:26` |
| `getLatitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java:39` |
| `getLatitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:279` |
| `getLongitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java:28` |
| `getLongitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java:44` |
| `getLongitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:275` |
| `getRangeAsRectangle` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:98` |
| `getRootNode` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:86` |
| `getWidth` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:283` |
| `kmToDegree` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java:30` |
| `locateAndCreateNodeForPoint` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:258` |
| `normalizeLatitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:90` |
| `normalizeLongitude` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:94` |
| `removeNeighbour` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java:64` |
| `removeNeighbour` | `method` | ❌ no | `quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java:117` |
