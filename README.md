# Advanced Claude Code Agents                


<img width="1080" height="559" alt="image" src="https://github.com/user-attachments/assets/89e48112-6509-4645-bd2c-73a22dc094d2" />

---

## 📦 Installation

```bash
# 1. Add the marketplace
/plugin marketplace add https://github.com/BryanCaceres/advanced-claude-code-Agents

# 2. Install the plugin
/plugin install advance-dev-agents@advance-dev-agents-marketplace
```

---

## 🔌 Dependencies

This plugin integrates with **Context7 MCP server** for real-time documentation retrieval.

---

Look, I'll be honest with you: I was tired of AI giving me code that *kinda* works but definitely shouldn't exist in production unless you hate your future self.

> *(Yes, I'm looking at you, Claude Sonnet. No, not you specifically—you're actually great. But you know who you are.)*

This multi-agent system for `Claude Code` that turns your casual "just make it work" prompts into actual, production-grade workflows with peer review, validation loops, and agents that specialize in different aspects of code quality.

Think of it like having a senior dev team that actually reviews each other's work before anything gets merged. I know, """" revolutionary """" concept—code that gets reviewed before production.


## Core Workflows

---




### 📋 Workflow 1: Code Review Orchestrator

**Command:** `/code-review:code-review-[custom] [scope]`

**The deal:** Comprehensive code analysis from multiple specialized perspectives. Like a code review, but with people who actually know what they're talking about.

#### Step-by-Step Flow

---

**1. Scope Definition**

- You choose what to review: staged changes, branch vs origin, some feature folder or custom file selection
- The system automatically detects your tech stack and project context *(because reading minds is still in beta)*

---

**2. Agent Discovery**

- The orchestrator scans for complementary agents in your environment
- If you're working on a `Next.js` project, it might offer a Next.js architect agent.
- You decide which specialized perspectives to include—it's your code review.

> **This is crucial to use this plugin in any project** — the plugin complements the agents that you have in your project.

---

**3. Analysis Level Selection**

The orchestrator gona ask you between two analysis levels:

| Level | Coverage |
|-------|----------|
| **Basic Review** | Bug detection + Clean Code principles *(the essentials)* |
| **Advanced Review** | Everything in Basic, plus SOLID patterns, OWASP security audit, and architectural integrity *(the full treatment, but slower)* |

---

**4. Parallel Agent Execution**

Multiple specialist agents analyze your code *simultaneously* *(because who has time to wait around?)*:

- `bugs-investigator` — hunts logic errors and runtime issues
- `code-review-investigator` — validates readability and maintainability
- `hard-review-investigator` — checks SOLID principle compliance
- `owasp-investigator` — scans for security vulnerabilities
- `architecture-investigator` — verifies structural integrity and patterns

Each agent operates with deep domain expertise, not that "I kinda know everything" vibe.

---

**5. Centralization and Cross-Verification**

- The orchestrator consolidates all findings
- Conflicting recommendations are resolved *(diplomatically, usually)*
- Redundancies are filtered out
- A unified, prioritized report emerges like a phoenix from the ashes

---

**6. Learning Documentation**

If recurring error patterns are identified, the orchestrator will ask you if you want to document them.

- You choose which categories to document
- The `learning-investigator` persists knowledge to your project's learning library

> **WHY THIS?** As you run more code reviews, you'll rack up tons of snippets and examples to add to your `AGENTS.md` | `CLAUDE.md` or use in your Claude skills.

-------------------------------------------------------------------------X-----------------------------------------------------------------



## 🧑‍💻 Human in the Loop

> **Yes, human—yes, YOU—you're part of the loop.**

You need to read the report, because AI tends to oversell the need for massive refactorizations. And applying a whole new pattern when a small adjustment would do the trick doesn't do any favors for your sanity.

**YES** — Your human judgment still matters.

So yes, human—read the report and strip out anything you think shouldn't be fixed. This report feeds into the next workflow, which handles the bulk fixes.



-------------------------------------------------------------------------X-----------------------------------------------------------------

### 🔧 Workflow 2: Code Fixer Orchestrator

**Command:** `/code-review:code-fixer-orchestrator-[custom] [problems list or reference]`

**The deal:** Coordinate large-scale problem resolution with strategic grouping and parallel execution. Because fixing 47 issues one by one is nobody's idea of fun.

#### Step-by-Step Flow

---

**1. Input Validation**

- The orchestrator verifies the problem list or reference exists
- If input is empty or invalid, you're prompted for clarification immediately *(no "I'll just guess" situations)*

---

**2. Strategic Analysis Phase**

- **Multi-Perspective Simulation**: Problems analyzed from Security, Performance, Technical Debt, and UX viewpoints
- **Tree of Thought Grouping**: Issues are grouped by architectural similarity, not file proximity
  - *Example: All "data validation" issues form one cluster, all "DB optimization" issues form another*
- Grouping minimizes merge conflicts and maximizes logic reuse *(fancy way of saying "works better, fights less")*

---

**3. High-Visibility Documentation**

- A master plan is created in `docs/bulk_fixes/[name]_fix_plan_[TIMESTAMP].md`
- Contains global task list, assignment matrix, and collaboration space
- This document is the "Single Source of Truth" for the entire operation *(buzzword compliant, I know)*

---

**4. Elite Delegation**

Multiple `code-fixer` agents are invoked in parallel:

- Each receives a precise cluster of related problems
- Each must follow the `software-developer` skill *(consistency is king)*
- Each must research official docs via Context7 *(no "I think it works this way")*
- Each must document progress in the shared tracking document

---

**5. Supervision and Validation**

- **Chain of Verification**: The orchestrator monitors the tracking document for vague updates *(no "fixed some stuff" allowed)*
- **Final Validation**: The `approach-reviewer` examines the entire change set
- **Refinement Loop**: If validation fails, code-fixers are reassigned to address issues
- **Closure**: Only after "ACCEPT" from the reviewer is completion confirmed *(finish lines exist for a reason)*


-------------------------------------------------------------------------X-----------------------------------------------------------------



### ✨ Workflow 3: Code Change Orchestrator

**Command:** `/code-review:code-change-request-[custom] [detailed change description]`

**The deal:** Implement complex code changes through validated, multi-phase execution. Because "just refactor it" is not a strategy.

> **But...what if I just want to request a single specific change?** This is the workflow for you.

#### Step-by-Step Flow

---

**1. Clarification Phase**

- If your request is ambiguous, the orchestrator asks precise questions
- No assumptions are made—clarity precedes action *(unlike that one teammate who just "figures it out" and breaks everything)*

---

**2. Exploration Phase (Code Explorers)**

- Multiple `code-explorer` agents run in parallel
- They map dependencies, identify side effects, trace data flow
- The full impact of the requested change is understood before any code is touched—imagine that

---

**3. Research Phase (Technical Researcher)**

- The `technical-researcher` agent queries official documentation via Context7
- Exact dependency versions are verified *(because "should work" is not a version)*
- Best practices and compatibility issues are identified
- Current implementation is compared against official docs

---

**4. Decision Phase (User Feedback)**

- The orchestrator presents what will be done and how
- Key design decisions are explained
- You confirm the approach before implementation begins—it's your code

---

**5. Implementation Phase (Code Fixers)**

- One or more `code-fixer` agents receive ultra-precise instructions
- Each follows the `software-developer` skill for consistency
- Progress is documented in `docs/code_changes/` in real-time

---

**6. Validation Loop (Approach Reviewer)**

- **Critical Gate**: No change is considered finished without external approval
- The `approach-reviewer` examines all modified files
- If validation fails, the loop repeats: `code-fixers adjust → reviewer validates`
- Only an "ACCEPT" verdict allows progression *(no participation trophies here)*

---

**7. Learning Phase (Optional)**

- If the change fixed a bug, the orchestrator offers to document the learning
- Root cause, anti-patterns, and solutions are archived
- Future agents benefit from this knowledge

## The Plugin Agent Ecosystem

---

### 🔍 Investigator Agents (Analysis Specialists)

| Agent | Specialty |
|-------|-----------|
| `bugs-investigator` | Logic errors, race conditions, runtime issues |
| `code-review-investigator` | Clean Code principles, readability |
| `hard-review-investigator` | SOLID patterns, design principles |
| `owasp-investigator` | Security vulnerabilities *(OWASP Top 10)* |
| `architecture-investigator` | Structural integrity, patterns, consistency |
| `technical-researcher` | Official documentation lookup, version verification |
| `learning-investigator` | Knowledge management and documentation |

---

### 🛠️ Implementation Agents

| Agent | Role |
|-------|------|
| `code-fixer` | Executes code changes following strict standards |
| `approach-reviewer` | Quality gatekeeper—validates and can reject changes |

---

### 🎯 Orchestrator Agents

Orchestrators manage workflows, coordinate parallel execution, consolidate findings, and ensure quality through iterative validation loops.

---

## The Skill System

**`software-developer` skill** — Enforced across all code modifications

### Key Principles

- **Strict Contracts** — No `Any` types—use explicit schemas
- **Boundary Validation** — Validate once when receiving external data
- **Errors as State** — Return structured state objects, don't just log
- **Self-Documenting Code** — Names reveal intent; obvious comments are avoided
- **No Nesting** — Functions at module scope only
- **Guard Clauses** — Reduce nesting through early returns
- **Named Booleans** — Complex conditions get descriptive names
- **No Magic Numbers** — Constants with semantic meaning

> This skill ensures consistency across all agents and maintains codebase health.

---

## 📦 Installation

```bash
# 1. Add the marketplace
/plugin marketplace add https://github.com/BryanCaceres/advanced-claude-code-agents

# 2. Install the plugin
/plugin install advance-dev-agents@advance-dev-agents
```

---

## 🔌 Dependencies

This plugin integrates with **Context7 MCP server** for real-time documentation retrieval.

---

## The Fundamental Difference

| Simple Prompt | Advance Dev Agents |
|---------------|-------------------|
| Single generalist attempt | Multiple specialized perspectives |
| No validation | Independent reviewer approval |
| Isolated interactions | Persistent learning system |
| Sequential thinking | Parallel execution |
| First attempt = final result | Iterative refinement until quality |
| Shallow analysis | Deep domain expertise |
| No documentation | Complete audit trail |

---


<div align="center">

*Developed with ♥️ by **Bryan Duarte** — [LinkedIn](https://www.linkedin.com/in/bryanduarte/) — [GitHub](https://github.com/BryanCaceres)*

</div>
