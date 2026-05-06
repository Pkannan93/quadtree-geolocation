# Static Code Analysis

Generated at: 2026-05-06T14:37:41.276Z

## Symbol Graph

_No entries found._

## Dependency Graph

### Item 1

- **File:** quadtree-graphic/src/main/java/src/BaseObject.java

#### Imports

_No entries found._

### Item 2

- **File:** quadtree-graphic/src/main/java/src/CanvasPanel.java

#### Imports

_No entries found._

### Item 3

- **File:** quadtree-graphic/src/main/java/src/Drawable.java

#### Imports

_No entries found._

### Item 4

- **File:** quadtree-graphic/src/main/java/src/Main.java

#### Imports

_No entries found._

### Item 5

- **File:** quadtree-graphic/src/main/java/src/MainScreen.java

#### Imports

_No entries found._

### Item 6

- **File:** quadtree-graphic/src/main/java/src/Screen.java

#### Imports

_No entries found._

### Item 7

- **File:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java

#### Imports

_No entries found._

### Item 8

- **File:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java

#### Imports

_No entries found._

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

_No entries found._

### Item 12

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeConstants.java

#### Imports

_No entries found._

### Item 13

- **File:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java

#### Imports

_No entries found._

### Item 14

- **File:** quadtree-graphic/.idea/fileTemplates/includes/File Header.java

#### Imports

_No entries found._

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

- **Module:** quadtree-graphic/.idea/fileTemplates/includes/File Header.java

- **Role:** other

- **Importance Score:** 11

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 2

- **Module:** quadtree-graphic/src/main/java/src/BaseObject.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 3

- **Module:** quadtree-graphic/src/main/java/src/CanvasPanel.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 4

- **Module:** quadtree-graphic/src/main/java/src/Drawable.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 5

- **Module:** quadtree-graphic/src/main/java/src/Main.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 6

- **Module:** quadtree-graphic/src/main/java/src/MainScreen.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 7

- **Module:** quadtree-graphic/src/main/java/src/Screen.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 8

- **Module:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTree.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 9

- **Module:** quadtree-graphic/src/main/java/src/quadtree/DrawableQuadTreeNode.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 10

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/Neighbour.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 11

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/NeighbourImpl.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 12

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTree.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 13

- **Module:** quadtree-graphic/src/main/java/src/quadtree/core/QuadTreeNode.java

- **Role:** other

- **Importance Score:** 1

#### Why Important

- Role: other
- Limited incoming dependencies
- Cross-feature or core scope

### Item 14

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

- **Files Analyzed:** 14

- **Key Modules:** 14

- **Hotspots:** 0

- **Api Signals:** 0

### Caveats

- API inference depends on explicit HTTP usage patterns in code
- Backend-focused evidence detected; presentation-layer insights may be limited

## Service Http Summary

_No entries found._

## Notable Snippets

_No entries found._
