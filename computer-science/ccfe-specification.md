# The Cost-Confusion-Friction-Era Specification: A Normalized Classification System for Programming Languages.

> **Status**: Active RFC (Request for Comments)

> **Version**: 0.2.0

> **Author**: BurningHot687

> **Feedback**: Please open a GitHub issue or pull request to suggest changes or submit edge cases

## Summary
The low-level vs high-level debate has become ambiguous and counterproductive. The Cost-Confusion-Friction-Era Specification (CCFE) aims to provide a more constructed definition for *eventually* quantifying language classification, inspired by the study [Flat Maps that improve on the Winkel Tripel](https://arxiv.org/abs/2102.08176v1).

## Detailed Breakdown
CCFE operates based on four core pillars of measurement, using the general notion of "low-level" to mean "low score". It is measured using the normal final form of a language.
This is defined as the terminal output of a standard development workflow that is considered the most globally accepted or standard execution environment (e.g., the V8 JIT engine for JavaScript, or native binary machine code for C and Rust). It is also worth noting the need to find a universal program that can be translated to all other languages without compromising unfair logic or performance differences.

### Cost
Cost measures the operational distance between the language's Normal Final Form and the raw physical hardware architecture. 
* **The Runtime Factor:** Cost is primarily driven by the scale of the software layer required to execute code. If a language requires a runtime, which is defined as any software which must be bundled with almost every final form of a user's project, its Cost score increases. A runtime is not needed to be in the final binary, it could be separate, such as a virtual machine.
* **The Final Form Factor:** Cost is secondarily driven by the final form's distance from native machine code. This is subject co change, removal, or re-definition.
* **The Compilation Space Complexity Factor:** It should be noted that space complexity during compilation is specifically the part of compilation which was chosen to affect cost. Time complexity is a factor, but not in Cost.
* *The Memory Management Notice:* This specification explicitly avoids utilizing a standalone "garbage collection" metric. Memory management strategies are treated universally as subset features of the overarching Runtime Factor.

### Confusion
Confusion measures the language's ability to abide by it's own rules. In other words, confusion increases based on the number of edge cases within the linker, parser, compiler, etc. It is defined by two sub-vectors:
* **Complexity:** The degree to which a language's syntax is dissimilar to its already established rules. Lisp should score near 0 for this, but machine code should **also** score near 0 for this, while C++ should score higher.
* **Operator Inclusion:** For measurement purposes, symbolic operators (`+`, `==`, etc.) are treated identically to textual keywords and must be counted toward the language's structural footprint.

### Friction
Friction measures the developer's pain with using the language. It is defined by multiple sub-vectors:
* **Coherence:** The logical mapping of keywords to their universal human definitions. High "coherence" means syntax never contradicts itself (e.g., avoiding the overloading of the `static` keyword in C++ across different scopes). This is a direct counter against excessive orthogonality.
* **Compilation Time Complexity:** The time taken to compile a program, including preprocessing, parsing, and code generation. This is more of a human annoyance than a technical limitation, hence its position in the friction vector.
* **Configuration Package Management:** The ease with which developers can manage dependencies and packages for their projects, alongside how exactly it should be built.
* **CLI:** The ease with which developers can interact with the language's tooling.

### Era
The Era metric, arguably the most important one, represents the historical timestamp and goals of the language's design or major refactor. 
* **The Context Selector:** Era does not function as a static numerical modifier within the core equations. Instead, it acts as a **function selector**. 
* **Reactionary Design:** Because language design is inherently reactionary to the hardware limitations of its time, a language's Cost and Complexity must be ran through an Era-specific function to prevent historical bias (e.g., evaluating 1972 constraints using 2026 hardware benchmarks creates massive distortion). This results in a fairer scoring across eras, although there is nothing stopping you from evaluating all languages in a single era.

### Open Areas of Concern (RFC Feedback Required)
We are actively seeking feedback and mathematical patches for the following edge cases:
1. **Multi-Paradigm Weights:** How should the parser weigh keywords in multi-paradigm languages (like Python) where developers can achieve the exact same output using entirely different functional, procedural, or object-oriented keyword structures?
2. **Formulae Undefined:** How should we calculate each of the 4 values of the language?

## Formatting/Usage Guide
The following is a proposed formatting guide on the results of any calculations made.
1. To use the actual numbers, write the following: `Language Name [CCE[cost, confusion, friction, era]]`
2. For a more generalized sense, consider the following keywords:
   - Metal       - low cost
   - Managed     - high cost
   - Scriptal    - low friction
   - Industrial  - high friction
