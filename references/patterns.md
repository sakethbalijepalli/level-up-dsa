# Pattern Taxonomy and Scale Heuristics

Load this file when pattern selection or target complexity is not obvious from the problem.

## Scale heuristics (orientation, not rules)

Rough bands for a single test case under typical limits:

- $N \le 10^3$: an $O(N^2)$ brute force is usually feasible.
- $N \ge 10^5$: aim for $O(N \log N)$ or $O(N)$.
- $N \ge 10^9$: the data usually cannot be read element-by-element; expect $O(\log N)$ (binary search), a formula, or coordinate/value-range reasoning.

Before choosing a target complexity, also consider: the time and memory limits, constant factors, the number of test cases and the aggregate limit on the sum of $N$, value ranges versus element counts, graph density, and the cost of reading the input itself. A band that works for one test case may fail across many.

## Pattern selection

State the invariant or correctness reason for the selected pattern before coding.

- **Hash Map/Set**: repeated membership or complement lookups. Check-before-insert ordering matters when duplicates or self-pairing are possible.
- **Two Pointers**: sorted input, or pairs/subarrays with a monotonic relationship between the pointers.
- **Sliding Window**: a contiguous segment plus a window property that stays valid when the left edge advances (e.g. all values non-negative). State what makes shrinking valid.
- **Prefix Sum**: many range-sum queries, or counting subarrays by sum via a frequency map of prefixes.
- **Kadane's**: maximum subarray sum; state what the running value represents at each index.
- **Sorting**: when order unlocks two pointers, greedy choices, or interval merging.
- **Binary Search**: a monotonic predicate. Define the predicate and the boundary invariant (what is always true on each side).
- **Monotonic Stack**: next greater/smaller element, or span problems where each element is pushed and popped once.
- **Heap / Priority Queue (incl. Two Heaps)**: top-k, streaming medians, merging sorted streams.
- **Greedy**: state the exchange or dominance argument showing a local choice never hurts.
- **Backtracking**: enumerate subsets, permutations, or combinations; define how choices are made and undone.
- **Divide & Conquer**: independent subproblems whose results combine cheaply.
- **Dynamic Programming**: define the state, the transition, the base cases, and the evaluation order. Check whether space compression preserves every value the transition still needs.
- **Trees**: traversals (inorder, preorder, postorder, level order); define what each recursive call returns.
- **Graphs**: BFS/DFS, Dijkstra's, topological sort, matrix traversal. Define the node/edge mapping, when nodes are marked visited, and how disconnected components are handled.
- **Union-Find**: dynamic connectivity and grouping with near-constant amortized operations.
- **Trie**: shared prefixes across many strings.
- **Bit Manipulation / Math & Geometry**: parity, masks, XOR cancellation, counting arguments, closed-form formulas.
