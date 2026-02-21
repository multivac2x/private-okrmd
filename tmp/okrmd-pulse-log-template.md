# OKRMD Pulse Log Template

**OKRMD Standard v1.0** · **pulse-log.md**

> This template defines a single day's Pulse Log for one worker (human or agent).
> Place it at `.okrmd/pulses/{YYYY-MM-DD}-{worker}.md`.
> A Pulse Log records every focused work session in a day — what was worked on, for how long, what was accomplished, and what interrupted the flow. It answers: *"How was today's energy spent, and what did it produce?"*
>
> **One file per worker per day**: Alice's Monday log and Claude Code's Monday log are separate files. This enables per-worker analysis while keeping files small and focused.
>
> **Human vs Agent**: This template has sections for both. Use the section that matches the worker type — the structure differs because the constraints differ (time vs tokens, interruptions vs context utilization).

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| Date | `YYYY-MM-DD` | |
| Worker | `___` | Name matching the team or agent profile (e.g. `alice`, `claude-code`) |
| Worker type | `human` / `agent` | |
| Profile | `[[___]]` | Link to team member or agent profile |

---

## Human Pulse Log

> Use this section for human workers. Delete the Agent section if not needed.

### Day Summary

| Metric | Value |
|--------|-------|
| Pulses completed | `___` |
| Deep Pulses | `___` |
| Total focus time | `___` min |
| Total rest time | `___` min |
| Interruptions | `___` |
| Stories progressed | `___` |
| Items completed | `___` |
| PRs submitted | `___` |
| PRs reviewed | `___` |

### Pulses

<!-- Copy the pulse block below for each pulse in the day. -->

#### Pulse 1 (`HH:MM`–`HH:MM`) — `___` min

| Field | Value |
|-------|-------|
| Type | `standard` / `deep` / `pair` |
| Task | `[[___]]` — `___` (brief description) |
| Status | `___` (what was accomplished) |
| Interruptions | `___` (count + brief cause, or `0`) |
| Notes | `___` |

> _Rest: `___` min_

---

#### Pulse 2 (`HH:MM`–`HH:MM`) — `___` min

| Field | Value |
|-------|-------|
| Type | `standard` / `deep` / `pair` |
| Task | `[[___]]` — `___` |
| Status | `___` |
| Interruptions | `___` |
| Notes | `___` |

> _Rest: `___` min_

---

#### Pulse 3 (`HH:MM`–`HH:MM`) — `___` min

| Field | Value |
|-------|-------|
| Type | `standard` / `deep` / `pair` |
| Task | `[[___]]` — `___` |
| Status | `___` |
| Interruptions | `___` |
| Notes | `___` |

> _Rest: `___` min_

---

#### Pulse 4 (`HH:MM`–`HH:MM`) — `___` min

| Field | Value |
|-------|-------|
| Type | `standard` / `deep` / `pair` |
| Task | `[[___]]` — `___` |
| Status | `___` |
| Interruptions | `___` |
| Notes | `___` |

> _Long rest: `___` min (after 4 pulses)_

---

<!-- Add more pulse blocks as needed. -->

### Interruption Log

> Optional detailed tracking. Useful for identifying patterns and protecting future focus time.

| Pulse | Time | Source | Type | Duration | Avoidable? |
|-------|------|--------|------|----------|-----------|
| `___` | `HH:MM` | `___` | `meeting` / `message` / `incident` / `question` / `other` | `___` min | `yes` / `no` |
| | | | | | |

### Energy & Focus Rating

> Subjective self-assessment. Tracked over time to identify patterns (best days, best hours, burnout signals).

| Field | Value | Scale |
|-------|-------|-------|
| Morning energy | `___` | 1 (depleted) – 5 (peak) |
| Afternoon energy | `___` | 1 – 5 |
| Overall focus quality | `___` | 1 (scattered) – 5 (deep flow) |
| Notes | `___` | _e.g. "slept poorly", "high motivation after demo"_ |

### End of Day Reflection

> Optional but recommended. Two minutes of reflection at the end of the day compounds into significant self-awareness over weeks.

| Field | Value |
|-------|-------|
| Most productive pulse | `___` (which pulse and why) |
| Biggest blocker | `___` |
| Tomorrow's first task | `___` (reduces morning decision fatigue) |
| One thing to improve | `___` |

---

## Agent Pulse Log

> Use this section for AI agent workers. Delete the Human section if not needed.

### Session Summary

| Metric | Value |
|--------|-------|
| Pulses completed | `___` |
| Total tokens used | `___` |
| Token budget | `___` |
| Budget utilization | `___` % |
| Average context utilization | `___` % |
| Files created | `___` |
| Files modified | `___` |
| Tests written | `___` |
| Tests passing | `___` |
| PRs opened | `___` |
| Stories progressed | `___` |
| Items completed | `___` |
| Errors encountered | `___` |

### Agent Configuration

> Record the configuration for this session. Useful for comparing performance across different setups.

| Field | Value |
|-------|-------|
| Model | `___` |
| Model version / snapshot | `___` |
| Temperature | `___` |
| Tools enabled | `___` |
| System prompt version | `___` |
| Custom instructions | `___` or `none` |

### Pulses

<!-- Copy the pulse block below for each agent pulse. -->

#### Pulse 1 (`HH:MM:SS`–`HH:MM:SS` UTC) — `___` tokens

| Field | Value |
|-------|-------|
| Task | `[[___]]` — `___` (brief description) |
| Status | `___` (what was accomplished) |
| Tokens used | `___` |
| Context utilization | `___` % |
| Checkpoint | `___` (e.g. "committed to branch", "saved summary", "PR opened") |
| Errors | `___` or `none` |
| Notes | `___` |

---

#### Pulse 2 (`HH:MM:SS`–`HH:MM:SS` UTC) — `___` tokens

| Field | Value |
|-------|-------|
| Task | `[[___]]` — `___` |
| Status | `___` |
| Tokens used | `___` |
| Context utilization | `___` % |
| Checkpoint | `___` |
| Errors | `___` or `none` |
| Notes | `___` |

---

#### Pulse 3 (`HH:MM:SS`–`HH:MM:SS` UTC) — `___` tokens

| Field | Value |
|-------|-------|
| Task | `[[___]]` — `___` |
| Status | `___` |
| Tokens used | `___` |
| Context utilization | `___` % |
| Checkpoint | `___` |
| Errors | `___` or `none` |
| Notes | `___` |

---

<!-- Add more pulse blocks as needed. -->

### Error Log

> Track errors, failures, and retries. Patterns here inform agent profile updates and autonomy adjustments.

| Pulse | Error | Type | Recovery | Tokens wasted |
|-------|-------|------|----------|--------------|
| `___` | `___` | `tool-failure` / `context-overflow` / `hallucination` / `logic-error` / `permission` / `timeout` / `other` | `self-corrected` / `retry` / `abandoned` / `escalated` | `___` |
| | | | | |

### Handoff Summary

> What the agent is passing to the next worker (human reviewer or next agent session). This is the "end of shift report."

| Field | Value |
|-------|-------|
| Work completed | `___` |
| Work remaining | `___` |
| Decisions made | `___` |
| Decisions deferred | `___` (items the agent flagged for human input) |
| Blockers for next session | `___` or `none` |
| Recommended next steps | `___` |
| PR / branch ready for review | `___` or `none` |
| Review urgency | `low` / `normal` / `high` |

---

## Pair Pulse Log

> Use this section when a human and agent work together in a pair session. This supplements (not replaces) the individual pulse entries above.

### Pair Session

| Field | Value |
|-------|-------|
| Human | `[[___]]` |
| Agent | `[[___]]` |
| Duration | `___` min |
| Task | `[[___]]` — `___` |
| Autonomy level | `___` |

### Collaboration Pattern

| Field | Value |
|-------|-------|
| Who drove | `human` / `agent` / `alternating` |
| Human contribution | `___` (e.g. "architecture decisions, code review inline") |
| Agent contribution | `___` (e.g. "implementation, test writing") |
| Handoff points | `___` (moments where control shifted) |

### Pair Session Outcome

| Field | Value |
|-------|-------|
| What was accomplished | `___` |
| Quality of collaboration | 1 (friction) – 5 (seamless) |
| Would pair again for similar task | `yes` / `no` / `with-adjustments` |
| Adjustments for next time | `___` |

---

## Cross-Day Continuity

> Link to yesterday's log and tomorrow's planned first task. Maintains the thread across days.

| Field | Value |
|-------|-------|
| Previous log | `[[{YYYY-MM-DD}-{worker}]]` |
| Next log | `[[{YYYY-MM-DD}-{worker}]]` |
| Carry-over from yesterday | `___` or `none` |
| First task tomorrow | `___` |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Pulse log created |
