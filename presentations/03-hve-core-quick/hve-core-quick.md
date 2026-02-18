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

# HVE Core (Quick)

An enterprise-ready prompt engineering framework for GitHub Copilot

---

## What is HVE Core?

An **open-source framework** from Microsoft ISE with **18 agents**, **17+ instructions**, and **18 prompts** that structure how AI works on complex tasks.

> AI can't tell the difference between **investigating** and **implementing**. HVE Core solves this by **constraining** what AI can do at each step.

---

## Getting Started: VS Code Extension

The fastest way to start — zero configuration, works everywhere:

1. Open VS Code Extensions view (`Ctrl+Shift+X`)
2. Search for **"HVE Core"**
3. Click **Install** — that's it! ✅

- ✅ Zero configuration required
- ✅ Automatic updates via VS Code
- ✅ Works in local VS Code, devcontainers, and Codespaces

---

## Alternative Installation Methods

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

## RPI: Research → Plan → Implement → Review

| Phase | Agent | What It Does |
|-------|-------|-------------|
| 🔬 **Research** | `task-researcher` | Investigates codebase, APIs, docs |
| 📋 **Plan** | `task-planner` | Creates actionable steps with line refs |
| ⚡ **Implement** | `task-implementor` | Executes plan task-by-task |
| ✅ **Review** | `task-reviewer` | Validates against specs, runs checks |

> When AI knows it **cannot implement** during research, it stops optimizing for "plausible code" and starts optimizing for **"verified truth."**

---

## `rpi-agent` vs. `task-*` Agents

**Strict RPI** — four separate agents with `/clear` between each phase:

```text
task-researcher → /clear → task-planner → /clear → task-implementor → /clear → task-reviewer
```

**`rpi-agent`** — single agent that orchestrates all phases automatically

| Factor | Strict RPI | `rpi-agent` |
|--------|-----------|-------------|
| **Best for** | Complex, unfamiliar, team | Simple, familiar, solo |
| **Audit trail** | Complete artifacts | Summary only |

---

## 🔴 The Critical Rule: `/clear`

**Always use `/clear` between strict RPI phases.**

- Each agent has **different instructions** — accumulated context confuses roles
- Research findings live in **files**, not chat history
- Without `/clear`, the planner writes code and the implementor researches

**Not sure which workflow?** Start with `rpi-agent` — it escalates to strict RPI automatically if complexity emerges.

---

## How HVE Core Tracks Progress

Agents create structured artifacts in `.copilot-tracking/`:

```text
.copilot-tracking/
├── research/    # Evidence and citations
├── plans/       # Phased checklists with line refs
├── changes/     # Files added / modified / removed
└── reviews/     # Validation findings and severity counts
```

Each phase's output feeds the next. Review drives iteration back to earlier phases when gaps are found.

> Add `.copilot-tracking/` to `.gitignore` — ephemeral workflow artifacts.

---

<!-- _class: lead -->
<!-- _paginate: false -->

# Thank You!

**Get started:** `github.com/microsoft/hve-core`

Questions?
