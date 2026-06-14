# The Cost-Complexity-Era Specification: A Normalized Classification System for Programming Languages.

> **Status**: Active RFC (Request for Comments)

> **Version**: 0.1.0

> **Author**: BurningHot687 under Escapee Organization

> **Feedback**: Please open a GitHub issue or pull request to suggest changes, critique formulae, or submit edge cases

## Summary
The low-level vs high-level debate has become ambiguous and counterproductive. The Cost-Complexity-Era Specification (CCE) aims to provide a more constructed definition for *eventually* quantifying language classification, inspired by the study [Flat Maps that improve on the Winkel Tripel](https://arxiv.org/abs/2102.08176v1).

## Detailed Breakdown
CCE operates based on three core pillars of measurement, using the general notion of "low-level" to mean "low score". It is measured using the normal final form of a language.
This is defined as the terminal output of a standard development workflow that is considered the most globally accepted or standard execution environment (e.g., the V8 JIT engine for JavaScript, or native binary machine code for C and Rust).
### Cost
Cost measures the operational distance between the language's Normal Final Form and the raw physical hardware architecture. 
* **The Runtime Factor:** Cost is primarily driven by the scale of the software layer required to execute code. If a language requires a runtime, which is defined as any software which must be bundled with almost every final form of a user's project, its Cost score increases.
* **The Final Form Factor:** Cost is secondarily driven by the final form's distance from native machine code. This is subject co change, removal, or re-definition.
* *The Memory Management Notice:* This specification explicitly avoids utilizing a standalone "garbage collection" metric. Memory management strategies are treated universally as subset features of the overarching Runtime Factor.

### Complexity
Complexity measures the language's architectural ergonomics, balancing vocabulary size against expressive clarity. It is defined by two sub-vectors:
* **Orthogonality:** The degree to which a language's features are independent and can be combined without unexpected side effects or strict limitations. Higher orthogonality reduces keyword bloat, which reduces complexity.
* **Coherence:** The logical mapping of keywords to their universal human definitions. High "coherence" means syntax never contradicts itself (e.g., avoiding the overloading of the `static` keyword in C++ across different scopes). This is a direct counter against excessive orthogonality.
* **Operator Inclusion:** For measurement purposes, symbolic operators (`+`, `==`, etc.) are treated identically to textual keywords and must be counted toward the language's structural footprint.

### Era
The Era metric, arguably the most important one, represents the historical timestamp and goals of the language's design or major refactor. 
* **The Context Selector:** Era does not function as a static numerical modifier within the core equations. Instead, it acts as a **function selector**. 
* **Reactionary Design:** Because language design is inherently reactionary to the hardware limitations of its time, a language's Cost and Complexity must be ran through an Era-specific function to prevent historical bias (e.g., evaluating 1972 constraints using 2026 hardware benchmarks creates massive distortion). This results in a fairer scoring across eras, although there is nothing stopping you from evaluating all languages in a single era.

## Mathematical Starting Point
The following formulae are **not set in stone**. They are explicitly made as a starting point to critique and configure.
### Cost Equation
Cost evaluates the ratio of execution environment overhead relative to raw user instructions, tracking the native readability of the standard output:

$$Cost = \frac{\text{Size of Bundled Runtime Component}}{\text{Size of User Code}} + \left( 1 - \frac{\text{Standard Output Machine-Readability}}{\text{CPU Native Machine Code}} \right)$$

### Complexity Equation
Complexity measures structural footprint against human expressiveness. To prevent perfectly orthogonal, low-feature languages (like Lisp or Brainfuck) from completely collapsing the numerator to zero, a constant modifier of $+1$ is applied to the overlap vector:

$$Complexity = \frac{(\text{Keywords} + \text{Operators}) \times (\text{Overlapping Functions} + 1)}{\text{Total Expressiveness}}$$

### Open Areas of Concern (RFC Feedback Required)
We are actively seeking feedback and mathematical patches for the following edge cases:
1. **The Low-Expressiveness Infinity Trap:** For esoteric languages (e.g., BF), the `Total Expressiveness` denominator approaches $0$, causing the complexity score to mathematically shoot toward infinity. We need an elegant way to establish a **Human Ergonomics Constant ($H$)** to bound this minimum value.
2. **Multi-Paradigm Weights:** How should the parser weigh keywords in multi-paradigm languages (like Python) where developers can achieve the exact same output using entirely different functional, procedural, or object-oriented keyword structures?
3. **Era Boundary Anomalies:** Defining the logical constraints of the Era function selector to prevent negative value distortion when projecting legacy languages into modern execution environments.

## Formatting/Usage Guide
The following is a proposed formatting guide on the results of any calculations made.
1. To use the actual numbers, write the following: `Language Name [CCE[cost, complexity, era]]`
2. For a more generalized sense, consider the following keywords:
   - Metal       - low cost
   - Managed     - high cost
   - Scriptal    - low complexity
   - Industrial  - high complexity
