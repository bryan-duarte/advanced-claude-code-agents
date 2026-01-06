# Advance Dev Agents

A multi-agent orchestration system for Claude Code that transforms simple prompts into sophisticated, production-grade development workflows through specialized agent coordination and iterative quality assurance.

---

## Why This Matters

Traditional AI-assisted development relies on single prompts that attempt to do everything at once: analyze, research, implement, and validate. This approach has fundamental limitations:

- **Cognitive Overload**: A single prompt must maintain context across security, performance, architecture, and business logic simultaneously
- **No Peer Review**: Changes are made without independent validation from specialized perspectives
- **Shallow Analysis**: Generic prompts lack depth in domain-specific concerns (OWASP security, SOLID patterns, database optimization)
- **No Iteration**: Once a response is generated, there's no built-in mechanism for refinement loops
- **Lost Knowledge**: Each interaction is isolated—learnings aren't systematically captured for future reference

**Advance Dev Agents** solves this by treating each development task as a multi-agent orchestration problem. Specialized agents work in parallel, validate each other's work, and only proceed when independent reviewers grant approval.

---

## The Three Core Workflows

### Workflow 1: Code Review Orchestrator

**Command:** `/code-review:code-review-[custom] [scope]`

**Purpose:** Comprehensive code analysis from multiple specialized perspectives

#### Step-by-Step Flow

1. **Scope Definition**
   - You choose what to review: staged changes, branch vs origin, or custom file selection
   - The system automatically detects your tech stack and project context

2. **Agent Discovery**
   - The orchestrator scans for complementary agents in your environment
   - If you're using Next.js, it might offer a Next.js architect agent
   - You decide which specialized perspectives to include

3. **Analysis Level Selection**
   - **Basic Review**: Bug detection + Clean Code principles
   - **Advanced Review**: Everything in Basic, plus SOLID patterns, OWASP security audit, and architectural integrity

4. **Parallel Agent Execution**
   - Multiple specialist agents analyze your code simultaneously:
     - `bugs-investigator` hunts logic errors and runtime issues
     - `code-review-investigator` validates readability and maintainability
     - `hard-review-investigator` checks SOLID principle compliance
     - `owasp-investigator` scans for security vulnerabilities
     - `architecture-investigator` verifies structural integrity and patterns
   - Each agent operates with deep domain expertise, not general knowledge

5. **Centralization and Cross-Verification**
   - The orchestrator consolidates all findings
   - Conflicting recommendations are resolved
   - Redundancies are filtered out
   - A unified, prioritized report emerges

6. **Learning Documentation**
   - Recurring error patterns are identified
   - You choose which categories to document
   - The `learning-investigator` persists knowledge to your project's learning library

#### What You Get

A professional report saved to `docs/agent_reports/` containing:
- Executive Summary (3-paragraph technical overview)
- Key Findings prioritized by severity with specific fix recommendations
- Actionable Roadmap (concrete technical steps before merge)
- AI Context (dense technical summary for future AI interactions)

#### Why This Beats a Simple Prompt

A single "review my code" prompt gives you a generalist's overview. This workflow gives you five senior specialists, each examining your code through their lens, plus an orchestrator ensuring consistency and a learning system preventing recurrence of issues.

---

### Workflow 2: Code Change Orchestrator

**Command:** `/code-review:code-change-request-[custom] [detailed change description]`

**Purpose:** Implement complex code changes through validated, multi-phase execution

#### Step-by-Step Flow

1. **Clarification Phase**
   - If your request is ambiguous, the orchestrator asks precise questions
   - No assumptions are made—clarity precedes action

2. **Exploration Phase (Code Explorers)**
   - Multiple `code-explorer` agents run in parallel
   - They map dependencies, identify side effects, trace data flow
   - The full impact of the requested change is understood before any code is touched

3. **Research Phase (Technical Researcher)**
   - The `technical-researcher` agent queries official documentation via Context7
   - Exact dependency versions are verified
   - Best practices and compatibility issues are identified
   - Current implementation is compared against official docs

4. **Decision Phase (User Feedback)**
   - The orchestrator presents what will be done and how
   - Key design decisions are explained
   - You confirm the approach before implementation begins

5. **Implementation Phase (Code Fixers)**
   - One or more `code-fixer` agents receive ultra-precise instructions
   - Each follows the `software-developer` skill for consistency
   - Progress is documented in `docs/code_changes/` in real-time

6. **Validation Loop (Approach Reviewer)**
   - **Critical Gate**: No change is considered finished without external approval
   - The `approach-reviewer` examines all modified files
   - If validation fails, the loop repeats: code-fixers adjust → reviewer validates
   - Only an "ACCEPT" verdict allows progression

7. **Learning Phase (Optional)**
   - If the change fixed a bug, you're offered the option to document the learning
   - Root cause, anti-patterns, and solutions are archived
   - Future agents benefit from this knowledge

#### What You Get

- A progress document in `docs/code_changes/` tracking every decision and modification
- Implemented changes that have passed independent validation
- Optional knowledge persistence for bug fixes
- Confidence that the change is correct, maintainable, and secure

#### Why This Beats a Simple Prompt

A "implement this feature" prompt gives you a first attempt that might work. This workflow gives you exploration, research, user confirmation, implementation, independent validation, and iterative refinement until a senior reviewer grants approval. It's the difference between a draft and a peer-reviewed production change.

---

### Workflow 3: Code Fixer Orchestrator

**Command:** `/code-review:code-fixer-orchestrator-[custom] [problems list or reference]`

**Purpose:** Coordinate large-scale problem resolution with strategic grouping and parallel execution

#### Step-by-Step Flow

1. **Input Validation**
   - The orchestrator verifies the problem list or reference exists
   - If input is empty or invalid, you're prompted for clarification immediately

2. **Strategic Analysis Phase**
   - **Multi-Perspective Simulation**: Problems analyzed from Security, Performance, Technical Debt, and UX viewpoints
   - **Tree of Thought Grouping**: Issues are grouped by architectural similarity, not file proximity
   - Example: All "data validation" issues form one cluster, all "DB optimization" issues form another
   - Grouping minimizes merge conflicts and maximizes logic reuse

3. **High-Visibility Documentation**
   - A master plan is created in `docs/bulk_fixes/[name]_fix_plan_[TIMESTAMP].md`
   - Contains global task list, assignment matrix, and collaboration space
   - This document is the "Single Source of Truth" for the entire operation

4. **Elite Delegation**
   - Multiple `code-fixer` agents are invoked in parallel
   - Each receives a precise cluster of related problems
   - Each must follow the `software-developer` skill
   - Each must research official docs via Context7
   - Each must document progress in the shared tracking document

5. **Supervision and Validation**
   - **Chain of Verification**: The orchestrator monitors the tracking document for vague updates
   - **Final Validation**: The `approach-reviewer` examines the entire change set
   - **Refinement Loop**: If validation fails, code-fixers are reassigned to address issues
   - **Closure**: Only after "ACCEPT" from the reviewer is completion confirmed

#### What You Get

- A strategic execution plan that groups related problems intelligently
- Parallel execution by multiple specialist agents
- Real-time progress tracking in a centralized document
- Holistic validation of the entire change set
- Confidence that all fixes are integrated and consistent

#### Why This Beats a Simple Prompt

A "fix these issues" prompt gives you sequential fixes that might conflict. This workflow gives you strategic grouping, parallel execution, centralized tracking, and holistic validation. It transforms a laundry list into a coordinated architectural improvement effort.

---

## The Agent Ecosystem

### Investigator Agents (Analysis Specialists)

| Agent | Specialty |
|-------|-----------|
| `bugs-investigator` | Logic errors, race conditions, runtime issues |
| `code-review-investigator` | Clean Code principles, readability |
| `hard-review-investigator` | SOLID patterns, design principles |
| `owasp-investigator` | Security vulnerabilities (OWASP Top 10) |
| `architecture-investigator` | Structural integrity, patterns, consistency |
| `technical-researcher` | Official documentation lookup, version verification |
| `learning-investigator` | Knowledge management and documentation |

### Implementation Agents

| Agent | Role |
|-------|-----|
| `code-fixer` | Executes code changes following strict standards |
| `approach-reviewer` | Quality gatekeeper—validates and can reject changes |

### Orchestrator Agents

Orchestrators manage workflows, coordinate parallel execution, consolidate findings, and ensure quality through iterative validation loops.

---

## The Skill System

**`software-developer` skill**: Enforced across all code modifications

Key principles:
- **Strict Contracts**: No `Any` types—use explicit schemas
- **Boundary Validation**: Validate once when receiving external data
- **Errors as State**: Return structured state objects, don't just log
- **Self-Documenting Code**: Names reveal intent; obvious comments are avoided
- **No Nesting**: Functions at module scope only
- **Guard Clauses**: Reduce nesting through early returns
- **Named Booleans**: Complex conditions get descriptive names
- **No Magic Numbers**: Constants with semantic meaning

This skill ensures consistency across all agents and maintains codebase health.

---

## Installation

1. Add the marketplace:
   ```bash
   /plugin marketplace add https://github.com/YOUR_USERNAME/YOUR_REPO
   ```

2. Install the plugin:
   ```bash
   /plugin install advance-dev-agents@advance-dev-agents-marketplace
   ```

## Dependencies

This plugin integrates with Context7 MCP server for real-time documentation retrieval.

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

**Advance Dev Agents** transforms AI-assisted development from a prompt-response cycle into a disciplined engineering process with peer review, validation loops, and organizational learning.

---

*Developed by Bryan Duarte — [LinkedIn](https://www.linkedin.com/in/bryanduarte/) — [GitHub](https://github.com/BryanCaceres)*
