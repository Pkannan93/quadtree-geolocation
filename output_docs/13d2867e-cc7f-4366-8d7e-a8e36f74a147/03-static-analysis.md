# Static Code Analysis

Generated at: 2026-05-11T09:47:37.246Z

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

- **Observation:** Domain model layer is weak or not explicit. Entities are not clearly identified, indicating a lack of clear separation between domain logic and technical infrastructure. This suggests an anemic domain model or domain logic scattered throughout the codebase.

- **Severity:** high

- **Business Impact:** Reduced ability to evolve business requirements, increased coupling between business and technical concerns, and difficulty for domain experts to understand the codebase.

### Item 3

- **Area:** Routing and Navigation Structure

- **Observation:** Routing/navigation structure is not clearly detected. This indicates potential lack of centralized route management, inconsistent URL patterns, or navigation logic embedded in multiple locations.

- **Severity:** medium

- **Business Impact:** Difficult to maintain consistent user experience, higher risk of broken links, and challenges in implementing cross-cutting concerns like authentication/authorization checks.

### Item 4

- **Area:** Architectural Layering

- **Observation:** Layers are unknown or undefined. The codebase lacks a clear architectural structure (e.g., presentation, business, data access layers). This indicates potential monolithic organization or unclear separation of concerns.

- **Severity:** high

- **Business Impact:** Difficult to scale development team, higher risk of unintended side effects when making changes, and challenges in deploying specific components independently.

### Item 5

- **Area:** API Contract Definition

- **Observation:** API count is zero with no detected patterns. This suggests either missing API documentation, lack of clear API boundaries, or APIs not being explicitly defined. Integration points are unclear.

- **Severity:** medium

- **Business Impact:** Increased integration complexity, difficulty for external teams or third-party developers to consume services, and risk of breaking changes in undocumented APIs.

## Decorator Patterns

_No entries found._
