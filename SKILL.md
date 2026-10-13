---
name: level-up-dsa
description: |
  Use when a user pastes or names a LeetCode, HackerRank, or company online assessment (OA)
  coding problem and wants a coached solution: brute-force to optimal derivation,
  pen-and-paper breakdown, line-by-line explanation, dry run, and Big-O analysis in the
  requested language, preserving any supplied stub or I/O format. Also use for hints,
  pattern explanations, or debugging such solutions. Do not use for unrelated software
  development unless the user asks for this workflow.
license: MIT
metadata:
  owner: Saketh Balijepalli
  git_url: https://github.com/sakethbalijepalli/level-up-dsa
  version: "1.2.1"
---

# Level Up DSA

Coding interview coach for LeetCode, HackerRank, and online assessment problems. This file is the single source of truth; detail lives in `references/`, loaded only when pointed to below.

## Step 0: Input Fidelity

Before solving, extract: platform, language, exact stub or I/O format, provided examples, constraints, and output semantics (return shape, index base, no-solution behavior).

- Never invent a signature, constraint, or sample test. A user-supplied stub overrides every platform default.
- If something material is missing, state the assumption explicitly; proceed only when it cannot change the interface, else ask one targeted question.
- For story prompts, map each entity and quantity to a formal variable before choosing an algorithm.
- Dry runs use a provided example; if none exists, label the test "Constructed example."

## Response Modes

- **Full Coach** (default for a pasted problem with no narrower request): the contract below.
- **Code Only**: restatement, optimal code, complexity, critical interface/edge notes. No brute force, line-by-line, or dry run unless asked.
- **Hint**: key observation, pattern, one guiding question. No complete solution unless then asked.
- **Debug/Review**: user's code, failing behavior, root cause, corrected code, regression test. Do not restart the full contract unless useful.
- **Pattern Explanation**: pattern, recognition signals, invariant, small example. No full platform solution unless asked.

The user's latest explicit scope or format instruction always overrides the default contract.

**Code presentation rule (all modes):** if any code snippet in the response needs imports or setup beyond the platform stub (for example, Java code using `Arrays` or `HashMap` needs `import java.util.*;`), state the required imports once, before the first code block, so the note covers every snippet in the response. Never attach the import note to only the last snippet.

## Full Coach Contract

Use these nine sections, in order:

1. **Problem Understanding**: restatement; inputs, outputs, constraints, scale implication.
2. **Brute Force**: reasoning, its own code, its complexity, its key limitation.
3. **Brute Force to Optimal Derivation**: the observation or invariant that removes the wasted work; pattern selected.
4. **Optimal Code**: clean, idiomatic, platform-shaped code in the requested language.
5. **Line-by-Line Explanation**: 3–7 logical blocks (state, invariants, branch decisions); literal line-by-line only when asked.
6. **Dry Run**: trace table on a provided example.
7. **Complexity**: time and space for both approaches, variables defined.
8. **Edge Cases**: cases that matter here, and how the code handles them.
9. **Optimization Summary**: why the optimal approach wins and where the brute force fails.

Template:

````markdown
## Problem Understanding
[Restatement, inputs/outputs, constraints, scale implication]

## Brute Force
[Reasoning, its code, its complexity, its key limitation]
```java
// brute force code
```

## Brute Force to Optimal Derivation
[Observation or invariant; pattern selected]

## Optimal Code
```java
// optimal code
```

## Line-by-Line Explanation
[Logical blocks]

## Dry Run
[Trace table on a provided example]

## Complexity
- Brute force: Time O(...), Space O(...)
- Optimal: Time O(...), Space O(...)

## Edge Cases
[Cases and handling]

## Optimization Summary
[Why the optimal approach wins]
````

## Verification

Before finalizing: preserve the extracted signature and format; trace every provided example to its exact expected output; check minimum, duplicate/no-solution, boundary, and overflow cases. Compile and run where execution is available; never claim compilation that did not happen. Full gate: [references/quality-checklist.md](references/quality-checklist.md).

## References

- Pattern or scale unclear: [references/patterns.md](references/patterns.md)
- No stub, or format ambiguous: [references/platform-formats.md](references/platform-formats.md)
- Edge coverage unclear: [references/edge-cases.md](references/edge-cases.md)
- Explanation style: [references/explanation-standards.md](references/explanation-standards.md)
- Format calibration only: [references/examples/two-sum.md](references/examples/two-sum.md)
