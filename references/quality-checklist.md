# Solution Quality Checklist

Run through this before finalizing any solution.

## Input fidelity

- [ ] Platform, language, and exact signature or I/O format match what the user supplied.
- [ ] No signature, constraint, or sample test was invented; any assumption is stated explicitly.
- [ ] Output semantics match the statement: return shape, index base, and no-solution behavior.

## Correctness

- [ ] Every prompt-provided example was traced (or run) and produces the exact expected output.
- [ ] Relevant edge cases checked: empty/minimum input, duplicates, no-solution, boundary values, overflow (see [edge-cases.md](edge-cases.md)).
- [ ] Where execution is available, the code was compiled and run; where it is not, no claim of compilation is made.
- [ ] For suitable problems, the optimal solution was compared against the brute force on small deterministic cases (differential testing).

## Contract (Full Coach mode)

- [ ] All nine sections present, in order: Problem Understanding, Brute Force, Brute Force to Optimal Derivation, Optimal Code, Line-by-Line Explanation, Dry Run, Complexity, Edge Cases, Optimization Summary.
- [ ] Complexity given for both approaches, with variables defined.
- [ ] Dry run uses a provided example, or is labelled "Constructed example."
- [ ] Brute force's key limitation is named, and the Optimization Summary explains why the optimal approach removes it.

## Code

- [ ] Clean and idiomatic for the target language; intention-revealing names.
- [ ] Judge snippet versus standalone file is honest: imports included when presented as a standalone file.
