# OKRMD — Objectives and Key Results in Markdown

[![Version](https://img.shields.io/badge/version-0.1-blue.svg)](https://semver.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![Status](https://img.shields.io/badge/status-stable-brightgreen.svg)](https://github.com/pescatoreluca/okrmd)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-orange.svg)](CONTRIBUTING.md)

**OKRMD Standard v0.1** · **Reference Implementation**

> OKRMD is a lightweight, file-based standard for managing OKRs (Objectives and Key Results) combined with agile project management — all in plain markdown files. It bridges the gap between human teams and AI agents, providing a single source of truth that both can read and write.

---

## 📖 What is OKRMD?

OKRMD (Objectives and Key Results in Markdown) it tries to be a comprehensive framework that combines:

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
- ✅ **Machine parsable** — automatic tools for validation
- ✅ **Vendor independent** — no platform lock-in, no API changes
- ✅ **Portable** — works with Obsidian, VS Code, Cursor, or any editor
- ✅ **Scalable** — from solo developers to large distributed teams

---

## 🚀 Quick Start

### Prerequisites

- A text editor (VS Code, vim, Obsidian, Cursor — anything that edits `.md` files)
- Git (recommended but not required)
- 5 minutes to read the tutorial
- Start planning

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

## 📚 Documentation

This repository contains the initial OKRMD standard documentation:

| Document | Purpose |
|----------|---------|
| [Manifesto](MANIFESTO.md) | Philosophy and principles |

---

## 🛠️ Installation & Setup

OKRMD is **just markdown files** — there's no software to install.

## 📖 Usage Examples

Soon some real life examples will be released.

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
4. Ensure documentation is updated
5. Commit (`git commit -m 'Add new feature'`)
6. Push (`git push origin feature/new-feature`)
7. Open a Pull Request

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

## 🗺️ Roadmap

OKRMD v0.1 is the **initial public release** with core functionality stable.

Future versions will include:

- [ ] Review of the initial draft proposal for Stories
- [ ] Review of the initial draft proposal for Epics
- [ ] Review of other initial documents used in OKRMD
- [ ] Review of the initial tutorial on how to use OKRMD
- [ ] Official schema validation tool

---

**OKRMD** — Objectives and Key Results in Markdown.

*Plain text will rule the AI era. And through it, humans and agents will build together — aligned, measured, and steady.*

`v0.1 · February 2026`
