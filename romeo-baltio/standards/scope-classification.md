# Scope Classification

How to classify features into MVP, V2, V3, and Out of Scope in Romeo Baltio.

---

## Scope Tiers

### MVP (V1)

Features essential to validate the core product concept. Without these, the product cannot demonstrate its value proposition.

**Criteria — a feature is MVP if:**
- It solves the primary user pain point identified in the Baseline Spec
- It's required for the core happy flow to work end-to-end
- The product cannot be demoed or piloted without it
- It's needed to test the core hypothesis

**Litmus test:** "If we remove this feature, can we still validate the core idea?" If no → MVP. If yes → probably V2.

### V2

Important features that enhance the product but are not required for initial validation. These make the product better, not possible.

**Criteria — a feature is V2 if:**
- It extends core functionality (more options, richer data, advanced workflows)
- It addresses secondary personas or edge-case use cases
- It requires MVP infrastructure to exist first
- It's valuable but won't invalidate the product if missing from launch

### V3 / Future

Nice-to-have features for longer-term consideration.

**Criteria — a feature is V3 if:**
- It's an advanced capability (AI-powered insights, advanced analytics, white-labeling)
- It requires market validation before investing (do users actually want this?)
- It depends on V2 features being built first
- It's an optimization or scale feature (multi-region, enterprise SSO)

### Out of Scope

Explicitly excluded features. Documenting these prevents scope creep and expectation misalignment.

**Criteria — a feature is Out of Scope if:**
- It's not aligned with the product mission
- It requires a separate product initiative or team
- It was explicitly rejected during scoping discussions
- It's a different product disguised as a feature

---

## Decision Matrix

Use this matrix to classify features when unsure:

| Question | Yes → | No → |
|----------|-------|------|
| Is it required for the core happy flow? | MVP | Continue ↓ |
| Can the product be demoed without it? | Continue ↓ | MVP |
| Does it extend a core MVP feature? | V2 | Continue ↓ |
| Does it serve a secondary persona? | V2 | Continue ↓ |
| Does it require V2 to exist first? | V3 | Continue ↓ |
| Is it aligned with the product mission? | V3 | Out of Scope |

---

## Common Anti-Patterns

### Features Hiding in MVP That Should Be V2

Watch for these scope-creep signals:
- **"While we're at it..."** — A feature tacked onto an MVP feature because they share a screen
- **Admin dashboards** — Often V2 unless there's a regulatory requirement
- **Advanced analytics** — Basic metrics are MVP; advanced dashboards and reports are V2
- **Multi-role support** — If the product has 3 user roles, MVP might only need 2
- **Notification systems** — Email/push notifications beyond the most basic are usually V2

### Features Marked V2 That Are Actually MVP Blockers

Watch for these under-scoping signals:
- **Authentication & authorization** — If users need to log in, this is MVP, not V2
- **Data import/migration** — If users can't start without their existing data, this is MVP
- **Core integrations** — If the product can't function without a specific API, that integration is MVP
- **Error handling for core flows** — Basic error states in the happy flow are MVP

---

## Prioritization Frameworks

When building the feature list, use one of these frameworks to justify priority assignments. Don't just assign MVP/V2/V3 by gut — show the reasoning.

### RICE Scoring (Recommended for Feature Lists)

Score each feature on four dimensions:

| Dimension | Question | Scale |
|-----------|----------|-------|
| **Reach** | How many users will this impact in a given period? | Number of users/month |
| **Impact** | How much will this move the needle per user? | 3 = massive, 2 = high, 1 = medium, 0.5 = low, 0.25 = minimal |
| **Confidence** | How sure are we about reach and impact? | 100% = high, 80% = medium, 50% = low |
| **Effort** | How many person-weeks to build? | Person-weeks (use estimation guide) |

**RICE Score = (Reach × Impact × Confidence) / Effort**

Higher score = higher priority. Use this when the PM needs help deciding between competing features.

### MoSCoW (Recommended for Scope Discussions)

Use MoSCoW when the PM needs a simpler, faster classification:

| Category | Meaning | Baltio Mapping |
|----------|---------|---------------|
| **Must Have** | The product fails without this | MVP |
| **Should Have** | Important but not critical for launch | MVP (if small) or V2 |
| **Could Have** | Nice to have, include if time allows | V2 |
| **Won't Have (this time)** | Explicitly deferred | V3 or Out of Scope |

### When to Use Which

- **RICE** — When the PM is struggling to prioritize a long feature list (15+ features) and needs data-driven justification
- **MoSCoW** — When the PM needs a quick gut-check classification or when discussing scope with stakeholders
- **Both** — RICE to score, MoSCoW to communicate. Score with RICE internally, present as MoSCoW to stakeholders.

---

## Scope Change Protocol

Moving a feature between tiers requires:

1. **PM decision** — the PM explicitly approves the change
2. **Rationale documented** — why the feature is moving (e.g., "moved to V2 because user interviews showed this isn't a launch blocker")
3. **Impact assessed** — does moving this feature affect other features, flows, or estimates?
4. **State updated** — `.romeo-state.json` and the feature list reflect the change

Never silently move features between tiers. Always flag the change to the PM.
