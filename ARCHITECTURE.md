# Architecture Decision Record: The Future of Unduckified

This document outlines the architectural direction for the Unduckified project, based on a thorough discussion about a potential rewrite. It details the chosen hybrid architecture, the rationale behind the decision, and how it aligns with the project's ambitious feature roadmap.

## 1. The Final Decision: A Hybrid TypeScript + Rust Architecture

After evaluating multiple languages and rewrite strategies, the decision is to **evolve the project into a hybrid architecture, not to perform a full rewrite.**

*   **TypeScript will remain the primary language** for the application's user interface, core logic, and integrations.
*   **Rust (compiled to WebAssembly/WASM) will be incrementally introduced** to serve as a high-performance "engine" for specific, CPU-intensive features.

This model provides the optimal balance of development velocity, flexibility, performance, and long-term maintainability.

## 2. Architectural Roles & Responsibilities

### 2.1. TypeScript: The Application Chassis

TypeScript will continue to handle the majority of the codebase.

*   **Role:**
    *   **User Interface (UI):** All DOM manipulation, component rendering, and user interaction logic.
    *   **API Integrations:** All `fetch` calls to third-party services, which is critical for features like "Personal Assistant Integration" (`!todo`, `!cal`), "Multi-Modal Input" (`!shazam`), and many "Bang Actions."
    *   **Core Application Logic:** The main application orchestration, settings management, and state handling.
*   **Justification:** The JavaScript/TypeScript ecosystem is unbeatable for web development. Its vast collection of libraries (npm), mature frameworks, and flexible, dynamic nature is essential for rapidly implementing the wide array of integration-heavy features planned for Unduckified.

### 2.2. Rust/WASM: The Performance Engine

Rust will be used surgically for performance-critical modules that can be isolated from the UI and browser APIs.

*   **Role:**
    *   **High-Performance Search:** Powering features like "Fuzzy Bang Search" with near-instantaneous results, even with massive datasets.
    *   **Client-Side AI/ML:** Running small, efficient machine learning models directly in the browser for features like "Proactive & Predictive Assistance." This enhances privacy and enables offline capabilities.
    *   **Complex Computations:** Handling any "Bang Actions" that are purely computational (e.g., `!calc`).
*   **Justification:** WebAssembly provides near-native performance in the browser. Rust is a memory-safe, high-performance language with a best-in-class toolchain for compiling to WASM. It allows us to offload heavy lifting from the main JavaScript thread, ensuring the UI remains responsive.

## 3. Future Feature: Domain-Specific Language (DSL) for "Bang Actions" (Lower Priority)

A compelling future direction is to create a custom mini-language to define complex bangs.

*   **Concept:** Instead of being limited to a URL, a bang could be defined by a simple script that describes a series of actions.
*   **Potential Syntax:**
    ```
    # A simple redirect
    !gh-issues {repo} -> "https://github.com/{repo}/issues"

    # An action that calls an API and copies the result
    !shorten {url} -> fetch("https://tinyurl.com/api-create.php?url={url}") -> clipboard

    # An action that performs a calculation and displays it in-app
    !sum {a} {b} -> display(a + b)
    ```
*   **Implementation:** This would involve creating a parser and an execution engine in TypeScript or Rust. It represents the ultimate power-user feature.
*   **Priority:** This is a **lower-priority** but highly desirable long-term goal that fits the project's ethos perfectly.

## 4. Alternative Languages Considered & Rationale for Exclusion

Several other languages were considered, but were ultimately not chosen for the following reasons:

*   **Full Rewrite to ReScript/Elm/PureScript:** While these functional languages offer superior reliability and type safety, their JavaScript interoperability is more rigid than TypeScript's. For a project with a roadmap full of diverse API integrations, this would introduce significant friction and slow down development.
*   **Zig as a Rust Alternative:** Zig is a strong contender for the WASM performance engine and is a valid alternative to Rust. The choice between them often comes down to a philosophical preference for Zig's simplicity vs. Rust's compile-time safety guarantees. Rust was chosen here due to its more mature ecosystem and wider adoption.
*   **Full Rewrite to Rust:** A full rewrite is not practical as Rust/WASM is not well-suited for direct DOM manipulation or the rapid, flexible development required for UI and API integrations. Its strength is in computation, not orchestration.

By formally adopting this hybrid strategy, we set a clear and powerful direction for Unduckified, enabling it to become both richer in features and faster in performance.
