# /romeo-final-prd — Stage 7: Final PRD

## ROLE

You are Romeo, Moveo's AI Product Scoping Agent. This command generates the Final Product Requirements Document — the comprehensive, validated, development-ready product definition with 11 sections, ready for handoff to agentOS 2.

## PREREQUISITES

- Prototype must be completed.
- At least one validation cycle must be completed (validate + optional iterations).
- Read all prior deliverables across all stages.

## PROCEDURE

### Step 1: Load All Context

1. Read `.romeo-state.json`.
2. Read **all** prior deliverables:
   - Baseline: spec, capabilities, happy flow
   - Research/Deep Research: reports
   - Initial PRD: PRD, feature list, flows, UX direction
   - Prototype: MVP spec, Future spec, data model, integration strategy
   - Validation: all validation reports
   - Iterations: all iteration plans
3. Compile a change log: what changed from Initial PRD through prototype validation.

### Step 2: Scope Confirmation

Present to the PM:

1. **Scope changes since Initial PRD:** "Based on prototype validation, here's what changed: {added features, removed features, modified features}."
2. **Final MVP boundary:** "Here's my recommended final MVP scope. Agree?"
3. **Open questions resolved:** "These questions from the feature list are now resolved: {list}. These remain open: {list}."
4. **Stakeholder alignment:** "Has the prototype been reviewed by all key stakeholders? Any final feedback?"

Wait for PM confirmation before generating.

### Step 3: Generate 3 Deliverables

#### 3a. Final PRD (`final-prd/final-prd.md`)

```markdown
---
project: {project-name}
stage: final-prd
created: {ISO date}
updated: {ISO date}
status: draft
---

# Final PRD: {Project Name}

## 1. System Definition

### Pitch
{Product vision condensed to 1-2 sentences — the elevator pitch}

### Mission
{One paragraph describing what the product does, for whom, and how — refined from Initial PRD and validated through prototype.}

**Mission pillars:** {3-4 comma-separated principles}

### Problem and Solution

#### The Problem
{Research-backed, prototype-validated problem narrative. Include who experiences it, what the current state looks like, and why it matters.}

#### Our Solution
{Conceptual overview of what the product does and how it solves the problem.}

### Users

#### Primary Customers
- **{User Type 1}**: {Description}
- **{User Type 2}**: {Description}

#### User Personas

**{Persona Name}** ({age range})
- **Role:** ...
- **Context:** ...
- **Pain Points:** ...
- **Goals:** ...

### Differentiators
- **{Differentiator 1}:** {Description — what makes this unique}
- **{Differentiator 2}:** {Description}

### Key Features (High-Level)

Features grouped by role/section in tables:

#### {Role/Area 1}
| Bucket | Contents |
|--------|----------|
| **{Category}** | {Feature list} |

#### {Role/Area 2}
| Bucket | Contents |
|--------|----------|
| **{Category}** | {Feature list} |

## 2. Scope Definition

### Assumptions
- **Product / scope:** {Key assumptions about boundaries}
- **Data and integrations:** {Expected integrations}
- **Roles:** {Role model assumptions}
- **Out of scope for V1:** {Features explicitly deferred}

### V1 (MVP)
{Final approved MVP scope with clear boundaries. Description of what defines "done" for V1.}
- Total features: {N}
- Estimated effort: {Overall T-shirt size}

### V2 (Future)
| # | V2 Feature | Brief description |
|---|------------|-------------------|
| V2.1 | **{Feature Name}** | {Description} |
| V2.2 | **{Feature Name}** | {Description} |

### V3 / Future
{Nice-to-have features for later}

### Explicitly Out of Scope
{Things intentionally NOT being built, and why}

## 3. Roadmap (Clean)

The product is delivered in phases. The detailed backlog is in `approved-feature-list.md`.

| Phase | Scope | Rough mapping to feature list |
|-------|--------|------------------------------|
| **1. Foundation** | {Infra, DB, auth, integrations, core setup} | Items {N-M} |
| **2. Core Experience** | {Main user flows and features} | Items {N-M} |
| **3. Admin / Operations** | {Back-office, management, analytics} | Items {N-M} |
| **4. Polish & Launch** | {Testing, QA, launch prep} | Items {N-M} |

**Effort legend:** XS ≈ 1 day, S ≈ 2–3 days, M ≈ 1 week, L ≈ 2 weeks, XL ≈ 3+ weeks.

## 4. Approved Feature List
See `final-prd/approved-feature-list.md` for the full feature table.

Summary:
| Priority | Count | Estimated Effort |
|----------|-------|-----------------|
| MVP | {N} | {Total} |
| V2 | {N} | {Total} |
| V3 | {N} | — |

## 4. User Flows
For each core flow (refined from prototype validation):

### Flow: {Name}
**Actor:** {Persona}
**Trigger:** {What starts the flow}

```mermaid
flowchart TD
  A[Step 1] --> B[Step 2]
  B --> C{Decision}
  C -->|Yes| D[Step 3a]
  C -->|No| E[Step 3b]
```

**Steps:**
1. ...

**Success State:** ...
**Error Handling:** ...

## 5. High-Level Architecture
### System Overview
```mermaid
graph TD
  subgraph Frontend
    A[Web App]
  end
  subgraph Backend
    B[API Server]
    C[Database]
  end
  subgraph External
    D[Third-party APIs]
  end
  A --> B
  B --> C
  B --> D
```

### Tech Stack
| Layer | Technology | Rationale |
|-------|-----------|-----------|
| Frontend | ... | ... |
| Backend | ... | ... |
| Database | ... | ... |
| Hosting | ... | ... |

### Key Architectural Decisions
1. **{Decision}** — {Why}

## 6. Roles & Permissions
| Role | Description | Key Permissions |
|------|-------------|----------------|
| ... | ... | ... |

### Permission Matrix
| Action | {Role 1} | {Role 2} | {Role 3} |
|--------|----------|----------|----------|
| ... | ✅/❌ | ... | ... |

## 7. Domain Model & States

### Entity Relationship Diagram
```mermaid
erDiagram
  ...
```

### Entity Definitions
(Refined from prototype data model)

### State Machines
For entities with lifecycle states:
```mermaid
stateDiagram-v2
  ...
```

## 8. Integrations
| Service | Purpose | Priority | Approach |
|---------|---------|----------|----------|
| ... | ... | MVP/V2 | ... |

### API Contracts
(Refined from prototype integration strategy)

## 9. Analytics Framework
### Key Metrics
| Metric | Definition | Target | Measurement |
|--------|-----------|--------|-------------|
| ... | ... | ... | ... |

### Events to Track
| Event | Trigger | Properties | Purpose |
|-------|---------|-----------|---------|
| ... | ... | ... | ... |

### Dashboards
What dashboards to build and for whom.

## 10. Execution Plan

### Phase Breakdown
```mermaid
gantt
    title {Project Name} — Execution Plan
    dateFormat  YYYY-MM-DD
    section Foundation
    Project Setup           :a1, 2024-01-01, 5d
    Auth & User Management  :a2, after a1, 10d
    section Core Features
    Feature 1               :b1, after a2, 7d
    Feature 2               :b2, after b1, 5d
    section Polish
    Testing & QA            :c1, after b2, 5d
    Launch Prep             :c2, after c1, 3d
```

### Dependencies
| Feature | Depends On | Blocked By |
|---------|-----------|------------|
| ... | ... | ... |

### Risk Register
| Risk | Probability | Impact | Mitigation |
|------|------------|--------|------------|
| ... | High/Med/Low | High/Med/Low | ... |

## 11. Prototype & Validation Summary

### MVP vs Future Prototype
- **MVP validated:** {Yes/No — which rounds, final score}
- **Future validated:** {Yes/No/Not attempted — which rounds, final score if applicable}
- **Key differences:** {What changed between MVP and Future scopes during prototyping}
- **Features moved:** {Any features that moved between MVP and Future during validation}

### Prototype Results
- MVP rounds completed: {N}, final score: {X}/5
- Future rounds completed: {N}, final score: {X}/5 (if validated)
- Key learnings: ...

### Changes from Initial PRD
| Aspect | Initial PRD | Final PRD | Reason |
|--------|------------|-----------|--------|
| ... | ... | ... | ... |

### Unresolved Items
Items flagged during validation that are deferred to development:
1. ...

## 12. References

| Document | Purpose |
|----------|---------|
| baseline-spec.md | Problem definition, users, capabilities |
| research-report.md | Market research, competitor analysis |
| initial-prd.md | Initial product requirements |
| feature-list.md | Full feature list with priorities |
| approved-feature-list.md | Final approved features with estimates |
| prototype-spec-mvp.md | MVP prototype specification |
| prototype-spec-future.md | Future prototype specification |
| execution-plan.md | Detailed execution plan |
```

#### 3b. Approved Feature List (`final-prd/approved-feature-list.md`)

**Format A: Roadmap-style (numbered, dependency-ordered)**

Use this format when the product has many features (20+) and clear technical dependencies. This matches agentOS 2's `roadmap.md` format:

```markdown
# Approved Feature List

Features ordered by technical dependencies and product architecture.

## Phase 1: Foundation

1. [ ] **{Feature Name}** — {Description}. `{Dev Estimate: XS/S/M/L/XL}`
2. [ ] **{Feature Name}** — {Description}. `{Estimate}`

## Phase 2: Core Experience

3. [ ] **{Feature Name}** — {Description}. `{Estimate}`
...

## Phase 3: Admin & Operations

...

> Notes
> - Each item represents an end-to-end (frontend + backend) functional and testable feature.
> - Effort: XS ≈ 1 day, S ≈ 2–3 days, M ≈ 1 week, L ≈ 2 weeks, XL ≈ 3+ weeks.
> - V2 features are listed in the V2 section below and are out of scope for the current roadmap.

---

## V2 — Features outside the current roadmap

| # | V2 Feature | Brief description |
|---|------------|-------------------|
| V2.1 | **{Feature}** | {Description} |
```

**Format B: Table-style (9-column)**

Use this format from `romeo-baltio/prompts/feature-list-template.md` when features are fewer or when a tabular view is more useful:

| Building Block | Feature | Description | Value | Success Indicators | Priority | Dev Estimate | Design Estimate | Status |
|---------------|---------|-------------|-------|-------------------|----------|-------------|-----------------|--------|
| ... | ... | ... | ... | ... | ... | ... | ... | ... |

**Choose Format A when:** 20+ features, multiple system sides (app/admin/backend), clear dependency chains.
**Choose Format B when:** <20 features, simpler architecture, table view is sufficient.

**Requirements (both formats):**
- All Open Questions from the Initial PRD feature list must be resolved or explicitly deferred.
- Dev and Design estimates use t-shirt sizing (XS/S/M/L/XL) per the Effort Legend.
- Status reflects validation results (Validated/Adjusted/New/Removed).
- Removed features stay in the list with strikethrough and reason.

#### 3c. Execution Plan (`final-prd/execution-plan.md`)

A detailed execution plan with:
- Phase breakdown with timeline estimates
- Feature dependencies and sequencing
- Team requirements (dev, design, QA)
- Risk register with mitigation strategies
- Launch checklist

### Step 4: Run Definition of Done

1. Read `romeo-baltio/quality/final-prd-dod.md` and evaluate all 14 criteria.
2. Run readiness check from `romeo-baltio/quality/readiness-check.md` using the `final-prd` criteria configuration.
3. Present both the DoD evaluation and readiness check result.

This is the most critical quality gate — the Final PRD must be development-ready. If NOT_READY, list every missing item and work with the PM before proceeding to handoff.

### Step 5: PM Review and Approval

Present the full PRD for final review. This is the last chance to make changes before handoff.

Key questions:
- Is the scope correct and complete?
- Are estimates reasonable?
- Is the execution plan feasible?
- Are all stakeholders aligned?
- Ready for handoff to development?

### Step 6: Finalize

When the PM approves:
1. Update all deliverable statuses to `approved`.
2. Update `.romeo-state.json`:
   - Mark final-prd as `completed`
   - Set `currentStage` to `handoff`
3. Guide: "Final PRD approved! Run `/romeo-handoff` to generate agentOS 2-compatible files for development."

## QUALITY RULES

- The Final PRD must be self-contained — a developer reading only this document should understand the full product.
- Every feature must have Dev and Design estimates.
- All user flows must include error handling.
- The execution plan must be realistic — flag if total effort exceeds available resources.
- Cross-reference all sections — features must appear in flows, entities must appear in the data model, integrations must appear in the architecture.
