# Static Code Analysis

Generated at: 2026-05-11T11:39:04.212Z

## Symbol Graph

_No entries found._

## Dependency Graph

_No entries found._

## Api Catalog

_No entries found._

## Entity Candidates

_No entries found._

## Sql Usage

_No entries found._

## Event Producers Consumers

_No entries found._

## Architecture Layers

_No entries found._

## Key Modules

_No entries found._

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

- **Overall:** low

### Evidence Coverage

- **Files Analyzed:** 0

- **Key Modules:** 0

- **Hotspots:** 0

- **Api Signals:** 0

### Caveats

- API inference depends on explicit HTTP usage patterns in code

## Service Http Summary

_No entries found._

## Notable Snippets

_No entries found._

## Llm Module Annotations

_No entries found._

- **Llm Architecture Summary:** Unable to provide architecture summary: no modules, entities, or API endpoints were detected in the codebase analysis. Please verify the codebase contains source files and re-run the static analysis.

## Llm Code Quality Insights

### Item 1

- **Area:** Service Layer Architecture

- **Observation:** Service layer pattern is not clearly detected. This suggests business logic may be scattered across controllers, utilities, or mixed with infrastructure concerns. Without a dedicated service layer, code reusability is compromised and testing becomes difficult.

- **Severity:** high

- **Business Impact:** Increased time to implement new features, higher defect rates due to logic duplication, and difficulty in maintaining consistent business rules across the application.

### Item 2

- **Area:** Domain Model Definition

- **Observation:** Domain model layer is weak or not explicit. Entities are not clearly identified, indicating a lack of clear separation between domain objects and infrastructure/persistence models. This leads to anemic domain models or domain logic leaking into other layers.

- **Severity:** high

- **Business Impact:** Reduced ability to evolve business requirements independently from technical implementation. Domain knowledge becomes implicit and harder to communicate across teams.

### Item 3

- **Area:** Routing and Navigation Structure

- **Observation:** Routing/navigation structure is not clearly detected. The absence of a well-defined routing layer suggests potential tight coupling between UI components and business logic, or inconsistent navigation patterns throughout the application.

- **Severity:** medium

- **Business Impact:** Difficult to maintain consistent user experience, higher risk of broken navigation flows, and increased complexity when refactoring UI or adding new features.

### Item 4

- **Area:** Architectural Layering

- **Observation:** No clear layering architecture detected (presentation, business, data access layers are undefined). This indicates potential monolithic structure or unclear separation of concerns, making the codebase difficult to navigate and maintain.

- **Severity:** high

- **Business Impact:** Slower onboarding for new developers, increased risk of unintended side effects when making changes, and difficulty in scaling or modularizing the application.

### Item 5

- **Area:** API Contract Definition

- **Observation:** Zero APIs detected despite analyzing files. This suggests either missing API documentation, lack of clear interface contracts between modules, or absence of API-first design patterns. Internal module communication may be implicit and undocumented.

- **Severity:** medium

- **Business Impact:** Increased integration complexity, difficulty in parallel development, and higher risk of breaking changes when refactoring internal module interfaces.

## Decorator Patterns

_No entries found._
