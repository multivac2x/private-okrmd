# OKRMD Workflows Guide

**OKRMD Standard v0.1** · **Reference Document**

> This document defines the standard workflows for using OKRMD — from quarterly planning down to daily pulse execution.
> Workflows describe the sequence of activities, who performs them, and which files are created or updated at each step.
> Teams should adapt these workflows to their context. The sequence matters; the exact ceremonies are flexible.

---

## Workflow Overview

OKRMD operates on four nested time horizons, each with its own workflow:

```
Quarterly Planning (every 13 weeks)
  └── Phase Gate Review (at phase boundaries)
       └── Cycle Flow (every 1–2 weeks)
            └── Daily Pulse Execution (every day)
```

Additional workflows handle unplanned situations:

```
Incident Response (when things break)
Backlog Triage (ongoing)
Agent Onboarding (when adding a new agent)
Mid-Quarter Course Correction (when strategy shifts)
```

---

## 1. Quarterly Planning Workflow

> **Frequency**: Every quarter (13 weeks)
> **Duration**: 1–3 days depending on team size
> **Participants**: Leadership, team leads, key contributors
> **Outcome**: Objectives, Key Results, Phases, and initial Epic breakdown defined

### Steps

| Step | Action | Who | Files Created / Updated | Duration |
|------|--------|-----|------------------------|----------|
| 1.1 | **Review previous quarter** | All | Update previous quarter's O and KR files with final scores. Complete `Q{n}-retro.md`. | 2–4 hours |
| 1.2 | **Review company / team context** | Leadership | None (discussion only) | 1 hour |
| 1.3 | **Draft objectives** | Leadership + leads | Create `O{n}-{slug}.md` files (3–5 objectives) | 2 hours |
| 1.4 | **Define key results** | KR owners | Create `KR-{obj}.{n}-{slug}.md` files (2–5 per objective) | 2–4 hours |
| 1.5 | **Define phases** | Product + tech leads | Create `P{n}-{slug}.md` files with gate criteria | 1–2 hours |
| 1.6 | **Break phases into epics** | Epic owners | Create `E{n}-{slug}/` folders with `_epic.md` | 2–4 hours |
| 1.7 | **Initial story breakdown** | Epic owners | Create `S{e}.{n}-{slug}.md` story files (at least titles + rough AC) | 4–8 hours |
| 1.8 | **Create / update PRDs** | Product | Create or update `PRD-{slug}.md` files | Varies |
| 1.9 | **Set autonomy defaults** | Team leads | Update `config.md` and `_epic.md` defaults | 30 min |
| 1.10 | **Plan first cycle** | All | Create `C{nn}/_cycle.md` with committed stories | 2 hours |

### Checklist

- [ ] Previous quarter's OKRs scored and retrospective complete
- [ ] 3–5 Objectives defined with clear owners
- [ ] 2–5 Key Results per Objective, all measurable
- [ ] Phases defined with gate criteria
- [ ] Epics created and assigned to phases
- [ ] Initial stories written (at least for Phase 1)
- [ ] PRDs created or updated
- [ ] First cycle planned
- [ ] Agent profiles reviewed and updated
- [ ] Team profiles reviewed and updated
- [ ] `config.md` reviewed and updated for the new quarter

---

## 2. Phase Gate Review Workflow

> **Frequency**: At phase boundaries (when all epics in a phase are complete)
> **Duration**: 1–2 hours
> **Participants**: Phase owner, epic owners, stakeholders
> **Outcome**: Go / No-Go decision on shipping the phase

### Steps

| Step | Action | Who | Files Updated |
|------|--------|-----|---------------|
| 2.1 | **Verify gate criteria** | Phase owner | Check all items in `P{n}.md` gate criteria section |
| 2.2 | **Review quality gates** | Tech lead / QA | Verify test coverage, performance, security in `P{n}.md` |
| 2.3 | **Review KR progress** | KR owner | Update `KR-{obj}.{n}.md` tracking log |
| 2.4 | **Gather stakeholder input** | Phase owner | Discussion — document in phase file |
| 2.5 | **Make decision** | Decision makers | Update `P{n}.md` Go/No-Go section |
| 2.6 | **Document rationale** | Phase owner | Complete decision rationale in `P{n}.md` |
| 2.7 | **Plan next phase** (if Go) | Epic owners | Refine stories for next phase's epics |
| 2.8 | **Phase retrospective** | All | Complete `P{n}.md` retrospective section or create `P{n}-retro.md` |

### Decision Options

| Decision | Next step |
|----------|-----------|
| **Ship** | Deploy / release. Begin next phase planning. |
| **Iterate** | Fix specific issues. Schedule follow-up gate review. |
| **Pivot** | Revise phase scope or approach. May affect OKRs. Trigger Mid-Quarter Course Correction. |
| **Stop** | Cancel remaining phases. Document reasoning. Redirect resources. |

---

## 3. Cycle (Sprint) Flow Workflow

> **Frequency**: Every 1–2 weeks (as set in `config.md`)
> **Participants**: Full team (humans and agent supervisors)
> **Outcome**: Stories delivered, velocity tracked, retrospective completed

### 3.1 Cycle Planning

> **When**: First day of the cycle
> **Duration**: 1–2 hours

| Step | Action | Who | Files Created / Updated |
|------|--------|-----|------------------------|
| 3.1.1 | **Review previous cycle** | All | Ensure previous `_cycle.md` review section is complete |
| 3.1.2 | **Review capacity** | All | Fill capacity section in new `_cycle.md` |
| 3.1.3 | **Set cycle goal** | Team lead | Write goal in `_cycle.md` |
| 3.1.4 | **Select stories** | All | Pull stories from current phase's epics into committed work table |
| 3.1.5 | **Select backlog items** | All | Pull priority backlog items into committed work table |
| 3.1.6 | **Assign work** | All | Set assignee, reviewer, and autonomy level per item |
| 3.1.7 | **Set agent budgets** | Agent supervisors | Set token budgets per agent story |
| 3.1.8 | **Identify stretch goals** | All | Add stretch items to `_cycle.md` |
| 3.1.9 | **Finalize commitment** | All | Verify total commitment ≤ 80% capacity (humans), ≤ 90% (agents) |

### 3.2 Daily Execution

> **Every working day during the cycle**

#### Morning (Humans)

| Step | Action | Who |
|------|--------|-----|
| 3.2.1 | Check yesterday's pulse log for carry-over items | Assignee |
| 3.2.2 | Update standup log in `_cycle.md` | All team members |
| 3.2.3 | Review any agent PRs / output from overnight | Agent supervisors |
| 3.2.4 | Begin first Pulse of the day | Assignee |

#### During the Day (Humans)

| Step | Action | Who |
|------|--------|-----|
| 3.2.5 | Work in Pulses (25 min focus + 5 min rest) | Assignee |
| 3.2.6 | Log each Pulse to daily pulse log | Assignee |
| 3.2.7 | Check tasks off in story file as completed | Assignee |
| 3.2.8 | If blocked, add blocker to `_cycle.md` blockers table | Assignee |
| 3.2.9 | If story complete, move status to `review` | Assignee |

#### Agent Execution (Async, 24/7)

| Step | Action | Who |
|------|--------|-----|
| 3.2.10 | Agent receives story assignment with full context | Orchestrator / Supervisor |
| 3.2.11 | Agent executes in Pulses (token-bounded) | Agent |
| 3.2.12 | Agent checkpoints after each Pulse (commit, save state) | Agent |
| 3.2.13 | Agent logs each Pulse to its pulse log | Agent |
| 3.2.14 | If uncertain (A3), agent pauses and flags for human input | Agent |
| 3.2.15 | Agent completes and opens PR / submits output with handoff summary | Agent |
| 3.2.16 | Agent updates story status to `review` | Agent |

#### Evening (Humans)

| Step | Action | Who |
|------|--------|-----|
| 3.2.17 | Complete end-of-day reflection in pulse log | Assignee |
| 3.2.18 | Queue agent work for overnight execution (if applicable) | Agent supervisor |

### 3.3 Mid-Cycle Check-In

> **When**: Midpoint of the cycle (optional but recommended)
> **Duration**: 15–30 minutes

| Step | Action | Who |
|------|--------|-----|
| 3.3.1 | Count stories completed vs committed | Cycle lead |
| 3.3.2 | Assess goal achievability | All |
| 3.3.3 | Adjust scope if needed (cut low-priority items, pull stretch goals) | All |
| 3.3.4 | Document in `_cycle.md` mid-cycle check-in section | Cycle lead |

### 3.4 Cycle Review

> **When**: Last day of the cycle
> **Duration**: 30–60 minutes

| Step | Action | Who | Files Updated |
|------|--------|-----|---------------|
| 3.4.1 | **Tally delivery** | Cycle lead | Complete delivery summary in `_cycle.md` |
| 3.4.2 | **Calculate velocity** | Cycle lead | Update velocity section in `_cycle.md` |
| 3.4.3 | **Identify carry-overs** | All | List unfinished items in carry-over section |
| 3.4.4 | **Demo / showcase** | Presenters | Document demos in `_cycle.md` |
| 3.4.5 | **Update OKR scores** | KR owners | Update `KR-{obj}.{n}.md` tracking logs |
| 3.4.6 | **Update phase progress** | Phase owner | Update `P{n}.md` epics progress table |

### 3.5 Cycle Retrospective

> **When**: After cycle review, same day or next morning
> **Duration**: 30–60 minutes

| Step | Action | Who | Files Created |
|------|--------|-----|---------------|
| 3.5.1 | **Follow up on previous retro actions** | Facilitator | Review `previous-retro.md` action items |
| 3.5.2 | **Collect what went well** | All | Add to retro file |
| 3.5.3 | **Collect what didn't go well** | All | Add to retro file |
| 3.5.4 | **Review human-agent collaboration** | All | Complete human-agent section |
| 3.5.5 | **Identify action items** (max 3–5) | All | Add with owners and target dates |
| 3.5.6 | **Assess team mood** | All | Complete mood section |
| 3.5.7 | **Archive cycle** | Cycle lead | Move `C{nn}/` to `cycles/archive/` |
| 3.5.8 | **Create next cycle file** | Cycle lead | Create `C{nn+1}/_cycle.md` |

---

## 4. Daily Pulse Execution Workflow

> **Frequency**: Every working day
> **Participants**: Individual worker (human or agent)
> **Outcome**: Focused progress on assigned work, logged in pulse files

### Human Daily Flow

```
1. Open/create today's pulse log: pulses/{date}-{name}.md
2. Check carry-over from yesterday's log
3. Identify first task (from cycle commitment or yesterday's "tomorrow's first task")
4. Start Pulse timer (25 min standard, 50 min deep)
5. Work on ONE task only — no multitasking
6. Timer ends → log the Pulse (task, status, interruptions)
7. Take rest (5 min standard, 15 min after 4 pulses)
8. Repeat steps 4–7
9. End of day → complete reflection section
10. Set "tomorrow's first task"
```

### Agent Session Flow

```
1. Receive task assignment with story file + context
2. Load context: story → epic → PRD section → relevant code
3. Begin Pulse 1 — execute task group
4. Monitor context utilization
5. At 80% context or task group complete → checkpoint (commit, log)
6. Log the Pulse (task, tokens, context %, checkpoint)
7. Begin new Pulse with fresh context + checkpoint data
8. Repeat steps 3–7 until story complete or token budget exhausted
9. Write handoff summary
10. Submit output (PR, file, report) with status update
```

---

## 5. Incident Response Workflow

> **Trigger**: Production outage, critical bug, security breach, or any P0/P1 event
> **Priority**: Overrides all cycle commitments
> **Outcome**: Issue resolved, incident documented, preventive actions identified

| Step | Action | Who | Files Created / Updated | Timebox |
|------|--------|-----|------------------------|---------|
| 5.1 | **Detect and triage** | First responder | Create `INC-{nnn}-{slug}.md` in `backlog/` | Immediate |
| 5.2 | **Set severity** | Incident lead | Update `INC` file severity field | 5 min |
| 5.3 | **Assign responder** | Incident lead | Set assignee and autonomy (typically A2–A3) | 5 min |
| 5.4 | **Investigate and mitigate** | Assignee | Update `INC` file timeline section | Varies |
| 5.5 | **Apply fix** | Assignee | Code changes via hotfix branch | Varies |
| 5.6 | **Verify resolution** | Reviewer | Verify fix in production | 30 min |
| 5.7 | **Update incident file** | Assignee | Complete root cause, fix, timeline | 30 min |
| 5.8 | **Log in cycle** | Cycle lead | Add to `_cycle.md` unplanned work section | 5 min |
| 5.9 | **Post-incident retro** (for P0/P1) | Team | Create `INC-{nnn}-retro.md` | 1 hour |
| 5.10 | **Create follow-up items** | Incident lead | Create backlog items for preventive actions | 30 min |

### Agent Involvement in Incidents

| Severity | Agent role |
|----------|-----------|
| P0 | Agent assists at A4 (human drives, agent accelerates investigation) |
| P1 | Agent can lead at A3 (executes fix, human reviews before deploy) |
| P2 | Agent can lead at A2–A3 (standard supervised workflow) |
| P3 | Agent can lead at A2 (routine fix, spot-check review) |

---

## 6. Backlog Triage Workflow

> **Frequency**: Weekly or as items accumulate
> **Duration**: 30 minutes
> **Participants**: Product lead, tech lead, relevant team members
> **Outcome**: Backlog items prioritized, assigned, or archived

| Step | Action | Who |
|------|--------|-----|
| 6.1 | Review all items in `triage` status | Triage lead |
| 6.2 | Set priority and severity for each item | Triage participants |
| 6.3 | Determine if item should be promoted to story | Product lead |
| 6.4 | If promoting: create story in appropriate epic, link from backlog item | Product lead |
| 6.5 | If keeping as backlog item: set status to `ready`, assign to cycle | Triage lead |
| 6.6 | If deferring: keep in `triage` with a note on when to reconsider | Triage lead |
| 6.7 | If rejecting: set status to `wont-fix` with rationale, archive | Triage lead |

---

## 7. Agent Onboarding Workflow

> **Trigger**: Adding a new AI agent to the team
> **Duration**: 1–2 hours setup + 1 cycle evaluation period
> **Outcome**: Agent profile created, tested on low-risk tasks, ready for regular assignment

| Step | Action | Who | Files Created |
|------|--------|-----|---------------|
| 7.1 | **Create agent profile** | Agent supervisor | `agents/{name}.md` |
| 7.2 | **Configure tools and access** | Agent supervisor | Update profile tools section |
| 7.3 | **Set initial autonomy** | Agent supervisor | Set conservative default (A3 or A4) |
| 7.4 | **Assign trial task** | Agent supervisor | Pick a low-risk story or backlog item |
| 7.5 | **Monitor trial execution** | Agent supervisor | Review pulse logs, check quality |
| 7.6 | **Full review of trial output** | Reviewer | Standard review process |
| 7.7 | **Update profile with findings** | Agent supervisor | Update strengths, limitations, performance |
| 7.8 | **Adjust autonomy based on trial** | Agent supervisor | Increase or decrease from initial setting |
| 7.9 | **Announce to team** | Agent supervisor | Add to `config.md` team roster |
| 7.10 | **Begin regular assignment** | Cycle planning | Include in next cycle planning |

### Evaluation Period

> New agents should operate at **one level less autonomous** than their expected steady-state for the first full cycle (minimum 5 stories). Track pass rate closely during this period.

---

## 8. Mid-Quarter Course Correction Workflow

> **Trigger**: OKR scores are off track, strategic context has changed, or phase gate review triggers a pivot
> **Duration**: 2–4 hours
> **Participants**: OKR owners, team leads
> **Outcome**: OKRs adjusted, phases restructured, or work redirected

| Step | Action | Who | Files Updated |
|------|--------|-----|---------------|
| 8.1 | **Review current OKR scores** | KR owners | Read `KR-{obj}.{n}.md` tracking logs |
| 8.2 | **Identify off-track KRs** | All | Flag KRs scoring below 0.3 at midpoint |
| 8.3 | **Diagnose root cause** | All | Discussion — external factors, execution issues, wrong target? |
| 8.4 | **Decide action per KR** | OKR owners | See decision options below |
| 8.5 | **Update affected files** | Owners | Modify O, KR, P, E files as needed |
| 8.6 | **Communicate changes** | Team lead | Update `config.md` if defaults change, notify team |
| 8.7 | **Adjust current cycle** | Cycle lead | Update `_cycle.md` committed work if priorities shifted |

### Decision Options

| Option | When to use | File changes |
|--------|------------|-------------|
| **Stay the course** | On track or minor deviation. Execution needs improvement, not strategy. | Update KR review notes |
| **Adjust target** | Original target was unrealistic given new information | Update KR `metric_target` and notes |
| **Restructure phases** | Work is progressing but in wrong order | Update phase files, resequence epics |
| **Add / remove epics** | Scope change needed to hit KR | Create/archive epic folders |
| **Abandon KR** | KR is no longer relevant or achievable | Set KR status to `abandoned` with rationale |
| **Abandon objective** | Entire strategic direction has changed | Set O status to `abandoned`, cascade to KRs |

---

## Workflow Summary Calendar

| Time Horizon | Workflow | Frequency | Duration |
|-------------|----------|-----------|----------|
| Day | Pulse Execution | Daily | All day |
| Day | Agent Review (overnight output) | Daily | 30 min |
| Week | Backlog Triage | Weekly | 30 min |
| Week | OKR Score Update | Weekly | 15 min |
| 1–2 weeks | Cycle Planning | Per cycle | 1–2 hours |
| 1–2 weeks | Cycle Review + Retro | Per cycle | 1–2 hours |
| 4–8 weeks | Phase Gate Review | Per phase | 1–2 hours |
| ~6 weeks | Mid-Quarter Course Correction | Once per quarter | 2–4 hours |
| 13 weeks | Quarterly Planning | Per quarter | 1–3 days |
| As needed | Incident Response | On trigger | Varies |
| As needed | Agent Onboarding | On addition | 1–2 hours + 1 cycle eval |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 0.1 | 2026-02-19 | Initial workflows guide |
