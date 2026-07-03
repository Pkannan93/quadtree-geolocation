# Static Code Analysis

Generated at: 2026-05-11T10:16:38.818Z

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

- **Business Purpose:** Defines the interface for objects that can be drawn on the canvas.

### Item 4

- **Module:** Main.java

- **Business Purpose:** Entry point that initializes and launches the application.

### Item 5

- **Module:** MainScreen.java

- **Business Purpose:** Constructs the primary user interface screen and manages its layout.

### Item 6

- **Module:** Screen.java

- **Business Purpose:** Defines the base interface or contract for screen components.

### Item 7

- **Module:** DrawableQuadTree.java

- **Business Purpose:** Extends the quad tree data structure with rendering capabilities for visual display.

### Item 8

- **Module:** DrawableQuadTreeNode.java

- **Business Purpose:** Represents a drawable node within the quad tree hierarchy for spatial partitioning visualization.

### Item 9

- **Module:** Neighbour.java

- **Business Purpose:** Defines the interface for accessing neighboring nodes in the quad tree structure.

### Item 10

- **Module:** NeighbourImpl.java

- **Business Purpose:** Implements neighbor-finding logic to locate adjacent nodes in the quad tree.

### Item 11

- **Module:** QuadTree.java

- **Business Purpose:** Implements a quad tree data structure for efficient spatial partitioning and querying.

### Item 12

- **Module:** QuadTreeNode.java

- **Business Purpose:** Represents an individual node in the quad tree with spatial bounds and child references.

- **Llm Architecture Summary:** This application visualizes a quad tree data structure through a graphical interface, using spatial partitioning to organize and display drawable objects efficiently. The architecture separates concerns between the core quad tree logic (data structure and neighbor queries) and the presentation layer (canvas rendering and UI screens).

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

- **Relationship:** owns

### Item 6

- **From:** DrawableQuadTree

- **To:** DrawableQuadTreeNode

- **Relationship:** has-many

### Item 7

- **From:** DrawableQuadTreeNode

- **To:** QuadTreeNode

- **Relationship:** owns

### Item 8

- **From:** QuadTree

- **To:** QuadTreeNode

- **Relationship:** has-many

### Item 9

- **From:** QuadTreeNode

- **To:** QuadTreeNode

- **Relationship:** has-many

### Item 10

- **From:** QuadTree

- **To:** QuadTreeConstants

- **Relationship:** references

### Item 11

- **From:** QuadTreeNode

- **To:** NeighbourImpl

- **Relationship:** references

### Item 12

- **From:** BaseObject

- **To:** QuadTreeNode

- **Relationship:** belongs-to

## Llm Code Quality Insights

### Item 1

- **Area:** Layer Architecture

- **Observation:** No clear separation between presentation, business logic, and data layers. CanvasPanel, DrawableQuadTree, and Main appear to mix UI rendering with spatial data structure logic, violating single responsibility principle.

- **Severity:** high

### Item 2

- **Area:** Domain Model

- **Observation:** Domain entities (BaseObject, QuadTreeNode, QuadTreeConstants) lack explicit business semantics. QuadTree implementation details are exposed throughout the codebase rather than encapsulated behind a domain-focused interface.

- **Severity:** high

### Item 3

- **Area:** Service Layer Absence

- **Observation:** No identifiable service layer for business operations. Spatial queries, object management, and canvas operations appear to be scattered across multiple classes without coordinating facades or service abstractions.

- **Severity:** high

### Item 4

- **Area:** Navigation/Routing Structure

- **Observation:** Main and MainScreen classes suggest UI navigation exists but no routing pattern is evident. Screen transitions and state management lack explicit architectural definition, creating implicit dependencies.

- **Severity:** medium

### Item 5

- **Area:** Drawable vs Data Separation

- **Observation:** DrawableQuadTree and DrawableQuadTreeNode duplicate QuadTree/QuadTreeNode logic with rendering concerns. This violates DRY principle and creates maintenance burden when spatial logic changes.

- **Severity:** medium

## Decorator Patterns

_No entries found._
