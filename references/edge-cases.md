# Edge Case Matrix

Load this file when edge coverage for a problem is not obvious. Verify the cases relevant to the problem at hand; do not recite the whole list in a response.

## General

- Empty array/string, single element, all elements identical.
- No valid answer (follow the problem's stated no-solution behavior; if none is stated, say what you assumed).
- Multiple valid answers: does any answer count, or is a specific one required?
- Duplicate values, and whether an element may be paired or combined with itself.
- Negative numbers and zero.
- Extreme bounds: values above $2 \cdot 10^9$ may require `long` (Java/C++) or wider accumulation types; check sums and products for overflow.
- Sorted or reverse-sorted input.
- Index base: zero-based versus one-based in inputs, outputs, and examples.

## Structures

- Graphs: disconnected components, self-loops, parallel edges, single node.
- Trees: single-node tree, skewed (degenerate) tree, null children in level-order input.
- Strings: empty string, single character, all same character, pattern longer than text.
- Intervals/ranges: single point, fully nested, fully disjoint, touching endpoints (inclusive versus exclusive).

## Complexity traps

- Brute force that is fine for one test case but times out across the aggregate of many test cases.
- Recursion depth on degenerate inputs (deep trees, long chains) exceeding stack limits.
- Space used by auxiliary structures at maximum constraint size.
