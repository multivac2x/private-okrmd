# OKRMD Key Result Template

**OKRMD Standard v1.0** · **key-result.md**

> This template defines a single Key Result.
> Place it at `.okrmd/key-results/KR-{obj}.{n}-{slug}.md`.
> A Key Result is a quantitative, measurable outcome that proves an Objective is being achieved. It answers: *"How do we know we're getting there?"*

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `KR-{obj}.{n}` | Parent objective number + KR sequence (e.g. `KR-1.1`, `KR-2.3`) |
| Title | `___` | Short description including the metric (e.g. "Increase MRR from $180K to $234K") |
| Objective | `[[O{n}]]` | Link to parent objective |
| Status | `not-started` | `not-started` · `in-progress` · `achieved` · `missed` |
| Owner | `___` | Person accountable for this key result (name or `[[profile]]` link) |
| Contributors | `___` | Others actively working toward this KR (humans and/or agents) |
| Created | `YYYY-MM-DD` | Date this key result was defined |
| Updated | `YYYY-MM-DD` | Date of last update |

---

## Metric

| Field | Value | Instructions |
|-------|-------|--------------|
| Metric name | `___` | What is being measured (e.g. "Monthly Recurring Revenue") |
| Unit | `___` | Unit of measurement (e.g. `USD`, `%`, `count`, `seconds`, `NPS score`) |
| Start value | `___` | Baseline at the beginning of the OKR cycle |
| Target value | `___` | Target to achieve by end of cycle |
| Current value | `___` | Latest measured value |
| Direction | `increase` | `increase` (higher is better) or `decrease` (lower is better) |
| Score | `0.0` | Calculated: `(current - start) / (target - start)` for increase; inverse for decrease. Capped at 1.0. |

> **Scoring note**: For aspirational KRs, a score of 0.7 is considered successful. For committed KRs, the target is 1.0. A score above 1.0 may indicate the target was not ambitious enough.

### Measurement Method

> How is this metric collected? Specify the data source, frequency, and who/what is responsible for updating it. This ensures both humans and agents know where the truth lives.

| Field | Value | Instructions |
|-------|-------|--------------|
| Data source | `___` | Where the metric comes from (e.g. "Stripe dashboard", "Google Analytics", "internal DB query") |
| Measurement frequency | `___` | How often the metric is updated (e.g. `daily`, `weekly`, `monthly`) |
| Measured by | `___` | Who or what updates the value (e.g. "finance team", "automated script", `[[agent-name]]`) |
| Dashboard link | `___` | Optional: URL to live dashboard or report |

---

## Key Result Statement

> Write 1–3 sentences describing what this Key Result means in plain language. A new team member or agent should be able to read this and understand what success looks like, without needing to interpret the numbers alone.

`___`

---

## Phases

> List the Phases that contribute to achieving this Key Result. Each Phase has its own file in `.okrmd/phases/`. Not all KRs require phases — small KRs may link directly to epics.

| Phase | Title | Target contribution | Status |
|-------|-------|--------------------|--------|
| `[[P{n}-___]]` | `___` | `___` | `planned` |
| `[[P{n}-___]]` | `___` | `___` | `planned` |

> **Target contribution**: What portion of the KR does this phase aim to deliver? (e.g. "+$20K MRR", "reduce from 5.2% to 4.0%", "first 50 users onboarded")

---

## Initiatives & Epics

> If this KR does not use phases, or if you want a flat view of all work contributing to the KR regardless of phase, list epics and initiatives here.

| Epic / Initiative | Phase | Status | Impact |
|-------------------|-------|--------|--------|
| `[[E{n}]]` | `[[P{n}]]` or `—` | `___` | `___` |
| `[[E{n}]]` | `[[P{n}]]` or `—` | `___` | `___` |

> **Impact**: Brief description of how this epic moves the KR metric (e.g. "Enables mid-market pricing tier → new revenue stream")

---

## Dependencies & Risks

| Type | Description | Mitigation | Status |
|------|-------------|------------|--------|
| Dependency | `___` | `___` | `open` / `resolved` |
| Risk | `___` | `___` | `open` / `mitigated` / `occurred` |

> List anything that could prevent this KR from being achieved. Dependencies are things you need from others. Risks are things that might go wrong.

---

## Tracking Log

> Update this table at each measurement cadence. This is the data trail that feeds the KR score and the parent Objective's review log.

| Date | Value | Score | Delta | Notes |
|------|-------|-------|-------|-------|
| `YYYY-MM-DD` | `___` | `0.0` | `—` | _Baseline_ |
| | | | | |
| | | | | |
| | | | | |

> **Delta**: Change since last measurement. Useful for spotting trends — accelerating, decelerating, or flat.

---

## Leading Indicators

> Optional but recommended. Leading indicators are early signals that predict whether the KR will be achieved, before the final metric moves. They give you time to course-correct.

| Indicator | Current | Target | Correlation | Source |
|-----------|---------|--------|-------------|--------|
| `___` | `___` | `___` | `___` | `___` |
| `___` | `___` | `___` | `___` | `___` |

> **Example**: If the KR is "Increase MRR to $234K", a leading indicator might be "Number of mid-market trials started this week" — trials lead to conversions which lead to MRR.

---

## Quarter-End Review

> Filled in at the end of the OKR cycle alongside the parent Objective review.

### Final Score: `___` / 1.0

### Final Value: `___` (target was `___`)

### Outcome

> `achieved` · `missed` · `partially achieved` — and why.

`___`

### What moved the metric

> What actions, stories, or events had the most impact on the metric — positive or negative?

`___`

### What would you do differently

> Lessons for setting and pursuing this type of KR in future cycles.

`___`

### Carry-forward

> Does this KR continue next quarter (with a new target), get replaced, or get retired?

| Decision | Details |
|----------|---------|
| `continue` / `replace` / `retire` | `___` |
| Next quarter target | `___` |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Key Result created |
