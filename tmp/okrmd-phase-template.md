# OKRMD Phase Template

**OKRMD Standard v1.0** · **phase.md**

> This template defines a single Phase.
> Place it at `.okrmd/phases/P{n}-{slug}.md`.
> A Phase is a delivery gate — a sequential, shippable increment that groups epics into a coherent release. It answers: *"What do we ship next, and how do we know it's ready?"*

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `P{n}` | Phase sequence number (e.g. `P1`, `P2`, `P3`) |
| Title | `___` | Descriptive name (e.g. "Phase 1: MVP — Core Platform") |
| Status | `planned` | `planned` · `in-progress` · `shipped` · `cancelled` |
| Key Result | `[[KR-___]]` | Parent Key Result this phase contributes to. Optional — phases can be orphans. |
| Objective | `[[O{n}]]` | Parent Objective, if linking directly (when no KR applies) |
| Order | `___` | Sequence within the parent KR or project (e.g. `1`, `2`, `3`) |
| Owner | `___` | Person accountable for this phase (name or `[[profile]]` link) |
| Target date | `YYYY-MM-DD` | Target completion date |
| Actual date | `___` | Actual ship date (filled when shipped) |
| Created | `YYYY-MM-DD` | Date this phase was defined |
| Updated | `YYYY-MM-DD` | Date of last update |

---

## Phase Description

> Write 2–5 sentences describing what this phase delivers and why it's sequenced at this position. A team member (or agent) joining mid-project should understand what this phase achieves, what came before it, and what comes after.

`___`

---

## Target Contribution

> What portion of the parent Key Result does this phase aim to deliver? Be specific with numbers where possible.

| Field | Value | Instructions |
|-------|-------|--------------|
| KR metric at phase start | `___` | Expected KR value when this phase begins |
| KR metric at phase end | `___` | Expected KR value when this phase ships |
| Expected contribution | `___` | The delta (e.g. "+$20K MRR", "reduce latency from 800ms to 400ms") |

> If this phase is an orphan (no parent KR), describe the business value it delivers instead.

---

## Phase Dependencies

> What must be true before this phase can begin? List prior phases, external dependencies, and prerequisites.

| Dependency | Type | Status | Notes |
|------------|------|--------|-------|
| `___` | `prior-phase` / `external` / `technical` / `business` | `met` / `pending` / `blocked` | `___` |
| `___` | | | |

---

## Epics in This Phase

> List all epics included in this phase. Each epic has its own folder in `.okrmd/epics/`. Order them by priority or logical sequence.

| # | Epic | Title | Owner | Status | Stories | Done |
|---|------|-------|-------|--------|---------|------|
| 1 | `[[E{n}]]` | `___` | `___` | `not-started` | `___` | `___` |
| 2 | `[[E{n}]]` | `___` | `___` | `not-started` | `___` | `___` |
| 3 | `[[E{n}]]` | `___` | `___` | `not-started` | `___` | `___` |

> **Stories / Done**: Total story count and completed count (e.g. `5` / `2`). Updated as work progresses.

---

## Gate Criteria

> These are the conditions that must ALL be true before this phase is considered shippable. They are the "definition of done" for the phase. Be specific — vague gates lead to vague decisions.

- [ ] `___`
- [ ] `___`
- [ ] `___`
- [ ] `___`

> **Guidelines for good gate criteria**:
> - Testable: someone can verify it's true or false
> - Specific: no room for interpretation (e.g. "all P0/P1 bugs resolved" not "quality is good")
> - Outcome-oriented: what must be true in the product or business, not just "code is merged"

### Quality Gates

> Minimum quality standards that apply to all work in this phase.

| Gate | Requirement | Verified by |
|------|------------|-------------|
| Test coverage | `___` | _e.g. CI pipeline, `[[agent-name]]`_ |
| Performance | `___` | _e.g. load test results_ |
| Security | `___` | _e.g. security scan, manual audit_ |
| Documentation | `___` | _e.g. API docs complete_ |
| Accessibility | `___` | _e.g. WCAG 2.1 AA compliance_ |

---

## Risks

> What could prevent this phase from shipping on time or meeting its gate criteria?

| Risk | Probability | Impact | Mitigation | Owner | Status |
|------|-------------|--------|------------|-------|--------|
| `___` | `high` / `medium` / `low` | `high` / `medium` / `low` | `___` | `___` | `open` / `mitigated` / `occurred` |
| `___` | | | | | |

---

## Timeline

> Map this phase against cycles (sprints). This shows which cycles contribute to this phase and provides a rough timeline.

| Cycle | Dates | Focus | Stories planned |
|-------|-------|-------|----------------|
| `[[C{nn}]]` | `___` – `___` | `___` | `___` |
| `[[C{nn}]]` | `___` – `___` | `___` | `___` |
| `[[C{nn}]]` | `___` – `___` | `___` | `___` |

> **Note**: A phase spans multiple cycles. A cycle may contain stories from only one phase or from multiple phases if work overlaps during transition.

---

## Scope Changes

> Document any additions, removals, or changes to this phase's scope after initial definition. This prevents scope creep from going unnoticed and provides an audit trail.

| Date | Change | Reason | Approved by |
|------|--------|--------|-------------|
| | | | |

> If an epic is added or removed from the phase, update the Epics table above AND log it here.

---

## Go / No-Go Decision

> Filled in at the phase boundary. This is the gate review — the moment the team decides whether to ship, iterate, or stop.

### Decision: `___`

> `ship` · `iterate` (fix issues, review again) · `pivot` (change direction) · `stop` (cancel remaining phases)

### Date: `YYYY-MM-DD`

### Decision Makers

| Name | Role | Vote |
|------|------|------|
| `___` | `___` | `go` / `no-go` / `conditional` |
| `___` | `___` | |

### Gate Criteria Status at Decision

| Criterion | Met? | Notes |
|-----------|------|-------|
| `___` | `yes` / `no` / `partial` | `___` |
| `___` | | |

### Conditions (if conditional go)

> If the decision is "go with conditions," list what must be resolved post-ship.

`___`

### Rationale

> Why was this decision made? Capture the reasoning for future reference.

`___`

---

## Phase Retrospective

> Filled after the phase ships (or is cancelled). What did we learn from this increment?

### What went well

`___`

### What didn't go well

`___`

### What to change for next phase

`___`

### Metrics

| Metric | Planned | Actual | Notes |
|--------|---------|--------|-------|
| Duration (weeks) | `___` | `___` | |
| Cycles consumed | `___` | `___` | |
| Stories completed | `___` | `___` | |
| Scope changes | `0` | `___` | |
| Gate criteria met on first review | `___` / `___` | | _e.g. 4/5_ |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Phase created |
