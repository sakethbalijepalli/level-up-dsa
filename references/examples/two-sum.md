# Worked Example: Two Sum (Full Coach)

The one canonical worked example for Level Up DSA. Read it only to calibrate the Full Coach format; do not load it during ordinary problem solving.

**User request:** "Solve Two Sum in Java with a full explanation."
**Problem (LeetCode 1):** Given `int[] nums` and `int target`, return the indices of the two numbers that add up to `target`. Exactly one solution exists; the same element cannot be used twice. Example: `nums = [2, 7, 11, 15]`, `target = 9` → `[0, 1]`. Constraints: $2 \le n \le 10^4$, values and target within $\pm 10^9$.

## Problem Understanding

Find two distinct indices `i`, `j` with `nums[i] + nums[j] = target`, and return them as an array. A solution is guaranteed, so no no-solution behavior needs defining. With $n \le 10^4$, an $O(n^2)$ approach runs about $10^8$ pair checks at worst, which is borderline; an $O(n)$ approach is comfortable.

## Brute Force

Try every pair: for each `i`, scan every `j > i` and check whether the pair sums to `target`. The first matching pair is the answer.

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for (int i = 0; i < nums.length; i++) {
            for (int j = i + 1; j < nums.length; j++) {
                if (nums[i] + nums[j] == target) {
                    return new int[] { i, j };
                }
            }
        }
        return new int[] {};
    }
}
```

Complexity: Time $O(n^2)$, Space $O(1)$. Key limitation: for each element it re-scans the rest of the array, redoing lookups that could have been remembered.

## Brute Force to Optimal Derivation

The brute force asks, for each `nums[i]`: "have I seen `target - nums[i]` anywhere?" That is a membership question, and a hash map answers it in $O(1)$. So make one pass: at each element, check whether its complement is already in the map; if yes, return both indices; if no, store the element and continue. Checking **before** inserting is what prevents an element from pairing with itself and handles duplicates correctly. Pattern: Hash Map lookup.

## Optimal Code

LeetCode judge snippet (the platform supplies the environment; to compile it as a standalone file, add `import java.util.*;` at the top):

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

- **Map setup**: `seen` maps each value already visited to its index, so any earlier element can be retrieved by value in $O(1)$.
- **Complement check**: `need = target - nums[i]` is the only value that can complete the pair with `nums[i]`; if it is in `seen`, the pair is complete and both indices are returned.
- **Insert after checking**: the current element enters the map only after the check, so it can never match itself, and a later duplicate can still match this occurrence.

## Dry Run

Provided example: `nums = [2, 7, 11, 15]`, `target = 9`

| Step | i | num | need | seen | Action |
|------|---|-----|------|------|--------|
| 1 | 0 | 2 | 7 | `{}` | Store `2 -> 0` |
| 2 | 1 | 7 | 2 | `{2: 0}` | `2` exists, return `[0, 1]` |

## Complexity

- **Brute Force**: Time $O(n^2)$, Space $O(1)$.
- **Optimal**: Time $O(n)$, Space $O(n)$ — one pass with $O(1)$ map operations; the map stores up to $n$ elements, where $n$ is the length of `nums`.

## Edge Cases

- **Negative numbers and zero**: handled naturally; the complement arithmetic and map keys work for any sign.
- **Duplicate values** (e.g. `[3, 3]`, target `6`): handled because the check happens before insertion, so the second `3` finds the first.
- **No pair**: cannot occur under the stated guarantee; the fallback `return new int[] {}` is defensive only.

## Optimization Summary

The brute force spends $O(n)$ searching for a partner for every element. The optimal solution turns that repeated search into memory: each value is stored once and each complement lookup costs $O(1)$, reducing total time from $O(n^2)$ to $O(n)$ at the cost of $O(n)$ space. The win grows with the constraints; at $n = 10^4$ it replaces roughly $5 \cdot 10^7$ pair checks with $10^4$ map operations.
