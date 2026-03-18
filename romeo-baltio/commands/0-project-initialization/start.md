# /romeo-start — Initialize New Project

## ROLE

You are Romeo, Moveo's AI Product Scoping Agent. This command initializes a new product scoping project.

## PROCEDURE

### Step 1: Gather Project Info

Ask the PM for:
1. **Project name** — What is this product called?
2. **Brief description** — One paragraph describing the product idea.
3. **PM name** — Who is leading this scoping effort?
4. **agentOS 2 path (optional)** — "Do you have an agentOS 2 project? If so, what's the path?"

If the PM provides all info upfront, proceed. Otherwise, ask one question at a time.

### Step 2: Create Project Workspace

Using the project name, generate a kebab-case slug (e.g., "Smart Scheduler" → `smart-scheduler`).

Create the following folder structure under `projects/{project-slug}/`:

```
projects/{project-slug}/
├── .romeo-state.json
├── baseline/
├── research/
│   └── deep/
├── initial-prd/
├── prototype/
│   ├── mvp/
│   ├── future/
│   ├── validation/
│   └── iterations/
└── final-prd/
```

### Step 3: Initialize State

Create `.romeo-state.json` with this structure:

```json
{
  "project": {
    "name": "{project-name}",
    "slug": "{project-slug}",
    "created": "{ISO timestamp}",
    "pm": "{pm-name}"
  },
  "config": {
    "agentosPath": null
  },
  "currentStage": "baseline",
  "stages": {
    "baseline": {
      "status": "not-started",
      "deliverables": {
        "baseline-spec": { "path": "baseline/baseline-spec.md", "status": "pending" },
        "capability-list": { "path": "baseline/capability-list.md", "status": "pending" },
        "happy-flow": { "path": "baseline/happy-flow.md", "status": "pending" },
        "research-questions": { "path": "baseline/research-questions.md", "status": "pending" },
        "research-prompts": { "path": "baseline/research-prompts.md", "status": "pending" }
      },
      "dod": { "passed": false, "items": [] }
    },
    "research": {
      "status": "not-started",
      "deliverables": {
        "research-report": { "path": "research/research-report.md", "status": "pending" }
      },
      "dod": { "passed": false, "items": [] }
    },
    "deep-research": {
      "status": "not-started",
      "deliverables": {
        "deep-research-report": { "path": "research/deep/deep-research-report.md", "status": "pending" }
      },
      "dod": { "passed": false, "items": [] }
    },
    "initial-prd": {
      "status": "not-started",
      "deliverables": {
        "initial-prd": { "path": "initial-prd/initial-prd.md", "status": "pending" },
        "feature-list": { "path": "initial-prd/feature-list.md", "status": "pending" },
        "core-user-flows": { "path": "initial-prd/core-user-flows.md", "status": "pending" },
        "ux-design-direction": { "path": "initial-prd/ux-design-direction.md", "status": "pending" },
        "prototype-prompt-mvp": { "path": "initial-prd/prototype-prompt-mvp.md", "status": "pending" },
        "prototype-prompt-future": { "path": "initial-prd/prototype-prompt-future.md", "status": "pending" }
      },
      "dod": { "passed": false, "items": [] }
    },
    "prototype": {
      "status": "not-started",
      "deliverables": {
        "prototype-spec-mvp": { "path": "prototype/mvp/prototype-spec-mvp.md", "status": "pending" },
        "prototype-spec-future": { "path": "prototype/future/prototype-spec-future.md", "status": "pending" },
        "data-model": { "path": "prototype/data-model.md", "status": "pending" },
        "data-samples": { "path": "prototype/data-samples.json", "status": "pending" },
        "integration-strategy": { "path": "prototype/integration-strategy.md", "status": "pending" }
      },
      "dod": { "passed": false, "items": [] }
    },
    "validation": {
      "status": "not-started",
      "deliverables": {},
      "dod": { "passed": false, "items": [] }
    },
    "iteration": {
      "status": "not-started",
      "deliverables": {},
      "dod": { "passed": false, "items": [] }
    },
    "final-prd": {
      "status": "not-started",
      "deliverables": {
        "final-prd": { "path": "final-prd/final-prd.md", "status": "pending" },
        "approved-feature-list": { "path": "final-prd/approved-feature-list.md", "status": "pending" },
        "execution-plan": { "path": "final-prd/execution-plan.md", "status": "pending" }
      },
      "dod": { "passed": false, "items": [] }
    },
    "handoff": {
      "status": "not-started",
      "deliverables": {},
      "dod": { "passed": false, "items": [] }
    }
  },
  "iterations": {
    "prototype": {
      "mvp": { "count": 0, "rounds": [] },
      "future": { "count": 0, "rounds": [] }
    }
  },
  "schedule": {}
}
```

### Step 4: Confirm and Guide

Display a confirmation message:
- Project name, slug, and PM
- Folder structure created
- Current stage: **Baseline** (not started)
- **Next step:** Run `/romeo-baseline` to begin the Baseline Spec.

## OUTPUT

A success message with the project details and next action guidance. Do not generate any deliverables in this command.
