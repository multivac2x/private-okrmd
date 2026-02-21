# OKRMD Autonomy Levels (A1–A5) Reference

**OKRMD Standard v0.1** · **Reference Document**

> This document defines the five autonomy levels used in OKRMD to describe how humans and AI agents collaborate on a given work item.
> Every story and backlog item has an `autonomy` field. This guide explains what each level means, when to use it, and how it affects the workflow.

---

## The Scale

> **A1 = maximum AI autonomy. A5 = maximum human autonomy.**
> The "A" stands for Autonomy. A1 reads as "AI" — by design.

| Level | Name | Who Drives | Agent Role | Human Role | Review |
|-------|------|-----------|------------|------------|--------|
| **A1** | Full Auto | Agent | Full execution, self-validation, auto-merge | Monitors dashboards, handles escalations only | Automated checks only |
| **A2** | Supervised Auto | Agent | Full execution, flags decisions | Spot-checks output, approves key decisions | Spot-check review |
| **A3** | Guided Auto | Agent + Human | Drives execution, asks when uncertain | Provides guidance when asked, reviews all output | Required full review |
| **A4** | Co-Pilot | Human | Drafts, generates, suggests on demand | Drives decisions, uses agent as accelerator | Self-review |
| **A5** | Human-Led | Human | Not involved | Full ownership, execution, and review | Self-review or peer review |

---

## Detailed Level Descriptions

### A1 — Full Auto

> The agent works independently from start to finish. Humans are not in the loop unless something goes wrong.

**Workflow:**
```
Agent receives task → Agent executes → Automated tests run →
Tests pass → Auto-merge → Human receives notification
Tests fail → Agent retries → If still fails → Escalate to human
```

**Human involvement**: Near zero. The human monitors a dashboard or receives periodic summaries. Intervention only when automated checks fail or the agent explicitly escalates.

**Requirements for A1**:
- Crystal-clear acceptance criteria with no ambiguity
- Comprehensive automated test suite covering all AC
- Well-defined output format
- Low risk if output is imperfect (can be fixed later)
- Agent has demonstrated consistent quality on similar tasks

**Risk level**: Lowest human oversight. Only appropriate when the cost of an imperfect output is low and automated validation is strong.

---

### A2 — Supervised Auto

> The agent works autonomously but a human spot-checks the output before it ships.

**Workflow:**
```
Agent receives task → Agent executes → Agent flags decisions made →
Agent opens PR/submits output → Human spot-checks (not full review) →
Approve or request changes
```

**Human involvement**: Light review. The human skims the output, checks the flagged decisions, and verifies the overall approach. Not a line-by-line review.

**Requirements for A2**:
- Clear acceptance criteria
- Agent has a track record on similar tasks
- Some automated validation exists
- Moderate risk tolerance
- Human reviewer available within reasonable turnaround

**Risk level**: Low. Agent handles execution; human catches strategic errors.

---

### A3 — Guided Auto

> The agent drives execution but the human reviews everything. The agent asks for guidance when it encounters uncertainty.

**Workflow:**
```
Agent receives task → Agent begins execution →
  If uncertain → Agent pauses, asks human for guidance →
  Human responds → Agent continues →
Agent completes → Full human review → Approve or request changes
```

**Human involvement**: Moderate. The human is available for questions during execution and reviews all output thoroughly before it ships. This is the **default level** for most OKRMD projects.

**Requirements for A3**:
- Well-defined acceptance criteria (some ambiguity acceptable)
- Human reviewer with relevant domain expertise
- Agent has basic familiarity with the domain
- Human available for questions within working hours

**Risk level**: Balanced. The most common and safest level for meaningful work.

---

### A4 — Co-Pilot

> The human drives. The agent accelerates. Think of it as the human using the agent as a power tool.

**Workflow:**
```
Human works on task → Human asks agent for help with specific parts →
Agent drafts/generates/suggests → Human reviews and integrates →
Human makes all decisions → Human self-reviews or requests peer review
```

**Human involvement**: High. The human is in control at all times. The agent is invoked for specific sub-tasks: "draft this function," "generate test cases," "review this paragraph."

**Requirements for A4**:
- Human has expertise in the domain
- Task requires judgment, creativity, or context the agent lacks
- Human wants to move faster but not hand over control
- No specific agent configuration needed — ad-hoc usage

**Risk level**: Very low. Human is making all decisions.

---

### A5 — Human-Led

> No agent involvement. A human does everything.

**Workflow:**
```
Human receives task → Human executes → Human self-reviews or
requests peer review → Human ships
```

**Human involvement**: Complete. The agent is not part of this work item.

**When to use A5**:
- Highly sensitive work (legal, compliance, HR decisions)
- Creative work where human judgment is the entire point
- Strategic decisions (OKR setting, phase gate reviews, hiring)
- Relationship-dependent work (client calls, negotiations)
- Tasks where AI involvement would be inappropriate or counterproductive

**Risk level**: Standard human risk. No AI-specific risks.

---

## Decision Guide

### By Task Characteristics

| Characteristic | Recommended Level |
|---------------|-------------------|
| Automated formatting, linting, code generation from templates | A1 |
| Documentation generation from existing code | A1–A2 |
| Routine CRUD implementation with clear patterns | A2 |
| Feature implementation with clear acceptance criteria | A3 |
| Bug fix with clear reproduction steps | A2–A3 |
| Bug fix requiring investigation | A3–A4 |
| Architecture design or technical decisions | A4–A5 |
| Security-sensitive code (auth, encryption, access control) | A3–A4 |
| Customer-facing copy, UX writing | A4–A5 |
| Novel or first-of-its-kind implementation | A4 |
| Refactoring with comprehensive test coverage | A2 |
| Refactoring without test coverage | A4 |
| Research / spike | A3–A4 |
| Incident first response | A2–A3 |
| Post-incident analysis | A4–A5 |
| Test writing for existing code | A1–A2 |
| Strategic planning, OKR setting | A5 |
| Legal, compliance, policy review | A5 |
| Performance optimization | A3–A4 |
| Data migration | A3 |
| API design | A4 |
| Content creation (blog, marketing) | A3–A4 |
| Translation / localization | A2–A3 |
| Financial analysis / reporting | A4–A5 |

### By Risk Profile

| Risk if wrong | Recommended Level |
|--------------|-------------------|
| Cosmetic / easily reverted | A1–A2 |
| Functional but fixable | A2–A3 |
| User-facing impact | A3 |
| Data integrity at stake | A3–A4 |
| Security implications | A4 |
| Legal / compliance implications | A5 |
| Cannot be easily undone | A4–A5 |

### By Agent Experience

| Agent familiarity with task type | Adjustment |
|----------------------------------|-----------|
| Has done similar tasks 5+ times with >90% pass rate | Can operate 1 level more autonomous |
| Has done similar tasks 1–4 times | Use recommended level |
| First time doing this type of task | Operate 1 level less autonomous |
| Known struggles with this task type | Operate 2 levels less autonomous or assign to human |

---

## Governance

### Setting Autonomy Levels

| Who sets it | When | Scope |
|-------------|------|-------|
| Project config (`config.md`) | Project setup | Default level and max ceiling |
| Epic definition (`_epic.md`) | Epic creation | Default for all stories in this epic |
| Story / backlog item author | Work item creation | Per-item level |
| Cycle planning participants | Cycle planning | Review and adjust per-item levels |

### Inheritance and Override

```
config.md default (e.g. A3)
  └── overridden by epic default (e.g. A2 for security epic)
       └── overridden by story-level setting (e.g. A4 for one complex story)
```

> The most specific level wins. If a story sets `autonomy: A4`, that overrides the epic default and the project default.

### Max Autonomy Ceiling

The `max agent autonomy` in `config.md` is a hard ceiling. No work item can be set to a more autonomous level than this without explicit override approval.

| Scenario | Outcome |
|----------|---------|
| Config max = A2, story set to A2 | Allowed |
| Config max = A2, story set to A1 | **Blocked** — requires override approval |
| Config max = A1, story set to A1 | Allowed (no ceiling in effect) |
| Config max = A3, no story-level set | Uses config default (e.g. A3) |

### Override Process

When a work item needs to exceed the max autonomy ceiling:

1. Author sets the autonomy level and adds a justification in the story's Dev Notes
2. Override approver (defined in `config.md`) reviews the justification
3. If approved, approver notes their approval in the story's Changelog
4. Work proceeds at the overridden level

---

## Adjusting Levels Over Time

Autonomy levels should evolve as the team learns what works.

### Signals to Increase Autonomy (Move Toward A1)

- Agent consistently passes review on first attempt (>90% over 5+ stories)
- Review findings are minor / style-only, not substantive
- Automated test coverage is comprehensive
- Task type is well-understood and repetitive
- Time spent on review exceeds time agent spent on execution

### Signals to Decrease Autonomy (Move Toward A5)

- Agent output frequently needs rework (>30% revision rate)
- Review findings include logic errors, security issues, or missed requirements
- Task requires judgment that agent consistently gets wrong
- Agent hallucinations or incorrect assumptions are occurring
- Stakeholders express concern about quality

### Tracking Autonomy Effectiveness

Track in retrospectives (Human-Agent Collaboration Review section):

| Story | Level Set | Correct Level | Outcome |
|-------|-----------|---------------|---------|
| `[[S2.1]]` | A3 | A3 | Correct — review found only minor issues |
| `[[S2.2]]` | A2 | A3 | Too autonomous — missed edge cases, needed full review |
| `[[S1.3]]` | A3 | A2 | Too restrictive — wasted review time on clean output |

Over time, this data informs agent profile updates and project-wide defaults.

---

## Anti-Patterns

| Anti-Pattern | Problem | Fix |
|-------------|---------|-----|
| "Everything is A1" | Agents ship low-quality work without oversight | Audit failures, tighten to A2–A3 |
| "Everything is A5" | Team doesn't leverage agents, defeats purpose of OKRMD | Identify routine tasks suitable for A1–A2 |
| "A3 for everything" | Default laziness — not thinking about appropriate levels | Review per-task characteristics in cycle planning |
| Autonomy without AC | Agent given A1 but acceptance criteria are vague | Tighten AC first, then set level |
| Ceiling without override process | Max set to A3 but no way to request A2 for appropriate tasks | Define override approver in config |
| Never adjusting levels | Same defaults used quarter after quarter despite evidence | Review in retrospectives, update per cycle |
| Level set by agent | Agent suggests its own autonomy level | Humans always set autonomy levels |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 0.1 | 2026-02-19 | Initial autonomy levels reference |
