# OKRMD Roadmap

This document outlines the future development of OKRMD. It's a living document that will evolve based on community feedback and real-world usage.

---

## Current Status: v0.1 (February 2026)

**v0.1** is the initial public release. It includes:

- ✅ Complete folder structure standard
- ✅ Naming conventions and cross-reference syntax
- ✅ Autonomy levels (A1–A5) for human-agent collaboration
- ✅ Pulse-based time management
- ✅ Comprehensive workflows guide
- ✅ Config template with all settings
- ✅ Templates for all entity types
- ✅ Manifesto and core principles

The standard is **stable** and ready for production use. We consider v0.1 to be a "feature-complete" initial release that implements the full vision.

---

## Upcoming: v0.2 (Target: Q2 2026)

Focus: Tooling and ecosystem

### Planned Enhancements

- [ ] **Official validation tool** — CLI to validate `.okrmd/` structure
- [ ] **VS Code extension** — autocomplete, validation, preview
- [ ] **GitHub Actions** — automated OKR scoring, reports
- [ ] **Schema definition** — JSON Schema for all file types
- [ ] **Import/export tools** — migrate from Jira, Asana, Linear
- [ ] **Reporting templates** — pre-built markdown reports
- [ ] **Community examples** — curated examples from early adopters

### Potential Additions (Under Consideration)

- [ ] Webhook support for integrations
- [ ] Enhanced search and query language
- [ ] Conflict resolution strategies for concurrent edits
- [ ] Internationalization (i18n) support

---

## Future: v1.0 (Target: Q4 2026 or Q1 2027)

Focus: Stability, polish, and widespread adoption

### Criteria for v1.0

- [ ] At least 6 months of production use by multiple teams
- [ ] No breaking changes proposed for 3 months
- [ ] Complete tooling ecosystem (validation, editor support, CI/CD)
- [ ] Comprehensive test suite for all standards
- [ ] Migration guide from v0.x to v1.0 (if needed)
- [ ] Community governance model established
- [ ] At least 3 third-party integrations

### What v1.0 Means

v1.0 will signify that OKRMD is a **stable, production-ready standard** suitable for:

- Enterprise deployments
- Long-term projects (multi-year)
- Regulated industries (with proper documentation)
- Educational use in project management courses

We commit to backward compatibility from v1.0 onward according to semver.

---

## Beyond v1.0

### Potential Future Directions

These are ideas for post-v1.0 development. They are NOT planned for v1.0 and may never happen depending on community interest.

- **Distributed OKRMD** — peer-to-peer sync for offline teams
- **Real-time collaboration** — multi-user editing with conflict resolution
- **Advanced analytics** — predictive velocity, risk forecasting
- **AI-powered suggestions** — auto-generated acceptance criteria, task breakdown
- **Mobile app** — native iOS/Android for pulse logging
- **Enterprise features** — SSO, audit logs, compliance reports
- **Visualization tools** — Gantt charts, network graphs, dashboards
- **Plugin architecture** — extendable with custom entity types
- **Blockchain integration** — immutable audit trail (for highly regulated environments)

---

## Community-Driven Development

OKRMD is an **open standard**, not a product. Its direction is determined by:

1. **User feedback** — what real teams need
2. **Contributor effort** — what people build and submit
3. **Adoption patterns** — what works in practice
4. **Maintainer judgment** — ensuring coherence and quality

If you want something, **open an issue** or **submit a PR**. The roadmap is not set in stone — it's a plan that adapts to the community's needs.

---

## How to Influence the Roadmap

### Submit an Issue

- Use the `enhancement` label for new features
- Use the `question` label for "would this be useful?"
- Provide concrete use cases, not abstract ideas
- Explain the problem before proposing a solution

### Submit a PR

- Small, focused changes have the best chance of acceptance
- Documentation improvements are always welcome
- New templates or entity types need strong justification
- Breaking changes require extensive discussion

### Participate in Discussions

- Join [GitHub Discussions](https://github.com/pescatoreluca/okrmd/discussions)
- Vote on proposed features with 👍 reactions
- Share your team's use cases and pain points
- Help test pre-release versions

---

## Release Cadence

We aim for:

- **Patch releases** (0.1.x) as needed for bug fixes (immediate)
- **Minor releases** (0.2, 0.3, 0.4) every 2-3 months with new features
- **Major release** (1.0) when stability criteria are met

Each release will include:

- Updated documentation
- Migration notes (if breaking changes)
- Changelog with all changes
- Pre-release testing period

---

## Known Limitations (v0.1)

These are intentional or necessary constraints:

- **No built-in tooling** — you must create your own scripts or use community tools
- **No conflict resolution** — Git merge conflicts must be resolved manually
- **No real-time collaboration** — not designed for simultaneous editing
- **No access control** — file permissions only, no per-entity permissions
- **No built-in reporting** — you must create your own reports or use community templates
- **No official GUI** — text-only interface (though editors provide previews)

These may be addressed in future versions if there's sufficient demand.

---

## Unlikely to Happen

These are explicitly **out of scope** for OKRMD:

- ❌ A hosted SaaS platform (OKRMD is file-based, not a service)
- ❌ A mobile app (use a markdown editor on mobile)
- ❌ A web-based editor (use Obsidian, VS Code, etc.)
- ❌ Proprietary integrations (use open standards like Git, markdown)
- ❌ AI agent that executes work (OKRMD is a standard, not an agent platform)
- ❌ Real-time sync across devices (use Git)
- ❌ Rich media support (embed images/PDFs if your editor supports it, but they're not part of the standard)

If you need these, build them as **external tools** that read/write OKRMD files.

---

## Questions?

- **Is X on the roadmap?** Check this document and search existing issues
- **Can Y be added?** Open an issue to discuss — if it aligns with OKRMD's philosophy and someone is willing to implement it, possibly
- **When will Z be done?** If it's not listed under "Upcoming" or "v1.0 criteria," it's not planned. Convince us!

---

**The roadmap is a plan, not a promise.** We'll adapt based on what the community actually needs and uses.

Last updated: 2026-02-19
