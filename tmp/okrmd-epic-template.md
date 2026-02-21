# OKRMD Epic Template

**OKRMD Standard v1.0** · **_epic.md**

> This template defines a single Epic.
> Place it at `.okrmd/epics/E{n}-{slug}/_epic.md` — always inside its own folder.
> Stories belonging to this epic are placed as sibling files in the same folder.
> An Epic is a large body of work that delivers a meaningful capability. It answers: *"What are we building, and what does it look like when it's done?"*

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `E{n}` | Unique epic number (e.g. `E1`, `E2`, `E12`) |
| Title | `___` | Short, descriptive name (e.g. "Alert System", "User Onboarding") |
| Status | `not-started` | `not-started` · `in-progress` · `done` · `cancelled` |
| Phase | `[[P{n}-___]]` | Parent phase this epic belongs to. Optional — epics can be orphans. |
| Key Result | `[[KR-___]]` | Direct KR link, if applicable (shortcut when no phase exists) |
| PRD | `[[PRD-___]]` | PRD this epic is derived from. Optional. |
| PRD Section | `___` | Specific section of the PRD (e.g. "Section 4.2 — Alert Management") |
| Owner | `___` | Person accountable for this epic (name or `[[profile]]` link) |
| Default autonomy | `___` | Default A1–A5 level for stories in this epic (overridable per story) |
| Created | `YYYY-MM-DD` | Date this epic was defined |
| Updated | `YYYY-MM-DD` | Date of last update |

---

## Epic Description

> Describe what this epic delivers in 3–8 sentences. Include enough context that a team member or agent assigned a story within this epic can understand the bigger picture without reading the full PRD. What capability does this epic add? Who benefits? What changes when it's done?

`___`

---

## Business Value

> Why does this epic matter? Connect it to the business outcome. This section helps prioritize when resources are constrained and helps agents understand the "why" behind their tasks.

| Field | Value |
|-------|-------|
| User impact | `___` |
| Business impact | `___` |
| What happens if we don't build this | `___` |

---

## Scope

### In Scope

> What this epic covers. Be specific.

- `___`
- `___`
- `___`

### Out of Scope

> What this epic explicitly does NOT cover. Reference other epics or future phases where appropriate.

- `___`
- `___`

> **Why this matters for agents**: An agent working on a story in this epic will encounter adjacent problems. This list tells them where to stop and hand off.

---

## Acceptance Criteria (Epic-Level)

> These are the conditions that must ALL be true for the entire epic to be considered done. They are higher-level than individual story acceptance criteria — think of them as the "definition of done" for the capability this epic delivers.

- [ ] `___`
- [ ] `___`
- [ ] `___`
- [ ] `___`

---

## Stories

> List all stories in this epic. Each story is a separate `.md` file in this epic's folder. Order by dependency or logical sequence.

| # | Story | Title | Assignee | Autonomy | Status | Cycle |
|---|-------|-------|----------|----------|--------|-------|
| 1 | `[[S{e}.1]]` | `___` | `___` | `___` | `draft` | `___` |
| 2 | `[[S{e}.2]]` | `___` | `___` | `___` | `draft` | `___` |
| 3 | `[[S{e}.3]]` | `___` | `___` | `___` | `draft` | `___` |

### Story Dependency Map

> If stories have dependencies between them, document the order here. This helps both humans and agents understand what can be parallelized and what must be sequential.

```
S{e}.1 ──→ S{e}.2 ──→ S{e}.4
               │
               └──→ S{e}.3 (can run in parallel with S{e}.2)
```

> Use plain text or ASCII diagrams. Keep it simple — the goal is to show blocking relationships, not every possible connection.

---

## Technical Context

> Technical information that applies across all stories in this epic. Individual stories reference this section rather than repeating it.

### Architecture Notes

> Describe the technical approach, patterns, or architectural decisions relevant to this epic. Reference the PRD architecture section if applicable.

`___`

### Key Technical Decisions

| Decision | Choice | Rationale | Decided by | Date |
|----------|--------|-----------|------------|------|
| `___` | `___` | `___` | `___` | `YYYY-MM-DD` |
| `___` | | | | |

> Document decisions here so agents and future team members don't re-debate settled questions.

### Technology & Tools

| Component | Technology | Notes |
|-----------|-----------|-------|
| `___` | `___` | `___` |
| `___` | `___` | `___` |

### Shared Conventions

> Coding standards, naming patterns, API conventions, or other rules that apply to all stories in this epic.

`___`

---

## Dependencies

### Internal Dependencies

> Other epics, stories, or systems within the project that this epic depends on or is depended upon by.

| Dependency | Direction | Status | Notes |
|-----------|-----------|--------|-------|
| `[[E{n}]]` or `[[S{e}.{n}]]` | `depends-on` / `blocks` | `resolved` / `pending` | `___` |
| | | | |

### External Dependencies

> Things outside the project that this epic requires — third-party APIs, vendor deliverables, other teams, legal approvals, etc.

| Dependency | Owner | Expected date | Status | Notes |
|-----------|-------|---------------|--------|-------|
| `___` | `___` | `YYYY-MM-DD` | `pending` / `resolved` / `blocked` | `___` |
| | | | | |

---

## Risks

| Risk | Probability | Impact | Mitigation | Owner | Status |
|------|-------------|--------|------------|-------|--------|
| `___` | `high` / `medium` / `low` | `high` / `medium` / `low` | `___` | `___` | `open` / `mitigated` / `occurred` |
| | | | | | |

---

## Progress

> Updated regularly as stories complete. Provides a snapshot view without needing to read every story file.

| Metric | Value |
|--------|-------|
| Total stories | `___` |
| Done | `___` |
| In progress | `___` |
| Blocked | `___` |
| Not started | `___` |
| Estimated total pulses | `___` |
| Actual pulses spent | `___` |

### Progress Notes

> Notable milestones, blockers encountered, or scope adjustments during execution.

| Date | Note |
|------|------|
| `YYYY-MM-DD` | `___` |
| | |

---

## Cross-Repository / Cross-Team Coordination

> If this epic requires work across multiple repositories, teams, or systems, document the coordination plan here.

| Repository / Team | Work required | Story / Contact | Status |
|-------------------|--------------|-----------------|--------|
| `___` | `___` | `___` | `pending` / `in-progress` / `done` |
| | | | |

> **Example**: Your epic "Alert System" may require backend work in one repo, frontend in another, and mobile in a third — each with their own stories. Document the contracts and handoff points here.

---

## Definition of Done (Epic-Level)

> All of the following must be true for this epic to move to `done` status.

- [ ] All stories in `done` status
- [ ] All epic-level acceptance criteria met
- [ ] Cross-repository coordination items completed
- [ ] No open P0/P1 bugs related to this epic
- [ ] Documentation updated
- [ ] `___` _(add project-specific criteria)_
- [ ] `___`

---

## Epic Retrospective

> Filled when the epic reaches `done` or `cancelled` status. What did we learn?

### Outcome

> `completed-as-planned` · `completed-with-changes` · `partially-completed` · `cancelled`

`___`

### What went well

`___`

### What didn't go well

`___`

### What to carry forward

> Lessons, patterns, or decisions that should inform future epics.

`___`

### Metrics

| Metric | Planned | Actual | Notes |
|--------|---------|--------|-------|
| Stories | `___` | `___` | |
| Pulses | `___` | `___` | |
| Cycles spanned | `___` | `___` | |
| Scope changes | `0` | `___` | |
| Bugs found post-completion | `0` | `___` | |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Epic created |
