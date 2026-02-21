# OKRMD Project Configuration

**OKRMD Standard v0.1** · **config.md**

> This file is the single source of truth for your project's OKRMD settings.
> Place it at `.okrmd/config.md` in your repository root.
> Both humans and AI agents read this file to understand project rules, team composition, and conventions.

---

## Project

| Field | Value | Instructions |
|-------|-------|--------------|
| Project name | `___` | Short identifier, kebab-case (e.g. `iot-dashboard`) |
| Description | `___` | One-line project description |
| Repository | `___` | Primary repo URL |
| OKRMD version | `0.1` | Version of the OKRMD standard this project follows |
| Created | `YYYY-MM-DD` | Date this config was initialized |
| Updated | `YYYY-MM-DD` | Date of last config change |

---

## OKR Settings

| Field | Value | Instructions |
|-------|-------|--------------|
| OKR cadence | `quarterly` | `quarterly` or `annual` — how often objectives are set |
| Review cadence | `weekly` | How often KR scores are reviewed (`weekly`, `biweekly`, `monthly`) |
| Scoring scale | `0.0–1.0` | Default: 0.0–1.0 (see scoring guide below) |
| Default OKR type | `aspirational` | `aspirational` (target 0.7) or `committed` (target 1.0) |
| Max objectives per quarter | `3` | Recommended: 3–5 |
| Max key results per objective | `5` | Recommended: 2–5 |

### OKR Scoring Guide

| Score | Meaning |
|-------|---------|
| 0.0–0.3 | Failed to make meaningful progress |
| 0.4–0.6 | Made progress but fell short |
| 0.7–0.9 | Delivered — sweet spot for aspirational OKRs |
| 1.0 | Fully achieved — expected for committed OKRs |

---

## Cycle (Sprint) Settings

| Field | Value | Instructions |
|-------|-------|--------------|
| Cycle duration | `14` | Duration in days (common: `7`, `14`, `21`) |
| Cycle naming | `C{nn}` | Prefix + zero-padded number (e.g. `C01`, `C12`) |
| Planning day | `___` | Day of week cycle planning occurs (e.g. `Monday`) |
| Review day | `___` | Day of week cycle review occurs (e.g. `Friday`) |
| Estimation method | `pulses` | `pulses`, `story_points`, or `hours` |
| Velocity tracking | `yes` | Track completed estimates per cycle (`yes` / `no`) |

---

## Pulse Settings

### Human Pulses

| Field | Value | Instructions |
|-------|-------|--------------|
| Standard Pulse | `25 min` | Default focused work interval |
| Deep Pulse | `50 min` | Extended focus for complex work |
| Short rest | `5 min` | Rest after each standard Pulse |
| Long rest | `15 min` | Rest after every `4` Pulses |
| Long rest frequency | `4` | Number of Pulses before a long rest |

### Agent Pulses

| Field | Value | Instructions |
|-------|-------|--------------|
| Default token budget | `___` | Default tokens per agent Pulse (e.g. `100000`) |
| Max token budget | `___` | Hard ceiling per single Pulse |
| Checkpoint rule | `always` | `always` — agent must checkpoint after each Pulse |
| Context utilization warning | `80%` | Warn/checkpoint when context window reaches this % |

---

## Autonomy Levels (A1–A5)

> **How autonomy works across levels**: This section defines **project-wide defaults and guardrails**. Each individual story, task, or backlog item sets its own autonomy level in its file. The `default autonomy` below is applied when a work item doesn't specify one. The `max agent autonomy` is the ceiling — agents cannot operate above this level without an explicit override and documented justification.

| Level | Name | Who Drives | Review Required |
|-------|------|-----------|-----------------|
| A1 | Full Auto | Agent | Automated checks only |
| A2 | Supervised Auto | Agent | Spot-check by human |
| A3 | Guided Auto | Agent + Human | Required review |
| A4 | Co-Pilot | Human | Self-review |
| A5 | Human-Led | Human (no agent) | Self-review |

| Field | Value | Instructions |
|-------|-------|--------------|
| Default autonomy | `A3` | Applied when a work item doesn't specify a level |
| Max agent autonomy | `___` | Highest level agents can operate at without explicit override (e.g. `A2`) |
| Override approval | `___` | Who can approve exceeding max autonomy (e.g. `project-lead`, `any-reviewer`) |

---

## Team

### Humans

<!-- Copy this row for each human team member. Profile files go in `.okrmd/team/`. -->

| Name | Role | Profile | Pulses/day capacity | Notes |
|------|------|---------|---------------------|-------|
| `___` | `___` | `[[name]]` | `___` | _e.g. available Mon–Fri_ |
| `___` | `___` | `[[name]]` | `___` | |

### Agents

<!-- Copy this row for each AI agent. Profile files go in `.okrmd/agents/`. -->

| Name | Model | Profile | Default autonomy | Token budget/day | Notes |
|------|-------|---------|-----------------|-----------------|-------|
| `___` | `___` | `[[name]]` | `___` | `___` | _e.g. available 24/7_ |
| `___` | `___` | `[[name]]` | `___` | `___` | |

---

## Git & Branching Conventions

| Field | Value | Instructions |
|-------|-------|--------------|
| Main branch | `main` | Production branch name |
| Branch naming | `{type}/S{epic}.{story}-{slug}` | e.g. `feature/S2.1-alert-backend` |
| Branch types | `feature`, `bugfix`, `hotfix`, `spike` | Allowed branch prefixes |
| PR required | `yes` | All merges require pull request (`yes` / `no`) |
| PR reviewers | `___` | Minimum reviewers required (e.g. `1`) |
| Agent auto-merge | `no` | Can agents merge without human approval? (`yes` / `no`, see autonomy) |
| Commit format | `[{ID}] {message}` | e.g. `[S2.1] Add alert model migration` |

---

## Backlog Item Prefixes

> **How prefixes work**: OKRMD defines a reference catalog of prefixes organized by domain. Projects select the prefixes relevant to their work and add custom ones as needed. Every backlog item filename starts with its prefix: `{PREFIX}-{nnn}-{slug}.md`.

### Core Prefixes (recommended for all projects)

| Prefix | Type | Description |
|--------|------|-------------|
| `ADH` | Ad-hoc | Unplanned request from stakeholder or client |
| `SPK` | Spike | Research or investigation task with timeboxed scope |
| `RIS` | Risk | Identified risk requiring mitigation action |
| `IMP` | Improvement | General process or quality improvement |

### Software & Engineering

| Prefix | Type | Description |
|--------|------|-------------|
| `BUG` | Bug | Defect in existing functionality |
| `INC` | Incident | Production outage or degradation |
| `TDB` | Tech Debt | Refactoring, cleanup, performance improvement |
| `SEC` | Security | Security vulnerability or hardening task |
| `DEP` | Dependency | Dependency update, migration, or deprecation |
| `PER` | Performance | Performance optimization or investigation |

### Infrastructure & Operations

| Prefix | Type | Description |
|--------|------|-------------|
| `SRV` | Server | Server provisioning, maintenance, or migration |
| `NET` | Network | Network configuration, DNS, firewall, CDN |
| `MON` | Monitoring | Monitoring, alerting, observability setup |
| `BAK` | Backup | Backup, disaster recovery, data restoration |
| `CLD` | Cloud | Cloud infrastructure, scaling, cost optimization |

### Marketing & Content

| Prefix | Type | Description |
|--------|------|-------------|
| `CMP` | Campaign | Marketing campaign planning or execution |
| `CNT` | Content | Blog post, article, whitepaper, documentation |
| `SEO` | SEO | Search engine optimization task |
| `SOC` | Social | Social media content or engagement task |
| `BRD` | Brand | Branding, design, visual identity task |
| `EVT` | Event | Event planning, webinar, conference |

### Customer & Support

| Prefix | Type | Description |
|--------|------|-------------|
| `SUP` | Support | Customer support ticket or escalation |
| `FRQ` | Feature Request | Customer or internal feature request |
| `FBK` | Feedback | Customer feedback requiring action |
| `ONB` | Onboarding | Customer onboarding or training task |
| `CHN` | Churn | Churn prevention or retention action |

### Management & Organization

| Prefix | Type | Description |
|--------|------|-------------|
| `HIR` | Hiring | Recruitment, interviewing, onboarding |
| `BDG` | Budget | Budget planning, allocation, or review |
| `MTG` | Meeting | Meeting preparation, follow-up actions |
| `TRN` | Training | Team training, skill development, certification |
| `PRO` | Process | Process definition, documentation, or change |
| `VND` | Vendor | Vendor evaluation, negotiation, management |

### Legal, Regulatory & Compliance

| Prefix | Type | Description |
|--------|------|-------------|
| `AUD` | Audit | Internal or external audit task |
| `POL` | Policy | Policy creation, review, or update |
| `REG` | Regulatory | Regulatory compliance requirement |
| `CTR` | Contract | Contract drafting, review, or renewal |
| `PRI` | Privacy | Data privacy, GDPR, data protection task |
| `LIC` | License | Software licensing, IP, trademark task |

### Strategy & Business

| Prefix | Type | Description |
|--------|------|-------------|
| `STR` | Strategy | Strategic initiative or analysis |
| `PRT` | Partnership | Partnership evaluation or management |
| `M&A` | M&A | Merger, acquisition, or due diligence task |
| `BIZ` | Business Dev | Business development or sales enablement |
| `FIN` | Finance | Financial analysis, reporting, forecasting |

### Custom Prefixes

<!-- Add project-specific or domain-specific prefixes below. -->

| Prefix | Type | Description |
|--------|------|-------------|
| `___` | `___` | `___` |
| `___` | `___` | `___` |

> **Prefix rules**: Prefixes must be 2–4 uppercase letters. Each prefix must be unique within the project. Register all custom prefixes in this table to avoid collisions.

---

## Status Values

### Stories & Backlog Items

| Status | Meaning | Who can set |
|--------|---------|-------------|
| `draft` | Being written, not ready for work | Author |
| `ready` | Fully specified, can be assigned | Author / reviewer |
| `in-progress` | Actively being worked on | Assignee |
| `review` | Work complete, awaiting review | Assignee |
| `done` | Reviewed and accepted | Reviewer |
| `blocked` | Cannot proceed — blocker documented | Assignee |

### Objectives & Key Results

| Status | Meaning |
|--------|---------|
| `active` | Currently being pursued |
| `achieved` | Target met |
| `missed` | Quarter ended, target not met |
| `abandoned` | Intentionally dropped |

### Phases

| Status | Meaning |
|--------|---------|
| `planned` | Defined but not yet started |
| `in-progress` | Epics in this phase are being worked |
| `shipped` | Gate criteria met, phase delivered |
| `cancelled` | Phase dropped from plan |

### Cycles

| Status | Meaning |
|--------|---------|
| `planning` | Cycle being planned, stories being assigned |
| `active` | Cycle in progress |
| `review` | Cycle ended, review/retro in progress |
| `closed` | Review complete, cycle archived |

---

## Priority & Severity

### Priority (applies to all work items)

| Priority | Meaning |
|----------|---------|
| `critical` | Must be resolved immediately — blocks release or causes outage |
| `high` | Must be completed this cycle |
| `medium` | Should be completed this cycle if capacity allows |
| `low` | Can wait for a future cycle |

### Severity (applies to bugs and incidents only)

| Severity | Meaning |
|----------|---------|
| `P0` | Complete outage or data loss — all hands on deck |
| `P1` | Major feature broken — significant user impact |
| `P2` | Feature degraded — workaround exists |
| `P3` | Minor issue — cosmetic or edge case |

---

## Naming Conventions

| Entity | Pattern | Example |
|--------|---------|---------|
| Objective | `O{n}-{slug}.md` | `O1-grow-revenue.md` |
| Key Result | `KR-{obj}.{n}-{slug}.md` | `KR-1.1-increase-mrr-30pct.md` |
| Phase | `P{n}-{slug}.md` | `P1-mvp.md` |
| Epic (folder) | `E{n}-{slug}/` | `E1-auth-system/` |
| Epic (file) | `_epic.md` | Always inside its epic folder |
| Story | `S{epic}.{n}-{slug}.md` | `S1.1-user-login.md` |
| Cycle (folder) | `C{nn}/` | `C05/` |
| Cycle (file) | `_cycle.md` | Always inside its cycle folder |
| Backlog item | `{PREFIX}-{nnn}-{slug}.md` | `BUG-042-login-crash.md` |
| PRD | `PRD-{slug}.md` | `PRD-iot-dashboard.md` |
| Pulse log | `{YYYY-MM-DD}-{worker}.md` | `2026-02-16-alice.md` |
| Agent profile | `{agent-name}.md` | `claude-code.md` |
| Team profile | `{name}.md` | `alice.md` |
| Retrospective | `{scope}-retro.md` | `C05-retro.md` |

**Rules**: Slugs are kebab-case, lowercase, no special characters. IDs are used for cross-referencing in `[[ID]]` wiki-link syntax.

---

## Folder Structure

```
.okrmd/
├── config.md              ← This file
├── objectives/
├── key-results/
├── phases/
├── epics/
│   └── E{n}-{slug}/
│       ├── _epic.md
│       └── S{n}.{n}-{slug}.md
├── prds/
├── cycles/
│   └── C{nn}/
│       └── _cycle.md
├── backlog/
├── pulses/
├── agents/
├── team/
├── retros/
└── templates/
```

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 0.1 | YYYY-MM-DD | Initial project configuration |
