# OKRMD Quick Start Guide

**OKRMD Standard v0.1** · **Reference Document**

> Get OKRMD running in 15 minutes. This guide walks you through the minimum viable setup.
> You can always add more structure later — OKRMD scales up without reorganization.

---

## Prerequisites

- A text editor (VS Code, vim, Obsidian, Cursor — anything that edits `.md` files)
- Git (recommended but not required)
- 15 minutes

---

## Step 1: Create the Folder Structure (2 minutes)

```bash
mkdir -p .okrmd/{epics,backlog,pulses,cycles,agents,team,templates}
```

---

## Step 2: Create `config.md` (5 minutes)

Create `.okrmd/config.md` with the minimum required fields:

```markdown
# OKRMD Project Configuration

## Project

| Field | Value |
|-------|-------|
| Project name | my-project |
| OKRMD version | 0.1 |
| Created | 2026-02-16 |

## Cycle Settings

| Field | Value |
|-------|-------|
| Cycle duration | 14 |
| Estimation method | pulses |

## Pulse Settings

| Field | Value |
|-------|-------|
| Standard Pulse | 25 min |
| Short rest | 5 min |
| Long rest (after 4 pulses) | 15 min |

## Autonomy Levels

| Field | Value |
|-------|-------|
| Default autonomy | A3 |
| Max agent autonomy | A2 |

## Team

### Humans

| Name | Role |
|------|------|
| your-name | Lead |

### Agents

| Name | Model |
|------|-------|
| claude-code | claude-sonnet-4 |
```

> That's it. Add more sections from the full `config.md` template when you need them.

---

## Step 3: Create Your First Epic and Story (5 minutes)

### Create the epic folder and definition:

```bash
mkdir -p .okrmd/epics/E1-my-first-epic
```

Create `.okrmd/epics/E1-my-first-epic/_epic.md`:

```markdown
# Epic: My First Epic

| Field | Value |
|-------|-------|
| ID | E1 |
| Title | My First Epic |
| Status | in-progress |
| Owner | your-name |

## Description

What this epic delivers. 2–3 sentences.

## Stories

| Story | Title | Assignee | Status |
|-------|-------|----------|--------|
| [[S1.1]] | First Story | your-name | draft |
| [[S1.2]] | Second Story | claude-code | draft |
```

### Create your first story:

Create `.okrmd/epics/E1-my-first-epic/S1.1-first-story.md`:

```markdown
# Story: First Story

| Field | Value |
|-------|-------|
| ID | S1.1 |
| Title | First Story |
| Epic | [[E1]] |
| Status | ready |
| Assignee | your-name |
| Autonomy | A5 |

## Story

As a user, I need [capability] so that [benefit].

## Acceptance Criteria

- [ ] First criterion
- [ ] Second criterion
- [ ] Third criterion

## Tasks

- [ ] First task
- [ ] Second task
- [ ] Third task
```

> That's a working story. You can add Dev Notes, Dependencies, File List, and all other sections from the full Story template as needed.

---

## Step 4: Start Your First Pulse (3 minutes)

Create `.okrmd/pulses/2026-02-16-your-name.md`:

```markdown
# Pulse Log — your-name — 2026-02-16

| Metric | Value |
|--------|-------|
| Pulses completed | 0 |
| Total focus time | 0 min |

## Pulse 1 (09:00–09:25) — 25 min
- **Task**: [[S1.1]] — First task
- **Status**: _fill in after pulse_
- **Interruptions**: 0
```

Now set a 25-minute timer and start working. When the timer ends, fill in the status, take a 5-minute rest, and log the next Pulse.

---

## You're Running OKRMD

That's all you need to start. Your structure looks like this:

```
.okrmd/
├── config.md
├── epics/
│   └── E1-my-first-epic/
│       ├── _epic.md
│       └── S1.1-first-story.md
└── pulses/
    └── 2026-02-16-your-name.md
```

---

## What to Add Next

Add structure as you need it — not before. Here's a progressive adoption path:

### Week 1: Add an Agent

Create `.okrmd/agents/claude-code.md` with the agent's capabilities and assign it a story at A3 autonomy. Review its output. Log in pulse files.

### Week 2: Add Cycles

Create `.okrmd/cycles/C01/_cycle.md` to formalize your sprint. Commit stories to the cycle. Do a cycle review at the end.

### Week 3: Add Backlog

Create `.okrmd/backlog/BUG-001-first-bug.md` for your first unplanned item. Run a quick triage.

### Week 4: Add Retrospectives

Create `.okrmd/retros/C01-retro.md` after your first cycle. Reflect on human-agent collaboration.

### Month 2: Add OKRs and Phases

When you have enough work to need strategic direction, create `objectives/` and `key-results/` directories. Add `phases/` when you need delivery gates.

### Month 3: Full Setup

By now you'll know which parts of OKRMD your team uses and which you don't need. Customize accordingly.

---

## Quick Reference: Common Actions

| I want to... | Create this file |
|-------------|-----------------|
| Set a strategic goal | `.okrmd/objectives/O1-{slug}.md` |
| Define a measurable outcome | `.okrmd/key-results/KR-1.1-{slug}.md` |
| Plan a delivery phase | `.okrmd/phases/P1-{slug}.md` |
| Start a new work area | `.okrmd/epics/E{n}-{slug}/_epic.md` |
| Define a deliverable | `.okrmd/epics/E{n}-{slug}/S{e}.{n}-{slug}.md` |
| Track a bug or urgent item | `.okrmd/backlog/BUG-{nnn}-{slug}.md` |
| Plan a sprint | `.okrmd/cycles/C{nn}/_cycle.md` |
| Log my daily work | `.okrmd/pulses/{date}-{name}.md` |
| Add an AI agent to the team | `.okrmd/agents/{name}.md` |
| Add a human to the team | `.okrmd/team/{name}.md` |
| Reflect on what we learned | `.okrmd/retros/{scope}-retro.md` |
| Write product requirements | `.okrmd/prds/PRD-{slug}.md` |

---

## Quick Reference: Autonomy Levels

| Level | Who drives | When to use |
|-------|-----------|-------------|
| **A1** | Agent (full auto) | Routine automation, strong test coverage |
| **A2** | Agent (human spot-checks) | Familiar tasks, agent has track record |
| **A3** | Agent + Human (guided) | **Default.** Most knowledge work. |
| **A4** | Human (agent assists) | Complex decisions, novel problems |
| **A5** | Human (no agent) | Strategy, sensitive topics, pure human work |

---

## Quick Reference: Status Values

| Stories | Backlog | Cycles |
|---------|---------|--------|
| `draft` | `triage` | `planning` |
| `ready` | `ready` | `active` |
| `in-progress` | `in-progress` | `review` |
| `review` | `review` | `closed` |
| `done` | `done` | |
| `blocked` | `blocked` | |
| | `wont-fix` | |

---

## Need More?

| Document | When you need it |
|----------|-----------------|
| Full `config.md` template | When you need team roster, branching conventions, all prefixes |
| Folder Structure Standard | When you're not sure where a file goes |
| Naming Convention Standard | When you're not sure what to name a file |
| Autonomy Levels Reference | When you're debating A2 vs A3 for a specific task |
| Workflows Guide | When you want the full ceremony playbook |
| Manifesto | When you want to remember why you're doing this |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 0.1 | 2026-02-19 | Initial quick start guide |
