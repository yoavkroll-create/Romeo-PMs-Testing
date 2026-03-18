# Naming Conventions

Consistent naming rules across all Romeo Baltio projects.

---

## File Naming

- **All files use kebab-case:** `baseline-spec.md`, `feature-list.md`, `data-samples.json`
- **No spaces, no camelCase, no underscores** in file names
- **Lowercase only** — no uppercase letters in file names
- **Descriptive names** — the file name should tell you what's inside without opening it

---

## Project Slugs

Project slugs are derived from the project name using kebab-case:

| Project Name | Slug |
|-------------|------|
| Smart Scheduler | `smart-scheduler` |
| CherryClipz Mobile App | `cherryclipz-mobile-app` |
| CO-IN Fund Management | `co-in-fund-management` |

Rules:
- Lowercase
- Spaces → hyphens
- Remove special characters (parentheses, periods, etc.)
- Keep it concise — abbreviate if the name is very long

---

## Folder Structure

### Framework Folder

```
romeo-baltio/
├── CLAUDE.md              # Thin loader (IDE auto-loads)
├── .cursorrules           # Thin loader (Cursor auto-loads)
├── commands/              # Stage command files
└── standards/             # All framework standards
```

### Project Folder

All project deliverables live under `projects/{project-slug}/` at the workspace root:

```
projects/{project-slug}/
├── .romeo-state.json      # Project state and progress
├── baseline/              # Stage 1 deliverables
├── research/              # Stage 2 deliverables
├── initial-prd/           # Stage 3 deliverables
├── prototype/             # Stage 4 deliverables
└── final-prd/             # Stage 7 deliverables + handoff
```

---

## Deliverable Names Per Stage

| Stage | Deliverable | File Name |
|-------|------------|-----------|
| Baseline | Baseline Spec | `baseline/baseline-spec.md` |
| Baseline | Capability List | `baseline/capability-list.md` |
| Baseline | Happy Flow | `baseline/happy-flow.md` |
| Baseline | Research Questions | `baseline/research-questions.md` |
| Baseline | Research Prompts | `baseline/research-prompts.md` |
| Research | Research Report | `research/research-report.md` |
| Deep Research | Deep Research Report | `research/deep/deep-research-report.md` |
| Initial PRD | Initial PRD | `initial-prd/initial-prd.md` |
| Initial PRD | Feature List | `initial-prd/feature-list.md` |
| Initial PRD | Core User Flows | `initial-prd/core-user-flows.md` |
| Initial PRD | UX Design Direction | `initial-prd/ux-design-direction.md` |
| Initial PRD | MVP Prototype Prompt | `initial-prd/prototype-prompt-mvp.md` |
| Initial PRD | Future Prototype Prompt | `initial-prd/prototype-prompt-future.md` |
| Prototype | MVP Prototype Spec | `prototype/mvp/prototype-spec-mvp.md` |
| Prototype | Future Prototype Spec | `prototype/future/prototype-spec-future.md` |
| Prototype | Data Model | `prototype/data-model.md` |
| Prototype | Data Samples | `prototype/data-samples.json` |
| Prototype | Integration Strategy | `prototype/integration-strategy.md` |
| Final PRD | Final PRD | `final-prd/final-prd.md` |
| Final PRD | Approved Feature List | `final-prd/approved-feature-list.md` |
| Final PRD | Execution Plan | `final-prd/execution-plan.md` |
| Handoff | Mission | `final-prd/handoff/mission.md` |
| Handoff | Roadmap | `final-prd/handoff/roadmap.md` |
| Handoff | Tech Stack | `final-prd/handoff/tech-stack.md` |
| Handoff | Feature Descriptions | `final-prd/handoff/features/{feature-slug}.md` |

---

## Command File Naming

Command files are organized by stage number:

```
commands/
├── 0-project-initialization/    # Setup commands
├── 1-baseline/                  # Stage 1
├── 2-research/                  # Stage 2
├── 3-initial-prd/               # Stage 3
├── 4-prototype/                 # Stage 4-6 (prototype, validate, iterate)
├── 5-final-prd/                 # Stage 7
└── 6-handoff/                   # Stage 8
```

---

## State File

The project state file is always named `.romeo-state.json` and lives at the project root: `projects/{project-slug}/.romeo-state.json`
