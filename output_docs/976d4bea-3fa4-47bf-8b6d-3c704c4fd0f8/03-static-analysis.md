# Static Code Analysis

Generated at: 2026-05-12T12:38:23.542Z

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

- **Observation:** Service layer pattern is not clearly detected, indicating potential lack of business logic separation from presentation and data access layers. This suggests business logic may be scattered across controllers, utilities, or directly in data access code, making it difficult to test, reuse, and maintain.

- **Severity:** high

- **Business Impact:** Increased time to implement features, higher defect rates in business logic, difficulty in unit testing, and reduced code reusability across different interfaces (API, CLI, etc.)

### Item 2

- **Area:** Routing and Navigation Structure

- **Observation:** Routing/navigation structure is not clearly detected, suggesting either ad-hoc route definitions, missing centralized routing configuration, or unclear navigation patterns. This indicates potential inconsistency in how requests are handled and directed through the application.

- **Severity:** high

- **Business Impact:** Difficult onboarding for new developers, increased bug risk in request handling, poor maintainability of API endpoints, and potential security vulnerabilities from inconsistent request validation

### Item 3

- **Area:** Domain Model Layer

- **Observation:** Domain model layer is weak or not explicit, indicating insufficient separation between domain entities and infrastructure concerns. Business rules and domain logic may be mixed with persistence, validation, or framework-specific code.

- **Severity:** high

- **Business Impact:** Domain knowledge is implicit and scattered, making it harder to understand business requirements, increasing risk of implementing business logic incorrectly, and creating tight coupling to specific frameworks or databases

### Item 4

- **Area:** Lack of Architectural Clarity

- **Observation:** No clear layered architecture detected (layers: unknown), suggesting the codebase may follow an ad-hoc structure without explicit separation of concerns. This indicates potential mixing of responsibilities across the codebase.

- **Severity:** high

- **Business Impact:** Reduced code maintainability, higher cognitive load for developers, increased technical debt accumulation, and difficulty in scaling the team or application

## Decorator Patterns

_No entries found._
