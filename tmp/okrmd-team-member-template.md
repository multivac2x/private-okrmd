# OKRMD Team Member Profile Template

**OKRMD Standard v1.0** · **team-member.md**

> This template defines a single human team member's profile.
> Place it at `.okrmd/team/{name}.md`.
> A Team Member Profile tells the team (and agents) who this person is, what they're responsible for, how they prefer to work, and how to collaborate with them effectively. It answers: *"Who is this teammate, and how do I work well with them?"*
>
> **Privacy note**: This profile contains professional information relevant to project execution. Do not include personal information beyond what the team member consents to share. The team member should own and maintain their own profile.

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| Name | `___` | Display name used in assignments and references |
| Handle | `___` | Short identifier for mentions and filenames (e.g. `alice`, `bob-k`) |
| Role | `___` | Primary role (e.g. "Backend Engineer", "Product Manager", "Designer") |
| Team | `___` | Team or department, if applicable |
| Status | `active` | `active` · `away` · `part-time` · `offboarding` · `departed` |
| Joined | `YYYY-MM-DD` | Date joined the project |
| Updated | `YYYY-MM-DD` | Date of last profile update |

---

## Responsibilities

### Primary

> Core responsibilities — what this person is accountable for.

- `___`
- `___`
- `___`

### Secondary

> Additional responsibilities this person contributes to but doesn't own.

- `___`
- `___`

### OKRMD Role(s)

> Specific roles within the OKRMD workflow.

| Role | Scope | Notes |
|------|-------|-------|
| `___` | `___` | `___` |

> **Common OKRMD roles**: Objective owner, KR owner, Phase owner, Epic owner, Story assignee, Story reviewer, Cycle lead, Agent supervisor, Retrospective facilitator.

---

## Skills & Expertise

### Domain Expertise

| Domain | Level | Notes |
|--------|-------|-------|
| `___` | `expert` / `proficient` / `learning` | `___` |
| `___` | | |
| `___` | | |

### Technical Skills

| Skill | Level | Notes |
|-------|-------|-------|
| `___` | `expert` / `proficient` / `learning` | `___` |
| `___` | | |
| `___` | | |

> **Why this matters for OKRMD**: Skills inform story assignment. When an agent's output needs review, the reviewer should have sufficient expertise in the relevant domain. When a story requires a specific skill, this profile helps identify the right assignee.

---

## Capacity & Availability

### Standard Availability

| Field | Value | Instructions |
|-------|-------|--------------|
| Working days | `___` | e.g. `Mon–Fri`, `Mon–Thu`, `Tue–Sat` |
| Working hours | `___` | e.g. `09:00–17:30 CET`, `flexible` |
| Timezone | `___` | e.g. `CET (UTC+1)`, `PST (UTC-8)` |
| Pulses per day (target) | `___` | Realistic daily pulse target (typically 6–8) |
| Deep Pulse preference | `yes` / `no` | Prefers 50–90 min deep pulses over standard 25 min |
| Best focus hours | `___` | When this person does their best deep work (e.g. `09:00–12:00`) |

### Current Availability

> Update this section when availability changes. Agents and cycle planners check this before making assignments.

| Field | Value |
|-------|-------|
| Current status | `available` / `limited` / `unavailable` |
| Exceptions | `___` (e.g. "PTO Feb 20–22", "half-days this week") |
| Return date | `___` (if away) |

### Recurring Commitments

> Meetings, ceremonies, or obligations that reduce available pulse time.

| Commitment | Frequency | Duration | Notes |
|-----------|-----------|----------|-------|
| `___` | `daily` / `weekly` / `biweekly` / `monthly` | `___` | `___` |
| `___` | | | |

---

## Working Preferences

> How this person prefers to work. Agents and collaborators should respect these preferences when possible.

### Communication

| Field | Value | Instructions |
|-------|-------|--------------|
| Preferred channel | `___` | e.g. `Slack`, `email`, `in-person`, `async in files` |
| Response time expectation | `___` | e.g. `within 2 hours during work hours`, `next business day` |
| Notification preference | `___` | e.g. `tag in PR only`, `Slack for blockers, email for FYI` |
| Meeting preference | `___` | e.g. `async-first`, `prefers video calls`, `no meetings before 10am` |

### Code Review / Work Review

| Field | Value | Instructions |
|-------|-------|--------------|
| Review turnaround | `___` | Typical time to review a PR or deliverable (e.g. `same day`, `24 hours`) |
| Review style | `___` | e.g. `thorough line-by-line`, `high-level architecture focus`, `test-focused` |
| Feedback format preference | `___` | e.g. `inline comments`, `summary + action items`, `verbal walkthrough` |

### Agent Collaboration

> How this person prefers to work with AI agents.

| Field | Value | Instructions |
|-------|-------|--------------|
| Agent review comfort | `___` | Comfort level reviewing agent output (e.g. `high — reviews daily`, `moderate`, `learning`) |
| Preferred agent autonomy | `___` | Typical A-level this person sets for agent-assigned work (e.g. `A2–A3`) |
| Agent supervision style | `___` | e.g. `reviews every PR`, `spot-checks weekly`, `reviews only flagged items` |
| Agent tools this person manages | `___` | e.g. `claude-code`, `devin` — agents this person is primary supervisor for |

---

## Pulse Preferences

> Personal Pulse settings that may differ from project defaults in `config.md`.

| Field | Value | Instructions |
|-------|-------|--------------|
| Standard Pulse duration | `___` | Personal preference (default: `25 min`) |
| Deep Pulse duration | `___` | Personal preference (default: `50 min`) |
| Short rest | `___` | Personal preference (default: `5 min`) |
| Long rest | `___` | Personal preference (default: `15 min`) |
| Long rest frequency | `___` | Pulses before long rest (default: `4`) |
| Pulse tracking method | `___` | e.g. `manual in .md file`, `timer app`, `Pulse device`, `honor system` |

---

## Objectives & Assignments

### Current OKR Ownership

| Type | ID | Title | Role |
|------|-----|-------|------|
| Objective | `[[O{n}]]` | `___` | `owner` / `contributor` |
| Key Result | `[[KR-___]]` | `___` | `owner` / `contributor` |
| Phase | `[[P{n}]]` | `___` | `owner` / `contributor` |
| Epic | `[[E{n}]]` | `___` | `owner` / `contributor` |

### Current Cycle Assignments

| Cycle | Stories / Items | Role | Status |
|-------|----------------|------|--------|
| `[[C{nn}]]` | `___` | `assignee` / `reviewer` | `___` |

> This section is updated at the start of each cycle during planning.

---

## Performance & Growth

### Velocity History

| Cycle | Pulses logged | Stories completed | Stories reviewed | Notes |
|-------|--------------|-------------------|-----------------|-------|
| `[[C{nn}]]` | `___` | `___` | `___` | `___` |
| `[[C{nn}]]` | | | | |
| `[[C{nn}]]` | | | | |

### Growth Areas

> Skills or capabilities this person is actively developing. Relevant for stretch assignments and learning-oriented task allocation.

| Area | Current level | Target level | Plan |
|------|-------------|-------------|------|
| `___` | `___` | `___` | `___` |
| `___` | | | |

### Mentoring & Knowledge Sharing

| Field | Value |
|-------|-------|
| Can mentor others in | `___` |
| Seeking mentorship in | `___` |
| Knowledge sharing contributions | `___` (e.g. "wrote team guide on OAuth patterns", "runs weekly architecture review") |

---

## Emergency & Escalation

| Field | Value | Instructions |
|-------|-------|--------------|
| Escalation contact | `___` | Who to contact if this person is unavailable and something is urgent |
| Backup for | `___` | Who this person can cover for (e.g. "alice — backend reviews") |
| Backed up by | `___` | Who covers for this person when away |

---

## Notes

> Any additional context that helps the team (and agents) work effectively with this person.

`___`

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Profile created |
