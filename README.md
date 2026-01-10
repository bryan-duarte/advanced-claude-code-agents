<br>
<br>

<div align="center">

<img width="1080" height="559" alt="Advanced Claude Code Agents" src="https://github.com/user-attachments/assets/89e48112-6509-4645-bd2c-73a22dc094d2" />

# Advanced Claude Code Agents

*Multi-agent system for production workflows with peer review and iterative validation*

[![Claude Code](https://img.shields.io/badge/Claude_Code-Plugin-black?style=flat&logo=data:image/svg%2bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0ibm9uZSIgc3Ryb2tlPSJjdXJyZW50Q29sb3IiIHN0cm9rZS13aWR0aD0iMiIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBzdHJva2UtbGluZWpvaW49InJvdW5kIj48cGF0aCBkPSJNMTIgMmEzIDMgMCAwIDAtMyAzdjE0YTMgMyAwIDAgMCA2IDBWNWEzIDMgMCAwIDAtMy0zeiIvPjxwYXRoIGQ9Ik0xMiAyMmMzLjMxNCAwIDYtMi42ODYgNi02cy0yLjY4Ni02LTYtNi02IDItNiA2IDIuNjg2IDYgNiA2ek0xMiAxNmMtMS4xMDUgMC0yLS4wNTgtMi0uMTA5VjguMTA5QzEwIDguMDU4IDEwLjg5NSA4IDEyIDhzMiAuMDU4IDIgLjEwOXY3Ljc4MmMwIC4wNTEtLjg5NS4xMDktMi4xMDkuMTA5eiIvPjwvc3ZnPg==)](https://claude.ai/code)
[![Version](https://img.shields.io/badge/version-1.0.0-black?style=flat)](https://github.com/BryanCaceres/advanced-claude-code-Agents)

</div>

<br>
<br>

## Quick Start

```bash
# Add the marketplace
/plugin marketplace add https://github.com/BryanCaceres/advanced-claude-code-Agents

# Install the plugin
/plugin install advance-dev-agents@advance-dev-agents-marketplace
```

<br>

## MCP Configuration

Real-time documentation is powered by **DeepWiki** (Zero-config) and **Context7** (Auth required).

Get you context7 api key from [Context7](https://context7.com/dashboard)

**Persistent Setup (Recommended)**

```bash
claude config set --global env.CONTEXT7_API_KEY "your_api_key"
```

**Manual Export**

| Platform | Command |
|----------|---------|
| MacOS/Linux | `export CONTEXT7_API_KEY="your_key"` |
| Windows | `$env:CONTEXT7_API_KEY="your_key"` |

<br>

## Workflows

<div align="center">

### Code Review Orchestrator

`/code-review:code-review-[custom] [scope]`

Comprehensive analysis from multiple specialized perspectives

---

### Code Fixer Orchestrator

`/code-review:code-fixer-orchestrator-[custom] [problem list]`

Coordinated problem resolution with parallel execution and strategic grouping

---

### Code Change Orchestrator

`/code-review:code-change-request-[custom] [change description]`

Implementation of complex changes with multi-phase exploration, research, and validation

</div>

<br>
<hr>
<br>

## Why This Is Different

### 1. Scope Definition

You choose: staged changes, branch vs origin, feature folder, or custom files.

Auto-detects tech stack *(because reading minds is still in beta)*.

<details>
<summary>See available scopes</summary>

- `staged` — Git staged changes
- `branch` — Branch vs origin
- `folder` — Specific feature folder
- `custom` — Hand-picked files

</details>

<hr>

### 2. Agent Discovery

**Scans for complementary agents in your environment.**

Next.js project? You get Next.js architect agent.

You decide which perspectives to include.

<blockquote>
<strong>Crucial:</strong> The plugin COMPLEMENTS your existing agents.
</blockquote>

<details>
<summary>How it works</summary>

The plugin searches your workspace for agent definitions (AGENTS.md, .claude/agents/) and offers to integrate relevant specialists into the review process.

</details>

<hr>

### 3. Analysis Level Selection

| Level | Coverage |
|-------|----------|
| **Basic** | Bug detection + Clean Code |
| **Advanced** | + SOLID + OWASP + Architecture |

<hr>

### 4. Learning Documentation

Document recurring patterns to build knowledge.

Snippets for `AGENTS.md` | `CLAUDE.md` over time.

<details>
<summary>Knowledge accumulation</summary>

Each review identifies patterns worth documenting. The learning investigator captures these for future context, creating a living knowledge base.

</details>

<hr>

### 5. Human in the Loop

**You are part of the loop.**

AI oversells refactorizations. Your judgment matters.

Review and strip what shouldn't be fixed.

<blockquote>
<strong>Reality check:</strong> Not every suggestion should be implemented. You maintain final say.
</blockquote>

<hr>

### 6. Clarification Phase

Ambiguous? Asks precise questions. No assumptions.

<details>
<summary>Example</summary>

If scope is unclear, you'll see: "Did you mean X or Y?" instead of the agent guessing wrong.

</details>

<hr>

### 7. Research Phase

Queries official docs via MCP.

Exact versions verified *(no "should work")*.

<hr>

### 8. Decision Phase

You confirm the approach. It's your code.

<blockquote>
<strong>Your approval gates all progress.</strong>
</blockquote>

<hr>

### 9. Validation Loop

**Critical Gate: External approval required.**

`approach-reviewer` examines all changes.

Only "ACCEPT" allows progression.

<details>
<summary>The safety mechanism</summary>

After implementation, the approach-reviewer validates:
- Changes match approved approach
- No unintended side effects
- Quality standards met

Any failure returns to decision phase. No silent failures.

</details>

<br>
<hr>
<br>

## Agents

**Investigators**

| Agent | Specialty |
| :--- | :--- |
| `bugs-investigator` | Logical errors, race conditions, runtime problems |
| `code-review-investigator` | Clean Code, readability, and maintainability |
| `hard-review-investigator` | SOLID patterns and design principles |
| `owasp-investigator` | Security vulnerabilities (OWASP Top 10) |
| `architecture-investigator` | Structural integrity, patterns, and consistency |
| `technical-researcher` | Official documentation search and version verification |
| `learning-investigator` | Knowledge management and documentation |

<br>

**Implementation**

| Agent | Role |
| :--- | :--- |
| `code-fixer` | Executes code changes following strict standards |
| `approach-reviewer` | Quality gatekeeper — validates and can reject changes |

<br>

## Skills System

The plugin enforces the `software-developer` skill in all code modifications:

- **Strict contracts** — Explicit schemas, no `Any` types
- **Boundary validation** — Validate once when receiving external data
- **Errors as state** — Structured state objects
- **Self-documenting code** — Names that reveal intention
- **Guard clauses** — Reduce nesting with early returns
- **Named booleans** — Complex conditions with descriptive names
- **No magic numbers** — Constants with semantic meaning

<br>
<hr>
<br>

<div align="center">

**Developed by [Bryan Duarte](https://github.com/BryanCaceres)**

[LinkedIn](https://www.linkedin.com/in/bryanduarte/) · [GitHub](https://github.com/BryanCaceres)

</div>

<br>
