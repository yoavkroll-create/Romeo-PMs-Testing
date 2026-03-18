# Estimation Guide

T-shirt sizing definitions and estimation rules for Romeo Baltio.

---

## T-Shirt Size Definitions

All effort estimates across the framework use this scale:

| Size | Effort | Dev Examples | Design Examples |
|------|--------|-------------|-----------------|
| **XS** | ~1 day | Config change, copy update, simple toggle, environment variable | Icon swap, color change, copy update |
| **S** | 2–3 days | Simple feature, single component, basic CRUD, webhook handler | Single screen design, component variant, simple form layout |
| **M** | ~1 week | Moderate feature, multiple components, API integration, data pipeline | Multi-screen flow, responsive layouts, interactive components |
| **L** | ~2 weeks | Complex feature, multiple systems, new patterns, state machines | Complex interactions, design system creation, multi-state flows |
| **XL** | 3+ weeks | Major feature, architectural changes, new infrastructure, migration | Full product redesign, extensive prototyping, design system overhaul |

---

## Dev vs. Design Effort

Dev and Design estimates are **independent**. A feature can have different sizes for each:

| Feature | Dev | Design | Why |
|---------|-----|--------|-----|
| Rich text editor | L | S | Complex engineering, simple UI (use existing editor component) |
| Onboarding wizard | S | L | Simple CRUD flow, but requires extensive UX research and illustration |
| Dashboard with charts | M | M | Both moderate — API aggregation + chart layout design |
| Email notification system | M | XS | Backend work, minimal design (email template) |

---

## Estimation Assumptions

- Estimates assume **a single developer or designer** working at normal pace
- **Do not factor in:** ramp-up time, context switching, meetings, or multi-tasking
- **Do factor in:** testing, code review, and basic QA for dev estimates
- **Do factor in:** design review, iteration rounds, and asset export for design estimates

---

## When to Estimate

| Stage | Estimation Level |
|-------|-----------------|
| Baseline | No estimates — too early |
| Research | No estimates |
| Initial PRD | Informal effort sense in Prototype Notes column — "this feels like a big build" |
| Prototype | No formal estimates — focus on what to prototype |
| Final PRD | **Formal estimates required** — Dev and Design for all MVP features, Dev for V2 features |
| Handoff | Estimates carried from Final PRD into roadmap |

---

## Priority vs. Estimate

These are orthogonal dimensions. Don't confuse them:

| Dimension | What It Measures | Scale |
|-----------|-----------------|-------|
| **Priority** | How urgent / important the feature is | MVP / V2 / V3 (or P0 / P1 / P2) |
| **Estimate** | How much effort it takes to build | XS / S / M / L / XL |

A feature can be high priority AND low effort (P0, XS) or high priority AND high effort (P0, XL). Priority determines *what* to build; estimates determine *how long*.

---

## Estimation Anti-Patterns

| Anti-Pattern | Problem | Fix |
|-------------|---------|-----|
| **Everything is M** | Lack of granularity — not thinking critically about effort | Force a spread: roughly 20% XS/S, 40% M, 30% L, 10% XL |
| **Underestimating integrations** | "It's just an API call" — ignoring auth, error handling, rate limits, data mapping | Always add one size up for external integrations |
| **Forgetting design effort** | Dev-only estimates ignore UX work that blocks development | Always estimate both Dev and Design |
| **Anchoring to ideal conditions** | Estimating best-case, not realistic-case | Estimate for "normal" pace, not "everything goes perfectly" |
| **Estimating unknowns as S** | Unknown scope defaults to small | If you don't know how big it is, it's at least M |

---

## Effort Legend Reference

For use in feature lists and roadmaps:

```
XS ≈ 1 day | S ≈ 2–3 days | M ≈ 1 week | L ≈ 2 weeks | XL ≈ 3+ weeks
```
