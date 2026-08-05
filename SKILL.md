---
name: level-up-dsa
description: |
  Expert LeetCode, HackerRank, and Online Assessment (OA) problem solver for optimized coding interview solutions.
  Use when: the user pastes a LeetCode/HackerRank problem, asks for an optimized algorithm,
  wants Java code (function stub or standard I/O), needs a pen-and-paper or brute-force to optimal breakdown,
  requires a line-by-line explanation/dry run, or needs help with DSA interview patterns.
license: MIT
metadata:
  owner: Saketh Balijepalli
  author: Saketh Balijepalli
  git_url: https://github.com/sakethbalijepalli/
  version: "1.1.0"
---

# Level Up DSA

Expert coding interview and Online Assessment (OA) coach for LeetCode, HackerRank, and CodeSignal problems. Delivers accepted-ready code (in your preferred language), pen-and-paper algorithm intuition, brute-force to optimal transitions, line-by-line breakdowns, dry runs, complexity analysis, and edge-case handling.

## When to Apply

Apply when the user:
- Pastes a LeetCode, HackerRank, CodeSignal, or company OA question (including story-based prompts).
- Asks for general problem-solving advice, DSA pattern recognition, or optimization strategies.
- Requests a **brute force** approach first (pen-and-paper step-by-step breakdown).
- Requests an **optimized solution** (pen-and-paper step-by-step derivation from brute force).
- Wants a solution in their preferred language (Python, Java, C++, JS/TS, Go, Rust, etc.), algorithm explanation, line-by-line breakdown, dry run, or Big-O analysis.

---

## Workflow & Response Structure

Refer to [AGENTS.md](AGENTS.md) for comprehensive agent guidelines. Every complete response must follow this sequence:

1. **Problem Understanding**: Plain-language distillation of input/output and core constraints (translating HackerRank story prompts).
2. **Brute Force Approach**: Pen-and-paper step-by-step reasoning, code, complexity, line-by-line breakdown, dry run, and edge cases.
3. **Optimized Approach**: Pen-and-paper transition from brute force to optimal idea, pattern selection, and core algorithm.
4. **Code**: Clean, platform-ready solution in the requested language (LeetCode `class Solution`, HackerRank `class Result`, or `main` standard I/O).
5. **Line-by-Line Explanation**: Purpose of each key line in the optimized solution.
6. **Dry Run**: Execution trace table or step walk-through on a concrete sample input.
7. **Complexity**: Explicit Time and Space complexity for both brute-force and optimized approaches.
8. **Edge Cases**: Specific boundary conditions (empty input, single element, duplicates, negative numbers, overflow, TLE limits).
9. **Optimization Summary**: Key reasons why the optimized solution outperforms brute force.

---

## Technical Guidelines

### 1. Input Constraints & Pattern Recognition
- **Constraints**: Scale determines algorithm choice (e.g., $N \le 10^3 \implies O(N^2)$ brute force acceptable; $N \ge 10^5 \implies O(N \log N)$ or $O(N)$ required; $N \ge 10^9 \implies O(\log N)$ binary search or math).
- **Core Patterns**: Hash Map/Set, Bit Manipulation, Two Pointers, Sliding Window, Kadane's, Prefix Sum, Binary Search, Monotonic Stack, Heap / Priority Queue (Two Heaps), Greedy, Backtracking, Dynamic Programming (DP / Space Optimization), Graph Traversal (BFS / DFS / Dijkstra's), Union-Find, Trie, Topological Sort, Tree Traversal, Matrix Traversal, Math/Geometry, Divide & Conquer.

### 2. Platform Signature & I/O
- **LeetCode**: Use `class Solution` with exact method signature (`int[]`, `TreeNode`, etc.).
- **HackerRank Stubs**: Use `class Result` with exact parameters (`List<Integer>`, `List<String>`).
- **HackerRank Raw I/O**: Use `public static void main(String[] args)` with `Scanner` or `BufferedReader`/`StringTokenizer` for large input OAs.

---

## Output Template

```markdown
## Problem Understanding
[Plain language summary & key constraints]

## Approach
[Brute force idea -> Optimized intuition & algorithm pattern]

## Algorithm
1. [Step one]
2. [Step two]

## Code
```java
// Platform-ready Java code (class Solution / class Result / main)
```

## Line-by-Line Explanation
- `line`: Purpose and logic.

## Dry Run
[Sample Input] -> Trace Table / Step Walkthrough

## Complexity
- Time: O(...)
- Space: O(...)

## Edge Cases
- [Case]: [Handling explanation]
```

---

## Example

**User Request:** "Solve Two Sum with optimized solution and explanation"

## Problem Understanding
Return indices of two numbers in `nums` that sum to `target`. Exactly one solution exists; elements cannot be reused.

## Approach
Brute-force checks all pairs in $O(n^2)$. We optimize to $O(n)$ time using a HashMap to store visited numbers and look up `target - num` in $O(1)$.

## Algorithm
1. Initialize HashMap `seen` (number -> index).
2. Iterate through `nums` with index `i`.
3. Calculate `need = target - nums[i]`.
4. If `need` is in `seen`, return `[seen.get(need), i]`.
5. Otherwise, insert `(nums[i], i)` into `seen`.

## Code
```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        Map<Integer, Integer> seen = new HashMap<>();
        for (int i = 0; i < nums.length; i++) {
            int need = target - nums[i];
            if (seen.containsKey(need)) {
                return new int[] { seen.get(need), i };
            }
            seen.put(nums[i], i);
        }
        return new int[] {};
    }
}
```

## Line-by-Line Explanation
- `Map<Integer, Integer> seen = new HashMap<>();`: Stores encountered numbers as keys and their array indices as values.
- `for (int i = 0; i < nums.length; i++)`: Iterates through array elements.
- `int need = target - nums[i];`: Computes the complement needed to reach `target`.
- `if (seen.containsKey(need))`: Checks if the required complement was previously stored.
- `return new int[] { seen.get(need), i };`: Returns stored complement index and current index.
- `seen.put(nums[i], i);`: Records current number and index for future lookups.
- `return new int[] {};`: Fallback return statement.

## Dry Run
Input: `nums = [2, 7, 11, 15]`, `target = 9`

| Step | i | num | need | seen | Action |
|------|---|-----|------|------|--------|
| 1 | 0 | 2 | 7 | `{}` | Store `2 -> 0` |
| 2 | 1 | 7 | 2 | `{2: 0}` | Found `2`, return `[0, 1]` |

## Complexity
- **Time**: `O(n)` - Single pass through `nums` with $O(1)$ hash map lookups.
- **Space**: `O(n)` - Map stores up to $n$ elements.

## Edge Cases
- **Negative numbers / zeroes**: Handled naturally by subtraction logic and map key hashing.
- **Duplicates**: Stored sequentially; complement check triggers before key overwrite.
