# Prototype — Definition of Done

## Criteria

| # | Criterion | Description |
|---|-----------|-------------|
| 1 | **Prototype goals are defined** | Clear, measurable goals for what the prototype must prove. |
| 2 | **Both MVP and Future prototype specs exist with distinct scopes** | MVP spec contains only MVP features. Future spec extends MVP with Vision features. Scopes do not overlap ambiguously. |
| 3 | **All MVP flows are specified** | Every core user flow from the Initial PRD has a prototype-level implementation plan in the MVP spec. |
| 4 | **Screen structure is complete** | All screens are listed with purpose, components, and flow mapping across both specs. |
| 5 | **Data model supports all flows** | Every entity and relationship needed for the defined flows is modeled. Vision-only entities marked `[Future]`. |
| 6 | **Sample data is realistic** | Data samples cover all entity types, multiple states, realistic content, and include `"scope": "mvp"` or `"scope": "future"` annotations. |
| 7 | **Integration strategy is defined** | For each external dependency, the prototype approach (mock/sandbox/real) is specified with MVP/Future scope noted. |
| 8 | **Demo mode works end-to-end for MVP. Future has demo scenario defined.** | MVP has a golden-path demo that can run without manual setup. Future has a demo scenario defined (execution is optional). |
| 9 | **Technical setup is specified** | Stack, dependencies, and run instructions are documented. |
| 10 | **All 5 deliverables exist** | prototype-spec-mvp.md, prototype-spec-future.md, data-model.md, data-samples.json, and integration-strategy.md are created. |

## Evaluation

- All 10 criteria must pass for the stage to be marked complete.
- The prototype stage is about the specification — the actual build happens outside Romeo.
- Validation (`/romeo-validate-prototype`) evaluates the built prototype, not just the spec.
- MVP validation is required for stage progression. Future validation is optional.
