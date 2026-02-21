# OKRMD Story Template

**OKRMD Standard v1.0** · **story.md**

> This template defines a single Story.
> Place it at `.okrmd/epics/E{n}-{slug}/S{e}.{n}-{slug}.md` — inside its parent epic folder.
> A Story is the primary unit of work in OKRMD — a self-contained deliverable that one person or agent can complete in one to several days. It answers: *"What exactly needs to be built, and how do I know it's done?"*
>
> **Self-contained principle**: A story file must include enough context that an assignee (human or agent) can begin working without asking questions or reading other files. Reference the epic's `_epic.md` and the PRD for background, but embed the essential details directly.

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `S{e}.{n}` | Epic number + story sequence (e.g. `S2.1`, `S2.10`) |
| Title | `___` | Descriptive name (e.g. "Alert System Foundation (Backend)") |
| Epic | `[[E{n}]]` | Parent epic. Optional — stories can be orphans in `backlog/`. |
| Status | `draft` | `draft` · `ready` · `in-progress` · `review` · `done` · `blocked` |
| Priority | `medium` | `critical` · `high` · `medium` · `low` |
| Created | `YYYY-MM-DD` | |
| Updated | `YYYY-MM-DD` | |
| Started | `___` | Date work began |
| Completed | `___` | Date story reached `done` |

### Assignment

| Field | Value | Instructions |
|-------|-------|--------------|
| Assignee | `___` | Human name or agent name (e.g. `alice`, `claude-code`) |
| Reviewer | `___` | Who reviews the output (name or `[[profile]]` link) |
| Autonomy | `___` | `A1`–`A5` per this story. Defaults to epic's `default autonomy` if blank. |
| Cycle | `[[C{nn}]]` | Which cycle this story is assigned to |

### Agent-Specific Fields

> Fill these when the assignee is an AI agent. Leave blank for human-assigned stories.

| Field | Value | Instructions |
|-------|-------|--------------|
| Agent model | `___` | Model identifier (e.g. `claude-sonnet-4`, `devin`) |
| Token budget | `___` | Max tokens for this story (e.g. `100000`) |
| Tools allowed | `___` | Comma-separated (e.g. `bash, file_edit, web_search`) |
| Output format | `___` | Expected deliverable type (e.g. `code + tests`, `document`, `analysis`) |
| Max pulses | `___` | Maximum agent pulses before requiring human check-in |

### Estimation

| Field | Value | Instructions |
|-------|-------|--------------|
| Estimate (pulses) | `___` | Estimated pulses to complete (human or agent) |
| Estimate (story points) | `___` | If using story points (see `config.md` estimation method) |
| Actual pulses | `___` | Filled during/after execution from pulse logs |

### Git

| Field | Value | Instructions |
|-------|-------|--------------|
| Branch | `___` | Git branch name (e.g. `feature/S2.1-alert-backend`) |
| PR | `___` | Pull request URL or number, when created |

### Dependencies

| Field | Value | Instructions |
|-------|-------|--------------|
| Depends on | `___` | Stories that must be done before this one (e.g. `[[S1.1]]`, `[[S2.3]]`) |
| Blocks | `___` | Stories that cannot start until this one is done (e.g. `[[S2.2]]`) |

---

## Story

> Write the story statement. Use the "As a... I need... so that..." format when it fits, or use a direct description. The statement should make the purpose and value clear in 1–3 sentences.

`___`

---

## Context

> Background information that helps the assignee understand why this story exists and how it fits into the bigger picture. Reference the epic and PRD but include the essential points directly — don't force the assignee to read five other files before starting.

`___`

---

## Acceptance Criteria

> Conditions that must ALL be true for this story to be considered done. Each criterion should be independently testable. Write them as checkboxes — the assignee checks them off as they're met.

- [ ] `___`
- [ ] `___`
- [ ] `___`
- [ ] `___`
- [ ] `___`

> **Guidelines for good acceptance criteria**:
> - Start with a verb (e.g. "Returns paginated results", "Displays error message")
> - Be specific enough that two people would agree whether it's met
> - Include both happy path and error/edge cases
> - For agents: include measurable thresholds (e.g. "Tests achieve 90%+ coverage" not "Tests are comprehensive")

---

## Tasks / Subtasks

> Break the story into concrete action items. Group by area when the story spans multiple concerns. Use nested checkboxes for subtasks.

### `___` (Task Group Name)

- [ ] `___`
  - [ ] `___`
  - [ ] `___`
- [ ] `___`
- [ ] `___`

### `___` (Task Group Name)

- [ ] `___`
  - [ ] `___`
  - [ ] `___`
- [ ] `___`

### Testing

- [ ] `___`
- [ ] `___`
- [ ] `___`

> **Granularity guidance**: Tasks should be completable in 1–4 pulses. If a task would take more than 4 pulses, it probably needs to be broken into subtasks or split into a separate story.

---

## Dev Notes

> Technical notes, architecture decisions, implementation hints, and gotchas specific to this story. This section is the "how" — it helps the assignee make good decisions without needing to ask.

### Architecture / Approach

`___`

### Key Decisions

| Decision | Choice | Rationale |
|----------|--------|-----------|
| `___` | `___` | `___` |

### Gotchas / Warnings

> Things that are easy to get wrong or that have tripped people up before.

`___`

### Performance Considerations

`___`

### Security Considerations

`___`

---

## Scope Boundaries

### In Scope

> What this story covers. Be precise — especially important for agents who might try to solve adjacent problems.

- `___`
- `___`

### Out of Scope

> What this story explicitly does NOT cover. Reference other stories or future work where appropriate.

- `___`
- `___`

---

## Cross-References

### Related Stories

| Story | Relationship | Notes |
|-------|-------------|-------|
| `[[S{e}.{n}]]` | `depends-on` / `blocks` / `related` / `replaces` | `___` |
| | | |

### Related Documents

| Document | Section | Why relevant |
|----------|---------|-------------|
| `[[PRD-___]]` | `___` | `___` |
| `[[E{n}/_epic.md]]` | `___` | `___` |
| `___` | `___` | `___` |

---

## Definition of Done

> All of the following must be true for this story to move to `done` status. Start with the standard checklist and add story-specific criteria.

- [ ] All acceptance criteria met
- [ ] All tasks/subtasks checked off
- [ ] Code/work reviewed by `___` (reviewer)
- [ ] No open P0/P1 bugs related to this story
- [ ] `___` _(add story-specific criteria)_
- [ ] `___`

---

## Review Notes

> Filled by the reviewer when the story is in `review` status.

### Review Date: `YYYY-MM-DD`

### Reviewer: `___`

### Verdict: `___`

> `approved` · `changes-requested` · `rejected`

### Feedback

`___`

### Changes Requested

> If verdict is `changes-requested`, list specific items that need to be addressed.

- [ ] `___`
- [ ] `___`

---

## Completion Notes

> Filled by the assignee upon completing the story. Captures what was actually built, any deviations from the plan, and anything the next person should know.

### What was built

`___`

### Deviations from plan

> Did the implementation differ from what was originally specified? If yes, explain what changed and why.

`___`

### Known limitations

> Anything that works but isn't ideal, tech debt introduced, or edge cases not covered.

`___`

### Follow-up items

> Work that was discovered during implementation but is out of scope for this story. Create backlog items or note them for future stories.

| Item | Type | Created as |
|------|------|-----------|
| `___` | `bug` / `tech-debt` / `feature` / `improvement` | `[[___]]` or `pending` |
| | | |

---

## File List

> All files created, modified, or deleted by this story. Helps reviewers know what to look at and provides an audit trail.

| File | Action | Notes |
|------|--------|-------|
| `___` | `created` / `modified` / `deleted` | `___` |
| `___` | | |
| `___` | | |

---

## Pulse Log Summary

> Aggregated from individual pulse logs in `.okrmd/pulses/`. Provides a quick view of effort spent on this story.

| Date | Worker | Pulses | Tokens (if agent) | Notes |
|------|--------|--------|--------------------|-------|
| `YYYY-MM-DD` | `___` | `___` | `___` | `___` |
| | | | | |
| **Total** | | **___** | **___** | |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Story created |
