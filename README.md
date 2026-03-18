# Romeo OS

**Romeo OS** is Moveo's AI-powered product scoping framework. It guides Product Managers from a raw product idea through a structured, multi-stage process — Baseline → Research → Initial PRD → Prototype → Validation → Final PRD — producing a development-ready PRD and agentOS 2 handoff files. Every stage enforces quality gates (Definition of Done + Readiness Checks) and tracks state so you can pause and resume at any point.

---

## Prerequisites

- **Claude Code** (auto-loads `CLAUDE.md`) or **Cursor** (auto-loads `.cursorrules`)
- A terminal or IDE with access to the `romeo-os/` folder

---

## Quick Start

1. Copy the `romeo-os/` folder into your project root.
2. Open the project in Claude Code or Cursor.
3. Run `/romeo-start` to initialize a new scoping project.
4. Follow Romeo's guidance through each stage.

---

## Command Reference

| # | Stage | Command | Description |
|---|-------|---------|-------------|
| — | Setup | `/romeo-start` | Initialize a new project workspace |
| — | Status | `/romeo-status` | Show progress dashboard |
| 1 | Baseline | `/romeo-baseline` | Generate Baseline Spec (problem, users, capabilities) |
| 2a | Research | `/romeo-research` | Market research report |
| 2b | Deep Research | `/romeo-deep-research` | Deep research with targeted prompts |
| 3 | Initial PRD | `/romeo-initial-prd` | Initial PRD, feature list, flows, UX, prototype prompts |
| 4 | Prototype | `/romeo-prototype` | Prototype specs (MVP + Future), data model, samples, integrations |
| 5 | Validation | `/romeo-validate-prototype` | Evaluate prototype against goals (MVP or Future) |
| 6 | Iteration | `/romeo-iterate-prototype` | Generate iteration plan from validation findings |
| 7 | Final PRD | `/romeo-final-prd` | Comprehensive, development-ready PRD |
| 8 | Handoff | `/romeo-handoff` | Generate agentOS 2-compatible files |

---

## File Structure

```
romeo-os/
├── CLAUDE.md                              # Master system prompt (identity, framework, rules)
├── .cursorrules                           # Cursor IDE mirror of CLAUDE.md
├── README.md                              # This file
├── .gitignore                             # Ignores .DS_Store and projects/
├── commands/
│   ├── 0-project-initialization/
│   │   ├── start.md                       # /romeo-start
│   │   └── status.md                      # /romeo-status
│   ├── 1-baseline/
│   │   └── baseline.md                    # /romeo-baseline
│   ├── 2-research/
│   │   ├── research.md                    # /romeo-research
│   │   └── deep-research.md               # /romeo-deep-research
│   ├── 3-initial-prd/
│   │   └── initial-prd.md                 # /romeo-initial-prd
│   ├── 4-prototype/
│   │   ├── prototype.md                   # /romeo-prototype
│   │   ├── validate-prototype.md          # /romeo-validate-prototype
│   │   └── iterate-prototype.md           # /romeo-iterate-prototype
│   ├── 5-final-prd/
│   │   └── final-prd.md                   # /romeo-final-prd
│   └── 6-handoff/
│       └── handoff.md                     # /romeo-handoff
├── prompts/
│   ├── feature-list-template.md           # 8-column feature list template
│   ├── research-prompt-template.md        # Research prompt template
│   └── spec-template.md                   # agentOS 2 spec template
└── quality/
    ├── baseline-dod.md                    # Baseline Definition of Done
    ├── research-dod.md                    # Research DoD
    ├── initial-prd-dod.md                 # Initial PRD DoD
    ├── prototype-dod.md                   # Prototype DoD
    ├── final-prd-dod.md                   # Final PRD DoD
    └── readiness-check.md                 # Reusable readiness check engine
```

---

## Configuration

### agentOS 2 Path

If your project hands off to agentOS 2, configure the path during `/romeo-start` or set it manually in your project's `.romeo-state.json`:

```json
{
  "config": {
    "agentosPath": "/path/to/your/agent-os"
  }
}
```

The handoff stage (`/romeo-handoff`) reads this path from state. If not set, Romeo will ask for it at handoff time.

---

## Output

All project deliverables are saved under `projects/{project-slug}/` at the workspace root. This folder is `.gitignore`d by default — it contains generated artifacts, not source code.
