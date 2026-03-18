# Spec Template

This is the standard agentOS 2 specification format used for handoff feature files. It matches the format used in Testchair, CherryClipz, and CO-IN specs.

## When to Use

- During `/romeo-handoff` for generating per-feature spec files
- As a reference for `shape-spec` output format in agentOS 2
- When the PM needs a standalone spec for a specific feature

## Template

```markdown
# Specification: {Feature Name}

## Goal

{1-2 sentences describing what this feature accomplishes and why. Be specific about the outcome, not just the mechanism.}

## User Stories

- As a {role}, I want to {action} so that {outcome}.
- As a {role}, I want to {action} so that {outcome}.

## Specific Requirements

**{Requirement Group 1 — e.g., "Account Type Selection Screen"}**

- {Specific requirement — be precise about behavior, not vague. Include exact values, states, and conditions.}
- {Requirement with implementation detail — e.g., "Next button is disabled until one account type is selected."}
- {Requirement referencing specific components — e.g., "Use the existing `EntityCard` component for each card."}
- {Requirement about text/copy — e.g., 'Subtitle inside step component: "Hello there! Choose your account type"'}

**{Requirement Group 2 — e.g., "Data Flow"}**

- {Requirements about how data moves through the system}
- {Requirements about state management}
- {Requirements about API calls or computations}

**{Requirement Group 3 — e.g., "Responsive / No-Scroll"}**

- {Layout requirements}
- {Viewport requirements}

**{Requirement Group 4 — e.g., "State Preservation"}**

- {How state is maintained across navigation}
- {Refresh behavior}

## Visual Design

{Reference to Figma, design tokens, or specific visual specifications.}

- {Visual spec — e.g., "Four cards stacked vertically with ~12px gap; white cards, neutral border, 12px border-radius."}
- {Visual spec — e.g., "Next button: full-width, 53px tall, 12px border-radius; disabled state uses neutral gray."}
- {Reference — e.g., "`planning/visuals/account-type-selection.md` (Figma node `1:3530`, file `9EHO...`)"}

If no Figma exists yet, describe the visual direction with enough detail for a designer or AI builder to implement:
- Layout structure (grid, stack, sidebar + content, etc.)
- Key component patterns (cards, tables, modals, etc.)
- Color/spacing direction (refer to design system if one exists)

## Existing Code to Leverage

{Table of existing components, patterns, or code that should be reused. This prevents reinventing the wheel and ensures consistency.}

| Asset | Location | How it's used |
|-------|----------|---------------|
| **{Component/pattern}** | `{file path}` | {How to reuse — what to keep, what to modify} |
| **{Component/pattern}** | `{file path}` | {How to reuse} |

## Edge Cases

- **{Edge case name}** — {How to handle it}
- **{Edge case name}** — {How to handle it}
- **{Edge case name}** — {How to handle it or "Deferred — acceptable for MVP"}

## Out of Scope

- {Thing explicitly NOT being built in this spec}
- {Thing NOT being changed}
- {Thing deferred to a future spec}

## Verification

- [ ] {Verification step — how to confirm the feature works correctly}
- [ ] {Verification step}
- [ ] {Verification step}
```

## Writing Guidelines

1. **Be specific, not vague.** "Button is disabled until selection" > "Button should be appropriately enabled."
2. **Reference existing code.** Always search the codebase for reusable components before specifying new ones.
3. **Group requirements by area.** Use bold group headers (`**Screen Name**`, `**Data Flow**`, `**Responsive**`) to organize related requirements.
4. **Include exact values.** Pixel sizes, color tokens, specific strings, field types, enum values.
5. **Edge cases are mandatory.** Every spec must consider at least 3 edge cases: navigation, state, and error handling.
6. **Out of Scope is mandatory.** Explicitly stating what's NOT included prevents scope creep during implementation.
7. **Visual Design can reference Figma or describe layout.** If Figma exists, reference nodes. If not, describe layout, components, and styling with enough detail for implementation.

## Spec Directory Structure

When a spec is generated via agentOS 2's `shape-spec` → `write-spec`, it lives in:

```
specs/{YYYY-MM-DD}-{feature-slug}/
├── spec.md                    # Main specification (this template)
├── planning/
│   ├── initialization.md      # Raw feature idea/description
│   ├── requirements.md        # Q&A decisions from shape-spec
│   └── visuals/
│       └── {screen-name}.md   # Visual references per screen
├── visual/
│   └── design-tokens.md       # Specific colors, spacing, icons
├── implementation/             # Created during implement-tasks
├── shape.md                   # Architecture decisions (optional)
└── references.md              # External docs and codebase paths
```
