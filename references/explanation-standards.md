# Explanation Standards

Load this file when calibrating how a Full Coach response should read.

## Algorithm intuition

Explain the key insight before the code: the data structure's role, how the input is progressed through, and why the approach is correct (the invariant or observation it rests on).

## Line-by-line explanation

Explain the optimized code in 3–7 logical blocks. Focus on data-structure state, invariants, branch decisions, and non-obvious operations. Do not narrate imports, braces, simple iteration, or plain returns unless they encode an important edge-case decision. Give a literal line-by-line treatment only when the user explicitly asks for one.

## Dry run

Trace a prompt-provided example (or one labelled "Constructed example") in a table that follows the variables as they change:

```markdown
| Step | Index/Var | State | Condition | Action |
|------|-----------|-------|-----------|--------|
```

## Complexity

State time and space for both the brute-force and the optimal approach, and define every variable used:

```markdown
## Complexity
- Brute force: Time O(n^2), Space O(1).
- Optimal: Time O(n), Space O(n) - hash map stores up to n elements, where n is the length of the input array.
```

## Code quality

- Clean, idiomatic code in the target language with platform-ready wrappers, minimal imports, and no over-engineering.
- Intention-revealing names (e.g. `left`/`right`, `window_sum`, `prefix_sum`, `seen`, `need`, `dp`, `graph`, `visited`, `result`).
- Efficient I/O when raw input is large; see [platform-formats.md](platform-formats.md).
