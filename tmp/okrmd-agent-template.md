# OKRMD Agent Profile Template

**OKRMD Standard v1.0** · **agent.md**

> This template defines a single AI Agent's profile.
> Place it at `.okrmd/agents/{agent-name}.md`.
> An Agent Profile tells the team (and other agents) what this agent can do, how to work with it, what its constraints are, and how it has performed historically. It answers: *"What can I expect from this teammate, and how do I set it up for success?"*
>
> **One profile per agent instance**: If you use the same model in different configurations (e.g. Claude Code for backend work vs. Claude Code for documentation), create separate profiles with distinct names (e.g. `claude-code-backend.md`, `claude-code-docs.md`).

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| Name | `___` | Unique agent name used in assignments (e.g. `claude-code`, `devin`, `custom-reviewer`) |
| Model | `___` | Model identifier (e.g. `claude-sonnet-4`, `gpt-4o`, `devin-v2`) |
| Provider | `___` | AI provider (e.g. `anthropic`, `openai`, `cognition`, `custom`) |
| Version | `___` | Model version or snapshot date, if applicable |
| Status | `active` | `active` · `evaluation` · `deprecated` · `retired` |
| Added | `YYYY-MM-DD` | Date this agent was added to the team |
| Updated | `YYYY-MM-DD` | Date of last profile update |

---

## Capabilities

### Context Window

| Field | Value | Instructions |
|-------|-------|--------------|
| Max context tokens | `___` | Maximum tokens the model supports (e.g. `200000`) |
| Effective context tokens | `___` | Practical working limit before quality degrades (often 60–80% of max) |
| Default token budget per pulse | `___` | Standard allocation per focus session |
| Default token budget per story | `___` | Standard allocation per story assignment |

### Tools & Access

> What tools and integrations does this agent have access to?

| Tool / Access | Available | Notes |
|--------------|-----------|-------|
| Bash / terminal | `yes` / `no` | `___` |
| File read | `yes` / `no` | `___` |
| File write / edit | `yes` / `no` | `___` |
| Web search | `yes` / `no` | `___` |
| Web fetch (URLs) | `yes` / `no` | `___` |
| Git operations | `yes` / `no` | `___` |
| Database access | `yes` / `no` | `___` |
| API calls (external) | `yes` / `no` | `___` |
| Image generation | `yes` / `no` | `___` |
| Code execution | `yes` / `no` | `___` |
| `___` | `___` | `___` |

### Strengths

> What this agent does well. Be specific — this helps with task assignment.

- `___`
- `___`
- `___`
- `___`

### Limitations

> What this agent struggles with or cannot do. Equally important as strengths for correct assignment and autonomy level setting.

- `___`
- `___`
- `___`
- `___`

### Supported Languages & Frameworks

> For coding agents. List languages, frameworks, and tools this agent has demonstrated proficiency in.

| Category | Proficient | Functional | Limited |
|----------|-----------|------------|---------|
| Languages | `___` | `___` | `___` |
| Frameworks | `___` | `___` | `___` |
| Databases | `___` | `___` | `___` |
| DevOps / Infra | `___` | `___` | `___` |
| Other | `___` | `___` | `___` |

> **Proficient**: Produces high-quality output consistently. **Functional**: Can produce working output, may need review. **Limited**: Can attempt but output frequently needs significant correction.

### Supported Domains

> For non-coding agents or general-purpose agents. What knowledge domains does this agent handle well?

| Domain | Proficiency | Notes |
|--------|-----------|-------|
| `___` | `proficient` / `functional` / `limited` | `___` |
| `___` | | |

---

## Autonomy Configuration

| Field | Value | Instructions |
|-------|-------|--------------|
| Default autonomy | `___` | Default A1–A5 level for tasks assigned to this agent |
| Max autonomy | `___` | Highest level this agent is approved to operate at |
| Autonomy override approval | `___` | Who can approve this agent operating above max (e.g. `project-lead`) |

### Autonomy Guidelines for This Agent

> Specific guidance on when to assign this agent at different autonomy levels.

| Level | Appropriate for | Not appropriate for |
|-------|----------------|---------------------|
| A1 | `___` | `___` |
| A2 | `___` | `___` |
| A3 | `___` | `___` |
| A4 | `___` | `___` |
| A5 | _N/A — agent not involved_ | _Everything_ |

---

## Operating Instructions

### How to Assign Work

> Step-by-step instructions for assigning a story or backlog item to this agent. Different agents have different interfaces.

1. `___`
2. `___`
3. `___`

### Context Requirements

> What context does this agent need to perform well? What files should be provided? What information must be included?

| Context type | Required / Recommended | Notes |
|-------------|----------------------|-------|
| Story file (full) | `required` | Always provide the complete story `.md` file |
| Epic `_epic.md` | `___` | `___` |
| PRD (relevant section) | `___` | `___` |
| Architecture docs | `___` | `___` |
| Existing codebase access | `___` | `___` |
| Test suite access | `___` | `___` |
| Previous pulse logs | `___` | `___` |
| `___` | `___` | `___` |

### Checkpoint Protocol

> How does this agent save progress between pulses?

| Field | Value | Instructions |
|-------|-------|--------------|
| Checkpoint method | `___` | e.g. `git commit`, `file save`, `session summary` |
| Checkpoint frequency | `___` | e.g. `after each pulse`, `after each task group` |
| Checkpoint format | `___` | e.g. `commit message + pulse log entry` |
| Recovery method | `___` | How to resume after an interrupted session |

### Output Standards

> What standards does this agent's output need to meet?

| Standard | Requirement | Verification |
|----------|------------|-------------|
| Code style | `___` | _e.g. ESLint config, Prettier_ |
| Test coverage | `___` | _e.g. minimum 80%_ |
| Documentation | `___` | _e.g. JSDoc for public functions_ |
| Commit messages | `___` | _e.g. `[{ID}] {message}` format_ |
| PR description | `___` | _e.g. include AC checklist_ |
| `___` | `___` | `___` |

---

## Cost

| Field | Value | Instructions |
|-------|-------|--------------|
| Cost model | `___` | `per-token` / `per-hour` / `per-task` / `subscription` / `free` |
| Input cost | `___` | e.g. `$0.003 / 1K tokens` |
| Output cost | `___` | e.g. `$0.015 / 1K tokens` |
| Average cost per story | `___` | Calculated from history |
| Average cost per pulse | `___` | Calculated from history |
| Monthly budget cap | `___` | Hard spending limit, if any |

---

## Availability & Scheduling

| Field | Value | Instructions |
|-------|-------|--------------|
| Availability | `___` | e.g. `24/7`, `business hours only`, `on-demand` |
| Concurrent sessions | `___` | Can this agent run multiple tasks in parallel? (e.g. `1`, `unlimited`) |
| Queue behavior | `___` | What happens when the agent is busy? (e.g. `queue`, `reject`, `spawn new`) |
| Rate limits | `___` | API rate limits or usage caps to be aware of |
| Maintenance windows | `___` | Known downtime or degradation periods |

---

## Integration

### Platform / Interface

| Field | Value |
|-------|-------|
| Primary interface | `___` (e.g. `CLI`, `API`, `IDE plugin`, `web UI`, `Slack bot`) |
| IDE integration | `___` (e.g. `VS Code`, `Cursor`, `Windsurf`) |
| CI/CD integration | `___` (e.g. `GitHub Actions`, `none`) |
| Notification channel | `___` (e.g. `Slack #agent-updates`, `email`, `none`) |

### MCP Servers / Plugins

> Model Context Protocol servers or plugins this agent has access to.

| MCP Server / Plugin | Purpose | Notes |
|--------------------|---------|-------|
| `___` | `___` | `___` |
| `___` | | |

---

## Performance History

### Summary Metrics

| Metric | All Time | Last 5 Cycles | Trend |
|--------|---------|---------------|-------|
| Stories completed | `___` | `___` | `↑` / `→` / `↓` |
| Average pulses per story | `___` | `___` | |
| Average tokens per story | `___` | `___` | |
| Review pass rate (first attempt) | `___` % | `___` % | |
| Review pass rate (after revision) | `___` % | `___` % | |
| Average review findings | `___` | `___` | |
| Average cost per story | `___` | `___` | |

### Per-Cycle History

| Cycle | Stories | Pulses | Tokens | Pass Rate | Cost | Notes |
|-------|---------|--------|--------|-----------|------|-------|
| `[[C{nn}]]` | `___` | `___` | `___` | `___` % | `___` | `___` |
| `[[C{nn}]]` | | | | | | |
| `[[C{nn}]]` | | | | | | |

### Notable Successes

> Stories or tasks where this agent performed particularly well. Reference for future similar assignments.

| Story / Item | What went well | Autonomy level used |
|-------------|---------------|---------------------|
| `[[___]]` | `___` | `___` |
| `[[___]]` | | |

### Notable Failures

> Stories or tasks where this agent struggled. Reference to avoid repeating mistakes.

| Story / Item | What went wrong | Root cause | Lesson |
|-------------|----------------|------------|--------|
| `[[___]]` | `___` | `___` | `___` |
| `[[___]]` | | | |

---

## Known Issues & Workarounds

> Specific quirks, bugs, or behaviors to be aware of when working with this agent.

| Issue | Workaround | Status |
|-------|-----------|--------|
| `___` | `___` | `persistent` / `intermittent` / `resolved` |
| `___` | | |

---

## Retirement Plan

> When and why this agent would be retired or replaced.

| Field | Value |
|-------|-------|
| Retirement trigger | `___` (e.g. "model deprecated by provider", "replaced by better agent", "cost exceeds budget") |
| Replacement candidate | `___` |
| Migration notes | `___` |

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 1.0 | `YYYY-MM-DD` | Agent profile created |
