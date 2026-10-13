# Platform Signatures and I/O Rules

Load this file only when the user has not supplied a stub, or the platform format is ambiguous.

## Precedence

1. A user-supplied stub or I/O specification always wins.
2. An explicit user-stated language comes next.
3. Prior conversation context comes third.
4. If no language is specified and the choice would change the answer, ask, or state the assumption explicitly.

Never impose one language's wrapper on another language (for example, a Java `class Result` shape on a Python answer). Use only language features and standard-library constructs the stated platform supports; if the version is unknown, prefer widely supported constructs.

## LeetCode-style function stubs

The judge calls your function; there is no `main` and no input parsing.

- **Java**: `class Solution` with the exact method signature from the problem (parameter and return types, `TreeNode`/`ListNode` as given).
- **Python**: `class Solution:` with the method from the problem; type hints as supplied by the stub.
- **C++**: `class Solution { public: ... };` with the signature from the problem.
- **JavaScript/TypeScript**: the function or prototype exactly as the stub declares it.

Judge snippets assume the platform's standard environment. If you present Java code as a standalone file instead of a judge snippet, include the imports it needs (e.g. `import java.util.*;`) and say that you did.

## HackerRank

HackerRank problems come in two shapes; match the one the problem actually uses.

- **Stub mode**: complete the provided function in whatever language is selected. In Java this is often `class Result` with exact parameter types (e.g. `List<Integer>`, `List<String>`), but the stub's shape varies by language and problem; follow the supplied stub, not this example.
- **Raw I/O mode**: write a complete program that reads stdin and writes stdout.
  - Java: `public static void main(String[] args)`; use `BufferedReader` with `StringTokenizer` for large inputs instead of `Scanner`.
  - Python: `sys.stdin.read()` for large inputs.
  - C++: fast I/O (`ios::sync_with_stdio(false); cin.tie(nullptr);`).

## Fast I/O guidance

When raw input size is large ($N \ge 10^5$), prefer the fast options above and avoid per-token flushing or synchronization overhead.
