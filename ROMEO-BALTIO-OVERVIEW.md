# Romeo Baltio

## AI-Powered Product Scoping Framework

**By Moveo | Yoav Kroll, PM Team Lead**

---

## What Is Romeo Baltio?

Romeo Baltio is an AI-powered product scoping framework that transforms how Product Managers work. It pairs a PM with an AI agent named **Baltio** — a senior-level PM and Tech Lead assistant — that guides the scoping process from a raw product idea to a development-ready PRD.

Baltio doesn't generate documents autonomously. It works **with** the PM through structured conversation: asking one question at a time, challenging vague answers with real-world knowledge, and co-creating deliverables through multiple iterations. The PM stays in control; Baltio ensures nothing falls through the cracks.

The output is a comprehensive, validated PRD ready for handoff to development — specifically formatted for Moveo's agentOS 2 Spec-Driven Development workflow.

---

## The Problem Romeo Baltio Solves

Product scoping today is inconsistent, time-consuming, and error-prone:

- **PMs work in silos** — each PM has their own approach, templates, and quality bar. There's no shared standard for what a "good PRD" looks like.
- **Critical gaps surface late** — missing user flows, underestimated integrations, and undefined edge cases appear during development, not during scoping.
- **Context is lost between stages** — research findings don't flow into feature lists. Prototype learnings don't make it back into the PRD. Each stage starts from scratch.
- **Quality is subjective** — without structured quality gates, "done" means different things to different people.

Romeo Baltio enforces a consistent, high-quality process that any PM can follow — while adapting to each project's unique needs.

---

## How It Works

### The Scoping Framework

Romeo Baltio guides PMs through **7 stages + 1 handoff**, each with defined inputs, outputs, and quality gates:

```
/romeo-start → Baseline → Research → Initial PRD → Prototype → Validation → Final PRD → Handoff
```

| # | Stage | What Happens | Key Output |
|---|-------|-------------|------------|
| 0 | **Start** | Project initialization + business context capture | `business-context.md`, project workspace |
| 1 | **Baseline** | Define the problem, users, happy flow, and capabilities | Baseline Spec, Capability List, Happy Flow, Research Questions |
| 2 | **Research** | Market research, competitor analysis, user validation | Research Report, Deep Research Report |
| 3 | **Initial PRD** | First structured product definition with features, flows, and scope | Initial PRD, Feature List, Core Flows, UX Direction, Prototype Prompts |
| 4 | **Prototype** | Two prototype specs (MVP + Future) with data model | MVP Spec, Future Spec, Data Model, Sample Data, Integration Strategy |
| 5 | **Validation** | Evaluate prototype against goals and success metrics | Validation Report |
| 6 | **Iteration** | Address validation findings, refine prototype | Iteration Plan |
| 7 | **Final PRD** | Comprehensive, development-ready product definition | Final PRD, Approved Feature List, Execution Plan |
| 8 | **Handoff** | Generate agentOS 2-compatible files for development | Mission, Roadmap, Tech Stack, Feature Descriptions |

### Every Stage Is Gated

No stage is marked complete without passing:
1. **Definition of Done (DoD)** — a checklist of criteria specific to each stage
2. **Readiness Check** — a structured validation that produces a binary READY / NOT_READY result

If a stage isn't ready, Baltio identifies exactly what's missing and works with the PM to fix it.

---

## What Makes Romeo Baltio Different

### 1. Collaborative, Not Autonomous

Baltio is not a "press a button, get a PRD" tool. It works through conversation:

- **Atomic interviewing** — asks one question at a time during data gathering, never overwhelming the PM with compound requests
- **Section-by-section approval** — presents each section for review before writing to file
- **2-3 iteration rounds minimum** — no deliverable is finalized on the first pass

### 2. Challenges Like a Senior PM + Tech Lead

Baltio doesn't accept vague inputs. It pushes back with:

- **Real product references:** "Slack solved a similar onboarding problem by doing X — have you considered that approach?"
- **Industry benchmarks:** "For B2B SaaS, average time-to-value is under 10 minutes. Your flow looks like 30+."
- **Engineering risk flags:** "This real-time sync feature sounds simple but usually requires WebSocket infrastructure and conflict resolution."
- **Prioritization frameworks:** "Using RICE scoring, this feature ranks higher than the one you're prioritizing."

### 3. Context Never Gets Lost

Every stage builds on the last. Baltio enforces:

- **Automatic data inheritance** — pulls forward personas, scope decisions, and research findings from prior stages
- **Confirm, don't re-ask** — presents inherited data for confirmation instead of making the PM repeat themselves
- **Explicit citations** — every claim traces back to a specific prior artifact
- **Contradiction detection** — flags when a new decision conflicts with an earlier one

### 4. Business Context First

Before any product scoping begins, `/romeo-start` captures the business context:

- Company vision and strategic alignment
- Problem statement with market trigger
- KPIs using SMART framework (baseline → target → timeframe)
- Competitive landscape and unfair advantage
- Stakeholders, blockers, GTM strategy, and ROI

This context flows into every downstream stage automatically.

### 5. Enforced Quality Standards

The `standards/` folder contains the framework's operating rules:

| Standard | What It Enforces |
|----------|-----------------|
| **Interaction Protocol** | Atomic interviewing, iteration loop, challenging with real knowledge |
| **File Writing Format** | Metadata headers, status lifecycle, section data sources |
| **Naming Conventions** | kebab-case files, project slugs, deliverable names per stage |
| **Scope Classification** | MVP/V2/V3/Out of Scope criteria, RICE and MoSCoW frameworks |
| **Estimation Guide** | T-shirt sizing (XS–XL) for both dev and design effort |
| **Cross-Reference Rules** | How each stage cites prior stages, contradiction handling |
| **Quality Gates** | Definition of Done per stage + reusable readiness check engine |

### 6. Language Flexibility

Baltio conducts the conversation in the PM's preferred language (Hebrew, English, etc.) but **all deliverables are written in professional English** using industry-standard terminology.

---

## The Output

A fully scoped project produces **20+ deliverables** across all stages, organized in a clean folder structure:

```
projects/{project-name}/
├── business-context.md              # Business context from initialization
├── baseline/                        # Problem, users, capabilities, happy flow
├── research/                        # Market research + deep research
├── initial-prd/                     # PRD, features, flows, UX, prototype prompts
├── prototype/                       # MVP + Future specs, data model, integrations
├── final-prd/                       # Final PRD, approved features, execution plan
│   └── handoff/                     # agentOS 2-ready files
└── .romeo-state.json                # Full project state and progress tracking
```

The Final PRD is a **self-contained, development-ready document** covering:
- System definition, users, and problem (research-backed)
- Approved feature list with dev and design estimates
- User flows with error handling
- Domain model and state machines
- Architecture and tech stack
- Roles and permissions
- Analytics framework
- Execution plan with phases, dependencies, and risks
- Prototype validation summary and learnings

---

## How to Install

From any project's root directory:

```bash
git clone https://github.com/anthropics/Romeo-PMs-Testing.git /tmp/romeo-baltio-src && \
cp -r /tmp/romeo-baltio-src/romeo-baltio . && \
rm -rf /tmp/romeo-baltio-src
```

Then open the project in **Claude Code** or **Cursor** and run `/romeo-start`.

---

## Architecture

```
romeo-baltio/
├── CLAUDE.md                    # System prompt loader (Claude Code)
├── .cursorrules                 # System prompt loader (Cursor IDE)
├── commands/                    # Stage command definitions (11 commands)
└── standards/                   # Framework operating rules
    ├── system-prompt.md         # Baltio identity and behavior
    ├── interaction-protocol.md  # How Baltio collaborates with PMs
    ├── file-writing-format.md   # Deliverable structure and quality
    ├── naming-conventions.md    # File and folder naming rules
    ├── scope-classification.md  # Feature prioritization (RICE, MoSCoW)
    ├── estimation-guide.md      # T-shirt sizing definitions
    ├── cross-reference-rules.md # Stage-to-stage data continuity
    ├── quality/                 # DoD checklists + readiness engine
    └── templates/               # Feature list, research prompt, spec templates
```

---

## Command Reference

| Command | Stage | What It Does |
|---------|-------|-------------|
| `/romeo-start` | Setup | Initialize project, capture business context |
| `/romeo-status` | Status | Show progress dashboard |
| `/romeo-baseline` | 1 | Generate Baseline Spec (problem, users, capabilities) |
| `/romeo-research` | 2a | Market research report |
| `/romeo-deep-research` | 2b | Deep research across 8 landscapes |
| `/romeo-initial-prd` | 3 | Initial PRD, feature list, flows, UX, prototype prompts |
| `/romeo-prototype` | 4 | Prototype specs (MVP + Future), data model |
| `/romeo-validate-prototype` | 5 | Evaluate prototype against goals |
| `/romeo-iterate-prototype` | 6 | Generate iteration plan from validation |
| `/romeo-final-prd` | 7 | Comprehensive, development-ready PRD |
| `/romeo-handoff` | 8 | Generate agentOS 2-compatible handoff files |

---

## Who Is This For

- **Product Managers** who want a structured, repeatable scoping process with built-in quality gates
- **PM teams** who want consistency across projects without limiting individual PM judgment
- **Organizations** bridging product scoping to spec-driven development (agentOS 2)

---

## Built By

**Moveo** — AI-powered product and engineering tools.

Romeo Baltio is part of Moveo's vision to make every PM 10x more effective by pairing them with AI agents that bring senior-level product and engineering knowledge to every scoping conversation.
