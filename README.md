# Level Up DSA

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Skill: AI Agent](https://img.shields.io/badge/Skill-AI%20Agent-orange.svg)](SKILL.md)

**Level Up DSA** (v1.2.0) is a portable AI agent skill for solving LeetCode, HackerRank, and Online Assessment (OA) coding interview problems with optimized multi-language solutions, platform-specific code (function stubs or custom I/O), and step-by-step whiteboard explanations.

---

## Owner

**Saketh Balijepalli** ([GitHub](https://github.com/sakethbalijepalli/))

---

## Features

When given a coding problem, this skill guides the AI agent to provide:

- **Problem Understanding**: Plain-language distillation of constraints and story-based prompts.
- **Brute Force Breakdown**: Pen-and-paper step-by-step breakdown as if solving on a whiteboard, with its own code and complexity.
- **Brute Force to Optimal Derivation**: Step-by-step transition showing *why* and *how* to optimize the approach.
- **Submission-Ready Code**: Platform-shaped solutions in your requested programming language (Python, Java, C++, JS/TS, Go, Rust, etc.) using platform wrappers (LeetCode `class Solution`, HackerRank `class Result`, or fast I/O), checked against the supplied examples and stated constraints.
- **Line-by-Line Breakdown**: Explanation of the intuition and structural design behind the key logical blocks of the code.
- **Dry Run Trace Table**: Concrete variable state trace walking through sample test inputs step-by-step.
- **Complexity Analysis**: Big-O Time & Space analysis for **both** brute-force and optimized approaches.
- **Edge Case Matrix**: Explicit boundary conditions (overflow, negative numbers, extreme scale bounds, duplicates).
- **Optimization Summary**: Comparative breakdown highlighting why the optimal solution passes time limits (TLE protection).

The skill first extracts the platform, language, stub or I/O format, examples, and constraints from your problem statement, and never invents them. It also supports narrower response modes (Code Only, Hint, Debug/Review, Pattern Explanation) when you ask for them instead of the full coaching format.

---

## Repository Structure

- [`SKILL.md`](SKILL.md): The skill itself and single source of truth: frontmatter, input fidelity step, response modes, the Full Coach response contract, and pointers to references.
- [`AGENTS.md`](AGENTS.md): Short pointer for agents; it defers to `SKILL.md` and holds no separate rules.
- [`references/`](references/): Detail loaded only when needed: [pattern taxonomy](references/patterns.md), [platform signatures and I/O rules](references/platform-formats.md), [edge case matrix](references/edge-cases.md), [explanation standards](references/explanation-standards.md), [solution quality checklist](references/quality-checklist.md), and the [worked Two Sum example](references/examples/two-sum.md).
- [`LICENSE`](LICENSE): Permissive MIT License.

---

## Quick Start / Installation

You can add **Level Up DSA** to your favorite AI assistant or IDE:

### Easiest: one command
Installing is easy. Run this single command and the skill is added to your agent:
```bash
npx skills add sakethbalijepalli/level-up-dsa
```

Or install manually:

### 1. Antigravity / Gemini CLI / Codex
Place the repository files inside your workspace customizations:
```bash
git clone https://github.com/sakethbalijepalli/level-up-dsa.git .agents/skills/level-up-dsa
```

### 2. Claude Desktop / ChatGPT / Custom GPTs
Copy the complete contents of [`SKILL.md`](SKILL.md) into your system prompt or custom instructions. For the full coaching format, include the reference files it points to (especially the quality checklist and explanation standards), or install the complete folder where your tool supports it.

---

## Usage

Simply paste any LeetCode, HackerRank, or OA problem into your chat with your target programming language:

```text
Solve Two Sum in Python with an optimized approach and full explanation.
```

---

## License

This project is licensed under the [MIT License](LICENSE).
