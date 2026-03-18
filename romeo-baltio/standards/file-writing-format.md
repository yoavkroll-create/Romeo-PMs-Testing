# File Writing Format

How every deliverable in Romeo Baltio should be structured, formatted, and labeled.

---

## Metadata Header

Every deliverable file must start with a YAML frontmatter block:

```yaml
---
project: {project-name}
stage: {stage-name}
created: {ISO date, e.g., 2025-03-18}
updated: {ISO date}
status: draft | review | approved
---
```

### Status Lifecycle

```
draft → review → approved
```

| Status | Meaning | Transition Rule |
|--------|---------|-----------------|
| `draft` | Initial generation or work-in-progress | Default on creation |
| `review` | PM is actively reviewing and providing feedback | Set when draft is presented to PM |
| `approved` | PM has signed off; DoD and readiness check passed | Set only after DoD passes and PM confirms |

A deliverable may move backwards (`approved` → `review`) if a later stage surfaces issues that require revision.

---

## Markdown Structure

### Heading Hierarchy

- **H1 (`#`)** — Document title. Exactly one per file. Format: `# {Type}: {Project Name}` (e.g., `# Baseline Spec: Smart Scheduler`)
- **H2 (`##`)** — Major sections (e.g., `## The Problem`, `## Users`, `## Core Features`)
- **H3 (`###`)** — Subsections within a major section (e.g., `### User Personas`, `### Competitor: Slack`)
- **H4 (`####`)** — Rarely used. Only for deeply nested content within subsections.

### Tables

Use standard markdown pipe syntax. Always include the header row and alignment row:

```markdown
| Column A | Column B | Column C |
|----------|----------|----------|
| data     | data     | data     |
```

**When to use tables vs. bullet lists:**
- Use **tables** for structured, multi-attribute data (features, competitors, permissions)
- Use **bullet lists** for sequential items, single-attribute lists, or narrative points
- If a table would have only 2 columns and one is just a label, use bold bullet points instead

### Diagrams

Use Mermaid fenced code blocks. Choose the right diagram type:

| Diagram Type | When to Use | Example |
|-------------|-------------|---------|
| `flowchart TD` | User flows, process flows, navigation maps | Step-by-step user journey |
| `erDiagram` | Entity relationships, data models | Database schema |
| `stateDiagram-v2` | Entity lifecycle, status transitions | Order states: Draft → Active → Complete |
| `gantt` | Execution plans, timelines | Phase breakdown with dependencies |
| `graph TD` | System architecture, component relationships | Frontend → Backend → Database |

### Text Formatting

- **Bold** for key terms, feature names, persona names, and emphasis
- *Italic* for product names, book titles, and soft emphasis
- `Code` for file names, paths, command names, field names, and technical terms
- Use **numbered lists** for sequential steps and ordered processes
- Use **bullet lists** for unordered items and attributes

---

## Deliverable Organization

### One File Per Deliverable

Each deliverable is a standalone `.md` file (or `.json` for data samples) in its stage directory. Never combine multiple deliverables into a single file.

### Stage Directory Structure

```
projects/{project-slug}/
├── baseline/
│   ├── baseline-spec.md
│   ├── capability-list.md
│   ├── happy-flow.md
│   ├── research-questions.md
│   └── research-prompts.md
├── research/
│   ├── research-report.md
│   └── deep/
│       └── deep-research-report.md
├── initial-prd/
│   ├── initial-prd.md
│   ├── feature-list.md
│   ├── core-user-flows.md
│   ├── ux-design-direction.md
│   ├── prototype-prompt-mvp.md
│   └── prototype-prompt-future.md
├── prototype/
│   ├── mvp/
│   │   └── prototype-spec-mvp.md
│   ├── future/
│   │   └── prototype-spec-future.md
│   ├── data-model.md
│   ├── data-samples.json
│   └── integration-strategy.md
├── final-prd/
│   ├── final-prd.md
│   ├── approved-feature-list.md
│   ├── execution-plan.md
│   └── handoff/
│       ├── mission.md
│       ├── roadmap.md
│       ├── tech-stack.md
│       └── features/
│           └── {feature-slug}.md
└── .romeo-state.json
```

---

## Content Quality Rules

1. **Be specific, not generic.** "Users want it to be faster" is not a deliverable-quality statement. "Fund managers need portfolio NAV calculations to complete in under 5 seconds" is.

2. **Cite sources.** When referencing prior stage artifacts, use explicit citations: "Per the Baseline Spec's capability list, ..." or "Research finding #3 indicates ..."

3. **No placeholder text.** Never use "Lorem ipsum", "TBD", or "[Insert here]" in approved deliverables. If something is unknown, it should be listed as an Open Question.

4. **Realistic sample data.** Data samples must use realistic names, amounts, dates, and states — not "Test User 1" or "$100".

5. **Self-contained sections.** Each major section should be understandable without reading the entire document. Cross-reference other sections when needed.
