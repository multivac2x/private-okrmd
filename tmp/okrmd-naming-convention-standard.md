# OKRMD Naming Convention Standard

**OKRMD Standard v0.1** · **Reference Document**

> This document defines all naming rules for OKRMD entities: IDs, file names, slugs, cross-references, and branch names.
> Consistent naming enables automation, cross-referencing, and navigation by both humans and agents.

---

## Core Principles

1. **IDs are for machines and cross-references.** They are short, unique, and never change once assigned.
2. **Slugs are for humans.** They make filenames readable at a glance.
3. **File names combine both.** `{ID}-{slug}.md` gives you uniqueness and readability.
4. **kebab-case everywhere.** Lowercase, hyphens between words, no spaces, no special characters.
5. **Prefixes encode type.** You can identify what a file is from its first characters alone.

---

## Entity Naming Reference

| Entity | ID Format | File Name Pattern | Example |
|--------|-----------|-------------------|---------|
| Objective | `O{n}` | `O{n}-{slug}.md` | `O1-grow-revenue.md` |
| Key Result | `KR-{obj}.{n}` | `KR-{obj}.{n}-{slug}.md` | `KR-1.1-increase-mrr-30pct.md` |
| Phase | `P{n}` | `P{n}-{slug}.md` | `P1-mvp.md` |
| Epic (folder) | `E{n}` | `E{n}-{slug}/` | `E1-auth-system/` |
| Epic (file) | `E{n}` | `_epic.md` | `_epic.md` (always inside epic folder) |
| Story | `S{epic}.{n}` | `S{epic}.{n}-{slug}.md` | `S2.1-alert-backend.md` |
| Backlog Item | `{PREFIX}-{nnn}` | `{PREFIX}-{nnn}-{slug}.md` | `BUG-042-login-crash.md` |
| PRD | `PRD-{slug}` | `PRD-{slug}.md` | `PRD-iot-dashboard.md` |
| Cycle (folder) | `C{nn}` | `C{nn}/` | `C05/` |
| Cycle (file) | `C{nn}` | `_cycle.md` | `_cycle.md` (always inside cycle folder) |
| Agent Profile | — | `{agent-name}.md` | `claude-code.md` |
| Team Profile | — | `{handle}.md` | `alice.md` |
| Pulse Log | — | `{YYYY-MM-DD}-{worker}.md` | `2026-02-16-alice.md` |
| Retrospective | — | `{scope}-retro.md` | `C05-retro.md` |

---

## ID Rules

### Numbering

| Entity | Numbering style | Starts at | Zero-padded | Examples |
|--------|----------------|-----------|-------------|---------|
| Objective | Sequential integer | `1` | No | `O1`, `O2`, `O12` |
| Key Result | `{parent}.{seq}` | `1` | No | `KR-1.1`, `KR-1.2`, `KR-2.1` |
| Phase | Sequential integer | `1` | No | `P1`, `P2`, `P3` |
| Epic | Sequential integer | `1` | No | `E1`, `E2`, `E15` |
| Story | `{epic}.{seq}` | `1` | No | `S1.1`, `S2.10`, `S15.3` |
| Backlog Item | Sequential per prefix | `001` | Yes (3 digits) | `BUG-001`, `BUG-042`, `INC-007` |
| Cycle | Sequential | `01` | Yes (2 digits) | `C01`, `C05`, `C12` |

### ID Immutability

> **IDs never change once assigned.** If a story is moved between epics, its ID stays the same. If an objective is reworded, its `O1` ID remains. This ensures cross-references never break.

| Scenario | Rule |
|----------|------|
| Story moved to different epic | Keep original ID. Update the `epic:` field in metadata. |
| Objective reworded | Keep original ID. Update title and slug in filename. |
| Backlog item promoted to story | Story gets a new ID (`S{e}.{n}`). Backlog item keeps its ID and links to the story. |
| Entity deleted/cancelled | ID is retired. Never reuse it. |

### ID Gaps

> Gaps in numbering are expected and acceptable. If `S2.3` is deleted, `S2.4` does not become `S2.3`. Sequential integrity matters less than reference stability.

---

## Slug Rules

Slugs are the human-readable portion of filenames.

| Rule | Detail | Good | Bad |
|------|--------|------|-----|
| Case | Always lowercase | `alert-backend` | `Alert-Backend` |
| Separator | Hyphens only | `user-login` | `user_login`, `user login` |
| Length | 2–5 words recommended | `oauth-integration` | `implement-the-oauth2-authentication-flow-for-users` |
| Characters | `a-z`, `0-9`, `-` only | `reduce-latency-50pct` | `reduce-latency-50%` |
| Articles | Omit articles (a, an, the) | `alert-backend` | `the-alert-backend` |
| Verbs | Omit leading verbs when possible | `password-reset` | `implement-password-reset` |
| Abbreviations | Use common ones, avoid obscure | `auth`, `config`, `db` | `authn`, `cfg`, `dbms` |
| Numbers | Use digits, not words | `reduce-latency-50pct` | `reduce-latency-fifty-percent` |

### Slug Changes

> Slugs CAN change (unlike IDs). If a story's scope changes and the slug no longer describes it, rename the file. Update the filename but keep the same ID in the metadata.

| Before | After | ID unchanged |
|--------|-------|-------------|
| `S2.1-alert-model.md` | `S2.1-alert-backend.md` | `S2.1` stays `S2.1` |

---

## Cross-Reference Syntax

OKRMD uses **wiki-style double-bracket links** to reference other entities.

### Syntax

```markdown
This story depends on [[S1.1]] and blocks [[S2.2]].
Assigned to [[claude-code]] with [[alice]] as reviewer.
See [[PRD-iot-dashboard]] for requirements.
Parent objective: [[O1]]
```

### Resolution Rules

| Reference | Resolves to |
|-----------|------------|
| `[[O1]]` | `objectives/O1-*.md` |
| `[[KR-1.1]]` | `key-results/KR-1.1-*.md` |
| `[[P1]]` | `phases/P1-*.md` |
| `[[E1]]` | `epics/E1-*/_epic.md` |
| `[[S2.1]]` | `epics/E2-*/S2.1-*.md` |
| `[[BUG-042]]` | `backlog/BUG-042-*.md` |
| `[[PRD-iot-dashboard]]` | `prds/PRD-iot-dashboard.md` |
| `[[C05]]` | `cycles/C05/_cycle.md` |
| `[[claude-code]]` | `agents/claude-code.md` |
| `[[alice]]` | `team/alice.md` |
| `[[C05-retro]]` | `retros/C05-retro.md` |

> The `*` wildcard matches the slug portion. Tooling resolves by matching the ID prefix. This means IDs must be unique across their entity type.

### Source References

For referencing specific sections within documents:

```markdown
[Source: PRD-iot-dashboard#Section-4.3-Alerts]
[Source: E2/_epic.md#Architecture-Notes]
[Source: docs/architecture.md#Database-Schema]
```

---

## Git Branch Naming

| Field | Pattern | Example |
|-------|---------|---------|
| Feature (story) | `feature/S{e}.{n}-{slug}` | `feature/S2.1-alert-backend` |
| Feature (epic) | `feature/E{n}-{slug}` | `feature/E2-alert-system` |
| Bugfix | `bugfix/{PREFIX}-{nnn}-{slug}` | `bugfix/BUG-042-login-crash` |
| Hotfix | `hotfix/{PREFIX}-{nnn}-{slug}` | `hotfix/INC-007-server-down` |
| Spike | `spike/SPK-{nnn}-{slug}` | `spike/SPK-008-evaluate-redis` |
| Release (phase) | `release/P{n}-{slug}` | `release/P1-mvp` |

### Commit Message Format

```
[{ID}] {message}
```

| Example | Explanation |
|---------|-------------|
| `[S2.1] Add alert model migration` | Story commit |
| `[BUG-042] Fix Safari auth bundle error` | Bug fix commit |
| `[S2.1] WIP: alert routes, 3/5 endpoints done` | Work in progress |
| `[C05] Update cycle status to review` | Cycle management |

### PR Title Format

```
[{ID}] {Title}
```

| Example |
|---------|
| `[S2.1] Alert System Foundation (Backend)` |
| `[BUG-042] Fix login crash on Safari 17.2` |

---

## Backlog Prefix Rules

| Rule | Detail |
|------|--------|
| Length | 2–4 uppercase letters |
| Characters | `A-Z` only (no numbers, no special characters) |
| Uniqueness | Each prefix must be unique within the project |
| Registration | All prefixes must be registered in `config.md` |
| Custom prefixes | Teams can add custom prefixes following these rules |
| Reserved | `S` (story), `E` (epic), `O` (objective), `KR` (key result), `P` (phase), `C` (cycle), `PRD` (PRD) are reserved for the hierarchy — do not use as backlog prefixes |

---

## Special File Names

| Name | Purpose | Location |
|------|---------|----------|
| `_epic.md` | Epic definition | Inside epic folder |
| `_cycle.md` | Cycle definition | Inside cycle folder |
| `config.md` | Project configuration | `.okrmd/` root |

> The underscore prefix (`_`) is used for "meta" files that define a container (epic or cycle). It ensures these files sort first in directory listings.

---

## Case Sensitivity

| Component | Case | Example |
|-----------|------|---------|
| Entity prefixes | Uppercase | `O`, `KR`, `E`, `S`, `P`, `C`, `PRD`, `BUG` |
| Slugs | Lowercase | `alert-backend` |
| File extensions | Lowercase | `.md` |
| Agent names | Lowercase | `claude-code` |
| Team handles | Lowercase | `alice` |
| Folder names | Mixed (prefix uppercase, slug lowercase) | `E2-alert-system/` |

> **File systems**: OKRMD assumes a case-sensitive file system. On case-insensitive systems (macOS default, Windows), follow these conventions strictly to avoid collisions.

---

## Changelog

| Version | Date | Changes |
|---------|------|---------|
| 0.1 | 2026-02-19 | Initial naming convention standard |
