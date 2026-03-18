# Feature List Template

## Initial PRD Feature List (8 Columns)

Use this format for the feature list in the Initial PRD stage:

| Building Block | Feature | Description | Value | Success Indicators | Priority | Prototype Notes | Open Questions |
|---------------|---------|-------------|-------|-------------------|----------|-----------------|----------------|
| {System area} | {Feature name} | {What it does} | {Why it matters} | {How to measure success} | {MVP / V2 / V3} | {What to prototype} | {Unknowns} |

### Column Definitions

1. **Building Block** — The system area or module this feature belongs to (e.g., "User Management", "Analytics", "Workflow Engine"). Group related features under the same building block.

2. **Feature** — The feature name. Keep it concise and descriptive (e.g., "Role-Based Access Control", "Real-Time Dashboard").

3. **Description** — What the feature does. One clear sentence. Avoid technical implementation details — describe the user-facing behavior.

4. **Value** — Why this feature matters. Connect it to user pain points or business goals from the Baseline Spec and Research.

5. **Success Indicators** — How you'll know this feature works. Measurable outcomes (e.g., "Users can complete onboarding in < 3 minutes", "Dashboard loads in < 2 seconds").

6. **Priority** — Scope classification:
   - **MVP** — Must have for first release
   - **V2** — Important but can wait for second release
   - **V3** — Nice to have, future consideration
   - **Out of Scope** — Explicitly excluded

7. **Prototype Notes** — What aspect of this feature should be prototyped and how (e.g., "Full flow with mock data", "Static screens only", "API integration required").

8. **Open Questions** — Unresolved questions that affect this feature's design or priority.

---

## Final PRD Feature List (9 Columns)

Use this format for the Approved Feature List in the Final PRD stage. Adds development/design estimates:

| Building Block | Feature | Description | Value | Success Indicators | Priority | Dev Estimate | Design Estimate | Status |
|---------------|---------|-------------|-------|-------------------|----------|-------------|-----------------|--------|
| {System area} | {Feature name} | {What it does} | {Why it matters} | {How to measure} | {MVP/V2/V3} | {XS/S/M/L/XL} | {XS/S/M/L/XL} | {Status} |

### Additional Column Definitions (Final PRD)

8. **Dev Estimate** — Development effort using t-shirt sizing (see Effort Legend below).

9. **Design Estimate** — Design effort using the same t-shirt sizing scale.

10. **Status** — Current state:
    - **Validated** — Confirmed through prototype testing
    - **Adjusted** — Modified based on validation feedback
    - **New** — Added after validation
    - **Removed** — Cut from scope (keep in table with strikethrough)

---

## Detailed Feature Table (10 Columns)

Use this format for detailed feature breakdown — useful for handoff and development planning. This is the format used for step-by-step feature decomposition (e.g., CO-IN's feature-table-estimates):

| Step # | Step Name | System Side | Feature Name | Detail | Logic/Data Flow | Dev Estimate | Design Estimate | Priority | Dependencies |
|--------|-----------|------------|--------------|--------|----------------|-------------|-----------------|----------|-------------|
| {#} | {Step or screen name} | {App / Admin / Backend / Infra} | {Feature name} | {What it does in detail} | {Where data comes from/goes, API calls, state changes} | {XS/S/M/L/XL} | {XS/S/M/L/XL} | {P0/P1/P2} | {What must be built first} |

### Additional Column Definitions (Detailed Table)

1. **Step #** — Sequential number following the product flow order (e.g., setup → onboarding → core features → admin → analytics).

2. **Step Name** — The screen, flow, or system area this feature belongs to (e.g., "Onboarding Step 2", "Deal Details Screen", "Admin Dashboard").

3. **System Side** — Which part of the system owns this feature:
   - **App** — End-user facing (mobile or web)
   - **Admin** — Back-office / admin panel
   - **Backend** — API, services, infrastructure
   - **Infra** — DevOps, CI/CD, hosting, monitoring

4. **Feature Name** — Concise feature name.

5. **Detail** — Detailed description of what is built, including specific behaviors and states.

6. **Logic/Data Flow** — Where the data comes from, where it goes, what APIs are called, what state changes occur. This is critical for development — it bridges product and engineering.

7. **Priority** — Urgency classification:
   - **P0** — Launch blocker, must be in MVP
   - **P1** — Important, should be in MVP if time allows
   - **P2** — Nice to have, can defer to V2

8. **Dependencies** — What must be built before this feature can start (reference Step #).

---

## Effort Legend

All effort estimates across all feature list formats use this scale:

| Size | Effort | Example |
|------|--------|---------|
| **XS** | ~1 day | Config change, copy update, simple toggle |
| **S** | 2–3 days | Simple feature, single component, basic CRUD |
| **M** | ~1 week | Moderate feature, multiple components, integration |
| **L** | ~2 weeks | Complex feature, multiple systems, new patterns |
| **XL** | 3+ weeks | Major feature, architectural changes, new infrastructure |

---

## Guidelines

- Sort features by Building Block, then by Priority (MVP first).
- Every MVP feature must have a clear Success Indicator.
- Open Questions should be resolved before Final PRD.
- The feature list is the single source of truth for product scope.
- agentOS 2 handoff will use this list to generate `product/roadmap.md`.
- When features are numerous (20+), prefer the Detailed 10-column format for development clarity.
- The 10-column format is especially useful when multiple system sides (App, Admin, Backend) are involved.
