# OKRMD Objective Template

**OKRMD Standard v1.0** · **objective.md**

> This template defines a single strategic Objective.
> Place it at `.okrmd/objectives/O{n}-{slug}.md`.
> An Objective is a qualitative, inspirational goal that sets direction for a quarter or year. It answers: *"What are we trying to achieve?"*

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `O{n}` | Unique objective number (e.g. `O1`, `O2`, `O3`) |
| Title | `___` | Short, memorable name (e.g. "Grow recurring revenue") |
| Status | `active` | `active` · `achieved` · `missed` · `abandoned` |
| Scope | `quarterly` | `quarterly` or `annual` |
| Quarter / Year | `___` | e.g. `Q1-2026` or `FY-2026` |
| OKR type | `aspirational` | `aspirational` (target score 0.7) or `committed` (target score 1.0) |
| Owner | `___` | Person accountable for this objective (name or `[[profile]]` link) |
| Score | `0.0` | Current score (0.0–1.0), updated at each review cadence |
| Created | `YYYY-MM-DD` | Date this objective was defined |
| Updated | `YYYY-MM-DD` | Date of last update |

---

## Objective

> Write 1–3 sentences describing the objective. Be qualitative and directional — the "what" and "why", not the "how much." Objectives should be ambitious enough to be motivating but clear enough that anyone on the team (human or agent) can understand the intent.

`___`

---

## Context

> Why does this objective matter right now? What changed in the market, the business, or the team that makes this the right goal? Include any relevant background that helps a new team member (or a newly assigned agent) understand the strategic reasoning.

`___`

---

## Key Results

> List the Key Results that prove this objective is being achieved. Each Key Result has its own file in `.okrmd/key-results/`. Link them here using `[[KR-x.x]]` syntax.

| Key Result | Title | Score | Status |
|------------|-------|-------|--------|
| `[[KR-___]]` | `___` | `0.0` | `not-started` |
| `[[KR-___]]` | `___` | `0.0` | `not-started` |
| `[[KR-___]]` | `___` | `0.0` | `not-started` |

> **Guidelines**: 2–5 Key Results per Objective. Each must be measurable with a number. If you can't measure it, it's not a Key Result — it might be a task or an initiative.

---

## Alignment

> How does this objective connect to the broader organization? Fill in what applies.

| Field | Value | Instructions |
|-------|-------|--------------|
| Parent objective | `___` | Annual objective this rolls up to, if any (e.g. `[[O-annual-1]]`) |
| Related objectives | `___` | Other objectives this interacts with (e.g. `[[O2]]`, `[[O3]]`) |
| Stakeholders | `___` | People or teams with a stake in this outcome |
| Dependencies | `___` | External factors this objective depends on |
| Risks | `___` | Known risks that could prevent achievement |

---

## Review Log

> Update this table at each review cadence (weekly, biweekly, or monthly as set in `config.md`). This is the heartbeat of the OKR process — a regular check that keeps the objective alive rather than forgotten.

| Date | Score | Confidence | Notes |
|------|-------|------------|-------|
| `YYYY-MM-DD` | `0.0` | `___` | _Initial baseline_ |
| | | | |
| | | | |

> **Confidence**: `high` (on track), `medium` (at risk), `low` (off track). This is a subjective human judgment, not a calculated metric. Even when agents execute the work, a human should assess confidence.

---

## Quarter-End Review

> Filled in at the end of the OKR cycle. This section captures what happened, what was learned, and what carries forward.

### Final Score: `___` / 1.0

### What went well

`___`

### What didn't go well

`___`

### Key learnings

`___`

### Carry-forward items

> Anything that should inform next quarter's objectives or remain as ongoing work.

`___`

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Objective created |
