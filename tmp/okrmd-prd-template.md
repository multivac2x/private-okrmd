# OKRMD PRD Template

**OKRMD Standard v1.0** · **prd.md**

> This template defines a Product Requirements Document.
> Place it at `.okrmd/prds/PRD-{slug}.md`.
> A PRD describes *what* to build and *why* — it is the detailed specification that informs epics, stories, and tasks. It lives alongside the OKR hierarchy, not inside it. A PRD may serve one Key Result, span multiple, or exist independently (e.g. a client contract with no OKR).

---

## Metadata

| Field | Value | Instructions |
|-------|-------|--------------|
| ID | `PRD-{slug}` | Unique identifier, kebab-case (e.g. `PRD-iot-dashboard`, `PRD-mobile-app`) |
| Title | `___` | Full product/project name |
| Version | `1.0` | Document version (increment on significant changes) |
| Status | `draft` | `draft` · `review` · `approved` · `superseded` |
| Owner | `___` | Person accountable for this PRD (name or `[[profile]]` link) |
| Author | `___` | Who wrote this document (human, agent, or both) |
| Stakeholders | `___` | People or teams who must review/approve (comma-separated) |
| Key Results | `___` | Linked KRs this PRD serves, if any (e.g. `[[KR-1.1]]`, `[[KR-2.1]]`) |
| Phases | `___` | Linked phases, if any (e.g. `[[P1-mvp]]`, `[[P2-advanced]]`) |
| Target audience | `___` | Who will use the product described in this PRD |
| Created | `YYYY-MM-DD` | Date this PRD was created |
| Updated | `YYYY-MM-DD` | Date of last update |

---

## 1. Overview

> High-level summary of what this product/project is, who it's for, and why it matters. 3–5 sentences. A team member or agent reading only this section should understand the purpose.

`___`

---

## 2. Problem Statement

> What problem does this product/project solve? Describe the current pain, who experiences it, and what happens if we don't solve it.

### Current State

> How things work today — the pain, inefficiency, or gap.

`___`

### Desired State

> How things should work after this product ships.

`___`

### Impact of Inaction

> What happens if we don't build this? Business cost, user frustration, competitive risk, etc.

`___`

---

## 3. User Personas

> Define the key users of this product. Include both human users and, where relevant, system/agent actors.

<!-- Copy this block for each persona. -->

### Persona: `___`

| Field | Value |
|-------|-------|
| Name / Archetype | `___` |
| Type | `human` / `system` / `agent` |
| Role | `___` |
| Goals | `___` |
| Frustrations | `___` |
| Technical proficiency | `low` / `medium` / `high` |

> **Usage scenario**: Describe a typical interaction this persona has with the product.

`___`

---

## 4. Functional Requirements

> What the product must do. Each requirement should be specific, testable, and traceable to an epic or story.

### 4.1 `___` (Feature Area Name)

| ID | Requirement | Priority | Epic | Notes |
|----|------------|----------|------|-------|
| FR-001 | `___` | `must` / `should` / `could` | `[[E{n}]]` | `___` |
| FR-002 | `___` | | | |
| FR-003 | `___` | | | |

### 4.2 `___` (Feature Area Name)

| ID | Requirement | Priority | Epic | Notes |
|----|------------|----------|------|-------|
| FR-010 | `___` | | | |
| FR-011 | `___` | | | |

<!-- Add sections (4.3, 4.4, etc.) for each feature area. -->

> **Priority key** (MoSCoW):
> - `must` — Required for the product to function. Ship blocker.
> - `should` — Important but not critical. Degrade gracefully without it.
> - `could` — Desirable if time/resources allow.
> - `won't` — Explicitly excluded from scope (document to prevent scope creep).

---

## 5. Non-Functional Requirements

> How the product must behave — quality attributes that apply across all features.

### Performance

| ID | Requirement | Target | Measurement |
|----|------------|--------|-------------|
| NFR-001 | `___` | `___` | `___` |
| NFR-002 | `___` | | |

### Scalability

| ID | Requirement | Target | Measurement |
|----|------------|--------|-------------|
| NFR-010 | `___` | `___` | `___` |

### Security

| ID | Requirement | Standard | Measurement |
|----|------------|----------|-------------|
| NFR-020 | `___` | `___` | `___` |

### Reliability & Availability

| ID | Requirement | Target | Measurement |
|----|------------|--------|-------------|
| NFR-030 | `___` | `___` | `___` |

### Accessibility

| ID | Requirement | Standard | Measurement |
|----|------------|----------|-------------|
| NFR-040 | `___` | `___` | `___` |

### Compliance & Regulatory

| ID | Requirement | Regulation | Measurement |
|----|------------|-----------|-------------|
| NFR-050 | `___` | `___` | `___` |

### Internationalization & Localization

| ID | Requirement | Scope | Notes |
|----|------------|-------|-------|
| NFR-060 | `___` | `___` | `___` |

> Add or remove NFR categories as appropriate for your domain. Not every project needs all categories.

---

## 6. User Flows

> Describe the key user journeys through the product. Use numbered steps. For complex flows, reference external diagrams.

### Flow 1: `___` (Flow Name)

> **Actor**: `___` (persona name)
> **Trigger**: `___` (what initiates this flow)
> **Outcome**: `___` (what success looks like)

1. `___`
2. `___`
3. `___`
4. `___`

> **Error paths**: What happens if step `___` fails?

`___`

<!-- Copy this block for each major flow. -->

---

## 7. Information Architecture

> How is information organized within the product? Describe the key data entities, their relationships, and the navigation structure.

### Data Entities

| Entity | Description | Key fields | Relationships |
|--------|------------|------------|---------------|
| `___` | `___` | `___` | `___` |
| `___` | `___` | `___` | `___` |

### Navigation Structure

> Describe the primary navigation paths, menu structure, or API endpoint hierarchy.

`___`

---

## 8. Integration Points

> What external systems, APIs, services, or data sources does this product interact with?

| System | Type | Direction | Protocol | Notes |
|--------|------|-----------|----------|-------|
| `___` | `API` / `database` / `file` / `webhook` / `agent` | `inbound` / `outbound` / `bidirectional` | `___` | `___` |
| `___` | | | | |

---

## 9. Constraints & Assumptions

### Constraints

> Hard limits that the product must work within.

| Constraint | Type | Impact |
|-----------|------|--------|
| `___` | `technical` / `business` / `regulatory` / `budget` / `timeline` | `___` |
| `___` | | |

### Assumptions

> Things assumed to be true that, if wrong, would change the requirements.

| Assumption | Risk if wrong | How to validate |
|-----------|---------------|-----------------|
| `___` | `___` | `___` |
| `___` | | |

---

## 10. Out of Scope

> Explicitly list what this PRD does NOT cover. This prevents scope creep and sets clear expectations.

- `___`
- `___`
- `___`

> **Why document out-of-scope?** Because agents and new team members will try to solve problems they encounter. Explicitly listing what's excluded prevents wasted effort and keeps work focused.

---

## 11. Epic Breakdown

> Map the requirements above to epics. This provides the bridge from PRD to execution.

| Epic | Title | Phase | Key FRs covered | Priority |
|------|-------|-------|-----------------|----------|
| `[[E{n}]]` | `___` | `[[P{n}]]` | FR-001, FR-002 | `must` |
| `[[E{n}]]` | `___` | `[[P{n}]]` | FR-010, FR-011 | `should` |
| `[[E{n}]]` | `___` | `[[P{n}]]` | FR-003 | `could` |

---

## 12. Success Metrics

> How will we know the product described in this PRD is successful? These should align with the linked Key Results but may include product-specific metrics.

| Metric | Baseline | Target | Measurement method | Timeline |
|--------|----------|--------|--------------------|----------|
| `___` | `___` | `___` | `___` | `___` |
| `___` | | | | |

---

## 13. Open Questions

> Unresolved questions that need answers before or during implementation. Assign owners and deadlines.

| # | Question | Owner | Deadline | Resolution |
|---|----------|-------|----------|------------|
| 1 | `___` | `___` | `YYYY-MM-DD` | `___` |
| 2 | `___` | | | |

> Update the Resolution column as questions are answered. Do not delete questions — the history is valuable.

---

## 14. References

> Link to any external documents, research, prior art, or related artifacts.

| Document | Type | Location | Notes |
|----------|------|----------|-------|
| `___` | `research` / `competitor` / `technical` / `legal` / `design` | `___` | `___` |
| `___` | | | |

---

## Approval

| Role | Name | Status | Date |
|------|------|--------|------|
| Author | `___` | `complete` | `YYYY-MM-DD` |
| Product owner | `___` | `pending` / `approved` / `changes-requested` | |
| Technical lead | `___` | `pending` / `approved` / `changes-requested` | |
| Stakeholder | `___` | `pending` / `approved` / `changes-requested` | |

> A PRD moves to `approved` status only when all required approvers have signed off. Changes after approval must be documented in the changelog and may trigger a new version.

---

## Changelog

| Version | Date | Changes | Author |
|---------|------|---------|--------|
| 1.0 | `YYYY-MM-DD` | Initial PRD created | `___` |
