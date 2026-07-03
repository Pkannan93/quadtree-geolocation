# Static Code Analysis

Generated at: 2026-05-11T10:42:23.901Z

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

- **Observation:** Service layer pattern is not clearly detected, indicating potential lack of separation between business logic and presentation/data access concerns. This suggests business logic may be scattered across controllers, utilities, or directly in data access code, making it difficult to test, reuse, and maintain.

- **Severity:** high

- **Business Impact:** Increased time to implement features, higher defect rates in business logic, difficulty in unit testing, and reduced ability to reuse business rules across different interfaces (API, CLI, etc.)

### Item 2

- **Area:** Domain Model Layer

- **Observation:** Domain model layer is weak or not explicit, suggesting the codebase lacks a clear representation of core business entities and their relationships. Domain logic may be implicit or embedded in procedural code rather than encapsulated in domain objects.

- **Severity:** high

- **Business Impact:** Poor code maintainability, increased risk of business rule violations, difficulty onboarding new developers, and challenges in evolving the product as business requirements change

### Item 3

- **Area:** Routing and Navigation Structure

- **Observation:** Routing/navigation structure is not clearly detected, indicating unclear or inconsistent patterns for handling application flow, request routing, or state transitions. This may result in ad-hoc navigation logic scattered throughout the codebase.

- **Severity:** medium

- **Business Impact:** Difficult to understand application flow, higher risk of navigation bugs, inconsistent user experience, and challenges in implementing complex workflows or multi-step processes

### Item 4

- **Area:** Architectural Layering

- **Observation:** No clear layering architecture detected (presentation, business logic, data access, etc.), suggesting a monolithic or poorly organized structure. Without explicit layers, dependencies may flow in all directions, creating tight coupling.

- **Severity:** high

- **Business Impact:** Reduced modularity, increased coupling between components, difficulty scaling development team, higher risk of cascading failures, and challenges in deploying or testing individual components

## Decorator Patterns

_No entries found._
