# Level Up DSA

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Skill: AI Agent](https://img.shields.io/badge/Skill-AI%20Agent-orange.svg)](SKILL.md)

**Level Up DSA** is a universal AI agent skill for solving LeetCode, HackerRank, and Online Assessment (OA) coding interview problems with optimized multi-language solutions, platform-specific code (function stubs or custom I/O), and step-by-step whiteboard explanations.

---

## Owner

**Saketh Balijepalli** ([GitHub](https://github.com/sakethbalijepalli/))

---

## Features

When given a coding problem, this skill guides the AI agent to provide:

- **Problem Understanding**: Plain-language distillation of constraints and story-based prompts.
- **Brute Force Breakdown**: Pen-and-paper step-by-step breakdown as if solving on a whiteboard.
- **Brute Force to Optimal Derivation**: Step-by-step transition showing *why* and *how* to optimize the approach.
- **Clean Accepted Code**: Platform-ready solutions in your requested programming language (Python, Java, C++, JS/TS, Go, Rust, etc.) using platform wrappers (LeetCode `class Solution`, HackerRank `class Result`, or fast I/O).
- **Line-by-Line Breakdown**: Deep explanation of the intuition and structural design behind each key line of code.
- **Dry Run Trace Table**: Concrete variable state trace walking through sample test inputs step-by-step.
- **Complexity Analysis**: Big-O Time & Space analysis for **both** brute-force and optimized approaches.
- **Edge Case Matrix**: Explicit boundary conditions (overflow, negative numbers, extreme scale bounds, duplicates).
- **Optimization Summary**: Comparative breakdown highlighting why the optimal solution passes time limits (TLE protection).

---

## Repository Structure

- [`SKILL.md`](SKILL.md): Agent skill metadata, pattern directory, output templates, and core workflow instructions.
- [`AGENTS.md`](AGENTS.md): Detailed agent execution rules, formatting standards, code quality guidelines, and reference examples.
- [`LICENSE`](LICENSE): Permissive MIT License.

---

## Quick Start / Installation

You can add **Level Up DSA** to your favorite AI assistant or IDE:

### 1. Antigravity / Gemini CLI / Codex
Place the repository files inside your workspace customizations:
```bash
git clone https://github.com/sakethbalijepalli/level-up-dsa.git .agents/skills/level-up-dsa
```

### 2. Claude Desktop / ChatGPT / Custom GPTs
Copy the contents of [`SKILL.md`](SKILL.md) or [`AGENTS.md`](AGENTS.md) into your system prompt or custom instructions.

---

## Usage

Simply paste any LeetCode, HackerRank, or OA problem into your chat with your target programming language:

```text
Solve Two Sum in Python with an optimized approach and full explanation.
```

---

## License

This project is licensed under the [MIT License](LICENSE).
