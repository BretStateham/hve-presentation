---
marp: true
theme: hve
paginate: true
header: 'HVE Core'
footer: 'Hypervelocity Engineering'
---

<!-- _class: lead -->
<!-- _paginate: false -->
<!-- _header: '' -->
<!-- _footer: '' -->

# HVE Core

An enterprise-ready prompt engineering framework for GitHub Copilot

<!-- Presenter note: This deck introduces the microsoft/hve-core repository — what it is, how to install it, the RPI methodology, choosing the right agent workflow, and how it tracks progress behind the scenes. -->

---

<!-- _class: lead -->

# 1. Overview of HVE Core

---

## What is HVE Core?

HVE Core is an **open-source prompt engineering framework** from Microsoft's ISE team that supercharges GitHub Copilot with structured, constraint-based AI workflows.

> Instead of asking AI to "write code," HVE Core teaches AI to **research first, plan second, and implement with evidence**.

It provides ready-to-use **agents**, **instructions**, **prompts**, and **skills** that prevent AI from guessing and push it toward verified, traceable outputs.

<!-- Note: HVE Core lives at github.com/microsoft/hve-core and is MIT licensed. -->

---

## What's Included

| Component        | Count | Purpose                                              |
|------------------|-------|------------------------------------------------------|
| 🤖 **Agents**       | 18    | Specialized AI assistants (research, planning, code) |
| 📏 **Instructions**  | 17+   | Auto-applied coding guidelines via file patterns     |
| 📝 **Prompts**       | 18    | Reusable templates for commits, PRs, reviews         |
| 🛠️ **Skills**        | 1     | Executable utilities with cross-platform scripts     |
| ✅ **Validation**    | CI/CD | JSON schema enforcement for all AI artifacts         |

All components are validated through an enterprise CI/CD pipeline with JSON schema enforcement.

---

## The Core Insight

AI coding assistants are brilliant at simple tasks. But for complex, multi-file features:

- ❌ AI **invents** plausible patterns instead of using existing ones
- ❌ AI **calls APIs that don't exist** with full confidence
- ❌ AI **ignores your codebase conventions** and naming
- ❌ AI **writes first and thinks never**

**The root cause:** AI can't tell the difference between **investigating** and **implementing**.

> HVE Core solves this by **constraining** what AI can do at each step.

---

## Four Artifact Types

| Artifact         | Purpose                                 | Activation              |
|------------------|-----------------------------------------|-------------------------|
| **Instructions** | Passive guidance applied by file pattern | Automatic via `applyTo` |
| **Prompts**      | Task-specific procedures with variables  | Manual via `/` command  |
| **Agents**       | Specialized personas with constraints    | Manual via agent picker |
| **Skills**       | Executable cross-platform utilities      | On demand by Copilot    |

Each type has clear boundaries, preventing runaway behavior through constraint-based design.

---

<!-- _class: lead -->

# 2. Getting Started with the VS Code Extension

---

## Simplest Installation: VS Code Extension

The fastest way to start — zero configuration, works everywhere:

1. Open VS Code Extensions view (`Ctrl+Shift+X`)
2. Search for **"HVE Core"**
3. Click **Install** — that's it! ✅

- ✅ Zero configuration required
- ✅ Automatic updates via VS Code
- ✅ Works in local VS Code, devcontainers, and Codespaces

<!-- Note: This is the recommended method for most users who don't need to customize components. -->

---

## Verify Your Installation

After installing, confirm everything works:

1. Open GitHub Copilot Chat (`Ctrl+Alt+I`)
2. Click the **agent picker dropdown**
3. Verify HVE Core agents appear (e.g. `task-researcher`, `task-planner`, `rpi-agent`)
4. Select any agent and submit a test prompt

> **Prerequisites:** GitHub Copilot subscription + VS Code with Copilot extension

---

<!-- _class: lead -->

# 3. Alternative Installation Methods

---

## Installation Decision Tree

```text
┌──────────────────────────────────────────────────────────┐
│                                                          │
│  Want the simplest setup?                                │
│  └─ Yes ────────────────────────► VS Code Extension *    │
│                                                          │
│  Need to customize HVE Core?                             │
│  ├─ Local VS Code only ─────────► Peer Directory Clone   │
│  ├─ Local devcontainer ─────────► Git-Ignored Folder     │
│  ├─ Codespaces only ────────────► GitHub Codespaces      │
│  └─ Both local + Codespaces ────► Multi-Root Workspace   │
│                                                          │
│  Working in a team?                                      │
│  └─ Need version control ───────► Submodule              │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

---

## Methods Comparison

| Method                    | Best For                 | Customizable | Complexity |
|---------------------------|--------------------------|:------------:|:----------:|
| **VS Code Extension** ⭐  | Most users               | ❌           | Minimal    |
| **Copilot CLI Plugins**   | Terminal workflows       | ❌           | Low        |
| **Multi-Root Workspace**  | Cross-environment        | ✅           | Low        |
| **Submodule**             | Teams, version control   | ✅           | Medium     |
| **Peer Directory Clone**  | Solo, local VS Code      | ✅           | Low        |
| **Git-Ignored Folder**    | Devcontainer, ephemeral  | ✅           | Low        |
| **GitHub Codespaces**     | Cloud-only development   | ✅           | Medium     |

---

## Key Trade-Offs

| Method | Pro | Con |
|--------|-----|-----|
| **VS Code Extension** ⭐ | Install and forget — auto updates, zero config | Cannot customize agents or prompts |
| **Submodule** | Team pins to same version; tracked in git | Requires submodule knowledge |
| **CLI Plugins** | Terminal-first; works outside VS Code | Separate from VS Code agent picker |
| **Agent Installer** | Guided setup — 3 questions, done | Requires `hve-core-installer` agent |

---

<!-- _class: lead -->

# 4. The What and Why of RPI

---

## What is RPI?

**RPI = Research → Plan → Implement → Review**

A structured workflow that transforms complex tasks into validated code through four distinct phases:

```text
Uncertainty → Knowledge → Strategy → Working Code → Validated Code
```

Each phase is handled by a **specialized agent** with constraints that prevent it from doing the wrong work at the wrong time.

<!-- Note: The "Review" phase was added to close the feedback loop. Some docs still reference "RPI" as the three core phases with review as the validation step. -->

---

## Why Does RPI Work?

The counterintuitive insight:

> **When AI knows it cannot implement during research, it stops optimizing for "plausible code" and starts optimizing for "verified truth."**

The constraint changes the goal.

| Without RPI | With RPI |
|-------------|----------|
| AI invents plausible patterns | AI uses **verified existing** patterns |
| "The AI wrote it this way" | "Research cites `variables.tf` line 47" |
| Tribal knowledge in your head | Research docs **anyone** can follow |
| Frequent rework after wrong assumptions | Rare rework — assumptions verified first |

---

## The Four Phases

| Phase | Agent | What It Does | Output |
|-------|-------|-------------|--------|
| 🔬 **Research** | `task-researcher` | Investigates codebase, APIs, docs | `*-research.md` |
| 📋 **Plan** | `task-planner` | Creates actionable steps with line refs | `*-plan.md` + `*-details.md` |
| ⚡ **Implement** | `task-implementor` | Executes plan task-by-task | Code + `*-changes.md` |
| ✅ **Review** | `task-reviewer` | Validates against specs, runs checks | `*-review.md` |

Each phase starts fresh. Research findings are preserved in **files**, not chat history.

---

## The Quality Difference

| Aspect | Traditional AI | RPI Approach |
|--------|---------------|-------------|
| **Patterns** | Invents plausible ones | Uses verified existing ones |
| **Traceability** | "The AI wrote it" | "Research cites lines 47-52" |
| **Knowledge** | Tribal, in your head | Documented, anyone can follow |
| **Rework** | Frequent | Rare — assumptions verified first |

> **Stop asking AI:** "Write this code."
> **Start asking:** "Help me research, plan, then implement with evidence."

---

<!-- _class: lead -->

# 5. `rpi-agent` vs. `task-*` Agents

---

## Two Workflow Options

### Strict RPI (the `task-*` agents)
Four separate agents, each invoked manually with `/clear` between phases:

```text
task-researcher → /clear → task-planner → /clear → task-implementor → /clear → task-reviewer
```

### Autonomous RPI (the `rpi-agent`)
A single agent that orchestrates all four phases via subagent delegation:

```text
rpi-agent (handles Research → Plan → Implement → Review automatically)
```

---

## When to Use Which

| Factor | Strict RPI (`task-*`) | `rpi-agent` |
|--------|----------------------|-------------|
| **Research depth** | Deep, verified, cited | Moderate, inline |
| **Context contamination** | Eliminated via `/clear` | Possible |
| **Audit trail** | Complete artifacts | Summary only |
| **Best for** | Complex, unfamiliar, team | Simple, familiar, solo |

- 🔬 **New framework, external APIs, compliance?** → Strict RPI
- ✅ **Clear scope, familiar codebase?** → `rpi-agent`
- 🔀 **Not sure?** → Start with `rpi-agent`, escalate if needed

---

## 🔴 The Critical Rule: `/clear`

**Always use `/clear` or start a new chat between strict RPI phases.**

- Each agent has **different instructions and behaviors**
- Accumulated context causes the AI to **confuse roles**
- Research findings live in **files**, not chat history

```text
/task-research topic → /clear → /task-plan → /clear → /task-implement → /clear → /task-review
```

> Without `/clear`, the planner might write code and the implementor might start researching. The constraints break down.

---

## Escalation Path

You don't have to decide upfront:

```text
Start with rpi-agent (speed)
         │
         ├─ Task is simple? ──► rpi-agent handles it end-to-end ✅
         │
         └─ Hidden complexity? ──► rpi-agent escalates to task-researcher
                                    │
                                    └─► Continue with strict RPI phases
```

The **hybrid approach** gives you speed for simple tasks and depth when the task reveals hidden complexity.

---

<!-- _class: lead -->

# 6. Behind the Scenes: How HVE Core Tracks Progress

---

## The `.copilot-tracking/` Directory

HVE Core agents create structured tracking artifacts in `.copilot-tracking/`:

```text
.copilot-tracking/
├── research/       # Research documents with evidence
├── plans/          # Implementation plans with checkboxes
│   └── logs/       # Planning logs & discrepancies
├── details/        # Per-phase step details with line ranges
├── changes/        # Change logs tracking what was modified
└── reviews/        # Review findings & validation results
    └── rpi/        # Per-phase validation reports
```

All artifacts are **date-organized** (`YYYY-MM-DD/`) so workflows don't collide.

> Add `.copilot-tracking/` to your `.gitignore` — these are ephemeral workflow artifacts.

---

## Artifact Flow

Each RPI phase produces artifacts that feed the next:

```text
  task-researcher          task-planner          task-implementor       task-reviewer
       │                        │                       │                      │
       ▼                        ▼                       ▼                      ▼
  research.md ──────►  plan.md + details.md ──►  code + changes.md ──►  review.md
       │                        │                       │                      │
  Evidence &            Checkboxes &            File diffs &           Findings &
  citations             line references         deviation notes        validation
```

Artifacts are **date-organized** (`YYYY-MM-DD/`) so multiple workflows don't collide.

---

## What Gets Tracked

| Artifact | Contains | Created By |
|----------|----------|------------|
| **Research doc** | Scope, evidence, evaluated alternatives | `task-researcher` |
| **Plan** | Phased checklist, success criteria | `task-planner` |
| **Details** | Per-step file ops, line ranges | `task-planner` |
| **Planning log** | Discrepancies, alternatives, follow-ons | `task-planner` |
| **Changes log** | Files added / modified / removed | `task-implementor` |
| **Review log** | Severity findings, validation outputs | `task-reviewer` |

---

## The Review Feedback Loop

The review phase doesn't just validate — it drives iteration:

| Review Status | Action | Target |
|---------------|--------|--------|
| ✅ **Complete** | No critical/major findings — ready to commit | Done |
| 🔄 **Iterate** | Critical/major findings need fixes | Back to Implement |
| ⬆️ **Escalate** | Research or plan gaps discovered | Back to Research or Plan |

This ensures that every implementation is **validated against the original research and plan**, not just "does it compile."

---

## Why This Matters

Traditional AI: *"It generated code. Ship it."* 🤞

HVE Core: *"Research verified the pattern. Plan defined the steps. Review confirmed it matches specs."* ✅

**The artifacts create:**
- 📋 **Accountability** — every decision is traceable
- 🤝 **Team handoffs** — anyone can pick up where you left off
- 📚 **Institutional memory** — patterns documented once, referenced forever

---

<!-- _class: lead -->
<!-- _paginate: false -->

# Thank You!

**Get started:** `github.com/microsoft/hve-core`

Questions?
