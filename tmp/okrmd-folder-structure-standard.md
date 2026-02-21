# OKRMD Folder Structure Standard

**OKRMD Standard v0.1** · **Reference Document**

> This document defines the canonical folder structure for an OKRMD project.
> The `.okrmd/` directory lives at the root of your repository (or standalone if not using Git).
> Every folder and file has a specific purpose. The structure itself encodes the hierarchy — navigating the filesystem is navigating the project.

---

## Root Structure

```
.okrmd/
├── config.md                     # Project configuration (required)
│
├── objectives/                   # Strategic goals
├── key-results/                  # Measurable outcomes
├── phases/                       # Delivery gates
├── epics/                        # Large work areas (folders containing stories)
├── prds/                         # Product Requirements Documents
├── cycles/                       # Sprint/iteration timeboxes
├── backlog/                      # Orphan/unplanned work items
├── pulses/                       # Daily focus session logs
├── agents/                       # AI agent profiles
├── team/                         # Human team member profiles
├── retros/                       # Retrospective documents
└── templates/                    # File templates for all entity types
```

---

## Directory Specifications

### `.okrmd/` (Root)

The root directory contains only `config.md` and subdirectories. No other files should live at the root level.

| Contents | Description |
|----------|-------------|
| `config.md` | **Required.** Project configuration, defaults, team roster, conventions. |

---

### `objectives/`

Flat directory. One file per objective.

```
objectives/
├── O1-grow-revenue.md
├── O2-improve-platform.md
└── O3-expand-team.md
```

| Rule | Detail |
|------|--------|
| File pattern | `O{n}-{slug}.md` |
| Nesting | None — objectives are flat |
| Ordering | By objective number (`O1`, `O2`, `O3`) |
| Archive | Move achieved/abandoned objectives to `objectives/archive/` at end of cycle |

---

### `key-results/`

Flat directory. One file per key result.

```
key-results/
├── KR-1.1-increase-mrr-30pct.md
├── KR-1.2-reduce-churn.md
├── KR-2.1-reduce-latency.md
└── archive/
    └── KR-1.1-increase-mrr-30pct.md
```

| Rule | Detail |
|------|--------|
| File pattern | `KR-{obj}.{n}-{slug}.md` |
| Nesting | None — key results are flat |
| Ordering | By parent objective, then sequence (`KR-1.1`, `KR-1.2`, `KR-2.1`) |
| Archive | Move completed KRs to `key-results/archive/` at end of quarter |

---

### `phases/`

Flat directory. One file per phase.

```
phases/
├── P1-mvp.md
├── P2-advanced-features.md
├── P3-analytics.md
└── archive/
    └── P1-mvp.md
```

| Rule | Detail |
|------|--------|
| File pattern | `P{n}-{slug}.md` |
| Nesting | None — phases are flat |
| Ordering | By sequence number (`P1`, `P2`, `P3`) |
| Archive | Move shipped/cancelled phases to `phases/archive/` |

---

### `epics/`

**Nested directory. Each epic is a folder containing its `_epic.md` definition and all story files.**

This is the most important structural convention in OKRMD. Epics are folders, not files. Stories live inside their parent epic's folder.

```
epics/
├── E1-auth-system/
│   ├── _epic.md                  # Epic definition (required)
│   ├── S1.1-user-login.md
│   ├── S1.2-oauth-integration.md
│   └── S1.3-password-reset.md
├── E2-alert-system/
│   ├── _epic.md
│   ├── S2.1-alert-backend.md
│   ├── S2.2-alert-ui.md
│   └── S2.10-alert-mobile.md
├── E3-dashboard/
│   ├── _epic.md
│   ├── S3.1-overview-widgets.md
│   └── S3.2-chart-components.md
└── archive/
    └── E0-prototype/
        ├── _epic.md
        └── S0.1-proof-of-concept.md
```

| Rule | Detail |
|------|--------|
| Folder pattern | `E{n}-{slug}/` |
| Epic file | Always `_epic.md` (underscore prefix sorts it first) |
| Story file pattern | `S{epic}.{n}-{slug}.md` inside the epic folder |
| Nesting | Exactly one level — stories inside epics. No sub-epics. |
| Ordering | Stories ordered by sequence number within the epic |
| Archive | Move completed/cancelled epic folders to `epics/archive/` |
| Empty epics | An epic folder must always contain `_epic.md`. Stories may not exist yet. |

**Why folders, not flat files?**
- An agent assigned a story can `ls ..` to see sibling stories and read `_epic.md` for context
- File counts stay manageable — 50 stories across 8 epics vs. 50 stories in one folder
- Git permissions, branch protections, and CODEOWNERS can be set per epic folder
- Natural grouping matches how humans think about related work

---

### `prds/`

Flat directory. One file per PRD.

```
prds/
├── PRD-iot-dashboard.md
├── PRD-mobile-app.md
└── archive/
    └── PRD-prototype-v1.md
```

| Rule | Detail |
|------|--------|
| File pattern | `PRD-{slug}.md` |
| Nesting | None — PRDs are flat |
| Archive | Move superseded PRDs to `prds/archive/` |

---

### `cycles/`

**Nested directory. Each cycle is a folder containing its `_cycle.md` definition.**

```
cycles/
├── C05/
│   └── _cycle.md
├── C06/
│   └── _cycle.md
└── archive/
    ├── C01/
    │   └── _cycle.md
    ├── C02/
    │   └── _cycle.md
    ├── C03/
    │   └── _cycle.md
    └── C04/
        └── _cycle.md
```

| Rule | Detail |
|------|--------|
| Folder pattern | `C{nn}/` (zero-padded) |
| Cycle file | Always `_cycle.md` |
| Nesting | One level — only `_cycle.md` inside each cycle folder |
| Stories live in epics | Stories are NOT duplicated into cycle folders. The cycle's `_cycle.md` references stories by ID. |
| Archive | Move closed cycles to `cycles/archive/` |
| Active cycles | Typically 1 active cycle at a time. During transition, 1 in `review` and 1 in `planning`. |

**Why don't stories live in cycle folders?**
A story belongs to an epic permanently but is assigned to a cycle temporarily. If stories moved into cycle folders, you'd lose the epic grouping. Instead, the cycle file references stories by `[[S{e}.{n}]]` links, and each story's metadata has a `cycle: C05` field.

---

### `backlog/`

Flat directory. One file per backlog item.

```
backlog/
├── BUG-042-login-crash.md
├── INC-007-server-down.md
├── ADH-015-client-request.md
├── TDB-003-refactor-auth.md
├── FRQ-021-export-feature.md
├── SPK-008-evaluate-redis.md
└── archive/
    ├── BUG-039-signup-error.md
    └── INC-005-dns-outage.md
```

| Rule | Detail |
|------|--------|
| File pattern | `{PREFIX}-{nnn}-{slug}.md` |
| Prefixes | Must be registered in `config.md` |
| Nesting | None — backlog items are flat |
| Numbering | Sequential per prefix (`BUG-001`, `BUG-002`, ...) or global (`001`, `002`, ...) — choose one in `config.md` |
| Promotion | When a backlog item is promoted to a story, create the story in its epic folder and update the backlog item's `promoted_to` field |
| Archive | Move completed/wont-fix items to `backlog/archive/` |

---

### `pulses/`

Flat directory. One file per worker per day.

```
pulses/
├── 2026-02-16-alice.md
├── 2026-02-16-bob.md
├── 2026-02-16-claude-code.md
├── 2026-02-17-alice.md
├── 2026-02-17-claude-code.md
└── archive/
    └── 2026-01/
        ├── 2026-01-06-alice.md
        ├── 2026-01-06-claude-code.md
        └── ...
```

| Rule | Detail |
|------|--------|
| File pattern | `{YYYY-MM-DD}-{worker}.md` |
| Nesting | None at top level. Archive by month. |
| One file per worker per day | Alice and Claude Code each have their own file for the same day |
| Archive | Move past months to `pulses/archive/{YYYY-MM}/` |
| Retention | Recommended: keep current month + 2 previous months active. Archive the rest. |

---

### `agents/`

Flat directory. One file per agent.

```
agents/
├── claude-code.md
├── claude-code-docs.md
├── devin.md
└── custom-reviewer.md
```

| Rule | Detail |
|------|--------|
| File pattern | `{agent-name}.md` |
| Nesting | None |
| One profile per configuration | Same model in different configs = separate profiles |

---

### `team/`

Flat directory. One file per human team member.

```
team/
├── alice.md
├── bob.md
└── carol.md
```

| Rule | Detail |
|------|--------|
| File pattern | `{handle}.md` |
| Nesting | None |
| Ownership | Each team member maintains their own profile |
| Departed members | Move to `team/archive/` when someone leaves |

---

### `retros/`

Flat directory. One file per retrospective.

```
retros/
├── C05-retro.md
├── C06-retro.md
├── Q1-2026-retro.md
├── P1-mvp-retro.md
└── archive/
    ├── C01-retro.md
    └── C02-retro.md
```

| Rule | Detail |
|------|--------|
| File pattern | `{scope}-retro.md` |
| Nesting | None |
| Archive | Move retros older than 2 quarters to `retros/archive/` |

---

### `templates/`

Flat directory. Contains one template file for each OKRMD entity type. These are the canonical templates — copy them when creating new entities.

```
templates/
├── objective.md
├── key-result.md
├── phase.md
├── prd.md
├── epic.md
├── story.md
├── backlog-item.md
├── cycle.md
├── agent.md
├── team-member.md
├── pulse-log.md
└── retro.md
```

| Rule | Detail |
|------|--------|
| Read-only intent | Templates should not be modified during normal work. Update them deliberately when the team agrees to change the standard. |
| Versioned with project | Templates are committed to Git and versioned with the project |
| Customizable | Teams may add fields to templates. Removing standard fields is discouraged. |

---

## Archive Convention

Every directory that accumulates files over time has an `archive/` subdirectory. Archiving keeps the active working directories clean and navigable.

| Directory | Archive trigger | Archive location |
|-----------|----------------|-----------------|
| `objectives/` | Achieved, missed, or abandoned | `objectives/archive/` |
| `key-results/` | Quarter ended | `key-results/archive/` |
| `phases/` | Shipped or cancelled | `phases/archive/` |
| `epics/` | All stories done or epic cancelled | `epics/archive/` |
| `prds/` | Superseded | `prds/archive/` |
| `cycles/` | Closed | `cycles/archive/` |
| `backlog/` | Done or wont-fix | `backlog/archive/` |
| `pulses/` | Past months | `pulses/archive/{YYYY-MM}/` |
| `team/` | Departed | `team/archive/` |
| `retros/` | Older than 2 quarters | `retros/archive/` |

> **Never delete files.** Archive them. The history has value — for retrospectives, for audits, for understanding how the project evolved.

---

## Minimal Setup

For small projects, you don't need every directory. Start with what you need:

### Solo / Tiny Project

```
.okrmd/
├── config.md
├── epics/
│   └── E1-my-project/
│       ├── _epic.md
│       └── S1.1-first-feature.md
└── backlog/
```

### Small Team

```
.okrmd/
├── config.md
├── epics/
├── cycles/
├── backlog/
├── pulses/
├── agents/
├── team/
└── templates/
```

### Full Setup

Use the complete structure from the Root Structure section above.

> **Progressive adoption**: Start minimal. Add directories as they become needed. The structure scales up without reorganization.

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 0.1 | 2026-02-19 | Initial folder structure standard |
