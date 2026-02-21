# OKRMD Cycle Template

**OKRMD Standard v1.0** · **_cycle.md**

> This template defines a single Cycle (sprint/iteration).
> Place it at `.okrmd/cycles/C{nn}/_cycle.md` — inside its own folder.
> A Cycle is a timeboxed iteration where the team commits to delivering a set of stories and backlog items. It answers: *"What are we delivering in the next 1–2 weeks, and who is doing what?"*
>
> **Cycles vs Phases**: A phase is a strategic delivery gate spanning weeks or months. A cycle is an operational timebox spanning 1–2 weeks. A phase contains multiple cycles. A cycle may pull stories from one or more phases.

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `C{nn}` | Zero-padded cycle number (e.g. `C01`, `C05`, `C12`) |
| Title | `___` | Descriptive name summarizing the cycle focus (e.g. "Cycle 5: Alert System Foundation") |
| Status | `planning` | `planning` · `active` · `review` · `closed` |
| Number | `___` | Sequential cycle number |
| Start date | `YYYY-MM-DD` | First working day of the cycle |
| End date | `YYYY-MM-DD` | Last working day of the cycle |
| Duration (days) | `___` | Working days (default from `config.md`, typically `10` or `14`) |
| Phase(s) | `___` | Phase(s) this cycle contributes to (e.g. `[[P1-mvp]]`) |
| Created | `YYYY-MM-DD` | |
| Updated | `YYYY-MM-DD` | |

---

## Cycle Goal

> One to three sentences describing what this cycle aims to achieve. The goal should be specific enough that at cycle review, everyone can agree whether it was met. Write it in terms of outcomes, not tasks.

`___`

---

## Capacity

### Human Capacity

| Team Member | Profile | Available days | Pulses available | Notes |
|-------------|---------|---------------|-----------------|-------|
| `___` | `[[___]]` | `___` / `___` | `___` | _e.g. PTO on Wed, half-day Fri_ |
| `___` | `[[___]]` | | | |
| | | **Total** | **___** | |

> **Pulses available**: Available days × expected pulses per day (typically 6–8 for humans). Subtract time for ceremonies, meetings, and overhead.

### Agent Capacity

| Agent | Profile | Token budget | Max pulses | Availability | Notes |
|-------|---------|-------------|------------|-------------|-------|
| `___` | `[[___]]` | `___` | `___` | `24/7` / `___` | |
| `___` | `[[___]]` | | | | |
| | | **Total tokens** | **___** | | |

### Ceremony Time Budget

> Time reserved for cycle ceremonies. Subtract from available capacity.

| Ceremony | Duration | Participants | When |
|----------|----------|-------------|------|
| Cycle planning | `___` | `___` | Start of cycle |
| Daily standup | `___` × `___` days | `___` | Daily |
| Cycle review | `___` | `___` | End of cycle |
| Retrospective | `___` | `___` | End of cycle |
| **Total ceremony time** | **___** | | |

> **Note for agents**: Agents do not attend ceremonies by default. They contribute via async updates in this file and in their pulse logs. Include agents in ceremonies only when their input is needed for planning or review.

---

## Committed Work

### Stories

| # | Story | Title | Assignee | Autonomy | Points/Pulses | Status |
|---|-------|-------|----------|----------|--------------|--------|
| 1 | `[[S{e}.{n}]]` | `___` | `___` | `___` | `___` | `___` |
| 2 | `[[S{e}.{n}]]` | `___` | `___` | `___` | `___` | `___` |
| 3 | `[[S{e}.{n}]]` | `___` | `___` | `___` | `___` | `___` |

### Backlog Items

| # | Item | Title | Assignee | Autonomy | Points/Pulses | Status |
|---|------|-------|----------|----------|--------------|--------|
| 1 | `[[{PREFIX}-{nnn}]]` | `___` | `___` | `___` | `___` | `___` |
| 2 | `[[{PREFIX}-{nnn}]]` | `___` | `___` | `___` | `___` | `___` |

### Totals

| Metric | Value |
|--------|-------|
| Total stories committed | `___` |
| Total backlog items committed | `___` |
| Total points/pulses committed | `___` |
| Human capacity utilized | `___` % |
| Agent capacity utilized | `___` % |

> **Commitment guideline**: Commit to 70–80% of available capacity. Leave buffer for unplanned work, context switching, and review overhead. Agents can be loaded higher (85–90%) since they don't have meetings or interruptions.

---

## Stretch Goals

> Work that the team will pull in if committed work finishes early. Not promised — no penalty for not completing these.

| # | Item | Title | Assignee | Points/Pulses |
|---|------|-------|----------|--------------|
| 1 | `[[___]]` | `___` | `___` | `___` |
| 2 | `[[___]]` | `___` | `___` | `___` |

---

## Assignment Matrix

> Visual overview of who is working on what. Useful for spotting overload and gaps.

### Human Assignments

| Team Member | Mon | Tue | Wed | Thu | Fri |
|-------------|-----|-----|-----|-----|-----|
| `___` | `___` | `___` | `___` | `___` | `___` |
| `___` | | | | | |

> Fill with story/item IDs or brief descriptions. Use `PTO`, `ceremony`, `review` for non-delivery time.

### Agent Assignments

| Agent | Assigned items | Token allocation | Expected completion |
|-------|---------------|-----------------|-------------------|
| `___` | `___` | `___` | `___` |
| `___` | | | |

> Agents typically work through items sequentially or in parallel depending on their orchestration model. List the order of priority if sequential.

---

## Daily Standup Log

> Async daily updates. Each team member (human or agent) logs what they did, what they'll do next, and any blockers. Agents update automatically from pulse logs when possible.

### `YYYY-MM-DD` (Day Name)

| Member | Yesterday / Last update | Today / Next | Blockers |
|--------|------------------------|-------------|----------|
| `___` | `___` | `___` | `___` or `none` |
| `___` | | | |

<!-- Copy this block for each working day of the cycle. -->

### `YYYY-MM-DD` (Day Name)

| Member | Yesterday / Last update | Today / Next | Blockers |
|--------|------------------------|-------------|----------|
| `___` | `___` | `___` | `___` or `none` |
| `___` | | | |

---

## Blockers & Escalations

> Track blockers that affect cycle delivery. Resolve them here or escalate.

| # | Blocker | Affects | Raised by | Date raised | Owner | Status | Resolution |
|---|---------|---------|-----------|-------------|-------|--------|------------|
| 1 | `___` | `[[___]]` | `___` | `YYYY-MM-DD` | `___` | `open` / `escalated` / `resolved` | `___` |
| 2 | | | | | | | |

---

## Mid-Cycle Check-In

> Optional but recommended. At the cycle midpoint, assess whether the goal is still achievable and adjust if needed.

| Field | Value |
|-------|-------|
| Check-in date | `YYYY-MM-DD` |
| Stories completed so far | `___` / `___` |
| Goal still achievable? | `yes` / `at-risk` / `no` |
| Adjustments made | `___` or `none` |

---

## Unplanned Work Added

> Track any work added after cycle planning. This is the "interrupt rate" — a key health metric.

| # | Item | Type | Added date | Reason | Displaced |
|---|------|------|-----------|--------|-----------|
| 1 | `[[___]]` | `___` | `YYYY-MM-DD` | `___` | `___` or `nothing` |
| 2 | | | | | |

> **Displaced**: If adding unplanned work meant removing a committed item, note what was removed. This tracks the true cost of interrupts.

---

## Cycle Review

> Filled at the end of the cycle. What was delivered?

### Review Date: `YYYY-MM-DD`

### Goal Met?

> `yes` · `partially` · `no`

`___`

### Delivery Summary

| Category | Planned | Completed | Carry-over | Notes |
|----------|---------|-----------|------------|-------|
| Stories | `___` | `___` | `___` | |
| Backlog items | `___` | `___` | `___` | |
| Stretch goals | `___` | `___` | `—` | |
| Unplanned items | `___` | `___` | `___` | |
| **Total** | **___** | **___** | **___** | |

### Velocity

| Metric | This Cycle | Previous | Trend |
|--------|-----------|----------|-------|
| Points/Pulses completed | `___` | `___` | `↑` / `→` / `↓` |
| Stories completed | `___` | `___` | |
| Unplanned work ratio | `___` % | `___` % | |
| Agent efficiency (tokens/point) | `___` | `___` | |

### Carry-Over Items

> Items not completed that roll into the next cycle.

| Item | Reason | Priority for next cycle |
|------|--------|------------------------|
| `[[___]]` | `___` | `must` / `should` / `re-evaluate` |
| `[[___]]` | | |

### Demos / Showcases

> What was demonstrated to stakeholders at the cycle review?

| Demo | Presenter | Audience | Feedback |
|------|-----------|----------|----------|
| `___` | `___` | `___` | `___` |

---

## Retrospective

> What did the team learn during this cycle? Capture insights, not blame.

### Retrospective Date: `YYYY-MM-DD`

### Participants

`___`

### What went well

`___`

### What didn't go well

`___`

### What to try next cycle

> Concrete action items, not vague aspirations. Assign an owner to each.

| Action | Owner | Carry to cycle |
|--------|-------|---------------|
| `___` | `___` | `[[C{nn}]]` |
| `___` | | |

### Human-Agent Collaboration Notes

> Specific observations about how human-agent teamwork functioned this cycle. What worked? What needs adjustment?

| Observation | Category | Action |
|-------------|----------|--------|
| `___` | `assignment` / `review` / `handoff` / `autonomy` / `communication` | `___` |
| `___` | | |

> **Why this section exists**: Human-agent collaboration patterns are new and evolving. Explicitly reflecting on them accelerates learning. Track autonomy level accuracy (was A3 the right call?), review turnaround (did agent PRs wait too long?), and handoff friction (did the agent have enough context?).

### Previous Retro Actions Follow-Up

> Check whether action items from the last retrospective were actually implemented.

| Action (from `[[C{nn}]]`) | Status | Notes |
|---------------------------|--------|-------|
| `___` | `done` / `in-progress` / `dropped` | `___` |
| `___` | | |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Cycle created (planning) |
