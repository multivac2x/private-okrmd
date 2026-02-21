# OKRMD Backlog Item Template

**OKRMD Standard v1.0** · **backlog-item.md**

> This template defines a single Backlog Item — any work that lives outside the planned OKR → Phase → Epic → Story hierarchy.
> Place it at `.okrmd/backlog/{PREFIX}-{nnn}-{slug}.md`.
> Backlog items are orphans by design: they don't require a parent epic, phase, or key result. They can be **retroactively linked** to the hierarchy at any time by filling in the optional parent fields.
>
> **When to use a backlog item instead of a story**: Use a story when the work is planned and belongs to an epic. Use a backlog item when the work is unplanned, urgent, cross-cutting, or doesn't fit neatly into an existing epic.

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `{PREFIX}-{nnn}` | Prefix from `config.md` + sequence number (e.g. `BUG-042`, `INC-007`, `ADH-015`) |
| Title | `___` | Short, descriptive name |
| Type | `___` | Must match a registered prefix in `config.md` (see reference below) |
| Status | `triage` | `triage` · `ready` · `in-progress` · `review` · `done` · `blocked` · `wont-fix` |
| Priority | `___` | `critical` · `high` · `medium` · `low` |
| Severity | `___` | `P0` · `P1` · `P2` · `P3` — required for `BUG` and `INC`, optional for others |
| Created | `YYYY-MM-DD` | |
| Updated | `YYYY-MM-DD` | |
| Started | `___` | Date work began |
| Completed | `___` | Date item reached `done` or `wont-fix` |

### Type Quick Reference

> Full prefix catalog is in `config.md`. Common types:

| Prefix | Type | When to use |
|--------|------|-------------|
| `BUG` | Bug | Defect in existing functionality |
| `INC` | Incident | Production outage or degradation |
| `ADH` | Ad-hoc | Unplanned stakeholder or client request |
| `TDB` | Tech Debt | Refactoring, cleanup, performance improvement |
| `SPK` | Spike | Timeboxed research or investigation |
| `SEC` | Security | Vulnerability or hardening task |
| `SUP` | Support | Customer support escalation |
| `FRQ` | Feature Request | Feature request not yet assigned to an epic |
| `POL` | Policy | Policy creation, review, or update |
| `CMP` | Campaign | Marketing campaign task |
| `IMP` | Improvement | Process or quality improvement |
| _other_ | _see config.md_ | _All registered prefixes are valid_ |

### Assignment

| Field | Value | Instructions |
|-------|-------|--------------|
| Assignee | `___` | Human name or agent name |
| Reviewer | `___` | Who reviews the output |
| Autonomy | `___` | `A1`–`A5` for this item |
| Cycle | `[[C{nn}]]` | Cycle this item is assigned to, if any |

### Agent-Specific Fields

> Fill when the assignee is an AI agent. Leave blank for human-assigned items.

| Field | Value | Instructions |
|-------|-------|--------------|
| Agent model | `___` | Model identifier |
| Token budget | `___` | Max tokens for this item |
| Tools allowed | `___` | Comma-separated |
| Output format | `___` | Expected deliverable type |

### Optional Parent Links

> Backlog items start as orphans. Fill these to link into the hierarchy retroactively.

| Field | Value | Instructions |
|-------|-------|--------------|
| Epic | `[[E{n}]]` | If this item logically belongs to an existing epic |
| Phase | `[[P{n}]]` | If this item relates to a specific phase |
| Key Result | `[[KR-___]]` | If this item directly impacts a KR metric |
| Objective | `[[O{n}]]` | If this item relates to a strategic objective |
| PRD | `[[PRD-___]]` | If this item traces back to a PRD requirement |
| Promoted to story | `[[S{e}.{n}]]` | If this backlog item was promoted to a full story |

> **Promotion**: When a backlog item grows in scope and needs full story treatment, create a story file in the appropriate epic folder, set its status to `draft`, and link it here. The backlog item's status becomes `done` with a completion note referencing the new story.

---

## Description

> Describe the item clearly. What happened, what needs to happen, or what needs to be investigated. An assignee (human or agent) should understand the full picture from this section alone.

`___`

---

## Type-Specific Sections

> Use the section below that matches your backlog item type. Delete the others or leave them blank.

---

### Bug (`BUG`)

#### Steps to Reproduce

1. `___`
2. `___`
3. `___`
4. → **Actual result**: `___`

#### Expected Behavior

`___`

#### Environment

| Field | Value |
|-------|-------|
| Browser / Client | `___` |
| OS / Platform | `___` |
| Version / Build | `___` |
| User role / Account | `___` |
| Environment | `production` / `staging` / `development` |

#### Error Details

> Console errors, stack traces, log entries, screenshots, or relevant output.

```
___
```

#### Root Cause

> Filled by assignee during investigation.

`___`

#### Fix Description

> Filled by assignee after implementing the fix.

`___`

---

### Incident (`INC`)

#### Incident Timeline

| Time (UTC) | Event |
|------------|-------|
| `___` | Incident detected — `___` |
| `___` | First response — `___` |
| `___` | Mitigation applied — `___` |
| `___` | Root cause identified — `___` |
| `___` | Fully resolved — `___` |

#### Impact

| Field | Value |
|-------|-------|
| Users affected | `___` |
| Services affected | `___` |
| Revenue impact | `___` |
| Data loss | `yes` / `no` — details: `___` |
| SLA breach | `yes` / `no` — details: `___` |

#### Root Cause

`___`

#### Mitigation Applied

`___`

#### Permanent Fix

`___`

#### Post-Incident Actions

> Preventive measures to avoid recurrence.

- [ ] `___`
- [ ] `___`
- [ ] `___`

---

### Spike / Research (`SPK`)

#### Research Question

> What specific question(s) does this spike aim to answer?

`___`

#### Timebox

| Field | Value | Instructions |
|-------|-------|--------------|
| Max pulses | `___` | Hard limit — stop and report findings when reached |
| Max duration | `___` | Calendar time limit (e.g. "2 days") |

> **Spike rule**: A spike must be timeboxed. When the timebox expires, document findings regardless of completeness. Spikes that need more time become new spikes or are promoted to stories.

#### Findings

> Filled by assignee during/after investigation.

`___`

#### Recommendation

> What should the team do based on the findings?

`___`

#### Decision

> What was decided based on the recommendation?

| Field | Value |
|-------|-------|
| Decision | `___` |
| Decided by | `___` |
| Date | `YYYY-MM-DD` |
| Follow-up work | `[[___]]` or `none` |

---

### Feature Request (`FRQ`)

#### Requested By

| Field | Value |
|-------|-------|
| Source | `customer` / `internal` / `stakeholder` / `agent` |
| Contact | `___` |
| Date requested | `YYYY-MM-DD` |

#### Request Details

`___`

#### Business Case

> Why should this be built? What value does it deliver?

`___`

#### Sizing Estimate

| Field | Value |
|-------|-------|
| T-shirt size | `XS` / `S` / `M` / `L` / `XL` |
| Estimated pulses | `___` |
| Recommended phase | `[[P{n}]]` or `future` |

#### Disposition

| Field | Value |
|-------|-------|
| Decision | `accept` / `defer` / `decline` |
| Rationale | `___` |
| Promoted to | `[[S{e}.{n}]]` or `[[E{n}]]` or `___` |

---

### Ad-Hoc / General (`ADH`, `IMP`, `CMP`, `POL`, `SUP`, and all other types)

#### Background

> Why is this needed now? What triggered it?

`___`

#### Desired Outcome

> What does "done" look like for this item?

`___`

#### Constraints

> Time limits, budget limits, dependencies, or other constraints.

`___`

---

## Tasks

> Break the work into concrete action items. Keep it simpler than a full story — backlog items are typically smaller.

- [ ] `___`
- [ ] `___`
- [ ] `___`

---

## Acceptance Criteria

> Conditions for this item to be considered done.

- [ ] `___`
- [ ] `___`
- [ ] `___`

---

## Definition of Done

- [ ] All acceptance criteria met
- [ ] All tasks checked off
- [ ] Reviewed by `___` (reviewer)
- [ ] No regressions introduced
- [ ] `___` _(add item-specific criteria)_

---

## Review Notes

> Filled by reviewer.

### Reviewer: `___`

### Verdict: `___`

> `approved` · `changes-requested` · `rejected`

### Feedback

`___`

---

## Completion Notes

> Filled by assignee upon completion.

### What was done

`___`

### Follow-up items

| Item | Type | Created as |
|------|------|-----------|
| `___` | `___` | `[[___]]` or `pending` |

---

## File List

> Files created, modified, or deleted by this item.

| File | Action | Notes |
|------|--------|-------|
| `___` | `created` / `modified` / `deleted` | `___` |

---

## Pulse Log Summary

| Date | Worker | Pulses | Tokens (if agent) | Notes |
|------|--------|--------|--------------------|-------|
| `YYYY-MM-DD` | `___` | `___` | `___` | `___` |
| **Total** | | **___** | **___** | |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Backlog item created |
