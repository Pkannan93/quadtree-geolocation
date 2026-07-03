# Static Code Analysis

Generated at: 2026-05-11T11:19:08.282Z

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

- **Llm Architecture Summary:** Unable to provide architecture summary: no modules, entity candidates, API endpoints, or layer information were detected in the codebase analysis. Please provide codebase details or re-run the static analysis to generate meaningful annotations.

## Llm Code Quality Insights

### Item 1

- **Area:** Service Layer Architecture

- **Observation:** Service layer pattern is not clearly detected. This suggests business logic may be scattered across controllers, utilities, or mixed with infrastructure concerns. Without a dedicated service layer, code reusability is compromised and testing becomes difficult.

- **Severity:** high

- **Business Impact:** Increased time to implement new features, higher defect rates due to logic duplication, and difficulty in maintaining consistent business rules across the application.

### Item 2

- **Area:** Domain Model Definition

- **Observation:** Domain model layer is weak or not explicit. No clear separation between domain entities and data transfer objects (DTOs). This indicates potential anemic domain models or missing domain-driven design principles.

- **Severity:** high

- **Business Impact:** Reduced ability to evolve business logic independently, increased coupling between layers, and difficulty in understanding business requirements from the codebase.

### Item 3

- **Area:** Routing and Navigation Structure

- **Observation:** Routing/navigation structure is not clearly detected. Absence of explicit routing patterns suggests ad-hoc endpoint definitions or unclear request flow management.

- **Severity:** medium

- **Business Impact:** Difficult onboarding for new developers, increased risk of inconsistent API contracts, and challenges in implementing cross-cutting concerns like authentication and authorization.

### Item 4

- **Area:** Lack of Layered Architecture Definition

- **Observation:** Unknown layer structure with no detected API boundaries or clear separation of concerns. This indicates the codebase may lack a defined architectural pattern (e.g., MVC, Clean Architecture, Hexagonal).

- **Severity:** high

- **Business Impact:** Difficulty scaling the team, increased technical debt accumulation, and challenges in implementing architectural governance and standards.

### Item 5

- **Area:** Missing Entity and API Documentation

- **Observation:** Zero entities and zero APIs detected despite files being analyzed. This suggests either incomplete analysis, missing documentation, or a codebase with minimal structure and organization.

- **Severity:** medium

- **Business Impact:** Poor code discoverability, increased time spent understanding system behavior, and risk of duplicate implementations or inconsistent data models.

## Decorator Patterns

_No entries found._
