# Cynefin Dynamics — VS Code Copilot Environment

A `.github` customization template that uses the [Cynefin Dynamics](https://cynefin.io/wiki/Cynefin_Dynamics) framework to guide digital product development — from early idea validation through to scaled production.

Every perspective (business, customer, design, development, data, cloud) is always present. Every decision is documented. Every experiment is tracked.

## What is this?

This is a **GitHub Copilot (VS Code) project template** that provides custom agents, skills, instructions, and handoff workflows for building digital products using the Cynefin sense-making framework. Instead of jumping straight to coding, the environment guides you through:

1. **Understanding where you are** — mapping each area of your project to a Cynefin domain
2. **Working the right way** — probing when uncertain, building when confident, automating when clear
3. **Hearing all perspectives** — mob-style collaboration with 6 specialist viewpoints
4. **Documenting everything** — decisions, experiments, and learnings are always recorded

## Quick Start

### Prerequisites

- [VS Code](https://code.visualstudio.com/) with [GitHub Copilot](https://github.com/features/copilot) extension installed

### Setup

1. Copy this repository (or the `.github/` and `docs/` folders) into your project root
2. Open the project in VS Code
3. Open Copilot Chat and start with `/status` to see the empty Cynefin map
4. Use `/assess [your first topic]` to begin mapping your project

### First Session Example

```
You: /status
→ Shows an empty Cynefin map, ready to start

You: /assess core value proposition
→ Navigator evaluates the domain (likely Complex — still unvalidated)
→ Cynefin map is updated
→ Recommends next steps (probably /probe or /mob)

You: /mob should we build a B2B SaaS or a marketplace?
→ All 6 perspectives weigh in
→ Conflicts and consensus are surfaced
→ Action items generated

You: /probe users will pay €50/month for automated reporting
→ Designs a safe-to-fail experiment
→ Documented in docs/probes/

You: /decide use Next.js for frontend
→ Records an ADR in docs/decisions/
→ Includes context, alternatives, and consequences
```

## Commands

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `/status` | Show Cynefin map and project overview | Start of every session |
| `/assess [topic]` | Evaluate which Cynefin domain a topic belongs to | Starting work on anything new |
| `/probe [hypothesis]` | Design a safe-to-fail experiment | In Complex domain — testing unknowns |
| `/validate [area]` | Check if a pattern is stable enough to transition | At inflection points (Alpha/Beta/Delta) |
| `/decide [title]` | Record a decision as an ADR | Any significant decision |
| `/mob [topic]` | Get all 6 perspectives on a topic | Major decisions, architecture, pivots |
| `/retro` | Retrospective — review progress and learnings | Regularly, or when feeling stuck |
| `/pivot [reason]` | Trigger radical rethinking (Red Line dynamic) | When current direction is fundamentally wrong |

## How It Works

### The Cynefin Domains

Your project areas move through domains as understanding grows:

```
┌─────────────────────────────┬─────────────────────────────┐
│                             │                             │
│   COMPLEX                   │   COMPLICATED               │
│   "We don't know yet"       │   "Experts can figure out"  │
│                             │                             │
│   → Run safe-to-fail probes │   → Build with expertise    │
│   → Multiple experiments    │   → Architecture decisions  │
│   → Embrace failure         │   → Governing constraints   │
│                             │                             │
│         ──── Alpha ────────►│                             │
│                             │                             │
├─ ─ ─ ─ APORIA ─ ─ ─ ─ ─ ─ ─┼─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ─ ┤
│                             │                             │
│   CHAOTIC                   │   CLEAR                     │
│   "Nothing makes sense"     │   "We know exactly how"     │
│                             │                             │
│   → Act first, analyze later│   → Standardize & automate  │
│   → Radical rethinking      │   → CI/CD, IaC, runbooks    │
│                             │                             │
│                             │◄──── Delta ─────────────────│
│                             │                             │
└─────────────────────────────┴─────────────────────────────┘
```

### Three Dynamic Lines

- **Blue Line** — The standard maturation path: Complex → Complicated → Clear
- **Purple Line** — Continuous innovation cycle: Complex ↔ Aporetic (for areas that never stabilize)
- **Red Line** — Radical change: triggered when stability can't be confirmed, dives through Chaos back to Complex

### Inflection Points

| Point | Transition | Key Question |
|-------|-----------|--------------|
| **Alpha** | Complex → Complicated | Are probes producing consistent, repeatable results? |
| **Beta** | Complicated → Clear? | Has the solution stabilized? Any exceptions still appearing? |
| **Delta** | Complicated → Clear (commit) | Is this truly stable enough to standardize? High-cost commitment. |
| **Gamma** | Aporetic → Redistribution | How do we decompose, recompose, and find new possibilities? |

## Agents & Handoff Workflow

Agents guide you through the Cynefin workflow via **handoffs** — clickable buttons that transition you to the next appropriate agent:

```
@navigator ──→ assesses domain ──→ hands off to:
  ├── @probe-runner ──→ experiments ──→ @pattern-validator
  ├── @pattern-validator ──→ validates ──→ @solution-builder
  ├── @solution-builder ──→ builds ──→ @standardizer
  ├── @standardizer ──→ automates
  ├── @disruptor ──→ rethinks ──→ @probe-runner
  └── @mob-facilitator ──→ all perspectives
```

### Domain Agents (How to Work)

| Agent | Domain | Role |
|-------|--------|------|
| `@navigator` | Meta | Assesses Cynefin domain, orchestrates handoffs to the right agent |
| `@probe-runner` | Complex | Designs and runs safe-to-fail experiments |
| `@pattern-validator` | Liminal (Alpha) | Validates whether patterns are genuinely repeatable |
| `@solution-builder` | Complicated | Builds solutions with expert judgment |
| `@standardizer` | Clear | Automates, standardizes, and hardens processes |
| `@disruptor` | Aporetic/Chaotic | Radical rethinking in isolated branches |
| `@mob-facilitator` | All | Orchestrates mob sessions with all 6 perspectives |

### Perspective Agents (What to Consider)

| Agent | Perspective |
|-------|------------|
| `@business-strategist` | Value proposition, business model, market, revenue |
| `@customer-advocate` | User needs, journeys, pain points, Jobs-to-be-Done |
| `@designer` | UX/UI, service design, accessibility, prototyping |
| `@developer` | Architecture, tech choices, code quality, feasibility |
| `@data-specialist` | Data model, analytics, metrics, AI/ML, privacy |
| `@cloud-infra` | Cloud services, infrastructure, scaling, security, cost |

## Project Structure

```
your-project/
├── .github/
│   ├── copilot-instructions.md    # Main Copilot instructions & Cynefin overview
│   ├── agents/                    # 13 agent definitions (.agent.md)
│   │   ├── navigator.agent.md     #   Domain orchestrator with handoffs
│   │   ├── probe-runner.agent.md  #   Complex domain
│   │   ├── pattern-validator.agent.md  # Alpha inflection
│   │   ├── solution-builder.agent.md   # Complicated domain
│   │   ├── standardizer.agent.md  #   Clear domain
│   │   ├── disruptor.agent.md     #   Aporetic/Chaotic
│   │   ├── mob-facilitator.agent.md #  All-perspective orchestrator
│   │   ├── business-strategist.agent.md
│   │   ├── customer-advocate.agent.md
│   │   ├── designer.agent.md
│   │   ├── developer.agent.md
│   │   ├── data-specialist.agent.md
│   │   └── cloud-infra.agent.md
│   ├── skills/                    # 8 slash commands (SKILL.md)
│   │   ├── assess/SKILL.md
│   │   ├── probe/SKILL.md
│   │   ├── validate/SKILL.md
│   │   ├── decide/SKILL.md
│   │   ├── mob/SKILL.md
│   │   ├── retro/SKILL.md
│   │   ├── pivot/SKILL.md
│   │   └── status/SKILL.md
│   └── instructions/              # 3 instruction sets (.instructions.md)
│       ├── cynefin-principles.instructions.md
│       ├── documentation.instructions.md
│       └── mob-working.instructions.md
├── docs/
│   ├── cynefin-map.md             # Where each area sits (single source of truth)
│   ├── project-journal.md         # Chronological activity log
│   ├── decisions/                 # Architecture Decision Records
│   │   └── 0000-template.md
│   └── probes/                    # Safe-to-fail experiment docs
│       └── template.md
└── README.md
```

## Core Principles

1. **Never assume the domain.** Always `/assess` first. When in doubt, assume Complex.
2. **No building in Complex.** Only safe-to-fail probes. If the need isn't validated, you're in Complex.
3. **All perspectives matter.** Use `/mob` for significant decisions. Six viewpoints catch blind spots.
4. **Document everything.** If it's not in `docs/`, it didn't happen.
5. **Start with the need.** Every action must trace to a validated need. Needs can be hypotheses.
6. **Dynamics are natural.** Areas move between domains — including backwards. That's reality, not failure.

## Customization

This is a **generic template**. To adapt it for your project:

- **Add agents** — Create new `.agent.md` files in `.github/agents/` for project-specific agents
- **Add skills** — Create new directories in `.github/skills/` for project-specific workflows
- **Add instructions** — Create `.instructions.md` files in `.github/instructions/` with `applyTo` glob patterns for path-specific rules
- **Tune tools** — Adjust `tools:` in agent frontmatter to control what each agent can do
- **Configure handoffs** — Edit `handoffs:` in agent frontmatter to customize agent-to-agent transitions
- **Add MCP servers** — Configure MCP tools for GitHub, Figma, Slack, databases etc.

## Further Reading

- [Cynefin Dynamics](https://cynefin.io/wiki/Cynefin_Dynamics) — The framework this environment is built on
- [Cynefin Framework](https://cynefin.io/wiki/Cynefin) — Overview of the Cynefin sense-making framework
- [VS Code Copilot Customization](https://code.visualstudio.com/docs/copilot/copilot-customization) — How to customize Copilot in VS Code
- [Agent Skills Open Standard](https://agentskills.io) — Open standard for agent skills (SKILL.md format)

## License

This template is provided as-is for use in your projects. The Cynefin framework is created by Dave Snowden and Cognitive Edge / The Cynefin Co.
