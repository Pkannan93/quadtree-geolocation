# Static Code Analysis

Generated at: 2026-05-11T09:55:01.493Z

## Symbol Graph

_No entries found._

## Dependency Graph

### Item 1

- **File:** quadtree-graphic/src/main/java/src/BaseObject.java

#### Imports

- java.awt.

### Item 2

- **File:** quadtree-graphic/src/main/java/src/CanvasPanel.java

#### Imports

- java.awt.
- java.awt.event.
- java.awt.image.BufferStrategy
- static

### Item 3

- **File:** quadtree-graphic/src/main/java/src/Drawable.java

#### Imports

- java.awt.

### Item 4

- **File:** quadtree-graphic/src/main/java/src/Main.java

#### Imports

- javax.swing.
- java.awt.

### Item 5

- **File:** quadtree-graphic/src/main/java/src/MainScreen.java

#### Imports

- src.quadtree.DrawableQuadTree
- src.quadtree.core.Neighbour
- javax.imageio.ImageIO
- java.awt.
- java.awt.image.BufferedImage
- java.io.IOException
- java.util.HashSet
- java.util.Random
- java.util.Set
- static

### Item 6

- **File:** quadtree-graphic/src/main/java/src/Screen.java

#### Imports

- java.awt.
- java.util.ArrayList
- java.util.List

### Item 7

- **File:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java

#### Imports

- src.Drawable
- src.quadtree.core.QuadTree
- java.awt.

### Item 8

- **File:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java

#### Imports

- src.Drawable
- src.quadtree.core.Neighbour
- src.quadtree.core.QuadTreeNode
- java.awt.
- java.awt.geom.Rectangle2D

### Item 9

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java

#### Imports

_No entries found._

### Item 10

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java

#### Imports

_No entries found._

### Item 11

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java

#### Imports

- java.awt.geom.Rectangle2D
- java.util.HashSet
- java.util.Set

### Item 12

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java

#### Imports

_No entries found._

### Item 13

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java

#### Imports

- java.awt.geom.Rectangle2D
- java.util.ArrayList
- java.util.List
- java.util.Set

## Api Catalog

_No entries found._

## Entity Candidates

- BaseObject
- CanvasPanel
- DrawableQuadTree
- DrawableQuadTreeNode
- Main
- MainScreen
- NeighbourImpl
- QuadTree
- QuadTreeConstants
- QuadTreeNode
- Screen

## Sql Usage

### Item 1

- **File:** quadtree-graphic/src/main/java/src/CanvasPanel.java

- **Snippet:** mMainScreen.update(difftime, difftime / 1000.f);

### Item 2

- **File:** quadtree-graphic/src/main/java/src/Drawable.java

- **Snippet:** * Update is called each time a frame is about to be rendered.

### Item 3

- **File:** quadtree-graphic/src/main/java/src/Drawable.java

- **Snippet:** * @param difftime the difference in milliseconds from the last update

### Item 4

- **File:** quadtree-graphic/src/main/java/src/Drawable.java

- **Snippet:** abstract void update(long difftime, float difftimeInSeconds);

### Item 5

- **File:** quadtree-graphic/src/main/java/src/MainScreen.java

- **Snippet:** public void update(long difftime, float difftimeInSeconds) {

### Item 6

- **File:** quadtree-graphic/src/main/java/src/MainScreen.java

- **Snippet:** super.update(difftime, difftimeInSeconds);

### Item 7

- **File:** quadtree-graphic/src/main/java/src/MainScreen.java

- **Snippet:** mQuadTree.update(difftime, difftimeInSeconds);

### Item 8

- **File:** quadtree-graphic/src/main/java/src/Screen.java

- **Snippet:** public void update(long difftime, float difftimeInSeconds) {

### Item 9

- **File:** quadtree-graphic/src/main/java/src/Screen.java

- **Snippet:** drawable.update(difftime, difftimeInSeconds);

### Item 10

- **File:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java

- **Snippet:** public void update(long difftime, float difftimeInSeconds) {

### Item 11

- **File:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java

- **Snippet:** ((DrawableQuadTreeNode) getRootNode()).update(difftime, difftimeInSeconds);

### Item 12

- **File:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java

- **Snippet:** public void update(long difftime, float difftimeInSeconds) {

### Item 13

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java

- **Snippet:** * Removes a neighbour from the quadtree

## Event Producers Consumers

_No entries found._

## Architecture Layers

_No entries found._

## Key Modules

### Item 1

- **Module:** quadtree-graphic/src/main/java/src/BaseObject.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 2

- **Module:** quadtree-graphic/src/main/java/src/CanvasPanel.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 3

- **Module:** quadtree-graphic/src/main/java/src/Drawable.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 4

- **Module:** quadtree-graphic/src/main/java/src/Main.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 5

- **Module:** quadtree-graphic/src/main/java/src/MainScreen.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 6

- **Module:** quadtree-graphic/src/main/java/src/Screen.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 7

- **Module:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 8

- **Module:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 9

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 10

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 11

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 12

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 13

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java

- **Role:** other

- **Importance Score:** -3

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

## Dependency Hotspots

_No entries found._

## Architectural Patterns

### Item 1

- **Pattern:** feature-based structure

- **Detected:** No

#### Evidence

_No entries found._

- **Confidence:** low

### Item 2

- **Pattern:** service layer pattern

- **Detected:** No

#### Evidence

_No entries found._

- **Confidence:** low

### Item 3

- **Pattern:** guard/interceptor usage

- **Detected:** No

#### Evidence

_No entries found._

- **Confidence:** low

### Item 4

- **Pattern:** API abstraction layer

- **Detected:** No

#### Evidence

_No entries found._

- **Confidence:** low

### Item 5

- **Pattern:** mock-data pattern

- **Detected:** No

#### Evidence

_No entries found._

- **Confidence:** low

### Item 6

- **Pattern:** shared component reuse

- **Detected:** No

#### Evidence

_No entries found._

- **Confidence:** low

### Item 7

- **Pattern:** routing-driven navigation

- **Detected:** No

#### Evidence

_No entries found._

- **Confidence:** low

## Mock Vs Api Assessment

- **Classification:** unknown

### Mock Data Signals

_No entries found._

### Real Api Signals

_No entries found._

- **Notes:** No endpoint catalog confidently inferred from frontend-only evidence

## Code Quality Observations

_No entries found._

## Missing Or Weak Areas

### Item 1

- **Issue:** Service layer pattern not clearly detected

- **Why It Matters:** Without service orchestration boundaries, business logic may be scattered and harder to govern.

- **Confidence:** medium

- **Suggested Next Refinement:** Improve role inference for domain-specific orchestrator files and facades.

### Item 2

- **Issue:** Routing/navigation structure not clearly detected

- **Why It Matters:** Navigation control points are critical for feature boundaries and UX flow analysis.

- **Confidence:** medium

- **Suggested Next Refinement:** Expand routing detection to framework-specific route registration styles.

### Item 3

- **Issue:** Domain model layer is weak or not explicit

- **Why It Matters:** Weak domain representation reduces confidence in business-architecture mapping.

- **Confidence:** medium

- **Suggested Next Refinement:** Expand model detection to include view-model/state interfaces and schema objects.

## Confidence Notes

- **Overall:** medium

### Evidence Coverage

- **Files Analyzed:** 13

- **Key Modules:** 13

- **Hotspots:** 0

- **Api Signals:** 0

### Caveats

- API inference depends on explicit HTTP usage patterns in code
- Backend-focused evidence detected; presentation-layer insights may be limited

## Service Http Summary

_No entries found._

## Notable Snippets

_No entries found._

## Llm Module Annotations

### Item 1

- **Module:** BaseObject.java

- **Business Purpose:** Provides a base class for drawable objects with common properties and behavior.

### Item 2

- **Module:** CanvasPanel.java

- **Business Purpose:** Renders drawable objects onto a graphical canvas for visual display.

### Item 3

- **Module:** Drawable.java

- **Business Purpose:** Defines the interface for objects that can be rendered on the canvas.

### Item 4

- **Module:** Main.java

- **Business Purpose:** Entry point that initializes and launches the application.

### Item 5

- **Module:** MainScreen.java

- **Business Purpose:** Constructs and manages the primary user interface window and its components.

### Item 6

- **Module:** Screen.java

- **Business Purpose:** Defines the contract for screen implementations that display content.

### Item 7

- **Module:** DrawableQuadTree.java

- **Business Purpose:** Extends the quad tree data structure with rendering capabilities for visual display.

### Item 8

- **Module:** DrawableQuadTreeNode.java

- **Business Purpose:** Represents a renderable node within a quad tree structure.

### Item 9

- **Module:** Neighbour.java

- **Business Purpose:** Defines the interface for accessing neighboring nodes in a quad tree.

### Item 10

- **Module:** NeighbourImpl.java

- **Business Purpose:** Implements neighbor lookup logic to find adjacent nodes in a quad tree.

### Item 11

- **Module:** QuadTree.java

- **Business Purpose:** Implements a quad tree data structure for efficient spatial partitioning and queries.

### Item 12

- **Module:** QuadTreeNode.java

- **Business Purpose:** Represents a single node in the quad tree hierarchy with spatial bounds and child references.

- **Llm Architecture Summary:** This application is a graphical visualization tool built around a quad tree spatial data structure, which efficiently organizes and queries objects in 2D space. The system layers a rendering framework (canvas, screens, drawable objects) on top of the core quad tree implementation to display and interact with spatially-partitioned data.

## Llm Entity Relationships

### Item 1

- **From:** Main

- **To:** MainScreen

- **Relationship:** owns

### Item 2

- **From:** MainScreen

- **To:** Screen

- **Relationship:** belongs-to

### Item 3

- **From:** MainScreen

- **To:** CanvasPanel

- **Relationship:** owns

### Item 4

- **From:** CanvasPanel

- **To:** DrawableQuadTree

- **Relationship:** references

### Item 5

- **From:** DrawableQuadTree

- **To:** QuadTree

- **Relationship:** belongs-to

### Item 6

- **From:** DrawableQuadTree

- **To:** DrawableQuadTreeNode

- **Relationship:** has-many

### Item 7

- **From:** DrawableQuadTreeNode

- **To:** QuadTreeNode

- **Relationship:** belongs-to

### Item 8

- **From:** DrawableQuadTreeNode

- **To:** DrawableQuadTreeNode

- **Relationship:** has-many

### Item 9

- **From:** DrawableQuadTreeNode

- **To:** BaseObject

- **Relationship:** has-many

### Item 10

- **From:** QuadTreeNode

- **To:** QuadTreeNode

- **Relationship:** has-many

### Item 11

- **From:** QuadTreeNode

- **To:** NeighbourImpl

- **Relationship:** references

### Item 12

- **From:** QuadTree

- **To:** QuadTreeNode

- **Relationship:** owns

### Item 13

- **From:** QuadTree

- **To:** QuadTreeConstants

- **Relationship:** references

### Item 14

- **From:** DrawableQuadTree

- **To:** QuadTreeConstants

- **Relationship:** references

## Llm Code Quality Insights

### Item 1

- **Area:** Layer Architecture

- **Observation:** No clear separation between presentation, business logic, and data layers. CanvasPanel, DrawableQuadTree, and Main appear to mix UI rendering with spatial data structure logic, indicating tight coupling between concerns.

- **Severity:** high

### Item 2

- **Area:** Domain Model

- **Observation:** Domain entities (BaseObject, QuadTreeNode, QuadTreeConstants) lack explicit business logic encapsulation. The QuadTree implementation appears to be a generic data structure without domain-specific abstractions, making it difficult to evolve business rules independently.

- **Severity:** high

### Item 3

- **Area:** Service Layer Absence

- **Observation:** No identifiable service layer for orchestrating business operations. Direct coupling between UI components (MainScreen, CanvasPanel) and data structures (DrawableQuadTree, QuadTree) suggests business logic is scattered or embedded in presentation/data layers.

- **Severity:** high

### Item 4

- **Area:** Navigation and Routing

- **Observation:** Main and MainScreen classes suggest a simple entry point with no explicit navigation framework or routing pattern. This creates brittleness when adding new screens or complex user flows, limiting scalability.

- **Severity:** medium

### Item 5

- **Area:** Drawable vs Domain Separation

- **Observation:** DrawableQuadTree and DrawableQuadTreeNode appear to conflate rendering concerns with spatial indexing logic. This violates single responsibility principle and makes it difficult to reuse the QuadTree in non-visual contexts or swap rendering implementations.

- **Severity:** medium

## Decorator Patterns

_No entries found._
