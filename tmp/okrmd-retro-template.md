# OKRMD Retrospective Template

**OKRMD Standard v1.0** · **retro.md**

> This template defines a Retrospective document.
> Place it at `.okrmd/retros/{scope}-retro.md` where scope identifies what is being reviewed.
> A Retrospective is a structured reflection on a completed period of work. It answers: *"What did we learn, and what will we change?"*
>
> **Naming convention**:
> - Cycle retro: `C05-retro.md`
> - Quarterly retro: `Q1-2026-retro.md`
> - Phase retro: `P1-mvp-retro.md`
> - Incident retro: `INC-007-retro.md`
> - Custom: `{scope}-retro.md`
>
> **Retrospectives are not blame sessions.** They are learning mechanisms. The goal is to identify what to change in the system and process, not who made mistakes. This applies equally to human and agent performance — an agent that underperformed had the wrong assignment, context, or autonomy level. Fix the system.

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `___` | Matches filename scope (e.g. `C05-retro`, `Q1-2026-retro`) |
| Title | `___` | Descriptive name (e.g. "Cycle 5 Retrospective", "Q1 2026 OKR Review") |
| Type | `___` | `cycle` · `quarterly` · `phase` · `incident` · `project` · `custom` |
| Scope | `[[___]]` | Link to the cycle, quarter, phase, or incident being reviewed |
| Status | `scheduled` | `scheduled` · `in-progress` · `complete` |
| Date | `YYYY-MM-DD` | Date the retro was held |
| Facilitator | `___` | Who facilitated the session |
| Participants | `___` | Comma-separated names of all participants |
| Duration | `___` | Actual duration of the session (e.g. `60 min`) |
| Created | `YYYY-MM-DD` | |
| Updated | `YYYY-MM-DD` | |

---

## Period Summary

> Brief factual summary of the period being reviewed. Set the context before diving into reflection.

| Field | Value |
|-------|-------|
| Period | `YYYY-MM-DD` to `YYYY-MM-DD` |
| Goal / Objective | `___` |
| Goal met? | `yes` / `partially` / `no` |

### Key Metrics

| Metric | Planned | Actual | Delta | Notes |
|--------|---------|--------|-------|-------|
| Stories completed | `___` | `___` | `___` | |
| Backlog items completed | `___` | `___` | `___` | |
| Points / Pulses delivered | `___` | `___` | `___` | |
| Scope changes | `0` | `___` | `___` | |
| Unplanned work items | `0` | `___` | `___` | |
| Carry-over items | `0` | `___` | `___` | |
| Blockers encountered | `0` | `___` | `___` | |

### OKR Progress (Quarterly Retros)

> For quarterly retrospectives, summarize OKR scores.

| Objective | Score | Status | Notes |
|-----------|-------|--------|-------|
| `[[O{n}]]` — `___` | `___` / 1.0 | `___` | `___` |

| Key Result | Score | Status | Notes |
|------------|-------|--------|-------|
| `[[KR-___]]` — `___` | `___` / 1.0 | `___` | `___` |

---

## What Went Well

> Things the team should keep doing. Be specific — name the practice, decision, or behavior, not vague sentiments.

| # | What went well | Category | Impact |
|---|---------------|----------|--------|
| 1 | `___` | `process` / `technical` / `collaboration` / `planning` / `quality` / `agent-perf` | `___` |
| 2 | `___` | | |
| 3 | `___` | | |
| 4 | `___` | | |

---

## What Didn't Go Well

> Things the team should stop doing or change. Focus on systemic issues, not individual blame.

| # | What didn't go well | Category | Impact | Root cause |
|---|---------------------|----------|--------|------------|
| 1 | `___` | `process` / `technical` / `collaboration` / `planning` / `quality` / `agent-perf` | `___` | `___` |
| 2 | `___` | | | |
| 3 | `___` | | | |
| 4 | `___` | | | |

---

## What We Learned

> Insights, surprises, or new understanding gained during this period. Different from "what went well/badly" — this is about knowledge, not evaluation.

| # | Learning | Applies to |
|---|---------|-----------|
| 1 | `___` | `future-cycles` / `team-process` / `agent-config` / `estimation` / `architecture` / `other` |
| 2 | `___` | |
| 3 | `___` | |

---

## Human-Agent Collaboration Review

> Dedicated section for reflecting on how human-agent teamwork functioned. This is a core differentiator of OKRMD retrospectives.

### Autonomy Level Accuracy

> Were the A1–A5 levels set correctly for agent-assigned work?

| Story / Item | Agent | Level Set | Correct Level | Notes |
|-------------|-------|-----------|---------------|-------|
| `[[___]]` | `___` | `___` | `___` | _e.g. "Set A3 but should have been A2 — too many judgment calls"_ |
| `[[___]]` | | | | |

### Agent Performance

| Agent | Stories | Pass Rate (1st review) | Avg Review Findings | Token Efficiency | Notes |
|-------|---------|----------------------|--------------------|--------------------|-------|
| `[[___]]` | `___` | `___` % | `___` | `___` tokens/story | `___` |
| `[[___]]` | | | | | |

### Review Bottleneck

> Did human review capacity keep pace with agent output?

| Metric | Value | Notes |
|--------|-------|-------|
| Avg time from agent PR to first review | `___` | |
| Avg time from first review to merge | `___` | |
| PRs that waited > 24h for review | `___` | |
| Agent idle time (waiting for review) | `___` | |

### Handoff Quality

> How well did context transfer between humans and agents?

| Observation | Quality | Action needed |
|------------|---------|---------------|
| Agent → Human handoffs | `smooth` / `adequate` / `poor` | `___` |
| Human → Agent handoffs | `smooth` / `adequate` / `poor` | `___` |
| Agent → Agent handoffs | `smooth` / `adequate` / `poor` / `N/A` | `___` |

### Agent Profile Updates Needed

> Based on this period's experience, do any agent profiles need updating?

| Agent | Update needed | Details |
|-------|--------------|---------|
| `[[___]]` | `strengths` / `limitations` / `autonomy` / `cost` / `tools` / `none` | `___` |
| `[[___]]` | | |

---

## Process Review

### Estimation Accuracy

| Metric | Value | Notes |
|--------|-------|-------|
| Stories estimated accurately (±20%) | `___` / `___` | |
| Average overestimation | `___` % | |
| Average underestimation | `___` % | |
| Most misestimated story | `[[___]]` — off by `___` | `___` |

> **Trend**: Are estimates improving cycle over cycle? `improving` / `stable` / `degrading`

### Cycle Health Indicators

| Indicator | This Period | Previous | Healthy Range | Status |
|-----------|-----------|----------|---------------|--------|
| Velocity (points/pulses) | `___` | `___` | `___` | `healthy` / `watch` / `concern` |
| Unplanned work ratio | `___` % | `___` % | `< 20%` | |
| Carry-over ratio | `___` % | `___` % | `< 15%` | |
| Blocker resolution time | `___` | `___` | `< 24h` | |
| Interrupt rate (per person/day) | `___` | `___` | `< 2` | |
| Agent review turnaround | `___` | `___` | `< 8h` | |

### Ceremony Effectiveness

> Were the cycle ceremonies (planning, standups, review) effective?

| Ceremony | Effective? | Time spent | Notes |
|----------|-----------|-----------|-------|
| Cycle planning | `yes` / `partially` / `no` | `___` | `___` |
| Daily standup | `yes` / `partially` / `no` | `___` | `___` |
| Cycle review | `yes` / `partially` / `no` | `___` | `___` |
| This retrospective | `yes` / `partially` / `no` | `___` | `___` |

---

## Action Items

> Concrete changes to implement in the next period. Every action item must have an owner and a target. Vague intentions ("we should communicate better") are not action items.

| # | Action | Category | Owner | Target cycle / date | Priority |
|---|--------|----------|-------|-------------------|----------|
| 1 | `___` | `process` / `technical` / `agent-config` / `tooling` / `planning` / `communication` | `___` | `[[C{nn}]]` | `must` / `should` / `could` |
| 2 | `___` | | | | |
| 3 | `___` | | | | |
| 4 | `___` | | | | |
| 5 | `___` | | | | |

> **Limit**: Commit to 3–5 action items maximum. More than that and none will get done. Prioritize ruthlessly.

---

## Previous Retro Actions Follow-Up

> Review action items from the last retrospective. Were they implemented? Did they help?

| # | Action (from `[[___-retro]]`) | Status | Outcome |
|---|-------------------------------|--------|---------|
| 1 | `___` | `done` / `in-progress` / `dropped` | `___` |
| 2 | `___` | | |
| 3 | `___` | | |

> **Accountability note**: If the same action item appears in three consecutive retros without being completed, it's either not important enough (drop it) or too hard to do incrementally (break it down or escalate it).

---

## Team Mood

> Optional. Anonymous or open — team decides. A simple check on how people are feeling. Tracked over time to detect burnout, disengagement, or momentum.

| Dimension | Score (1–5) | Notes |
|-----------|-------------|-------|
| Motivation | `___` | 1 = burned out, 5 = energized |
| Confidence in direction | `___` | 1 = lost, 5 = clear and aligned |
| Workload sustainability | `___` | 1 = overwhelmed, 5 = comfortable pace |
| Team collaboration quality | `___` | 1 = siloed/friction, 5 = seamless |
| Human-agent collaboration quality | `___` | 1 = frustrating, 5 = productive and natural |

> **Trend**: Compare to last retro. `improving` / `stable` / `declining` for each dimension.

---

## Closing Notes

> Any final thoughts, acknowledgments, or context that doesn't fit elsewhere.

`___`

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Retrospective created |
