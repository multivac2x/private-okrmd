# OKRMD — Objectives and Key Results in Markdown

[![Version](https://img.shields.io/badge/version-0.1-blue.svg)](https://semver.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-stable-brightgreen.svg)](https://github.com/pescatoreluca/okrmd)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-orange.svg)](CONTRIBUTING.md)

**OKRMD Standard v0.1** · **Reference Implementation**

> OKRMD is a lightweight, file-based standard for managing OKRs (Objectives and Key Results) combined with agile project management — all in plain markdown files. It bridges the gap between human teams and AI agents, providing a single source of truth that both can read and write.

---

## 📖 What is OKRMD?

OKRMD (Objectives and Key Results in Markdown) is a comprehensive framework that combines:

- **OKR methodology** for strategic goal setting and tracking
- **Agile project management** with sprints (cycles), epics, and stories
- **Human-AI collaboration** through explicit autonomy levels (A1–A5)
- **Pulse-based time management** for focused work sessions
- **Plain text storage** in Git for version control and portability

### Why OKRMD?

Traditional project management tools (Jira, Asana, Linear) are proprietary, expensive, and often opaque. OKRMD stores everything in `.md` files that:

- ✅ **Are human-readable** — open in any text editor
- ✅ **Are AI-parsable** — agents can read and write natively
- ✅ **Version control friendly** — full Git history, diffs, branches
- ✅ **Vendor independent** — no platform lock-in, no API changes
- ✅ **Portable** — works with Obsidian, VS Code, Cursor, or any editor
- ✅ **Scalable** — from solo developers to large distributed teams

---

## 🚀 Quick Start

### Prerequisites

- A text editor (VS Code, vim, Obsidian, Cursor — anything that edits `.md` files)
- Git (recommended but not required)
- 15 minutes

### 1. Create the Folder Structure

```bash
mkdir -p .okrmd/{epics,backlog,pulses,cycles,agents,team,templates}
```

### 2. Create `config.md`

Create `.okrmd/config.md` with minimum required fields:

```markdown
# OKRMD Project Configuration

## Project

| Field | Value |
|-------|-------|
| Project name | my-project |
| OKRMD version | 0.1 |
| Created | 2026-02-19 |

## Cycle Settings

| Field | Value |
|-------|-------|
| Cycle duration | 14 |
| Estimation method | pulses |

## Pulse Settings

| Field | Value |
|-------|-------|
| Standard Pulse | 25 min |
| Short rest | 5 min |
| Long rest (after 4 pulses) | 15 min |

## Autonomy Levels

| Field | Value |
|-------|-------|
| Default autonomy | A3 |
| Max agent autonomy | A2 |

## Team

### Humans

| Name | Role |
|------|------|
| your-name | Lead |

### Agents

| Name | Model |
|------|-------|
| claude-code | claude-sonnet-4 |
```

### 3. Create Your First Epic and Story

Create the epic folder:

```bash
mkdir -p .okrmd/epics/E1-my-first-epic
```

Create `.okrmd/epics/E1-my-first-epic/_epic.md`:

```markdown
# Epic: My First Epic

| Field | Value |
|-------|-------|
| ID | E1 |
| Title | My First Epic |
| Status | in-progress |
| Owner | your-name |

## Description

What this epic delivers. 2–3 sentences.

## Stories

| Story | Title | Assignee | Status |
|-------|-------|----------|--------|
| [[S1.1]] | First Story | your-name | draft |
| [[S1.2]] | Second Story | claude-code | draft |
```

Create your first story `.okrmd/epics/E1-my-first-epic/S1.1-first-story.md`:

```markdown
# Story: First Story

| Field | Value |
|-------|-------|
| ID | S1.1 |
| Title | First Story |
| Epic | [[E1]] |
| Status | ready |
| Assignee | your-name |
| Autonomy | A5 |

## Story

As a user, I need [capability] so that [benefit].

## Acceptance Criteria

- [ ] First criterion
- [ ] Second criterion
- [ ] Third criterion

## Tasks

- [ ] First task
- [ ] Second task
- [ ] Third task
```

### 4. Start Your First Pulse

Create `.okrmd/pulses/2026-02-19-your-name.md`:

```markdown
# Pulse Log — your-name — 2026-02-19

| Metric | Value |
|--------|-------|
| Pulses completed | 0 |
| Total focus time | 0 min |

## Pulse 1 (09:00–09:25) — 25 min
- **Task**: [[S1.1]] — First task
- **Status**: _fill in after pulse_
- **Interruptions**: 0
```

Now set a 25-minute timer and start working. When the timer ends, fill in the status, take a 5-minute rest, and log the next Pulse.

---

## 📁 Folder Structure

```
.okrmd/
├── config.md                     # Project configuration (required)
│
├── objectives/                   # Strategic goals
├── key-results/                  # Measurable outcomes
├── phases/                       # Delivery gates
├── epics/                        # Large work areas (folders containing stories)
├── prds/                         # Product Requirements Documents
├── cycles/                       # Sprint/iteration timeboxes
├── backlog/                      # Orphan/unplanned work items
├── pulses/                       # Daily focus session logs
├── agents/                       # AI agent profiles
├── team/                         # Human team member profiles
├── retros/                       # Retrospective documents
└── templates/                    # File templates for all entity types
```

---

## 🎯 Core Concepts

### Autonomy Levels (A1–A5)

OKRMD defines five autonomy levels to clarify human-agent collaboration:

| Level | Name | Who Drives | When to Use |
|-------|------|-----------|-------------|
| **A1** | Full Auto | Agent (full auto) | Routine automation, strong test coverage |
| **A2** | Supervised Auto | Agent (human spot-checks) | Familiar tasks, agent has track record |
| **A3** | Guided Auto | Agent + Human (guided) | **Default.** Most knowledge work. |
| **A4** | Co-Pilot | Human (agent assists) | Complex decisions, novel problems |
| **A5** | Human-Led | Human (no agent) | Strategy, sensitive topics, pure human work |

Every story and backlog item specifies its autonomy level. This clarity prevents miscommunication and sets appropriate expectations for both humans and agents.

### Pulse-Based Work

A **Pulse** is a bounded interval of focused effort:

- **Standard Pulse**: 25 minutes of deep work + 5 minutes of rest
- **Deep Pulse**: 50 minutes for complex tasks + 15 minutes of rest
- **Long Rest**: After 4 consecutive Pulses, take a 15-minute break

Humans log each Pulse in their daily pulse file. Agents checkpoint after each Pulse to manage context window limits. The pulse rhythm creates sustainable, measurable progress.

### Cross-References

OKRMD uses wiki-style `[[ID]]` links to connect entities:

```markdown
This story depends on [[S1.1]] and blocks [[S2.2]].
Assigned to [[claude-code]] with [[alice]] as reviewer.
See [[PRD-iot-dashboard]] for requirements.
Parent objective: [[O1]]
```

These links are resolved by tools and provide traceability from any task to strategic objectives.

---

## 📚 Documentation

This repository contains the complete OKRMD standard documentation:

| Document | Purpose |
|----------|---------|
| [Quick Start Guide](tmp/okrmd-quick-start-guide.md) | Get running in 15 minutes |
| [Folder Structure Standard](tmp/okrmd-folder-structure-standard.md) | Where each file belongs |
| [Naming Conventions](tmp/okrmd-naming-convention-standard.md) | IDs, slugs, and file names |
| [Autonomy Levels Reference](tmp/okrmd-autonomy-levels-reference.md) | A1–A5 detailed guide |
| [Workflows Guide](tmp/okrmd-workflows-guide.md) | Ceremonies and processes |
| [Config Template](tmp/okrmd-config-template.md) | Complete `config.md` reference |
| [Manifesto](tmp/okrmd-manifesto.md) | Philosophy and principles |

---

## 🛠️ Installation & Setup

OKRMD is **just markdown files** — there's no software to install. However, you may want tooling support:

### Editor Plugins

- **VS Code**: Install the "Markdown All in One" extension for preview
- **Obsidian**: Create a vault pointing to your repository
- **Cursor**: Native markdown support with AI assistance

### Optional CLI Tools

Community-maintained tools (not required):

- `okrmd-validate` — validates your `.okrmd/` structure
- `okrmd-report` — generates velocity and OKR score reports
- `okrmd-link` — resolves and checks wiki-links

Check the [community tools directory](https://github.com/pescatoreluca/okrmd/tree/main/tools) for installation instructions.

---

## 📖 Usage Examples

### Setting a Strategic Goal

Create `.okrmd/objectives/O1-grow-revenue.md`:

```markdown
# Objective: Grow Revenue

| Field | Value |
|-------|-------|
| ID | O1 |
| Title | Grow Revenue |
| Owner | alice |
| Status | active |
| Cadence | Q1 2026 |

## Description

Increase monthly recurring revenue by expanding into new markets.

## Key Results

| Key Result | Target | Current |
|------------|--------|---------|
| [[KR-1.1]] | $100K MRR | $65K |
| [[KR-1.2]] | 500 customers | 320 |
| [[KR-1.3]] | 20% expansion revenue | 12% |
```

### Planning a Sprint

Create `.okrmd/cycles/C05/_cycle.md`:

```markdown
# Cycle C05: Feature Sprint

| Field | Value |
|-------|-------|
| ID | C05 |
| Goal | Complete alert system MVP |
| Start | 2026-02-19 |
| End | 2026-03-04 |
| Status | planning |

## Committed Work

| Story | Title | Assignee | Autonomy | Est. |
|-------|-------|----------|----------|------|
| [[S2.1]] | Alert backend | claude-code | A2 | 8 |
| [[S2.2]] | Alert UI components | alice | A4 | 5 |
| [[S2.3]] | Alert configuration | bob | A3 | 6 |

## Capacity

| Team Member | Available Pulses | Total Capacity |
|-------------|------------------|----------------|
| alice | 8/day × 10 days | 80 |
| bob | 8/day × 10 days | 80 |
| claude-code | 12/day × 10 days | 120 |

**Total committed**: 19 pulses (well under 80% capacity)
```

### Logging Daily Work

Create `.okrmd/pulses/2026-02-19-alice.md`:

```markdown
# Pulse Log — alice — 2026-02-19

| Metric | Value |
|--------|-------|
| Pulses completed | 0 |
| Total focus time | 0 min |

## Pulse 1 (09:00–09:25) — 25 min
- **Task**: [[S2.2]] — Alert UI components
- **Status**: Completed basic AlertButton component
- **Interruptions**: 0 (Slack, then back to work)

## Pulse 2 (09:30–09:55) — 25 min
- **Task**: [[S2.2]] — AlertButton tests
- **Status**: Wrote 85% of unit tests
- **Interruptions**: 1 (quick question from bob)

## End of Day Reflection

- **Accomplishments**: AlertButton component + tests ready for review
- **Blockers**: None
- **Tomorrow's first task**: [[S2.2]] — AlertList component
- **Energy level**: 7/10 — good focus day
```

---

## 🤝 Contributing

OKRMD is an open standard. Contributions are welcome!

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on:

- How to submit issues and feature requests
- Code of conduct
- Development workflow
- Versioning policy
- Release process

### Quick Contribution Steps

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Add or update tests as needed
5. Ensure documentation is updated
6. Commit (`git commit -m 'Add amazing feature'`)
7. Push (`git push origin feature/amazing-feature`)
8. Open a Pull Request

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

OKRMD synthesizes best practices from:

- **OKR** (Objectives and Key Results) — Andy Grove, John Doerr
- **Agile & Scrum** — iterative development, timeboxing
- **Pomodoro Technique** — focused work intervals
- **Git Flow** — branch naming, PR workflows
- **AI-Human Collaboration** — autonomy spectrum, context management

---

## 📞 Support

- **Documentation**: See the [docs folder](tmp/) for complete standards
- **Issues**: [GitHub Issues](https://github.com/pescatoreluca/okrmd/issues)
- **Discussions**: [GitHub Discussions](https://github.com/pescatoreluca/okrmd/discussions)
- **Email**: [Open an issue](https://github.com/pescatoreluca/okrmd/issues/new) for direct contact

---

## 🗺️ Roadmap

OKRMD v0.1 is the **initial public release** with core functionality stable.

Future versions may include:

- [ ] Official schema validation tool
- [ ] VS Code extension with autocomplete
- [ ] GitHub Actions for automated OKR scoring
- [ ] Integration with popular project management tools
- [ ] Enhanced reporting dashboards
- [ ] Multi-language support

See [ROADMAP.md](ROADMAP.md) for details.

---

**OKRMD** — Objectives and Key Results in Markdown.

*Plain text will rule the AI era. And through it, humans and agents will build together — aligned, measured, and steady.*

`v0.1 · February 2026`
